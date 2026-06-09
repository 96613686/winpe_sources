# FidoRegController::FidoRegisterKey(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,_DISCOVERY_METADATA *,ushort const *,_GUID *,ulong,void (*)(struct_fido_reg_response,unsigned __int64,long),unsigned __int64,ushort const *,ushort const *,ushort const *,ushort const *,ulong *)

- ea: `0x180086538`
- end: `0x180086cc2`
- name: `?FidoRegisterKey@FidoRegController@@SAJPEBG0000PEAU_DISCOVERY_METADATA@@0PEAU_GUID@@KP6AXUstruct_fido_reg_response@@_KJ@Z40000PEAK@Z`
- size: `1930`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *, struct _DISCOVERY_METADATA *, const unsigned __int16 *, struct _GUID *, unsigned int, void (__high *)(struct struct_fido_reg_response, unsigned __int64, int), unsigned __int64, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18004a770`

## callees

- `0x1800011ec`
- `0x180005ba0`
- `0x1800084f4`
- `0x180009780`
- `0x18000bac0`
- `0x18000ddf0`
- `0x18000f368`
- `0x180017bb0`
- `0x18001b560`
- `0x1800204f0`
- `0x1800307c4`
- `0x18003334c`
- `0x180034328`
- `0x18003a19c`
- `0x18003ef28`
- `0x180043ef8`
- `0x180044300`
- `0x18004651c`
- `0x180046540`
- `0x1800860d4`
- `0x180086538`
- `0x180086fa0`
- `0x180088af8`
- `0x180089574`
- `0x1800bf010`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x180086740`
- `RPCRT4!RpcStringFreeW` at `0x180086740`
- `RPCRT4!UuidToStringW` at `0x18008660a`
- `RPCRT4!UuidToStringW` at `0x18008660a`

## string_xrefs

- `0x180086ab5`: `CopyStringW`
- `0x18008677e`: `CreateGuid`
- `0x180086a78`: `StringCompare`
- `0x1800867ef`: `pcszAuthToken`
- `0x18008680e`: `pcszAuthToken`
- `0x1800868fd`: `pRegistrationInfo->pszWebAuthNServiceVersion`
- `0x18008691c`: `pRegistrationInfo->pszWebAuthNServiceVersion`
- `0x180086aa3`: `login.microsoft.com`
- `0x180086a60`: `login.microsoftonline.com`

## pseudocode

```c
__int64 __fastcall FidoRegController::FidoRegisterKey(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        const unsigned __int16 **a6,
        unsigned __int16 *a7,
        struct _GUID *a8,
        unsigned int a9,
        void (__high *a10)(struct struct_fido_reg_response, unsigned __int64, int),
        unsigned __int64 a11,
        unsigned __int16 *a12,
        unsigned __int16 *a13,
        unsigned __int16 *a14,
        unsigned __int16 *a15,
        unsigned int *a16)
{
  unsigned __int16 *v16; // r12
  struct STRUCT_FIDO_REG_RESPONSE_CALLBACK_CONTEXT *v17; // r13
  struct FidoHttpRequest *v18; // r15
  WCHAR *v19; // rsi
  unsigned int v20; // eax
  signed int v21; // ebx
  bool v22; // sf
  unsigned __int16 *v23; // r15
  unsigned __int16 *v24; // r13
  int v26; // eax
  const unsigned __int16 *v27; // rdx
  const unsigned __int16 *v28; // rdx
  unsigned __int16 **v29; // rax
  unsigned __int16 **v30; // rdi
  int v31; // eax
  struct STRUCT_FIDO_REG_RESPONSE_CALLBACK_CONTEXT *v32; // rax
  FidoHttpRequest *v33; // rax
  int PostEndpoint; // eax
  const unsigned __int16 *v35; // r8
  int v36; // eax
  const wchar_t *v37; // r8
  unsigned __int16 *v38; // r14
  void (*v39)(struct FidoHttpRequest *, struct STRUCT_FIDO_REG_RESPONSE_CALLBACK_CONTEXT *, int); // r9
  unsigned __int16 *v40; // r13
  unsigned __int16 *v41; // r15
  unsigned __int16 *v42; // [rsp+40h] [rbp-C0h]
  unsigned __int16 *v43; // [rsp+40h] [rbp-C0h]
  unsigned __int16 *v44; // [rsp+48h] [rbp-B8h]
  unsigned __int16 *v45; // [rsp+80h] [rbp-80h] BYREF
  int v46; // [rsp+88h] [rbp-78h] BYREF
  RPC_WSTR StringUuid; // [rsp+90h] [rbp-70h] BYREF
  LPCWCH lpString1; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v49; // [rsp+A0h] [rbp-60h]
  unsigned __int16 *v50; // [rsp+A8h] [rbp-58h]
  unsigned __int16 *v51; // [rsp+B0h] [rbp-50h]
  unsigned __int16 *v52; // [rsp+B8h] [rbp-48h]
  unsigned __int16 *v53; // [rsp+C0h] [rbp-40h]
  void *lpMem; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 *v55; // [rsp+D0h] [rbp-30h]
  void *Block; // [rsp+D8h] [rbp-28h] BYREF
  unsigned int *v57; // [rsp+E0h] [rbp-20h]
  unsigned __int16 *v58; // [rsp+E8h] [rbp-18h]
  unsigned __int16 *v59; // [rsp+F0h] [rbp-10h]
  unsigned __int16 *v60; // [rsp+F8h] [rbp-8h]
  FidoHttpRequest *v61; // [rsp+100h] [rbp+0h]
  UUID Uuid; // [rsp+108h] [rbp+8h] BYREF

  v16 = a1;
  v45 = a1;
  v55 = a12;
  v60 = a13;
  v58 = a15;
  v49 = a5;
  v57 = a16;
  v50 = a7;
  v17 = 0;
  v18 = 0;
  v51 = a4;
  v19 = 0;
  v52 = a3;
  v53 = a2;
  v59 = a14;
  StringUuid = 0;
  lpMem = 0;
  lpString1 = 0;
  Block = 0;
  v46 = 0;
  Uuid = 0;
  if ( a8 )
  {
    Uuid = *a8;
  }
  else
  {
    v26 = CreateGuid(&Uuid);
    v21 = v26;
    if ( v26 < 0 )
    {
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"FidoRegController::FidoRegisterKey",
        L"CreateGuid",
        (unsigned int)v26);
      goto LABEL_59;
    }
  }
  v20 = UuidToStringW(&Uuid, &StringUuid);
  v21 = v20;
  if ( v20 )
  {
    Logger::TraceError(
      L"%s: Cannot convert the request ID to a string. UuidToStringW failed with error code: 0x%08x.",
      L"FidoRegController::FidoRegisterKey",
      v20);
    v22 = v21 < 0;
    if ( v21 > 0 )
    {
      v21 = (unsigned __int16)v21 | 0x80070000;
      v22 = v21 < 0;
    }
    if ( !v22 )
      goto LABEL_7;
    goto LABEL_59;
  }
  if ( (unsigned int)IsEmptyString(v16) )
  {
    v21 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null or empty.",
      L"FidoRegController::FidoRegisterKey",
      L"pcszUserEmail");
    v27 = L"pcszUserEmail";
LABEL_18:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"FidoRegController::FidoRegisterKey", v27);
    goto LABEL_59;
  }
  if ( (unsigned int)IsEmptyString(v50) )
  {
    v21 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null or empty.",
      L"FidoRegController::FidoRegisterKey",
      L"pcszAuthToken");
    v27 = L"pcszAuthToken";
    goto LABEL_18;
  }
  if ( (unsigned int)IsEmptyString(a14) )
  {
    v21 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null or empty.",
      L"FidoRegController::FidoRegisterKey",
      L"pwszTenantId");
    v27 = L"pwszTenantId";
    goto LABEL_18;
  }
  if ( a10 )
  {
    if ( !a6 )
    {
      v21 = -2147024809;
      Logger::TraceError(L"%s: \"%s\" should not be null.", L"FidoRegController::FidoRegisterKey", L"pRegistrationInfo");
      v28 = L"pRegistrationInfo";
      goto LABEL_25;
    }
    if ( (unsigned int)IsEmptyString(a6[12]) )
    {
      v21 = -2147024809;
      Logger::TraceError(
        L"%s: \"%s\" should not be null or empty.",
        L"FidoRegController::FidoRegisterKey",
        L"pRegistrationInfo->pszWebAuthNEndpointReference");
      v28 = L"pRegistrationInfo->pszWebAuthNEndpointReference";
      goto LABEL_25;
    }
    if ( (unsigned int)IsEmptyString(a6[11]) )
    {
      v21 = -2147024809;
      Logger::TraceError(
        L"%s: \"%s\" should not be null or empty.",
        L"FidoRegController::FidoRegisterKey",
        L"pRegistrationInfo->pszWebAuthNServiceVersion");
      v28 = L"pRegistrationInfo->pszWebAuthNServiceVersion";
      goto LABEL_25;
    }
    v29 = (unsigned __int16 **)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
    v61 = (FidoHttpRequest *)v29;
    v30 = v29;
    if ( !v29 )
    {
      v21 = -2147024882;
      Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"FidoRegController::FidoRegisterKey");
      goto LABEL_58;
    }
    *((_DWORD *)v29 + 2) = 0;
    *v29 = (unsigned __int16 *)&FidoRegController::`vftable';
    v29[2] = 0;
    v29[3] = 0;
    v31 = StringDup(StringUuid, v29 + 3, 0);
    v21 = v31;
    if ( v31 < 0 )
    {
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"FidoRegController::FidoRegisterKey",
        L"StringDup",
        (unsigned int)v31);
LABEL_55:
      v16 = v45;
      goto LABEL_56;
    }
    *((_DWORD *)v30 + 8) = a9;
    *((_DWORD *)v30 + 2) = 1;
    v32 = (struct STRUCT_FIDO_REG_RESPONSE_CALLBACK_CONTEXT *)operator new(
                                                                0x18u,
                                                                (const struct std::nothrow_t *)&std::nothrow);
    v17 = v32;
    if ( !v32
      || (*(_QWORD *)v32 = a10,
          *((_QWORD *)v32 + 1) = a11,
          v33 = (FidoHttpRequest *)operator new(0xD0u, (const struct std::nothrow_t *)&std::nothrow),
          (v61 = v33) == 0)
      || (v18 = FidoHttpRequest::FidoHttpRequest(v33)) == 0 )
    {
      v21 = -2147024882;
      Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"FidoRegController::FidoRegisterKey");
      goto LABEL_55;
    }
    v16 = v45;
    PostEndpoint = FidoRegController::GetPostEndpoint(
                     (struct _DISCOVERY_METADATA *)a6,
                     v45,
                     (unsigned __int16 **)&lpMem);
    v21 = PostEndpoint;
    if ( PostEndpoint < 0 )
    {
      v35 = L"FidoRegController::GetPostEndpoint";
LABEL_51:
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"FidoRegController::FidoRegisterKey",
        v35,
        (unsigned int)PostEndpoint);
      goto LABEL_56;
    }
    v36 = ParseUrl(a6[4], (int *)&v45, (unsigned __int16 **)&lpString1, (unsigned __int16 **)&Block);
    v21 = v36;
    if ( v36 < 0 )
    {
      v37 = L"ParseUrl";
LABEL_47:
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"FidoRegController::FidoRegisterKey",
        v37,
        (unsigned int)v36);
      v19 = (WCHAR *)lpString1;
LABEL_56:
      (*(void (__fastcall **)(unsigned __int16 **, __int64))*v30)(v30, 1);
      goto LABEL_59;
    }
    v19 = (WCHAR *)lpString1;
    PostEndpoint = StringCompare(lpString1, L"login.microsoftonline.com", 1u, &v46);
    v21 = PostEndpoint;
    if ( PostEndpoint < 0 )
    {
      v35 = L"StringCompare";
      goto LABEL_51;
    }
    if ( v46 )
    {
      operator delete(v19);
      lpString1 = 0;
      v36 = CopyStringW(L"login.microsoft.com", 0x13u, (unsigned __int16 **)&lpString1);
      v21 = v36;
      if ( v36 < 0 )
      {
        v37 = L"CopyStringW";
        goto LABEL_47;
      }
      v19 = (WCHAR *)lpString1;
    }
    Logger::TraceVerbose((wchar_t *)L"%s: RPID: %s", L"FidoRegController::FidoRegisterKey", v19);
    v38 = v50;
    PostEndpoint = FidoKeyManager::MakeCredential(
                     v19,
                     v16,
                     v53,
                     v52,
                     v51,
                     v49,
                     v50,
                     StringUuid,
                     a9,
                     v55,
                     v60,
                     v59,
                     v58,
                     (struct FidoKey **)v30 + 2,
                     v57);
    v21 = PostEndpoint;
    if ( PostEndpoint >= 0 )
    {
      PostEndpoint = FidoRegController::FidoRegBegin(
                       (FidoRegController *)v30,
                       (const unsigned __int16 *)lpMem,
                       v38,
                       v39,
                       v17,
                       v18);
      v21 = PostEndpoint;
      if ( PostEndpoint >= 0 )
        goto LABEL_7;
      v35 = L"FidoRegController::FidoRegBegin";
    }
    else
    {
      v35 = L"FidoKeyManager::MakeCredential";
    }
    goto LABEL_51;
  }
  v21 = -2147024809;
  Logger::TraceError(L"%s: \"%s\" should not be null.", L"FidoRegController::FidoRegisterKey", L"pfnCallback");
  v28 = L"pfnCallback";
LABEL_25:
  Logger::WriteNullOrEmptyParameterFailureEvent(L"FidoRegController::FidoRegisterKey", v28);
LABEL_58:
  v16 = v45;
LABEL_59:
  operator delete(v17);
  if ( v18 )
    (**(void (__fastcall ***)(struct FidoHttpRequest *, __int64))v18)(v18, 1);
  if ( v21 < 0 )
  {
    v40 = v51;
    v41 = v52;
    Logger::WriteFidoRegistrationBeginFailureEvent(v21, v19, v16, v53, v52, v51, v49, v50, StringUuid, a9);
    LODWORD(v44) = v21;
    LODWORD(v43) = a9;
    Logger::TraceError(
      L"%s: FidoRegisterKey begin failed. UPN: %s, Key display name: \"%s\", User display name: \"%s\", User image URL: \""
       "%s\", Key algorithm: \"%s\", Request ID: %s, Flags: %lu, Error code: 0x%08x.",
      L"FidoRegController::FidoRegisterKey",
      v16,
      v53,
      v41,
      v40,
      v49,
      StringUuid,
      v43,
      v44);
    goto LABEL_8;
  }
LABEL_7:
  v23 = v52;
  v24 = v51;
  Logger::WriteFidoRegistrationBeginSuccessEvent(v19, v16, v53, v52, v51, v49, v50, StringUuid, a9);
  LODWORD(v42) = a9;
  Logger::TraceVerbose(
    (wchar_t *)L"%s: FidoRegisterKey begin succeeded. UPN: %s, Key display name: \"%s\", User display name: \"%s\", User i"
                "mage URL: \"%s\", Key algorithm: \"%s\", Request ID: %s, Flags: %lu.",
    L"FidoRegController::FidoRegisterKey",
    v16,
    v53,
    v23,
    v24,
    v49,
    StringUuid,
    v42);
LABEL_8:
  if ( (unsigned int)dword_18013D150 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x400000000000LL) )
  {
    v46 = v21;
    v55 = (unsigned __int16 *)0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (__int64)&dword_18013D150,
      (__int64)&byte_18012B1F7);
  }
  operator delete(v19);
  operator delete(Block);
  SafeFree(lpMem);
  if ( StringUuid )
    RpcStringFreeW(&StringUuid);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x180086538  push    rbp
0x18008653a  push    rbx
0x18008653b  push    rsi
0x18008653c  push    rdi
0x18008653d  push    r12
0x18008653f  push    r13
0x180086541  push    r14
0x180086543  push    r15
0x180086545  lea     rbp, [rsp-28h]
0x18008654a  sub     rsp, 128h
0x180086551  mov     rax, cs:__security_cookie
0x180086558  xor     rax, rsp
0x18008655b  mov     [rbp+60h+var_48], rax
0x18008655f  mov     rax, [rbp+60h+arg_20]
0x180086566  mov     r12, rcx
0x180086569  mov     rdi, [rbp+60h+arg_68]
0x180086570  xorps   xmm0, xmm0
0x180086573  mov     r14, [rbp+60h+arg_28]
0x18008657a  mov     [rbp+60h+var_E0], rcx
0x18008657e  mov     rcx, [rbp+60h+arg_58]
0x180086585  mov     [rbp+60h+var_90], rcx
0x180086589  mov     rcx, [rbp+60h+arg_60]
0x180086590  mov     [rbp+60h+var_68], rcx
0x180086594  mov     rcx, [rbp+60h+arg_70]
0x18008659b  mov     [rbp+60h+var_78], rcx
0x18008659f  mov     rcx, [rbp+60h+arg_78]
0x1800865a6  mov     [rbp+60h+var_C0], rax
0x1800865aa  mov     rax, [rbp+60h+arg_30]
0x1800865b1  mov     [rbp+60h+var_80], rcx
0x1800865b5  xor     ecx, ecx
0x1800865b7  mov     [rbp+60h+var_B8], rax
0x1800865bb  mov     r13d, ecx
0x1800865be  mov     rax, [rbp+60h+arg_38]
0x1800865c5  mov     r15d, ecx
0x1800865c8  mov     [rbp+60h+var_B0], r9
0x1800865cc  mov     esi, ecx
0x1800865ce  mov     [rbp+60h+var_A8], r8
0x1800865d2  mov     [rbp+60h+var_A0], rdx
0x1800865d6  mov     [rbp+60h+var_70], rdi
0x1800865da  mov     [rbp+60h+StringUuid], rcx
0x1800865de  mov     [rbp+60h+lpMem], rcx
0x1800865e2  mov     [rbp+60h+lpString1], rcx
0x1800865e6  mov     [rbp+60h+Block], rcx
0x1800865ea  mov     [rbp+60h+var_D8], ecx
0x1800865ed  movups  xmmword ptr [rbp+60h+Uuid.Data1], xmm0
0x1800865f1  test    rax, rax
0x1800865f4  jz      loc_180086768
0x1800865fa  movups  xmm0, xmmword ptr [rax]
0x1800865fd  movdqu  xmmword ptr [rbp+60h+Uuid.Data1], xmm0
0x180086602  lea     rdx, [rbp+60h+StringUuid]; StringUuid
0x180086606  lea     rcx, [rbp+60h+Uuid]; Uuid
0x18008660a  call    cs:__imp_UuidToStringW
0x180086610  mov     ebx, eax
0x180086612  test    eax, eax
0x180086614  jz      loc_18008679D
0x18008661a  mov     r8d, eax
0x18008661d  lea     rdx, aFidoregcontrol_1; "FidoRegController::FidoRegisterKey"
0x180086624  lea     rcx, aSCannotConvert_0; "%s: Cannot convert the request ID to a "...
0x18008662b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180086630  test    ebx, ebx
0x180086632  jle     short loc_18008663F
0x180086634  movzx   ebx, bx
0x180086637  or      ebx, 80070000h
0x18008663d  test    ebx, ebx
0x18008663f  js      loc_180086C0A
0x180086645  mov     rax, [rbp+60h+StringUuid]
0x180086649  mov     rdx, r12; unsigned __int16 *
0x18008664c  mov     edi, [rbp+60h+arg_40]
0x180086652  mov     rcx, rsi; unsigned __int16 *
0x180086655  mov     r15, [rbp+60h+var_A8]
0x180086659  mov     r13, [rbp+60h+var_B0]
0x18008665d  mov     r9, r15; unsigned __int16 *
0x180086660  mov     r8, [rbp+60h+var_A0]; unsigned __int16 *
0x180086664  mov     dword ptr [rsp+160h+var_120], edi; unsigned int
0x180086668  mov     [rsp+160h+var_128], rax; unsigned __int16 *
0x18008666d  mov     rax, [rbp+60h+var_B8]
0x180086671  mov     [rsp+160h+var_130], rax; unsigned __int16 *
0x180086676  mov     rax, [rbp+60h+var_C0]
0x18008667a  mov     [rsp+160h+var_138], rax; unsigned __int16 *
0x18008667f  mov     [rsp+160h+var_140], r13; unsigned __int16 *
0x180086684  call    ?WriteFidoRegistrationBeginSuccessEvent@Logger@@SAJPEBG0000000K@Z; Logger::WriteFidoRegistrationBeginSuccessEvent(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong)
0x180086689  mov     rax, [rbp+60h+StringUuid]
0x18008668d  lea     rdx, aFidoregcontrol_1; "FidoRegController::FidoRegisterKey"
0x180086694  mov     r9, [rbp+60h+var_A0]
0x180086698  lea     rcx, aSFidoregisterk; "%s: FidoRegisterKey begin succeeded. UP"...
0x18008669f  mov     dword ptr [rsp+160h+var_120], edi
0x1800866a3  mov     r8, r12
0x1800866a6  mov     [rsp+160h+var_128], rax
0x1800866ab  mov     rax, [rbp+60h+var_C0]
0x1800866af  mov     [rsp+160h+var_130], rax
0x1800866b4  mov     [rsp+160h+var_138], r13
0x1800866b9  mov     [rsp+160h+var_140], r15
0x1800866be  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800866c3  mov     eax, cs:dword_18013D150
0x1800866c9  cmp     eax, 4
0x1800866cc  jbe     short loc_18008671B
0x1800866ce  mov     rdx, 400000000000h
0x1800866d8  lea     rcx, dword_18013D150
0x1800866df  call    _tlgKeywordOn
0x1800866e4  test    al, al
0x1800866e6  jz      short loc_18008671B
0x1800866e8  lea     rax, [rbp+60h+var_D8]
0x1800866ec  mov     [rbp+60h+var_D8], ebx
0x1800866ef  mov     [rsp+160h+var_138], rax
0x1800866f4  lea     rdx, byte_18012B1F7
0x1800866fb  lea     rax, [rbp+60h+var_90]
0x1800866ff  mov     [rbp+60h+var_90], 1000000h
0x180086707  xor     r8d, r8d
0x18008670a  mov     [rsp+160h+var_140], rax
0x18008670f  lea     rcx, dword_18013D150
0x180086716  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18008671b  mov     rcx, rsi; Block
0x18008671e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180086723  mov     rcx, [rbp+60h+Block]; Block
0x180086727  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18008672c  mov     rcx, [rbp+60h+lpMem]; lpMem
0x180086730  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180086735  cmp     [rbp+60h+StringUuid], 0
0x18008673a  jz      short loc_180086746
0x18008673c  lea     rcx, [rbp+60h+StringUuid]; String
0x180086740  call    cs:__imp_RpcStringFreeW
0x180086746  mov     eax, ebx
0x180086748  mov     rcx, [rbp+60h+var_48]
0x18008674c  xor     rcx, rsp; StackCookie
0x18008674f  call    __security_check_cookie
0x180086754  add     rsp, 128h
0x18008675b  pop     r15
0x18008675d  pop     r14
0x18008675f  pop     r13
0x180086761  pop     r12
0x180086763  pop     rdi
0x180086764  pop     rsi
0x180086765  pop     rbx
0x180086766  pop     rbp
0x180086767  retn
0x180086768  lea     rcx, [rbp+60h+Uuid]; struct _GUID *
0x18008676c  call    ?CreateGuid@@YAJPEAU_GUID@@@Z; CreateGuid(_GUID *)
0x180086771  mov     ebx, eax
0x180086773  test    eax, eax
0x180086775  jns     loc_180086602
0x18008677b  mov     r9d, eax
0x18008677e  lea     r8, aCreateguid; "CreateGuid"
0x180086785  lea     rdx, aFidoregcontrol_1; "FidoRegController::FidoRegisterKey"
0x18008678c  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180086793  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180086798  jmp     loc_180086C0A
0x18008679d  mov     rcx, r12; unsigned __int16 *
0x1800867a0  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x1800867a5  xor     ebx, ebx
0x1800867a7  test    eax, eax
0x1800867a9  jz      short loc_1800867E2
0x1800867ab  lea     r8, aPcszuseremail; "pcszUserEmail"
0x1800867b2  mov     ebx, 80070057h
0x1800867b7  lea     rdx, aFidoregcontrol_1; "FidoRegController::FidoRegisterKey"
0x1800867be  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null or empty."
0x1800867c5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800867ca  lea     rdx, aPcszuseremail; "pcszUserEmail"
0x1800867d1  lea     rcx, aFidoregcontrol_1; "FidoRegController::FidoRegisterKey"
0x1800867d8  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x1800867dd  jmp     loc_180086C0A
0x1800867e2  mov     rcx, [rbp+60h+var_B8]; unsigned __int16 *
0x1800867e6  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x1800867eb  test    eax, eax
0x1800867ed  jz      short loc_180086817
0x1800867ef  lea     r8, aPcszauthtoken; "pcszAuthToken"
0x1800867f6  mov     ebx, 80070057h
0x1800867fb  lea     rdx, aFidoregcontrol_1; "FidoRegController::FidoRegisterKey"
0x180086802  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null or empty."
0x180086809  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008680e  lea     rdx, aPcszauthtoken; "pcszAuthToken"
0x180086815  jmp     short loc_1800867D1
0x180086817  mov     rcx, rdi; unsigned __int16 *
0x18008681a  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18008681f  test    eax, eax
0x180086821  jz      short loc_18008684B
0x180086823  lea     r8, aPwsztenantid; "pwszTenantId"
0x18008682a  mov     ebx, 80070057h
0x18008682f  lea     rdx, aFidoregcontrol_1; "FidoRegController::FidoRegisterKey"
0x180086836  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null or empty."
0x18008683d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180086842  lea     rdx, aPwsztenantid; "pwszTenantId"
0x180086849  jmp     short loc_1800867D1
0x18008684b  mov     r12, [rbp+60h+arg_48]
0x180086852  test    r12, r12
0x180086855  jnz     short loc_18008688E
0x180086857  lea     r8, aPfncallback; "pfnCallback"
0x18008685e  mov     ebx, 80070057h
0x180086863  lea     rdx, aFidoregcontrol_1; "FidoRegController::FidoRegisterKey"
0x18008686a  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180086871  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180086876  lea     rdx, aPfncallback; "pfnCallback"
0x18008687d  lea     rcx, aFidoregcontrol_1; "FidoRegController::FidoRegisterKey"
0x180086884  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180086889  jmp     loc_180086C06
0x18008688e  test    r14, r14
0x180086891  jnz     short loc_1800868BB
0x180086893  lea     r8, aPregistrationi_0; "pRegistrationInfo"
0x18008689a  mov     ebx, 80070057h
0x18008689f  lea     rdx, aFidoregcontrol_1; "FidoRegController::FidoRegisterKey"
0x1800868a6  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x1800868ad  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800868b2  lea     rdx, aPregistrationi_0; "pRegistrationInfo"
0x1800868b9  jmp     short loc_18008687D
0x1800868bb  mov     rcx, [r14+60h]; unsigned __int16 *
0x1800868bf  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x1800868c4  test    eax, eax
0x1800868c6  jz      short loc_1800868F0
0x1800868c8  lea     r8, aPregistrationi_2; "pRegistrationInfo->pszWebAuthNEndpointR"...
0x1800868cf  mov     ebx, 80070057h
0x1800868d4  lea     rdx, aFidoregcontrol_1; "FidoRegController::FidoRegisterKey"
0x1800868db  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null or empty."
0x1800868e2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800868e7  lea     rdx, aPregistrationi_2; "pRegistrationInfo->pszWebAuthNEndpointR"...
0x1800868ee  jmp     short loc_18008687D
0x1800868f0  mov     rcx, [r14+58h]; unsigned __int16 *
0x1800868f4  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x1800868f9  test    eax, eax
0x1800868fb  jz      short loc_180086928
0x1800868fd  lea     r8, aPregistrationi_1; "pRegistrationInfo->pszWebAuthNServiceVe"...
0x180086904  mov     ebx, 80070057h
0x180086909  lea     rdx, aFidoregcontrol_1; "FidoRegController::FidoRegisterKey"
0x180086910  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null or empty."
0x180086917  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008691c  lea     rdx, aPregistrationi_1; "pRegistrationInfo->pszWebAuthNServiceVe"...
0x180086923  jmp     loc_18008687D
0x180086928  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008692f  mov     ecx, 28h ; '('; unsigned __int64
0x180086934  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180086939  mov     [rbp+60h+var_60], rax
0x18008693d  mov     rdi, rax
0x180086940  test    rax, rax
0x180086943  jz      loc_180086BEE
0x180086949  mov     [rdi+8], ebx
0x18008694c  lea     rax, ??_7FidoRegController@@6B@; const FidoRegController::`vftable'
0x180086953  mov     [rdi], rax
0x180086956  mov     [rdi+10h], rbx
0x18008695a  mov     [rdi+18h], rbx
0x18008695e  test    rdi, rdi
0x180086961  jz      loc_180086BEE
0x180086967  mov     rcx, [rbp+60h+StringUuid]; unsigned __int16 *
0x18008696b  lea     rdx, [rdi+18h]; unsigned __int16 **
0x18008696f  xor     r8d, r8d; int
0x180086972  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x180086977  mov     ebx, eax
0x180086979  test    eax, eax
0x18008697b  jns     short loc_18008699F
0x18008697d  mov     r9d, eax
0x180086980  lea     r8, aStringdup; "StringDup"
0x180086987  lea     rdx, aFidoregcontrol_1; "FidoRegController::FidoRegisterKey"
0x18008698e  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180086995  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008699a  jmp     loc_180086BD5
0x18008699f  mov     eax, [rbp+60h+arg_40]
0x1800869a5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800869ac  mov     ecx, 18h; unsigned __int64
0x1800869b1  mov     [rdi+20h], eax
0x1800869b4  mov     dword ptr [rdi+8], 1
0x1800869bb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800869c0  mov     r13, rax
0x1800869c3  test    rax, rax
0x1800869c6  jz      loc_180086BBD
0x1800869cc  mov     [rax], r12
0x1800869cf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800869d6  mov     rax, [rbp+60h+arg_50]
0x1800869dd  mov     ecx, 0D0h; unsigned __int64
0x1800869e2  mov     [r13+8], rax
0x1800869e6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800869eb  mov     [rbp+60h+var_60], rax
0x1800869ef  test    rax, rax
0x1800869f2  jz      loc_180086BBD
0x1800869f8  mov     rcx, rax; this
0x1800869fb  call    ??0FidoHttpRequest@@QEAA@XZ; FidoHttpRequest::FidoHttpRequest(void)
0x180086a00  mov     r15, rax
0x180086a03  test    rax, rax
0x180086a06  jz      loc_180086BBD
0x180086a0c  mov     r12, [rbp+60h+var_E0]
0x180086a10  lea     r8, [rbp+60h+lpMem]; unsigned __int16 **
0x180086a14  mov     rdx, r12; unsigned __int16 *
0x180086a17  mov     rcx, r14; struct _DISCOVERY_METADATA *
0x180086a1a  call    ?GetPostEndpoint@FidoRegController@@CAJPEAU_DISCOVERY_METADATA@@PEBGPEAPEAG@Z; FidoRegController::GetPostEndpoint(_DISCOVERY_METADATA *,ushort const *,ushort * *)
0x180086a1f  mov     ebx, eax
0x180086a21  test    eax, eax
0x180086a23  jns     short loc_180086A31
0x180086a25  lea     r8, aFidoregcontrol_2; "FidoRegController::GetPostEndpoint"
0x180086a2c  jmp     loc_180086B79
0x180086a31  mov     rcx, [r14+20h]; unsigned __int16 *
0x180086a35  lea     r9, [rbp+60h+Block]; unsigned __int16 **
0x180086a39  lea     r8, [rbp+60h+lpString1]; unsigned __int16 **
0x180086a3d  lea     rdx, [rbp+60h+var_E0]; int *
0x180086a41  call    ?ParseUrl@@YAJPEBGPEAHPEAPEAG2@Z; ParseUrl(ushort const *,int *,ushort * *,ushort * *)
0x180086a46  mov     ebx, eax
0x180086a48  test    eax, eax
0x180086a4a  jns     short loc_180086A55
0x180086a4c  lea     r8, aParseurl; "ParseUrl"
0x180086a53  jmp     short loc_180086ABC
0x180086a55  mov     rsi, [rbp+60h+lpString1]
0x180086a59  lea     r9, [rbp+60h+var_D8]; int *
0x180086a5d  mov     rcx, rsi; lpString1
0x180086a60  lea     rdx, aLoginMicrosoft; "login.microsoftonline.com"
0x180086a67  mov     r8d, 1; unsigned int
  ... truncated ...
```
