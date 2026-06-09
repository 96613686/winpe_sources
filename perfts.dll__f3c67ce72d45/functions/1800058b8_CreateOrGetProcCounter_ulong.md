# CreateOrGetProcCounter(ulong)

- ea: `0x1800058b8`
- end: `0x180005bc3`
- name: `?CreateOrGetProcCounter@@YAPEAVCounterHelper@@K@Z`
- size: `779`
- prototype: `struct CounterHelper *__fastcall(DWORD dwProcessId)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x180005be0`
- `0x180007668`
- `0x180007b10`

## callees

- `0x180001140`
- `0x180001da8`
- `0x1800047c4`
- `0x1800047fc`
- `0x180004be0`
- `0x1800058b8`
- `0x180008af0`
- `0x180009930`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180005a10`
- `msvcrt!wcsrchr` at `0x180005a10`
- `KERNEL32!CreateMutexW` at `0x180005ae4`
- `KERNEL32!CreateMutexW` at `0x180005ae4`
- `KERNEL32!WaitForSingleObject` at `0x180005af7`
- `KERNEL32!WaitForSingleObject` at `0x180005af7`
- `KERNEL32!ReleaseMutex` at `0x180005b81`
- `KERNEL32!ReleaseMutex` at `0x180005b81`
- `KERNEL32!OpenProcess` at `0x18000594a`
- `KERNEL32!OpenProcess` at `0x1800059d3`
- `KERNEL32!OpenProcess` at `0x18000594a`
- `KERNEL32!OpenProcess` at `0x1800059d3`
- `KERNEL32!ProcessIdToSessionId` at `0x18000595f`
- `KERNEL32!ProcessIdToSessionId` at `0x18000595f`
- `KERNEL32!CloseHandle` at `0x180005ac9`
- `KERNEL32!CloseHandle` at `0x180005b94`
- `KERNEL32!CloseHandle` at `0x180005ac9`
- `KERNEL32!CloseHandle` at `0x180005b94`
- `KERNEL32!QueryFullProcessImageNameW` at `0x1800059f6`
- `KERNEL32!QueryFullProcessImageNameW` at `0x1800059f6`

## pseudocode

```c
struct CounterHelper *__fastcall CreateOrGetProcCounter(DWORD dwProcessId)
{
  __int64 v1; // rbx
  __int64 v2; // rcx
  __int64 v3; // rax
  int v5; // esi
  HANDLE v6; // rdi
  int v7; // r8d
  int v8; // r9d
  wchar_t *v9; // r14
  const wchar_t *v10; // rdx
  HANDLE MutexW; // rax
  __int64 v12; // rdi
  __int64 v13; // rcx
  __int64 v14; // rax
  const char *v15; // rax
  __int64 v16; // [rsp+20h] [rbp-E0h]
  __int64 v17; // [rsp+28h] [rbp-D8h]
  DWORD pSessionId; // [rsp+30h] [rbp-D0h] BYREF
  DWORD dwSize; // [rsp+34h] [rbp-CCh] BYREF
  int v20; // [rsp+38h] [rbp-C8h] BYREF
  const char *v21; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v22; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v23[264]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v24[528]; // [rsp+260h] [rbp+160h] BYREF
  WCHAR ExeName[264]; // [rsp+470h] [rbp+370h] BYREF

  v1 = dwProcessId;
  v2 = CounterHelper::ProcessesToCounter;
  v20 = v1;
  v3 = *(_QWORD *)(CounterHelper::ProcessesToCounter + 8);
  while ( !*(_BYTE *)(v3 + 25) )
  {
    if ( *(_DWORD *)(v3 + 32) >= (unsigned int)v1 )
    {
      v2 = v3;
      v3 = *(_QWORD *)v3;
    }
    else
    {
      v3 = *(_QWORD *)(v3 + 16);
    }
  }
  if ( v2 == CounterHelper::ProcessesToCounter || (unsigned int)v1 < *(_DWORD *)(v2 + 32) )
    v2 = CounterHelper::ProcessesToCounter;
  if ( v2 != CounterHelper::ProcessesToCounter )
    return *(struct CounterHelper **)(v2 + 40);
  pSessionId = 0;
  dwSize = 259;
  v5 = 0;
  v6 = OpenProcess(0x400u, 0, v1);
  if ( v6 )
  {
    if ( ProcessIdToSessionId(v1, &pSessionId) )
    {
      v5 = 1;
    }
    else
    {
      if ( (unsigned int)dword_180012020 > 2 )
      {
        v22 = v1;
        v21 = "LagCounter->CounterHelper: Couldn't resolve process ID to Session";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          dword_180012020,
          (unsigned int)&unk_18000F598,
          v7,
          v8,
          (__int64)&v21,
          (__int64)&v22);
      }
      pSessionId = 0;
      if ( !CounterHelper::LagCounterShowUnknown )
        goto LABEL_49;
    }
  }
  else
  {
    if ( !CounterHelper::LagCounterShowUnknown )
      return 0;
    v6 = OpenProcess(0x1000u, 0, v1);
    if ( !v6 )
    {
LABEL_27:
      if ( CounterHelper::LagCounterShowUnknown )
      {
        v10 = L"%u <Unknown>";
        if ( !CounterHelper::LagCounterImageNameFirst )
          v10 = L"Unknown <%u>";
        swprintf_s<260>(v23, v10, (unsigned int)v1);
        goto LABEL_31;
      }
      if ( v6 )
LABEL_49:
        CloseHandle(v6);
      return 0;
    }
  }
  if ( !QueryFullProcessImageNameW(v6, 0, ExeName, &dwSize) )
    goto LABEL_27;
  v9 = wcsrchr(ExeName, 0x5Cu) + 1;
  if ( v5 )
    swprintf_s<260>(v24, L"%u", pSessionId);
  else
    swprintf_s<260>(v24, L"?");
  if ( CounterHelper::LagCounterImageNameFirst )
  {
    LODWORD(v17) = v1;
    StringCchPrintfW(v23, dwSize, L"%s <%s:%u>", v9, v24, v17);
  }
  else
  {
    LODWORD(v16) = v1;
    StringCchPrintfW(v23, dwSize, L"%s:%u <%s>", v24, v16, v9);
  }
LABEL_31:
  if ( v6 )
    CloseHandle(v6);
  MutexW = CounterHelper::LagCounterMajorEvent;
  v12 = 0;
  if ( !CounterHelper::LagCounterMajorEvent )
  {
    MutexW = CreateMutexW(0, 0, 0);
    CounterHelper::LagCounterMajorEvent = MutexW;
  }
  WaitForSingleObject(MutexW, 0xFFFFFFFF);
  v13 = CounterHelper::ProcessesToCounter;
  v14 = *(_QWORD *)(CounterHelper::ProcessesToCounter + 8);
  while ( !*(_BYTE *)(v14 + 25) )
  {
    if ( *(_DWORD *)(v14 + 32) >= (unsigned int)v1 )
    {
      v13 = v14;
      v14 = *(_QWORD *)v14;
    }
    else
    {
      v14 = *(_QWORD *)(v14 + 16);
    }
  }
  if ( v13 == CounterHelper::ProcessesToCounter || (unsigned int)v1 < *(_DWORD *)(v13 + 32) )
    v13 = CounterHelper::ProcessesToCounter;
  if ( v13 == CounterHelper::ProcessesToCounter )
  {
    v15 = (const char *)operator new(0x1B0u);
    v21 = v15;
    if ( v15 )
      v12 = CounterHelper::CounterHelper(v15, v23, 0);
    *(_QWORD *)std::map<unsigned long,CounterHelper *>::operator[](&CounterHelper::ProcessesToCounter, &v20) = v12;
  }
  ReleaseMutex(CounterHelper::LagCounterMajorEvent);
  return (struct CounterHelper *)v12;
}

```

## disassembly

```asm
0x1800058b8  mov     [rsp-8+arg_8], rbx
0x1800058bd  mov     [rsp-8+arg_10], rsi
0x1800058c2  push    rbp
0x1800058c3  push    rdi
0x1800058c4  push    r14
0x1800058c6  lea     rbp, [rsp-590h]
0x1800058ce  sub     rsp, 690h
0x1800058d5  mov     rax, cs:__security_cookie
0x1800058dc  xor     rax, rsp
0x1800058df  mov     [rbp+5A0h+var_20], rax
0x1800058e6  mov     rdx, cs:?ProcessesToCounter@CounterHelper@@2V?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@A; std::map<ulong,CounterHelper *> CounterHelper::ProcessesToCounter
0x1800058ed  mov     ebx, ecx
0x1800058ef  mov     rcx, rdx
0x1800058f2  mov     [rsp+6A0h+var_668], ebx
0x1800058f6  mov     rax, [rdx+8]
0x1800058fa  jmp     short loc_18000590D
0x1800058fc  cmp     [rax+20h], ebx
0x1800058ff  jnb     short loc_180005907
0x180005901  mov     rax, [rax+10h]
0x180005905  jmp     short loc_18000590D
0x180005907  mov     rcx, rax
0x18000590a  mov     rax, [rax]
0x18000590d  cmp     byte ptr [rax+19h], 0
0x180005911  jz      short loc_1800058FC
0x180005913  cmp     rcx, rdx
0x180005916  jz      short loc_18000591D
0x180005918  cmp     ebx, [rcx+20h]
0x18000591b  jnb     short loc_180005920
0x18000591d  mov     rcx, rdx
0x180005920  cmp     rcx, rdx
0x180005923  jz      short loc_18000592E
0x180005925  mov     rax, [rcx+28h]
0x180005929  jmp     loc_180005B9C
0x18000592e  mov     r8d, ebx; dwProcessId
0x180005931  mov     [rsp+6A0h+pSessionId], 0
0x180005939  xor     edx, edx; bInheritHandle
0x18000593b  mov     [rsp+6A0h+dwSize], 103h
0x180005943  mov     ecx, 400h; dwDesiredAccess
0x180005948  xor     esi, esi
0x18000594a  call    cs:__imp_OpenProcess
0x180005950  mov     rdi, rax
0x180005953  test    rax, rax
0x180005956  jz      short loc_1800059BD
0x180005958  lea     rdx, [rsp+6A0h+pSessionId]; pSessionId
0x18000595d  mov     ecx, ebx; dwProcessId
0x18000595f  call    cs:__imp_ProcessIdToSessionId
0x180005965  test    eax, eax
0x180005967  jnz     short loc_1800059B6
0x180005969  mov     ecx, cs:dword_180012020
0x18000596f  cmp     ecx, 2
0x180005972  jbe     short loc_1800059A5
0x180005974  lea     rax, aLagcounterCoun; "LagCounter->CounterHelper: Couldn't res"...
0x18000597b  mov     [rsp+6A0h+var_658], rbx
0x180005980  mov     [rsp+6A0h+var_660], rax
0x180005985  lea     rdx, unk_18000F598
0x18000598c  lea     rax, [rsp+6A0h+var_658]
0x180005991  mov     [rsp+6A0h+var_678], rax
0x180005996  lea     rax, [rsp+6A0h+var_660]
0x18000599b  mov     [rsp+6A0h+var_680], rax
0x1800059a0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x1800059a5  cmp     cs:?LagCounterShowUnknown@CounterHelper@@2HA, esi; int CounterHelper::LagCounterShowUnknown
0x1800059ab  mov     [rsp+6A0h+pSessionId], esi
0x1800059af  jnz     short loc_1800059E5
0x1800059b1  jmp     loc_180005B91
0x1800059b6  mov     esi, 1
0x1800059bb  jmp     short loc_1800059E5
0x1800059bd  cmp     cs:?LagCounterShowUnknown@CounterHelper@@2HA, esi; int CounterHelper::LagCounterShowUnknown
0x1800059c3  jz      loc_180005B9A
0x1800059c9  mov     r8d, ebx; dwProcessId
0x1800059cc  xor     edx, edx; bInheritHandle
0x1800059ce  mov     ecx, 1000h; dwDesiredAccess
0x1800059d3  call    cs:__imp_OpenProcess
0x1800059d9  mov     rdi, rax
0x1800059dc  test    rax, rax
0x1800059df  jz      loc_180005A90
0x1800059e5  lea     r9, [rsp+6A0h+dwSize]; lpdwSize
0x1800059ea  xor     edx, edx; dwFlags
0x1800059ec  lea     r8, [rbp+5A0h+ExeName]; lpExeName
0x1800059f3  mov     rcx, rdi; hProcess
0x1800059f6  call    cs:__imp_QueryFullProcessImageNameW
0x1800059fc  test    eax, eax
0x1800059fe  jz      loc_180005A90
0x180005a04  mov     edx, 5Ch ; '\'; Ch
0x180005a09  lea     rcx, [rbp+5A0h+ExeName]; Str
0x180005a10  call    cs:__imp_wcsrchr
0x180005a16  lea     rcx, [rbp+5A0h+var_440]
0x180005a1d  lea     r14, [rax+2]
0x180005a21  test    esi, esi
0x180005a23  jnz     short loc_180005A33
0x180005a25  lea     rdx, asc_18000E1E4; "?"
0x180005a2c  call    ??$swprintf_s@$0BAE@@@YAHAEAY0BAE@GPEBGZZ; swprintf_s<260>(ushort (&)[260],ushort const *,...)
0x180005a31  jmp     short loc_180005A44
0x180005a33  mov     r8d, [rsp+6A0h+pSessionId]
0x180005a38  lea     rdx, aU; "%u"
0x180005a3f  call    ??$swprintf_s@$0BAE@@@YAHAEAY0BAE@GPEBGZZ; swprintf_s<260>(ushort (&)[260],ushort const *,...)
0x180005a44  cmp     cs:?LagCounterImageNameFirst@CounterHelper@@2HA, 0; int CounterHelper::LagCounterImageNameFirst
0x180005a4b  lea     rcx, [rsp+6A0h+var_650]; unsigned __int16 *
0x180005a50  mov     edx, [rsp+6A0h+dwSize]; unsigned __int64
0x180005a54  jz      short loc_180005A72
0x180005a56  lea     rax, [rbp+5A0h+var_440]
0x180005a5d  mov     dword ptr [rsp+6A0h+var_678], ebx
0x180005a61  mov     [rsp+6A0h+var_680], rax
0x180005a66  lea     r8, aSSU; "%s <%s:%u>"
0x180005a6d  mov     r9, r14
0x180005a70  jmp     short loc_180005A89
0x180005a72  mov     [rsp+6A0h+var_678], r14
0x180005a77  lea     r9, [rbp+5A0h+var_440]
0x180005a7e  mov     dword ptr [rsp+6A0h+var_680], ebx
0x180005a82  lea     r8, aSUS; "%s:%u <%s>"
0x180005a89  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005a8e  jmp     short loc_180005AC1
0x180005a90  cmp     cs:?LagCounterShowUnknown@CounterHelper@@2HA, 0; int CounterHelper::LagCounterShowUnknown
0x180005a97  jz      loc_180005B8C
0x180005a9d  cmp     cs:?LagCounterImageNameFirst@CounterHelper@@2HA, 0; int CounterHelper::LagCounterImageNameFirst
0x180005aa4  lea     rcx, [rsp+6A0h+var_650]
0x180005aa9  mov     r8d, ebx
0x180005aac  lea     rdx, aUUnknown; "%u <Unknown>"
0x180005ab3  jnz     short loc_180005ABC
0x180005ab5  lea     rdx, aUnknownU; "Unknown <%u>"
0x180005abc  call    ??$swprintf_s@$0BAE@@@YAHAEAY0BAE@GPEBGZZ; swprintf_s<260>(ushort (&)[260],ushort const *,...)
0x180005ac1  test    rdi, rdi
0x180005ac4  jz      short loc_180005ACF
0x180005ac6  mov     rcx, rdi; hObject
0x180005ac9  call    cs:__imp_CloseHandle
0x180005acf  mov     rax, cs:?LagCounterMajorEvent@CounterHelper@@2PEAXEA; void * CounterHelper::LagCounterMajorEvent
0x180005ad6  xor     edi, edi
0x180005ad8  test    rax, rax
0x180005adb  jnz     short loc_180005AF1
0x180005add  xor     r8d, r8d; lpName
0x180005ae0  xor     edx, edx; bInitialOwner
0x180005ae2  xor     ecx, ecx; lpMutexAttributes
0x180005ae4  call    cs:__imp_CreateMutexW
0x180005aea  mov     cs:?LagCounterMajorEvent@CounterHelper@@2PEAXEA, rax; void * CounterHelper::LagCounterMajorEvent
0x180005af1  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180005af4  mov     rcx, rax; hHandle
0x180005af7  call    cs:__imp_WaitForSingleObject
0x180005afd  mov     rdx, cs:?ProcessesToCounter@CounterHelper@@2V?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@A; std::map<ulong,CounterHelper *> CounterHelper::ProcessesToCounter
0x180005b04  mov     rcx, rdx
0x180005b07  mov     rax, [rdx+8]
0x180005b0b  jmp     short loc_180005B1E
0x180005b0d  cmp     [rax+20h], ebx
0x180005b10  jnb     short loc_180005B18
0x180005b12  mov     rax, [rax+10h]
0x180005b16  jmp     short loc_180005B1E
0x180005b18  mov     rcx, rax
0x180005b1b  mov     rax, [rax]
0x180005b1e  cmp     [rax+19h], dil
0x180005b22  jz      short loc_180005B0D
0x180005b24  cmp     rcx, rdx
0x180005b27  jz      short loc_180005B2E
0x180005b29  cmp     ebx, [rcx+20h]
0x180005b2c  jnb     short loc_180005B31
0x180005b2e  mov     rcx, rdx
0x180005b31  cmp     rcx, rdx
0x180005b34  jnz     short loc_180005B7A
0x180005b36  mov     ecx, 1B0h; Size
0x180005b3b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005b40  mov     [rsp+6A0h+var_660], rax
0x180005b45  test    rax, rax
0x180005b48  jz      short loc_180005B66
0x180005b4a  mov     r9d, [rsp+6A0h+pSessionId]
0x180005b4f  lea     rdx, [rsp+6A0h+var_650]
0x180005b54  xor     r8d, r8d
0x180005b57  mov     dword ptr [rsp+6A0h+var_680], ebx
0x180005b5b  mov     rcx, rax
0x180005b5e  call    ??0CounterHelper@@QEAA@PEAGW4COUNTER_HELPER_TYPE@@KK@Z; CounterHelper::CounterHelper(ushort *,COUNTER_HELPER_TYPE,ulong,ulong)
0x180005b63  mov     rdi, rax
0x180005b66  lea     rdx, [rsp+6A0h+var_668]
0x180005b6b  lea     rcx, ?ProcessesToCounter@CounterHelper@@2V?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@A; std::map<ulong,CounterHelper *> CounterHelper::ProcessesToCounter
0x180005b72  call    ??A?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@QEAAAEAPEAVCounterHelper@@AEBK@Z; std::map<ulong,CounterHelper *>::operator[](ulong const &)
0x180005b77  mov     [rax], rdi
0x180005b7a  mov     rcx, cs:?LagCounterMajorEvent@CounterHelper@@2PEAXEA; hMutex
0x180005b81  call    cs:__imp_ReleaseMutex
0x180005b87  mov     rax, rdi
0x180005b8a  jmp     short loc_180005B9C
0x180005b8c  test    rdi, rdi
0x180005b8f  jz      short loc_180005B9A
0x180005b91  mov     rcx, rdi; hObject
0x180005b94  call    cs:__imp_CloseHandle
0x180005b9a  xor     eax, eax
0x180005b9c  mov     rcx, [rbp+5A0h+var_20]
0x180005ba3  xor     rcx, rsp; StackCookie
0x180005ba6  call    __security_check_cookie
0x180005bab  lea     r11, [rsp+6A0h+var_10]
0x180005bb3  mov     rbx, [r11+28h]
0x180005bb7  mov     rsi, [r11+30h]
0x180005bbb  mov     rsp, r11
0x180005bbe  pop     r14
0x180005bc0  pop     rdi
0x180005bc1  pop     rbp
0x180005bc2  retn
```
