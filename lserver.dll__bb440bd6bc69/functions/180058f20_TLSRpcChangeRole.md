# TLSRpcChangeRole

- ea: `0x180058f20`
- end: `0x180059138`
- name: `TLSRpcChangeRole`
- size: `536`
- prototype: `__int64 __fastcall(__int64, unsigned int, LSTATUS *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task`

## callees

- `0x18000bb98`
- `0x18000e8b4`
- `0x18000f8b8`
- `0x18001ae3c`
- `0x180058f20`
- `0x18006d850`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180059040`
- `ADVAPI32!RegSetValueExW` at `0x180059040`
- `ADVAPI32!RegCreateKeyExW` at `0x18005900e`
- `ADVAPI32!RegCreateKeyExW` at `0x18005900e`
- `ADVAPI32!RegCloseKey` at `0x180059097`
- `ADVAPI32!RegCloseKey` at `0x180059097`

## string_xrefs

- `0x180058fe1`: `System\CurrentControlSet\Services\TermServLicensing\Parameters`

## pseudocode

```c
__int64 __fastcall TLSRpcChangeRole(__int64 a1, unsigned int a2, LSTATUS *a3)
{
  PVOID *v5; // rcx
  char IsEnabled; // al
  int v7; // ecx
  bool v8; // zf
  LSTATUS v9; // ebx
  HKEY hKey; // [rsp+50h] [rbp-10h] BYREF
  int v12; // [rsp+80h] [rbp+20h] BYREF
  unsigned int Data; // [rsp+88h] [rbp+28h] BYREF
  DWORD dwDisposition; // [rsp+98h] [rbp+38h] BYREF

  Data = a2;
  dwDisposition = 0;
  hKey = 0;
  v12 = 0;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
  {
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      WPP_32285b1e2ab033aa73a29666e87f0116_Traceguids,
      L"TLSRpcChangeRole");
    a2 = Data;
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a1 && a3 && a2 < 2 )
  {
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_1156395322>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_1156395322>::GetImpl'::`2'::impl);
    v7 = *(_DWORD *)(a1 + 12) & 2;
    if ( IsEnabled )
    {
      if ( !v7 )
        goto LABEL_11;
      v8 = (unsigned int)IsCallFromAdmin() == 0;
    }
    else
    {
      v8 = v7 == 0;
    }
    if ( !v8 )
    {
      v9 = RegCreateKeyExW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Services\\TermServLicensing\\Parameters",
             0,
             0,
             0,
             0x20006u,
             0,
             &hKey,
             &dwDisposition);
      if ( !v9 )
      {
        v9 = RegSetValueExW(hKey, L"Role", 0, 4u, (const BYTE *)&Data, 4u);
        if ( !v9 )
        {
          *(_DWORD *)&g_SrvRole = Data;
          if ( (Data & 1) == 0 )
          {
            v9 = IsLSonDC(&v12, 0);
            if ( !v9 && !v12 )
              CrimsonHelper::RaiseEventInternal(
                (CrimsonHelper *)CrimsonHelper::s_instance,
                &TLS_W_TLSARW_LS_NOT_ON_DC,
                0,
                0);
          }
        }
      }
      goto LABEL_19;
    }
LABEL_11:
    v9 = 5;
LABEL_19:
    if ( hKey )
      RegCloseKey(hKey);
    *a3 = v9;
    if ( !v9 )
      CrimsonHelper::RaiseEventInternal((CrimsonHelper *)CrimsonHelper::s_instance, &TLS_I_LS_ROLE_CHANGED, 0, 0);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        WPP_32285b1e2ab033aa73a29666e87f0116_Traceguids,
        L"TLSRpcChangeRole");
    return 0;
  }
  if ( v5 != &WPP_GLOBAL_Control && (*((_DWORD *)v5 + 7) & 0x1000) != 0 )
    WPP_SF_S(v5[2], 25, WPP_32285b1e2ab033aa73a29666e87f0116_Traceguids, L"TLSRpcChangeRole");
  return 87;
}

```

## disassembly

```asm
0x180058f20  mov     [rsp-18h+arg_10], rbx
0x180058f25  mov     [rsp-18h+Data], edx
0x180058f29  push    rbp
0x180058f2a  push    rdi
0x180058f2b  push    r15
0x180058f2d  mov     rbp, rsp
0x180058f30  sub     rsp, 60h
0x180058f34  and     [rbp+dwDisposition], 0
0x180058f38  mov     rdi, r8
0x180058f3b  and     [rbp+hKey], 0
0x180058f40  mov     rbx, rcx
0x180058f43  and     [rbp+arg_0], 0
0x180058f47  mov     rcx, cs:WPP_GLOBAL_Control
0x180058f4e  lea     r15, WPP_GLOBAL_Control
0x180058f55  cmp     rcx, r15
0x180058f58  jz      short loc_180058F89
0x180058f5a  test    dword ptr [rcx+1Ch], 1000h
0x180058f61  jz      short loc_180058F89
0x180058f63  mov     rcx, [rcx+10h]
0x180058f67  lea     r9, aTlsrpcchangero; "TLSRpcChangeRole"
0x180058f6e  mov     edx, 18h
0x180058f73  lea     r8, WPP_32285b1e2ab033aa73a29666e87f0116_Traceguids
0x180058f7a  call    WPP_SF_S
0x180058f7f  mov     edx, [rbp+Data]
0x180058f82  mov     rcx, cs:WPP_GLOBAL_Control
0x180058f89  test    rbx, rbx
0x180058f8c  jz      loc_1800590F7
0x180058f92  test    rdi, rdi
0x180058f95  jz      loc_1800590F7
0x180058f9b  cmp     edx, 2
0x180058f9e  jnb     loc_1800590F7
0x180058fa4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_1156395322@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_1156395322@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_1156395322> `wil::Feature<__WilFeatureTraits_Feature_1156395322>::GetImpl(void)'::`2'::impl
0x180058fab  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_1156395322@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_1156395322>::__private_IsEnabled(void)
0x180058fb0  mov     ecx, [rbx+0Ch]
0x180058fb3  and     ecx, 2
0x180058fb6  test    al, al
0x180058fb8  jz      short loc_180058FD1
0x180058fba  test    ecx, ecx
0x180058fbc  jz      short loc_180058FC7
0x180058fbe  call    IsCallFromAdmin
0x180058fc3  test    eax, eax
0x180058fc5  jnz     short loc_180058FD5
0x180058fc7  mov     ebx, 5
0x180058fcc  jmp     loc_18005908E
0x180058fd1  test    ecx, ecx
0x180058fd3  jmp     short loc_180058FC5
0x180058fd5  lea     rax, [rbp+dwDisposition]
0x180058fd9  xor     r9d, r9d; lpClass
0x180058fdc  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x180058fe1  lea     rdx, aSystemCurrentc_6; "System\\CurrentControlSet\\Services\\Te"...
0x180058fe8  lea     rax, [rbp+hKey]
0x180058fec  xor     r8d, r8d; Reserved
0x180058fef  mov     [rsp+60h+phkResult], rax; phkResult
0x180058ff4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180058ffb  and     [rsp+60h+var_30], 0
0x180059001  mov     [rsp+60h+samDesired], 20006h; samDesired
0x180059009  and     dword ptr [rsp+60h+lpData], 0
0x18005900e  call    cs:__imp_RegCreateKeyExW
0x180059015  nop     dword ptr [rax+rax+00h]
0x18005901a  mov     ebx, eax
0x18005901c  test    eax, eax
0x18005901e  jnz     short loc_18005908E
0x180059020  mov     rcx, [rbp+hKey]; hKey
0x180059024  lea     r9d, [rax+4]; dwType
0x180059028  lea     rax, [rbp+Data]
0x18005902c  mov     [rsp+60h+samDesired], r9d; cbData
0x180059031  xor     r8d, r8d; Reserved
0x180059034  mov     [rsp+60h+lpData], rax; lpData
0x180059039  lea     rdx, aRole_0; "Role"
0x180059040  call    cs:__imp_RegSetValueExW
0x180059047  nop     dword ptr [rax+rax+00h]
0x18005904c  mov     ebx, eax
0x18005904e  test    eax, eax
0x180059050  jnz     short loc_18005908E
0x180059052  mov     eax, [rbp+Data]
0x180059055  mov     cs:?g_SrvRole@@3KA, eax; ulong g_SrvRole
0x18005905b  test    al, 1
0x18005905d  jnz     short loc_18005908E
0x18005905f  xor     edx, edx
0x180059061  lea     rcx, [rbp+arg_0]
0x180059065  call    IsLSonDC
0x18005906a  mov     ebx, eax
0x18005906c  test    eax, eax
0x18005906e  jnz     short loc_18005908E
0x180059070  cmp     [rbp+arg_0], eax
0x180059073  jnz     short loc_18005908E
0x180059075  xor     r9d, r9d; struct _EVENT_DATA_DESCRIPTOR *
0x180059078  lea     rdx, TLS_W_TLSARW_LS_NOT_ON_DC; struct _EVENT_DESCRIPTOR *
0x18005907f  xor     r8d, r8d; unsigned int
0x180059082  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; this
0x180059089  call    ?RaiseEventInternal@CrimsonHelper@@AEAAKAEBU_EVENT_DESCRIPTOR@@KQEAU_EVENT_DATA_DESCRIPTOR@@@Z; CrimsonHelper::RaiseEventInternal(_EVENT_DESCRIPTOR const &,ulong,_EVENT_DATA_DESCRIPTOR * const)
0x18005908e  mov     rcx, [rbp+hKey]; hKey
0x180059092  test    rcx, rcx
0x180059095  jz      short loc_1800590A3
0x180059097  call    cs:__imp_RegCloseKey
0x18005909e  nop     dword ptr [rax+rax+00h]
0x1800590a3  mov     [rdi], ebx
0x1800590a5  test    ebx, ebx
0x1800590a7  jnz     short loc_1800590C2
0x1800590a9  xor     r9d, r9d; struct _EVENT_DATA_DESCRIPTOR *
0x1800590ac  lea     rdx, TLS_I_LS_ROLE_CHANGED; struct _EVENT_DESCRIPTOR *
0x1800590b3  xor     r8d, r8d; unsigned int
0x1800590b6  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; this
0x1800590bd  call    ?RaiseEventInternal@CrimsonHelper@@AEAAKAEBU_EVENT_DESCRIPTOR@@KQEAU_EVENT_DATA_DESCRIPTOR@@@Z; CrimsonHelper::RaiseEventInternal(_EVENT_DESCRIPTOR const &,ulong,_EVENT_DATA_DESCRIPTOR * const)
0x1800590c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800590c9  cmp     rcx, r15
0x1800590cc  jz      short loc_1800590F3
0x1800590ce  test    dword ptr [rcx+1Ch], 1000h
0x1800590d5  jz      short loc_1800590F3
0x1800590d7  mov     rcx, [rcx+10h]
0x1800590db  lea     r9, aTlsrpcchangero; "TLSRpcChangeRole"
0x1800590e2  mov     edx, 1Ah
0x1800590e7  lea     r8, WPP_32285b1e2ab033aa73a29666e87f0116_Traceguids
0x1800590ee  call    WPP_SF_S
0x1800590f3  xor     eax, eax
0x1800590f5  jmp     short loc_180059126
0x1800590f7  cmp     rcx, r15
0x1800590fa  jz      short loc_180059121
0x1800590fc  test    dword ptr [rcx+1Ch], 1000h
0x180059103  jz      short loc_180059121
0x180059105  mov     rcx, [rcx+10h]
0x180059109  lea     r9, aTlsrpcchangero; "TLSRpcChangeRole"
0x180059110  mov     edx, 19h
0x180059115  lea     r8, WPP_32285b1e2ab033aa73a29666e87f0116_Traceguids
0x18005911c  call    WPP_SF_S
0x180059121  mov     eax, 57h ; 'W'
0x180059126  mov     rbx, [rsp+60h+arg_10]
0x18005912e  add     rsp, 60h
0x180059132  pop     r15
0x180059134  pop     rdi
0x180059135  pop     rbp
0x180059136  retn
```
