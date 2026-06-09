# NlDeleteBinaryLog(ushort *)

- ea: `0x180040760`
- end: `0x180040921`
- name: `?NlDeleteBinaryLog@@YAKPEAG@Z`
- size: `449`
- prototype: `unsigned int __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180018720`
- `0x18001eacc`

## callees

- `0x180003340`
- `0x180007518`
- `0x18000e910`
- `0x180040760`
- `0x180091010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18004087b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18004087b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040813`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800408a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040813`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800408a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180040803`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180040803`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004088a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004088a`

## string_xrefs

- `0x18004081f`: `NlDeleteBinaryLog: GetSystemWindowsDirectoryW failed (%ld)\n`
- `0x180040858`: `NlDeleteBinaryLog: file name length is too long \n`
- `0x18004089a`: `NlDeleteBinaryLog: successfully deleted %ws \n`
- `0x1800408b9`: `Failed to delete log file %ws (%ld)\n`
- `0x1800408cf`: `NlDeleteBinaryLog: log file was not on disk %ws \n`

## pseudocode

```c
__int64 __fastcall NlDeleteBinaryLog(unsigned __int16 *a1)
{
  void *v2; // rsp
  WCHAR *v3; // rbx
  _DWORD *v4; // rax
  UINT SystemWindowsDirectoryW; // eax
  __int64 v6; // rdi
  __int64 v7; // rcx
  DWORD LastError; // eax
  _DWORD v10[10]; // [rsp-20h] [rbp-240h] BYREF
  _BYTE v11[504]; // [rsp+8h] [rbp-218h] BYREF

  if ( (unsigned __int64)g_ulMaxStackAllocSize < 0x20A
    || (unsigned __int64)(g_ulAdditionalProbeSize + 530) < 0x20A
    || !(unsigned int)VerifyStackAvailable()
    || (v2 = alloca(544), v10 == (_DWORD *)-32LL)
    || (v10[8] = 1801679955, (v3 = (WCHAR *)v11) == 0) )
  {
    v4 = (_DWORD *)((__int64 (__fastcall *)(__int64))g_pfnAllocate)(530);
    if ( !v4 || (v3 = (WCHAR *)(v4 + 2), *v4 = 1885431112, v4 == (_DWORD *)-8LL) )
    {
      LODWORD(v6) = 8;
      return (unsigned int)v6;
    }
  }
  SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(v3, 0x105u);
  if ( SystemWindowsDirectoryW )
  {
    v7 = -1;
    do
      ++v7;
    while ( a1[v7] );
    if ( (unsigned __int64)SystemWindowsDirectoryW + v7 + 1 < 0x104 )
    {
      _o_wcscat_s(v3, 261, a1);
      if ( DeleteFileW(v3) )
      {
        NlPrintRoutine(0x100u, L"NlDeleteBinaryLog: successfully deleted %ws \n", v3);
      }
      else
      {
        LastError = GetLastError();
        LODWORD(v6) = LastError;
        if ( LastError != 2 )
        {
          NlPrintRoutine(0x100u, L"Failed to delete log file %ws (%ld)\n", v3, LastError);
          goto LABEL_20;
        }
        NlPrintRoutine(0x100u, L"NlDeleteBinaryLog: log file was not on disk %ws \n", v3);
      }
      LODWORD(v6) = 0;
      goto LABEL_20;
    }
    NlPrintRoutine(0x100u, L"NlDeleteBinaryLog: file name length is too long \n");
    LODWORD(v6) = 123;
  }
  else
  {
    v6 = GetLastError();
    NlPrintRoutine(0x100u, L"NlDeleteBinaryLog: GetSystemWindowsDirectoryW failed (%ld)\n", v6);
  }
LABEL_20:
  if ( v3 && *((_DWORD *)v3 - 2) == 1885431112 )
    ((void (__fastcall *)(WCHAR *))g_pfnFree)(v3 - 4);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180040760  push    rbp
0x180040762  push    rbx
0x180040763  push    rsi
0x180040764  push    rdi
0x180040765  sub     rsp, 38h
0x180040769  lea     rbp, [rsp+20h]
0x18004076e  mov     rax, cs:__security_cookie
0x180040775  xor     rax, rbp
0x180040778  mov     [rbp+30h+var_30], rax
0x18004077c  xor     esi, esi
0x18004077e  mov     edx, 20Ah
0x180040783  cmp     cs:g_ulMaxStackAllocSize, rdx
0x18004078a  mov     rdi, rcx
0x18004078d  jb      short loc_1800407CE
0x18004078f  mov     rcx, cs:g_ulAdditionalProbeSize
0x180040796  add     rcx, 212h
0x18004079d  cmp     rcx, rdx
0x1800407a0  jb      short loc_1800407CE
0x1800407a2  call    VerifyStackAvailable
0x1800407a7  test    eax, eax
0x1800407a9  jz      short loc_1800407CE
0x1800407ab  mov     eax, [rsp+50h+var_50]
0x1800407ae  mov     eax, 220h
0x1800407b3  sub     rsp, rax
0x1800407b6  lea     rbx, [rsp+270h+var_250]
0x1800407bb  mov     eax, [rbx]
0x1800407bd  test    rbx, rbx
0x1800407c0  jz      short loc_1800407CE
0x1800407c2  mov     dword ptr [rbx], 6B637453h
0x1800407c8  add     rbx, 8
0x1800407cc  jnz     short loc_1800407FB
0x1800407ce  mov     rax, cs:g_pfnAllocate
0x1800407d5  mov     ecx, 212h
0x1800407da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800407df  test    rax, rax
0x1800407e2  jz      loc_180040904
0x1800407e8  lea     rbx, [rax+8]
0x1800407ec  mov     dword ptr [rax], 70616548h
0x1800407f2  test    rbx, rbx
0x1800407f5  jz      loc_180040904
0x1800407fb  mov     edx, 105h; uSize
0x180040800  mov     rcx, rbx; lpBuffer
0x180040803  call    cs:__imp_GetSystemWindowsDirectoryW
0x18004080a  nop     dword ptr [rax+rax+00h]
0x18004080f  test    eax, eax
0x180040811  jnz     short loc_18004083A
0x180040813  call    cs:__imp_GetLastError
0x18004081a  nop     dword ptr [rax+rax+00h]
0x18004081f  lea     rdx, aNldeletebinary; "NlDeleteBinaryLog: GetSystemWindowsDire"...
0x180040826  mov     ecx, 100h; unsigned int
0x18004082b  mov     r8d, eax
0x18004082e  mov     edi, eax
0x180040830  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180040835  jmp     loc_1800408E5
0x18004083a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004083e  inc     rcx
0x180040841  cmp     [rdi+rcx*2], si
0x180040845  jnz     short loc_18004083E
0x180040847  inc     rcx
0x18004084a  mov     eax, eax
0x18004084c  add     rcx, rax
0x18004084f  cmp     rcx, 104h
0x180040856  jb      short loc_180040870
0x180040858  lea     rdx, aNldeletebinary_0; "NlDeleteBinaryLog: file name length is "...
0x18004085f  mov     ecx, 100h; unsigned int
0x180040864  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180040869  mov     edi, 7Bh ; '{'
0x18004086e  jmp     short loc_1800408E5
0x180040870  mov     r8, rdi
0x180040873  mov     edx, 105h
0x180040878  mov     rcx, rbx
0x18004087b  call    cs:__imp__o_wcscat_s
0x180040882  nop     dword ptr [rax+rax+00h]
0x180040887  mov     rcx, rbx; lpFileName
0x18004088a  call    cs:__imp_DeleteFileW
0x180040891  nop     dword ptr [rax+rax+00h]
0x180040896  test    eax, eax
0x180040898  jz      short loc_1800408A3
0x18004089a  lea     rdx, aNldeletebinary_2; "NlDeleteBinaryLog: successfully deleted"...
0x1800408a1  jmp     short loc_1800408D6
0x1800408a3  call    cs:__imp_GetLastError
0x1800408aa  nop     dword ptr [rax+rax+00h]
0x1800408af  mov     edi, eax
0x1800408b1  cmp     eax, 2
0x1800408b4  jz      short loc_1800408CF
0x1800408b6  mov     r9d, eax
0x1800408b9  lea     rdx, aFailedToDelete; "Failed to delete log file %ws (%ld)\n"
0x1800408c0  mov     r8, rbx
0x1800408c3  mov     ecx, 100h; unsigned int
0x1800408c8  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800408cd  jmp     short loc_1800408E5
0x1800408cf  lea     rdx, aNldeletebinary_1; "NlDeleteBinaryLog: log file was not on "...
0x1800408d6  mov     r8, rbx
0x1800408d9  mov     ecx, 100h; unsigned int
0x1800408de  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800408e3  mov     edi, esi
0x1800408e5  test    rbx, rbx
0x1800408e8  jz      short loc_180040909
0x1800408ea  lea     rcx, [rbx-8]
0x1800408ee  cmp     dword ptr [rcx], 70616548h
0x1800408f4  jnz     short loc_180040909
0x1800408f6  mov     rax, cs:g_pfnFree
0x1800408fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040902  jmp     short loc_180040909
0x180040904  mov     edi, 8
0x180040909  mov     eax, edi
0x18004090b  mov     rcx, [rbp+30h+var_30]
0x18004090f  xor     rcx, rbp; StackCookie
0x180040912  call    __security_check_cookie
0x180040917  lea     rsp, [rbp+18h]
0x18004091b  pop     rdi
0x18004091c  pop     rsi
0x18004091d  pop     rbx
0x18004091e  pop     rbp
0x18004091f  retn
```
