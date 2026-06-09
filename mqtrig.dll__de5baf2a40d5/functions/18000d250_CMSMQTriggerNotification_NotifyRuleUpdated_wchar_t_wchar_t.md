# CMSMQTriggerNotification::NotifyRuleUpdated(wchar_t *,wchar_t *)

- ea: `0x18000d250`
- end: `0x18000d309`
- name: `?NotifyRuleUpdated@CMSMQTriggerNotification@@IEAAJPEA_W0@Z`
- size: `185`
- prototype: `__int64 __fastcall(CMSMQTriggerNotification *__hidden this, wchar_t *, wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18000bda0`

## callees

- `0x18000544c`
- `0x180009ab0`
- `0x18000d250`
- `0x18000d520`
- `0x180016024`

## string_xrefs

- `0x18000d271`: `MSMQTriggerNotification:RuleUpdated`

## pseudocode

```c
__int64 __fastcall CMSMQTriggerNotification::NotifyRuleUpdated(
        CMSMQTriggerNotification *this,
        wchar_t *a2,
        wchar_t *a3)
{
  wchar_t *v4; // r8
  wchar_t *v5; // rdx
  CMSMQTriggerNotification *v6; // rcx
  unsigned int v7; // ebx
  const bad_hresult *v9; // rbx
  unsigned int v10; // eax
  wchar_t **v11; // [rsp+20h] [rbp-28h] BYREF
  wchar_t **v12; // [rsp+28h] [rbp-20h] BYREF
  const bad_hresult *v13; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v14; // [rsp+68h] [rbp+20h]

  v11 = 0;
  _bstr_t::_bstr_t((_bstr_t *)&v12, L"MSMQTriggerNotification:RuleUpdated");
  try
  {
    FormatBSTR((struct _bstr_t *)&v11, L"RuleID=%s;RuleName=%s");
    if ( v11 )
      v4 = *v11;
    else
      v4 = 0;
    if ( v12 )
      v5 = *v12;
    else
      v5 = 0;
    v6 = this;
  }
  catch ( const bad_hresult *v13 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      v9 = v13;
    }
    else
    {
      v9 = v13;
      v10 = (*(__int64 (__fastcall **)(const bad_hresult *))(*(_QWORD *)v13 + 16LL))(v13);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_6d1c6f0186f431bde13e7207227cdc41_Traceguids, v10);
    }
    v14 = (*(__int64 (__fastcall **)(const bad_hresult *))(*(_QWORD *)v9 + 16LL))(v9);
    _bstr_t::_Free((_bstr_t *)&v12);
    _bstr_t::_Free((_bstr_t *)&v11);
    return v14;
  }
  FormatBSTR((struct _bstr_t *)&v11, L"RuleID=%s;RuleName=%s");
  if ( v11 )
    v4 = *v11;
  else
    v4 = 0;
  if ( v12 )
    v5 = *v12;
  else
    v5 = 0;
  v6 = this;
}

```

## disassembly

```asm
0x18000d250  mov     rax, rsp
0x18000d253  mov     [rax+8], rbx
0x18000d257  mov     [rax+10h], rsi
0x18000d25b  push    rdi
0x18000d25c  sub     rsp, 40h
0x18000d260  mov     rbx, r8
0x18000d263  mov     rdi, rdx
0x18000d266  mov     rsi, rcx
0x18000d269  mov     qword ptr [rax-28h], 0
0x18000d271  lea     rdx, aMsmqtriggernot_2; "MSMQTriggerNotification:RuleUpdated"
0x18000d278  lea     rcx, [rax-20h]; this
0x18000d27c  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x18000d281  nop
0x18000d282  mov     r9, rbx
0x18000d285  mov     r8, rdi
0x18000d288  lea     rdx, aRuleidSRulenam; "RuleID=%s;RuleName=%s"
0x18000d28f  lea     rcx, [rsp+48h+var_28]; struct _bstr_t *
0x18000d294  call    ?FormatBSTR@@YAXPEAV_bstr_t@@PEB_WZZ; FormatBSTR(_bstr_t *,wchar_t const *,...)
0x18000d299  nop
0x18000d29a  mov     rax, [rsp+48h+var_28]
0x18000d29f  test    rax, rax
0x18000d2a2  jz      short loc_18000D2A9
0x18000d2a4  mov     r8, [rax]
0x18000d2a7  jmp     short loc_18000D2AC
0x18000d2a9  xor     r8d, r8d; wchar_t *
0x18000d2ac  mov     rax, [rsp+48h+var_20]
0x18000d2b1  test    rax, rax
0x18000d2b4  jz      short loc_18000D2BB
0x18000d2b6  mov     rdx, [rax]
0x18000d2b9  jmp     short loc_18000D2BD
0x18000d2bb  xor     edx, edx; wchar_t *
0x18000d2bd  mov     rcx, rsi; this
0x18000d2c0  call    ?SendToQueue@CMSMQTriggerNotification@@AEAAJPEA_W0@Z; CMSMQTriggerNotification::SendToQueue(wchar_t *,wchar_t *)
0x18000d2c5  mov     ebx, eax
0x18000d2c7  lea     rcx, [rsp+48h+var_20]; this
0x18000d2cc  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000d2d1  nop
0x18000d2d2  lea     rcx, [rsp+48h+var_28]; this
0x18000d2d7  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000d2dc  mov     eax, ebx
0x18000d2de  jmp     short loc_18000D2F9
0x18000d2e0  lea     rcx, [rsp+48h+var_20]; this
0x18000d2e5  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000d2ea  nop
0x18000d2eb  lea     rcx, [rsp+48h+var_28]; this
0x18000d2f0  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000d2f5  mov     eax, [rsp+48h+arg_18]
0x18000d2f9  mov     rbx, [rsp+48h+arg_0]
0x18000d2fe  mov     rsi, [rsp+48h+arg_8]
0x18000d303  add     rsp, 40h
0x18000d307  pop     rdi
0x18000d308  retn
```
