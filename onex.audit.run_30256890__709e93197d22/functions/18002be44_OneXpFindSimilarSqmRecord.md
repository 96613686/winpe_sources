# OneXpFindSimilarSqmRecord

- ea: `0x18002be44`
- end: `0x18002bf8f`
- name: `OneXpFindSimilarSqmRecord`
- size: `331`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001f690`

## callees

- `0x180005440`
- `0x180012040`
- `0x1800214f0`
- `0x18002be44`

## import_xrefs

- `MobileNetworking!ReleaseReadLock` at `0x18002bf1f`
- `MobileNetworking!ReleaseReadLock` at `0x18002bf1f`
- `MobileNetworking!AcquireReadLock` at `0x18002be93`
- `MobileNetworking!AcquireReadLock` at `0x18002be93`

## pseudocode

```c
__int64 __fastcall OneXpFindSimilarSqmRecord(__int64 a1)
{
  unsigned __int8 v1; // di
  int v2; // esi
  int v3; // ebx
  int v5; // ebp
  __int64 v6; // r8
  __int64 v7; // r9
  __int128 v8; // xmm1
  __int64 v9; // r8
  _QWORD *v10; // rcx
  __int128 v12; // [rsp+20h] [rbp-58h] BYREF
  _OWORD v13[4]; // [rsp+30h] [rbp-48h] BYREF

  v1 = 0;
  v2 = 0;
  v3 = 0;
  v5 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 87, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids);
  AcquireReadLock(qword_18003DE28);
  v6 = qword_18003DE18;
  v7 = 1;
  while ( (__int64 *)v6 != &qword_18003DE18 )
  {
    v8 = *(_OWORD *)(v6 + 16);
    v12 = *(_OWORD *)(a1 + 16);
    v13[0] = v8;
    if ( !(unsigned int)((__int64 (__fastcall *)(_OWORD *, __int128 *, __int64, __int64))AreDifferentEapTypes)(
                          v13,
                          &v12,
                          v6,
                          v7) )
      v2 = v7;
    if ( ((*(_DWORD *)(a1 + 52) ^ *(_DWORD *)(v9 + 52)) & 0x3FE) == 0 )
      v5 = v7;
    if ( *(_DWORD *)(v9 + 32) == *(_DWORD *)(a1 + 32) && *(_DWORD *)(v9 + 36) == *(_DWORD *)(a1 + 36) )
      v3 = v7;
    if ( v2 && v3 && v5 )
    {
      v1 = v7;
      break;
    }
    v6 = *(_QWORD *)v9;
  }
  ReleaseReadLock(qword_18003DE28);
  if ( v1 )
    goto LABEL_22;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v1;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 88, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids);
LABEL_22:
    v10 = WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 17) & 0x800) != 0 )
    WPP_SF_D(v10[7], 89, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids, 0);
  return v1;
}

```

## disassembly

```asm
0x18002be44  push    rbx
0x18002be46  push    rbp
0x18002be47  push    rsi
0x18002be48  push    rdi
0x18002be49  push    r14
0x18002be4b  push    r15
0x18002be4d  sub     rsp, 48h
0x18002be51  xor     dil, dil
0x18002be54  xor     esi, esi
0x18002be56  xor     ebx, ebx
0x18002be58  mov     r14, rcx
0x18002be5b  xor     ebp, ebp
0x18002be5d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002be64  lea     r15, WPP_GLOBAL_Control
0x18002be6b  cmp     rcx, r15
0x18002be6e  jz      short loc_18002BE8C
0x18002be70  test    dword ptr [rcx+44h], 800h
0x18002be77  jz      short loc_18002BE8C
0x18002be79  mov     rcx, [rcx+38h]
0x18002be7d  lea     edx, [rsi+57h]
0x18002be80  lea     r8, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids
0x18002be87  call    WPP_SF_
0x18002be8c  lea     rcx, qword_18003DE28
0x18002be93  call    cs:__imp_AcquireReadLock
0x18002be99  mov     r8, cs:qword_18003DE18
0x18002bea0  mov     r9d, 1
0x18002bea6  lea     rax, qword_18003DE18
0x18002bead  cmp     r8, rax
0x18002beb0  jz      short loc_18002BF18
0x18002beb2  movups  xmm0, xmmword ptr [r14+10h]
0x18002beb7  lea     rdx, [rsp+78h+var_58]
0x18002bebc  movups  xmm1, xmmword ptr [r8+10h]
0x18002bec1  lea     rcx, [rsp+78h+var_48]
0x18002bec6  movdqu  [rsp+78h+var_58], xmm0
0x18002becc  movdqu  [rsp+78h+var_48], xmm1
0x18002bed2  call    AreDifferentEapTypes
0x18002bed7  test    eax, eax
0x18002bed9  mov     eax, [r8+34h]
0x18002bedd  cmovz   esi, r9d
0x18002bee1  xor     eax, [r14+34h]
0x18002bee5  test    eax, 3FEh
0x18002beea  mov     eax, [r14+20h]
0x18002beee  cmovz   ebp, r9d
0x18002bef2  cmp     [r8+20h], eax
0x18002bef6  jnz     short loc_18002BF04
0x18002bef8  mov     eax, [r14+24h]
0x18002befc  cmp     [r8+24h], eax
0x18002bf00  cmovz   ebx, r9d
0x18002bf04  test    esi, esi
0x18002bf06  jz      short loc_18002BF10
0x18002bf08  test    ebx, ebx
0x18002bf0a  jz      short loc_18002BF10
0x18002bf0c  test    ebp, ebp
0x18002bf0e  jnz     short loc_18002BF15
0x18002bf10  mov     r8, [r8]
0x18002bf13  jmp     short loc_18002BEA6
0x18002bf15  mov     dil, r9b
0x18002bf18  lea     rcx, qword_18003DE28
0x18002bf1f  call    cs:__imp_ReleaseReadLock
0x18002bf25  test    dil, dil
0x18002bf28  jnz     short loc_18002BF51
0x18002bf2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bf31  cmp     rcx, r15
0x18002bf34  jz      short loc_18002BF7E
0x18002bf36  test    byte ptr [rcx+44h], 4
0x18002bf3a  jz      short loc_18002BF58
0x18002bf3c  mov     rcx, [rcx+38h]
0x18002bf40  lea     r8, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids
0x18002bf47  mov     edx, 58h ; 'X'
0x18002bf4c  call    WPP_SF_
0x18002bf51  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bf58  cmp     rcx, r15
0x18002bf5b  jz      short loc_18002BF7E
0x18002bf5d  test    dword ptr [rcx+44h], 800h
0x18002bf64  jz      short loc_18002BF7E
0x18002bf66  mov     rcx, [rcx+38h]
0x18002bf6a  lea     r8, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids
0x18002bf71  mov     edx, 59h ; 'Y'
0x18002bf76  xor     r9d, r9d
0x18002bf79  call    WPP_SF_D
0x18002bf7e  movzx   eax, dil
0x18002bf82  add     rsp, 48h
0x18002bf86  pop     r15
0x18002bf88  pop     r14
0x18002bf8a  pop     rdi
0x18002bf8b  pop     rsi
0x18002bf8c  pop     rbp
0x18002bf8d  pop     rbx
0x18002bf8e  retn
```
