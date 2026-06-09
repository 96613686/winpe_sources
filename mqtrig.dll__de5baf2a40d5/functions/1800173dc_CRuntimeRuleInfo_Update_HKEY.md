# CRuntimeRuleInfo::Update(HKEY__ *)

- ea: `0x1800173dc`
- end: `0x1800174cb`
- name: `?Update@CRuntimeRuleInfo@@QEAA_NPEAUHKEY__@@@Z`
- size: `239`
- prototype: `char __fastcall(const wchar_t ***this, HKEY)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x18000bda0`

## callees

- `0x180004d88`
- `0x18000a2b8`
- `0x180016bf0`
- `0x180016d90`
- `0x1800173dc`

## pseudocode

```c
char __fastcall CRuntimeRuleInfo::Update(const wchar_t ***this, HKEY a2)
{
  const wchar_t *v3; // r8
  HKEY RuleKeyHandle; // rax
  HKEY v6; // [rsp+38h] [rbp+10h] BYREF
  HKEY v7; // [rsp+40h] [rbp+18h] BYREF

  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
    return 0;
  }
  if ( *this )
    v3 = **this;
  else
    v3 = 0;
  RuleKeyHandle = CRuntimeRuleInfo::GetRuleKeyHandle((CRuntimeRuleInfo *)this, a2, v3);
  v6 = RuleKeyHandle;
  if ( !RuleKeyHandle )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
LABEL_13:
    CRegHandle::~CRegHandle((CRegHandle *)&v6);
    return 0;
  }
  try
  {
    v7 = RuleKeyHandle;
    CRuntimeRuleInfo::FlushValuesToRegistry((CRuntimeRuleInfo *)this, &v7);
  }
  catch ( std::bad_alloc )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
    goto LABEL_13;
  }
  v7 = RuleKeyHandle;
  CRuntimeRuleInfo::FlushValuesToRegistry((CRuntimeRuleInfo *)this, &v7);
}

```

## disassembly

```asm
0x1800173dc  mov     [rsp+arg_0], rcx
0x1800173e1  push    rbx
0x1800173e2  sub     rsp, 20h
0x1800173e6  mov     rbx, rcx
0x1800173e9  test    rdx, rdx
0x1800173ec  jnz     short loc_180017439
0x1800173ee  lea     rax, WPP_GLOBAL_Control
0x1800173f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800173fc  cmp     rcx, rax
0x1800173ff  jz      loc_1800174C3
0x180017405  test    byte ptr [rcx+1Ch], 1
0x180017409  jz      loc_1800174C3
0x18001740f  mov     rax, [rbx]
0x180017412  test    rax, rax
0x180017415  jz      short loc_18001741C
0x180017417  mov     r9, [rax]
0x18001741a  jmp     short loc_18001741F
0x18001741c  xor     r9d, r9d
0x18001741f  mov     edx, 0Dh
0x180017424  lea     r8, WPP_d76c01569fa63fba5f13379e908326ce_Traceguids
0x18001742b  mov     rcx, [rcx+10h]; LoggerHandle
0x18001742f  call    WPP_SF_S
0x180017434  jmp     loc_1800174C3
0x180017439  mov     rax, [rcx]
0x18001743c  test    rax, rax
0x18001743f  jz      short loc_180017446
0x180017441  mov     r8, [rax]
0x180017444  jmp     short loc_180017449
0x180017446  xor     r8d, r8d; wchar_t *
0x180017449  call    ?GetRuleKeyHandle@CRuntimeRuleInfo@@AEAAPEAUHKEY__@@PEAU2@PEB_W@Z; CRuntimeRuleInfo::GetRuleKeyHandle(HKEY__ *,wchar_t const *)
0x18001744e  mov     [rsp+28h+arg_8], rax
0x180017453  test    rax, rax
0x180017456  jnz     short loc_180017498
0x180017458  lea     rax, WPP_GLOBAL_Control
0x18001745f  mov     rcx, cs:WPP_GLOBAL_Control
0x180017466  cmp     rcx, rax
0x180017469  jz      short loc_1800174B9
0x18001746b  test    byte ptr [rcx+1Ch], 1
0x18001746f  jz      short loc_1800174B9
0x180017471  mov     rax, [rbx]
0x180017474  test    rax, rax
0x180017477  jz      short loc_18001747E
0x180017479  mov     r9, [rax]
0x18001747c  jmp     short loc_180017481
0x18001747e  xor     r9d, r9d
0x180017481  mov     edx, 0Eh
0x180017486  lea     r8, WPP_d76c01569fa63fba5f13379e908326ce_Traceguids
0x18001748d  mov     rcx, [rcx+10h]; LoggerHandle
0x180017491  call    WPP_SF_S
0x180017496  jmp     short loc_1800174B9
0x180017498  mov     [rsp+28h+arg_10], rax
0x18001749d  lea     rdx, [rsp+28h+arg_10]; HKEY *
0x1800174a2  mov     rcx, rbx; this
0x1800174a5  call    ?FlushValuesToRegistry@CRuntimeRuleInfo@@QEAAXAEBQEAUHKEY__@@@Z; CRuntimeRuleInfo::FlushValuesToRegistry(HKEY__ * const &)
0x1800174aa  nop
0x1800174ab  lea     rcx, [rsp+28h+arg_8]; this
0x1800174b0  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x1800174b5  mov     al, 1
0x1800174b7  jmp     short loc_1800174C5
0x1800174b9  lea     rcx, [rsp+28h+arg_8]; this
0x1800174be  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x1800174c3  xor     al, al
0x1800174c5  add     rsp, 20h
0x1800174c9  pop     rbx
0x1800174ca  retn
```
