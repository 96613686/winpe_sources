# ProfileMgrCreateDiscoveryProfiles

- ea: `0x18002aa58`
- end: `0x18002b0ec`
- name: `ProfileMgrCreateDiscoveryProfiles`
- size: `1684`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18002c650`

## callees

- `0x180004f40`
- `0x180005440`
- `0x180010ae0`
- `0x1800148b0`
- `0x180018670`
- `0x18001a54c`
- `0x18001d5b4`
- `0x1800214f0`
- `0x18002aa58`
- `0x18002b224`
- `0x18002ec50`

## import_xrefs

- `MobileNetworking!IsDomainMemberMode` at `0x18002aae9`
- `MobileNetworking!IsDomainMemberMode` at `0x18002aae9`
- `MobileNetworking!SetBufferAndLength` at `0x18002ae8f`
- `MobileNetworking!SetBufferAndLength` at `0x18002aef9`
- `MobileNetworking!SetBufferAndLength` at `0x18002ae8f`
- `MobileNetworking!SetBufferAndLength` at `0x18002aef9`
- `MobileNetworking!AllocateMemory` at `0x18002ab7d`
- `MobileNetworking!AllocateMemory` at `0x18002ad57`
- `MobileNetworking!AllocateMemory` at `0x18002adb8`
- `MobileNetworking!AllocateMemory` at `0x18002ab7d`
- `MobileNetworking!AllocateMemory` at `0x18002ad57`
- `MobileNetworking!AllocateMemory` at `0x18002adb8`
- `MobileNetworking!FreeMemory` at `0x18002afd3`
- `MobileNetworking!FreeMemory` at `0x18002b00d`
- `MobileNetworking!FreeMemory` at `0x18002b034`
- `MobileNetworking!FreeMemory` at `0x18002b059`
- `MobileNetworking!FreeMemory` at `0x18002b09c`
- `MobileNetworking!FreeMemory` at `0x18002afd3`
- `MobileNetworking!FreeMemory` at `0x18002b00d`
- `MobileNetworking!FreeMemory` at `0x18002b034`
- `MobileNetworking!FreeMemory` at `0x18002b059`
- `MobileNetworking!FreeMemory` at `0x18002b09c`
- `eappcfg!EapHostPeerGetMethods` at `0x18002ab07`
- `eappcfg!EapHostPeerGetMethods` at `0x18002ab07`
- `eappcfg!EapHostPeerGetMethodProperties` at `0x18002ac7d`
- `eappcfg!EapHostPeerGetMethodProperties` at `0x18002ac7d`
- `eappcfg!EapHostPeerFreeErrorMemory` at `0x18002acbc`
- `eappcfg!EapHostPeerFreeErrorMemory` at `0x18002afe2`
- `eappcfg!EapHostPeerFreeErrorMemory` at `0x18002acbc`
- `eappcfg!EapHostPeerFreeErrorMemory` at `0x18002afe2`

## string_xrefs

- `0x18002ab5e`: `ProfileMgrCreateDiscoveryProfiles`
- `0x18002ad4c`: `ProfileMgrCreateDiscoveryProfiles`
- `0x18002adad`: `ProfileMgrCreateDiscoveryProfiles`
- `0x18002b002`: `ProfileMgrCreateDiscoveryProfiles`
- `0x18002b02d`: `ProfileMgrCreateDiscoveryProfiles`
- `0x18002b04e`: `ProfileMgrCreateDiscoveryProfiles`
- `0x18002b091`: `ProfileMgrCreateDiscoveryProfiles`

## pseudocode

```c
__int64 __fastcall ProfileMgrCreateDiscoveryProfiles(unsigned int a1, int a2, unsigned int *a3, _QWORD *a4, _QWORD *a5)
{
  DWORD dwNumberOfMethods; // r12d
  EAP_METHOD_INFO *pEapMethods; // r14
  int v7; // edi
  unsigned int v10; // r15d
  __int64 Methods; // rbx
  unsigned int v12; // eax
  __int64 v13; // rsi
  EAP_METHOD_TYPE *p_eaptype; // r14
  EAP_METHOD_TYPE v15; // xmm0
  __int64 v16; // rbx
  __int64 i; // rcx
  __int64 v18; // rax
  _QWORD *v19; // rcx
  unsigned int v20; // eax
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  unsigned int v23; // esi
  void *v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rdi
  __int64 v27; // rax
  DWORD v28; // edi
  EAP_METHOD_INFO *v30; // [rsp+58h] [rbp-41h]
  _DWORD *v31; // [rsp+60h] [rbp-39h] BYREF
  __int64 v32; // [rsp+68h] [rbp-31h] BYREF
  unsigned int v33; // [rsp+70h] [rbp-29h] BYREF
  EAP_ERROR *ppEapError; // [rsp+78h] [rbp-21h] BYREF
  __int64 v35; // [rsp+80h] [rbp-19h] BYREF
  __int64 v36; // [rsp+88h] [rbp-11h] BYREF
  EAP_METHOD_INFO_ARRAY pEapMethodInfoArray; // [rsp+90h] [rbp-9h] BYREF
  EAP_METHOD_TYPE eapMethodType; // [rsp+A8h] [rbp+Fh] BYREF

  dwNumberOfMethods = 0;
  v31 = 0;
  pEapMethods = 0;
  v32 = 0;
  v30 = 0;
  pEapMethodInfoArray = 0;
  ppEapError = 0;
  v7 = 0;
  v36 = 0;
  v35 = 0;
  v33 = 0;
  v10 = 1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 30, WPP_cf2b0dcf9cd735c0c1c863ae54fcb446_Traceguids);
  if ( !(unsigned int)IsDomainMemberMode() || !a2 )
    goto LABEL_34;
  Methods = EapHostPeerGetMethods(&pEapMethodInfoArray, &ppEapError);
  EapDumpEaphostError(Methods, 0, ppEapError);
  if ( (_DWORD)Methods )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        31,
        WPP_cf2b0dcf9cd735c0c1c863ae54fcb446_Traceguids,
        (unsigned int)Methods);
    goto LABEL_68;
  }
  dwNumberOfMethods = pEapMethodInfoArray.dwNumberOfMethods;
  pEapMethods = pEapMethodInfoArray.pEapMethods;
  v30 = pEapMethodInfoArray.pEapMethods;
  v12 = AllocateMemory(16 * pEapMethodInfoArray.dwNumberOfMethods, &v35, "ProfileMgrCreateDiscoveryProfiles", 303);
  LODWORD(Methods) = v12;
  if ( !v12 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        33,
        WPP_cf2b0dcf9cd735c0c1c863ae54fcb446_Traceguids,
        dwNumberOfMethods);
    v13 = 0;
    while ( (unsigned int)v13 < dwNumberOfMethods )
    {
      p_eaptype = &pEapMethods[v13].eaptype;
      if ( (unsigned int)ProfileMgrIsValidDiscoveryMethod(p_eaptype) )
      {
        v15 = *p_eaptype;
        eapMethodType = *p_eaptype;
        if ( !(unsigned int)OneXIsValidEapTypeForMedia(&eapMethodType, a1) )
        {
          v16 = 16LL * (unsigned int)v13;
          eapMethodType = v15;
          if ( !EapHostPeerGetMethodProperties(
                  0,
                  0,
                  &eapMethodType,
                  0,
                  0,
                  0,
                  0,
                  0,
                  (EAP_METHOD_PROPERTY_ARRAY *)(v16 + v35),
                  &ppEapError) )
          {
            for ( i = 0; (unsigned int)i < *(_DWORD *)(v16 + v35); i = (unsigned int)(i + 1) )
            {
              v18 = *(_QWORD *)(v16 + v35 + 8);
              if ( *(_DWORD *)(v18 + 24 * i) == 24 )
              {
                if ( *(_DWORD *)(v18 + 24 * i + 12) )
                  v7 = 1;
                break;
              }
            }
          }
          if ( ppEapError )
          {
            EapHostPeerFreeErrorMemory(ppEapError);
            ppEapError = 0;
          }
        }
      }
      pEapMethods = v30;
      v13 = (unsigned int)(v13 + 1);
      if ( v7 )
      {
        v10 = 2;
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_38;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 34, WPP_cf2b0dcf9cd735c0c1c863ae54fcb446_Traceguids);
          break;
        }
        goto LABEL_35;
      }
    }
LABEL_34:
    v19 = WPP_GLOBAL_Control;
LABEL_35:
    if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 68) & 4) != 0 )
      WPP_SF_d(v19[7], 35, WPP_cf2b0dcf9cd735c0c1c863ae54fcb446_Traceguids, v10);
LABEL_38:
    v20 = AllocateMemory(4 * v10, &v36, "ProfileMgrCreateDiscoveryProfiles", 378);
    LODWORD(Methods) = v20;
    if ( v20 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_67;
      v22 = 36;
      goto LABEL_42;
    }
    v20 = AllocateMemory(8 * v10, &v32, "ProfileMgrCreateDiscoveryProfiles", 381);
    LODWORD(Methods) = v20;
    if ( v20 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_67;
      v22 = 37;
      goto LABEL_42;
    }
    v20 = OneXHlpCreateDefaultProfile(&v31, &v33, a1, 0);
    LODWORD(Methods) = v20;
    if ( v20 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_67;
      v22 = 38;
      goto LABEL_42;
    }
    v23 = 0;
    v31[2] |= 0x80u;
    v31[10] = 1;
    v31[2] |= 0x10u;
    v31[7] = 5;
    v31[2] |= 0x20u;
    v31[8] = 1;
    v31[2] |= 1u;
    v31[3] = 16;
    if ( v7 )
    {
      v20 = SetBufferAndLength(v32, v36, v31, v33);
      LODWORD(Methods) = v20;
      if ( v20 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_67;
        v22 = 39;
        goto LABEL_42;
      }
      v23 = 1;
      *(_DWORD *)(*(_QWORD *)v32 + 8LL) |= 4u;
      *(_DWORD *)(*(_QWORD *)v32 + 20LL) = 1;
    }
    v20 = SetBufferAndLength(v32 + 8LL * v23, v36 + 4LL * v23, v31, v33);
    LODWORD(Methods) = v20;
    if ( !v20 )
    {
      *(_DWORD *)(*(_QWORD *)(v32 + 8LL * v23) + 8LL) |= 4u;
      *(_DWORD *)(*(_QWORD *)(v32 + 8LL * v23) + 20LL) = v7 == 0 ? 2 : 0;
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 41, WPP_cf2b0dcf9cd735c0c1c863ae54fcb446_Traceguids, v23 + 1);
      if ( (byte_18003DF41 & 4) != 0 )
        McTemplateU0q_EtwEventWriteTransfer(v24, DiscoveryProfilesCreated, v23);
      *a3 = v10;
      *a4 = v36;
      *a5 = v32;
      goto LABEL_67;
    }
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
    {
LABEL_67:
      pEapMethods = v30;
      goto LABEL_68;
    }
    v22 = 40;
LABEL_42:
    WPP_SF_d(v21[7], v22, WPP_cf2b0dcf9cd735c0c1c863ae54fcb446_Traceguids, v20);
    goto LABEL_67;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 32, WPP_cf2b0dcf9cd735c0c1c863ae54fcb446_Traceguids, v12);
LABEL_68:
  FreeMemory(&v31, "OneXHlpFreeMemory", 414);
  if ( ppEapError )
    EapHostPeerFreeErrorMemory(ppEapError);
  if ( pEapMethods )
    EapFreeEaphostMethodInfoArray(&pEapMethods->eaptype.eapType.type);
  if ( (_DWORD)Methods )
  {
    FreeMemory(&v36, "ProfileMgrCreateDiscoveryProfiles", 450);
    v25 = v32;
    if ( v32 )
    {
      v26 = 0;
      while ( 1 )
      {
        FreeMemory(v25 + 8 * v26, "ProfileMgrCreateDiscoveryProfiles", 455);
        v26 = (unsigned int)(v26 + 1);
        if ( (unsigned int)v26 >= v10 )
          break;
        v25 = v32;
      }
      FreeMemory(&v32, "ProfileMgrCreateDiscoveryProfiles", 457);
    }
  }
  v27 = v35;
  if ( v35 )
  {
    v28 = 0;
    if ( dwNumberOfMethods )
    {
      while ( 1 )
      {
        FreeEapMethodProperties(v27 + 16LL * v28++);
        if ( v28 >= dwNumberOfMethods )
          break;
        v27 = v35;
      }
    }
    FreeMemory(&v35, "ProfileMgrCreateDiscoveryProfiles", 468);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      42,
      WPP_cf2b0dcf9cd735c0c1c863ae54fcb446_Traceguids,
      (unsigned int)Methods);
  return (unsigned int)Methods;
}

```

## disassembly

```asm
0x18002aa58  mov     rax, rsp
0x18002aa5b  mov     [rax+8], rbx
0x18002aa5f  mov     [rax+20h], r9
0x18002aa63  mov     [rax+18h], r8
0x18002aa67  push    rbp
0x18002aa68  push    rsi
0x18002aa69  push    rdi
0x18002aa6a  push    r12
0x18002aa6c  push    r13
0x18002aa6e  push    r14
0x18002aa70  push    r15
0x18002aa72  lea     rbp, [rax-57h]
0x18002aa76  sub     rsp, 0B0h
0x18002aa7d  xor     r12d, r12d
0x18002aa80  mov     [rbp+4Fh+var_88], 0
0x18002aa88  xor     r14d, r14d
0x18002aa8b  mov     [rbp+4Fh+var_80], r12
0x18002aa8f  xorps   xmm0, xmm0
0x18002aa92  mov     [rbp+4Fh+var_90], r14
0x18002aa96  movups  xmmword ptr [rbp+4Fh+pEapMethodInfoArray.dwNumberOfMethods], xmm0
0x18002aa9a  mov     [rbp+4Fh+ppEapError], r14
0x18002aa9e  xor     edi, edi
0x18002aaa0  mov     [rbp+4Fh+var_60], r12
0x18002aaa4  mov     ebx, edx
0x18002aaa6  mov     [rbp+4Fh+var_68], r12
0x18002aaaa  mov     r13d, ecx
0x18002aaad  mov     [rbp+4Fh+var_78], 0
0x18002aab4  mov     r15d, 1
0x18002aaba  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aac1  lea     rsi, WPP_GLOBAL_Control
0x18002aac8  cmp     rcx, rsi
0x18002aacb  jz      short loc_18002AAE9
0x18002aacd  test    dword ptr [rcx+44h], 800h
0x18002aad4  jz      short loc_18002AAE9
0x18002aad6  mov     rcx, [rcx+38h]
0x18002aada  lea     edx, [rdi+1Eh]
0x18002aadd  lea     r8, WPP_cf2b0dcf9cd735c0c1c863ae54fcb446_Traceguids
0x18002aae4  call    WPP_SF_
0x18002aae9  call    cs:__imp_IsDomainMemberMode
0x18002aaef  test    eax, eax
0x18002aaf1  jz      loc_18002AD14
0x18002aaf7  test    ebx, ebx
0x18002aaf9  jz      loc_18002AD14
0x18002aaff  lea     rdx, [rbp+4Fh+ppEapError]; ppEapError
0x18002ab03  lea     rcx, [rbp+4Fh+pEapMethodInfoArray]; pEapMethodInfoArray
0x18002ab07  call    cs:__imp_EapHostPeerGetMethods
0x18002ab0d  mov     r8, [rbp+4Fh+ppEapError]
0x18002ab11  xor     edx, edx
0x18002ab13  mov     ecx, eax
0x18002ab15  mov     ebx, eax
0x18002ab17  call    EapDumpEaphostError
0x18002ab1c  test    ebx, ebx
0x18002ab1e  jz      short loc_18002AB5A
0x18002ab20  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ab27  mov     r13d, r15d
0x18002ab2a  cmp     rcx, rsi
0x18002ab2d  jz      loc_18002AFC2
0x18002ab33  test    [rcx+44h], r13b
0x18002ab37  jz      loc_18002AFC2
0x18002ab3d  mov     rcx, [rcx+38h]
0x18002ab41  lea     r8, WPP_cf2b0dcf9cd735c0c1c863ae54fcb446_Traceguids
0x18002ab48  mov     edx, 1Fh
0x18002ab4d  mov     r9d, ebx
0x18002ab50  call    WPP_SF_D
0x18002ab55  jmp     loc_18002AFC2
0x18002ab5a  mov     r12d, [rbp+4Fh+pEapMethodInfoArray.dwNumberOfMethods]
0x18002ab5e  lea     r8, aProfilemgrcrea; "ProfileMgrCreateDiscoveryProfiles"
0x18002ab65  mov     r14, [rbp+4Fh+pEapMethodInfoArray.pEapMethods]
0x18002ab69  lea     rdx, [rbp+4Fh+var_68]
0x18002ab6d  mov     ecx, r12d
0x18002ab70  mov     [rbp+4Fh+var_90], r14
0x18002ab74  shl     ecx, 4
0x18002ab77  mov     r9d, 12Fh
0x18002ab7d  call    cs:__imp_AllocateMemory
0x18002ab83  mov     ebx, eax
0x18002ab85  test    eax, eax
0x18002ab87  jz      short loc_18002ABC3
0x18002ab89  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ab90  mov     r13d, r15d
0x18002ab93  cmp     rcx, rsi
0x18002ab96  jz      loc_18002AFC2
0x18002ab9c  test    [rcx+44h], r13b
0x18002aba0  jz      loc_18002AFC2
0x18002aba6  mov     rcx, [rcx+38h]
0x18002abaa  lea     r8, WPP_cf2b0dcf9cd735c0c1c863ae54fcb446_Traceguids
0x18002abb1  mov     edx, 20h ; ' '
0x18002abb6  mov     r9d, eax
0x18002abb9  call    WPP_SF_d
0x18002abbe  jmp     loc_18002AFC2
0x18002abc3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002abca  cmp     rcx, rsi
0x18002abcd  jz      short loc_18002ABED
0x18002abcf  test    byte ptr [rcx+44h], 4
0x18002abd3  jz      short loc_18002ABED
0x18002abd5  mov     rcx, [rcx+38h]
0x18002abd9  lea     r8, WPP_cf2b0dcf9cd735c0c1c863ae54fcb446_Traceguids
0x18002abe0  mov     edx, 21h ; '!'
0x18002abe5  mov     r9d, r12d
0x18002abe8  call    WPP_SF_d
0x18002abed  xor     esi, esi
0x18002abef  cmp     esi, r12d
0x18002abf2  jnb     loc_18002AD0D
0x18002abf8  lea     rax, [rsi+rsi*2]
0x18002abfc  mov     ebx, esi
0x18002abfe  shl     rax, 4
0x18002ac02  add     r14, rax
0x18002ac05  mov     rcx, r14
0x18002ac08  call    ProfileMgrIsValidDiscoveryMethod
0x18002ac0d  test    eax, eax
0x18002ac0f  jz      loc_18002ACCA
0x18002ac15  movups  xmm0, xmmword ptr [r14]
0x18002ac19  mov     edx, r13d
0x18002ac1c  lea     rcx, [rbp+4Fh+eapMethodType]
0x18002ac20  movdqu  xmmword ptr [rbp+4Fh+eapMethodType.eapType.type], xmm0
0x18002ac25  call    OneXIsValidEapTypeForMedia
0x18002ac2a  test    eax, eax
0x18002ac2c  jnz     loc_18002ACCA
0x18002ac32  mov     rcx, [rbp+4Fh+var_68]
0x18002ac36  lea     rax, [rbp+4Fh+ppEapError]
0x18002ac3a  mov     [rsp+48h], rax; ppEapError
0x18002ac3f  lea     r8, [rbp+4Fh+eapMethodType]; eapMethodType
0x18002ac43  shl     rbx, 4
0x18002ac47  xor     r9d, r9d; hUserImpersonationToken
0x18002ac4a  add     rcx, rbx
0x18002ac4d  xor     edx, edx; dwFlags
0x18002ac4f  mov     [rsp+0E0h+pMethodPropertyArray], rcx; pMethodPropertyArray
0x18002ac54  xor     ecx, ecx; dwVersion
0x18002ac56  mov     [rsp+0E0h+pbUserData], 0; pbUserData
0x18002ac5f  mov     [rsp+0E0h+dwUserDataSize], 0; dwUserDataSize
0x18002ac67  mov     [rsp+0E0h+pbEapConnData], 0; pbEapConnData
0x18002ac70  mov     [rsp+0E0h+dwEapConnDataSize], 0; dwEapConnDataSize
0x18002ac78  movdqu  xmmword ptr [rbp+4Fh+eapMethodType.eapType.type], xmm0
0x18002ac7d  call    cs:__imp_EapHostPeerGetMethodProperties
0x18002ac83  test    eax, eax
0x18002ac85  jnz     short loc_18002ACB3
0x18002ac87  mov     r8, [rbp+4Fh+var_68]
0x18002ac8b  xor     ecx, ecx
0x18002ac8d  mov     r9d, r15d
0x18002ac90  cmp     ecx, [rbx+r8]
0x18002ac94  jnb     short loc_18002ACB3
0x18002ac96  mov     rax, [rbx+r8+8]
0x18002ac9b  lea     rdx, [rcx+rcx*2]
0x18002ac9f  cmp     dword ptr [rax+rdx*8], 18h
0x18002aca3  jz      short loc_18002ACAA
0x18002aca5  add     ecx, r9d
0x18002aca8  jmp     short loc_18002AC90
0x18002acaa  cmp     dword ptr [rax+rdx*8+0Ch], 0
0x18002acaf  cmovnz  edi, r9d
0x18002acb3  mov     rcx, [rbp+4Fh+ppEapError]; pEapError
0x18002acb7  test    rcx, rcx
0x18002acba  jz      short loc_18002ACCA
0x18002acbc  call    cs:__imp_EapHostPeerFreeErrorMemory
0x18002acc2  mov     [rbp+4Fh+ppEapError], 0
0x18002acca  mov     r14, [rbp+4Fh+var_90]
0x18002acce  inc     esi
0x18002acd0  test    edi, edi
0x18002acd2  jz      loc_18002ABEF
0x18002acd8  mov     r15d, 2
0x18002acde  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ace5  lea     rsi, WPP_GLOBAL_Control
0x18002acec  cmp     rcx, rsi
0x18002acef  jz      short loc_18002AD3E
0x18002acf1  test    byte ptr [rcx+44h], 4
0x18002acf5  jz      short loc_18002AD1B
0x18002acf7  mov     rcx, [rcx+38h]
0x18002acfb  lea     edx, [r15+20h]
0x18002acff  lea     r8, WPP_cf2b0dcf9cd735c0c1c863ae54fcb446_Traceguids
0x18002ad06  call    WPP_SF_
0x18002ad0b  jmp     short loc_18002AD14
0x18002ad0d  lea     rsi, WPP_GLOBAL_Control
0x18002ad14  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ad1b  cmp     rcx, rsi
0x18002ad1e  jz      short loc_18002AD3E
0x18002ad20  test    byte ptr [rcx+44h], 4
0x18002ad24  jz      short loc_18002AD3E
0x18002ad26  mov     rcx, [rcx+38h]
0x18002ad2a  lea     r8, WPP_cf2b0dcf9cd735c0c1c863ae54fcb446_Traceguids
0x18002ad31  mov     edx, 23h ; '#'
0x18002ad36  mov     r9d, r15d
0x18002ad39  call    WPP_SF_d
0x18002ad3e  lea     ecx, ds:0[r15*4]
0x18002ad46  mov     r9d, 17Ah
0x18002ad4c  lea     r8, aProfilemgrcrea; "ProfileMgrCreateDiscoveryProfiles"
0x18002ad53  lea     rdx, [rbp+4Fh+var_60]
0x18002ad57  call    cs:__imp_AllocateMemory
0x18002ad5d  mov     ebx, eax
0x18002ad5f  test    eax, eax
0x18002ad61  jz      short loc_18002AD9F
0x18002ad63  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ad6a  mov     r13d, 1
0x18002ad70  cmp     rcx, rsi
0x18002ad73  jz      loc_18002AFBE
0x18002ad79  test    [rcx+44h], r13b
0x18002ad7d  jz      loc_18002AFBE
0x18002ad83  lea     edx, [r13+23h]
0x18002ad87  mov     rcx, [rcx+38h]
0x18002ad8b  lea     r8, WPP_cf2b0dcf9cd735c0c1c863ae54fcb446_Traceguids
0x18002ad92  mov     r9d, eax
0x18002ad95  call    WPP_SF_d
0x18002ad9a  jmp     loc_18002AFBE
0x18002ad9f  lea     ecx, ds:0[r15*8]
0x18002ada7  mov     r9d, 17Dh
0x18002adad  lea     r8, aProfilemgrcrea; "ProfileMgrCreateDiscoveryProfiles"
0x18002adb4  lea     rdx, [rbp+4Fh+var_80]
0x18002adb8  call    cs:__imp_AllocateMemory
0x18002adbe  mov     ebx, eax
0x18002adc0  test    eax, eax
0x18002adc2  jz      short loc_18002ADEA
0x18002adc4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002adcb  mov     r13d, 1
0x18002add1  cmp     rcx, rsi
0x18002add4  jz      loc_18002AFBE
0x18002adda  test    [rcx+44h], r13b
0x18002adde  jz      loc_18002AFBE
0x18002ade4  lea     edx, [r13+24h]
0x18002ade8  jmp     short loc_18002AD87
0x18002adea  xor     r9d, r9d
0x18002aded  lea     rdx, [rbp+4Fh+var_78]
0x18002adf1  mov     r8d, r13d
0x18002adf4  lea     rcx, [rbp+4Fh+var_88]
0x18002adf8  call    OneXHlpCreateDefaultProfile
0x18002adfd  mov     ebx, eax
0x18002adff  test    eax, eax
0x18002ae01  jz      short loc_18002AE2C
0x18002ae03  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ae0a  mov     r13d, 1
0x18002ae10  cmp     rcx, rsi
0x18002ae13  jz      loc_18002AFBE
0x18002ae19  test    [rcx+44h], r13b
0x18002ae1d  jz      loc_18002AFBE
0x18002ae23  lea     edx, [r13+25h]
0x18002ae27  jmp     loc_18002AD87
0x18002ae2c  mov     rax, [rbp+4Fh+var_88]
0x18002ae30  mov     r13d, 1
0x18002ae36  xor     esi, esi
0x18002ae38  bts     dword ptr [rax+8], 7
0x18002ae3d  mov     rax, [rbp+4Fh+var_88]
0x18002ae41  mov     [rax+28h], r13d
0x18002ae45  mov     rax, [rbp+4Fh+var_88]
0x18002ae49  or      dword ptr [rax+8], 10h
0x18002ae4d  mov     rax, [rbp+4Fh+var_88]
0x18002ae51  mov     dword ptr [rax+1Ch], 5
0x18002ae58  mov     rax, [rbp+4Fh+var_88]
0x18002ae5c  or      dword ptr [rax+8], 20h
0x18002ae60  mov     rax, [rbp+4Fh+var_88]
0x18002ae64  mov     [rax+20h], r13d
0x18002ae68  mov     rax, [rbp+4Fh+var_88]
0x18002ae6c  or      [rax+8], r13d
0x18002ae70  mov     rax, [rbp+4Fh+var_88]
0x18002ae74  mov     dword ptr [rax+0Ch], 10h
0x18002ae7b  test    edi, edi
0x18002ae7d  jz      short loc_18002AEDE
0x18002ae7f  mov     r9d, [rbp+4Fh+var_78]
0x18002ae83  mov     r8, [rbp+4Fh+var_88]
0x18002ae87  mov     rdx, [rbp+4Fh+var_60]
0x18002ae8b  mov     rcx, [rbp+4Fh+var_80]
0x18002ae8f  call    cs:__imp_SetBufferAndLength
0x18002ae95  mov     ebx, eax
0x18002ae97  test    eax, eax
0x18002ae99  jz      short loc_18002AEC5
0x18002ae9b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aea2  lea     rsi, WPP_GLOBAL_Control
0x18002aea9  cmp     rcx, rsi
0x18002aeac  jz      loc_18002AFBE
0x18002aeb2  test    [rcx+44h], r13b
0x18002aeb6  jz      loc_18002AFBE
0x18002aebc  lea     edx, [r13+26h]
0x18002aec0  jmp     loc_18002AD87
0x18002aec5  mov     rax, [rbp+4Fh+var_80]
0x18002aec9  mov     esi, r13d
0x18002aecc  mov     rcx, [rax]
0x18002aecf  or      dword ptr [rcx+8], 4
0x18002aed3  mov     rax, [rbp+4Fh+var_80]
0x18002aed7  mov     rcx, [rax]
0x18002aeda  mov     [rcx+14h], r13d
0x18002aede  mov     rax, [rbp+4Fh+var_60]
0x18002aee2  mov     r9d, [rbp+4Fh+var_78]
0x18002aee6  mov     r8, [rbp+4Fh+var_88]
0x18002aeea  mov     r14d, esi
0x18002aeed  lea     rdx, [rax+r14*4]
0x18002aef1  mov     rax, [rbp+4Fh+var_80]
0x18002aef5  lea     rcx, [rax+r14*8]
0x18002aef9  call    cs:__imp_SetBufferAndLength
0x18002aeff  mov     ebx, eax
0x18002af01  test    eax, eax
0x18002af03  jz      short loc_18002AF30
0x18002af05  mov     rcx, cs:WPP_GLOBAL_Control
0x18002af0c  lea     rsi, WPP_GLOBAL_Control
0x18002af13  cmp     rcx, rsi
0x18002af16  jz      loc_18002AFBE
0x18002af1c  test    [rcx+44h], r13b
0x18002af20  jz      loc_18002AFBE
0x18002af26  mov     edx, 28h ; '('
0x18002af2b  jmp     loc_18002AD87
0x18002af30  mov     rax, [rbp+4Fh+var_80]
0x18002af34  mov     rcx, [rax+r14*8]
0x18002af38  or      dword ptr [rcx+8], 4
0x18002af3c  mov     rax, [rbp+4Fh+var_80]
0x18002af40  neg     edi
0x18002af42  sbb     edx, edx
  ... truncated ...
```
