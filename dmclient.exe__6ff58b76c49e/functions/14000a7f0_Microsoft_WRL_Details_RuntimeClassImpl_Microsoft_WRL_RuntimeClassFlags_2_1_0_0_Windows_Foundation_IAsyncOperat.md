# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)

- ea: `0x14000a7f0`
- end: `0x14000a8cd`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `221`
- prototype: `__int64 __fastcall(__int64, _DWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14000a8e0`

## callees

- `0x14000a7f0`
- `0x140019010`

## pseudocode

```c
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
0x14000a7f0  push    rbx
0x14000a7f2  sub     rsp, 20h
0x14000a7f6  xor     ebx, ebx
0x14000a7f8  mov     [r8], rbx
0x14000a7fb  cmp     [rdx], ebx
0x14000a7fd  jnz     short loc_14000A834
0x14000a7ff  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x14000a805  cmp     [rdx+4], eax
0x14000a808  jnz     short loc_14000A862
0x14000a80a  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x14000a810  cmp     [rdx+8], eax
0x14000a813  jnz     short loc_14000A862
0x14000a815  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x14000a81b  cmp     [rdx+0Ch], eax
0x14000a81e  jnz     short loc_14000A862
0x14000a820  mov     [r8], rcx
0x14000a823  mov     rax, [rcx]
0x14000a826  mov     rax, [rax+8]
0x14000a82a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a82f  jmp     loc_14000A8C5
0x14000a834  cmp     dword ptr [rdx], 7EA7D7ECh
0x14000a83a  jnz     short loc_14000A862
0x14000a83c  mov     eax, dword ptr cs:_GUID_7ea7d7ec_e164_52c3_8e32_bba7126d9028.Data2
0x14000a842  cmp     [rdx+4], eax
0x14000a845  jnz     short loc_14000A862
0x14000a847  mov     eax, dword ptr cs:_GUID_7ea7d7ec_e164_52c3_8e32_bba7126d9028.Data4
0x14000a84d  cmp     [rdx+8], eax
0x14000a850  jnz     short loc_14000A862
0x14000a852  mov     eax, dword ptr cs:_GUID_7ea7d7ec_e164_52c3_8e32_bba7126d9028.Data4+4
0x14000a858  cmp     [rdx+0Ch], eax
0x14000a85b  jnz     short loc_14000A862
0x14000a85d  mov     [r8], rcx
0x14000a860  jmp     short loc_14000A8B8
0x14000a862  add     rcx, 8
0x14000a866  cmp     dword ptr [rdx], 94EA2B94h
0x14000a86c  jnz     short loc_14000A88C
0x14000a86e  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
0x14000a874  cmp     [rdx+4], eax
0x14000a877  jnz     short loc_14000A8C0
0x14000a879  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4
0x14000a87f  cmp     [rdx+8], eax
0x14000a882  jnz     short loc_14000A8C0
0x14000a884  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4+4
0x14000a88a  jmp     short loc_14000A8AD
0x14000a88c  cmp     dword ptr [rdx], 3
0x14000a88f  jnz     short loc_14000A8C0
0x14000a891  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data2
0x14000a897  cmp     [rdx+4], eax
0x14000a89a  jnz     short loc_14000A8C0
0x14000a89c  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4
0x14000a8a2  cmp     [rdx+8], eax
0x14000a8a5  jnz     short loc_14000A8C0
0x14000a8a7  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4+4
0x14000a8ad  cmp     [rdx+0Ch], eax
0x14000a8b0  jnz     short loc_14000A8C0
0x14000a8b2  mov     rax, r8
0x14000a8b5  mov     [rax], rcx
0x14000a8b8  mov     rcx, [r8]
0x14000a8bb  jmp     loc_14000A823
0x14000a8c0  mov     ebx, 80004002h
0x14000a8c5  mov     eax, ebx
0x14000a8c7  add     rsp, 20h
0x14000a8cb  pop     rbx
0x14000a8cc  retn
```
