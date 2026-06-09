# LogIncompleteRestoreEvent(void)

- ea: `0x1800075c4`
- end: `0x1800077e6`
- name: `?LogIncompleteRestoreEvent@@YAXXZ`
- size: `546`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007ba0`

## callees

- `0x1800075c4`
- `0x180009370`
- `0x180009464`
- `0x1800094cc`
- `0x180009578`
- `0x180009a00`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x18000762e`
- `ADVAPI32!RegGetValueW` at `0x18000762e`
- `ADVAPI32!RegCreateKeyExW` at `0x180007755`
- `ADVAPI32!RegCreateKeyExW` at `0x180007755`
- `ADVAPI32!RegDeleteValueW` at `0x180007792`
- `ADVAPI32!RegDeleteValueW` at `0x180007792`

## pseudocode

```c
void LogIncompleteRestoreEvent(void)
{
  int v0; // ebx
  LSTATUS ValueW; // eax
  __int64 v2; // r8
  __int64 v3; // rcx
  __int64 v4; // r8
  int v5; // r8d
  unsigned int pvData; // [rsp+50h] [rbp-9h] BYREF
  DWORD pdwType; // [rsp+54h] [rbp-5h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp-1h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+7h] BYREF
  _BYTE v10[16]; // [rsp+68h] [rbp+Fh] BYREF
  const wchar_t *v11; // [rsp+78h] [rbp+1Fh]
  __int64 v12; // [rsp+80h] [rbp+27h]

  pcbData = 4;
  v0 = 0;
  pdwType = 0;
  ValueW = RegGetValueW(
             HKEY_CURRENT_USER,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\FileHistory\\RestoreUI",
             L"RehydrationFilesFailed",
             0x10000012u,
             &pdwType,
             &pvData,
             &pcbData);
  v3 = (unsigned int)ValueW;
  if ( ValueW )
  {
    if ( ValueW == 234 )
    {
      LOWORD(v3) = 13;
    }
    else if ( ValueW <= 0 )
    {
      goto LABEL_12;
    }
  }
  else
  {
    LOWORD(v3) = 13;
    if ( pdwType == 4 )
    {
      if ( pvData <= 1 )
      {
        v3 = 0;
        LOBYTE(v0) = pvData == 1;
        goto LABEL_12;
      }
    }
    else if ( pcbData == 4 && (unsigned __int16)(pvData - 48) <= 1u )
    {
      LOBYTE(v0) = (_WORD)pvData == 49;
      v3 = 0;
      goto LABEL_12;
    }
  }
  v3 = (unsigned __int16)v3 | 0x80070000;
LABEL_12:
  if ( (int)v3 >= 0 )
  {
    if ( v0 && (Microsoft_Windows_FileHistory_CoreEnableBits & 8) != 0 )
    {
      v12 = 32;
      v11 = L"FileHistory.exe";
      McGenEventWrite_EventWriteTransfer(v3, RestoreIncomplete, v2, 2, v10);
    }
    hKey = 0;
    if ( RegCreateKeyExW(
           HKEY_CURRENT_USER,
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\FileHistory\\RestoreUI",
           0,
           0,
           0,
           0x2001Fu,
           0,
           &hKey,
           0) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          v4,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\FileHistory\\RestoreUI");
    }
    else if ( RegDeleteValueW(hKey, L"RehydrationFilesFailed")
           && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        v5,
        (unsigned int)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\FileHistory\\RestoreUI",
        (__int64)L"RehydrationFilesFailed");
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_SSd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      25,
      (_DWORD)WPP_GLOBAL_Control,
      (unsigned int)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\FileHistory\\RestoreUI",
      (__int64)L"RehydrationFilesFailed",
      v3);
  }
}

```

## disassembly

```asm
0x1800075c4  push    rbp
0x1800075c6  push    rbx
0x1800075c7  push    rsi
0x1800075c8  push    r14
0x1800075ca  push    r15
0x1800075cc  lea     rbp, [rsp-37h]
0x1800075d1  sub     rsp, 90h
0x1800075d8  mov     rax, cs:__security_cookie
0x1800075df  xor     rax, rsp
0x1800075e2  mov     [rbp+57h+var_28], rax
0x1800075e6  lea     rax, [rbp+57h+var_58]
0x1800075ea  mov     [rbp+57h+var_58], 4
0x1800075f1  mov     [rsp+0B0h+pcbData], rax; pcbData
0x1800075f6  lea     r15, aRehydrationfil; "RehydrationFilesFailed"
0x1800075fd  lea     rax, [rbp+57h+var_60]
0x180007601  xor     ebx, ebx
0x180007603  mov     [rsp+0B0h+pvData], rax; pvData
0x180007608  lea     r14, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000760f  lea     rax, [rbp+57h+var_5C]
0x180007613  mov     [rbp+57h+var_5C], ebx
0x180007616  mov     r9d, 10000012h; dwFlags
0x18000761c  mov     [rsp+0B0h+pdwType], rax; pdwType
0x180007621  mov     r8, r15; lpValue
0x180007624  mov     rdx, r14; lpSubKey
0x180007627  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18000762e  call    cs:__imp_RegGetValueW
0x180007634  lea     esi, [rbx+1]
0x180007637  mov     ecx, eax
0x180007639  test    eax, eax
0x18000763b  jnz     short loc_180007678
0x18000763d  cmp     [rbp+57h+var_5C], 4
0x180007641  lea     ecx, [rbx+0Dh]
0x180007644  jnz     short loc_180007655
0x180007646  cmp     [rbp+57h+var_60], esi
0x180007649  ja      short loc_18000768A
0x18000764b  xor     ecx, ecx
0x18000764d  cmp     [rbp+57h+var_60], esi
0x180007650  setz    bl
0x180007653  jmp     short loc_180007693
0x180007655  cmp     [rbp+57h+var_58], 4
0x180007659  jnz     short loc_18000768A
0x18000765b  movzx   eax, word ptr [rbp+57h+var_60]
0x18000765f  sub     ax, 30h ; '0'
0x180007663  cmp     ax, si
0x180007666  ja      short loc_18000768A
0x180007668  mov     eax, 31h ; '1'
0x18000766d  cmp     ax, word ptr [rbp+57h+var_60]
0x180007671  setz    bl
0x180007674  xor     ecx, ecx
0x180007676  jmp     short loc_180007693
0x180007678  cmp     eax, 0EAh
0x18000767d  jnz     short loc_180007686
0x18000767f  mov     ecx, 0Dh
0x180007684  jmp     short loc_18000768A
0x180007686  test    eax, eax
0x180007688  jle     short loc_180007693
0x18000768a  movzx   ecx, cx
0x18000768d  or      ecx, 80070000h
0x180007693  test    ecx, ecx
0x180007695  jns     short loc_1800076D7
0x180007697  mov     r8, cs:WPP_GLOBAL_Control
0x18000769e  lea     rax, WPP_GLOBAL_Control
0x1800076a5  cmp     r8, rax
0x1800076a8  jz      loc_1800077CB
0x1800076ae  test    [r8+1Ch], sil
0x1800076b2  jz      loc_1800077CB
0x1800076b8  mov     dword ptr [rsp+0B0h+pvData], ecx
0x1800076bc  mov     edx, 19h
0x1800076c1  mov     rcx, [r8+10h]
0x1800076c5  mov     r9, r14
0x1800076c8  mov     [rsp+0B0h+pdwType], r15
0x1800076cd  call    WPP_SF_SSd
0x1800076d2  jmp     loc_1800077CB
0x1800076d7  test    ebx, ebx
0x1800076d9  jz      short loc_180007712
0x1800076db  test    cs:Microsoft_Windows_FileHistory_CoreEnableBits, 8
0x1800076e2  jz      short loc_180007712
0x1800076e4  lea     rax, aFilehistoryExe; "FileHistory.exe"
0x1800076eb  mov     [rbp+57h+var_30], 20h ; ' '
0x1800076f3  mov     [rbp+57h+var_38], rax
0x1800076f7  lea     rdx, RestoreIncomplete
0x1800076fe  lea     rax, [rbp+57h+var_48]
0x180007702  mov     r9d, 2
0x180007708  mov     [rsp+0B0h+pdwType], rax
0x18000770d  call    McGenEventWrite_EventWriteTransfer
0x180007712  mov     [rsp+0B0h+lpdwDisposition], 0; lpdwDisposition
0x18000771b  lea     rax, [rbp+57h+hKey]
0x18000771f  mov     [rsp+0B0h+phkResult], rax; phkResult
0x180007724  xor     r9d, r9d; lpClass
0x180007727  mov     [rsp+0B0h+pcbData], 0; lpSecurityAttributes
0x180007730  xor     r8d, r8d; Reserved
0x180007733  mov     dword ptr [rsp+0B0h+pvData], 2001Fh; samDesired
0x18000773b  mov     rdx, r14; lpSubKey
0x18000773e  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180007745  mov     dword ptr [rsp+0B0h+pdwType], 0; dwOptions
0x18000774d  mov     [rbp+57h+hKey], 0
0x180007755  call    cs:__imp_RegCreateKeyExW
0x18000775b  test    eax, eax
0x18000775d  jz      short loc_18000778B
0x18000775f  mov     rcx, cs:WPP_GLOBAL_Control
0x180007766  lea     rax, WPP_GLOBAL_Control
0x18000776d  cmp     rcx, rax
0x180007770  jz      short loc_1800077CB
0x180007772  test    [rcx+1Ch], sil
0x180007776  jz      short loc_1800077CB
0x180007778  mov     rcx, [rcx+10h]
0x18000777c  mov     edx, 1Ah
0x180007781  mov     r9, r14
0x180007784  call    WPP_SF_S
0x180007789  jmp     short loc_1800077CB
0x18000778b  mov     rcx, [rbp+57h+hKey]; hKey
0x18000778f  mov     rdx, r15; lpValueName
0x180007792  call    cs:__imp_RegDeleteValueW
0x180007798  test    eax, eax
0x18000779a  jz      short loc_1800077CB
0x18000779c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800077a3  lea     rax, WPP_GLOBAL_Control
0x1800077aa  cmp     rcx, rax
0x1800077ad  jz      short loc_1800077CB
0x1800077af  test    [rcx+1Ch], sil
0x1800077b3  jz      short loc_1800077CB
0x1800077b5  mov     rcx, [rcx+10h]
0x1800077b9  mov     edx, 1Bh
0x1800077be  mov     r9, r14
0x1800077c1  mov     [rsp+0B0h+pdwType], r15
0x1800077c6  call    WPP_SF_SS
0x1800077cb  mov     rcx, [rbp+57h+var_28]
0x1800077cf  xor     rcx, rsp; StackCookie
0x1800077d2  call    __security_check_cookie
0x1800077d7  add     rsp, 90h
0x1800077de  pop     r15
0x1800077e0  pop     r14
0x1800077e2  pop     rsi
0x1800077e3  pop     rbx
0x1800077e4  pop     rbp
0x1800077e5  retn
```
