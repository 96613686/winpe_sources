# GetStateSeparatedSiufLocFilesPath(ushort * *)

- ea: `0x1400175e8`
- end: `0x140017769`
- name: `?GetStateSeparatedSiufLocFilesPath@@YAJPEAPEAG@Z`
- size: `385`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x140017468`

## callees

- `0x140001d68`
- `0x14000b5c4`
- `0x1400175e8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140017635`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140017660`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140017635`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140017660`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001761f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001764f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400176fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001771a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001761f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001764f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400176fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001771a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001770b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140017728`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001770b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140017728`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400176f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400176f2`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedFileLocationW` at `0x1400176d3`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedFileLocationW` at `0x1400176d3`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x14001767f`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x14001767f`

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
    v13 = dword_140027000;
    *a1 = v4;
    if ( v13 > 5 )
    {
      v17 = v4;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        v10,
        (unsigned int)&word_140022EBE,
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
0x1400175e8  mov     [rsp+arg_18], rbx
0x1400175ed  push    rsi
0x1400175ee  push    rdi
0x1400175ef  push    r14
0x1400175f1  sub     rsp, 30h
0x1400175f5  mov     [rsp+48h+ppszPath], 0
0x1400175fe  mov     r14, rcx
0x140017601  mov     [rsp+48h+arg_0], 0
0x140017609  test    rcx, rcx
0x14001760c  jnz     short loc_140017618
0x14001760e  mov     ebx, 80004003h
0x140017613  jmp     loc_140017759
0x140017618  mov     qword ptr [rcx], 0
0x14001761f  call    cs:__imp_GetProcessHeap
0x140017625  mov     ebx, 8
0x14001762a  mov     r8d, 208h; dwBytes
0x140017630  mov     rcx, rax; hHeap
0x140017633  mov     edx, ebx; dwFlags
0x140017635  call    cs:__imp_HeapAlloc
0x14001763b  mov     rdi, rax
0x14001763e  test    rax, rax
0x140017641  jnz     short loc_14001764F
0x140017643  xor     esi, esi
0x140017645  mov     ebx, 8007000Eh
0x14001764a  jmp     loc_1400176E8
0x14001764f  call    cs:__imp_GetProcessHeap
0x140017655  mov     r8d, 208h; dwBytes
0x14001765b  mov     edx, ebx; dwFlags
0x14001765d  mov     rcx, rax; hHeap
0x140017660  call    cs:__imp_HeapAlloc
0x140017666  mov     rsi, rax
0x140017669  test    rax, rax
0x14001766c  jz      short loc_140017645
0x14001766e  lea     r9, [rsp+48h+ppszPath]; ppszPath
0x140017673  xor     r8d, r8d; hToken
0x140017676  xor     edx, edx; dwFlags
0x140017678  lea     rcx, FOLDERID_ProgramData; rfid
0x14001767f  call    cs:__imp_SHGetKnownFolderPath
0x140017685  mov     ebx, eax
0x140017687  test    eax, eax
0x140017689  js      short loc_1400176E8
0x14001768b  mov     r9, [rsp+48h+ppszPath]
0x140017690  lea     rax, aMicrosoftDiagn_0; "microsoft\\diagnosis\\siufloc"
0x140017697  lea     r8, aSS_0; "%s\\%s"
0x14001769e  mov     [rsp+48h+var_28], rax
0x1400176a3  mov     edx, 104h; unsigned __int64
0x1400176a8  mov     rcx, rsi; unsigned __int16 *
0x1400176ab  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400176b0  mov     ebx, eax
0x1400176b2  test    eax, eax
0x1400176b4  js      short loc_1400176E8
0x1400176b6  lea     rax, [rsp+48h+arg_0]
0x1400176bb  mov     r9d, 208h
0x1400176c1  mov     r8, rdi
0x1400176c4  mov     [rsp+48h+var_28], rax
0x1400176c9  mov     rdx, rsi
0x1400176cc  lea     rcx, aSiuflocfileroo; "siuflocfileroot"
0x1400176d3  call    cs:__imp_GetPersistedFileLocationW
0x1400176d9  mov     ebx, eax
0x1400176db  test    eax, eax
0x1400176dd  jle     short loc_1400176E8
0x1400176df  movzx   ebx, ax
0x1400176e2  or      ebx, 80070000h
0x1400176e8  mov     rcx, [rsp+48h+ppszPath]; pv
0x1400176ed  test    rcx, rcx
0x1400176f0  jz      short loc_1400176F8
0x1400176f2  call    cs:__imp_CoTaskMemFree
0x1400176f8  test    rsi, rsi
0x1400176fb  jz      short loc_140017711
0x1400176fd  call    cs:__imp_GetProcessHeap
0x140017703  mov     r8, rsi; lpMem
0x140017706  xor     edx, edx; dwFlags
0x140017708  mov     rcx, rax; hHeap
0x14001770b  call    cs:__imp_HeapFree
0x140017711  test    ebx, ebx
0x140017713  jns     short loc_140017730
0x140017715  test    rdi, rdi
0x140017718  jz      short loc_140017759
0x14001771a  call    cs:__imp_GetProcessHeap
0x140017720  mov     r8, rdi; lpMem
0x140017723  xor     edx, edx; dwFlags
0x140017725  mov     rcx, rax; hHeap
0x140017728  call    cs:__imp_HeapFree
0x14001772e  jmp     short loc_140017759
0x140017730  mov     eax, cs:dword_140027000
0x140017736  mov     [r14], rdi
0x140017739  cmp     eax, 5
0x14001773c  jbe     short loc_140017759
0x14001773e  lea     rax, [rsp+48h+arg_10]
0x140017743  mov     [rsp+48h+arg_10], rdi
0x140017748  lea     rdx, word_140022EBE
0x14001774f  mov     [rsp+48h+var_28], rax
0x140017754  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x140017759  mov     eax, ebx
0x14001775b  mov     rbx, [rsp+48h+arg_18]
0x140017760  add     rsp, 30h
0x140017764  pop     r14
0x140017766  pop     rdi
0x140017767  pop     rsi
0x140017768  retn
```
