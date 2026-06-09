# ATL::CComEnumImpl<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>>::Init(_GUID *,_GUID *,IUnknown *,ATL::CComEnumFlags)

- ea: `0x18000c438`
- end: `0x18000c49f`
- name: `?Init@?$CComEnumImpl@UIEnumDiscMasterFormats@@$1?IID_IEnumDiscMasterFormats@@3U_GUID@@BU3@V?$_Copy@U_GUID@@@ATL@@@ATL@@QEAAJPEAU_GUID@@0PEAUIUnknown@@W4CComEnumFlags@2@@Z`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b8f0`

## callees

- `0x18000c438`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComEnumImpl<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>>::Init(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5)
{
  __int64 v7; // rcx

  *(_QWORD *)(a1 + 16) = a2;
  *(_QWORD *)(a1 + 24) = a3;
  if ( *(_QWORD *)(a1 + 8) != a4 )
  {
    if ( a4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a4 + 8LL))(a4);
    v7 = *(_QWORD *)(a1 + 8);
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    *(_QWORD *)(a1 + 8) = a4;
  }
  *(_QWORD *)(a1 + 32) = *(_QWORD *)(a1 + 16);
  *(_DWORD *)(a1 + 40) = a5;
  return 0;
}

```

## disassembly

```asm
0x18000c438  mov     [rsp+arg_0], rbx
0x18000c43d  push    rdi
0x18000c43e  sub     rsp, 20h
0x18000c442  mov     [rcx+10h], rdx
0x18000c446  mov     rdi, r9
0x18000c449  mov     [rcx+18h], r8
0x18000c44d  mov     rbx, rcx
0x18000c450  cmp     [rcx+8], r9
0x18000c454  jz      short loc_18000C483
0x18000c456  test    r9, r9
0x18000c459  jz      short loc_18000C46A
0x18000c45b  mov     rax, [r9]
0x18000c45e  mov     rcx, r9
0x18000c461  mov     rax, [rax+8]
0x18000c465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c46a  mov     rcx, [rbx+8]
0x18000c46e  test    rcx, rcx
0x18000c471  jz      short loc_18000C47F
0x18000c473  mov     rax, [rcx]
0x18000c476  mov     rax, [rax+10h]
0x18000c47a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c47f  mov     [rbx+8], rdi
0x18000c483  mov     rax, [rbx+10h]
0x18000c487  mov     [rbx+20h], rax
0x18000c48b  mov     eax, [rsp+28h+arg_20]
0x18000c48f  mov     [rbx+28h], eax
0x18000c492  xor     eax, eax
0x18000c494  mov     rbx, [rsp+28h+arg_0]
0x18000c499  add     rsp, 20h
0x18000c49d  pop     rdi
0x18000c49e  retn
```
