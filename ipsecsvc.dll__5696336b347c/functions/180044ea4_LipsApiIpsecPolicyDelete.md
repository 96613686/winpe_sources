# LipsApiIpsecPolicyDelete

- ea: `0x180044ea4`
- end: `0x180044f55`
- name: `LipsApiIpsecPolicyDelete`
- size: `177`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180018a94`
- `0x180018f78`

## callees

- `0x18000e510`
- `0x18000f6ac`
- `0x180044ea4`
- `0x180047094`

## string_xrefs

- `0x180044ece`: `LipsApiIpsecPolicyDelete`

## pseudocode

```c
__int64 __fastcall LipsApiIpsecPolicyDelete(__int64 a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  _QWORD *v4; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      49,
      WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids,
      "LipsApiIpsecPolicyDelete");
  v2 = LipsStateIpsecPolicyDelete(a1);
  v3 = v2;
  if ( v2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids, v2);
        v4 = WPP_GLOBAL_Control;
      }
      if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x10) != 0 )
        WPP_SF_d(v4[2], 51, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids, v3);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180044ea4  mov     [rsp+arg_0], rbx
0x180044ea9  push    rdi
0x180044eaa  sub     rsp, 20h
0x180044eae  mov     rbx, rcx
0x180044eb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180044eb8  lea     rdi, WPP_GLOBAL_Control
0x180044ebf  cmp     rcx, rdi
0x180044ec2  jz      short loc_180044EE6
0x180044ec4  test    byte ptr [rcx+1Ch], 4
0x180044ec8  jz      short loc_180044EE6
0x180044eca  mov     rcx, [rcx+10h]
0x180044ece  lea     r9, aLipsapiipsecpo_2; "LipsApiIpsecPolicyDelete"
0x180044ed5  mov     edx, 31h ; '1'
0x180044eda  lea     r8, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids
0x180044ee1  call    WPP_SF_s
0x180044ee6  mov     rcx, rbx
0x180044ee9  call    LipsStateIpsecPolicyDelete
0x180044eee  mov     ebx, eax
0x180044ef0  test    eax, eax
0x180044ef2  jz      short loc_180044F48
0x180044ef4  mov     rcx, cs:WPP_GLOBAL_Control
0x180044efb  cmp     rcx, rdi
0x180044efe  jz      short loc_180044F48
0x180044f00  test    byte ptr [rcx+1Ch], 10h
0x180044f04  jz      short loc_180044F25
0x180044f06  mov     rcx, [rcx+10h]
0x180044f0a  lea     r8, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids
0x180044f11  mov     edx, 32h ; '2'
0x180044f16  mov     r9d, eax
0x180044f19  call    WPP_SF_d
0x180044f1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180044f25  cmp     rcx, rdi
0x180044f28  jz      short loc_180044F48
0x180044f2a  test    byte ptr [rcx+1Ch], 10h
0x180044f2e  jz      short loc_180044F48
0x180044f30  mov     rcx, [rcx+10h]
0x180044f34  lea     r8, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids
0x180044f3b  mov     edx, 33h ; '3'
0x180044f40  mov     r9d, ebx
0x180044f43  call    WPP_SF_d
0x180044f48  mov     eax, ebx
0x180044f4a  mov     rbx, [rsp+28h+arg_0]
0x180044f4f  add     rsp, 20h
0x180044f53  pop     rdi
0x180044f54  retn
```
