# ReportEnumBegin(_TLSReportEnumContainer * *)

- ea: `0x180054e90`
- end: `0x180055011`
- name: `?ReportEnumBegin@@YAKPEAPEAU_TLSReportEnumContainer@@@Z`
- size: `385`
- prototype: `unsigned int __fastcall(struct _TLSReportEnumContainer **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180017700`

## callees

- `0x180005665`
- `0x18000d060`
- `0x18001ad48`
- `0x18001ebc0`
- `0x180054e90`
- `0x1800a0fb0`

## import_xrefs

- `KERNEL32!CreateDirectoryW` at `0x180054fa4`
- `KERNEL32!CreateDirectoryW` at `0x180054fa4`
- `KERNEL32!FindFirstFileW` at `0x180054f78`
- `KERNEL32!FindFirstFileW` at `0x180054f78`
- `KERNEL32!GetLastError` at `0x180054f8a`
- `KERNEL32!GetLastError` at `0x180054fb4`
- `KERNEL32!GetLastError` at `0x180054f8a`
- `KERNEL32!GetLastError` at `0x180054fb4`
- `KERNEL32!LocalAlloc` at `0x180054f05`
- `KERNEL32!LocalAlloc` at `0x180054f05`

## pseudocode

```c
__int64 __fastcall ReportEnumBegin(struct _TLSReportEnumContainer **a1)
{
  DWORD LastError; // esi
  _WORD *v4; // rbx
  HANDLE FirstFileW; // rax
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-478h] BYREF
  WCHAR FileName[264]; // [rsp+280h] [rbp-228h] BYREF

  LastError = 0;
  if ( a1 )
  {
    v4 = LocalAlloc(0x40u, 0x210u);
    if ( v4 )
    {
      StringCchPrintfW(FileName, 0x104u, L"%s%s*%s", &g_szReportDir, L"PER-USER_", L".dat");
      memset_0(&FindFileData, 0, sizeof(FindFileData));
      FirstFileW = FindFirstFileW(FileName, &FindFileData);
      if ( FirstFileW == (HANDLE)-1LL )
      {
        if ( GetLastError() == 3 && !CreateDirectoryW(&g_szReportDir, 0) )
          LastError = GetLastError();
        *(_QWORD *)v4 = -1;
        v4[4] = 0;
      }
      else
      {
        *(_QWORD *)v4 = FirstFileW;
        StringCbCopyW(v4 + 4, 0x208u, FindFileData.cFileName);
      }
      *a1 = (struct _TLSReportEnumContainer *)v4;
      return LastError;
    }
    else
    {
      return 8;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_36b3ebb3851d38e5219956dcc07ca210_Traceguids);
    return 87;
  }
}

```

## disassembly

```asm
0x180054e90  mov     [rsp+arg_8], rbx
0x180054e95  mov     [rsp+arg_10], rbp
0x180054e9a  mov     [rsp+arg_18], rsi
0x180054e9f  push    rdi
0x180054ea0  sub     rsp, 4A0h
0x180054ea7  mov     rax, cs:__security_cookie
0x180054eae  xor     rax, rsp
0x180054eb1  mov     [rsp+4A8h+var_18], rax
0x180054eb9  xor     ebp, ebp
0x180054ebb  mov     rdi, rcx
0x180054ebe  mov     esi, ebp
0x180054ec0  test    rcx, rcx
0x180054ec3  jnz     short loc_180054EFB
0x180054ec5  mov     rcx, cs:WPP_GLOBAL_Control
0x180054ecc  lea     rax, WPP_GLOBAL_Control
0x180054ed3  cmp     rcx, rax
0x180054ed6  jz      short loc_180054EF1
0x180054ed8  test    byte ptr [rcx+1Ch], 10h
0x180054edc  jz      short loc_180054EF1
0x180054ede  mov     rcx, [rcx+10h]
0x180054ee2  lea     edx, [rdi+0Ah]
0x180054ee5  lea     r8, WPP_36b3ebb3851d38e5219956dcc07ca210_Traceguids
0x180054eec  call    WPP_SF_
0x180054ef1  mov     eax, 57h ; 'W'
0x180054ef6  jmp     loc_180054FE7
0x180054efb  mov     edx, 210h; uBytes
0x180054f00  mov     ecx, 40h ; '@'; uFlags
0x180054f05  call    cs:__imp_LocalAlloc
0x180054f0c  nop     dword ptr [rax+rax+00h]
0x180054f11  mov     rbx, rax
0x180054f14  test    rax, rax
0x180054f17  jnz     short loc_180054F21
0x180054f19  lea     eax, [rbx+8]
0x180054f1c  jmp     loc_180054FE7
0x180054f21  lea     rax, aDat; ".dat"
0x180054f28  mov     edx, 104h; unsigned __int64
0x180054f2d  mov     [rsp+4A8h+var_480], rax
0x180054f32  lea     r9, ?g_szReportDir@@3PAGA; ushort near * g_szReportDir
0x180054f39  lea     rax, aPerUser; "PER-USER_"
0x180054f40  lea     r8, aSSS; "%s%s*%s"
0x180054f47  mov     [rsp+4A8h+var_488], rax
0x180054f4c  lea     rcx, [rsp+4A8h+FileName]; unsigned __int16 *
0x180054f54  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180054f59  xor     edx, edx; Val
0x180054f5b  lea     rcx, [rsp+4A8h+FindFileData]; void *
0x180054f60  mov     r8d, 250h; Size
0x180054f66  call    memset_0
0x180054f6b  lea     rdx, [rsp+4A8h+FindFileData]; lpFindFileData
0x180054f70  lea     rcx, [rsp+4A8h+FileName]; lpFileName
0x180054f78  call    cs:__imp_FindFirstFileW
0x180054f7f  nop     dword ptr [rax+rax+00h]
0x180054f84  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180054f88  jnz     short loc_180054FCC
0x180054f8a  call    cs:__imp_GetLastError
0x180054f91  nop     dword ptr [rax+rax+00h]
0x180054f96  cmp     eax, 3
0x180054f99  jnz     short loc_180054FC2
0x180054f9b  xor     edx, edx; lpSecurityAttributes
0x180054f9d  lea     rcx, ?g_szReportDir@@3PAGA; lpPathName
0x180054fa4  call    cs:__imp_CreateDirectoryW
0x180054fab  nop     dword ptr [rax+rax+00h]
0x180054fb0  test    eax, eax
0x180054fb2  jnz     short loc_180054FC2
0x180054fb4  call    cs:__imp_GetLastError
0x180054fbb  nop     dword ptr [rax+rax+00h]
0x180054fc0  mov     esi, eax
0x180054fc2  or      qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x180054fc6  mov     [rbx+8], bp
0x180054fca  jmp     short loc_180054FE2
0x180054fcc  lea     rcx, [rbx+8]; unsigned __int16 *
0x180054fd0  mov     [rbx], rax
0x180054fd3  lea     r8, [rsp+4A8h+FindFileData.cFileName]; unsigned __int16 *
0x180054fd8  mov     edx, 208h; unsigned __int64
0x180054fdd  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180054fe2  mov     [rdi], rbx
0x180054fe5  mov     eax, esi
0x180054fe7  mov     rcx, [rsp+4A8h+var_18]
0x180054fef  xor     rcx, rsp; StackCookie
0x180054ff2  call    __security_check_cookie
0x180054ff7  lea     r11, [rsp+4A8h+var_8]
0x180054fff  mov     rbx, [r11+18h]
0x180055003  mov     rbp, [r11+20h]
0x180055007  mov     rsi, [r11+28h]
0x18005500b  mov     rsp, r11
0x18005500e  pop     rdi
0x18005500f  retn
```
