# NcsiWinINetProxySettingMonitor::ProcessEvent(void *)

- ea: `0x18005d170`
- end: `0x18005d533`
- name: `?ProcessEvent@NcsiWinINetProxySettingMonitor@@MEAAXPEAX@Z`
- size: `963`
- prototype: `void __fastcall(NcsiWinINetProxySettingMonitor *this, void *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000175c`
- `0x18000afdc`
- `0x18000b0f4`
- `0x18002283c`
- `0x1800257b8`
- `0x180029cf4`
- `0x18002a048`
- `0x180047240`
- `0x180047f78`
- `0x18004b618`
- `0x180051b7c`
- `0x18005d170`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005d2c0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005d2c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005d2af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005d4f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005d2af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005d4f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005d501`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005d501`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d1ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d26d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d2ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d1ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d26d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d2ff`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtCreateRenderContext` at `0x18005d1ee`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtCreateRenderContext` at `0x18005d1ee`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x18005d50a`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x18005d50a`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtRender` at `0x18005d25f`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtRender` at `0x18005d2f5`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtRender` at `0x18005d25f`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtRender` at `0x18005d2f5`

## string_xrefs

- `0x18005d1c2`: `Event/EventData/Data[@Name="pwszAutoConfigUrl"]`

## pseudocode

```c
void __fastcall NcsiWinINetProxySettingMonitor::ProcessEvent(NcsiWinINetProxySettingMonitor *this, void *a2)
{
  EVT_HANDLE RenderContext; // r12
  DWORD v4; // eax
  int v5; // r8d
  int v6; // r9d
  const unsigned __int16 **Buffer; // rbx
  int v8; // r8d
  int v9; // r9d
  DWORD LastError; // eax
  DWORD v11; // edi
  DWORD v12; // edi
  HANDLE ProcessHeap; // rax
  int v14; // ecx
  DWORD v15; // eax
  DWORD v16; // r15d
  const unsigned __int16 *v17; // r14
  const unsigned __int16 *v18; // rsi
  const unsigned __int16 *v19; // rdi
  unsigned __int64 v20; // r11
  NcsiConfigData *v21; // rcx
  HANDLE v22; // rax
  DWORD v23; // [rsp+40h] [rbp-C0h] BYREF
  const char *v24; // [rsp+48h] [rbp-B8h] BYREF
  char v25; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 *v26; // [rsp+70h] [rbp-90h] BYREF
  const unsigned __int16 *v27; // [rsp+78h] [rbp-88h] BYREF
  __int128 v28; // [rsp+80h] [rbp-80h] BYREF
  __int128 v29; // [rsp+90h] [rbp-70h]
  LPCWSTR ValuePaths[4]; // [rsp+A0h] [rbp-60h] BYREF
  DWORD PropertyCount; // [rsp+C0h] [rbp-40h] BYREF
  DWORD BufferUsed[3]; // [rsp+C4h] [rbp-3Ch] BYREF
  _BYTE v33[64]; // [rsp+D0h] [rbp-30h] BYREF
  int v34; // [rsp+110h] [rbp+10h]
  DWORD v35; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v36[260]; // [rsp+124h] [rbp+24h] BYREF
  unsigned __int16 v37[260]; // [rsp+32Ch] [rbp+22Ch] BYREF
  unsigned __int16 v38[262]; // [rsp+534h] [rbp+434h] BYREF

  if ( (unsigned int)dword_18009A048 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      this,
      &dword_180087C14);
  ValuePaths[0] = L"Event/EventData/Data[@Name=\"fAutoDetect\"]";
  ValuePaths[1] = L"Event/EventData/Data[@Name=\"pwszAutoConfigUrl\"]";
  ValuePaths[2] = L"Event/EventData/Data[@Name=\"pwszProxy\"]";
  ValuePaths[3] = L"Event/EventData/Data[@Name=\"pwszProxyBypass\"]";
  RenderContext = EvtCreateRenderContext(4u, ValuePaths, 0);
  if ( RenderContext )
  {
    Buffer = 0;
    BufferUsed[0] = 0;
    PropertyCount = 0;
    if ( EvtRender(RenderContext, a2, 0, 0, 0, BufferUsed, &PropertyCount) )
      goto LABEL_34;
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError == 122 )
    {
      v12 = BufferUsed[0];
      ProcessHeap = GetProcessHeap();
      Buffer = (const unsigned __int16 **)HeapAlloc(ProcessHeap, 8u, v12);
      if ( !Buffer )
        goto LABEL_34;
    }
    else
    {
      if ( (unsigned int)dword_18009A048 > 5 )
      {
        v23 = LastError;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          dword_18009A048,
          (unsigned int)byte_180087BB3,
          v8,
          v9,
          (__int64)&v23);
      }
      if ( v11 )
        goto LABEL_34;
      v12 = 0;
    }
    if ( !EvtRender(RenderContext, a2, 0, v12, Buffer, BufferUsed, &PropertyCount) )
    {
      v15 = GetLastError();
      v14 = dword_18009A048;
      if ( (unsigned int)dword_18009A048 > 5 )
      {
        v23 = v15;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          dword_18009A048,
          (unsigned int)&dword_180087B84,
          v8,
          v9,
          (__int64)&v23);
      }
    }
    if ( Buffer
      && PropertyCount == 4
      && *((_DWORD *)Buffer + 3) == 13
      && *((_DWORD *)Buffer + 7) == 1
      && *((_DWORD *)Buffer + 11) == 1
      && *((_DWORD *)Buffer + 15) == 1 )
    {
      v28 = 0;
      v29 = 0;
      v16 = *(_DWORD *)Buffer;
      LODWORD(v28) = *(_DWORD *)Buffer;
      v17 = Buffer[2];
      *((_QWORD *)&v28 + 1) = v17;
      v18 = Buffer[4];
      *(_QWORD *)&v29 = v18;
      v19 = Buffer[6];
      *((_QWORD *)&v29 + 1) = v19;
      if ( (unsigned int)dword_18009A048 > 5 )
      {
        v26 = v19;
        v27 = v18;
        v24 = (const char *)v17;
        v23 = v16;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v14,
          (unsigned int)&unk_180087AD8,
          v8,
          v9,
          (__int64)&v23,
          (__int64)&v24,
          (__int64)&v27,
          (__int64)&v26);
      }
      memset_0(v36, 0, 0x618u);
      v35 = v16;
      v20 = 260;
      if ( v17 && *v17 )
        StringCchCopyW(v36, 0x104u, v17);
      if ( v18 && *v18 )
        StringCchCopyW(v37, v20, v18);
      if ( v19 && *v19 )
        StringCchCopyW(v38, v20, v19);
      memset_0(v33, 0, sizeof(v33));
      v34 = 5;
      std::any::operator=<_NcsiUserProxyChangeMetadata,0>(v33, &v35);
      v25 = 0;
      NlmManager::PublishDiagnosticsNotificationToNlm((struct std::any *)v33);
      NcsiConfigData::HandleWinInetProxyConfigForCurrentUser(
        v21,
        (const struct _WINHTTP_CURRENT_USER_IE_PROXY_CONFIG *)&v28);
      std::any::reset((std::any *)v33);
LABEL_37:
      v22 = GetProcessHeap();
      HeapFree(v22, 0, Buffer);
LABEL_38:
      EvtClose(RenderContext);
      return;
    }
LABEL_34:
    if ( (unsigned int)dword_18009A048 > 5 )
    {
      v24 = "Invalid event content";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&dword_18009A048,
        (unsigned int)&unk_180087B48,
        v8,
        v9,
        (__int64)&v24);
    }
    if ( !Buffer )
      goto LABEL_38;
    goto LABEL_37;
  }
  v4 = GetLastError();
  if ( (unsigned int)dword_18009A048 > 5 )
  {
    PropertyCount = v4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      dword_18009A048,
      (unsigned int)byte_180087BDD,
      v5,
      v6,
      (__int64)&PropertyCount);
  }
}

```

## disassembly

```asm
0x18005d170  push    rbp
0x18005d172  push    rbx
0x18005d173  push    rsi
0x18005d174  push    rdi
0x18005d175  push    r12
0x18005d177  push    r13
0x18005d179  push    r14
0x18005d17b  push    r15
0x18005d17d  lea     rbp, [rsp-658h]
0x18005d185  sub     rsp, 758h
0x18005d18c  mov     rax, cs:__security_cookie
0x18005d193  xor     rax, rsp
0x18005d196  mov     [rbp+690h+var_50], rax
0x18005d19d  mov     rsi, rdx
0x18005d1a0  mov     eax, cs:dword_18009A048
0x18005d1a6  cmp     eax, 5
0x18005d1a9  jbe     short loc_18005D1B7
0x18005d1ab  lea     rdx, dword_180087C14
0x18005d1b2  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18005d1b7  lea     rax, aEventEventdata_3; "Event/EventData/Data[@Name=\"fAutoDetec"...
0x18005d1be  mov     [rbp+690h+ValuePaths], rax
0x18005d1c2  lea     rax, aEventEventdata_1; "Event/EventData/Data[@Name=\"pwszAutoCo"...
0x18005d1c9  mov     [rbp+690h+var_6E8], rax
0x18005d1cd  lea     rax, aEventEventdata_0; "Event/EventData/Data[@Name=\"pwszProxy"...
0x18005d1d4  mov     [rbp+690h+var_6E0], rax
0x18005d1d8  lea     rax, aEventEventdata_2; "Event/EventData/Data[@Name=\"pwszProxyB"...
0x18005d1df  mov     [rbp+690h+var_6D8], rax
0x18005d1e3  xor     r8d, r8d; Flags
0x18005d1e6  lea     rdx, [rbp+690h+ValuePaths]; ValuePaths
0x18005d1ea  lea     ecx, [r8+4]; ValuePathsCount
0x18005d1ee  call    cs:__imp_EvtCreateRenderContext
0x18005d1f4  mov     r12, rax
0x18005d1f7  xor     r13d, r13d
0x18005d1fa  test    rax, rax
0x18005d1fd  jnz     short loc_18005D231
0x18005d1ff  call    cs:__imp_GetLastError
0x18005d205  mov     ecx, cs:dword_18009A048
0x18005d20b  cmp     ecx, 5
0x18005d20e  jbe     loc_18005D510
0x18005d214  mov     [rbp+690h+var_6D0], eax
0x18005d217  lea     rax, [rbp+690h+var_6D0]
0x18005d21b  mov     [rsp+790h+Buffer], rax
0x18005d220  lea     rdx, byte_180087BDD
0x18005d227  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18005d22c  jmp     loc_18005D510
0x18005d231  mov     rbx, r13
0x18005d234  mov     [rbp+690h+var_6CC], r13d
0x18005d238  mov     [rbp+690h+var_6D0], r13d
0x18005d23c  lea     rax, [rbp+690h+var_6D0]
0x18005d240  mov     [rsp+790h+PropertyCount], rax; PropertyCount
0x18005d245  lea     rax, [rbp+690h+var_6CC]
0x18005d249  mov     [rsp+790h+BufferUsed], rax; BufferUsed
0x18005d24e  mov     [rsp+790h+Buffer], r13; Buffer
0x18005d253  xor     r9d, r9d; BufferSize
0x18005d256  xor     r8d, r8d; Flags
0x18005d259  mov     rdx, rsi; Fragment
0x18005d25c  mov     rcx, r12; Context
0x18005d25f  call    cs:__imp_EvtRender
0x18005d265  test    eax, eax
0x18005d267  jnz     loc_18005D4BA
0x18005d26d  call    cs:__imp_GetLastError
0x18005d273  mov     edi, eax
0x18005d275  cmp     eax, 7Ah ; 'z'
0x18005d278  jz      short loc_18005D2AC
0x18005d27a  mov     ecx, cs:dword_18009A048
0x18005d280  cmp     ecx, 5
0x18005d283  jbe     short loc_18005D29F
0x18005d285  mov     [rsp+790h+var_750], eax
0x18005d289  lea     rax, [rsp+790h+var_750]
0x18005d28e  mov     [rsp+790h+Buffer], rax
0x18005d293  lea     rdx, byte_180087BB3
0x18005d29a  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18005d29f  test    edi, edi
0x18005d2a1  jnz     loc_18005D4BA
0x18005d2a7  mov     edi, r13d
0x18005d2aa  jmp     short loc_18005D2D2
0x18005d2ac  mov     edi, [rbp+690h+var_6CC]
0x18005d2af  call    cs:__imp_GetProcessHeap
0x18005d2b5  mov     r8d, edi; dwBytes
0x18005d2b8  mov     edx, 8; dwFlags
0x18005d2bd  mov     rcx, rax; hHeap
0x18005d2c0  call    cs:__imp_HeapAlloc
0x18005d2c6  mov     rbx, rax
0x18005d2c9  test    rax, rax
0x18005d2cc  jz      loc_18005D4BA
0x18005d2d2  lea     rax, [rbp+690h+var_6D0]
0x18005d2d6  mov     [rsp+790h+PropertyCount], rax; PropertyCount
0x18005d2db  lea     rax, [rbp+690h+var_6CC]
0x18005d2df  mov     [rsp+790h+BufferUsed], rax; BufferUsed
0x18005d2e4  mov     [rsp+790h+Buffer], rbx; Buffer
0x18005d2e9  mov     r9d, edi; BufferSize
0x18005d2ec  xor     r8d, r8d; Flags
0x18005d2ef  mov     rdx, rsi; Fragment
0x18005d2f2  mov     rcx, r12; Context
0x18005d2f5  call    cs:__imp_EvtRender
0x18005d2fb  test    eax, eax
0x18005d2fd  jnz     short loc_18005D32A
0x18005d2ff  call    cs:__imp_GetLastError
0x18005d305  mov     ecx, cs:dword_18009A048
0x18005d30b  cmp     ecx, 5
0x18005d30e  jbe     short loc_18005D32A
0x18005d310  mov     [rsp+790h+var_750], eax
0x18005d314  lea     rax, [rsp+790h+var_750]
0x18005d319  mov     [rsp+790h+Buffer], rax
0x18005d31e  lea     rdx, dword_180087B84
0x18005d325  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18005d32a  test    rbx, rbx
0x18005d32d  jz      loc_18005D4BA
0x18005d333  cmp     [rbp+690h+var_6D0], 4
0x18005d337  jnz     loc_18005D4BA
0x18005d33d  cmp     dword ptr [rbx+0Ch], 0Dh
0x18005d341  jnz     loc_18005D4BA
0x18005d347  cmp     dword ptr [rbx+1Ch], 1
0x18005d34b  jnz     loc_18005D4BA
0x18005d351  cmp     dword ptr [rbx+2Ch], 1
0x18005d355  jnz     loc_18005D4BA
0x18005d35b  cmp     dword ptr [rbx+3Ch], 1
0x18005d35f  jnz     loc_18005D4BA
0x18005d365  xorps   xmm0, xmm0
0x18005d368  movups  [rbp+690h+var_710], xmm0
0x18005d36c  movups  [rbp+690h+var_700], xmm0
0x18005d370  mov     r15d, [rbx]
0x18005d373  mov     dword ptr [rbp+690h+var_710], r15d
0x18005d377  mov     r14, [rbx+10h]
0x18005d37b  mov     qword ptr [rbp+690h+var_710+8], r14
0x18005d37f  mov     rsi, [rbx+20h]
0x18005d383  mov     qword ptr [rbp+690h+var_700], rsi
0x18005d387  mov     rdi, [rbx+30h]
0x18005d38b  mov     qword ptr [rbp+690h+var_700+8], rdi
0x18005d38f  mov     eax, cs:dword_18009A048
0x18005d395  cmp     eax, 5
0x18005d398  jbe     short loc_18005D3E2
0x18005d39a  mov     [rsp+790h+var_720], rdi
0x18005d39f  mov     [rsp+790h+var_718], rsi
0x18005d3a4  mov     [rsp+790h+var_748], r14
0x18005d3a9  mov     [rsp+790h+var_750], r15d
0x18005d3ae  lea     rax, [rsp+790h+var_720]
0x18005d3b3  mov     [rsp+790h+var_758], rax
0x18005d3b8  lea     rax, [rsp+790h+var_718]
0x18005d3bd  mov     [rsp+790h+PropertyCount], rax
0x18005d3c2  lea     rax, [rsp+790h+var_748]
0x18005d3c7  mov     [rsp+790h+BufferUsed], rax
0x18005d3cc  lea     rax, [rsp+790h+var_750]
0x18005d3d1  mov     [rsp+790h+Buffer], rax
0x18005d3d6  lea     rdx, unk_180087AD8
0x18005d3dd  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18005d3e2  xor     edx, edx; Val
0x18005d3e4  mov     r8d, 618h; Size
0x18005d3ea  lea     rcx, [rbp+690h+var_66C]; void *
0x18005d3ee  call    memset_0
0x18005d3f3  mov     [rbp+690h+var_670], r15d
0x18005d3f7  mov     r11d, 104h
0x18005d3fd  test    r14, r14
0x18005d400  jz      short loc_18005D417
0x18005d402  cmp     [r14], r13w
0x18005d406  jz      short loc_18005D417
0x18005d408  mov     r8, r14; unsigned __int16 *
0x18005d40b  mov     edx, r11d; unsigned __int64
0x18005d40e  lea     rcx, [rbp+690h+var_66C]; unsigned __int16 *
0x18005d412  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005d417  test    rsi, rsi
0x18005d41a  jz      short loc_18005D434
0x18005d41c  cmp     [rsi], r13w
0x18005d420  jz      short loc_18005D434
0x18005d422  mov     r8, rsi; unsigned __int16 *
0x18005d425  mov     rdx, r11; unsigned __int64
0x18005d428  lea     rcx, [rbp+690h+var_464]; unsigned __int16 *
0x18005d42f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005d434  test    rdi, rdi
0x18005d437  jz      short loc_18005D451
0x18005d439  cmp     [rdi], r13w
0x18005d43d  jz      short loc_18005D451
0x18005d43f  mov     r8, rdi; unsigned __int16 *
0x18005d442  mov     rdx, r11; unsigned __int64
0x18005d445  lea     rcx, [rbp+690h+var_25C]; unsigned __int16 *
0x18005d44c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005d451  xor     edx, edx; Val
0x18005d453  lea     r8d, [rdx+40h]; Size
0x18005d457  lea     rcx, [rbp+690h+var_6C0]; void *
0x18005d45b  call    memset_0
0x18005d460  nop
0x18005d461  mov     [rbp+690h+var_680], 5
0x18005d468  lea     rdx, [rbp+690h+var_670]
0x18005d46c  lea     rcx, [rbp+690h+var_6C0]
0x18005d470  call    ??$?4U_NcsiUserProxyChangeMetadata@@$0A@@any@std@@QEAAAEAV01@$$QEAU_NcsiUserProxyChangeMetadata@@@Z; std::any::operator=<_NcsiUserProxyChangeMetadata,0>(_NcsiUserProxyChangeMetadata &&)
0x18005d475  movups  xmm0, [rsp+790h+var_740]
0x18005d47a  movdqu  [rsp+790h+var_740], xmm0
0x18005d480  mov     [rsp+790h+var_730], r13b
0x18005d485  movzx   eax, [rsp+790h+var_72F]
0x18005d48a  mov     [rsp+790h+var_72F], ax
0x18005d48f  mov     al, [rsp+790h+var_72D]
0x18005d493  mov     [rsp+790h+var_72D], al
0x18005d497  lea     rdx, [rsp+790h+var_740]
0x18005d49c  lea     rcx, [rbp+690h+var_6C0]; struct std::any *
0x18005d4a0  call    ?PublishDiagnosticsNotificationToNlm@NlmManager@@SAX$$QEAUNotification@Diagnostics@@V?$optional@U_GUID@@@std@@@Z; NlmManager::PublishDiagnosticsNotificationToNlm(Diagnostics::Notification &&,std::optional<_GUID>)
0x18005d4a5  lea     rdx, [rbp+690h+var_710]; struct _WINHTTP_CURRENT_USER_IE_PROXY_CONFIG *
0x18005d4a9  call    ?HandleWinInetProxyConfigForCurrentUser@NcsiConfigData@@QEAAXAEBU_WINHTTP_CURRENT_USER_IE_PROXY_CONFIG@@@Z; NcsiConfigData::HandleWinInetProxyConfigForCurrentUser(_WINHTTP_CURRENT_USER_IE_PROXY_CONFIG const &)
0x18005d4ae  nop
0x18005d4af  lea     rcx, [rbp+690h+var_6C0]; this
0x18005d4b3  call    ?reset@any@std@@QEAAXXZ; std::any::reset(void)
0x18005d4b8  jmp     short loc_18005D4F3
0x18005d4ba  mov     eax, cs:dword_18009A048
0x18005d4c0  cmp     eax, 5
0x18005d4c3  jbe     short loc_18005D4EE
0x18005d4c5  lea     rax, aInvalidEventCo; "Invalid event content"
0x18005d4cc  mov     [rsp+790h+var_748], rax
0x18005d4d1  lea     rax, [rsp+790h+var_748]
0x18005d4d6  mov     [rsp+790h+Buffer], rax
0x18005d4db  lea     rdx, unk_180087B48
0x18005d4e2  lea     rcx, dword_18009A048
0x18005d4e9  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18005d4ee  test    rbx, rbx
0x18005d4f1  jz      short loc_18005D507
0x18005d4f3  call    cs:__imp_GetProcessHeap
0x18005d4f9  mov     rcx, rax; hHeap
0x18005d4fc  mov     r8, rbx; lpMem
0x18005d4ff  xor     edx, edx; dwFlags
0x18005d501  call    cs:__imp_HeapFree
0x18005d507  mov     rcx, r12; Object
0x18005d50a  call    cs:__imp_EvtClose
0x18005d510  mov     rcx, [rbp+690h+var_50]
0x18005d517  xor     rcx, rsp; StackCookie
0x18005d51a  call    __security_check_cookie
0x18005d51f  add     rsp, 758h
0x18005d526  pop     r15
0x18005d528  pop     r14
0x18005d52a  pop     r13
0x18005d52c  pop     r12
0x18005d52e  pop     rdi
0x18005d52f  pop     rsi
0x18005d530  pop     rbx
0x18005d531  pop     rbp
0x18005d532  retn
```
