# CNodeMonitorNode::AutoSetNodeHashValue(ushort *,IConfigManager2 *)

- ea: `0x18005745c`
- end: `0x180057649`
- name: `?AutoSetNodeHashValue@CNodeMonitorNode@@IEAAJPEAGPEAUIConfigManager2@@@Z`
- size: `493`
- prototype: `int(CNodeMonitorNode *__hidden this, unsigned __int16 *, struct IConfigManager2 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800594a0`

## callees

- `0x18000d4b4`
- `0x18000d4d4`
- `0x180022e10`
- `0x180057030`
- `0x18005745c`
- `0x18005a298`
- `0x18005a35c`
- `0x18005dcfc`
- `0x180061474`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180057482`
- `OLEAUT32!__imp_VariantInit` at `0x180057482`
- `OLEAUT32!__imp_VariantClear` at `0x180057621`
- `OLEAUT32!__imp_VariantClear` at `0x180057621`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180057521`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180057555`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180057521`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180057555`
- `CRYPTSP!CryptAcquireContextW` at `0x180057586`
- `CRYPTSP!CryptAcquireContextW` at `0x180057586`

## string_xrefs

- `0x1800574e9`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodemonnode.cpp`
- `0x18005759a`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodemonnode.cpp`
- `0x1800575e3`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodemonnode.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CNodeMonitorNode::AutoSetNodeHashValue(
        CNodeMonitorNode *this,
        unsigned __int16 *a2,
        struct IConfigManager2 *a3)
{
  unsigned int v6; // edi
  wchar_t *v7; // rax
  const WCHAR *v8; // rsi
  int v9; // eax
  unsigned int LastError; // ebx
  __int64 v11; // rdx
  int v12; // ebx
  __int64 v13; // rdx
  const char *v14; // r9
  int CspNodeValueHash; // eax
  __int64 v16; // rdx
  int lpString2; // [rsp+20h] [rbp-40h]
  int lpString2a; // [rsp+20h] [rbp-40h]
  HCRYPTPROV phProv; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int64 v21; // [rsp+38h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  int cchCount2; // [rsp+A8h] [rbp+48h] BYREF

  VariantInit(&pvarg);
  v6 = 0;
  v7 = wcsstr(a2, L"?");
  v8 = v7;
  if ( v7 )
  {
    v21 = 0;
    cchCount2 = 0;
    v9 = StringCchLengthW(v7, 0x7FFFFFFFu, &v21);
    LastError = v9;
    if ( v9 < 0 )
    {
      v11 = 1181;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodemonnode.cpp",
        (const char *)(unsigned int)v9,
        lpString2);
      goto LABEL_19;
    }
    v9 = UIntPtrToInt(v21, &cchCount2);
    LastError = v9;
    if ( v9 < 0 )
    {
      v11 = 1183;
      goto LABEL_6;
    }
    v12 = cchCount2;
    if ( CompareStringW(0x7Fu, 1u, L"?list=structData", 16, v8, cchCount2) == 2 )
      v6 = 2;
    else
      v6 = CompareStringW(0x7Fu, 1u, L"?list=struct", 12, v8, v12) == 2;
  }
  phProv = 0;
  if ( CryptAcquireContextW(&phProv, 0, 0, 0x18u, 0xF0000040) )
  {
    lpString2a = phProv;
    CspNodeValueHash = CNodeChangeSetBuilder::GetCspNodeValueHash(a3, v13, a2, v6);
    LastError = CspNodeValueHash;
    if ( CspNodeValueHash >= 0 )
    {
      CspNodeValueHash = CNodeCacheManager::SetExpectedValue((CNodeMonitorNode *)((char *)this + 8), &pvarg);
      LastError = CspNodeValueHash;
      if ( CspNodeValueHash >= 0 )
      {
        __1__unique_storage_U__resource_policy__KP6AX_K__E_1_CryptReleaseContextNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd___K_K_0A___T_details_wil___details_wil__QEAA_XZ(&phProv);
        LastError = 0;
        goto LABEL_19;
      }
      v16 = 1215;
    }
    else
    {
      v16 = 1213;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodemonnode.cpp",
      (const char *)(unsigned int)CspNodeValueHash,
      lpString2a);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x4BB,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodemonnode.cpp",
                  v14);
  }
  __1__unique_storage_U__resource_policy__KP6AX_K__E_1_CryptReleaseContextNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd___K_K_0A___T_details_wil___details_wil__QEAA_XZ(&phProv);
LABEL_19:
  VariantClear(&pvarg);
  return LastError;
}

```

## disassembly

```asm
0x18005745c  mov     [rsp-28h+arg_0], rbx
0x180057461  mov     [rsp-28h+arg_8], rsi
0x180057466  push    rbp
0x180057467  push    rdi
0x180057468  push    r12
0x18005746a  push    r14
0x18005746c  push    r15
0x18005746e  mov     rbp, rsp
0x180057471  sub     rsp, 60h
0x180057475  mov     r12, r8
0x180057478  mov     r14, rdx
0x18005747b  mov     r15, rcx
0x18005747e  lea     rcx, [rbp+pvarg]; pvarg
0x180057482  call    cs:__imp_VariantInit
0x180057489  nop     dword ptr [rax+rax+00h]
0x18005748e  nop
0x18005748f  xor     edi, edi
0x180057491  lea     rdx, SubStr; "?"
0x180057498  mov     rcx, r14; Str
0x18005749b  call    ?wcsstr@@YAPEAGPEAGPEBG@Z; wcsstr(ushort *,ushort const *)
0x1800574a0  mov     rsi, rax
0x1800574a3  test    rax, rax
0x1800574a6  jz      loc_180057567
0x1800574ac  mov     [rbp+var_28], rdi
0x1800574b0  mov     [rbp+arg_18], edi
0x1800574b3  lea     r8, [rbp+var_28]; unsigned __int64 *
0x1800574b7  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800574bc  mov     rcx, rax; unsigned __int16 *
0x1800574bf  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800574c4  mov     ebx, eax
0x1800574c6  test    eax, eax
0x1800574c8  jns     short loc_1800574D1
0x1800574ca  mov     edx, 49Dh
0x1800574cf  jmp     short loc_1800574E9
0x1800574d1  lea     rdx, [rbp+arg_18]; int *
0x1800574d5  mov     rcx, [rbp+var_28]; unsigned __int64
0x1800574d9  call    ?UIntPtrToInt@@YAJ_KPEAH@Z; UIntPtrToInt(unsigned __int64,int *)
0x1800574de  mov     ebx, eax
0x1800574e0  test    eax, eax
0x1800574e2  jns     short loc_180057501
0x1800574e4  mov     edx, 49Fh; void *
0x1800574e9  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800574f0  mov     r9d, eax; char *
0x1800574f3  mov     rcx, [rbp+28h]; this
0x1800574f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800574fc  jmp     loc_18005761D
0x180057501  mov     ebx, [rbp+arg_18]
0x180057504  mov     [rsp+60h+cchCount2], ebx; cchCount2
0x180057508  mov     [rsp+60h+lpString2], rsi; lpString2
0x18005750d  mov     r9d, 10h; cchCount1
0x180057513  lea     r8, String1; "?list=structData"
0x18005751a  lea     edx, [r9-0Fh]; dwCmpFlags
0x18005751e  lea     ecx, [rdx+7Eh]; Locale
0x180057521  call    cs:__imp_CompareStringW
0x180057528  nop     dword ptr [rax+rax+00h]
0x18005752d  cmp     eax, 2
0x180057530  jnz     short loc_180057536
0x180057532  mov     edi, eax
0x180057534  jmp     short loc_180057567
0x180057536  mov     [rsp+60h+cchCount2], ebx; cchCount2
0x18005753a  mov     [rsp+60h+lpString2], rsi; lpString2
0x18005753f  mov     r9d, 0Ch; cchCount1
0x180057545  lea     r8, aListStruct; "?list=struct"
0x18005754c  lea     ebx, [r9-0Bh]
0x180057550  mov     edx, ebx; dwCmpFlags
0x180057552  lea     ecx, [rbx+7Eh]; Locale
0x180057555  call    cs:__imp_CompareStringW
0x18005755c  nop     dword ptr [rax+rax+00h]
0x180057561  cmp     eax, 2
0x180057564  cmovz   edi, ebx
0x180057567  mov     [rbp+phProv], 0
0x18005756f  mov     dword ptr [rsp+60h+lpString2], 0F0000040h; dwFlags
0x180057577  mov     r9d, 18h; dwProvType
0x18005757d  xor     r8d, r8d; szProvider
0x180057580  xor     edx, edx; szContainer
0x180057582  lea     rcx, [rbp+phProv]; phProv
0x180057586  call    cs:__imp_CryptAcquireContextW
0x18005758d  nop     dword ptr [rax+rax+00h]
0x180057592  test    eax, eax
0x180057594  jnz     short loc_1800575B8
0x180057596  mov     rcx, [rbp+28h]; this
0x18005759a  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800575a1  mov     edx, 4BBh; void *
0x1800575a6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800575ab  mov     ebx, eax
0x1800575ad  lea     rcx, [rbp+phProv]
0x1800575b1  call    ??1?$unique_storage@U?$resource_policy@_KP6AX_K@_E$1?CryptReleaseContextNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800575b6  jmp     short loc_18005761D
0x1800575b8  lea     rax, [rbp+pvarg]
0x1800575bc  mov     qword ptr [rsp+60h+cchCount2], rax
0x1800575c1  mov     rax, [rbp+phProv]
0x1800575c5  mov     [rsp+60h+lpString2], rax; int
0x1800575ca  mov     r9d, edi
0x1800575cd  mov     r8, r14
0x1800575d0  mov     rcx, r12
0x1800575d3  call    ?GetCspNodeValueHash@CNodeChangeSetBuilder@@SAJPEAUIConfigManager2@@PEAUIConfigNode@@PEBGW4NodeUriAttribute@@_KPEAUtagVARIANT@@@Z; CNodeChangeSetBuilder::GetCspNodeValueHash(IConfigManager2 *,IConfigNode *,ushort const *,NodeUriAttribute,unsigned __int64,tagVARIANT *)
0x1800575d8  mov     ebx, eax
0x1800575da  test    eax, eax
0x1800575dc  jns     short loc_1800575F8
0x1800575de  mov     edx, 4BDh; void *
0x1800575e3  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800575ea  mov     r9d, eax; char *
0x1800575ed  mov     rcx, [rbp+28h]; this
0x1800575f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800575f6  jmp     short loc_1800575AD
0x1800575f8  lea     rcx, [r15+8]; this
0x1800575fc  lea     rdx, [rbp+pvarg]; struct tagVARIANT *
0x180057600  call    ?SetExpectedValue@CNodeCacheManager@@QEAAJPEAUtagVARIANT@@@Z; CNodeCacheManager::SetExpectedValue(tagVARIANT *)
0x180057605  mov     ebx, eax
0x180057607  test    eax, eax
0x180057609  jns     short loc_180057612
0x18005760b  mov     edx, 4BFh
0x180057610  jmp     short loc_1800575E3
0x180057612  lea     rcx, [rbp+phProv]
0x180057616  call    ??1?$unique_storage@U?$resource_policy@_KP6AX_K@_E$1?CryptReleaseContextNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005761b  xor     ebx, ebx
0x18005761d  lea     rcx, [rbp+pvarg]; pvarg
0x180057621  call    cs:__imp_VariantClear
0x180057628  nop     dword ptr [rax+rax+00h]
0x18005762d  mov     eax, ebx
0x18005762f  lea     r11, [rsp+60h+var_s0]
0x180057634  mov     rbx, [r11+30h]
0x180057638  mov     rsi, [r11+38h]
0x18005763c  mov     rsp, r11
0x18005763f  pop     r15
0x180057641  pop     r14
0x180057643  pop     r12
0x180057645  pop     rdi
0x180057646  pop     rbp
0x180057647  retn
```
