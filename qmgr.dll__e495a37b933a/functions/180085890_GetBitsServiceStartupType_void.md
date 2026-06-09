# GetBitsServiceStartupType(void)

- ea: `0x180085890`
- end: `0x180085ab3`
- name: `?GetBitsServiceStartupType@@YA?AW4ServiceStartupType@@XZ`
- size: `547`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18008fbfc`

## callees

- `0x180006640`
- `0x180085890`
- `0x1800971ec`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800858ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800858d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800858e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008594a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085954`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008595c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800859f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085a02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085a0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800858ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800858d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800858e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008594a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085954`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008595c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800859f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085a02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085a0a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180085a92`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180085aa0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180085a92`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180085aa0`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180085934`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180085934`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800858b8`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800858b8`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800859ee`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800859ee`

## string_xrefs

- `0x1800858af`: `ServicesActive`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 GetBitsServiceStartupType()
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rbx
  unsigned int LastError; // eax
  SC_HANDLE v3; // rdi
  unsigned int v4; // eax
  struct _QUERY_SERVICE_CONFIGW *v5; // rsi
  unsigned int v6; // eax
  DWORD dwStartType; // esi
  __int64 result; // rax
  bool v9[8]; // [rsp+20h] [rbp-158h] BYREF
  struct _QUERY_SERVICE_CONFIGW *v10; // [rsp+28h] [rbp-150h]
  void **pExceptionObject; // [rsp+30h] [rbp-148h] BYREF
  __int128 v12; // [rsp+38h] [rbp-140h]
  unsigned int v13; // [rsp+48h] [rbp-130h]
  int v14; // [rsp+4Ch] [rbp-12Ch]
  int v15; // [rsp+50h] [rbp-128h]
  void **v16; // [rsp+90h] [rbp-E8h] BYREF
  __int128 v17; // [rsp+98h] [rbp-E0h]
  unsigned int v18; // [rsp+A8h] [rbp-D0h]
  int v19; // [rsp+ACh] [rbp-CCh]
  int v20; // [rsp+B0h] [rbp-C8h]
  void **v21; // [rsp+F0h] [rbp-88h] BYREF
  __int128 v22; // [rsp+F8h] [rbp-80h]
  unsigned int v23; // [rsp+108h] [rbp-70h]
  int v24; // [rsp+10Ch] [rbp-6Ch]
  int v25; // [rsp+110h] [rbp-68h]
  const ComError *v26; // [rsp+150h] [rbp-28h] BYREF
  DWORD pcbBytesNeeded; // [rsp+188h] [rbp+10h] BYREF
  SC_HANDLE v28; // [rsp+190h] [rbp+18h]
  SC_HANDLE hSCObject; // [rsp+198h] [rbp+20h]

  v28 = 0;
  v0 = OpenSCManagerW(0, L"ServicesActive", 0x80000000);
  try
  {
    v1 = v0;
    hSCObject = v0;
    if ( !v0 )
    {
      if ( (int)GetLastError() > 0 )
        LastError = (unsigned __int16)GetLastError() | 0x80070000;
      else
        LastError = GetLastError();
      v12 = 0;
      pExceptionObject = &ComError::`vftable';
      v13 = LastError;
      v14 = 510;
      v15 = 1;
      throw (ComError *)&pExceptionObject;
    }
    v3 = OpenServiceW(v0, L"BITS", 0x80000000);
    v28 = v3;
    if ( !v3 )
    {
      if ( (int)GetLastError() > 0 )
        v4 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v4 = GetLastError();
      v17 = 0;
      v16 = &ComError::`vftable';
      v18 = v4;
      v19 = 521;
      v20 = 1;
      throw (ComError *)&v16;
    }
    v5 = (struct _QUERY_SERVICE_CONFIGW *)operator new(0x2000u);
    v9[0] = v5 != 0;
    v10 = v5;
    pcbBytesNeeded = 0;
    if ( !QueryServiceConfigW(v3, v5, 0x2000u, &pcbBytesNeeded) )
    {
      if ( (int)GetLastError() > 0 )
        v6 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v6 = GetLastError();
      v22 = 0;
      v21 = &ComError::`vftable';
      v23 = v6;
      v24 = 535;
      v25 = 1;
      throw (ComError *)&v21;
    }
    dwStartType = v5->dwStartType;
    auto_array<tag_JET_COLUMNCREATE_W>::~auto_array<tag_JET_COLUMNCREATE_W>((__int64)v9);
  }
  catch ( const ComError *v26 )
  {
    v3 = v28;
    dwStartType = 0;
    v1 = hSCObject;
    if ( v28 )
      goto LABEL_19;
LABEL_20:
    if ( v1 )
      CloseServiceHandle(v1);
    result = dwStartType;
  }
LABEL_19:
  CloseServiceHandle(v3);
  goto LABEL_20;
}

```

## disassembly

```asm
0x180085890  push    rbx
0x180085892  push    rsi
0x180085893  push    rdi
0x180085894  sub     rsp, 160h
0x18008589b  mov     [rsp+178h+arg_10], 0
0x1800858a7  mov     edi, 80000000h
0x1800858ac  mov     r8d, edi; dwDesiredAccess
0x1800858af  lea     rdx, DatabaseName; "ServicesActive"
0x1800858b6  xor     ecx, ecx; lpMachineName
0x1800858b8  call    cs:__imp_OpenSCManagerW
0x1800858be  mov     rbx, rax
0x1800858c1  mov     [rsp+178h+hSCObject], rax
0x1800858c9  test    rax, rax
0x1800858cc  jnz     short loc_180085927
0x1800858ce  call    cs:__imp_GetLastError
0x1800858d4  test    eax, eax
0x1800858d6  jg      short loc_1800858E0
0x1800858d8  call    cs:__imp_GetLastError
0x1800858de  jmp     short loc_1800858EE
0x1800858e0  call    cs:__imp_GetLastError
0x1800858e6  movzx   eax, ax
0x1800858e9  or      eax, 80070000h
0x1800858ee  xorps   xmm0, xmm0
0x1800858f1  movups  [rsp+178h+var_140], xmm0
0x1800858f6  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800858fd  mov     [rsp+178h+pExceptionObject], rcx
0x180085902  mov     [rsp+178h+var_130], eax
0x180085906  mov     [rsp+178h+var_12C], 1FEh
0x18008590e  mov     [rsp+178h+var_128], 1
0x180085916  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18008591d  lea     rcx, [rsp+178h+pExceptionObject]; pExceptionObject
0x180085922  call    _CxxThrowException_0
0x180085927  mov     r8d, edi; dwDesiredAccess
0x18008592a  lea     rdx, ServiceName; "BITS"
0x180085931  mov     rcx, rax; hSCManager
0x180085934  call    cs:__imp_OpenServiceW
0x18008593a  mov     rdi, rax
0x18008593d  mov     [rsp+178h+arg_10], rax
0x180085945  test    rax, rax
0x180085948  jnz     short loc_1800859B5
0x18008594a  call    cs:__imp_GetLastError
0x180085950  test    eax, eax
0x180085952  jg      short loc_18008595C
0x180085954  call    cs:__imp_GetLastError
0x18008595a  jmp     short loc_18008596A
0x18008595c  call    cs:__imp_GetLastError
0x180085962  movzx   eax, ax
0x180085965  or      eax, 80070000h
0x18008596a  xorps   xmm0, xmm0
0x18008596d  movups  [rsp+178h+var_E0], xmm0
0x180085975  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18008597c  mov     [rsp+178h+var_E8], rcx
0x180085984  mov     [rsp+178h+var_D0], eax
0x18008598b  mov     [rsp+178h+var_CC], 209h
0x180085996  mov     [rsp+178h+var_C8], 1
0x1800859a1  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800859a8  lea     rcx, [rsp+178h+var_E8]; pExceptionObject
0x1800859b0  call    _CxxThrowException_0
0x1800859b5  mov     ecx, 2000h; dwBytes
0x1800859ba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800859bf  mov     rsi, rax
0x1800859c2  test    rax, rax
0x1800859c5  setnz   [rsp+178h+var_158]
0x1800859ca  mov     [rsp+178h+var_150], rax
0x1800859cf  mov     [rsp+178h+pcbBytesNeeded], 0
0x1800859da  lea     r9, [rsp+178h+pcbBytesNeeded]; pcbBytesNeeded
0x1800859e2  mov     r8d, 2000h; cbBufSize
0x1800859e8  mov     rdx, rax; lpServiceConfig
0x1800859eb  mov     rcx, rdi; hService
0x1800859ee  call    cs:__imp_QueryServiceConfigW
0x1800859f4  test    eax, eax
0x1800859f6  jnz     short loc_180085A63
0x1800859f8  call    cs:__imp_GetLastError
0x1800859fe  test    eax, eax
0x180085a00  jg      short loc_180085A0A
0x180085a02  call    cs:__imp_GetLastError
0x180085a08  jmp     short loc_180085A18
0x180085a0a  call    cs:__imp_GetLastError
0x180085a10  movzx   eax, ax
0x180085a13  or      eax, 80070000h
0x180085a18  xorps   xmm0, xmm0
0x180085a1b  movups  [rsp+178h+var_80], xmm0
0x180085a23  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180085a2a  mov     [rsp+178h+var_88], rcx
0x180085a32  mov     [rsp+178h+var_70], eax
0x180085a39  mov     [rsp+178h+var_6C], 217h
0x180085a44  mov     [rsp+178h+var_68], 1
0x180085a4f  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180085a56  lea     rcx, [rsp+178h+var_88]; pExceptionObject
0x180085a5e  call    _CxxThrowException_0
0x180085a63  mov     esi, [rsi+4]
0x180085a66  lea     rcx, [rsp+178h+var_158]
0x180085a6b  call    ??1?$auto_array@Utag_JET_COLUMNCREATE_W@@@@QEAA@XZ; auto_array<tag_JET_COLUMNCREATE_W>::~auto_array<tag_JET_COLUMNCREATE_W>(void)
0x180085a70  nop
0x180085a71  jmp     short loc_180085A8F
0x180085a73  mov     rdi, [rsp+178h+arg_10]
0x180085a7b  mov     esi, [rsp+178h+arg_0]
0x180085a82  mov     rbx, [rsp+178h+hSCObject]
0x180085a8a  test    rdi, rdi
0x180085a8d  jz      short loc_180085A98
0x180085a8f  mov     rcx, rdi; hSCObject
0x180085a92  call    cs:__imp_CloseServiceHandle
0x180085a98  test    rbx, rbx
0x180085a9b  jz      short loc_180085AA6
0x180085a9d  mov     rcx, rbx; hSCObject
0x180085aa0  call    cs:__imp_CloseServiceHandle
0x180085aa6  mov     eax, esi
0x180085aa8  add     rsp, 160h
0x180085aaf  pop     rdi
0x180085ab0  pop     rsi
0x180085ab1  pop     rbx
0x180085ab2  retn
```
