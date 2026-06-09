# SettingsCopier::GetRegKeyValue(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong *,ATL::CHeapPtr<uchar,ATL::CCRTAllocator> &,ulong *)

- ea: `0x1401bdc00`
- end: `0x1401bdf5b`
- name: `?GetRegKeyValue@SettingsCopier@@CAJPEAUHKEY__@@PEBGKPEAGKPEAKAEAV?$CHeapPtr@EVCCRTAllocator@ATL@@@ATL@@3@Z`
- size: `859`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpSubKey@<rdx>, DWORD cchValueName, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, registry_config`

## callers

- `0x1401bd918`

## callees

- `0x1401bd8c4`
- `0x1401bdc00`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1401bdc5e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1401bde4c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1401bded7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1401bdf14`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1401bdc5e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1401bde4c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1401bded7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1401bdf14`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1401bdc77`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1401bdc77`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1401bdea3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1401bdea3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401bdc8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401bdc8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401bdcdc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401bdd27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401bddc1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401bde2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401bdeb4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401bdcdc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401bdd27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401bddc1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401bde2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401bdeb4`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1401bdd12`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1401bdd12`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1401bdd7e`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1401bde18`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1401bdd7e`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1401bde18`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401bdcc7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401bdcc7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401bdd37`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401bddd1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401bde3d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401bde92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401bdd37`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401bddd1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401bde3d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401bde92`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1401bde80`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1401bde80`

## string_xrefs

- `0x1401bde79`: `SymbolicLinkValue`

## pseudocode

```c
signed int __fastcall SettingsCopier::GetRegKeyValue(
        HKEY hKey,
        LPCWSTR lpSubKey,
        DWORD a3,
        WCHAR *a4,
        DWORD cchValueName,
        DWORD *a6,
        void **a7,
        DWORD *a8)
{
  DWORD *v8; // r12
  DWORD *v9; // r13
  void **v11; // rsi
  void *v14; // rcx
  HANDLE EventW; // r14
  signed int result; // eax
  LSTATUS v17; // ebx
  LSTATUS v18; // edi
  LSTATUS v19; // eax
  DWORD v20; // ebx
  BYTE *lpData; // [rsp+30h] [rbp-30h]
  DWORD Type; // [rsp+40h] [rbp-20h] BYREF
  DWORD v23; // [rsp+44h] [rbp-1Ch] BYREF
  DWORD v24; // [rsp+48h] [rbp-18h] BYREF
  HKEY hKeya; // [rsp+50h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+B8h] [rbp+58h] BYREF

  v8 = a6;
  v9 = a8;
  v11 = a7;
  *a4 = 0;
  *v8 = 0;
  *v9 = 0;
  v14 = *v11;
  hKeya = 0;
  cchValueName = 260;
  Type = 0;
  cbData = 0;
  v23 = 0;
  v24 = 0;
  free(v14);
  *v11 = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  if ( EventW )
  {
    v17 = RegOpenKeyExW(hKey, lpSubKey, 8u, 0x20019u, &hKeya);
    if ( v17 )
    {
      CloseHandle(EventW);
      goto LABEL_6;
    }
    v18 = 1;
    v17 = RegNotifyChangeKeyValue(hKeya, 0, 5u, EventW, 1);
    if ( v17 )
      goto LABEL_10;
    cchValueName = 260;
    v19 = RegEnumValueW(hKeya, a3, a4, &cchValueName, 0, &Type, 0, &cbData);
    v17 = v19;
    if ( v19 == 259 )
      goto LABEL_17;
    if ( v19 && v19 != 234 )
    {
LABEL_10:
      CloseHandle(EventW);
      RegCloseKey(hKeya);
      goto LABEL_6;
    }
    if ( cbData )
    {
      if ( !(unsigned __int8)ATL::CHeapPtr<unsigned char,ATL::CCRTAllocator>::Allocate(v11, cbData) )
      {
        v18 = -2147024882;
LABEL_17:
        CloseHandle(EventW);
        RegCloseKey(hKeya);
        return v18;
      }
      lpData = (BYTE *)*v11;
      cchValueName = 260;
      v17 = RegEnumValueW(hKeya, a3, a4, &cchValueName, 0, &Type, lpData, &cbData);
      if ( v17 )
      {
        CloseHandle(EventW);
        RegCloseKey(hKeya);
        free(*v11);
        *v11 = 0;
LABEL_6:
        if ( v17 > 0 )
          return (unsigned __int16)v17 | 0x80070000;
        return v17;
      }
    }
    v18 = RegQueryValueExW(hKeya, L"SymbolicLinkValue", 0, &v23, 0, &v24);
    RegCloseKey(hKeya);
    v20 = WaitForSingleObject(EventW, 0);
    CloseHandle(EventW);
    if ( !v20 )
    {
      v17 = -2147023590;
LABEL_29:
      free(*v11);
      *v11 = 0;
      *a4 = 0;
      return v17;
    }
    if ( v18 )
    {
      if ( v18 != 2 )
      {
        free(*v11);
        *v11 = 0;
        *a4 = 0;
        if ( v18 > 0 )
          return (unsigned __int16)v18 | 0x80070000;
        return v18;
      }
    }
    else if ( v23 == 6 )
    {
      v17 = -2147023432;
      goto LABEL_29;
    }
    *v8 = Type;
    *v9 = cbData;
    return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1401bdc00  mov     [rsp-38h+arg_0], rbx
0x1401bdc05  mov     [rsp-38h+dwIndex], r8d
0x1401bdc0a  push    rbp
0x1401bdc0b  push    rsi
0x1401bdc0c  push    rdi
0x1401bdc0d  push    r12
0x1401bdc0f  push    r13
0x1401bdc11  push    r14
0x1401bdc13  push    r15
0x1401bdc15  mov     rbp, rsp
0x1401bdc18  sub     rsp, 60h
0x1401bdc1c  mov     r12, [rbp+arg_28]
0x1401bdc20  xor     r14d, r14d
0x1401bdc23  mov     r13, [rbp+arg_38]
0x1401bdc27  mov     rdi, rcx
0x1401bdc2a  mov     rsi, [rbp+arg_30]
0x1401bdc2e  mov     r15, r9
0x1401bdc31  mov     [r9], r14w
0x1401bdc35  mov     rbx, rdx
0x1401bdc38  mov     [r12], r14d
0x1401bdc3c  mov     [r13+0], r14d
0x1401bdc40  mov     rcx, [rsi]; Block
0x1401bdc43  mov     [rbp+hKey], r14
0x1401bdc47  mov     [rbp+cchValueName], 104h
0x1401bdc4e  mov     [rbp+Type], r14d
0x1401bdc52  mov     [rbp+cbData], r14d
0x1401bdc56  mov     [rbp+var_1C], r14d
0x1401bdc5a  mov     [rbp+var_18], r14d
0x1401bdc5e  call    cs:__imp_free
0x1401bdc65  nop     dword ptr [rax+rax+00h]
0x1401bdc6a  xor     r9d, r9d; lpName
0x1401bdc6d  mov     [rsi], r14
0x1401bdc70  xor     r8d, r8d; bInitialState
0x1401bdc73  xor     edx, edx; bManualReset
0x1401bdc75  xor     ecx, ecx; lpEventAttributes
0x1401bdc77  call    cs:__imp_CreateEventW
0x1401bdc7e  nop     dword ptr [rax+rax+00h]
0x1401bdc83  mov     r14, rax
0x1401bdc86  test    rax, rax
0x1401bdc89  jnz     short loc_1401BDCAC
0x1401bdc8b  call    cs:__imp_GetLastError
0x1401bdc92  nop     dword ptr [rax+rax+00h]
0x1401bdc97  test    eax, eax
0x1401bdc99  jle     loc_1401BDF42
0x1401bdc9f  movzx   eax, ax
0x1401bdca2  or      eax, 80070000h
0x1401bdca7  jmp     loc_1401BDF42
0x1401bdcac  lea     rax, [rbp+hKey]
0x1401bdcb0  mov     r9d, 20019h; samDesired
0x1401bdcb6  mov     r8d, 8; ulOptions
0x1401bdcbc  mov     [rsp+60h+phkResult], rax; phkResult
0x1401bdcc1  mov     rdx, rbx; lpSubKey
0x1401bdcc4  mov     rcx, rdi; hKey
0x1401bdcc7  call    cs:__imp_RegOpenKeyExW
0x1401bdcce  nop     dword ptr [rax+rax+00h]
0x1401bdcd3  mov     ebx, eax
0x1401bdcd5  test    eax, eax
0x1401bdcd7  jz      short loc_1401BDCFC
0x1401bdcd9  mov     rcx, r14; hObject
0x1401bdcdc  call    cs:__imp_CloseHandle
0x1401bdce3  nop     dword ptr [rax+rax+00h]
0x1401bdce8  test    ebx, ebx
0x1401bdcea  jle     short loc_1401BDCF5
0x1401bdcec  movzx   ebx, bx
0x1401bdcef  or      ebx, 80070000h
0x1401bdcf5  mov     eax, ebx
0x1401bdcf7  jmp     loc_1401BDF42
0x1401bdcfc  mov     rcx, [rbp+hKey]; hKey
0x1401bdd00  mov     edi, 1
0x1401bdd05  mov     r9, r14; hEvent
0x1401bdd08  mov     dword ptr [rsp+60h+phkResult], edi; fAsynchronous
0x1401bdd0c  xor     edx, edx; bWatchSubtree
0x1401bdd0e  lea     r8d, [rdi+4]; dwNotifyFilter
0x1401bdd12  call    cs:__imp_RegNotifyChangeKeyValue
0x1401bdd19  nop     dword ptr [rax+rax+00h]
0x1401bdd1e  mov     ebx, eax
0x1401bdd20  test    eax, eax
0x1401bdd22  jz      short loc_1401BDD45
0x1401bdd24  mov     rcx, r14; hObject
0x1401bdd27  call    cs:__imp_CloseHandle
0x1401bdd2e  nop     dword ptr [rax+rax+00h]
0x1401bdd33  mov     rcx, [rbp+hKey]; hKey
0x1401bdd37  call    cs:__imp_RegCloseKey
0x1401bdd3e  nop     dword ptr [rax+rax+00h]
0x1401bdd43  jmp     short loc_1401BDCE8
0x1401bdd45  mov     edx, [rbp+dwIndex]; dwIndex
0x1401bdd48  lea     rax, [rbp+cbData]
0x1401bdd4c  mov     rcx, [rbp+hKey]; hKey
0x1401bdd50  lea     r9, [rbp+cchValueName]; lpcchValueName
0x1401bdd54  mov     [rsp+60h+lpcbData], rax; lpcbData
0x1401bdd59  mov     r8, r15; lpValueName
0x1401bdd5c  lea     rax, [rbp+Type]
0x1401bdd60  mov     [rsp+60h+lpData], 0; lpData
0x1401bdd69  mov     [rsp+60h+lpType], rax; lpType
0x1401bdd6e  mov     [rsp+60h+phkResult], 0; lpReserved
0x1401bdd77  mov     [rbp+cchValueName], 104h
0x1401bdd7e  call    cs:__imp_RegEnumValueW
0x1401bdd85  nop     dword ptr [rax+rax+00h]
0x1401bdd8a  mov     ebx, eax
0x1401bdd8c  cmp     eax, 103h
0x1401bdd91  jz      short loc_1401BDDBE
0x1401bdd93  xor     edi, edi
0x1401bdd95  test    eax, eax
0x1401bdd97  jz      short loc_1401BDDA0
0x1401bdd99  cmp     eax, 0EAh
0x1401bdd9e  jnz     short loc_1401BDD24
0x1401bdda0  mov     eax, [rbp+cbData]
0x1401bdda3  test    eax, eax
0x1401bdda5  jz      loc_1401BDE60
0x1401bddab  mov     edx, eax
0x1401bddad  mov     rcx, rsi
0x1401bddb0  call    ?Allocate@?$CHeapPtr@EVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<uchar,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x1401bddb5  test    al, al
0x1401bddb7  jnz     short loc_1401BDDE4
0x1401bddb9  mov     edi, 8007000Eh
0x1401bddbe  mov     rcx, r14; hObject
0x1401bddc1  call    cs:__imp_CloseHandle
0x1401bddc8  nop     dword ptr [rax+rax+00h]
0x1401bddcd  mov     rcx, [rbp+hKey]; hKey
0x1401bddd1  call    cs:__imp_RegCloseKey
0x1401bddd8  nop     dword ptr [rax+rax+00h]
0x1401bdddd  mov     eax, edi
0x1401bdddf  jmp     loc_1401BDF42
0x1401bdde4  mov     edx, [rbp+dwIndex]; dwIndex
0x1401bdde7  lea     rax, [rbp+cbData]
0x1401bddeb  mov     rcx, [rbp+hKey]; hKey
0x1401bddef  lea     r9, [rbp+cchValueName]; lpcchValueName
0x1401bddf3  mov     [rsp+60h+lpcbData], rax; lpcbData
0x1401bddf8  mov     r8, r15; lpValueName
0x1401bddfb  mov     rax, [rsi]
0x1401bddfe  mov     [rsp+60h+lpData], rax; lpData
0x1401bde03  lea     rax, [rbp+Type]
0x1401bde07  mov     [rsp+60h+lpType], rax; lpType
0x1401bde0c  mov     [rsp+60h+phkResult], rdi; lpReserved
0x1401bde11  mov     [rbp+cchValueName], 104h
0x1401bde18  call    cs:__imp_RegEnumValueW
0x1401bde1f  nop     dword ptr [rax+rax+00h]
0x1401bde24  mov     ebx, eax
0x1401bde26  test    eax, eax
0x1401bde28  jz      short loc_1401BDE60
0x1401bde2a  mov     rcx, r14; hObject
0x1401bde2d  call    cs:__imp_CloseHandle
0x1401bde34  nop     dword ptr [rax+rax+00h]
0x1401bde39  mov     rcx, [rbp+hKey]; hKey
0x1401bde3d  call    cs:__imp_RegCloseKey
0x1401bde44  nop     dword ptr [rax+rax+00h]
0x1401bde49  mov     rcx, [rsi]; Block
0x1401bde4c  call    cs:__imp_free
0x1401bde53  nop     dword ptr [rax+rax+00h]
0x1401bde58  mov     [rsi], rdi
0x1401bde5b  jmp     loc_1401BDCE8
0x1401bde60  mov     rcx, [rbp+hKey]; hKey
0x1401bde64  lea     rax, [rbp+var_18]
0x1401bde68  mov     [rsp+60h+lpType], rax; lpcbData
0x1401bde6d  lea     r9, [rbp+var_1C]; lpType
0x1401bde71  xor     r8d, r8d; lpReserved
0x1401bde74  mov     [rsp+60h+phkResult], rdi; lpData
0x1401bde79  lea     rdx, aSymboliclinkva; "SymbolicLinkValue"
0x1401bde80  call    cs:__imp_RegQueryValueExW
0x1401bde87  nop     dword ptr [rax+rax+00h]
0x1401bde8c  mov     rcx, [rbp+hKey]; hKey
0x1401bde90  mov     edi, eax
0x1401bde92  call    cs:__imp_RegCloseKey
0x1401bde99  nop     dword ptr [rax+rax+00h]
0x1401bde9e  xor     edx, edx; dwMilliseconds
0x1401bdea0  mov     rcx, r14; hHandle
0x1401bdea3  call    cs:__imp_WaitForSingleObject
0x1401bdeaa  nop     dword ptr [rax+rax+00h]
0x1401bdeaf  mov     rcx, r14; hObject
0x1401bdeb2  mov     ebx, eax
0x1401bdeb4  call    cs:__imp_CloseHandle
0x1401bdebb  nop     dword ptr [rax+rax+00h]
0x1401bdec0  test    ebx, ebx
0x1401bdec2  jnz     short loc_1401BDECB
0x1401bdec4  mov     ebx, 8007051Ah
0x1401bdec9  jmp     short loc_1401BDF11
0x1401bdecb  test    edi, edi
0x1401bdecd  jz      short loc_1401BDF06
0x1401bdecf  cmp     edi, 2
0x1401bded2  jz      short loc_1401BDF32
0x1401bded4  mov     rcx, [rsi]; Block
0x1401bded7  call    cs:__imp_free
0x1401bdede  nop     dword ptr [rax+rax+00h]
0x1401bdee3  xor     eax, eax
0x1401bdee5  mov     qword ptr [rsi], 0
0x1401bdeec  mov     [r15], ax
0x1401bdef0  test    edi, edi
0x1401bdef2  jle     loc_1401BDDDD
0x1401bdef8  movzx   edi, di
0x1401bdefb  or      edi, 80070000h
0x1401bdf01  jmp     loc_1401BDDDD
0x1401bdf06  cmp     [rbp+var_1C], 6
0x1401bdf0a  jnz     short loc_1401BDF32
0x1401bdf0c  mov     ebx, 800705B8h
0x1401bdf11  mov     rcx, [rsi]; Block
0x1401bdf14  call    cs:__imp_free
0x1401bdf1b  nop     dword ptr [rax+rax+00h]
0x1401bdf20  xor     ecx, ecx
0x1401bdf22  mov     qword ptr [rsi], 0
0x1401bdf29  mov     [r15], cx
0x1401bdf2d  jmp     loc_1401BDCF5
0x1401bdf32  mov     eax, [rbp+Type]
0x1401bdf35  mov     [r12], eax
0x1401bdf39  mov     eax, [rbp+cbData]
0x1401bdf3c  mov     [r13+0], eax
0x1401bdf40  xor     eax, eax
0x1401bdf42  mov     rbx, [rsp+60h+arg_0]
0x1401bdf4a  add     rsp, 60h
0x1401bdf4e  pop     r15
0x1401bdf50  pop     r14
0x1401bdf52  pop     r13
0x1401bdf54  pop     r12
0x1401bdf56  pop     rdi
0x1401bdf57  pop     rsi
0x1401bdf58  pop     rbp
0x1401bdf59  retn
```
