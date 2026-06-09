# EventWriteTaskComplete(_SCRUB_ENVIRONMENT *)

- ea: `0x18000be0c`
- end: `0x18000bee5`
- name: `?EventWriteTaskComplete@@YAXPEAU_SCRUB_ENVIRONMENT@@@Z`
- size: `217`
- prototype: `void __fastcall(struct _SCRUB_ENVIRONMENT *, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000502c`

## callees

- `0x180001008`
- `0x18000166c`
- `0x18000be0c`
- `0x180010c28`
- `0x180037620`

## pseudocode

```c
void __fastcall EventWriteTaskComplete(struct _SCRUB_ENVIRONMENT *a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  int *v7; // rdx
  _QWORD v8[2]; // [rsp+30h] [rbp-28h] BYREF

  if ( *((_DWORD *)a1 + 2) )
  {
    if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 8) != 0 )
      McGenEventWrite_EventWriteTransfer(DISCAN_EVENT_PROVIDER_Context, DISCANCR_EVENT_TASK_COMPLETED, a3, 1, v8);
    if ( (unsigned int)dword_1800470B8 > 5 && (unsigned __int8)tlgKeywordOn(a1, a2, a3) )
    {
      v7 = &dword_1800413EC;
      goto LABEL_12;
    }
  }
  else
  {
    if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(DISCAN_EVENT_PROVIDER_Context, DISCAN_EVENT_TASK_COMPLETED, a3, 1, v8);
    if ( (unsigned int)dword_1800470B8 > 5 && (unsigned __int8)tlgKeywordOn(a1, a2, a3) )
    {
      v7 = (int *)byte_180041425;
LABEL_12:
      v8[0] = (char *)a1 + 52;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(
        v4,
        (__int64)v7,
        v5,
        v6,
        v8);
    }
  }
}

```

## disassembly

```asm
0x18000be0c  push    rbx
0x18000be0e  sub     rsp, 50h
0x18000be12  mov     rax, cs:__security_cookie
0x18000be19  xor     rax, rsp
0x18000be1c  mov     [rsp+58h+var_18], rax
0x18000be21  cmp     dword ptr [rcx+8], 0
0x18000be25  mov     rbx, rcx
0x18000be28  jnz     short loc_18000BE73
0x18000be2a  test    cs:Microsoft_Windows_DataIntegrityScanEnableBits, 1
0x18000be31  jz      short loc_18000BE56
0x18000be33  lea     rax, [rsp+58h+var_28]
0x18000be38  mov     r9d, 1
0x18000be3e  lea     rdx, DISCAN_EVENT_TASK_COMPLETED
0x18000be45  mov     [rsp+58h+var_38], rax
0x18000be4a  lea     rcx, DISCAN_EVENT_PROVIDER_Context
0x18000be51  call    McGenEventWrite_EventWriteTransfer
0x18000be56  mov     eax, cs:dword_1800470B8
0x18000be5c  cmp     eax, 5
0x18000be5f  jbe     short loc_18000BED2
0x18000be61  call    _tlgKeywordOn
0x18000be66  test    al, al
0x18000be68  jz      short loc_18000BED2
0x18000be6a  lea     rdx, byte_180041425
0x18000be71  jmp     short loc_18000BEBA
0x18000be73  test    cs:Microsoft_Windows_DataIntegrityScanEnableBits, 8
0x18000be7a  jz      short loc_18000BE9F
0x18000be7c  lea     rax, [rsp+58h+var_28]
0x18000be81  mov     r9d, 1
0x18000be87  lea     rdx, DISCANCR_EVENT_TASK_COMPLETED
0x18000be8e  mov     [rsp+58h+var_38], rax
0x18000be93  lea     rcx, DISCAN_EVENT_PROVIDER_Context
0x18000be9a  call    McGenEventWrite_EventWriteTransfer
0x18000be9f  mov     eax, cs:dword_1800470B8
0x18000bea5  cmp     eax, 5
0x18000bea8  jbe     short loc_18000BED2
0x18000beaa  call    _tlgKeywordOn
0x18000beaf  test    al, al
0x18000beb1  jz      short loc_18000BED2
0x18000beb3  lea     rdx, dword_1800413EC
0x18000beba  lea     rax, [rbx+34h]
0x18000bebe  mov     [rsp+58h+var_28], rax
0x18000bec3  lea     rax, [rsp+58h+var_28]
0x18000bec8  mov     [rsp+58h+var_38], rax
0x18000becd  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &)
0x18000bed2  mov     rcx, [rsp+58h+var_18]
0x18000bed7  xor     rcx, rsp; StackCookie
0x18000beda  call    __security_check_cookie
0x18000bedf  add     rsp, 50h
0x18000bee3  pop     rbx
0x18000bee4  retn
```
