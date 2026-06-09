# CAppImport::UpdateNTServiceSettings(ISimpleTableRead *)

- ea: `0x180040ecc`
- end: `0x180041219`
- name: `?UpdateNTServiceSettings@CAppImport@@AEAAJPEAUISimpleTableRead@@@Z`
- size: `845`
- prototype: `__int64 __fastcall(CAppImport *__hidden this, struct ISimpleTableRead *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003e730`

## callees

- `0x18001a6c8`
- `0x180040ecc`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800410f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041127`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041185`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800410f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041127`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041185`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800411e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800411e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004103b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004103b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800411ac`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800411f1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800411ff`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800411ac`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800411f1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800411ff`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800410de`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800410de`
- `api-ms-win-service-management-l1-1-0!DeleteService` at `0x1800411d5`
- `api-ms-win-service-management-l1-1-0!DeleteService` at `0x1800411d5`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180041119`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800411c4`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180041119`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800411c4`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18004117b`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18004117b`

## pseudocode

```c
__int64 __fastcall CAppImport::UpdateNTServiceSettings(const WCHAR *this, struct ISimpleTableRead *a2)
{
  __int64 v2; // rax
  __int64 (__fastcall *v4)(struct ISimpleTableRead *, __int64, _QWORD, _QWORD, _DWORD **); // rax
  SC_HANDLE v5; // rsi
  SC_HANDLE v6; // rdi
  WCHAR *lpDependencies; // r15
  signed int v8; // ebx
  unsigned __int16 *v9; // rbx
  SIZE_T v10; // rax
  WCHAR *v11; // rax
  WCHAR *i; // rdx
  unsigned __int16 v13; // ax
  unsigned __int16 v14; // cx
  signed int LastError; // eax
  signed int v16; // eax
  signed int v17; // eax
  const WCHAR *v18; // rdx
  SC_HANDLE v19; // rax
  DWORD *v21; // [rsp+60h] [rbp-20h] BYREF
  DWORD *v22; // [rsp+68h] [rbp-18h] BYREF
  DWORD *v23; // [rsp+70h] [rbp-10h]
  LPCWSTR lpServiceName; // [rsp+C0h] [rbp+40h] BYREF
  _DWORD *v25; // [rsp+C8h] [rbp+48h] BYREF
  unsigned __int16 *v26; // [rsp+D0h] [rbp+50h] BYREF
  LPCWSTR lpLoadOrderGroup; // [rsp+D8h] [rbp+58h]

  lpServiceName = this;
  v2 = *(_QWORD *)a2;
  lpServiceName = 0;
  v25 = 0;
  v4 = *(__int64 (__fastcall **)(struct ISimpleTableRead *, __int64, _QWORD, _QWORD, _DWORD **))(v2 + 64);
  v22 = 0;
  v21 = 0;
  v5 = 0;
  v23 = 0;
  v6 = 0;
  v26 = 0;
  lpDependencies = 0;
  lpLoadOrderGroup = 0;
  v8 = v4(a2, 33, 0, 0, &v25);
  if ( v8 < 0 )
    goto LABEL_30;
  if ( *v25 )
    return (unsigned int)v8;
  v8 = (*(__int64 (__fastcall **)(struct ISimpleTableRead *, __int64, _QWORD, _QWORD, LPCWSTR *))(*(_QWORD *)a2 + 64LL))(
         a2,
         6,
         0,
         0,
         &lpServiceName);
  if ( v8 < 0 )
    goto LABEL_30;
  if ( !lpServiceName || !*lpServiceName )
    return (unsigned int)v8;
  v8 = (*(__int64 (__fastcall **)(struct ISimpleTableRead *, __int64, _QWORD, _QWORD, DWORD **))(*(_QWORD *)a2 + 64LL))(
         a2,
         58,
         0,
         0,
         &v22);
  if ( v8 < 0 )
    goto LABEL_30;
  v8 = (*(__int64 (__fastcall **)(struct ISimpleTableRead *, __int64, _QWORD, _QWORD, DWORD **))(*(_QWORD *)a2 + 64LL))(
         a2,
         59,
         0,
         0,
         &v21);
  if ( v8 < 0 )
    goto LABEL_30;
  v8 = (*(__int64 (__fastcall **)(struct ISimpleTableRead *, __int64, _QWORD, _QWORD, unsigned __int16 **))(*(_QWORD *)a2 + 64LL))(
         a2,
         60,
         0,
         0,
         &v26);
  if ( v8 < 0 )
    goto LABEL_30;
  v9 = v26;
  v10 = saturated_mul((int)(safe_lstrlenW(v26) + 2), 2u);
  v11 = (WCHAR *)CoTaskMemAlloc(v10);
  lpDependencies = v11;
  if ( !v11 )
  {
    lpDependencies = 0;
    v8 = -2147024882;
    goto LABEL_30;
  }
  for ( i = v11; ; ++i )
  {
    v14 = *v9;
    if ( !*v9 )
      break;
    ++v9;
    v13 = 0;
    if ( v14 != 92 )
      v13 = v14;
    *i = v13;
  }
  *(_DWORD *)i = 0;
  v8 = (*(__int64 (__fastcall **)(struct ISimpleTableRead *, __int64, _QWORD))(*(_QWORD *)a2 + 64LL))(a2, 61, 0);
  if ( v8 < 0 )
    goto LABEL_30;
  v8 = (*(__int64 (__fastcall **)(struct ISimpleTableRead *, __int64, _QWORD))(*(_QWORD *)a2 + 64LL))(a2, 62, 0);
  if ( v8 < 0 )
    goto LABEL_30;
  v5 = OpenSCManagerW(0, 0, 0x80000000);
  if ( !v5 )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 < 0 )
      goto LABEL_30;
  }
  v6 = OpenServiceW(v5, lpServiceName, 2u);
  if ( !v6 )
  {
    v16 = GetLastError();
    v8 = v16;
    if ( v16 > 0 )
      v8 = (unsigned __int16)v16 | 0x80070000;
    if ( v8 < 0 )
      goto LABEL_30;
  }
  if ( !ChangeServiceConfigW(v6, *v23, *v22, *v21, 0, lpLoadOrderGroup, 0, lpDependencies, 0, 0, 0) )
  {
    v17 = GetLastError();
    v8 = v17;
    if ( v17 > 0 )
      v8 = (unsigned __int16)v17 | 0x80070000;
    if ( v8 < 0 )
    {
LABEL_30:
      v18 = lpServiceName;
      if ( lpServiceName )
      {
        if ( v6 )
        {
          CloseServiceHandle(v6);
          v18 = lpServiceName;
        }
        if ( v5 )
        {
          v19 = OpenServiceW(v5, v18, 0x10000u);
          v6 = v19;
          if ( v19 )
            DeleteService(v19);
        }
      }
      if ( !lpDependencies )
        goto LABEL_38;
    }
  }
  CoTaskMemFree(lpDependencies);
LABEL_38:
  if ( v5 )
    CloseServiceHandle(v5);
  if ( v6 )
    CloseServiceHandle(v6);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180040ecc  mov     [rsp-38h+lpServiceName], rcx
0x180040ed1  push    rbp
0x180040ed2  push    rbx
0x180040ed3  push    rsi
0x180040ed4  push    rdi
0x180040ed5  push    r12
0x180040ed7  push    r14
0x180040ed9  push    r15
0x180040edb  mov     rbp, rsp
0x180040ede  sub     rsp, 80h
0x180040ee5  mov     rax, [rdx]
0x180040ee8  lea     rcx, [rbp+arg_8]
0x180040eec  xor     r12d, r12d
0x180040eef  mov     [rsp+80h+lpBinaryPathName], rcx
0x180040ef4  mov     r14, rdx
0x180040ef7  mov     [rbp+lpServiceName], r12
0x180040efb  xor     r9d, r9d
0x180040efe  mov     [rbp+arg_8], r12
0x180040f02  mov     rax, [rax+40h]
0x180040f06  xor     r8d, r8d
0x180040f09  lea     edx, [r12+21h]
0x180040f0e  mov     [rbp+var_18], r12
0x180040f12  mov     rcx, r14
0x180040f15  mov     [rbp+var_20], r12
0x180040f19  mov     esi, r12d
0x180040f1c  mov     [rbp+var_10], r12
0x180040f20  mov     edi, r12d
0x180040f23  mov     [rbp+arg_10], r12
0x180040f27  mov     r15d, r12d
0x180040f2a  mov     [rbp+arg_18], r12
0x180040f2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040f33  mov     ebx, eax
0x180040f35  test    eax, eax
0x180040f37  js      loc_18004119B
0x180040f3d  mov     rax, [rbp+arg_8]
0x180040f41  cmp     [rax], r12d
0x180040f44  jnz     loc_180041205
0x180040f4a  mov     rax, [r14]
0x180040f4d  lea     rcx, [rbp+lpServiceName]
0x180040f51  mov     [rsp+80h+lpBinaryPathName], rcx
0x180040f56  lea     edx, [r12+6]
0x180040f5b  xor     r9d, r9d
0x180040f5e  xor     r8d, r8d
0x180040f61  mov     rcx, r14
0x180040f64  mov     rax, [rax+40h]
0x180040f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040f6d  mov     ebx, eax
0x180040f6f  test    eax, eax
0x180040f71  js      loc_18004119B
0x180040f77  mov     rax, [rbp+lpServiceName]
0x180040f7b  test    rax, rax
0x180040f7e  jz      loc_180041205
0x180040f84  cmp     [rax], r12w
0x180040f88  jz      loc_180041205
0x180040f8e  mov     rax, [r14]
0x180040f91  lea     rcx, [rbp+var_18]
0x180040f95  mov     [rsp+80h+lpBinaryPathName], rcx
0x180040f9a  lea     edx, [r12+3Ah]
0x180040f9f  xor     r9d, r9d
0x180040fa2  xor     r8d, r8d
0x180040fa5  mov     rcx, r14
0x180040fa8  mov     rax, [rax+40h]
0x180040fac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040fb1  mov     ebx, eax
0x180040fb3  test    eax, eax
0x180040fb5  js      loc_18004119B
0x180040fbb  mov     rax, [r14]
0x180040fbe  lea     rcx, [rbp+var_20]
0x180040fc2  mov     [rsp+80h+lpBinaryPathName], rcx
0x180040fc7  lea     edx, [r12+3Bh]
0x180040fcc  xor     r9d, r9d
0x180040fcf  xor     r8d, r8d
0x180040fd2  mov     rcx, r14
0x180040fd5  mov     rax, [rax+40h]
0x180040fd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040fde  mov     ebx, eax
0x180040fe0  test    eax, eax
0x180040fe2  js      loc_18004119B
0x180040fe8  mov     rax, [r14]
0x180040feb  lea     rcx, [rbp+arg_10]
0x180040fef  mov     [rsp+80h+lpBinaryPathName], rcx
0x180040ff4  lea     edx, [r12+3Ch]
0x180040ff9  xor     r9d, r9d
0x180040ffc  xor     r8d, r8d
0x180040fff  mov     rcx, r14
0x180041002  mov     rax, [rax+40h]
0x180041006  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004100b  mov     ebx, eax
0x18004100d  test    eax, eax
0x18004100f  js      loc_18004119B
0x180041015  mov     rbx, [rbp+arg_10]
0x180041019  mov     rcx, rbx; unsigned __int16 *
0x18004101c  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180041021  add     eax, 2
0x180041024  movsxd  rcx, eax
0x180041027  lea     eax, [r12+2]
0x18004102c  mul     rcx
0x18004102f  lea     rcx, [r12-1]
0x180041034  cmovb   rax, rcx
0x180041038  mov     rcx, rax; cb
0x18004103b  call    cs:__imp_CoTaskMemAlloc
0x180041041  mov     r15, rax
0x180041044  test    rax, rax
0x180041047  jnz     short loc_180041056
0x180041049  mov     r15d, r12d
0x18004104c  mov     ebx, 8007000Eh
0x180041051  jmp     loc_18004119B
0x180041056  mov     rdx, r15
0x180041059  jmp     short loc_180041071
0x18004105b  cmp     cx, 5Ch ; '\'
0x18004105f  lea     rbx, [rbx+2]
0x180041063  mov     eax, r12d
0x180041066  cmovnz  ax, cx
0x18004106a  mov     [rdx], ax
0x18004106d  add     rdx, 2
0x180041071  movzx   ecx, word ptr [rbx]
0x180041074  test    cx, cx
0x180041077  jnz     short loc_18004105B
0x180041079  mov     [rdx], r12d
0x18004107c  lea     rcx, [rbp+arg_18]
0x180041080  mov     rax, [r14]
0x180041083  xor     r9d, r9d
0x180041086  mov     [rsp+80h+lpBinaryPathName], rcx
0x18004108b  xor     r8d, r8d
0x18004108e  mov     rcx, r14
0x180041091  mov     rax, [rax+40h]
0x180041095  lea     edx, [r9+3Dh]
0x180041099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004109e  mov     ebx, eax
0x1800410a0  test    eax, eax
0x1800410a2  js      loc_18004119B
0x1800410a8  mov     rax, [r14]
0x1800410ab  lea     rcx, [rbp+var_10]
0x1800410af  xor     r9d, r9d
0x1800410b2  mov     [rsp+80h+lpBinaryPathName], rcx
0x1800410b7  xor     r8d, r8d
0x1800410ba  mov     rcx, r14
0x1800410bd  mov     rax, [rax+40h]
0x1800410c1  lea     edx, [r9+3Eh]
0x1800410c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800410ca  mov     ebx, eax
0x1800410cc  test    eax, eax
0x1800410ce  js      loc_18004119B
0x1800410d4  xor     edx, edx; lpDatabaseName
0x1800410d6  xor     ecx, ecx; lpMachineName
0x1800410d8  mov     r8d, 80000000h; dwDesiredAccess
0x1800410de  call    cs:__imp_OpenSCManagerW
0x1800410e4  mov     rsi, rax
0x1800410e7  mov     r14d, 80070000h
0x1800410ed  test    rax, rax
0x1800410f0  jnz     short loc_18004110C
0x1800410f2  call    cs:__imp_GetLastError
0x1800410f8  mov     ebx, eax
0x1800410fa  test    eax, eax
0x1800410fc  jle     short loc_180041104
0x1800410fe  movzx   ebx, ax
0x180041101  or      ebx, r14d
0x180041104  test    ebx, ebx
0x180041106  js      loc_18004119B
0x18004110c  mov     rdx, [rbp+lpServiceName]; lpServiceName
0x180041110  mov     r8d, 2; dwDesiredAccess
0x180041116  mov     rcx, rsi; hSCManager
0x180041119  call    cs:__imp_OpenServiceW
0x18004111f  mov     rdi, rax
0x180041122  test    rax, rax
0x180041125  jnz     short loc_18004113D
0x180041127  call    cs:__imp_GetLastError
0x18004112d  mov     ebx, eax
0x18004112f  test    eax, eax
0x180041131  jle     short loc_180041139
0x180041133  movzx   ebx, ax
0x180041136  or      ebx, r14d
0x180041139  test    ebx, ebx
0x18004113b  js      short loc_18004119B
0x18004113d  mov     r9, [rbp+var_20]
0x180041141  mov     rcx, rdi; hService
0x180041144  mov     r8, [rbp+var_18]
0x180041148  mov     rdx, [rbp+var_10]
0x18004114c  mov     rax, [rbp+arg_18]
0x180041150  mov     r9d, [r9]; dwErrorControl
0x180041153  mov     r8d, [r8]; dwStartType
0x180041156  mov     edx, [rdx]; dwServiceType
0x180041158  mov     [rsp+80h+lpDisplayName], r12; lpDisplayName
0x18004115d  mov     [rsp+80h+lpPassword], r12; lpPassword
0x180041162  mov     [rsp+80h+lpServiceStartName], r12; lpServiceStartName
0x180041167  mov     [rsp+80h+lpDependencies], r15; lpDependencies
0x18004116c  mov     [rsp+80h+lpdwTagId], r12; lpdwTagId
0x180041171  mov     [rsp+80h+lpLoadOrderGroup], rax; lpLoadOrderGroup
0x180041176  mov     [rsp+80h+lpBinaryPathName], r12; lpBinaryPathName
0x18004117b  call    cs:__imp_ChangeServiceConfigW
0x180041181  test    eax, eax
0x180041183  jnz     short loc_1800411E0
0x180041185  call    cs:__imp_GetLastError
0x18004118b  mov     ebx, eax
0x18004118d  test    eax, eax
0x18004118f  jle     short loc_180041197
0x180041191  movzx   ebx, ax
0x180041194  or      ebx, r14d
0x180041197  test    ebx, ebx
0x180041199  jns     short loc_1800411E0
0x18004119b  mov     rdx, [rbp+lpServiceName]
0x18004119f  test    rdx, rdx
0x1800411a2  jz      short loc_1800411DB
0x1800411a4  test    rdi, rdi
0x1800411a7  jz      short loc_1800411B6
0x1800411a9  mov     rcx, rdi; hSCObject
0x1800411ac  call    cs:__imp_CloseServiceHandle
0x1800411b2  mov     rdx, [rbp+lpServiceName]; lpServiceName
0x1800411b6  test    rsi, rsi
0x1800411b9  jz      short loc_1800411DB
0x1800411bb  mov     r8d, 10000h; dwDesiredAccess
0x1800411c1  mov     rcx, rsi; hSCManager
0x1800411c4  call    cs:__imp_OpenServiceW
0x1800411ca  mov     rdi, rax
0x1800411cd  test    rax, rax
0x1800411d0  jz      short loc_1800411DB
0x1800411d2  mov     rcx, rax; hService
0x1800411d5  call    cs:__imp_DeleteService
0x1800411db  test    r15, r15
0x1800411de  jz      short loc_1800411E9
0x1800411e0  mov     rcx, r15; pv
0x1800411e3  call    cs:__imp_CoTaskMemFree
0x1800411e9  test    rsi, rsi
0x1800411ec  jz      short loc_1800411F7
0x1800411ee  mov     rcx, rsi; hSCObject
0x1800411f1  call    cs:__imp_CloseServiceHandle
0x1800411f7  test    rdi, rdi
0x1800411fa  jz      short loc_180041205
0x1800411fc  mov     rcx, rdi; hSCObject
0x1800411ff  call    cs:__imp_CloseServiceHandle
0x180041205  mov     eax, ebx
0x180041207  add     rsp, 80h
0x18004120e  pop     r15
0x180041210  pop     r14
0x180041212  pop     r12
0x180041214  pop     rdi
0x180041215  pop     rsi
0x180041216  pop     rbx
0x180041217  pop     rbp
0x180041218  retn
```
