# CMapsToastTaskHandler::GetAppDisplayName(ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x1800038e4`
- end: `0x180003af8`
- name: `?GetAppDisplayName@CMapsToastTaskHandler@@AEAAJKPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `532`
- prototype: `__int64 __fastcall(const void *, DWORD, char **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180005e60`

## callees

- `0x1800015b0`
- `0x1800020a4`
- `0x1800038e4`
- `0x1800094e0`
- `0x18000954c`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOrigination` at `0x180003984`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180003984`
- `USERENV!__imp_LookupAppContainerDisplayName` at `0x180003a2e`
- `USERENV!__imp_LookupAppContainerDisplayName` at `0x180003a2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003a0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003a9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003a0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003a9c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800039d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800039d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003957`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003957`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039c4`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180003944`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180003944`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003acf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003acf`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFullName` at `0x18000399e`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFullName` at `0x18000399e`
- `api-ms-win-appmodel-identity-l1-2-0!AppXFreeMemory` at `0x1800039cf`
- `api-ms-win-appmodel-identity-l1-2-0!AppXFreeMemory` at `0x180003abb`
- `api-ms-win-appmodel-identity-l1-2-0!AppXFreeMemory` at `0x1800039cf`
- `api-ms-win-appmodel-identity-l1-2-0!AppXFreeMemory` at `0x180003abb`
- `api-ms-win-appmodel-identity-l1-2-0!AppXGetPackageSid` at `0x1800039ec`
- `api-ms-win-appmodel-identity-l1-2-0!AppXGetPackageSid` at `0x1800039ec`

## string_xrefs

- `0x18000397b`: `CMapsToastTaskHandler::GetAppDisplayName`

## pseudocode

```c
__int64 __fastcall CMapsToastTaskHandler::GetAppDisplayName(const void *a1, DWORD a2, char **a3)
{
  char *v5; // rax
  char *v6; // r15
  int LastError; // eax
  int v8; // r8d
  unsigned int v9; // edi
  unsigned __int64 v10; // rbx
  __int64 v11; // r8
  const void *v12; // r9
  char *v13; // r14
  size_t v14; // rbx
  __int64 v16; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v18; // [rsp+30h] [rbp-D0h]
  __int64 v19; // [rsp+38h] [rbp-C8h]
  UINT32 packageFullNameLength; // [rsp+40h] [rbp-C0h] BYREF
  char *v21; // [rsp+48h] [rbp-B8h]
  WCHAR packageFullName[2048]; // [rsp+50h] [rbp-B0h] BYREF

  packageFullNameLength = 2048;
  v16 = 0;
  pv = 0;
  v18 = 0;
  v19 = 0;
  v5 = (char *)OpenProcess(0x1000u, 0, a2);
  v6 = v5;
  v21 = v5;
  if ( !v5 )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2143748092;
    }
    v8 = 294;
    goto LABEL_7;
  }
  LastError = GetPackageFullName(v5, &packageFullNameLength, packageFullName);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v8 = 296;
    goto LABEL_7;
  }
  v16 = 0;
  LastError = AppXGetPackageSid(packageFullName, &v16);
  if ( LastError < 0 )
  {
    v8 = 297;
LABEL_7:
    v9 = ZTraceReportOrigination(LastError, "CMapsToastTaskHandler::GetAppDisplayName", v8, a1);
    goto LABEL_26;
  }
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  v10 = -1;
  v18 = -1;
  v19 = -1;
  LastError = LookupAppContainerDisplayName(v16, &pv);
  if ( LastError < 0 )
  {
    v8 = 298;
    goto LABEL_7;
  }
  v9 = 0;
  v12 = pv;
  do
    ++v10;
  while ( *((_WORD *)pv + v10) );
  if ( v10 > (unsigned __int64)a3[3] )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(a3, v10, v11, pv);
  }
  else
  {
    if ( (unsigned __int64)a3[3] <= 7 )
      v13 = (char *)a3;
    else
      v13 = *a3;
    a3[2] = (char *)v10;
    v14 = 2 * v10;
    memmove_0(v13, v12, v14);
    *(_WORD *)&v13[v14] = 0;
  }
LABEL_26:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  v18 = 0;
  v19 = 0;
  if ( v16 )
    AppXFreeMemory(v16);
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
  return v9;
}

```

## disassembly

```asm
0x1800038e4  push    rbp
0x1800038e6  push    rbx
0x1800038e7  push    rsi
0x1800038e8  push    rdi
0x1800038e9  push    r12
0x1800038eb  push    r14
0x1800038ed  push    r15
0x1800038ef  lea     rbp, [rsp-0F60h]
0x1800038f7  mov     eax, 1060h
0x1800038fc  call    _alloca_probe
0x180003901  sub     rsp, rax
0x180003904  mov     rax, cs:__security_cookie
0x18000390b  xor     rax, rsp
0x18000390e  mov     [rbp+0F90h+var_40], rax
0x180003915  mov     rsi, r8
0x180003918  mov     r14, rcx
0x18000391b  mov     [rsp+1090h+packageFullNameLength], 800h
0x180003923  xor     r12d, r12d
0x180003926  mov     [rsp+1090h+var_1070], r12
0x18000392b  mov     [rsp+1090h+pv], r12
0x180003930  mov     [rsp+1090h+var_1060], r12
0x180003935  mov     [rsp+1090h+var_1058], r12
0x18000393a  mov     r8d, edx; dwProcessId
0x18000393d  xor     edx, edx; bInheritHandle
0x18000393f  mov     ecx, 1000h; dwDesiredAccess
0x180003944  call    cs:__imp_OpenProcess
0x18000394a  mov     r15, rax
0x18000394d  mov     [rsp+1090h+var_1048], rax
0x180003952  test    rax, rax
0x180003955  jnz     short loc_180003991
0x180003957  call    cs:__imp_GetLastError
0x18000395d  test    eax, eax
0x18000395f  jz      short loc_18000396D
0x180003961  jle     short loc_180003972
0x180003963  movzx   eax, ax
0x180003966  or      eax, 80070000h
0x18000396b  jmp     short loc_180003972
0x18000396d  mov     eax, 80390004h
0x180003972  mov     r8d, 126h
0x180003978  mov     r9, r14
0x18000397b  lea     rdx, aCmapstoasttask_2; "CMapsToastTaskHandler::GetAppDisplayNam"...
0x180003982  mov     ecx, eax
0x180003984  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18000398a  mov     edi, eax
0x18000398c  jmp     loc_180003A92
0x180003991  lea     r8, [rsp+1090h+packageFullName]; packageFullName
0x180003996  lea     rdx, [rsp+1090h+packageFullNameLength]; packageFullNameLength
0x18000399b  mov     rcx, r15; hProcess
0x18000399e  call    cs:__imp_GetPackageFullName
0x1800039a4  test    eax, eax
0x1800039a6  jz      short loc_1800039BA
0x1800039a8  jle     short loc_1800039B2
0x1800039aa  movzx   eax, ax
0x1800039ad  or      eax, 80070000h
0x1800039b2  mov     r8d, 128h
0x1800039b8  jmp     short loc_180003978
0x1800039ba  mov     rdi, [rsp+1090h+var_1070]
0x1800039bf  test    rdi, rdi
0x1800039c2  jz      short loc_1800039DD
0x1800039c4  call    cs:__imp_GetLastError
0x1800039ca  mov     ebx, eax
0x1800039cc  mov     rcx, rdi
0x1800039cf  call    cs:__imp_AppXFreeMemory
0x1800039d5  mov     ecx, ebx; dwErrCode
0x1800039d7  call    cs:__imp_SetLastError
0x1800039dd  mov     [rsp+1090h+var_1070], r12
0x1800039e2  lea     rdx, [rsp+1090h+var_1070]
0x1800039e7  lea     rcx, [rsp+1090h+packageFullName]
0x1800039ec  call    cs:__imp_AppXGetPackageSid
0x1800039f2  test    eax, eax
0x1800039f4  jns     short loc_180003A01
0x1800039f6  mov     r8d, 129h
0x1800039fc  jmp     loc_180003978
0x180003a01  mov     rcx, [rsp+1090h+pv]; pv
0x180003a06  test    rcx, rcx
0x180003a09  jz      short loc_180003A16
0x180003a0b  call    cs:__imp_CoTaskMemFree
0x180003a11  mov     [rsp+1090h+pv], r12
0x180003a16  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180003a1a  mov     [rsp+1090h+var_1060], rbx
0x180003a1f  mov     [rsp+1090h+var_1058], rbx
0x180003a24  lea     rdx, [rsp+1090h+pv]
0x180003a29  mov     rcx, [rsp+1090h+var_1070]
0x180003a2e  call    cs:__imp_LookupAppContainerDisplayName
0x180003a34  test    eax, eax
0x180003a36  jns     short loc_180003A43
0x180003a38  mov     r8d, 12Ah
0x180003a3e  jmp     loc_180003978
0x180003a43  mov     edi, r12d
0x180003a46  mov     r9, [rsp+1090h+pv]
0x180003a4b  inc     rbx
0x180003a4e  cmp     [r9+rbx*2], r12w
0x180003a53  jnz     short loc_180003A4B
0x180003a55  cmp     rbx, [rsi+18h]
0x180003a59  ja      short loc_180003A86
0x180003a5b  cmp     qword ptr [rsi+18h], 7
0x180003a60  jbe     short loc_180003A67
0x180003a62  mov     r14, [rsi]
0x180003a65  jmp     short loc_180003A6A
0x180003a67  mov     r14, rsi
0x180003a6a  mov     [rsi+10h], rbx
0x180003a6e  add     rbx, rbx
0x180003a71  mov     r8, rbx; Size
0x180003a74  mov     rdx, r9; Src
0x180003a77  mov     rcx, r14; void *
0x180003a7a  call    memmove_0
0x180003a7f  mov     [rbx+r14], r12w
0x180003a84  jmp     short loc_180003A92
0x180003a86  mov     rdx, rbx
0x180003a89  mov     rcx, rsi
0x180003a8c  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180003a91  nop
0x180003a92  mov     rcx, [rsp+1090h+pv]; pv
0x180003a97  test    rcx, rcx
0x180003a9a  jz      short loc_180003AA7
0x180003a9c  call    cs:__imp_CoTaskMemFree
0x180003aa2  mov     [rsp+1090h+pv], r12
0x180003aa7  mov     [rsp+1090h+var_1060], r12
0x180003aac  mov     [rsp+1090h+var_1058], r12
0x180003ab1  mov     rcx, [rsp+1090h+var_1070]
0x180003ab6  test    rcx, rcx
0x180003ab9  jz      short loc_180003AC2
0x180003abb  call    cs:__imp_AppXFreeMemory
0x180003ac1  nop
0x180003ac2  lea     rax, [r15-1]
0x180003ac6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003aca  ja      short loc_180003AD5
0x180003acc  mov     rcx, r15; hObject
0x180003acf  call    cs:__imp_CloseHandle
0x180003ad5  mov     eax, edi
0x180003ad7  mov     rcx, [rbp+0F90h+var_40]
0x180003ade  xor     rcx, rsp; StackCookie
0x180003ae1  call    __security_check_cookie
0x180003ae6  add     rsp, 1060h
0x180003aed  pop     r15
0x180003aef  pop     r14
0x180003af1  pop     r12
0x180003af3  pop     rdi
0x180003af4  pop     rsi
0x180003af5  pop     rbx
0x180003af6  pop     rbp
0x180003af7  retn
```
