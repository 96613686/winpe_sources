# CreateSiufSystemRootReg(void)

- ea: `0x140005830`
- end: `0x140005a46`
- name: `?CreateSiufSystemRootReg@@YAJXZ`
- size: `534`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000c47c`

## callees

- `0x140001414`
- `0x140005830`
- `0x140017770`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140005945`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140005945`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005a37`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005a37`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005a19`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005a19`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005a28`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005a28`

## string_xrefs

- `0x14000589c`: `CreateSiufSystemRootReg`
- `0x14000599d`: `CreateSiufSystemRootReg`
- `0x1400059c9`: `RegCreateKeyEx failed creating or opening SIUF_REG_PATH`

## pseudocode

```c
__int64 CreateSiufSystemRootReg(void)
{
  signed int StateSeparatedSiufMachineRegRoot; // ebx
  __int64 v1; // r9
  __int64 v2; // r8
  __int64 v3; // rcx
  char *v4; // rdx
  const unsigned __int16 **v5; // rax
  LSTATUS v6; // eax
  HANDLE ProcessHeap; // rax
  const char **lpSecurityAttributes; // [rsp+30h] [rbp-48h]
  const char **phkResult; // [rsp+38h] [rbp-40h]
  __int64 *v11; // [rsp+48h] [rbp-30h]
  __int64 v12; // [rsp+50h] [rbp-28h] BYREF
  const char *v13; // [rsp+58h] [rbp-20h] BYREF
  const char *v14; // [rsp+60h] [rbp-18h] BYREF
  _QWORD v15[2]; // [rsp+68h] [rbp-10h] BYREF
  int v16; // [rsp+90h] [rbp+18h] BYREF
  signed int v17; // [rsp+98h] [rbp+20h] BYREF
  LPCWSTR lpSubKey; // [rsp+A0h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+30h] BYREF

  hKey = 0;
  lpSubKey = 0;
  StateSeparatedSiufMachineRegRoot = GetStateSeparatedSiufMachineRegRoot((unsigned __int16 **)&lpSubKey);
  if ( StateSeparatedSiufMachineRegRoot >= 0 )
  {
    v6 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
    StateSeparatedSiufMachineRegRoot = v6;
    if ( v6 > 0 )
      StateSeparatedSiufMachineRegRoot = (unsigned __int16)v6 | 0x80070000;
    if ( StateSeparatedSiufMachineRegRoot < 0 && (unsigned int)dword_140027000 > 2 )
    {
      v3 = qword_140027018;
      if ( (qword_140027010 & 0x400000000000LL) != 0 && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
      {
        v15[0] = 0x1000000;
        v14 = "CreateSiufSystemRootReg";
        v4 = byte_140020CE9;
        v16 = 398;
        v13 = "onecore\\base\\diagnosis\\feedback\\siuf\\deploymentmgr\\client\\exe\\main.cpp";
        v12 = (__int64)"RegCreateKeyEx failed creating or opening SIUF_REG_PATH";
        v11 = v15;
        phkResult = &v14;
        lpSecurityAttributes = &v13;
        v5 = (const unsigned __int16 **)&v12;
        goto LABEL_13;
      }
    }
  }
  else if ( (unsigned int)dword_140027000 > 2 )
  {
    v2 = qword_140027018;
    v3 = qword_140027010;
    if ( (qword_140027010 & 0x400000000000LL) != 0 && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
    {
      v12 = 0x1000000;
      v13 = "CreateSiufSystemRootReg";
      v4 = &byte_140020B67;
      v16 = 381;
      v14 = "onecore\\base\\diagnosis\\feedback\\siuf\\deploymentmgr\\client\\exe\\main.cpp";
      v15[0] = "GetStateSeparatedSiufMachineRegRoot failed";
      v11 = &v12;
      phkResult = &v13;
      lpSecurityAttributes = &v14;
      v5 = (const unsigned __int16 **)v15;
LABEL_13:
      v17 = StateSeparatedSiufMachineRegRoot;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v3,
        (__int64)v4,
        v2,
        v1,
        v5,
        (__int64)&v17,
        (const unsigned __int16 **)lpSecurityAttributes,
        (const unsigned __int16 **)phkResult,
        (__int64)&v16,
        (__int64)v11);
    }
  }
  if ( lpSubKey )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)lpSubKey);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)StateSeparatedSiufMachineRegRoot;
}

```

## disassembly

```asm
0x140005830  push    rbp
0x140005832  push    rbx
0x140005833  mov     rbp, rsp
0x140005836  sub     rsp, 78h
0x14000583a  lea     rcx, [rbp+lpSubKey]; unsigned __int16 **
0x14000583e  mov     [rbp+hKey], 0
0x140005846  mov     [rbp+lpSubKey], 0
0x14000584e  call    ?GetStateSeparatedSiufMachineRegRoot@@YAJPEAPEAG@Z; GetStateSeparatedSiufMachineRegRoot(ushort * *)
0x140005853  mov     ebx, eax
0x140005855  test    eax, eax
0x140005857  jns     loc_140005909
0x14000585d  mov     ecx, cs:dword_140027000
0x140005863  cmp     ecx, 2
0x140005866  jbe     loc_140005A12
0x14000586c  mov     r8, cs:qword_140027018
0x140005873  mov     rdx, 400000000000h
0x14000587d  mov     rcx, cs:qword_140027010
0x140005884  test    rdx, rcx
0x140005887  jz      loc_140005A12
0x14000588d  mov     rax, r8
0x140005890  and     rax, rdx
0x140005893  cmp     rax, r8
0x140005896  jnz     loc_140005A12
0x14000589c  lea     rax, aCreatesiufsyst; "CreateSiufSystemRootReg"
0x1400058a3  mov     [rbp+var_28], 1000000h
0x1400058ab  mov     [rbp+var_20], rax
0x1400058af  lea     rdx, byte_140020B67
0x1400058b6  lea     rax, aOnecoreBaseDia; "onecore\\base\\diagnosis\\feedback\\siu"...
0x1400058bd  mov     [rbp+arg_0], 17Dh
0x1400058c4  mov     [rbp+var_18], rax
0x1400058c8  lea     rax, aGetstatesepara; "GetStateSeparatedSiufMachineRegRoot fai"...
0x1400058cf  mov     [rbp+var_10], rax
0x1400058d3  lea     rax, [rbp+var_28]
0x1400058d7  mov     [rsp+78h+var_30], rax
0x1400058dc  lea     rax, [rbp+arg_0]
0x1400058e0  mov     [rsp+78h+lpdwDisposition], rax
0x1400058e5  lea     rax, [rbp+var_20]
0x1400058e9  mov     [rsp+78h+phkResult], rax
0x1400058ee  lea     rax, [rbp+var_18]
0x1400058f2  mov     [rsp+78h+lpSecurityAttributes], rax
0x1400058f7  lea     rax, [rbp+arg_8]
0x1400058fb  mov     qword ptr [rsp+78h+samDesired], rax
0x140005900  lea     rax, [rbp+var_10]
0x140005904  jmp     loc_140005A05
0x140005909  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x14000590d  lea     rax, [rbp+hKey]
0x140005911  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x14000591a  xor     r9d, r9d; lpClass
0x14000591d  mov     [rsp+78h+phkResult], rax; phkResult
0x140005922  xor     r8d, r8d; Reserved
0x140005925  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14000592e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140005935  mov     [rsp+78h+samDesired], 0F003Fh; samDesired
0x14000593d  mov     [rsp+78h+dwOptions], 0; dwOptions
0x140005945  call    cs:__imp_RegCreateKeyExW
0x14000594b  mov     ebx, eax
0x14000594d  test    eax, eax
0x14000594f  jle     short loc_14000595A
0x140005951  movzx   ebx, ax
0x140005954  or      ebx, 80070000h
0x14000595a  test    ebx, ebx
0x14000595c  jns     loc_140005A12
0x140005962  mov     eax, cs:dword_140027000
0x140005968  cmp     eax, 2
0x14000596b  jbe     loc_140005A12
0x140005971  mov     rcx, cs:qword_140027018
0x140005978  mov     rdx, 400000000000h
0x140005982  mov     rax, cs:qword_140027010
0x140005989  test    rdx, rax
0x14000598c  jz      loc_140005A12
0x140005992  mov     rax, rcx
0x140005995  and     rax, rdx
0x140005998  cmp     rax, rcx
0x14000599b  jnz     short loc_140005A12
0x14000599d  lea     rax, aCreatesiufsyst; "CreateSiufSystemRootReg"
0x1400059a4  mov     [rbp+var_10], 1000000h
0x1400059ac  mov     [rbp+var_18], rax
0x1400059b0  lea     rdx, byte_140020CE9
0x1400059b7  lea     rax, aOnecoreBaseDia; "onecore\\base\\diagnosis\\feedback\\siu"...
0x1400059be  mov     [rbp+arg_0], 18Eh
0x1400059c5  mov     [rbp+var_20], rax
0x1400059c9  lea     rax, aRegcreatekeyex_0; "RegCreateKeyEx failed creating or openi"...
0x1400059d0  mov     [rbp+var_28], rax
0x1400059d4  lea     rax, [rbp+var_10]
0x1400059d8  mov     [rsp+78h+var_30], rax
0x1400059dd  lea     rax, [rbp+arg_0]
0x1400059e1  mov     [rsp+78h+lpdwDisposition], rax
0x1400059e6  lea     rax, [rbp+var_18]
0x1400059ea  mov     [rsp+78h+phkResult], rax
0x1400059ef  lea     rax, [rbp+var_20]
0x1400059f3  mov     [rsp+78h+lpSecurityAttributes], rax
0x1400059f8  lea     rax, [rbp+arg_8]
0x1400059fc  mov     qword ptr [rsp+78h+samDesired], rax
0x140005a01  lea     rax, [rbp+var_28]
0x140005a05  mov     qword ptr [rsp+78h+dwOptions], rax
0x140005a0a  mov     [rbp+arg_8], ebx
0x140005a0d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140005a12  cmp     [rbp+lpSubKey], 0
0x140005a17  jz      short loc_140005A2E
0x140005a19  call    cs:__imp_GetProcessHeap
0x140005a1f  mov     r8, [rbp+lpSubKey]; lpMem
0x140005a23  xor     edx, edx; dwFlags
0x140005a25  mov     rcx, rax; hHeap
0x140005a28  call    cs:__imp_HeapFree
0x140005a2e  mov     rcx, [rbp+hKey]; hKey
0x140005a32  test    rcx, rcx
0x140005a35  jz      short loc_140005A3D
0x140005a37  call    cs:__imp_RegCloseKey
0x140005a3d  mov     eax, ebx
0x140005a3f  add     rsp, 78h
0x140005a43  pop     rbx
0x140005a44  pop     rbp
0x140005a45  retn
```
