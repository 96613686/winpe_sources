# InputTraceLogging::PerfRegion::PerfRegion(char const *,InputTraceLogging::PerfRegion const *)

- ea: `0x1800163b0`
- end: `0x18001664a`
- name: `??0PerfRegion@InputTraceLogging@@QEAA@PEBDPEBU01@@Z`
- size: `666`
- prototype: `__int64 __fastcall(InputTraceLogging::PerfRegion *__hidden this, const char *, const struct InputTraceLogging::PerfRegion *)`
- caller_count: `38`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000dd00`
- `0x180013f64`
- `0x1800150f0`
- `0x180015b50`
- `0x18001bf10`
- `0x18002cfc0`
- `0x18002f360`
- `0x180031270`
- `0x1800312e0`
- `0x18003134c`
- `0x18004b990`
- `0x1800587f0`
- `0x1800588b0`
- `0x180058960`
- `0x180058a20`
- `0x180058ad0`
- `0x180058b90`
- `0x180058c40`
- `0x180058cf0`
- `0x180058da0`
- `0x180058e50`
- `0x180058f00`
- `0x180058fc0`
- `0x180059070`
- `0x18006aff0`
- `0x180076fa0`
- `0x18012e3a8`
- `0x18012f300`
- `0x18012f3c0`
- `0x18012f420`
- `0x18012f4f0`
- `0x18012f560`
- `0x18012f8e0`
- `0x18012f990`
- `0x18012fa50`
- `0x18012fb10`
- `0x18012fbc0`
- `0x1801725f0`

## callees

- `0x1800163b0`
- `0x18003e7a0`
- `0x18003e8e0`
- `0x1800f0354`
- `0x1800f0990`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001651c`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001651c`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180016463`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180016463`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180016441`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180016441`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001661f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001661f`

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
  const unsigned __int16 *v8; // rcx
  const GUID *v9; // r9
  __int64 v10; // rax
  int v11; // eax
  WINBOOL fPending; // [rsp+30h] [rbp-58h] BYREF
  EVENT_DESCRIPTOR Context; // [rsp+38h] [rbp-50h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+48h] [rbp-40h] BYREF
  __int16 *v16; // [rsp+58h] [rbp-30h]
  int v17; // [rsp+60h] [rbp-28h]
  int v18; // [rsp+64h] [rbp-24h]
  const unsigned __int16 *v19; // [rsp+68h] [rbp-20h]
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
    if ( __std_init_once_begin_initialize(
           &`InputTraceLogging::Instance'::`2'::wrapper,
           0,
           &fPending,
           (LPVOID *)&Context)
      && fPending )
    {
      qword_180243F80 = 0;
      *(_QWORD *)&Context.Id = &qword_180243F78;
      byte_180243F88 = 0;
      dword_180243F8C = 0;
      qword_180243F78 = &RawInputProvidersContinuousTracing::`vftable';
      CallbackContext = &`InputTraceLogging::StaticHandle::StaticHandle'::`2'::__hInner;
      atexit(_lambda_a8e7baa2fca040c17c3e795f3590cb07_::_lambda_invoker_cdecl_);
      qword_180243F80 = (__int64)CallbackContext;
      byte_180243F88 = 1;
      TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
      dword_180243F8C = 1;
      (*(void (__fastcall **)(void *))(qword_180243F78 + 8LL))(&qword_180243F78);
      InputTraceLogging::s_registered = 1;
      InitOnceComplete(&`InputTraceLogging::Instance'::`2'::wrapper, 0, &qword_180243F78);
    }
    v7 = *(_QWORD *)(*(_QWORD *)&Context.Id + 8LL);
    if ( *(_DWORD *)v7 > 6u && (*(_QWORD *)(v7 + 16) & 1) != 0 && (*(_QWORD *)(v7 + 24) & 1LL) == *(_QWORD *)(v7 + 24) )
    {
      v8 = (const unsigned __int16 *)*((_QWORD *)this + 1);
      v9 = (const GUID *)*((_QWORD *)this + 6);
      if ( v8 )
      {
        v10 = -1;
        do
          ++v10;
        while ( *((_BYTE *)v8 + v10) );
        v11 = v10 + 1;
      }
      else
      {
        v8 = &qword_1801F0710;
        v11 = 1;
      }
      v20 = v11;
      UserData.Ptr = *(_QWORD *)(v7 + 8);
      v19 = v8;
      v21 = 0;
      *(_QWORD *)&Context.Id = 0x1060B000000LL;
      Context.Keyword = 1;
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      v16 = &word_180203326;
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
0x1800163b0  mov     [rsp+arg_10], rbx
0x1800163b5  mov     [rsp+arg_18], rbp
0x1800163ba  push    rdi
0x1800163bb  sub     rsp, 80h
0x1800163c2  mov     rax, cs:__security_cookie
0x1800163c9  xor     rax, rsp
0x1800163cc  mov     [rsp+88h+var_10], rax
0x1800163d1  mov     byte ptr [rcx], 0
0x1800163d4  lea     rax, [rcx+20h]
0x1800163d8  mov     [rcx+8], rdx
0x1800163dc  xor     ebp, ebp
0x1800163de  xorps   xmm0, xmm0
0x1800163e1  xorps   xmm1, xmm1
0x1800163e4  mov     rbx, rcx
0x1800163e7  movups  xmmword ptr [rcx+10h], xmm0
0x1800163eb  movups  xmmword ptr [rax], xmm1
0x1800163ee  mov     [rcx+30h], rbp
0x1800163f2  test    r8, r8
0x1800163f5  jz      short loc_180016403
0x1800163f7  movups  xmm0, xmmword ptr [r8+10h]
0x1800163fc  mov     [rcx+30h], rax
0x180016400  movups  xmmword ptr [rax], xmm0
0x180016403  call    ?Provider@InputTraceLogging@@SAPEBU_tlgProvider_t@@XZ; InputTraceLogging::Provider(void)
0x180016408  mov     rcx, rax
0x18001640b  mov     eax, [rax]
0x18001640d  cmp     eax, 6
0x180016410  jbe     loc_180016625
0x180016416  mov     rdx, [rcx+18h]
0x18001641a  mov     rax, [rcx+10h]
0x18001641e  test    al, 1
0x180016420  jz      loc_180016625
0x180016426  mov     rax, rdx
0x180016429  and     eax, 1
0x18001642c  cmp     rax, rdx
0x18001642f  jnz     loc_180016625
0x180016435  lea     rdx, [rbx+10h]; ActivityId
0x180016439  mov     byte ptr [rbx], 1
0x18001643c  mov     ecx, 3; ControlCode
0x180016441  call    cs:__imp_EventActivityIdControl
0x180016447  lea     r9, [rsp+88h+Context]; lpContext
0x18001644c  mov     [rsp+88h+Context], rbp
0x180016451  lea     r8, [rsp+88h+fPending]; fPending
0x180016456  mov     [rsp+88h+fPending], ebp
0x18001645a  xor     edx, edx; dwFlags
0x18001645c  lea     rcx, ?wrapper@?1??Instance@InputTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VInputTraceLogging@@@details@wil@@A; lpInitOnce
0x180016463  call    cs:__imp___std_init_once_begin_initialize
0x180016469  test    eax, eax
0x18001646b  jz      loc_18001652A
0x180016471  cmp     [rsp+88h+fPending], ebp
0x180016475  jz      loc_18001652A
0x18001647b  mov     [rsp+88h+arg_8], rsi
0x180016483  lea     rax, ??_7RawInputProvidersContinuousTracing@@6B@; const RawInputProvidersContinuousTracing::`vftable'
0x18001648a  lea     rsi, qword_180243F78
0x180016491  mov     cs:qword_180243F80, rbp
0x180016498  mov     [rsp+88h+Context], rsi
0x18001649d  mov     cs:byte_180243F88, bpl
0x1800164a4  mov     cs:dword_180243F8C, ebp
0x1800164aa  mov     cs:qword_180243F78, rax
0x1800164b1  lea     rax, ?__hInner@?1???0StaticHandle@InputTraceLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `InputTraceLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1800164b8  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_a8e7baa2fca040c17c3e795f3590cb07_@@CA@XZ; void (__cdecl *)()
0x1800164bf  mov     cs:CallbackContext, rax
0x1800164c6  call    atexit
0x1800164cb  mov     rcx, cs:CallbackContext; CallbackContext
0x1800164d2  lea     rdx, ?Callback@InputTraceLogging@@CAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; InputTraceLogging::Callback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x1800164d9  mov     cs:qword_180243F80, rcx
0x1800164e0  mov     cs:byte_180243F88, 1
0x1800164e7  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1800164ec  mov     rax, cs:qword_180243F78
0x1800164f3  mov     rcx, rsi
0x1800164f6  mov     cs:dword_180243F8C, 1
0x180016500  mov     rax, [rax+8]
0x180016504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016509  mov     r8, rsi; lpContext
0x18001650c  mov     cs:?s_registered@InputTraceLogging@@0_NA, 1; bool InputTraceLogging::s_registered
0x180016513  xor     edx, edx; dwFlags
0x180016515  lea     rcx, ?wrapper@?1??Instance@InputTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VInputTraceLogging@@@details@wil@@A; lpInitOnce
0x18001651c  call    cs:__imp_InitOnceComplete
0x180016522  mov     rsi, [rsp+88h+arg_8]
0x18001652a  mov     rax, [rsp+88h+Context]
0x18001652f  mov     r10, [rax+8]
0x180016533  mov     eax, [r10]
0x180016536  cmp     eax, 6
0x180016539  jbe     loc_180016625
0x18001653f  mov     rcx, [r10+18h]
0x180016543  mov     rax, [r10+10h]
0x180016547  test    al, 1
0x180016549  jz      loc_180016625
0x18001654f  mov     rax, rcx
0x180016552  and     eax, 1
0x180016555  cmp     rax, rcx
0x180016558  jnz     loc_180016625
0x18001655e  mov     rcx, [rbx+8]
0x180016562  mov     r9, [rbx+30h]; RelatedActivityId
0x180016566  test    rcx, rcx
0x180016569  jz      short loc_18001657F
0x18001656b  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180016572  inc     rax
0x180016575  cmp     [rcx+rax], bpl
0x180016579  jnz     short loc_180016572
0x18001657b  inc     eax
0x18001657d  jmp     short loc_18001658B
0x18001657f  lea     rcx, qword_1801F0710
0x180016586  mov     eax, 1
0x18001658b  mov     [rsp+88h+var_18], eax
0x18001658f  lea     rdx, _TraceLoggingMetadataEnd
0x180016596  movzx   eax, cs:word_18020331C
0x18001659d  lea     r8, [rbx+10h]; ActivityId
0x1800165a1  mov     dword ptr [rsp+88h+Context+4], eax
0x1800165a5  mov     rax, [r10+8]
0x1800165a9  mov     [rsp+88h+var_40.Ptr], rax
0x1800165ae  mov     [rsp+88h+var_20], rcx
0x1800165b3  mov     [rsp+88h+var_14], ebp
0x1800165b7  mov     dword ptr [rsp+88h+Context], 0B000000h
0x1800165bf  mov     [rsp+88h+var_48], 1
0x1800165c8  movzx   eax, word ptr [rax]
0x1800165cb  mov     [rsp+88h+var_40.Size], eax
0x1800165cf  lea     rax, word_180203326
0x1800165d6  mov     [rsp+88h+var_30], rax
0x1800165db  lea     rax, _TraceLoggingMetadata
0x1800165e2  sub     edx, eax
0x1800165e4  mov     dword ptr [rsp+88h+var_40.0Ch], 2
0x1800165ec  mov     [rsp+88h+var_28], 13h
0x1800165f4  lea     rax, [rsp+88h+var_40]
0x1800165f9  mov     [rsp+88h+var_24], 1
0x180016601  mov     [rsp+88h+fPending], edx
0x180016605  mov     edx, [rsp+88h+fPending]
0x180016609  mov     rcx, [r10+20h]; RegHandle
0x18001660d  lea     rdx, [rsp+88h+Context]; EventDescriptor
0x180016612  mov     [rsp+88h+UserData], rax; UserData
0x180016617  mov     [rsp+88h+UserDataCount], 3; UserDataCount
0x18001661f  call    cs:__imp_EventWriteTransfer
0x180016625  mov     rax, rbx
0x180016628  mov     rcx, [rsp+88h+var_10]
0x18001662d  xor     rcx, rsp; StackCookie
0x180016630  call    __security_check_cookie
0x180016635  lea     r11, [rsp+88h+var_8]
0x18001663d  mov     rbx, [r11+20h]
0x180016641  mov     rbp, [r11+28h]
0x180016645  mov     rsp, r11
0x180016648  pop     rdi
0x180016649  retn
```
