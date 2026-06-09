# GetStateSeparatedSiufLocFilesPath(ushort * *)

- ea: `0x1400153dc`
- end: `0x1400155a0`
- name: `?GetStateSeparatedSiufLocFilesPath@@YAJPEAPEAG@Z`
- size: `452`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x14001522c`

## callees

- `0x140001d80`
- `0x14000b904`
- `0x1400153dc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001542f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140015466`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001542f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140015466`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015413`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001544f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001551b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015544`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015413`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001544f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001551b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015544`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001552f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015558`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001552f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015558`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001550a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001550a`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedFileLocationW` at `0x1400154e5`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedFileLocationW` at `0x1400154e5`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x14001548b`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x14001548b`

## pseudocode

```c
__int64 __fastcall GetStateSeparatedSiufLocFilesPath(unsigned __int16 **a1)
{
  int v2; // ebx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v4; // rdi
  int v5; // r8d
  int v6; // r9d
  unsigned __int16 *v7; // rsi
  HANDLE v8; // rax
  int PersistedFileLocationW; // eax
  int v10; // ecx
  HANDLE v11; // rax
  HANDLE v12; // rax
  unsigned int v13; // eax
  int v15; // [rsp+50h] [rbp+8h] BYREF
  PWSTR ppszPath; // [rsp+58h] [rbp+10h] BYREF
  unsigned __int16 *v17; // [rsp+60h] [rbp+18h] BYREF

  ppszPath = 0;
  v15 = 0;
  if ( !a1 )
    return (unsigned int)-2147467261;
  *a1 = 0;
  ProcessHeap = GetProcessHeap();
  v4 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 0x208u);
  if ( v4 )
  {
    v8 = GetProcessHeap();
    v7 = (unsigned __int16 *)HeapAlloc(v8, 8u, 0x208u);
    if ( v7 )
    {
      v2 = SHGetKnownFolderPath(&FOLDERID_ProgramData, 0, 0, &ppszPath);
      if ( v2 >= 0 )
      {
        v2 = StringCchPrintfW(v7, 0x104u, L"%s\\%s", ppszPath, L"microsoft\\diagnosis\\siufloc");
        if ( v2 >= 0 )
        {
          PersistedFileLocationW = GetPersistedFileLocationW(L"siuflocfileroot", v7, v4, 520, &v15);
          v2 = PersistedFileLocationW;
          if ( PersistedFileLocationW > 0 )
            v2 = (unsigned __int16)PersistedFileLocationW | 0x80070000;
        }
      }
      goto LABEL_11;
    }
  }
  else
  {
    v7 = 0;
  }
  v2 = -2147024882;
LABEL_11:
  v10 = (int)ppszPath;
  if ( ppszPath )
    CoTaskMemFree(ppszPath);
  if ( v7 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v7);
  }
  if ( v2 >= 0 )
  {
    v13 = dword_140028000;
    *a1 = v4;
    if ( v13 > 5 )
    {
      v17 = v4;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        v10,
        (unsigned int)&word_140023EC6,
        v5,
        v6,
        (__int64)&v17);
    }
  }
  else if ( v4 )
  {
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v4);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400153dc  mov     [rsp+arg_18], rbx
0x1400153e1  push    rsi
0x1400153e2  push    rdi
0x1400153e3  push    r14
0x1400153e5  sub     rsp, 30h
0x1400153e9  mov     [rsp+48h+ppszPath], 0
0x1400153f2  mov     r14, rcx
0x1400153f5  mov     [rsp+48h+arg_0], 0
0x1400153fd  test    rcx, rcx
0x140015400  jnz     short loc_14001540C
0x140015402  mov     ebx, 80004003h
0x140015407  jmp     loc_14001558F
0x14001540c  mov     qword ptr [rcx], 0
0x140015413  call    cs:__imp_GetProcessHeap
0x14001541a  nop     dword ptr [rax+rax+00h]
0x14001541f  mov     ebx, 8
0x140015424  mov     r8d, 208h; dwBytes
0x14001542a  mov     rcx, rax; hHeap
0x14001542d  mov     edx, ebx; dwFlags
0x14001542f  call    cs:__imp_HeapAlloc
0x140015436  nop     dword ptr [rax+rax+00h]
0x14001543b  mov     rdi, rax
0x14001543e  test    rax, rax
0x140015441  jnz     short loc_14001544F
0x140015443  xor     esi, esi
0x140015445  mov     ebx, 8007000Eh
0x14001544a  jmp     loc_140015500
0x14001544f  call    cs:__imp_GetProcessHeap
0x140015456  nop     dword ptr [rax+rax+00h]
0x14001545b  mov     r8d, 208h; dwBytes
0x140015461  mov     edx, ebx; dwFlags
0x140015463  mov     rcx, rax; hHeap
0x140015466  call    cs:__imp_HeapAlloc
0x14001546d  nop     dword ptr [rax+rax+00h]
0x140015472  mov     rsi, rax
0x140015475  test    rax, rax
0x140015478  jz      short loc_140015445
0x14001547a  lea     r9, [rsp+48h+ppszPath]; ppszPath
0x14001547f  xor     r8d, r8d; hToken
0x140015482  xor     edx, edx; dwFlags
0x140015484  lea     rcx, FOLDERID_ProgramData; rfid
0x14001548b  call    cs:__imp_SHGetKnownFolderPath
0x140015492  nop     dword ptr [rax+rax+00h]
0x140015497  mov     ebx, eax
0x140015499  test    eax, eax
0x14001549b  js      short loc_140015500
0x14001549d  mov     r9, [rsp+48h+ppszPath]
0x1400154a2  lea     rax, aMicrosoftDiagn_0; "microsoft\\diagnosis\\siufloc"
0x1400154a9  lea     r8, aSS_0; "%s\\%s"
0x1400154b0  mov     [rsp+48h+var_28], rax
0x1400154b5  mov     edx, 104h; unsigned __int64
0x1400154ba  mov     rcx, rsi; unsigned __int16 *
0x1400154bd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400154c2  mov     ebx, eax
0x1400154c4  test    eax, eax
0x1400154c6  js      short loc_140015500
0x1400154c8  lea     rax, [rsp+48h+arg_0]
0x1400154cd  mov     r9d, 208h
0x1400154d3  mov     r8, rdi
0x1400154d6  mov     [rsp+48h+var_28], rax
0x1400154db  mov     rdx, rsi
0x1400154de  lea     rcx, aSiuflocfileroo; "siuflocfileroot"
0x1400154e5  call    cs:__imp_GetPersistedFileLocationW
0x1400154ec  nop     dword ptr [rax+rax+00h]
0x1400154f1  mov     ebx, eax
0x1400154f3  test    eax, eax
0x1400154f5  jle     short loc_140015500
0x1400154f7  movzx   ebx, ax
0x1400154fa  or      ebx, 80070000h
0x140015500  mov     rcx, [rsp+48h+ppszPath]; pv
0x140015505  test    rcx, rcx
0x140015508  jz      short loc_140015516
0x14001550a  call    cs:__imp_CoTaskMemFree
0x140015511  nop     dword ptr [rax+rax+00h]
0x140015516  test    rsi, rsi
0x140015519  jz      short loc_14001553B
0x14001551b  call    cs:__imp_GetProcessHeap
0x140015522  nop     dword ptr [rax+rax+00h]
0x140015527  mov     r8, rsi; lpMem
0x14001552a  xor     edx, edx; dwFlags
0x14001552c  mov     rcx, rax; hHeap
0x14001552f  call    cs:__imp_HeapFree
0x140015536  nop     dword ptr [rax+rax+00h]
0x14001553b  test    ebx, ebx
0x14001553d  jns     short loc_140015566
0x14001553f  test    rdi, rdi
0x140015542  jz      short loc_14001558F
0x140015544  call    cs:__imp_GetProcessHeap
0x14001554b  nop     dword ptr [rax+rax+00h]
0x140015550  mov     r8, rdi; lpMem
0x140015553  xor     edx, edx; dwFlags
0x140015555  mov     rcx, rax; hHeap
0x140015558  call    cs:__imp_HeapFree
0x14001555f  nop     dword ptr [rax+rax+00h]
0x140015564  jmp     short loc_14001558F
0x140015566  mov     eax, cs:dword_140028000
0x14001556c  mov     [r14], rdi
0x14001556f  cmp     eax, 5
0x140015572  jbe     short loc_14001558F
0x140015574  lea     rax, [rsp+48h+arg_10]
0x140015579  mov     [rsp+48h+arg_10], rdi
0x14001557e  lea     rdx, word_140023EC6
0x140015585  mov     [rsp+48h+var_28], rax
0x14001558a  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x14001558f  mov     eax, ebx
0x140015591  mov     rbx, [rsp+48h+arg_18]
0x140015596  add     rsp, 30h
0x14001559a  pop     r14
0x14001559c  pop     rdi
0x14001559d  pop     rsi
0x14001559e  retn
```
