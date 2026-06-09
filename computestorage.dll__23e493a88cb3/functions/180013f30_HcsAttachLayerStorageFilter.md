# HcsAttachLayerStorageFilter

- ea: `0x180013f30`
- end: `0x180014122`
- name: `HcsAttachLayerStorageFilter`
- size: `498`
- prototype: `HRESULT __stdcall(PCWSTR layerPath, PCWSTR layerData)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001008`
- `0x180002690`
- `0x18000b9b4`
- `0x18000e38c`
- `0x1800137fc`
- `0x180013f30`
- `0x180015a40`
- `0x180015b20`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180013f68`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180013ff6`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180013f68`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180013ff6`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180014006`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180014006`

## string_xrefs

- `0x180013fb7`: `onecore\vm\compute\dll\storage\src\layer.cpp`

## pseudocode

```c
HRESULT __stdcall HcsAttachLayerStorageFilter(PCWSTR layerPath, PCWSTR layerData)
{
  __int64 v2; // rdx
  HRESULT v3; // ebx
  __int64 v4; // r8
  __int64 v5; // r9
  HRESULT v7; // [rsp+48h] [rbp-59h] BYREF
  unsigned __int64 v8; // [rsp+50h] [rbp-51h] BYREF
  _QWORD v9[3]; // [rsp+58h] [rbp-49h] BYREF
  _QWORD v10[3]; // [rsp+70h] [rbp-31h] BYREF
  __int16 v11; // [rsp+88h] [rbp-19h]
  LARGE_INTEGER PerformanceCount[2]; // [rsp+90h] [rbp-11h] BYREF
  LARGE_INTEGER Frequency[2]; // [rsp+A0h] [rbp-1h] BYREF
  _QWORD v14[2]; // [rsp+B0h] [rbp+Fh] BYREF
  __int64 v15; // [rsp+C0h] [rbp+1Fh] BYREF
  __int128 v16; // [rsp+C8h] [rbp+27h] BYREF
  __int64 v17; // [rsp+D8h] [rbp+37h]
  __int64 v18; // [rsp+E0h] [rbp+3Fh]
  _UNKNOWN *retaddr; // [rsp+100h] [rbp+5Fh]
  PCWSTR v20; // [rsp+108h] [rbp+67h] BYREF
  PCWSTR v21; // [rsp+110h] [rbp+6Fh] BYREF

  v21 = layerData;
  v20 = layerPath;
  *(_OWORD *)&PerformanceCount[0].LowPart = 0;
  *(_OWORD *)&Frequency[0].LowPart = 0;
  QueryPerformanceCounter(PerformanceCount);
  v15 = 0;
  v9[0] = &v21;
  v17 = 0;
  v9[1] = &v15;
  v18 = 0;
  v9[2] = &v20;
  v10[0] = retaddr;
  v10[1] = "onecore\\vm\\compute\\dll\\storage\\src\\layer.cpp";
  v11 = 281;
  v14[0] = &off_18004A088;
  v14[1] = v9;
  v16 = 0;
  v10[2] = 0;
  v3 = wil::details::ResultFromException(v10, v2, v14);
  QueryPerformanceCounter(&PerformanceCount[1]);
  QueryPerformanceFrequency(Frequency);
  Frequency[1].QuadPart = 1000000
                        * (PerformanceCount[1].QuadPart - PerformanceCount[0].QuadPart)
                        / Frequency[0].QuadPart;
  if ( (unsigned int)VmlIsDebugTraceEnabled(
                       49152,
                       1000000 * (PerformanceCount[1].QuadPart - PerformanceCount[0].QuadPart) % Frequency[0].QuadPart) )
    VmlDebugTrace(49152, L"%s, Time Taken (us) : %llu\n", L"HcsAttachLayerStorageFilter", Frequency[1].QuadPart);
  v4 = *((_QWORD *)ComputeStorage::Diagnostics::TraceProvider::Instance() + 1);
  if ( *(_DWORD *)v4 > 5u
    && (*(_QWORD *)(v4 + 16) & 0x400000000000LL) != 0
    && (*(_QWORD *)(v4 + 24) & 0x400000000000LL) == *(_QWORD *)(v4 + 24) )
  {
    v8 = Frequency[1].QuadPart / 0x3E8uLL;
    v7 = v3;
    v14[0] = 0x6DB6DB6DB6DB6DB7LL * ((__int64)(*((_QWORD *)&v16 + 1) - v16) >> 3);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      v4,
      (int)word_180054C12,
      v4,
      v5,
      (__int64)&v7,
      (__int64)v14,
      (__int64)&v8);
  }
  std::vector<Schema::Common::Resources::Layer>::_Tidy((char ***)&v16);
  return v3;
}

```

## disassembly

```asm
0x180013f30  mov     rax, rsp
0x180013f33  mov     [rax+18h], rbx
0x180013f37  mov     [rax+10h], rdx
0x180013f3b  mov     [rax+8], rcx
0x180013f3f  push    rbp
0x180013f40  lea     rbp, [rax-5Fh]
0x180013f44  sub     rsp, 0F0h
0x180013f4b  mov     rax, cs:__security_cookie
0x180013f52  xor     rax, rsp
0x180013f55  mov     [rbp+57h+var_10], rax
0x180013f59  xorps   xmm0, xmm0
0x180013f5c  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x180013f60  movups  xmmword ptr [rbp+57h+PerformanceCount], xmm0
0x180013f64  movups  xmmword ptr [rbp+57h+Frequency], xmm0
0x180013f68  call    cs:__imp_QueryPerformanceCounter
0x180013f6f  nop     dword ptr [rax+rax+00h]
0x180013f74  lea     rax, [rbp+57h+arg_8]
0x180013f78  mov     [rbp+57h+var_38], 0
0x180013f80  mov     [rbp+57h+var_A0], rax
0x180013f84  lea     r8, [rbp+57h+var_48]
0x180013f88  lea     rax, [rbp+57h+var_38]
0x180013f8c  mov     [rbp+57h+var_20], 0
0x180013f94  mov     [rbp+57h+var_98], rax
0x180013f98  lea     rcx, [rbp+57h+var_88]
0x180013f9c  lea     rax, [rbp+57h+arg_0]
0x180013fa0  mov     [rbp+57h+var_18], 0
0x180013fa8  mov     [rbp+57h+var_90], rax
0x180013fac  xorps   xmm0, xmm0
0x180013faf  mov     rax, [rbp+5Fh]
0x180013fb3  mov     [rbp+57h+var_88], rax
0x180013fb7  lea     rax, aOnecoreVmCompu_1; "onecore\\vm\\compute\\dll\\storage\\src"...
0x180013fbe  mov     [rbp+57h+var_80], rax
0x180013fc2  mov     eax, 119h
0x180013fc7  mov     [rbp+57h+var_70], ax
0x180013fcb  lea     rax, off_18004A088
0x180013fd2  mov     [rbp+57h+var_48], rax
0x180013fd6  lea     rax, [rbp+57h+var_A0]
0x180013fda  mov     [rbp+57h+var_40], rax
0x180013fde  movdqu  [rbp+57h+var_30], xmm0
0x180013fe3  mov     [rbp+57h+var_78], 0
0x180013feb  call    ?ResultFromException@details@wil@@YAJAEBUDiagnosticsInfo@2@W4SupportedExceptions@2@AEAUIFunctor@12@@Z; wil::details::ResultFromException(wil::DiagnosticsInfo const &,wil::SupportedExceptions,wil::details::IFunctor &)
0x180013ff0  lea     rcx, [rbp+57h+PerformanceCount+8]; lpPerformanceCount
0x180013ff4  mov     ebx, eax
0x180013ff6  call    cs:__imp_QueryPerformanceCounter
0x180013ffd  nop     dword ptr [rax+rax+00h]
0x180014002  lea     rcx, [rbp+57h+Frequency]; lpFrequency
0x180014006  call    cs:__imp_QueryPerformanceFrequency
0x18001400d  nop     dword ptr [rax+rax+00h]
0x180014012  mov     rcx, qword ptr [rbp+57h+PerformanceCount+8]
0x180014016  sub     rcx, qword ptr [rbp+57h+PerformanceCount]
0x18001401a  imul    rax, rcx, 0F4240h
0x180014021  mov     ecx, 0C000h
0x180014026  cqo
0x180014028  idiv    qword ptr [rbp+57h+Frequency]
0x18001402c  mov     qword ptr [rbp+57h+Frequency+8], rax
0x180014030  call    VmlIsDebugTraceEnabled
0x180014035  test    eax, eax
0x180014037  jz      short loc_180014055
0x180014039  mov     r9, qword ptr [rbp+57h+Frequency+8]
0x18001403d  lea     r8, aHcsattachlayer_0; "HcsAttachLayerStorageFilter"
0x180014044  lea     rdx, aSTimeTakenUsLl; "%s, Time Taken (us) : %llu\n"
0x18001404b  mov     ecx, 0C000h
0x180014050  call    VmlDebugTrace
0x180014055  call    ?Instance@TraceProvider@Diagnostics@ComputeStorage@@KAPEAV123@XZ; ComputeStorage::Diagnostics::TraceProvider::Instance(void)
0x18001405a  mov     r8, [rax+8]
0x18001405e  mov     eax, [r8]
0x180014061  cmp     eax, 5
0x180014064  jbe     loc_1800140F9
0x18001406a  mov     rcx, [r8+18h]
0x18001406e  mov     rdx, 400000000000h
0x180014078  mov     rax, [r8+10h]
0x18001407c  test    rdx, rax
0x18001407f  jz      short loc_1800140F9
0x180014081  mov     rax, rcx
0x180014084  and     rax, rdx
0x180014087  cmp     rax, rcx
0x18001408a  jnz     short loc_1800140F9
0x18001408c  mov     rcx, qword ptr [rbp+57h+Frequency+8]
0x180014090  mov     rax, 624DD2F1A9FBE77h
0x18001409a  mul     rcx
0x18001409d  mov     rax, qword ptr [rbp+57h+var_30+8]
0x1800140a1  sub     rax, qword ptr [rbp+57h+var_30]
0x1800140a5  sub     rcx, rdx
0x1800140a8  shr     rcx, 1
0x1800140ab  add     rcx, rdx
0x1800140ae  sar     rax, 3
0x1800140b2  shr     rcx, 9
0x1800140b6  lea     rdx, word_180054C12
0x1800140bd  mov     [rbp+57h+var_A8], rcx
0x1800140c1  mov     rcx, 6DB6DB6DB6DB6DB7h
0x1800140cb  imul    rax, rcx
0x1800140cf  mov     rcx, r8
0x1800140d2  mov     [rbp+57h+var_B0], ebx
0x1800140d5  mov     [rbp+57h+var_48], rax
0x1800140d9  lea     rax, [rbp+57h+var_A8]
0x1800140dd  mov     [rsp+30h], rax
0x1800140e2  lea     rax, [rbp+57h+var_48]
0x1800140e6  mov     [rsp+0F0h+var_C8], rax
0x1800140eb  lea     rax, [rbp+57h+var_B0]
0x1800140ef  mov     [rsp+0F0h+var_D0], rax
0x1800140f4  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x1800140f9  lea     rcx, [rbp+57h+var_30]
0x1800140fd  call    ?_Tidy@?$vector@ULayer@Resources@Common@Schema@@V?$allocator@ULayer@Resources@Common@Schema@@@std@@@std@@AEAAXXZ; std::vector<Schema::Common::Resources::Layer>::_Tidy(void)
0x180014102  mov     eax, ebx
0x180014104  mov     rcx, [rbp+57h+var_10]
0x180014108  xor     rcx, rsp; StackCookie
0x18001410b  call    __security_check_cookie
0x180014110  mov     rbx, [rsp+0F0h+arg_10]
0x180014118  add     rsp, 0F0h
0x18001411f  pop     rbp
0x180014120  retn
```
