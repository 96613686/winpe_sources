# ServiceUserTokenHelper::CreateServiceToken(ushort const *,TokenHandle *)

- ea: `0x180013368`
- end: `0x180013670`
- name: `?CreateServiceToken@ServiceUserTokenHelper@@SAJPEBGPEAVTokenHandle@@@Z`
- size: `776`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void ***)`
- caller_count: `4`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180019690`
- `0x18001a6fc`
- `0x18005a2cc`
- `0x1800d691c`

## callees

- `0x180011760`
- `0x180013368`
- `0x180013678`
- `0x180081600`
- `0x180086674`
- `0x180090524`
- `0x1800959c0`
- `0x1800e0cb0`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800133b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800133b6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800133d5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800133d5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001341a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001341a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800133df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013498`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800134a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800134ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013520`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800133df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013498`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800134a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800134ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013520`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800135ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800135ad`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001362d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180013637`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001362d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180013637`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001350d`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001350d`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180013482`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180013482`
- `api-ms-win-service-private-l1-2-0!GetServiceProcessToken` at `0x1800135ca`
- `api-ms-win-service-private-l1-2-0!GetServiceProcessToken` at `0x1800135ca`

## string_xrefs

- `0x1800133f1`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ServiceUserTokenHelper::CreateServiceToken(const unsigned __int16 *a1, char ***a2)
{
  __int64 result; // rax
  __int64 v5; // rbx
  HANDLE CurrentThread; // rax
  const char *v7; // r9
  __int64 v8; // rdx
  int LastError; // edi
  SC_HANDLE v11; // rax
  SC_HANDLE v12; // rdi
  unsigned int v13; // ecx
  SC_HANDLE v14; // rsi
  signed int v15; // ebx
  unsigned __int64 v16; // rdx
  unsigned __int8 v17; // cl
  __int64 v18; // rcx
  CTelemetry *v19; // rcx
  char *v20; // rcx
  int ServiceProcessToken; // eax
  unsigned int v22; // ecx
  void *v23; // rdx
  const ComError *v24; // rbx
  const ComError *v25[2]; // [rsp+30h] [rbp-1B8h] BYREF
  void **pExceptionObject; // [rsp+40h] [rbp-1A8h] BYREF
  __int128 v27; // [rsp+48h] [rbp-1A0h]
  int v28; // [rsp+58h] [rbp-190h]
  int v29; // [rsp+5Ch] [rbp-18Ch]
  int v30; // [rsp+60h] [rbp-188h]
  void **v31; // [rsp+A0h] [rbp-148h] BYREF
  __int128 v32; // [rsp+A8h] [rbp-140h]
  unsigned int v33; // [rsp+B8h] [rbp-130h]
  int v34; // [rsp+BCh] [rbp-12Ch]
  int v35; // [rsp+C0h] [rbp-128h]
  void **v36; // [rsp+100h] [rbp-E8h] BYREF
  __int128 v37; // [rsp+108h] [rbp-E0h]
  signed int v38; // [rsp+118h] [rbp-D0h]
  int v39; // [rsp+11Ch] [rbp-CCh]
  int v40; // [rsp+120h] [rbp-C8h]
  void **v41; // [rsp+160h] [rbp-88h] BYREF
  __int128 v42; // [rsp+168h] [rbp-80h]
  unsigned int v43; // [rsp+178h] [rbp-70h]
  int v44; // [rsp+17Ch] [rbp-6Ch]
  int v45; // [rsp+180h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+0h]
  void *TokenHandle; // [rsp+200h] [rbp+18h] BYREF
  __int64 v48; // [rsp+208h] [rbp+20h]

  TokenHandle::operator=(a2);
  if ( !ghServiceHandle )
    return 2147942405LL;
  v5 = -1;
  v48 = -1;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) || GetLastError() == 1008 )
  {
    if ( SetThreadToken(0, 0) )
    {
      v5 = (__int64)TokenHandle;
      v48 = (__int64)TokenHandle;
      LastError = 0;
      goto LABEL_37;
    }
    v8 = 454;
  }
  else
  {
    v8 = 450;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v8,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                v7);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
LABEL_37:
  try
  {
    if ( LastError < 0 )
    {
      v27 = 0;
      pExceptionObject = &ComError::`vftable';
      v28 = LastError;
      v29 = 202;
      v30 = 1;
      throw (ComError *)&pExceptionObject;
    }
    v11 = OpenSCManagerW(0, 0, 0xF003Fu);
    v12 = v11;
    TokenHandle = v11;
    if ( !v11 )
    {
      if ( (int)GetLastError() > 0 )
        v13 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v13 = GetLastError();
      v32 = 0;
      v31 = &ComError::`vftable';
      v33 = v13;
      v34 = 208;
      v35 = 1;
      throw (ComError *)&v31;
    }
    v14 = OpenServiceW(v11, a1, 0xF01FFu);
    v25[1] = (const ComError *)v14;
    if ( !v14 )
    {
      v15 = GetLastError();
      if ( CTelemetry::IsEnabled(v17, v16) )
      {
        wil::details::static_lazy<CTelemetry>::get(
          v18,
          _lambda_522be0d8c7a8171f2eb2c3a9bc6a1151_::_lambda_invoker_cdecl_);
        CTelemetry::OpenServiceFailure_(v19, a1, v15);
      }
      if ( v15 > 0 )
        v15 = (unsigned __int16)v15 | 0x80070000;
      v37 = 0;
      v36 = &ComError::`vftable';
      v38 = v15;
      v39 = 221;
      v40 = 1;
      throw (ComError *)&v36;
    }
    v20 = **a2;
    if ( (unsigned __int64)(v20 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v20);
    **a2 = 0;
    ServiceProcessToken = GetServiceProcessToken(ghServiceHandle, v14, *a2);
    v22 = ServiceProcessToken;
    if ( ServiceProcessToken )
    {
      if ( ServiceProcessToken > 0 )
        v22 = (unsigned __int16)ServiceProcessToken | 0x80070000;
      v42 = 0;
      v41 = &ComError::`vftable';
      v43 = v22;
      v44 = 227;
      v45 = 1;
      throw (ComError *)&v41;
    }
    CloseServiceHandle(v14);
    CloseServiceHandle(v12);
    if ( v5 != -1 )
      wil::details::RevertImpersonateToken((HANDLE)v5, v23);
    result = 0;
  }
  catch ( const ComError *v25 )
  {
    if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      v24 = v25[0];
    }
    else
    {
      v24 = v25[0];
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        &WPP_3e78b7e784103a2eddd42a41df8e41c2_Traceguids,
        *((unsigned int *)v24 + 6),
        *((_DWORD *)v24 + 7));
    }
    LODWORD(TokenHandle) = *((_DWORD *)v24 + 6);
    return (unsigned int)TokenHandle;
  }
  return result;
}

```

## disassembly

```asm
0x180013368  mov     [rsp+arg_0], rbx
0x18001336d  push    rsi
0x18001336e  push    rdi
0x18001336f  push    r13
0x180013371  push    r14
0x180013373  push    r15
0x180013375  sub     rsp, 1C0h
0x18001337c  mov     r14, rdx
0x18001337f  mov     r15, rcx
0x180013382  mov     rcx, rdx
0x180013385  call    ??4TokenHandle@@QEAAAEAV0@QEAX@Z; TokenHandle::operator=(void * const)
0x18001338a  cmp     cs:?ghServiceHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, 0; SERVICE_STATUS_HANDLE__ * ghServiceHandle
0x180013392  jnz     short loc_18001339E
0x180013394  mov     eax, 80070005h
0x180013399  jmp     loc_180013657
0x18001339e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800133a2  mov     [rsp+1E8h+arg_18], rbx
0x1800133aa  mov     [rsp+1E8h+TokenHandle], 0
0x1800133b6  call    cs:__imp_GetCurrentThread
0x1800133bc  lea     r9, [rsp+1E8h+TokenHandle]; TokenHandle
0x1800133c4  lea     r13d, [rbx+2]
0x1800133c8  mov     r8d, r13d; OpenAsSelf
0x1800133cb  mov     esi, 0F01FFh
0x1800133d0  mov     edx, esi; DesiredAccess
0x1800133d2  mov     rcx, rax; ThreadHandle
0x1800133d5  call    cs:__imp_OpenThreadToken
0x1800133db  test    eax, eax
0x1800133dd  jnz     short loc_180013416
0x1800133df  call    cs:__imp_GetLastError
0x1800133e5  cmp     eax, 3F0h
0x1800133ea  jz      short loc_180013416
0x1800133ec  mov     edx, 1C2h; void *
0x1800133f1  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800133f8  mov     rcx, [rsp+1E8h]; this
0x180013400  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180013405  mov     edi, eax
0x180013407  lea     rcx, [rsp+1E8h+TokenHandle]
0x18001340f  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180013414  jmp     short loc_18001343D
0x180013416  xor     edx, edx; Token
0x180013418  xor     ecx, ecx; Thread
0x18001341a  call    cs:__imp_SetThreadToken
0x180013420  test    eax, eax
0x180013422  jnz     short loc_18001342B
0x180013424  mov     edx, 1C6h
0x180013429  jmp     short loc_1800133F1
0x18001342b  mov     rbx, [rsp+1E8h+TokenHandle]
0x180013433  mov     [rsp+1E8h+arg_18], rbx
0x18001343b  xor     edi, edi
0x18001343d  test    edi, edi
0x18001343f  jns     short loc_180013478
0x180013441  xorps   xmm0, xmm0
0x180013444  movups  [rsp+1E8h+var_1A0], xmm0
0x180013449  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180013450  mov     [rsp+1E8h+pExceptionObject], rax
0x180013455  mov     [rsp+1E8h+var_190], edi
0x180013459  mov     [rsp+1E8h+var_18C], 0CAh
0x180013461  mov     [rsp+1E8h+var_188], r13d
0x180013466  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18001346d  lea     rcx, [rsp+1E8h+pExceptionObject]; pExceptionObject
0x180013472  call    _CxxThrowException_0
0x180013478  xor     edx, edx; lpDatabaseName
0x18001347a  xor     ecx, ecx; lpMachineName
0x18001347c  mov     r8d, 0F003Fh; dwDesiredAccess
0x180013482  call    cs:__imp_OpenSCManagerW
0x180013488  mov     rdi, rax
0x18001348b  mov     [rsp+1E8h+TokenHandle], rax
0x180013493  test    rax, rax
0x180013496  jnz     short loc_180013504
0x180013498  call    cs:__imp_GetLastError
0x18001349e  test    eax, eax
0x1800134a0  jg      short loc_1800134AC
0x1800134a2  call    cs:__imp_GetLastError
0x1800134a8  mov     ecx, eax
0x1800134aa  jmp     short loc_1800134BB
0x1800134ac  call    cs:__imp_GetLastError
0x1800134b2  movzx   ecx, ax
0x1800134b5  or      ecx, 80070000h
0x1800134bb  xorps   xmm0, xmm0
0x1800134be  movups  [rsp+1E8h+var_140], xmm0
0x1800134c6  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800134cd  mov     [rsp+1E8h+var_148], rax
0x1800134d5  mov     [rsp+1E8h+var_130], ecx
0x1800134dc  mov     [rsp+1E8h+var_12C], 0D0h
0x1800134e7  mov     [rsp+1E8h+var_128], r13d
0x1800134ef  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800134f6  lea     rcx, [rsp+1E8h+var_148]; pExceptionObject
0x1800134fe  call    _CxxThrowException_0
0x180013504  mov     r8d, esi; dwDesiredAccess
0x180013507  mov     rdx, r15; lpServiceName
0x18001350a  mov     rcx, rdi; hSCManager
0x18001350d  call    cs:__imp_OpenServiceW
0x180013513  mov     rsi, rax
0x180013516  mov     [rsp+1E8h+var_1B0], rax
0x18001351b  test    rax, rax
0x18001351e  jnz     short loc_18001359D
0x180013520  call    cs:__imp_GetLastError
0x180013526  mov     ebx, eax
0x180013528  call    ?IsEnabled@CTelemetry@@SA_NE_K@Z; CTelemetry::IsEnabled(uchar,unsigned __int64)
0x18001352d  test    al, al
0x18001352f  jz      short loc_180013548
0x180013531  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_522be0d8c7a8171f2eb2c3a9bc6a1151_@@CA@XZ; _lambda_522be0d8c7a8171f2eb2c3a9bc6a1151_::_lambda_invoker_cdecl_(void)
0x180013538  call    ?get@?$static_lazy@VCTelemetry@@@details@wil@@QEAAPEAVCTelemetry@@P6AXXZ@Z; wil::details::static_lazy<CTelemetry>::get(void (*)(void))
0x18001353d  mov     r8d, ebx; unsigned int
0x180013540  mov     rdx, r15; unsigned __int16 *
0x180013543  call    ?OpenServiceFailure_@CTelemetry@@QEAAXPEBGK@Z; CTelemetry::OpenServiceFailure_(ushort const *,ulong)
0x180013548  test    ebx, ebx
0x18001354a  jle     short loc_180013555
0x18001354c  movzx   ebx, bx
0x18001354f  or      ebx, 80070000h
0x180013555  xorps   xmm0, xmm0
0x180013558  movups  [rsp+1E8h+var_E0], xmm0
0x180013560  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180013567  mov     [rsp+1E8h+var_E8], rax
0x18001356f  mov     [rsp+1E8h+var_D0], ebx
0x180013576  mov     [rsp+1E8h+var_CC], 0DDh
0x180013581  mov     [rsp+1E8h+var_C8], r13d
0x180013589  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180013590  lea     rcx, [rsp+1E8h+var_E8]; pExceptionObject
0x180013598  call    _CxxThrowException_0
0x18001359d  mov     rax, [r14]
0x1800135a0  mov     rcx, [rax]; hObject
0x1800135a3  lea     rax, [rcx-1]
0x1800135a7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800135ab  ja      short loc_1800135B3
0x1800135ad  call    cs:__imp_CloseHandle
0x1800135b3  mov     rax, [r14]
0x1800135b6  mov     qword ptr [rax], 0
0x1800135bd  mov     r8, [r14]
0x1800135c0  mov     rdx, rsi
0x1800135c3  mov     rcx, cs:?ghServiceHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; SERVICE_STATUS_HANDLE__ * ghServiceHandle
0x1800135ca  call    cs:__imp_GetServiceProcessToken
0x1800135d0  mov     ecx, eax
0x1800135d2  test    eax, eax
0x1800135d4  jz      short loc_18001362A
0x1800135d6  jle     short loc_1800135E1
0x1800135d8  movzx   ecx, ax
0x1800135db  or      ecx, 80070000h
0x1800135e1  xorps   xmm0, xmm0
0x1800135e4  movups  [rsp+1E8h+var_80], xmm0
0x1800135ec  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800135f3  mov     [rsp+1E8h+var_88], rax
0x1800135fb  mov     [rsp+1E8h+var_70], ecx
0x180013602  mov     [rsp+1E8h+var_6C], 0E3h
0x18001360d  mov     [rsp+1E8h+var_68], r13d
0x180013615  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18001361c  lea     rcx, [rsp+1E8h+var_88]; pExceptionObject
0x180013624  call    _CxxThrowException_0
0x18001362a  mov     rcx, rsi; hSCObject
0x18001362d  call    cs:__imp_CloseServiceHandle
0x180013633  nop
0x180013634  mov     rcx, rdi; hSCObject
0x180013637  call    cs:__imp_CloseServiceHandle
0x18001363d  nop
0x18001363e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180013642  jz      short loc_18001364C
0x180013644  mov     rcx, rbx; Token
0x180013647  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x18001364c  xor     eax, eax
0x18001364e  jmp     short loc_180013657
0x180013650  mov     eax, dword ptr [rsp+1E8h+TokenHandle]
0x180013657  mov     rbx, [rsp+1E8h+arg_0]
0x18001365f  add     rsp, 1C0h
0x180013666  pop     r15
0x180013668  pop     r14
0x18001366a  pop     r13
0x18001366c  pop     rdi
0x18001366d  pop     rsi
0x18001366e  retn
```
