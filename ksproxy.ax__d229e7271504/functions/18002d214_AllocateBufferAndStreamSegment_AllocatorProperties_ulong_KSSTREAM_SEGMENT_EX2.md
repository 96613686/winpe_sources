# AllocateBufferAndStreamSegment(_AllocatorProperties *,ulong,_KSSTREAM_SEGMENT_EX2 * *)

- ea: `0x18002d214`
- end: `0x18002d34b`
- name: `?AllocateBufferAndStreamSegment@@YAJPEAU_AllocatorProperties@@KPEAPEAU_KSSTREAM_SEGMENT_EX2@@@Z`
- size: `311`
- prototype: `__int64 __fastcall(struct _AllocatorProperties *, int, struct _KSSTREAM_SEGMENT_EX2 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18002e2dc`

## callees

- `0x18001f1c4`
- `0x18001f1d0`
- `0x18001f210`
- `0x18001ffb0`
- `0x18002d214`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x18002d27a`
- `KERNEL32!CreateEventW` at `0x18002d27a`
- `KERNEL32!CloseHandle` at `0x18002d2f2`
- `KERNEL32!CloseHandle` at `0x18002d2f2`

## pseudocode

```c
__int64 __fastcall AllocateBufferAndStreamSegment(
        struct _AllocatorProperties *a1,
        int a2,
        struct _KSSTREAM_SEGMENT_EX2 **a3)
{
  void *v6; // rdi
  unsigned int v7; // ebx
  _DWORD *v8; // rsi
  HANDLE EventW; // rbp
  unsigned __int64 v10; // rdx
  void *v11; // rax
  unsigned __int64 v12; // rdx

  v6 = operator new(0x258u);
  if ( !v6 )
    return (unsigned int)-2147024882;
  v8 = operator new[]((unsigned int)(a2 + 56));
  if ( !v8 )
  {
    operator delete(v6, 0x258u);
    return (unsigned int)-2147024882;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  if ( EventW )
  {
    memset_0(v6, 0, 0x258u);
    memset_0(v8, 0, (unsigned int)(a2 + 56));
    v11 = operator new[](a1->cbBuffer);
    if ( v11 )
    {
      *v8 = a2 + 56;
      v7 = 0;
      *((_QWORD *)v8 + 5) = v11;
      v8[8] = a1->cbBuffer;
      *((_QWORD *)v6 + 69) = v8;
      *((_DWORD *)v6 + 137) = a2;
      *((_QWORD *)v6 + 4) = 0;
      *((_DWORD *)v6 + 136) = 0;
      *((_QWORD *)v6 + 73) = EventW;
      *((_QWORD *)v6 + 3) = EventW;
      *a3 = (struct _KSSTREAM_SEGMENT_EX2 *)v6;
    }
    else
    {
      v7 = -2147024882;
      operator delete(v6, 0x258u);
      operator delete(v8, v12);
      CloseHandle(EventW);
    }
  }
  else
  {
    operator delete(v6, 0x258u);
    operator delete(v8, v10);
    return (unsigned int)-2147467259;
  }
  return v7;
}

```

## disassembly

```asm
0x18002d214  push    rbx
0x18002d216  push    rbp
0x18002d217  push    rsi
0x18002d218  push    rdi
0x18002d219  push    r12
0x18002d21b  push    r13
0x18002d21d  push    r14
0x18002d21f  push    r15
0x18002d221  sub     rsp, 28h
0x18002d225  mov     r13, rcx
0x18002d228  mov     ebp, 258h
0x18002d22d  mov     ecx, ebp; Size
0x18002d22f  mov     r12, r8
0x18002d232  mov     r14d, edx
0x18002d235  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002d23a  mov     rdi, rax
0x18002d23d  test    rax, rax
0x18002d240  jnz     short loc_18002D24C
0x18002d242  mov     ebx, 8007000Eh
0x18002d247  jmp     loc_18002D337
0x18002d24c  lea     r15d, [r14+38h]
0x18002d250  mov     ecx, r15d; unsigned __int64
0x18002d253  mov     ebx, r15d
0x18002d256  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002d25b  mov     rsi, rax
0x18002d25e  test    rax, rax
0x18002d261  jnz     short loc_18002D270
0x18002d263  mov     rdx, rbp; unsigned __int64
0x18002d266  mov     rcx, rdi; void *
0x18002d269  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002d26e  jmp     short loc_18002D242
0x18002d270  xor     r9d, r9d; lpName
0x18002d273  xor     r8d, r8d; bInitialState
0x18002d276  xor     edx, edx; bManualReset
0x18002d278  xor     ecx, ecx; lpEventAttributes
0x18002d27a  call    cs:__imp_CreateEventW
0x18002d281  nop     dword ptr [rax+rax+00h]
0x18002d286  mov     rbp, rax
0x18002d289  mov     rcx, rdi; void *
0x18002d28c  test    rax, rax
0x18002d28f  jnz     short loc_18002D2AD
0x18002d291  mov     edx, 258h; unsigned __int64
0x18002d296  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002d29b  mov     rcx, rsi; void *
0x18002d29e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002d2a3  mov     ebx, 80004005h
0x18002d2a8  jmp     loc_18002D337
0x18002d2ad  xor     edx, edx; Val
0x18002d2af  mov     r8d, 258h; Size
0x18002d2b5  call    memset_0
0x18002d2ba  mov     r8, rbx; Size
0x18002d2bd  xor     edx, edx; Val
0x18002d2bf  mov     rcx, rsi; void *
0x18002d2c2  call    memset_0
0x18002d2c7  movsxd  rcx, dword ptr [r13+4]; unsigned __int64
0x18002d2cb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002d2d0  test    rax, rax
0x18002d2d3  jnz     short loc_18002D300
0x18002d2d5  mov     edx, 258h; unsigned __int64
0x18002d2da  mov     rcx, rdi; void *
0x18002d2dd  mov     ebx, 8007000Eh
0x18002d2e2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002d2e7  mov     rcx, rsi; void *
0x18002d2ea  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002d2ef  mov     rcx, rbp; hObject
0x18002d2f2  call    cs:__imp_CloseHandle
0x18002d2f9  nop     dword ptr [rax+rax+00h]
0x18002d2fe  jmp     short loc_18002D337
0x18002d300  mov     [rsi], r15d
0x18002d303  xor     ebx, ebx
0x18002d305  mov     [rsi+28h], rax
0x18002d309  mov     ecx, [r13+4]
0x18002d30d  mov     [rsi+20h], ecx
0x18002d310  mov     [rdi+228h], rsi
0x18002d317  mov     [rdi+224h], r14d
0x18002d31e  mov     [rdi+20h], rbx
0x18002d322  mov     [rdi+220h], ebx
0x18002d328  mov     [rdi+248h], rbp
0x18002d32f  mov     [rdi+18h], rbp
0x18002d333  mov     [r12], rdi
0x18002d337  mov     eax, ebx
0x18002d339  add     rsp, 28h
0x18002d33d  pop     r15
0x18002d33f  pop     r14
0x18002d341  pop     r13
0x18002d343  pop     r12
0x18002d345  pop     rdi
0x18002d346  pop     rsi
0x18002d347  pop     rbp
0x18002d348  pop     rbx
0x18002d349  retn
```
