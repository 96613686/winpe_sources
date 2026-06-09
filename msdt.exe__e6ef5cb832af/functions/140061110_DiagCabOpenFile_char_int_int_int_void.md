# DiagCabOpenFile(char *,int,int,int *,void *)

- ea: `0x140061110`
- end: `0x140061245`
- name: `?DiagCabOpenFile@@YA_JPEADHHPEAHPEAX@Z`
- size: `309`
- prototype: `INT_PTR __fastcall(const CHAR *pszFile, int oflag, unsigned int pmode, int *err)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140060840`

## callees

- `0x140061110`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x14006114d`
- `KERNEL32!MultiByteToWideChar` at `0x1400611c6`
- `KERNEL32!MultiByteToWideChar` at `0x14006114d`
- `KERNEL32!MultiByteToWideChar` at `0x1400611c6`
- `KERNEL32!GetLastError` at `0x14006115f`
- `KERNEL32!GetLastError` at `0x1400611d6`
- `KERNEL32!GetLastError` at `0x14006115f`
- `KERNEL32!GetLastError` at `0x1400611d6`
- `KERNEL32!HeapAlloc` at `0x14006118e`
- `KERNEL32!HeapAlloc` at `0x14006118e`
- `KERNEL32!HeapFree` at `0x140061226`
- `KERNEL32!HeapFree` at `0x140061226`
- `KERNEL32!GetProcessHeap` at `0x14006117a`
- `KERNEL32!GetProcessHeap` at `0x140061212`
- `KERNEL32!GetProcessHeap` at `0x14006117a`
- `KERNEL32!GetProcessHeap` at `0x140061212`
- `msvcrt!_errno` at `0x140061202`
- `msvcrt!_errno` at `0x140061202`
- `msvcrt!_wopen` at `0x1400611ef`
- `msvcrt!_wopen` at `0x1400611ef`

## pseudocode

```c
INT_PTR __fastcall DiagCabOpenFile(const CHAR *pszFile, int oflag, unsigned int pmode, int *err)
{
  int v4; // esi
  int v9; // eax
  int cchWideChar; // ebp
  SIZE_T v11; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR *lpWideCharStr; // rax
  wchar_t *v14; // rbx
  HANDLE v15; // rax

  v4 = -1;
  v9 = MultiByteToWideChar(0xFDE9u, 8u, pszFile, -1, 0, 0);
  cchWideChar = v9;
  if ( v9 )
  {
    v11 = 2LL * (v9 + 1);
    ProcessHeap = GetProcessHeap();
    lpWideCharStr = (WCHAR *)HeapAlloc(ProcessHeap, 0, v11);
    v14 = lpWideCharStr;
    if ( lpWideCharStr )
    {
      if ( MultiByteToWideChar(0xFDE9u, 8u, pszFile, -1, lpWideCharStr, cchWideChar) )
      {
        v4 = _wopen(v14, oflag, pmode);
        if ( v4 == -1 )
          *err = *_errno();
      }
      else
      {
        *err = GetLastError();
      }
      v15 = GetProcessHeap();
      HeapFree(v15, 0, v14);
    }
    else
    {
      *err = 14;
    }
  }
  else
  {
    *err = GetLastError();
  }
  return v4;
}

```

## disassembly

```asm
0x140061110  push    rbx
0x140061112  push    rbp
0x140061113  push    rsi
0x140061114  push    rdi
0x140061115  push    r12
0x140061117  push    r14
0x140061119  push    r15
0x14006111b  sub     rsp, 30h
0x14006111f  or      esi, 0FFFFFFFFh
0x140061122  mov     [rsp+68h+cchWideChar], 0; cchWideChar
0x14006112a  mov     r14d, r8d
0x14006112d  mov     [rsp+68h+lpWideCharStr], 0; lpWideCharStr
0x140061136  mov     rdi, r9
0x140061139  mov     r15d, edx
0x14006113c  mov     r12, rcx
0x14006113f  mov     r8, rcx; lpMultiByteStr
0x140061142  lea     edx, [rsi+9]; dwFlags
0x140061145  or      r9d, esi; cbMultiByte
0x140061148  mov     ecx, 0FDE9h; CodePage
0x14006114d  call    cs:__imp_MultiByteToWideChar
0x140061154  nop     dword ptr [rax+rax+00h]
0x140061159  mov     ebp, eax
0x14006115b  test    eax, eax
0x14006115d  jnz     short loc_140061172
0x14006115f  call    cs:__imp_GetLastError
0x140061166  nop     dword ptr [rax+rax+00h]
0x14006116b  mov     [rdi], eax
0x14006116d  jmp     loc_140061232
0x140061172  inc     eax
0x140061174  movsxd  rbx, eax
0x140061177  add     rbx, rbx
0x14006117a  call    cs:__imp_GetProcessHeap
0x140061181  nop     dword ptr [rax+rax+00h]
0x140061186  mov     r8, rbx; dwBytes
0x140061189  xor     edx, edx; dwFlags
0x14006118b  mov     rcx, rax; hHeap
0x14006118e  call    cs:__imp_HeapAlloc
0x140061195  nop     dword ptr [rax+rax+00h]
0x14006119a  mov     rbx, rax
0x14006119d  test    rax, rax
0x1400611a0  jnz     short loc_1400611AD
0x1400611a2  mov     dword ptr [rdi], 0Eh
0x1400611a8  jmp     loc_140061232
0x1400611ad  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1400611b1  mov     [rsp+68h+cchWideChar], ebp; cchWideChar
0x1400611b5  mov     r8, r12; lpMultiByteStr
0x1400611b8  mov     [rsp+68h+lpWideCharStr], rbx; lpWideCharStr
0x1400611bd  mov     ecx, 0FDE9h; CodePage
0x1400611c2  lea     edx, [r9+9]; dwFlags
0x1400611c6  call    cs:__imp_MultiByteToWideChar
0x1400611cd  nop     dword ptr [rax+rax+00h]
0x1400611d2  test    eax, eax
0x1400611d4  jnz     short loc_1400611E6
0x1400611d6  call    cs:__imp_GetLastError
0x1400611dd  nop     dword ptr [rax+rax+00h]
0x1400611e2  mov     [rdi], eax
0x1400611e4  jmp     short loc_140061212
0x1400611e6  mov     r8d, r14d
0x1400611e9  mov     edx, r15d; OpenFlag
0x1400611ec  mov     rcx, rbx; FileName
0x1400611ef  call    cs:__imp__wopen
0x1400611f6  nop     dword ptr [rax+rax+00h]
0x1400611fb  mov     esi, eax
0x1400611fd  cmp     eax, 0FFFFFFFFh
0x140061200  jnz     short loc_140061212
0x140061202  call    cs:__imp__errno
0x140061209  nop     dword ptr [rax+rax+00h]
0x14006120e  mov     ecx, [rax]
0x140061210  mov     [rdi], ecx
0x140061212  call    cs:__imp_GetProcessHeap
0x140061219  nop     dword ptr [rax+rax+00h]
0x14006121e  mov     r8, rbx; lpMem
0x140061221  xor     edx, edx; dwFlags
0x140061223  mov     rcx, rax; hHeap
0x140061226  call    cs:__imp_HeapFree
0x14006122d  nop     dword ptr [rax+rax+00h]
0x140061232  movsxd  rax, esi
0x140061235  add     rsp, 30h
0x140061239  pop     r15
0x14006123b  pop     r14
0x14006123d  pop     r12
0x14006123f  pop     rdi
0x140061240  pop     rsi
0x140061241  pop     rbp
0x140061242  pop     rbx
0x140061243  retn
```
