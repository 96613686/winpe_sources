# SslpEnumCipherSuites

- ea: `0x18001de24`
- end: `0x18001e00b`
- name: `SslpEnumCipherSuites`
- size: `487`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001eae0`

## callees

- `0x180003ef0`
- `0x180007940`
- `0x18000b654`
- `0x180010280`
- `0x180012c68`
- `0x18001de24`
- `0x180023cf8`
- `0x180025660`

## string_xrefs

- `0x18001de99`: `onecore\ds\security\cryptoapi\ncrypt\schannel\enum.c`
- `0x18001df00`: `onecore\ds\security\cryptoapi\ncrypt\schannel\enum.c`
- `0x18001dfe8`: `onecore\ds\security\cryptoapi\ncrypt\schannel\enum.c`

## pseudocode

```c
__int64 __fastcall SslpEnumCipherSuites(__int64 a1, int a2, __int64 *a3, _QWORD *a4)
{
  _DWORD *v4; // rbx
  _DWORD *v8; // rax
  __int64 v9; // rcx
  __int64 v10; // r9
  int v11; // esi
  int v12; // ecx
  int v13; // r9d
  int v14; // eax
  unsigned int v15; // edi
  unsigned int v16; // eax
  __int64 v17; // r9
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // r8
  __int64 v21; // rcx
  _OWORD *v22; // rdx
  _OWORD *v23; // rax
  __int128 v24; // xmm1

  v4 = (_DWORD *)*a4;
  if ( *a4 )
  {
    if ( MSCryptLookupMemoryBuffer(a1, *a4) )
    {
      v16 = v4[9];
      if ( v16 <= 0xE1 )
      {
        v11 = 0;
        if ( v4[8] <= v16 )
          goto LABEL_10;
      }
      v10 = 987;
    }
    else
    {
      v10 = 979;
    }
    v9 = 2148073511LL;
    goto LABEL_25;
  }
  v8 = (_DWORD *)SafeAllocaAllocateFromHeap(181840);
  v4 = v8;
  if ( !v8 )
  {
    v9 = 2148073486LL;
    v10 = 946;
LABEL_25:
    v15 = v9;
    DebugTraceError(v9, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\enum.c", v10);
    return v15;
  }
  v11 = 1;
  memset(v8, 0, 0x2C650u);
  v14 = BuildCipherList(v12, a2, (int)v4 + 40, v13, (__int64)(v4 + 9));
  v15 = v14;
  if ( v14 < 0 )
  {
    DebugTraceError((unsigned int)v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\enum.c", 965);
LABEL_22:
    MSCryptFree(v4);
    return v15;
  }
LABEL_10:
  if ( v4[8] == v4[9] )
  {
    v15 = -2146893782;
    v17 = 1001;
    v18 = 2148073514LL;
LABEL_12:
    DebugTraceError(v18, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\enum.c", v17);
    goto LABEL_20;
  }
  v19 = SafeAllocaAllocateFromHeap(676);
  v20 = v19;
  if ( !v19 )
  {
    v18 = 2148073486LL;
    v17 = 1015;
    v15 = -2146893810;
    goto LABEL_12;
  }
  v21 = 5;
  v22 = (_OWORD *)v19;
  v23 = &v4[202 * v4[8] + 11];
  do
  {
    *v22 = *v23;
    v22[1] = v23[1];
    v22[2] = v23[2];
    v22[3] = v23[3];
    v22[4] = v23[4];
    v22[5] = v23[5];
    v22[6] = v23[6];
    v24 = v23[7];
    v23 += 8;
    v22[7] = v24;
    v22 += 8;
    --v21;
  }
  while ( v21 );
  *v22 = *v23;
  v22[1] = v23[1];
  *((_DWORD *)v22 + 8) = *((_DWORD *)v23 + 8);
  ++v4[8];
  *a3 = v20;
  if ( v11 )
  {
    *((_QWORD *)v4 + 1) = v4;
    MSCryptAddMemoryBuffer(0, v4, v20, 128);
    *a4 = v4;
    v4 = 0;
  }
  v15 = 0;
LABEL_20:
  if ( v11 && v4 )
    goto LABEL_22;
  return v15;
}

```

## disassembly

```asm
0x18001de24  push    rbx
0x18001de26  push    rsi
0x18001de27  push    rdi
0x18001de28  push    r14
0x18001de2a  push    r15
0x18001de2c  sub     rsp, 30h
0x18001de30  mov     rbx, [r9]
0x18001de33  mov     r14, r9
0x18001de36  mov     r15, r8
0x18001de39  mov     rdi, rdx
0x18001de3c  test    rbx, rbx
0x18001de3f  jnz     short loc_18001DEB3
0x18001de41  mov     ecx, 2C650h
0x18001de46  call    SafeAllocaAllocateFromHeap
0x18001de4b  mov     rbx, rax
0x18001de4e  test    rax, rax
0x18001de51  jnz     short loc_18001DE63
0x18001de53  mov     ecx, 8009000Eh
0x18001de58  mov     r9d, 3B2h
0x18001de5e  jmp     loc_18001DFE8
0x18001de63  xor     edx, edx; Val
0x18001de65  mov     r8d, 2C650h; Size
0x18001de6b  mov     rcx, rbx; void *
0x18001de6e  mov     esi, 1
0x18001de73  call    memset
0x18001de78  lea     rax, [rbx+24h]
0x18001de7c  mov     rdx, rdi
0x18001de7f  lea     r8, [rbx+28h]
0x18001de83  mov     [rsp+58h+var_38], rax
0x18001de88  call    BuildCipherList
0x18001de8d  mov     edi, eax
0x18001de8f  test    eax, eax
0x18001de91  jns     short loc_18001DEE4
0x18001de93  mov     r9d, 3C5h
0x18001de99  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001dea0  lea     rdx, aStatus; "Status"
0x18001dea7  mov     ecx, eax
0x18001dea9  call    DebugTraceError
0x18001deae  jmp     loc_18001DFD3
0x18001deb3  mov     rdx, rbx
0x18001deb6  call    MSCryptLookupMemoryBuffer
0x18001debb  test    rax, rax
0x18001debe  jnz     short loc_18001DECB
0x18001dec0  mov     r9d, 3D3h
0x18001dec6  jmp     loc_18001DFE3
0x18001decb  mov     eax, [rbx+24h]
0x18001dece  cmp     eax, 0E1h
0x18001ded3  ja      loc_18001DFDD
0x18001ded9  xor     esi, esi
0x18001dedb  cmp     [rbx+20h], eax
0x18001dede  ja      loc_18001DFDD
0x18001dee4  mov     eax, [rbx+24h]
0x18001dee7  cmp     [rbx+20h], eax
0x18001deea  jnz     short loc_18001DF11
0x18001deec  mov     edi, 8009002Ah
0x18001def1  mov     r9d, 3E9h
0x18001def7  mov     ecx, edi
0x18001def9  lea     rdx, aStatus; "Status"
0x18001df00  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001df07  call    DebugTraceError
0x18001df0c  jmp     loc_18001DFCA
0x18001df11  mov     ecx, 2A4h
0x18001df16  call    SafeAllocaAllocateFromHeap
0x18001df1b  mov     r8, rax
0x18001df1e  test    rax, rax
0x18001df21  jnz     short loc_18001DF32
0x18001df23  mov     ecx, 8009000Eh
0x18001df28  mov     r9d, 3F7h
0x18001df2e  mov     edi, ecx
0x18001df30  jmp     short loc_18001DEF9
0x18001df32  mov     eax, [rbx+20h]
0x18001df35  mov     ecx, 5
0x18001df3a  imul    rax, 328h
0x18001df41  mov     rdx, r8
0x18001df44  lea     r9d, [rcx+7Bh]
0x18001df48  add     rax, 2Ch ; ','
0x18001df4c  add     rax, rbx
0x18001df4f  movups  xmm0, xmmword ptr [rax]
0x18001df52  movups  xmmword ptr [rdx], xmm0
0x18001df55  movups  xmm1, xmmword ptr [rax+10h]
0x18001df59  movups  xmmword ptr [rdx+10h], xmm1
0x18001df5d  movups  xmm0, xmmword ptr [rax+20h]
0x18001df61  movups  xmmword ptr [rdx+20h], xmm0
0x18001df65  movups  xmm1, xmmword ptr [rax+30h]
0x18001df69  movups  xmmword ptr [rdx+30h], xmm1
0x18001df6d  movups  xmm0, xmmword ptr [rax+40h]
0x18001df71  movups  xmmword ptr [rdx+40h], xmm0
0x18001df75  movups  xmm1, xmmword ptr [rax+50h]
0x18001df79  movups  xmmword ptr [rdx+50h], xmm1
0x18001df7d  movups  xmm0, xmmword ptr [rax+60h]
0x18001df81  movups  xmmword ptr [rdx+60h], xmm0
0x18001df85  movups  xmm1, xmmword ptr [rax+70h]
0x18001df89  add     rax, r9
0x18001df8c  movups  xmmword ptr [rdx+70h], xmm1
0x18001df90  add     rdx, r9
0x18001df93  sub     rcx, 1
0x18001df97  jnz     short loc_18001DF4F
0x18001df99  movups  xmm0, xmmword ptr [rax]
0x18001df9c  movups  xmmword ptr [rdx], xmm0
0x18001df9f  movups  xmm1, xmmword ptr [rax+10h]
0x18001dfa3  movups  xmmword ptr [rdx+10h], xmm1
0x18001dfa7  mov     eax, [rax+20h]
0x18001dfaa  mov     [rdx+20h], eax
0x18001dfad  inc     dword ptr [rbx+20h]
0x18001dfb0  mov     [r15], r8
0x18001dfb3  test    esi, esi
0x18001dfb5  jz      short loc_18001DFC8
0x18001dfb7  mov     rdx, rbx
0x18001dfba  mov     [rbx+8], rbx
0x18001dfbe  call    MSCryptAddMemoryBuffer
0x18001dfc3  mov     [r14], rbx
0x18001dfc6  xor     ebx, ebx
0x18001dfc8  xor     edi, edi
0x18001dfca  test    esi, esi
0x18001dfcc  jz      short loc_18001DFFD
0x18001dfce  test    rbx, rbx
0x18001dfd1  jz      short loc_18001DFFD
0x18001dfd3  mov     rcx, rbx
0x18001dfd6  call    MSCryptFree
0x18001dfdb  jmp     short loc_18001DFFD
0x18001dfdd  mov     r9d, 3DBh
0x18001dfe3  mov     ecx, 80090027h
0x18001dfe8  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001dfef  mov     edi, ecx
0x18001dff1  lea     rdx, aStatus; "Status"
0x18001dff8  call    DebugTraceError
0x18001dffd  mov     eax, edi
0x18001dfff  add     rsp, 30h
0x18001e003  pop     r15
0x18001e005  pop     r14
0x18001e007  pop     rdi
0x18001e008  pop     rsi
0x18001e009  pop     rbx
0x18001e00a  retn
```
