# InputTraceLogging::PerfRegion::PerfRegion(char const *,InputTraceLogging::PerfRegion const *)

- ea: `0x180112110`
- end: `0x18011239c`
- name: `??0PerfRegion@InputTraceLogging@@QEAA@PEBDPEBU01@@Z`
- size: `652`
- prototype: `__int64 __fastcall(InputTraceLogging::PerfRegion *__hidden this, const char *, const struct InputTraceLogging::PerfRegion *)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180111950`
- `0x18011374c`
- `0x180113920`
- `0x180189268`

## callees

- `0x180112110`
- `0x18017bf60`
- `0x18017c09c`
- `0x180228490`
- `0x180228840`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1801121c3`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1801121c3`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18011226e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18011226e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180112371`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180112371`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801121a1`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801121a1`

## pseudocode

```c
InputTraceLogging::PerfRegion *__fastcall InputTraceLogging::PerfRegion::PerfRegion(
        InputTraceLogging::PerfRegion *this,
        const char *a2,
        const struct InputTraceLogging::PerfRegion *a3)
{
  _OWORD *v3; // rax
  __int128 v5; // xmm0
  const struct _tlgProvider_t *v6; // rcx
  __int64 v7; // r10
  const char *v8; // rcx
  const GUID *v9; // r9
  __int64 v10; // rax
  int v11; // eax
  WINBOOL fPending; // [rsp+30h] [rbp-58h] BYREF
  EVENT_DESCRIPTOR Context; // [rsp+38h] [rbp-50h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+48h] [rbp-40h] BYREF
  char *v16; // [rsp+58h] [rbp-30h]
  int v17; // [rsp+60h] [rbp-28h]
  int v18; // [rsp+64h] [rbp-24h]
  const char *v19; // [rsp+68h] [rbp-20h]
  int v20; // [rsp+70h] [rbp-18h]
  int v21; // [rsp+74h] [rbp-14h]

  *(_BYTE *)this = 0;
  v3 = (_OWORD *)((char *)this + 32);
  *((_QWORD *)this + 1) = a2;
  *((_OWORD *)this + 1) = 0;
  *((_OWORD *)this + 2) = 0;
  *((_QWORD *)this + 6) = 0;
  if ( a3 )
  {
    v5 = *((_OWORD *)a3 + 1);
    *((_QWORD *)this + 6) = v3;
    *v3 = v5;
  }
  v6 = InputTraceLogging::Provider();
  if ( *(_DWORD *)v6 > 6u && (*((_QWORD *)v6 + 2) & 1) != 0 && (*((_QWORD *)v6 + 3) & 1LL) == *((_QWORD *)v6 + 3) )
  {
    *(_BYTE *)this = 1;
    EventActivityIdControl(3u, (LPGUID)this + 1);
    *(_QWORD *)&Context.Id = 0;
    fPending = 0;
    if ( InitOnceBeginInitialize(&`InputTraceLogging::Instance'::`2'::wrapper, 0, &fPending, (LPVOID *)&Context)
      && fPending )
    {
      qword_1803BB198 = 0;
      *(_QWORD *)&Context.Id = &qword_1803BB190;
      byte_1803BB1A0 = 0;
      dword_1803BB1A4 = 0;
      qword_1803BB190 = &wil::details::FeatureLogging::`vftable';
      CallbackContext = &`InputTraceLogging::StaticHandle::StaticHandle'::`2'::__hInner;
      atexit(`InputTraceLogging::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
      qword_1803BB198 = (__int64)CallbackContext;
      byte_1803BB1A0 = 1;
      TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
      dword_1803BB1A4 = 1;
      (*(void (__fastcall **)(void *))(qword_1803BB190 + 8LL))(&qword_1803BB190);
      InitOnceComplete(&`InputTraceLogging::Instance'::`2'::wrapper, 0, &qword_1803BB190);
    }
    v7 = *(_QWORD *)(*(_QWORD *)&Context.Id + 8LL);
    if ( *(_DWORD *)v7 > 6u && (*(_QWORD *)(v7 + 16) & 1) != 0 && (*(_QWORD *)(v7 + 24) & 1LL) == *(_QWORD *)(v7 + 24) )
    {
      v8 = (const char *)*((_QWORD *)this + 1);
      v9 = (const GUID *)*((_QWORD *)this + 6);
      if ( v8 )
      {
        v10 = -1;
        do
          ++v10;
        while ( v8[v10] );
        v11 = v10 + 1;
      }
      else
      {
        v8 = word_1802D2E32;
        v11 = 1;
      }
      v20 = v11;
      UserData.Ptr = *(_QWORD *)(v7 + 8);
      v19 = v8;
      v21 = 0;
      *(_QWORD *)&Context.Id = 0x1060B000000LL;
      Context.Keyword = 1;
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      v16 = byte_18038EC1D;
      UserData.Reserved = 2;
      v17 = 19;
      v18 = 1;
      fPending = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(*(_QWORD *)(v7 + 32), &Context, (LPCGUID)this + 1, v9, 3u, &UserData);
    }
  }
  return this;
}

```

## disassembly

```asm
0x180112110  mov     [rsp+arg_10], rbx
0x180112115  mov     [rsp+arg_18], rbp
0x18011211a  push    rdi
0x18011211b  sub     rsp, 80h
0x180112122  mov     rax, cs:__security_cookie
0x180112129  xor     rax, rsp
0x18011212c  mov     [rsp+88h+var_10], rax
0x180112131  mov     byte ptr [rcx], 0
0x180112134  lea     rax, [rcx+20h]
0x180112138  mov     [rcx+8], rdx
0x18011213c  xor     ebp, ebp
0x18011213e  xorps   xmm0, xmm0
0x180112141  xorps   xmm1, xmm1
0x180112144  mov     rbx, rcx
0x180112147  movups  xmmword ptr [rcx+10h], xmm0
0x18011214b  movups  xmmword ptr [rax], xmm1
0x18011214e  mov     [rcx+30h], rbp
0x180112152  test    r8, r8
0x180112155  jz      short loc_180112163
0x180112157  movups  xmm0, xmmword ptr [r8+10h]
0x18011215c  mov     [rcx+30h], rax
0x180112160  movups  xmmword ptr [rax], xmm0
0x180112163  call    ?Provider@InputTraceLogging@@SAPEBU_tlgProvider_t@@XZ; InputTraceLogging::Provider(void)
0x180112168  mov     rcx, rax
0x18011216b  mov     eax, [rax]
0x18011216d  cmp     eax, 6
0x180112170  jbe     loc_180112377
0x180112176  mov     rdx, [rcx+18h]
0x18011217a  mov     rax, [rcx+10h]
0x18011217e  test    al, 1
0x180112180  jz      loc_180112377
0x180112186  mov     rax, rdx
0x180112189  and     eax, 1
0x18011218c  cmp     rax, rdx
0x18011218f  jnz     loc_180112377
0x180112195  lea     rdx, [rbx+10h]; ActivityId
0x180112199  mov     byte ptr [rbx], 1
0x18011219c  mov     ecx, 3; ControlCode
0x1801121a1  call    cs:__imp_EventActivityIdControl
0x1801121a7  lea     r9, [rsp+88h+Context]; lpContext
0x1801121ac  mov     [rsp+88h+Context], rbp
0x1801121b1  lea     r8, [rsp+88h+fPending]; fPending
0x1801121b6  mov     [rsp+88h+fPending], ebp
0x1801121ba  xor     edx, edx; dwFlags
0x1801121bc  lea     rcx, ?wrapper@?1??Instance@InputTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VInputTraceLogging@@@details@wil@@A; lpInitOnce
0x1801121c3  call    cs:__imp_InitOnceBeginInitialize
0x1801121c9  test    eax, eax
0x1801121cb  jz      loc_18011227C
0x1801121d1  cmp     [rsp+88h+fPending], ebp
0x1801121d5  jz      loc_18011227C
0x1801121db  mov     [rsp+88h+arg_8], rsi
0x1801121e3  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x1801121ea  lea     rsi, qword_1803BB190
0x1801121f1  mov     cs:qword_1803BB198, rbp
0x1801121f8  mov     [rsp+88h+Context], rsi
0x1801121fd  mov     cs:byte_1803BB1A0, bpl
0x180112204  mov     cs:dword_1803BB1A4, ebp
0x18011220a  mov     cs:qword_1803BB190, rax
0x180112211  lea     rax, ?__hInner@?1???0StaticHandle@InputTraceLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `InputTraceLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180112218  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@InputTraceLogging@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x18011221f  mov     cs:CallbackContext, rax
0x180112226  call    atexit
0x18011222b  mov     rcx, cs:CallbackContext; CallbackContext
0x180112232  mov     cs:qword_1803BB198, rcx
0x180112239  mov     cs:byte_1803BB1A0, 1
0x180112240  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180112245  mov     rax, cs:qword_1803BB190
0x18011224c  mov     rcx, rsi
0x18011224f  mov     cs:dword_1803BB1A4, 1
0x180112259  mov     rax, [rax+8]
0x18011225d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180112262  mov     r8, rsi; lpContext
0x180112265  lea     rcx, ?wrapper@?1??Instance@InputTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VInputTraceLogging@@@details@wil@@A; lpInitOnce
0x18011226c  xor     edx, edx; dwFlags
0x18011226e  call    cs:__imp_InitOnceComplete
0x180112274  mov     rsi, [rsp+88h+arg_8]
0x18011227c  mov     rax, [rsp+88h+Context]
0x180112281  mov     r10, [rax+8]
0x180112285  mov     eax, [r10]
0x180112288  cmp     eax, 6
0x18011228b  jbe     loc_180112377
0x180112291  mov     rcx, [r10+18h]
0x180112295  mov     rax, [r10+10h]
0x180112299  test    al, 1
0x18011229b  jz      loc_180112377
0x1801122a1  mov     rax, rcx
0x1801122a4  and     eax, 1
0x1801122a7  cmp     rax, rcx
0x1801122aa  jnz     loc_180112377
0x1801122b0  mov     rcx, [rbx+8]
0x1801122b4  mov     r9, [rbx+30h]; RelatedActivityId
0x1801122b8  test    rcx, rcx
0x1801122bb  jz      short loc_1801122D1
0x1801122bd  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1801122c4  inc     rax
0x1801122c7  cmp     [rcx+rax], bpl
0x1801122cb  jnz     short loc_1801122C4
0x1801122cd  inc     eax
0x1801122cf  jmp     short loc_1801122DD
0x1801122d1  lea     rcx, word_1802D2E32
0x1801122d8  mov     eax, 1
0x1801122dd  mov     [rsp+88h+var_18], eax
0x1801122e1  lea     rdx, _TraceLoggingMetadataEnd
0x1801122e8  movzx   eax, cs:word_18038EC13
0x1801122ef  lea     r8, [rbx+10h]; ActivityId
0x1801122f3  mov     dword ptr [rsp+88h+Context+4], eax
0x1801122f7  mov     rax, [r10+8]
0x1801122fb  mov     [rsp+88h+var_40.Ptr], rax
0x180112300  mov     [rsp+88h+var_20], rcx
0x180112305  mov     [rsp+88h+var_14], ebp
0x180112309  mov     dword ptr [rsp+88h+Context], 0B000000h
0x180112311  mov     [rsp+88h+var_48], 1
0x18011231a  movzx   eax, word ptr [rax]
0x18011231d  mov     [rsp+88h+var_40.Size], eax
0x180112321  lea     rax, byte_18038EC1D
0x180112328  mov     [rsp+88h+var_30], rax
0x18011232d  lea     rax, _TraceLoggingMetadata
0x180112334  sub     edx, eax
0x180112336  mov     dword ptr [rsp+88h+var_40.0Ch], 2
0x18011233e  mov     [rsp+88h+var_28], 13h
0x180112346  lea     rax, [rsp+88h+var_40]
0x18011234b  mov     [rsp+88h+var_24], 1
0x180112353  mov     [rsp+88h+fPending], edx
0x180112357  mov     edx, [rsp+88h+fPending]
0x18011235b  mov     rcx, [r10+20h]; RegHandle
0x18011235f  lea     rdx, [rsp+88h+Context]; EventDescriptor
0x180112364  mov     [rsp+88h+UserData], rax; UserData
0x180112369  mov     [rsp+88h+UserDataCount], 3; UserDataCount
0x180112371  call    cs:__imp_EventWriteTransfer
0x180112377  mov     rax, rbx
0x18011237a  mov     rcx, [rsp+88h+var_10]
0x18011237f  xor     rcx, rsp; StackCookie
0x180112382  call    __security_check_cookie
0x180112387  lea     r11, [rsp+88h+var_8]
0x18011238f  mov     rbx, [r11+20h]
0x180112393  mov     rbp, [r11+28h]
0x180112397  mov     rsp, r11
0x18011239a  pop     rdi
0x18011239b  retn
```
