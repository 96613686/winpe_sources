# CRuntimeTriggerInfo::FlushAttachedRulesToRegistry(HKEY__ * const &)

- ea: `0x180019dc0`
- end: `0x180019f4f`
- name: `?FlushAttachedRulesToRegistry@CRuntimeTriggerInfo@@AEAAXAEBQEAUHKEY__@@@Z`
- size: `399`
- prototype: `void __fastcall(CRuntimeTriggerInfo *__hidden this, HKEY *)`
- caller_count: `4`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1800190c8`
- `0x180019230`
- `0x180019ce0`
- `0x180019d88`

## callees

- `0x180001ce6`
- `0x180004d88`
- `0x180009ab0`
- `0x18000a2b8`
- `0x180014fc8`
- `0x180015068`
- `0x18001519c`
- `0x180016024`
- `0x180019dc0`
- `0x18001a15c`

## import_xrefs

- `msvcrt!??0exception@@QEAA@XZ` at `0x180019e41`
- `msvcrt!??0exception@@QEAA@XZ` at `0x180019e41`

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
  CRegHandle::~CRegHandle(&v18);
  CRegHandle::~CRegHandle(&v19);
}

```

## disassembly

```asm
0x180019dc0  mov     [rsp-28h+arg_18], rbx
0x180019dc5  push    rbp
0x180019dc6  push    rsi
0x180019dc7  push    rdi
0x180019dc8  push    r14
0x180019dca  push    r15
0x180019dcc  mov     rbp, rsp
0x180019dcf  sub     rsp, 50h
0x180019dd3  mov     rdi, rcx
0x180019dd6  mov     rax, [rcx+820h]
0x180019ddd  test    rax, rax
0x180019de0  jz      short loc_180019DE7
0x180019de2  mov     r8, [rax]
0x180019de5  jmp     short loc_180019DEA
0x180019de7  xor     r8d, r8d; wchar_t *
0x180019dea  mov     rdx, [rdx]; HKEY
0x180019ded  call    ?GetTriggerKeyHandle@CRuntimeTriggerInfo@@AEAAPEAUHKEY__@@PEAU2@PEB_W@Z; CRuntimeTriggerInfo::GetTriggerKeyHandle(HKEY__ *,wchar_t const *)
0x180019df2  mov     [rbp+arg_10], rax
0x180019df6  test    rax, rax
0x180019df9  jnz     short loc_180019E58
0x180019dfb  lea     rax, WPP_GLOBAL_Control
0x180019e02  mov     rcx, cs:WPP_GLOBAL_Control
0x180019e09  cmp     rcx, rax
0x180019e0c  jz      short loc_180019E3D
0x180019e0e  test    byte ptr [rcx+1Ch], 1
0x180019e12  jz      short loc_180019E3D
0x180019e14  mov     rax, [rdi+820h]
0x180019e1b  test    rax, rax
0x180019e1e  jz      short loc_180019E25
0x180019e20  mov     r9, [rax]
0x180019e23  jmp     short loc_180019E28
0x180019e25  xor     r9d, r9d
0x180019e28  mov     edx, 21h ; '!'
0x180019e2d  lea     r8, WPP_5d468cdb8ea734f7fb134a242ccb11b7_Traceguids
0x180019e34  mov     rcx, [rcx+10h]; LoggerHandle
0x180019e38  call    WPP_SF_S
0x180019e3d  lea     rcx, [rbp+pExceptionObject]
0x180019e41  call    cs:__imp_??0exception@@QEAA@XZ; exception::exception(void)
0x180019e47  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x180019e4e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180019e52  call    _CxxThrowException_0
0x180019e58  mov     [rbp+pExceptionObject], 1
0x180019e5f  lea     rcx, aAttachedrules; "AttachedRules"
0x180019e66  mov     [rbp+var_28], rcx
0x180019e6a  mov     [rbp+var_20], 0
0x180019e72  mov     [rbp+var_18], 0
0x180019e79  mov     [rbp+var_10], rax
0x180019e7d  lea     rcx, [rbp+pExceptionObject]; struct RegEntry *
0x180019e81  call    ?CmDeleteKey@@YAXAEBVRegEntry@@@Z; CmDeleteKey(RegEntry const &)
0x180019e86  mov     edx, 30003h; samDesired
0x180019e8b  lea     rcx, [rbp+pExceptionObject]; struct RegEntry *
0x180019e8f  call    ?CmCreateKey@@YAPEAUHKEY__@@AEBVRegEntry@@K@Z; CmCreateKey(RegEntry const &,ulong)
0x180019e94  mov     r15, rax
0x180019e97  mov     [rbp+arg_8], rax
0x180019e9b  xor     esi, esi
0x180019e9d  mov     rbx, [rdi+848h]
0x180019ea4  mov     rbx, [rbx]
0x180019ea7  cmp     rbx, [rdi+848h]
0x180019eae  jz      short loc_180019F28
0x180019eb0  mov     r14, [rbx+10h]
0x180019eb4  mov     [rbp+arg_0], 0
0x180019ebc  mov     r9d, esi
0x180019ebf  lea     r8, aRule; "Rule"
0x180019ec6  lea     rdx, aSD; "%s%d"
0x180019ecd  lea     rcx, [rbp+arg_0]; struct _bstr_t *
0x180019ed1  call    ?FormatBSTR@@YAXPEAV_bstr_t@@PEB_WZZ; FormatBSTR(_bstr_t *,wchar_t const *,...)
0x180019ed6  mov     rax, [rbp+arg_0]
0x180019eda  test    rax, rax
0x180019edd  jz      short loc_180019EE4
0x180019edf  mov     rcx, [rax]
0x180019ee2  jmp     short loc_180019EE6
0x180019ee4  xor     ecx, ecx
0x180019ee6  mov     [rbp+pExceptionObject], 1
0x180019eed  mov     [rbp+var_28], 0
0x180019ef5  mov     [rbp+var_20], rcx
0x180019ef9  mov     [rbp+var_18], 0
0x180019f00  mov     [rbp+var_10], r15
0x180019f04  mov     rdx, [r14]
0x180019f07  test    rdx, rdx
0x180019f0a  jz      short loc_180019F0F
0x180019f0c  mov     rdx, [rdx]; lpData
0x180019f0f  lea     rcx, [rbp+pExceptionObject]; struct RegEntry *
0x180019f13  call    ?CmSetValue@@YAXAEBVRegEntry@@PEB_W@Z; CmSetValue(RegEntry const &,wchar_t const *)
0x180019f18  inc     esi
0x180019f1a  lea     rcx, [rbp+arg_0]; this
0x180019f1e  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180019f23  jmp     loc_180019EA4
0x180019f28  lea     rcx, [rbp+arg_8]; this
0x180019f2c  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x180019f31  nop
0x180019f32  lea     rcx, [rbp+arg_10]; this
0x180019f36  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x180019f3b  mov     rbx, [rsp+50h+arg_18]
0x180019f43  add     rsp, 50h
0x180019f47  pop     r15
0x180019f49  pop     r14
0x180019f4b  pop     rdi
0x180019f4c  pop     rsi
0x180019f4d  pop     rbp
0x180019f4e  retn
```
