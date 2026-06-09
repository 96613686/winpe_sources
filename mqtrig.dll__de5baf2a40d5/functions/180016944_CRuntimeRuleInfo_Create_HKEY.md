# CRuntimeRuleInfo::Create(HKEY__ *)

- ea: `0x180016944`
- end: `0x180016b4a`
- name: `?Create@CRuntimeRuleInfo@@QEAA_NPEAUHKEY__@@@Z`
- size: `518`
- prototype: `bool __fastcall(CRuntimeRuleInfo *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000a300`

## callees

- `0x180004d88`
- `0x180004dfc`
- `0x18000a2b8`
- `0x180012c84`
- `0x180014fc8`
- `0x180016944`
- `0x180016bf0`
- `0x180016d90`
- `0x18001e380`

## pseudocode

```c
bool __fastcall CRuntimeRuleInfo::Create(CRuntimeRuleInfo *this, HKEY a2)
{
  const wchar_t *v4; // r8
  __int64 v5; // rcx
  int v6; // eax
  bool result; // al
  HKEY RuleKeyHandle; // [rsp+30h] [rbp-468h] BYREF
  int v9; // [rsp+38h] [rbp-460h] BYREF
  wchar_t *v10; // [rsp+40h] [rbp-458h]
  __int64 v11; // [rsp+48h] [rbp-450h]
  int v12; // [rsp+50h] [rbp-448h]
  HKEY v13; // [rsp+58h] [rbp-440h]
  HKEY v14; // [rsp+60h] [rbp-438h] BYREF
  HKEY Key; // [rsp+68h] [rbp-430h] BYREF
  HKEY v16; // [rsp+70h] [rbp-428h]
  CRuntimeRuleInfo *v17; // [rsp+78h] [rbp-420h]
  wchar_t v18[512]; // [rsp+80h] [rbp-418h] BYREF

  v17 = this;
  v16 = a2;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
    return 0;
  }
  if ( *(_QWORD *)this )
    v4 = **(const wchar_t ***)this;
  else
    v4 = 0;
  RuleKeyHandle = CRuntimeRuleInfo::GetRuleKeyHandle(this, a2, v4);
  if ( RuleKeyHandle )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
LABEL_19:
    CRegHandle::~CRegHandle((CRegHandle *)&RuleKeyHandle);
    return 0;
  }
  if ( *(_QWORD *)this )
    v5 = **(_QWORD **)this;
  else
    v5 = 0;
  v6 = StringCchPrintfW(v18, 0x200u, L"%s%s", (char *)this + 48, v5);
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), v6);
    goto LABEL_19;
  }
  try
  {
    v9 = 1;
    v10 = v18;
    v11 = 0;
    v12 = 0;
    v13 = a2;
    Key = CmCreateKey((const struct RegEntry *)&v9, 0x30003u);
    v14 = Key;
    CRuntimeRuleInfo::FlushValuesToRegistry(this, &v14);
    CRegHandle::~CRegHandle((CRegHandle *)&Key);
    CRegHandle::~CRegHandle((CRegHandle *)&RuleKeyHandle);
    result = 1;
  }
  catch ( std::bad_alloc )
  {
    v9 = 0;
    v10 = v18;
    v11 = 0;
    v12 = 0;
    v13 = v16;
    CmDeleteKey((const struct RegEntry *)&v9);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
    goto LABEL_19;
  }
  v9 = 1;
}

```

## disassembly

```asm
0x180016944  mov     [rsp+arg_10], rbx
0x180016949  push    rdi
0x18001694a  sub     rsp, 490h
0x180016951  mov     rax, cs:__security_cookie
0x180016958  xor     rax, rsp
0x18001695b  mov     [rsp+498h+var_18], rax
0x180016963  mov     rdi, rdx
0x180016966  mov     rbx, rcx
0x180016969  mov     [rsp+498h+var_420], rcx
0x18001696e  mov     [rsp+498h+var_428], rdx
0x180016973  test    rdx, rdx
0x180016976  jnz     short loc_1800169C3
0x180016978  lea     rax, WPP_GLOBAL_Control
0x18001697f  mov     rcx, cs:WPP_GLOBAL_Control
0x180016986  cmp     rcx, rax
0x180016989  jz      loc_180016B27
0x18001698f  test    byte ptr [rcx+1Ch], 1
0x180016993  jz      loc_180016B27
0x180016999  mov     rax, [rbx]
0x18001699c  test    rax, rax
0x18001699f  jz      short loc_1800169A6
0x1800169a1  mov     r9, [rax]
0x1800169a4  jmp     short loc_1800169A9
0x1800169a6  xor     r9d, r9d
0x1800169a9  mov     edx, 10h
0x1800169ae  lea     r8, WPP_d76c01569fa63fba5f13379e908326ce_Traceguids
0x1800169b5  mov     rcx, [rcx+10h]; LoggerHandle
0x1800169b9  call    WPP_SF_S
0x1800169be  jmp     loc_180016B27
0x1800169c3  mov     rax, [rcx]
0x1800169c6  test    rax, rax
0x1800169c9  jz      short loc_1800169D0
0x1800169cb  mov     r8, [rax]
0x1800169ce  jmp     short loc_1800169D3
0x1800169d0  xor     r8d, r8d; wchar_t *
0x1800169d3  call    ?GetRuleKeyHandle@CRuntimeRuleInfo@@AEAAPEAUHKEY__@@PEAU2@PEB_W@Z; CRuntimeRuleInfo::GetRuleKeyHandle(HKEY__ *,wchar_t const *)
0x1800169d8  mov     [rsp+498h+var_468], rax
0x1800169dd  test    rax, rax
0x1800169e0  jz      short loc_180016A2D
0x1800169e2  lea     rax, WPP_GLOBAL_Control
0x1800169e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800169f0  cmp     rcx, rax
0x1800169f3  jz      loc_180016B1D
0x1800169f9  test    byte ptr [rcx+1Ch], 1
0x1800169fd  jz      loc_180016B1D
0x180016a03  mov     rax, [rbx]
0x180016a06  test    rax, rax
0x180016a09  jz      short loc_180016A10
0x180016a0b  mov     r9, [rax]
0x180016a0e  jmp     short loc_180016A13
0x180016a10  xor     r9d, r9d
0x180016a13  mov     edx, 11h
0x180016a18  lea     r8, WPP_d76c01569fa63fba5f13379e908326ce_Traceguids
0x180016a1f  mov     rcx, [rcx+10h]; LoggerHandle
0x180016a23  call    WPP_SF_S
0x180016a28  jmp     loc_180016B1D
0x180016a2d  mov     rax, [rbx]
0x180016a30  test    rax, rax
0x180016a33  jz      short loc_180016A3A
0x180016a35  mov     rcx, [rax]
0x180016a38  jmp     short loc_180016A3C
0x180016a3a  xor     ecx, ecx
0x180016a3c  lea     r9, [rbx+30h]
0x180016a40  mov     qword ptr [rsp+498h+var_478], rcx
0x180016a45  lea     r8, aSS_0; "%s%s"
0x180016a4c  mov     edx, 200h; unsigned __int64
0x180016a51  lea     rcx, [rsp+498h+var_418]; wchar_t *
0x180016a59  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180016a5e  mov     r8d, eax
0x180016a61  test    eax, eax
0x180016a63  jns     short loc_180016AB2
0x180016a65  lea     rax, WPP_GLOBAL_Control
0x180016a6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180016a73  cmp     rcx, rax
0x180016a76  jz      loc_180016B1D
0x180016a7c  test    byte ptr [rcx+1Ch], 1
0x180016a80  jz      loc_180016B1D
0x180016a86  mov     rax, [rbx]
0x180016a89  test    rax, rax
0x180016a8c  jz      short loc_180016A93
0x180016a8e  mov     r9, [rax]
0x180016a91  jmp     short loc_180016A96
0x180016a93  xor     r9d, r9d
0x180016a96  mov     edx, 12h
0x180016a9b  mov     dword ptr [rsp+498h+var_478], r8d; char
0x180016aa0  lea     r8, WPP_d76c01569fa63fba5f13379e908326ce_Traceguids
0x180016aa7  mov     rcx, [rcx+10h]; LoggerHandle
0x180016aab  call    WPP_SF_SD
0x180016ab0  jmp     short loc_180016B1D
0x180016ab2  mov     [rsp+498h+var_460], 1
0x180016aba  lea     rax, [rsp+498h+var_418]
0x180016ac2  mov     [rsp+498h+var_458], rax
0x180016ac7  mov     [rsp+498h+var_450], 0
0x180016ad0  mov     [rsp+498h+var_448], 0
0x180016ad8  mov     [rsp+498h+var_440], rdi
0x180016add  mov     edx, 30003h; samDesired
0x180016ae2  lea     rcx, [rsp+498h+var_460]; struct RegEntry *
0x180016ae7  call    ?CmCreateKey@@YAPEAUHKEY__@@AEBVRegEntry@@K@Z; CmCreateKey(RegEntry const &,ulong)
0x180016aec  mov     [rsp+498h+var_430], rax
0x180016af1  mov     [rsp+498h+var_438], rax
0x180016af6  lea     rdx, [rsp+498h+var_438]; HKEY *
0x180016afb  mov     rcx, rbx; this
0x180016afe  call    ?FlushValuesToRegistry@CRuntimeRuleInfo@@QEAAXAEBQEAUHKEY__@@@Z; CRuntimeRuleInfo::FlushValuesToRegistry(HKEY__ * const &)
0x180016b03  nop
0x180016b04  lea     rcx, [rsp+498h+var_430]; this
0x180016b09  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x180016b0e  nop
0x180016b0f  lea     rcx, [rsp+498h+var_468]; this
0x180016b14  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x180016b19  mov     al, 1
0x180016b1b  jmp     short loc_180016B29
0x180016b1d  lea     rcx, [rsp+498h+var_468]; this
0x180016b22  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x180016b27  xor     al, al
0x180016b29  mov     rcx, [rsp+498h+var_18]
0x180016b31  xor     rcx, rsp; StackCookie
0x180016b34  call    __security_check_cookie
0x180016b39  mov     rbx, [rsp+498h+arg_10]
0x180016b41  add     rsp, 490h
0x180016b48  pop     rdi
0x180016b49  retn
```
