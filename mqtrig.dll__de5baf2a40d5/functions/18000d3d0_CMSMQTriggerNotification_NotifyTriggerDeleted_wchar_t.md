# CMSMQTriggerNotification::NotifyTriggerDeleted(wchar_t *)

- ea: `0x18000d3d0`
- end: `0x18000d47a`
- name: `?NotifyTriggerDeleted@CMSMQTriggerNotification@@IEAAJPEA_W@Z`
- size: `170`
- prototype: `__int64 __fastcall(CMSMQTriggerNotification *__hidden this, wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180010ea0`

## callees

- `0x18000544c`
- `0x180009ab0`
- `0x18000d3d0`
- `0x18000d520`
- `0x180016024`

## string_xrefs

- `0x18000d3e9`: `MSMQTriggerNotification:TriggerDeleted`

## pseudocode

```c
__int64 __fastcall CMSMQTriggerNotification::NotifyTriggerDeleted(CMSMQTriggerNotification *this, wchar_t *a2)
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
  _bstr_t::_bstr_t((_bstr_t *)&v10, L"MSMQTriggerNotification:TriggerDeleted");
  try
  {
    FormatBSTR((struct _bstr_t *)&v13, L"TriggerID=%s");
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_6d1c6f0186f431bde13e7207227cdc41_Traceguids, v9);
    }
    v12 = (*(__int64 (__fastcall **)(const bad_hresult *))(*(_QWORD *)v8 + 16LL))(v8);
    _bstr_t::_Free((_bstr_t *)&v10);
    _bstr_t::_Free((_bstr_t *)&v13);
    return v12;
  }
  FormatBSTR((struct _bstr_t *)&v13, L"TriggerID=%s");
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
0x18000d3d0  mov     [rsp+arg_0], rbx
0x18000d3d5  push    rdi
0x18000d3d6  sub     rsp, 30h
0x18000d3da  mov     rbx, rdx
0x18000d3dd  mov     rdi, rcx
0x18000d3e0  mov     [rsp+38h+arg_18], 0
0x18000d3e9  lea     rdx, aMsmqtriggernot_4; "MSMQTriggerNotification:TriggerDeleted"
0x18000d3f0  lea     rcx, [rsp+38h+var_18]; this
0x18000d3f5  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x18000d3fa  nop
0x18000d3fb  mov     r8, rbx
0x18000d3fe  lea     rdx, aTriggeridS; "TriggerID=%s"
0x18000d405  lea     rcx, [rsp+38h+arg_18]; struct _bstr_t *
0x18000d40a  call    ?FormatBSTR@@YAXPEAV_bstr_t@@PEB_WZZ; FormatBSTR(_bstr_t *,wchar_t const *,...)
0x18000d40f  nop
0x18000d410  mov     rax, [rsp+38h+arg_18]
0x18000d415  test    rax, rax
0x18000d418  jz      short loc_18000D41F
0x18000d41a  mov     r8, [rax]
0x18000d41d  jmp     short loc_18000D422
0x18000d41f  xor     r8d, r8d; wchar_t *
0x18000d422  mov     rax, [rsp+38h+var_18]
0x18000d427  test    rax, rax
0x18000d42a  jz      short loc_18000D431
0x18000d42c  mov     rdx, [rax]
0x18000d42f  jmp     short loc_18000D433
0x18000d431  xor     edx, edx; wchar_t *
0x18000d433  mov     rcx, rdi; this
0x18000d436  call    ?SendToQueue@CMSMQTriggerNotification@@AEAAJPEA_W0@Z; CMSMQTriggerNotification::SendToQueue(wchar_t *,wchar_t *)
0x18000d43b  mov     ebx, eax
0x18000d43d  lea     rcx, [rsp+38h+var_18]; this
0x18000d442  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000d447  nop
0x18000d448  lea     rcx, [rsp+38h+arg_18]; this
0x18000d44d  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000d452  mov     eax, ebx
0x18000d454  jmp     short loc_18000D46F
0x18000d456  lea     rcx, [rsp+38h+var_18]; this
0x18000d45b  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000d460  nop
0x18000d461  lea     rcx, [rsp+38h+arg_18]; this
0x18000d466  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000d46b  mov     eax, [rsp+38h+arg_10]
0x18000d46f  mov     rbx, [rsp+38h+arg_0]
0x18000d474  add     rsp, 30h
0x18000d478  pop     rdi
0x18000d479  retn
```
