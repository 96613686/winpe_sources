# InputTraceLogging::PerfRegion::~PerfRegion(void)

- ea: `0x180016180`
- end: `0x1800163a5`
- name: `??1PerfRegion@InputTraceLogging@@QEAA@XZ`
- size: `549`
- prototype: `void __fastcall(InputTraceLogging::PerfRegion *__hidden this)`
- caller_count: `43`
- callee_count: `5`
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
- `0x1801c433d`
- `0x1801c4900`
- `0x1801c4940`
- `0x1801c49f0`
- `0x1801c70a1`

## callees

- `0x180016180`
- `0x18003e8e0`
- `0x1800f0354`
- `0x1800f0990`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001627e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001627e`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800161c5`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800161c5`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180016381`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180016381`

## pseudocode

```c
void __fastcall InputTraceLogging::PerfRegion::~PerfRegion(InputTraceLogging::PerfRegion *this)
{
  __int64 v2; // r10
  const unsigned __int16 *v3; // rcx
  const GUID *v4; // r9
  __int64 v5; // rax
  int v6; // eax
  unsigned int v7; // [rsp+30h] [rbp-58h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-50h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+48h] [rbp-40h] BYREF
  char *v10; // [rsp+58h] [rbp-30h]
  int v11; // [rsp+60h] [rbp-28h]
  int v12; // [rsp+64h] [rbp-24h]
  const unsigned __int16 *v13; // [rsp+68h] [rbp-20h]
  int v14; // [rsp+70h] [rbp-18h]
  int v15; // [rsp+74h] [rbp-14h]

  if ( *(_BYTE *)this )
  {
    *(_QWORD *)&EventDescriptor.Id = 0;
    v7 = 0;
    if ( __std_init_once_begin_initialize(
           &`InputTraceLogging::Instance'::`2'::wrapper,
           0,
           (PBOOL)&v7,
           (LPVOID *)&EventDescriptor)
      && v7 )
    {
      qword_180243F80 = 0;
      *(_QWORD *)&EventDescriptor.Id = &qword_180243F78;
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
    v2 = *(_QWORD *)(*(_QWORD *)&EventDescriptor.Id + 8LL);
    if ( *(_DWORD *)v2 > 6u && (*(_QWORD *)(v2 + 16) & 1) != 0 && (*(_QWORD *)(v2 + 24) & 1LL) == *(_QWORD *)(v2 + 24) )
    {
      v3 = (const unsigned __int16 *)*((_QWORD *)this + 1);
      v4 = (const GUID *)*((_QWORD *)this + 6);
      if ( v3 )
      {
        v5 = -1;
        do
          ++v5;
        while ( *((_BYTE *)v3 + v5) );
        v6 = v5 + 1;
      }
      else
      {
        v3 = &qword_1801F0710;
        v6 = 1;
      }
      v14 = v6;
      *(_DWORD *)&EventDescriptor.Level = 518;
      UserData.Ptr = *(_QWORD *)(v2 + 8);
      v13 = v3;
      v15 = 0;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 1;
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      v10 = byte_1802032D3;
      UserData.Reserved = 2;
      v11 = 19;
      v12 = 1;
      v7 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(*(_QWORD *)(v2 + 32), &EventDescriptor, (LPCGUID)this + 1, v4, 3u, &UserData);
    }
  }
}

```

## disassembly

```asm
0x180016180  mov     r11, rsp
0x180016183  push    rbx
0x180016184  sub     rsp, 80h
0x18001618b  mov     rax, cs:__security_cookie
0x180016192  xor     rax, rsp
0x180016195  mov     [rsp+88h+var_10], rax
0x18001619a  cmp     byte ptr [rcx], 0
0x18001619d  mov     rbx, rcx
0x1800161a0  jz      loc_18001638F
0x1800161a6  mov     [r11+10h], rsi
0x1800161aa  lea     r9, [r11-50h]; lpContext
0x1800161ae  xor     esi, esi
0x1800161b0  lea     r8, [r11-58h]; fPending
0x1800161b4  xor     edx, edx; dwFlags
0x1800161b6  mov     [r11-50h], rsi
0x1800161ba  lea     rcx, ?wrapper@?1??Instance@InputTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VInputTraceLogging@@@details@wil@@A; lpInitOnce
0x1800161c1  mov     [rsp+88h+var_58], esi
0x1800161c5  call    cs:__imp___std_init_once_begin_initialize
0x1800161cb  test    eax, eax
0x1800161cd  jz      loc_18001628C
0x1800161d3  cmp     [rsp+88h+var_58], esi
0x1800161d7  jz      loc_18001628C
0x1800161dd  mov     [rsp+88h+arg_10], rdi
0x1800161e5  lea     rax, ??_7RawInputProvidersContinuousTracing@@6B@; const RawInputProvidersContinuousTracing::`vftable'
0x1800161ec  lea     rdi, qword_180243F78
0x1800161f3  mov     cs:qword_180243F80, rsi
0x1800161fa  mov     qword ptr [rsp+88h+EventDescriptor.Id], rdi
0x1800161ff  mov     cs:byte_180243F88, sil
0x180016206  mov     cs:dword_180243F8C, esi
0x18001620c  mov     cs:qword_180243F78, rax
0x180016213  lea     rax, ?__hInner@?1???0StaticHandle@InputTraceLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `InputTraceLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18001621a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_a8e7baa2fca040c17c3e795f3590cb07_@@CA@XZ; void (__cdecl *)()
0x180016221  mov     cs:CallbackContext, rax
0x180016228  call    atexit
0x18001622d  mov     rcx, cs:CallbackContext; CallbackContext
0x180016234  lea     rdx, ?Callback@InputTraceLogging@@CAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; InputTraceLogging::Callback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x18001623b  mov     cs:qword_180243F80, rcx
0x180016242  mov     cs:byte_180243F88, 1
0x180016249  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18001624e  mov     rax, cs:qword_180243F78
0x180016255  mov     rcx, rdi
0x180016258  mov     cs:dword_180243F8C, 1
0x180016262  mov     rax, [rax+8]
0x180016266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001626b  mov     r8, rdi; lpContext
0x18001626e  mov     cs:?s_registered@InputTraceLogging@@0_NA, 1; bool InputTraceLogging::s_registered
0x180016275  xor     edx, edx; dwFlags
0x180016277  lea     rcx, ?wrapper@?1??Instance@InputTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VInputTraceLogging@@@details@wil@@A; lpInitOnce
0x18001627e  call    cs:__imp_InitOnceComplete
0x180016284  mov     rdi, [rsp+88h+arg_10]
0x18001628c  mov     rax, qword ptr [rsp+88h+EventDescriptor.Id]
0x180016291  mov     r10, [rax+8]
0x180016295  mov     eax, [r10]
0x180016298  cmp     eax, 6
0x18001629b  jbe     loc_180016387
0x1800162a1  mov     rcx, [r10+18h]
0x1800162a5  mov     rax, [r10+10h]
0x1800162a9  test    al, 1
0x1800162ab  jz      loc_180016387
0x1800162b1  mov     rax, rcx
0x1800162b4  and     eax, 1
0x1800162b7  cmp     rax, rcx
0x1800162ba  jnz     loc_180016387
0x1800162c0  mov     rcx, [rbx+8]
0x1800162c4  mov     r9, [rbx+30h]; RelatedActivityId
0x1800162c8  test    rcx, rcx
0x1800162cb  jz      short loc_1800162E1
0x1800162cd  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800162d4  inc     rax
0x1800162d7  cmp     [rcx+rax], sil
0x1800162db  jnz     short loc_1800162D4
0x1800162dd  inc     eax
0x1800162df  jmp     short loc_1800162ED
0x1800162e1  lea     rcx, qword_1801F0710
0x1800162e8  mov     eax, 1
0x1800162ed  mov     [rsp+88h+var_18], eax
0x1800162f1  lea     r8, [rbx+10h]; ActivityId
0x1800162f5  movzx   eax, cs:word_1802032C9
0x1800162fc  lea     rdx, [rsp+88h+EventDescriptor]; EventDescriptor
0x180016301  mov     dword ptr [rsp+88h+EventDescriptor.Level], eax
0x180016305  mov     rax, [r10+8]
0x180016309  mov     [rsp+88h+var_40.Ptr], rax
0x18001630e  mov     [rsp+88h+var_20], rcx
0x180016313  lea     rcx, _TraceLoggingMetadata
0x18001631a  mov     [rsp+88h+var_14], esi
0x18001631e  mov     dword ptr [rsp+88h+EventDescriptor.Id], 0B000000h
0x180016326  mov     [rsp+88h+EventDescriptor.Keyword], 1
0x18001632f  movzx   eax, word ptr [rax]
0x180016332  mov     [rsp+88h+var_40.Size], eax
0x180016336  lea     rax, byte_1802032D3
0x18001633d  mov     [rsp+88h+var_30], rax
0x180016342  lea     rax, _TraceLoggingMetadataEnd
0x180016349  sub     eax, ecx
0x18001634b  mov     dword ptr [rsp+88h+var_40.0Ch], 2
0x180016353  mov     [rsp+88h+var_28], 13h
0x18001635b  mov     [rsp+88h+var_24], 1
0x180016363  mov     [rsp+88h+var_58], eax
0x180016367  mov     eax, [rsp+88h+var_58]
0x18001636b  mov     rcx, [r10+20h]; RegHandle
0x18001636f  lea     rax, [rsp+88h+var_40]
0x180016374  mov     [rsp+88h+UserData], rax; UserData
0x180016379  mov     [rsp+88h+UserDataCount], 3; UserDataCount
0x180016381  call    cs:__imp_EventWriteTransfer
0x180016387  mov     rsi, [rsp+88h+arg_8]
0x18001638f  mov     rcx, [rsp+88h+var_10]
0x180016394  xor     rcx, rsp; StackCookie
0x180016397  call    __security_check_cookie
0x18001639c  add     rsp, 80h
0x1800163a3  pop     rbx
0x1800163a4  retn
```
