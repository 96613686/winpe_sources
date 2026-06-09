# ReadHostsList

- ea: `0x140004868`
- end: `0x140004bcd`
- name: `ReadHostsList`
- size: `869`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1400030c0`
- `0x140003a48`
- `0x140009180`

## callees

- `0x140002bd8`
- `0x140002c00`
- `0x140004868`
- `0x140004bd4`
- `0x140004c34`
- `0x140004dd8`
- `0x140004e24`
- `0x14001831a`
- `0x140018350`

## import_xrefs

- `ADVAPI32!RegEnumValueW` at `0x140004916`
- `ADVAPI32!RegEnumValueW` at `0x140004aab`
- `ADVAPI32!RegEnumValueW` at `0x140004916`
- `ADVAPI32!RegEnumValueW` at `0x140004aab`
- `KERNEL32!GlobalAlloc` at `0x1400049b2`
- `KERNEL32!GlobalAlloc` at `0x1400049b2`
- `KERNEL32!GlobalFree` at `0x140004b6a`
- `KERNEL32!GlobalFree` at `0x140004b6a`
- `msvcrt!wcscpy_s` at `0x1400049d4`
- `msvcrt!wcscpy_s` at `0x1400049d4`
- `WS2_32!InetPtonW` at `0x140004a18`
- `WS2_32!InetPtonW` at `0x140004a18`

## string_xrefs

- `0x140004926`: `Configure Mode`

## pseudocode

```c
__int64 __fastcall ReadHostsList(__int64 a1, HKEY a2)
{
  int v4; // r13d
  unsigned int v5; // eax
  unsigned int v6; // edi
  int v7; // edx
  int v8; // r8d
  _QWORD *v9; // rcx
  char *v10; // rax
  _QWORD *v11; // rsi
  __int64 v12; // r9
  __int64 v13; // rax
  _QWORD *v15; // rcx
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchValueName[3]; // [rsp+44h] [rbp-BCh] BYREF
  WCHAR ValueName[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Data[264]; // [rsp+260h] [rbp+160h] BYREF

  cchValueName[0] = 0;
  cbData = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_90b53e51910230494b81f4a05de1546d_Traceguids, a2);
  cchValueName[0] = 261;
  v4 = 0;
  cbData = 261;
  v5 = RegEnumValueW(a2, 0, ValueName, cchValueName, 0, 0, (LPBYTE)Data, &cbData);
  v6 = 8;
  while ( !v5 )
  {
    if ( wcscmp_0(ValueName, L"Configure Mode") )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, v8, (unsigned int)ValueName, (__int64)Data);
          v9 = WPP_GLOBAL_Control;
        }
        if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 8) != 0 )
          WPP_SF_dd(v9[2], 24, &WPP_90b53e51910230494b81f4a05de1546d_Traceguids, cchValueName[0], cbData);
      }
      v10 = (char *)GlobalAlloc(0x40u, 2LL * (cchValueName[0] + 1) + 32);
      v11 = v10;
      if ( !v10 )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_90b53e51910230494b81f4a05de1546d_Traceguids, 8);
            goto LABEL_39;
          }
LABEL_40:
          if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 2) != 0 )
            WPP_SF_d(v15[2], 31, &WPP_90b53e51910230494b81f4a05de1546d_Traceguids, v6);
        }
        return v6;
      }
      *(_QWORD *)v10 = v10 + 32;
      wcscpy_s((wchar_t *)v10 + 16, cchValueName[0], ValueName);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_90b53e51910230494b81f4a05de1546d_Traceguids, *v11);
      --cbData;
      InetPtonW(2, Data, v11 + 1);
      v12 = *((unsigned int *)v11 + 2);
      if ( !(_DWORD)v12 )
      {
        v6 = 87;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_90b53e51910230494b81f4a05de1546d_Traceguids, 87);
        GlobalFree(v11);
LABEL_39:
        v15 = WPP_GLOBAL_Control;
        goto LABEL_40;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_90b53e51910230494b81f4a05de1546d_Traceguids, v12);
      v13 = *(_QWORD *)(a1 + 32);
      if ( v13 )
      {
        *(_QWORD *)(v13 + 24) = v11;
        v11[2] = *(_QWORD *)(a1 + 32);
      }
      *(_QWORD *)(a1 + 32) = v11;
    }
    cchValueName[0] = 261;
    cbData = 261;
    v5 = RegEnumValueW(a2, ++v4, ValueName, cchValueName, 0, 0, (LPBYTE)Data, &cbData);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_90b53e51910230494b81f4a05de1546d_Traceguids, v5);
  *(_QWORD *)(a1 + 24) = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_90b53e51910230494b81f4a05de1546d_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x140004868  mov     [rsp-8+arg_10], rbx
0x14000486d  push    rbp
0x14000486e  push    rsi
0x14000486f  push    rdi
0x140004870  push    r12
0x140004872  push    r13
0x140004874  push    r14
0x140004876  push    r15
0x140004878  lea     rbp, [rsp-380h]
0x140004880  sub     rsp, 480h
0x140004887  mov     rax, cs:__security_cookie
0x14000488e  xor     rax, rsp
0x140004891  mov     [rbp+3B0h+var_40], rax
0x140004898  xor     ebx, ebx
0x14000489a  mov     r15, rdx
0x14000489d  mov     [rsp+4B0h+cchValueName], ebx
0x1400048a1  mov     r14, rcx
0x1400048a4  mov     [rsp+4B0h+cbData], ebx
0x1400048a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400048af  lea     r12, WPP_GLOBAL_Control
0x1400048b6  cmp     rcx, r12
0x1400048b9  jz      short loc_1400048D7
0x1400048bb  test    byte ptr [rcx+1Ch], 1
0x1400048bf  jz      short loc_1400048D7
0x1400048c1  mov     rcx, [rcx+10h]
0x1400048c5  lea     edx, [rbx+16h]
0x1400048c8  mov     r9, r15
0x1400048cb  lea     r8, WPP_90b53e51910230494b81f4a05de1546d_Traceguids
0x1400048d2  call    WPP_SF_q
0x1400048d7  lea     rax, [rsp+4B0h+cbData]
0x1400048dc  mov     esi, 105h
0x1400048e1  mov     [rsp+4B0h+lpcbData], rax; lpcbData
0x1400048e6  lea     r9, [rsp+4B0h+cchValueName]; lpcchValueName
0x1400048eb  lea     rax, [rbp+3B0h+Data]
0x1400048f2  mov     [rsp+4B0h+cchValueName], esi
0x1400048f6  mov     [rsp+4B0h+lpData], rax; lpData
0x1400048fb  lea     r8, [rsp+4B0h+ValueName]; lpValueName
0x140004900  mov     [rsp+4B0h+lpType], rbx; lpType
0x140004905  xor     edx, edx; dwIndex
0x140004907  mov     rcx, r15; hKey
0x14000490a  mov     [rsp+4B0h+lpReserved], rbx; lpReserved
0x14000490f  mov     r13d, ebx
0x140004912  mov     [rsp+4B0h+cbData], esi
0x140004916  call    cs:__imp_RegEnumValueW
0x14000491c  mov     edi, 8
0x140004921  jmp     loc_140004AB1
0x140004926  lea     rdx, aConfigureMode; "Configure Mode"
0x14000492d  lea     rcx, [rsp+4B0h+ValueName]; String1
0x140004932  call    wcscmp_0
0x140004937  test    eax, eax
0x140004939  jz      loc_140004A70
0x14000493f  mov     rcx, cs:WPP_GLOBAL_Control
0x140004946  cmp     rcx, r12
0x140004949  jz      short loc_14000499F
0x14000494b  test    [rcx+1Ch], dil
0x14000494f  jz      short loc_140004972
0x140004951  mov     rcx, [rcx+10h]
0x140004955  lea     rax, [rbp+3B0h+Data]
0x14000495c  lea     r9, [rsp+4B0h+ValueName]
0x140004961  mov     [rsp+4B0h+lpReserved], rax
0x140004966  call    WPP_SF_SS
0x14000496b  mov     rcx, cs:WPP_GLOBAL_Control
0x140004972  cmp     rcx, r12
0x140004975  jz      short loc_14000499F
0x140004977  test    [rcx+1Ch], dil
0x14000497b  jz      short loc_14000499F
0x14000497d  mov     eax, [rsp+4B0h+cbData]
0x140004981  lea     r8, WPP_90b53e51910230494b81f4a05de1546d_Traceguids
0x140004988  mov     r9d, [rsp+4B0h+cchValueName]
0x14000498d  mov     edx, 18h
0x140004992  mov     rcx, [rcx+10h]
0x140004996  mov     dword ptr [rsp+4B0h+lpReserved], eax
0x14000499a  call    WPP_SF_dd
0x14000499f  mov     eax, [rsp+4B0h+cchValueName]
0x1400049a3  mov     ecx, 40h ; '@'; uFlags
0x1400049a8  inc     eax
0x1400049aa  lea     rdx, ds:20h[rax*2]; dwBytes
0x1400049b2  call    cs:__imp_GlobalAlloc
0x1400049b8  mov     rsi, rax
0x1400049bb  test    rax, rax
0x1400049be  jz      loc_140004B72
0x1400049c4  lea     rcx, [rax+20h]; Destination
0x1400049c8  mov     [rax], rcx
0x1400049cb  lea     r8, [rsp+4B0h+ValueName]; Source
0x1400049d0  mov     edx, [rsp+4B0h+cchValueName]; SizeInWords
0x1400049d4  call    cs:__imp_wcscpy_s
0x1400049da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400049e1  cmp     rcx, r12
0x1400049e4  jz      short loc_140004A04
0x1400049e6  test    [rcx+1Ch], dil
0x1400049ea  jz      short loc_140004A04
0x1400049ec  mov     r9, [rsi]
0x1400049ef  lea     r8, WPP_90b53e51910230494b81f4a05de1546d_Traceguids
0x1400049f6  mov     rcx, [rcx+10h]
0x1400049fa  mov     edx, 1Ah
0x1400049ff  call    WPP_SF_S
0x140004a04  dec     [rsp+4B0h+cbData]
0x140004a08  lea     r8, [rsi+8]; pAddrBuf
0x140004a0c  lea     rdx, [rbp+3B0h+Data]; pszAddrString
0x140004a13  mov     ecx, 2; Family
0x140004a18  call    cs:__imp_InetPtonW
0x140004a1e  mov     r9d, [rsi+8]
0x140004a22  xor     ebx, ebx
0x140004a24  test    r9d, r9d
0x140004a27  jz      loc_140004B3A
0x140004a2d  mov     rcx, cs:WPP_GLOBAL_Control
0x140004a34  cmp     rcx, r12
0x140004a37  jz      short loc_140004A52
0x140004a39  test    [rcx+1Ch], dil
0x140004a3d  jz      short loc_140004A52
0x140004a3f  mov     rcx, [rcx+10h]
0x140004a43  lea     edx, [rbx+1Ch]
0x140004a46  lea     r8, WPP_90b53e51910230494b81f4a05de1546d_Traceguids
0x140004a4d  call    WPP_SF_d
0x140004a52  mov     rax, [r14+20h]
0x140004a56  test    rax, rax
0x140004a59  jz      short loc_140004A67
0x140004a5b  mov     [rax+18h], rsi
0x140004a5f  mov     rax, [r14+20h]
0x140004a63  mov     [rsi+10h], rax
0x140004a67  mov     [r14+20h], rsi
0x140004a6b  mov     esi, 105h
0x140004a70  lea     rax, [rsp+4B0h+cbData]
0x140004a75  mov     [rsp+4B0h+cchValueName], esi
0x140004a79  mov     [rsp+4B0h+lpcbData], rax; lpcbData
0x140004a7e  lea     r9, [rsp+4B0h+cchValueName]; lpcchValueName
0x140004a83  lea     rax, [rbp+3B0h+Data]
0x140004a8a  mov     [rsp+4B0h+cbData], esi
0x140004a8e  mov     [rsp+4B0h+lpData], rax; lpData
0x140004a93  lea     r8, [rsp+4B0h+ValueName]; lpValueName
0x140004a98  inc     r13d
0x140004a9b  mov     [rsp+4B0h+lpType], rbx; lpType
0x140004aa0  mov     edx, r13d; dwIndex
0x140004aa3  mov     [rsp+4B0h+lpReserved], rbx; lpReserved
0x140004aa8  mov     rcx, r15; hKey
0x140004aab  call    cs:__imp_RegEnumValueW
0x140004ab1  test    eax, eax
0x140004ab3  jz      loc_140004926
0x140004ab9  mov     rcx, cs:WPP_GLOBAL_Control
0x140004ac0  cmp     rcx, r12
0x140004ac3  jz      short loc_140004AE3
0x140004ac5  test    [rcx+1Ch], dil
0x140004ac9  jz      short loc_140004AE3
0x140004acb  mov     rcx, [rcx+10h]
0x140004acf  lea     r8, WPP_90b53e51910230494b81f4a05de1546d_Traceguids
0x140004ad6  mov     edx, 1Dh
0x140004adb  mov     r9d, eax
0x140004ade  call    WPP_SF_d
0x140004ae3  mov     [r14+18h], rbx
0x140004ae7  mov     rcx, cs:WPP_GLOBAL_Control
0x140004aee  cmp     rcx, r12
0x140004af1  jz      short loc_140004B0E
0x140004af3  test    byte ptr [rcx+1Ch], 1
0x140004af7  jz      short loc_140004B0E
0x140004af9  mov     rcx, [rcx+10h]
0x140004afd  lea     r8, WPP_90b53e51910230494b81f4a05de1546d_Traceguids
0x140004b04  mov     edx, 1Eh
0x140004b09  call    WPP_SF_
0x140004b0e  xor     eax, eax
0x140004b10  mov     rcx, [rbp+3B0h+var_40]
0x140004b17  xor     rcx, rsp; StackCookie
0x140004b1a  call    __security_check_cookie
0x140004b1f  mov     rbx, [rsp+4B0h+arg_10]
0x140004b27  add     rsp, 480h
0x140004b2e  pop     r15
0x140004b30  pop     r14
0x140004b32  pop     r13
0x140004b34  pop     r12
0x140004b36  pop     rdi
0x140004b37  pop     rsi
0x140004b38  pop     rbp
0x140004b39  retn
0x140004b3a  mov     edi, 57h ; 'W'
0x140004b3f  mov     rcx, cs:WPP_GLOBAL_Control
0x140004b46  cmp     rcx, r12
0x140004b49  jz      short loc_140004B67
0x140004b4b  test    byte ptr [rcx+1Ch], 2
0x140004b4f  jz      short loc_140004B67
0x140004b51  mov     rcx, [rcx+10h]
0x140004b55  lea     edx, [rdi-3Ch]
0x140004b58  mov     r9d, edi
0x140004b5b  lea     r8, WPP_90b53e51910230494b81f4a05de1546d_Traceguids
0x140004b62  call    WPP_SF_d
0x140004b67  mov     rcx, rsi; hMem
0x140004b6a  call    cs:__imp_GlobalFree
0x140004b70  jmp     short loc_140004B9C
0x140004b72  mov     rcx, cs:WPP_GLOBAL_Control
0x140004b79  cmp     rcx, r12
0x140004b7c  jz      short loc_140004BC6
0x140004b7e  test    byte ptr [rcx+1Ch], 2
0x140004b82  jz      short loc_140004BA3
0x140004b84  mov     rcx, [rcx+10h]
0x140004b88  lea     r8, WPP_90b53e51910230494b81f4a05de1546d_Traceguids
0x140004b8f  mov     edx, 19h
0x140004b94  mov     r9d, edi
0x140004b97  call    WPP_SF_d
0x140004b9c  mov     rcx, cs:WPP_GLOBAL_Control
0x140004ba3  cmp     rcx, r12
0x140004ba6  jz      short loc_140004BC6
0x140004ba8  test    byte ptr [rcx+1Ch], 2
0x140004bac  jz      short loc_140004BC6
0x140004bae  mov     rcx, [rcx+10h]
0x140004bb2  lea     r8, WPP_90b53e51910230494b81f4a05de1546d_Traceguids
0x140004bb9  mov     edx, 1Fh
0x140004bbe  mov     r9d, edi
0x140004bc1  call    WPP_SF_d
0x140004bc6  mov     eax, edi
0x140004bc8  jmp     loc_140004B10
```
