# DiscpInstalliSCSIVirtualAdapter

- ea: `0x180013548`
- end: `0x1800138fe`
- name: `DiscpInstalliSCSIVirtualAdapter`
- size: `950`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180013b24`

## callees

- `0x180001410`
- `0x180001cfe`
- `0x180013548`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsupr` at `0x180013652`
- `api-ms-win-crt-private-l1-1-0!_o__wcsupr` at `0x180013652`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180013666`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180013666`
- `ISCSIUM!DiscpReportEventlogWithStatus` at `0x1800138c8`
- `ISCSIUM!DiscpReportEventlogWithStatus` at `0x1800138c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800136c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013745`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800137ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001381d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013894`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800136c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013745`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800137ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001381d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013894`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800135cc`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800136b5`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800135cc`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800136b5`
- `DEVOBJ!DevObjCreateDeviceInfo` at `0x18001373b`
- `DEVOBJ!DevObjCreateDeviceInfo` at `0x18001373b`
- `DEVOBJ!DevObjChangeState` at `0x18001388a`
- `DEVOBJ!DevObjChangeState` at `0x18001388a`
- `DEVOBJ!DevObjSetDeviceRegistryProperty` at `0x1800137a4`
- `DEVOBJ!DevObjSetDeviceRegistryProperty` at `0x1800137a4`
- `DEVOBJ!DevObjRegisterDeviceInfo` at `0x180013813`
- `DEVOBJ!DevObjRegisterDeviceInfo` at `0x180013813`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18001368f`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800138d7`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18001368f`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800138d7`
- `DEVOBJ!DevObjGetClassDevs` at `0x180013602`
- `DEVOBJ!DevObjGetClassDevs` at `0x180013602`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x18001367d`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x18001367d`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_IDW` at `0x180013641`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_IDW` at `0x180013641`

## string_xrefs

- `0x180013750`: `Failed to create DeviceInfo`
- `0x1800136cf`: `Failed to create DeviceInfoList`

## pseudocode

```c
__int64 DiscpInstalliSCSIVirtualAdapter()
{
  __int64 DeviceInfoList; // rax
  __int64 v1; // rbx
  char v2; // di
  unsigned int v3; // esi
  __int64 i; // rdx
  __int64 v6; // rdi
  DWORD LastError; // eax
  __int64 v8; // rcx
  const wchar_t *v9; // r8
  DWORD v10; // ebx
  __int64 v11; // rdx
  _WORD *v12; // rax
  _WORD *v13; // rcx
  DWORD v14; // eax
  __int64 v15; // rcx
  const wchar_t *v16; // r8
  DWORD v17; // eax
  __int64 v18; // rcx
  const wchar_t *v19; // r8
  DWORD v20; // eax
  __int64 v21; // rcx
  const wchar_t *v22; // r8
  _QWORD v23[2]; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v24[3]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v25; // [rsp+80h] [rbp-80h] BYREF
  DEVINST dnDevInst[4]; // [rsp+90h] [rbp-70h]
  __int128 v27; // [rsp+A0h] [rbp-60h]
  _BYTE v28[256]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR Buffer[200]; // [rsp+1B0h] [rbp+B0h] BYREF

  memset(v24, 0, sizeof(v24));
  memset_0(v28, 0, sizeof(v28));
  memset(v23, 0, 12);
  v25 = 0;
  LODWORD(v24[0]) = 48;
  LODWORD(v25) = 48;
  *(_OWORD *)dnDevInst = 0;
  v27 = 0;
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v1 = DeviceInfoList;
  if ( DeviceInfoList != -1
    && (unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVCLASS_SCSIADAPTER, L"Root", 2, 0, 0) )
  {
    v2 = 0;
    v3 = 0;
    for ( i = 0; (unsigned int)DevObjEnumDeviceInfo(v1, i, &v25); i = v3 )
    {
      memset_0(Buffer, 0, sizeof(Buffer));
      if ( !CM_Get_Device_IDW(dnDevInst[1], Buffer, 0xC8u, 0) )
      {
        _o__wcsupr(Buffer);
        if ( wcsstr(Buffer, L"ROOT\\ISCSIPRT") )
        {
          v2 = 1;
          break;
        }
      }
      ++v3;
    }
    DevObjDestroyDeviceInfoList(v1);
    if ( v2 )
      return 0;
  }
  v6 = DevObjCreateDeviceInfoList(&GUID_DEVCLASS_SCSIADAPTER, 0, 0, 0, 0);
  if ( v6 == -1 )
  {
    LastError = GetLastError();
    v8 = 2147483646;
    v9 = L"Failed to create DeviceInfoList";
    v10 = LastError;
    v11 = 128;
    v12 = v28;
    do
    {
      if ( !v8 )
        break;
      if ( !*v9 )
        break;
      *v12++ = *v9++;
      --v8;
      --v11;
    }
    while ( v11 );
LABEL_17:
    v13 = v12 - 1;
    if ( v11 )
      v13 = v12;
    *v13 = 0;
LABEL_40:
    if ( v10 )
      DiscpReportEventlogWithStatus(123, 1, 0, v10, 0, 0, 1);
    if ( v6 == -1 )
      return v10;
    goto LABEL_43;
  }
  if ( !(unsigned int)DevObjCreateDeviceInfo(v6, L"ISCSIPRT", &GUID_DEVCLASS_SCSIADAPTER, 0, 1, v24) )
  {
    v14 = GetLastError();
    v15 = 2147483646;
    v16 = L"Failed to create DeviceInfo";
    v10 = v14;
    v11 = 128;
    v12 = v28;
    do
    {
      if ( !v15 )
        break;
      if ( !*v16 )
        break;
      *v12++ = *v16++;
      --v15;
      --v11;
    }
    while ( v11 );
    goto LABEL_17;
  }
  if ( !(unsigned int)DevObjSetDeviceRegistryProperty(v6, v24, 1, L"ROOT\\ISCSIPRT", 30) )
  {
    v17 = GetLastError();
    v18 = 2147483646;
    v19 = L"Failed to set hardware ID";
    v10 = v17;
    v11 = 128;
    v12 = v28;
    do
    {
      if ( !v18 )
        break;
      if ( !*v19 )
        break;
      *v12++ = *v19++;
      --v18;
      --v11;
    }
    while ( v11 );
    goto LABEL_17;
  }
  if ( !(unsigned int)DevObjRegisterDeviceInfo(v6, v24, 0, 0, 0, 0) )
  {
    v20 = GetLastError();
    v21 = 2147483646;
    v22 = L"Failed to register device";
    v10 = v20;
    v11 = 128;
    v12 = v28;
    do
    {
      if ( !v21 )
        break;
      if ( !*v22 )
        break;
      *v12++ = *v22++;
      --v21;
      --v11;
    }
    while ( v11 );
    goto LABEL_17;
  }
  *(_QWORD *)((char *)v23 + 4) = 1;
  LODWORD(v23[0]) = 3;
  v10 = 0;
  if ( !(unsigned int)DevObjChangeState(v6, v24, v23, 0) )
  {
    v10 = GetLastError();
    goto LABEL_40;
  }
LABEL_43:
  DevObjDestroyDeviceInfoList(v6);
  return v10;
}

```

## disassembly

```asm
0x180013548  push    rbp
0x18001354a  push    rbx
0x18001354b  push    rsi
0x18001354c  push    rdi
0x18001354d  push    r14
0x18001354f  push    r15
0x180013551  lea     rbp, [rsp-258h]
0x180013559  sub     rsp, 358h
0x180013560  mov     rax, cs:__security_cookie
0x180013567  xor     rax, rsp
0x18001356a  mov     [rbp+280h+var_40], rax
0x180013571  xorps   xmm0, xmm0
0x180013574  lea     rcx, [rbp+280h+var_2D0]; void *
0x180013578  xor     edx, edx; Val
0x18001357a  mov     r8d, 100h; Size
0x180013580  movups  [rsp+380h+var_330], xmm0
0x180013585  movups  [rsp+380h+var_320], xmm0
0x18001358a  movups  [rsp+380h+var_310], xmm0
0x18001358f  call    memset_0
0x180013594  xor     eax, eax
0x180013596  xorps   xmm0, xmm0
0x180013599  mov     [rsp+380h+var_340], rax
0x18001359e  xor     r14d, r14d
0x1800135a1  mov     [rsp+380h+var_338], eax
0x1800135a5  xor     r9d, r9d
0x1800135a8  mov     eax, 30h ; '0'
0x1800135ad  mov     [rsp+380h+var_360], r14
0x1800135b2  movups  [rbp+280h+var_300], xmm0
0x1800135b6  xor     r8d, r8d
0x1800135b9  mov     dword ptr [rsp+380h+var_330], eax
0x1800135bd  xor     edx, edx
0x1800135bf  mov     dword ptr [rbp+280h+var_300], eax
0x1800135c2  xor     ecx, ecx
0x1800135c4  movups  xmmword ptr [rbp+280h+dnDevInst], xmm0
0x1800135c8  movups  [rbp+280h+var_2E0], xmm0
0x1800135cc  call    cs:__imp_DevObjCreateDeviceInfoList
0x1800135d2  lea     r15d, [r14+1]
0x1800135d6  mov     rbx, rax
0x1800135d9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800135dd  jz      loc_1800136A1
0x1800135e3  mov     [rsp+380h+var_358], r14
0x1800135e8  lea     r9d, [r14+2]
0x1800135ec  lea     r8, aRoot; "Root"
0x1800135f3  mov     [rsp+380h+var_360], r14
0x1800135f8  lea     rdx, GUID_DEVCLASS_SCSIADAPTER
0x1800135ff  mov     rcx, rax
0x180013602  call    cs:__imp_DevObjGetClassDevs
0x180013608  test    eax, eax
0x18001360a  jz      loc_1800136A1
0x180013610  mov     dil, r14b
0x180013613  mov     esi, r14d
0x180013616  xor     edx, edx
0x180013618  jmp     short loc_180013676
0x18001361a  xor     edx, edx; Val
0x18001361c  lea     rcx, [rbp+280h+Buffer]; void *
0x180013623  mov     r8d, 190h; Size
0x180013629  call    memset_0
0x18001362e  mov     ecx, [rbp+280h+dnDevInst+4]; dnDevInst
0x180013631  lea     rdx, [rbp+280h+Buffer]; Buffer
0x180013638  xor     r9d, r9d; ulFlags
0x18001363b  mov     r8d, 0C8h; BufferLen
0x180013641  call    cs:__imp_CM_Get_Device_IDW
0x180013647  test    eax, eax
0x180013649  jnz     short loc_180013671
0x18001364b  lea     rcx, [rbp+280h+Buffer]
0x180013652  call    cs:__imp__o__wcsupr
0x180013658  lea     rdx, aRootIscsiprt; "ROOT\\ISCSIPRT"
0x18001365f  lea     rcx, [rbp+280h+Buffer]; Str
0x180013666  call    cs:__imp_wcsstr
0x18001366c  test    rax, rax
0x18001366f  jnz     short loc_180013689
0x180013671  add     esi, r15d
0x180013674  mov     edx, esi
0x180013676  lea     r8, [rbp+280h+var_300]
0x18001367a  mov     rcx, rbx
0x18001367d  call    cs:__imp_DevObjEnumDeviceInfo
0x180013683  test    eax, eax
0x180013685  jnz     short loc_18001361A
0x180013687  jmp     short loc_18001368C
0x180013689  mov     dil, r15b
0x18001368c  mov     rcx, rbx
0x18001368f  call    cs:__imp_DevObjDestroyDeviceInfoList
0x180013695  test    dil, dil
0x180013698  jz      short loc_1800136A1
0x18001369a  xor     eax, eax
0x18001369c  jmp     loc_1800138DF
0x1800136a1  xor     r9d, r9d
0x1800136a4  mov     [rsp+380h+var_360], r14
0x1800136a9  xor     r8d, r8d
0x1800136ac  lea     rcx, GUID_DEVCLASS_SCSIADAPTER
0x1800136b3  xor     edx, edx
0x1800136b5  call    cs:__imp_DevObjCreateDeviceInfoList
0x1800136bb  mov     rdi, rax
0x1800136be  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800136c2  jnz     short loc_180013718
0x1800136c4  call    cs:__imp_GetLastError
0x1800136ca  mov     ecx, 7FFFFFFEh
0x1800136cf  lea     r8, aFailedToCreate_0; "Failed to create DeviceInfoList"
0x1800136d6  mov     ebx, eax
0x1800136d8  mov     edx, 80h
0x1800136dd  lea     rax, [rbp+280h+var_2D0]
0x1800136e1  test    rcx, rcx
0x1800136e4  jz      short loc_180013704
0x1800136e6  movzx   r9d, word ptr [r8]
0x1800136ea  test    r9w, r9w
0x1800136ee  jz      short loc_180013704
0x1800136f0  mov     [rax], r9w
0x1800136f4  add     r8, 2
0x1800136f8  add     rax, 2
0x1800136fc  sub     rcx, r15
0x1800136ff  sub     rdx, r15
0x180013702  jnz     short loc_1800136E1
0x180013704  test    rdx, rdx
0x180013707  lea     rcx, [rax-2]
0x18001370b  cmovnz  rcx, rax
0x18001370f  mov     [rcx], r14w
0x180013713  jmp     loc_18001389C
0x180013718  lea     rax, [rsp+380h+var_330]
0x18001371d  xor     r9d, r9d
0x180013720  mov     [rsp+380h+var_358], rax
0x180013725  lea     r8, GUID_DEVCLASS_SCSIADAPTER
0x18001372c  lea     rdx, aIscsiprt; "ISCSIPRT"
0x180013733  mov     dword ptr [rsp+380h+var_360], r15d
0x180013738  mov     rcx, rdi
0x18001373b  call    cs:__imp_DevObjCreateDeviceInfo
0x180013741  test    eax, eax
0x180013743  jnz     short loc_18001378A
0x180013745  call    cs:__imp_GetLastError
0x18001374b  mov     ecx, 7FFFFFFEh
0x180013750  lea     r8, aFailedToCreate; "Failed to create DeviceInfo"
0x180013757  mov     ebx, eax
0x180013759  mov     edx, 80h
0x18001375e  lea     rax, [rbp+280h+var_2D0]
0x180013762  test    rcx, rcx
0x180013765  jz      short loc_180013704
0x180013767  movzx   r9d, word ptr [r8]
0x18001376b  test    r9w, r9w
0x18001376f  jz      short loc_180013704
0x180013771  mov     [rax], r9w
0x180013775  add     r8, 2
0x180013779  add     rax, 2
0x18001377d  sub     rcx, r15
0x180013780  sub     rdx, r15
0x180013783  jnz     short loc_180013762
0x180013785  jmp     loc_180013704
0x18001378a  lea     r9, aRootIscsiprt; "ROOT\\ISCSIPRT"
0x180013791  mov     dword ptr [rsp+380h+var_360], 1Eh
0x180013799  mov     r8d, r15d
0x18001379c  lea     rdx, [rsp+380h+var_330]
0x1800137a1  mov     rcx, rdi
0x1800137a4  call    cs:__imp_DevObjSetDeviceRegistryProperty
0x1800137aa  test    eax, eax
0x1800137ac  jnz     short loc_1800137FB
0x1800137ae  call    cs:__imp_GetLastError
0x1800137b4  mov     ecx, 7FFFFFFEh
0x1800137b9  lea     r8, aFailedToSetHar; "Failed to set hardware ID"
0x1800137c0  mov     ebx, eax
0x1800137c2  mov     edx, 80h
0x1800137c7  lea     rax, [rbp+280h+var_2D0]
0x1800137cb  test    rcx, rcx
0x1800137ce  jz      loc_180013704
0x1800137d4  movzx   r9d, word ptr [r8]
0x1800137d8  test    r9w, r9w
0x1800137dc  jz      loc_180013704
0x1800137e2  mov     [rax], r9w
0x1800137e6  add     r8, 2
0x1800137ea  add     rax, 2
0x1800137ee  sub     rcx, r15
0x1800137f1  sub     rdx, r15
0x1800137f4  jnz     short loc_1800137CB
0x1800137f6  jmp     loc_180013704
0x1800137fb  mov     [rsp+380h+var_358], r14
0x180013800  lea     rdx, [rsp+380h+var_330]
0x180013805  xor     r9d, r9d
0x180013808  mov     [rsp+380h+var_360], r14
0x18001380d  xor     r8d, r8d
0x180013810  mov     rcx, rdi
0x180013813  call    cs:__imp_DevObjRegisterDeviceInfo
0x180013819  test    eax, eax
0x18001381b  jnz     short loc_18001386A
0x18001381d  call    cs:__imp_GetLastError
0x180013823  mov     ecx, 7FFFFFFEh
0x180013828  lea     r8, aFailedToRegist; "Failed to register device"
0x18001382f  mov     ebx, eax
0x180013831  mov     edx, 80h
0x180013836  lea     rax, [rbp+280h+var_2D0]
0x18001383a  test    rcx, rcx
0x18001383d  jz      loc_180013704
0x180013843  movzx   r9d, word ptr [r8]
0x180013847  test    r9w, r9w
0x18001384b  jz      loc_180013704
0x180013851  mov     [rax], r9w
0x180013855  add     r8, 2
0x180013859  add     rax, 2
0x18001385d  sub     rcx, r15
0x180013860  sub     rdx, r15
0x180013863  jnz     short loc_18001383A
0x180013865  jmp     loc_180013704
0x18001386a  xor     r9d, r9d
0x18001386d  mov     [rsp+380h+var_340+4], r15
0x180013872  lea     r8, [rsp+380h+var_340]
0x180013877  mov     dword ptr [rsp+380h+var_340], 3
0x18001387f  lea     rdx, [rsp+380h+var_330]
0x180013884  mov     rcx, rdi
0x180013887  mov     ebx, r14d
0x18001388a  call    cs:__imp_DevObjChangeState
0x180013890  test    eax, eax
0x180013892  jnz     short loc_1800138D4
0x180013894  call    cs:__imp_GetLastError
0x18001389a  mov     ebx, eax
0x18001389c  test    ebx, ebx
0x18001389e  jz      short loc_1800138CE
0x1800138a0  lea     rcx, [rbp+280h+var_2D0]
0x1800138a4  movzx   r8d, r14w
0x1800138a8  mov     [rsp+380h+var_348], rcx
0x1800138ad  mov     r9d, ebx
0x1800138b0  mov     [rsp+380h+var_350], r15w
0x1800138b6  mov     edx, r15d
0x1800138b9  mov     [rsp+380h+var_358], r14
0x1800138be  mov     ecx, 7Bh ; '{'
0x1800138c3  mov     [rsp+380h+var_360], r14
0x1800138c8  call    cs:__imp_DiscpReportEventlogWithStatus
0x1800138ce  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800138d2  jz      short loc_1800138DD
0x1800138d4  mov     rcx, rdi
0x1800138d7  call    cs:__imp_DevObjDestroyDeviceInfoList
0x1800138dd  mov     eax, ebx
0x1800138df  mov     rcx, [rbp+280h+var_40]
0x1800138e6  xor     rcx, rsp; StackCookie
0x1800138e9  call    __security_check_cookie
0x1800138ee  add     rsp, 358h
0x1800138f5  pop     r15
0x1800138f7  pop     r14
0x1800138f9  pop     rdi
0x1800138fa  pop     rsi
0x1800138fb  pop     rbx
0x1800138fc  pop     rbp
0x1800138fd  retn
```
