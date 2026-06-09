# FwHttpProxyIndicateProxy

- ea: `0x1800a66b4`
- end: `0x1800a6933`
- name: `FwHttpProxyIndicateProxy`
- size: `639`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800ba450`
- `0x1800c65e0`

## callees

- `0x18000af3c`
- `0x180044aec`
- `0x180044bd0`
- `0x180044ca4`
- `0x180058430`
- `0x18006f520`
- `0x18006ffc8`
- `0x1800a641c`
- `0x1800a66b4`

## import_xrefs

- `fwbase!IsAddressesEmpty` at `0x1800a6760`
- `fwbase!IsAddressesEmpty` at `0x1800a6760`
- `fwbase!FwHResultToWindowsError` at `0x1800a679b`
- `fwbase!FwHResultToWindowsError` at `0x1800a67f2`
- `fwbase!FwHResultToWindowsError` at `0x1800a6895`
- `fwbase!FwHResultToWindowsError` at `0x1800a679b`
- `fwbase!FwHResultToWindowsError` at `0x1800a67f2`
- `fwbase!FwHResultToWindowsError` at `0x1800a6895`
- `fwbase!FwStringCopy` at `0x1800a6793`
- `fwbase!FwStringCopy` at `0x1800a67ea`
- `fwbase!FwStringCopy` at `0x1800a6793`
- `fwbase!FwStringCopy` at `0x1800a67ea`
- `fwbase!FwCriticalSectionEnter` at `0x1800a6712`
- `fwbase!FwCriticalSectionEnter` at `0x1800a671f`
- `fwbase!FwCriticalSectionEnter` at `0x1800a6712`
- `fwbase!FwCriticalSectionEnter` at `0x1800a671f`
- `fwbase!FwCriticalSectionLeave` at `0x1800a6871`
- `fwbase!FwCriticalSectionLeave` at `0x1800a687e`
- `fwbase!FwCriticalSectionLeave` at `0x1800a68dd`
- `fwbase!FwCriticalSectionLeave` at `0x1800a68ea`
- `fwbase!FwCriticalSectionLeave` at `0x1800a6871`
- `fwbase!FwCriticalSectionLeave` at `0x1800a687e`
- `fwbase!FwCriticalSectionLeave` at `0x1800a68dd`
- `fwbase!FwCriticalSectionLeave` at `0x1800a68ea`
- `FWPolicyIOMgr!FwAreAllContainedInAddresses` at `0x1800a6735`
- `FWPolicyIOMgr!FwAreAllContainedInAddresses` at `0x1800a674f`
- `FWPolicyIOMgr!FwAreAllContainedInAddresses` at `0x1800a6779`
- `FWPolicyIOMgr!FwAreAllContainedInAddresses` at `0x1800a6735`
- `FWPolicyIOMgr!FwAreAllContainedInAddresses` at `0x1800a674f`
- `FWPolicyIOMgr!FwAreAllContainedInAddresses` at `0x1800a6779`

## pseudocode

```c
__int64 __fastcall FwHttpProxyIndicateProxy(__int64 a1, __int64 a2)
{
  unsigned int v4; // ebx
  int v5; // edi
  unsigned int v6; // eax
  __int64 v7; // rcx
  __int64 v8; // rdx
  unsigned int v9; // eax
  unsigned int v10; // eax
  _OWORD v12[2]; // [rsp+20h] [rbp-49h] BYREF
  _BYTE v13[72]; // [rsp+40h] [rbp-29h] BYREF
  int v14; // [rsp+88h] [rbp+1Fh]
  __int64 v15; // [rsp+90h] [rbp+27h]

  v4 = 0;
  memset_0(v12, 0, 0x78u);
  *(_QWORD *)&v12[0] = a1;
  *((_QWORD *)&v12[0] + 1) = a2;
  v14 = 32;
  FwHttpProxyResolveProxyNames((struct _FW_HTTP_URL_PROXY_ADDRESS_ENTRY *)v12);
  FwCriticalSectionEnter(qword_18012C4F0);
  FwCriticalSectionEnter(qword_18012C538);
  if ( qword_18012C648 && (unsigned int)FwAreAllContainedInAddresses(v13) == 1
    || (unsigned int)FwAreAllContainedInAddresses(v13)
    && ((unsigned int)IsAddressesEmpty(&xmmword_18012C5B0) || (unsigned int)FwAreAllContainedInAddresses(v13)) )
  {
    v5 = 0;
    goto LABEL_24;
  }
  v5 = 1;
  v6 = FwStringCopy(a1, v12);
  v4 = FwHResultToWindowsError(v6);
  if ( v4 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v8 = 72;
LABEL_10:
      WPP_SF_d(*(_QWORD *)(v7 + 16), v8, WPP_4fbb26be2b1a31d69c3c15e2f1ed7fd2_Traceguids, v4);
      goto LABEL_24;
    }
    goto LABEL_24;
  }
  v9 = FwStringCopy(a2, (char *)v12 + 8);
  v4 = FwHResultToWindowsError(v9);
  if ( v4 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v8 = 73;
      goto LABEL_10;
    }
LABEL_24:
    FwCriticalSectionLeave(qword_18012C538);
    FwCriticalSectionLeave(qword_18012C4F0);
    if ( !v5 )
    {
      v15 = 0;
      v12[0] = 0;
      FwHttpProxyEmptyProxyAndAddresses((struct _FW_HTTP_URL_PROXY_ADDRESS_ENTRY *)v12);
    }
    return v4;
  }
  v4 = FwHttpProxyUrlProxyAddressTableAddEntry((struct _FW_HTTP_URL_PROXY_ADDRESS_ENTRY *)v12);
  if ( v4 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v8 = 74;
      goto LABEL_10;
    }
    goto LABEL_24;
  }
  FwHttpProxyConglomerateProxyAddresses(3, 0);
  FwCriticalSectionLeave(qword_18012C538);
  FwCriticalSectionLeave(qword_18012C4F0);
  v10 = FwDynDataInterIntraAddressUpdate(0x7FFFFFFF, 2);
  v4 = FwHResultToWindowsError(v10);
  if ( v4 && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 75, WPP_4fbb26be2b1a31d69c3c15e2f1ed7fd2_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x1800a66b4  mov     [rsp-8+arg_10], rbx
0x1800a66b9  mov     [rsp-8+arg_18], rsi
0x1800a66be  push    rbp
0x1800a66bf  push    rdi
0x1800a66c0  push    r14
0x1800a66c2  lea     rbp, [rsp-47h]
0x1800a66c7  sub     rsp, 0B0h
0x1800a66ce  mov     rax, cs:__security_cookie
0x1800a66d5  xor     rax, rsp
0x1800a66d8  mov     [rbp+57h+var_20], rax
0x1800a66dc  mov     r14, rdx
0x1800a66df  mov     rsi, rcx
0x1800a66e2  xor     ebx, ebx
0x1800a66e4  lea     rcx, [rbp+57h+var_A0]; void *
0x1800a66e8  xor     edx, edx; Val
0x1800a66ea  lea     r8d, [rbx+78h]; Size
0x1800a66ee  call    memset_0
0x1800a66f3  lea     rcx, [rbp+57h+var_A0]; struct _FW_HTTP_URL_PROXY_ADDRESS_ENTRY *
0x1800a66f7  mov     qword ptr [rbp+57h+var_A0], rsi
0x1800a66fb  mov     qword ptr [rbp+57h+var_A0+8], r14
0x1800a66ff  mov     [rbp+57h+var_38], 20h ; ' '
0x1800a6706  call    ?FwHttpProxyResolveProxyNames@@YAKPEAU_FW_HTTP_URL_PROXY_ADDRESS_ENTRY@@@Z; FwHttpProxyResolveProxyNames(_FW_HTTP_URL_PROXY_ADDRESS_ENTRY *)
0x1800a670b  lea     rcx, qword_18012C4F0
0x1800a6712  call    cs:__imp_FwCriticalSectionEnter
0x1800a6718  lea     rcx, qword_18012C538
0x1800a671f  call    cs:__imp_FwCriticalSectionEnter
0x1800a6725  mov     rdx, cs:qword_18012C648
0x1800a672c  test    rdx, rdx
0x1800a672f  jz      short loc_1800A6744
0x1800a6731  lea     rcx, [rbp+57h+var_80]
0x1800a6735  call    cs:__imp_FwAreAllContainedInAddresses
0x1800a673b  cmp     eax, 1
0x1800a673e  jz      loc_1800A68D4
0x1800a6744  lea     rdx, xmmword_18012C568
0x1800a674b  lea     rcx, [rbp+57h+var_80]
0x1800a674f  call    cs:__imp_FwAreAllContainedInAddresses
0x1800a6755  test    eax, eax
0x1800a6757  jz      short loc_1800A6787
0x1800a6759  lea     rcx, xmmword_18012C5B0
0x1800a6760  call    cs:__imp_IsAddressesEmpty
0x1800a6766  test    eax, eax
0x1800a6768  jnz     loc_1800A68D4
0x1800a676e  lea     rdx, xmmword_18012C5B0
0x1800a6775  lea     rcx, [rbp+57h+var_80]
0x1800a6779  call    cs:__imp_FwAreAllContainedInAddresses
0x1800a677f  test    eax, eax
0x1800a6781  jnz     loc_1800A68D4
0x1800a6787  lea     rdx, [rbp+57h+var_A0]
0x1800a678b  mov     rcx, rsi
0x1800a678e  mov     edi, 1
0x1800a6793  call    cs:__imp_FwStringCopy
0x1800a6799  mov     ecx, eax
0x1800a679b  call    cs:__imp_FwHResultToWindowsError
0x1800a67a1  mov     ebx, eax
0x1800a67a3  test    eax, eax
0x1800a67a5  jz      short loc_1800A67E3
0x1800a67a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a67ae  lea     rax, WPP_GLOBAL_Control
0x1800a67b5  cmp     rcx, rax
0x1800a67b8  jz      loc_1800A68D6
0x1800a67be  test    [rcx+1Ch], dil
0x1800a67c2  jz      loc_1800A68D6
0x1800a67c8  lea     edx, [rdi+47h]
0x1800a67cb  mov     rcx, [rcx+10h]
0x1800a67cf  lea     r8, WPP_4fbb26be2b1a31d69c3c15e2f1ed7fd2_Traceguids
0x1800a67d6  mov     r9d, ebx
0x1800a67d9  call    WPP_SF_d
0x1800a67de  jmp     loc_1800A68D6
0x1800a67e3  lea     rdx, [rbp+57h+var_A0+8]
0x1800a67e7  mov     rcx, r14
0x1800a67ea  call    cs:__imp_FwStringCopy
0x1800a67f0  mov     ecx, eax
0x1800a67f2  call    cs:__imp_FwHResultToWindowsError
0x1800a67f8  mov     ebx, eax
0x1800a67fa  test    eax, eax
0x1800a67fc  jz      short loc_1800A6826
0x1800a67fe  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a6805  lea     rax, WPP_GLOBAL_Control
0x1800a680c  cmp     rcx, rax
0x1800a680f  jz      loc_1800A68D6
0x1800a6815  test    byte ptr [rcx+1Ch], 1
0x1800a6819  jz      loc_1800A68D6
0x1800a681f  mov     edx, 49h ; 'I'
0x1800a6824  jmp     short loc_1800A67CB
0x1800a6826  lea     rcx, [rbp+57h+var_A0]; struct _FW_HTTP_URL_PROXY_ADDRESS_ENTRY *
0x1800a682a  call    ?FwHttpProxyUrlProxyAddressTableAddEntry@@YAKPEAU_FW_HTTP_URL_PROXY_ADDRESS_ENTRY@@@Z; FwHttpProxyUrlProxyAddressTableAddEntry(_FW_HTTP_URL_PROXY_ADDRESS_ENTRY *)
0x1800a682f  mov     ebx, eax
0x1800a6831  test    eax, eax
0x1800a6833  jz      short loc_1800A6860
0x1800a6835  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a683c  lea     rax, WPP_GLOBAL_Control
0x1800a6843  cmp     rcx, rax
0x1800a6846  jz      loc_1800A68D6
0x1800a684c  test    byte ptr [rcx+1Ch], 1
0x1800a6850  jz      loc_1800A68D6
0x1800a6856  mov     edx, 4Ah ; 'J'
0x1800a685b  jmp     loc_1800A67CB
0x1800a6860  xor     edx, edx
0x1800a6862  lea     ecx, [rdx+3]
0x1800a6865  call    ?FwHttpProxyConglomerateProxyAddresses@@YAKW4FW_EVENT_HTTP_PROXY_CHANGE_TYPE_@@PEAH@Z; FwHttpProxyConglomerateProxyAddresses(FW_EVENT_HTTP_PROXY_CHANGE_TYPE_,int *)
0x1800a686a  lea     rcx, qword_18012C538
0x1800a6871  call    cs:__imp_FwCriticalSectionLeave
0x1800a6877  lea     rcx, qword_18012C4F0
0x1800a687e  call    cs:__imp_FwCriticalSectionLeave
0x1800a6884  mov     edx, 2
0x1800a6889  mov     ecx, 7FFFFFFFh
0x1800a688e  call    FwDynDataInterIntraAddressUpdate
0x1800a6893  mov     ecx, eax
0x1800a6895  call    cs:__imp_FwHResultToWindowsError
0x1800a689b  mov     ebx, eax
0x1800a689d  test    eax, eax
0x1800a689f  jz      short loc_1800A690D
0x1800a68a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a68a8  lea     rax, WPP_GLOBAL_Control
0x1800a68af  cmp     rcx, rax
0x1800a68b2  jz      short loc_1800A690D
0x1800a68b4  test    byte ptr [rcx+1Ch], 1
0x1800a68b8  jz      short loc_1800A690D
0x1800a68ba  mov     rcx, [rcx+10h]
0x1800a68be  lea     r8, WPP_4fbb26be2b1a31d69c3c15e2f1ed7fd2_Traceguids
0x1800a68c5  mov     edx, 4Bh ; 'K'
0x1800a68ca  mov     r9d, ebx
0x1800a68cd  call    WPP_SF_d
0x1800a68d2  jmp     short loc_1800A690D
0x1800a68d4  xor     edi, edi
0x1800a68d6  lea     rcx, qword_18012C538
0x1800a68dd  call    cs:__imp_FwCriticalSectionLeave
0x1800a68e3  lea     rcx, qword_18012C4F0
0x1800a68ea  call    cs:__imp_FwCriticalSectionLeave
0x1800a68f0  test    edi, edi
0x1800a68f2  jnz     short loc_1800A690D
0x1800a68f4  xorps   xmm0, xmm0
0x1800a68f7  mov     [rbp+57h+var_30], 0
0x1800a68ff  lea     rcx, [rbp+57h+var_A0]; struct _FW_HTTP_URL_PROXY_ADDRESS_ENTRY *
0x1800a6903  movdqa  [rbp+57h+var_A0], xmm0
0x1800a6908  call    ?FwHttpProxyEmptyProxyAndAddresses@@YAXPEAU_FW_HTTP_URL_PROXY_ADDRESS_ENTRY@@@Z; FwHttpProxyEmptyProxyAndAddresses(_FW_HTTP_URL_PROXY_ADDRESS_ENTRY *)
0x1800a690d  mov     eax, ebx
0x1800a690f  mov     rcx, [rbp+57h+var_20]
0x1800a6913  xor     rcx, rsp; StackCookie
0x1800a6916  call    __security_check_cookie
0x1800a691b  lea     r11, [rsp+0C0h+var_10]
0x1800a6923  mov     rbx, [r11+30h]
0x1800a6927  mov     rsi, [r11+38h]
0x1800a692b  mov     rsp, r11
0x1800a692e  pop     r14
0x1800a6930  pop     rdi
0x1800a6931  pop     rbp
0x1800a6932  retn
```
