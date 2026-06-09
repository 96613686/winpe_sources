# CRuntimeTriggerInfo::Delete(HKEY__ *)

- ea: `0x180019b4c`
- end: `0x180019cd8`
- name: `?Delete@CRuntimeTriggerInfo@@QEAA_NPEAUHKEY__@@@Z`
- size: `396`
- prototype: `bool __fastcall(CRuntimeTriggerInfo *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180010ea0`

## callees

- `0x180004d88`
- `0x18000a2b8`
- `0x18000c62c`
- `0x180015068`
- `0x1800150b8`
- `0x180019b4c`

## pseudocode

```c
bool __fastcall CRuntimeTriggerInfo::Delete(CRuntimeTriggerInfo *this, HKEY a2)
{
  _QWORD *v3; // rax
  HKEY v4; // rdx
  char **v5; // rax
  char *v6; // rcx
  bool result; // al
  int v8; // [rsp+20h] [rbp-58h] BYREF
  char *v9; // [rsp+28h] [rbp-50h]
  __int64 v10; // [rsp+30h] [rbp-48h]
  int v11; // [rsp+38h] [rbp-40h]
  HKEY v12; // [rsp+40h] [rbp-38h]
  int v13; // [rsp+48h] [rbp-30h] BYREF
  const wchar_t *v14; // [rsp+50h] [rbp-28h]
  __int64 v15; // [rsp+58h] [rbp-20h]
  int v16; // [rsp+60h] [rbp-18h]
  HKEY v17; // [rsp+68h] [rbp-10h]
  HKEY v18; // [rsp+90h] [rbp+18h] BYREF
  HKEY v19; // [rsp+98h] [rbp+20h] BYREF

  v3 = (_QWORD *)*((_QWORD *)this + 260);
  if ( !v3 || !*v3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_5d468cdb8ea734f7fb134a242ccb11b7_Traceguids);
    return 0;
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v8 = 1;
    v9 = (char *)this + 24;
    v10 = 0;
    v11 = 0;
    v12 = a2;
    v4 = CmOpenKey((const struct RegEntry *)&v8, 0xF003Fu);
    v19 = v4;
    v5 = (char **)*((_QWORD *)this + 260);
    if ( v5 )
      v6 = *v5;
    else
      v6 = 0;
    v8 = 1;
    v9 = v6;
    v10 = 0;
    v11 = 0;
    v12 = v4;
    v18 = CmOpenKey((const struct RegEntry *)&v8, 0xF003Fu);
    v13 = 1;
    v14 = L"AttachedRules";
    v15 = 0;
    v16 = 0;
    v17 = v18;
    CmDeleteKey((const struct RegEntry *)&v13);
    CmDeleteKey((const struct RegEntry *)&v8);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
    CRegHandle::~CRegHandle(&v18);
    CRegHandle::~CRegHandle(&v19);
    result = 1;
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &exception `RTTI Type Descriptor', 0) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
      __eh34_try_continuation(0, &exception `RTTI Type Descriptor', &loc_180019C9F);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180019b4c  mov     r11, rsp
0x180019b4f  mov     [r11+8], rcx
0x180019b53  push    rbx
0x180019b54  sub     rsp, 70h
0x180019b58  mov     rbx, rcx
0x180019b5b  mov     rax, [rcx+820h]
0x180019b62  test    rax, rax
0x180019b65  jz      loc_180019CA1
0x180019b6b  cmp     qword ptr [rax], 0
0x180019b6f  jz      loc_180019CA1
0x180019b75  mov     [rsp+78h+var_58], 1
0x180019b7d  lea     rax, [rcx+18h]
0x180019b81  mov     [r11-50h], rax
0x180019b85  mov     qword ptr [r11-48h], 0
0x180019b8d  mov     [rsp+78h+var_40], 0
0x180019b95  mov     [r11-38h], rdx
0x180019b99  mov     edx, 0F003Fh; samDesired
0x180019b9e  lea     rcx, [r11-58h]; struct RegEntry *
0x180019ba2  call    ?CmOpenKey@@YAPEAUHKEY__@@AEBVRegEntry@@K@Z; CmOpenKey(RegEntry const &,ulong)
0x180019ba7  mov     rdx, rax
0x180019baa  mov     [rsp+78h+arg_18], rax
0x180019bb2  mov     rax, [rbx+820h]
0x180019bb9  test    rax, rax
0x180019bbc  jz      short loc_180019BC3
0x180019bbe  mov     rcx, [rax]
0x180019bc1  jmp     short loc_180019BC5
0x180019bc3  xor     ecx, ecx
0x180019bc5  mov     [rsp+78h+var_58], 1
0x180019bcd  mov     [rsp+78h+var_50], rcx
0x180019bd2  mov     [rsp+78h+var_48], 0
0x180019bdb  mov     [rsp+78h+var_40], 0
0x180019be3  mov     [rsp+78h+var_38], rdx
0x180019be8  mov     edx, 0F003Fh; samDesired
0x180019bed  lea     rcx, [rsp+78h+var_58]; struct RegEntry *
0x180019bf2  call    ?CmOpenKey@@YAPEAUHKEY__@@AEBVRegEntry@@K@Z; CmOpenKey(RegEntry const &,ulong)
0x180019bf7  mov     [rsp+78h+arg_10], rax
0x180019bff  mov     [rsp+78h+var_30], 1
0x180019c07  lea     rcx, aAttachedrules; "AttachedRules"
0x180019c0e  mov     [rsp+78h+var_28], rcx
0x180019c13  mov     [rsp+78h+var_20], 0
0x180019c1c  mov     [rsp+78h+var_18], 0
0x180019c24  mov     [rsp+78h+var_10], rax
0x180019c29  lea     rcx, [rsp+78h+var_30]; struct RegEntry *
0x180019c2e  call    ?CmDeleteKey@@YAXAEBVRegEntry@@@Z; CmDeleteKey(RegEntry const &)
0x180019c33  lea     rcx, [rsp+78h+var_58]; struct RegEntry *
0x180019c38  call    ?CmDeleteKey@@YAXAEBVRegEntry@@@Z; CmDeleteKey(RegEntry const &)
0x180019c3d  lea     rax, WPP_GLOBAL_Control
0x180019c44  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c4b  cmp     rcx, rax
0x180019c4e  jz      short loc_180019C80
0x180019c50  test    byte ptr [rcx+1Ch], 4
0x180019c54  jz      short loc_180019C80
0x180019c56  mov     rax, [rbx+820h]
0x180019c5d  test    rax, rax
0x180019c60  jz      short loc_180019C67
0x180019c62  mov     r9, [rax]
0x180019c65  jmp     short loc_180019C6A
0x180019c67  xor     r9d, r9d
0x180019c6a  mov     edx, 17h
0x180019c6f  lea     r8, WPP_5d468cdb8ea734f7fb134a242ccb11b7_Traceguids
0x180019c76  mov     rcx, [rcx+10h]; LoggerHandle
0x180019c7a  call    WPP_SF_S
0x180019c7f  nop
0x180019c80  lea     rcx, [rsp+78h+arg_10]; this
0x180019c88  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x180019c8d  nop
0x180019c8e  lea     rcx, [rsp+78h+arg_18]; this
0x180019c96  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x180019c9b  mov     al, 1
0x180019c9d  jmp     short loc_180019CD1
0x180019c9f  jmp     short loc_180019CCF
0x180019ca1  lea     rax, WPP_GLOBAL_Control
0x180019ca8  mov     rcx, cs:WPP_GLOBAL_Control
0x180019caf  cmp     rcx, rax
0x180019cb2  jz      short loc_180019CCF
0x180019cb4  test    byte ptr [rcx+1Ch], 1
0x180019cb8  jz      short loc_180019CCF
0x180019cba  mov     edx, 16h
0x180019cbf  lea     r8, WPP_5d468cdb8ea734f7fb134a242ccb11b7_Traceguids
0x180019cc6  mov     rcx, [rcx+10h]
0x180019cca  call    WPP_SF_
0x180019ccf  xor     al, al
0x180019cd1  add     rsp, 70h
0x180019cd5  pop     rbx
0x180019cd6  retn
```
