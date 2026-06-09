# CflApiNew::GetCorrelationVectorInternal

- ea: `0x18002a498`
- end: `0x18002a69e`
- name: `CflApiNew::GetCorrelationVectorInternal`
- size: `518`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800107e0`
- `0x180029614`
- `0x18002aee8`

## callees

- `0x1800067c4`
- `0x180010700`
- `0x18001332c`
- `0x18001f948`
- `0x18002a498`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a54c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a617`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a54c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a617`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a4ce`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a4ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a4f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a65d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a68e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a4f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a65d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a68e`

## string_xrefs

- `0x18002a55d`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x18002a5c0`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x18002a628`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x18002a674`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CflApiNew::GetCorrelationVectorInternal(_QWORD *a1)
{
  LSTATUS v2; // eax
  unsigned int v3; // ebx
  unsigned int v4; // edi
  __int64 v6; // rdx
  unsigned int ValueW; // eax
  int v8; // eax
  PVOID v9; // rbx
  unsigned int v10; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-30h]
  unsigned int phkResulta; // [rsp+20h] [rbp-30h]
  PVOID hMem[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  DWORD pcbData; // [rsp+78h] [rbp+28h] BYREF
  DWORD pdwType; // [rsp+80h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+38h] BYREF

  hKey = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\CFL\\CorrelationVector",
         0,
         1u,
         &hKey);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( (v3 & 0x80000000) != 0 )
  {
    v4 = -2147024894;
    if ( v3 == -2147024894 )
    {
LABEL_5:
      if ( hKey )
        RegCloseKey(hKey);
      return v4;
    }
    v6 = 1466;
    goto LABEL_25;
  }
  pcbData = 0;
  pdwType = 0;
  ValueW = RegGetValueW(hKey, 0, L"WSI", 2u, &pdwType, 0, &pcbData);
  if ( ValueW )
  {
    v3 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x5C6,
           (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
           (const char *)ValueW,
           phkResult);
LABEL_26:
    if ( hKey )
      RegCloseKey(hKey);
    return v3;
  }
  if ( pdwType != 1 )
  {
    v3 = -2147024809;
    v6 = 1480;
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
      (const char *)v3,
      phkResult);
    goto LABEL_26;
  }
  if ( !pcbData || (pcbData & 1) != 0 )
  {
    v3 = -2147024872;
    v6 = 1483;
    goto LABEL_25;
  }
  hMem[0] = 0;
  v8 = CflApiNew::AllocBuffer_unsigned_short_((unsigned __int64)pcbData >> 1, hMem);
  v3 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5CE,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
      (const char *)(unsigned int)v8,
      phkResult);
    if ( hMem[0] )
      CflFreeBuffer(hMem[0]);
    goto LABEL_26;
  }
  v9 = hMem[0];
  v10 = RegGetValueW(hKey, 0, L"WSI", 2u, 0, hMem[0], &pcbData);
  if ( v10 )
  {
    v4 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x5D7,
           (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
           (const char *)v10,
           phkResulta);
    if ( v9 )
      CflFreeBuffer(v9);
    goto LABEL_5;
  }
  *a1 = v9;
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18002a498  push    rbp
0x18002a49a  push    rbx
0x18002a49b  push    rdi
0x18002a49c  mov     rbp, rsp
0x18002a49f  sub     rsp, 50h
0x18002a4a3  mov     rdi, rcx
0x18002a4a6  mov     [rbp+hKey], 0
0x18002a4ae  lea     rax, [rbp+hKey]
0x18002a4b2  mov     [rsp+50h+phkResult], rax; phkResult
0x18002a4b7  mov     r9d, 1; samDesired
0x18002a4bd  xor     r8d, r8d; ulOptions
0x18002a4c0  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002a4c7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002a4ce  call    cs:__imp_RegOpenKeyExW
0x18002a4d4  mov     ebx, eax
0x18002a4d6  test    eax, eax
0x18002a4d8  jle     short loc_18002A4E3
0x18002a4da  movzx   ebx, ax
0x18002a4dd  or      ebx, 80070000h
0x18002a4e3  test    ebx, ebx
0x18002a4e5  jns     short loc_18002A510
0x18002a4e7  mov     edi, 80070002h
0x18002a4ec  cmp     ebx, edi
0x18002a4ee  jnz     short loc_18002A506
0x18002a4f0  mov     rcx, [rbp+hKey]; hKey
0x18002a4f4  test    rcx, rcx
0x18002a4f7  jz      short loc_18002A4FF
0x18002a4f9  call    cs:__imp_RegCloseKey
0x18002a4ff  mov     eax, edi
0x18002a501  jmp     loc_18002A696
0x18002a506  mov     edx, 5BAh
0x18002a50b  jmp     loc_18002A671
0x18002a510  mov     [rbp+arg_8], 0
0x18002a517  mov     [rbp+pdwType], 0
0x18002a51e  lea     rax, [rbp+arg_8]
0x18002a522  mov     [rsp+50h+pcbData], rax; pcbData
0x18002a527  mov     [rsp+50h+pvData], 0; pvData
0x18002a530  lea     rax, [rbp+pdwType]
0x18002a534  mov     [rsp+50h+phkResult], rax; int
0x18002a539  mov     r9d, 2; dwFlags
0x18002a53f  lea     r8, aWsi; "WSI"
0x18002a546  xor     edx, edx; lpSubKey
0x18002a548  mov     rcx, [rbp+hKey]; hkey
0x18002a54c  call    cs:__imp_RegGetValueW
0x18002a552  test    eax, eax
0x18002a554  jz      short loc_18002A575
0x18002a556  mov     rcx, [rbp+18h]; this
0x18002a55a  mov     r9d, eax; char *
0x18002a55d  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18002a564  mov     edx, 5C6h; void *
0x18002a569  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002a56e  mov     ebx, eax
0x18002a570  jmp     loc_18002A685
0x18002a575  cmp     [rbp+pdwType], 1
0x18002a579  jz      short loc_18002A58A
0x18002a57b  mov     ebx, 80070057h
0x18002a580  mov     edx, 5C8h
0x18002a585  jmp     loc_18002A671
0x18002a58a  mov     eax, [rbp+arg_8]
0x18002a58d  test    eax, eax
0x18002a58f  jz      loc_18002A667
0x18002a595  test    al, 1
0x18002a597  jnz     loc_18002A667
0x18002a59d  mov     [rbp+hMem], 0
0x18002a5a5  mov     ecx, eax
0x18002a5a7  shr     rcx, 1
0x18002a5aa  lea     rdx, [rbp+hMem]
0x18002a5ae  call    CflApiNew__AllocBuffer_unsigned_short_
0x18002a5b3  mov     ebx, eax
0x18002a5b5  test    eax, eax
0x18002a5b7  jns     short loc_18002A5E9
0x18002a5b9  mov     rcx, [rbp+18h]; this
0x18002a5bd  mov     r9d, eax; char *
0x18002a5c0  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18002a5c7  mov     edx, 5CEh; void *
0x18002a5cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a5d1  nop
0x18002a5d2  mov     rcx, [rbp+hMem]; hMem
0x18002a5d6  test    rcx, rcx
0x18002a5d9  jz      loc_18002A685
0x18002a5df  call    CflFreeBuffer
0x18002a5e4  jmp     loc_18002A685
0x18002a5e9  lea     rax, [rbp+arg_8]
0x18002a5ed  mov     [rsp+50h+pcbData], rax; pcbData
0x18002a5f2  mov     rbx, [rbp+hMem]
0x18002a5f6  mov     [rsp+50h+pvData], rbx; pvData
0x18002a5fb  mov     [rsp+50h+phkResult], 0; unsigned int
0x18002a604  mov     r9d, 2; dwFlags
0x18002a60a  lea     r8, aWsi; "WSI"
0x18002a611  xor     edx, edx; lpSubKey
0x18002a613  mov     rcx, [rbp+hKey]; hkey
0x18002a617  call    cs:__imp_RegGetValueW
0x18002a61d  test    eax, eax
0x18002a61f  jz      short loc_18002A651
0x18002a621  mov     rcx, [rbp+18h]; this
0x18002a625  mov     r9d, eax; char *
0x18002a628  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18002a62f  mov     edx, 5D7h; void *
0x18002a634  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002a639  mov     edi, eax
0x18002a63b  test    rbx, rbx
0x18002a63e  jz      loc_18002A4F0
0x18002a644  mov     rcx, rbx; hMem
0x18002a647  call    CflFreeBuffer
0x18002a64c  jmp     loc_18002A4F0
0x18002a651  mov     [rdi], rbx
0x18002a654  mov     rcx, [rbp+hKey]; hKey
0x18002a658  test    rcx, rcx
0x18002a65b  jz      short loc_18002A663
0x18002a65d  call    cs:__imp_RegCloseKey
0x18002a663  xor     eax, eax
0x18002a665  jmp     short loc_18002A696
0x18002a667  mov     ebx, 80070018h
0x18002a66c  mov     edx, 5CBh; void *
0x18002a671  mov     r9d, ebx; char *
0x18002a674  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18002a67b  mov     rcx, [rbp+18h]; this
0x18002a67f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a684  nop
0x18002a685  mov     rcx, [rbp+hKey]; hKey
0x18002a689  test    rcx, rcx
0x18002a68c  jz      short loc_18002A694
0x18002a68e  call    cs:__imp_RegCloseKey
0x18002a694  mov     eax, ebx
0x18002a696  add     rsp, 50h
0x18002a69a  pop     rdi
0x18002a69b  pop     rbx
0x18002a69c  pop     rbp
0x18002a69d  retn
```
