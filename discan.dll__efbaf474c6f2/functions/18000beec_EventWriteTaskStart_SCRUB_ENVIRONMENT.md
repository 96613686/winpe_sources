# EventWriteTaskStart(_SCRUB_ENVIRONMENT *)

- ea: `0x18000beec`
- end: `0x18000bfc5`
- name: `?EventWriteTaskStart@@YAXPEAU_SCRUB_ENVIRONMENT@@@Z`
- size: `217`
- prototype: `void __fastcall(struct _SCRUB_ENVIRONMENT *, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800056f8`

## callees

- `0x180001008`
- `0x18000166c`
- `0x18000beec`
- `0x180010c28`
- `0x180037620`

## pseudocode

```c
void __fastcall EventWriteTaskStart(struct _SCRUB_ENVIRONMENT *a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  int *v7; // rdx
  _QWORD v8[2]; // [rsp+30h] [rbp-28h] BYREF

  if ( *((_DWORD *)a1 + 2) )
  {
    if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 8) != 0 )
      McGenEventWrite_EventWriteTransfer(DISCAN_EVENT_PROVIDER_Context, DISCANCR_EVENT_TASK_STARTING, a3, 1, v8);
    if ( (unsigned int)dword_1800470B8 > 5 && (unsigned __int8)tlgKeywordOn(a1, a2, a3) )
    {
      v7 = &dword_18004145C;
      goto LABEL_12;
    }
  }
  else
  {
    if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(DISCAN_EVENT_PROVIDER_Context, DISCAN_EVENT_TASK_STARTING, a3, 1, v8);
    if ( (unsigned int)dword_1800470B8 > 5 && (unsigned __int8)tlgKeywordOn(a1, a2, a3) )
    {
      v7 = &dword_180041494;
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
0x18000beec  push    rbx
0x18000beee  sub     rsp, 50h
0x18000bef2  mov     rax, cs:__security_cookie
0x18000bef9  xor     rax, rsp
0x18000befc  mov     [rsp+58h+var_18], rax
0x18000bf01  cmp     dword ptr [rcx+8], 0
0x18000bf05  mov     rbx, rcx
0x18000bf08  jnz     short loc_18000BF53
0x18000bf0a  test    cs:Microsoft_Windows_DataIntegrityScanEnableBits, 1
0x18000bf11  jz      short loc_18000BF36
0x18000bf13  lea     rax, [rsp+58h+var_28]
0x18000bf18  mov     r9d, 1
0x18000bf1e  lea     rdx, DISCAN_EVENT_TASK_STARTING
0x18000bf25  mov     [rsp+58h+var_38], rax
0x18000bf2a  lea     rcx, DISCAN_EVENT_PROVIDER_Context
0x18000bf31  call    McGenEventWrite_EventWriteTransfer
0x18000bf36  mov     eax, cs:dword_1800470B8
0x18000bf3c  cmp     eax, 5
0x18000bf3f  jbe     short loc_18000BFB2
0x18000bf41  call    _tlgKeywordOn
0x18000bf46  test    al, al
0x18000bf48  jz      short loc_18000BFB2
0x18000bf4a  lea     rdx, dword_180041494
0x18000bf51  jmp     short loc_18000BF9A
0x18000bf53  test    cs:Microsoft_Windows_DataIntegrityScanEnableBits, 8
0x18000bf5a  jz      short loc_18000BF7F
0x18000bf5c  lea     rax, [rsp+58h+var_28]
0x18000bf61  mov     r9d, 1
0x18000bf67  lea     rdx, DISCANCR_EVENT_TASK_STARTING
0x18000bf6e  mov     [rsp+58h+var_38], rax
0x18000bf73  lea     rcx, DISCAN_EVENT_PROVIDER_Context
0x18000bf7a  call    McGenEventWrite_EventWriteTransfer
0x18000bf7f  mov     eax, cs:dword_1800470B8
0x18000bf85  cmp     eax, 5
0x18000bf88  jbe     short loc_18000BFB2
0x18000bf8a  call    _tlgKeywordOn
0x18000bf8f  test    al, al
0x18000bf91  jz      short loc_18000BFB2
0x18000bf93  lea     rdx, dword_18004145C
0x18000bf9a  lea     rax, [rbx+34h]
0x18000bf9e  mov     [rsp+58h+var_28], rax
0x18000bfa3  lea     rax, [rsp+58h+var_28]
0x18000bfa8  mov     [rsp+58h+var_38], rax
0x18000bfad  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &)
0x18000bfb2  mov     rcx, [rsp+58h+var_18]
0x18000bfb7  xor     rcx, rsp; StackCookie
0x18000bfba  call    __security_check_cookie
0x18000bfbf  add     rsp, 50h
0x18000bfc3  pop     rbx
0x18000bfc4  retn
```
