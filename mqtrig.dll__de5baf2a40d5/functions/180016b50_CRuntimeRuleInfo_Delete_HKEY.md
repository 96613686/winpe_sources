# CRuntimeRuleInfo::Delete(HKEY__ *)

- ea: `0x180016b50`
- end: `0x180016be9`
- name: `?Delete@CRuntimeRuleInfo@@QEAA_NPEAUHKEY__@@@Z`
- size: `153`
- prototype: `bool __fastcall(CRuntimeRuleInfo *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000aa80`

## callees

- `0x18000a2b8`
- `0x180015068`
- `0x1800150b8`
- `0x180016b50`

## pseudocode

```c
bool __fastcall CRuntimeRuleInfo::Delete(CRuntimeRuleInfo *this, HKEY a2)
{
  HKEY v3; // rcx
  char *v4; // rax
  bool result; // al
  int v6; // [rsp+20h] [rbp-38h] BYREF
  char *v7; // [rsp+28h] [rbp-30h]
  __int64 v8; // [rsp+30h] [rbp-28h]
  int v9; // [rsp+38h] [rbp-20h]
  HKEY v10; // [rsp+40h] [rbp-18h]
  HKEY v11; // [rsp+68h] [rbp+10h] BYREF

  v6 = 1;
  v7 = (char *)this + 48;
  v8 = 0;
  v9 = 0;
  v10 = a2;
  try
  {
    v3 = CmOpenKey((const struct RegEntry *)&v6, 0xF003Fu);
    v11 = v3;
    v4 = *(char **)this;
    if ( *(_QWORD *)this )
      v4 = *(char **)v4;
    v6 = 1;
    v7 = v4;
    v8 = 0;
    v9 = 0;
    v10 = v3;
    CmDeleteKey((const struct RegEntry *)&v6);
    CRegHandle::~CRegHandle(&v11);
    result = 1;
  }
  catch ( exception )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
    return 0;
  }
  v3 = CmOpenKey((const struct RegEntry *)&v6, 0xF003Fu);
}

```

## disassembly

```asm
0x180016b50  mov     r11, rsp
0x180016b53  mov     [r11+8], rcx
0x180016b57  push    rbx
0x180016b58  sub     rsp, 50h
0x180016b5c  mov     rbx, rcx
0x180016b5f  mov     [rsp+58h+var_38], 1
0x180016b67  lea     rax, [rcx+30h]
0x180016b6b  mov     [r11-30h], rax
0x180016b6f  mov     qword ptr [r11-28h], 0
0x180016b77  mov     [rsp+58h+var_20], 0
0x180016b7f  mov     [r11-18h], rdx
0x180016b83  mov     edx, 0F003Fh; samDesired
0x180016b88  lea     rcx, [r11-38h]; struct RegEntry *
0x180016b8c  call    ?CmOpenKey@@YAPEAUHKEY__@@AEBVRegEntry@@K@Z; CmOpenKey(RegEntry const &,ulong)
0x180016b91  mov     rcx, rax
0x180016b94  mov     [rsp+58h+arg_8], rax
0x180016b99  mov     rax, [rbx]
0x180016b9c  test    rax, rax
0x180016b9f  jz      short loc_180016BA4
0x180016ba1  mov     rax, [rax]
0x180016ba4  mov     [rsp+58h+var_38], 1
0x180016bac  mov     [rsp+58h+var_30], rax
0x180016bb1  mov     [rsp+58h+var_28], 0
0x180016bba  mov     [rsp+58h+var_20], 0
0x180016bc2  mov     [rsp+58h+var_18], rcx
0x180016bc7  lea     rcx, [rsp+58h+var_38]; struct RegEntry *
0x180016bcc  call    ?CmDeleteKey@@YAXAEBVRegEntry@@@Z; CmDeleteKey(RegEntry const &)
0x180016bd1  nop
0x180016bd2  lea     rcx, [rsp+58h+arg_8]; this
0x180016bd7  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x180016bdc  mov     al, 1
0x180016bde  jmp     short loc_180016BE2
0x180016be0  xor     al, al
0x180016be2  add     rsp, 50h
0x180016be6  pop     rbx
0x180016be7  retn
```
