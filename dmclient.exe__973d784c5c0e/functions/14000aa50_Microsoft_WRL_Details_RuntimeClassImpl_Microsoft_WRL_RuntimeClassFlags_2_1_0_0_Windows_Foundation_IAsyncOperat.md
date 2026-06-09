# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)

- ea: `0x14000aa50`
- end: `0x14000ab2e`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14000ab40`

## callees

- `0x14000aa50`
- `0x14001a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Microsoft::WRL::FtmBase>::QueryInterface(
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
    if ( *a2 == 2124929004
      && a2[1] == *(_DWORD *)&GUID_7ea7d7ec_e164_52c3_8e32_bba7126d9028.Data2
      && a2[2] == *(_DWORD *)GUID_7ea7d7ec_e164_52c3_8e32_bba7126d9028.Data4
      && a2[3] == *(_DWORD *)&GUID_7ea7d7ec_e164_52c3_8e32_bba7126d9028.Data4[4] )
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
0x14000aa50  push    rbx
0x14000aa52  sub     rsp, 20h
0x14000aa56  xor     ebx, ebx
0x14000aa58  mov     [r8], rbx
0x14000aa5b  cmp     [rdx], ebx
0x14000aa5d  jnz     short loc_14000AA94
0x14000aa5f  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x14000aa65  cmp     [rdx+4], eax
0x14000aa68  jnz     short loc_14000AAC2
0x14000aa6a  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x14000aa70  cmp     [rdx+8], eax
0x14000aa73  jnz     short loc_14000AAC2
0x14000aa75  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x14000aa7b  cmp     [rdx+0Ch], eax
0x14000aa7e  jnz     short loc_14000AAC2
0x14000aa80  mov     [r8], rcx
0x14000aa83  mov     rax, [rcx]
0x14000aa86  mov     rax, [rax+8]
0x14000aa8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aa8f  jmp     loc_14000AB25
0x14000aa94  cmp     dword ptr [rdx], 7EA7D7ECh
0x14000aa9a  jnz     short loc_14000AAC2
0x14000aa9c  mov     eax, dword ptr cs:_GUID_7ea7d7ec_e164_52c3_8e32_bba7126d9028.Data2
0x14000aaa2  cmp     [rdx+4], eax
0x14000aaa5  jnz     short loc_14000AAC2
0x14000aaa7  mov     eax, dword ptr cs:_GUID_7ea7d7ec_e164_52c3_8e32_bba7126d9028.Data4
0x14000aaad  cmp     [rdx+8], eax
0x14000aab0  jnz     short loc_14000AAC2
0x14000aab2  mov     eax, dword ptr cs:_GUID_7ea7d7ec_e164_52c3_8e32_bba7126d9028.Data4+4
0x14000aab8  cmp     [rdx+0Ch], eax
0x14000aabb  jnz     short loc_14000AAC2
0x14000aabd  mov     [r8], rcx
0x14000aac0  jmp     short loc_14000AB18
0x14000aac2  add     rcx, 8
0x14000aac6  cmp     dword ptr [rdx], 94EA2B94h
0x14000aacc  jnz     short loc_14000AAEC
0x14000aace  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
0x14000aad4  cmp     [rdx+4], eax
0x14000aad7  jnz     short loc_14000AB20
0x14000aad9  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4
0x14000aadf  cmp     [rdx+8], eax
0x14000aae2  jnz     short loc_14000AB20
0x14000aae4  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4+4
0x14000aaea  jmp     short loc_14000AB0D
0x14000aaec  cmp     dword ptr [rdx], 3
0x14000aaef  jnz     short loc_14000AB20
0x14000aaf1  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data2
0x14000aaf7  cmp     [rdx+4], eax
0x14000aafa  jnz     short loc_14000AB20
0x14000aafc  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4
0x14000ab02  cmp     [rdx+8], eax
0x14000ab05  jnz     short loc_14000AB20
0x14000ab07  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4+4
0x14000ab0d  cmp     [rdx+0Ch], eax
0x14000ab10  jnz     short loc_14000AB20
0x14000ab12  mov     rax, r8
0x14000ab15  mov     [rax], rcx
0x14000ab18  mov     rcx, [r8]
0x14000ab1b  jmp     loc_14000AA83
0x14000ab20  mov     ebx, 80004002h
0x14000ab25  mov     eax, ebx
0x14000ab27  add     rsp, 20h
0x14000ab2b  pop     rbx
0x14000ab2c  retn
```
