# NlDeleteBinaryLog(ushort *)

- ea: `0x18003e060`
- end: `0x18003e202`
- name: `?NlDeleteBinaryLog@@YAKPEAG@Z`
- size: `418`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180017c24`
- `0x18001dad0`

## callees

- `0x180003220`
- `0x180007278`
- `0x18000e270`
- `0x18003e060`
- `0x18008a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18003e16f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18003e16f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e10d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e18b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e10d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e18b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18003e103`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18003e103`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003e178`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003e178`

## string_xrefs

- `0x18003e113`: `NlDeleteBinaryLog: GetSystemWindowsDirectoryW failed (%ld)\n`
- `0x18003e14c`: `NlDeleteBinaryLog: file name length is too long \n`
- `0x18003e182`: `NlDeleteBinaryLog: successfully deleted %ws \n`
- `0x18003e19b`: `Failed to delete log file %ws (%ld)\n`
- `0x18003e1b1`: `NlDeleteBinaryLog: log file was not on disk %ws \n`

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
0x18003e060  push    rbp
0x18003e062  push    rbx
0x18003e063  push    rsi
0x18003e064  push    rdi
0x18003e065  sub     rsp, 38h
0x18003e069  lea     rbp, [rsp+20h]
0x18003e06e  mov     rax, cs:__security_cookie
0x18003e075  xor     rax, rbp
0x18003e078  mov     [rbp+30h+var_30], rax
0x18003e07c  xor     esi, esi
0x18003e07e  mov     edx, 20Ah
0x18003e083  cmp     cs:g_ulMaxStackAllocSize, rdx
0x18003e08a  mov     rdi, rcx
0x18003e08d  jb      short loc_18003E0CE
0x18003e08f  mov     rcx, cs:g_ulAdditionalProbeSize
0x18003e096  add     rcx, 212h
0x18003e09d  cmp     rcx, rdx
0x18003e0a0  jb      short loc_18003E0CE
0x18003e0a2  call    VerifyStackAvailable
0x18003e0a7  test    eax, eax
0x18003e0a9  jz      short loc_18003E0CE
0x18003e0ab  mov     eax, [rsp+50h+var_50]
0x18003e0ae  mov     eax, 220h
0x18003e0b3  sub     rsp, rax
0x18003e0b6  lea     rbx, [rsp+270h+var_250]
0x18003e0bb  mov     eax, [rbx]
0x18003e0bd  test    rbx, rbx
0x18003e0c0  jz      short loc_18003E0CE
0x18003e0c2  mov     dword ptr [rbx], 6B637453h
0x18003e0c8  add     rbx, 8
0x18003e0cc  jnz     short loc_18003E0FB
0x18003e0ce  mov     rax, cs:g_pfnAllocate
0x18003e0d5  mov     ecx, 212h
0x18003e0da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e0df  test    rax, rax
0x18003e0e2  jz      loc_18003E1E6
0x18003e0e8  lea     rbx, [rax+8]
0x18003e0ec  mov     dword ptr [rax], 70616548h
0x18003e0f2  test    rbx, rbx
0x18003e0f5  jz      loc_18003E1E6
0x18003e0fb  mov     edx, 105h; uSize
0x18003e100  mov     rcx, rbx; lpBuffer
0x18003e103  call    cs:__imp_GetSystemWindowsDirectoryW
0x18003e109  test    eax, eax
0x18003e10b  jnz     short loc_18003E12E
0x18003e10d  call    cs:__imp_GetLastError
0x18003e113  lea     rdx, aNldeletebinary; "NlDeleteBinaryLog: GetSystemWindowsDire"...
0x18003e11a  mov     ecx, 100h; unsigned int
0x18003e11f  mov     r8d, eax
0x18003e122  mov     edi, eax
0x18003e124  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003e129  jmp     loc_18003E1C7
0x18003e12e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003e132  inc     rcx
0x18003e135  cmp     [rdi+rcx*2], si
0x18003e139  jnz     short loc_18003E132
0x18003e13b  inc     rcx
0x18003e13e  mov     eax, eax
0x18003e140  add     rcx, rax
0x18003e143  cmp     rcx, 104h
0x18003e14a  jb      short loc_18003E164
0x18003e14c  lea     rdx, aNldeletebinary_0; "NlDeleteBinaryLog: file name length is "...
0x18003e153  mov     ecx, 100h; unsigned int
0x18003e158  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003e15d  mov     edi, 7Bh ; '{'
0x18003e162  jmp     short loc_18003E1C7
0x18003e164  mov     r8, rdi
0x18003e167  mov     edx, 105h
0x18003e16c  mov     rcx, rbx
0x18003e16f  call    cs:__imp__o_wcscat_s
0x18003e175  mov     rcx, rbx; lpFileName
0x18003e178  call    cs:__imp_DeleteFileW
0x18003e17e  test    eax, eax
0x18003e180  jz      short loc_18003E18B
0x18003e182  lea     rdx, aNldeletebinary_2; "NlDeleteBinaryLog: successfully deleted"...
0x18003e189  jmp     short loc_18003E1B8
0x18003e18b  call    cs:__imp_GetLastError
0x18003e191  mov     edi, eax
0x18003e193  cmp     eax, 2
0x18003e196  jz      short loc_18003E1B1
0x18003e198  mov     r9d, eax
0x18003e19b  lea     rdx, aFailedToDelete; "Failed to delete log file %ws (%ld)\n"
0x18003e1a2  mov     r8, rbx
0x18003e1a5  mov     ecx, 100h; unsigned int
0x18003e1aa  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003e1af  jmp     short loc_18003E1C7
0x18003e1b1  lea     rdx, aNldeletebinary_1; "NlDeleteBinaryLog: log file was not on "...
0x18003e1b8  mov     r8, rbx
0x18003e1bb  mov     ecx, 100h; unsigned int
0x18003e1c0  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003e1c5  mov     edi, esi
0x18003e1c7  test    rbx, rbx
0x18003e1ca  jz      short loc_18003E1EB
0x18003e1cc  lea     rcx, [rbx-8]
0x18003e1d0  cmp     dword ptr [rcx], 70616548h
0x18003e1d6  jnz     short loc_18003E1EB
0x18003e1d8  mov     rax, cs:g_pfnFree
0x18003e1df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e1e4  jmp     short loc_18003E1EB
0x18003e1e6  mov     edi, 8
0x18003e1eb  mov     eax, edi
0x18003e1ed  mov     rcx, [rbp+30h+var_30]
0x18003e1f1  xor     rcx, rbp; StackCookie
0x18003e1f4  call    __security_check_cookie
0x18003e1f9  lea     rsp, [rbp+18h]
0x18003e1fd  pop     rdi
0x18003e1fe  pop     rsi
0x18003e1ff  pop     rbx
0x18003e200  pop     rbp
0x18003e201  retn
```
