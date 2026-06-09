# InitializeSPDSecurity

- ea: `0x18000aab4`
- end: `0x18000abe9`
- name: `InitializeSPDSecurity`
- size: `309`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a60c`

## callees

- `0x18000aab4`
- `0x18000abf0`
- `0x18000e510`
- `0x18000e550`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000abcc`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000abcc`

## pseudocode

```c
__int64 InitializeSPDSecurity()
{
  unsigned int v0; // eax
  __int64 v1; // rcx
  PSID pOwner; // rbx
  unsigned int v3; // edi
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  _BYTE *v7; // [rsp+38h] [rbp-21h]
  PSID pSid; // [rsp+50h] [rbp-9h] BYREF
  __int64 v9; // [rsp+58h] [rbp-1h] BYREF
  __int64 v10; // [rsp+60h] [rbp+7h] BYREF
  int v11[6]; // [rsp+68h] [rbp+Fh] BYREF
  int v12[2]; // [rsp+80h] [rbp+27h] BYREF
  PSID v13; // [rsp+88h] [rbp+2Fh]
  __int128 v14; // [rsp+90h] [rbp+37h]
  __int128 v15; // [rsp+A0h] [rbp+47h]

  pSid = 0;
  v10 = 0;
  v14 = 0;
  v15 = 0;
  v0 = CreateAdminAliasSID(&pSid);
  pOwner = pSid;
  v3 = v0;
  if ( v0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_10;
    v5 = 10;
LABEL_9:
    WPP_SF_d(v4[2], v5, WPP_ed468879b1803b25f9bc891025016378_Traceguids, v3);
LABEL_10:
    gpSPDSD = 0;
    goto LABEL_12;
  }
  LOWORD(pSid) = 0;
  *(_QWORD *)v12 = pOwner;
  v11[0] = 983043;
  LOWORD(v9) = 2816;
  v13 = pOwner;
  v11[1] = 0x10000000;
  v3 = BuildSPDObjectProtection(v1, (__int64)&pSid, (__int64)v12, (__int64)v11, (__int64)&v9, pOwner, pOwner, v7, &v10);
  if ( v3 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_10;
    v5 = 12;
    goto LABEL_9;
  }
  gpSPDSD = (PSECURITY_DESCRIPTOR)v10;
LABEL_12:
  if ( pOwner )
    FreeSid(pOwner);
  return v3;
}

```

## disassembly

```asm
0x18000aab4  mov     [rsp-8+arg_0], rbx
0x18000aab9  mov     [rsp-8+arg_8], rdi
0x18000aabe  push    rbp
0x18000aabf  lea     rbp, [rsp-57h]
0x18000aac4  sub     rsp, 0B0h
0x18000aacb  xorps   xmm0, xmm0
0x18000aace  mov     [rbp+57h+pSid], 0
0x18000aad6  xorps   xmm1, xmm1
0x18000aad9  mov     [rbp+57h+var_50], 0
0x18000aae1  lea     rcx, [rbp+57h+pSid]
0x18000aae5  movdqu  [rbp+57h+var_20], xmm0
0x18000aaea  movdqu  [rbp+57h+var_10], xmm1
0x18000aaef  call    CreateAdminAliasSID
0x18000aaf4  mov     rbx, [rbp+57h+pSid]
0x18000aaf8  mov     edi, eax
0x18000aafa  test    eax, eax
0x18000aafc  jz      short loc_18000AB26
0x18000aafe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab05  lea     rax, WPP_GLOBAL_Control
0x18000ab0c  cmp     rcx, rax
0x18000ab0f  jz      loc_18000ABAC
0x18000ab15  test    byte ptr [rcx+1Ch], 10h
0x18000ab19  jz      loc_18000ABAC
0x18000ab1f  mov     edx, 0Ah
0x18000ab24  jmp     short loc_18000AB99
0x18000ab26  lea     rax, [rbp+57h+var_50]
0x18000ab2a  mov     word ptr [rbp+57h+pSid], 0
0x18000ab30  mov     [rsp+0B0h+var_70], rax; __int64
0x18000ab35  lea     r9, [rbp+57h+var_48]; int
0x18000ab39  mov     [rsp+0B0h+pGroup], rbx; pGroup
0x18000ab3e  lea     rax, [rbp+57h+var_58]
0x18000ab42  mov     [rsp+0B0h+pOwner], rbx; pOwner
0x18000ab47  lea     r8, [rbp+57h+var_30]; int
0x18000ab4b  lea     rdx, [rbp+57h+pSid]; int
0x18000ab4f  mov     [rsp+0B0h+var_90], rax; __int64
0x18000ab54  mov     qword ptr [rbp+57h+var_30], rbx
0x18000ab58  mov     [rbp+57h+var_48], 0F0003h
0x18000ab5f  mov     word ptr [rbp+57h+var_58], 0B00h
0x18000ab65  mov     [rbp+57h+var_28], rbx
0x18000ab69  mov     [rbp+57h+var_44], 10000000h
0x18000ab70  call    BuildSPDObjectProtection
0x18000ab75  mov     edi, eax
0x18000ab77  test    eax, eax
0x18000ab79  jz      short loc_18000ABB9
0x18000ab7b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab82  lea     rax, WPP_GLOBAL_Control
0x18000ab89  cmp     rcx, rax
0x18000ab8c  jz      short loc_18000ABAC
0x18000ab8e  test    byte ptr [rcx+1Ch], 10h
0x18000ab92  jz      short loc_18000ABAC
0x18000ab94  mov     edx, 0Ch
0x18000ab99  mov     rcx, [rcx+10h]
0x18000ab9d  lea     r8, WPP_ed468879b1803b25f9bc891025016378_Traceguids
0x18000aba4  mov     r9d, edi
0x18000aba7  call    WPP_SF_d
0x18000abac  mov     cs:gpSPDSD, 0
0x18000abb7  jmp     short loc_18000ABC4
0x18000abb9  mov     rax, [rbp+57h+var_50]
0x18000abbd  mov     cs:gpSPDSD, rax
0x18000abc4  test    rbx, rbx
0x18000abc7  jz      short loc_18000ABD2
0x18000abc9  mov     rcx, rbx; pSid
0x18000abcc  call    cs:__imp_FreeSid
0x18000abd2  lea     r11, [rsp+0B0h+var_s0]
0x18000abda  mov     eax, edi
0x18000abdc  mov     rbx, [r11+10h]
0x18000abe0  mov     rdi, [r11+18h]
0x18000abe4  mov     rsp, r11
0x18000abe7  pop     rbp
0x18000abe8  retn
```
