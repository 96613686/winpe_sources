# FTP_COMMAND::HandleMDTM(int *)

- ea: `0x1800396b0`
- end: `0x180039b0b`
- name: `?HandleMDTM@FTP_COMMAND@@QEAAXPEAH@Z`
- size: `1115`
- prototype: `void __fastcall(FTP_COMMAND *__hidden this, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003732c`

## callees

- `0x180033c70`
- `0x180036b78`
- `0x1800396b0`
- `0x18003e564`
- `0x18003e980`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `msvcrt!isdigit` at `0x18003971e`
- `msvcrt!isdigit` at `0x18003971e`
- `KERNEL32!SystemTimeToFileTime` at `0x180039976`
- `KERNEL32!SystemTimeToFileTime` at `0x180039976`
- `KERNEL32!GetLastError` at `0x180039980`
- `KERNEL32!GetLastError` at `0x180039980`
- `KERNEL32!FileTimeToSystemTime` at `0x18003986d`
- `KERNEL32!FileTimeToSystemTime` at `0x18003986d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180039804`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180039a53`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180039804`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180039a53`

## pseudocode

```c
void __fastcall FTP_COMMAND::HandleMDTM(FTP_COMMAND *this, int *a2)
{
  _WORD *v2; // r14
  unsigned int v5; // r15d
  __int64 *v6; // rsi
  __int64 v7; // rdi
  int SanitizedFullVirtualPath; // edi
  __int64 v9; // rax
  __int64 *v10; // rcx
  const unsigned __int16 *v11; // r14
  int v12; // eax
  signed int LastError; // eax
  __int64 v14; // rax
  const unsigned __int16 *v15; // r14
  int v16; // eax
  FILETIME FileTime; // [rsp+50h] [rbp-30h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+58h] [rbp-28h] BYREF
  char v19[16]; // [rsp+68h] [rbp-18h] BYREF

  v2 = (_WORD *)*((_QWORD *)this + 43);
  v5 = 0;
  v6 = *(__int64 **)(*((_QWORD *)this + 132) + 1056LL);
  SystemTime = 0;
  FileTime = 0;
  if ( *((_DWORD *)this + 90) )
  {
    LODWORD(v7) = 0;
    if ( *v2 )
    {
      while ( isdigit(LOBYTE(v2[(unsigned int)v7])) )
      {
        v7 = (unsigned int)(v7 + 1);
        if ( !*(_WORD *)(*((_QWORD *)this + 43) + 2 * v7) )
          goto LABEL_10;
      }
      if ( ((_DWORD)v7 == 8 || (_DWORD)v7 == 14) && v2[(unsigned int)v7] == 32 )
        v5 = v7 + 1;
    }
  }
LABEL_10:
  SanitizedFullVirtualPath = FTP_SESSION::GetSanitizedFullVirtualPath(
                               *((FTP_SESSION **)this + 132),
                               (const unsigned __int16 *)(*((_QWORD *)this + 43) + 2LL * v5),
                               *((_DWORD *)this + 90) - v5,
                               (unsigned __int16 **)this + 78);
  if ( SanitizedFullVirtualPath < 0 )
    goto LABEL_16;
  if ( v5 )
  {
    SystemTime = 0;
    SystemTime.wYear = v2[3] + 10 * (v2[2] + 10 * (v2[1] + 10 * *v2)) + 12208;
    SystemTime.wMonth = v2[5] + 10 * v2[4] - 528;
    SystemTime.wDay = v2[7] + 10 * v2[6] - 528;
    if ( v5 == 15 )
    {
      SystemTime.wHour = v2[9] + 10 * v2[8] - 528;
      SystemTime.wMinute = v2[11] + 10 * v2[10] - 528;
      SystemTime.wSecond = v2[13] + 10 * v2[12] - 528;
    }
    if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
      goto LABEL_25;
    SanitizedFullVirtualPath = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, __int64, int, char *, _QWORD, _QWORD, _QWORD))(*v6 + 136))(
                                 v6,
                                 *((_QWORD *)this + 82),
                                 0x40000000,
                                 4,
                                 3,
                                 (char *)this + 1184,
                                 0,
                                 0,
                                 0);
    v10 = v6;
    v9 = *v6;
    if ( SanitizedFullVirtualPath < 0 )
    {
LABEL_14:
      v11 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64 *))(v9 + 208))(v10);
      v12 = (*(__int64 (__fastcall **)(__int64 *))(*v6 + 200))(v6);
      if ( !*((_DWORD *)this + 274) )
      {
        *((_DWORD *)this + 274) = v12;
        STRU::Copy((FTP_COMMAND *)((char *)this + 1112), v11);
        *((_QWORD *)this + 138) = *((_QWORD *)this + 143);
      }
LABEL_16:
      if ( !*((_DWORD *)this + 292) )
        *((_DWORD *)this + 292) = SanitizedFullVirtualPath;
      FTP_COMMAND::WriteResponseWithErrorTextAndLog(this, "550");
      goto LABEL_19;
    }
    SanitizedFullVirtualPath = (*(__int64 (__fastcall **)(__int64 *, FILETIME *, _QWORD))(v9 + 128))(v6, &FileTime, 0);
    v14 = *v6;
    if ( SanitizedFullVirtualPath < 0 )
    {
      v15 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64 *))(v14 + 208))(v6);
      v16 = (*(__int64 (__fastcall **)(__int64 *))(*v6 + 200))(v6);
      if ( !*((_DWORD *)this + 274) )
      {
        *((_DWORD *)this + 274) = v16;
        STRU::Copy((FTP_COMMAND *)((char *)this + 1112), v15);
        *((_QWORD *)this + 138) = *((_QWORD *)this + 143);
      }
      (*(void (__fastcall **)(__int64 *))(*v6 + 184))(v6);
      goto LABEL_16;
    }
    (*(void (__fastcall **)(__int64 *))(v14 + 184))(v6);
LABEL_35:
    SanitizedFullVirtualPath = StringCbPrintfA(
                                 v19,
                                 0xFu,
                                 "%.4hu%.2hu%.2hu%.2hu%.2hu%.2hu",
                                 SystemTime.wYear & 0xFFF,
                                 SystemTime.wMonth & 0xF,
                                 SystemTime.wDay & 0x1F,
                                 SystemTime.wHour & 0x1F,
                                 SystemTime.wMinute & 0x3F,
                                 SystemTime.wSecond & 0x3F);
    if ( SanitizedFullVirtualPath >= 0 )
    {
      FTP_COMMAND::WriteResponseAndLog(this, "213", v19);
      goto LABEL_19;
    }
    goto LABEL_16;
  }
  SanitizedFullVirtualPath = (*(__int64 (__fastcall **)(__int64 *, _QWORD, char *, FILETIME *, _QWORD))(*v6 + 120))(
                               v6,
                               *((_QWORD *)this + 82),
                               (char *)this + 1184,
                               &FileTime,
                               0);
  if ( SanitizedFullVirtualPath < 0 )
  {
    v9 = *v6;
    v10 = v6;
    goto LABEL_14;
  }
  if ( FileTimeToSystemTime(&FileTime, &SystemTime) )
    goto LABEL_35;
LABEL_25:
  LastError = GetLastError();
  SanitizedFullVirtualPath = LastError;
  if ( LastError > 0 )
    SanitizedFullVirtualPath = (unsigned __int16)LastError | 0x80070000;
  if ( SanitizedFullVirtualPath < 0 )
    goto LABEL_16;
LABEL_19:
  *a2 = 1;
}

```

## disassembly

```asm
0x1800396b0  mov     [rsp-38h+arg_10], rbx
0x1800396b5  push    rbp
0x1800396b6  push    rsi
0x1800396b7  push    rdi
0x1800396b8  push    r12
0x1800396ba  push    r13
0x1800396bc  push    r14
0x1800396be  push    r15
0x1800396c0  mov     rbp, rsp
0x1800396c3  sub     rsp, 80h
0x1800396ca  mov     rax, cs:__security_cookie
0x1800396d1  xor     rax, rsp
0x1800396d4  mov     [rbp+var_8], rax
0x1800396d8  mov     rax, [rcx+420h]
0x1800396df  xor     r12d, r12d
0x1800396e2  xorps   xmm0, xmm0
0x1800396e5  mov     r14, [rcx+158h]
0x1800396ec  mov     r13, rdx
0x1800396ef  mov     rbx, rcx
0x1800396f2  mov     r15d, r12d
0x1800396f5  mov     rsi, [rax+420h]
0x1800396fc  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x180039700  mov     qword ptr [rbp+FileTime.dwLowDateTime], r12
0x180039704  cmp     [rcx+168h], r12d
0x18003970b  jbe     short loc_180039756
0x18003970d  mov     edi, r12d
0x180039710  cmp     [r14], r12w
0x180039714  jz      short loc_180039756
0x180039716  mov     r12d, edi
0x180039719  movzx   ecx, byte ptr [r14+r12*2]; C
0x18003971e  call    cs:__imp_isdigit
0x180039724  test    eax, eax
0x180039726  jz      short loc_18003973D
0x180039728  mov     rax, [rbx+158h]
0x18003972f  inc     edi
0x180039731  xor     r12d, r12d
0x180039734  cmp     [rax+rdi*2], r12w
0x180039739  jnz     short loc_180039716
0x18003973b  jmp     short loc_180039756
0x18003973d  cmp     edi, 8
0x180039740  jz      short loc_180039747
0x180039742  cmp     edi, 0Eh
0x180039745  jnz     short loc_180039753
0x180039747  cmp     word ptr [r14+r12*2], 20h ; ' '
0x18003974d  jnz     short loc_180039753
0x18003974f  lea     r15d, [rdi+1]
0x180039753  xor     r12d, r12d
0x180039756  mov     rax, [rbx+158h]
0x18003975d  lea     r9, [rbx+270h]; struct STRU *
0x180039764  mov     r8d, [rbx+168h]
0x18003976b  mov     ecx, r15d
0x18003976e  sub     r8d, r15d; unsigned int
0x180039771  lea     rdx, [rax+rcx*2]; unsigned __int16 *
0x180039775  mov     rcx, [rbx+420h]; this
0x18003977c  call    ?GetSanitizedFullVirtualPath@FTP_SESSION@@QEAAJPEBGKPEAVSTRU@@@Z; FTP_SESSION::GetSanitizedFullVirtualPath(ushort const *,ulong,STRU *)
0x180039781  mov     edi, eax
0x180039783  test    eax, eax
0x180039785  js      loc_180039818
0x18003978b  test    r15d, r15d
0x18003978e  jnz     loc_180039880
0x180039794  mov     rax, [rsi]
0x180039797  lea     r8, [rbx+4A0h]
0x18003979e  mov     rdx, [rbx+290h]
0x1800397a5  lea     r9, [rbp+FileTime]
0x1800397a9  mov     rcx, rsi
0x1800397ac  mov     [rsp+80h+var_60], r12
0x1800397b1  mov     rax, [rax+78h]
0x1800397b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800397ba  mov     edi, eax
0x1800397bc  test    eax, eax
0x1800397be  jns     loc_180039865
0x1800397c4  mov     rax, [rsi]
0x1800397c7  mov     rcx, rsi
0x1800397ca  mov     rax, [rax+0D0h]
0x1800397d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800397d6  mov     rcx, [rsi]
0x1800397d9  mov     r14, rax
0x1800397dc  mov     rax, [rcx+0C8h]
0x1800397e3  mov     rcx, rsi
0x1800397e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800397eb  cmp     [rbx+448h], r12d
0x1800397f2  jnz     short loc_180039818
0x1800397f4  lea     rcx, [rbx+458h]
0x1800397fb  mov     [rbx+448h], eax
0x180039801  mov     rdx, r14
0x180039804  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18003980a  mov     rax, [rbx+478h]
0x180039811  mov     [rbx+450h], rax
0x180039818  cmp     [rbx+490h], r12d
0x18003981f  jnz     short loc_180039827
0x180039821  mov     [rbx+490h], edi
0x180039827  lea     rdx, a550; "550"
0x18003982e  mov     rcx, rbx; this
0x180039831  call    ?WriteResponseWithErrorTextAndLog@FTP_COMMAND@@QEAAJPEBD@Z; FTP_COMMAND::WriteResponseWithErrorTextAndLog(char const *)
0x180039836  mov     dword ptr [r13+0], 1
0x18003983e  mov     rcx, [rbp+var_8]
0x180039842  xor     rcx, rsp; StackCookie
0x180039845  call    __security_check_cookie
0x18003984a  mov     rbx, [rsp+80h+arg_10]
0x180039852  add     rsp, 80h
0x180039859  pop     r15
0x18003985b  pop     r14
0x18003985d  pop     r13
0x18003985f  pop     r12
0x180039861  pop     rdi
0x180039862  pop     rsi
0x180039863  pop     rbp
0x180039864  retn
0x180039865  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x180039869  lea     rcx, [rbp+FileTime]; lpFileTime
0x18003986d  call    cs:__imp_FileTimeToSystemTime
0x180039873  test    eax, eax
0x180039875  jnz     loc_180039A8A
0x18003987b  jmp     loc_180039980
0x180039880  xorps   xmm0, xmm0
0x180039883  mov     edx, 210h
0x180039888  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x18003988c  movzx   ecx, word ptr [r14]
0x180039890  movzx   eax, cx
0x180039893  shl     ax, 2
0x180039897  add     cx, ax
0x18003989a  add     cx, cx
0x18003989d  add     cx, [r14+2]
0x1800398a2  movzx   eax, cx
0x1800398a5  shl     ax, 2
0x1800398a9  add     cx, ax
0x1800398ac  add     cx, cx
0x1800398af  add     cx, [r14+4]
0x1800398b4  movzx   eax, cx
0x1800398b7  shl     ax, 2
0x1800398bb  add     cx, ax
0x1800398be  mov     eax, 2FB0h
0x1800398c3  add     cx, cx
0x1800398c6  add     cx, [r14+6]
0x1800398cb  add     cx, ax
0x1800398ce  mov     [rbp+SystemTime.wYear], cx
0x1800398d2  movzx   ecx, word ptr [r14+8]
0x1800398d7  movzx   eax, cx
0x1800398da  shl     ax, 2
0x1800398de  add     cx, ax
0x1800398e1  add     cx, cx
0x1800398e4  add     cx, [r14+0Ah]
0x1800398e9  sub     cx, dx
0x1800398ec  mov     [rbp+SystemTime.wMonth], cx
0x1800398f0  movzx   ecx, word ptr [r14+0Ch]
0x1800398f5  movzx   eax, cx
0x1800398f8  shl     ax, 2
0x1800398fc  add     cx, ax
0x1800398ff  add     cx, cx
0x180039902  add     cx, [r14+0Eh]
0x180039907  sub     cx, dx
0x18003990a  mov     [rbp+SystemTime.wDay], cx
0x18003990e  cmp     r15d, 0Fh
0x180039912  jnz     short loc_18003996E
0x180039914  movzx   ecx, word ptr [r14+10h]
0x180039919  movzx   eax, cx
0x18003991c  shl     ax, 2
0x180039920  add     cx, ax
0x180039923  add     cx, cx
0x180039926  add     cx, [r14+12h]
0x18003992b  sub     cx, dx
0x18003992e  mov     [rbp+SystemTime.wHour], cx
0x180039932  movzx   ecx, word ptr [r14+14h]
0x180039937  movzx   eax, cx
0x18003993a  shl     ax, 2
0x18003993e  add     cx, ax
0x180039941  add     cx, cx
0x180039944  add     cx, [r14+16h]
0x180039949  sub     cx, dx
0x18003994c  mov     [rbp+SystemTime.wMinute], cx
0x180039950  movzx   ecx, word ptr [r14+18h]
0x180039955  movzx   eax, cx
0x180039958  shl     ax, 2
0x18003995c  add     cx, ax
0x18003995f  add     cx, cx
0x180039962  add     cx, [r14+1Ah]
0x180039967  sub     cx, dx
0x18003996a  mov     [rbp+SystemTime.wSecond], cx
0x18003996e  lea     rdx, [rbp+FileTime]; lpFileTime
0x180039972  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x180039976  call    cs:__imp_SystemTimeToFileTime
0x18003997c  test    eax, eax
0x18003997e  jnz     short loc_1800399A2
0x180039980  call    cs:__imp_GetLastError
0x180039986  mov     edi, eax
0x180039988  test    eax, eax
0x18003998a  jle     short loc_180039995
0x18003998c  movzx   edi, ax
0x18003998f  or      edi, 80070000h
0x180039995  test    edi, edi
0x180039997  jns     loc_180039836
0x18003999d  jmp     loc_180039818
0x1800399a2  mov     rax, [rsi]
0x1800399a5  lea     rcx, [rbx+4A0h]
0x1800399ac  mov     rdx, [rbx+290h]
0x1800399b3  mov     r9d, 4
0x1800399b9  mov     [rsp+80h+var_40], r12
0x1800399be  mov     r8d, 40000000h
0x1800399c4  mov     [rsp+80h+var_48], r12
0x1800399c9  mov     rax, [rax+88h]
0x1800399d0  mov     [rsp+80h+var_50], r12
0x1800399d5  mov     [rsp+80h+var_58], rcx
0x1800399da  mov     rcx, rsi
0x1800399dd  mov     dword ptr [rsp+80h+var_60], 3
0x1800399e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800399ea  mov     edi, eax
0x1800399ec  mov     rcx, rsi
0x1800399ef  mov     rax, [rsi]
0x1800399f2  test    edi, edi
0x1800399f4  js      loc_1800397CA
0x1800399fa  mov     rax, [rax+80h]
0x180039a01  lea     rdx, [rbp+FileTime]
0x180039a05  xor     r8d, r8d
0x180039a08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039a0d  mov     edi, eax
0x180039a0f  mov     rcx, rsi
0x180039a12  mov     rax, [rsi]
0x180039a15  test    edi, edi
0x180039a17  jns     short loc_180039A7E
0x180039a19  mov     rax, [rax+0D0h]
0x180039a20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039a25  mov     rcx, [rsi]
0x180039a28  mov     r14, rax
0x180039a2b  mov     rax, [rcx+0C8h]
0x180039a32  mov     rcx, rsi
0x180039a35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039a3a  cmp     [rbx+448h], r12d
0x180039a41  jnz     short loc_180039A67
0x180039a43  lea     rcx, [rbx+458h]
0x180039a4a  mov     [rbx+448h], eax
0x180039a50  mov     rdx, r14
0x180039a53  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180039a59  mov     rax, [rbx+478h]
0x180039a60  mov     [rbx+450h], rax
0x180039a67  mov     rax, [rsi]
0x180039a6a  mov     rcx, rsi
0x180039a6d  mov     rax, [rax+0B8h]
0x180039a74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039a79  jmp     loc_180039818
0x180039a7e  mov     rax, [rax+0B8h]
0x180039a85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039a8a  movzx   ecx, [rbp+SystemTime.wMinute]
0x180039a8e  mov     edx, 0Fh; unsigned __int64
0x180039a93  movzx   r8d, [rbp+SystemTime.wDay]
0x180039a98  and     ecx, 3Fh
0x180039a9b  movzx   r11d, [rbp+SystemTime.wSecond]
0x180039aa0  and     r8d, 1Fh
0x180039aa4  mov     r10d, dword ptr [rbp+SystemTime.wHour]
0x180039aa8  and     r11d, 3Fh
0x180039aac  movzx   eax, [rbp+SystemTime.wMonth]
0x180039ab0  and     r10d, 1Fh
0x180039ab4  mov     r9d, dword ptr [rbp+SystemTime.wYear]
0x180039ab8  and     eax, 0Fh
0x180039abb  mov     dword ptr [rsp+80h+var_40], r11d
0x180039ac0  and     r9d, 0FFFh
0x180039ac7  mov     dword ptr [rsp+80h+var_48], ecx
0x180039acb  lea     rcx, [rbp+var_18]; char *
0x180039acf  mov     dword ptr [rsp+80h+var_50], r10d
0x180039ad4  mov     dword ptr [rsp+80h+var_58], r8d
0x180039ad9  lea     r8, a4hu2hu2hu2hu2h; "%.4hu%.2hu%.2hu%.2hu%.2hu%.2hu"
0x180039ae0  mov     dword ptr [rsp+80h+var_60], eax
0x180039ae4  call    ?StringCbPrintfA@@YAJPEAD_KPEBDZZ; StringCbPrintfA(char *,unsigned __int64,char const *,...)
0x180039ae9  mov     edi, eax
0x180039aeb  test    eax, eax
0x180039aed  js      loc_180039818
0x180039af3  lea     r8, [rbp+var_18]; char *
0x180039af7  mov     rcx, rbx; this
0x180039afa  lea     rdx, a213; "213"
0x180039b01  call    ?WriteResponseAndLog@FTP_COMMAND@@QEAAJPEBD0ZZ; FTP_COMMAND::WriteResponseAndLog(char const *,char const *,...)
0x180039b06  jmp     loc_180039836
```
