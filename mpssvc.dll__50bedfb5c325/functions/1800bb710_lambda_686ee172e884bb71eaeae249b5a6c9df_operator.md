# _lambda_686ee172e884bb71eaeae249b5a6c9df_::operator()

- ea: `0x1800bb710`
- end: `0x1800bb905`
- name: `_lambda_686ee172e884bb71eaeae249b5a6c9df_::operator()`
- size: `501`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800bcadc`

## callees

- `0x180035c98`
- `0x180039644`
- `0x18003d708`
- `0x18005a5d4`
- `0x18005a810`
- `0x1800729c0`
- `0x1800bb710`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800bb83b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800bb83b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bb86d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bb8f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bb86d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bb8f3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800bb824`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800bb824`
- `FWPolicyIOMgr!FwFreeRules` at `0x1800bb7b1`
- `FWPolicyIOMgr!FwFreeRules` at `0x1800bb89e`
- `FWPolicyIOMgr!FwFreeRules` at `0x1800bb7b1`
- `FWPolicyIOMgr!FwFreeRules` at `0x1800bb89e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall lambda_686ee172e884bb71eaeae249b5a6c9df_::operator()(__int64 a1, unsigned int a2, void *a3)
{
  unsigned int v4; // eax
  __int64 v5; // rdx
  unsigned int v6; // ebx
  struct _tag_FW_RULE *v8; // rbx
  const WCHAR *v9; // rcx
  unsigned int v10; // eax
  unsigned int v11; // [rsp+20h] [rbp-60h]
  struct _tag_FW_RPC_STORE_HANDLE *v12; // [rsp+58h] [rbp-28h] BYREF
  struct _tag_FW_RULE *v13; // [rsp+60h] [rbp-20h] BYREF
  PSID Sid; // [rsp+68h] [rbp-18h] BYREF
  unsigned int v15; // [rsp+70h] [rbp-10h] BYREF
  int v16; // [rsp+74h] [rbp-Ch] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v12 = 0;
  v13 = 0;
  v15 = 0;
  v4 = SvrImpl_FWOpenPolicyStore(0, 545, a2, 2u, 0, (__int64 *)&v12);
  if ( v4 )
  {
    v5 = 643;
LABEL_3:
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v5,
           (unsigned int)"onecore\\net\\mpssvc\\lics\\fwnetappisolation\\lib\\fw_moneis_mgr.cpp",
           (const char *)v4,
           v11);
    goto LABEL_4;
  }
  v4 = SvrImpl_FWEnumFirewallRules2_33(0, v12, 0x30000u, 0x7FFFFFFFu, 7u, &v15, &v13);
  if ( v4 )
  {
    v5 = 652;
    goto LABEL_3;
  }
  v8 = v13;
  if ( !v13 )
  {
LABEL_19:
    if ( v12 )
      SvrImpl_FWClosePolicyStore(0, (void **)&v12);
    if ( v13 )
      FwFreeRules(v13, 0);
    return 0;
  }
  while ( 1 )
  {
    v9 = (const WCHAR *)*((_QWORD *)v8 + 47);
    if ( v9 )
      break;
LABEL_18:
    v8 = *(struct _tag_FW_RULE **)v8;
    if ( !v8 )
      goto LABEL_19;
  }
  Sid = 0;
  if ( !ConvertStringSidToSidW(v9, &Sid)
    || !EqualSid(Sid, a3)
    || (v16 = 0, (v10 = SvrImpl_FWSetFirewallRule2_33(0, v12, v8, (enum _tag_FW_RULE_STATUS *)&v16)) == 0) )
  {
    if ( Sid )
      LocalFree(Sid);
    goto LABEL_18;
  }
  v6 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)0x297,
         (unsigned int)"onecore\\net\\mpssvc\\lics\\fwnetappisolation\\lib\\fw_moneis_mgr.cpp",
         (const char *)v10,
         v11);
  if ( Sid )
    LocalFree(Sid);
LABEL_4:
  if ( v12 )
    SvrImpl_FWClosePolicyStore(0, (void **)&v12);
  if ( v13 )
    FwFreeRules(v13, 0);
  return v6;
}

```

## disassembly

```asm
0x1800bb710  mov     [rsp-18h+arg_0], rbx
0x1800bb715  push    rbp
0x1800bb716  push    rsi
0x1800bb717  push    rdi
0x1800bb718  mov     rbp, rsp
0x1800bb71b  sub     rsp, 80h
0x1800bb722  mov     rax, cs:__security_cookie
0x1800bb729  xor     rax, rsp
0x1800bb72c  mov     [rbp+var_8], rax
0x1800bb730  mov     rdi, r8
0x1800bb733  mov     r8d, edx
0x1800bb736  xor     esi, esi
0x1800bb738  mov     [rbp+var_28], rsi
0x1800bb73c  mov     [rbp+var_20], rsi
0x1800bb740  mov     [rbp+var_10], esi
0x1800bb743  lea     rax, [rbp+var_28]
0x1800bb747  mov     [rbp+var_40], rax
0x1800bb74b  lea     rax, [rbp+var_20]
0x1800bb74f  mov     [rbp+var_38], rax
0x1800bb753  mov     [rbp+var_30], 1
0x1800bb757  mov     edx, 221h
0x1800bb75c  lea     rax, [rbp+var_28]
0x1800bb760  mov     [rsp+80h+var_58], rax
0x1800bb765  mov     dword ptr [rsp+80h+var_60], esi; unsigned int
0x1800bb769  xor     ecx, ecx
0x1800bb76b  mov     r9d, 2
0x1800bb771  call    ?SvrImpl_FWOpenPolicyStore@@YAKPEAXGW4_tag_FW_STORE_TYPE@@W4_tag_FW_POLICY_ACCESS_RIGHT@@KPEAPEAX@Z; SvrImpl_FWOpenPolicyStore(void *,ushort,_tag_FW_STORE_TYPE,_tag_FW_POLICY_ACCESS_RIGHT,ulong,void * *)
0x1800bb776  test    eax, eax
0x1800bb778  jz      short loc_1800BB7C4
0x1800bb77a  mov     edx, 283h; void *
0x1800bb77f  mov     r9d, eax; char *
0x1800bb782  lea     r8, aOnecoreNetMpss_4; "onecore\\net\\mpssvc\\lics\\fwnetappiso"...
0x1800bb789  mov     rcx, [rbp+18h]; this
0x1800bb78d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800bb792  mov     ebx, eax
0x1800bb794  cmp     [rbp+var_28], 0
0x1800bb799  jz      short loc_1800BB7A6
0x1800bb79b  lea     rdx, [rbp+var_28]; void **
0x1800bb79f  xor     ecx, ecx; void *
0x1800bb7a1  call    ?SvrImpl_FWClosePolicyStore@@YAKPEAXPEAPEAX@Z; SvrImpl_FWClosePolicyStore(void *,void * *)
0x1800bb7a6  mov     rcx, [rbp+var_20]
0x1800bb7aa  test    rcx, rcx
0x1800bb7ad  jz      short loc_1800BB7BD
0x1800bb7af  xor     edx, edx
0x1800bb7b1  call    cs:__imp_FwFreeRules
0x1800bb7b8  nop     dword ptr [rax+rax+00h]
0x1800bb7bd  mov     eax, ebx
0x1800bb7bf  jmp     loc_1800BB8AC
0x1800bb7c4  lea     rax, [rbp+var_20]
0x1800bb7c8  mov     [rsp+80h+var_50], rax; struct _tag_FW_RULE **
0x1800bb7cd  lea     rax, [rbp+var_10]
0x1800bb7d1  mov     [rsp+80h+var_58], rax; unsigned int *
0x1800bb7d6  mov     [rsp+80h+var_60], 7; unsigned int
0x1800bb7dd  mov     r9d, 7FFFFFFFh; unsigned int
0x1800bb7e3  mov     r8d, 30000h; unsigned int
0x1800bb7e9  mov     rdx, [rbp+var_28]; struct _tag_FW_RPC_STORE_HANDLE *
0x1800bb7ed  xor     ecx, ecx; void *
0x1800bb7ef  call    ?SvrImpl_FWEnumFirewallRules2_33@@YAKPEAX0KKGPEAKPEAPEAU_tag_FW_RULE@@@Z; SvrImpl_FWEnumFirewallRules2_33(void *,void *,ulong,ulong,ushort,ulong *,_tag_FW_RULE * *)
0x1800bb7f4  test    eax, eax
0x1800bb7f6  jz      short loc_1800BB7FF
0x1800bb7f8  mov     edx, 28Ch
0x1800bb7fd  jmp     short loc_1800BB77F
0x1800bb7ff  mov     rbx, [rbp+var_20]
0x1800bb803  test    rbx, rbx
0x1800bb806  jz      short loc_1800BB881
0x1800bb808  nop     dword ptr [rax+rax+00000000h]
0x1800bb810  mov     rcx, [rbx+178h]; StringSid
0x1800bb817  test    rcx, rcx
0x1800bb81a  jz      short loc_1800BB879
0x1800bb81c  mov     [rbp+Sid], rsi
0x1800bb820  lea     rdx, [rbp+Sid]; Sid
0x1800bb824  call    cs:__imp_ConvertStringSidToSidW
0x1800bb82b  nop     dword ptr [rax+rax+00h]
0x1800bb830  test    eax, eax
0x1800bb832  jz      short loc_1800BB864
0x1800bb834  mov     rdx, rdi; pSid2
0x1800bb837  mov     rcx, [rbp+Sid]; pSid1
0x1800bb83b  call    cs:__imp_EqualSid
0x1800bb842  nop     dword ptr [rax+rax+00h]
0x1800bb847  test    eax, eax
0x1800bb849  jz      short loc_1800BB864
0x1800bb84b  mov     [rbp+var_C], esi
0x1800bb84e  lea     r9, [rbp+var_C]; enum _tag_FW_RULE_STATUS *
0x1800bb852  mov     r8, rbx; struct _tag_FW_RULE *
0x1800bb855  mov     rdx, [rbp+var_28]; void *
0x1800bb859  xor     ecx, ecx; void *
0x1800bb85b  call    ?SvrImpl_FWSetFirewallRule2_33@@YAKPEAX0PEAU_tag_FW_RULE@@PEAW4_tag_FW_RULE_STATUS@@@Z; SvrImpl_FWSetFirewallRule2_33(void *,void *,_tag_FW_RULE *,_tag_FW_RULE_STATUS *)
0x1800bb860  test    eax, eax
0x1800bb862  jnz     short loc_1800BB8CC
0x1800bb864  mov     rcx, [rbp+Sid]; hMem
0x1800bb868  test    rcx, rcx
0x1800bb86b  jz      short loc_1800BB879
0x1800bb86d  call    cs:__imp_LocalFree
0x1800bb874  nop     dword ptr [rax+rax+00h]
0x1800bb879  mov     rbx, [rbx]
0x1800bb87c  test    rbx, rbx
0x1800bb87f  jnz     short loc_1800BB810
0x1800bb881  cmp     [rbp+var_28], 0
0x1800bb886  jz      short loc_1800BB893
0x1800bb888  lea     rdx, [rbp+var_28]; void **
0x1800bb88c  xor     ecx, ecx; void *
0x1800bb88e  call    ?SvrImpl_FWClosePolicyStore@@YAKPEAXPEAPEAX@Z; SvrImpl_FWClosePolicyStore(void *,void * *)
0x1800bb893  mov     rcx, [rbp+var_20]
0x1800bb897  test    rcx, rcx
0x1800bb89a  jz      short loc_1800BB8AA
0x1800bb89c  xor     edx, edx
0x1800bb89e  call    cs:__imp_FwFreeRules
0x1800bb8a5  nop     dword ptr [rax+rax+00h]
0x1800bb8aa  xor     eax, eax
0x1800bb8ac  mov     rcx, [rbp+var_8]
0x1800bb8b0  xor     rcx, rsp; StackCookie
0x1800bb8b3  call    __security_check_cookie
0x1800bb8b8  mov     rbx, [rsp+80h+arg_0]
0x1800bb8c0  add     rsp, 80h
0x1800bb8c7  pop     rdi
0x1800bb8c8  pop     rsi
0x1800bb8c9  pop     rbp
0x1800bb8ca  retn
0x1800bb8cc  mov     rcx, [rbp+18h]; this
0x1800bb8d0  mov     r9d, eax; char *
0x1800bb8d3  lea     r8, aOnecoreNetMpss_4; "onecore\\net\\mpssvc\\lics\\fwnetappiso"...
0x1800bb8da  mov     edx, 297h; void *
0x1800bb8df  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800bb8e4  mov     ebx, eax
0x1800bb8e6  mov     rcx, [rbp+Sid]; hMem
0x1800bb8ea  test    rcx, rcx
0x1800bb8ed  jz      loc_1800BB794
0x1800bb8f3  call    cs:__imp_LocalFree
0x1800bb8fa  nop     dword ptr [rax+rax+00h]
0x1800bb8ff  jmp     loc_1800BB794
```
