# InputTraceLogging::ContextualProcessing::OnHitTest(HitTestInfo const *,ushort const *,ContextualProcessorState)

- ea: `0x180016650`
- end: `0x18001694b`
- name: `?OnHitTest@ContextualProcessing@InputTraceLogging@@SAXPEBUHitTestInfo@@PEBGW4ContextualProcessorState@@@Z`
- size: `763`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180015b50`

## callees

- `0x180016650`
- `0x18003e8e0`
- `0x180066188`
- `0x1800f0354`
- `0x1800f0990`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180016756`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180016756`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001669d`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001669d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180016921`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180016921`

## pseudocode

```c
int __fastcall InputTraceLogging::ContextualProcessing::OnHitTest(unsigned int *a1, const WCHAR *a2, int a3)
{
  __int64 v6; // rdx
  __int64 v7; // r10
  __int64 v8; // rax
  int v9; // ebx
  int v10; // ebx
  const char *v11; // r8
  __int64 v12; // rcx
  __int64 v13; // r8
  const unsigned __int16 *v14; // r9
  __int64 v15; // r10
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rax
  int v20; // eax
  int v21; // ecx
  WINBOOL fPending; // [rsp+30h] [rbp-79h] BYREF
  LPVOID Context; // [rsp+38h] [rbp-71h] BYREF
  unsigned int v25; // [rsp+40h] [rbp-69h] BYREF
  __int64 v26; // [rsp+48h] [rbp-61h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+50h] [rbp-59h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-49h] BYREF
  char *v29; // [rsp+70h] [rbp-39h]
  int v30; // [rsp+78h] [rbp-31h]
  int v31; // [rsp+7Ch] [rbp-2Dh]
  __int64 *v32; // [rsp+80h] [rbp-29h]
  __int64 v33; // [rsp+88h] [rbp-21h]
  unsigned int *v34; // [rsp+90h] [rbp-19h]
  __int64 v35; // [rsp+98h] [rbp-11h]
  const unsigned __int16 *v36; // [rsp+A0h] [rbp-9h]
  int v37; // [rsp+A8h] [rbp-1h]
  int v38; // [rsp+ACh] [rbp+3h]
  WINBOOL *p_fPending; // [rsp+B0h] [rbp+7h]
  __int64 v40; // [rsp+B8h] [rbp+Fh]
  const WCHAR *v41; // [rsp+C0h] [rbp+17h]
  int v42; // [rsp+C8h] [rbp+1Fh]
  int v43; // [rsp+CCh] [rbp+23h]
  __int64 v44; // [rsp+D0h] [rbp+27h]
  int v45; // [rsp+D8h] [rbp+2Fh]
  int v46; // [rsp+DCh] [rbp+33h]

  Context = 0;
  fPending = 0;
  if ( __std_init_once_begin_initialize(&`InputTraceLogging::Instance'::`2'::wrapper, 0, &fPending, &Context)
    && fPending )
  {
    qword_180243F80 = 0;
    Context = &qword_180243F78;
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
  v7 = *((_QWORD *)Context + 1);
  LODWORD(v8) = *(_DWORD *)v7;
  if ( *(_DWORD *)v7 > 4u )
  {
    v8 = *(_QWORD *)(v7 + 16);
    if ( (v8 & 0x400) != 0 )
    {
      v8 = *(_QWORD *)(v7 + 24) & 0x400LL;
      if ( v8 == *(_QWORD *)(v7 + 24) )
      {
        if ( a3 )
        {
          v9 = a3 - 1;
          if ( v9 )
          {
            v10 = v9 - 1;
            if ( v10 )
            {
              if ( v10 == 1 )
                v11 = "Listen";
              else
                v11 = "UNKNOWN";
            }
            else
            {
              v11 = "Handle";
            }
          }
          else
          {
            v11 = "Buffer";
          }
        }
        else
        {
          v11 = "Ignore";
        }
        v12 = *a1;
        fPending = a1[1];
        v14 = (const unsigned __int16 *)InputTraceLogging::InputTypeToString(v12, v6, v11);
        v25 = a1[10];
        v26 = *((_QWORD *)a1 + 2);
        v16 = -1;
        v17 = -1;
        do
          ++v17;
        while ( *(_BYTE *)(v13 + v17) );
        v44 = v13;
        v45 = v17 + 1;
        v46 = 0;
        if ( a2 )
        {
          v18 = -1;
          while ( a2[++v18] != 0 )
            ;
          v20 = 2 * v18 + 2;
        }
        else
        {
          a2 = &WindowName;
          v20 = 2;
        }
        v42 = v20;
        p_fPending = &fPending;
        v41 = a2;
        v43 = 0;
        v40 = 4;
        if ( v14 )
        {
          do
            ++v16;
          while ( *((_BYTE *)v14 + v16) );
          v21 = v16 + 1;
        }
        else
        {
          v14 = &qword_1801F0710;
          v21 = 1;
        }
        v37 = v21;
        v34 = &v25;
        v36 = v14;
        v32 = &v26;
        *(_DWORD *)&EventDescriptor.Level = 4;
        UserData.Ptr = *(_QWORD *)(v15 + 8);
        v38 = 0;
        v35 = 4;
        v33 = 8;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 1024;
        UserData.Size = *(unsigned __int16 *)UserData.Ptr;
        v29 = byte_18021AB35;
        UserData.Reserved = 2;
        v30 = 90;
        v31 = 1;
        LODWORD(Context) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        LODWORD(v8) = EventWriteTransfer(*(_QWORD *)(v15 + 32), &EventDescriptor, 0, 0, 8u, &UserData);
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180016650  mov     [rsp-8+arg_8], rbx
0x180016655  mov     [rsp-8+arg_10], rsi
0x18001665a  push    rbp
0x18001665b  push    rdi
0x18001665c  push    r15
0x18001665e  lea     rbp, [rsp-47h]
0x180016663  sub     rsp, 0F0h
0x18001666a  mov     rax, cs:__security_cookie
0x180016671  xor     rax, rsp
0x180016674  mov     [rbp+57h+var_20], rax
0x180016678  mov     ebx, r8d
0x18001667b  lea     r9, [rbp+57h+Context]; lpContext
0x18001667f  mov     rdi, rdx
0x180016682  lea     r8, [rbp+57h+fPending]; fPending
0x180016686  mov     rsi, rcx
0x180016689  xor     r15d, r15d
0x18001668c  xor     edx, edx; dwFlags
0x18001668e  mov     [rbp+57h+Context], r15
0x180016692  lea     rcx, ?wrapper@?1??Instance@InputTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VInputTraceLogging@@@details@wil@@A; lpInitOnce
0x180016699  mov     [rbp+57h+fPending], r15d
0x18001669d  call    cs:__imp___std_init_once_begin_initialize
0x1800166a3  test    eax, eax
0x1800166a5  jz      loc_180016764
0x1800166ab  cmp     [rbp+57h+fPending], r15d
0x1800166af  jz      loc_180016764
0x1800166b5  mov     [rsp+100h+arg_0], r14
0x1800166bd  lea     rax, ??_7RawInputProvidersContinuousTracing@@6B@; const RawInputProvidersContinuousTracing::`vftable'
0x1800166c4  lea     r14, qword_180243F78
0x1800166cb  mov     cs:qword_180243F80, r15
0x1800166d2  mov     [rbp+57h+Context], r14
0x1800166d6  mov     cs:byte_180243F88, r15b
0x1800166dd  mov     cs:dword_180243F8C, r15d
0x1800166e4  mov     cs:qword_180243F78, rax
0x1800166eb  lea     rax, ?__hInner@?1???0StaticHandle@InputTraceLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `InputTraceLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1800166f2  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_a8e7baa2fca040c17c3e795f3590cb07_@@CA@XZ; void (__cdecl *)()
0x1800166f9  mov     cs:CallbackContext, rax
0x180016700  call    atexit
0x180016705  mov     rcx, cs:CallbackContext; CallbackContext
0x18001670c  lea     rdx, ?Callback@InputTraceLogging@@CAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; InputTraceLogging::Callback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x180016713  mov     cs:qword_180243F80, rcx
0x18001671a  mov     cs:byte_180243F88, 1
0x180016721  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180016726  mov     rax, cs:qword_180243F78
0x18001672d  mov     rcx, r14
0x180016730  mov     cs:dword_180243F8C, 1
0x18001673a  mov     rax, [rax+8]
0x18001673e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016743  mov     r8, r14; lpContext
0x180016746  mov     cs:?s_registered@InputTraceLogging@@0_NA, 1; bool InputTraceLogging::s_registered
0x18001674d  xor     edx, edx; dwFlags
0x18001674f  lea     rcx, ?wrapper@?1??Instance@InputTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VInputTraceLogging@@@details@wil@@A; lpInitOnce
0x180016756  call    cs:__imp_InitOnceComplete
0x18001675c  mov     r14, [rsp+100h+arg_0]
0x180016764  mov     rax, [rbp+57h+Context]
0x180016768  mov     r10, [rax+8]
0x18001676c  mov     eax, [r10]
0x18001676f  cmp     eax, 4
0x180016772  jbe     loc_180016927
0x180016778  mov     rcx, [r10+18h]
0x18001677c  mov     rax, [r10+10h]
0x180016780  bt      rax, 0Ah
0x180016785  jnb     loc_180016927
0x18001678b  mov     rax, rcx
0x18001678e  and     eax, 400h
0x180016793  cmp     rax, rcx
0x180016796  jnz     loc_180016927
0x18001679c  test    ebx, ebx
0x18001679e  jz      short loc_1800167D3
0x1800167a0  sub     ebx, 1
0x1800167a3  jz      short loc_1800167CA
0x1800167a5  sub     ebx, 1
0x1800167a8  jz      short loc_1800167C1
0x1800167aa  cmp     ebx, 1
0x1800167ad  jz      short loc_1800167B8
0x1800167af  lea     r8, aUnknown; "UNKNOWN"
0x1800167b6  jmp     short loc_1800167DA
0x1800167b8  lea     r8, aListen; "Listen"
0x1800167bf  jmp     short loc_1800167DA
0x1800167c1  lea     r8, aHandle; "Handle"
0x1800167c8  jmp     short loc_1800167DA
0x1800167ca  lea     r8, aBuffer; "Buffer"
0x1800167d1  jmp     short loc_1800167DA
0x1800167d3  lea     r8, aIgnore; "Ignore"
0x1800167da  mov     eax, [rsi+4]
0x1800167dd  mov     ecx, [rsi]
0x1800167df  mov     [rbp+57h+fPending], eax
0x1800167e2  call    ?InputTypeToString@InputTraceLogging@@CAPEBDW4InputType@@@Z; InputTraceLogging::InputTypeToString(InputType)
0x1800167e7  mov     ecx, [rsi+28h]
0x1800167ea  mov     r9, rax
0x1800167ed  mov     [rbp+57h+var_C0], ecx
0x1800167f0  mov     rcx, [rsi+10h]
0x1800167f4  mov     [rbp+57h+var_B8], rcx
0x1800167f8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800167ff  mov     rax, rcx
0x180016802  inc     rax
0x180016805  cmp     [r8+rax], r15b
0x180016809  jnz     short loc_180016802
0x18001680b  inc     eax
0x18001680d  mov     [rbp+57h+var_30], r8
0x180016811  mov     [rbp+57h+var_28], eax
0x180016814  mov     [rbp+57h+var_24], r15d
0x180016818  test    rdi, rdi
0x18001681b  jz      short loc_180016835
0x18001681d  mov     rax, rcx
0x180016820  cmp     [rdi+rax*2+2], r15w
0x180016826  lea     rax, [rax+1]
0x18001682a  jnz     short loc_180016820
0x18001682c  lea     eax, ds:2[rax*2]
0x180016833  jmp     short loc_180016841
0x180016835  lea     rdi, WindowName
0x18001683c  mov     eax, 2
0x180016841  mov     [rbp+57h+var_38], eax
0x180016844  lea     rax, [rbp+57h+fPending]
0x180016848  mov     [rbp+57h+var_50], rax
0x18001684c  mov     [rbp+57h+var_40], rdi
0x180016850  mov     [rbp+57h+var_34], r15d
0x180016854  mov     [rbp+57h+var_48], 4
0x18001685c  test    r9, r9
0x18001685f  jz      short loc_18001686E
0x180016861  inc     rcx
0x180016864  cmp     [r9+rcx], r15b
0x180016868  jnz     short loc_180016861
0x18001686a  inc     ecx
0x18001686c  jmp     short loc_18001687A
0x18001686e  lea     r9, qword_1801F0710
0x180016875  mov     ecx, 1
0x18001687a  mov     [rbp+57h+var_58], ecx
0x18001687d  lea     rax, [rbp+57h+var_C0]
0x180016881  mov     [rbp+57h+var_70], rax
0x180016885  lea     rcx, _TraceLoggingMetadata
0x18001688c  mov     [rbp+57h+var_60], r9
0x180016890  lea     rax, [rbp+57h+var_B8]
0x180016894  mov     [rbp+57h+var_80], rax
0x180016898  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18001689c  movzx   eax, cs:word_18021AB2B
0x1800168a3  xor     r9d, r9d; RelatedActivityId
0x1800168a6  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x1800168a9  xor     r8d, r8d; ActivityId
0x1800168ac  mov     rax, [r10+8]
0x1800168b0  mov     [rbp+57h+var_A0.Ptr], rax
0x1800168b4  mov     [rbp+57h+var_54], r15d
0x1800168b8  mov     [rbp+57h+var_68], 4
0x1800168c0  mov     [rbp+57h+var_78], 8
0x1800168c8  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x1800168cf  mov     [rbp+57h+EventDescriptor.Keyword], 400h
0x1800168d7  movzx   eax, word ptr [rax]
0x1800168da  mov     [rbp+57h+var_A0.Size], eax
0x1800168dd  lea     rax, byte_18021AB35
0x1800168e4  mov     [rbp+57h+var_90], rax
0x1800168e8  lea     rax, _TraceLoggingMetadataEnd
0x1800168ef  sub     eax, ecx
0x1800168f1  mov     dword ptr [rbp+57h+var_A0.0Ch], 2
0x1800168f8  mov     [rbp+57h+var_88], 5Ah ; 'Z'
0x1800168ff  mov     [rbp+57h+var_84], 1
0x180016906  mov     dword ptr [rbp+57h+Context], eax
0x180016909  mov     eax, dword ptr [rbp+57h+Context]
0x18001690c  mov     rcx, [r10+20h]; RegHandle
0x180016910  lea     rax, [rbp+57h+var_A0]
0x180016914  mov     [rsp+100h+UserData], rax; UserData
0x180016919  mov     [rsp+100h+UserDataCount], 8; UserDataCount
0x180016921  call    cs:__imp_EventWriteTransfer
0x180016927  mov     rcx, [rbp+57h+var_20]
0x18001692b  xor     rcx, rsp; StackCookie
0x18001692e  call    __security_check_cookie
0x180016933  lea     r11, [rsp+100h+var_10]
0x18001693b  mov     rbx, [r11+28h]
0x18001693f  mov     rsi, [r11+30h]
0x180016943  mov     rsp, r11
0x180016946  pop     r15
0x180016948  pop     rdi
0x180016949  pop     rbp
0x18001694a  retn
```
