# APP_POOL_DATA_OBJECT_CS::SetRecycleSettingsFromConfigStoreData(INativeConfigurationElement *)

- ea: `0x180048718`
- end: `0x180048aae`
- name: `?SetRecycleSettingsFromConfigStoreData@APP_POOL_DATA_OBJECT_CS@@QEAAJPEAVINativeConfigurationElement@@@Z`
- size: `918`
- prototype: `__int64 __fastcall(APP_POOL_DATA_OBJECT_CS *__hidden this, struct INativeConfigurationElement *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180044950`

## callees

- `0x180046788`
- `0x180048718`
- `0x180052d90`
- `0x180052f8c`
- `0x180053908`
- `0x180062010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18004885e`
- `iisutil!PuDbgPrint` at `0x180048951`
- `iisutil!PuDbgPrint` at `0x180048a36`
- `iisutil!PuDbgPrint` at `0x18004885e`
- `iisutil!PuDbgPrint` at `0x180048951`
- `iisutil!PuDbgPrint` at `0x180048a36`
- `iisutil!PuDbgPrintError` at `0x180048a79`
- `iisutil!PuDbgPrintError` at `0x180048a79`

## string_xrefs

- `0x180048785`: ` Failed reading property \n`
- `0x1800488a5`: ` Failed reading property \n`
- `0x180048994`: ` Failed reading property \n`
- `0x180048799`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\apppoolstore_cs.cxx`
- `0x18004880c`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\apppoolstore_cs.cxx`
- `0x180048792`: `APP_POOL_DATA_OBJECT_CS::SetRecycleSettingsFromConfigStoreData`
- `0x180048803`: `APP_POOL_DATA_OBJECT_CS::SetRecycleSettingsFromConfigStoreData`
- `0x18004887f`: `disallowRotationOnConfigChange`
- `0x1800488c5`: `disallowRotationOnConfigChange`
- `0x18004893d`: ` Don't Rotate on Config Change = %S \n`

## pseudocode

```c
__int64 __fastcall APP_POOL_DATA_OBJECT_CS::SetRecycleSettingsFromConfigStoreData(
        APP_POOL_DATA_OBJECT_CS *this,
        struct INativeConfigurationElement *a2)
{
  __int64 v2; // rax
  int *v3; // r15
  int v6; // ebx
  struct CONFIG_ERROR *v7; // rdx
  const wchar_t *v8; // r13
  const wchar_t *v9; // rax
  int *v10; // r15
  const char *v11; // rax
  __int64 v12; // r8
  struct CONFIG_ERROR *v13; // rdx
  int *v14; // r15
  struct CONFIG_ERROR *v15; // rdx
  struct INativePropertyException *v17; // [rsp+80h] [rbp+40h] BYREF
  struct CONFIG_ERROR *v18; // [rsp+88h] [rbp+48h] BYREF

  v2 = *(_QWORD *)a2;
  v3 = (int *)((char *)this + 240);
  v17 = 0;
  v18 = 0;
  v6 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(v2 + 72))(
         a2,
         L"disallowOverlappingRotation",
         (char *)this + 240,
         &v17,
         0);
  if ( v6 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
        1295,
        "APP_POOL_DATA_OBJECT_CS::SetRecycleSettingsFromConfigStoreData",
        v6,
        " Failed reading property \n");
    goto LABEL_36;
  }
  if ( v17 )
  {
    CONFIG_ERROR::CreateAndInitWithBool(&v18, L"disallowOverlappingRotation", *v3, v17);
    v7 = v18;
    if ( v18 )
    {
      *((_DWORD *)v18 + 2) = 19;
      CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v7);
    }
    v18 = 0;
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  v8 = L"TRUE";
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
  {
    v9 = L"TRUE";
    if ( !*v3 )
      v9 = L"FALSE";
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
      1316,
      "APP_POOL_DATA_OBJECT_CS::SetRecycleSettingsFromConfigStoreData",
      " Don't Overlapped = %S \n",
      v9);
  }
  v10 = (int *)((char *)this + 364);
  v6 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 72LL))(
         a2,
         L"disallowRotationOnConfigChange",
         (char *)this + 364,
         &v17,
         0);
  if ( v6 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_36;
    v11 = " Failed reading property \n";
    v12 = 1326;
    goto LABEL_35;
  }
  if ( v17 )
  {
    CONFIG_ERROR::CreateAndInitWithBool(&v18, L"disallowRotationOnConfigChange", *v10, v17);
    v13 = v18;
    if ( v18 )
    {
      *((_DWORD *)v18 + 2) = 23;
      CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v13);
    }
    v18 = 0;
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
  {
    if ( !*v10 )
      v8 = L"FALSE";
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
      1347,
      "APP_POOL_DATA_OBJECT_CS::SetRecycleSettingsFromConfigStoreData",
      " Don't Rotate on Config Change = %S \n",
      v8);
  }
  v14 = (int *)((char *)this + 724);
  v6 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 48LL))(
         a2,
         L"logEventOnRecycle",
         (char *)this + 724,
         &v17,
         0);
  if ( v6 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_36;
    v11 = " Failed reading property \n";
    v12 = 1357;
    goto LABEL_35;
  }
  if ( v17 )
  {
    CONFIG_ERROR::CreateAndInitWithLong(&v18, L"logEventOnRecycle", *v14, v17);
    v15 = v18;
    if ( v18 )
    {
      *((_DWORD *)v18 + 2) = 40;
      CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v15);
    }
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
      1379,
      "APP_POOL_DATA_OBJECT_CS::SetRecycleSettingsFromConfigStoreData",
      " Recycle Logging Flag = %u (0x%X) \n",
      *v14,
      *v14);
  v6 = APP_POOL_DATA_OBJECT_CS::SetPeriodicRestart(this, a2);
  if ( v6 < 0 && (g_dwDebugFlags & 0xF) != 0 )
  {
    v11 = " Failed setting up Periodic Restart\n";
    v12 = 1387;
LABEL_35:
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
      v12,
      "APP_POOL_DATA_OBJECT_CS::SetRecycleSettingsFromConfigStoreData",
      v6,
      v11);
  }
LABEL_36:
  if ( v17 )
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v17 + 16LL))(v17);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180048718  mov     [rsp-38h+arg_10], rbx
0x18004871d  push    rbp
0x18004871e  push    rsi
0x18004871f  push    rdi
0x180048720  push    r12
0x180048722  push    r13
0x180048724  push    r14
0x180048726  push    r15
0x180048728  mov     rbp, rsp
0x18004872b  sub     rsp, 40h
0x18004872f  mov     rax, [rdx]
0x180048732  lea     r15, [rcx+0F0h]
0x180048739  mov     r12, rdx
0x18004873c  mov     [rbp+arg_0], 0
0x180048744  mov     r14, rcx
0x180048747  mov     [rbp+arg_8], 0
0x18004874f  lea     r9, [rbp+arg_0]
0x180048753  mov     [rsp+40h+var_20], 0
0x18004875c  mov     rax, [rax+48h]
0x180048760  lea     rdx, aDisallowoverla; "disallowOverlappingRotation"
0x180048767  mov     r8, r15
0x18004876a  mov     rcx, r12
0x18004876d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048772  mov     ebx, eax
0x180048774  test    eax, eax
0x180048776  jns     short loc_1800487A5
0x180048778  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004877f  jz      loc_180048A7F
0x180048785  lea     rax, aFailedReadingP_1; " Failed reading property \n"
0x18004878c  mov     r8d, 50Fh
0x180048792  lea     r9, aAppPoolDataObj_5; "APP_POOL_DATA_OBJECT_CS::SetRecycleSett"...
0x180048799  lea     rdx, aServercommonIn_62; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800487a0  jmp     loc_180048A69
0x1800487a5  mov     r9, [rbp+arg_0]; struct INativePropertyException *
0x1800487a9  test    r9, r9
0x1800487ac  jz      short loc_1800487FD
0x1800487ae  mov     r8d, [r15]; int
0x1800487b1  lea     rdx, aDisallowoverla; "disallowOverlappingRotation"
0x1800487b8  lea     rcx, [rbp+arg_8]; struct CONFIG_ERROR **
0x1800487bc  call    ?CreateAndInitWithBool@CONFIG_ERROR@@SAXPEAPEAV1@PEBGHPEAVINativePropertyException@@@Z; CONFIG_ERROR::CreateAndInitWithBool(CONFIG_ERROR * *,ushort const *,int,INativePropertyException *)
0x1800487c1  mov     rdx, [rbp+arg_8]; struct CONFIG_ERROR *
0x1800487c5  test    rdx, rdx
0x1800487c8  jz      short loc_1800487DD
0x1800487ca  lea     rcx, [r14+3E8h]; this
0x1800487d1  mov     dword ptr [rdx+8], 13h
0x1800487d8  call    ?Add@CONFIG_ERROR_LIST@@QEAAXPEAVCONFIG_ERROR@@@Z; CONFIG_ERROR_LIST::Add(CONFIG_ERROR *)
0x1800487dd  mov     rcx, [rbp+arg_0]
0x1800487e1  mov     [rbp+arg_8], 0
0x1800487e9  mov     rax, [rcx]
0x1800487ec  mov     rax, [rax+10h]
0x1800487f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800487f5  mov     [rbp+arg_0], 0
0x1800487fd  mov     eax, cs:g_dwDebugFlags
0x180048803  lea     rdi, aAppPoolDataObj_5; "APP_POOL_DATA_OBJECT_CS::SetRecycleSett"...
0x18004880a  test    al, 3
0x18004880c  lea     rsi, aServercommonIn_62; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180048813  lea     rdx, aFalse_1; "FALSE"
0x18004881a  setnz   cl
0x18004881d  lea     r13, aTrue_1; "TRUE"
0x180048824  bt      eax, 1Eh
0x180048828  setb    al
0x18004882b  test    al, cl
0x18004882d  jz      short loc_180048864
0x18004882f  cmp     dword ptr [r15], 0
0x180048833  mov     rax, r13
0x180048836  mov     rcx, cs:g_pDebug
0x18004883d  mov     r9, rdi
0x180048840  cmovz   rax, rdx
0x180048844  mov     r8d, 524h
0x18004884a  mov     [rsp+40h+var_18], rax
0x18004884f  mov     rdx, rsi
0x180048852  lea     rax, aDonTOverlapped; " Don't Overlapped = %S \n"
0x180048859  mov     [rsp+40h+var_20], rax
0x18004885e  call    cs:__imp_PuDbgPrint
0x180048864  mov     rax, [r12]
0x180048868  lea     r15, [r14+16Ch]
0x18004886f  lea     r9, [rbp+arg_0]
0x180048873  mov     [rsp+40h+var_20], 0
0x18004887c  mov     r8, r15
0x18004887f  lea     rdx, aDisallowrotati; "disallowRotationOnConfigChange"
0x180048886  mov     rcx, r12
0x180048889  mov     rax, [rax+48h]
0x18004888d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048892  mov     ebx, eax
0x180048894  test    eax, eax
0x180048896  jns     short loc_1800488B7
0x180048898  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004889f  jz      loc_180048A7F
0x1800488a5  lea     rax, aFailedReadingP_1; " Failed reading property \n"
0x1800488ac  mov     r8d, 52Eh
0x1800488b2  jmp     loc_180048A63
0x1800488b7  mov     r9, [rbp+arg_0]; struct INativePropertyException *
0x1800488bb  xor     ebx, ebx
0x1800488bd  test    r9, r9
0x1800488c0  jz      short loc_180048909
0x1800488c2  mov     r8d, [r15]; int
0x1800488c5  lea     rdx, aDisallowrotati; "disallowRotationOnConfigChange"
0x1800488cc  lea     rcx, [rbp+arg_8]; struct CONFIG_ERROR **
0x1800488d0  call    ?CreateAndInitWithBool@CONFIG_ERROR@@SAXPEAPEAV1@PEBGHPEAVINativePropertyException@@@Z; CONFIG_ERROR::CreateAndInitWithBool(CONFIG_ERROR * *,ushort const *,int,INativePropertyException *)
0x1800488d5  mov     rdx, [rbp+arg_8]; struct CONFIG_ERROR *
0x1800488d9  test    rdx, rdx
0x1800488dc  jz      short loc_1800488F1
0x1800488de  lea     rcx, [r14+3E8h]; this
0x1800488e5  mov     dword ptr [rdx+8], 17h
0x1800488ec  call    ?Add@CONFIG_ERROR_LIST@@QEAAXPEAVCONFIG_ERROR@@@Z; CONFIG_ERROR_LIST::Add(CONFIG_ERROR *)
0x1800488f1  mov     rcx, [rbp+arg_0]
0x1800488f5  mov     [rbp+arg_8], rbx
0x1800488f9  mov     rax, [rcx]
0x1800488fc  mov     rax, [rax+10h]
0x180048900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048905  mov     [rbp+arg_0], rbx
0x180048909  mov     eax, cs:g_dwDebugFlags
0x18004890f  test    al, 3
0x180048911  setnz   cl
0x180048914  bt      eax, 1Eh
0x180048918  setb    al
0x18004891b  test    al, cl
0x18004891d  jz      short loc_180048957
0x18004891f  cmp     [r15], ebx
0x180048922  lea     rax, aFalse_1; "FALSE"
0x180048929  mov     rcx, cs:g_pDebug
0x180048930  mov     r9, rdi
0x180048933  cmovz   r13, rax
0x180048937  mov     r8d, 543h
0x18004893d  lea     rax, aDonTRotateOnCo; " Don't Rotate on Config Change = %S \n"
0x180048944  mov     [rsp+40h+var_18], r13
0x180048949  mov     rdx, rsi
0x18004894c  mov     [rsp+40h+var_20], rax
0x180048951  call    cs:__imp_PuDbgPrint
0x180048957  mov     rax, [r12]
0x18004895b  lea     r15, [r14+2D4h]
0x180048962  lea     r9, [rbp+arg_0]
0x180048966  mov     [rsp+40h+var_20], rbx
0x18004896b  mov     r8, r15
0x18004896e  lea     rdx, aLogeventonrecy; "logEventOnRecycle"
0x180048975  mov     rcx, r12
0x180048978  mov     rax, [rax+30h]
0x18004897c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048981  mov     ebx, eax
0x180048983  test    eax, eax
0x180048985  jns     short loc_1800489A6
0x180048987  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004898e  jz      loc_180048A7F
0x180048994  lea     rax, aFailedReadingP_1; " Failed reading property \n"
0x18004899b  mov     r8d, 54Dh
0x1800489a1  jmp     loc_180048A63
0x1800489a6  mov     r9, [rbp+arg_0]; struct INativePropertyException *
0x1800489aa  test    r9, r9
0x1800489ad  jz      short loc_1800489F6
0x1800489af  mov     r8d, [r15]; int
0x1800489b2  lea     rdx, aLogeventonrecy; "logEventOnRecycle"
0x1800489b9  lea     rcx, [rbp+arg_8]; struct CONFIG_ERROR **
0x1800489bd  call    ?CreateAndInitWithLong@CONFIG_ERROR@@SAXPEAPEAV1@PEBGJPEAVINativePropertyException@@@Z; CONFIG_ERROR::CreateAndInitWithLong(CONFIG_ERROR * *,ushort const *,long,INativePropertyException *)
0x1800489c2  mov     rdx, [rbp+arg_8]; struct CONFIG_ERROR *
0x1800489c6  test    rdx, rdx
0x1800489c9  jz      short loc_1800489DE
0x1800489cb  lea     rcx, [r14+3E8h]; this
0x1800489d2  mov     dword ptr [rdx+8], 28h ; '('
0x1800489d9  call    ?Add@CONFIG_ERROR_LIST@@QEAAXPEAVCONFIG_ERROR@@@Z; CONFIG_ERROR_LIST::Add(CONFIG_ERROR *)
0x1800489de  mov     rcx, [rbp+arg_0]
0x1800489e2  mov     rax, [rcx]
0x1800489e5  mov     rax, [rax+10h]
0x1800489e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800489ee  mov     [rbp+arg_0], 0
0x1800489f6  mov     eax, cs:g_dwDebugFlags
0x1800489fc  test    al, 3
0x1800489fe  setnz   cl
0x180048a01  bt      eax, 1Eh
0x180048a05  setb    al
0x180048a08  test    al, cl
0x180048a0a  jz      short loc_180048A3C
0x180048a0c  mov     eax, [r15]
0x180048a0f  mov     r9, rdi
0x180048a12  mov     rcx, cs:g_pDebug
0x180048a19  mov     r8d, 563h
0x180048a1f  mov     [rsp+40h+var_10], eax
0x180048a23  mov     rdx, rsi
0x180048a26  mov     dword ptr [rsp+40h+var_18], eax
0x180048a2a  lea     rax, aRecycleLogging; " Recycle Logging Flag = %u (0x%X) \n"
0x180048a31  mov     [rsp+40h+var_20], rax
0x180048a36  call    cs:__imp_PuDbgPrint
0x180048a3c  mov     rdx, r12; struct INativeConfigurationElement *
0x180048a3f  mov     rcx, r14; this
0x180048a42  call    ?SetPeriodicRestart@APP_POOL_DATA_OBJECT_CS@@AEAAJPEAVINativeConfigurationElement@@@Z; APP_POOL_DATA_OBJECT_CS::SetPeriodicRestart(INativeConfigurationElement *)
0x180048a47  mov     ebx, eax
0x180048a49  test    eax, eax
0x180048a4b  jns     short loc_180048A7F
0x180048a4d  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180048a54  jz      short loc_180048A7F
0x180048a56  lea     rax, aFailedSettingU; " Failed setting up Periodic Restart\n"
0x180048a5d  mov     r8d, 56Bh
0x180048a63  mov     r9, rdi
0x180048a66  mov     rdx, rsi
0x180048a69  mov     rcx, cs:g_pDebug
0x180048a70  mov     [rsp+40h+var_18], rax
0x180048a75  mov     dword ptr [rsp+40h+var_20], ebx
0x180048a79  call    cs:__imp_PuDbgPrintError
0x180048a7f  mov     rcx, [rbp+arg_0]
0x180048a83  test    rcx, rcx
0x180048a86  jz      short loc_180048A94
0x180048a88  mov     rax, [rcx]
0x180048a8b  mov     rax, [rax+10h]
0x180048a8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048a94  mov     eax, ebx
0x180048a96  mov     rbx, [rsp+40h+arg_10]
0x180048a9e  add     rsp, 40h
0x180048aa2  pop     r15
0x180048aa4  pop     r14
0x180048aa6  pop     r13
0x180048aa8  pop     r12
0x180048aaa  pop     rdi
0x180048aab  pop     rsi
0x180048aac  pop     rbp
0x180048aad  retn
```
