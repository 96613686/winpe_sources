# CSteelhead::HrUpdateRouterConfiguration(void)

- ea: `0x180036c94`
- end: `0x180036e0c`
- name: `?HrUpdateRouterConfiguration@CSteelhead@@QEAAJXZ`
- size: `376`
- prototype: `__int64 __fastcall(CSteelhead *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x1800356d0`

## callees

- `0x1800265c0`
- `0x1800267f0`
- `0x180035f84`
- `0x18003643c`
- `0x180036660`
- `0x180036a0c`
- `0x180036c94`
- `0x180036e4c`

## import_xrefs

- `rtutils!TracePrintfW` at `0x180036ce9`
- `rtutils!TracePrintfW` at `0x180036df7`
- `rtutils!TracePrintfW` at `0x180036ce9`
- `rtutils!TracePrintfW` at `0x180036df7`

## string_xrefs

- `0x180036ded`: `CSteelhead::HrUpdateRouterConfiguration`
- `0x180036cd8`: `HrMprConfigServerConnect`

## pseudocode

```c
__int64 __fastcall CSteelhead::HrUpdateRouterConfiguration(CSteelhead *this)
{
  HANDLE *v1; // rsi
  unsigned int v3; // ebx
  signed int v4; // eax
  unsigned int v5; // r8d
  unsigned int v7; // r8d
  unsigned int v8; // r8d
  unsigned int v9; // r8d
  __int64 v10; // rdx
  const struct _GUID *v11; // r8

  v1 = (HANDLE *)((char *)this + 104);
  v3 = 0;
  v4 = MprConfigServerConnect(0, (HANDLE *)this + 13);
  if ( v4 )
  {
    if ( v4 > 0 )
      v3 = (unsigned __int16)v4 | 0x80070000;
    else
      v3 = v4;
    *v1 = 0;
    TracePrintfW(g_dwTraceHandle, L"%hs failed : hr = %08lx", "HrMprConfigServerConnect", v3);
    TracePrintfW(g_dwTraceHandle, L"%hs failed : hr = %08lx", "CSteelhead::HrUpdateRouterConfiguration", v3);
  }
  else
  {
    if ( *((_QWORD *)this + 5) && *((_DWORD *)this + 284) )
    {
      CSteelhead::HrEnsureRouterInterfaceForAdapter(
        this,
        ROUTER_IF_TYPE_LOOPBACK,
        v5,
        (const unsigned __int16 *)this + 312,
        (const unsigned __int16 *)this + 312,
        (const struct ROUTER_MANAGER_INFO *)&qword_1800540F8);
      CSteelhead::HrEnsureRouterInterfaceForAdapter(
        this,
        ROUTER_IF_TYPE_INTERNAL,
        v7,
        (const unsigned __int16 *)this + 56,
        (const unsigned __int16 *)this + 56,
        (const struct ROUTER_MANAGER_INFO *)&qword_1800540F8);
    }
    else
    {
      CSteelhead::HrEnsureRouterManagerDeleted((void **)this, (const struct ROUTER_MANAGER_INFO *)&qword_1800540F8);
    }
    if ( (unsigned int)CSteelhead::IsIpv6TransportInstalled(this) )
    {
      CSteelhead::HrEnsureRouterInterfaceForAdapter(
        this,
        ROUTER_IF_TYPE_LOOPBACK,
        v8,
        (const unsigned __int16 *)this + 312,
        (const unsigned __int16 *)this + 312,
        (const struct ROUTER_MANAGER_INFO *)&qword_1800540C8);
      CSteelhead::HrEnsureRouterInterfaceForAdapter(
        this,
        ROUTER_IF_TYPE_INTERNAL,
        v9,
        (const unsigned __int16 *)this + 56,
        (const unsigned __int16 *)this + 56,
        (const struct ROUTER_MANAGER_INFO *)&qword_1800540C8);
    }
    else
    {
      CSteelhead::HrEnsureRouterManagerDeleted((void **)this, (const struct ROUTER_MANAGER_INFO *)&qword_1800540C8);
    }
    CSteelhead::HrPassToAddInterfaces((struct INetCfg **)this, v10, v11);
    CSteelhead::HrPassToRemoveInterfaces(this);
    MprConfigServerDisconnect(*v1);
    *v1 = 0;
    TracePrintfW(g_dwTraceHandle, L"%hs succeeded : hr = %08lx", "CSteelhead::HrUpdateRouterConfiguration", 0);
  }
  return v3;
}

```

## disassembly

```asm
0x180036c94  push    rbx
0x180036c96  push    rbp
0x180036c97  push    rsi
0x180036c98  push    rdi
0x180036c99  push    r14
0x180036c9b  push    r15
0x180036c9d  sub     rsp, 38h
0x180036ca1  lea     rsi, [rcx+68h]
0x180036ca5  mov     rdi, rcx
0x180036ca8  mov     rdx, rsi; phMprConfig
0x180036cab  xor     ecx, ecx; lpwsServerName
0x180036cad  xor     ebx, ebx
0x180036caf  call    MprConfigServerConnect
0x180036cb4  test    eax, eax
0x180036cb6  jz      short loc_180036CFB
0x180036cb8  jg      short loc_180036CBE
0x180036cba  mov     ebx, eax
0x180036cbc  jmp     short loc_180036CC7
0x180036cbe  movzx   ebx, ax
0x180036cc1  or      ebx, 80070000h
0x180036cc7  mov     qword ptr [rsi], 0
0x180036cce  test    ebx, ebx
0x180036cd0  jns     short loc_180036CFB
0x180036cd2  mov     ecx, cs:g_dwTraceHandle; dwTraceID
0x180036cd8  lea     r8, aHrmprconfigser; "HrMprConfigServerConnect"
0x180036cdf  mov     r9d, ebx
0x180036ce2  lea     rdx, aHsFailedHr08lx; "%hs failed : hr = %08lx"
0x180036ce9  call    cs:__imp_TracePrintfW
0x180036cef  lea     rdx, aHsFailedHr08lx; "%hs failed : hr = %08lx"
0x180036cf6  jmp     loc_180036DE7
0x180036cfb  cmp     qword ptr [rdi+28h], 0
0x180036d00  jz      short loc_180036D12
0x180036d02  cmp     dword ptr [rdi+470h], 0
0x180036d09  jz      short loc_180036D12
0x180036d0b  mov     eax, 1
0x180036d10  jmp     short loc_180036D14
0x180036d12  xor     eax, eax
0x180036d14  lea     r14, [rdi+270h]
0x180036d1b  mov     rcx, rdi; this
0x180036d1e  lea     r15, [rdi+70h]
0x180036d22  test    eax, eax
0x180036d24  jz      short loc_180036D60
0x180036d26  lea     rbp, qword_1800540F8
0x180036d2d  mov     r9, r14; unsigned __int16 *
0x180036d30  mov     [rsp+68h+var_40], rbp; struct ROUTER_MANAGER_INFO *
0x180036d35  mov     edx, 5; enum _ROUTER_INTERFACE_TYPE
0x180036d3a  mov     [rsp+68h+var_48], r14; unsigned __int16 *
0x180036d3f  call    ?HrEnsureRouterInterfaceForAdapter@CSteelhead@@IEAAJW4_ROUTER_INTERFACE_TYPE@@KPEBG1AEBUROUTER_MANAGER_INFO@@@Z; CSteelhead::HrEnsureRouterInterfaceForAdapter(_ROUTER_INTERFACE_TYPE,ulong,ushort const *,ushort const *,ROUTER_MANAGER_INFO const &)
0x180036d44  mov     r9, r15; unsigned __int16 *
0x180036d47  mov     [rsp+68h+var_40], rbp; struct ROUTER_MANAGER_INFO *
0x180036d4c  mov     edx, 4; enum _ROUTER_INTERFACE_TYPE
0x180036d51  mov     [rsp+68h+var_48], r15; unsigned __int16 *
0x180036d56  mov     rcx, rdi; this
0x180036d59  call    ?HrEnsureRouterInterfaceForAdapter@CSteelhead@@IEAAJW4_ROUTER_INTERFACE_TYPE@@KPEBG1AEBUROUTER_MANAGER_INFO@@@Z; CSteelhead::HrEnsureRouterInterfaceForAdapter(_ROUTER_INTERFACE_TYPE,ulong,ushort const *,ushort const *,ROUTER_MANAGER_INFO const &)
0x180036d5e  jmp     short loc_180036D6C
0x180036d60  lea     rdx, qword_1800540F8; struct ROUTER_MANAGER_INFO *
0x180036d67  call    ?HrEnsureRouterManagerDeleted@CSteelhead@@IEAAJAEBUROUTER_MANAGER_INFO@@@Z; CSteelhead::HrEnsureRouterManagerDeleted(ROUTER_MANAGER_INFO const &)
0x180036d6c  mov     rcx, rdi; this
0x180036d6f  call    ?IsIpv6TransportInstalled@CSteelhead@@AEAAHXZ; CSteelhead::IsIpv6TransportInstalled(void)
0x180036d74  mov     rcx, rdi; this
0x180036d77  test    eax, eax
0x180036d79  jz      short loc_180036DB5
0x180036d7b  lea     rbp, qword_1800540C8
0x180036d82  mov     r9, r14; unsigned __int16 *
0x180036d85  mov     [rsp+68h+var_40], rbp; struct ROUTER_MANAGER_INFO *
0x180036d8a  mov     edx, 5; enum _ROUTER_INTERFACE_TYPE
0x180036d8f  mov     [rsp+68h+var_48], r14; unsigned __int16 *
0x180036d94  call    ?HrEnsureRouterInterfaceForAdapter@CSteelhead@@IEAAJW4_ROUTER_INTERFACE_TYPE@@KPEBG1AEBUROUTER_MANAGER_INFO@@@Z; CSteelhead::HrEnsureRouterInterfaceForAdapter(_ROUTER_INTERFACE_TYPE,ulong,ushort const *,ushort const *,ROUTER_MANAGER_INFO const &)
0x180036d99  mov     r9, r15; unsigned __int16 *
0x180036d9c  mov     [rsp+68h+var_40], rbp; struct ROUTER_MANAGER_INFO *
0x180036da1  mov     edx, 4; enum _ROUTER_INTERFACE_TYPE
0x180036da6  mov     [rsp+68h+var_48], r15; unsigned __int16 *
0x180036dab  mov     rcx, rdi; this
0x180036dae  call    ?HrEnsureRouterInterfaceForAdapter@CSteelhead@@IEAAJW4_ROUTER_INTERFACE_TYPE@@KPEBG1AEBUROUTER_MANAGER_INFO@@@Z; CSteelhead::HrEnsureRouterInterfaceForAdapter(_ROUTER_INTERFACE_TYPE,ulong,ushort const *,ushort const *,ROUTER_MANAGER_INFO const &)
0x180036db3  jmp     short loc_180036DC1
0x180036db5  lea     rdx, qword_1800540C8; struct ROUTER_MANAGER_INFO *
0x180036dbc  call    ?HrEnsureRouterManagerDeleted@CSteelhead@@IEAAJAEBUROUTER_MANAGER_INFO@@@Z; CSteelhead::HrEnsureRouterManagerDeleted(ROUTER_MANAGER_INFO const &)
0x180036dc1  mov     rcx, rdi; this
0x180036dc4  call    ?HrPassToAddInterfaces@CSteelhead@@IEAAJXZ; CSteelhead::HrPassToAddInterfaces(void)
0x180036dc9  mov     rcx, rdi; this
0x180036dcc  call    ?HrPassToRemoveInterfaces@CSteelhead@@IEAAJXZ; CSteelhead::HrPassToRemoveInterfaces(void)
0x180036dd1  mov     rcx, [rsi]; hMprConfig
0x180036dd4  call    MprConfigServerDisconnect
0x180036dd9  lea     rdx, szFormat; "%hs succeeded : hr = %08lx"
0x180036de0  mov     qword ptr [rsi], 0
0x180036de7  mov     ecx, cs:g_dwTraceHandle; dwTraceID
0x180036ded  lea     r8, aCsteelheadHrup; "CSteelhead::HrUpdateRouterConfiguration"
0x180036df4  mov     r9d, ebx
0x180036df7  call    cs:__imp_TracePrintfW
0x180036dfd  mov     eax, ebx
0x180036dff  add     rsp, 38h
0x180036e03  pop     r15
0x180036e05  pop     r14
0x180036e07  pop     rdi
0x180036e08  pop     rsi
0x180036e09  pop     rbp
0x180036e0a  pop     rbx
0x180036e0b  retn
```
