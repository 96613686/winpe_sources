# RasDefIntConnSet

- ea: `0x18006bf8c`
- end: `0x18006c25c`
- name: `RasDefIntConnSet`
- size: `720`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180077fd0`

## callees

- `0x18000efe4`
- `0x18000f0bc`
- `0x18004e580`
- `0x18006bf8c`
- `0x18007e5f0`
- `0x18007f084`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006c0e4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006c0e4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006c19d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006c19d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c128`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c1e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c128`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c1e1`

## pseudocode

```c
__int64 __fastcall RasDefIntConnSet(__int64 a1, __int64 a2, int a3, __int64 a4)
{
  int v4; // ebp
  __int64 v8; // rdi
  unsigned int DefIntConnName; // eax
  unsigned int v10; // ebx
  unsigned int v11; // eax
  _QWORD *v12; // rcx
  unsigned int v13; // eax
  unsigned int v14; // eax
  __int64 v15; // rax
  unsigned int v16; // eax
  bool lpData; // [rsp+20h] [rbp-58h]
  HKEY hKey; // [rsp+88h] [rbp+10h] BYREF

  v4 = a4;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    lpData = (_DWORD)a4 != 0;
    LOBYTE(a4) = a3 != 0;
    WPP_SF_cc(*((_QWORD *)WPP_GLOBAL_Control + 2), 694, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, a4, lpData);
  }
  v8 = a2 + 12;
  hKey = 0;
  DefIntConnName = RasGetDefIntConnName(0, a2 + 12, &hKey);
  v10 = DefIntConnName;
  if ( !DefIntConnName )
    goto LABEL_15;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 695, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, DefIntConnName);
  }
  v11 = RasGetDefIntConnName(1, v8, &hKey);
  v10 = v11;
  if ( !v11 )
    goto LABEL_15;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_20;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 696, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v11);
LABEL_15:
    v12 = WPP_GLOBAL_Control;
  }
  if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 7) & 0x800) != 0 && *((_BYTE *)v12 + 25) >= 5u )
  {
    WPP_SF_S(v12[2], 697, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v8);
    v12 = WPP_GLOBAL_Control;
  }
LABEL_20:
  if ( hKey )
  {
    v13 = RegDeleteValueW(hKey, L"DefaultInternet");
    v10 = v13;
    if ( v13
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 698, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v13);
    }
    RegCloseKey(hKey);
    v12 = WPP_GLOBAL_Control;
    hKey = 0;
  }
  if ( a3 )
    goto LABEL_42;
  v14 = RasDefIntConnOpenKey(0, v4, 0, &hKey);
  v10 = v14;
  if ( !v14 )
  {
    v15 = -1;
    do
      ++v15;
    while ( *(_WORD *)(a1 + 12 + 2 * v15) );
    v16 = RegSetValueExW(hKey, L"DefaultInternet", 0, 1u, (const BYTE *)(a1 + 12), 2 * v15 + 2);
    v10 = v16;
    if ( v16
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 699, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v16);
    }
    RegCloseKey(hKey);
    goto LABEL_41;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v10;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 700, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v14);
LABEL_41:
    v12 = WPP_GLOBAL_Control;
  }
LABEL_42:
  if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 7) & 0x800) != 0 && *((_BYTE *)v12 + 25) >= 6u )
    WPP_SF_d(v12[2], 701, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x18006bf8c  push    rbx
0x18006bf8e  push    rbp
0x18006bf8f  push    rsi
0x18006bf90  push    rdi
0x18006bf91  push    r12
0x18006bf93  push    r13
0x18006bf95  push    r14
0x18006bf97  push    r15
0x18006bf99  sub     rsp, 38h
0x18006bf9d  mov     ebp, r9d
0x18006bfa0  mov     esi, r8d
0x18006bfa3  mov     rbx, rdx
0x18006bfa6  mov     r14, rcx
0x18006bfa9  mov     rcx, cs:WPP_GLOBAL_Control
0x18006bfb0  lea     r13, WPP_GLOBAL_Control
0x18006bfb7  xor     r15d, r15d
0x18006bfba  mov     r12d, 800h
0x18006bfc0  cmp     rcx, r13
0x18006bfc3  jz      short loc_18006BFF7
0x18006bfc5  test    [rcx+1Ch], r12d
0x18006bfc9  jz      short loc_18006BFF7
0x18006bfcb  cmp     byte ptr [rcx+19h], 6
0x18006bfcf  jb      short loc_18006BFF7
0x18006bfd1  mov     rcx, [rcx+10h]
0x18006bfd5  test    r9d, r9d
0x18006bfd8  mov     edx, 2B6h
0x18006bfdd  setnz   al
0x18006bfe0  test    r8d, r8d
0x18006bfe3  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006bfea  mov     byte ptr [rsp+78h+lpData], al
0x18006bfee  setnz   r9b
0x18006bff2  call    WPP_SF_cc
0x18006bff7  lea     rdi, [rbx+0Ch]
0x18006bffb  mov     [rsp+78h+hKey], r15
0x18006c003  mov     rdx, rdi
0x18006c006  lea     r8, [rsp+78h+hKey]
0x18006c00e  xor     ecx, ecx
0x18006c010  call    RasGetDefIntConnName
0x18006c015  mov     ebx, eax
0x18006c017  test    eax, eax
0x18006c019  jz      short loc_18006C096
0x18006c01b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c022  cmp     rcx, r13
0x18006c025  jz      short loc_18006C04B
0x18006c027  test    [rcx+1Ch], r12d
0x18006c02b  jz      short loc_18006C04B
0x18006c02d  cmp     byte ptr [rcx+19h], 2
0x18006c031  jb      short loc_18006C04B
0x18006c033  mov     rcx, [rcx+10h]
0x18006c037  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006c03e  mov     edx, 2B7h
0x18006c043  mov     r9d, eax
0x18006c046  call    WPP_SF_d
0x18006c04b  lea     r8, [rsp+78h+hKey]
0x18006c053  mov     rdx, rdi
0x18006c056  mov     ecx, 1
0x18006c05b  call    RasGetDefIntConnName
0x18006c060  mov     ebx, eax
0x18006c062  test    eax, eax
0x18006c064  jz      short loc_18006C096
0x18006c066  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c06d  cmp     rcx, r13
0x18006c070  jz      short loc_18006C0CD
0x18006c072  test    [rcx+1Ch], r12d
0x18006c076  jz      short loc_18006C09D
0x18006c078  cmp     byte ptr [rcx+19h], 2
0x18006c07c  jb      short loc_18006C09D
0x18006c07e  mov     rcx, [rcx+10h]
0x18006c082  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006c089  mov     edx, 2B8h
0x18006c08e  mov     r9d, eax
0x18006c091  call    WPP_SF_d
0x18006c096  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c09d  cmp     rcx, r13
0x18006c0a0  jz      short loc_18006C0CD
0x18006c0a2  test    [rcx+1Ch], r12d
0x18006c0a6  jz      short loc_18006C0CD
0x18006c0a8  cmp     byte ptr [rcx+19h], 5
0x18006c0ac  jb      short loc_18006C0CD
0x18006c0ae  mov     rcx, [rcx+10h]
0x18006c0b2  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006c0b9  mov     edx, 2B9h
0x18006c0be  mov     r9, rdi
0x18006c0c1  call    WPP_SF_S
0x18006c0c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c0cd  mov     rax, [rsp+78h+hKey]
0x18006c0d5  test    rax, rax
0x18006c0d8  jz      short loc_18006C13D
0x18006c0da  lea     rdx, aDefaultinterne; "DefaultInternet"
0x18006c0e1  mov     rcx, rax; hKey
0x18006c0e4  call    cs:__imp_RegDeleteValueW
0x18006c0ea  mov     ebx, eax
0x18006c0ec  test    eax, eax
0x18006c0ee  jz      short loc_18006C120
0x18006c0f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c0f7  cmp     rcx, r13
0x18006c0fa  jz      short loc_18006C120
0x18006c0fc  test    [rcx+1Ch], r12d
0x18006c100  jz      short loc_18006C120
0x18006c102  cmp     byte ptr [rcx+19h], 2
0x18006c106  jb      short loc_18006C120
0x18006c108  mov     rcx, [rcx+10h]
0x18006c10c  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006c113  mov     edx, 2BAh
0x18006c118  mov     r9d, eax
0x18006c11b  call    WPP_SF_d
0x18006c120  mov     rcx, [rsp+78h+hKey]; hKey
0x18006c128  call    cs:__imp_RegCloseKey
0x18006c12e  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c135  mov     [rsp+78h+hKey], r15
0x18006c13d  test    esi, esi
0x18006c13f  jnz     loc_18006C220
0x18006c145  lea     r9, [rsp+78h+hKey]
0x18006c14d  xor     r8d, r8d
0x18006c150  mov     edx, ebp
0x18006c152  xor     ecx, ecx
0x18006c154  call    RasDefIntConnOpenKey
0x18006c159  mov     ebx, eax
0x18006c15b  test    eax, eax
0x18006c15d  jnz     loc_18006C1E9
0x18006c163  lea     rcx, [r14+0Ch]
0x18006c167  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006c16b  inc     rax
0x18006c16e  cmp     [rcx+rax*2], r15w
0x18006c173  jnz     short loc_18006C16B
0x18006c175  lea     eax, ds:2[rax*2]
0x18006c17c  mov     r9d, 1; dwType
0x18006c182  mov     [rsp+78h+cbData], eax; cbData
0x18006c186  lea     rdx, aDefaultinterne; "DefaultInternet"
0x18006c18d  mov     [rsp+78h+lpData], rcx; lpData
0x18006c192  xor     r8d, r8d; Reserved
0x18006c195  mov     rcx, [rsp+78h+hKey]; hKey
0x18006c19d  call    cs:__imp_RegSetValueExW
0x18006c1a3  mov     ebx, eax
0x18006c1a5  test    eax, eax
0x18006c1a7  jz      short loc_18006C1D9
0x18006c1a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c1b0  cmp     rcx, r13
0x18006c1b3  jz      short loc_18006C1D9
0x18006c1b5  test    [rcx+1Ch], r12d
0x18006c1b9  jz      short loc_18006C1D9
0x18006c1bb  cmp     byte ptr [rcx+19h], 2
0x18006c1bf  jb      short loc_18006C1D9
0x18006c1c1  mov     rcx, [rcx+10h]
0x18006c1c5  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006c1cc  mov     edx, 2BBh
0x18006c1d1  mov     r9d, eax
0x18006c1d4  call    WPP_SF_d
0x18006c1d9  mov     rcx, [rsp+78h+hKey]; hKey
0x18006c1e1  call    cs:__imp_RegCloseKey
0x18006c1e7  jmp     short loc_18006C219
0x18006c1e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c1f0  cmp     rcx, r13
0x18006c1f3  jz      short loc_18006C249
0x18006c1f5  test    [rcx+1Ch], r12d
0x18006c1f9  jz      short loc_18006C220
0x18006c1fb  cmp     byte ptr [rcx+19h], 2
0x18006c1ff  jb      short loc_18006C220
0x18006c201  mov     rcx, [rcx+10h]
0x18006c205  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006c20c  mov     edx, 2BCh
0x18006c211  mov     r9d, eax
0x18006c214  call    WPP_SF_d
0x18006c219  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c220  cmp     rcx, r13
0x18006c223  jz      short loc_18006C249
0x18006c225  test    [rcx+1Ch], r12d
0x18006c229  jz      short loc_18006C249
0x18006c22b  cmp     byte ptr [rcx+19h], 6
0x18006c22f  jb      short loc_18006C249
0x18006c231  mov     rcx, [rcx+10h]
0x18006c235  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006c23c  mov     edx, 2BDh
0x18006c241  mov     r9d, ebx
0x18006c244  call    WPP_SF_d
0x18006c249  mov     eax, ebx
0x18006c24b  add     rsp, 38h
0x18006c24f  pop     r15
0x18006c251  pop     r14
0x18006c253  pop     r13
0x18006c255  pop     r12
0x18006c257  pop     rdi
0x18006c258  pop     rsi
0x18006c259  pop     rbp
0x18006c25a  pop     rbx
0x18006c25b  retn
```
