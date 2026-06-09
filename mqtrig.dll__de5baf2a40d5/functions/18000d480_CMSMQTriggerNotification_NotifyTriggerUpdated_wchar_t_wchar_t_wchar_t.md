# CMSMQTriggerNotification::NotifyTriggerUpdated(wchar_t *,wchar_t *,wchar_t *)

- ea: `0x18000d480`
- end: `0x18000d519`
- name: `?NotifyTriggerUpdated@CMSMQTriggerNotification@@IEAAJPEA_W00@Z`
- size: `153`
- prototype: `__int64 __fastcall(CMSMQTriggerNotification *__hidden this, wchar_t *, wchar_t *, wchar_t *)`
- caller_count: `4`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180010b60`
- `0x180011160`
- `0x180011330`
- `0x180012f40`

## callees

- `0x18000544c`
- `0x180009ab0`
- `0x18000d480`
- `0x18000d520`
- `0x180016024`

## string_xrefs

- `0x18000d49e`: `MSMQTriggerNotification:TriggerUpdated`

## pseudocode

```c
__int64 __fastcall CMSMQTriggerNotification::NotifyTriggerUpdated(
        CMSMQTriggerNotification *this,
        wchar_t *a2,
        wchar_t *a3,
        wchar_t *a4)
{
  wchar_t *v8; // r8
  wchar_t *v9; // rdx
  unsigned int v10; // ebx
  wchar_t **v12; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v13[6]; // [rsp+38h] [rbp-30h] BYREF

  v12 = 0;
  _bstr_t::_bstr_t((_bstr_t *)v13, L"MSMQTriggerNotification:TriggerUpdated");
  FormatBSTR((struct _bstr_t *)&v12, L"TriggerID=%s;TriggerName=%s;QueueName=%s", a2, a3, a4);
  if ( v12 )
    v8 = *v12;
  else
    v8 = 0;
  if ( v13[0] )
    v9 = *(wchar_t **)v13[0];
  else
    v9 = 0;
  v10 = CMSMQTriggerNotification::SendToQueue(this, v9, v8);
  _bstr_t::_Free((_bstr_t *)v13);
  _bstr_t::_Free((_bstr_t *)&v12);
  return v10;
}

```

## disassembly

```asm
0x18000d480  push    rbx
0x18000d482  push    rbp
0x18000d483  push    rsi
0x18000d484  push    rdi
0x18000d485  sub     rsp, 48h
0x18000d489  mov     rbx, r9
0x18000d48c  mov     rdi, r8
0x18000d48f  mov     rsi, rdx
0x18000d492  mov     rbp, rcx
0x18000d495  mov     [rsp+68h+var_38], 0
0x18000d49e  lea     rdx, aMsmqtriggernot; "MSMQTriggerNotification:TriggerUpdated"
0x18000d4a5  lea     rcx, [rsp+68h+var_30]; this
0x18000d4aa  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x18000d4af  nop
0x18000d4b0  mov     [rsp+68h+var_48], rbx
0x18000d4b5  mov     r9, rdi
0x18000d4b8  mov     r8, rsi
0x18000d4bb  lea     rdx, aTriggeridSTrig; "TriggerID=%s;TriggerName=%s;QueueName=%"...
0x18000d4c2  lea     rcx, [rsp+68h+var_38]; struct _bstr_t *
0x18000d4c7  call    ?FormatBSTR@@YAXPEAV_bstr_t@@PEB_WZZ; FormatBSTR(_bstr_t *,wchar_t const *,...)
0x18000d4cc  mov     rax, [rsp+68h+var_38]
0x18000d4d1  test    rax, rax
0x18000d4d4  jz      short loc_18000D4DB
0x18000d4d6  mov     r8, [rax]
0x18000d4d9  jmp     short loc_18000D4DE
0x18000d4db  xor     r8d, r8d; wchar_t *
0x18000d4de  mov     rax, [rsp+68h+var_30]
0x18000d4e3  test    rax, rax
0x18000d4e6  jz      short loc_18000D4ED
0x18000d4e8  mov     rdx, [rax]
0x18000d4eb  jmp     short loc_18000D4EF
0x18000d4ed  xor     edx, edx; wchar_t *
0x18000d4ef  mov     rcx, rbp; this
0x18000d4f2  call    ?SendToQueue@CMSMQTriggerNotification@@AEAAJPEA_W0@Z; CMSMQTriggerNotification::SendToQueue(wchar_t *,wchar_t *)
0x18000d4f7  mov     ebx, eax
0x18000d4f9  lea     rcx, [rsp+68h+var_30]; this
0x18000d4fe  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000d503  nop
0x18000d504  lea     rcx, [rsp+68h+var_38]; this
0x18000d509  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000d50e  mov     eax, ebx
0x18000d510  add     rsp, 48h
0x18000d514  pop     rdi
0x18000d515  pop     rsi
0x18000d516  pop     rbp
0x18000d517  pop     rbx
0x18000d518  retn
```
