# GetSaveFileAndType(HWND__ *,CLogInfo *,SAVE_TYPE *,ushort *,ulong)

- ea: `0x18001fd74`
- end: `0x18001ffed`
- name: `?GetSaveFileAndType@@YAJPEAUHWND__@@PEAVCLogInfo@@PEAW4SAVE_TYPE@@PEAGK@Z`
- size: `633`
- prototype: `__int64 __fastcall(HWND, struct CLogInfo *, enum SAVE_TYPE *, unsigned __int16 *, unsigned int SizeInWords)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x18000688c`
- `0x1800087bc`

## callees

- `0x180001750`
- `0x180001910`
- `0x18000513c`
- `0x18000536c`
- `0x180016a98`
- `0x180016cd4`
- `0x18001f858`
- `0x18001fd74`
- `0x180020430`
- `0x180021158`
- `0x180022292`
- `0x1800222d0`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18001ff68`
- `msvcrt!wcscat_s` at `0x18001ff68`
- `KERNEL32!DeleteFileW` at `0x18001ffa6`
- `KERNEL32!DeleteFileW` at `0x18001ffa6`

## pseudocode

```c
__int64 __fastcall GetSaveFileAndType(
        HWND a1,
        struct CLogInfo *a2,
        enum SAVE_TYPE *a3,
        unsigned __int16 *a4,
        unsigned int SizeInWords)
{
  __int64 v9; // rdx
  int Str; // edi
  unsigned __int16 *DisplayName; // rax
  __int64 v12; // r9
  __int64 v13; // rax
  __int64 v14; // rdx
  _QWORD *v15; // rax
  int v16; // r8d
  wchar_t v17; // cx
  _WORD *v18; // rax
  __int64 v19; // rcx
  wchar_t *v20; // rax
  int i; // r8d
  __int64 v22; // rdx
  __int64 v23; // r9
  __int64 v24; // rax
  __int64 v25; // rdx
  const WCHAR *v26; // rcx
  int v28; // [rsp+20h] [rbp-E0h] BYREF
  HWND v29; // [rsp+28h] [rbp-D8h]
  HINSTANCE v30; // [rsp+30h] [rbp-D0h]
  wchar_t *v31; // [rsp+38h] [rbp-C8h]
  int v32; // [rsp+4Ch] [rbp-B4h]
  unsigned __int16 *v33; // [rsp+50h] [rbp-B0h]
  unsigned int v34; // [rsp+58h] [rbp-A8h]
  _QWORD *v35; // [rsp+78h] [rbp-88h]
  int v36; // [rsp+80h] [rbp-80h]
  const wchar_t *v37; // [rsp+88h] [rbp-78h]
  LPCWSTR lpFileName[4]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v39[4]; // [rsp+E0h] [rbp-20h] BYREF
  wchar_t Destination[200]; // [rsp+100h] [rbp+0h] BYREF

  memset_0(&v28, 0, 0x98u);
  std::wstring::wstring(v39);
  memset_0(Destination, 0, sizeof(Destination));
  Str = LoadStr(0xFEu, Destination, 0xC8u, 0);
  if ( Str >= 0 )
  {
    DisplayName = CLogInfo::GetDisplayName(a2);
    v13 = FormatString(lpFileName, 253, DisplayName, v12);
    std::wstring::operator=(v39, v13);
    LOBYTE(v14) = 1;
    std::wstring::_Tidy(lpFileName, v14, 0);
    *a4 = 0;
    memset_0(&v28, 0, 0x98u);
    v28 = 152;
    v29 = a1;
    v30 = g_hinst;
    v31 = Destination;
    v32 = 1;
    v33 = a4;
    v34 = SizeInWords;
    v37 = L"EVT";
    v15 = v39;
    if ( v39[3] >= 8u )
      v15 = (_QWORD *)v39[0];
    v35 = v15;
    v36 = 526350;
    if ( (unsigned int)IsolationAwareGetSaveFileNameW(&v28) )
    {
      v16 = v32;
      *(_DWORD *)a3 = v32;
      v17 = *a4;
      if ( !*a4 )
        goto LABEL_15;
      v18 = 0;
      v9 = (__int64)a4;
      do
      {
        if ( v17 == 92 )
        {
          v18 = 0;
        }
        else if ( v17 == 46 )
        {
          v18 = (_WORD *)v9;
        }
        v9 += 2;
        v17 = *(_WORD *)v9;
      }
      while ( *(_WORD *)v9 );
      if ( !v18 || !*v18 )
      {
LABEL_15:
        v19 = -1;
        v9 = -1;
        do
          ++v9;
        while ( a4[v9] );
        if ( (unsigned __int64)SizeInWords - v9 > 4 )
        {
          v20 = Destination;
          for ( i = v16 - 1; i; --i )
          {
            v22 = -1;
            do
              ++v22;
            while ( v20[v22] );
            v23 = (__int64)&v20[v22 + 1];
            v24 = -1;
            do
              ++v24;
            while ( *(_WORD *)(v23 + 2 * v24) );
            v20 = (wchar_t *)(v23 + 2 * (v24 + 1));
          }
          do
            ++v19;
          while ( v20[v19] );
          wcscat_s(a4, SizeInWords, &v20[v19 + 2]);
        }
      }
      if ( *(_DWORD *)a3 == 1 )
      {
        std::wstring::wstring(lpFileName, a4);
        if ( (*((_BYTE *)a2 + 24) & 1) != 0 || (Str = CLogInfo::ProcessBackupFilename(a2, a4), Str >= 0) )
        {
          v26 = (const WCHAR *)lpFileName;
          if ( lpFileName[3] >= (LPCWSTR)8 )
            v26 = lpFileName[0];
          DeleteFileW(v26);
        }
        LOBYTE(v25) = 1;
        std::wstring::_Tidy(lpFileName, v25, 0);
      }
    }
    else
    {
      Str = 1;
    }
  }
  LOBYTE(v9) = 1;
  std::wstring::_Tidy(v39, v9, 0);
  return (unsigned int)Str;
}

```

## disassembly

```asm
0x18001fd74  push    rbp
0x18001fd76  push    rbx
0x18001fd77  push    rsi
0x18001fd78  push    rdi
0x18001fd79  push    r12
0x18001fd7b  push    r14
0x18001fd7d  push    r15
0x18001fd7f  lea     rbp, [rsp-1A0h]
0x18001fd87  sub     rsp, 2A0h
0x18001fd8e  mov     rax, cs:__security_cookie
0x18001fd95  xor     rax, rsp
0x18001fd98  mov     [rbp+1D0h+var_40], rax
0x18001fd9f  mov     rbx, r9
0x18001fda2  mov     r15, r8
0x18001fda5  mov     rsi, rdx
0x18001fda8  mov     r14, rcx
0x18001fdab  xor     edx, edx; Val
0x18001fdad  mov     r8d, 98h; Size
0x18001fdb3  lea     rcx, [rsp+2D0h+var_2B0]; void *
0x18001fdb8  call    memset_0
0x18001fdbd  lea     rcx, [rbp+1D0h+var_1F0]
0x18001fdc1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001fdc6  nop
0x18001fdc7  xor     edx, edx; Val
0x18001fdc9  mov     r8d, 190h; Size
0x18001fdcf  lea     rcx, [rbp+1D0h+Destination]; void *
0x18001fdd3  call    memset_0
0x18001fdd8  xor     r9d, r9d; Source
0x18001fddb  mov     r8d, 0C8h; SizeInWords
0x18001fde1  lea     rdx, [rbp+1D0h+Destination]; Destination
0x18001fde5  lea     ecx, [r8+36h]; uID
0x18001fde9  call    ?LoadStr@@YAJKPEAGKPEBG@Z; LoadStr(ulong,ushort *,ulong,ushort const *)
0x18001fdee  mov     edi, eax
0x18001fdf0  xor     r12d, r12d
0x18001fdf3  test    eax, eax
0x18001fdf5  js      loc_18001FFBC
0x18001fdfb  mov     rcx, rsi; this
0x18001fdfe  call    ?GetDisplayName@CLogInfo@@QEAAPEAGXZ; CLogInfo::GetDisplayName(void)
0x18001fe03  mov     r8, rax
0x18001fe06  mov     edx, 0FDh
0x18001fe0b  lea     rcx, [rbp+1D0h+lpFileName]
0x18001fe0f  call    ?FormatString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IZZ; FormatString(uint,...)
0x18001fe14  mov     rdx, rax
0x18001fe17  lea     rcx, [rbp+1D0h+var_1F0]
0x18001fe1b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001fe20  xor     r8d, r8d
0x18001fe23  mov     dl, 1
0x18001fe25  lea     rcx, [rbp+1D0h+lpFileName]
0x18001fe29  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001fe2e  mov     [rbx], r12w
0x18001fe32  xor     edx, edx; Val
0x18001fe34  mov     r8d, 98h; Size
0x18001fe3a  lea     rcx, [rsp+2D0h+var_2B0]; void *
0x18001fe3f  call    memset_0
0x18001fe44  mov     [rsp+2D0h+var_2B0], 98h
0x18001fe4c  mov     [rsp+2D0h+var_2A8], r14
0x18001fe51  mov     rax, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinst
0x18001fe58  mov     [rsp+2D0h+var_2A0], rax
0x18001fe5d  lea     rax, [rbp+1D0h+Destination]
0x18001fe61  mov     [rsp+2D0h+var_298], rax
0x18001fe66  mov     [rsp+2D0h+var_284], 1
0x18001fe6e  mov     [rsp+2D0h+var_280], rbx
0x18001fe73  mov     r14d, dword ptr [rbp+1D0h+SizeInWords]
0x18001fe7a  mov     [rsp+2D0h+var_278], r14d
0x18001fe7f  lea     rax, aEvt; "EVT"
0x18001fe86  mov     [rbp+1D0h+var_248], rax
0x18001fe8a  lea     rax, [rbp+1D0h+var_1F0]
0x18001fe8e  cmp     [rbp+1D0h+var_1D8], 8
0x18001fe93  cmovnb  rax, [rbp+1D0h+var_1F0]
0x18001fe98  mov     [rsp+2D0h+var_258], rax
0x18001fe9d  mov     [rbp+1D0h+var_250], 8080Eh
0x18001fea4  lea     rcx, [rsp+2D0h+var_2B0]
0x18001fea9  call    IsolationAwareGetSaveFileNameW
0x18001feae  test    eax, eax
0x18001feb0  jnz     short loc_18001FEBA
0x18001feb2  lea     edi, [rax+1]
0x18001feb5  jmp     loc_18001FFBC
0x18001feba  mov     r8d, [rsp+2D0h+var_284]
0x18001febf  mov     [r15], r8d
0x18001fec2  movzx   ecx, word ptr [rbx]
0x18001fec5  test    cx, cx
0x18001fec8  jz      short loc_18001FEFA
0x18001feca  mov     rax, r12
0x18001fecd  mov     rdx, rbx
0x18001fed0  cmp     cx, 5Ch ; '\'
0x18001fed4  jnz     short loc_18001FEDB
0x18001fed6  mov     rax, r12
0x18001fed9  jmp     short loc_18001FEE3
0x18001fedb  cmp     cx, 2Eh ; '.'
0x18001fedf  cmovz   rax, rdx
0x18001fee3  add     rdx, 2
0x18001fee7  movzx   ecx, word ptr [rdx]
0x18001feea  test    cx, cx
0x18001feed  jnz     short loc_18001FED0
0x18001feef  test    rax, rax
0x18001fef2  jz      short loc_18001FEFA
0x18001fef4  cmp     [rax], r12w
0x18001fef8  jnz     short loc_18001FF6E
0x18001fefa  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001fefe  mov     rdx, rcx
0x18001ff01  inc     rdx
0x18001ff04  cmp     [rbx+rdx*2], r12w
0x18001ff09  jnz     short loc_18001FF01
0x18001ff0b  mov     rax, r14
0x18001ff0e  sub     rax, rdx
0x18001ff11  cmp     rax, 4
0x18001ff15  jbe     short loc_18001FF6E
0x18001ff17  lea     rax, [rbp+1D0h+Destination]
0x18001ff1b  sub     r8d, 1
0x18001ff1f  jz      short loc_18001FF50
0x18001ff21  mov     rdx, rcx
0x18001ff24  inc     rdx
0x18001ff27  cmp     [rax+rdx*2], r12w
0x18001ff2c  jnz     short loc_18001FF24
0x18001ff2e  lea     r9, [rax+2]
0x18001ff32  lea     r9, [r9+rdx*2]
0x18001ff36  mov     rax, rcx
0x18001ff39  inc     rax
0x18001ff3c  cmp     [r9+rax*2], r12w
0x18001ff41  jnz     short loc_18001FF39
0x18001ff43  inc     rax
0x18001ff46  lea     rax, [r9+rax*2]
0x18001ff4a  add     r8d, 0FFFFFFFFh
0x18001ff4e  jnz     short loc_18001FF21
0x18001ff50  inc     rcx
0x18001ff53  cmp     [rax+rcx*2], r12w
0x18001ff58  jnz     short loc_18001FF50
0x18001ff5a  add     rcx, 2
0x18001ff5e  lea     r8, [rax+rcx*2]; Source
0x18001ff62  mov     rdx, r14; SizeInWords
0x18001ff65  mov     rcx, rbx; Destination
0x18001ff68  call    cs:__imp_wcscat_s
0x18001ff6e  cmp     dword ptr [r15], 1
0x18001ff72  jnz     short loc_18001FFBC
0x18001ff74  mov     rdx, rbx
0x18001ff77  lea     rcx, [rbp+1D0h+lpFileName]
0x18001ff7b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001ff80  nop
0x18001ff81  test    byte ptr [rsi+18h], 1
0x18001ff85  jnz     short loc_18001FF98
0x18001ff87  mov     rdx, rbx; unsigned __int16 *
0x18001ff8a  mov     rcx, rsi; this
0x18001ff8d  call    ?ProcessBackupFilename@CLogInfo@@QEAAJPEAG@Z; CLogInfo::ProcessBackupFilename(ushort *)
0x18001ff92  mov     edi, eax
0x18001ff94  test    eax, eax
0x18001ff96  js      short loc_18001FFAD
0x18001ff98  lea     rcx, [rbp+1D0h+lpFileName]
0x18001ff9c  cmp     [rbp+1D0h+var_1F8], 8
0x18001ffa1  cmovnb  rcx, [rbp+1D0h+lpFileName]; lpFileName
0x18001ffa6  call    cs:__imp_DeleteFileW
0x18001ffac  nop
0x18001ffad  xor     r8d, r8d
0x18001ffb0  mov     dl, 1
0x18001ffb2  lea     rcx, [rbp+1D0h+lpFileName]
0x18001ffb6  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001ffbb  nop
0x18001ffbc  xor     r8d, r8d
0x18001ffbf  mov     dl, 1
0x18001ffc1  lea     rcx, [rbp+1D0h+var_1F0]
0x18001ffc5  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001ffca  mov     eax, edi
0x18001ffcc  mov     rcx, [rbp+1D0h+var_40]
0x18001ffd3  xor     rcx, rsp; StackCookie
0x18001ffd6  call    __security_check_cookie
0x18001ffdb  add     rsp, 2A0h
0x18001ffe2  pop     r15
0x18001ffe4  pop     r14
0x18001ffe6  pop     r12
0x18001ffe8  pop     rdi
0x18001ffe9  pop     rsi
0x18001ffea  pop     rbx
0x18001ffeb  pop     rbp
0x18001ffec  retn
```
