# MSMSetOneXConnectionProfile

- ea: `0x180028724`
- end: `0x1800288bd`
- name: `MSMSetOneXConnectionProfile`
- size: `409`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180009540`
- `0x180027598`
- `0x18002a3a0`

## callees

- `0x180005440`
- `0x180007f60`
- `0x180010ae0`
- `0x1800214f0`
- `0x180028724`
- `0x180030010`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x1800287de`
- `MobileNetworking!ReleaseWriteLock` at `0x1800287de`
- `MobileNetworking!AcquireWriteLock` at `0x180028841`
- `MobileNetworking!AcquireWriteLock` at `0x180028841`

## pseudocode

```c
__int64 __fastcall MSMSetOneXConnectionProfile(__int64 a1, unsigned int a2, __int64 a3)
{
  unsigned int v3; // edi
  __int64 v5; // r15
  __int64 v7; // r12
  char *v9; // rcx
  int v10; // eax
  __int64 v11; // rdx

  v3 = *(_DWORD *)(a1 + 20);
  v5 = *(_QWORD *)(a1 + 192);
  v7 = *(_QWORD *)(a1 + 2368);
  v9 = (char *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 56, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids);
    v9 = (char *)WPP_GLOBAL_Control;
  }
  if ( !*(_QWORD *)(a1 + 2304) )
  {
    if ( v9 == (char *)&WPP_GLOBAL_Control )
      return 0;
    if ( v9[68] >= 0 )
      goto LABEL_22;
    v11 = 60;
    goto LABEL_20;
  }
  if ( (*(_DWORD *)(a1 + 24) & 0x200) == 0 )
  {
    if ( v9 != (char *)&WPP_GLOBAL_Control && v9[68] < 0 )
      WPP_SF_d(*((_QWORD *)v9 + 7), 57, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v3);
    ReleaseWriteLock(a1, a1 + 2896, "MSMSetOneXConnectionProfile", 574);
    v10 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(a1 + 2304))(v5, v7, a2, a3);
    if ( v10 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 58, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v3, v10);
    AcquireWriteLock(a1, a1 + 2896, "MSMSetOneXConnectionProfile", 607);
    goto LABEL_21;
  }
  if ( v9 == (char *)&WPP_GLOBAL_Control )
    return 0;
  if ( v9[68] < 0 )
  {
    v11 = 59;
LABEL_20:
    WPP_SF_d(*((_QWORD *)v9 + 7), v11, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v3);
LABEL_21:
    v9 = (char *)WPP_GLOBAL_Control;
  }
LABEL_22:
  if ( v9 != (char *)&WPP_GLOBAL_Control && (*((_DWORD *)v9 + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)v9 + 7), 61, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x180028724  push    rbx
0x180028726  push    rbp
0x180028727  push    rsi
0x180028728  push    rdi
0x180028729  push    r12
0x18002872b  push    r13
0x18002872d  push    r14
0x18002872f  push    r15
0x180028731  sub     rsp, 38h
0x180028735  mov     edi, [rcx+14h]
0x180028738  mov     rbp, r8
0x18002873b  mov     r15, [rcx+0C0h]
0x180028742  mov     r14d, edx
0x180028745  mov     r12, [rcx+940h]
0x18002874c  mov     rbx, rcx
0x18002874f  mov     rcx, cs:WPP_GLOBAL_Control
0x180028756  lea     r13, WPP_GLOBAL_Control
0x18002875d  lea     rsi, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x180028764  cmp     rcx, r13
0x180028767  jz      short loc_18002878A
0x180028769  test    dword ptr [rcx+44h], 800h
0x180028770  jz      short loc_18002878A
0x180028772  mov     rcx, [rcx+38h]
0x180028776  mov     edx, 38h ; '8'
0x18002877b  mov     r8, rsi
0x18002877e  call    WPP_SF_
0x180028783  mov     rcx, cs:WPP_GLOBAL_Control
0x18002878a  cmp     qword ptr [rbx+900h], 0
0x180028792  jz      loc_180028862
0x180028798  test    dword ptr [rbx+18h], 200h
0x18002879f  jnz     loc_180028850
0x1800287a5  cmp     rcx, r13
0x1800287a8  jz      short loc_1800287C4
0x1800287aa  test    byte ptr [rcx+44h], 80h
0x1800287ae  jz      short loc_1800287C4
0x1800287b0  mov     rcx, [rcx+38h]
0x1800287b4  mov     edx, 39h ; '9'
0x1800287b9  mov     r9d, edi
0x1800287bc  mov     r8, rsi
0x1800287bf  call    WPP_SF_d
0x1800287c4  lea     rsi, [rbx+0B50h]
0x1800287cb  mov     r9d, 23Eh
0x1800287d1  mov     rdx, rsi
0x1800287d4  lea     r8, aMsmsetonexconn; "MSMSetOneXConnectionProfile"
0x1800287db  mov     rcx, rbx
0x1800287de  call    cs:__imp_ReleaseWriteLock
0x1800287e4  mov     rax, [rbx+900h]
0x1800287eb  mov     r9, rbp
0x1800287ee  mov     r8d, r14d
0x1800287f1  mov     rdx, r12
0x1800287f4  mov     rcx, r15
0x1800287f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800287fc  test    eax, eax
0x1800287fe  jz      short loc_18002882E
0x180028800  mov     rcx, cs:WPP_GLOBAL_Control
0x180028807  cmp     rcx, r13
0x18002880a  jz      short loc_18002882E
0x18002880c  test    byte ptr [rcx+44h], 1
0x180028810  jz      short loc_18002882E
0x180028812  mov     rcx, [rcx+38h]
0x180028816  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x18002881d  mov     edx, 3Ah ; ':'
0x180028822  mov     [rsp+78h+var_58], eax
0x180028826  mov     r9d, edi
0x180028829  call    WPP_SF_dd
0x18002882e  mov     r9d, 25Fh
0x180028834  lea     r8, aMsmsetonexconn; "MSMSetOneXConnectionProfile"
0x18002883b  mov     rdx, rsi
0x18002883e  mov     rcx, rbx
0x180028841  call    cs:__imp_AcquireWriteLock
0x180028847  lea     rsi, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x18002884e  jmp     short loc_180028881
0x180028850  cmp     rcx, r13
0x180028853  jz      short loc_1800288AA
0x180028855  test    byte ptr [rcx+44h], 80h
0x180028859  jz      short loc_180028888
0x18002885b  mov     edx, 3Bh ; ';'
0x180028860  jmp     short loc_180028872
0x180028862  cmp     rcx, r13
0x180028865  jz      short loc_1800288AA
0x180028867  test    byte ptr [rcx+44h], 80h
0x18002886b  jz      short loc_180028888
0x18002886d  mov     edx, 3Ch ; '<'
0x180028872  mov     rcx, [rcx+38h]
0x180028876  mov     r9d, edi
0x180028879  mov     r8, rsi
0x18002887c  call    WPP_SF_d
0x180028881  mov     rcx, cs:WPP_GLOBAL_Control
0x180028888  cmp     rcx, r13
0x18002888b  jz      short loc_1800288AA
0x18002888d  test    dword ptr [rcx+44h], 800h
0x180028894  jz      short loc_1800288AA
0x180028896  mov     rcx, [rcx+38h]
0x18002889a  mov     edx, 3Dh ; '='
0x18002889f  xor     r9d, r9d
0x1800288a2  mov     r8, rsi
0x1800288a5  call    WPP_SF_D
0x1800288aa  xor     eax, eax
0x1800288ac  add     rsp, 38h
0x1800288b0  pop     r15
0x1800288b2  pop     r14
0x1800288b4  pop     r13
0x1800288b6  pop     r12
0x1800288b8  pop     rdi
0x1800288b9  pop     rsi
0x1800288ba  pop     rbp
0x1800288bb  pop     rbx
0x1800288bc  retn
```
