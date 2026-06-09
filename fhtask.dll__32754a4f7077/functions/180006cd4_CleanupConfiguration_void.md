# CleanupConfiguration(void)

- ea: `0x180006cd4`
- end: `0x180006dcf`
- name: `?CleanupConfiguration@@YAXXZ`
- size: `251`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180007ba0`

## callees

- `0x1800067a0`
- `0x180006cd4`
- `0x18000b010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180006cff`
- `ole32!CoCreateInstance` at `0x180006cff`

## pseudocode

```c
void CleanupConfiguration(void)
{
  HRESULT v0; // eax
  _QWORD *v1; // rcx
  __int64 v2; // rdx
  LPVOID ppv; // [rsp+40h] [rbp+8h] BYREF

  ppv = 0;
  v0 = CoCreateInstance(&CLSID_FhConfigMgr, 0, 0x17u, &GUID_e388cb3e_d90b_4e2a_a025_42c7f1e655a4, &ppv);
  if ( v0 >= 0 )
  {
    v0 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 328LL))(ppv);
    if ( v0 >= 0 )
    {
      v0 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 320LL))(ppv);
      if ( v0 >= 0 )
        goto LABEL_14;
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_14;
      v2 = 39;
    }
    else
    {
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_14;
      v2 = 38;
    }
  }
  else
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_14;
    v2 = 37;
  }
  WPP_SF_d(v1[2], v2, &WPP_8158daeccbd13eff1bb477c819869c69_Traceguids, (unsigned int)v0);
LABEL_14:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
}

```

## disassembly

```asm
0x180006cd4  sub     rsp, 38h
0x180006cd8  mov     [rsp+38h+arg_0], 0
0x180006ce1  lea     rax, [rsp+38h+arg_0]
0x180006ce6  mov     [rsp+38h+ppv], rax; ppv
0x180006ceb  lea     r9, _GUID_e388cb3e_d90b_4e2a_a025_42c7f1e655a4; riid
0x180006cf2  xor     edx, edx; pUnkOuter
0x180006cf4  lea     r8d, [rdx+17h]; dwClsContext
0x180006cf8  lea     rcx, CLSID_FhConfigMgr; rclsid
0x180006cff  call    cs:__imp_CoCreateInstance
0x180006d05  test    eax, eax
0x180006d07  jns     short loc_180006D31
0x180006d09  lea     rdx, WPP_GLOBAL_Control
0x180006d10  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d17  cmp     rcx, rdx
0x180006d1a  jz      loc_180006DB3
0x180006d20  test    byte ptr [rcx+1Ch], 1
0x180006d24  jz      loc_180006DB3
0x180006d2a  mov     edx, 25h ; '%'
0x180006d2f  jmp     short loc_180006D9F
0x180006d31  mov     rcx, [rsp+38h+arg_0]
0x180006d36  mov     rax, [rcx]
0x180006d39  mov     rax, [rax+148h]
0x180006d40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d45  test    eax, eax
0x180006d47  jns     short loc_180006D69
0x180006d49  lea     rdx, WPP_GLOBAL_Control
0x180006d50  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d57  cmp     rcx, rdx
0x180006d5a  jz      short loc_180006DB3
0x180006d5c  test    byte ptr [rcx+1Ch], 1
0x180006d60  jz      short loc_180006DB3
0x180006d62  mov     edx, 26h ; '&'
0x180006d67  jmp     short loc_180006D9F
0x180006d69  mov     rcx, [rsp+38h+arg_0]
0x180006d6e  mov     rax, [rcx]
0x180006d71  mov     rax, [rax+140h]
0x180006d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d7d  test    eax, eax
0x180006d7f  jns     short loc_180006DB3
0x180006d81  lea     rdx, WPP_GLOBAL_Control
0x180006d88  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d8f  cmp     rcx, rdx
0x180006d92  jz      short loc_180006DB3
0x180006d94  test    byte ptr [rcx+1Ch], 1
0x180006d98  jz      short loc_180006DB3
0x180006d9a  mov     edx, 27h ; '''
0x180006d9f  mov     r9d, eax
0x180006da2  lea     r8, WPP_8158daeccbd13eff1bb477c819869c69_Traceguids
0x180006da9  mov     rcx, [rcx+10h]
0x180006dad  call    WPP_SF_d
0x180006db2  nop
0x180006db3  mov     rcx, [rsp+38h+arg_0]
0x180006db8  test    rcx, rcx
0x180006dbb  jz      short loc_180006DCA
0x180006dbd  mov     rax, [rcx]
0x180006dc0  mov     rax, [rax+10h]
0x180006dc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dc9  nop
0x180006dca  add     rsp, 38h
0x180006dce  retn
```
