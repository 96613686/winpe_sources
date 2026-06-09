# NamedSem_Open_Injected

- ea: `0x180006f28`
- end: `0x180006f9d`
- name: `NamedSem_Open_Injected`
- size: `117`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006b70`

## callees

- `0x180006f28`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006f80`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006f80`

## pseudocode

```c
__int64 __fastcall NamedSem_Open_Injected(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        const WCHAR *a4,
        __int64 a5,
        __int128 *a6)
{
  __int64 v8; // xmm1_8
  HANDLE v10; // rax
  __int128 v11; // [rsp+20h] [rbp-28h] BYREF
  __int64 v12; // [rsp+30h] [rbp-18h]

  if ( NITS_PRESENCE_STUB != 1 )
  {
    v8 = *((_QWORD *)a6 + 2);
    v11 = *a6;
    v12 = v8;
    if ( ((unsigned int (__fastcall *)(__int128 *, _QWORD))NITS_STUB[0])(&v11, 0) )
      return 0xFFFFFFFFLL;
  }
  v10 = OpenSemaphoreW(0x1F0003u, 0, a4);
  *a1 = v10;
  return (unsigned int)(v10 != 0) - 1;
}

```

## disassembly

```asm
0x180006f28  mov     [rsp+arg_0], rbx
0x180006f2d  push    rdi
0x180006f2e  sub     rsp, 40h
0x180006f32  cmp     cs:NITS_PRESENCE_STUB, 1
0x180006f3a  mov     rbx, r9
0x180006f3d  mov     rdi, rcx
0x180006f40  jz      short loc_180006F76
0x180006f42  mov     rax, [rsp+48h+arg_28]
0x180006f47  lea     rcx, [rsp+48h+var_28]
0x180006f4c  xor     edx, edx
0x180006f4e  movaps  xmm0, xmmword ptr [rax]
0x180006f51  movsd   xmm1, qword ptr [rax+10h]
0x180006f56  mov     rax, cs:NITS_STUB
0x180006f5d  movaps  [rsp+48h+var_28], xmm0
0x180006f62  movsd   [rsp+48h+var_18], xmm1
0x180006f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f6d  test    eax, eax
0x180006f6f  jz      short loc_180006F76
0x180006f71  or      eax, 0FFFFFFFFh
0x180006f74  jmp     short loc_180006F92
0x180006f76  mov     r8, rbx; lpName
0x180006f79  xor     edx, edx; bInheritHandle
0x180006f7b  mov     ecx, 1F0003h; dwDesiredAccess
0x180006f80  call    cs:__imp_OpenSemaphoreW
0x180006f86  mov     [rdi], rax
0x180006f89  neg     rax
0x180006f8c  sbb     eax, eax
0x180006f8e  neg     eax
0x180006f90  dec     eax
0x180006f92  mov     rbx, [rsp+48h+arg_0]
0x180006f97  add     rsp, 40h
0x180006f9b  pop     rdi
0x180006f9c  retn
```
