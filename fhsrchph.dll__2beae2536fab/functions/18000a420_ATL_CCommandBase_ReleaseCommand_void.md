# ATL::CCommandBase::ReleaseCommand(void)

- ea: `0x18000a420`
- end: `0x18000a4b5`
- name: `?ReleaseCommand@CCommandBase@ATL@@QEAAXXZ`
- size: `149`
- prototype: `void __fastcall(ATL::CCommandBase *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007bb8`
- `0x180008ca0`
- `0x1800099e4`

## callees

- `0x18000a420`
- `0x18000c010`

## pseudocode

```c
void __fastcall ATL::CCommandBase::ReleaseCommand(ATL::CCommandBase *this)
{
  int (__fastcall ***v2)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v3; // rcx
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  if ( *((_QWORD *)this + 1) )
  {
    v2 = *(int (__fastcall ****)(_QWORD, GUID *, __int64 *))this;
    if ( v2 )
    {
      v4 = 0;
      if ( (**v2)(v2, &GUID_0c733a8c_2a1c_11ce_ade5_00aa0044773d, &v4) >= 0 )
      {
        (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v4 + 48LL))(v4, *((_QWORD *)this + 1), 0);
        *((_QWORD *)this + 1) = 0;
      }
      if ( v4 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
  }
  v3 = *(_QWORD *)this;
  if ( *(_QWORD *)this )
  {
    *(_QWORD *)this = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
}

```

## disassembly

```asm
0x18000a420  push    rbx
0x18000a422  sub     rsp, 20h
0x18000a426  mov     rbx, rcx
0x18000a429  cmp     qword ptr [rcx+8], 0
0x18000a42e  jz      short loc_18000A493
0x18000a430  mov     rcx, [rcx]
0x18000a433  test    rcx, rcx
0x18000a436  jz      short loc_18000A493
0x18000a438  mov     [rsp+28h+arg_0], 0
0x18000a441  mov     rax, [rcx]
0x18000a444  lea     r8, [rsp+28h+arg_0]
0x18000a449  lea     rdx, _GUID_0c733a8c_2a1c_11ce_ade5_00aa0044773d
0x18000a450  mov     rax, [rax]
0x18000a453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a458  test    eax, eax
0x18000a45a  js      short loc_18000A47C
0x18000a45c  mov     rcx, [rsp+28h+arg_0]
0x18000a461  mov     rax, [rcx]
0x18000a464  xor     r8d, r8d
0x18000a467  mov     rdx, [rbx+8]
0x18000a46b  mov     rax, [rax+30h]
0x18000a46f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a474  mov     qword ptr [rbx+8], 0
0x18000a47c  mov     rcx, [rsp+28h+arg_0]
0x18000a481  test    rcx, rcx
0x18000a484  jz      short loc_18000A493
0x18000a486  mov     rax, [rcx]
0x18000a489  mov     rax, [rax+10h]
0x18000a48d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a492  nop
0x18000a493  mov     rcx, [rbx]
0x18000a496  test    rcx, rcx
0x18000a499  jz      short loc_18000A4AF
0x18000a49b  mov     qword ptr [rbx], 0
0x18000a4a2  mov     rax, [rcx]
0x18000a4a5  mov     rax, [rax+10h]
0x18000a4a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4ae  nop
0x18000a4af  add     rsp, 20h
0x18000a4b3  pop     rbx
0x18000a4b4  retn
```
