# RemoveTraceCallback

- ea: `0x1800080f0`
- end: `0x180008322`
- name: `RemoveTraceCallback`
- size: `562`
- prototype: `ULONG __stdcall(LPCGUID pGuid)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callees

- `0x180001008`
- `0x180001560`
- `0x180002014`
- `0x180002ec4`
- `0x180003f04`
- `0x1800080f0`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000828d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000828d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000824e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000824e`
- `ntdll!RtlSetLastWin32Error` at `0x1800082cd`
- `ntdll!RtlSetLastWin32Error` at `0x1800082cd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180008153`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180008153`

## pseudocode

```c
ULONG __stdcall RemoveTraceCallback(LPCGUID pGuid)
{
  GUID *v2; // rax
  GUID v3; // xmm0
  _OWORD *v4; // rcx
  void **v5; // rax
  ULONG v6; // ebx
  void **v7; // rdx
  ULONG LastError; // [rsp+30h] [rbp-49h] BYREF
  _QWORD v10[2]; // [rsp+38h] [rbp-41h] BYREF
  char v11; // [rsp+48h] [rbp-31h]
  int v12; // [rsp+50h] [rbp-29h] BYREF
  char v13; // [rsp+54h] [rbp-25h]
  GUID ActivityId; // [rsp+58h] [rbp-21h] BYREF
  GUID v15; // [rsp+78h] [rbp-1h] BYREF
  __int128 v16; // [rsp+88h] [rbp+Fh] BYREF
  _BYTE v17[32]; // [rsp+98h] [rbp+1Fh] BYREF
  GUID *v18; // [rsp+B8h] [rbp+3Fh]
  __int64 v19; // [rsp+C0h] [rbp+47h]

  LastError = 0;
  v12 = 0;
  v13 = 0;
  if ( (unsigned int)dword_18001D020 > 5 && (qword_18001D030 & 0x10) != 0 && (qword_18001D038 & 0x10) == qword_18001D038 )
    EventActivityIdControl(3u, &ActivityId);
  else
    ActivityId = 0;
  v12 = 1;
  if ( (unsigned int)dword_18001D020 > 5 && (qword_18001D030 & 0x10) != 0 && (qword_18001D038 & 0x10) == qword_18001D038 )
  {
    if ( pGuid )
    {
      v2 = &v15;
      v15 = *pGuid;
    }
    else
    {
      v2 = (GUID *)&v16;
      v16 = 0;
    }
    v18 = v2;
    v19 = 16;
    tlgWriteTransfer_EtwEventWriteTransfer(
      (__int64)&dword_18001D020,
      (unsigned __int8 *)&unk_180018B00,
      (__int64)&ActivityId,
      0,
      3,
      (__int64)v17);
  }
  v11 = 1;
  v10[0] = &v12;
  v10[1] = &LastError;
  if ( !pGuid || !EtwpEventCallbackList )
  {
    v6 = 87;
    LastError = 87;
LABEL_25:
    RtlSetLastWin32Error(v6);
    goto LABEL_26;
  }
  v3 = *pGuid;
  LastError = 4200;
  v15 = v3;
  RtlAcquireSRWLockExclusive(&EtwpConsumerLock);
  v4 = EtwpEventCallbackList;
  if ( EtwpEventCallbackList != &EtwpEventCallbackList )
  {
    while ( 1 )
    {
      v5 = *(void ***)v4;
      if ( v4[1] == *(_OWORD *)&v15 )
        break;
      v4 = *(_OWORD **)v4;
      if ( v5 == &EtwpEventCallbackList )
        goto LABEL_18;
    }
    if ( v5[1] != v4 || (v7 = (void **)*((_QWORD *)v4 + 1), *v7 != v4) )
      __fastfail(3u);
    *v7 = v5;
    v5[1] = v7;
    operator delete(v4);
    LastError = 0;
  }
LABEL_18:
  RtlReleaseSRWLockExclusive(&EtwpConsumerLock);
  v6 = LastError;
  if ( LastError )
    goto LABEL_25;
LABEL_26:
  if ( v11 )
    lambda_cd9191f3c19abe546b94e7eca0378842_::operator()(v10);
  if ( v12 == 1 )
  {
    v12 = 2;
    _tlgWriteActivityAutoStop<16,5>((unsigned int *)&dword_18001D020, (__int64)&ActivityId);
  }
  return v6;
}

```

## disassembly

```asm
0x1800080f0  mov     [rsp-8+arg_0], rbx
0x1800080f5  mov     [rsp-8+arg_8], rdi
0x1800080fa  push    rbp
0x1800080fb  lea     rbp, [rsp-57h]
0x180008100  sub     rsp, 0D0h
0x180008107  mov     rax, cs:__security_cookie
0x18000810e  xor     rax, rsp
0x180008111  mov     [rbp+57h+var_8], rax
0x180008115  mov     eax, cs:dword_18001D020
0x18000811b  xor     edi, edi
0x18000811d  mov     [rbp+57h+LastError], edi
0x180008120  mov     rbx, rcx
0x180008123  mov     [rbp+57h+var_80], edi
0x180008126  mov     [rbp+57h+var_7C], dil
0x18000812a  cmp     eax, 5
0x18000812d  jbe     short loc_18000815B
0x18000812f  mov     rcx, cs:qword_18001D038
0x180008136  mov     rax, cs:qword_18001D030
0x18000813d  test    al, 10h
0x18000813f  jz      short loc_18000815B
0x180008141  mov     rax, rcx
0x180008144  and     eax, 10h
0x180008147  cmp     rax, rcx
0x18000814a  jnz     short loc_18000815B
0x18000814c  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x180008150  lea     ecx, [rdi+3]; ControlCode
0x180008153  call    cs:__imp_EventActivityIdControl
0x180008159  jmp     short loc_180008162
0x18000815b  xorps   xmm0, xmm0
0x18000815e  movups  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x180008162  mov     eax, cs:dword_18001D020
0x180008168  mov     [rbp+57h+var_80], 1
0x18000816f  cmp     eax, 5
0x180008172  jbe     loc_18000820E
0x180008178  mov     rcx, cs:qword_18001D038
0x18000817f  mov     rax, cs:qword_18001D030
0x180008186  test    al, 10h
0x180008188  jz      loc_18000820E
0x18000818e  mov     rax, rcx
0x180008191  and     eax, 10h
0x180008194  cmp     rax, rcx
0x180008197  jnz     short loc_18000820E
0x180008199  test    rbx, rbx
0x18000819c  jz      short loc_1800081AC
0x18000819e  movups  xmm0, xmmword ptr [rbx]
0x1800081a1  lea     rax, [rbp+57h+var_58]
0x1800081a5  movdqu  [rbp+57h+var_58], xmm0
0x1800081aa  jmp     short loc_1800081B7
0x1800081ac  xorps   xmm0, xmm0
0x1800081af  lea     rax, [rbp+57h+var_48]
0x1800081b3  movups  [rbp+57h+var_48], xmm0
0x1800081b7  cmp     [rbp+57h+var_7C], dil
0x1800081bb  jz      short loc_1800081D7
0x1800081bd  cmp     [rbp+57h+var_68], edi
0x1800081c0  jnz     short loc_1800081D1
0x1800081c2  cmp     [rbp+57h+var_64], edi
0x1800081c5  jnz     short loc_1800081D1
0x1800081c7  cmp     [rbp+57h+var_60], edi
0x1800081ca  jnz     short loc_1800081D1
0x1800081cc  cmp     [rbp+57h+var_5C], edi
0x1800081cf  jz      short loc_1800081D7
0x1800081d1  lea     r9, [rbp+57h+var_68]
0x1800081d5  jmp     short loc_1800081DA
0x1800081d7  mov     r9, rdi
0x1800081da  mov     [rbp+57h+var_18], rax
0x1800081de  lea     r8, [rbp+57h+ActivityId]
0x1800081e2  lea     rax, [rbp+57h+var_38]
0x1800081e6  mov     [rbp+57h+var_10], 10h
0x1800081ee  mov     [rsp+0D0h+var_A8], rax
0x1800081f3  lea     rdx, unk_180018B00
0x1800081fa  lea     rcx, dword_18001D020
0x180008201  mov     [rsp+0D0h+var_B0], 3
0x180008209  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18000820e  mov     [rbp+57h+var_88], 1
0x180008212  lea     rax, [rbp+57h+var_80]
0x180008216  mov     [rbp+57h+var_98], rax
0x18000821a  lea     rax, [rbp+57h+LastError]
0x18000821e  mov     [rbp+57h+var_90], rax
0x180008222  test    rbx, rbx
0x180008225  jz      loc_1800082C3
0x18000822b  cmp     cs:?EtwpEventCallbackList@@3U_LIST_ENTRY@@A, rdi; _LIST_ENTRY EtwpEventCallbackList
0x180008232  jz      loc_1800082C3
0x180008238  movups  xmm0, xmmword ptr [rbx]
0x18000823b  lea     rcx, ?EtwpConsumerLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK EtwpConsumerLock
0x180008242  mov     [rbp+57h+LastError], 1068h
0x180008249  movdqu  [rbp+57h+var_58], xmm0
0x18000824e  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180008254  mov     rcx, cs:?EtwpEventCallbackList@@3U_LIST_ENTRY@@A; Block
0x18000825b  lea     r9, ?EtwpEventCallbackList@@3U_LIST_ENTRY@@A; _LIST_ENTRY EtwpEventCallbackList
0x180008262  cmp     rcx, r9
0x180008265  jz      short loc_180008286
0x180008267  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x18000826b  mov     r8, qword ptr [rbp+57h+var_58]
0x18000826f  mov     rax, [rcx]
0x180008272  cmp     [rcx+10h], r8
0x180008276  jnz     short loc_18000827E
0x180008278  cmp     [rcx+18h], rdx
0x18000827c  jz      short loc_18000829C
0x18000827e  mov     rcx, rax
0x180008281  cmp     rax, r9
0x180008284  jnz     short loc_18000826F
0x180008286  lea     rcx, ?EtwpConsumerLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK EtwpConsumerLock
0x18000828d  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180008293  mov     ebx, [rbp+57h+LastError]
0x180008296  test    ebx, ebx
0x180008298  jz      short loc_1800082D3
0x18000829a  jmp     short loc_1800082CB
0x18000829c  cmp     [rax+8], rcx
0x1800082a0  jnz     short loc_1800082BC
0x1800082a2  mov     rdx, [rcx+8]
0x1800082a6  cmp     [rdx], rcx
0x1800082a9  jnz     short loc_1800082BC
0x1800082ab  mov     [rdx], rax
0x1800082ae  mov     [rax+8], rdx
0x1800082b2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800082b7  mov     [rbp+57h+LastError], edi
0x1800082ba  jmp     short loc_180008286
0x1800082bc  mov     ecx, 3
0x1800082c1  int     29h; Win8: RtlFailFast(ecx)
0x1800082c3  mov     ebx, 57h ; 'W'
0x1800082c8  mov     [rbp+57h+LastError], ebx
0x1800082cb  mov     ecx, ebx; LastError
0x1800082cd  call    cs:__imp_RtlSetLastWin32Error
0x1800082d3  cmp     [rbp+57h+var_88], dil
0x1800082d7  jz      short loc_1800082E2
0x1800082d9  lea     rcx, [rbp+57h+var_98]
0x1800082dd  call    _lambda_cd9191f3c19abe546b94e7eca0378842___operator__
0x1800082e2  cmp     [rbp+57h+var_80], 1
0x1800082e6  jnz     short loc_1800082FF
0x1800082e8  lea     rdx, [rbp+57h+ActivityId]
0x1800082ec  mov     [rbp+57h+var_80], 2
0x1800082f3  lea     rcx, dword_18001D020
0x1800082fa  call    ??$_tlgWriteActivityAutoStop@$0BA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<16,5>(_tlgProvider_t const *,_GUID const *)
0x1800082ff  mov     eax, ebx
0x180008301  mov     rcx, [rbp+57h+var_8]
0x180008305  xor     rcx, rsp; StackCookie
0x180008308  call    __security_check_cookie
0x18000830d  lea     r11, [rsp+0D0h+var_s0]
0x180008315  mov     rbx, [r11+10h]
0x180008319  mov     rdi, [r11+18h]
0x18000831d  mov     rsp, r11
0x180008320  pop     rbp
0x180008321  retn
```
