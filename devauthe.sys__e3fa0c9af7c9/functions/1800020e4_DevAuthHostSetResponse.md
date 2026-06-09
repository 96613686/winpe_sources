# DevAuthHostSetResponse

- ea: `0x1800020e4`
- end: `0x180002340`
- name: `DevAuthHostSetResponse`
- size: `604`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000118c`

## callees

- `0x1800020e4`
- `0x180002444`
- `0x180002ef4`
- `0x1800035bc`
- `0x1800069c0`

## import_xrefs

- `cng!BCryptHashData` at `0x180002308`
- `cng!BCryptHashData` at `0x180002308`

## pseudocode

```c
__int64 __fastcall DevAuthHostSetResponse(__int64 a1, __int64 a2, unsigned int a3)
{
  char v4; // r9
  ULONG v5; // ebp
  unsigned int v6; // ecx
  __int64 v7; // rsi
  unsigned int v8; // edi
  unsigned int v9; // ecx
  __int64 v10; // rcx
  __int64 v11; // rcx
  int v12; // ecx
  unsigned int v13; // r14d
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  __int64 v16; // rcx
  int v17; // eax
  int v19; // [rsp+70h] [rbp+8h] BYREF

  if ( a1 )
  {
    if ( a2 )
    {
      v4 = 5;
      if ( a3 >= 5 && (*(_BYTE *)a2 != 0xC1 || *(_WORD *)(a2 + 1) == 256) )
      {
        v5 = a3 - 5;
        if ( a3 - 5 == (unsigned __int16)__ROR2__(*(_WORD *)(a2 + 3), 8) )
        {
          v6 = *(unsigned __int8 *)(a1 + 1);
          v7 = a2 + 5;
          v8 = 0;
          if ( v6 <= 6 )
          {
            if ( v6 == 6 )
            {
              v4 = 7;
            }
            else
            {
              v9 = v6 - 1;
              if ( v9 )
              {
                v10 = v9 - 1;
                if ( (_DWORD)v10 )
                {
                  v11 = (unsigned int)(v10 - 1);
                  if ( (_DWORD)v11 )
                  {
                    v12 = v11 - 1;
                    if ( v12 )
                    {
                      if ( v12 == 1 )
                      {
                        v8 = 1;
                        v4 = ((*(_BYTE *)(a1 + 80) & 1) == 0) + 6;
                        goto LABEL_37;
                      }
LABEL_41:
                      *(_BYTE *)a1 = 3;
                      return v8;
                    }
                    goto LABEL_36;
                  }
                  LODWORD(v11) = 3;
                  if ( !(unsigned int)DevAuthValidateHeader(v11, a2 + 5, v5) )
                    goto LABEL_41;
                  v13 = v5 - 4;
                  if ( v5 - 4 <= 0x400 )
                    memmove((void *)(a1 + 126), (const void *)(v7 + 4), v13);
                  *(_DWORD *)(a1 + 1152) = v13;
                  v19 = 0;
                  if ( !(unsigned int)DevAuthParseCert(
                                        a1 + 126,
                                        v13,
                                        (_QWORD *)(a1 + 1160),
                                        &v19,
                                        (_DWORD *)(a1 + 1216)) )
                    goto LABEL_41;
                  v8 = 1;
                  v4 = ((*(_BYTE *)(a1 + 80) & 1) == 0) + 4;
LABEL_37:
                  *(_BYTE *)(a1 + 1) = v4;
                  if ( v5 )
                  {
                    if ( BCryptHashData(*(BCRYPT_HASH_HANDLE *)(*(_QWORD *)(a1 + 1224) + 8LL), (PUCHAR)v7, v5, 0) < 0 )
                      v8 = 0;
                  }
                  *(_DWORD *)(a1 + 8) = 0;
                  if ( v8 )
                    return v8;
                  goto LABEL_41;
                }
                LODWORD(v10) = 2;
                if ( !(unsigned int)DevAuthValidateHeader(v10, a2 + 5, v5) )
                  goto LABEL_41;
                *(_OWORD *)(a1 + 48) = *(_OWORD *)(v7 + 4);
                *(_OWORD *)(a1 + 64) = *(_OWORD *)(v7 + 20);
                if ( _byteswap_ulong(*(_DWORD *)(v7 + 36)) != *(_DWORD *)(a1 + 12) )
                {
                  *(_DWORD *)(a1 + 4) = 0;
                  *(_DWORD *)(a1 + 12) = _byteswap_ulong(*(_DWORD *)(v7 + 36));
                }
                *(_BYTE *)(a1 + 80) = *(_BYTE *)(v7 + 40);
                *(_WORD *)(a1 + 124) = __ROR2__(*(_WORD *)(v7 + 41), 8);
                *(_OWORD *)(a1 + 81) = *(_OWORD *)(v7 + 44);
                *(_DWORD *)(a1 + 97) = *(_DWORD *)(v7 + 60);
                *(_OWORD *)(a1 + 101) = *(_OWORD *)(v7 + 64);
                *(_DWORD *)(a1 + 120) = _byteswap_ulong(*(_DWORD *)(v7 + 80));
                v4 = *(_DWORD *)(a1 + 4) != 0 ? 7 : 3;
              }
              else
              {
                v4 = 2;
              }
            }
LABEL_36:
            v8 = 1;
            goto LABEL_37;
          }
          v14 = v6 - 7;
          if ( !v14 )
          {
            v4 = 8;
            goto LABEL_36;
          }
          v15 = v14 - 1;
          if ( v15 )
          {
            v16 = v15 - 3;
            if ( !(_DWORD)v16 )
            {
              v4 = 12;
              goto LABEL_36;
            }
            if ( (_DWORD)v16 != 1 )
              goto LABEL_41;
            LOBYTE(v16) = 12;
            v17 = DevAuthValidateHeader(v16, a2 + 5, v5);
          }
          else
          {
            v17 = ProcessDeviceFinished(a1, a2 + 5, v5);
          }
          if ( !v17 )
            goto LABEL_41;
          v8 = 1;
          *(_BYTE *)a1 = 2;
          v4 = 1;
          goto LABEL_37;
        }
      }
    }
  }
  *(_BYTE *)a1 = 3;
  return 0;
}

```

## disassembly

```asm
0x1800020e4  push    rbx
0x1800020e6  push    rbp
0x1800020e7  push    rsi
0x1800020e8  push    rdi
0x1800020e9  push    r14
0x1800020eb  push    r15
0x1800020ed  sub     rsp, 38h
0x1800020f1  mov     rbx, rcx
0x1800020f4  test    rcx, rcx
0x1800020f7  jz      loc_18000232D
0x1800020fd  test    rdx, rdx
0x180002100  jz      loc_18000232D
0x180002106  mov     r9d, 5
0x18000210c  cmp     r8d, r9d
0x18000210f  jb      loc_18000232D
0x180002115  cmp     byte ptr [rdx], 0C1h
0x180002118  jnz     short loc_180002129
0x18000211a  mov     eax, 100h
0x18000211f  cmp     [rdx+1], ax
0x180002123  jnz     loc_18000232D
0x180002129  movzx   eax, word ptr [rdx+3]
0x18000212d  lea     ebp, [r8-5]
0x180002131  ror     ax, 8
0x180002135  movzx   eax, ax
0x180002138  cmp     ebp, eax
0x18000213a  jnz     loc_18000232D
0x180002140  movzx   ecx, byte ptr [rcx+1]
0x180002144  lea     rsi, [rdx+5]
0x180002148  xor     edi, edi
0x18000214a  cmp     ecx, 6
0x18000214d  ja      loc_18000229D
0x180002153  jz      loc_180002298
0x180002159  sub     ecx, 1
0x18000215c  jz      loc_180002293
0x180002162  sub     ecx, 1
0x180002165  jz      loc_180002218
0x18000216b  sub     ecx, 1
0x18000216e  jz      short loc_180002197
0x180002170  sub     ecx, 1
0x180002173  jz      loc_1800022E7
0x180002179  cmp     ecx, 1
0x18000217c  jnz     loc_180002326
0x180002182  mov     r9b, [rbx+50h]
0x180002186  mov     edi, ecx
0x180002188  not     r9b
0x18000218b  and     r9b, dil
0x18000218e  add     r9b, 6
0x180002192  jmp     loc_1800022EC
0x180002197  mov     r8d, ebp
0x18000219a  mov     rdx, rsi
0x18000219d  mov     cl, 3
0x18000219f  call    DevAuthValidateHeader
0x1800021a4  test    eax, eax
0x1800021a6  jz      loc_180002326
0x1800021ac  lea     r14d, [rbp-4]
0x1800021b0  cmp     r14d, 400h
0x1800021b7  ja      short loc_1800021C9
0x1800021b9  mov     r8d, r14d; Size
0x1800021bc  lea     rdx, [rsi+4]; Src
0x1800021c0  lea     rcx, [rbx+7Eh]; void *
0x1800021c4  call    memmove
0x1800021c9  lea     rax, [rbx+4C0h]
0x1800021d0  mov     [rbx+480h], r14d
0x1800021d7  lea     r8, [rbx+488h]
0x1800021de  mov     [rsp+68h+var_48], rax
0x1800021e3  lea     r9, [rsp+68h+arg_0]
0x1800021e8  mov     [rsp+68h+arg_0], edi
0x1800021ec  mov     edx, r14d
0x1800021ef  lea     rcx, [rbx+7Eh]
0x1800021f3  call    DevAuthParseCert
0x1800021f8  test    eax, eax
0x1800021fa  jz      loc_180002326
0x180002200  mov     r9b, [rbx+50h]
0x180002204  mov     edi, 1
0x180002209  not     r9b
0x18000220c  and     r9b, dil
0x18000220f  add     r9b, 4
0x180002213  jmp     loc_1800022EC
0x180002218  mov     r8d, ebp
0x18000221b  mov     rdx, rsi
0x18000221e  mov     cl, 2
0x180002220  call    DevAuthValidateHeader
0x180002225  test    eax, eax
0x180002227  jz      loc_180002326
0x18000222d  movups  xmm0, xmmword ptr [rsi+4]
0x180002231  movups  xmmword ptr [rbx+30h], xmm0
0x180002235  movups  xmm1, xmmword ptr [rsi+14h]
0x180002239  movups  xmmword ptr [rbx+40h], xmm1
0x18000223d  mov     eax, [rsi+24h]
0x180002240  bswap   eax
0x180002242  cmp     eax, [rbx+0Ch]
0x180002245  jz      short loc_180002252
0x180002247  mov     [rbx+4], edi
0x18000224a  mov     eax, [rsi+24h]
0x18000224d  bswap   eax
0x18000224f  mov     [rbx+0Ch], eax
0x180002252  mov     al, [rsi+28h]
0x180002255  mov     [rbx+50h], al
0x180002258  movzx   eax, word ptr [rsi+29h]
0x18000225c  ror     ax, 8
0x180002260  mov     [rbx+7Ch], ax
0x180002264  movups  xmm0, xmmword ptr [rsi+2Ch]
0x180002268  movups  xmmword ptr [rbx+51h], xmm0
0x18000226c  mov     eax, [rsi+3Ch]
0x18000226f  mov     [rbx+61h], eax
0x180002272  movups  xmm0, xmmword ptr [rsi+40h]
0x180002276  movdqu  xmmword ptr [rbx+65h], xmm0
0x18000227b  mov     eax, [rsi+50h]
0x18000227e  bswap   eax
0x180002280  mov     [rbx+78h], eax
0x180002283  mov     eax, [rbx+4]
0x180002286  neg     eax
0x180002288  sbb     cl, cl
0x18000228a  and     cl, 4
0x18000228d  lea     r9d, [rcx+3]
0x180002291  jmp     short loc_1800022E7
0x180002293  mov     r9b, 2
0x180002296  jmp     short loc_1800022E7
0x180002298  mov     r9b, 7
0x18000229b  jmp     short loc_1800022E7
0x18000229d  sub     ecx, 7
0x1800022a0  jz      short loc_1800022E4
0x1800022a2  sub     ecx, 1
0x1800022a5  jz      short loc_1800022D4
0x1800022a7  sub     ecx, 3
0x1800022aa  jz      short loc_1800022CF
0x1800022ac  cmp     ecx, 1
0x1800022af  jnz     short loc_180002326
0x1800022b1  mov     r8d, ebp
0x1800022b4  mov     rdx, rsi
0x1800022b7  mov     cl, 0Ch
0x1800022b9  call    DevAuthValidateHeader
0x1800022be  test    eax, eax
0x1800022c0  jz      short loc_180002326
0x1800022c2  mov     edi, 1
0x1800022c7  mov     byte ptr [rbx], 2
0x1800022ca  mov     r9b, dil
0x1800022cd  jmp     short loc_1800022EC
0x1800022cf  mov     r9b, 0Ch
0x1800022d2  jmp     short loc_1800022E7
0x1800022d4  mov     r8d, ebp
0x1800022d7  mov     rdx, rsi
0x1800022da  mov     rcx, rbx
0x1800022dd  call    _ProcessDeviceFinished
0x1800022e2  jmp     short loc_1800022BE
0x1800022e4  mov     r9b, 8
0x1800022e7  mov     edi, 1
0x1800022ec  mov     [rbx+1], r9b
0x1800022f0  test    ebp, ebp
0x1800022f2  jz      short loc_18000231B
0x1800022f4  mov     rcx, [rbx+4C8h]
0x1800022fb  xor     r9d, r9d; dwFlags
0x1800022fe  mov     r8d, ebp; cbInput
0x180002301  mov     rdx, rsi; pbInput
0x180002304  mov     rcx, [rcx+8]; hHash
0x180002308  call    cs:__imp_BCryptHashData
0x18000230f  nop     dword ptr [rax+rax+00h]
0x180002314  xor     ecx, ecx
0x180002316  test    eax, eax
0x180002318  cmovs   edi, ecx
0x18000231b  mov     dword ptr [rbx+8], 0
0x180002322  test    edi, edi
0x180002324  jnz     short loc_180002329
0x180002326  mov     byte ptr [rbx], 3
0x180002329  mov     eax, edi
0x18000232b  jmp     short loc_180002332
0x18000232d  mov     byte ptr [rcx], 3
0x180002330  xor     eax, eax
0x180002332  add     rsp, 38h
0x180002336  pop     r15
0x180002338  pop     r14
0x18000233a  pop     rdi
0x18000233b  pop     rsi
0x18000233c  pop     rbp
0x18000233d  pop     rbx
0x18000233e  retn
```
