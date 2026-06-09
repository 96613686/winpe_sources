# GetDiagTrackStorePath(ushort * *)

- ea: `0x1400172c4`
- end: `0x140017460`
- name: `?GetDiagTrackStorePath@@YAJPEAPEAG@Z`
- size: `412`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000e924`
- `0x140017094`

## callees

- `0x140001d68`
- `0x14000b5c4`
- `0x1400172c4`
- `0x1400187b2`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001737b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001737b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140017317`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140017317`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140017303`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001740d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140017303`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001740d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001741b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001741b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400173fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400173fe`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1400173c1`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1400173c1`

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
      if ( (unsigned int)dword_140027000 > 5 )
      {
        v16 = pvData;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          v10,
          (unsigned int)&byte_140022F3F,
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
0x1400172c4  mov     rax, rsp
0x1400172c7  mov     [rax+10h], rbx
0x1400172cb  mov     [rax+18h], rsi
0x1400172cf  push    rdi
0x1400172d0  sub     rsp, 60h
0x1400172d4  mov     dword ptr [rax-28h], 0
0x1400172db  mov     rsi, rcx
0x1400172de  mov     dword ptr [rax-24h], 2
0x1400172e5  mov     qword ptr [rax-20h], 0
0x1400172ed  test    rcx, rcx
0x1400172f0  jnz     short loc_1400172FC
0x1400172f2  mov     ebx, 80004003h
0x1400172f7  jmp     loc_14001744C
0x1400172fc  mov     qword ptr [rcx], 0
0x140017303  call    cs:__imp_GetProcessHeap
0x140017309  mov     edx, 8; dwFlags
0x14001730e  mov     r8d, 208h; dwBytes
0x140017314  mov     rcx, rax; hHeap
0x140017317  call    cs:__imp_HeapAlloc
0x14001731d  mov     rdi, rax
0x140017320  test    rax, rax
0x140017323  jnz     short loc_14001732F
0x140017325  mov     ebx, 8007000Eh
0x14001732a  jmp     loc_1400173F4
0x14001732f  xor     edx, edx; Val
0x140017331  mov     r8d, 208h; Size
0x140017337  mov     rcx, rdi; void *
0x14001733a  xor     ebx, ebx
0x14001733c  call    memset_0
0x140017341  lea     rax, [rsp+68h+var_28]
0x140017346  mov     [rsp+68h+var_28], 208h
0x14001734e  mov     [rsp+68h+pcbData], rax; pcbData
0x140017353  lea     r9d, [rbx+6]; dwFlags
0x140017357  lea     rax, [rsp+68h+var_24]
0x14001735c  mov     [rsp+68h+pvData], rdi; pvData
0x140017361  lea     r8, aRedirectedstor; "RedirectedStorageRoot"
0x140017368  mov     [rsp+68h+pdwType], rax; pdwType
0x14001736d  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x140017374  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14001737b  call    cs:__imp_RegGetValueW
0x140017381  movzx   edx, ax
0x140017384  mov     ecx, eax
0x140017386  mov     r8d, 80070000h
0x14001738c  test    eax, eax
0x14001738e  jle     short loc_140017397
0x140017390  mov     eax, edx
0x140017392  or      eax, r8d
0x140017395  test    eax, eax
0x140017397  jns     short loc_1400173F4
0x140017399  lea     eax, [rcx-2]
0x14001739c  cmp     eax, 1
0x14001739f  jbe     short loc_1400173B0
0x1400173a1  test    ecx, ecx
0x1400173a3  jg      short loc_1400173A9
0x1400173a5  mov     ebx, ecx
0x1400173a7  jmp     short loc_1400173F4
0x1400173a9  mov     ebx, edx
0x1400173ab  or      ebx, r8d
0x1400173ae  jmp     short loc_1400173F4
0x1400173b0  lea     r9, [rsp+68h+ppszPath]; ppszPath
0x1400173b5  xor     r8d, r8d; hToken
0x1400173b8  xor     edx, edx; dwFlags
0x1400173ba  lea     rcx, FOLDERID_ProgramData; rfid
0x1400173c1  call    cs:__imp_SHGetKnownFolderPath
0x1400173c7  mov     ebx, eax
0x1400173c9  test    eax, eax
0x1400173cb  js      short loc_1400173F4
0x1400173cd  mov     r9, [rsp+68h+ppszPath]
0x1400173d2  lea     rax, aMicrosoftDiagn; "microsoft\\diagnosis"
0x1400173d9  lea     r8, aSS_0; "%s\\%s"
0x1400173e0  mov     [rsp+68h+pdwType], rax
0x1400173e5  mov     edx, 104h; unsigned __int64
0x1400173ea  mov     rcx, rdi; unsigned __int16 *
0x1400173ed  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400173f2  mov     ebx, eax
0x1400173f4  mov     rcx, [rsp+68h+ppszPath]; pv
0x1400173f9  test    rcx, rcx
0x1400173fc  jz      short loc_140017404
0x1400173fe  call    cs:__imp_CoTaskMemFree
0x140017404  test    ebx, ebx
0x140017406  jns     short loc_140017423
0x140017408  test    rdi, rdi
0x14001740b  jz      short loc_14001744C
0x14001740d  call    cs:__imp_GetProcessHeap
0x140017413  mov     r8, rdi; lpMem
0x140017416  xor     edx, edx; dwFlags
0x140017418  mov     rcx, rax; hHeap
0x14001741b  call    cs:__imp_HeapFree
0x140017421  jmp     short loc_14001744C
0x140017423  mov     [rsi], rdi
0x140017426  mov     eax, cs:dword_140027000
0x14001742c  cmp     eax, 5
0x14001742f  jbe     short loc_14001744C
0x140017431  lea     rax, [rsp+68h+var_18]
0x140017436  mov     [rsp+68h+var_18], rdi
0x14001743b  lea     rdx, byte_140022F3F
0x140017442  mov     [rsp+68h+pdwType], rax
0x140017447  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x14001744c  lea     r11, [rsp+68h+var_8]
0x140017451  mov     eax, ebx
0x140017453  mov     rbx, [r11+18h]
0x140017457  mov     rsi, [r11+20h]
0x14001745b  mov     rsp, r11
0x14001745e  pop     rdi
0x14001745f  retn
```
