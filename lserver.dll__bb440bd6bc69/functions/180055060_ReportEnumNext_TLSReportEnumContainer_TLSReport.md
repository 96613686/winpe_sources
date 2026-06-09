# ReportEnumNext(_TLSReportEnumContainer *,_TLSReport *)

- ea: `0x180055060`
- end: `0x18005539c`
- name: `?ReportEnumNext@@YAKPEAU_TLSReportEnumContainer@@PEAU_TLSReport@@@Z`
- size: `828`
- prototype: `unsigned int(struct _TLSReportEnumContainer *, struct _TLSReport *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180017960`

## callees

- `0x180002ce0`
- `0x180002d26`
- `0x180005665`
- `0x18000cff0`
- `0x18000d060`
- `0x18001ebc0`
- `0x180055060`
- `0x1800a0fb0`

## import_xrefs

- `msvcrt!_wtol` at `0x1800551b1`
- `msvcrt!_wtol` at `0x1800551dd`
- `msvcrt!_wtol` at `0x18005525f`
- `msvcrt!_wtol` at `0x180055287`
- `msvcrt!_wtol` at `0x1800551b1`
- `msvcrt!_wtol` at `0x1800551dd`
- `msvcrt!_wtol` at `0x18005525f`
- `msvcrt!_wtol` at `0x180055287`
- `msvcrt!fgetws` at `0x18005517d`
- `msvcrt!fgetws` at `0x18005517d`
- `msvcrt!_errno` at `0x180055353`
- `msvcrt!_errno` at `0x180055353`
- `msvcrt!_wfopen` at `0x180055142`
- `msvcrt!_wfopen` at `0x180055142`
- `msvcrt!fclose` at `0x180055104`
- `msvcrt!fclose` at `0x180055345`
- `msvcrt!fclose` at `0x180055104`
- `msvcrt!fclose` at `0x180055345`
- `KERNEL32!FindNextFileW` at `0x1800552f6`
- `KERNEL32!FindNextFileW` at `0x1800552f6`
- `KERNEL32!GetLastError` at `0x180055321`
- `KERNEL32!GetLastError` at `0x180055321`

## pseudocode

```c
__int64 __fastcall ReportEnumNext(struct _TLSReportEnumContainer *a1, struct _TLSReport *a2)
{
  DWORD LastError; // edi
  FILE *v5; // rsi
  int v6; // ebx
  wchar_t **v7; // r8
  wchar_t *v8; // rax
  wchar_t **v9; // r8
  wchar_t *v10; // rax
  wchar_t **v11; // r8
  wchar_t *v12; // rax
  wchar_t **v13; // r8
  wchar_t *v14; // rax
  wchar_t **v15; // r8
  wchar_t *v16; // rax
  wchar_t **v17; // r8
  wchar_t *v18; // rax
  wchar_t **v19; // r8
  wchar_t *v20; // rax
  unsigned int v21; // r11d
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF
  int Src; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int16 v25[255]; // [rsp+284h] [rbp+184h] BYREF
  unsigned __int16 v26[255]; // [rsp+482h] [rbp+382h] BYREF
  int v27; // [rsp+680h] [rbp+580h]
  unsigned __int16 v28[256]; // [rsp+684h] [rbp+584h] BYREF
  int v29; // [rsp+884h] [rbp+784h]
  unsigned __int16 v30[258]; // [rsp+888h] [rbp+788h] BYREF
  int v31; // [rsp+A8Ch] [rbp+98Ch]
  wchar_t FileName; // [rsp+A90h] [rbp+990h] BYREF
  _BYTE v33[526]; // [rsp+A92h] [rbp+992h] BYREF
  wchar_t Buffer[256]; // [rsp+CA0h] [rbp+BA0h] BYREF

  FileName = 0;
  LastError = 0;
  memset_0(v33, 0, 0x206u);
  v5 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !a1 || !a2 )
    return 87;
  if ( *(_QWORD *)a1 == -1 || !*((_WORD *)a1 + 4) )
    return 1074790400;
  while ( 1 )
  {
    v6 = 1;
    if ( v5 )
      fclose(v5);
    StringCchPrintfW(&FileName, 0x104u, L"%s%s", &g_szReportDir, (char *)a1 + 8);
    v5 = _wfopen(&FileName, L"rt");
    if ( !v5 )
      return (DWORD)*_errno();
    memset_0(&Src, 0, 0x810u);
    if ( fgetws(Buffer, 255, v5) )
    {
      v8 = wcstok_mvcrt_legacy_two_parameter_form(Buffer, L",", v7);
      if ( v8 )
      {
        v31 = _wtol(v8);
        v10 = wcstok_mvcrt_legacy_two_parameter_form(0, L",", v9);
        if ( v10 )
        {
          Src = _wtol(v10);
          v12 = wcstok_mvcrt_legacy_two_parameter_form(0, L",", v11);
          if ( v12 )
          {
            StringCchCopyW(v25, 0xFFu, v12);
            v14 = wcstok_mvcrt_legacy_two_parameter_form(0, L",", v13);
            if ( v14 )
            {
              StringCchCopyW(v26, 0xFFu, v14);
              v16 = wcstok_mvcrt_legacy_two_parameter_form(0, L",", v15);
              if ( v16 )
              {
                v29 = _wtol(v16);
                v18 = wcstok_mvcrt_legacy_two_parameter_form(0, L",", v17);
                if ( v18 )
                {
                  v27 = _wtol(v18);
                  v20 = wcstok_mvcrt_legacy_two_parameter_form(0, L",", v19);
                  if ( v20 )
                  {
                    StringCchCopyW(v28, 0xFFu, v20);
                    StringCchCopyW(v30, v21, (const unsigned __int16 *)a1 + 4);
                    memcpy_0(a2, &Src, 0x810u);
                    v6 = 0;
                  }
                }
              }
            }
          }
        }
      }
    }
    if ( !FindNextFileW(*(HANDLE *)a1, &FindFileData) )
    {
      LastError = GetLastError();
      if ( LastError == 18 )
      {
        *((_WORD *)a1 + 4) = 0;
        LastError = v6 != 0 ? 0x40100000 : 0;
      }
LABEL_22:
      fclose(v5);
      return LastError;
    }
    StringCbCopyW((unsigned __int16 *)a1 + 4, 0x208u, FindFileData.cFileName);
    if ( !v6 )
      goto LABEL_22;
  }
}

```

## disassembly

```asm
0x180055060  mov     [rsp-8+arg_10], rbx
0x180055065  push    rbp
0x180055066  push    rsi
0x180055067  push    rdi
0x180055068  push    r12
0x18005506a  push    r13
0x18005506c  push    r14
0x18005506e  push    r15
0x180055070  lea     rbp, [rsp-0DB0h]
0x180055078  sub     rsp, 0EB0h
0x18005507f  mov     rax, cs:__security_cookie
0x180055086  xor     rax, rsp
0x180055089  mov     [rbp+0DE0h+var_40], rax
0x180055090  mov     r12, rdx
0x180055093  mov     r15, rcx
0x180055096  xor     r13d, r13d
0x180055099  lea     rcx, [rbp+0DE0h+var_44E]; void *
0x1800550a0  xor     edx, edx; Val
0x1800550a2  mov     [rbp+0DE0h+FileName], r13w
0x1800550aa  mov     r8d, 206h; Size
0x1800550b0  mov     edi, r13d
0x1800550b3  call    memset_0
0x1800550b8  xor     edx, edx; Val
0x1800550ba  lea     rcx, [rsp+0EE0h+FindFileData]; void *
0x1800550bf  mov     r8d, 250h; Size
0x1800550c5  mov     esi, r13d
0x1800550c8  call    memset_0
0x1800550cd  test    r15, r15
0x1800550d0  jz      loc_18005536C
0x1800550d6  test    r12, r12
0x1800550d9  jz      loc_18005536C
0x1800550df  cmp     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x1800550e3  jz      loc_180055365
0x1800550e9  lea     r14, [r15+8]
0x1800550ed  cmp     r13w, [r14]
0x1800550f1  jz      loc_180055365
0x1800550f7  mov     ebx, 1
0x1800550fc  test    rsi, rsi
0x1800550ff  jz      short loc_180055110
0x180055101  mov     rcx, rsi; Stream
0x180055104  call    cs:__imp_fclose
0x18005510b  nop     dword ptr [rax+rax+00h]
0x180055110  lea     r9, ?g_szReportDir@@3PAGA; ushort near * g_szReportDir
0x180055117  mov     [rsp+0EE0h+var_EC0], r14
0x18005511c  lea     r8, aSS_1; "%s%s"
0x180055123  mov     edx, 104h; unsigned __int64
0x180055128  lea     rcx, [rbp+0DE0h+FileName]; unsigned __int16 *
0x18005512f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180055134  lea     rdx, aRt; "rt"
0x18005513b  lea     rcx, [rbp+0DE0h+FileName]; FileName
0x180055142  call    cs:__imp__wfopen
0x180055149  nop     dword ptr [rax+rax+00h]
0x18005514e  mov     rsi, rax
0x180055151  test    rax, rax
0x180055154  jz      loc_180055353
0x18005515a  xor     edx, edx; Val
0x18005515c  lea     rcx, [rbp+0DE0h+Src]; void *
0x180055163  mov     r8d, 810h; Size
0x180055169  call    memset_0
0x18005516e  mov     r8, rsi; Stream
0x180055171  lea     rcx, [rbp+0DE0h+Buffer]; Buffer
0x180055178  mov     edx, 0FFh; BufferCount
0x18005517d  call    cs:__imp_fgetws
0x180055184  nop     dword ptr [rax+rax+00h]
0x180055189  test    rax, rax
0x18005518c  jz      loc_1800552EE
0x180055192  lea     rdx, asc_1800BA394; ","
0x180055199  lea     rcx, [rbp+0DE0h+Buffer]; String
0x1800551a0  call    wcstok_mvcrt_legacy_two_parameter_form
0x1800551a5  test    rax, rax
0x1800551a8  jz      loc_1800552EE
0x1800551ae  mov     rcx, rax; String
0x1800551b1  call    cs:__imp__wtol
0x1800551b8  nop     dword ptr [rax+rax+00h]
0x1800551bd  lea     rdx, asc_1800BA394; ","
0x1800551c4  xor     ecx, ecx; String
0x1800551c6  mov     [rbp+0DE0h+var_454], eax
0x1800551cc  call    wcstok_mvcrt_legacy_two_parameter_form
0x1800551d1  test    rax, rax
0x1800551d4  jz      loc_1800552EE
0x1800551da  mov     rcx, rax; String
0x1800551dd  call    cs:__imp__wtol
0x1800551e4  nop     dword ptr [rax+rax+00h]
0x1800551e9  lea     rdx, asc_1800BA394; ","
0x1800551f0  xor     ecx, ecx; String
0x1800551f2  mov     [rbp+0DE0h+Src], eax
0x1800551f8  call    wcstok_mvcrt_legacy_two_parameter_form
0x1800551fd  test    rax, rax
0x180055200  jz      loc_1800552EE
0x180055206  mov     r8, rax; unsigned __int16 *
0x180055209  lea     rcx, [rbp+0DE0h+var_C5C]; unsigned __int16 *
0x180055210  mov     edx, 0FFh; unsigned __int64
0x180055215  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005521a  lea     rdx, asc_1800BA394; ","
0x180055221  xor     ecx, ecx; String
0x180055223  call    wcstok_mvcrt_legacy_two_parameter_form
0x180055228  test    rax, rax
0x18005522b  jz      loc_1800552EE
0x180055231  mov     r8, rax; unsigned __int16 *
0x180055234  lea     rcx, [rbp+0DE0h+var_A5E]; unsigned __int16 *
0x18005523b  mov     edx, 0FFh; unsigned __int64
0x180055240  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180055245  lea     rdx, asc_1800BA394; ","
0x18005524c  xor     ecx, ecx; String
0x18005524e  call    wcstok_mvcrt_legacy_two_parameter_form
0x180055253  test    rax, rax
0x180055256  jz      loc_1800552EE
0x18005525c  mov     rcx, rax; String
0x18005525f  call    cs:__imp__wtol
0x180055266  nop     dword ptr [rax+rax+00h]
0x18005526b  lea     rdx, asc_1800BA394; ","
0x180055272  xor     ecx, ecx; String
0x180055274  mov     [rbp+0DE0h+var_65C], eax
0x18005527a  call    wcstok_mvcrt_legacy_two_parameter_form
0x18005527f  test    rax, rax
0x180055282  jz      short loc_1800552EE
0x180055284  mov     rcx, rax; String
0x180055287  call    cs:__imp__wtol
0x18005528e  nop     dword ptr [rax+rax+00h]
0x180055293  lea     rdx, asc_1800BA394; ","
0x18005529a  xor     ecx, ecx; String
0x18005529c  mov     [rbp+0DE0h+var_860], eax
0x1800552a2  call    wcstok_mvcrt_legacy_two_parameter_form
0x1800552a7  test    rax, rax
0x1800552aa  jz      short loc_1800552EE
0x1800552ac  mov     r11d, 0FFh
0x1800552b2  lea     rcx, [rbp+0DE0h+var_85C]; unsigned __int16 *
0x1800552b9  mov     edx, r11d; unsigned __int64
0x1800552bc  mov     r8, rax; unsigned __int16 *
0x1800552bf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800552c4  mov     r8, r14; unsigned __int16 *
0x1800552c7  lea     rcx, [rbp+0DE0h+var_658]; unsigned __int16 *
0x1800552ce  mov     edx, r11d; unsigned __int64
0x1800552d1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800552d6  mov     rcx, r12; void *
0x1800552d9  lea     rdx, [rbp+0DE0h+Src]; Src
0x1800552e0  mov     r8d, 810h; Size
0x1800552e6  call    memcpy_0
0x1800552eb  mov     ebx, r13d
0x1800552ee  mov     rcx, [r15]; hFindFile
0x1800552f1  lea     rdx, [rsp+0EE0h+FindFileData]; lpFindFileData
0x1800552f6  call    cs:__imp_FindNextFileW
0x1800552fd  nop     dword ptr [rax+rax+00h]
0x180055302  test    eax, eax
0x180055304  jz      short loc_180055321
0x180055306  lea     r8, [rsp+0EE0h+FindFileData.cFileName]; unsigned __int16 *
0x18005530b  mov     edx, 208h; unsigned __int64
0x180055310  mov     rcx, r14; unsigned __int16 *
0x180055313  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180055318  test    ebx, ebx
0x18005531a  jz      short loc_180055342
0x18005531c  jmp     loc_1800550F7
0x180055321  call    cs:__imp_GetLastError
0x180055328  nop     dword ptr [rax+rax+00h]
0x18005532d  mov     edi, eax
0x18005532f  cmp     eax, 12h
0x180055332  jnz     short loc_180055342
0x180055334  neg     ebx
0x180055336  mov     [r14], r13w
0x18005533a  sbb     edi, edi
0x18005533c  and     edi, 40100000h
0x180055342  mov     rcx, rsi; Stream
0x180055345  call    cs:__imp_fclose
0x18005534c  nop     dword ptr [rax+rax+00h]
0x180055351  jmp     short loc_180055361
0x180055353  call    cs:__imp__errno
0x18005535a  nop     dword ptr [rax+rax+00h]
0x18005535f  mov     edi, [rax]
0x180055361  mov     eax, edi
0x180055363  jmp     short loc_180055371
0x180055365  mov     eax, 40100000h
0x18005536a  jmp     short loc_180055371
0x18005536c  mov     eax, 57h ; 'W'
0x180055371  mov     rcx, [rbp+0DE0h+var_40]
0x180055378  xor     rcx, rsp; StackCookie
0x18005537b  call    __security_check_cookie
0x180055380  mov     rbx, [rsp+0EE0h+arg_10]
0x180055388  add     rsp, 0EB0h
0x18005538f  pop     r15
0x180055391  pop     r14
0x180055393  pop     r13
0x180055395  pop     r12
0x180055397  pop     rdi
0x180055398  pop     rsi
0x180055399  pop     rbp
0x18005539a  retn
```
