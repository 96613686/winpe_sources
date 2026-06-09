# CPipeVC::InitializeInstance(void)

- ea: `0x18000b820`
- end: `0x18000beeb`
- name: `?InitializeInstance@CPipeVC@@UEAAJXZ`
- size: `1739`
- prototype: `__int64 __fastcall(CPipeVC *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callees

- `0x1800091a8`
- `0x18000b820`
- `0x18000bef4`
- `0x18000c360`
- `0x18000c4ec`
- `0x18002e600`
- `0x180033940`
- `0x180033964`
- `0x180034970`
- `0x180059838`
- `0x180059878`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b873`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b891`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b8b2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b8d3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b873`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b891`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b8b2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b8d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bbb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bcc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bbb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bcc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd74`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b971`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b9ce`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b971`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b9ce`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18000be7c`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18000be7c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ba03`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ba03`

## string_xrefs

- `0x18000bc5d`: `Failed CreateEvent call for m_hConnectPipeEvent Event`
- `0x18000bc03`: `m_PipeWriteQueueLock.Initialize`
- `0x18000bd11`: `Failed CreateEvent call for m_hWriteCallbackEvent Event`
- `0x18000bcb7`: `Failed CreateEvent call for m_hReadCallbackEvent Event`
- `0x18000bdc2`: `m_ReadPipeQueueLock.Initialize`
- `0x18000bd6b`: `Failed CreateEvent call for m_hChannelOpenEvent Event`
- `0x18000bdd5`: `CPipeReadQueueEntry::CreateInstance`

## pseudocode

```c
__int64 __fastcall CPipeVC::InitializeInstance(CPipeVC *this)
{
  HANDLE EventW; // rax
  HANDLE v3; // rax
  HANDLE v4; // rax
  HANDLE v5; // rax
  const unsigned __int16 *v6; // rdx
  HKEY v7; // r8
  int v8; // r9d
  LSTATUS v9; // eax
  signed int v10; // ecx
  signed int v11; // ecx
  bool v12; // sf
  signed int v13; // esi
  int v14; // ebx
  _QWORD *v15; // r9
  struct CPipeReadQueueEntry *v16; // rdx
  char *v17; // r8
  void *v18; // rax
  int v20; // ebx
  int v21; // edi
  unsigned int v22; // eax
  signed int LastError; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v25; // edx
  const char *v26; // rcx
  signed int v27; // eax
  signed int v28; // eax
  signed int v29; // eax
  signed int v30; // eax
  signed int v31; // eax
  signed int v32; // eax
  unsigned int v33; // eax
  unsigned int lpData; // [rsp+20h] [rbp-48h]
  LPDWORD lpcbData; // [rsp+28h] [rbp-40h]
  HKEY hKey; // [rsp+30h] [rbp-38h] BYREF
  __int64 v37; // [rsp+38h] [rbp-30h]
  void *Block; // [rsp+40h] [rbp-28h]
  int v39; // [rsp+4Ch] [rbp-1Ch]
  int Data; // [rsp+B0h] [rbp+48h] BYREF
  int v41; // [rsp+B8h] [rbp+50h] BYREF
  struct CPipeReadQueueEntry *cbData; // [rsp+C0h] [rbp+58h] BYREF
  DWORD Type; // [rsp+C8h] [rbp+60h] BYREF

  if ( !(unsigned int)CTSCriticalSection::Initialize((CPipeVC *)((char *)this + 40)) )
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)v13;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v25 = 66;
      v26 = "m_objLock.Initialize";
      goto LABEL_94;
    }
  }
  if ( !(unsigned int)CTSCriticalSection::Initialize((CPipeVC *)((char *)this + 224)) )
  {
    v27 = GetLastError();
    v13 = v27;
    if ( v27 > 0 )
      v13 = (unsigned __int16)v27 | 0x80070000;
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)v13;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v25 = 67;
      v26 = "m_PipeWriteQueueLock.Initialize";
      goto LABEL_94;
    }
  }
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 11) = EventW;
  if ( !EventW )
  {
    v28 = GetLastError();
    v13 = v28;
    if ( v28 > 0 )
      v13 = (unsigned __int16)v28 | 0x80070000;
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)v13;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v25 = 68;
      v26 = "Failed CreateEvent call for m_hConnectPipeEvent Event";
      goto LABEL_94;
    }
  }
  v3 = CreateEventW(0, 1, 1, 0);
  *((_QWORD *)this + 34) = v3;
  if ( !v3 )
  {
    v29 = GetLastError();
    v13 = v29;
    if ( v29 > 0 )
      v13 = (unsigned __int16)v29 | 0x80070000;
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)v13;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v25 = 69;
      v26 = "Failed CreateEvent call for m_hReadCallbackEvent Event";
      goto LABEL_94;
    }
  }
  v4 = CreateEventW(0, 1, 1, 0);
  *((_QWORD *)this + 35) = v4;
  if ( !v4 )
  {
    v30 = GetLastError();
    v13 = v30;
    if ( v30 > 0 )
      v13 = (unsigned __int16)v30 | 0x80070000;
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)v13;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v25 = 70;
      v26 = "Failed CreateEvent call for m_hWriteCallbackEvent Event";
      goto LABEL_94;
    }
  }
  v5 = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 47) = v5;
  if ( !v5 )
  {
    v31 = GetLastError();
    v13 = v31;
    if ( v31 > 0 )
      v13 = (unsigned __int16)v31 | 0x80070000;
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)v13;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v25 = 71;
      v26 = "Failed CreateEvent call for m_hChannelOpenEvent Event";
      goto LABEL_94;
    }
  }
  if ( !(unsigned int)CTSCriticalSection::Initialize((CPipeVC *)((char *)this + 352)) )
  {
    v32 = GetLastError();
    v13 = v32;
    if ( v32 > 0 )
      v13 = (unsigned __int16)v32 | 0x80070000;
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)v13;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v25 = 72;
      v26 = "m_ReadPipeQueueLock.Initialize";
LABEL_94:
      LODWORD(lpcbData) = v13;
LABEL_95:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v25,
        (unsigned int)&WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v26,
        lpcbData,
        hKey,
        v37);
      return (unsigned int)v13;
    }
  }
  *((_DWORD *)this + 86) = 0;
  Data = 0;
  v41 = 0;
  CTSRegEntry::CTSRegEntry(&hKey, v6, v7, v8, lpData);
  v9 = v37;
  if ( (int)v37 > 0 )
    v10 = (unsigned __int16)v37 | 0x80070000;
  else
    v10 = v37;
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v33 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids, v33);
    }
    Data = 20;
    goto LABEL_22;
  }
  LODWORD(cbData) = 4;
  Type = 3;
  Data = 20;
  if ( HIDWORD(v37) )
  {
    v9 = RegQueryValueExW(hKey, L"PipeVCBuffers", 0, &Type, (LPBYTE)&Data, (LPDWORD)&cbData);
    LODWORD(v37) = v9;
  }
  if ( v9 > 0 )
    v11 = (unsigned __int16)v9 | 0x80070000;
  else
    v11 = v9;
  if ( v11 < 0 || Data <= 0 )
    Data = 20;
  Type = 3;
  LODWORD(cbData) = 4;
  v41 = 0x10000;
  if ( HIDWORD(v37) )
  {
    v9 = RegQueryValueExW(hKey, L"PipeVCBufferSize", 0, &Type, (LPBYTE)&v41, (LPDWORD)&cbData);
    LODWORD(v37) = v9;
  }
  v12 = v9 < 0;
  if ( v9 > 0 )
    v12 = 1;
  if ( v12 || v41 <= 0 )
LABEL_22:
    v41 = 0x10000;
  v13 = 0;
  if ( v39 )
  {
    if ( !HIDWORD(v37) )
      goto LABEL_26;
    LODWORD(v37) = RegFlushKey(hKey);
  }
  if ( HIDWORD(v37) )
    RegCloseKey(hKey);
LABEL_26:
  hKey = 0;
  if ( Block )
    operator delete(Block);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v20 = v41;
    v21 = Data;
    v22 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DdD(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids, v22, v21, v20);
  }
  v14 = 0;
  while ( v14 < Data )
  {
    cbData = 0;
    v13 = CPipeReadQueueEntry::CreateInstance((unsigned int)v41, &cbData);
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v25 = 75;
        v26 = "CPipeReadQueueEntry::CreateInstance";
        goto LABEL_94;
      }
      return (unsigned int)v13;
    }
    v15 = (_QWORD *)*((_QWORD *)this + 40);
    v16 = cbData;
    ++v14;
    v17 = (char *)cbData + 80;
    *((_QWORD *)cbData + 10) = (char *)this + 312;
    *((_QWORD *)v16 + 11) = v15;
    *v15 = v17;
    *((_QWORD *)this + 40) = v17;
  }
  *((_QWORD *)this + 22) = 0;
  v18 = operator new(0x648u);
  *((_QWORD *)this + 22) = v18;
  if ( v18 )
  {
    memset_0(v18, 0, 0x648u);
    *((_DWORD *)this - 5) |= 2u;
    return (unsigned int)v13;
  }
  v13 = -2147024882;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v25 = 76;
    LODWORD(lpcbData) = -2147024882;
    v26 = "OOM on m_pbCurrentPdu!";
    goto LABEL_95;
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000b820  push    rbp
0x18000b822  push    rbx
0x18000b823  push    rsi
0x18000b824  push    rdi
0x18000b825  push    r12
0x18000b827  push    r13
0x18000b829  push    r14
0x18000b82b  push    r15
0x18000b82d  mov     rbp, rsp
0x18000b830  sub     rsp, 68h
0x18000b834  mov     r15, rcx
0x18000b837  add     rcx, 28h ; '('; this
0x18000b83b  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x18000b840  xor     r12d, r12d
0x18000b843  mov     ebx, 80070000h
0x18000b848  test    eax, eax
0x18000b84a  jz      loc_18000BB59
0x18000b850  lea     rcx, [r15+0E0h]; this
0x18000b857  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x18000b85c  test    eax, eax
0x18000b85e  jz      loc_18000BBB5
0x18000b864  xor     r9d, r9d; lpName
0x18000b867  xor     r8d, r8d; bInitialState
0x18000b86a  xor     ecx, ecx; lpEventAttributes
0x18000b86c  lea     r13d, [r9+1]
0x18000b870  mov     edx, r13d; bManualReset
0x18000b873  call    cs:__imp_CreateEventW
0x18000b879  mov     [r15+58h], rax
0x18000b87d  test    rax, rax
0x18000b880  jz      loc_18000BC0F
0x18000b886  xor     r9d, r9d; lpName
0x18000b889  mov     r8d, r13d; bInitialState
0x18000b88c  mov     edx, r13d; bManualReset
0x18000b88f  xor     ecx, ecx; lpEventAttributes
0x18000b891  call    cs:__imp_CreateEventW
0x18000b897  mov     [r15+110h], rax
0x18000b89e  test    rax, rax
0x18000b8a1  jz      loc_18000BC69
0x18000b8a7  xor     r9d, r9d; lpName
0x18000b8aa  mov     r8d, r13d; bInitialState
0x18000b8ad  mov     edx, r13d; bManualReset
0x18000b8b0  xor     ecx, ecx; lpEventAttributes
0x18000b8b2  call    cs:__imp_CreateEventW
0x18000b8b8  mov     [r15+118h], rax
0x18000b8bf  test    rax, rax
0x18000b8c2  jz      loc_18000BCC3
0x18000b8c8  xor     r9d, r9d; lpName
0x18000b8cb  xor     r8d, r8d; bInitialState
0x18000b8ce  mov     edx, r13d; bManualReset
0x18000b8d1  xor     ecx, ecx; lpEventAttributes
0x18000b8d3  call    cs:__imp_CreateEventW
0x18000b8d9  mov     [r15+178h], rax
0x18000b8e0  test    rax, rax
0x18000b8e3  jz      loc_18000BD1D
0x18000b8e9  lea     rcx, [r15+160h]; this
0x18000b8f0  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x18000b8f5  test    eax, eax
0x18000b8f7  jz      loc_18000BD74
0x18000b8fd  lea     rcx, [rbp+hKey]; phkResult
0x18000b901  mov     [r15+158h], r12d
0x18000b908  mov     [rbp+Data], r12d
0x18000b90c  mov     [rbp+arg_8], r12d
0x18000b910  call    ??0CTSRegEntry@@QEAA@PEBGPEAUHKEY__@@HK@Z; CTSRegEntry::CTSRegEntry(ushort const *,HKEY__ *,int,ulong)
0x18000b915  mov     eax, [rbp+var_30]
0x18000b918  test    eax, eax
0x18000b91a  jg      loc_18000BAC0
0x18000b920  mov     ecx, eax
0x18000b922  lea     r14, WPP_GLOBAL_Control
0x18000b929  test    ecx, ecx
0x18000b92b  js      loc_18000BACA
0x18000b931  mov     edi, 3
0x18000b936  mov     dword ptr [rbp+cbData], 4
0x18000b93d  mov     [rbp+Type], edi
0x18000b940  mov     [rbp+Data], 14h
0x18000b947  cmp     [rbp+var_2C], r12d
0x18000b94b  jz      short loc_18000B97A
0x18000b94d  mov     rcx, [rbp+hKey]; hKey
0x18000b951  lea     rax, [rbp+cbData]
0x18000b955  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18000b95a  lea     r9, [rbp+Type]; lpType
0x18000b95e  lea     rax, [rbp+Data]
0x18000b962  xor     r8d, r8d; lpReserved
0x18000b965  lea     rdx, ValueName; "PipeVCBuffers"
0x18000b96c  mov     [rsp+68h+lpData], rax; lpData
0x18000b971  call    cs:__imp_RegQueryValueExW
0x18000b977  mov     [rbp+var_30], eax
0x18000b97a  test    eax, eax
0x18000b97c  jg      loc_18000BAE6
0x18000b982  mov     ecx, eax
0x18000b984  test    ecx, ecx
0x18000b986  jns     loc_18000BAFC
0x18000b98c  mov     [rbp+Data], 14h
0x18000b993  mov     [rbp+Type], edi
0x18000b996  mov     dword ptr [rbp+cbData], 4
0x18000b99d  mov     [rbp+arg_8], 10000h
0x18000b9a4  cmp     [rbp+var_2C], r12d
0x18000b9a8  jz      short loc_18000B9D7
0x18000b9aa  mov     rcx, [rbp+hKey]; hKey
0x18000b9ae  lea     rax, [rbp+cbData]
0x18000b9b2  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18000b9b7  lea     r9, [rbp+Type]; lpType
0x18000b9bb  lea     rax, [rbp+arg_8]
0x18000b9bf  xor     r8d, r8d; lpReserved
0x18000b9c2  lea     rdx, aPipevcbuffersi; "PipeVCBufferSize"
0x18000b9c9  mov     [rsp+68h+lpData], rax; lpData
0x18000b9ce  call    cs:__imp_RegQueryValueExW
0x18000b9d4  mov     [rbp+var_30], eax
0x18000b9d7  test    eax, eax
0x18000b9d9  jg      loc_18000BAF0
0x18000b9df  jns     loc_18000BE1F
0x18000b9e5  mov     [rbp+arg_8], 10000h
0x18000b9ec  mov     esi, r12d
0x18000b9ef  cmp     [rbp+var_1C], r12d
0x18000b9f3  jnz     loc_18000BE6E
0x18000b9f9  cmp     [rbp+var_2C], r12d
0x18000b9fd  jz      short loc_18000BA09
0x18000b9ff  mov     rcx, [rbp+hKey]; hKey
0x18000ba03  call    cs:__imp_RegCloseKey
0x18000ba09  mov     [rbp+hKey], r12
0x18000ba0d  mov     rcx, [rbp+Block]; Block
0x18000ba11  test    rcx, rcx
0x18000ba14  jnz     loc_18000BE8A
0x18000ba1a  mov     rax, cs:WPP_GLOBAL_Control
0x18000ba21  cmp     rax, r14
0x18000ba24  jnz     loc_18000BB0B
0x18000ba2a  mov     ebx, r12d
0x18000ba2d  cmp     ebx, [rbp+Data]
0x18000ba30  jge     short loc_18000BA78
0x18000ba32  mov     ecx, [rbp+arg_8]; Size
0x18000ba35  lea     rdx, [rbp+cbData]; struct CPipeReadQueueEntry **
0x18000ba39  mov     [rbp+cbData], r12
0x18000ba3d  call    ?CreateInstance@CPipeReadQueueEntry@@SAJKPEAPEAV1@@Z; CPipeReadQueueEntry::CreateInstance(ulong,CPipeReadQueueEntry * *)
0x18000ba42  mov     esi, eax
0x18000ba44  test    eax, eax
0x18000ba46  js      loc_18000BE94
0x18000ba4c  mov     r9, [r15+140h]
0x18000ba53  lea     rcx, [r15+138h]
0x18000ba5a  mov     rdx, [rbp+cbData]
0x18000ba5e  add     ebx, r13d
0x18000ba61  lea     r8, [rdx+50h]
0x18000ba65  mov     [r8], rcx
0x18000ba68  mov     [rdx+58h], r9
0x18000ba6c  mov     [r9], r8
0x18000ba6f  mov     [r15+140h], r8
0x18000ba76  jmp     short loc_18000BA2D
0x18000ba78  mov     ebx, 648h
0x18000ba7d  mov     [r15+0B0h], r12
0x18000ba84  mov     ecx, ebx; Size
0x18000ba86  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ba8b  mov     [r15+0B0h], rax
0x18000ba92  test    rax, rax
0x18000ba95  jz      loc_18000BEBD
0x18000ba9b  mov     r8d, ebx; Size
0x18000ba9e  xor     edx, edx; Val
0x18000baa0  mov     rcx, rax; void *
0x18000baa3  call    memset_0
0x18000baa8  or      dword ptr [r15-14h], 2
0x18000baad  mov     eax, esi
0x18000baaf  add     rsp, 68h
0x18000bab3  pop     r15
0x18000bab5  pop     r14
0x18000bab7  pop     r13
0x18000bab9  pop     r12
0x18000babb  pop     rdi
0x18000babc  pop     rsi
0x18000babd  pop     rbx
0x18000babe  pop     rbp
0x18000babf  retn
0x18000bac0  movzx   ecx, ax
0x18000bac3  or      ecx, ebx
0x18000bac5  jmp     loc_18000B922
0x18000baca  mov     rax, cs:WPP_GLOBAL_Control
0x18000bad1  cmp     rax, r14
0x18000bad4  jnz     loc_18000BE2E
0x18000bada  mov     [rbp+Data], 14h
0x18000bae1  jmp     loc_18000B9E5
0x18000bae6  movzx   ecx, ax
0x18000bae9  or      ecx, ebx
0x18000baeb  jmp     loc_18000B984
0x18000baf0  movzx   eax, ax
0x18000baf3  or      eax, ebx
0x18000baf5  test    eax, eax
0x18000baf7  jmp     loc_18000B9DF
0x18000bafc  cmp     [rbp+Data], r12d
0x18000bb00  jg      loc_18000B993
0x18000bb06  jmp     loc_18000B98C
0x18000bb0b  test    dword ptr [rax+1Ch], 800h
0x18000bb12  jz      loc_18000BA2A
0x18000bb18  cmp     byte ptr [rax+19h], 4
0x18000bb1c  jb      loc_18000BA2A
0x18000bb22  mov     ebx, [rbp+arg_8]
0x18000bb25  mov     edi, [rbp+Data]
0x18000bb28  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000bb2d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bb34  lea     r8, WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids
0x18000bb3b  mov     edx, 4Ah ; 'J'
0x18000bb40  mov     dword ptr [rsp+68h+lpcbData], ebx
0x18000bb44  mov     r9d, eax
0x18000bb47  mov     dword ptr [rsp+68h+lpData], edi
0x18000bb4b  mov     rcx, [rcx+10h]
0x18000bb4f  call    WPP_SF_DdD
0x18000bb54  jmp     loc_18000BA2A
0x18000bb59  call    cs:__imp_GetLastError
0x18000bb5f  mov     esi, eax
0x18000bb61  test    eax, eax
0x18000bb63  jg      short loc_18000BBAE
0x18000bb65  test    esi, esi
0x18000bb67  jns     loc_18000B850
0x18000bb6d  mov     rax, cs:WPP_GLOBAL_Control
0x18000bb74  lea     r14, WPP_GLOBAL_Control
0x18000bb7b  cmp     rax, r14
0x18000bb7e  jz      loc_18000BAAD
0x18000bb84  test    byte ptr [rax+1Ch], 8
0x18000bb88  jz      loc_18000BAAD
0x18000bb8e  cmp     byte ptr [rax+19h], 2
0x18000bb92  jb      loc_18000BAAD
0x18000bb98  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000bb9d  mov     edx, 42h ; 'B'
0x18000bba2  lea     rcx, aMObjlockInitia; "m_objLock.Initialize"
0x18000bba9  jmp     loc_18000BDDC
0x18000bbae  movzx   esi, ax
0x18000bbb1  or      esi, ebx
0x18000bbb3  jmp     short loc_18000BB65
0x18000bbb5  call    cs:__imp_GetLastError
0x18000bbbb  mov     esi, eax
0x18000bbbd  test    eax, eax
0x18000bbbf  jle     short loc_18000BBC6
0x18000bbc1  movzx   esi, ax
0x18000bbc4  or      esi, ebx
0x18000bbc6  test    esi, esi
0x18000bbc8  jns     loc_18000B864
0x18000bbce  mov     rax, cs:WPP_GLOBAL_Control
0x18000bbd5  lea     r14, WPP_GLOBAL_Control
0x18000bbdc  cmp     rax, r14
0x18000bbdf  jz      loc_18000BAAD
0x18000bbe5  test    byte ptr [rax+1Ch], 8
0x18000bbe9  jz      loc_18000BAAD
0x18000bbef  cmp     byte ptr [rax+19h], 2
0x18000bbf3  jb      loc_18000BAAD
0x18000bbf9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000bbfe  mov     edx, 43h ; 'C'
0x18000bc03  lea     rcx, aMPipewritequeu; "m_PipeWriteQueueLock.Initialize"
0x18000bc0a  jmp     loc_18000BDDC
0x18000bc0f  call    cs:__imp_GetLastError
0x18000bc15  mov     esi, eax
0x18000bc17  test    eax, eax
0x18000bc19  jle     short loc_18000BC20
0x18000bc1b  movzx   esi, ax
0x18000bc1e  or      esi, ebx
0x18000bc20  test    esi, esi
0x18000bc22  jns     loc_18000B886
0x18000bc28  mov     rax, cs:WPP_GLOBAL_Control
0x18000bc2f  lea     r14, WPP_GLOBAL_Control
0x18000bc36  cmp     rax, r14
0x18000bc39  jz      loc_18000BAAD
0x18000bc3f  test    byte ptr [rax+1Ch], 8
0x18000bc43  jz      loc_18000BAAD
0x18000bc49  cmp     byte ptr [rax+19h], 2
0x18000bc4d  jb      loc_18000BAAD
0x18000bc53  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000bc58  mov     edx, 44h ; 'D'
0x18000bc5d  lea     rcx, aFailedCreateev_5; "Failed CreateEvent call for m_hConnectP"...
0x18000bc64  jmp     loc_18000BDDC
0x18000bc69  call    cs:__imp_GetLastError
0x18000bc6f  mov     esi, eax
0x18000bc71  test    eax, eax
0x18000bc73  jle     short loc_18000BC7A
0x18000bc75  movzx   esi, ax
0x18000bc78  or      esi, ebx
0x18000bc7a  test    esi, esi
0x18000bc7c  jns     loc_18000B8A7
0x18000bc82  mov     rax, cs:WPP_GLOBAL_Control
0x18000bc89  lea     r14, WPP_GLOBAL_Control
0x18000bc90  cmp     rax, r14
0x18000bc93  jz      loc_18000BAAD
0x18000bc99  test    byte ptr [rax+1Ch], 8
0x18000bc9d  jz      loc_18000BAAD
0x18000bca3  cmp     byte ptr [rax+19h], 2
0x18000bca7  jb      loc_18000BAAD
0x18000bcad  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000bcb2  mov     edx, 45h ; 'E'
0x18000bcb7  lea     rcx, aFailedCreateev_4; "Failed CreateEvent call for m_hReadCall"...
0x18000bcbe  jmp     loc_18000BDDC
0x18000bcc3  call    cs:__imp_GetLastError
0x18000bcc9  mov     esi, eax
0x18000bccb  test    eax, eax
0x18000bccd  jle     short loc_18000BCD4
0x18000bccf  movzx   esi, ax
0x18000bcd2  or      esi, ebx
0x18000bcd4  test    esi, esi
0x18000bcd6  jns     loc_18000B8C8
0x18000bcdc  mov     rax, cs:WPP_GLOBAL_Control
0x18000bce3  lea     r14, WPP_GLOBAL_Control
0x18000bcea  cmp     rax, r14
0x18000bced  jz      loc_18000BAAD
0x18000bcf3  test    byte ptr [rax+1Ch], 8
0x18000bcf7  jz      loc_18000BAAD
0x18000bcfd  cmp     byte ptr [rax+19h], 2
0x18000bd01  jb      loc_18000BAAD
0x18000bd07  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
  ... truncated ...
```
