# EapCreateEaphostUserPreoperties

- ea: `0x180038f5c`
- end: `0x18003908d`
- name: `EapCreateEaphostUserPreoperties`
- size: `305`
- prototype: `__int64 __fastcall(EAP_METHOD_TYPE *, DWORD, unsigned int, __int64, DWORD dwEapConnDataSize, BYTE *pbEapConnData, DWORD pdwUserBlobSize, BYTE *pData, DWORD *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180032488`

## callees

- `0x1800030fc`
- `0x180038f5c`
- `0x1800390ec`
- `0x1800391b0`

## import_xrefs

- `MobileNetworking!AllocateMemory` at `0x18003902a`
- `MobileNetworking!AllocateMemory` at `0x18003902a`
- `eappcfg!EapHostPeerFreeMemory` at `0x180039075`
- `eappcfg!EapHostPeerFreeMemory` at `0x180039075`
- `eappcfg!EapHostPeerQueryUserBlobFromCredentialInputFields` at `0x18003900b`
- `eappcfg!EapHostPeerQueryUserBlobFromCredentialInputFields` at `0x18003900b`
- `eappcfg!EapHostPeerFreeErrorMemory` at `0x180039054`
- `eappcfg!EapHostPeerFreeErrorMemory` at `0x180039054`

## string_xrefs

- `0x18003901a`: `EapCreateEaphostUserPreoperties`

## pseudocode

```c
__int64 __fastcall EapCreateEaphostUserPreoperties(
        EAP_METHOD_TYPE *a1,
        DWORD a2,
        unsigned int a3,
        __int64 a4,
        DWORD dwEapConnDataSize,
        BYTE *pbEapConnData,
        DWORD pdwUserBlobSize,
        BYTE *pData,
        DWORD *a9,
        void **a10)
{
  void **v10; // rdi
  DWORD *v11; // rsi
  DWORD Memory; // ebx
  EAP_ERROR *pEapError; // [rsp+50h] [rbp-31h] BYREF
  EAP_CONFIG_INPUT_FIELD_ARRAY pEapConfigInputFieldArray; // [rsp+60h] [rbp-21h] BYREF
  EAP_METHOD_TYPE eapMethodType; // [rsp+70h] [rbp-11h] BYREF

  v10 = a10;
  v11 = a9;
  pEapError = 0;
  pData = 0;
  *a10 = 0;
  *v11 = 0;
  pdwUserBlobSize = 0;
  pEapConfigInputFieldArray = 0;
  Memory = EapMapToEapConfigArray(a3, a4, &pEapConfigInputFieldArray);
  if ( !Memory )
  {
    eapMethodType = *a1;
    Memory = EapHostPeerQueryUserBlobFromCredentialInputFields(
               0,
               &eapMethodType,
               a2,
               dwEapConnDataSize,
               pbEapConnData,
               &pEapConfigInputFieldArray,
               &pdwUserBlobSize,
               &pData,
               &pEapError);
    if ( !Memory )
    {
      Memory = AllocateMemory(pdwUserBlobSize, v10, "EapCreateEaphostUserPreoperties", 227);
      if ( !Memory )
      {
        memcpy_0(*v10, pData, pdwUserBlobSize);
        *v11 = pdwUserBlobSize;
      }
    }
  }
  if ( pEapError )
    EapHostPeerFreeErrorMemory(pEapError);
  eapMethodType = (EAP_METHOD_TYPE)pEapConfigInputFieldArray;
  EapFreeEapConfigArray(&eapMethodType);
  if ( pData )
    EapHostPeerFreeMemory(pData);
  return Memory;
}

```

## disassembly

```asm
0x180038f5c  push    rbp
0x180038f5e  push    rbx
0x180038f5f  push    rsi
0x180038f60  push    rdi
0x180038f61  push    r14
0x180038f63  push    r15
0x180038f65  lea     rbp, [rsp-7]
0x180038f6a  sub     rsp, 88h
0x180038f71  mov     rdi, [rbp+2Fh+arg_48]
0x180038f78  mov     eax, r8d
0x180038f7b  mov     rsi, [rbp+2Fh+arg_40]
0x180038f7f  lea     r8, [rbp+2Fh+var_50]
0x180038f83  mov     r14d, edx
0x180038f86  mov     [rbp+2Fh+pEapError], 0
0x180038f8e  mov     r15, rcx
0x180038f91  mov     [rbp+2Fh+pData], 0
0x180038f99  xorps   xmm0, xmm0
0x180038f9c  mov     qword ptr [rdi], 0
0x180038fa3  mov     rdx, r9
0x180038fa6  mov     dword ptr [rsi], 0
0x180038fac  mov     ecx, eax
0x180038fae  mov     [rbp+2Fh+arg_30], 0
0x180038fb5  movups  xmmword ptr [rbp+2Fh+var_50.dwVersion], xmm0
0x180038fb9  call    EapMapToEapConfigArray
0x180038fbe  mov     ebx, eax
0x180038fc0  test    eax, eax
0x180038fc2  jnz     loc_18003904B
0x180038fc8  movups  xmm0, xmmword ptr [r15]
0x180038fcc  mov     r9d, [rbp+2Fh+dwEapConnDataSize]; dwEapConnDataSize
0x180038fd0  lea     rax, [rbp+2Fh+pEapError]
0x180038fd4  mov     [rsp+0B0h+ppEapError], rax; ppEapError
0x180038fd9  lea     rdx, [rbp+2Fh+eapMethodType]; eapMethodType
0x180038fdd  lea     rax, [rbp+2Fh+pData]
0x180038fe1  mov     r8d, r14d; dwFlags
0x180038fe4  mov     [rsp+0B0h+ppbUserBlob], rax; ppbUserBlob
0x180038fe9  xor     ecx, ecx; hUserImpersonationToken
0x180038feb  lea     rax, [rbp+2Fh+arg_30]
0x180038fef  mov     [rsp+0B0h+pdwUserBlobSize], rax; pdwUserBlobSize
0x180038ff4  lea     rax, [rbp+2Fh+var_50]
0x180038ff8  mov     [rsp+0B0h+pEapConfigInputFieldArray], rax; pEapConfigInputFieldArray
0x180038ffd  mov     rax, [rbp+2Fh+arg_28]
0x180039001  mov     [rsp+0B0h+pbEapConnData], rax; pbEapConnData
0x180039006  movdqu  xmmword ptr [rbp+2Fh+eapMethodType.eapType.type], xmm0
0x18003900b  call    cs:__imp_EapHostPeerQueryUserBlobFromCredentialInputFields
0x180039011  mov     ebx, eax
0x180039013  test    eax, eax
0x180039015  jnz     short loc_18003904B
0x180039017  mov     ecx, [rbp+2Fh+arg_30]
0x18003901a  lea     r8, aEapcreateeapho; "EapCreateEaphostUserPreoperties"
0x180039021  mov     r9d, 0E3h
0x180039027  mov     rdx, rdi
0x18003902a  call    cs:__imp_AllocateMemory
0x180039030  mov     ebx, eax
0x180039032  test    eax, eax
0x180039034  jnz     short loc_18003904B
0x180039036  mov     r8d, [rbp+2Fh+arg_30]; Size
0x18003903a  mov     rdx, [rbp+2Fh+pData]; Src
0x18003903e  mov     rcx, [rdi]; void *
0x180039041  call    memcpy_0
0x180039046  mov     eax, [rbp+2Fh+arg_30]
0x180039049  mov     [rsi], eax
0x18003904b  mov     rcx, [rbp+2Fh+pEapError]; pEapError
0x18003904f  test    rcx, rcx
0x180039052  jz      short loc_18003905A
0x180039054  call    cs:__imp_EapHostPeerFreeErrorMemory
0x18003905a  movaps  xmm0, xmmword ptr [rbp+2Fh+var_50.dwVersion]
0x18003905e  lea     rcx, [rbp+2Fh+eapMethodType]
0x180039062  movdqa  xmmword ptr [rbp+2Fh+eapMethodType.eapType.type], xmm0
0x180039067  call    EapFreeEapConfigArray
0x18003906c  mov     rcx, [rbp+2Fh+pData]; pData
0x180039070  test    rcx, rcx
0x180039073  jz      short loc_18003907B
0x180039075  call    cs:__imp_EapHostPeerFreeMemory
0x18003907b  mov     eax, ebx
0x18003907d  add     rsp, 88h
0x180039084  pop     r15
0x180039086  pop     r14
0x180039088  pop     rdi
0x180039089  pop     rsi
0x18003908a  pop     rbx
0x18003908b  pop     rbp
0x18003908c  retn
```
