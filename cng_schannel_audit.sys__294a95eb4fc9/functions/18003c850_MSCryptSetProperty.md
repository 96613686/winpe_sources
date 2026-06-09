# MSCryptSetProperty

- ea: `0x18003c850`
- end: `0x18003ca30`
- name: `MSCryptSetProperty`
- size: `480`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x18003c850`
- `0x18003ca38`
- `0x18007cdd8`
- `0x18007ce88`
- `0x18009d746`

## string_xrefs

- `0x18003c912`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18003c9be`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x1800a14d1`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`

## pseudocode

```c
__int64 __fastcall MSCryptSetProperty(__int64 a1, const wchar_t *a2, char *a3, unsigned int a4, int a5)
{
  int v9; // edx
  _DWORD *v10; // rbx
  __int64 v11; // r8
  __int64 v12; // rdx
  unsigned __int16 *v13; // rcx
  int v14; // r8d
  int v15; // eax
  unsigned int v16; // ebx
  int v17; // r8d
  int v18; // eax
  int v19; // ecx
  int v20; // eax
  __int64 v22; // r9
  int v23; // ecx
  __int64 v24; // rcx
  int v25; // eax
  int v26; // eax

  v10 = (_DWORD *)validateMSCryptSymmObject();
  if ( v10 )
  {
    if ( a2 && v11 && !a5 )
    {
      if ( !wcscmp_0(a2, L"ChainingMode") )
      {
        v12 = 0;
        while ( 1 )
        {
          v13 = (unsigned __int16 *)a3;
          do
          {
            v14 = *(unsigned __int16 *)((char *)v13 + (char *)rgpszChainModeNameArray[v12] - a3);
            v15 = *v13 - v14;
            if ( v15 )
              break;
            ++v13;
          }
          while ( v14 );
          if ( !v15 )
            break;
          v12 = (unsigned int)(v12 + 1);
          if ( (unsigned int)v12 >= 6 )
          {
            v16 = -1073741811;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
            {
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v12,
                (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
                (unsigned int)"Status",
                13,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
                166);
            }
            return v16;
          }
        }
        v17 = v10[2];
        v18 = qword_1800A5090[14 * (unsigned int)(unsigned __int16)v17 - 14];
        if ( !_bittest(&v18, v12) )
        {
          v22 = 2477;
          goto LABEL_36;
        }
        v19 = rgdwDefaultMsgBlockSize[v12];
        v10[3] = v12;
        v10[5] = v19;
        if ( !v19 )
          v10[5] = v10[4];
        if ( v10[1] == 1297306433 && v17 == 65538 )
        {
          v20 = 3200;
          if ( (_DWORD)v12 != 5 )
            v20 = 592;
          v10[7] = v20;
        }
        return 0;
      }
      if ( wcscmp_0(a2, L"MessageBlockLength") )
      {
        if ( v10[1] == 1297306433 )
        {
          v26 = MSCryptSetAlgProperty(a1, a2, a3, a4);
          v16 = v26;
          if ( v26 >= 0 )
            return v16;
          v22 = 2557;
        }
        else
        {
          if ( v10[1] != 1297306443 )
          {
            v16 = -1073741816;
            v22 = 2577;
            v24 = 3221225480LL;
            goto LABEL_40;
          }
          v26 = MSCryptSetKeyProperty(a1, a2, a3, a4);
          v16 = v26;
          if ( v26 >= 0 )
            return v16;
          v22 = 2570;
        }
        v24 = (unsigned int)v26;
        goto LABEL_40;
      }
      v23 = v10[2];
      if ( v23 != 65544 && v10[3] != 3 )
      {
        v22 = 2512;
LABEL_36:
        v16 = -1073741637;
        v24 = 3221225659LL;
        goto LABEL_40;
      }
      if ( a4 == 4 )
      {
        v25 = *(_DWORD *)a3;
        if ( v23 == 65544 )
        {
          if ( (v25 & 0xF) != 0 || !v25 )
          {
            v22 = 2530;
            goto LABEL_39;
          }
        }
        else if ( v25 != 1 && v25 != v10[4] )
        {
          v22 = 2537;
          goto LABEL_39;
        }
        v10[5] = v25;
        return 0;
      }
      v22 = 2519;
    }
    else
    {
      v22 = 2446;
    }
LABEL_39:
    v24 = 3221225485LL;
    v16 = -1073741811;
LABEL_40:
    DebugTraceError(v24, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c", v22);
    return v16;
  }
  v16 = -1073741816;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v9,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
      (unsigned int)"Status",
      8,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
      133);
  return v16;
}

```

## disassembly

```asm
0x18003c850  push    rbx
0x18003c852  push    rbp
0x18003c853  push    rsi
0x18003c854  push    rdi
0x18003c855  push    r14
0x18003c857  sub     rsp, 40h
0x18003c85b  mov     ebp, r9d
0x18003c85e  mov     rsi, r8
0x18003c861  mov     rdi, rdx
0x18003c864  mov     r14, rcx
0x18003c867  call    validateMSCryptSymmObject
0x18003c86c  mov     rbx, rax
0x18003c86f  test    rax, rax
0x18003c872  jz      loc_18003C997
0x18003c878  test    rdi, rdi
0x18003c87b  jz      loc_18003CA25
0x18003c881  test    r8, r8
0x18003c884  jz      loc_18003CA25
0x18003c88a  cmp     [rsp+68h+arg_20], 0
0x18003c892  jnz     loc_18003CA25
0x18003c898  lea     rdx, aChainingmode; "ChainingMode"
0x18003c89f  mov     rcx, rdi; Str1
0x18003c8a2  call    wcscmp_0
0x18003c8a7  test    eax, eax
0x18003c8a9  jnz     loc_18003C9EF
0x18003c8af  xor     edx, edx
0x18003c8b1  lea     r10, cs:180000000h
0x18003c8b8  mov     r9, ds:rva rgpszChainModeNameArray[r10+rdx*8]
0x18003c8c0  mov     rcx, rsi
0x18003c8c3  sub     r9, rsi
0x18003c8c6  movzx   eax, word ptr [rcx]
0x18003c8c9  movzx   r8d, word ptr [rcx+r9]
0x18003c8ce  sub     eax, r8d
0x18003c8d1  jnz     short loc_18003C8DC
0x18003c8d3  add     rcx, 2
0x18003c8d7  test    r8d, r8d
0x18003c8da  jnz     short loc_18003C8C6
0x18003c8dc  test    eax, eax
0x18003c8de  jz      short loc_18003C92B
0x18003c8e0  inc     edx
0x18003c8e2  cmp     edx, 6
0x18003c8e5  jb      short loc_18003C8B8
0x18003c8e7  mov     ebx, 0C000000Dh
0x18003c8ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c8f3  lea     rax, WPP_GLOBAL_Control
0x18003c8fa  cmp     rcx, rax
0x18003c8fd  jz      loc_18003C989
0x18003c903  mov     eax, [rcx+2Ch]
0x18003c906  test    al, 1
0x18003c908  jz      short loc_18003C989
0x18003c90a  mov     [rsp+68h+var_38], 9A6h
0x18003c912  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003c919  mov     [rsp+68h+var_40], r8
0x18003c91e  mov     [rsp+68h+var_48], 0C000000Dh
0x18003c926  jmp     loc_18003C9D2
0x18003c92b  mov     r8d, [rbx+8]
0x18003c92f  movzx   eax, r8w
0x18003c933  dec     eax
0x18003c935  imul    rax, 70h ; 'p'
0x18003c939  mov     eax, [rax+r10+0A5090h]
0x18003c941  bt      eax, edx
0x18003c944  jnb     loc_18003C9E4
0x18003c94a  mov     ecx, ds:rva rgdwDefaultMsgBlockSize[r10+rdx*4]
0x18003c952  mov     [rbx+0Ch], edx
0x18003c955  mov     [rbx+14h], ecx
0x18003c958  test    ecx, ecx
0x18003c95a  jnz     short loc_18003C962
0x18003c95c  mov     eax, [rbx+10h]
0x18003c95f  mov     [rbx+14h], eax
0x18003c962  cmp     dword ptr [rbx+4], 4D535341h
0x18003c969  jnz     short loc_18003C987
0x18003c96b  cmp     r8d, 10002h
0x18003c972  jnz     short loc_18003C987
0x18003c974  cmp     edx, 5
0x18003c977  mov     eax, 0C80h
0x18003c97c  mov     ecx, 250h
0x18003c981  cmovnz  eax, ecx
0x18003c984  mov     [rbx+1Ch], eax
0x18003c987  xor     ebx, ebx
0x18003c989  mov     eax, ebx
0x18003c98b  add     rsp, 40h
0x18003c98f  pop     r14
0x18003c991  pop     rdi
0x18003c992  pop     rsi
0x18003c993  pop     rbp
0x18003c994  pop     rbx
0x18003c995  retn
0x18003c997  mov     ebx, 0C0000008h
0x18003c99c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c9a3  lea     rax, WPP_GLOBAL_Control
0x18003c9aa  cmp     rcx, rax
0x18003c9ad  jz      short loc_18003C989
0x18003c9af  mov     eax, [rcx+2Ch]
0x18003c9b2  test    al, 1
0x18003c9b4  jz      short loc_18003C989
0x18003c9b6  mov     [rsp+68h+var_38], 985h
0x18003c9be  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003c9c5  mov     [rsp+68h+var_40], r8
0x18003c9ca  mov     [rsp+68h+var_48], 0C0000008h
0x18003c9d2  mov     rcx, [rcx+18h]
0x18003c9d6  lea     r9, aStatus; "Status"
0x18003c9dd  call    WPP_SF_sDsd
0x18003c9e2  jmp     short loc_18003C989
0x18003c9e4  mov     r9d, 9ADh
0x18003c9ea  jmp     loc_1800A14B0
0x18003c9ef  lea     rdx, aMessageblockle; "MessageBlockLength"
0x18003c9f6  mov     rcx, rdi; Str1
0x18003c9f9  call    wcscmp_0
0x18003c9fe  test    eax, eax
0x18003ca00  jnz     loc_1800A151A
0x18003ca06  mov     ecx, [rbx+8]
0x18003ca09  mov     edx, 10008h
0x18003ca0e  cmp     ecx, edx
0x18003ca10  jz      loc_1800A14BC
0x18003ca16  cmp     dword ptr [rbx+0Ch], 3
0x18003ca1a  jnz     loc_1800A14AA
0x18003ca20  jmp     loc_1800A14BC
0x18003ca25  mov     r9d, 98Eh
0x18003ca2b  jmp     loc_1800A14C7
0x1800a14aa  mov     r9d, 9D0h
0x1800a14b0  mov     ebx, 0C00000BBh
0x1800a14b5  mov     ecx, 0C00000BBh
0x1800a14ba  jmp     short loc_1800A14D1
0x1800a14bc  cmp     ebp, 4
0x1800a14bf  jz      short loc_1800A14EA
0x1800a14c1  mov     r9d, 9D7h
0x1800a14c7  mov     ecx, 0C000000Dh
0x1800a14cc  mov     ebx, 0C000000Dh
0x1800a14d1  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a14d8  lea     rdx, aStatus; "Status"
0x1800a14df  call    DebugTraceError
0x1800a14e4  nop
0x1800a14e5  jmp     loc_18003C989
0x1800a14ea  mov     eax, [rsi]
0x1800a14ec  cmp     ecx, edx
0x1800a14ee  jnz     short loc_1800A1500
0x1800a14f0  test    al, 0Fh
0x1800a14f2  jnz     short loc_1800A14F8
0x1800a14f4  test    eax, eax
0x1800a14f6  jnz     short loc_1800A1512
0x1800a14f8  mov     r9d, 9E2h
0x1800a14fe  jmp     short loc_1800A14C7
0x1800a1500  cmp     eax, 1
0x1800a1503  jz      short loc_1800A1512
0x1800a1505  cmp     eax, [rbx+10h]
0x1800a1508  jz      short loc_1800A1512
0x1800a150a  mov     r9d, 9E9h
0x1800a1510  jmp     short loc_1800A14C7
0x1800a1512  mov     [rbx+14h], eax
0x1800a1515  jmp     loc_18003C987
0x1800a151a  mov     ecx, [rbx+4]
0x1800a151d  sub     ecx, 4D535341h
0x1800a1523  jz      short loc_1800A156C
0x1800a1525  cmp     ecx, 0Ah
0x1800a1528  jz      short loc_1800A153C
0x1800a152a  mov     ebx, 0C0000008h
0x1800a152f  mov     r9d, 0A11h
0x1800a1535  mov     ecx, 0C0000008h
0x1800a153a  jmp     short loc_1800A14D1
0x1800a153c  mov     r9d, ebp
0x1800a153f  mov     r8, rsi
0x1800a1542  mov     rdx, rdi
0x1800a1545  mov     rcx, r14
0x1800a1548  call    MSCryptSetKeyProperty
0x1800a154d  mov     ebx, eax
0x1800a154f  test    eax, eax
0x1800a1551  jns     loc_18003C989
0x1800a1557  mov     r9d, 0A0Ah
0x1800a155d  jmp     short loc_1800A1565
0x1800a155f  mov     r9d, 9FDh
0x1800a1565  mov     ecx, eax
0x1800a1567  jmp     loc_1800A14D1
0x1800a156c  mov     r9d, ebp
0x1800a156f  mov     r8, rsi
0x1800a1572  mov     rdx, rdi
0x1800a1575  mov     rcx, r14
0x1800a1578  call    MSCryptSetAlgProperty
0x1800a157d  mov     ebx, eax
0x1800a157f  test    eax, eax
0x1800a1581  jns     loc_18003C989
0x1800a1587  jmp     short loc_1800A155F
```
