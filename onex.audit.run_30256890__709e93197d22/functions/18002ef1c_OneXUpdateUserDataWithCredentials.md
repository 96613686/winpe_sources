# OneXUpdateUserDataWithCredentials

- ea: `0x18002ef1c`
- end: `0x18002f233`
- name: `OneXUpdateUserDataWithCredentials`
- size: `791`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x18002a76c`

## callees

- `0x18001f4e0`
- `0x18002edd8`
- `0x18002ef1c`
- `0x18002f23c`
- `0x18002f300`
- `0x18002f705`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f0db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f0db`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002f0cc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002f0cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f1bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f1bc`
- `MobileNetworking!SetBufferAndLength` at `0x18002f183`
- `MobileNetworking!SetBufferAndLength` at `0x18002f183`
- `MobileNetworking!AllocateMemory` at `0x18002f068`
- `MobileNetworking!AllocateMemory` at `0x18002f068`
- `MobileNetworking!FreeMemory` at `0x18002f1f0`
- `MobileNetworking!FreeMemory` at `0x18002f20e`
- `MobileNetworking!FreeMemory` at `0x18002f1f0`
- `MobileNetworking!FreeMemory` at `0x18002f20e`
- `eappcfg!EapHostPeerQueryUserBlobFromCredentialInputFields` at `0x18002f14b`
- `eappcfg!EapHostPeerQueryUserBlobFromCredentialInputFields` at `0x18002f14b`
- `eappcfg!EapHostPeerFreeMemory` at `0x18002f1b4`
- `eappcfg!EapHostPeerFreeMemory` at `0x18002f1b4`

## string_xrefs

- `0x18002f05d`: `OneXUpdateUserDataWithCredentials`
- `0x18002f1e5`: `OneXUpdateUserDataWithCredentials`
- `0x18002f203`: `OneXUpdateUserDataWithCredentials`

## pseudocode

```c
__int64 __fastcall OneXUpdateUserDataWithCredentials(
        int a1,
        void *a2,
        int a3,
        BYTE *a4,
        DWORD a5,
        size_t Size,
        void *Src,
        __int64 a8,
        __int64 a9)
{
  int v9; // r12d
  unsigned __int64 v10; // r8
  DWORD LastError; // ebx
  __int64 v14; // r14
  __int64 v15; // rdi
  DWORD v16; // edx
  unsigned int v17; // eax
  unsigned int v18; // edi
  _BYTE *v19; // rdx
  BYTE *v20; // rax
  __int64 v21; // r9
  BYTE *v22; // r8
  _BYTE *v23; // rax
  __int64 v24; // rcx
  BYTE *pData; // [rsp+58h] [rbp-51h] BYREF
  int v27; // [rsp+60h] [rbp-49h] BYREF
  DWORD dwEapConnDataSize; // [rsp+64h] [rbp-45h] BYREF
  unsigned int v29; // [rsp+68h] [rbp-41h]
  __int64 v30; // [rsp+70h] [rbp-39h] BYREF
  BYTE *pbEapConnData; // [rsp+78h] [rbp-31h] BYREF
  __int64 v32; // [rsp+80h] [rbp-29h] BYREF
  EAP_METHOD_TYPE eapMethodType; // [rsp+88h] [rbp-21h] BYREF
  EAP_ERROR *ppEapError; // [rsp+98h] [rbp-11h] BYREF
  EAP_CONFIG_INPUT_FIELD_ARRAY pEapConfigInputFieldArray; // [rsp+A8h] [rbp-1h] BYREF
  SIZE_T uBytes; // [rsp+F8h] [rbp+4Fh] BYREF

  LODWORD(uBytes) = a3;
  v9 = 0;
  v10 = 2580LL * a5;
  pEapConfigInputFieldArray = 0;
  eapMethodType = 0;
  v32 = 0;
  v29 = 0;
  pData = 0;
  v30 = 0;
  v27 = 0;
  ppEapError = 0;
  dwEapConnDataSize = 0;
  pbEapConnData = 0;
  if ( v10 > 0xFFFFFFFF )
    goto LABEL_29;
  if ( !a5 || !Src || (unsigned int)v10 > (unsigned int)Size )
  {
    LastError = 87;
    goto LABEL_30;
  }
  LastError = OneXDecryptMemory((unsigned int)Size, Src, (__int64)&v30);
  if ( LastError )
    goto LABEL_30;
  v14 = v30;
  LODWORD(v15) = 0;
  v16 = 0;
  if ( !a5 )
    goto LABEL_24;
  do
  {
    v17 = v15 + 1;
    if ( (*(_BYTE *)(2580LL * v16 + v30 + 4) & 2) == 0 )
      v17 = v15;
    ++v16;
    v15 = v17;
  }
  while ( v16 < a5 );
  if ( !v17 )
  {
LABEL_24:
    LastError = 232;
    if ( !a4 )
      goto LABEL_30;
    v21 = (unsigned int)uBytes;
    if ( !(_DWORD)uBytes )
      goto LABEL_30;
    v22 = a4;
    goto LABEL_27;
  }
  LastError = OneXGetEapTypeAndConnData(
                a1,
                (unsigned int)&eapMethodType,
                (unsigned int)&v27,
                (unsigned int)&dwEapConnDataSize,
                (__int64)&pbEapConnData);
  if ( LastError )
    goto LABEL_30;
  if ( (unsigned __int64)(2580 * v15) > 0xFFFFFFFF )
  {
LABEL_29:
    LastError = 534;
  }
  else
  {
    LastError = AllocateMemory(2580 * v15, &v32, "OneXUpdateUserDataWithCredentials", 575);
    if ( !LastError )
    {
      v18 = 0;
      do
      {
        v19 = (_BYTE *)(v14 + 2580LL * LastError);
        if ( (v19[4] & 2) != 0 )
          memcpy_0((void *)(v32 + 2580LL * v18++), v19, 0xA14u);
        ++LastError;
      }
      while ( LastError < a5 );
      LastError = EapMapToEapConfigArray(v18, v32, &pEapConfigInputFieldArray);
      if ( !LastError )
      {
        v20 = (BYTE *)LocalAlloc(0x40u, (unsigned int)uBytes);
        pData = v20;
        if ( !v20 )
        {
          LastError = GetLastError();
          if ( LastError )
            goto LABEL_30;
          v20 = pData;
        }
        memcpy_0(v20, a4, (unsigned int)uBytes);
        LastError = EapHostPeerQueryUserBlobFromCredentialInputFields(
                      a2,
                      &eapMethodType,
                      v27 | 0x40080,
                      dwEapConnDataSize,
                      pbEapConnData,
                      &pEapConfigInputFieldArray,
                      (DWORD *)&uBytes,
                      &pData,
                      &ppEapError);
        if ( !LastError )
        {
          v21 = (unsigned int)uBytes;
          v9 = 1;
          v22 = pData;
LABEL_27:
          LastError = SetBufferAndLength(a9, a8, v22, v21);
        }
      }
    }
  }
LABEL_30:
  eapMethodType = (EAP_METHOD_TYPE)pEapConfigInputFieldArray;
  EapFreeEapConfigArray(&eapMethodType);
  if ( v9 )
    EapHostPeerFreeMemory(pData);
  else
    LocalFree(pData);
  v23 = (_BYTE *)v30;
  if ( v30 )
  {
    v24 = v29;
    if ( v29 )
    {
      do
      {
        *v23++ = 0;
        --v24;
      }
      while ( v24 );
    }
    FreeMemory(&v30, "OneXUpdateUserDataWithCredentials", 637);
  }
  if ( pbEapConnData )
    FreeMemory(&pbEapConnData, "OneXUpdateUserDataWithCredentials", 642);
  return LastError;
}

```

## disassembly

```asm
0x18002ef1c  mov     rax, rsp
0x18002ef1f  mov     [rax+8], rbx
0x18002ef23  mov     [rax+20h], rdi
0x18002ef27  mov     [rax+18h], r8d
0x18002ef2b  mov     [rax+10h], rdx
0x18002ef2f  push    rbp
0x18002ef30  push    r12
0x18002ef32  push    r13
0x18002ef34  push    r14
0x18002ef36  push    r15
0x18002ef38  lea     rbp, [rax-37h]
0x18002ef3c  sub     rsp, 0B0h
0x18002ef43  mov     eax, [rbp+2Fh+arg_20]
0x18002ef46  xor     r12d, r12d
0x18002ef49  imul    r8, rax, 0A14h
0x18002ef50  xorps   xmm0, xmm0
0x18002ef53  movups  xmmword ptr [rbp+2Fh+var_30.dwVersion], xmm0
0x18002ef57  movups  xmmword ptr [rbp+2Fh+eapMethodType.eapType.type], xmm0
0x18002ef5b  mov     eax, 0FFFFFFFFh
0x18002ef60  mov     [rbp+2Fh+var_58], 0
0x18002ef68  mov     [rbp+2Fh+var_70], 0
0x18002ef6f  mov     r15, r9
0x18002ef72  mov     [rbp+2Fh+pData], 0
0x18002ef7a  mov     r13, rcx
0x18002ef7d  mov     [rbp+2Fh+var_68], 0
0x18002ef85  mov     [rbp+2Fh+var_78], 0
0x18002ef8c  mov     [rbp+2Fh+var_40], 0
0x18002ef94  mov     [rbp+2Fh+dwEapConnDataSize], r12d
0x18002ef98  mov     [rbp+2Fh+var_60], r12
0x18002ef9c  cmp     r8, rax
0x18002ef9f  ja      loc_18002F194
0x18002efa5  cmp     [rbp+2Fh+arg_20], r12d
0x18002efa9  jz      loc_18002F18D
0x18002efaf  mov     rdx, [rbp+2Fh+Src]; Src
0x18002efb3  test    rdx, rdx
0x18002efb6  jz      loc_18002F18D
0x18002efbc  mov     ecx, dword ptr [rbp+2Fh+Size]; Size
0x18002efbf  cmp     r8d, ecx
0x18002efc2  ja      loc_18002F18D
0x18002efc8  lea     rax, [rbp+2Fh+var_68]
0x18002efcc  lea     r9, [rbp+2Fh+var_70]
0x18002efd0  mov     [rsp+0D0h+pbEapConnData], rax; __int64
0x18002efd5  call    OneXDecryptMemory
0x18002efda  mov     ebx, eax
0x18002efdc  test    eax, eax
0x18002efde  jnz     loc_18002F199
0x18002efe4  mov     r14, [rbp+2Fh+var_68]
0x18002efe8  xor     edi, edi
0x18002efea  xor     edx, edx
0x18002efec  cmp     [rbp+2Fh+arg_20], edx
0x18002efef  jbe     loc_18002F165
0x18002eff5  mov     eax, edx
0x18002eff7  imul    rcx, rax, 0A14h
0x18002effe  lea     eax, [rdi+1]
0x18002f001  test    byte ptr [rcx+r14+4], 2
0x18002f007  cmovz   eax, edi
0x18002f00a  inc     edx
0x18002f00c  mov     edi, eax
0x18002f00e  cmp     edx, [rbp+2Fh+arg_20]
0x18002f011  jb      short loc_18002EFF5
0x18002f013  test    eax, eax
0x18002f015  jz      loc_18002F165
0x18002f01b  lea     rax, [rbp+2Fh+var_60]
0x18002f01f  mov     rcx, r13
0x18002f022  lea     r9, [rbp+2Fh+dwEapConnDataSize]
0x18002f026  mov     [rsp+0D0h+pbEapConnData], rax
0x18002f02b  lea     r8, [rbp+2Fh+var_78]
0x18002f02f  lea     rdx, [rbp+2Fh+eapMethodType]
0x18002f033  call    OneXGetEapTypeAndConnData
0x18002f038  mov     ebx, eax
0x18002f03a  test    eax, eax
0x18002f03c  jnz     loc_18002F199
0x18002f042  imul    rcx, rdi, 0A14h
0x18002f049  mov     eax, 0FFFFFFFFh
0x18002f04e  cmp     rcx, rax
0x18002f051  ja      loc_18002F194
0x18002f057  mov     r9d, 23Fh
0x18002f05d  lea     r8, aOnexupdateuser; "OneXUpdateUserDataWithCredentials"
0x18002f064  lea     rdx, [rbp+2Fh+var_58]
0x18002f068  call    cs:__imp_AllocateMemory
0x18002f06e  mov     ebx, eax
0x18002f070  test    eax, eax
0x18002f072  jnz     loc_18002F199
0x18002f078  xor     edi, edi
0x18002f07a  mov     eax, ebx
0x18002f07c  imul    rdx, rax, 0A14h
0x18002f083  add     rdx, r14; Src
0x18002f086  test    byte ptr [rdx+4], 2
0x18002f08a  jz      short loc_18002F0A6
0x18002f08c  mov     eax, edi
0x18002f08e  mov     r8d, 0A14h; Size
0x18002f094  imul    rcx, rax, 0A14h
0x18002f09b  add     rcx, [rbp+2Fh+var_58]; void *
0x18002f09f  call    memcpy_0
0x18002f0a4  inc     edi
0x18002f0a6  inc     ebx
0x18002f0a8  cmp     ebx, [rbp+2Fh+arg_20]
0x18002f0ab  jb      short loc_18002F07A
0x18002f0ad  mov     rdx, [rbp+2Fh+var_58]
0x18002f0b1  lea     r8, [rbp+2Fh+var_30]
0x18002f0b5  mov     ecx, edi
0x18002f0b7  call    EapMapToEapConfigArray
0x18002f0bc  mov     ebx, eax
0x18002f0be  test    eax, eax
0x18002f0c0  jnz     loc_18002F199
0x18002f0c6  mov     edx, dword ptr [rbp+2Fh+uBytes]; uBytes
0x18002f0c9  lea     ecx, [rax+40h]; uFlags
0x18002f0cc  call    cs:__imp_LocalAlloc
0x18002f0d2  mov     [rbp+2Fh+pData], rax
0x18002f0d6  test    rax, rax
0x18002f0d9  jnz     short loc_18002F0EF
0x18002f0db  call    cs:__imp_GetLastError
0x18002f0e1  mov     ebx, eax
0x18002f0e3  test    eax, eax
0x18002f0e5  jnz     loc_18002F199
0x18002f0eb  mov     rax, [rbp+2Fh+pData]
0x18002f0ef  mov     r8d, dword ptr [rbp+2Fh+uBytes]; Size
0x18002f0f3  mov     rdx, r15; Src
0x18002f0f6  mov     rcx, rax; void *
0x18002f0f9  call    memcpy_0
0x18002f0fe  mov     r8d, [rbp+2Fh+var_78]
0x18002f102  lea     rax, [rbp+2Fh+var_40]
0x18002f106  movaps  xmm0, xmmword ptr [rbp+2Fh+eapMethodType.eapType.type]
0x18002f10a  lea     rdx, [rbp+2Fh+eapMethodType]; eapMethodType
0x18002f10e  mov     r9d, [rbp+2Fh+dwEapConnDataSize]; dwEapConnDataSize
0x18002f112  or      r8d, 40080h; dwFlags
0x18002f119  mov     rcx, [rbp+2Fh+hUserImpersonationToken]; hUserImpersonationToken
0x18002f11d  mov     [rsp+0D0h+ppEapError], rax; ppEapError
0x18002f122  lea     rax, [rbp+2Fh+pData]
0x18002f126  mov     [rsp+0D0h+ppbUserBlob], rax; ppbUserBlob
0x18002f12b  lea     rax, [rbp+2Fh+uBytes]
0x18002f12f  mov     [rsp+0D0h+pdwUserBlobSize], rax; pdwUserBlobSize
0x18002f134  lea     rax, [rbp+2Fh+var_30]
0x18002f138  mov     [rsp+0D0h+pEapConfigInputFieldArray], rax; pEapConfigInputFieldArray
0x18002f13d  mov     rax, [rbp+2Fh+var_60]
0x18002f141  mov     [rsp+0D0h+pbEapConnData], rax; pbEapConnData
0x18002f146  movdqa  xmmword ptr [rbp+2Fh+eapMethodType.eapType.type], xmm0
0x18002f14b  call    cs:__imp_EapHostPeerQueryUserBlobFromCredentialInputFields
0x18002f151  mov     ebx, eax
0x18002f153  test    eax, eax
0x18002f155  jnz     short loc_18002F199
0x18002f157  mov     r9d, dword ptr [rbp+2Fh+uBytes]
0x18002f15b  lea     r12d, [rax+1]
0x18002f15f  mov     r8, [rbp+2Fh+pData]
0x18002f163  jmp     short loc_18002F17B
0x18002f165  mov     ebx, 0E8h
0x18002f16a  test    r15, r15
0x18002f16d  jz      short loc_18002F199
0x18002f16f  mov     r9d, dword ptr [rbp+2Fh+uBytes]
0x18002f173  test    r9d, r9d
0x18002f176  jz      short loc_18002F199
0x18002f178  mov     r8, r15
0x18002f17b  mov     rdx, [rbp+2Fh+arg_38]
0x18002f17f  mov     rcx, [rbp+2Fh+arg_40]
0x18002f183  call    cs:__imp_SetBufferAndLength
0x18002f189  mov     ebx, eax
0x18002f18b  jmp     short loc_18002F199
0x18002f18d  mov     ebx, 57h ; 'W'
0x18002f192  jmp     short loc_18002F199
0x18002f194  mov     ebx, 216h
0x18002f199  movaps  xmm0, xmmword ptr [rbp+2Fh+var_30.dwVersion]
0x18002f19d  lea     rcx, [rbp+2Fh+eapMethodType]
0x18002f1a1  movdqa  xmmword ptr [rbp+2Fh+eapMethodType.eapType.type], xmm0
0x18002f1a6  call    EapFreeEapConfigArray
0x18002f1ab  mov     rcx, [rbp+2Fh+pData]; hMem
0x18002f1af  test    r12d, r12d
0x18002f1b2  jz      short loc_18002F1BC
0x18002f1b4  call    cs:__imp_EapHostPeerFreeMemory
0x18002f1ba  jmp     short loc_18002F1C2
0x18002f1bc  call    cs:__imp_LocalFree
0x18002f1c2  mov     rax, [rbp+2Fh+var_68]
0x18002f1c6  test    rax, rax
0x18002f1c9  jz      short loc_18002F1F6
0x18002f1cb  mov     ecx, [rbp+2Fh+var_70]
0x18002f1ce  test    rcx, rcx
0x18002f1d1  jz      short loc_18002F1DF
0x18002f1d3  mov     byte ptr [rax], 0
0x18002f1d6  inc     rax
0x18002f1d9  sub     rcx, 1
0x18002f1dd  jnz     short loc_18002F1D3
0x18002f1df  mov     r8d, 27Dh
0x18002f1e5  lea     rdx, aOnexupdateuser; "OneXUpdateUserDataWithCredentials"
0x18002f1ec  lea     rcx, [rbp+2Fh+var_68]
0x18002f1f0  call    cs:__imp_FreeMemory
0x18002f1f6  cmp     [rbp+2Fh+var_60], 0
0x18002f1fb  jz      short loc_18002F214
0x18002f1fd  mov     r8d, 282h
0x18002f203  lea     rdx, aOnexupdateuser; "OneXUpdateUserDataWithCredentials"
0x18002f20a  lea     rcx, [rbp+2Fh+var_60]
0x18002f20e  call    cs:__imp_FreeMemory
0x18002f214  lea     r11, [rsp+0D0h+var_20]
0x18002f21c  mov     eax, ebx
0x18002f21e  mov     rbx, [r11+30h]
0x18002f222  mov     rdi, [r11+48h]
0x18002f226  mov     rsp, r11
0x18002f229  pop     r15
0x18002f22b  pop     r14
0x18002f22d  pop     r13
0x18002f22f  pop     r12
0x18002f231  pop     rbp
0x18002f232  retn
```
