# GetAutoTriggerProfileInfoInternalEx

- ea: `0x1800c623c`
- end: `0x1800c6645`
- name: `GetAutoTriggerProfileInfoInternalEx`
- size: `1033`
- prototype: `__int64 __usercall@<rax>(PVOID pvData@<rcx>, PVOID, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x1800c69f8`

## callees

- `0x18004e580`
- `0x18004eab4`
- `0x18007efdc`
- `0x1800c623c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c6326`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c6326`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c6409`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c64a8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c6554`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c6409`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c64a8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c6554`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c65cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c65cf`
- `rtutils!TracePrintfExA` at `0x1800c6383`
- `rtutils!TracePrintfExA` at `0x1800c6468`
- `rtutils!TracePrintfExA` at `0x1800c6503`
- `rtutils!TracePrintfExA` at `0x1800c65af`
- `rtutils!TracePrintfExA` at `0x1800c6383`
- `rtutils!TracePrintfExA` at `0x1800c6468`
- `rtutils!TracePrintfExA` at `0x1800c6503`
- `rtutils!TracePrintfExA` at `0x1800c65af`

## string_xrefs

- `0x1800c62cf`: `SYSTEM\CurrentControlSet\Services\RasMan\Config`
- `0x1800c634d`: `SYSTEM\CurrentControlSet\Services\RasMan\Config`
- `0x1800c62d9`: `OSDATA\SYSTEM\CurrentControlSet\Services\RasMan\Config`
- `0x1800c63e5`: `AutoTriggerProfilePhonebookPath`
- `0x1800c65a4`: `GetAutoTriggerProfileInfoInternal: Could not read connection GUID 0x%.8x`
- `0x1800c645f`: `GetAutoTriggerProfileInfoInternal: Could not read phonebookpath 0x%.8x`
- `0x1800c64f8`: `GetAutoTriggerProfileInfoInternal: Could not read EntryName 0x%.8x`
- `0x1800c636c`: `GetAutoTriggerProfileInfoInternal: Could not open regkey %S 0x%.8x`
- `0x1800c6302`: `SYSTEM\CurrentControlSet\Services\RasMan\DeviceTunnel`
- `0x1800c635f`: `SYSTEM\CurrentControlSet\Services\RasMan\DeviceTunnel`
- `0x1800c62fb`: `OSDATA\SYSTEM\CurrentControlSet\Services\RasMan\DeviceTunnel`
- `0x1800c6358`: `OSDATA\SYSTEM\CurrentControlSet\Services\RasMan\DeviceTunnel`

## pseudocode

```c
__int64 __fastcall GetAutoTriggerProfileInfoInternalEx(
        _WORD *pvData,
        __int64 a2,
        _WORD *a3,
        __int64 a4,
        _OWORD *a5,
        int a6)
{
  _QWORD *v8; // rcx
  int v9; // r14d
  const wchar_t *v10; // rdi
  int v11; // eax
  const WCHAR *v12; // rdx
  unsigned int v13; // ebx
  bool v14; // zf
  const WCHAR *v15; // rax
  __int64 v16; // rdx
  unsigned int ValueW; // eax
  unsigned int v18; // ebx
  unsigned int v19; // eax
  HKEY v20; // rcx
  unsigned int v21; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-20h]
  PVOID pvDataa; // [rsp+28h] [rbp-18h]
  HKEY hkey; // [rsp+70h] [rbp+30h] BYREF
  DWORD pcbData; // [rsp+88h] [rbp+48h] BYREF

  pcbData = a4;
  v8 = WPP_GLOBAL_Control;
  v9 = a6;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    LOBYTE(a4) = a6 != 0;
    WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, a4);
    v8 = WPP_GLOBAL_Control;
  }
  hkey = 0;
  pcbData = 0;
  if ( pvData && a3 )
  {
    *pvData = 0;
    v10 = L"OSDATA\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
    *a3 = 0;
    v11 = StateSepEnabled();
    if ( v9 )
    {
      v12 = L"OSDATA\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
      if ( !v11 )
        v12 = L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
    }
    else
    {
      v12 = L"OSDATA\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\DeviceTunnel";
      if ( !v11 )
        v12 = L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\DeviceTunnel";
    }
    v13 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v12, 0, 0x20019u, &hkey);
    if ( v13 )
    {
      if ( g_dwTraceId != -1 )
      {
        v14 = (unsigned int)StateSepEnabled() == 0;
        if ( v9 )
        {
          v15 = L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
        }
        else
        {
          v10 = L"OSDATA\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\DeviceTunnel";
          v15 = L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\DeviceTunnel";
        }
        if ( v14 )
          v10 = v15;
        LODWORD(phkResult) = v13;
        TracePrintfExA(
          g_dwTraceId,
          0xCu,
          "GetAutoTriggerProfileInfoInternal: Could not open regkey %S 0x%.8x",
          v10,
          phkResult);
      }
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_50;
      }
      v16 = 88;
      goto LABEL_25;
    }
    pcbData = 522;
    ValueW = RegGetValueW(hkey, 0, L"AutoTriggerProfilePhonebookPath", 2u, 0, pvData, &pcbData);
    v18 = ValueW;
    if ( ValueW )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, ValueW);
      }
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "GetAutoTriggerProfileInfoInternal: Could not read phonebookpath 0x%.8x", v18);
    }
    pcbData = 514;
    v19 = RegGetValueW(hkey, 0, L"AutoTriggerProfileEntryName", 2u, 0, a3, &pcbData);
    v13 = v19;
    if ( v19 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, v19);
        v8 = WPP_GLOBAL_Control;
      }
      if ( g_dwTraceId == -1 )
      {
LABEL_41:
        if ( a5 )
        {
          pcbData = 16;
          v20 = hkey;
          pvDataa = a5;
          *a5 = 0;
          v21 = RegGetValueW(v20, 0, L"AutoTriggerProfileGUID", 8u, 0, pvDataa, &pcbData);
          v13 = v21;
          if ( v21 )
          {
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, v21);
              v8 = WPP_GLOBAL_Control;
            }
            if ( g_dwTraceId == -1 )
              goto LABEL_50;
            TracePrintfExA(
              g_dwTraceId,
              0xCu,
              "GetAutoTriggerProfileInfoInternal: Could not read connection GUID 0x%.8x",
              v13);
          }
          v8 = WPP_GLOBAL_Control;
        }
LABEL_50:
        if ( hkey )
        {
          RegCloseKey(hkey);
          v8 = WPP_GLOBAL_Control;
          hkey = 0;
        }
        goto LABEL_52;
      }
      TracePrintfExA(g_dwTraceId, 0xCu, "GetAutoTriggerProfileInfoInternal: Could not read EntryName 0x%.8x", v13);
    }
    v8 = WPP_GLOBAL_Control;
    goto LABEL_41;
  }
  v13 = 87;
  if ( v8 == &WPP_GLOBAL_Control )
    return v13;
  if ( (*((_DWORD *)v8 + 7) & 0x1000) != 0 && *((_BYTE *)v8 + 25) >= 2u )
  {
    v16 = 87;
LABEL_25:
    WPP_SF_d(v8[2], v16, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, v13);
    v8 = WPP_GLOBAL_Control;
    goto LABEL_50;
  }
LABEL_52:
  if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x1000) != 0 && *((_BYTE *)v8 + 25) >= 6u )
    WPP_SF_d(v8[2], 95, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, v13);
  return v13;
}

```

## disassembly

```asm
0x1800c623c  mov     [rsp-28h+arg_8], rbx
0x1800c6241  mov     [rsp-28h+arg_10], rsi
0x1800c6246  mov     [rsp-28h+arg_18], r9d
0x1800c624b  push    rbp
0x1800c624c  push    rdi
0x1800c624d  push    r13
0x1800c624f  push    r14
0x1800c6251  push    r15
0x1800c6253  mov     rbp, rsp
0x1800c6256  sub     rsp, 40h
0x1800c625a  mov     r15, r8
0x1800c625d  mov     rsi, rcx
0x1800c6260  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c6267  lea     rdi, WPP_GLOBAL_Control
0x1800c626e  mov     r14d, [rbp+arg_28]
0x1800c6272  mov     r13d, 1000h
0x1800c6278  cmp     rcx, rdi
0x1800c627b  jz      short loc_1800C62AC
0x1800c627d  test    [rcx+1Ch], r13d
0x1800c6281  jz      short loc_1800C62AC
0x1800c6283  cmp     byte ptr [rcx+19h], 6
0x1800c6287  jb      short loc_1800C62AC
0x1800c6289  mov     rcx, [rcx+10h]
0x1800c628d  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x1800c6294  test    r14d, r14d
0x1800c6297  mov     edx, 56h ; 'V'
0x1800c629c  setnz   r9b
0x1800c62a0  call    WPP_SF_c
0x1800c62a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c62ac  mov     [rbp+hkey], 0
0x1800c62b4  mov     [rbp+arg_18], 0
0x1800c62bb  test    rsi, rsi
0x1800c62be  jz      loc_1800C6628
0x1800c62c4  test    r15, r15
0x1800c62c7  jz      loc_1800C6628
0x1800c62cd  xor     eax, eax
0x1800c62cf  lea     rbx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x1800c62d6  mov     [rsi], ax
0x1800c62d9  lea     rdi, aOsdataSystemCu_0; "OSDATA\\SYSTEM\\CurrentControlSet\\Serv"...
0x1800c62e0  mov     [r15], ax
0x1800c62e4  call    StateSepEnabled
0x1800c62e9  test    r14d, r14d
0x1800c62ec  jz      short loc_1800C62F9
0x1800c62ee  test    eax, eax
0x1800c62f0  mov     rdx, rdi
0x1800c62f3  cmovz   rdx, rbx
0x1800c62f7  jmp     short loc_1800C630D
0x1800c62f9  test    eax, eax
0x1800c62fb  lea     rdx, aOsdataSystemCu_1; "OSDATA\\SYSTEM\\CurrentControlSet\\Serv"...
0x1800c6302  lea     rax, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x1800c6309  cmovz   rdx, rax; lpSubKey
0x1800c630d  lea     rax, [rbp+hkey]
0x1800c6311  mov     r9d, 20019h; samDesired
0x1800c6317  xor     r8d, r8d; ulOptions
0x1800c631a  mov     [rsp+40h+phkResult], rax; phkResult
0x1800c631f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c6326  call    cs:__imp_RegOpenKeyExW
0x1800c632c  mov     ebx, eax
0x1800c632e  test    eax, eax
0x1800c6330  jz      loc_1800C63D8
0x1800c6336  or      esi, 0FFFFFFFFh
0x1800c6339  cmp     cs:g_dwTraceId, esi
0x1800c633f  jz      short loc_1800C6389
0x1800c6341  call    StateSepEnabled
0x1800c6346  test    r14d, r14d
0x1800c6349  jz      short loc_1800C6356
0x1800c634b  test    eax, eax
0x1800c634d  lea     rax, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x1800c6354  jmp     short loc_1800C6366
0x1800c6356  test    eax, eax
0x1800c6358  lea     rdi, aOsdataSystemCu_1; "OSDATA\\SYSTEM\\CurrentControlSet\\Serv"...
0x1800c635f  lea     rax, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x1800c6366  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c636c  lea     r8, aGetautotrigger_3; "GetAutoTriggerProfileInfoInternal: Coul"...
0x1800c6373  cmovz   rdi, rax
0x1800c6377  mov     dword ptr [rsp+40h+phkResult], ebx
0x1800c637b  mov     r9, rdi
0x1800c637e  mov     edx, 0Ch; dwFlags
0x1800c6383  call    cs:__imp_TracePrintfExA
0x1800c6389  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c6390  lea     rdi, WPP_GLOBAL_Control
0x1800c6397  cmp     rcx, rdi
0x1800c639a  jz      loc_1800C65C3
0x1800c63a0  test    [rcx+1Ch], r13d
0x1800c63a4  jz      loc_1800C65C3
0x1800c63aa  cmp     byte ptr [rcx+19h], 2
0x1800c63ae  jb      loc_1800C65C3
0x1800c63b4  mov     edx, 58h ; 'X'
0x1800c63b9  mov     rcx, [rcx+10h]
0x1800c63bd  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x1800c63c4  mov     r9d, ebx
0x1800c63c7  call    WPP_SF_d
0x1800c63cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c63d3  jmp     loc_1800C65C3
0x1800c63d8  mov     rcx, [rbp+hkey]; hkey
0x1800c63dc  lea     rax, [rbp+arg_18]
0x1800c63e0  mov     [rsp+40h+pcbData], rax; pcbData
0x1800c63e5  lea     r8, aAutotriggerpro_1; "AutoTriggerProfilePhonebookPath"
0x1800c63ec  mov     [rsp+40h+pvData], rsi; pvData
0x1800c63f1  mov     r9d, 2; dwFlags
0x1800c63f7  xor     edx, edx; lpSubKey
0x1800c63f9  mov     [rsp+40h+phkResult], 0; pdwType
0x1800c6402  mov     [rbp+arg_18], 20Ah
0x1800c6409  call    cs:__imp_RegGetValueW
0x1800c640f  or      esi, 0FFFFFFFFh
0x1800c6412  mov     edi, 0Ch
0x1800c6417  mov     ebx, eax
0x1800c6419  test    eax, eax
0x1800c641b  jz      short loc_1800C6470
0x1800c641d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c6424  lea     r14, WPP_GLOBAL_Control
0x1800c642b  cmp     rcx, r14
0x1800c642e  jz      short loc_1800C6452
0x1800c6430  test    [rcx+1Ch], r13d
0x1800c6434  jz      short loc_1800C6452
0x1800c6436  cmp     byte ptr [rcx+19h], 2
0x1800c643a  jb      short loc_1800C6452
0x1800c643c  mov     rcx, [rcx+10h]
0x1800c6440  lea     edx, [rdi+50h]
0x1800c6443  mov     r9d, eax
0x1800c6446  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x1800c644d  call    WPP_SF_d
0x1800c6452  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c6458  cmp     ecx, esi
0x1800c645a  jz      short loc_1800C6477
0x1800c645c  mov     r9d, ebx
0x1800c645f  lea     r8, aGetautotrigger_0; "GetAutoTriggerProfileInfoInternal: Coul"...
0x1800c6466  mov     edx, edi; dwFlags
0x1800c6468  call    cs:__imp_TracePrintfExA
0x1800c646e  jmp     short loc_1800C6477
0x1800c6470  lea     r14, WPP_GLOBAL_Control
0x1800c6477  mov     rcx, [rbp+hkey]; hkey
0x1800c647b  lea     rax, [rbp+arg_18]
0x1800c647f  mov     [rsp+40h+pcbData], rax; pcbData
0x1800c6484  lea     r8, aAutotriggerpro_2; "AutoTriggerProfileEntryName"
0x1800c648b  mov     [rsp+40h+pvData], r15; pvData
0x1800c6490  mov     r9d, 2; dwFlags
0x1800c6496  xor     edx, edx; lpSubKey
0x1800c6498  mov     [rsp+40h+phkResult], 0; pdwType
0x1800c64a1  mov     [rbp+arg_18], 202h
0x1800c64a8  call    cs:__imp_RegGetValueW
0x1800c64ae  mov     ebx, eax
0x1800c64b0  test    eax, eax
0x1800c64b2  jz      short loc_1800C6509
0x1800c64b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c64bb  cmp     rcx, r14
0x1800c64be  jz      short loc_1800C64EB
0x1800c64c0  test    [rcx+1Ch], r13d
0x1800c64c4  jz      short loc_1800C64EB
0x1800c64c6  cmp     byte ptr [rcx+19h], 2
0x1800c64ca  jb      short loc_1800C64EB
0x1800c64cc  mov     rcx, [rcx+10h]
0x1800c64d0  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x1800c64d7  mov     edx, 5Dh ; ']'
0x1800c64dc  mov     r9d, eax
0x1800c64df  call    WPP_SF_d
0x1800c64e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c64eb  mov     eax, cs:g_dwTraceId
0x1800c64f1  cmp     eax, esi
0x1800c64f3  jz      short loc_1800C6510
0x1800c64f5  mov     r9d, ebx
0x1800c64f8  lea     r8, aGetautotrigger_2; "GetAutoTriggerProfileInfoInternal: Coul"...
0x1800c64ff  mov     edx, edi; dwFlags
0x1800c6501  mov     ecx, eax; dwTraceID
0x1800c6503  call    cs:__imp_TracePrintfExA
0x1800c6509  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c6510  mov     rax, [rbp+arg_20]
0x1800c6514  test    rax, rax
0x1800c6517  jz      loc_1800C65BC
0x1800c651d  lea     rcx, [rbp+arg_18]
0x1800c6521  mov     [rbp+arg_18], 10h
0x1800c6528  mov     [rsp+40h+pcbData], rcx; pcbData
0x1800c652d  lea     r8, aAutotriggerpro_3; "AutoTriggerProfileGUID"
0x1800c6534  mov     rcx, [rbp+hkey]; hkey
0x1800c6538  xorps   xmm0, xmm0
0x1800c653b  mov     [rsp+40h+pvData], rax; pvData
0x1800c6540  mov     r9d, 8; dwFlags
0x1800c6546  xor     edx, edx; lpSubKey
0x1800c6548  mov     [rsp+40h+phkResult], 0; pdwType
0x1800c6551  movups  xmmword ptr [rax], xmm0
0x1800c6554  call    cs:__imp_RegGetValueW
0x1800c655a  mov     ebx, eax
0x1800c655c  test    eax, eax
0x1800c655e  jz      short loc_1800C65B5
0x1800c6560  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c6567  cmp     rcx, r14
0x1800c656a  jz      short loc_1800C6597
0x1800c656c  test    [rcx+1Ch], r13d
0x1800c6570  jz      short loc_1800C6597
0x1800c6572  cmp     byte ptr [rcx+19h], 2
0x1800c6576  jb      short loc_1800C6597
0x1800c6578  mov     rcx, [rcx+10h]
0x1800c657c  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x1800c6583  mov     edx, 5Eh ; '^'
0x1800c6588  mov     r9d, eax
0x1800c658b  call    WPP_SF_d
0x1800c6590  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c6597  mov     eax, cs:g_dwTraceId
0x1800c659d  cmp     eax, esi
0x1800c659f  jz      short loc_1800C65BC
0x1800c65a1  mov     r9d, ebx
0x1800c65a4  lea     r8, aGetautotrigger_1; "GetAutoTriggerProfileInfoInternal: Coul"...
0x1800c65ab  mov     edx, edi; dwFlags
0x1800c65ad  mov     ecx, eax; dwTraceID
0x1800c65af  call    cs:__imp_TracePrintfExA
0x1800c65b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c65bc  lea     rdi, WPP_GLOBAL_Control
0x1800c65c3  mov     rax, [rbp+hkey]
0x1800c65c7  test    rax, rax
0x1800c65ca  jz      short loc_1800C65E4
0x1800c65cc  mov     rcx, rax; hKey
0x1800c65cf  call    cs:__imp_RegCloseKey
0x1800c65d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c65dc  mov     [rbp+hkey], 0
0x1800c65e4  cmp     rcx, rdi
0x1800c65e7  jz      short loc_1800C660D
0x1800c65e9  test    [rcx+1Ch], r13d
0x1800c65ed  jz      short loc_1800C660D
0x1800c65ef  cmp     byte ptr [rcx+19h], 6
0x1800c65f3  jb      short loc_1800C660D
0x1800c65f5  mov     rcx, [rcx+10h]
0x1800c65f9  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x1800c6600  mov     edx, 5Fh ; '_'
0x1800c6605  mov     r9d, ebx
0x1800c6608  call    WPP_SF_d
0x1800c660d  lea     r11, [rsp+40h+var_s0]
0x1800c6612  mov     eax, ebx
0x1800c6614  mov     rbx, [r11+38h]
0x1800c6618  mov     rsi, [r11+40h]
0x1800c661c  mov     rsp, r11
0x1800c661f  pop     r15
0x1800c6621  pop     r14
0x1800c6623  pop     r13
0x1800c6625  pop     rdi
0x1800c6626  pop     rbp
0x1800c6627  retn
0x1800c6628  mov     ebx, 57h ; 'W'
0x1800c662d  cmp     rcx, rdi
0x1800c6630  jz      short loc_1800C660D
0x1800c6632  test    [rcx+1Ch], r13d
0x1800c6636  jz      short loc_1800C65E4
0x1800c6638  cmp     byte ptr [rcx+19h], 2
0x1800c663c  jb      short loc_1800C65E4
0x1800c663e  mov     edx, ebx
0x1800c6640  jmp     loc_1800C63B9
```
