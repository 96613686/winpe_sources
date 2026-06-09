# LipsApiIpsecPolicyAddForUpdate

- ea: `0x180044da0`
- end: `0x180044e9c`
- name: `LipsApiIpsecPolicyAddForUpdate`
- size: `252`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180019424`

## callees

- `0x18000e510`
- `0x18000f6ac`
- `0x180044da0`
- `0x180045f98`
- `0x180046f60`

## string_xrefs

- `0x180044dd5`: `LipsApiIpsecPolicyAddForUpdate`

## pseudocode

```c
__int64 __fastcall LipsApiIpsecPolicyAddForUpdate(__int64 a1, __int64 a2, __int64 a3)
{
  LPVOID v3; // rbp
  unsigned int QMIpsecFiltersForPolicy; // eax
  unsigned int v7; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  _OWORD v11[3]; // [rsp+20h] [rbp-38h] BYREF

  v3 = gpIniTxSFilter;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      52,
      WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids,
      "LipsApiIpsecPolicyAddForUpdate");
  QMIpsecFiltersForPolicy = LipsStateIpsecPolicyAdd(a1);
  v7 = QMIpsecFiltersForPolicy;
  if ( QMIpsecFiltersForPolicy )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v7;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_13;
    v9 = 53;
    goto LABEL_12;
  }
  v11[0] = *(_OWORD *)*(_QWORD *)(a1 + 56);
  QMIpsecFiltersForPolicy = LipsCreateQMIpsecFiltersForPolicy(v3, a3, v11);
  v7 = QMIpsecFiltersForPolicy;
  if ( !QMIpsecFiltersForPolicy )
    return v7;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v7;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v9 = 55;
LABEL_12:
    WPP_SF_d(v8[2], v9, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids, QMIpsecFiltersForPolicy);
    v8 = WPP_GLOBAL_Control;
  }
LABEL_13:
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x10) != 0 )
    WPP_SF_d(v8[2], 56, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x180044da0  push    rbx
0x180044da2  push    rbp
0x180044da3  push    rsi
0x180044da4  push    rdi
0x180044da5  push    r14
0x180044da7  sub     rsp, 30h
0x180044dab  mov     rbp, cs:gpIniTxSFilter
0x180044db2  mov     rsi, r8
0x180044db5  mov     rdi, rcx
0x180044db8  mov     rcx, cs:WPP_GLOBAL_Control
0x180044dbf  lea     r14, WPP_GLOBAL_Control
0x180044dc6  cmp     rcx, r14
0x180044dc9  jz      short loc_180044DED
0x180044dcb  test    byte ptr [rcx+1Ch], 4
0x180044dcf  jz      short loc_180044DED
0x180044dd1  mov     rcx, [rcx+10h]
0x180044dd5  lea     r9, aLipsapiipsecpo_0; "LipsApiIpsecPolicyAddForUpdate"
0x180044ddc  mov     edx, 34h ; '4'
0x180044de1  lea     r8, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids
0x180044de8  call    WPP_SF_s
0x180044ded  mov     rcx, rdi
0x180044df0  call    LipsStateIpsecPolicyAdd
0x180044df5  mov     ebx, eax
0x180044df7  test    eax, eax
0x180044df9  jz      short loc_180044E18
0x180044dfb  mov     rcx, cs:WPP_GLOBAL_Control
0x180044e02  cmp     rcx, r14
0x180044e05  jz      loc_180044E8F
0x180044e0b  test    byte ptr [rcx+1Ch], 10h
0x180044e0f  jz      short loc_180044E6C
0x180044e11  mov     edx, 35h ; '5'
0x180044e16  jmp     short loc_180044E52
0x180044e18  mov     rax, [rdi+38h]
0x180044e1c  lea     r8, [rsp+58h+var_38]
0x180044e21  mov     rdx, rsi
0x180044e24  mov     rcx, rbp
0x180044e27  movups  xmm0, xmmword ptr [rax]
0x180044e2a  movdqu  [rsp+58h+var_38], xmm0
0x180044e30  call    LipsCreateQMIpsecFiltersForPolicy
0x180044e35  mov     ebx, eax
0x180044e37  test    eax, eax
0x180044e39  jz      short loc_180044E8F
0x180044e3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180044e42  cmp     rcx, r14
0x180044e45  jz      short loc_180044E8F
0x180044e47  test    byte ptr [rcx+1Ch], 10h
0x180044e4b  jz      short loc_180044E6C
0x180044e4d  mov     edx, 37h ; '7'
0x180044e52  mov     rcx, [rcx+10h]
0x180044e56  lea     r8, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids
0x180044e5d  mov     r9d, eax
0x180044e60  call    WPP_SF_d
0x180044e65  mov     rcx, cs:WPP_GLOBAL_Control
0x180044e6c  cmp     rcx, r14
0x180044e6f  jz      short loc_180044E8F
0x180044e71  test    byte ptr [rcx+1Ch], 10h
0x180044e75  jz      short loc_180044E8F
0x180044e77  mov     rcx, [rcx+10h]
0x180044e7b  lea     r8, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids
0x180044e82  mov     edx, 38h ; '8'
0x180044e87  mov     r9d, ebx
0x180044e8a  call    WPP_SF_d
0x180044e8f  mov     eax, ebx
0x180044e91  add     rsp, 30h
0x180044e95  pop     r14
0x180044e97  pop     rdi
0x180044e98  pop     rsi
0x180044e99  pop     rbp
0x180044e9a  pop     rbx
0x180044e9b  retn
```
