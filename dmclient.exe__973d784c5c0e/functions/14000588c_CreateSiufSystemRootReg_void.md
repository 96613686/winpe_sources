# CreateSiufSystemRootReg(void)

- ea: `0x14000588c`
- end: `0x140005abb`
- name: `?CreateSiufSystemRootReg@@YAJXZ`
- size: `559`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000c928`

## callees

- `0x140001418`
- `0x14000588c`
- `0x1400155a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005aa5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005aa5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400059a1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400059a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005a7b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005a7b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005a90`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005a90`

## string_xrefs

- `0x1400058f8`: `CreateSiufSystemRootReg`
- `0x1400059ff`: `CreateSiufSystemRootReg`
- `0x140005a2b`: `RegCreateKeyEx failed creating or opening SIUF_REG_PATH`

## pseudocode

```c
__int64 CreateSiufSystemRootReg(void)
{
  signed int StateSeparatedSiufMachineRegRoot; // ebx
  int v1; // r9d
  int v2; // r8d
  int v3; // ecx
  char *v4; // rdx
  __int64 *v5; // rax
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
    if ( StateSeparatedSiufMachineRegRoot < 0 && (unsigned int)dword_140028000 > 2 )
    {
      v3 = qword_140028018;
      if ( (qword_140028010 & 0x400000000000LL) != 0 && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
      {
        v15[0] = 0x1000000;
        v14 = "CreateSiufSystemRootReg";
        v4 = byte_140021CF1;
        v16 = 398;
        v13 = "onecore\\base\\diagnosis\\feedback\\siuf\\deploymentmgr\\client\\exe\\main.cpp";
        v12 = (__int64)"RegCreateKeyEx failed creating or opening SIUF_REG_PATH";
        v11 = v15;
        phkResult = &v14;
        lpSecurityAttributes = &v13;
        v5 = &v12;
        goto LABEL_13;
      }
    }
  }
  else if ( (unsigned int)dword_140028000 > 2 )
  {
    v2 = qword_140028018;
    v3 = qword_140028010;
    if ( (qword_140028010 & 0x400000000000LL) != 0 && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
    {
      v12 = 0x1000000;
      v13 = "CreateSiufSystemRootReg";
      v4 = &byte_140021B6F;
      v16 = 381;
      v14 = "onecore\\base\\diagnosis\\feedback\\siuf\\deploymentmgr\\client\\exe\\main.cpp";
      v15[0] = "GetStateSeparatedSiufMachineRegRoot failed";
      v11 = &v12;
      phkResult = &v13;
      lpSecurityAttributes = &v14;
      v5 = v15;
LABEL_13:
      v17 = StateSeparatedSiufMachineRegRoot;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v3,
        (_DWORD)v4,
        v2,
        v1,
        (__int64)v5,
        (__int64)&v17,
        (__int64)lpSecurityAttributes,
        (__int64)phkResult,
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
0x14000588c  push    rbp
0x14000588e  push    rbx
0x14000588f  mov     rbp, rsp
0x140005892  sub     rsp, 78h
0x140005896  lea     rcx, [rbp+lpSubKey]; unsigned __int16 **
0x14000589a  mov     [rbp+hKey], 0
0x1400058a2  mov     [rbp+lpSubKey], 0
0x1400058aa  call    ?GetStateSeparatedSiufMachineRegRoot@@YAJPEAPEAG@Z; GetStateSeparatedSiufMachineRegRoot(ushort * *)
0x1400058af  mov     ebx, eax
0x1400058b1  test    eax, eax
0x1400058b3  jns     loc_140005965
0x1400058b9  mov     ecx, cs:dword_140028000
0x1400058bf  cmp     ecx, 2
0x1400058c2  jbe     loc_140005A74
0x1400058c8  mov     r8, cs:qword_140028018
0x1400058cf  mov     rdx, 400000000000h
0x1400058d9  mov     rcx, cs:qword_140028010
0x1400058e0  test    rdx, rcx
0x1400058e3  jz      loc_140005A74
0x1400058e9  mov     rax, r8
0x1400058ec  and     rax, rdx
0x1400058ef  cmp     rax, r8
0x1400058f2  jnz     loc_140005A74
0x1400058f8  lea     rax, aCreatesiufsyst; "CreateSiufSystemRootReg"
0x1400058ff  mov     [rbp+var_28], 1000000h
0x140005907  mov     [rbp+var_20], rax
0x14000590b  lea     rdx, byte_140021B6F
0x140005912  lea     rax, aOnecoreBaseDia; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140005919  mov     [rbp+arg_0], 17Dh
0x140005920  mov     [rbp+var_18], rax
0x140005924  lea     rax, aGetstatesepara; "GetStateSeparatedSiufMachineRegRoot fai"...
0x14000592b  mov     [rbp+var_10], rax
0x14000592f  lea     rax, [rbp+var_28]
0x140005933  mov     [rsp+78h+var_30], rax
0x140005938  lea     rax, [rbp+arg_0]
0x14000593c  mov     [rsp+78h+lpdwDisposition], rax
0x140005941  lea     rax, [rbp+var_20]
0x140005945  mov     [rsp+78h+phkResult], rax
0x14000594a  lea     rax, [rbp+var_18]
0x14000594e  mov     [rsp+78h+lpSecurityAttributes], rax
0x140005953  lea     rax, [rbp+arg_8]
0x140005957  mov     qword ptr [rsp+78h+samDesired], rax
0x14000595c  lea     rax, [rbp+var_10]
0x140005960  jmp     loc_140005A67
0x140005965  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x140005969  lea     rax, [rbp+hKey]
0x14000596d  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x140005976  xor     r9d, r9d; lpClass
0x140005979  mov     [rsp+78h+phkResult], rax; phkResult
0x14000597e  xor     r8d, r8d; Reserved
0x140005981  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14000598a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140005991  mov     [rsp+78h+samDesired], 0F003Fh; samDesired
0x140005999  mov     [rsp+78h+dwOptions], 0; dwOptions
0x1400059a1  call    cs:__imp_RegCreateKeyExW
0x1400059a8  nop     dword ptr [rax+rax+00h]
0x1400059ad  mov     ebx, eax
0x1400059af  test    eax, eax
0x1400059b1  jle     short loc_1400059BC
0x1400059b3  movzx   ebx, ax
0x1400059b6  or      ebx, 80070000h
0x1400059bc  test    ebx, ebx
0x1400059be  jns     loc_140005A74
0x1400059c4  mov     eax, cs:dword_140028000
0x1400059ca  cmp     eax, 2
0x1400059cd  jbe     loc_140005A74
0x1400059d3  mov     rcx, cs:qword_140028018
0x1400059da  mov     rdx, 400000000000h
0x1400059e4  mov     rax, cs:qword_140028010
0x1400059eb  test    rdx, rax
0x1400059ee  jz      loc_140005A74
0x1400059f4  mov     rax, rcx
0x1400059f7  and     rax, rdx
0x1400059fa  cmp     rax, rcx
0x1400059fd  jnz     short loc_140005A74
0x1400059ff  lea     rax, aCreatesiufsyst; "CreateSiufSystemRootReg"
0x140005a06  mov     [rbp+var_10], 1000000h
0x140005a0e  mov     [rbp+var_18], rax
0x140005a12  lea     rdx, byte_140021CF1
0x140005a19  lea     rax, aOnecoreBaseDia; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140005a20  mov     [rbp+arg_0], 18Eh
0x140005a27  mov     [rbp+var_20], rax
0x140005a2b  lea     rax, aRegcreatekeyex_0; "RegCreateKeyEx failed creating or openi"...
0x140005a32  mov     [rbp+var_28], rax
0x140005a36  lea     rax, [rbp+var_10]
0x140005a3a  mov     [rsp+78h+var_30], rax
0x140005a3f  lea     rax, [rbp+arg_0]
0x140005a43  mov     [rsp+78h+lpdwDisposition], rax
0x140005a48  lea     rax, [rbp+var_18]
0x140005a4c  mov     [rsp+78h+phkResult], rax
0x140005a51  lea     rax, [rbp+var_20]
0x140005a55  mov     [rsp+78h+lpSecurityAttributes], rax
0x140005a5a  lea     rax, [rbp+arg_8]
0x140005a5e  mov     qword ptr [rsp+78h+samDesired], rax
0x140005a63  lea     rax, [rbp+var_28]
0x140005a67  mov     qword ptr [rsp+78h+dwOptions], rax
0x140005a6c  mov     [rbp+arg_8], ebx
0x140005a6f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140005a74  cmp     [rbp+lpSubKey], 0
0x140005a79  jz      short loc_140005A9C
0x140005a7b  call    cs:__imp_GetProcessHeap
0x140005a82  nop     dword ptr [rax+rax+00h]
0x140005a87  mov     r8, [rbp+lpSubKey]; lpMem
0x140005a8b  xor     edx, edx; dwFlags
0x140005a8d  mov     rcx, rax; hHeap
0x140005a90  call    cs:__imp_HeapFree
0x140005a97  nop     dword ptr [rax+rax+00h]
0x140005a9c  mov     rcx, [rbp+hKey]; hKey
0x140005aa0  test    rcx, rcx
0x140005aa3  jz      short loc_140005AB1
0x140005aa5  call    cs:__imp_RegCloseKey
0x140005aac  nop     dword ptr [rax+rax+00h]
0x140005ab1  mov     eax, ebx
0x140005ab3  add     rsp, 78h
0x140005ab7  pop     rbx
0x140005ab8  pop     rbp
0x140005ab9  retn
```
