# RangeCheck

- ea: `0x1800038ac`
- end: `0x180003a2e`
- name: `RangeCheck`
- size: `386`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180001810`
- `0x180001a44`

## callees

- `0x180003520`
- `0x180003878`
- `0x1800038ac`
- `0x180005270`
- `0x180005ff0`

## pseudocode

```c
__int64 __fastcall RangeCheck(__int64 a1, unsigned int a2)
{
  DWORD_PTR v4; // rcx
  unsigned int v5; // eax
  unsigned int v6; // edx
  unsigned int v7; // esi
  int v9; // eax
  _OWORD v10[3]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v11; // [rsp+50h] [rbp-18h]

  v4 = *(_QWORD *)(a1 + 256);
  memset(v10, 0, sizeof(v10));
  v11 = 0;
  midiSeqMessage(v4, 0xBu, (__int64)v10, 0);
  v5 = CnvtTimeFromSeq(a1, DWORD1(v10[0]), v10);
  v6 = *(_DWORD *)(a1 + 344);
  v7 = v5;
  if ( !v6 )
    return a2 <= v5;
  if ( v6 != 4 && v6 != 5 && v6 != 6 && v6 != 7 )
  {
    if ( v6 == 16385 )
      return a2 <= v5;
    return 1;
  }
  v9 = FPSDisplay(v6);
  return HIBYTE(a2) < v9
      && BYTE2(a2) < 0x3Cu
      && BYTE1(a2) < 0x3Cu
      && (unsigned __int8)a2 <= 0x18u
      && (v9 / 2 + 1000 * (HIBYTE(a2) + v9 * (BYTE2(a2) + 60 * (BYTE1(a2) + 60 * (unsigned int)(unsigned __int8)a2))))
       / v9 <= (v9 / 2 + 1000 * (HIBYTE(v7) + v9 * (BYTE2(v7) + 60 * (BYTE1(v7) + 60 * (unsigned __int8)v7))))
             / (unsigned int)v9;
}

```

## disassembly

```asm
0x1800038ac  mov     r11, rsp
0x1800038af  mov     [r11+18h], rbx
0x1800038b3  mov     [r11+20h], rsi
0x1800038b7  mov     [rsp+arg_8], edx
0x1800038bb  push    rdi
0x1800038bc  sub     rsp, 60h
0x1800038c0  mov     rax, cs:__security_cookie
0x1800038c7  xor     rax, rsp
0x1800038ca  mov     [rsp+68h+var_10], rax
0x1800038cf  xorps   xmm0, xmm0
0x1800038d2  lea     r8, [r11-48h]
0x1800038d6  xor     eax, eax
0x1800038d8  mov     edi, edx
0x1800038da  mov     rbx, rcx
0x1800038dd  xor     r9d, r9d
0x1800038e0  mov     rcx, [rcx+100h]; dwUser
0x1800038e7  movups  [rsp+68h+var_48], xmm0
0x1800038ec  lea     edx, [rax+0Bh]
0x1800038ef  movups  [rsp+68h+var_38], xmm0
0x1800038f4  movups  [rsp+68h+var_28], xmm0
0x1800038f9  mov     [r11-18h], rax
0x1800038fd  call    midiSeqMessage
0x180003902  mov     edx, dword ptr [rsp+68h+var_48+4]
0x180003906  lea     r8, [rsp+68h+var_48]
0x18000390b  mov     rcx, rbx
0x18000390e  call    CnvtTimeFromSeq
0x180003913  mov     edx, [rbx+158h]
0x180003919  mov     esi, eax
0x18000391b  mov     ecx, edx
0x18000391d  test    edx, edx
0x18000391f  jz      short loc_180003941
0x180003921  sub     ecx, 4
0x180003924  jz      short loc_180003967
0x180003926  sub     ecx, 1
0x180003929  jz      short loc_180003967
0x18000392b  sub     ecx, 1
0x18000392e  jz      short loc_180003967
0x180003930  sub     ecx, 1
0x180003933  jz      short loc_180003967
0x180003935  cmp     ecx, 3FFAh
0x18000393b  jnz     loc_180003A1D
0x180003941  xor     eax, eax
0x180003943  cmp     edi, esi
0x180003945  setbe   al
0x180003948  mov     rcx, [rsp+68h+var_10]
0x18000394d  xor     rcx, rsp; StackCookie
0x180003950  call    __security_check_cookie
0x180003955  lea     r11, [rsp+68h+var_8]
0x18000395a  mov     rbx, [r11+20h]
0x18000395e  mov     rsi, [r11+28h]
0x180003962  mov     rsp, r11
0x180003965  pop     rdi
0x180003966  retn
0x180003967  mov     ecx, edx
0x180003969  call    FPSDisplay
0x18000396e  movzx   ebx, byte ptr [rsp+68h+arg_8+3]
0x180003973  mov     r11d, eax
0x180003976  cmp     ebx, eax
0x180003978  jge     loc_180003A27
0x18000397e  cmp     byte ptr [rsp+68h+arg_8+2], 3Ch ; '<'
0x180003983  jnb     loc_180003A27
0x180003989  cmp     byte ptr [rsp+68h+arg_8+1], 3Ch ; '<'
0x18000398e  jnb     loc_180003A27
0x180003994  cmp     dil, 18h
0x180003998  ja      loc_180003A27
0x18000399e  cdq
0x18000399f  movzx   ecx, sil
0x1800039a3  sub     eax, edx
0x1800039a5  mov     r8d, esi
0x1800039a8  shr     r8d, 8
0x1800039ac  mov     r9d, esi
0x1800039af  imul    edx, ecx, 3Ch ; '<'
0x1800039b2  movzx   ecx, r8b
0x1800039b6  sar     eax, 1
0x1800039b8  mov     r10d, eax
0x1800039bb  shr     r9d, 10h
0x1800039bf  shr     esi, 18h
0x1800039c2  add     edx, ecx
0x1800039c4  movzx   ecx, r9b
0x1800039c8  imul    r8d, edx, 3Ch ; '<'
0x1800039cc  xor     edx, edx
0x1800039ce  add     r8d, ecx
0x1800039d1  movzx   ecx, dil
0x1800039d5  imul    r8d, r11d
0x1800039d9  add     r8d, esi
0x1800039dc  imul    eax, r8d, 3E8h
0x1800039e3  add     eax, r10d
0x1800039e6  div     r11d
0x1800039e9  imul    edx, ecx, 3Ch ; '<'
0x1800039ec  movzx   ecx, byte ptr [rsp+68h+arg_8+1]
0x1800039f1  mov     r9d, eax
0x1800039f4  add     edx, ecx
0x1800039f6  movzx   ecx, byte ptr [rsp+68h+arg_8+2]
0x1800039fb  imul    r8d, edx, 3Ch ; '<'
0x1800039ff  xor     edx, edx
0x180003a01  add     r8d, ecx
0x180003a04  imul    r8d, r11d
0x180003a08  add     r8d, ebx
0x180003a0b  imul    eax, r8d, 3E8h
0x180003a12  add     eax, r10d
0x180003a15  div     r11d
0x180003a18  cmp     eax, r9d
0x180003a1b  ja      short loc_180003A27
0x180003a1d  mov     eax, 1
0x180003a22  jmp     loc_180003948
0x180003a27  xor     eax, eax
0x180003a29  jmp     loc_180003948
```
