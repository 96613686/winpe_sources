# CComBase::NDQueryInterface(_GUID const &,void * *)

- ea: `0x18000a1e0`
- end: `0x18000a229`
- name: `?NDQueryInterface@CComBase@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `73`
- prototype: `__int64 __fastcall(CComBase *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009300`

## callees

- `0x18000a1e0`
- `0x18000a230`

## pseudocode

```c
__int64 __fastcall CComBase::NDQueryInterface(CComBase *this, const struct _GUID *a2, void **a3)
{
  __int64 v4; // rax

  if ( !a3 )
    return 2147500035LL;
  v4 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
    v4 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IUnknown.Data4;
  if ( v4 )
  {
    *a3 = 0;
    return 2147500034LL;
  }
  else
  {
    CodecDSPGetInterface(this, a3);
    return 0;
  }
}

```

## disassembly

```asm
0x18000a1e0  sub     rsp, 28h
0x18000a1e4  test    r8, r8
0x18000a1e7  jnz     short loc_18000A1F0
0x18000a1e9  mov     eax, 80004003h
0x18000a1ee  jmp     short loc_18000A224
0x18000a1f0  mov     rax, [rdx]
0x18000a1f3  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x18000a1fa  jnz     short loc_18000A207
0x18000a1fc  mov     rax, [rdx+8]
0x18000a200  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x18000a207  test    rax, rax
0x18000a20a  jnz     short loc_18000A218
0x18000a20c  mov     rdx, r8
0x18000a20f  call    CodecDSPGetInterface
0x18000a214  xor     eax, eax
0x18000a216  jmp     short loc_18000A224
0x18000a218  mov     qword ptr [r8], 0
0x18000a21f  mov     eax, 80004002h
0x18000a224  add     rsp, 28h
0x18000a228  retn
```
