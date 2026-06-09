# ATL::CDynamicAccessor::ReleaseAccessors(IUnknown *)

- ea: `0x18000a330`
- end: `0x18000a418`
- name: `?ReleaseAccessors@CDynamicAccessor@ATL@@QEAAJPEAUIUnknown@@@Z`
- size: `232`
- prototype: `__int64 __fastcall(ATL::CDynamicAccessor *this, struct IRowset *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180008b10`
- `0x180008b98`

## callees

- `0x180008db4`
- `0x18000a330`
- `0x18000c010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000a3e2`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000a3e2`

## pseudocode

```c
__int64 __fastcall ATL::CDynamicAccessor::ReleaseAccessors(ATL::CDynamicAccessor *this, struct IRowset *a2)
{
  int v4; // edi
  unsigned int i; // esi
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

  ATL::CDynamicAccessor::FreeRecordMemory(this, a2);
  if ( !a2 )
    return (unsigned int)-2147467259;
  v4 = 0;
  if ( !*((_DWORD *)this + 2) )
    return (unsigned int)v4;
  v7 = 0;
  v4 = ((__int64 (__fastcall *)(struct IRowset *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
         a2,
         &GUID_0c733a8c_2a1c_11ce_ade5_00aa0044773d,
         &v7);
  if ( v4 >= 0 )
  {
    if ( !*(_QWORD *)this )
    {
      if ( v7 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      return (unsigned int)-2147467259;
    }
    for ( i = 0; i < *((_DWORD *)this + 2); ++i )
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v7 + 48LL))(
        v7,
        *(_QWORD *)(*(_QWORD *)this + 16LL * i),
        0);
  }
  *((_DWORD *)this + 2) = 0;
  operator delete[](*(void **)this);
  *(_QWORD *)this = 0;
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000a330  mov     [rsp+arg_0], rbx
0x18000a335  mov     [rsp+arg_10], rsi
0x18000a33a  push    rdi
0x18000a33b  sub     rsp, 20h
0x18000a33f  mov     rsi, rdx
0x18000a342  mov     rbx, rcx
0x18000a345  call    ?FreeRecordMemory@CDynamicAccessor@ATL@@QEAAXPEAUIRowset@@@Z; ATL::CDynamicAccessor::FreeRecordMemory(IRowset *)
0x18000a34a  nop
0x18000a34b  test    rsi, rsi
0x18000a34e  jnz     short loc_18000A35A
0x18000a350  mov     edi, 80004005h
0x18000a355  jmp     loc_18000A406
0x18000a35a  xor     edi, edi
0x18000a35c  cmp     [rbx+8], edi
0x18000a35f  jbe     loc_18000A406
0x18000a365  mov     [rsp+28h+arg_8], rdi
0x18000a36a  mov     rax, [rsi]
0x18000a36d  lea     r8, [rsp+28h+arg_8]
0x18000a372  lea     rdx, _GUID_0c733a8c_2a1c_11ce_ade5_00aa0044773d
0x18000a379  mov     rcx, rsi
0x18000a37c  mov     rax, [rax]
0x18000a37f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a384  mov     edi, eax
0x18000a386  test    eax, eax
0x18000a388  js      short loc_18000A3D8
0x18000a38a  cmp     qword ptr [rbx], 0
0x18000a38e  jnz     short loc_18000A3A9
0x18000a390  mov     rcx, [rsp+28h+arg_8]
0x18000a395  test    rcx, rcx
0x18000a398  jz      short loc_18000A3A7
0x18000a39a  mov     rax, [rcx]
0x18000a39d  mov     rax, [rax+10h]
0x18000a3a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3a6  nop
0x18000a3a7  jmp     short loc_18000A350
0x18000a3a9  xor     esi, esi
0x18000a3ab  cmp     [rbx+8], esi
0x18000a3ae  jbe     short loc_18000A3D8
0x18000a3b0  mov     rcx, [rsp+28h+arg_8]
0x18000a3b5  mov     rax, [rcx]
0x18000a3b8  mov     r9d, esi
0x18000a3bb  add     r9, r9
0x18000a3be  mov     rdx, [rbx]
0x18000a3c1  xor     r8d, r8d
0x18000a3c4  mov     rdx, [rdx+r9*8]
0x18000a3c8  mov     rax, [rax+30h]
0x18000a3cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3d1  inc     esi
0x18000a3d3  cmp     esi, [rbx+8]
0x18000a3d6  jb      short loc_18000A3B0
0x18000a3d8  mov     dword ptr [rbx+8], 0
0x18000a3df  mov     rcx, [rbx]
0x18000a3e2  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000a3e8  mov     qword ptr [rbx], 0
0x18000a3ef  mov     rcx, [rsp+28h+arg_8]
0x18000a3f4  test    rcx, rcx
0x18000a3f7  jz      short loc_18000A406
0x18000a3f9  mov     rdx, [rcx]
0x18000a3fc  mov     rax, [rdx+10h]
0x18000a400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a405  nop
0x18000a406  mov     eax, edi
0x18000a408  mov     rbx, [rsp+28h+arg_0]
0x18000a40d  mov     rsi, [rsp+28h+arg_10]
0x18000a412  add     rsp, 20h
0x18000a416  pop     rdi
0x18000a417  retn
```
