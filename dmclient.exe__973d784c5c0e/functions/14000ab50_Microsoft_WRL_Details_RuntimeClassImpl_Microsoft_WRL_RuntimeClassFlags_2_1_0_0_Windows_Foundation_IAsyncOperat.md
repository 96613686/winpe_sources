# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)

- ea: `0x14000ab50`
- end: `0x14000ac2e`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14000ac40`

## callees

- `0x14000ab50`
- `0x14001a010`

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
0x14000ab50  push    rbx
0x14000ab52  sub     rsp, 20h
0x14000ab56  xor     ebx, ebx
0x14000ab58  mov     [r8], rbx
0x14000ab5b  cmp     [rdx], ebx
0x14000ab5d  jnz     short loc_14000AB94
0x14000ab5f  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x14000ab65  cmp     [rdx+4], eax
0x14000ab68  jnz     short loc_14000ABC2
0x14000ab6a  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x14000ab70  cmp     [rdx+8], eax
0x14000ab73  jnz     short loc_14000ABC2
0x14000ab75  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x14000ab7b  cmp     [rdx+0Ch], eax
0x14000ab7e  jnz     short loc_14000ABC2
0x14000ab80  mov     [r8], rcx
0x14000ab83  mov     rax, [rcx]
0x14000ab86  mov     rax, [rax+8]
0x14000ab8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ab8f  jmp     loc_14000AC25
0x14000ab94  cmp     dword ptr [rdx], 0B6C6BBF2h
0x14000ab9a  jnz     short loc_14000ABC2
0x14000ab9c  mov     eax, dword ptr cs:_GUID_b6c6bbf2_72ca_5799_a651_d1990670097b.Data2
0x14000aba2  cmp     [rdx+4], eax
0x14000aba5  jnz     short loc_14000ABC2
0x14000aba7  mov     eax, dword ptr cs:_GUID_b6c6bbf2_72ca_5799_a651_d1990670097b.Data4
0x14000abad  cmp     [rdx+8], eax
0x14000abb0  jnz     short loc_14000ABC2
0x14000abb2  mov     eax, dword ptr cs:_GUID_b6c6bbf2_72ca_5799_a651_d1990670097b.Data4+4
0x14000abb8  cmp     [rdx+0Ch], eax
0x14000abbb  jnz     short loc_14000ABC2
0x14000abbd  mov     [r8], rcx
0x14000abc0  jmp     short loc_14000AC18
0x14000abc2  add     rcx, 8
0x14000abc6  cmp     dword ptr [rdx], 94EA2B94h
0x14000abcc  jnz     short loc_14000ABEC
0x14000abce  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
0x14000abd4  cmp     [rdx+4], eax
0x14000abd7  jnz     short loc_14000AC20
0x14000abd9  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4
0x14000abdf  cmp     [rdx+8], eax
0x14000abe2  jnz     short loc_14000AC20
0x14000abe4  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4+4
0x14000abea  jmp     short loc_14000AC0D
0x14000abec  cmp     dword ptr [rdx], 3
0x14000abef  jnz     short loc_14000AC20
0x14000abf1  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data2
0x14000abf7  cmp     [rdx+4], eax
0x14000abfa  jnz     short loc_14000AC20
0x14000abfc  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4
0x14000ac02  cmp     [rdx+8], eax
0x14000ac05  jnz     short loc_14000AC20
0x14000ac07  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4+4
0x14000ac0d  cmp     [rdx+0Ch], eax
0x14000ac10  jnz     short loc_14000AC20
0x14000ac12  mov     rax, r8
0x14000ac15  mov     [rax], rcx
0x14000ac18  mov     rcx, [r8]
0x14000ac1b  jmp     loc_14000AB83
0x14000ac20  mov     ebx, 80004002h
0x14000ac25  mov     eax, ebx
0x14000ac27  add     rsp, 20h
0x14000ac2b  pop     rbx
0x14000ac2c  retn
```
