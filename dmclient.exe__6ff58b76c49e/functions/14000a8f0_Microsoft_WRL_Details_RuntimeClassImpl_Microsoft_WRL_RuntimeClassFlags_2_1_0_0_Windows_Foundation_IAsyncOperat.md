# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)

- ea: `0x14000a8f0`
- end: `0x14000a9cd`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `221`
- prototype: `__int64 __fastcall(__int64, _DWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14000a9e0`

## callees

- `0x14000a8f0`
- `0x140019010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus>,Microsoft::WRL::FtmBase>::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        __int64 *a3)
{
  unsigned int v3; // ebx
  __int64 v4; // rcx
  int v5; // eax

  v3 = 0;
  *a3 = 0;
  if ( *a2 )
  {
    if ( *a2 == -1228489742
      && a2[1] == *(_DWORD *)&GUID_b6c6bbf2_72ca_5799_a651_d1990670097b.Data2
      && a2[2] == *(_DWORD *)GUID_b6c6bbf2_72ca_5799_a651_d1990670097b.Data4
      && a2[3] == *(_DWORD *)&GUID_b6c6bbf2_72ca_5799_a651_d1990670097b.Data4[4] )
    {
      *a3 = a1;
LABEL_22:
      a1 = *a3;
      goto LABEL_6;
    }
LABEL_12:
    v4 = a1 + 8;
    if ( *a2 == -1796592748 )
    {
      if ( a2[1] != *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
        || a2[2] != *(_DWORD *)GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4 )
      {
        return (unsigned int)-2147467262;
      }
      v5 = *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4[4];
    }
    else
    {
      if ( *a2 != 3
        || a2[1] != *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data2
        || a2[2] != *(_DWORD *)GUID_00000003_0000_0000_c000_000000000046.Data4 )
      {
        return (unsigned int)-2147467262;
      }
      v5 = *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data4[4];
    }
    if ( a2[3] == v5 )
    {
      *a3 = v4;
      goto LABEL_22;
    }
    return (unsigned int)-2147467262;
  }
  if ( a2[1] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
    || a2[2] != *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4
    || a2[3] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4] )
  {
    goto LABEL_12;
  }
  *a3 = a1;
LABEL_6:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  return v3;
}

```

## disassembly

```asm
0x14000a8f0  push    rbx
0x14000a8f2  sub     rsp, 20h
0x14000a8f6  xor     ebx, ebx
0x14000a8f8  mov     [r8], rbx
0x14000a8fb  cmp     [rdx], ebx
0x14000a8fd  jnz     short loc_14000A934
0x14000a8ff  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x14000a905  cmp     [rdx+4], eax
0x14000a908  jnz     short loc_14000A962
0x14000a90a  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x14000a910  cmp     [rdx+8], eax
0x14000a913  jnz     short loc_14000A962
0x14000a915  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x14000a91b  cmp     [rdx+0Ch], eax
0x14000a91e  jnz     short loc_14000A962
0x14000a920  mov     [r8], rcx
0x14000a923  mov     rax, [rcx]
0x14000a926  mov     rax, [rax+8]
0x14000a92a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a92f  jmp     loc_14000A9C5
0x14000a934  cmp     dword ptr [rdx], 0B6C6BBF2h
0x14000a93a  jnz     short loc_14000A962
0x14000a93c  mov     eax, dword ptr cs:_GUID_b6c6bbf2_72ca_5799_a651_d1990670097b.Data2
0x14000a942  cmp     [rdx+4], eax
0x14000a945  jnz     short loc_14000A962
0x14000a947  mov     eax, dword ptr cs:_GUID_b6c6bbf2_72ca_5799_a651_d1990670097b.Data4
0x14000a94d  cmp     [rdx+8], eax
0x14000a950  jnz     short loc_14000A962
0x14000a952  mov     eax, dword ptr cs:_GUID_b6c6bbf2_72ca_5799_a651_d1990670097b.Data4+4
0x14000a958  cmp     [rdx+0Ch], eax
0x14000a95b  jnz     short loc_14000A962
0x14000a95d  mov     [r8], rcx
0x14000a960  jmp     short loc_14000A9B8
0x14000a962  add     rcx, 8
0x14000a966  cmp     dword ptr [rdx], 94EA2B94h
0x14000a96c  jnz     short loc_14000A98C
0x14000a96e  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
0x14000a974  cmp     [rdx+4], eax
0x14000a977  jnz     short loc_14000A9C0
0x14000a979  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4
0x14000a97f  cmp     [rdx+8], eax
0x14000a982  jnz     short loc_14000A9C0
0x14000a984  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4+4
0x14000a98a  jmp     short loc_14000A9AD
0x14000a98c  cmp     dword ptr [rdx], 3
0x14000a98f  jnz     short loc_14000A9C0
0x14000a991  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data2
0x14000a997  cmp     [rdx+4], eax
0x14000a99a  jnz     short loc_14000A9C0
0x14000a99c  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4
0x14000a9a2  cmp     [rdx+8], eax
0x14000a9a5  jnz     short loc_14000A9C0
0x14000a9a7  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4+4
0x14000a9ad  cmp     [rdx+0Ch], eax
0x14000a9b0  jnz     short loc_14000A9C0
0x14000a9b2  mov     rax, r8
0x14000a9b5  mov     [rax], rcx
0x14000a9b8  mov     rcx, [r8]
0x14000a9bb  jmp     loc_14000A923
0x14000a9c0  mov     ebx, 80004002h
0x14000a9c5  mov     eax, ebx
0x14000a9c7  add     rsp, 20h
0x14000a9cb  pop     rbx
0x14000a9cc  retn
```
