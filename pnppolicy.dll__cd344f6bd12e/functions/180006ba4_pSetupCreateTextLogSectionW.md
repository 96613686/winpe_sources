# pSetupCreateTextLogSectionW

- ea: `0x180006ba4`
- end: `0x180006c4d`
- name: `pSetupCreateTextLogSectionW`
- size: `169`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180001da8`

## callees

- `0x180006590`
- `0x180006ba4`
- `0x1800071f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006c3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006c3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c02`
- `KERNEL32!HeapFree` at `0x180006c1b`
- `KERNEL32!HeapFree` at `0x180006c32`
- `KERNEL32!HeapFree` at `0x180006c1b`
- `KERNEL32!HeapFree` at `0x180006c32`

## pseudocode

```c
_BOOL8 __fastcall pSetupCreateTextLogSectionW(const WCHAR *a1, __int64 a2, const WCHAR *a3, unsigned __int64 *a4)
{
  BOOL TextLogSectionA; // ebp
  char *v5; // rsi
  DWORD LastError; // ebx
  CHAR *v9; // rdi

  TextLogSectionA = 0;
  v5 = 0;
  if ( !a1 || (v5 = (char *)pSetupUnicodeToMultiByte(a1)) != 0 )
  {
    v9 = 0;
    if ( !a3 || (v9 = (CHAR *)pSetupUnicodeToMultiByte(a3)) != 0 )
    {
      LastError = 0;
      TextLogSectionA = pSetupCreateTextLogSectionA(v5, a2, v9, a4);
      if ( !TextLogSectionA )
        LastError = GetLastError();
    }
    else
    {
      LastError = 8;
    }
    if ( v5 )
      HeapFree(hHeap, 0, v5);
    if ( v9 )
      HeapFree(hHeap, 0, v9);
  }
  else
  {
    LastError = 8;
  }
  SetLastError(LastError);
  return TextLogSectionA;
}

```

## disassembly

```asm
0x180006ba4  push    rbx
0x180006ba6  push    rbp
0x180006ba7  push    rsi
0x180006ba8  push    rdi
0x180006ba9  push    r14
0x180006bab  sub     rsp, 20h
0x180006baf  xor     ebp, ebp
0x180006bb1  xor     esi, esi
0x180006bb3  mov     r14, r9
0x180006bb6  mov     rbx, r8
0x180006bb9  test    rcx, rcx
0x180006bbc  jz      short loc_180006BD0
0x180006bbe  call    pSetupUnicodeToMultiByte
0x180006bc3  mov     rsi, rax
0x180006bc6  test    rax, rax
0x180006bc9  jnz     short loc_180006BD0
0x180006bcb  lea     ebx, [rbp+8]
0x180006bce  jmp     short loc_180006C38
0x180006bd0  xor     edi, edi
0x180006bd2  test    rbx, rbx
0x180006bd5  jz      short loc_180006BEC
0x180006bd7  mov     rcx, rbx; lpWideCharStr
0x180006bda  call    pSetupUnicodeToMultiByte
0x180006bdf  mov     rdi, rax
0x180006be2  test    rax, rax
0x180006be5  jnz     short loc_180006BEC
0x180006be7  lea     ebx, [rax+8]
0x180006bea  jmp     short loc_180006C0A
0x180006bec  mov     r9, r14
0x180006bef  mov     r8, rdi
0x180006bf2  mov     rcx, rsi
0x180006bf5  xor     ebx, ebx
0x180006bf7  call    pSetupCreateTextLogSectionA
0x180006bfc  mov     ebp, eax
0x180006bfe  test    eax, eax
0x180006c00  jnz     short loc_180006C0A
0x180006c02  call    cs:__imp_GetLastError
0x180006c08  mov     ebx, eax
0x180006c0a  test    rsi, rsi
0x180006c0d  jz      short loc_180006C21
0x180006c0f  mov     rcx, cs:hHeap; hHeap
0x180006c16  mov     r8, rsi; lpMem
0x180006c19  xor     edx, edx; dwFlags
0x180006c1b  call    cs:__imp_HeapFree
0x180006c21  test    rdi, rdi
0x180006c24  jz      short loc_180006C38
0x180006c26  mov     rcx, cs:hHeap; hHeap
0x180006c2d  mov     r8, rdi; lpMem
0x180006c30  xor     edx, edx; dwFlags
0x180006c32  call    cs:__imp_HeapFree
0x180006c38  mov     ecx, ebx; dwErrCode
0x180006c3a  call    cs:__imp_SetLastError
0x180006c40  mov     eax, ebp
0x180006c42  add     rsp, 20h
0x180006c46  pop     r14
0x180006c48  pop     rdi
0x180006c49  pop     rsi
0x180006c4a  pop     rbp
0x180006c4b  pop     rbx
0x180006c4c  retn
```
