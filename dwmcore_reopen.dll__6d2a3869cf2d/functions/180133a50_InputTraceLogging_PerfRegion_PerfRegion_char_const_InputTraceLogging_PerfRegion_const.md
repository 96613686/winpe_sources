# InputTraceLogging::PerfRegion::PerfRegion(char const *,InputTraceLogging::PerfRegion const *)

- ea: `0x180133a50`
- end: `0x180133cdc`
- name: `??0PerfRegion@InputTraceLogging@@QEAA@PEBDPEBU01@@Z`
- size: `652`
- prototype: `__int64 __fastcall(InputTraceLogging::PerfRegion *__hidden this, const char *, const struct InputTraceLogging::PerfRegion *)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180133290`
- `0x18013508c`
- `0x180135260`
- `0x18018a9e8`

## callees

- `0x180133a50`
- `0x18017c1a0`
- `0x18017c2dc`
- `0x1802284b0`
- `0x180228860`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180133b03`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180133b03`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180133bae`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180133bae`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180133cb1`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180133cb1`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180133ae1`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180133ae1`

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
  void *v16; // [rsp+58h] [rbp-30h]
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
      qword_1803BB188 = 0;
      *(_QWORD *)&Context.Id = &qword_1803BB180;
      byte_1803BB190 = 0;
      dword_1803BB194 = 0;
      qword_1803BB180 = &wil::details::FeatureLogging::`vftable';
      CallbackContext = &`InputTraceLogging::StaticHandle::StaticHandle'::`2'::__hInner;
      atexit(`InputTraceLogging::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
      qword_1803BB188 = (__int64)CallbackContext;
      byte_1803BB190 = 1;
      TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
      dword_1803BB194 = 1;
      (*(void (__fastcall **)(void *))(qword_1803BB180 + 8LL))(&qword_1803BB180);
      InitOnceComplete(&`InputTraceLogging::Instance'::`2'::wrapper, 0, &qword_1803BB180);
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
        v8 = word_1802D21E2;
        v11 = 1;
      }
      v20 = v11;
      UserData.Ptr = *(_QWORD *)(v7 + 8);
      v19 = v8;
      v21 = 0;
      *(_QWORD *)&Context.Id = 0x1060B000000LL;
      Context.Keyword = 1;
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      v16 = &unk_18038FA2D;
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
0x180133a50  mov     [rsp+arg_10], rbx
0x180133a55  mov     [rsp+arg_18], rbp
0x180133a5a  push    rdi
0x180133a5b  sub     rsp, 80h
0x180133a62  mov     rax, cs:__security_cookie
0x180133a69  xor     rax, rsp
0x180133a6c  mov     [rsp+88h+var_10], rax
0x180133a71  mov     byte ptr [rcx], 0
0x180133a74  lea     rax, [rcx+20h]
0x180133a78  mov     [rcx+8], rdx
0x180133a7c  xor     ebp, ebp
0x180133a7e  xorps   xmm0, xmm0
0x180133a81  xorps   xmm1, xmm1
0x180133a84  mov     rbx, rcx
0x180133a87  movups  xmmword ptr [rcx+10h], xmm0
0x180133a8b  movups  xmmword ptr [rax], xmm1
0x180133a8e  mov     [rcx+30h], rbp
0x180133a92  test    r8, r8
0x180133a95  jz      short loc_180133AA3
0x180133a97  movups  xmm0, xmmword ptr [r8+10h]
0x180133a9c  mov     [rcx+30h], rax
0x180133aa0  movups  xmmword ptr [rax], xmm0
0x180133aa3  call    ?Provider@InputTraceLogging@@SAPEBU_tlgProvider_t@@XZ; InputTraceLogging::Provider(void)
0x180133aa8  mov     rcx, rax
0x180133aab  mov     eax, [rax]
0x180133aad  cmp     eax, 6
0x180133ab0  jbe     loc_180133CB7
0x180133ab6  mov     rdx, [rcx+18h]
0x180133aba  mov     rax, [rcx+10h]
0x180133abe  test    al, 1
0x180133ac0  jz      loc_180133CB7
0x180133ac6  mov     rax, rdx
0x180133ac9  and     eax, 1
0x180133acc  cmp     rax, rdx
0x180133acf  jnz     loc_180133CB7
0x180133ad5  lea     rdx, [rbx+10h]; ActivityId
0x180133ad9  mov     byte ptr [rbx], 1
0x180133adc  mov     ecx, 3; ControlCode
0x180133ae1  call    cs:__imp_EventActivityIdControl
0x180133ae7  lea     r9, [rsp+88h+Context]; lpContext
0x180133aec  mov     [rsp+88h+Context], rbp
0x180133af1  lea     r8, [rsp+88h+fPending]; fPending
0x180133af6  mov     [rsp+88h+fPending], ebp
0x180133afa  xor     edx, edx; dwFlags
0x180133afc  lea     rcx, ?wrapper@?1??Instance@InputTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VInputTraceLogging@@@details@wil@@A; lpInitOnce
0x180133b03  call    cs:__imp_InitOnceBeginInitialize
0x180133b09  test    eax, eax
0x180133b0b  jz      loc_180133BBC
0x180133b11  cmp     [rsp+88h+fPending], ebp
0x180133b15  jz      loc_180133BBC
0x180133b1b  mov     [rsp+88h+arg_8], rsi
0x180133b23  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x180133b2a  lea     rsi, qword_1803BB180
0x180133b31  mov     cs:qword_1803BB188, rbp
0x180133b38  mov     [rsp+88h+Context], rsi
0x180133b3d  mov     cs:byte_1803BB190, bpl
0x180133b44  mov     cs:dword_1803BB194, ebp
0x180133b4a  mov     cs:qword_1803BB180, rax
0x180133b51  lea     rax, ?__hInner@?1???0StaticHandle@InputTraceLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `InputTraceLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180133b58  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@InputTraceLogging@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x180133b5f  mov     cs:CallbackContext, rax
0x180133b66  call    atexit
0x180133b6b  mov     rcx, cs:CallbackContext; CallbackContext
0x180133b72  mov     cs:qword_1803BB188, rcx
0x180133b79  mov     cs:byte_1803BB190, 1
0x180133b80  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180133b85  mov     rax, cs:qword_1803BB180
0x180133b8c  mov     rcx, rsi
0x180133b8f  mov     cs:dword_1803BB194, 1
0x180133b99  mov     rax, [rax+8]
0x180133b9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180133ba2  mov     r8, rsi; lpContext
0x180133ba5  lea     rcx, ?wrapper@?1??Instance@InputTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VInputTraceLogging@@@details@wil@@A; lpInitOnce
0x180133bac  xor     edx, edx; dwFlags
0x180133bae  call    cs:__imp_InitOnceComplete
0x180133bb4  mov     rsi, [rsp+88h+arg_8]
0x180133bbc  mov     rax, [rsp+88h+Context]
0x180133bc1  mov     r10, [rax+8]
0x180133bc5  mov     eax, [r10]
0x180133bc8  cmp     eax, 6
0x180133bcb  jbe     loc_180133CB7
0x180133bd1  mov     rcx, [r10+18h]
0x180133bd5  mov     rax, [r10+10h]
0x180133bd9  test    al, 1
0x180133bdb  jz      loc_180133CB7
0x180133be1  mov     rax, rcx
0x180133be4  and     eax, 1
0x180133be7  cmp     rax, rcx
0x180133bea  jnz     loc_180133CB7
0x180133bf0  mov     rcx, [rbx+8]
0x180133bf4  mov     r9, [rbx+30h]; RelatedActivityId
0x180133bf8  test    rcx, rcx
0x180133bfb  jz      short loc_180133C11
0x180133bfd  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180133c04  inc     rax
0x180133c07  cmp     [rcx+rax], bpl
0x180133c0b  jnz     short loc_180133C04
0x180133c0d  inc     eax
0x180133c0f  jmp     short loc_180133C1D
0x180133c11  lea     rcx, word_1802D21E2
0x180133c18  mov     eax, 1
0x180133c1d  mov     [rsp+88h+var_18], eax
0x180133c21  lea     rdx, _TraceLoggingMetadataEnd
0x180133c28  movzx   eax, cs:word_18038FA23
0x180133c2f  lea     r8, [rbx+10h]; ActivityId
0x180133c33  mov     dword ptr [rsp+88h+Context+4], eax
0x180133c37  mov     rax, [r10+8]
0x180133c3b  mov     [rsp+88h+var_40.Ptr], rax
0x180133c40  mov     [rsp+88h+var_20], rcx
0x180133c45  mov     [rsp+88h+var_14], ebp
0x180133c49  mov     dword ptr [rsp+88h+Context], 0B000000h
0x180133c51  mov     [rsp+88h+var_48], 1
0x180133c5a  movzx   eax, word ptr [rax]
0x180133c5d  mov     [rsp+88h+var_40.Size], eax
0x180133c61  lea     rax, unk_18038FA2D
0x180133c68  mov     [rsp+88h+var_30], rax
0x180133c6d  lea     rax, _TraceLoggingMetadata
0x180133c74  sub     edx, eax
0x180133c76  mov     dword ptr [rsp+88h+var_40.0Ch], 2
0x180133c7e  mov     [rsp+88h+var_28], 13h
0x180133c86  lea     rax, [rsp+88h+var_40]
0x180133c8b  mov     [rsp+88h+var_24], 1
0x180133c93  mov     [rsp+88h+fPending], edx
0x180133c97  mov     edx, [rsp+88h+fPending]
0x180133c9b  mov     rcx, [r10+20h]; RegHandle
0x180133c9f  lea     rdx, [rsp+88h+Context]; EventDescriptor
0x180133ca4  mov     [rsp+88h+UserData], rax; UserData
0x180133ca9  mov     [rsp+88h+UserDataCount], 3; UserDataCount
0x180133cb1  call    cs:__imp_EventWriteTransfer
0x180133cb7  mov     rax, rbx
0x180133cba  mov     rcx, [rsp+88h+var_10]
0x180133cbf  xor     rcx, rsp; StackCookie
0x180133cc2  call    __security_check_cookie
0x180133cc7  lea     r11, [rsp+88h+var_8]
0x180133ccf  mov     rbx, [r11+20h]
0x180133cd3  mov     rbp, [r11+28h]
0x180133cd7  mov     rsp, r11
0x180133cda  pop     rdi
0x180133cdb  retn
```
