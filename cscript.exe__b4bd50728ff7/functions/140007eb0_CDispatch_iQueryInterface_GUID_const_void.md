# CDispatch::iQueryInterface(_GUID const &,void * *)

- ea: `0x140007eb0`
- end: `0x140007ef8`
- name: `?iQueryInterface@CDispatch@@MEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `72`
- prototype: `__int64 __fastcall(CDispatch *__hidden this, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140007dc0`
- `0x140009ac0`
- `0x140009be0`

## callees

- `0x140007eb0`
- `0x140017010`

## pseudocode

```c
__int64 __fastcall CDispatch::iQueryInterface(CDispatch *this, const struct _GUID *a2, void **a3)
{
  __int64 v3; // rax

  v3 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IDispatch.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IDispatch.Data1 )
    v3 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IDispatch.Data4;
  if ( v3 )
  {
    *a3 = 0;
    return 2147500034LL;
  }
  else
  {
    *a3 = (void *)*((_QWORD *)this + 2);
    (*(void (__fastcall **)(CDispatch *))(*(_QWORD *)this + 24LL))(this);
    return 0;
  }
}

```

## disassembly

```asm
0x140007eb0  sub     rsp, 28h
0x140007eb4  mov     rax, [rdx]
0x140007eb7  sub     rax, qword ptr cs:IID_IDispatch.Data1
0x140007ebe  jnz     short loc_140007ECB
0x140007ec0  mov     rax, [rdx+8]
0x140007ec4  sub     rax, qword ptr cs:IID_IDispatch.Data4
0x140007ecb  test    rax, rax
0x140007ece  jnz     short loc_140007EE7
0x140007ed0  mov     rax, [rcx+10h]
0x140007ed4  mov     [r8], rax
0x140007ed7  mov     rax, [rcx]
0x140007eda  mov     rax, [rax+18h]
0x140007ede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007ee3  xor     eax, eax
0x140007ee5  jmp     short loc_140007EF3
0x140007ee7  mov     qword ptr [r8], 0
0x140007eee  mov     eax, 80004002h
0x140007ef3  add     rsp, 28h
0x140007ef7  retn
```
