# RealtimeProtection::DlpEngineUtils::SetCloudSyncAppsConfig(void)

- ea: `0x1801ad448`
- end: `0x1801ad6e2`
- name: `?SetCloudSyncAppsConfig@DlpEngineUtils@RealtimeProtection@@YAXXZ`
- size: `666`
- prototype: `void __fastcall(RealtimeProtection::DlpEngineUtils *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18019fa0c`

## callees

- `0x180028d80`
- `0x180029590`
- `0x18002ece0`
- `0x1800809d0`
- `0x18010cb40`
- `0x180175cec`
- `0x1801ad448`

## import_xrefs

- `MpClient!MpConfigSetValue` at `0x1801ad59c`
- `MpClient!MpConfigSetValue` at `0x1801ad59c`
- `MpClient!MpConfigClose` at `0x1801ad52f`
- `MpClient!MpConfigClose` at `0x1801ad5ed`
- `MpClient!MpConfigClose` at `0x1801ad652`
- `MpClient!MpConfigClose` at `0x1801ad670`
- `MpClient!MpConfigClose` at `0x1801ad52f`
- `MpClient!MpConfigClose` at `0x1801ad5ed`
- `MpClient!MpConfigClose` at `0x1801ad652`
- `MpClient!MpConfigClose` at `0x1801ad670`
- `MpClient!MpConfigDelValue` at `0x1801ad60b`
- `MpClient!MpConfigDelValue` at `0x1801ad60b`
- `MpClient!MpConfigOpen` at `0x1801ad4ea`
- `MpClient!MpConfigOpen` at `0x1801ad4ea`

## string_xrefs

- `0x1801ad4e3`: `DLP Configs`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
void __fastcall RealtimeProtection::DlpEngineUtils::SetCloudSyncAppsConfig(RealtimeProtection::DlpEngineUtils *this)
{
  _QWORD *Instance; // rax
  int CloudSyncApps; // edi
  unsigned int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 v7; // rcx
  _QWORD *v8; // rdx
  __int64 v9; // rax
  __int64 v10; // rax
  int v11; // edi
  int v12; // edi
  _BYTE v13[8]; // [rsp+38h] [rbp-50h] BYREF
  std::_Ref_count_base *v14; // [rsp+40h] [rbp-48h]
  __int64 v15; // [rsp+48h] [rbp-40h] BYREF
  _QWORD v16[4]; // [rsp+50h] [rbp-38h] BYREF
  char v17; // [rsp+70h] [rbp-18h]

  v17 = 0;
  Instance = (_QWORD *)EndpointDlp::endpointDlpImpl::GetInstance(v13);
  CloudSyncApps = EndpointDlp::endpointDlpImpl::GetCloudSyncApps(*Instance, v16);
  if ( v14 )
    std::_Ref_count_base::_Decref(v14);
  if ( CloudSyncApps < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        208,
        &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
        (unsigned int)CloudSyncApps);
    goto LABEL_39;
  }
  v15 = 0;
  v3 = MpConfigOpen(L"DLP Configs", &v15);
  v6 = v3;
  if ( (v3 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 209, &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids, v3);
    if ( v15 )
      MpConfigClose(v15, v4, v5, v6);
    goto LABEL_39;
  }
  v7 = v15;
  if ( v17 )
  {
    v8 = v16;
    if ( v16[3] > 7u )
      v8 = (_QWORD *)v16[0];
    v9 = -1;
    do
      ++v9;
    while ( *((_WORD *)v8 + v9) );
    v10 = 2 * v9 + 2;
    if ( v10 != (unsigned int)v10 )
    {
      v11 = -2147024809;
      goto LABEL_24;
    }
    v11 = MpConfigSetValue(v15, L"CloudSyncAppsList", 2, (unsigned int)v10, v8);
    if ( v11 < 0 )
    {
      v7 = v15;
LABEL_24:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          210,
          &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
          (unsigned int)v11);
        v7 = v15;
      }
      if ( v7 )
        ((void (*)(void))MpConfigClose)();
      goto LABEL_39;
    }
    goto LABEL_37;
  }
  v12 = MpConfigDelValue(v15, L"CloudSyncAppsList", v5, v3);
  if ( v12 >= 0 )
  {
LABEL_37:
    if ( v15 )
      ((void (*)(void))MpConfigClose)();
    goto LABEL_39;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      211,
      &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
      (unsigned int)v12);
  if ( v15 )
    ((void (*)(void))MpConfigClose)();
LABEL_39:
  std::optional<std::wstring>::~optional<std::wstring>(v16);
}

```

## disassembly

```asm
0x1801ad448  mov     [rsp+arg_0], rbx
0x1801ad44d  push    rdi
0x1801ad44e  sub     rsp, 80h
0x1801ad455  mov     rax, cs:__security_cookie
0x1801ad45c  xor     rax, rsp
0x1801ad45f  mov     [rsp+88h+var_10], rax
0x1801ad464  xor     ebx, ebx
0x1801ad466  mov     [rsp+88h+var_18], bl
0x1801ad46a  lea     rcx, [rsp+88h+var_50]
0x1801ad46f  call    ?GetInstance@endpointDlpImpl@EndpointDlp@@SA?AV?$shared_ptr@VendpointDlpImpl@EndpointDlp@@@std@@XZ; EndpointDlp::endpointDlpImpl::GetInstance(void)
0x1801ad474  nop
0x1801ad475  lea     rdx, [rsp+88h+var_38]
0x1801ad47a  mov     rcx, [rax]
0x1801ad47d  call    ?GetCloudSyncApps@endpointDlpImpl@EndpointDlp@@QEBAJAEAV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@Z; EndpointDlp::endpointDlpImpl::GetCloudSyncApps(std::optional<std::wstring> &)
0x1801ad482  mov     edi, eax
0x1801ad484  mov     rcx, [rsp+88h+var_48]; this
0x1801ad489  test    rcx, rcx
0x1801ad48c  jz      short loc_1801AD493
0x1801ad48e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801ad493  test    edi, edi
0x1801ad495  jns     short loc_1801AD4D9
0x1801ad497  lea     rax, WPP_GLOBAL_Control
0x1801ad49e  mov     rcx, cs:WPP_GLOBAL_Control
0x1801ad4a5  cmp     rcx, rax
0x1801ad4a8  jz      short loc_1801AD4C9
0x1801ad4aa  test    byte ptr [rcx+1Ch], 1
0x1801ad4ae  jz      short loc_1801AD4C9
0x1801ad4b0  mov     edx, 0D0h
0x1801ad4b5  mov     r9d, edi
0x1801ad4b8  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x1801ad4bf  mov     rcx, [rcx+10h]
0x1801ad4c3  call    WPP_SF_d
0x1801ad4c8  nop
0x1801ad4c9  lea     rcx, [rsp+88h+var_38]
0x1801ad4ce  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x1801ad4d3  nop
0x1801ad4d4  jmp     loc_1801AD6C4
0x1801ad4d9  mov     [rsp+88h+var_40], rbx
0x1801ad4de  lea     rdx, [rsp+88h+var_40]
0x1801ad4e3  lea     rcx, aDlpConfigs_0; "DLP Configs"
0x1801ad4ea  call    cs:__imp_MpConfigOpen
0x1801ad4f0  mov     r9d, eax
0x1801ad4f3  test    eax, eax
0x1801ad4f5  jns     short loc_1801AD546
0x1801ad4f7  lea     rax, WPP_GLOBAL_Control
0x1801ad4fe  mov     rcx, cs:WPP_GLOBAL_Control
0x1801ad505  cmp     rcx, rax
0x1801ad508  jz      short loc_1801AD525
0x1801ad50a  test    byte ptr [rcx+1Ch], 1
0x1801ad50e  jz      short loc_1801AD525
0x1801ad510  mov     edx, 0D1h
0x1801ad515  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x1801ad51c  mov     rcx, [rcx+10h]
0x1801ad520  call    WPP_SF_d
0x1801ad525  mov     rcx, [rsp+88h+var_40]
0x1801ad52a  test    rcx, rcx
0x1801ad52d  jz      short loc_1801AD536
0x1801ad52f  call    cs:__imp_MpConfigClose
0x1801ad535  nop
0x1801ad536  lea     rcx, [rsp+88h+var_38]
0x1801ad53b  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x1801ad540  nop
0x1801ad541  jmp     loc_1801AD6C4
0x1801ad546  mov     rcx, [rsp+88h+var_40]
0x1801ad54b  cmp     [rsp+88h+var_18], bl
0x1801ad54f  jz      loc_1801AD604
0x1801ad555  lea     rdx, [rsp+88h+var_38]
0x1801ad55a  cmp     [rsp+88h+var_20], 7
0x1801ad560  cmova   rdx, [rsp+88h+var_38]
0x1801ad566  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801ad56a  inc     rax
0x1801ad56d  cmp     [rdx+rax*2], bx
0x1801ad571  jnz     short loc_1801AD56A
0x1801ad573  lea     rax, ds:2[rax*2]
0x1801ad57b  mov     r9d, eax
0x1801ad57e  cmp     rax, r9
0x1801ad581  jz      short loc_1801AD58A
0x1801ad583  mov     edi, 80070057h
0x1801ad588  jmp     short loc_1801AD5B1
0x1801ad58a  mov     [rsp+88h+var_68], rdx
0x1801ad58f  mov     r8d, 2
0x1801ad595  lea     rdx, aCloudsyncappsl; "CloudSyncAppsList"
0x1801ad59c  call    cs:__imp_MpConfigSetValue
0x1801ad5a2  mov     edi, eax
0x1801ad5a4  test    eax, eax
0x1801ad5a6  jns     loc_1801AD666
0x1801ad5ac  mov     rcx, [rsp+88h+var_40]
0x1801ad5b1  lea     rax, WPP_GLOBAL_Control
0x1801ad5b8  mov     r10, cs:WPP_GLOBAL_Control
0x1801ad5bf  cmp     r10, rax
0x1801ad5c2  jz      short loc_1801AD5E8
0x1801ad5c4  test    byte ptr [r10+1Ch], 1
0x1801ad5c9  jz      short loc_1801AD5E8
0x1801ad5cb  mov     edx, 0D2h
0x1801ad5d0  mov     r9d, edi
0x1801ad5d3  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x1801ad5da  mov     rcx, [r10+10h]
0x1801ad5de  call    WPP_SF_d
0x1801ad5e3  mov     rcx, [rsp+88h+var_40]
0x1801ad5e8  test    rcx, rcx
0x1801ad5eb  jz      short loc_1801AD5F4
0x1801ad5ed  call    cs:__imp_MpConfigClose
0x1801ad5f3  nop
0x1801ad5f4  lea     rcx, [rsp+88h+var_38]
0x1801ad5f9  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x1801ad5fe  nop
0x1801ad5ff  jmp     loc_1801AD6C4
0x1801ad604  lea     rdx, aCloudsyncappsl; "CloudSyncAppsList"
0x1801ad60b  call    cs:__imp_MpConfigDelValue
0x1801ad611  mov     edi, eax
0x1801ad613  test    eax, eax
0x1801ad615  jns     short loc_1801AD666
0x1801ad617  lea     rax, WPP_GLOBAL_Control
0x1801ad61e  mov     rcx, cs:WPP_GLOBAL_Control
0x1801ad625  cmp     rcx, rax
0x1801ad628  jz      short loc_1801AD648
0x1801ad62a  test    byte ptr [rcx+1Ch], 1
0x1801ad62e  jz      short loc_1801AD648
0x1801ad630  mov     edx, 0D3h
0x1801ad635  mov     r9d, edi
0x1801ad638  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x1801ad63f  mov     rcx, [rcx+10h]
0x1801ad643  call    WPP_SF_d
0x1801ad648  mov     rcx, [rsp+88h+var_40]
0x1801ad64d  test    rcx, rcx
0x1801ad650  jz      short loc_1801AD659
0x1801ad652  call    cs:__imp_MpConfigClose
0x1801ad658  nop
0x1801ad659  lea     rcx, [rsp+88h+var_38]
0x1801ad65e  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x1801ad663  nop
0x1801ad664  jmp     short loc_1801AD6C4
0x1801ad666  mov     rcx, [rsp+88h+var_40]
0x1801ad66b  test    rcx, rcx
0x1801ad66e  jz      short loc_1801AD677
0x1801ad670  call    cs:__imp_MpConfigClose
0x1801ad676  nop
0x1801ad677  lea     rcx, [rsp+88h+var_38]
0x1801ad67c  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x1801ad681  nop
0x1801ad682  jmp     short loc_1801AD688
0x1801ad684  mov     edi, dword ptr [rsp+88h+var_40]
0x1801ad688  test    edi, edi
0x1801ad68a  jns     short loc_1801AD6C4
0x1801ad68c  jmp     short loc_1801AD692
0x1801ad68e  mov     edi, dword ptr [rsp+88h+var_40]
0x1801ad692  lea     rax, WPP_GLOBAL_Control
0x1801ad699  mov     rcx, cs:WPP_GLOBAL_Control
0x1801ad6a0  cmp     rcx, rax
0x1801ad6a3  jz      short loc_1801AD6C4
0x1801ad6a5  test    byte ptr [rcx+1Ch], 1
0x1801ad6a9  jz      short loc_1801AD6C4
0x1801ad6ab  mov     edx, 0D4h
0x1801ad6b0  mov     r9d, edi
0x1801ad6b3  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x1801ad6ba  mov     rcx, [rcx+10h]
0x1801ad6be  call    WPP_SF_d
0x1801ad6c3  nop
0x1801ad6c4  mov     rcx, [rsp+88h+var_10]
0x1801ad6c9  xor     rcx, rsp; StackCookie
0x1801ad6cc  call    __security_check_cookie
0x1801ad6d1  mov     rbx, [rsp+88h+arg_0]
0x1801ad6d9  add     rsp, 80h
0x1801ad6e0  pop     rdi
0x1801ad6e1  retn
```
