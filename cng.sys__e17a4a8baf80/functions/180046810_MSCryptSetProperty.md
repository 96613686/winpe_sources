# MSCryptSetProperty

- ea: `0x180046810`
- end: `0x1800469f0`
- name: `MSCryptSetProperty`
- size: `480`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18001155c`
- `0x1800123d0`
- `0x180046810`
- `0x1800469f8`
- `0x180086fd8`
- `0x180087088`
- `0x1800a4232`

## string_xrefs

- `0x1800468d2`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18004697e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x1800a826f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`

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
                195);
            }
            return v16;
          }
        }
        v17 = v10[2];
        v18 = qword_1800AC090[14 * (unsigned int)(unsigned __int16)v17 - 14];
        if ( !_bittest(&v18, v12) )
        {
          v22 = 2506;
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
          v22 = 2586;
        }
        else
        {
          if ( v10[1] != 1297306443 )
          {
            v16 = -1073741816;
            v22 = 2606;
            v24 = 3221225480LL;
            goto LABEL_40;
          }
          v26 = MSCryptSetKeyProperty(a1, a2, a3, a4);
          v16 = v26;
          if ( v26 >= 0 )
            return v16;
          v22 = 2599;
        }
        v24 = (unsigned int)v26;
        goto LABEL_40;
      }
      v23 = v10[2];
      if ( v23 != 65544 && v10[3] != 3 )
      {
        v22 = 2541;
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
            v22 = 2559;
            goto LABEL_39;
          }
        }
        else if ( v25 != 1 && v25 != v10[4] )
        {
          v22 = 2566;
          goto LABEL_39;
        }
        v10[5] = v25;
        return 0;
      }
      v22 = 2548;
    }
    else
    {
      v22 = 2475;
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
      162);
  return v16;
}

```

## disassembly

```asm
0x180046810  push    rbx
0x180046812  push    rbp
0x180046813  push    rsi
0x180046814  push    rdi
0x180046815  push    r14
0x180046817  sub     rsp, 40h
0x18004681b  mov     ebp, r9d
0x18004681e  mov     rsi, r8
0x180046821  mov     rdi, rdx
0x180046824  mov     r14, rcx
0x180046827  call    validateMSCryptSymmObject
0x18004682c  mov     rbx, rax
0x18004682f  test    rax, rax
0x180046832  jz      loc_180046957
0x180046838  test    rdi, rdi
0x18004683b  jz      loc_1800469E5
0x180046841  test    r8, r8
0x180046844  jz      loc_1800469E5
0x18004684a  cmp     [rsp+68h+arg_20], 0
0x180046852  jnz     loc_1800469E5
0x180046858  lea     rdx, aChainingmode; "ChainingMode"
0x18004685f  mov     rcx, rdi; Str1
0x180046862  call    wcscmp_0
0x180046867  test    eax, eax
0x180046869  jnz     loc_1800469AF
0x18004686f  xor     edx, edx
0x180046871  lea     r10, cs:180000000h
0x180046878  mov     r9, ds:rva rgpszChainModeNameArray[r10+rdx*8]
0x180046880  mov     rcx, rsi
0x180046883  sub     r9, rsi
0x180046886  movzx   eax, word ptr [rcx]
0x180046889  movzx   r8d, word ptr [rcx+r9]
0x18004688e  sub     eax, r8d
0x180046891  jnz     short loc_18004689C
0x180046893  add     rcx, 2
0x180046897  test    r8d, r8d
0x18004689a  jnz     short loc_180046886
0x18004689c  test    eax, eax
0x18004689e  jz      short loc_1800468EB
0x1800468a0  inc     edx
0x1800468a2  cmp     edx, 6
0x1800468a5  jb      short loc_180046878
0x1800468a7  mov     ebx, 0C000000Dh
0x1800468ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800468b3  lea     rax, WPP_GLOBAL_Control
0x1800468ba  cmp     rcx, rax
0x1800468bd  jz      loc_180046949
0x1800468c3  mov     eax, [rcx+2Ch]
0x1800468c6  test    al, 1
0x1800468c8  jz      short loc_180046949
0x1800468ca  mov     [rsp+68h+var_38], 9C3h
0x1800468d2  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800468d9  mov     [rsp+68h+var_40], r8
0x1800468de  mov     [rsp+68h+var_48], 0C000000Dh
0x1800468e6  jmp     loc_180046992
0x1800468eb  mov     r8d, [rbx+8]
0x1800468ef  movzx   eax, r8w
0x1800468f3  dec     eax
0x1800468f5  imul    rax, 70h ; 'p'
0x1800468f9  mov     eax, [rax+r10+0AC090h]
0x180046901  bt      eax, edx
0x180046904  jnb     loc_1800469A4
0x18004690a  mov     ecx, ds:rva rgdwDefaultMsgBlockSize[r10+rdx*4]
0x180046912  mov     [rbx+0Ch], edx
0x180046915  mov     [rbx+14h], ecx
0x180046918  test    ecx, ecx
0x18004691a  jnz     short loc_180046922
0x18004691c  mov     eax, [rbx+10h]
0x18004691f  mov     [rbx+14h], eax
0x180046922  cmp     dword ptr [rbx+4], 4D535341h
0x180046929  jnz     short loc_180046947
0x18004692b  cmp     r8d, 10002h
0x180046932  jnz     short loc_180046947
0x180046934  cmp     edx, 5
0x180046937  mov     eax, 0C80h
0x18004693c  mov     ecx, 250h
0x180046941  cmovnz  eax, ecx
0x180046944  mov     [rbx+1Ch], eax
0x180046947  xor     ebx, ebx
0x180046949  mov     eax, ebx
0x18004694b  add     rsp, 40h
0x18004694f  pop     r14
0x180046951  pop     rdi
0x180046952  pop     rsi
0x180046953  pop     rbp
0x180046954  pop     rbx
0x180046955  retn
0x180046957  mov     ebx, 0C0000008h
0x18004695c  mov     rcx, cs:WPP_GLOBAL_Control
0x180046963  lea     rax, WPP_GLOBAL_Control
0x18004696a  cmp     rcx, rax
0x18004696d  jz      short loc_180046949
0x18004696f  mov     eax, [rcx+2Ch]
0x180046972  test    al, 1
0x180046974  jz      short loc_180046949
0x180046976  mov     [rsp+68h+var_38], 9A2h
0x18004697e  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180046985  mov     [rsp+68h+var_40], r8
0x18004698a  mov     [rsp+68h+var_48], 0C0000008h
0x180046992  mov     rcx, [rcx+18h]
0x180046996  lea     r9, aStatus; "Status"
0x18004699d  call    WPP_SF_sDsd
0x1800469a2  jmp     short loc_180046949
0x1800469a4  mov     r9d, 9CAh
0x1800469aa  jmp     loc_1800A824E
0x1800469af  lea     rdx, aMessageblockle; "MessageBlockLength"
0x1800469b6  mov     rcx, rdi; Str1
0x1800469b9  call    wcscmp_0
0x1800469be  test    eax, eax
0x1800469c0  jnz     loc_1800A82B8
0x1800469c6  mov     ecx, [rbx+8]
0x1800469c9  mov     edx, 10008h
0x1800469ce  cmp     ecx, edx
0x1800469d0  jz      loc_1800A825A
0x1800469d6  cmp     dword ptr [rbx+0Ch], 3
0x1800469da  jnz     loc_1800A8248
0x1800469e0  jmp     loc_1800A825A
0x1800469e5  mov     r9d, 9ABh
0x1800469eb  jmp     loc_1800A8265
0x1800a8248  mov     r9d, 9EDh
0x1800a824e  mov     ebx, 0C00000BBh
0x1800a8253  mov     ecx, 0C00000BBh
0x1800a8258  jmp     short loc_1800A826F
0x1800a825a  cmp     ebp, 4
0x1800a825d  jz      short loc_1800A8288
0x1800a825f  mov     r9d, 9F4h
0x1800a8265  mov     ecx, 0C000000Dh
0x1800a826a  mov     ebx, 0C000000Dh
0x1800a826f  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a8276  lea     rdx, aStatus; "Status"
0x1800a827d  call    DebugTraceError
0x1800a8282  nop
0x1800a8283  jmp     loc_180046949
0x1800a8288  mov     eax, [rsi]
0x1800a828a  cmp     ecx, edx
0x1800a828c  jnz     short loc_1800A829E
0x1800a828e  test    al, 0Fh
0x1800a8290  jnz     short loc_1800A8296
0x1800a8292  test    eax, eax
0x1800a8294  jnz     short loc_1800A82B0
0x1800a8296  mov     r9d, 9FFh
0x1800a829c  jmp     short loc_1800A8265
0x1800a829e  cmp     eax, 1
0x1800a82a1  jz      short loc_1800A82B0
0x1800a82a3  cmp     eax, [rbx+10h]
0x1800a82a6  jz      short loc_1800A82B0
0x1800a82a8  mov     r9d, 0A06h
0x1800a82ae  jmp     short loc_1800A8265
0x1800a82b0  mov     [rbx+14h], eax
0x1800a82b3  jmp     loc_180046947
0x1800a82b8  mov     ecx, [rbx+4]
0x1800a82bb  sub     ecx, 4D535341h
0x1800a82c1  jz      short loc_1800A830A
0x1800a82c3  cmp     ecx, 0Ah
0x1800a82c6  jz      short loc_1800A82DA
0x1800a82c8  mov     ebx, 0C0000008h
0x1800a82cd  mov     r9d, 0A2Eh
0x1800a82d3  mov     ecx, 0C0000008h
0x1800a82d8  jmp     short loc_1800A826F
0x1800a82da  mov     r9d, ebp
0x1800a82dd  mov     r8, rsi
0x1800a82e0  mov     rdx, rdi
0x1800a82e3  mov     rcx, r14
0x1800a82e6  call    MSCryptSetKeyProperty
0x1800a82eb  mov     ebx, eax
0x1800a82ed  test    eax, eax
0x1800a82ef  jns     loc_180046949
0x1800a82f5  mov     r9d, 0A27h
0x1800a82fb  jmp     short loc_1800A8303
0x1800a82fd  mov     r9d, 0A1Ah
0x1800a8303  mov     ecx, eax
0x1800a8305  jmp     loc_1800A826F
0x1800a830a  mov     r9d, ebp
0x1800a830d  mov     r8, rsi
0x1800a8310  mov     rdx, rdi
0x1800a8313  mov     rcx, r14
0x1800a8316  call    MSCryptSetAlgProperty
0x1800a831b  mov     ebx, eax
0x1800a831d  test    eax, eax
0x1800a831f  jns     loc_180046949
0x1800a8325  jmp     short loc_1800A82FD
```
