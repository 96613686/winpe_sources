# ATL::CCommandBase::Create(ATL::CSession const &,ushort const *,_GUID const &)

- ea: `0x180008ca0`
- end: `0x180008dad`
- name: `?Create@CCommandBase@ATL@@QEAAJAEBVCSession@2@PEBGAEBU_GUID@@@Z`
- size: `269`
- prototype: `__int64 __fastcall(ATL::CCommandBase *__hidden this, const struct ATL::CSession *, const unsigned __int16 *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009790`

## callees

- `0x180008ca0`
- `0x18000a420`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CCommandBase::Create(
        ATL::CCommandBase *this,
        const struct ATL::CSession *a2,
        const unsigned __int16 *a3,
        const struct _GUID *a4)
{
  int v7; // ebx
  const struct _GUID *v9; // [rsp+58h] [rbp+20h] BYREF

  v9 = a4;
  ATL::CCommandBase::ReleaseCommand(this);
  v9 = 0;
  v7 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, const struct _GUID **))a2)(
         *(_QWORD *)a2,
         &GUID_0c733a1d_2a1c_11ce_ade5_00aa0044773d,
         &v9);
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(const struct _GUID *, _QWORD, GUID *, ATL::CCommandBase *))(*(_QWORD *)&v9->Data1
                                                                                              + 24LL))(
           v9,
           0,
           &GUID_0c733a63_2a1c_11ce_ade5_00aa0044773d,
           this);
    if ( v9 )
      (*(void (__fastcall **)(const struct _GUID *))(*(_QWORD *)&v9->Data1 + 16LL))(v9);
  }
  else if ( v9 )
  {
    (*(void (__fastcall **)(const struct _GUID *))(*(_QWORD *)&v9->Data1 + 16LL))(v9);
  }
  if ( v7 >= 0 )
  {
    v9 = 0;
    v7 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, const struct _GUID **))this)(
           *(_QWORD *)this,
           &GUID_0c733a27_2a1c_11ce_ade5_00aa0044773d,
           &v9);
    if ( v7 >= 0 )
      v7 = (*(__int64 (__fastcall **)(const struct _GUID *, const GUID *, const unsigned __int16 *))(*(_QWORD *)&v9->Data1 + 56LL))(
             v9,
             &DBGUID_DEFAULT,
             a3);
    if ( v9 )
      (*(void (__fastcall **)(const struct _GUID *))(*(_QWORD *)&v9->Data1 + 16LL))(v9);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180008ca0  mov     [rsp+arg_0], rbx
0x180008ca5  mov     [rsp+arg_8], rsi
0x180008caa  mov     [rsp+arg_18], r9
0x180008caf  push    rdi
0x180008cb0  sub     rsp, 30h
0x180008cb4  mov     rsi, r8
0x180008cb7  mov     rbx, rdx
0x180008cba  mov     rdi, rcx
0x180008cbd  call    ?ReleaseCommand@CCommandBase@ATL@@QEAAXXZ; ATL::CCommandBase::ReleaseCommand(void)
0x180008cc2  mov     [rsp+38h+arg_18], 0
0x180008ccb  mov     rcx, [rbx]
0x180008cce  mov     rax, [rcx]
0x180008cd1  lea     r8, [rsp+38h+arg_18]
0x180008cd6  lea     rdx, _GUID_0c733a1d_2a1c_11ce_ade5_00aa0044773d
0x180008cdd  mov     rax, [rax]
0x180008ce0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ce5  mov     ebx, eax
0x180008ce7  test    eax, eax
0x180008ce9  jns     short loc_180008D04
0x180008ceb  mov     rcx, [rsp+38h+arg_18]
0x180008cf0  test    rcx, rcx
0x180008cf3  jz      short loc_180008D02
0x180008cf5  mov     rax, [rcx]
0x180008cf8  mov     rax, [rax+10h]
0x180008cfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d01  nop
0x180008d02  jmp     short loc_180008D3A
0x180008d04  mov     rcx, [rsp+38h+arg_18]
0x180008d09  mov     rax, [rcx]
0x180008d0c  mov     r9, rdi
0x180008d0f  lea     r8, _GUID_0c733a63_2a1c_11ce_ade5_00aa0044773d
0x180008d16  xor     edx, edx
0x180008d18  mov     rax, [rax+18h]
0x180008d1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d21  mov     ebx, eax
0x180008d23  mov     rcx, [rsp+38h+arg_18]
0x180008d28  test    rcx, rcx
0x180008d2b  jz      short loc_180008D3A
0x180008d2d  mov     rax, [rcx]
0x180008d30  mov     rax, [rax+10h]
0x180008d34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d39  nop
0x180008d3a  test    ebx, ebx
0x180008d3c  js      short loc_180008D9B
0x180008d3e  mov     [rsp+38h+arg_18], 0
0x180008d47  mov     rcx, [rdi]
0x180008d4a  mov     rax, [rcx]
0x180008d4d  lea     r8, [rsp+38h+arg_18]
0x180008d52  lea     rdx, _GUID_0c733a27_2a1c_11ce_ade5_00aa0044773d
0x180008d59  mov     rax, [rax]
0x180008d5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d61  mov     ebx, eax
0x180008d63  test    eax, eax
0x180008d65  js      short loc_180008D84
0x180008d67  mov     rcx, [rsp+38h+arg_18]
0x180008d6c  mov     rax, [rcx]
0x180008d6f  mov     r8, rsi
0x180008d72  lea     rdx, DBGUID_DEFAULT
0x180008d79  mov     rax, [rax+38h]
0x180008d7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d82  mov     ebx, eax
0x180008d84  mov     rcx, [rsp+38h+arg_18]
0x180008d89  test    rcx, rcx
0x180008d8c  jz      short loc_180008D9B
0x180008d8e  mov     rax, [rcx]
0x180008d91  mov     rax, [rax+10h]
0x180008d95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d9a  nop
0x180008d9b  mov     eax, ebx
0x180008d9d  mov     rbx, [rsp+38h+arg_0]
0x180008da2  mov     rsi, [rsp+38h+arg_8]
0x180008da7  add     rsp, 30h
0x180008dab  pop     rdi
0x180008dac  retn
```
