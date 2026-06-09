# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDOServiceCallback,IDOServiceCallback2>::QueryInterface(_GUID const &,void * *)

- ea: `0x180009e10`
- end: `0x180009e82`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIDOServiceCallback@@UIDOServiceCallback2@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `114`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009e90`

## callees

- `0x1800023b0`
- `0x180009e10`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDOServiceCallback,IDOServiceCallback2>::QueryInterface(
        __int64 a1,
        const struct _GUID *a2,
        _QWORD *a3)
{
  unsigned int v3; // ebx
  const struct _GUID *v4; // rcx
  _QWORD *v5; // r8
  __int64 v6; // r9
  const struct _GUID *v7; // rcx
  _QWORD *v8; // r8
  __int64 v9; // r9

  v3 = 0;
  *a3 = 0;
  if ( (unsigned int)InlineIsEqualGUID(a2, &GUID_00000000_0000_0000_c000_000000000046) )
  {
    *v5 = v6;
    goto LABEL_8;
  }
  if ( (unsigned int)InlineIsEqualGUID(v4, &GUID_a92e7211_62cc_4a07_8e5c_2972f0bfe476) )
  {
LABEL_5:
    *v8 = v6;
LABEL_8:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
    return v3;
  }
  if ( (unsigned int)InlineIsEqualGUID(v7, &GUID_67ed8e25_a748_4265_a6d4_8cdd80016333) )
  {
    v6 = v9 + 8;
    goto LABEL_5;
  }
  return (unsigned int)-2147467262;
}

```

## disassembly

```asm
0x180009e10  push    rbx
0x180009e12  sub     rsp, 20h
0x180009e16  mov     r10, rdx
0x180009e19  mov     r9, rcx
0x180009e1c  xor     ebx, ebx
0x180009e1e  mov     [r8], rbx
0x180009e21  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x180009e28  mov     rcx, r10; struct _GUID *
0x180009e2b  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180009e30  test    eax, eax
0x180009e32  jnz     short loc_180009E67
0x180009e34  lea     rdx, _GUID_a92e7211_62cc_4a07_8e5c_2972f0bfe476; struct _GUID *
0x180009e3b  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180009e40  test    eax, eax
0x180009e42  jnz     short loc_180009E58
0x180009e44  lea     rdx, _GUID_67ed8e25_a748_4265_a6d4_8cdd80016333; struct _GUID *
0x180009e4b  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180009e50  test    eax, eax
0x180009e52  jz      short loc_180009E60
0x180009e54  add     r9, 8
0x180009e58  mov     rax, r9
0x180009e5b  mov     [r8], rax
0x180009e5e  jmp     short loc_180009E6A
0x180009e60  mov     ebx, 80004002h
0x180009e65  jmp     short loc_180009E7A
0x180009e67  mov     [r8], r9
0x180009e6a  mov     rax, [r9]
0x180009e6d  mov     rcx, r9
0x180009e70  mov     rax, [rax+8]
0x180009e74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e79  nop
0x180009e7a  mov     eax, ebx
0x180009e7c  add     rsp, 20h
0x180009e80  pop     rbx
0x180009e81  retn
```
