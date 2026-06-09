# InitSecurityInterfaceW

- ea: `0x1800019b0`
- end: `0x180001b44`
- name: `InitSecurityInterfaceW`
- size: `404`
- prototype: `PSecurityFunctionTableW __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## pseudocode

```c
PSecurityFunctionTableW __stdcall InitSecurityInterfaceW()
{
  PSecurityFunctionTableW result; // rax

  CREDSSPFnTableW.dwVersion = 3;
  qword_1800076A8 = (__int64)SpAcceptSecurityContext;
  qword_180007740 = (__int64)SpDecryptMessage;
  qword_180007688 = (__int64)SpAcquireCredentialsHandleW;
  qword_180007738 = (__int64)SpEncryptMessage;
  qword_180007720 = (__int64)SpCompleteAuthToken;
  qword_1800076C0 = (__int64)SpApplyControlToken;
  qword_180007758 = (__int64)SpCompleteAuthToken;
  qword_1800076B0 = (__int64)SpCompleteAuthToken;
  qword_1800076B8 = (__int64)SpDeleteSecurityContext;
  qword_180007678 = (__int64)SpEnumerateSecurityPackagesW;
  qword_180007710 = (__int64)SpCompleteAuthToken;
  qword_1800076F0 = (__int64)SpFreeContextBuffer;
  qword_180007690 = (__int64)SpFreeCredentialsHandle;
  qword_1800076D0 = (__int64)SpImpersonateSecurityContext;
  qword_180007718 = (__int64)SpCompleteAuthToken;
  qword_1800076A0 = (__int64)SpInitializeSecurityContextW;
  qword_1800076E0 = (__int64)SpMakeSignature;
  qword_1800076C8 = (__int64)SpQueryContextAttributesW;
  qword_180007680 = (__int64)SpCompleteAuthToken;
  qword_180007730 = (__int64)SpQuerySecurityContextToken;
  qword_1800076F8 = (__int64)SpQuerySecurityPackageInfoW;
  qword_1800076D8 = (__int64)SpRevertSecurityContext;
  qword_180007748 = (__int64)SpCompleteAuthToken;
  qword_180007750 = (__int64)SpSetCredentialsAttributesW;
  qword_1800076E8 = (__int64)SpVerifySignature;
  result = &CREDSSPFnTableW;
  qword_180007698 = 0;
  qword_180007700 = (__int64)SpEncryptMessage;
  qword_180007708 = (__int64)SpDecryptMessage;
  qword_180007728 = 0;
  return result;
}

```

## disassembly

```asm
0x1800019b0  lea     rax, SpAcceptSecurityContext
0x1800019b7  mov     cs:?CREDSSPFnTableW@@3U_SECURITY_FUNCTION_TABLE_W@@A, 3; _SECURITY_FUNCTION_TABLE_W CREDSSPFnTableW
0x1800019c1  mov     cs:qword_1800076A8, rax
0x1800019c8  lea     rdx, SpDecryptMessage
0x1800019cf  lea     rax, SpAcquireCredentialsHandleW
0x1800019d6  mov     cs:qword_180007740, rdx
0x1800019dd  mov     cs:qword_180007688, rax
0x1800019e4  lea     rcx, SpEncryptMessage
0x1800019eb  lea     rax, SpCompleteAuthToken
0x1800019f2  mov     cs:qword_180007738, rcx
0x1800019f9  mov     cs:qword_180007720, rax
0x180001a00  lea     rax, SpApplyControlToken
0x180001a07  mov     cs:qword_1800076C0, rax
0x180001a0e  lea     rax, SpCompleteAuthToken
0x180001a15  mov     cs:qword_180007758, rax
0x180001a1c  lea     rax, SpCompleteAuthToken
0x180001a23  mov     cs:qword_1800076B0, rax
0x180001a2a  lea     rax, SpDeleteSecurityContext
0x180001a31  mov     cs:qword_1800076B8, rax
0x180001a38  lea     rax, SpEnumerateSecurityPackagesW
0x180001a3f  mov     cs:qword_180007678, rax
0x180001a46  lea     rax, SpCompleteAuthToken
0x180001a4d  mov     cs:qword_180007710, rax
0x180001a54  lea     rax, SpFreeContextBuffer
0x180001a5b  mov     cs:qword_1800076F0, rax
0x180001a62  lea     rax, SpFreeCredentialsHandle
0x180001a69  mov     cs:qword_180007690, rax
0x180001a70  lea     rax, SpImpersonateSecurityContext
0x180001a77  mov     cs:qword_1800076D0, rax
0x180001a7e  lea     rax, SpCompleteAuthToken
0x180001a85  mov     cs:qword_180007718, rax
0x180001a8c  lea     rax, SpInitializeSecurityContextW
0x180001a93  mov     cs:qword_1800076A0, rax
0x180001a9a  lea     rax, SpMakeSignature
0x180001aa1  mov     cs:qword_1800076E0, rax
0x180001aa8  lea     rax, SpQueryContextAttributesW
0x180001aaf  mov     cs:qword_1800076C8, rax
0x180001ab6  lea     rax, SpCompleteAuthToken
0x180001abd  mov     cs:qword_180007680, rax
0x180001ac4  lea     rax, SpQuerySecurityContextToken
0x180001acb  mov     cs:qword_180007730, rax
0x180001ad2  lea     rax, SpQuerySecurityPackageInfoW
0x180001ad9  mov     cs:qword_1800076F8, rax
0x180001ae0  lea     rax, SpRevertSecurityContext
0x180001ae7  mov     cs:qword_1800076D8, rax
0x180001aee  lea     rax, SpCompleteAuthToken
0x180001af5  mov     cs:qword_180007748, rax
0x180001afc  lea     rax, SpSetCredentialsAttributesW
0x180001b03  mov     cs:qword_180007750, rax
0x180001b0a  lea     rax, SpVerifySignature
0x180001b11  mov     cs:qword_1800076E8, rax
0x180001b18  lea     rax, ?CREDSSPFnTableW@@3U_SECURITY_FUNCTION_TABLE_W@@A; _SECURITY_FUNCTION_TABLE_W CREDSSPFnTableW
0x180001b1f  mov     cs:qword_180007698, 0
0x180001b2a  mov     cs:qword_180007700, rcx
0x180001b31  mov     cs:qword_180007708, rdx
0x180001b38  mov     cs:qword_180007728, 0
0x180001b43  retn
```
