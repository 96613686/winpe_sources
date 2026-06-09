# KsecddLsaStateRef::KsecddLsaStateRef(void)

- ea: `0x180001c00`
- end: `0x180001cea`
- name: `??0KsecddLsaStateRef@@QEAA@XZ`
- size: `234`
- prototype: `KsecddLsaStateRef *__fastcall(KsecddLsaStateRef *__hidden this)`
- caller_count: `46`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001230`
- `0x180001478`
- `0x18000150c`
- `0x1800017c4`
- `0x1800018f8`
- `0x180001ae4`
- `0x1800021bc`
- `0x180004e7c`
- `0x180005160`
- `0x1800053e0`
- `0x180005718`
- `0x180005b58`
- `0x180005cf0`
- `0x180005e94`
- `0x18000ba98`
- `0x18000bcbc`
- `0x18000bf50`
- `0x18000c1f0`
- `0x18000d01c`
- `0x18000d2f0`
- `0x18000dad4`
- `0x18000f4ec`
- `0x180021a40`
- `0x180021b68`
- `0x18002267c`
- `0x1800230d0`
- `0x180024330`
- `0x180024910`
- `0x1800250e0`
- `0x180025220`
- `0x180025c20`
- `0x180025e00`
- `0x180026fb8`
- `0x180029008`
- `0x1800290c4`
- `0x180029180`
- `0x18002923c`
- `0x1800294a0`
- `0x180029570`
- `0x180029690`
- `0x1800297f0`
- `0x1800298e0`
- `0x180029aa0`
- `0x180029ba0`
- `0x180029c90`
- `0x180029d80`

## callees

- `0x180001c00`

## import_xrefs

- `ntoskrnl!PsGetCurrentServerSilo` at `0x180001c23`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x180001c4f`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x180001c23`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x180001c4f`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x180001c39`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x180001c39`
- `ntoskrnl!KeBugCheckEx` at `0x180001c72`
- `ntoskrnl!KeBugCheckEx` at `0x180001c72`

## pseudocode

```c
KsecddLsaStateRef *__fastcall KsecddLsaStateRef::KsecddLsaStateRef(KsecddLsaStateRef *this)
{
  unsigned int v1; // ebx
  __int64 CurrentServerSilo; // rax
  __int64 v4; // rdx
  ULONG_PTR v5; // rax
  signed __int64 v6; // rax
  signed __int64 v7; // rcx
  bool v8; // zf
  signed __int64 v9; // rtt
  __int64 v11; // [rsp+40h] [rbp+8h] BYREF

  v1 = KsecddSiloContextSlot;
  *(_QWORD *)this = 0;
  v11 = 0;
  CurrentServerSilo = PsGetCurrentServerSilo();
  PsGetPermanentSiloContext(CurrentServerSilo, v1, &v11);
  v4 = v11;
  if ( !v11 )
  {
    v5 = PsGetCurrentServerSilo();
    KeBugCheckEx(0x18Au, v5, 0, 0, 0);
  }
  _m_prefetchw((const void *)(v11 + 520));
  v6 = *(_QWORD *)(v11 + 520);
  v7 = v6 + 1;
  v8 = v6 == 0;
  if ( (unsigned __int64)(v6 + 1) <= 1 )
  {
LABEL_7:
    if ( !v8 )
      __fastfail(0xEu);
    return this;
  }
  else
  {
    while ( 1 )
    {
      v9 = v6;
      v6 = _InterlockedCompareExchange64((volatile signed __int64 *)(v4 + 520), v7, v6);
      if ( v9 == v6 )
        break;
      v7 = v6 + 1;
      if ( v6 == -1 || v6 == 0 )
      {
        v8 = v7 == 1;
        goto LABEL_7;
      }
    }
    *(_QWORD *)this = v11;
    return this;
  }
}

```

## disassembly

```asm
0x180001c00  mov     [rsp+arg_8], rbx
0x180001c05  push    rdi
0x180001c06  sub     rsp, 30h
0x180001c0a  mov     ebx, cs:?KsecddSiloContextSlot@@3KA; ulong KsecddSiloContextSlot
0x180001c10  mov     rdi, rcx
0x180001c13  mov     qword ptr [rcx], 0
0x180001c1a  mov     [rsp+38h+arg_0], 0
0x180001c23  call    cs:__imp_PsGetCurrentServerSilo
0x180001c2a  nop     dword ptr [rax+rax+00h]
0x180001c2f  lea     r8, [rsp+38h+arg_0]
0x180001c34  mov     edx, ebx
0x180001c36  mov     rcx, rax
0x180001c39  call    cs:__imp_PsGetPermanentSiloContext
0x180001c40  nop     dword ptr [rax+rax+00h]
0x180001c45  mov     rdx, [rsp+38h+arg_0]
0x180001c4a  test    rdx, rdx
0x180001c4d  jnz     short loc_180001C7F
0x180001c4f  call    cs:__imp_PsGetCurrentServerSilo
0x180001c56  nop     dword ptr [rax+rax+00h]
0x180001c5b  xor     r9d, r9d; BugCheckParameter3
0x180001c5e  mov     [rsp+38h+BugCheckParameter4], 0; BugCheckParameter4
0x180001c67  mov     rdx, rax; BugCheckParameter1
0x180001c6a  xor     r8d, r8d; BugCheckParameter2
0x180001c6d  mov     ecx, 18Ah; BugCheckCode
0x180001c72  call    cs:__imp_KeBugCheckEx
0x180001c7f  prefetchw byte ptr [rdx+208h]
0x180001c86  mov     rax, [rdx+208h]
0x180001c8d  lea     rcx, [rax+1]
0x180001c91  cmp     rcx, 1
0x180001c95  jbe     short loc_180001CBB
0x180001c97  nop     word ptr [rax+rax+00000000h]
0x180001ca0  lock cmpxchg [rdx+208h], rcx
0x180001ca9  mov     rcx, rax
0x180001cac  jz      short loc_180001CD3
0x180001cae  inc     rcx
0x180001cb1  cmp     rcx, 1
0x180001cb5  ja      short loc_180001CA0
0x180001cb7  cmp     rcx, 1
0x180001cbb  jz      short loc_180001CC4
0x180001cbd  mov     ecx, 0Eh
0x180001cc2  int     29h; Win8: RtlFailFast(ecx)
0x180001cc4  mov     rax, rdi
0x180001cc7  mov     rbx, [rsp+38h+arg_8]
0x180001ccc  add     rsp, 30h
0x180001cd0  pop     rdi
0x180001cd1  retn
0x180001cd3  mov     rax, [rsp+38h+arg_0]
0x180001cd8  mov     rbx, [rsp+38h+arg_8]
0x180001cdd  mov     [rdi], rax
0x180001ce0  mov     rax, rdi
0x180001ce3  add     rsp, 30h
0x180001ce7  pop     rdi
0x180001ce8  retn
```
