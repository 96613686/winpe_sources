# MSCryptSetProperty

- ea: `0x18003d350`
- end: `0x18003d530`
- name: `MSCryptSetProperty`
- size: `480`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x18003d350`
- `0x18003d538`
- `0x18007ddc8`
- `0x18007de78`
- `0x18009f616`

## string_xrefs

- `0x18003d412`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18003d4be`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x1800a3301`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`

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
        v18 = qword_1800A7090[14 * (unsigned int)(unsigned __int16)v17 - 14];
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
0x18003d350  push    rbx
0x18003d352  push    rbp
0x18003d353  push    rsi
0x18003d354  push    rdi
0x18003d355  push    r14
0x18003d357  sub     rsp, 40h
0x18003d35b  mov     ebp, r9d
0x18003d35e  mov     rsi, r8
0x18003d361  mov     rdi, rdx
0x18003d364  mov     r14, rcx
0x18003d367  call    validateMSCryptSymmObject
0x18003d36c  mov     rbx, rax
0x18003d36f  test    rax, rax
0x18003d372  jz      loc_18003D497
0x18003d378  test    rdi, rdi
0x18003d37b  jz      loc_18003D525
0x18003d381  test    r8, r8
0x18003d384  jz      loc_18003D525
0x18003d38a  cmp     [rsp+68h+arg_20], 0
0x18003d392  jnz     loc_18003D525
0x18003d398  lea     rdx, aChainingmode; "ChainingMode"
0x18003d39f  mov     rcx, rdi; Str1
0x18003d3a2  call    wcscmp_0
0x18003d3a7  test    eax, eax
0x18003d3a9  jnz     loc_18003D4EF
0x18003d3af  xor     edx, edx
0x18003d3b1  lea     r10, cs:180000000h
0x18003d3b8  mov     r9, ds:rva rgpszChainModeNameArray[r10+rdx*8]
0x18003d3c0  mov     rcx, rsi
0x18003d3c3  sub     r9, rsi
0x18003d3c6  movzx   eax, word ptr [rcx]
0x18003d3c9  movzx   r8d, word ptr [rcx+r9]
0x18003d3ce  sub     eax, r8d
0x18003d3d1  jnz     short loc_18003D3DC
0x18003d3d3  add     rcx, 2
0x18003d3d7  test    r8d, r8d
0x18003d3da  jnz     short loc_18003D3C6
0x18003d3dc  test    eax, eax
0x18003d3de  jz      short loc_18003D42B
0x18003d3e0  inc     edx
0x18003d3e2  cmp     edx, 6
0x18003d3e5  jb      short loc_18003D3B8
0x18003d3e7  mov     ebx, 0C000000Dh
0x18003d3ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d3f3  lea     rax, WPP_GLOBAL_Control
0x18003d3fa  cmp     rcx, rax
0x18003d3fd  jz      loc_18003D489
0x18003d403  mov     eax, [rcx+2Ch]
0x18003d406  test    al, 1
0x18003d408  jz      short loc_18003D489
0x18003d40a  mov     [rsp+68h+var_38], 9A6h
0x18003d412  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003d419  mov     [rsp+68h+var_40], r8
0x18003d41e  mov     [rsp+68h+var_48], 0C000000Dh
0x18003d426  jmp     loc_18003D4D2
0x18003d42b  mov     r8d, [rbx+8]
0x18003d42f  movzx   eax, r8w
0x18003d433  dec     eax
0x18003d435  imul    rax, 70h ; 'p'
0x18003d439  mov     eax, [rax+r10+0A7090h]
0x18003d441  bt      eax, edx
0x18003d444  jnb     loc_18003D4E4
0x18003d44a  mov     ecx, ds:rva rgdwDefaultMsgBlockSize[r10+rdx*4]
0x18003d452  mov     [rbx+0Ch], edx
0x18003d455  mov     [rbx+14h], ecx
0x18003d458  test    ecx, ecx
0x18003d45a  jnz     short loc_18003D462
0x18003d45c  mov     eax, [rbx+10h]
0x18003d45f  mov     [rbx+14h], eax
0x18003d462  cmp     dword ptr [rbx+4], 4D535341h
0x18003d469  jnz     short loc_18003D487
0x18003d46b  cmp     r8d, 10002h
0x18003d472  jnz     short loc_18003D487
0x18003d474  cmp     edx, 5
0x18003d477  mov     eax, 0C80h
0x18003d47c  mov     ecx, 250h
0x18003d481  cmovnz  eax, ecx
0x18003d484  mov     [rbx+1Ch], eax
0x18003d487  xor     ebx, ebx
0x18003d489  mov     eax, ebx
0x18003d48b  add     rsp, 40h
0x18003d48f  pop     r14
0x18003d491  pop     rdi
0x18003d492  pop     rsi
0x18003d493  pop     rbp
0x18003d494  pop     rbx
0x18003d495  retn
0x18003d497  mov     ebx, 0C0000008h
0x18003d49c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d4a3  lea     rax, WPP_GLOBAL_Control
0x18003d4aa  cmp     rcx, rax
0x18003d4ad  jz      short loc_18003D489
0x18003d4af  mov     eax, [rcx+2Ch]
0x18003d4b2  test    al, 1
0x18003d4b4  jz      short loc_18003D489
0x18003d4b6  mov     [rsp+68h+var_38], 985h
0x18003d4be  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003d4c5  mov     [rsp+68h+var_40], r8
0x18003d4ca  mov     [rsp+68h+var_48], 0C0000008h
0x18003d4d2  mov     rcx, [rcx+18h]
0x18003d4d6  lea     r9, aStatus; "Status"
0x18003d4dd  call    WPP_SF_sDsd
0x18003d4e2  jmp     short loc_18003D489
0x18003d4e4  mov     r9d, 9ADh
0x18003d4ea  jmp     loc_1800A32E0
0x18003d4ef  lea     rdx, aMessageblockle; "MessageBlockLength"
0x18003d4f6  mov     rcx, rdi; Str1
0x18003d4f9  call    wcscmp_0
0x18003d4fe  test    eax, eax
0x18003d500  jnz     loc_1800A334A
0x18003d506  mov     ecx, [rbx+8]
0x18003d509  mov     edx, 10008h
0x18003d50e  cmp     ecx, edx
0x18003d510  jz      loc_1800A32EC
0x18003d516  cmp     dword ptr [rbx+0Ch], 3
0x18003d51a  jnz     loc_1800A32DA
0x18003d520  jmp     loc_1800A32EC
0x18003d525  mov     r9d, 98Eh
0x18003d52b  jmp     loc_1800A32F7
0x1800a32da  mov     r9d, 9D0h
0x1800a32e0  mov     ebx, 0C00000BBh
0x1800a32e5  mov     ecx, 0C00000BBh
0x1800a32ea  jmp     short loc_1800A3301
0x1800a32ec  cmp     ebp, 4
0x1800a32ef  jz      short loc_1800A331A
0x1800a32f1  mov     r9d, 9D7h
0x1800a32f7  mov     ecx, 0C000000Dh
0x1800a32fc  mov     ebx, 0C000000Dh
0x1800a3301  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a3308  lea     rdx, aStatus; "Status"
0x1800a330f  call    DebugTraceError
0x1800a3314  nop
0x1800a3315  jmp     loc_18003D489
0x1800a331a  mov     eax, [rsi]
0x1800a331c  cmp     ecx, edx
0x1800a331e  jnz     short loc_1800A3330
0x1800a3320  test    al, 0Fh
0x1800a3322  jnz     short loc_1800A3328
0x1800a3324  test    eax, eax
0x1800a3326  jnz     short loc_1800A3342
0x1800a3328  mov     r9d, 9E2h
0x1800a332e  jmp     short loc_1800A32F7
0x1800a3330  cmp     eax, 1
0x1800a3333  jz      short loc_1800A3342
0x1800a3335  cmp     eax, [rbx+10h]
0x1800a3338  jz      short loc_1800A3342
0x1800a333a  mov     r9d, 9E9h
0x1800a3340  jmp     short loc_1800A32F7
0x1800a3342  mov     [rbx+14h], eax
0x1800a3345  jmp     loc_18003D487
0x1800a334a  mov     ecx, [rbx+4]
0x1800a334d  sub     ecx, 4D535341h
0x1800a3353  jz      short loc_1800A339C
0x1800a3355  cmp     ecx, 0Ah
0x1800a3358  jz      short loc_1800A336C
0x1800a335a  mov     ebx, 0C0000008h
0x1800a335f  mov     r9d, 0A11h
0x1800a3365  mov     ecx, 0C0000008h
0x1800a336a  jmp     short loc_1800A3301
0x1800a336c  mov     r9d, ebp
0x1800a336f  mov     r8, rsi
0x1800a3372  mov     rdx, rdi
0x1800a3375  mov     rcx, r14
0x1800a3378  call    MSCryptSetKeyProperty
0x1800a337d  mov     ebx, eax
0x1800a337f  test    eax, eax
0x1800a3381  jns     loc_18003D489
0x1800a3387  mov     r9d, 0A0Ah
0x1800a338d  jmp     short loc_1800A3395
0x1800a338f  mov     r9d, 9FDh
0x1800a3395  mov     ecx, eax
0x1800a3397  jmp     loc_1800A3301
0x1800a339c  mov     r9d, ebp
0x1800a339f  mov     r8, rsi
0x1800a33a2  mov     rdx, rdi
0x1800a33a5  mov     rcx, r14
0x1800a33a8  call    MSCryptSetAlgProperty
0x1800a33ad  mov     ebx, eax
0x1800a33af  test    eax, eax
0x1800a33b1  jns     loc_18003D489
0x1800a33b7  jmp     short loc_1800A338F
```
