# FwHttpProxyIndicateProxy

- ea: `0x1800ac24c`
- end: `0x1800ac4c1`
- name: `FwHttpProxyIndicateProxy`
- size: `629`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800c13d0`
- `0x1800cdab0`

## callees

- `0x18000a710`
- `0x180045c58`
- `0x180045d48`
- `0x180045e40`
- `0x18005d468`
- `0x1800729c0`
- `0x180073488`
- `0x1800abd90`
- `0x1800abf7c`
- `0x1800ac24c`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x1800ac2ef`
- `fwbase!FwHResultToWindowsError` at `0x1800ac3b5`
- `fwbase!FwHResultToWindowsError` at `0x1800ac46d`
- `fwbase!FwHResultToWindowsError` at `0x1800ac2ef`
- `fwbase!FwHResultToWindowsError` at `0x1800ac3b5`
- `fwbase!FwHResultToWindowsError` at `0x1800ac46d`
- `fwbase!FwStringCopy` at `0x1800ac2e1`
- `fwbase!FwStringCopy` at `0x1800ac3a7`
- `fwbase!FwStringCopy` at `0x1800ac2e1`
- `fwbase!FwStringCopy` at `0x1800ac3a7`
- `fwbase!FwCriticalSectionEnter` at `0x1800ac2aa`
- `fwbase!FwCriticalSectionEnter` at `0x1800ac2bd`
- `fwbase!FwCriticalSectionEnter` at `0x1800ac2aa`
- `fwbase!FwCriticalSectionEnter` at `0x1800ac2bd`
- `fwbase!FwCriticalSectionLeave` at `0x1800ac33c`
- `fwbase!FwCriticalSectionLeave` at `0x1800ac34f`
- `fwbase!FwCriticalSectionLeave` at `0x1800ac43d`
- `fwbase!FwCriticalSectionLeave` at `0x1800ac450`
- `fwbase!FwCriticalSectionLeave` at `0x1800ac33c`
- `fwbase!FwCriticalSectionLeave` at `0x1800ac34f`
- `fwbase!FwCriticalSectionLeave` at `0x1800ac43d`
- `fwbase!FwCriticalSectionLeave` at `0x1800ac450`

## pseudocode

```c
__int64 __fastcall FwHttpProxyIndicateProxy(__int64 a1, __int64 a2)
{
  __int128 v2; // rdi
  unsigned int v3; // ebx
  int v4; // r14d
  unsigned int v5; // eax
  unsigned int v6; // eax
  __int64 v7; // rcx
  __int64 v8; // rdx
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  _OWORD v13[6]; // [rsp+20h] [rbp-49h] BYREF
  int v14; // [rsp+88h] [rbp+1Fh]
  __int64 v15; // [rsp+90h] [rbp+27h]

  *((_QWORD *)&v2 + 1) = a2;
  *(_QWORD *)&v2 = a1;
  v3 = 0;
  memset_0(v13, 0, 0x78u);
  v13[0] = v2;
  v14 = 32;
  FwHttpProxyResolveProxyNames((struct _FW_HTTP_URL_PROXY_ADDRESS_ENTRY *)v13);
  FwCriticalSectionEnter(qword_1801326C0);
  FwCriticalSectionEnter(qword_180132708);
  v4 = FwHttpProxyEntryContributesNewProxy((struct _FW_HTTP_URL_PROXY_ADDRESS_ENTRY *)v13);
  if ( v4 != 1 )
    goto LABEL_7;
  v5 = FwStringCopy(v2, v13);
  v6 = FwHResultToWindowsError(v5);
  v3 = v6;
  if ( v6 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v8 = 72;
LABEL_6:
      WPP_SF_d(*(_QWORD *)(v7 + 16), v8, WPP_beda3cd07d663dfecc8ed25415b6e23b_Traceguids, v6);
      goto LABEL_7;
    }
    goto LABEL_7;
  }
  v10 = FwStringCopy(*((_QWORD *)&v2 + 1), (char *)v13 + 8);
  v6 = FwHResultToWindowsError(v10);
  v3 = v6;
  if ( v6 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v8 = 73;
      goto LABEL_6;
    }
LABEL_7:
    FwCriticalSectionLeave(qword_180132708);
    FwCriticalSectionLeave(qword_1801326C0);
    if ( !v4 )
    {
      v15 = 0;
      v13[0] = 0;
      FwHttpProxyEmptyProxyAndAddresses((struct _FW_HTTP_URL_PROXY_ADDRESS_ENTRY *)v13);
    }
    return v3;
  }
  v6 = FwHttpProxyUrlProxyAddressTableAddEntry((struct _FW_HTTP_URL_PROXY_ADDRESS_ENTRY *)v13);
  v3 = v6;
  if ( v6 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v8 = 74;
      goto LABEL_6;
    }
    goto LABEL_7;
  }
  FwHttpProxyConglomerateProxyAddresses(3, 0);
  FwCriticalSectionLeave(qword_180132708);
  FwCriticalSectionLeave(qword_1801326C0);
  v11 = FwDynDataInterIntraAddressUpdate(0x7FFFFFFF, 2);
  v12 = FwHResultToWindowsError(v11);
  v3 = v12;
  if ( v12 && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 75, WPP_beda3cd07d663dfecc8ed25415b6e23b_Traceguids, v12);
  return v3;
}

```

## disassembly

```asm
0x1800ac24c  mov     [rsp-8+arg_10], rbx
0x1800ac251  mov     [rsp-8+arg_18], rsi
0x1800ac256  push    rbp
0x1800ac257  push    rdi
0x1800ac258  push    r14
0x1800ac25a  lea     rbp, [rsp-47h]
0x1800ac25f  sub     rsp, 0B0h
0x1800ac266  mov     rax, cs:__security_cookie
0x1800ac26d  xor     rax, rsp
0x1800ac270  mov     [rbp+57h+var_20], rax
0x1800ac274  mov     rsi, rdx
0x1800ac277  mov     rdi, rcx
0x1800ac27a  xor     ebx, ebx
0x1800ac27c  lea     rcx, [rbp+57h+var_A0]; void *
0x1800ac280  xor     edx, edx; Val
0x1800ac282  lea     r8d, [rbx+78h]; Size
0x1800ac286  call    memset_0
0x1800ac28b  lea     rcx, [rbp+57h+var_A0]; struct _FW_HTTP_URL_PROXY_ADDRESS_ENTRY *
0x1800ac28f  mov     qword ptr [rbp+57h+var_A0], rdi
0x1800ac293  mov     qword ptr [rbp+57h+var_A0+8], rsi
0x1800ac297  mov     [rbp+57h+var_38], 20h ; ' '
0x1800ac29e  call    ?FwHttpProxyResolveProxyNames@@YAKPEAU_FW_HTTP_URL_PROXY_ADDRESS_ENTRY@@@Z; FwHttpProxyResolveProxyNames(_FW_HTTP_URL_PROXY_ADDRESS_ENTRY *)
0x1800ac2a3  lea     rcx, qword_1801326C0
0x1800ac2aa  call    cs:__imp_FwCriticalSectionEnter
0x1800ac2b1  nop     dword ptr [rax+rax+00h]
0x1800ac2b6  lea     rcx, qword_180132708
0x1800ac2bd  call    cs:__imp_FwCriticalSectionEnter
0x1800ac2c4  nop     dword ptr [rax+rax+00h]
0x1800ac2c9  lea     rcx, [rbp+57h+var_A0]; struct _FW_HTTP_URL_PROXY_ADDRESS_ENTRY *
0x1800ac2cd  call    ?FwHttpProxyEntryContributesNewProxy@@YAHPEAU_FW_HTTP_URL_PROXY_ADDRESS_ENTRY@@@Z; FwHttpProxyEntryContributesNewProxy(_FW_HTTP_URL_PROXY_ADDRESS_ENTRY *)
0x1800ac2d2  mov     r14d, eax
0x1800ac2d5  cmp     eax, 1
0x1800ac2d8  jnz     short loc_1800AC335
0x1800ac2da  lea     rdx, [rbp+57h+var_A0]
0x1800ac2de  mov     rcx, rdi
0x1800ac2e1  call    cs:__imp_FwStringCopy
0x1800ac2e8  nop     dword ptr [rax+rax+00h]
0x1800ac2ed  mov     ecx, eax
0x1800ac2ef  call    cs:__imp_FwHResultToWindowsError
0x1800ac2f6  nop     dword ptr [rax+rax+00h]
0x1800ac2fb  mov     ebx, eax
0x1800ac2fd  test    eax, eax
0x1800ac2ff  jz      loc_1800AC3A0
0x1800ac305  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ac30c  lea     rdx, WPP_GLOBAL_Control
0x1800ac313  cmp     rcx, rdx
0x1800ac316  jz      short loc_1800AC335
0x1800ac318  test    [rcx+1Ch], r14b
0x1800ac31c  jz      short loc_1800AC335
0x1800ac31e  lea     edx, [r14+47h]
0x1800ac322  mov     rcx, [rcx+10h]
0x1800ac326  lea     r8, WPP_beda3cd07d663dfecc8ed25415b6e23b_Traceguids
0x1800ac32d  mov     r9d, eax
0x1800ac330  call    WPP_SF_d
0x1800ac335  lea     rcx, qword_180132708
0x1800ac33c  call    cs:__imp_FwCriticalSectionLeave
0x1800ac343  nop     dword ptr [rax+rax+00h]
0x1800ac348  lea     rcx, qword_1801326C0
0x1800ac34f  call    cs:__imp_FwCriticalSectionLeave
0x1800ac356  nop     dword ptr [rax+rax+00h]
0x1800ac35b  test    r14d, r14d
0x1800ac35e  jnz     short loc_1800AC379
0x1800ac360  xorps   xmm0, xmm0
0x1800ac363  mov     [rbp+57h+var_30], 0
0x1800ac36b  lea     rcx, [rbp+57h+var_A0]; struct _FW_HTTP_URL_PROXY_ADDRESS_ENTRY *
0x1800ac36f  movdqa  [rbp+57h+var_A0], xmm0
0x1800ac374  call    ?FwHttpProxyEmptyProxyAndAddresses@@YAXPEAU_FW_HTTP_URL_PROXY_ADDRESS_ENTRY@@@Z; FwHttpProxyEmptyProxyAndAddresses(_FW_HTTP_URL_PROXY_ADDRESS_ENTRY *)
0x1800ac379  mov     eax, ebx
0x1800ac37b  mov     rcx, [rbp+57h+var_20]
0x1800ac37f  xor     rcx, rsp; StackCookie
0x1800ac382  call    __security_check_cookie
0x1800ac387  lea     r11, [rsp+0C0h+var_10]
0x1800ac38f  mov     rbx, [r11+30h]
0x1800ac393  mov     rsi, [r11+38h]
0x1800ac397  mov     rsp, r11
0x1800ac39a  pop     r14
0x1800ac39c  pop     rdi
0x1800ac39d  pop     rbp
0x1800ac39e  retn
0x1800ac3a0  lea     rdx, [rbp+57h+var_A0+8]
0x1800ac3a4  mov     rcx, rsi
0x1800ac3a7  call    cs:__imp_FwStringCopy
0x1800ac3ae  nop     dword ptr [rax+rax+00h]
0x1800ac3b3  mov     ecx, eax
0x1800ac3b5  call    cs:__imp_FwHResultToWindowsError
0x1800ac3bc  nop     dword ptr [rax+rax+00h]
0x1800ac3c1  mov     ebx, eax
0x1800ac3c3  test    eax, eax
0x1800ac3c5  jz      short loc_1800AC3F2
0x1800ac3c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ac3ce  lea     rdx, WPP_GLOBAL_Control
0x1800ac3d5  cmp     rcx, rdx
0x1800ac3d8  jz      loc_1800AC335
0x1800ac3de  test    byte ptr [rcx+1Ch], 1
0x1800ac3e2  jz      loc_1800AC335
0x1800ac3e8  mov     edx, 49h ; 'I'
0x1800ac3ed  jmp     loc_1800AC322
0x1800ac3f2  lea     rcx, [rbp+57h+var_A0]; struct _FW_HTTP_URL_PROXY_ADDRESS_ENTRY *
0x1800ac3f6  call    ?FwHttpProxyUrlProxyAddressTableAddEntry@@YAKPEAU_FW_HTTP_URL_PROXY_ADDRESS_ENTRY@@@Z; FwHttpProxyUrlProxyAddressTableAddEntry(_FW_HTTP_URL_PROXY_ADDRESS_ENTRY *)
0x1800ac3fb  mov     ebx, eax
0x1800ac3fd  test    eax, eax
0x1800ac3ff  jz      short loc_1800AC42C
0x1800ac401  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ac408  lea     rdx, WPP_GLOBAL_Control
0x1800ac40f  cmp     rcx, rdx
0x1800ac412  jz      loc_1800AC335
0x1800ac418  test    byte ptr [rcx+1Ch], 1
0x1800ac41c  jz      loc_1800AC335
0x1800ac422  mov     edx, 4Ah ; 'J'
0x1800ac427  jmp     loc_1800AC322
0x1800ac42c  xor     edx, edx
0x1800ac42e  lea     ecx, [rdx+3]
0x1800ac431  call    ?FwHttpProxyConglomerateProxyAddresses@@YAKW4FW_EVENT_HTTP_PROXY_CHANGE_TYPE_@@PEAH@Z; FwHttpProxyConglomerateProxyAddresses(FW_EVENT_HTTP_PROXY_CHANGE_TYPE_,int *)
0x1800ac436  lea     rcx, qword_180132708
0x1800ac43d  call    cs:__imp_FwCriticalSectionLeave
0x1800ac444  nop     dword ptr [rax+rax+00h]
0x1800ac449  lea     rcx, qword_1801326C0
0x1800ac450  call    cs:__imp_FwCriticalSectionLeave
0x1800ac457  nop     dword ptr [rax+rax+00h]
0x1800ac45c  mov     edx, 2
0x1800ac461  mov     ecx, 7FFFFFFFh
0x1800ac466  call    FwDynDataInterIntraAddressUpdate
0x1800ac46b  mov     ecx, eax
0x1800ac46d  call    cs:__imp_FwHResultToWindowsError
0x1800ac474  nop     dword ptr [rax+rax+00h]
0x1800ac479  mov     ebx, eax
0x1800ac47b  test    eax, eax
0x1800ac47d  jz      loc_1800AC379
0x1800ac483  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ac48a  lea     rdx, WPP_GLOBAL_Control
0x1800ac491  cmp     rcx, rdx
0x1800ac494  jz      loc_1800AC379
0x1800ac49a  test    byte ptr [rcx+1Ch], 1
0x1800ac49e  jz      loc_1800AC379
0x1800ac4a4  mov     rcx, [rcx+10h]
0x1800ac4a8  lea     r8, WPP_beda3cd07d663dfecc8ed25415b6e23b_Traceguids
0x1800ac4af  mov     edx, 4Bh ; 'K'
0x1800ac4b4  mov     r9d, eax
0x1800ac4b7  call    WPP_SF_d
0x1800ac4bc  jmp     loc_1800AC379
```
