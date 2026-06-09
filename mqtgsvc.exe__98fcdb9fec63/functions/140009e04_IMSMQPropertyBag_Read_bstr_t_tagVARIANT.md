# IMSMQPropertyBag::Read(_bstr_t,tagVARIANT *)

- ea: `0x140009e04`
- end: `0x140009e6e`
- name: `?Read@IMSMQPropertyBag@@QEAAJV_bstr_t@@PEAUtagVARIANT@@@Z`
- size: `106`
- prototype: `__int64 __fastcall(struct IUnknown *, _bstr_t *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140009358`
- `0x14000d648`

## callees

- `0x140003868`
- `0x140009e04`
- `0x14000ec38`
- `0x140020010`

## pseudocode

```c
__int64 __fastcall IMSMQPropertyBag::Read(struct IUnknown *a1, _bstr_t *a2)
{
  __int64 v4; // rdx
  int v5; // eax
  unsigned int v6; // ebx

  if ( *(_QWORD *)a2 )
    v4 = **(_QWORD **)a2;
  else
    v4 = 0;
  v5 = ((__int64 (__fastcall *)(struct IUnknown *, __int64))a1->lpVtbl[2].Release)(a1, v4);
  v6 = v5;
  if ( v5 < 0 )
    _com_issue_errorex(v5, a1, &GUID_07f19951_ab28_11d2_8936_000000000000);
  _bstr_t::_Free(a2);
  return v6;
}

```

## disassembly

```asm
0x140009e04  mov     [rsp+arg_0], rbx
0x140009e09  mov     [rsp+arg_10], rsi
0x140009e0e  mov     [rsp+arg_8], rdx
0x140009e13  push    rdi
0x140009e14  sub     rsp, 20h
0x140009e18  mov     rdi, rdx
0x140009e1b  mov     rsi, rcx
0x140009e1e  mov     rax, [rcx]
0x140009e21  mov     r9, [rax+40h]
0x140009e25  mov     rax, [rdx]
0x140009e28  test    rax, rax
0x140009e2b  jz      short loc_140009E32
0x140009e2d  mov     rdx, [rax]
0x140009e30  jmp     short loc_140009E34
0x140009e32  xor     edx, edx
0x140009e34  mov     rax, r9
0x140009e37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009e3c  mov     ebx, eax
0x140009e3e  test    eax, eax
0x140009e40  jns     short loc_140009E54
0x140009e42  lea     r8, _GUID_07f19951_ab28_11d2_8936_000000000000; struct _GUID *
0x140009e49  mov     rdx, rsi; struct IUnknown *
0x140009e4c  mov     ecx, eax; int
0x140009e4e  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x140009e54  mov     rcx, rdi; this
0x140009e57  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x140009e5c  mov     eax, ebx
0x140009e5e  mov     rbx, [rsp+28h+arg_0]
0x140009e63  mov     rsi, [rsp+28h+arg_10]
0x140009e68  add     rsp, 20h
0x140009e6c  pop     rdi
0x140009e6d  retn
```
