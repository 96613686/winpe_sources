# ThreadHandle<SNIThreadHandleAllocator>::WaitForAllThreadsToExit(unsigned __int64,ThreadHandle<SNIThreadHandleAllocator> *,ulong *)

- ea: `0x100416868`
- end: `0x10041695f`
- name: `?WaitForAllThreadsToExit@?$ThreadHandle@USNIThreadHandleAllocator@@@@SAK_KPEAV1@PEAK@Z`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x100419574`

## callees

- `0x100416868`
- `0x100548210`

## import_xrefs

- `KERNEL32!WaitForMultipleObjects` at `0x1004168d1`
- `KERNEL32!WaitForMultipleObjects` at `0x1004168d1`
- `KERNEL32!GetExitCodeThread` at `0x100416909`
- `KERNEL32!GetExitCodeThread` at `0x100416909`
- `KERNEL32!GetLastError` at `0x1004168e7`
- `KERNEL32!GetLastError` at `0x100416957`
- `KERNEL32!GetLastError` at `0x1004168e7`
- `KERNEL32!GetLastError` at `0x100416957`

## pseudocode

```c
DWORD __fastcall ThreadHandle<SNIThreadHandleAllocator>::WaitForAllThreadsToExit(
        unsigned __int64 a1,
        __int64 a2,
        DWORD *a3)
{
  unsigned __int64 v3; // rbx
  DWORD v7; // ebp
  HANDLE *v8; // rcx
  DWORD v9; // eax
  DWORD result; // eax
  unsigned __int64 v11; // rbx
  HANDLE Handles[64]; // [rsp+20h] [rbp-228h] BYREF

  v3 = 0;
  while ( v3 < a1 )
  {
    v7 = 0;
    v8 = Handles;
    do
    {
      if ( v3 >= a1 )
        break;
      ++v7;
      *v8++ = *(HANDLE *)(a2 + 8 * v3++);
    }
    while ( v7 < 0x40 );
    v9 = WaitForMultipleObjects(v7, Handles, 1, 0xFFFFFFFF);
    if ( v9 >= v7 )
    {
      if ( v9 == 258 )
        return 258;
      if ( v9 != -1 )
        return -2147418113;
      result = GetLastError();
      if ( result )
        return result;
    }
  }
  if ( !a3 )
    return 0;
  v11 = 0;
  if ( !a1 )
    return 0;
  while ( GetExitCodeThread(*(HANDLE *)(a2 + 8 * v11), a3) )
  {
    ++v11;
    ++a3;
    if ( v11 >= a1 )
      return 0;
  }
  return GetLastError();
}

```

## disassembly

```asm
0x100416868  mov     [rsp+arg_0], rbx
0x10041686d  mov     [rsp+arg_18], rbp
0x100416872  push    rsi
0x100416873  push    rdi
0x100416874  push    r14
0x100416876  sub     rsp, 230h
0x10041687d  mov     rax, cs:__security_cookie
0x100416884  xor     rax, rsp
0x100416887  mov     [rsp+248h+var_28], rax
0x10041688f  xor     ebx, ebx
0x100416891  mov     rsi, r8
0x100416894  mov     r14, rdx
0x100416897  mov     rdi, rcx
0x10041689a  test    rcx, rcx
0x10041689d  jz      short loc_1004168F6
0x10041689f  xor     ebp, ebp
0x1004168a1  lea     rcx, [rsp+248h+Handles]
0x1004168a6  cmp     rbx, rdi
0x1004168a9  jnb     short loc_1004168C0
0x1004168ab  mov     rax, [r14+rbx*8]
0x1004168af  inc     ebp
0x1004168b1  mov     [rcx], rax
0x1004168b4  inc     rbx
0x1004168b7  add     rcx, 8
0x1004168bb  cmp     ebp, 40h ; '@'
0x1004168be  jb      short loc_1004168A6
0x1004168c0  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1004168c4  lea     rdx, [rsp+248h+Handles]; lpHandles
0x1004168c9  mov     r8d, 1; bWaitAll
0x1004168cf  mov     ecx, ebp; nCount
0x1004168d1  call    cs:__imp_WaitForMultipleObjects
0x1004168d7  cmp     eax, ebp
0x1004168d9  jb      short loc_1004168F1
0x1004168db  cmp     eax, 102h
0x1004168e0  jz      short loc_100416950
0x1004168e2  cmp     eax, 0FFFFFFFFh
0x1004168e5  jnz     short loc_100416949
0x1004168e7  call    cs:__imp_GetLastError
0x1004168ed  test    eax, eax
0x1004168ef  jnz     short loc_100416921
0x1004168f1  cmp     rbx, rdi
0x1004168f4  jb      short loc_10041689F
0x1004168f6  test    rsi, rsi
0x1004168f9  jz      short loc_10041691F
0x1004168fb  xor     ebx, ebx
0x1004168fd  test    rdi, rdi
0x100416900  jz      short loc_10041691F
0x100416902  mov     rcx, [r14+rbx*8]; hThread
0x100416906  mov     rdx, rsi; lpExitCode
0x100416909  call    cs:__imp_GetExitCodeThread
0x10041690f  test    eax, eax
0x100416911  jz      short loc_100416957
0x100416913  inc     rbx
0x100416916  add     rsi, 4
0x10041691a  cmp     rbx, rdi
0x10041691d  jb      short loc_100416902
0x10041691f  xor     eax, eax
0x100416921  mov     rcx, [rsp+248h+var_28]
0x100416929  xor     rcx, rsp; StackCookie
0x10041692c  call    __security_check_cookie
0x100416931  lea     r11, [rsp+248h+var_18]
0x100416939  mov     rbx, [r11+20h]
0x10041693d  mov     rbp, [r11+38h]
0x100416941  mov     rsp, r11
0x100416944  pop     r14
0x100416946  pop     rdi
0x100416947  pop     rsi
0x100416948  retn
0x100416949  mov     eax, 8000FFFFh
0x10041694e  jmp     short loc_100416921
0x100416950  mov     eax, 102h
0x100416955  jmp     short loc_100416921
0x100416957  call    cs:__imp_GetLastError
0x10041695d  jmp     short loc_100416921
```
