# FwChangeSourceInitializeInternal(FW_CHANGE_TYPE_)

- ea: `0x180013140`
- end: `0x1800133ea`
- name: `?FwChangeSourceInitializeInternal@@YAJW4FW_CHANGE_TYPE_@@@Z`
- size: `682`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180013120`
- `0x180013130`

## callees

- `0x180002610`
- `0x1800028e0`
- `0x1800031a0`
- `0x1800047e0`
- `0x180006f50`
- `0x180013140`
- `0x18001e1d0`
- `0x18001eb54`
- `0x180030010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800132cf`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800132cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001323f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001323f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001322f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001322f`

## string_xrefs

- `0x180013169`: `SYSTEM\CurrentControlSet\Services\SharedAccess\Epoch`
- `0x1800131d5`: `SharedAccessEpoch`
- `0x1800132bc`: `SharedAccessEpoch2`
- `0x180013228`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall FwChangeSourceInitializeInternal(int a1)
{
  __int64 v1; // rdi
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  unsigned int v4; // esi
  unsigned int Key; // ebx
  unsigned int v6; // eax
  __int64 v8; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SubKey[53]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v10[422]; // [rsp+BAh] [rbp-46h] BYREF
  _OWORD v11[2]; // [rsp+260h] [rbp+160h] BYREF
  int v12; // [rsp+280h] [rbp+180h]
  _BYTE v13[492]; // [rsp+284h] [rbp+184h] BYREF

  wcscpy(SubKey, L"SYSTEM\\CurrentControlSet\\Services\\SharedAcs\\Epoch");
  v1 = a1;
  LODWORD(v8) = 0;
  memset_0(v10, 0, 0x19Eu);
  v11[0] = *(_OWORD *)L"SharedAccessEpoch";
  v11[1] = *(_OWORD *)L"cessEpoch";
  v12 = *(_DWORD *)L"h";
  memset_0(v13, 0, 0x1E4u);
  if ( (int)v1 >= 2 )
  {
    Key = -2147024809;
    goto LABEL_17;
  }
  if ( (_DWORD)v1 )
  {
    if ( (_DWORD)v1 == 1 && (unsigned int)_o_wcscpy_s(v11, 260, L"SharedAccessEpoch2") )
    {
      Key = -2147024809;
      FwReportReturnError("FwChangeSourceInitializeInternal", 2147942487LL);
      goto LABEL_10;
    }
  }
  else
  {
    dword_18003C5A4 = 0;
  }
  ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
  ProcAddress = GetProcAddress(ModuleHandleW, "RtlGetPersistedStateLocation");
  if ( ProcAddress )
  {
    v4 = ((__int64 (__fastcall *)(_OWORD *, _QWORD, wchar_t *, _QWORD, WCHAR *, int, _QWORD))ProcAddress)(
           v11,
           0,
           off_180031228[v1],
           0,
           SubKey,
           520,
           0);
    if ( (int)FwNtStatusToHResult(v4) < 0 )
    {
      Key = 0;
      v6 = FwNtStatusToHResult(v4);
      FwReportReturnError("FwChangeSourceInitializeInternal", v6);
      return Key;
    }
  }
  Key = FwRegCreateKey(HKEY_LOCAL_MACHINE, SubKey, 3u, &gFwChangeSource + 2 * v1);
  if ( (Key & 0x80000000) != 0
    || (Key = FwRegQueryDWord(*(&gFwChangeSource + 2 * v1), 0, L"Epoch", (LPBYTE)&dword_18003C5A0[4 * v1], (__int64)&v8),
        (Key & 0x80000000) != 0) )
  {
LABEL_17:
    FwReportReturnError("FwChangeSourceInitializeInternal", Key);
    if ( !(_DWORD)v1 )
    {
      FwRegCloseKey(gFwChangeSource);
      gFwChangeSource = 0;
      dword_18003C5A4 = 0;
      return (unsigned int)FwReportReturnError("FwChangeSourceInitializeInternal", Key);
    }
LABEL_10:
    FwRegCloseKey(hKey);
    hKey = 0;
    dword_18003C5B4 = 0;
    return (unsigned int)FwReportReturnError("FwChangeSourceInitializeInternal", Key);
  }
  return Key;
}

```

## disassembly

```asm
0x180013140  push    rbp
0x180013142  push    rbx
0x180013143  push    rsi
0x180013144  push    rdi
0x180013145  push    r12
0x180013147  push    r14
0x180013149  lea     rbp, [rsp-388h]
0x180013151  sub     rsp, 488h
0x180013158  mov     rax, cs:__security_cookie
0x18001315f  xor     rax, rsp
0x180013162  mov     [rbp+3B0h+var_40], rax
0x180013169  movaps  xmm0, xmmword ptr cs:aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Sh"...
0x180013170  xor     edx, edx; Val
0x180013172  movaps  xmm1, xmmword ptr cs:aSystemCurrentc+10h; "urrentControlSet\\Services\\SharedAcces"...
0x180013179  mov     r8d, 19Eh; Size
0x18001317f  movaps  xmmword ptr [rsp+4B0h+SubKey], xmm0
0x180013184  movaps  xmm0, xmmword ptr cs:aSystemCurrentc+20h; "ntrolSet\\Services\\SharedAccess\\Epoch"
0x18001318b  movaps  [rsp+4B0h+var_440], xmm0
0x180013190  movaps  xmm0, xmmword ptr cs:aSystemCurrentc+40h; "s\\SharedAccess\\Epoch"
0x180013197  movaps  [rsp+4B0h+var_450], xmm1
0x18001319c  movaps  xmm1, xmmword ptr cs:aSystemCurrentc+30h; "\\Services\\SharedAccess\\Epoch"
0x1800131a3  movaps  [rbp+3B0h+var_420], xmm0
0x1800131a7  movups  xmm0, xmmword ptr cs:aSystemCurrentc+5Ah; "s\\Epoch"
0x1800131ae  movsxd  rdi, ecx
0x1800131b1  lea     rcx, [rbp+3B0h+var_3F6]; void *
0x1800131b5  movaps  [rbp+3B0h+var_430], xmm1
0x1800131b9  movaps  xmm1, xmmword ptr cs:aSystemCurrentc+50h; "Access\\Epoch"
0x1800131c0  movaps  [rbp+3B0h+var_410], xmm1
0x1800131c4  movups  [rbp+3B0h+var_410+0Ah], xmm0
0x1800131c8  mov     dword ptr [rsp+4B0h+var_470], 0
0x1800131d0  call    memset_0
0x1800131d5  movups  xmm0, xmmword ptr cs:aSharedaccessep_0; "SharedAccessEpoch"
0x1800131dc  mov     eax, dword ptr cs:aSharedaccessep_0+20h; "h"
0x1800131e2  xor     edx, edx; Val
0x1800131e4  movups  xmm1, xmmword ptr cs:aSharedaccessep_0+10h; "cessEpoch"
0x1800131eb  mov     r8d, 1E4h; Size
0x1800131f1  lea     rcx, [rbp+3B0h+var_22C]; void *
0x1800131f8  movaps  [rbp+3B0h+var_250], xmm0
0x1800131ff  movaps  [rbp+3B0h+var_240], xmm1
0x180013206  mov     [rbp+3B0h+var_230], eax
0x18001320c  call    memset_0
0x180013211  cmp     edi, 2
0x180013214  jge     loc_1800133A5
0x18001321a  test    edi, edi
0x18001321c  jnz     loc_1800132B3
0x180013222  mov     cs:dword_18003C5A4, edi
0x180013228  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18001322f  call    cs:__imp_GetModuleHandleW
0x180013235  mov     rcx, rax; hModule
0x180013238  lea     rdx, aRtlgetpersiste; "RtlGetPersistedStateLocation"
0x18001323f  call    cs:__imp_GetProcAddress
0x180013245  lea     r12, __ImageBase
0x18001324c  test    rax, rax
0x18001324f  jz      loc_180013342
0x180013255  mov     r8, ds:rva off_180031228[r12+rdi*8]; "SYSTEM\\CurrentControlSet\\Services\\Sh"... ...
0x18001325d  lea     rcx, [rsp+4B0h+SubKey]
0x180013262  mov     [rsp+4B0h+var_480], 0
0x18001326b  xor     r9d, r9d
0x18001326e  mov     [rsp+4B0h+var_488], 208h
0x180013276  xor     edx, edx
0x180013278  mov     [rsp+4B0h+var_490], rcx
0x18001327d  lea     rcx, [rbp+3B0h+var_250]
0x180013284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013289  mov     ecx, eax
0x18001328b  mov     esi, eax
0x18001328d  call    FwNtStatusToHResult
0x180013292  test    eax, eax
0x180013294  jns     loc_180013342
0x18001329a  mov     ecx, esi
0x18001329c  xor     ebx, ebx
0x18001329e  call    FwNtStatusToHResult
0x1800132a3  mov     edx, eax
0x1800132a5  lea     rcx, aFwchangesource_4; "FwChangeSourceInitializeInternal"
0x1800132ac  call    FwReportReturnError
0x1800132b1  jmp     short loc_180013321
0x1800132b3  cmp     edi, 1
0x1800132b6  jnz     loc_180013228
0x1800132bc  lea     r8, aSharedaccessep; "SharedAccessEpoch2"
0x1800132c3  mov     edx, 104h
0x1800132c8  lea     rcx, [rbp+3B0h+var_250]
0x1800132cf  call    cs:__imp__o_wcscpy_s
0x1800132d5  test    eax, eax
0x1800132d7  jz      loc_180013228
0x1800132dd  mov     ebx, 80070057h
0x1800132e2  lea     rcx, aFwchangesource_4; "FwChangeSourceInitializeInternal"
0x1800132e9  mov     edx, ebx
0x1800132eb  call    FwReportReturnError
0x1800132f0  mov     rcx, cs:hKey
0x1800132f7  call    FwRegCloseKey
0x1800132fc  mov     cs:hKey, 0
0x180013307  mov     cs:dword_18003C5B4, 0
0x180013311  mov     edx, ebx
0x180013313  lea     rcx, aFwchangesource_4; "FwChangeSourceInitializeInternal"
0x18001331a  call    FwReportReturnError
0x18001331f  mov     ebx, eax
0x180013321  mov     eax, ebx
0x180013323  mov     rcx, [rbp+3B0h+var_40]
0x18001332a  xor     rcx, rsp; StackCookie
0x18001332d  call    __security_check_cookie
0x180013332  add     rsp, 488h
0x180013339  pop     r14
0x18001333b  pop     r12
0x18001333d  pop     rdi
0x18001333e  pop     rsi
0x18001333f  pop     rbx
0x180013340  pop     rbp
0x180013341  retn
0x180013342  mov     rsi, rdi
0x180013345  lea     r14, rva ?gFwChangeSource@@3PAUFW_CHANGE_SOURCE_COMPONENT_@@A[r12]; FW_CHANGE_SOURCE_COMPONENT_ near * gFwChangeSource ...
0x18001334d  shl     rsi, 4
0x180013351  lea     rdx, [rsp+4B0h+SubKey]; lpSubKey
0x180013356  add     r14, rsi
0x180013359  mov     r8d, 3; samDesired
0x18001335f  mov     r9, r14
0x180013362  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180013369  call    FwRegCreateKey
0x18001336e  mov     ebx, eax
0x180013370  test    eax, eax
0x180013372  js      short loc_1800133AA
0x180013374  mov     rcx, [r14]; hKey
0x180013377  lea     rax, [rsp+4B0h+var_470]
0x18001337c  lea     r9, rva dword_18003C5A0[r12]
0x180013384  mov     [rsp+4B0h+var_490], rax; __int64
0x180013389  add     r9, rsi; lpData
0x18001338c  lea     r8, aEpoch; "Epoch"
0x180013393  xor     edx, edx; lpSubKey
0x180013395  call    FwRegQueryDWord
0x18001339a  mov     ebx, eax
0x18001339c  test    eax, eax
0x18001339e  js      short loc_1800133AA
0x1800133a0  jmp     loc_180013321
0x1800133a5  mov     ebx, 80070057h
0x1800133aa  mov     edx, ebx
0x1800133ac  lea     rcx, aFwchangesource_4; "FwChangeSourceInitializeInternal"
0x1800133b3  call    FwReportReturnError
0x1800133b8  test    ebx, ebx
0x1800133ba  jns     loc_180013321
0x1800133c0  test    edi, edi
0x1800133c2  jnz     loc_1800132F0
0x1800133c8  mov     rcx, cs:?gFwChangeSource@@3PAUFW_CHANGE_SOURCE_COMPONENT_@@A; FW_CHANGE_SOURCE_COMPONENT_ near * gFwChangeSource
0x1800133cf  call    FwRegCloseKey
0x1800133d4  mov     cs:?gFwChangeSource@@3PAUFW_CHANGE_SOURCE_COMPONENT_@@A, 0; FW_CHANGE_SOURCE_COMPONENT_ near * gFwChangeSource
0x1800133df  mov     cs:dword_18003C5A4, edi
0x1800133e5  jmp     loc_180013311
```
