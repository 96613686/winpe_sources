# CMSMQTriggerNotification::NotifyRuleDeleted(wchar_t *)

- ea: `0x18000d1a0`
- end: `0x18000d24a`
- name: `?NotifyRuleDeleted@CMSMQTriggerNotification@@IEAAJPEA_W@Z`
- size: `170`
- prototype: `__int64 __fastcall(CMSMQTriggerNotification *__hidden this, wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000aa80`

## callees

- `0x18000544c`
- `0x180009ab0`
- `0x18000d1a0`
- `0x18000d520`
- `0x180016024`

## string_xrefs

- `0x18000d1b9`: `MSMQTriggerNotification:RuleDeleted`

## pseudocode

```c
__int64 __fastcall CMSMQTriggerNotification::NotifyRuleDeleted(CMSMQTriggerNotification *this, wchar_t *a2)
{
  wchar_t *v3; // r8
  wchar_t *v4; // rdx
  CMSMQTriggerNotification *v5; // rcx
  unsigned int v6; // ebx
  const bad_hresult *v8; // rbx
  unsigned int v9; // eax
  wchar_t **v10; // [rsp+20h] [rbp-18h] BYREF
  const bad_hresult *v11; // [rsp+28h] [rbp-10h] BYREF
  unsigned int v12; // [rsp+50h] [rbp+18h]
  wchar_t **v13; // [rsp+58h] [rbp+20h] BYREF

  v13 = 0;
  _bstr_t::_bstr_t((_bstr_t *)&v10, L"MSMQTriggerNotification:RuleDeleted");
  try
  {
    FormatBSTR((struct _bstr_t *)&v13, L"RuleID=%s");
    if ( v13 )
      v3 = *v13;
    else
      v3 = 0;
    if ( v10 )
      v4 = *v10;
    else
      v4 = 0;
    v5 = this;
  }
  catch ( const bad_hresult *v11 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      v8 = v11;
    }
    else
    {
      v8 = v11;
      v9 = (*(__int64 (__fastcall **)(const bad_hresult *))(*(_QWORD *)v11 + 16LL))(v11);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_6d1c6f0186f431bde13e7207227cdc41_Traceguids, v9);
    }
    v12 = (*(__int64 (__fastcall **)(const bad_hresult *))(*(_QWORD *)v8 + 16LL))(v8);
    _bstr_t::_Free((_bstr_t *)&v10);
    _bstr_t::_Free((_bstr_t *)&v13);
    return v12;
  }
  FormatBSTR((struct _bstr_t *)&v13, L"RuleID=%s");
  if ( v13 )
    v3 = *v13;
  else
    v3 = 0;
  if ( v10 )
    v4 = *v10;
  else
    v4 = 0;
  v5 = this;
}

```

## disassembly

```asm
0x18000d1a0  mov     [rsp+arg_0], rbx
0x18000d1a5  push    rdi
0x18000d1a6  sub     rsp, 30h
0x18000d1aa  mov     rbx, rdx
0x18000d1ad  mov     rdi, rcx
0x18000d1b0  mov     [rsp+38h+arg_18], 0
0x18000d1b9  lea     rdx, aMsmqtriggernot_0; "MSMQTriggerNotification:RuleDeleted"
0x18000d1c0  lea     rcx, [rsp+38h+var_18]; this
0x18000d1c5  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x18000d1ca  nop
0x18000d1cb  mov     r8, rbx
0x18000d1ce  lea     rdx, aRuleidS; "RuleID=%s"
0x18000d1d5  lea     rcx, [rsp+38h+arg_18]; struct _bstr_t *
0x18000d1da  call    ?FormatBSTR@@YAXPEAV_bstr_t@@PEB_WZZ; FormatBSTR(_bstr_t *,wchar_t const *,...)
0x18000d1df  nop
0x18000d1e0  mov     rax, [rsp+38h+arg_18]
0x18000d1e5  test    rax, rax
0x18000d1e8  jz      short loc_18000D1EF
0x18000d1ea  mov     r8, [rax]
0x18000d1ed  jmp     short loc_18000D1F2
0x18000d1ef  xor     r8d, r8d; wchar_t *
0x18000d1f2  mov     rax, [rsp+38h+var_18]
0x18000d1f7  test    rax, rax
0x18000d1fa  jz      short loc_18000D201
0x18000d1fc  mov     rdx, [rax]
0x18000d1ff  jmp     short loc_18000D203
0x18000d201  xor     edx, edx; wchar_t *
0x18000d203  mov     rcx, rdi; this
0x18000d206  call    ?SendToQueue@CMSMQTriggerNotification@@AEAAJPEA_W0@Z; CMSMQTriggerNotification::SendToQueue(wchar_t *,wchar_t *)
0x18000d20b  mov     ebx, eax
0x18000d20d  lea     rcx, [rsp+38h+var_18]; this
0x18000d212  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000d217  nop
0x18000d218  lea     rcx, [rsp+38h+arg_18]; this
0x18000d21d  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000d222  mov     eax, ebx
0x18000d224  jmp     short loc_18000D23F
0x18000d226  lea     rcx, [rsp+38h+var_18]; this
0x18000d22b  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000d230  nop
0x18000d231  lea     rcx, [rsp+38h+arg_18]; this
0x18000d236  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000d23b  mov     eax, [rsp+38h+arg_10]
0x18000d23f  mov     rbx, [rsp+38h+arg_0]
0x18000d244  add     rsp, 30h
0x18000d248  pop     rdi
0x18000d249  retn
```
