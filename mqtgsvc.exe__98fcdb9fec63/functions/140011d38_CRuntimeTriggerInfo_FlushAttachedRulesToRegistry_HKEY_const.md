# CRuntimeTriggerInfo::FlushAttachedRulesToRegistry(HKEY__ * const &)

- ea: `0x140011d38`
- end: `0x140011ec7`
- name: `?FlushAttachedRulesToRegistry@CRuntimeTriggerInfo@@AEAAXAEBQEAUHKEY__@@@Z`
- size: `399`
- prototype: `void __fastcall(CRuntimeTriggerInfo *__hidden this, HKEY *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1400115c8`

## callees

- `0x140001cc6`
- `0x140003868`
- `0x140005b38`
- `0x14000ce94`
- `0x14000ee94`
- `0x14000ef34`
- `0x14000f068`
- `0x14000f6e0`
- `0x140011d38`
- `0x140011f54`

## import_xrefs

- `msvcrt!??0exception@@QEAA@XZ` at `0x140011db9`
- `msvcrt!??0exception@@QEAA@XZ` at `0x140011db9`

## pseudocode

```c
void __fastcall CRuntimeTriggerInfo::FlushAttachedRulesToRegistry(CRuntimeTriggerInfo *this, HKEY *a2)
{
  const wchar_t **v3; // rax
  const wchar_t *v4; // r8
  HKEY TriggerKeyHandle; // rax
  HKEY Key; // r15
  unsigned int v7; // esi
  _QWORD *v8; // rbx
  const wchar_t **v9; // r14
  __int64 v10; // rcx
  const wchar_t *v11; // rdx
  int pExceptionObject; // [rsp+20h] [rbp-30h] BYREF
  const wchar_t *v13; // [rsp+28h] [rbp-28h]
  __int64 v14; // [rsp+30h] [rbp-20h]
  int v15; // [rsp+38h] [rbp-18h]
  HKEY v16; // [rsp+40h] [rbp-10h]
  __int64 *v17; // [rsp+80h] [rbp+30h] BYREF
  HKEY v18; // [rsp+88h] [rbp+38h] BYREF
  HKEY v19; // [rsp+90h] [rbp+40h] BYREF

  v3 = (const wchar_t **)*((_QWORD *)this + 260);
  if ( v3 )
    v4 = *v3;
  else
    v4 = 0;
  TriggerKeyHandle = CRuntimeTriggerInfo::GetTriggerKeyHandle(this, *a2, v4);
  v19 = TriggerKeyHandle;
  if ( !TriggerKeyHandle )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
    exception::exception((exception *)&pExceptionObject);
    throw (exception *)&pExceptionObject;
  }
  pExceptionObject = 1;
  v13 = L"AttachedRules";
  v14 = 0;
  v15 = 0;
  v16 = TriggerKeyHandle;
  CmDeleteKey((const struct RegEntry *)&pExceptionObject);
  Key = CmCreateKey((const struct RegEntry *)&pExceptionObject, 0x30003u);
  v18 = Key;
  v7 = 0;
  v8 = (_QWORD *)*((_QWORD *)this + 265);
  while ( 1 )
  {
    v8 = (_QWORD *)*v8;
    if ( v8 == *((_QWORD **)this + 265) )
      break;
    v9 = (const wchar_t **)v8[2];
    v17 = 0;
    FormatBSTR((struct _bstr_t *)&v17, L"%s%d", L"Rule", v7);
    if ( v17 )
      v10 = *v17;
    else
      v10 = 0;
    pExceptionObject = 1;
    v13 = 0;
    v14 = v10;
    v15 = 0;
    v16 = Key;
    v11 = *v9;
    if ( *v9 )
      v11 = *(const wchar_t **)v11;
    CmSetValue((const struct RegEntry *)&pExceptionObject, v11);
    ++v7;
    _bstr_t::_Free((_bstr_t *)&v17);
  }
  CRegHandle::~CRegHandle((CRegHandle *)&v18);
  CRegHandle::~CRegHandle((CRegHandle *)&v19);
}

```

## disassembly

```asm
0x140011d38  mov     [rsp-28h+arg_18], rbx
0x140011d3d  push    rbp
0x140011d3e  push    rsi
0x140011d3f  push    rdi
0x140011d40  push    r14
0x140011d42  push    r15
0x140011d44  mov     rbp, rsp
0x140011d47  sub     rsp, 50h
0x140011d4b  mov     rdi, rcx
0x140011d4e  mov     rax, [rcx+820h]
0x140011d55  test    rax, rax
0x140011d58  jz      short loc_140011D5F
0x140011d5a  mov     r8, [rax]
0x140011d5d  jmp     short loc_140011D62
0x140011d5f  xor     r8d, r8d; wchar_t *
0x140011d62  mov     rdx, [rdx]; HKEY
0x140011d65  call    ?GetTriggerKeyHandle@CRuntimeTriggerInfo@@AEAAPEAUHKEY__@@PEAU2@PEB_W@Z; CRuntimeTriggerInfo::GetTriggerKeyHandle(HKEY__ *,wchar_t const *)
0x140011d6a  mov     [rbp+arg_10], rax
0x140011d6e  test    rax, rax
0x140011d71  jnz     short loc_140011DD0
0x140011d73  lea     rax, WPP_GLOBAL_Control
0x140011d7a  mov     rcx, cs:WPP_GLOBAL_Control
0x140011d81  cmp     rcx, rax
0x140011d84  jz      short loc_140011DB5
0x140011d86  test    byte ptr [rcx+1Ch], 1
0x140011d8a  jz      short loc_140011DB5
0x140011d8c  mov     rax, [rdi+820h]
0x140011d93  test    rax, rax
0x140011d96  jz      short loc_140011D9D
0x140011d98  mov     r9, [rax]
0x140011d9b  jmp     short loc_140011DA0
0x140011d9d  xor     r9d, r9d
0x140011da0  mov     edx, 21h ; '!'
0x140011da5  lea     r8, WPP_5d468cdb8ea734f7fb134a242ccb11b7_Traceguids
0x140011dac  mov     rcx, [rcx+10h]; LoggerHandle
0x140011db0  call    WPP_SF_S
0x140011db5  lea     rcx, [rbp+pExceptionObject]
0x140011db9  call    cs:__imp_??0exception@@QEAA@XZ; exception::exception(void)
0x140011dbf  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x140011dc6  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x140011dca  call    _CxxThrowException_0
0x140011dd0  mov     [rbp+pExceptionObject], 1
0x140011dd7  lea     rcx, aAttachedrules; "AttachedRules"
0x140011dde  mov     [rbp+var_28], rcx
0x140011de2  mov     [rbp+var_20], 0
0x140011dea  mov     [rbp+var_18], 0
0x140011df1  mov     [rbp+var_10], rax
0x140011df5  lea     rcx, [rbp+pExceptionObject]; struct RegEntry *
0x140011df9  call    ?CmDeleteKey@@YAXAEBVRegEntry@@@Z; CmDeleteKey(RegEntry const &)
0x140011dfe  mov     edx, 30003h; samDesired
0x140011e03  lea     rcx, [rbp+pExceptionObject]; struct RegEntry *
0x140011e07  call    ?CmCreateKey@@YAPEAUHKEY__@@AEBVRegEntry@@K@Z; CmCreateKey(RegEntry const &,ulong)
0x140011e0c  mov     r15, rax
0x140011e0f  mov     [rbp+arg_8], rax
0x140011e13  xor     esi, esi
0x140011e15  mov     rbx, [rdi+848h]
0x140011e1c  mov     rbx, [rbx]
0x140011e1f  cmp     rbx, [rdi+848h]
0x140011e26  jz      short loc_140011EA0
0x140011e28  mov     r14, [rbx+10h]
0x140011e2c  mov     [rbp+arg_0], 0
0x140011e34  mov     r9d, esi
0x140011e37  lea     r8, aRule; "Rule"
0x140011e3e  lea     rdx, aSD; "%s%d"
0x140011e45  lea     rcx, [rbp+arg_0]; struct _bstr_t *
0x140011e49  call    ?FormatBSTR@@YAXPEAV_bstr_t@@PEB_WZZ; FormatBSTR(_bstr_t *,wchar_t const *,...)
0x140011e4e  mov     rax, [rbp+arg_0]
0x140011e52  test    rax, rax
0x140011e55  jz      short loc_140011E5C
0x140011e57  mov     rcx, [rax]
0x140011e5a  jmp     short loc_140011E5E
0x140011e5c  xor     ecx, ecx
0x140011e5e  mov     [rbp+pExceptionObject], 1
0x140011e65  mov     [rbp+var_28], 0
0x140011e6d  mov     [rbp+var_20], rcx
0x140011e71  mov     [rbp+var_18], 0
0x140011e78  mov     [rbp+var_10], r15
0x140011e7c  mov     rdx, [r14]
0x140011e7f  test    rdx, rdx
0x140011e82  jz      short loc_140011E87
0x140011e84  mov     rdx, [rdx]; wchar_t *
0x140011e87  lea     rcx, [rbp+pExceptionObject]; struct RegEntry *
0x140011e8b  call    ?CmSetValue@@YAXAEBVRegEntry@@PEB_W@Z; CmSetValue(RegEntry const &,wchar_t const *)
0x140011e90  inc     esi
0x140011e92  lea     rcx, [rbp+arg_0]; this
0x140011e96  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x140011e9b  jmp     loc_140011E1C
0x140011ea0  lea     rcx, [rbp+arg_8]; this
0x140011ea4  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x140011ea9  nop
0x140011eaa  lea     rcx, [rbp+arg_10]; this
0x140011eae  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x140011eb3  mov     rbx, [rsp+50h+arg_18]
0x140011ebb  add     rsp, 50h
0x140011ebf  pop     r15
0x140011ec1  pop     r14
0x140011ec3  pop     rdi
0x140011ec4  pop     rsi
0x140011ec5  pop     rbp
0x140011ec6  retn
```
