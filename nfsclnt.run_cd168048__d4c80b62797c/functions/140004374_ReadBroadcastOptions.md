# ReadBroadcastOptions

- ea: `0x140004374`
- end: `0x14000485f`
- name: `ReadBroadcastOptions`
- size: `1259`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1400030c0`
- `0x140003a48`

## callees

- `0x140002bd8`
- `0x140002c00`
- `0x140004374`
- `0x140004cd8`
- `0x140004d58`
- `0x14001830e`
- `0x140018350`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x140004465`
- `ADVAPI32!RegQueryValueExW` at `0x140004538`
- `ADVAPI32!RegQueryValueExW` at `0x1400045a0`
- `ADVAPI32!RegQueryValueExW` at `0x140004603`
- `ADVAPI32!RegQueryValueExW` at `0x14000466c`
- `ADVAPI32!RegQueryValueExW` at `0x1400046d5`
- `ADVAPI32!RegQueryValueExW` at `0x14000473b`
- `ADVAPI32!RegQueryValueExW` at `0x140004465`
- `ADVAPI32!RegQueryValueExW` at `0x140004538`
- `ADVAPI32!RegQueryValueExW` at `0x1400045a0`
- `ADVAPI32!RegQueryValueExW` at `0x140004603`
- `ADVAPI32!RegQueryValueExW` at `0x14000466c`
- `ADVAPI32!RegQueryValueExW` at `0x1400046d5`
- `ADVAPI32!RegQueryValueExW` at `0x14000473b`
- `KERNEL32!GlobalAlloc` at `0x1400043f3`
- `KERNEL32!GlobalAlloc` at `0x1400043f3`
- `KERNEL32!GlobalFree` at `0x1400047d3`
- `KERNEL32!GlobalFree` at `0x1400047d3`
- `KERNEL32!GetLastError` at `0x14000446f`
- `KERNEL32!GetLastError` at `0x140004542`
- `KERNEL32!GetLastError` at `0x14000460d`
- `KERNEL32!GetLastError` at `0x140004676`
- `KERNEL32!GetLastError` at `0x1400046df`
- `KERNEL32!GetLastError` at `0x140004745`
- `KERNEL32!GetLastError` at `0x14000479d`
- `KERNEL32!GetLastError` at `0x14000446f`
- `KERNEL32!GetLastError` at `0x140004542`
- `KERNEL32!GetLastError` at `0x14000460d`
- `KERNEL32!GetLastError` at `0x140004676`
- `KERNEL32!GetLastError` at `0x1400046df`
- `KERNEL32!GetLastError` at `0x140004745`
- `KERNEL32!GetLastError` at `0x14000479d`
- `KERNEL32!CreateEventW` at `0x140004788`
- `KERNEL32!CreateEventW` at `0x140004788`
- `WS2_32!InetPtonW` at `0x1400044c6`
- `WS2_32!InetPtonW` at `0x1400044c6`

## string_xrefs

- `0x140004582`: `SPUpdateMinutes`

## pseudocode

```c
__int64 __fastcall ReadBroadcastOptions(__int64 a1, HKEY a2)
{
  int v4; // edx
  int v5; // r8d
  HGLOBAL v6; // rax
  unsigned int v7; // ebx
  _QWORD *v8; // rcx
  DWORD LastError; // eax
  int v10; // r8d
  _QWORD *v11; // rcx
  int v12; // edx
  const WCHAR *v13; // r9
  __int64 v14; // rax
  __int64 v15; // r9
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  BYTE *v18; // rax
  LSTATUS Value; // eax
  __int64 v20; // rcx
  int v21; // eax
  BYTE *v22; // rax
  BYTE *v23; // rax
  BYTE *v24; // rax
  __int64 v25; // rbx
  DWORD v26; // eax
  BYTE *lpData; // [rsp+20h] [rbp-E0h]
  DWORD cbData[4]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v30[4]; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD pAddrBuf[31]; // [rsp+44h] [rbp-BCh] BYREF
  WCHAR Data[264]; // [rsp+C0h] [rbp-40h] BYREF

  cbData[0] = 0;
  memset_0(Data, 0, 0x20Au);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_Sq(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, v5, *(_QWORD *)(a1 + 8), (char)a2);
  v6 = GlobalAlloc(0x40u, 0x28u);
  *(_QWORD *)(a1 + 24) = v6;
  if ( !v6 )
  {
    v7 = 8;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v7;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    {
LABEL_49:
      if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 2) != 0 )
        WPP_SF_d(v8[2], 21, &WPP_90b53e51910230494b81f4a05de1546d_Traceguids, v7);
      return v7;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_90b53e51910230494b81f4a05de1546d_Traceguids, 8);
LABEL_48:
    v8 = WPP_GLOBAL_Control;
    goto LABEL_49;
  }
  cbData[0] = 261;
  if ( RegQueryValueExW(a2, L"SPBroadcastAddr", 0, 0, (LPBYTE)Data, cbData) )
  {
    LastError = GetLastError();
    v7 = LastError;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_47;
    v12 = 12;
    v13 = L"SPBroadcastAddr";
    goto LABEL_41;
  }
  --cbData[0];
  memset_0(v30, 0, 0x80u);
  InetPtonW(2, Data, pAddrBuf);
  **(_DWORD **)(a1 + 24) = pAddrBuf[0];
  v14 = *(_QWORD *)(a1 + 24);
  if ( !*(_DWORD *)v14 )
  {
    v15 = 87;
    v7 = 87;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_47;
    v17 = 13;
    goto LABEL_46;
  }
  cbData[0] = 4;
  if ( RegQueryValueExW(a2, L"SPBroadcastRetry", 0, 0, (LPBYTE)(v14 + 4), cbData) )
  {
    LastError = GetLastError();
    v7 = LastError;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_47;
    v12 = 14;
    v13 = L"SPBroadcastRetry";
    goto LABEL_41;
  }
  v18 = (BYTE *)(*(_QWORD *)(a1 + 24) + 12LL);
  cbData[0] = 4;
  Value = RegQueryValueExW(a2, L"SPUpdateMinutes", 0, 0, v18, cbData);
  v20 = *(_QWORD *)(a1 + 24);
  if ( Value )
  {
    v21 = *(_DWORD *)&UpdateCycle;
  }
  else
  {
    if ( (unsigned int)(*(_DWORD *)(v20 + 12) - 1) > 0x275F )
      *(_DWORD *)(v20 + 12) = 10080;
    v20 = *(_QWORD *)(a1 + 24);
    v21 = 60000 * *(_DWORD *)(v20 + 12);
  }
  *(_DWORD *)(v20 + 12) = v21;
  lpData = (BYTE *)(*(_QWORD *)(a1 + 24) + 8LL);
  cbData[0] = 4;
  if ( RegQueryValueExW(a2, L"SPTimeoutSeconds", 0, 0, lpData, cbData) )
  {
    LastError = GetLastError();
    v7 = LastError;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_47;
    v12 = 15;
    v13 = L"SPTimeoutSeconds";
    goto LABEL_41;
  }
  v22 = (BYTE *)(*(_QWORD *)(a1 + 24) + 16LL);
  cbData[0] = 4;
  if ( RegQueryValueExW(a2, L"SPMaxNodes", 0, 0, v22, cbData) )
  {
    LastError = GetLastError();
    v7 = LastError;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_47;
    v12 = 16;
    v13 = L"SPMaxNodes";
    goto LABEL_41;
  }
  v23 = (BYTE *)(*(_QWORD *)(a1 + 24) + 20LL);
  cbData[0] = 4;
  if ( RegQueryValueExW(a2, L"SPBrowseMethod", 0, 0, v23, cbData) )
  {
    LastError = GetLastError();
    v7 = LastError;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_47;
    v12 = 17;
    v13 = L"SPBrowseMethod";
    goto LABEL_41;
  }
  v24 = (BYTE *)(*(_QWORD *)(a1 + 24) + 24LL);
  cbData[0] = 4;
  if ( RegQueryValueExW(a2, L"SPGetHostByAddr", 0, 0, v24, cbData) )
  {
    LastError = GetLastError();
    v7 = LastError;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_47;
    v12 = 18;
    v13 = L"SPGetHostByAddr";
LABEL_41:
    WPP_SF_Sd(v11[2], v12, v10, (_DWORD)v13, LastError);
LABEL_47:
    GlobalFree(*(HGLOBAL *)(a1 + 24));
    *(_QWORD *)(a1 + 24) = 0;
    goto LABEL_48;
  }
  v25 = *(_QWORD *)(a1 + 24);
  *(_QWORD *)(v25 + 32) = CreateEventW(0, 0, 0, 0);
  if ( !*(_QWORD *)(*(_QWORD *)(a1 + 24) + 32LL) )
  {
    v26 = GetLastError();
    v7 = v26;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_47;
    v17 = 19;
    v15 = v26;
LABEL_46:
    WPP_SF_d(v16[2], v17, &WPP_90b53e51910230494b81f4a05de1546d_Traceguids, v15);
    goto LABEL_47;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_90b53e51910230494b81f4a05de1546d_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x140004374  mov     [rsp-8+arg_10], rbx
0x140004379  push    rbp
0x14000437a  push    rsi
0x14000437b  push    r13
0x14000437d  push    r14
0x14000437f  push    r15
0x140004381  lea     rbp, [rsp-1E0h]
0x140004389  sub     rsp, 2E0h
0x140004390  mov     rax, cs:__security_cookie
0x140004397  xor     rax, rsp
0x14000439a  mov     [rbp+200h+var_30], rax
0x1400043a1  mov     r14, rdx
0x1400043a4  mov     [rsp+300h+cbData], 0
0x1400043ac  mov     rsi, rcx
0x1400043af  xor     edx, edx; Val
0x1400043b1  lea     rcx, [rbp+200h+Data]; void *
0x1400043b5  mov     r8d, 20Ah; Size
0x1400043bb  call    memset_0
0x1400043c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400043c7  lea     r15, WPP_GLOBAL_Control
0x1400043ce  cmp     rcx, r15
0x1400043d1  jz      short loc_1400043EB
0x1400043d3  test    byte ptr [rcx+1Ch], 1
0x1400043d7  jz      short loc_1400043EB
0x1400043d9  mov     r9, [rsi+8]
0x1400043dd  mov     rcx, [rcx+10h]
0x1400043e1  mov     [rsp+300h+lpData], r14
0x1400043e6  call    WPP_SF_Sq
0x1400043eb  mov     edx, 28h ; '('; dwBytes
0x1400043f0  lea     ecx, [rdx+18h]; uFlags
0x1400043f3  call    cs:__imp_GlobalAlloc
0x1400043f9  mov     [rsi+18h], rax
0x1400043fd  test    rax, rax
0x140004400  jnz     short loc_14000443A
0x140004402  lea     ebx, [rax+8]
0x140004405  mov     rcx, cs:WPP_GLOBAL_Control
0x14000440c  cmp     rcx, r15
0x14000440f  jz      loc_14000480B
0x140004415  test    byte ptr [rcx+1Ch], 2
0x140004419  jz      loc_1400047E8
0x14000441f  mov     rcx, [rcx+10h]
0x140004423  lea     edx, [rax+0Bh]
0x140004426  mov     r9d, ebx
0x140004429  lea     r8, WPP_90b53e51910230494b81f4a05de1546d_Traceguids
0x140004430  call    WPP_SF_d
0x140004435  jmp     loc_1400047E1
0x14000443a  lea     rax, [rsp+300h+cbData]
0x14000443f  mov     [rsp+300h+cbData], 105h
0x140004447  mov     [rsp+300h+lpcbData], rax; lpcbData
0x14000444c  lea     rdx, aSpbroadcastadd; "SPBroadcastAddr"
0x140004453  lea     rax, [rbp+200h+Data]
0x140004457  xor     r9d, r9d; lpType
0x14000445a  xor     r8d, r8d; lpReserved
0x14000445d  mov     [rsp+300h+lpData], rax; lpData
0x140004462  mov     rcx, r14; hKey
0x140004465  call    cs:__imp_RegQueryValueExW
0x14000446b  test    eax, eax
0x14000446d  jz      short loc_1400044A2
0x14000446f  call    cs:__imp_GetLastError
0x140004475  mov     ebx, eax
0x140004477  mov     rcx, cs:WPP_GLOBAL_Control
0x14000447e  cmp     rcx, r15
0x140004481  jz      loc_1400047CF
0x140004487  test    byte ptr [rcx+1Ch], 2
0x14000448b  jz      loc_1400047CF
0x140004491  mov     edx, 0Ch
0x140004496  lea     r9, aSpbroadcastadd; "SPBroadcastAddr"
0x14000449d  jmp     loc_14000476B
0x1400044a2  dec     [rsp+300h+cbData]
0x1400044a6  lea     rcx, [rsp+300h+var_2C0]; void *
0x1400044ab  xor     edx, edx; Val
0x1400044ad  mov     r8d, 80h; Size
0x1400044b3  call    memset_0
0x1400044b8  lea     r8, [rsp+300h+pAddrBuf]; pAddrBuf
0x1400044bd  mov     ecx, 2; Family
0x1400044c2  lea     rdx, [rbp+200h+Data]; pszAddrString
0x1400044c6  call    cs:__imp_InetPtonW
0x1400044cc  mov     eax, [rsp+300h+pAddrBuf]
0x1400044d0  mov     rcx, [rsi+18h]
0x1400044d4  mov     [rcx], eax
0x1400044d6  mov     rax, [rsi+18h]
0x1400044da  cmp     dword ptr [rax], 0
0x1400044dd  jnz     short loc_14000450B
0x1400044df  mov     r9d, 57h ; 'W'
0x1400044e5  mov     ebx, r9d
0x1400044e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400044ef  cmp     rcx, r15
0x1400044f2  jz      loc_1400047CF
0x1400044f8  test    byte ptr [rcx+1Ch], 2
0x1400044fc  jz      loc_1400047CF
0x140004502  lea     edx, [r9-4Ah]
0x140004506  jmp     loc_1400047BF
0x14000450b  mov     r13d, 4
0x140004511  lea     rcx, [rsp+300h+cbData]
0x140004516  mov     [rsp+300h+lpcbData], rcx; lpcbData
0x14000451b  lea     rdx, aSpbroadcastret; "SPBroadcastRetry"
0x140004522  add     rax, r13
0x140004525  mov     [rsp+300h+cbData], r13d
0x14000452a  mov     rcx, r14; hKey
0x14000452d  mov     [rsp+300h+lpData], rax; lpData
0x140004532  xor     r9d, r9d; lpType
0x140004535  xor     r8d, r8d; lpReserved
0x140004538  call    cs:__imp_RegQueryValueExW
0x14000453e  test    eax, eax
0x140004540  jz      short loc_140004574
0x140004542  call    cs:__imp_GetLastError
0x140004548  mov     ebx, eax
0x14000454a  mov     rcx, cs:WPP_GLOBAL_Control
0x140004551  cmp     rcx, r15
0x140004554  jz      loc_1400047CF
0x14000455a  test    byte ptr [rcx+1Ch], 2
0x14000455e  jz      loc_1400047CF
0x140004564  lea     edx, [r13+0Ah]
0x140004568  lea     r9, aSpbroadcastret; "SPBroadcastRetry"
0x14000456f  jmp     loc_14000476B
0x140004574  mov     rax, [rsi+18h]
0x140004578  lea     rcx, [rsp+300h+cbData]
0x14000457d  mov     [rsp+300h+lpcbData], rcx; lpcbData
0x140004582  lea     rdx, aSpupdateminute; "SPUpdateMinutes"
0x140004589  add     rax, 0Ch
0x14000458d  mov     [rsp+300h+cbData], r13d
0x140004592  mov     rcx, r14; hKey
0x140004595  mov     [rsp+300h+lpData], rax; lpData
0x14000459a  xor     r9d, r9d; lpType
0x14000459d  xor     r8d, r8d; lpReserved
0x1400045a0  call    cs:__imp_RegQueryValueExW
0x1400045a6  mov     rcx, [rsi+18h]
0x1400045aa  test    eax, eax
0x1400045ac  jz      short loc_1400045B6
0x1400045ae  mov     eax, cs:UpdateCycle
0x1400045b4  jmp     short loc_1400045D4
0x1400045b6  mov     eax, [rcx+0Ch]
0x1400045b9  dec     eax
0x1400045bb  cmp     eax, 275Fh
0x1400045c0  jbe     short loc_1400045C9
0x1400045c2  mov     dword ptr [rcx+0Ch], 2760h
0x1400045c9  mov     rcx, [rsi+18h]
0x1400045cd  imul    eax, [rcx+0Ch], 0EA60h
0x1400045d4  mov     [rcx+0Ch], eax
0x1400045d7  lea     rdx, aSptimeoutsecon; "SPTimeoutSeconds"
0x1400045de  mov     rax, [rsi+18h]
0x1400045e2  lea     rcx, [rsp+300h+cbData]
0x1400045e7  mov     [rsp+300h+lpcbData], rcx; lpcbData
0x1400045ec  add     rax, 8
0x1400045f0  mov     rcx, r14; hKey
0x1400045f3  mov     [rsp+300h+lpData], rax; lpData
0x1400045f8  xor     r9d, r9d; lpType
0x1400045fb  mov     [rsp+300h+cbData], r13d
0x140004600  xor     r8d, r8d; lpReserved
0x140004603  call    cs:__imp_RegQueryValueExW
0x140004609  test    eax, eax
0x14000460b  jz      short loc_140004640
0x14000460d  call    cs:__imp_GetLastError
0x140004613  mov     ebx, eax
0x140004615  mov     rcx, cs:WPP_GLOBAL_Control
0x14000461c  cmp     rcx, r15
0x14000461f  jz      loc_1400047CF
0x140004625  test    byte ptr [rcx+1Ch], 2
0x140004629  jz      loc_1400047CF
0x14000462f  mov     edx, 0Fh
0x140004634  lea     r9, aSptimeoutsecon; "SPTimeoutSeconds"
0x14000463b  jmp     loc_14000476B
0x140004640  mov     rax, [rsi+18h]
0x140004644  lea     rcx, [rsp+300h+cbData]
0x140004649  mov     [rsp+300h+lpcbData], rcx; lpcbData
0x14000464e  lea     rdx, aSpmaxnodes; "SPMaxNodes"
0x140004655  add     rax, 10h
0x140004659  mov     [rsp+300h+cbData], r13d
0x14000465e  mov     rcx, r14; hKey
0x140004661  mov     [rsp+300h+lpData], rax; lpData
0x140004666  xor     r9d, r9d; lpType
0x140004669  xor     r8d, r8d; lpReserved
0x14000466c  call    cs:__imp_RegQueryValueExW
0x140004672  test    eax, eax
0x140004674  jz      short loc_1400046A9
0x140004676  call    cs:__imp_GetLastError
0x14000467c  mov     ebx, eax
0x14000467e  mov     rcx, cs:WPP_GLOBAL_Control
0x140004685  cmp     rcx, r15
0x140004688  jz      loc_1400047CF
0x14000468e  test    byte ptr [rcx+1Ch], 2
0x140004692  jz      loc_1400047CF
0x140004698  mov     edx, 10h
0x14000469d  lea     r9, aSpmaxnodes; "SPMaxNodes"
0x1400046a4  jmp     loc_14000476B
0x1400046a9  mov     rax, [rsi+18h]
0x1400046ad  lea     rcx, [rsp+300h+cbData]
0x1400046b2  mov     [rsp+300h+lpcbData], rcx; lpcbData
0x1400046b7  lea     rdx, aSpbrowsemethod; "SPBrowseMethod"
0x1400046be  add     rax, 14h
0x1400046c2  mov     [rsp+300h+cbData], r13d
0x1400046c7  mov     rcx, r14; hKey
0x1400046ca  mov     [rsp+300h+lpData], rax; lpData
0x1400046cf  xor     r9d, r9d; lpType
0x1400046d2  xor     r8d, r8d; lpReserved
0x1400046d5  call    cs:__imp_RegQueryValueExW
0x1400046db  test    eax, eax
0x1400046dd  jz      short loc_14000470F
0x1400046df  call    cs:__imp_GetLastError
0x1400046e5  mov     ebx, eax
0x1400046e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400046ee  cmp     rcx, r15
0x1400046f1  jz      loc_1400047CF
0x1400046f7  test    byte ptr [rcx+1Ch], 2
0x1400046fb  jz      loc_1400047CF
0x140004701  mov     edx, 11h
0x140004706  lea     r9, aSpbrowsemethod; "SPBrowseMethod"
0x14000470d  jmp     short loc_14000476B
0x14000470f  mov     rax, [rsi+18h]
0x140004713  lea     rcx, [rsp+300h+cbData]
0x140004718  mov     [rsp+300h+lpcbData], rcx; lpcbData
0x14000471d  lea     rdx, aSpgethostbyadd; "SPGetHostByAddr"
0x140004724  add     rax, 18h
0x140004728  mov     [rsp+300h+cbData], r13d
0x14000472d  mov     rcx, r14; hKey
0x140004730  mov     [rsp+300h+lpData], rax; lpData
0x140004735  xor     r9d, r9d; lpType
0x140004738  xor     r8d, r8d; lpReserved
0x14000473b  call    cs:__imp_RegQueryValueExW
0x140004741  test    eax, eax
0x140004743  jz      short loc_14000477A
0x140004745  call    cs:__imp_GetLastError
0x14000474b  mov     ebx, eax
0x14000474d  mov     rcx, cs:WPP_GLOBAL_Control
0x140004754  cmp     rcx, r15
0x140004757  jz      short loc_1400047CF
0x140004759  test    byte ptr [rcx+1Ch], 2
0x14000475d  jz      short loc_1400047CF
0x14000475f  mov     edx, 12h
0x140004764  lea     r9, aSpgethostbyadd; "SPGetHostByAddr"
0x14000476b  mov     rcx, [rcx+10h]
0x14000476f  mov     dword ptr [rsp+300h+lpData], eax
0x140004773  call    WPP_SF_Sd
0x140004778  jmp     short loc_1400047CF
0x14000477a  mov     rbx, [rsi+18h]
0x14000477e  xor     r9d, r9d; lpName
0x140004781  xor     r8d, r8d; bInitialState
0x140004784  xor     edx, edx; bManualReset
0x140004786  xor     ecx, ecx; lpEventAttributes
0x140004788  call    cs:__imp_CreateEventW
0x14000478e  mov     [rbx+20h], rax
0x140004792  mov     rax, [rsi+18h]
0x140004796  cmp     qword ptr [rax+20h], 0
0x14000479b  jnz     short loc_14000480F
0x14000479d  call    cs:__imp_GetLastError
0x1400047a3  mov     ebx, eax
0x1400047a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400047ac  cmp     rcx, r15
0x1400047af  jz      short loc_1400047CF
0x1400047b1  test    byte ptr [rcx+1Ch], 2
0x1400047b5  jz      short loc_1400047CF
0x1400047b7  mov     edx, 13h
0x1400047bc  mov     r9d, eax
0x1400047bf  mov     rcx, [rcx+10h]
0x1400047c3  lea     r8, WPP_90b53e51910230494b81f4a05de1546d_Traceguids
0x1400047ca  call    WPP_SF_d
0x1400047cf  mov     rcx, [rsi+18h]; hMem
0x1400047d3  call    cs:__imp_GlobalFree
0x1400047d9  mov     qword ptr [rsi+18h], 0
0x1400047e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400047e8  cmp     rcx, r15
0x1400047eb  jz      short loc_14000480B
0x1400047ed  test    byte ptr [rcx+1Ch], 2
0x1400047f1  jz      short loc_14000480B
0x1400047f3  mov     rcx, [rcx+10h]
0x1400047f7  lea     r8, WPP_90b53e51910230494b81f4a05de1546d_Traceguids
0x1400047fe  mov     edx, 15h
0x140004803  mov     r9d, ebx
0x140004806  call    WPP_SF_d
0x14000480b  mov     eax, ebx
0x14000480d  jmp     short loc_140004838
0x14000480f  mov     rcx, cs:WPP_GLOBAL_Control
0x140004816  cmp     rcx, r15
0x140004819  jz      short loc_140004836
0x14000481b  test    byte ptr [rcx+1Ch], 1
0x14000481f  jz      short loc_140004836
0x140004821  mov     rcx, [rcx+10h]
0x140004825  lea     r8, WPP_90b53e51910230494b81f4a05de1546d_Traceguids
0x14000482c  mov     edx, 14h
0x140004831  call    WPP_SF_
0x140004836  xor     eax, eax
0x140004838  mov     rcx, [rbp+200h+var_30]
0x14000483f  xor     rcx, rsp; StackCookie
0x140004842  call    __security_check_cookie
0x140004847  mov     rbx, [rsp+300h+arg_10]
0x14000484f  add     rsp, 2E0h
0x140004856  pop     r15
0x140004858  pop     r14
0x14000485a  pop     r13
0x14000485c  pop     rsi
0x14000485d  pop     rbp
0x14000485e  retn
```
