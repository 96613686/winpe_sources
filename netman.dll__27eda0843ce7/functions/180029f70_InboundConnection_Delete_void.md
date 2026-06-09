# InboundConnection::Delete(void)

- ea: `0x180029f70`
- end: `0x18002a02f`
- name: `?Delete@InboundConnection@@UEAAJXZ`
- size: `191`
- prototype: `__int64 __fastcall(InboundConnection *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x18000538c`
- `0x180029f70`
- `0x18002ad2c`
- `0x1800317f4`
- `0x18003286c`

## import_xrefs

- `RASDLG!RasSrvCleanupService` at `0x180029fb4`
- `RASDLG!RasSrvCleanupService` at `0x180029fb4`

## pseudocode

```c
__int64 __fastcall InboundConnection::Delete(InboundConnection *this)
{
  unsigned int v3; // eax
  int v4; // eax
  unsigned int v5; // ebx
  PVOID *v6; // rcx

  if ( !(unsigned int)FIsCallerNetworkConfigOpsOrAdmin() )
    return 2147746532LL;
  if ( !(unsigned __int8)std::_Atomic_storage<bool,1>::load((char *)this + 180)
    || !(unsigned __int8)std::_Atomic_storage<bool,1>::load((char *)this + 80) )
  {
    v5 = -2147418113;
    goto LABEL_10;
  }
  v3 = RasSrvCleanupService();
  v4 = HrFromRasError(v3);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_11;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        WPP_f5b0e8f8468b399d61f8354bdcc79c55_Traceguids,
        (unsigned int)v4);
LABEL_10:
      v6 = (PVOID *)WPP_GLOBAL_Control;
LABEL_11:
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 )
        WPP_SF_d(v6[2], 17, WPP_f5b0e8f8468b399d61f8354bdcc79c55_Traceguids, v5);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180029f70  mov     [rsp+arg_0], rbx
0x180029f75  push    rdi
0x180029f76  sub     rsp, 20h
0x180029f7a  mov     rbx, rcx
0x180029f7d  call    ?FIsCallerNetworkConfigOpsOrAdmin@@YAHXZ; FIsCallerNetworkConfigOpsOrAdmin(void)
0x180029f82  test    eax, eax
0x180029f84  jnz     short loc_180029F90
0x180029f86  mov     eax, 800402E4h
0x180029f8b  jmp     loc_18002A024
0x180029f90  lea     rcx, [rbx+0B4h]
0x180029f97  call    ?load@?$_Atomic_storage@_N$00@std@@QEBA_NW4memory_order@2@@Z; std::_Atomic_storage<bool,1>::load(std::memory_order)
0x180029f9c  lea     rdi, WPP_GLOBAL_Control
0x180029fa3  test    al, al
0x180029fa5  jz      short loc_180029FF3
0x180029fa7  lea     rcx, [rbx+50h]
0x180029fab  call    ?load@?$_Atomic_storage@_N$00@std@@QEBA_NW4memory_order@2@@Z; std::_Atomic_storage<bool,1>::load(std::memory_order)
0x180029fb0  test    al, al
0x180029fb2  jz      short loc_180029FF3
0x180029fb4  call    cs:__imp_RasSrvCleanupService
0x180029fba  mov     ecx, eax; unsigned int
0x180029fbc  call    ?HrFromRasError@@YAJK@Z; HrFromRasError(ulong)
0x180029fc1  mov     ebx, eax
0x180029fc3  test    eax, eax
0x180029fc5  jns     short loc_18002A022
0x180029fc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180029fce  cmp     rcx, rdi
0x180029fd1  jz      short loc_18002A022
0x180029fd3  test    byte ptr [rcx+1Ch], 1
0x180029fd7  jz      short loc_180029FFF
0x180029fd9  mov     rcx, [rcx+10h]
0x180029fdd  lea     r8, WPP_f5b0e8f8468b399d61f8354bdcc79c55_Traceguids
0x180029fe4  mov     edx, 10h
0x180029fe9  mov     r9d, eax
0x180029fec  call    WPP_SF_d
0x180029ff1  jmp     short loc_180029FF8
0x180029ff3  mov     ebx, 8000FFFFh
0x180029ff8  mov     rcx, cs:WPP_GLOBAL_Control
0x180029fff  cmp     rcx, rdi
0x18002a002  jz      short loc_18002A022
0x18002a004  test    byte ptr [rcx+1Ch], 1
0x18002a008  jz      short loc_18002A022
0x18002a00a  mov     rcx, [rcx+10h]
0x18002a00e  lea     r8, WPP_f5b0e8f8468b399d61f8354bdcc79c55_Traceguids
0x18002a015  mov     edx, 11h
0x18002a01a  mov     r9d, ebx
0x18002a01d  call    WPP_SF_d
0x18002a022  mov     eax, ebx
0x18002a024  mov     rbx, [rsp+28h+arg_0]
0x18002a029  add     rsp, 20h
0x18002a02d  pop     rdi
0x18002a02e  retn
```
