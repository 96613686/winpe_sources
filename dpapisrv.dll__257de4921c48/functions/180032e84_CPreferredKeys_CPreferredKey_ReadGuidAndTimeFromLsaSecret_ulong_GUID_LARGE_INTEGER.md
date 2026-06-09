# CPreferredKeys::CPreferredKey::ReadGuidAndTimeFromLsaSecret(ulong,_GUID *,_LARGE_INTEGER *)

- ea: `0x180032e84`
- end: `0x180033089`
- name: `?ReadGuidAndTimeFromLsaSecret@CPreferredKey@CPreferredKeys@@SAJKPEAU_GUID@@PEAT_LARGE_INTEGER@@@Z`
- size: `517`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct _GUID *, union _LARGE_INTEGER *)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180032cb4`
- `0x180033090`
- `0x180035320`

## callees

- `0x180007f10`
- `0x18000e420`
- `0x18002f914`
- `0x180032898`
- `0x180032e84`
- `0x1800367a4`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenSecret` at `0x180032f4f`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenSecret` at `0x180032f4f`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQuerySecret` at `0x180032f8d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQuerySecret` at `0x180032f8d`

## string_xrefs

- `0x180032eb0`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x180032ef4`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x180032fa5`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x180032ff7`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x180033041`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`

## pseudocode

```c
__int64 __fastcall CPreferredKeys::CPreferredKey::ReadGuidAndTimeFromLsaSecret(
        unsigned __int16 *a1,
        struct _GUID *a2,
        union _LARGE_INTEGER *a3)
{
  int v5; // r14d
  NTSTATUS v7; // eax
  NTSTATUS v8; // ebx
  unsigned __int16 *v9; // rdx
  NTSTATUS v10; // eax
  PLSA_UNICODE_STRING v11; // rcx
  PWSTR v12; // rax
  __int64 Length; // rdx
  _BYTE *Buffer; // rax
  PVOID SecretHandle; // [rsp+30h] [rbp-30h] BYREF
  PLSA_UNICODE_STRING CurrentValue; // [rsp+38h] [rbp-28h] BYREF
  union _LARGE_INTEGER CurrentValueSetTime; // [rsp+40h] [rbp-20h] BYREF
  struct _LSA_UNICODE_STRING SecretName; // [rsp+48h] [rbp-18h] BYREF
  LSA_HANDLE PolicyHandle; // [rsp+98h] [rbp+38h] BYREF

  v5 = (int)a1;
  if ( (unsigned int)((_DWORD)a1 - 1) <= 1 )
  {
    PolicyHandle = 0;
    v7 = OpenPolicy(a1, 4u, &PolicyHandle);
    v8 = v7;
    if ( v7 >= 0 )
    {
      SecretName = 0;
      v9 = L"G$BCKUPKEY_P";
      if ( v5 != 1 )
        v9 = L"G$BCKUPKEY_PREFERRED";
      InitLsaString((struct _UNICODE_STRING *)&SecretName, v9);
      SecretHandle = 0;
      v8 = LsaOpenSecret(PolicyHandle, &SecretName, 2u, &SecretHandle);
      if ( v8 >= 0 )
      {
        CurrentValue = 0;
        CurrentValueSetTime.QuadPart = 0;
        v10 = LsaQuerySecret(SecretHandle, &CurrentValue, &CurrentValueSetTime, 0, 0);
        v8 = v10;
        if ( v10 >= 0 )
        {
          v11 = CurrentValue;
          if ( CurrentValue && (v12 = CurrentValue->Buffer) != 0 )
          {
            if ( CurrentValue->Length == 16 )
            {
              if ( a2 )
                *a2 = *(struct _GUID *)v12;
              if ( a3 )
                *a3 = CurrentValueSetTime;
            }
            else
            {
              DebugTraceError(
                3221225990LL,
                "STATUS_INVALID_BUFFER_SIZE",
                "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp",
                3734);
              v8 = -1073741306;
              v11 = CurrentValue;
            }
            Length = v11->Length;
            Buffer = v11->Buffer;
            if ( v11->Length )
            {
              do
              {
                *Buffer++ = 0;
                --Length;
              }
              while ( Length );
              v11 = CurrentValue;
            }
            MIDL_user_free(v11);
          }
          else
          {
            DebugTraceError(
              3221225485LL,
              "STATUS_INVALID_PARAMETER",
              "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp",
              3742);
            v8 = -1073741811;
          }
        }
        else
        {
          DebugTraceError(
            (unsigned int)v10,
            "status",
            "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp",
            3715);
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&SecretHandle);
    }
    else
    {
      DebugTraceError(
        (unsigned int)v7,
        "status",
        "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp",
        3696);
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&PolicyHandle);
    return (unsigned int)v8;
  }
  else
  {
    DebugTraceError(
      3221225485LL,
      "STATUS_INVALID_PARAMETER",
      "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp",
      3688);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x180032e84  mov     [rsp-18h+arg_0], rbx
0x180032e89  mov     [rsp-18h+arg_8], rsi
0x180032e8e  push    rbp
0x180032e8f  push    rdi
0x180032e90  push    r14
0x180032e92  mov     rbp, rsp
0x180032e95  sub     rsp, 60h
0x180032e99  mov     rdi, r8
0x180032e9c  mov     rsi, rdx
0x180032e9f  mov     r14d, ecx
0x180032ea2  lea     eax, [rcx-1]
0x180032ea5  cmp     eax, 1
0x180032ea8  jbe     short loc_180032ED2
0x180032eaa  mov     r9d, 0E68h
0x180032eb0  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180032eb7  lea     rdx, aStatusInvalidP; "STATUS_INVALID_PARAMETER"
0x180032ebe  mov     ecx, 0C000000Dh
0x180032ec3  call    DebugTraceError
0x180032ec8  mov     eax, 0C000000Dh
0x180032ecd  jmp     loc_180033073
0x180032ed2  mov     [rbp+PolicyHandle], 0
0x180032eda  lea     r8, [rbp+PolicyHandle]; void **
0x180032ede  mov     edx, 4; unsigned int
0x180032ee3  call    ?OpenPolicy@@YAJPEAGKPEAPEAX@Z; OpenPolicy(ushort *,ulong,void * *)
0x180032ee8  mov     ebx, eax
0x180032eea  test    eax, eax
0x180032eec  jns     short loc_180032F0E
0x180032eee  mov     r9d, 0E70h
0x180032ef4  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180032efb  lea     rdx, aStatus_0; "status"
0x180032f02  mov     ecx, eax
0x180032f04  call    DebugTraceError
0x180032f09  jmp     loc_180033068
0x180032f0e  xorps   xmm0, xmm0
0x180032f11  movups  xmmword ptr [rbp+SecretName.Length], xmm0
0x180032f15  lea     rax, aGBckupkeyPrefe; "G$BCKUPKEY_PREFERRED"
0x180032f1c  lea     rdx, aGBckupkeyP; "G$BCKUPKEY_P"
0x180032f23  cmp     r14d, 1
0x180032f27  cmovnz  rdx, rax; unsigned __int16 *
0x180032f2b  lea     rcx, [rbp+SecretName]; struct _UNICODE_STRING *
0x180032f2f  call    ?InitLsaString@@YAXPEAU_UNICODE_STRING@@PEAG@Z; InitLsaString(_UNICODE_STRING *,ushort *)
0x180032f34  nop
0x180032f35  mov     [rbp+SecretHandle], 0
0x180032f3d  lea     r9, [rbp+SecretHandle]; SecretHandle
0x180032f41  mov     r8d, 2; DesiredAccess
0x180032f47  lea     rdx, [rbp+SecretName]; SecretName
0x180032f4b  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x180032f4f  call    cs:__imp_LsaOpenSecret
0x180032f56  nop     dword ptr [rax+rax+00h]
0x180032f5b  mov     ebx, eax
0x180032f5d  test    eax, eax
0x180032f5f  js      loc_18003305E
0x180032f65  mov     [rbp+CurrentValue], 0
0x180032f6d  mov     qword ptr [rbp+CurrentValueSetTime], 0
0x180032f75  mov     [rsp+60h+OldValueSetTime], 0; OldValueSetTime
0x180032f7e  xor     r9d, r9d; OldValue
0x180032f81  lea     r8, [rbp+CurrentValueSetTime]; CurrentValueSetTime
0x180032f85  lea     rdx, [rbp+CurrentValue]; CurrentValue
0x180032f89  mov     rcx, [rbp+SecretHandle]; SecretHandle
0x180032f8d  call    cs:__imp_LsaQuerySecret
0x180032f94  nop     dword ptr [rax+rax+00h]
0x180032f99  mov     ebx, eax
0x180032f9b  test    eax, eax
0x180032f9d  jns     short loc_180032FBF
0x180032f9f  mov     r9d, 0E83h
0x180032fa5  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180032fac  lea     rdx, aStatus_0; "status"
0x180032fb3  mov     ecx, eax
0x180032fb5  call    DebugTraceError
0x180032fba  jmp     loc_18003305E
0x180032fbf  mov     rcx, [rbp+CurrentValue]
0x180032fc3  test    rcx, rcx
0x180032fc6  jz      short loc_18003303B
0x180032fc8  mov     rax, [rcx+8]
0x180032fcc  test    rax, rax
0x180032fcf  jz      short loc_18003303B
0x180032fd1  cmp     word ptr [rcx], 10h
0x180032fd5  jnz     short loc_180032FF1
0x180032fd7  test    rsi, rsi
0x180032fda  jz      short loc_180032FE3
0x180032fdc  movups  xmm0, xmmword ptr [rax]
0x180032fdf  movdqu  xmmword ptr [rsi], xmm0
0x180032fe3  test    rdi, rdi
0x180032fe6  jz      short loc_180033018
0x180032fe8  mov     rax, qword ptr [rbp+CurrentValueSetTime]
0x180032fec  mov     [rdi], rax
0x180032fef  jmp     short loc_180033018
0x180032ff1  mov     r9d, 0E96h
0x180032ff7  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180032ffe  lea     rdx, aStatusInvalidB; "STATUS_INVALID_BUFFER_SIZE"
0x180033005  mov     ecx, 0C0000206h
0x18003300a  call    DebugTraceError
0x18003300f  mov     ebx, 0C0000206h
0x180033014  mov     rcx, [rbp+CurrentValue]
0x180033018  movzx   edx, word ptr [rcx]
0x18003301b  mov     rax, [rcx+8]
0x18003301f  test    rdx, rdx
0x180033022  jz      short loc_180033034
0x180033024  mov     byte ptr [rax], 0
0x180033027  inc     rax
0x18003302a  sub     rdx, 1
0x18003302e  jnz     short loc_180033024
0x180033030  mov     rcx, [rbp+CurrentValue]; void *
0x180033034  call    MIDL_user_free
0x180033039  jmp     short loc_18003305E
0x18003303b  mov     r9d, 0E9Eh
0x180033041  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180033048  lea     rdx, aStatusInvalidP; "STATUS_INVALID_PARAMETER"
0x18003304f  mov     ecx, 0C000000Dh
0x180033054  call    DebugTraceError
0x180033059  mov     ebx, 0C000000Dh
0x18003305e  lea     rcx, [rbp+SecretHandle]
0x180033062  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180033067  nop
0x180033068  lea     rcx, [rbp+PolicyHandle]
0x18003306c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180033071  mov     eax, ebx
0x180033073  lea     r11, [rsp+60h+var_s0]
0x180033078  mov     rbx, [r11+20h]
0x18003307c  mov     rsi, [r11+28h]
0x180033080  mov     rsp, r11
0x180033083  pop     r14
0x180033085  pop     rdi
0x180033086  pop     rbp
0x180033087  retn
```
