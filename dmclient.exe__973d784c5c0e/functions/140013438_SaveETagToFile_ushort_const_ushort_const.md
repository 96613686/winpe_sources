# SaveETagToFile(ushort const *,ushort const *)

- ea: `0x140013438`
- end: `0x1400135a7`
- name: `?SaveETagToFile@@YAJPEBG0@Z`
- size: `367`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140012928`

## callees

- `0x14000b904`
- `0x140013438`

## import_xrefs

- `msvcrt!wcsnlen` at `0x14001351d`
- `msvcrt!wcsnlen` at `0x14001351d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001347d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001347d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013463`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001357b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013463`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001357b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001358f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001358f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400134f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013551`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400134f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013551`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001356f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001356f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140013541`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140013541`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1400134e3`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1400134e3`

## pseudocode

```c
__int64 __fastcall SaveETagToFile(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  signed int v4; // ebx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v6; // rdi
  void *File2; // rbp
  signed int LastError; // eax
  int v9; // eax
  signed int v10; // eax
  HANDLE v11; // rax
  DWORD NumberOfBytesWritten; // [rsp+60h] [rbp+8h] BYREF

  NumberOfBytesWritten = 0;
  if ( a1 && a2 )
  {
    ProcessHeap = GetProcessHeap();
    v6 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 0x208u);
    if ( v6 )
    {
      v4 = StringCchPrintfW(v6, 0x104u, L"%s.%s", a1, L"etag");
      if ( v4 >= 0 )
      {
        File2 = (void *)CreateFile2(v6, 0x40000000, 1);
        if ( File2 == (void *)-1LL )
        {
          LastError = GetLastError();
          v4 = LastError;
          if ( LastError > 0 )
            v4 = (unsigned __int16)LastError | 0x80070000;
        }
        else
        {
          v9 = wcsnlen(a2, 0x104u);
          if ( !WriteFile(File2, a2, 2 * v9, &NumberOfBytesWritten, 0) )
          {
            v10 = GetLastError();
            v4 = v10;
            if ( v10 > 0 )
              v4 = (unsigned __int16)v10 | 0x80070000;
          }
          CloseHandle(File2);
        }
      }
      v11 = GetProcessHeap();
      HeapFree(v11, 0, v6);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140013438  push    rbx
0x14001343a  push    rbp
0x14001343b  push    rsi
0x14001343c  push    rdi
0x14001343d  sub     rsp, 38h
0x140013441  mov     [rsp+58h+NumberOfBytesWritten], 0
0x140013449  mov     rsi, rdx
0x14001344c  mov     rbx, rcx
0x14001344f  test    rcx, rcx
0x140013452  jnz     short loc_14001345E
0x140013454  mov     ebx, 80004003h
0x140013459  jmp     loc_14001359B
0x14001345e  test    rsi, rsi
0x140013461  jz      short loc_140013454
0x140013463  call    cs:__imp_GetProcessHeap
0x14001346a  nop     dword ptr [rax+rax+00h]
0x14001346f  mov     edx, 8; dwFlags
0x140013474  mov     r8d, 208h; dwBytes
0x14001347a  mov     rcx, rax; hHeap
0x14001347d  call    cs:__imp_HeapAlloc
0x140013484  nop     dword ptr [rax+rax+00h]
0x140013489  mov     rdi, rax
0x14001348c  test    rax, rax
0x14001348f  jnz     short loc_14001349B
0x140013491  mov     ebx, 8007000Eh
0x140013496  jmp     loc_14001359B
0x14001349b  lea     rax, aEtag; "etag"
0x1400134a2  mov     r9, rbx
0x1400134a5  lea     r8, aSS; "%s.%s"
0x1400134ac  mov     [rsp+58h+lpOverlapped], rax
0x1400134b1  mov     edx, 104h; unsigned __int64
0x1400134b6  mov     rcx, rdi; unsigned __int16 *
0x1400134b9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400134be  mov     ebx, eax
0x1400134c0  test    eax, eax
0x1400134c2  js      loc_14001357B
0x1400134c8  mov     r9d, 2
0x1400134ce  mov     [rsp+58h+lpOverlapped], 0
0x1400134d7  mov     edx, 40000000h
0x1400134dc  mov     rcx, rdi
0x1400134df  lea     r8d, [r9-1]
0x1400134e3  call    cs:__imp_CreateFile2
0x1400134ea  nop     dword ptr [rax+rax+00h]
0x1400134ef  mov     rbp, rax
0x1400134f2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400134f6  jnz     short loc_140013515
0x1400134f8  call    cs:__imp_GetLastError
0x1400134ff  nop     dword ptr [rax+rax+00h]
0x140013504  mov     ebx, eax
0x140013506  test    eax, eax
0x140013508  jle     short loc_14001357B
0x14001350a  movzx   ebx, ax
0x14001350d  or      ebx, 80070000h
0x140013513  jmp     short loc_14001357B
0x140013515  mov     edx, 104h; MaxCount
0x14001351a  mov     rcx, rsi; Source
0x14001351d  call    cs:__imp_wcsnlen
0x140013524  nop     dword ptr [rax+rax+00h]
0x140013529  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14001352e  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x140013537  mov     rdx, rsi; lpBuffer
0x14001353a  mov     rcx, rbp; hFile
0x14001353d  lea     r8d, [rax+rax]; nNumberOfBytesToWrite
0x140013541  call    cs:__imp_WriteFile
0x140013548  nop     dword ptr [rax+rax+00h]
0x14001354d  test    eax, eax
0x14001354f  jnz     short loc_14001356C
0x140013551  call    cs:__imp_GetLastError
0x140013558  nop     dword ptr [rax+rax+00h]
0x14001355d  mov     ebx, eax
0x14001355f  test    eax, eax
0x140013561  jle     short loc_14001356C
0x140013563  movzx   ebx, ax
0x140013566  or      ebx, 80070000h
0x14001356c  mov     rcx, rbp; hObject
0x14001356f  call    cs:__imp_CloseHandle
0x140013576  nop     dword ptr [rax+rax+00h]
0x14001357b  call    cs:__imp_GetProcessHeap
0x140013582  nop     dword ptr [rax+rax+00h]
0x140013587  mov     r8, rdi; lpMem
0x14001358a  xor     edx, edx; dwFlags
0x14001358c  mov     rcx, rax; hHeap
0x14001358f  call    cs:__imp_HeapFree
0x140013596  nop     dword ptr [rax+rax+00h]
0x14001359b  mov     eax, ebx
0x14001359d  add     rsp, 38h
0x1400135a1  pop     rdi
0x1400135a2  pop     rsi
0x1400135a3  pop     rbp
0x1400135a4  pop     rbx
0x1400135a5  retn
```
