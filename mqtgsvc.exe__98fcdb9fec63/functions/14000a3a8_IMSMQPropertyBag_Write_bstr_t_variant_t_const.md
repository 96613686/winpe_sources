# IMSMQPropertyBag::Write(_bstr_t,_variant_t const &)

- ea: `0x14000a3a8`
- end: `0x14000a42c`
- name: `?Write@IMSMQPropertyBag@@QEAAJV_bstr_t@@AEBV_variant_t@@@Z`
- size: `132`
- prototype: `__int64 __fastcall(struct IUnknown *, _bstr_t *, __int128 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000858c`

## callees

- `0x140003868`
- `0x14000a3a8`
- `0x14000ec38`
- `0x140020010`

## pseudocode

```c
__int64 __fastcall IMSMQPropertyBag::Write(struct IUnknown *a1, _bstr_t *a2, __int128 *a3)
{
  ULONG (__stdcall *AddRef)(IUnknown *); // r9
  __int64 v6; // rdx
  int v7; // eax
  unsigned int v8; // edi
  __int128 v10; // [rsp+20h] [rbp-28h] BYREF
  __int64 v11; // [rsp+30h] [rbp-18h]

  AddRef = a1->lpVtbl[2].AddRef;
  if ( *(_QWORD *)a2 )
    v6 = **(_QWORD **)a2;
  else
    v6 = 0;
  v10 = *a3;
  v11 = *((_QWORD *)a3 + 2);
  v7 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int128 *))AddRef)(a1, v6, &v10);
  v8 = v7;
  if ( v7 < 0 )
    _com_issue_errorex(v7, a1, &GUID_07f19951_ab28_11d2_8936_000000000000);
  _bstr_t::_Free(a2);
  return v8;
}

```

## disassembly

```asm
0x14000a3a8  mov     [rsp+arg_0], rbx
0x14000a3ad  mov     [rsp+arg_10], rsi
0x14000a3b2  mov     [rsp+arg_8], rdx
0x14000a3b7  push    rdi
0x14000a3b8  sub     rsp, 40h
0x14000a3bc  mov     rbx, rdx
0x14000a3bf  mov     rsi, rcx
0x14000a3c2  mov     rax, [rcx]
0x14000a3c5  mov     r9, [rax+38h]
0x14000a3c9  mov     rax, [rdx]
0x14000a3cc  test    rax, rax
0x14000a3cf  jz      short loc_14000A3D6
0x14000a3d1  mov     rdx, [rax]
0x14000a3d4  jmp     short loc_14000A3D8
0x14000a3d6  xor     edx, edx
0x14000a3d8  movups  xmm0, xmmword ptr [r8]
0x14000a3dc  movaps  [rsp+48h+var_28], xmm0
0x14000a3e1  movsd   xmm1, qword ptr [r8+10h]
0x14000a3e7  movsd   [rsp+48h+var_18], xmm1
0x14000a3ed  lea     r8, [rsp+48h+var_28]
0x14000a3f2  mov     rax, r9
0x14000a3f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a3fa  mov     edi, eax
0x14000a3fc  test    eax, eax
0x14000a3fe  jns     short loc_14000A412
0x14000a400  lea     r8, _GUID_07f19951_ab28_11d2_8936_000000000000; struct _GUID *
0x14000a407  mov     rdx, rsi; struct IUnknown *
0x14000a40a  mov     ecx, eax; int
0x14000a40c  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x14000a412  mov     rcx, rbx; this
0x14000a415  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14000a41a  mov     eax, edi
0x14000a41c  mov     rbx, [rsp+48h+arg_0]
0x14000a421  mov     rsi, [rsp+48h+arg_10]
0x14000a426  add     rsp, 40h
0x14000a42a  pop     rdi
0x14000a42b  retn
```
