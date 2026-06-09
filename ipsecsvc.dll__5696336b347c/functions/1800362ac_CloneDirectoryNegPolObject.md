# CloneDirectoryNegPolObject

- ea: `0x1800362ac`
- end: `0x180036575`
- name: `CloneDirectoryNegPolObject`
- size: `713`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18003657c`

## callees

- `0x180006f00`
- `0x18000c828`
- `0x18000e510`
- `0x1800362ac`
- `0x180036a94`
- `0x180036bd0`
- `0x180036c54`
- `0x180042d44`

## pseudocode

```c
__int64 __fastcall CloneDirectoryNegPolObject(__int64 a1, __int64 *a2)
{
  __int64 v4; // rax
  __int64 v5; // rsi
  unsigned int v6; // edi
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  unsigned __int16 *v9; // rcx
  __int64 v10; // rax
  __int64 v11; // r9
  unsigned __int16 *v12; // rcx
  __int64 v13; // rax
  unsigned __int16 *v14; // rcx
  __int64 v15; // rax
  void *v16; // rcx
  unsigned __int16 *v17; // rcx
  __int64 v18; // rax
  unsigned __int16 *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rcx

  v4 = IpsecAllocMem(88);
  v5 = v4;
  if ( !v4 )
  {
    v6 = 14;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, WPP_536406ce45663b69fb8864445bd745b5_Traceguids, 14);
    goto LABEL_50;
  }
  if ( *(_QWORD *)a1 )
  {
    v6 = CopyDSToFQRegString(*(_QWORD *)a1, 0, v4);
    if ( v6 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_49;
      v8 = 114;
      goto LABEL_47;
    }
  }
  else
  {
    v6 = 0;
  }
  v9 = *(unsigned __int16 **)(a1 + 8);
  if ( v9 )
  {
    v10 = IpsecAllocStr(v9);
    *(_QWORD *)(v5 + 8) = v10;
    if ( !v10 )
    {
      v11 = 14;
      v6 = 14;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_49;
      v8 = 115;
      goto LABEL_48;
    }
  }
  v12 = *(unsigned __int16 **)(a1 + 80);
  if ( v12 )
  {
    v13 = IpsecAllocStr(v12);
    *(_QWORD *)(v5 + 80) = v13;
    if ( !v13 )
    {
      v11 = 14;
      v6 = 14;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_49;
      v8 = 116;
      goto LABEL_48;
    }
  }
  v14 = *(unsigned __int16 **)(a1 + 16);
  if ( v14 )
  {
    v15 = IpsecAllocStr(v14);
    *(_QWORD *)(v5 + 16) = v15;
    if ( !v15 )
    {
      v11 = 14;
      v6 = 14;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_49;
      v8 = 117;
      goto LABEL_48;
    }
  }
  *(_DWORD *)(v5 + 24) = *(_DWORD *)(a1 + 24);
  v16 = *(void **)(a1 + 32);
  if ( v16 )
  {
    v6 = CopyBinaryValue(v16, *(unsigned int *)(a1 + 40));
    if ( v6 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_49;
      v8 = 118;
      goto LABEL_47;
    }
    *(_DWORD *)(v5 + 40) = *(_DWORD *)(a1 + 40);
  }
  v17 = *(unsigned __int16 **)(a1 + 48);
  if ( v17 )
  {
    v18 = IpsecAllocStr(v17);
    *(_QWORD *)(v5 + 48) = v18;
    if ( !v18 )
    {
      v11 = 14;
      v6 = 14;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_49;
      v8 = 119;
      goto LABEL_48;
    }
  }
  v19 = *(unsigned __int16 **)(a1 + 56);
  if ( v19 )
  {
    v20 = IpsecAllocStr(v19);
    *(_QWORD *)(v5 + 56) = v20;
    if ( !v20 )
    {
      v11 = 14;
      v6 = 14;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_49;
      v8 = 120;
      goto LABEL_48;
    }
  }
  v21 = *(_QWORD *)(a1 + 64);
  if ( !v21 || (v6 = CloneNFAReferencesDSToRegistry(v21, *(unsigned int *)(a1 + 72), v5 + 64, v5 + 72)) == 0 )
  {
    *(_DWORD *)(v5 + 76) = *(_DWORD *)(a1 + 76);
    *a2 = v5;
    return v6;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
    goto LABEL_49;
  v8 = 121;
LABEL_47:
  v11 = v6;
LABEL_48:
  WPP_SF_d(v7[2], v8, WPP_536406ce45663b69fb8864445bd745b5_Traceguids, v11);
LABEL_49:
  FreeIpsecNegPolObject((LPVOID)v5);
LABEL_50:
  *a2 = 0;
  return v6;
}

```

## disassembly

```asm
0x1800362ac  push    rbx
0x1800362ae  push    rsi
0x1800362af  push    rdi
0x1800362b0  push    r14
0x1800362b2  sub     rsp, 28h
0x1800362b6  mov     rbx, rcx
0x1800362b9  mov     r14, rdx
0x1800362bc  mov     ecx, 58h ; 'X'
0x1800362c1  call    IpsecAllocMem
0x1800362c6  mov     rsi, rax
0x1800362c9  test    rax, rax
0x1800362cc  jnz     short loc_18003630E
0x1800362ce  lea     r9d, [rax+0Eh]
0x1800362d2  mov     edi, r9d
0x1800362d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800362dc  lea     rax, WPP_GLOBAL_Control
0x1800362e3  cmp     rcx, rax
0x1800362e6  jz      loc_180036557
0x1800362ec  test    byte ptr [rcx+1Ch], 10h
0x1800362f0  jz      loc_180036557
0x1800362f6  mov     rcx, [rcx+10h]
0x1800362fa  lea     edx, [rsi+71h]
0x1800362fd  lea     r8, WPP_536406ce45663b69fb8864445bd745b5_Traceguids
0x180036304  call    WPP_SF_d
0x180036309  jmp     loc_180036557
0x18003630e  mov     rcx, [rbx]
0x180036311  test    rcx, rcx
0x180036314  jz      short loc_180036351
0x180036316  mov     r8, rsi
0x180036319  xor     edx, edx
0x18003631b  call    CopyDSToFQRegString
0x180036320  mov     edi, eax
0x180036322  test    eax, eax
0x180036324  jz      short loc_180036353
0x180036326  mov     rcx, cs:WPP_GLOBAL_Control
0x18003632d  lea     rax, WPP_GLOBAL_Control
0x180036334  cmp     rcx, rax
0x180036337  jz      loc_18003654F
0x18003633d  test    byte ptr [rcx+1Ch], 10h
0x180036341  jz      loc_18003654F
0x180036347  mov     edx, 72h ; 'r'
0x18003634c  jmp     loc_18003653C
0x180036351  xor     edi, edi
0x180036353  mov     rcx, [rbx+8]; unsigned __int16 *
0x180036357  test    rcx, rcx
0x18003635a  jz      short loc_18003639B
0x18003635c  call    IpsecAllocStr
0x180036361  mov     [rsi+8], rax
0x180036365  test    rax, rax
0x180036368  jnz     short loc_18003639B
0x18003636a  lea     r9d, [rax+0Eh]
0x18003636e  mov     edi, r9d
0x180036371  mov     rcx, cs:WPP_GLOBAL_Control
0x180036378  lea     rax, WPP_GLOBAL_Control
0x18003637f  cmp     rcx, rax
0x180036382  jz      loc_18003654F
0x180036388  test    byte ptr [rcx+1Ch], 10h
0x18003638c  jz      loc_18003654F
0x180036392  lea     edx, [r9+65h]
0x180036396  jmp     loc_18003653F
0x18003639b  mov     rcx, [rbx+50h]; unsigned __int16 *
0x18003639f  test    rcx, rcx
0x1800363a2  jz      short loc_1800363E3
0x1800363a4  call    IpsecAllocStr
0x1800363a9  mov     [rsi+50h], rax
0x1800363ad  test    rax, rax
0x1800363b0  jnz     short loc_1800363E3
0x1800363b2  lea     r9d, [rax+0Eh]
0x1800363b6  mov     edi, r9d
0x1800363b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800363c0  lea     rax, WPP_GLOBAL_Control
0x1800363c7  cmp     rcx, rax
0x1800363ca  jz      loc_18003654F
0x1800363d0  test    byte ptr [rcx+1Ch], 10h
0x1800363d4  jz      loc_18003654F
0x1800363da  lea     edx, [r9+66h]
0x1800363de  jmp     loc_18003653F
0x1800363e3  mov     rcx, [rbx+10h]; unsigned __int16 *
0x1800363e7  test    rcx, rcx
0x1800363ea  jz      short loc_18003642B
0x1800363ec  call    IpsecAllocStr
0x1800363f1  mov     [rsi+10h], rax
0x1800363f5  test    rax, rax
0x1800363f8  jnz     short loc_18003642B
0x1800363fa  lea     r9d, [rax+0Eh]
0x1800363fe  mov     edi, r9d
0x180036401  mov     rcx, cs:WPP_GLOBAL_Control
0x180036408  lea     rax, WPP_GLOBAL_Control
0x18003640f  cmp     rcx, rax
0x180036412  jz      loc_18003654F
0x180036418  test    byte ptr [rcx+1Ch], 10h
0x18003641c  jz      loc_18003654F
0x180036422  lea     edx, [r9+67h]
0x180036426  jmp     loc_18003653F
0x18003642b  mov     eax, [rbx+18h]
0x18003642e  mov     [rsi+18h], eax
0x180036431  mov     rcx, [rbx+20h]; Src
0x180036435  test    rcx, rcx
0x180036438  jz      short loc_18003647D
0x18003643a  mov     edx, [rbx+28h]; Size
0x18003643d  lea     r8, [rsi+20h]
0x180036441  call    CopyBinaryValue
0x180036446  mov     edi, eax
0x180036448  test    eax, eax
0x18003644a  jz      short loc_180036477
0x18003644c  mov     rcx, cs:WPP_GLOBAL_Control
0x180036453  lea     rax, WPP_GLOBAL_Control
0x18003645a  cmp     rcx, rax
0x18003645d  jz      loc_18003654F
0x180036463  test    byte ptr [rcx+1Ch], 10h
0x180036467  jz      loc_18003654F
0x18003646d  mov     edx, 76h ; 'v'
0x180036472  jmp     loc_18003653C
0x180036477  mov     eax, [rbx+28h]
0x18003647a  mov     [rsi+28h], eax
0x18003647d  mov     rcx, [rbx+30h]; unsigned __int16 *
0x180036481  test    rcx, rcx
0x180036484  jz      short loc_1800364C2
0x180036486  call    IpsecAllocStr
0x18003648b  mov     [rsi+30h], rax
0x18003648f  test    rax, rax
0x180036492  jnz     short loc_1800364C2
0x180036494  lea     r9d, [rax+0Eh]
0x180036498  mov     edi, r9d
0x18003649b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800364a2  lea     rax, WPP_GLOBAL_Control
0x1800364a9  cmp     rcx, rax
0x1800364ac  jz      loc_18003654F
0x1800364b2  test    byte ptr [rcx+1Ch], 10h
0x1800364b6  jz      loc_18003654F
0x1800364bc  lea     edx, [r9+69h]
0x1800364c0  jmp     short loc_18003653F
0x1800364c2  mov     rcx, [rbx+38h]; unsigned __int16 *
0x1800364c6  test    rcx, rcx
0x1800364c9  jz      short loc_1800364FF
0x1800364cb  call    IpsecAllocStr
0x1800364d0  mov     [rsi+38h], rax
0x1800364d4  test    rax, rax
0x1800364d7  jnz     short loc_1800364FF
0x1800364d9  lea     r9d, [rax+0Eh]
0x1800364dd  mov     edi, r9d
0x1800364e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800364e7  lea     rax, WPP_GLOBAL_Control
0x1800364ee  cmp     rcx, rax
0x1800364f1  jz      short loc_18003654F
0x1800364f3  test    byte ptr [rcx+1Ch], 10h
0x1800364f7  jz      short loc_18003654F
0x1800364f9  lea     edx, [r9+6Ah]
0x1800364fd  jmp     short loc_18003653F
0x1800364ff  mov     rcx, [rbx+40h]
0x180036503  test    rcx, rcx
0x180036506  jz      short loc_180036560
0x180036508  mov     edx, [rbx+48h]
0x18003650b  lea     r9, [rsi+48h]
0x18003650f  lea     r8, [rsi+40h]
0x180036513  call    CloneNFAReferencesDSToRegistry
0x180036518  mov     edi, eax
0x18003651a  test    eax, eax
0x18003651c  jz      short loc_180036560
0x18003651e  mov     rcx, cs:WPP_GLOBAL_Control
0x180036525  lea     rax, WPP_GLOBAL_Control
0x18003652c  cmp     rcx, rax
0x18003652f  jz      short loc_18003654F
0x180036531  test    byte ptr [rcx+1Ch], 10h
0x180036535  jz      short loc_18003654F
0x180036537  mov     edx, 79h ; 'y'
0x18003653c  mov     r9d, edi
0x18003653f  mov     rcx, [rcx+10h]
0x180036543  lea     r8, WPP_536406ce45663b69fb8864445bd745b5_Traceguids
0x18003654a  call    WPP_SF_d
0x18003654f  mov     rcx, rsi; lpMem
0x180036552  call    FreeIpsecNegPolObject
0x180036557  mov     qword ptr [r14], 0
0x18003655e  jmp     short loc_180036569
0x180036560  mov     eax, [rbx+4Ch]
0x180036563  mov     [rsi+4Ch], eax
0x180036566  mov     [r14], rsi
0x180036569  mov     eax, edi
0x18003656b  add     rsp, 28h
0x18003656f  pop     r14
0x180036571  pop     rdi
0x180036572  pop     rsi
0x180036573  pop     rbx
0x180036574  retn
```
