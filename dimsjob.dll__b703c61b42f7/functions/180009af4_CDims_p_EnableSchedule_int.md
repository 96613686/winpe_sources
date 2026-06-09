# CDims::p_EnableSchedule(int)

- ea: `0x180009af4`
- end: `0x180009c82`
- name: `?p_EnableSchedule@CDims@@AEAAJH@Z`
- size: `398`
- prototype: `__int64 __fastcall(CDims *__hidden this, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800018f0`

## callees

- `0x180009af4`
- `0x180009c88`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009b4e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009b4e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009c45`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009c45`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009c36`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009c36`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009c0c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009c0c`

## string_xrefs

- `0x180009c2b`: `UserTaskRoamEnabled`

## pseudocode

```c
__int64 __fastcall CDims::p_EnableSchedule(CDims *this, int a2)
{
  struct IRegisteredTask *v2; // rbx
  unsigned __int16 v3; // si
  unsigned int Instance; // edi
  CDims *v5; // rcx
  const unsigned __int16 *v6; // r8
  _BYTE v8[24]; // [rsp+30h] [rbp-49h] BYREF
  __int128 v9; // [rsp+50h] [rbp-29h] BYREF
  __int64 v10; // [rsp+60h] [rbp-19h]
  __int128 v11; // [rsp+70h] [rbp-9h] BYREF
  __int64 v12; // [rsp+80h] [rbp+7h]
  __int128 v13; // [rsp+90h] [rbp+17h] BYREF
  __int64 v14; // [rsp+A0h] [rbp+27h]
  struct ITaskService *ppv; // [rsp+E0h] [rbp+67h] BYREF
  int Data; // [rsp+E8h] [rbp+6Fh] BYREF
  struct IRegisteredTask *v17; // [rsp+F0h] [rbp+77h] BYREF
  HKEY phkResult; // [rsp+F8h] [rbp+7Fh] BYREF

  Data = a2;
  phkResult = 0;
  ppv = 0;
  v2 = 0;
  v17 = 0;
  *(_WORD *)v8 = 1;
  v3 = 0;
  *(_OWORD *)&v8[2] = 0;
  Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, (LPVOID *)&ppv);
  if ( !Instance )
  {
    *(_QWORD *)&v8[16] = 0;
    v9 = *(_OWORD *)v8;
    v10 = 0;
    v11 = *(_OWORD *)v8;
    v12 = 0;
    v13 = *(_OWORD *)v8;
    v14 = 0;
    Instance = ((__int64 (__fastcall *)(struct ITaskService *, __int128 *, __int128 *, __int128 *, _BYTE *))ppv->lpVtbl->Connect)(
                 ppv,
                 &v13,
                 &v11,
                 &v9,
                 v8);
    if ( !Instance )
    {
      if ( Data )
        v3 = -1;
      Instance = CDims::p_GetWMIBackupTask(v5, ppv, v6, &v17);
      v2 = v17;
      if ( !Instance )
      {
        Instance = ((__int64 (__fastcall *)(struct IRegisteredTask *, _QWORD))v17->lpVtbl->put_Enabled)(v17, v3);
        if ( !Instance
          && !RegOpenKeyExW(
                HKEY_CURRENT_USER,
                L"SOFTWARE\\Policies\\Microsoft\\Cryptography\\AutoEnrollment",
                0,
                0xF003Fu,
                &phkResult) )
        {
          RegSetValueExW(phkResult, L"UserTaskRoamEnabled", 0, Instance + 4, (const BYTE *)&Data, Instance + 4);
        }
      }
    }
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( ppv )
    ((void (__fastcall *)(struct ITaskService *))ppv->lpVtbl->Release)(ppv);
  if ( v2 )
    ((void (__fastcall *)(struct IRegisteredTask *))v2->lpVtbl->Release)(v2);
  return Instance;
}

```

## disassembly

```asm
0x180009af4  mov     [rsp-8+Data], edx
0x180009af8  mov     [rsp-8+arg_0], rcx
0x180009afd  push    rbp
0x180009afe  push    rbx
0x180009aff  push    rsi
0x180009b00  push    rdi
0x180009b01  lea     rbp, [rsp-3Fh]
0x180009b06  sub     rsp, 0B8h
0x180009b0d  mov     [rbp+57h+phkResult], 0
0x180009b15  mov     [rbp+57h+arg_0], 0
0x180009b1d  xor     ebx, ebx
0x180009b1f  mov     [rbp+57h+arg_10], rbx
0x180009b23  lea     r8d, [rbx+1]; dwClsContext
0x180009b27  mov     word ptr [rbp+57h+var_A0], r8w
0x180009b2c  xorps   xmm0, xmm0
0x180009b2f  xor     esi, esi
0x180009b31  movups  [rbp+57h+var_A0+2], xmm0
0x180009b35  lea     rax, [rbp+57h+arg_0]
0x180009b39  mov     [rsp+0D0h+ppv], rax; ppv
0x180009b3e  lea     r9, IID_ITaskService; riid
0x180009b45  xor     edx, edx; pUnkOuter
0x180009b47  lea     rcx, CLSID_TaskScheduler; rclsid
0x180009b4e  call    cs:__imp_CoCreateInstance
0x180009b54  mov     edi, eax
0x180009b56  test    eax, eax
0x180009b58  jnz     loc_180009C3C
0x180009b5e  movups  xmm1, [rbp+57h+var_A0]
0x180009b62  movaps  [rbp+57h+var_A0], xmm1
0x180009b66  mov     [rbp+57h+var_90], rsi
0x180009b6a  movaps  [rbp+57h+var_80], xmm1
0x180009b6e  mov     [rbp+57h+var_70], rsi
0x180009b72  movaps  [rbp+57h+var_60], xmm1
0x180009b76  mov     [rbp+57h+var_50], rsi
0x180009b7a  movaps  [rbp+57h+var_40], xmm1
0x180009b7e  mov     [rbp+57h+var_30], rsi
0x180009b82  mov     rcx, [rbp+57h+arg_0]
0x180009b86  mov     rax, [rcx]
0x180009b89  lea     rdx, [rbp+57h+var_A0]
0x180009b8d  mov     [rsp+0D0h+ppv], rdx
0x180009b92  lea     r9, [rbp+57h+var_80]
0x180009b96  lea     r8, [rbp+57h+var_60]
0x180009b9a  lea     rdx, [rbp+57h+var_40]
0x180009b9e  mov     rax, [rax+50h]
0x180009ba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ba7  mov     edi, eax
0x180009ba9  test    eax, eax
0x180009bab  jnz     loc_180009C3C
0x180009bb1  cmp     [rbp+57h+Data], ebx
0x180009bb4  jz      short loc_180009BBB
0x180009bb6  or      esi, 0FFFFFFFFh
0x180009bb9  jmp     short loc_180009BBD
0x180009bbb  xor     eax, eax
0x180009bbd  lea     r9, [rbp+57h+arg_10]; struct IRegisteredTask **
0x180009bc1  mov     rdx, [rbp+57h+arg_0]; struct ITaskService *
0x180009bc5  call    ?p_GetWMIBackupTask@CDims@@AEAAJPEAUITaskService@@PEBGPEAPEAUIRegisteredTask@@@Z; CDims::p_GetWMIBackupTask(ITaskService *,ushort const *,IRegisteredTask * *)
0x180009bca  mov     edi, eax
0x180009bcc  mov     rbx, [rbp+57h+arg_10]
0x180009bd0  test    eax, eax
0x180009bd2  jnz     short loc_180009C3C
0x180009bd4  mov     rax, [rbx]
0x180009bd7  movzx   edx, si
0x180009bda  mov     rcx, rbx
0x180009bdd  mov     rax, [rax+58h]
0x180009be1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009be6  mov     edi, eax
0x180009be8  test    eax, eax
0x180009bea  jnz     short loc_180009C3C
0x180009bec  lea     rax, [rbp+57h+phkResult]
0x180009bf0  mov     [rsp+0D0h+ppv], rax; phkResult
0x180009bf5  mov     r9d, 0F003Fh; samDesired
0x180009bfb  xor     r8d, r8d; ulOptions
0x180009bfe  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Cryptogr"...
0x180009c05  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180009c0c  call    cs:__imp_RegOpenKeyExW
0x180009c12  test    eax, eax
0x180009c14  jnz     short loc_180009C3C
0x180009c16  lea     r9d, [rdi+4]; dwType
0x180009c1a  mov     [rsp+0D0h+cbData], r9d; cbData
0x180009c1f  lea     rax, [rbp+57h+Data]
0x180009c23  mov     [rsp+0D0h+ppv], rax; lpData
0x180009c28  xor     r8d, r8d; Reserved
0x180009c2b  lea     rdx, aUsertaskroamen; "UserTaskRoamEnabled"
0x180009c32  mov     rcx, [rbp+57h+phkResult]; hKey
0x180009c36  call    cs:__imp_RegSetValueExW
0x180009c3c  mov     rcx, [rbp+57h+phkResult]; hKey
0x180009c40  test    rcx, rcx
0x180009c43  jz      short loc_180009C4B
0x180009c45  call    cs:__imp_RegCloseKey
0x180009c4b  mov     rcx, [rbp+57h+arg_0]
0x180009c4f  test    rcx, rcx
0x180009c52  jz      short loc_180009C60
0x180009c54  mov     rax, [rcx]
0x180009c57  mov     rax, [rax+10h]
0x180009c5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c60  test    rbx, rbx
0x180009c63  jz      short loc_180009C74
0x180009c65  mov     rax, [rbx]
0x180009c68  mov     rcx, rbx
0x180009c6b  mov     rax, [rax+10h]
0x180009c6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c74  mov     eax, edi
0x180009c76  add     rsp, 0B8h
0x180009c7d  pop     rdi
0x180009c7e  pop     rsi
0x180009c7f  pop     rbx
0x180009c80  pop     rbp
0x180009c81  retn
```
