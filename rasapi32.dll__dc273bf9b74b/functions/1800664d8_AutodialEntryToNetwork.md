# AutodialEntryToNetwork

- ea: `0x1800664d8`
- end: `0x1800668af`
- name: `AutodialEntryToNetwork`
- size: `983`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, char, BYTE **)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18006b430`
- `0x180077fd0`

## callees

- `0x18004e580`
- `0x18004e984`
- `0x1800664d8`
- `0x18006a710`
- `0x18007eed0`
- `0x18007efdc`
- `0x1800ded06`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180066732`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180066732`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800665fa`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800665fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006683d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006683d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180066655`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800667eb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180066655`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800667eb`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18006677f`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18006677f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180066856`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180066856`

## pseudocode

```c
__int64 __fastcall AutodialEntryToNetwork(HKEY hKey, LPCWSTR lpValueName, char a3, BYTE **a4)
{
  BYTE **v4; // r13
  _QWORD *v8; // rcx
  BYTE *v9; // rdi
  unsigned int v10; // eax
  unsigned int v11; // ebx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  unsigned int v14; // eax
  unsigned int v15; // eax
  __int64 v16; // rax
  BYTE *v17; // rax
  __int64 v18; // r9
  DWORD dwDisposition; // [rsp+50h] [rbp-20h] BYREF
  HKEY hKeya; // [rsp+58h] [rbp-18h] BYREF
  BYTE *lpData; // [rsp+60h] [rbp-10h]
  DWORD cbData; // [rsp+B8h] [rbp+48h] BYREF
  DWORD Type; // [rsp+C8h] [rbp+58h] BYREF

  v4 = a4;
  if ( lpValueName )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_15;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
      goto LABEL_11;
    WPP_SF_Sc(*((_QWORD *)WPP_GLOBAL_Control + 2), 639, a3, (_DWORD)lpValueName, a3 != 0);
    goto LABEL_10;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_15;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    LOBYTE(a4) = a3 != 0;
    WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 640, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, a4);
LABEL_10:
    v8 = WPP_GLOBAL_Control;
  }
LABEL_11:
  if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x800) != 0 && *((_BYTE *)v8 + 25) >= 6u )
    WPP_SF_(v8[2], 641, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids);
LABEL_15:
  hKeya = 0;
  Type = 0;
  v9 = 0;
  cbData = 0;
  dwDisposition = 0;
  lpData = 0;
  v10 = RegCreateKeyExW(hKey, L"Entries", 0, 0, 0, 3u, 0, &hKeya, &dwDisposition);
  v11 = v10;
  if ( v10 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 642;
LABEL_49:
      v18 = v10;
      goto LABEL_50;
    }
    goto LABEL_52;
  }
  v14 = RegQueryValueExW(hKeya, lpValueName, 0, &Type, 0, &cbData);
  v11 = v14;
  if ( !v14 )
  {
    v17 = (BYTE *)GlobalAlloc(0x40u, cbData + 2LL);
    v9 = v17;
    if ( !v17 )
    {
      v11 = 8;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = 646;
        v18 = 8;
LABEL_50:
        WPP_SF_d(v12[2], v13, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v18);
        goto LABEL_51;
      }
      goto LABEL_52;
    }
    memset_0(v17, 0, cbData + 2LL);
    v10 = RegQueryValueExW(hKeya, lpValueName, 0, &Type, v9, &cbData);
    v11 = v10;
    if ( v10 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = 647;
        goto LABEL_49;
      }
      goto LABEL_52;
    }
LABEL_51:
    v12 = WPP_GLOBAL_Control;
    goto LABEL_52;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 643, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v14);
    v12 = WPP_GLOBAL_Control;
  }
  if ( !a3 )
    goto LABEL_52;
  v15 = NewAutodialNetwork(hKey);
  v11 = v15;
  if ( v15 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      v9 = lpData;
      goto LABEL_52;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 644, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v15);
    v9 = lpData;
    goto LABEL_51;
  }
  v9 = lpData;
  v16 = -1;
  do
    ++v16;
  while ( *(_WORD *)&lpData[2 * v16] );
  v10 = RegSetValueExW(hKeya, lpValueName, 0, 1u, lpData, 2 * v16 + 2);
  v11 = v10;
  if ( !v10 )
    goto LABEL_51;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v13 = 645;
    goto LABEL_49;
  }
LABEL_52:
  if ( hKeya )
  {
    RegCloseKey(hKeya);
    v12 = WPP_GLOBAL_Control;
  }
  if ( v11 && v9 )
  {
    GlobalFree(v9);
    v12 = WPP_GLOBAL_Control;
    v9 = 0;
  }
  *v4 = v9;
  if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 7) & 0x800) != 0 && *((_BYTE *)v12 + 25) >= 6u )
    WPP_SF_d(v12[2], 648, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x1800664d8  mov     [rsp-38h+arg_0], rbx
0x1800664dd  push    rbp
0x1800664de  push    rsi
0x1800664df  push    rdi
0x1800664e0  push    r12
0x1800664e2  push    r13
0x1800664e4  push    r14
0x1800664e6  push    r15
0x1800664e8  mov     rbp, rsp
0x1800664eb  sub     rsp, 70h
0x1800664ef  xor     ebx, ebx
0x1800664f1  mov     r13, r9
0x1800664f4  mov     r14b, r8b
0x1800664f7  mov     r15, rdx
0x1800664fa  mov     r12, rcx
0x1800664fd  test    rdx, rdx
0x180066500  jz      short loc_180066545
0x180066502  mov     rcx, cs:WPP_GLOBAL_Control
0x180066509  lea     rsi, WPP_GLOBAL_Control
0x180066510  cmp     rcx, rsi
0x180066513  jz      loc_1800665B3
0x180066519  test    dword ptr [rcx+1Ch], 800h
0x180066520  jz      short loc_18006658A
0x180066522  cmp     byte ptr [rcx+19h], 6
0x180066526  jb      short loc_18006658A
0x180066528  mov     rcx, [rcx+10h]
0x18006652c  test    r8b, r8b
0x18006652f  mov     edx, 27Fh
0x180066534  mov     r9, r15
0x180066537  setnz   al
0x18006653a  mov     byte ptr [rsp+70h+dwOptions], al
0x18006653e  call    WPP_SF_Sc
0x180066543  jmp     short loc_180066583
0x180066545  mov     rcx, cs:WPP_GLOBAL_Control
0x18006654c  lea     rsi, WPP_GLOBAL_Control
0x180066553  cmp     rcx, rsi
0x180066556  jz      short loc_1800665B3
0x180066558  test    dword ptr [rcx+1Ch], 800h
0x18006655f  jz      short loc_18006658A
0x180066561  cmp     byte ptr [rcx+19h], 6
0x180066565  jb      short loc_18006658A
0x180066567  mov     rcx, [rcx+10h]
0x18006656b  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x180066572  test    r14b, r14b
0x180066575  mov     edx, 280h
0x18006657a  setnz   r9b
0x18006657e  call    WPP_SF_c
0x180066583  mov     rcx, cs:WPP_GLOBAL_Control
0x18006658a  cmp     rcx, rsi
0x18006658d  jz      short loc_1800665B3
0x18006658f  test    dword ptr [rcx+1Ch], 800h
0x180066596  jz      short loc_1800665B3
0x180066598  cmp     byte ptr [rcx+19h], 6
0x18006659c  jb      short loc_1800665B3
0x18006659e  mov     rcx, [rcx+10h]
0x1800665a2  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x1800665a9  mov     edx, 281h
0x1800665ae  call    WPP_SF_
0x1800665b3  lea     rax, [rbp+dwDisposition]
0x1800665b7  mov     [rbp+hKey], rbx
0x1800665bb  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x1800665c0  lea     rdx, aEntries; "Entries"
0x1800665c7  lea     rax, [rbp+hKey]
0x1800665cb  mov     [rbp+Type], ebx
0x1800665ce  mov     [rsp+70h+phkResult], rax; phkResult
0x1800665d3  xor     r9d, r9d; lpClass
0x1800665d6  mov     [rsp+70h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x1800665db  xor     r8d, r8d; Reserved
0x1800665de  mov     [rsp+70h+samDesired], 3; samDesired
0x1800665e6  mov     rcx, r12; hKey
0x1800665e9  mov     [rsp+70h+dwOptions], ebx; dwOptions
0x1800665ed  mov     rdi, rbx
0x1800665f0  mov     [rbp+cbData], ebx
0x1800665f3  mov     [rbp+dwDisposition], ebx
0x1800665f6  mov     [rbp+lpData], rbx
0x1800665fa  call    cs:__imp_RegCreateKeyExW
0x180066600  xor     ecx, ecx
0x180066602  mov     ebx, eax
0x180066604  test    eax, eax
0x180066606  jz      short loc_180066639
0x180066608  mov     rcx, cs:WPP_GLOBAL_Control
0x18006660f  cmp     rcx, rsi
0x180066612  jz      loc_180066831
0x180066618  test    dword ptr [rcx+1Ch], 800h
0x18006661f  jz      loc_180066831
0x180066625  cmp     byte ptr [rcx+19h], 2
0x180066629  jb      loc_180066831
0x18006662f  mov     edx, 282h
0x180066634  jmp     loc_180066817
0x180066639  lea     rax, [rbp+cbData]
0x18006663d  xor     r8d, r8d; lpReserved
0x180066640  mov     qword ptr [rsp+70h+samDesired], rax; lpcbData
0x180066645  lea     r9, [rbp+Type]; lpType
0x180066649  mov     qword ptr [rsp+70h+dwOptions], rcx; lpData
0x18006664e  mov     rdx, r15; lpValueName
0x180066651  mov     rcx, [rbp+hKey]; hKey
0x180066655  call    cs:__imp_RegQueryValueExW
0x18006665b  mov     ebx, eax
0x18006665d  test    eax, eax
0x18006665f  jz      loc_180066773
0x180066665  mov     rcx, cs:WPP_GLOBAL_Control
0x18006666c  cmp     rcx, rsi
0x18006666f  jz      short loc_18006669F
0x180066671  test    dword ptr [rcx+1Ch], 800h
0x180066678  jz      short loc_18006669F
0x18006667a  cmp     byte ptr [rcx+19h], 2
0x18006667e  jb      short loc_18006669F
0x180066680  mov     rcx, [rcx+10h]
0x180066684  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006668b  mov     edx, 283h
0x180066690  mov     r9d, eax
0x180066693  call    WPP_SF_d
0x180066698  mov     rcx, cs:WPP_GLOBAL_Control
0x18006669f  test    r14b, r14b
0x1800666a2  jz      loc_180066831
0x1800666a8  lea     rdx, [rbp+lpData]
0x1800666ac  mov     rcx, r12; hKey
0x1800666af  call    NewAutodialNetwork
0x1800666b4  xor     ecx, ecx
0x1800666b6  mov     ebx, eax
0x1800666b8  test    eax, eax
0x1800666ba  jz      short loc_180066701
0x1800666bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800666c3  cmp     rcx, rsi
0x1800666c6  jz      short loc_1800666F8
0x1800666c8  test    dword ptr [rcx+1Ch], 800h
0x1800666cf  jz      short loc_1800666F8
0x1800666d1  cmp     byte ptr [rcx+19h], 2
0x1800666d5  jb      short loc_1800666F8
0x1800666d7  mov     rcx, [rcx+10h]
0x1800666db  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x1800666e2  mov     edx, 284h
0x1800666e7  mov     r9d, eax
0x1800666ea  call    WPP_SF_d
0x1800666ef  mov     rdi, [rbp+lpData]
0x1800666f3  jmp     loc_18006682A
0x1800666f8  mov     rdi, [rbp+lpData]
0x1800666fc  jmp     loc_180066831
0x180066701  mov     rdi, [rbp+lpData]
0x180066705  or      rax, 0FFFFFFFFFFFFFFFFh
0x180066709  inc     rax
0x18006670c  cmp     [rdi+rax*2], cx
0x180066710  jnz     short loc_180066709
0x180066712  mov     rcx, [rbp+hKey]; hKey
0x180066716  lea     eax, ds:2[rax*2]
0x18006671d  mov     [rsp+70h+samDesired], eax; cbData
0x180066721  mov     r9d, 1; dwType
0x180066727  xor     r8d, r8d; Reserved
0x18006672a  mov     qword ptr [rsp+70h+dwOptions], rdi; lpData
0x18006672f  mov     rdx, r15; lpValueName
0x180066732  call    cs:__imp_RegSetValueExW
0x180066738  mov     ebx, eax
0x18006673a  test    eax, eax
0x18006673c  jz      loc_18006682A
0x180066742  mov     rcx, cs:WPP_GLOBAL_Control
0x180066749  cmp     rcx, rsi
0x18006674c  jz      loc_180066831
0x180066752  test    dword ptr [rcx+1Ch], 800h
0x180066759  jz      loc_180066831
0x18006675f  cmp     byte ptr [rcx+19h], 2
0x180066763  jb      loc_180066831
0x180066769  mov     edx, 285h
0x18006676e  jmp     loc_180066817
0x180066773  mov     edx, [rbp+cbData]
0x180066776  mov     ecx, 40h ; '@'; uFlags
0x18006677b  add     rdx, 2; dwBytes
0x18006677f  call    cs:__imp_GlobalAlloc
0x180066785  mov     rdi, rax
0x180066788  test    rax, rax
0x18006678b  jnz     short loc_1800667BD
0x18006678d  lea     ebx, [rax+8]
0x180066790  mov     rcx, cs:WPP_GLOBAL_Control
0x180066797  cmp     rcx, rsi
0x18006679a  jz      loc_180066831
0x1800667a0  test    dword ptr [rcx+1Ch], 800h
0x1800667a7  jz      loc_180066831
0x1800667ad  cmp     byte ptr [rcx+19h], 2
0x1800667b1  jb      short loc_180066831
0x1800667b3  mov     edx, 286h
0x1800667b8  mov     r9d, ebx
0x1800667bb  jmp     short loc_18006681A
0x1800667bd  mov     r8d, [rbp+cbData]
0x1800667c1  xor     edx, edx; Val
0x1800667c3  add     r8, 2; Size
0x1800667c7  mov     rcx, rdi; void *
0x1800667ca  call    memset_0
0x1800667cf  mov     rcx, [rbp+hKey]; hKey
0x1800667d3  lea     rax, [rbp+cbData]
0x1800667d7  mov     qword ptr [rsp+70h+samDesired], rax; lpcbData
0x1800667dc  lea     r9, [rbp+Type]; lpType
0x1800667e0  xor     r8d, r8d; lpReserved
0x1800667e3  mov     qword ptr [rsp+70h+dwOptions], rdi; lpData
0x1800667e8  mov     rdx, r15; lpValueName
0x1800667eb  call    cs:__imp_RegQueryValueExW
0x1800667f1  mov     ebx, eax
0x1800667f3  test    eax, eax
0x1800667f5  jz      short loc_18006682A
0x1800667f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800667fe  cmp     rcx, rsi
0x180066801  jz      short loc_180066831
0x180066803  test    dword ptr [rcx+1Ch], 800h
0x18006680a  jz      short loc_180066831
0x18006680c  cmp     byte ptr [rcx+19h], 2
0x180066810  jb      short loc_180066831
0x180066812  mov     edx, 287h
0x180066817  mov     r9d, eax
0x18006681a  mov     rcx, [rcx+10h]
0x18006681e  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x180066825  call    WPP_SF_d
0x18006682a  mov     rcx, cs:WPP_GLOBAL_Control
0x180066831  mov     rax, [rbp+hKey]
0x180066835  test    rax, rax
0x180066838  jz      short loc_18006684A
0x18006683a  mov     rcx, rax; hKey
0x18006683d  call    cs:__imp_RegCloseKey
0x180066843  mov     rcx, cs:WPP_GLOBAL_Control
0x18006684a  test    ebx, ebx
0x18006684c  jz      short loc_180066865
0x18006684e  test    rdi, rdi
0x180066851  jz      short loc_180066865
0x180066853  mov     rcx, rdi; hMem
0x180066856  call    cs:__imp_GlobalFree
0x18006685c  mov     rcx, cs:WPP_GLOBAL_Control
0x180066863  xor     edi, edi
0x180066865  mov     [r13+0], rdi
0x180066869  cmp     rcx, rsi
0x18006686c  jz      short loc_180066895
0x18006686e  test    dword ptr [rcx+1Ch], 800h
0x180066875  jz      short loc_180066895
0x180066877  cmp     byte ptr [rcx+19h], 6
0x18006687b  jb      short loc_180066895
0x18006687d  mov     rcx, [rcx+10h]
0x180066881  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x180066888  mov     edx, 288h
0x18006688d  mov     r9d, ebx
0x180066890  call    WPP_SF_d
0x180066895  mov     eax, ebx
0x180066897  mov     rbx, [rsp+70h+arg_0]
0x18006689f  add     rsp, 70h
0x1800668a3  pop     r15
0x1800668a5  pop     r14
0x1800668a7  pop     r13
0x1800668a9  pop     r12
0x1800668ab  pop     rdi
0x1800668ac  pop     rsi
0x1800668ad  pop     rbp
0x1800668ae  retn
```
