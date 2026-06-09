# bCreateSemaphores(CDDPDEV *)

- ea: `0x140018c68`
- end: `0x140018d94`
- name: `?bCreateSemaphores@@YAHPEAUCDDPDEV@@@Z`
- size: `300`
- prototype: `__int64 __fastcall(struct CDDPDEV *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001d980`

## callees

- `0x140018c68`

## import_xrefs

- `ntoskrnl!KeInitializeMutex` at `0x140018d0a`
- `ntoskrnl!KeInitializeMutex` at `0x140018d0a`
- `ntoskrnl!KeInitializeSemaphore` at `0x140018cf1`
- `ntoskrnl!KeInitializeSemaphore` at `0x140018cf1`
- `WIN32K!EngCreateSemaphore` at `0x140018c7a`
- `WIN32K!EngCreateSemaphore` at `0x140018c8d`
- `WIN32K!EngCreateSemaphore` at `0x140018d50`
- `WIN32K!EngCreateSemaphore` at `0x140018c7a`
- `WIN32K!EngCreateSemaphore` at `0x140018c8d`
- `WIN32K!EngCreateSemaphore` at `0x140018d50`
- `WIN32K!EngAllocMem` at `0x140018cae`
- `WIN32K!EngAllocMem` at `0x140018cae`

## pseudocode

```c
__int64 __fastcall bCreateSemaphores(struct CDDPDEV *a1)
{
  struct _KSEMAPHORE *v2; // rax
  bool v3; // zf
  __int64 i; // rsi
  unsigned int j; // edi
  HSEMAPHORE Semaphore; // rax

  *((_QWORD *)a1 + 365) = EngCreateSemaphore();
  *((_QWORD *)a1 + 448) = EngCreateSemaphore();
  v2 = (struct _KSEMAPHORE *)EngAllocMem(6u, 0x60u, 0x6F6C5343u);
  v3 = *((_QWORD *)a1 + 365) == 0;
  *((_QWORD *)a1 + 449) = v2;
  if ( v3 || !*((_QWORD *)a1 + 448) || !v2 )
    return 0;
  KeInitializeSemaphore(v2, 0, 0x7FFFFFFF);
  KeInitializeMutex((PRKMUTEX)(*((_QWORD *)a1 + 449) + 32LL), 0);
  *(_DWORD *)(*((_QWORD *)a1 + 449) + 88LL) = 0;
  *((_DWORD *)a1 + 894) = *((_DWORD *)a1 + 199) >> 3;
  *((_DWORD *)a1 + 895) = *((_DWORD *)a1 + 200) >> 3;
  for ( i = 0; (unsigned int)i < 9; i = (unsigned int)(i + 1) )
  {
    for ( j = 0; j < 9; ++j )
    {
      Semaphore = EngCreateSemaphore();
      *((_QWORD *)a1 + 9 * i + j + 366) = Semaphore;
      if ( !Semaphore )
        return 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x140018c68  mov     [rsp+arg_0], rbx
0x140018c6d  mov     [rsp+arg_8], rsi
0x140018c72  push    rdi
0x140018c73  sub     rsp, 20h
0x140018c77  mov     rbx, rcx
0x140018c7a  call    cs:__imp_EngCreateSemaphore
0x140018c81  nop     dword ptr [rax+rax+00h]
0x140018c86  mov     [rbx+0B68h], rax
0x140018c8d  call    cs:__imp_EngCreateSemaphore
0x140018c94  nop     dword ptr [rax+rax+00h]
0x140018c99  mov     edx, 60h ; '`'; cjMemSize
0x140018c9e  mov     r8d, 6F6C5343h; ulTag
0x140018ca4  mov     [rbx+0E00h], rax
0x140018cab  lea     ecx, [rdx-5Ah]; fl
0x140018cae  call    cs:__imp_EngAllocMem
0x140018cb5  nop     dword ptr [rax+rax+00h]
0x140018cba  cmp     qword ptr [rbx+0B68h], 0
0x140018cc2  mov     [rbx+0E08h], rax
0x140018cc9  jz      loc_140018D90
0x140018ccf  cmp     qword ptr [rbx+0E00h], 0
0x140018cd7  jz      loc_140018D90
0x140018cdd  test    rax, rax
0x140018ce0  jz      loc_140018D90
0x140018ce6  xor     edx, edx; Count
0x140018ce8  mov     r8d, 7FFFFFFFh; Limit
0x140018cee  mov     rcx, rax; Semaphore
0x140018cf1  call    cs:__imp_KeInitializeSemaphore
0x140018cf8  nop     dword ptr [rax+rax+00h]
0x140018cfd  mov     rcx, [rbx+0E08h]
0x140018d04  xor     edx, edx; Level
0x140018d06  add     rcx, 20h ; ' '; Mutex
0x140018d0a  call    cs:__imp_KeInitializeMutex
0x140018d11  nop     dword ptr [rax+rax+00h]
0x140018d16  mov     rax, [rbx+0E08h]
0x140018d1d  mov     dword ptr [rax+58h], 0
0x140018d24  mov     eax, [rbx+31Ch]
0x140018d2a  shr     eax, 3
0x140018d2d  mov     [rbx+0DF8h], eax
0x140018d33  mov     eax, [rbx+320h]
0x140018d39  shr     eax, 3
0x140018d3c  mov     [rbx+0DFCh], eax
0x140018d42  xor     esi, esi
0x140018d44  cmp     esi, 9
0x140018d47  jnb     short loc_140018D7A
0x140018d49  xor     edi, edi
0x140018d4b  cmp     edi, 9
0x140018d4e  jnb     short loc_140018D76
0x140018d50  call    cs:__imp_EngCreateSemaphore
0x140018d57  nop     dword ptr [rax+rax+00h]
0x140018d5c  lea     rdx, [rsi+rsi*8]
0x140018d60  mov     ecx, edi
0x140018d62  add     rdx, rcx
0x140018d65  mov     [rbx+rdx*8+0B70h], rax
0x140018d6d  test    rax, rax
0x140018d70  jz      short loc_140018D90
0x140018d72  inc     edi
0x140018d74  jmp     short loc_140018D4B
0x140018d76  inc     esi
0x140018d78  jmp     short loc_140018D44
0x140018d7a  mov     eax, 1
0x140018d7f  mov     rbx, [rsp+28h+arg_0]
0x140018d84  mov     rsi, [rsp+28h+arg_8]
0x140018d89  add     rsp, 20h
0x140018d8d  pop     rdi
0x140018d8e  retn
0x140018d90  xor     eax, eax
0x140018d92  jmp     short loc_140018D7F
```
