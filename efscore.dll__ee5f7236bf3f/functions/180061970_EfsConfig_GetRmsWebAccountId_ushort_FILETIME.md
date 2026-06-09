# EfsConfig_GetRmsWebAccountId(ushort * *,_FILETIME *)

- ea: `0x180061970`
- end: `0x180061bae`
- name: `?EfsConfig_GetRmsWebAccountId@@YAJPEAPEAGPEAU_FILETIME@@@Z`
- size: `574`
- prototype: `__int64 __fastcall(unsigned __int16 **, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006c764`

## callees

- `0x18000b12c`
- `0x18000dc8c`
- `0x18000ef44`
- `0x180045f68`
- `0x18004d12c`
- `0x180061748`
- `0x180061970`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800619b1`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800619b1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180061a24`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180061aba`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180061b39`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180061a24`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180061aba`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180061b39`

## string_xrefs

- `0x180061b27`: `AccountIdLastWriteTime`
- `0x1800619cd`: `onecoreuap\ds\security\efs\common\lib\efsenv.cxx`
- `0x180061a60`: `onecoreuap\ds\security\efs\common\lib\efsenv.cxx`
- `0x180061acb`: `onecoreuap\ds\security\efs\common\lib\efsenv.cxx`
- `0x180061b4a`: `onecoreuap\ds\security\efs\common\lib\efsenv.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EfsConfig_GetRmsWebAccountId(unsigned __int16 **a1, struct _FILETIME *a2)
{
  unsigned int v4; // ebx
  unsigned int v5; // ebx
  unsigned __int16 *v7; // rbx
  __int64 v8; // rdx
  unsigned int ValueW; // eax
  __int64 v10; // rdx
  unsigned int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rdx
  unsigned int pdwType; // [rsp+20h] [rbp-50h]
  int pdwTypea; // [rsp+20h] [rbp-50h]
  unsigned int pdwTypeb; // [rsp+20h] [rbp-50h]
  unsigned int pdwTypec; // [rsp+20h] [rbp-50h]
  PVOID pvData; // [rsp+40h] [rbp-30h] BYREF
  struct _FILETIME v19; // [rsp+48h] [rbp-28h] BYREF
  HKEY *p_hkey; // [rsp+50h] [rbp-20h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-18h] BYREF
  char v22; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  DWORD pcbData; // [rsp+A0h] [rbp+30h] BYREF
  HKEY hkey; // [rsp+A8h] [rbp+38h] BYREF

  pcbData = 0;
  hkey = 0;
  p_hkey = &hkey;
  phkResult = 0;
  v22 = 1;
  v4 = RegOpenCurrentUser(0x20019u, &phkResult);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hkey);
  if ( v4 )
  {
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x268,
           (unsigned int)"onecoreuap\\ds\\security\\efs\\common\\lib\\efsenv.cxx",
           (const char *)v4,
           pdwType);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    return v5;
  }
  if ( !RegGetValueW(
          hkey,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\EFS\\RMS",
          L"AccountId",
          2u,
          0,
          0,
          &pcbData)
    && pcbData )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &pvData,
      0,
      pcbData);
    v7 = (unsigned __int16 *)pvData;
    if ( !pvData )
    {
      v5 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x273,
        (unsigned int)"onecoreuap\\ds\\security\\efs\\common\\lib\\efsenv.cxx",
        (const char *)0x8007000ELL,
        pdwTypea);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(
        &pvData,
        v8);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      return v5;
    }
    ValueW = RegGetValueW(
               hkey,
               L"Software\\Microsoft\\Windows NT\\CurrentVersion\\EFS\\RMS",
               L"AccountId",
               2u,
               0,
               pvData,
               &pcbData);
    if ( ValueW )
    {
      v5 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x27B,
             (unsigned int)"onecoreuap\\ds\\security\\efs\\common\\lib\\efsenv.cxx",
             (const char *)ValueW,
             pdwTypeb);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(
        &pvData,
        v10);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      return v5;
    }
    v19 = 0;
    pcbData = 8;
    v11 = RegGetValueW(
            hkey,
            L"Software\\Microsoft\\Windows NT\\CurrentVersion\\EFS\\RMS",
            L"AccountIdLastWriteTime",
            0x40u,
            0,
            &v19,
            &pcbData);
    if ( v11 )
    {
      v5 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x285,
             (unsigned int)"onecoreuap\\ds\\security\\efs\\common\\lib\\efsenv.cxx",
             (const char *)v11,
             pdwTypec);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(
        &pvData,
        v13);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      return v5;
    }
    *a2 = v19;
    pvData = 0;
    *a1 = v7;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(
      &pvData,
      v12);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  return 0;
}

```

## disassembly

```asm
0x180061970  mov     [rsp-18h+arg_0], rbx
0x180061975  push    rbp
0x180061976  push    rsi
0x180061977  push    rdi
0x180061978  mov     rbp, rsp
0x18006197b  sub     rsp, 70h
0x18006197f  mov     rdi, rdx
0x180061982  mov     rsi, rcx
0x180061985  mov     [rbp+arg_10], 0
0x18006198c  mov     [rbp+hkey], 0
0x180061994  lea     rax, [rbp+hkey]
0x180061998  mov     [rbp+var_20], rax
0x18006199c  mov     [rbp+phkResult], 0
0x1800619a4  mov     [rbp+var_10], 1
0x1800619a8  lea     rdx, [rbp+phkResult]; phkResult
0x1800619ac  mov     ecx, 20019h; samDesired
0x1800619b1  call    cs:__imp_RegOpenCurrentUser
0x1800619b7  mov     ebx, eax
0x1800619b9  lea     rcx, [rbp+var_20]
0x1800619bd  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800619c2  test    ebx, ebx
0x1800619c4  jz      short loc_1800619F1
0x1800619c6  mov     rcx, [rbp+18h]; this
0x1800619ca  mov     r9d, ebx; char *
0x1800619cd  lea     r8, aOnecoreuapDsSe_6; "onecoreuap\\ds\\security\\efs\\common\\"...
0x1800619d4  mov     edx, 268h; void *
0x1800619d9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800619de  mov     ebx, eax
0x1800619e0  lea     rcx, [rbp+hkey]
0x1800619e4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800619e9  nop
0x1800619ea  mov     eax, ebx
0x1800619ec  jmp     loc_180061B9E
0x1800619f1  lea     rax, [rbp+arg_10]
0x1800619f5  mov     [rsp+70h+pcbData], rax; pcbData
0x1800619fa  mov     [rsp+70h+pvData], 0; pvData
0x180061a03  mov     [rsp+70h+pdwType], 0; int
0x180061a0c  mov     r9d, 2; dwFlags
0x180061a12  lea     r8, aAccountid; "AccountId"
0x180061a19  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows NT\\Curren"...
0x180061a20  mov     rcx, [rbp+hkey]; hkey
0x180061a24  call    cs:__imp_RegGetValueW
0x180061a2a  test    eax, eax
0x180061a2c  jnz     loc_180061B92
0x180061a32  mov     eax, [rbp+arg_10]
0x180061a35  test    eax, eax
0x180061a37  jz      loc_180061B92
0x180061a3d  mov     r8d, eax
0x180061a40  xor     edx, edx
0x180061a42  lea     rcx, [rbp+var_30]
0x180061a46  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180061a4b  mov     rbx, [rbp+var_30]
0x180061a4f  test    rbx, rbx
0x180061a52  jnz     short loc_180061A8B
0x180061a54  mov     rcx, [rbp+18h]; this
0x180061a58  mov     ebx, 8007000Eh
0x180061a5d  mov     r9d, ebx; char *
0x180061a60  lea     r8, aOnecoreuapDsSe_6; "onecoreuap\\ds\\security\\efs\\common\\"...
0x180061a67  mov     edx, 273h; void *
0x180061a6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180061a71  nop
0x180061a72  lea     rcx, [rbp+var_30]
0x180061a76  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180061a7b  nop
0x180061a7c  lea     rcx, [rbp+hkey]
0x180061a80  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180061a85  nop
0x180061a86  jmp     loc_1800619EA
0x180061a8b  lea     rax, [rbp+arg_10]
0x180061a8f  mov     [rsp+70h+pcbData], rax; pcbData
0x180061a94  mov     [rsp+70h+pvData], rbx; pvData
0x180061a99  mov     [rsp+70h+pdwType], 0; unsigned int
0x180061aa2  mov     r9d, 2; dwFlags
0x180061aa8  lea     r8, aAccountid; "AccountId"
0x180061aaf  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows NT\\Curren"...
0x180061ab6  mov     rcx, [rbp+hkey]; hkey
0x180061aba  call    cs:__imp_RegGetValueW
0x180061ac0  test    eax, eax
0x180061ac2  jz      short loc_180061AF7
0x180061ac4  mov     rcx, [rbp+18h]; this
0x180061ac8  mov     r9d, eax; char *
0x180061acb  lea     r8, aOnecoreuapDsSe_6; "onecoreuap\\ds\\security\\efs\\common\\"...
0x180061ad2  mov     edx, 27Bh; void *
0x180061ad7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180061adc  mov     ebx, eax
0x180061ade  lea     rcx, [rbp+var_30]
0x180061ae2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180061ae7  nop
0x180061ae8  lea     rcx, [rbp+hkey]
0x180061aec  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180061af1  nop
0x180061af2  jmp     loc_1800619EA
0x180061af7  mov     [rbp+var_28], 0
0x180061aff  mov     [rbp+arg_10], 8
0x180061b06  lea     rax, [rbp+arg_10]
0x180061b0a  mov     [rsp+70h+pcbData], rax; pcbData
0x180061b0f  lea     rax, [rbp+var_28]
0x180061b13  mov     [rsp+70h+pvData], rax; pvData
0x180061b18  mov     [rsp+70h+pdwType], 0; unsigned int
0x180061b21  mov     r9d, 40h ; '@'; dwFlags
0x180061b27  lea     r8, aAccountidlastw; "AccountIdLastWriteTime"
0x180061b2e  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows NT\\Curren"...
0x180061b35  mov     rcx, [rbp+hkey]; hkey
0x180061b39  call    cs:__imp_RegGetValueW
0x180061b3f  test    eax, eax
0x180061b41  jz      short loc_180061B76
0x180061b43  mov     rcx, [rbp+18h]; this
0x180061b47  mov     r9d, eax; char *
0x180061b4a  lea     r8, aOnecoreuapDsSe_6; "onecoreuap\\ds\\security\\efs\\common\\"...
0x180061b51  mov     edx, 285h; void *
0x180061b56  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180061b5b  mov     ebx, eax
0x180061b5d  lea     rcx, [rbp+var_30]
0x180061b61  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180061b66  nop
0x180061b67  lea     rcx, [rbp+hkey]
0x180061b6b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180061b70  nop
0x180061b71  jmp     loc_1800619EA
0x180061b76  mov     rax, [rbp+var_28]
0x180061b7a  mov     [rdi], rax
0x180061b7d  mov     [rbp+var_30], 0
0x180061b85  mov     [rsi], rbx
0x180061b88  lea     rcx, [rbp+var_30]
0x180061b8c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180061b91  nop
0x180061b92  lea     rcx, [rbp+hkey]
0x180061b96  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180061b9b  nop
0x180061b9c  xor     eax, eax
0x180061b9e  mov     rbx, [rsp+70h+arg_0]
0x180061ba6  add     rsp, 70h
0x180061baa  pop     rdi
0x180061bab  pop     rsi
0x180061bac  pop     rbp
0x180061bad  retn
```
