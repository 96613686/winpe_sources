# GetDiagTrackStorePath(ushort * *)

- ea: `0x14001505c`
- end: `0x140015223`
- name: `?GetDiagTrackStorePath@@YAJPEAPEAG@Z`
- size: `455`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000ee98`
- `0x140014e08`

## callees

- `0x140001d80`
- `0x14000b904`
- `0x14001505c`
- `0x1400195e2`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001511f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001511f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400150b5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400150b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001509b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400151c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001509b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400151c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400151d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400151d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400151ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400151ae`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x14001516b`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x14001516b`

## pseudocode

```c
__int64 __fastcall GetDiagTrackStorePath(unsigned __int16 **a1)
{
  int v2; // ebx
  HANDLE ProcessHeap; // rax
  void *v4; // rax
  int v5; // r8d
  int v6; // r9d
  void *pvData; // rdi
  LSTATUS ValueW; // eax
  bool v9; // sf
  int v10; // ecx
  HANDLE v11; // rax
  DWORD pcbData; // [rsp+40h] [rbp-28h] BYREF
  DWORD pdwType; // [rsp+44h] [rbp-24h] BYREF
  PWSTR ppszPath; // [rsp+48h] [rbp-20h] BYREF
  void *v16; // [rsp+50h] [rbp-18h] BYREF

  pcbData = 0;
  pdwType = 2;
  ppszPath = 0;
  if ( a1 )
  {
    *a1 = 0;
    ProcessHeap = GetProcessHeap();
    v4 = HeapAlloc(ProcessHeap, 8u, 0x208u);
    pvData = v4;
    if ( v4 )
    {
      v2 = 0;
      memset_0(v4, 0, 0x208u);
      pcbData = 520;
      ValueW = RegGetValueW(
                 HKEY_LOCAL_MACHINE,
                 L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Diagnostics\\DiagTrack",
                 L"RedirectedStorageRoot",
                 6u,
                 &pdwType,
                 pvData,
                 &pcbData);
      v5 = -2147024896;
      v9 = ValueW < 0;
      if ( ValueW > 0 )
        v9 = 1;
      if ( v9 )
      {
        if ( (unsigned int)(ValueW - 2) <= 1 )
        {
          v2 = SHGetKnownFolderPath(&FOLDERID_ProgramData, 0, 0, &ppszPath);
          if ( v2 >= 0 )
            v2 = StringCchPrintfW((unsigned __int16 *)pvData, 0x104u, L"%s\\%s", ppszPath, L"microsoft\\diagnosis");
        }
        else if ( ValueW > 0 )
        {
          v2 = (unsigned __int16)ValueW | 0x80070000;
        }
        else
        {
          v2 = ValueW;
        }
      }
    }
    else
    {
      v2 = -2147024882;
    }
    v10 = (int)ppszPath;
    if ( ppszPath )
      CoTaskMemFree(ppszPath);
    if ( v2 >= 0 )
    {
      *a1 = (unsigned __int16 *)pvData;
      if ( (unsigned int)dword_140028000 > 5 )
      {
        v16 = pvData;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          v10,
          (unsigned int)&byte_140023F47,
          v5,
          v6,
          (__int64)&v16);
      }
    }
    else if ( pvData )
    {
      v11 = GetProcessHeap();
      HeapFree(v11, 0, pvData);
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14001505c  mov     rax, rsp
0x14001505f  mov     [rax+10h], rbx
0x140015063  mov     [rax+18h], rsi
0x140015067  push    rdi
0x140015068  sub     rsp, 60h
0x14001506c  mov     dword ptr [rax-28h], 0
0x140015073  mov     rsi, rcx
0x140015076  mov     dword ptr [rax-24h], 2
0x14001507d  mov     qword ptr [rax-20h], 0
0x140015085  test    rcx, rcx
0x140015088  jnz     short loc_140015094
0x14001508a  mov     ebx, 80004003h
0x14001508f  jmp     loc_14001520E
0x140015094  mov     qword ptr [rcx], 0
0x14001509b  call    cs:__imp_GetProcessHeap
0x1400150a2  nop     dword ptr [rax+rax+00h]
0x1400150a7  mov     edx, 8; dwFlags
0x1400150ac  mov     r8d, 208h; dwBytes
0x1400150b2  mov     rcx, rax; hHeap
0x1400150b5  call    cs:__imp_HeapAlloc
0x1400150bc  nop     dword ptr [rax+rax+00h]
0x1400150c1  mov     rdi, rax
0x1400150c4  test    rax, rax
0x1400150c7  jnz     short loc_1400150D3
0x1400150c9  mov     ebx, 8007000Eh
0x1400150ce  jmp     loc_1400151A4
0x1400150d3  xor     edx, edx; Val
0x1400150d5  mov     r8d, 208h; Size
0x1400150db  mov     rcx, rdi; void *
0x1400150de  xor     ebx, ebx
0x1400150e0  call    memset_0
0x1400150e5  lea     rax, [rsp+68h+var_28]
0x1400150ea  mov     [rsp+68h+var_28], 208h
0x1400150f2  mov     [rsp+68h+pcbData], rax; pcbData
0x1400150f7  lea     r9d, [rbx+6]; dwFlags
0x1400150fb  lea     rax, [rsp+68h+var_24]
0x140015100  mov     [rsp+68h+pvData], rdi; pvData
0x140015105  lea     r8, aRedirectedstor; "RedirectedStorageRoot"
0x14001510c  mov     [rsp+68h+pdwType], rax; pdwType
0x140015111  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x140015118  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14001511f  call    cs:__imp_RegGetValueW
0x140015126  nop     dword ptr [rax+rax+00h]
0x14001512b  movzx   edx, ax
0x14001512e  mov     ecx, eax
0x140015130  mov     r8d, 80070000h
0x140015136  test    eax, eax
0x140015138  jle     short loc_140015141
0x14001513a  mov     eax, edx
0x14001513c  or      eax, r8d
0x14001513f  test    eax, eax
0x140015141  jns     short loc_1400151A4
0x140015143  lea     eax, [rcx-2]
0x140015146  cmp     eax, 1
0x140015149  jbe     short loc_14001515A
0x14001514b  test    ecx, ecx
0x14001514d  jg      short loc_140015153
0x14001514f  mov     ebx, ecx
0x140015151  jmp     short loc_1400151A4
0x140015153  mov     ebx, edx
0x140015155  or      ebx, r8d
0x140015158  jmp     short loc_1400151A4
0x14001515a  lea     r9, [rsp+68h+ppszPath]; ppszPath
0x14001515f  xor     r8d, r8d; hToken
0x140015162  xor     edx, edx; dwFlags
0x140015164  lea     rcx, FOLDERID_ProgramData; rfid
0x14001516b  call    cs:__imp_SHGetKnownFolderPath
0x140015172  nop     dword ptr [rax+rax+00h]
0x140015177  mov     ebx, eax
0x140015179  test    eax, eax
0x14001517b  js      short loc_1400151A4
0x14001517d  mov     r9, [rsp+68h+ppszPath]
0x140015182  lea     rax, aMicrosoftDiagn; "microsoft\\diagnosis"
0x140015189  lea     r8, aSS_0; "%s\\%s"
0x140015190  mov     [rsp+68h+pdwType], rax
0x140015195  mov     edx, 104h; unsigned __int64
0x14001519a  mov     rcx, rdi; unsigned __int16 *
0x14001519d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400151a2  mov     ebx, eax
0x1400151a4  mov     rcx, [rsp+68h+ppszPath]; pv
0x1400151a9  test    rcx, rcx
0x1400151ac  jz      short loc_1400151BA
0x1400151ae  call    cs:__imp_CoTaskMemFree
0x1400151b5  nop     dword ptr [rax+rax+00h]
0x1400151ba  test    ebx, ebx
0x1400151bc  jns     short loc_1400151E5
0x1400151be  test    rdi, rdi
0x1400151c1  jz      short loc_14001520E
0x1400151c3  call    cs:__imp_GetProcessHeap
0x1400151ca  nop     dword ptr [rax+rax+00h]
0x1400151cf  mov     r8, rdi; lpMem
0x1400151d2  xor     edx, edx; dwFlags
0x1400151d4  mov     rcx, rax; hHeap
0x1400151d7  call    cs:__imp_HeapFree
0x1400151de  nop     dword ptr [rax+rax+00h]
0x1400151e3  jmp     short loc_14001520E
0x1400151e5  mov     [rsi], rdi
0x1400151e8  mov     eax, cs:dword_140028000
0x1400151ee  cmp     eax, 5
0x1400151f1  jbe     short loc_14001520E
0x1400151f3  lea     rax, [rsp+68h+var_18]
0x1400151f8  mov     [rsp+68h+var_18], rdi
0x1400151fd  lea     rdx, byte_140023F47
0x140015204  mov     [rsp+68h+pdwType], rax
0x140015209  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x14001520e  lea     r11, [rsp+68h+var_8]
0x140015213  mov     eax, ebx
0x140015215  mov     rbx, [r11+18h]
0x140015219  mov     rsi, [r11+20h]
0x14001521d  mov     rsp, r11
0x140015220  pop     rdi
0x140015221  retn
```
