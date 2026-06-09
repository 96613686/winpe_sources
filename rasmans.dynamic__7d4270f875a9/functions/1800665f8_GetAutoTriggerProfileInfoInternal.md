# GetAutoTriggerProfileInfoInternal

- ea: `0x1800665f8`
- end: `0x1800668f0`
- name: `GetAutoTriggerProfileInfoInternal`
- size: `760`
- prototype: `__int64 __usercall@<rax>(PVOID pvData@<rcx>, PVOID)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180066ca4`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x1800665f8`
- `0x180069cc0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800666bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800666bb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006672f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006679c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180066825`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006672f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006679c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180066825`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180066894`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180066894`

## string_xrefs

- `0x180066690`: `SYSTEM\CurrentControlSet\Services\RasMan\Config`
- `0x1800666a1`: `OSDATA\SYSTEM\CurrentControlSet\Services\RasMan\Config`
- `0x18006670b`: `AutoTriggerProfilePhonebookPath`

## pseudocode

```c
__int64 __fastcall GetAutoTriggerProfileInfoInternal(_WORD *pvData, __int64 a2, _WORD *a3, DWORD a4, _OWORD *a5)
{
  struct _LIST_ENTRY *v7; // rcx
  int v8; // eax
  const WCHAR *v9; // rdx
  unsigned int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // r9
  unsigned int ValueW; // eax
  unsigned int v15; // eax
  HKEY v16; // rcx
  PVOID pvDataa; // [rsp+28h] [rbp-18h]
  HKEY hkey; // [rsp+70h] [rbp+30h] BYREF
  DWORD pcbData; // [rsp+88h] [rbp+48h] BYREF

  pcbData = a4;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x1000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 77, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  hkey = 0;
  pcbData = 0;
  if ( pvData && a3 )
  {
    *pvData = 0;
    *a3 = 0;
    v8 = StateSepEnabled();
    v9 = L"OSDATA\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
    if ( !v8 )
      v9 = L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
    v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v9, 0, 0x20019u, &hkey);
    v11 = v10;
    if ( v10 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x1000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v12 = 79;
LABEL_14:
        v13 = v10;
LABEL_36:
        WPP_SF_d(v7[1].Flink, v12, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, v13);
LABEL_37:
        v7 = WPP_GLOBAL_Control;
        goto LABEL_38;
      }
      goto LABEL_38;
    }
    pcbData = 522;
    ValueW = RegGetValueW(hkey, 0, L"AutoTriggerProfilePhonebookPath", 2u, 0, pvData, &pcbData);
    if ( ValueW
      && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x1000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 82, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, ValueW);
    }
    pcbData = 514;
    v15 = RegGetValueW(hkey, 0, L"AutoTriggerProfileEntryName", 2u, 0, a3, &pcbData);
    v11 = v15;
    if ( v15 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x1000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
LABEL_26:
        if ( !a5 )
          goto LABEL_38;
        pcbData = 16;
        v16 = hkey;
        pvDataa = a5;
        *a5 = 0;
        v10 = RegGetValueW(v16, 0, L"AutoTriggerProfileGUID", 8u, 0, pvDataa, &pcbData);
        v11 = v10;
        if ( !v10 )
          goto LABEL_37;
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x1000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          v12 = 84;
          goto LABEL_14;
        }
LABEL_38:
        if ( hkey )
        {
          RegCloseKey(hkey);
          v7 = WPP_GLOBAL_Control;
          hkey = 0;
        }
        goto LABEL_40;
      }
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 83, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, v15);
    }
    v7 = WPP_GLOBAL_Control;
    goto LABEL_26;
  }
  v11 = 87;
  if ( v7 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    return v11;
  if ( (HIDWORD(v7[1].Blink) & 0x1000) != 0 && BYTE1(v7[1].Blink) >= 2u )
  {
    v12 = 78;
    v13 = 87;
    goto LABEL_36;
  }
LABEL_40:
  if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v7[1].Blink) & 0x1000) != 0
    && BYTE1(v7[1].Blink) >= 6u )
  {
    WPP_SF_d(v7[1].Flink, 85, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, v11);
  }
  return v11;
}

```

## disassembly

```asm
0x1800665f8  mov     [rsp-28h+arg_8], rbx
0x1800665fd  mov     [rsp-28h+arg_10], rsi
0x180066602  mov     [rsp-28h+arg_18], r9d
0x180066607  push    rbp
0x180066608  push    rdi
0x180066609  push    r12
0x18006660b  push    r13
0x18006660d  push    r15
0x18006660f  mov     rbp, rsp
0x180066612  sub     rsp, 40h
0x180066616  mov     rsi, r8
0x180066619  mov     rdi, rcx
0x18006661c  mov     rcx, cs:WPP_GLOBAL_Control
0x180066623  lea     r12, WPP_GLOBAL_Control
0x18006662a  lea     r13, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x180066631  mov     r15d, 1000h
0x180066637  cmp     rcx, r12
0x18006663a  jz      short loc_180066660
0x18006663c  test    [rcx+1Ch], r15d
0x180066640  jz      short loc_180066660
0x180066642  cmp     byte ptr [rcx+19h], 6
0x180066646  jb      short loc_180066660
0x180066648  mov     rcx, [rcx+10h]
0x18006664c  mov     edx, 4Dh ; 'M'
0x180066651  mov     r8, r13
0x180066654  call    WPP_SF_
0x180066659  mov     rcx, cs:WPP_GLOBAL_Control
0x180066660  mov     [rbp+hkey], 0
0x180066668  mov     [rbp+arg_18], 0
0x18006666f  test    rdi, rdi
0x180066672  jz      loc_180066859
0x180066678  test    rsi, rsi
0x18006667b  jz      loc_180066859
0x180066681  xor     eax, eax
0x180066683  mov     [rdi], ax
0x180066686  mov     [rsi], ax
0x180066689  call    StateSepEnabled
0x18006668e  test    eax, eax
0x180066690  lea     rcx, aSystemCurrentc_21; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x180066697  lea     rax, [rbp+hkey]
0x18006669b  mov     r9d, 20019h; samDesired
0x1800666a1  lea     rdx, aOsdataSystemCu_0; "OSDATA\\SYSTEM\\CurrentControlSet\\Serv"...
0x1800666a8  mov     [rsp+40h+phkResult], rax; phkResult
0x1800666ad  cmovz   rdx, rcx; lpSubKey
0x1800666b1  xor     r8d, r8d; ulOptions
0x1800666b4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800666bb  call    cs:__imp_RegOpenKeyExW
0x1800666c2  nop     dword ptr [rax+rax+00h]
0x1800666c7  mov     ebx, eax
0x1800666c9  test    eax, eax
0x1800666cb  jz      short loc_1800666FE
0x1800666cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800666d4  cmp     rcx, r12
0x1800666d7  jz      loc_180066888
0x1800666dd  test    [rcx+1Ch], r15d
0x1800666e1  jz      loc_180066888
0x1800666e7  cmp     byte ptr [rcx+19h], 2
0x1800666eb  jb      loc_180066888
0x1800666f1  mov     edx, 4Fh ; 'O'
0x1800666f6  mov     r9d, eax
0x1800666f9  jmp     loc_180066875
0x1800666fe  mov     rcx, [rbp+hkey]; hkey
0x180066702  lea     rax, [rbp+arg_18]
0x180066706  mov     [rsp+40h+pcbData], rax; pcbData
0x18006670b  lea     r8, aAutotriggerpro_5; "AutoTriggerProfilePhonebookPath"
0x180066712  mov     [rsp+40h+pvData], rdi; pvData
0x180066717  mov     r9d, 2; dwFlags
0x18006671d  xor     edx, edx; lpSubKey
0x18006671f  mov     [rsp+40h+phkResult], 0; pdwType
0x180066728  mov     [rbp+arg_18], 20Ah
0x18006672f  call    cs:__imp_RegGetValueW
0x180066736  nop     dword ptr [rax+rax+00h]
0x18006673b  test    eax, eax
0x18006673d  jz      short loc_18006676B
0x18006673f  mov     rcx, cs:WPP_GLOBAL_Control
0x180066746  cmp     rcx, r12
0x180066749  jz      short loc_18006676B
0x18006674b  test    [rcx+1Ch], r15d
0x18006674f  jz      short loc_18006676B
0x180066751  cmp     byte ptr [rcx+19h], 2
0x180066755  jb      short loc_18006676B
0x180066757  mov     rcx, [rcx+10h]
0x18006675b  mov     edx, 52h ; 'R'
0x180066760  mov     r9d, eax
0x180066763  mov     r8, r13
0x180066766  call    WPP_SF_d
0x18006676b  mov     rcx, [rbp+hkey]; hkey
0x18006676f  lea     rax, [rbp+arg_18]
0x180066773  mov     [rsp+40h+pcbData], rax; pcbData
0x180066778  lea     r8, aAutotriggerpro_6; "AutoTriggerProfileEntryName"
0x18006677f  mov     [rsp+40h+pvData], rsi; pvData
0x180066784  mov     r9d, 2; dwFlags
0x18006678a  xor     edx, edx; lpSubKey
0x18006678c  mov     [rsp+40h+phkResult], 0; pdwType
0x180066795  mov     [rbp+arg_18], 202h
0x18006679c  call    cs:__imp_RegGetValueW
0x1800667a3  nop     dword ptr [rax+rax+00h]
0x1800667a8  mov     ebx, eax
0x1800667aa  test    eax, eax
0x1800667ac  jz      short loc_1800667DA
0x1800667ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800667b5  cmp     rcx, r12
0x1800667b8  jz      short loc_1800667E1
0x1800667ba  test    [rcx+1Ch], r15d
0x1800667be  jz      short loc_1800667E1
0x1800667c0  cmp     byte ptr [rcx+19h], 2
0x1800667c4  jb      short loc_1800667E1
0x1800667c6  mov     rcx, [rcx+10h]
0x1800667ca  mov     edx, 53h ; 'S'
0x1800667cf  mov     r9d, eax
0x1800667d2  mov     r8, r13
0x1800667d5  call    WPP_SF_d
0x1800667da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800667e1  mov     rax, [rbp+arg_20]
0x1800667e5  test    rax, rax
0x1800667e8  jz      loc_180066888
0x1800667ee  lea     rcx, [rbp+arg_18]
0x1800667f2  mov     [rbp+arg_18], 10h
0x1800667f9  mov     [rsp+40h+pcbData], rcx; pcbData
0x1800667fe  lea     r8, aAutotriggerpro_7; "AutoTriggerProfileGUID"
0x180066805  mov     rcx, [rbp+hkey]; hkey
0x180066809  xorps   xmm0, xmm0
0x18006680c  mov     [rsp+40h+pvData], rax; pvData
0x180066811  mov     r9d, 8; dwFlags
0x180066817  xor     edx, edx; lpSubKey
0x180066819  mov     [rsp+40h+phkResult], 0; pdwType
0x180066822  movups  xmmword ptr [rax], xmm0
0x180066825  call    cs:__imp_RegGetValueW
0x18006682c  nop     dword ptr [rax+rax+00h]
0x180066831  mov     ebx, eax
0x180066833  test    eax, eax
0x180066835  jz      short loc_180066881
0x180066837  mov     rcx, cs:WPP_GLOBAL_Control
0x18006683e  cmp     rcx, r12
0x180066841  jz      short loc_180066888
0x180066843  test    [rcx+1Ch], r15d
0x180066847  jz      short loc_180066888
0x180066849  cmp     byte ptr [rcx+19h], 2
0x18006684d  jb      short loc_180066888
0x18006684f  mov     edx, 54h ; 'T'
0x180066854  jmp     loc_1800666F6
0x180066859  mov     ebx, 57h ; 'W'
0x18006685e  cmp     rcx, r12
0x180066861  jz      short loc_1800668D4
0x180066863  test    [rcx+1Ch], r15d
0x180066867  jz      short loc_1800668AF
0x180066869  cmp     byte ptr [rcx+19h], 2
0x18006686d  jb      short loc_1800668AF
0x18006686f  lea     edx, [rbx-9]
0x180066872  mov     r9d, ebx
0x180066875  mov     rcx, [rcx+10h]
0x180066879  mov     r8, r13
0x18006687c  call    WPP_SF_d
0x180066881  mov     rcx, cs:WPP_GLOBAL_Control
0x180066888  mov     rax, [rbp+hkey]
0x18006688c  test    rax, rax
0x18006688f  jz      short loc_1800668AF
0x180066891  mov     rcx, rax; hKey
0x180066894  call    cs:__imp_RegCloseKey
0x18006689b  nop     dword ptr [rax+rax+00h]
0x1800668a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800668a7  mov     [rbp+hkey], 0
0x1800668af  cmp     rcx, r12
0x1800668b2  jz      short loc_1800668D4
0x1800668b4  test    [rcx+1Ch], r15d
0x1800668b8  jz      short loc_1800668D4
0x1800668ba  cmp     byte ptr [rcx+19h], 6
0x1800668be  jb      short loc_1800668D4
0x1800668c0  mov     rcx, [rcx+10h]
0x1800668c4  mov     edx, 55h ; 'U'
0x1800668c9  mov     r9d, ebx
0x1800668cc  mov     r8, r13
0x1800668cf  call    WPP_SF_d
0x1800668d4  lea     r11, [rsp+40h+var_s0]
0x1800668d9  mov     eax, ebx
0x1800668db  mov     rbx, [r11+38h]
0x1800668df  mov     rsi, [r11+40h]
0x1800668e3  mov     rsp, r11
0x1800668e6  pop     r15
0x1800668e8  pop     r13
0x1800668ea  pop     r12
0x1800668ec  pop     rdi
0x1800668ed  pop     rbp
0x1800668ee  retn
```
