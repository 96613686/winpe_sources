# CClfsLogFcbPhysical::Release(void)

- ea: `0x140008c70`
- end: `0x140008ea6`
- name: `?Release@CClfsLogFcbPhysical@@UEAAKXZ`
- size: `566`
- prototype: `unsigned int __fastcall(ULONG_PTR BugCheckParameter4)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140016210`
- `0x140016230`
- `0x140016250`
- `0x140016270`

## callees

- `0x140008c70`
- `0x140008eac`
- `0x140017f20`

## import_xrefs

- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140008e48`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140008e86`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140008e48`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140008e86`
- `ntoskrnl!KeClearEvent` at `0x140008cbb`
- `ntoskrnl!KeClearEvent` at `0x140008cbb`
- `ntoskrnl!KeBugCheckEx` at `0x140008d76`
- `ntoskrnl!KeBugCheckEx` at `0x140008da5`
- `ntoskrnl!KeBugCheckEx` at `0x140008d76`
- `ntoskrnl!KeBugCheckEx` at `0x140008da5`
- `ntoskrnl!ExAcquireFastMutex` at `0x140008d14`
- `ntoskrnl!ExAcquireFastMutex` at `0x140008d14`
- `ntoskrnl!ExReleaseFastMutex` at `0x140008d34`
- `ntoskrnl!ExReleaseFastMutex` at `0x140008d34`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140008c89`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140008c89`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140008cf0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140008cf0`

## pseudocode

```c
__int64 __fastcall CClfsLogFcbPhysical::Release(ULONG_PTR BugCheckParameter4)
{
  struct _FAST_MUTEX *v1; // rbp
  unsigned __int32 v3; // edi
  __int64 v4; // rcx
  __int64 v5; // rbp
  _QWORD *v7; // rcx
  _QWORD *v8; // r8
  ULONG_PTR v9; // rax
  __int64 v10; // rdx
  ULONG_PTR v11; // r14
  ULONG_PTR v12; // rax
  __int64 v13; // rcx
  ULONG_PTR BugCheckParameter3[2]; // [rsp+30h] [rbp-28h] BYREF

  v1 = *(struct _FAST_MUTEX **)(BugCheckParameter4 + 912);
  ExAcquireFastMutexUnsafe(v1);
  v3 = _InterlockedDecrement((volatile signed __int32 *)(BugCheckParameter4 + 368));
  if ( !v3 )
  {
    _InterlockedExchange((volatile __int32 *)(BugCheckParameter4 + 944), 1);
    KeClearEvent((PRKEVENT)(BugCheckParameter4 + 920));
    _InterlockedIncrement((volatile signed __int32 *)(BugCheckParameter4 + 1304));
  }
  v4 = *(_QWORD *)(BugCheckParameter4 + 912);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(BugCheckParameter4 + 1304), 0xFFFFFFFF) == 1 )
  {
    v9 = BugCheckParameter4 + 672;
    v10 = *(_QWORD *)(BugCheckParameter4 + 672);
    *(_OWORD *)BugCheckParameter3 = *(_OWORD *)(BugCheckParameter4 + 40);
    if ( v10 )
    {
      if ( *(_QWORD *)(v10 + 8) != v9 )
        goto LABEL_24;
      v7 = *(_QWORD **)(BugCheckParameter4 + 680);
      if ( *v7 != v9 )
        goto LABEL_24;
      *v7 = v10;
      *(_QWORD *)(v10 + 8) = v7;
      (*(void (__fastcall **)(ULONG_PTR, __int64))(*(_QWORD *)BugCheckParameter4 + 56LL))(BugCheckParameter4, 1);
    }
    else
    {
      v11 = v4 + 56;
      if ( !RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(v4 + 56), BugCheckParameter3)
        && (*(_DWORD *)(BugCheckParameter4 + 364) & 1) == 0 )
      {
        KeBugCheckEx(0xC1F5u, 0x23u, v11, (ULONG_PTR)BugCheckParameter3, BugCheckParameter4);
      }
    }
  }
  ExReleaseFastMutexUnsafe(v1);
  if ( !v3 )
  {
    CClfsLogFcbPhysical::Finalize((CClfsLogFcbPhysical *)BugCheckParameter4, 1);
    v5 = *(_QWORD *)(BugCheckParameter4 + 912);
    ExAcquireFastMutex((PFAST_MUTEX)v5);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(BugCheckParameter4 + 1304), 0xFFFFFFFF) != 1 )
    {
LABEL_6:
      ExReleaseFastMutex((PFAST_MUTEX)v5);
      return v3;
    }
    v12 = BugCheckParameter4 + 672;
    v13 = *(_QWORD *)(BugCheckParameter4 + 672);
    *(_OWORD *)BugCheckParameter3 = *(_OWORD *)(BugCheckParameter4 + 40);
    if ( !v13 )
    {
      if ( !RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(v5 + 56), BugCheckParameter3)
        && (*(_DWORD *)(BugCheckParameter4 + 364) & 1) == 0 )
      {
        KeBugCheckEx(0xC1F5u, 0x23u, v5 + 56, (ULONG_PTR)BugCheckParameter3, BugCheckParameter4);
      }
      goto LABEL_6;
    }
    if ( *(_QWORD *)(v13 + 8) == v12 )
    {
      v8 = *(_QWORD **)(BugCheckParameter4 + 680);
      if ( *v8 == v12 )
      {
        *v8 = v13;
        *(_QWORD *)(v13 + 8) = v8;
        (*(void (__fastcall **)(ULONG_PTR, __int64))(*(_QWORD *)BugCheckParameter4 + 56LL))(BugCheckParameter4, 1);
        goto LABEL_6;
      }
    }
LABEL_24:
    __fastfail(3u);
  }
  return v3;
}

```

## disassembly

```asm
0x140008c70  mov     [rsp+arg_10], rbx
0x140008c75  push    rbp
0x140008c76  push    rsi
0x140008c77  push    rdi
0x140008c78  sub     rsp, 40h
0x140008c7c  mov     rbp, [rcx+390h]
0x140008c83  mov     rbx, rcx
0x140008c86  mov     rcx, rbp; FastMutex
0x140008c89  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140008c90  nop     dword ptr [rax+rax+00h]
0x140008c95  mov     esi, 0FFFFFFFFh
0x140008c9a  mov     edi, esi
0x140008c9c  lock xadd [rbx+170h], edi
0x140008ca4  sub     edi, 1
0x140008ca7  jnz     short loc_140008CCE
0x140008ca9  mov     eax, 1
0x140008cae  lea     rcx, [rbx+398h]; Event
0x140008cb5  xchg    eax, [rbx+3B0h]
0x140008cbb  call    cs:__imp_KeClearEvent
0x140008cc2  nop     dword ptr [rax+rax+00h]
0x140008cc7  lock inc dword ptr [rbx+518h]
0x140008cce  mov     rcx, [rbx+390h]
0x140008cd5  mov     eax, esi
0x140008cd7  mov     [rsp+58h+arg_8], r14
0x140008cdc  lock xadd [rbx+518h], eax
0x140008ce4  cmp     eax, 1
0x140008ce7  jz      loc_140008E20
0x140008ced  mov     rcx, rbp; FastMutex
0x140008cf0  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140008cf7  nop     dword ptr [rax+rax+00h]
0x140008cfc  test    edi, edi
0x140008cfe  jnz     short loc_140008D40
0x140008d00  mov     dl, 1; unsigned __int8
0x140008d02  mov     rcx, rbx; this
0x140008d05  call    ?Finalize@CClfsLogFcbPhysical@@AEAAXE@Z; CClfsLogFcbPhysical::Finalize(uchar)
0x140008d0a  mov     rbp, [rbx+390h]
0x140008d11  mov     rcx, rbp; FastMutex
0x140008d14  call    cs:__imp_ExAcquireFastMutex
0x140008d1b  nop     dword ptr [rax+rax+00h]
0x140008d20  lock xadd [rbx+518h], esi
0x140008d28  cmp     esi, 1
0x140008d2b  jz      loc_140008E61
0x140008d31  mov     rcx, rbp; FastMutex
0x140008d34  call    cs:__imp_ExReleaseFastMutex
0x140008d3b  nop     dword ptr [rax+rax+00h]
0x140008d40  mov     r14, [rsp+58h+arg_8]
0x140008d45  mov     eax, edi
0x140008d47  mov     rbx, [rsp+58h+arg_10]
0x140008d4c  add     rsp, 40h
0x140008d50  pop     rdi
0x140008d51  pop     rsi
0x140008d52  pop     rbp
0x140008d53  retn
0x140008d55  mov     eax, [rbx+16Ch]
0x140008d5b  test    al, 1
0x140008d5d  jnz     short loc_140008CED
0x140008d5f  lea     r9, [rsp+58h+BugCheckParameter3]; BugCheckParameter3
0x140008d64  mov     [rsp+58h+BugCheckParameter4], rbx; BugCheckParameter4
0x140008d69  mov     r8, r14; BugCheckParameter2
0x140008d6c  mov     edx, 23h ; '#'; BugCheckParameter1
0x140008d71  mov     ecx, 0C1F5h; BugCheckCode
0x140008d76  call    cs:__imp_KeBugCheckEx
0x140008d83  mov     eax, [rbx+16Ch]
0x140008d89  test    al, 1
0x140008d8b  jnz     short loc_140008D31
0x140008d8d  lea     r9, [rsp+58h+BugCheckParameter3]; BugCheckParameter3
0x140008d92  mov     [rsp+58h+BugCheckParameter4], rbx; BugCheckParameter4
0x140008d97  lea     r8, [rbp+38h]; BugCheckParameter2
0x140008d9b  mov     edx, 23h ; '#'; BugCheckParameter1
0x140008da0  mov     ecx, 0C1F5h; BugCheckCode
0x140008da5  call    cs:__imp_KeBugCheckEx
0x140008db2  cmp     [rdx+8], rax
0x140008db6  jnz     loc_140008E9F
0x140008dbc  mov     rcx, [rax+8]
0x140008dc0  cmp     [rcx], rax
0x140008dc3  jnz     loc_140008E9F
0x140008dc9  mov     [rcx], rdx
0x140008dcc  mov     [rdx+8], rcx
0x140008dd0  mov     edx, 1
0x140008dd5  mov     rax, [rbx]
0x140008dd8  mov     rcx, rbx
0x140008ddb  mov     rax, [rax+38h]
0x140008ddf  call    _guard_dispatch_icall
0x140008de4  jmp     loc_140008CED
0x140008de9  cmp     [rcx+8], rax
0x140008ded  jnz     loc_140008E9F
0x140008df3  mov     r8, [rax+8]
0x140008df7  cmp     [r8], rax
0x140008dfa  jnz     loc_140008E9F
0x140008e00  mov     [r8], rcx
0x140008e03  mov     edx, 1
0x140008e08  mov     [rcx+8], r8
0x140008e0c  mov     rcx, rbx
0x140008e0f  mov     rax, [rbx]
0x140008e12  mov     rax, [rax+38h]
0x140008e16  call    _guard_dispatch_icall
0x140008e1b  jmp     loc_140008D31
0x140008e20  movups  xmm0, xmmword ptr [rbx+28h]
0x140008e24  lea     rax, [rbx+2A0h]
0x140008e2b  mov     rdx, [rax]
0x140008e2e  movups  xmmword ptr [rsp+58h+BugCheckParameter3], xmm0
0x140008e33  test    rdx, rdx
0x140008e36  jnz     loc_140008DB2
0x140008e3c  lea     r14, [rcx+38h]
0x140008e40  mov     rcx, r14; Table
0x140008e43  lea     rdx, [rsp+58h+BugCheckParameter3]; Buffer
0x140008e48  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140008e4f  nop     dword ptr [rax+rax+00h]
0x140008e54  test    al, al
0x140008e56  jnz     loc_140008CED
0x140008e5c  jmp     loc_140008D55
0x140008e61  movups  xmm0, xmmword ptr [rbx+28h]
0x140008e65  lea     rax, [rbx+2A0h]
0x140008e6c  mov     rcx, [rax]
0x140008e6f  movups  xmmword ptr [rsp+58h+BugCheckParameter3], xmm0
0x140008e74  test    rcx, rcx
0x140008e77  jnz     loc_140008DE9
0x140008e7d  lea     rdx, [rsp+58h+BugCheckParameter3]; Buffer
0x140008e82  lea     rcx, [rbp+38h]; Table
0x140008e86  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140008e8d  nop     dword ptr [rax+rax+00h]
0x140008e92  test    al, al
0x140008e94  jnz     loc_140008D31
0x140008e9a  jmp     loc_140008D83
0x140008e9f  mov     ecx, 3
0x140008ea4  int     29h; Win8: RtlFailFast(ecx)
```
