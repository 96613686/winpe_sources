# Microsoft::WRL::Details::RuntimeClassBaseT<2>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMFD3D12SynchronizationObjectCommands,IMFD3D12SynchronizationObject,IMFD3D12SynchronizationObjectCommandsInternal,IMFD3D11SynchronizationObjectCommands,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMFD3D12SynchronizationObjectCommands,IMFD3D12SynchronizationObject,IMFD3D12SynchronizationObjectCommandsInternal,IMFD3D11SynchronizationObjectCommands,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)

- ea: `0x180066b9c`
- end: `0x180066c7a`
- name: `??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIMFD3D12SynchronizationObjectCommands@@UIMFD3D12SynchronizationObject@@UIMFD3D12SynchronizationObjectCommandsInternal@@UIMFD3D11SynchronizationObjectCommands@@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$01@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIMFD3D12SynchronizationObjectCommands@@UIMFD3D12SynchronizationObject@@UIMFD3D12SynchronizationObjectCommandsInternal@@UIMFD3D11SynchronizationObjectCommands@@VFtmBase@23@@123@AEBU_GUID@@PEAPEAX@Z`
- size: `222`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180069b14`
- `0x18006aa60`
- `0x18006cc58`

## callees

- `0x18004d87c`
- `0x180066b9c`
- `0x180070010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassBaseT<2>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMFD3D12SynchronizationObjectCommands,IMFD3D12SynchronizationObject,IMFD3D12SynchronizationObjectCommandsInternal,IMFD3D11SynchronizationObjectCommands,Microsoft::WRL::FtmBase>>(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v3; // rcx
  _QWORD *v4; // r8
  __int64 v5; // r10
  __int64 v6; // rcx
  _QWORD *v7; // r8
  __int64 v8; // r10
  int v9; // ebx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // r10
  __int64 v13; // rcx
  __int64 v14; // rcx

  *a3 = 0;
  if ( !(unsigned int)InlineIsEqualGUID(a2, &GUID_00000000_0000_0000_c000_000000000046) )
  {
    if ( (unsigned int)InlineIsEqualGUID(v3, &GUID_09d0f835_92ff_4e53_8efa_40faa551f233)
      || (unsigned int)InlineIsEqualGUID(v6, &GUID_802302b0_82de_45e1_b421_f19ee5bdaf23) )
    {
      *v7 = v8;
      v9 = 0;
    }
    else
    {
      if ( (unsigned int)InlineIsEqualGUID(v10, &GUID_312cd3b9_7923_438d_bb2b_04cc603c6158)
        || (unsigned int)InlineIsEqualGUID(v11, &GUID_2f7563e0_1f9a_4317_99de_700ede97eebe)
        || (unsigned int)InlineIsEqualGUID(v13, &GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90)
        || (unsigned int)InlineIsEqualGUID(v14, &GUID_00000003_0000_0000_c000_000000000046) )
      {
        *v7 = v12;
        v9 = 0;
      }
      else
      {
        v9 = -2147467262;
      }
      if ( v9 < 0 )
        return (unsigned int)v9;
    }
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 8LL))(*v7);
    return (unsigned int)v9;
  }
  *v4 = v5;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
  return 0;
}

```

## disassembly

```asm
0x180066b9c  push    rbx
0x180066b9e  sub     rsp, 20h
0x180066ba2  mov     r9, rdx
0x180066ba5  mov     r10, rcx
0x180066ba8  mov     qword ptr [r8], 0
0x180066baf  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180066bb6  mov     rcx, r9
0x180066bb9  call    InlineIsEqualGUID
0x180066bbe  test    eax, eax
0x180066bc0  jnz     loc_180066C60
0x180066bc6  lea     rdx, _GUID_09d0f835_92ff_4e53_8efa_40faa551f233
0x180066bcd  call    InlineIsEqualGUID
0x180066bd2  test    eax, eax
0x180066bd4  jz      short loc_180066BDD
0x180066bd6  mov     [r8], r10
0x180066bd9  xor     ebx, ebx
0x180066bdb  jmp     short loc_180066C4D
0x180066bdd  add     r10, 8
0x180066be1  lea     rdx, _GUID_802302b0_82de_45e1_b421_f19ee5bdaf23
0x180066be8  call    InlineIsEqualGUID
0x180066bed  test    eax, eax
0x180066bef  jnz     short loc_180066BD6
0x180066bf1  add     r10, 8
0x180066bf5  lea     rdx, _GUID_312cd3b9_7923_438d_bb2b_04cc603c6158
0x180066bfc  call    InlineIsEqualGUID
0x180066c01  test    eax, eax
0x180066c03  jz      short loc_180066C0C
0x180066c05  mov     [r8], r10
0x180066c08  xor     ebx, ebx
0x180066c0a  jmp     short loc_180066C49
0x180066c0c  add     r10, 8
0x180066c10  lea     rdx, _GUID_2f7563e0_1f9a_4317_99de_700ede97eebe
0x180066c17  call    InlineIsEqualGUID
0x180066c1c  test    eax, eax
0x180066c1e  jnz     short loc_180066C05
0x180066c20  add     r10, 8
0x180066c24  lea     rdx, _GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90
0x180066c2b  call    InlineIsEqualGUID
0x180066c30  test    eax, eax
0x180066c32  jnz     short loc_180066C05
0x180066c34  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180066c3b  call    InlineIsEqualGUID
0x180066c40  test    eax, eax
0x180066c42  jnz     short loc_180066C05
0x180066c44  mov     ebx, 80004002h
0x180066c49  test    ebx, ebx
0x180066c4b  js      short loc_180066C5C
0x180066c4d  mov     rcx, [r8]
0x180066c50  mov     rdx, [rcx]
0x180066c53  mov     rax, [rdx+8]
0x180066c57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066c5c  mov     eax, ebx
0x180066c5e  jmp     short loc_180066C74
0x180066c60  mov     [r8], r10
0x180066c63  mov     rax, [r10]
0x180066c66  mov     rcx, r10
0x180066c69  mov     rax, [rax+8]
0x180066c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066c72  xor     eax, eax
0x180066c74  add     rsp, 20h
0x180066c78  pop     rbx
0x180066c79  retn
```
