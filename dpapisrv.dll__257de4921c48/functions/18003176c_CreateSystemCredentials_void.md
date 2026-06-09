# CreateSystemCredentials(void)

- ea: `0x18003176c`
- end: `0x1800318a2`
- name: `?CreateSystemCredentials@@YAHXZ`
- size: `310`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001aaac`
- `0x180032674`
- `0x180035b68`
- `0x180035bb4`

## callees

- `0x180007f10`
- `0x18001d810`
- `0x180029e7c`
- `0x18003176c`
- `0x180032898`
- `0x1800367a4`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x1800317b8`
- `bcrypt!BCryptGenRandom` at `0x1800317b8`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180031843`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180031843`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x180031831`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x180031831`

## string_xrefs

- `0x1800317da`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`

## pseudocode

```c
__int64 CreateSystemCredentials(void)
{
  __int64 v0; // r9
  const char *v1; // rdx
  __int64 v2; // rcx
  unsigned __int16 *v4; // rcx
  NTSTATUS v5; // ebx
  __int64 v6; // rcx
  LSA_HANDLE PolicyHandle; // [rsp+20h] [rbp-60h] BYREF
  struct _LSA_UNICODE_STRING PrivateData; // [rsp+28h] [rbp-58h] BYREF
  struct _LSA_UNICODE_STRING KeyName; // [rsp+38h] [rbp-48h] BYREF
  UCHAR pbBuffer[16]; // [rsp+48h] [rbp-38h] BYREF
  _BYTE v11[28]; // [rsp+58h] [rbp-28h] BYREF

  memset(v11, 0, sizeof(v11));
  PolicyHandle = 0;
  *(_OWORD *)pbBuffer = 0;
  KeyName = 0;
  PrivateData = 0;
  if ( BCryptGenRandom(0, pbBuffer, 0x2Cu, 2u) < 0 )
  {
    v0 = 2813;
    v1 = "E_FAIL";
    v2 = 2147500037LL;
LABEL_3:
    DebugTraceError(v2, v1, "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", v0);
    return 0;
  }
  *(_DWORD *)pbBuffer = 1;
  InitLsaString((struct _UNICODE_STRING *)&KeyName, L"DPAPI_SYSTEM");
  *(_DWORD *)&PrivateData.Length = 2883628;
  PrivateData.Buffer = (PWSTR)pbBuffer;
  if ( OpenPolicy(v4, 0x20u, &PolicyHandle) < 0 )
    return 0;
  v5 = LsaStorePrivateData(PolicyHandle, &KeyName, &PrivateData);
  LsaClose(PolicyHandle);
  if ( v5 < 0 )
  {
    if ( (Microsoft_Windows_Crypto_DPAPIEnableBits & 0x10) != 0 )
      McTemplateU0d_EtwEventWriteTransfer(v6, ETW_LOG_SYSTEM_CREDENTIALS_LSASS_CREATION_FAILED, (unsigned int)v5);
    v0 = 2844;
    v1 = "Status";
    v2 = (unsigned int)v5;
    goto LABEL_3;
  }
  return 1;
}

```

## disassembly

```asm
0x18003176c  mov     [rsp-8+arg_0], rbx
0x180031771  push    rbp
0x180031772  mov     rbp, rsp
0x180031775  sub     rsp, 80h
0x18003177c  mov     rax, cs:__security_cookie
0x180031783  xor     rax, rsp
0x180031786  mov     [rbp+var_8], rax
0x18003178a  xorps   xmm0, xmm0
0x18003178d  lea     rdx, [rbp+pbBuffer]; pbBuffer
0x180031791  xor     eax, eax
0x180031793  xorps   xmm1, xmm1
0x180031796  movups  xmmword ptr [rbp+var_28], xmm0
0x18003179a  xor     ecx, ecx; hAlgorithm
0x18003179c  mov     [rbp+PolicyHandle], rax
0x1800317a0  movups  xmmword ptr [rbp+pbBuffer], xmm0
0x1800317a4  lea     r8d, [rax+2Ch]; cbBuffer
0x1800317a8  lea     r9d, [rax+2]; dwFlags
0x1800317ac  movups  xmmword ptr [rbp+var_28+0Ch], xmm0
0x1800317b0  movups  xmmword ptr [rbp+KeyName.Length], xmm0
0x1800317b4  movups  xmmword ptr [rbp+PrivateData.Length], xmm1
0x1800317b8  call    cs:__imp_BCryptGenRandom
0x1800317bf  nop     dword ptr [rax+rax+00h]
0x1800317c4  test    eax, eax
0x1800317c6  jns     short loc_1800317ED
0x1800317c8  mov     r9d, 0AFDh
0x1800317ce  lea     rdx, aEFail; "E_FAIL"
0x1800317d5  mov     ecx, 80004005h
0x1800317da  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800317e1  call    DebugTraceError
0x1800317e6  xor     eax, eax
0x1800317e8  jmp     loc_180031884
0x1800317ed  lea     rdx, aDpapiSystem; "DPAPI_SYSTEM"
0x1800317f4  mov     dword ptr [rbp+pbBuffer], 1
0x1800317fb  lea     rcx, [rbp+KeyName]; struct _UNICODE_STRING *
0x1800317ff  call    ?InitLsaString@@YAXPEAU_UNICODE_STRING@@PEAG@Z; InitLsaString(_UNICODE_STRING *,ushort *)
0x180031804  lea     rax, [rbp+pbBuffer]
0x180031808  mov     dword ptr [rbp+PrivateData.Length], 2C002Ch
0x18003180f  lea     r8, [rbp+PolicyHandle]; void **
0x180031813  mov     [rbp+PrivateData.Buffer], rax
0x180031817  mov     edx, 20h ; ' '; unsigned int
0x18003181c  call    ?OpenPolicy@@YAJPEAGKPEAPEAX@Z; OpenPolicy(ushort *,ulong,void * *)
0x180031821  test    eax, eax
0x180031823  js      short loc_1800317E6
0x180031825  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x180031829  lea     r8, [rbp+PrivateData]; PrivateData
0x18003182d  lea     rdx, [rbp+KeyName]; KeyName
0x180031831  call    cs:__imp_LsaStorePrivateData
0x180031838  nop     dword ptr [rax+rax+00h]
0x18003183d  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x180031841  mov     ebx, eax
0x180031843  call    cs:__imp_LsaClose
0x18003184a  nop     dword ptr [rax+rax+00h]
0x18003184f  test    ebx, ebx
0x180031851  jns     short loc_18003187F
0x180031853  test    cs:Microsoft_Windows_Crypto_DPAPIEnableBits, 10h
0x18003185a  jz      short loc_18003186B
0x18003185c  mov     r8d, ebx
0x18003185f  lea     rdx, ETW_LOG_SYSTEM_CREDENTIALS_LSASS_CREATION_FAILED
0x180031866  call    McTemplateU0d_EtwEventWriteTransfer
0x18003186b  mov     r9d, 0B1Ch
0x180031871  lea     rdx, aStatus; "Status"
0x180031878  mov     ecx, ebx
0x18003187a  jmp     loc_1800317DA
0x18003187f  mov     eax, 1
0x180031884  mov     rcx, [rbp+var_8]
0x180031888  xor     rcx, rsp; StackCookie
0x18003188b  call    __security_check_cookie
0x180031890  mov     rbx, [rsp+80h+arg_0]
0x180031898  add     rsp, 80h
0x18003189f  pop     rbp
0x1800318a0  retn
```
