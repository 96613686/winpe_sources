# DiagCabDeleteFile(char *,int *,void *)

- ea: `0x140060740`
- end: `0x140060813`
- name: `?DiagCabDeleteFile@@YAHPEADPEAHPEAX@Z`
- size: `211`
- prototype: `int __cdecl(LPSTR pszFile, int *err, void *pv)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x140060740`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x14006079c`
- `KERNEL32!MultiByteToWideChar` at `0x14006079c`
- `KERNEL32!GetLastError` at `0x1400607ac`
- `KERNEL32!GetLastError` at `0x1400607ac`
- `KERNEL32!HeapAlloc` at `0x140060769`
- `KERNEL32!HeapAlloc` at `0x140060769`
- `KERNEL32!HeapFree` at `0x1400607fb`
- `KERNEL32!HeapFree` at `0x1400607fb`
- `KERNEL32!GetProcessHeap` at `0x140060752`
- `KERNEL32!GetProcessHeap` at `0x1400607e7`
- `KERNEL32!GetProcessHeap` at `0x140060752`
- `KERNEL32!GetProcessHeap` at `0x1400607e7`
- `msvcrt!_errno` at `0x1400607d7`
- `msvcrt!_errno` at `0x1400607d7`
- `msvcrt!_wremove` at `0x1400607c4`
- `msvcrt!_wremove` at `0x1400607c4`

## pseudocode

```c
__int64 __fastcall DiagCabDeleteFile(const CHAR *pszFile, int *err, void *pv)
{
  unsigned int v5; // ebx
  HANDLE ProcessHeap; // rax
  WCHAR *lpWideCharStr; // rax
  wchar_t *v8; // rdi
  unsigned int v9; // eax
  HANDLE v10; // rax

  v5 = -1;
  ProcessHeap = GetProcessHeap();
  lpWideCharStr = (WCHAR *)HeapAlloc(ProcessHeap, 0, 0x208u);
  v8 = lpWideCharStr;
  if ( lpWideCharStr )
  {
    v9 = MultiByteToWideChar(0xFDE9u, 8u, pszFile, -1, lpWideCharStr, 260);
    if ( v9 )
    {
      if ( v9 < 0x104 )
      {
        v5 = _wremove(v8);
        if ( v5 == -1 )
          *err = *_errno();
      }
    }
    else
    {
      GetLastError();
    }
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v8);
  }
  return v5;
}

```

## disassembly

```asm
0x140060740  push    rbx
0x140060742  push    rbp
0x140060743  push    rsi
0x140060744  push    rdi
0x140060745  sub     rsp, 38h
0x140060749  mov     rsi, rdx
0x14006074c  mov     rbp, rcx
0x14006074f  or      ebx, 0FFFFFFFFh
0x140060752  call    cs:__imp_GetProcessHeap
0x140060759  nop     dword ptr [rax+rax+00h]
0x14006075e  xor     edx, edx; dwFlags
0x140060760  mov     r8d, 208h; dwBytes
0x140060766  mov     rcx, rax; hHeap
0x140060769  call    cs:__imp_HeapAlloc
0x140060770  nop     dword ptr [rax+rax+00h]
0x140060775  mov     rdi, rax
0x140060778  test    rax, rax
0x14006077b  jz      loc_140060807
0x140060781  mov     [rsp+58h+cchWideChar], 104h; cchWideChar
0x140060789  lea     edx, [rbx+9]; dwFlags
0x14006078c  or      r9d, ebx; cbMultiByte
0x14006078f  mov     [rsp+58h+lpWideCharStr], rax; lpWideCharStr
0x140060794  mov     r8, rbp; lpMultiByteStr
0x140060797  mov     ecx, 0FDE9h; CodePage
0x14006079c  call    cs:__imp_MultiByteToWideChar
0x1400607a3  nop     dword ptr [rax+rax+00h]
0x1400607a8  test    eax, eax
0x1400607aa  jnz     short loc_1400607BA
0x1400607ac  call    cs:__imp_GetLastError
0x1400607b3  nop     dword ptr [rax+rax+00h]
0x1400607b8  jmp     short loc_1400607E7
0x1400607ba  cmp     eax, 104h
0x1400607bf  jnb     short loc_1400607E7
0x1400607c1  mov     rcx, rdi; FileName
0x1400607c4  call    cs:__imp__wremove
0x1400607cb  nop     dword ptr [rax+rax+00h]
0x1400607d0  mov     ebx, eax
0x1400607d2  cmp     eax, 0FFFFFFFFh
0x1400607d5  jnz     short loc_1400607E7
0x1400607d7  call    cs:__imp__errno
0x1400607de  nop     dword ptr [rax+rax+00h]
0x1400607e3  mov     ecx, [rax]
0x1400607e5  mov     [rsi], ecx
0x1400607e7  call    cs:__imp_GetProcessHeap
0x1400607ee  nop     dword ptr [rax+rax+00h]
0x1400607f3  mov     r8, rdi; lpMem
0x1400607f6  xor     edx, edx; dwFlags
0x1400607f8  mov     rcx, rax; hHeap
0x1400607fb  call    cs:__imp_HeapFree
0x140060802  nop     dword ptr [rax+rax+00h]
0x140060807  mov     eax, ebx
0x140060809  add     rsp, 38h
0x14006080d  pop     rdi
0x14006080e  pop     rsi
0x14006080f  pop     rbp
0x140060810  pop     rbx
0x140060811  retn
```
