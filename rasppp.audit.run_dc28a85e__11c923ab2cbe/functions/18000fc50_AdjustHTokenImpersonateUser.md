# AdjustHTokenImpersonateUser

- ea: `0x18000fc50`
- end: `0x18000fd33`
- name: `AdjustHTokenImpersonateUser`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000ecac`

## callees

- `0x18000fc50`
- `0x1800101bc`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000fd0c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000fd0c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000fccb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000fcda`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000fccb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000fcda`

## pseudocode

```c
int __fastcall AdjustHTokenImpersonateUser(__int64 a1)
{
  __int64 v1; // rax
  __int64 v3; // rdi
  __int64 *i; // rbx
  void *v5; // rbp
  HANDLE CurrentProcess; // rbx
  HANDLE v7; // rax
  HANDLE TargetHandle; // [rsp+70h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 8);
  TargetHandle = 0;
  if ( *(_QWORD *)(v1 + 64) == -1 )
  {
    v3 = 0;
LABEL_3:
    if ( (unsigned int)v3 < (unsigned int)qword_18004D970 )
    {
      LODWORD(v1) = (_DWORD)PcbTable;
      for ( i = (__int64 *)*((_QWORD *)PcbTable + v3); ; i = (__int64 *)*i )
      {
        if ( !i )
        {
          v3 = (unsigned int)(v3 + 1);
          goto LABEL_3;
        }
        v1 = *(_QWORD *)(a1 + 16);
        if ( i[2] != v1 && (i[7] & 1) != 0 )
        {
          v5 = *(void **)(i[1] + 64);
          LODWORD(v1) = CanPortsBeBundled(i, a1, 0);
          if ( (_DWORD)v1 )
          {
            if ( v5 != (void *)-1LL )
              break;
          }
        }
      }
      CurrentProcess = GetCurrentProcess();
      v7 = GetCurrentProcess();
      LODWORD(v1) = DuplicateHandle(v7, v5, CurrentProcess, &TargetHandle, 0, 1, 2u);
      if ( (_DWORD)v1 )
      {
        LODWORD(v1) = (_DWORD)TargetHandle;
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 64LL) = TargetHandle;
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18000fc50  push    rbx
0x18000fc52  push    rbp
0x18000fc53  push    rsi
0x18000fc54  push    rdi
0x18000fc55  sub     rsp, 48h
0x18000fc59  mov     rax, [rcx+8]
0x18000fc5d  mov     rsi, rcx
0x18000fc60  mov     [rsp+68h+TargetHandle], 0
0x18000fc69  cmp     qword ptr [rax+40h], 0FFFFFFFFFFFFFFFFh
0x18000fc6e  jnz     loc_18000FD29
0x18000fc74  xor     edi, edi
0x18000fc76  cmp     edi, dword ptr cs:qword_18004D970
0x18000fc7c  jnb     loc_18000FD29
0x18000fc82  mov     rax, qword ptr cs:PcbTable
0x18000fc89  mov     rbx, [rax+rdi*8]
0x18000fc8d  test    rbx, rbx
0x18000fc90  jz      short loc_18000FCC7
0x18000fc92  mov     rax, [rsi+10h]
0x18000fc96  cmp     [rbx+10h], rax
0x18000fc9a  jz      short loc_18000FCC2
0x18000fc9c  test    byte ptr [rbx+38h], 1
0x18000fca0  jz      short loc_18000FCC2
0x18000fca2  mov     rax, [rbx+8]
0x18000fca6  xor     r8d, r8d
0x18000fca9  mov     rdx, rsi
0x18000fcac  mov     rcx, rbx
0x18000fcaf  mov     rbp, [rax+40h]
0x18000fcb3  call    CanPortsBeBundled
0x18000fcb8  test    eax, eax
0x18000fcba  jz      short loc_18000FCC2
0x18000fcbc  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x18000fcc0  jnz     short loc_18000FCCB
0x18000fcc2  mov     rbx, [rbx]
0x18000fcc5  jmp     short loc_18000FC8D
0x18000fcc7  inc     edi
0x18000fcc9  jmp     short loc_18000FC76
0x18000fccb  call    cs:__imp_GetCurrentProcess
0x18000fcd2  nop     dword ptr [rax+rax+00h]
0x18000fcd7  mov     rbx, rax
0x18000fcda  call    cs:__imp_GetCurrentProcess
0x18000fce1  nop     dword ptr [rax+rax+00h]
0x18000fce6  mov     [rsp+68h+dwOptions], 2; dwOptions
0x18000fcee  lea     r9, [rsp+68h+TargetHandle]; lpTargetHandle
0x18000fcf3  mov     rcx, rax; hSourceProcessHandle
0x18000fcf6  mov     [rsp+68h+bInheritHandle], 1; bInheritHandle
0x18000fcfe  mov     r8, rbx; hTargetProcessHandle
0x18000fd01  mov     [rsp+68h+dwDesiredAccess], 0; dwDesiredAccess
0x18000fd09  mov     rdx, rbp; hSourceHandle
0x18000fd0c  call    cs:__imp_DuplicateHandle
0x18000fd13  nop     dword ptr [rax+rax+00h]
0x18000fd18  test    eax, eax
0x18000fd1a  jz      short loc_18000FD29
0x18000fd1c  mov     rcx, [rsi+8]
0x18000fd20  mov     rax, [rsp+68h+TargetHandle]
0x18000fd25  mov     [rcx+40h], rax
0x18000fd29  add     rsp, 48h
0x18000fd2d  pop     rdi
0x18000fd2e  pop     rsi
0x18000fd2f  pop     rbp
0x18000fd30  pop     rbx
0x18000fd31  retn
```
