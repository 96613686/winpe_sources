# FIPfOpenAttemptsRundownStart

- ea: `0x140015d3c`
- end: `0x140016065`
- name: `FIPfOpenAttemptsRundownStart`
- size: `809`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: ``

## callers

- `0x140010cd0`
- `0x140015a48`
- `0x14001606c`

## callees

- `0x140001c00`
- `0x140001da0`
- `0x140001f20`
- `0x140003920`
- `0x140003a80`
- `0x140003d80`
- `0x14000ed40`
- `0x14000ef70`
- `0x140015d3c`
- `0x140016788`
- `0x14001689c`

## import_xrefs

- `ntoskrnl!PsIsCurrentThreadPrefetching` at `0x140015f05`
- `ntoskrnl!PsIsCurrentThreadPrefetching` at `0x140015f05`

## string_xrefs

- `0x140015e22`: `\FI_AllVolumeOpenAttemptsRundown`
- `0x140015de3`: `\FI_GlobalOpenAttemptsRundown`

## pseudocode

```c
__int64 __fastcall FIPfOpenAttemptsRundownStart(__m128i *a1, int a2, __int64 a3)
{
  __int64 v3; // rdi
  int v5; // r15d
  unsigned int v6; // ebx
  __int64 *v7; // r12
  __int64 *v8; // rax
  char *m128i_i8; // r13
  volatile signed __int32 *v10; // rdi
  __int64 *v11; // r14
  __m128i v12; // xmm7
  __m128i v13; // xmm6
  unsigned int v14; // edi
  __int16 v15; // si
  __int16 v16; // ax
  __int16 v17; // r12
  __int64 v18; // rcx
  __int64 v19; // rdi
  __int64 v20; // rcx
  unsigned __int16 epi16; // [rsp+48h] [rbp-C0h]
  unsigned __int16 v23; // [rsp+4Ch] [rbp-BCh]
  __int64 v25; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v26; // [rsp+60h] [rbp-A8h]
  __int64 *m128i_i64; // [rsp+68h] [rbp-A0h]
  wchar_t *v28; // [rsp+70h] [rbp-98h]
  wchar_t *v29; // [rsp+78h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-88h]
  __int64 v31; // [rsp+88h] [rbp-80h]
  _WORD v32[32]; // [rsp+98h] [rbp-70h] BYREF
  _QWORD v33[28]; // [rsp+D8h] [rbp-30h] BYREF

  v3 = a2;
  v31 = a3;
  memset(v33, 0, 0xD8u);
  memset(v32, 0, sizeof(v32));
  v25 = 0;
  v5 = 2;
  v6 = MEMORY[0xFFFFF78000000320];
  v30 = MEMORY[0xFFFFF78000000320];
  LODWORD(v26) = MEMORY[0xFFFFF78000000004];
  if ( a1 == (__m128i *)1 )
  {
    _InterlockedIncrement((volatile signed __int32 *)&FIGlobals + v3 + 311);
    v23 = 29;
    v29 = FIPfGlobalOpenAttemptsRundown;
    v7 = &qword_140009570;
    v8 = qword_140009558;
    m128i_i8 = byte_140009568;
    v10 = &dword_14000956C;
LABEL_5:
    m128i_i64 = v8;
    v11 = &qword_140009510;
    a1 = 0;
    epi16 = v32[15];
    v28 = 0;
    goto LABEL_7;
  }
  if ( a1 == (__m128i *)2 )
  {
    _InterlockedIncrement((volatile signed __int32 *)&FIGlobals + v3 + 316);
    v29 = FIPfAllVolumeOpenAttemptsRundown;
    v7 = &qword_140009540;
    v8 = qword_140009528;
    v23 = 32;
    m128i_i8 = byte_140009538;
    v10 = &dword_14000953C;
    goto LABEL_5;
  }
  v11 = &a1[8].m128i_i64[1];
  _InterlockedIncrement(&a1[27].m128i_i32[v3 + 1]);
  _InterlockedIncrement((volatile signed __int32 *)&FIGlobals + v3 + 321);
  FILockSharedAcquire(&a1[1].m128i_u64[1]);
  v12 = a1[5];
  v13 = a1[6];
  FILockExclusiveRelease(&a1[1].m128i_u64[1]);
  v7 = &a1[16].m128i_i64[1];
  v29 = (wchar_t *)_mm_srli_si128(v13, 8).m128i_u64[0];
  m128i_i8 = a1[16].m128i_i8;
  v5 = 1;
  v28 = v29;
  epi16 = _mm_extract_epi16(v12, 7);
  v10 = &a1[16].m128i_i32[1];
  v23 = epi16;
  m128i_i64 = a1[15].m128i_i64;
LABEL_7:
  FILockExclusiveAcquire(v11);
  _InterlockedIncrement(v10);
  v14 = 0;
  if ( *(_DWORD *)v7 )
  {
    if ( PsIsCurrentThreadPrefetching() )
    {
      _InterlockedIncrement(&dword_1400098E0);
      v14 = -1073610679;
      v15 = 0;
    }
    else
    {
      v16 = *(_WORD *)v7;
      v17 = *(_WORD *)v7 + v25;
      LOWORD(v25) = v16 + v25;
      WORD1(v25) = v16;
      FIPfBlockedOpInsert(m128i_i64, m128i_i8, v33);
      FILockExclusiveRelease(v11);
      LODWORD(v33[14]) |= 8u;
      LODWORD(v33[11]) = a2;
      v33[12] = a1;
      if ( a1 )
      {
        v18 = 49;
        if ( epi16 < 0x31u )
          v18 = epi16;
        v19 = 2 * v18;
        memmove((char *)&v33[14] + 4, &v28[epi16 - (unsigned int)v18], 2 * v18);
        *(_WORD *)((char *)&v33[14] + v19 + 4) = 0;
        LODWORD(v33[14]) |= 0x10u;
      }
      v14 = FIPfBlockedOpBlock((__int64)v33, 1);
      FILockExclusiveAcquire(v11);
      FIPfBlockedOpRemove(v20, m128i_i8, v33);
      v15 = v17;
    }
  }
  else
  {
    v15 = 0;
  }
  FILockExclusiveRelease(v11);
  if ( v15 )
    FIPfConflictTelemetryAccumulate(
      (_DWORD)v29,
      v23,
      v5,
      a2,
      (((_DWORD)v26 * HIDWORD(v30)) << 8) + (((unsigned int)v26 * (unsigned __int64)v6) >> 24),
      (__int64)&v25,
      v31);
  return v14;
}

```

## disassembly

```asm
0x140015d3c  mov     rax, rsp
0x140015d3f  mov     [rax+20h], rbx
0x140015d43  push    rbp
0x140015d44  push    rsi
0x140015d45  push    rdi
0x140015d46  push    r12
0x140015d48  push    r13
0x140015d4a  push    r14
0x140015d4c  push    r15
0x140015d4e  lea     rbp, [rax-118h]
0x140015d55  sub     rsp, 1E0h
0x140015d5c  movaps  xmmword ptr [rax-48h], xmm6
0x140015d60  movaps  xmmword ptr [rax-58h], xmm7
0x140015d64  mov     rax, cs:__security_cookie
0x140015d6b  xor     rax, rsp
0x140015d6e  mov     [rbp+110h+var_60], rax
0x140015d75  movsxd  rdi, edx
0x140015d78  mov     rsi, rcx
0x140015d7b  mov     [rbp+110h+var_190], r8
0x140015d7f  lea     rcx, [rbp+110h+var_140]; void *
0x140015d83  xor     edx, edx; Val
0x140015d85  mov     dword ptr [rsp+210h+var_1C8], edi
0x140015d89  mov     r8d, 0D8h; Size
0x140015d8f  call    memset
0x140015d94  xor     edx, edx; Val
0x140015d96  lea     rcx, [rbp+110h+var_180]; void *
0x140015d9a  lea     r8d, [rdx+40h]; Size
0x140015d9e  call    memset
0x140015da3  xor     r8d, r8d
0x140015da6  lea     rcx, FIGlobals
0x140015dad  mov     [rsp+210h+var_1C0], r8
0x140015db2  mov     rbx, 0FFFFF78000000320h
0x140015dbc  lea     r15d, [r8+2]
0x140015dc0  mov     rbx, [rbx]
0x140015dc3  mov     eax, ds:0FFFFF78000000004h
0x140015dcc  mov     [rsp+210h+var_198], rbx
0x140015dd1  mov     dword ptr [rsp+210h+var_1B8], eax
0x140015dd5  cmp     rsi, 1
0x140015dd9  jnz     short loc_140015E15
0x140015ddb  lock inc dword ptr [rcx+rdi*4+4DCh]
0x140015de3  lea     rax, FIPfGlobalOpenAttemptsRundown; "\\FI_GlobalOpenAttemptsRundown"
0x140015dea  mov     [rsp+210h+var_1CC], 1Dh
0x140015df2  mov     [rsp+210h+var_1A0], rax
0x140015df7  lea     r12, qword_140009570
0x140015dfe  lea     rax, qword_140009558
0x140015e05  lea     r13, byte_140009568
0x140015e0c  lea     rdi, dword_14000956C
0x140015e13  jmp     short loc_140015E54
0x140015e15  cmp     rsi, r15
0x140015e18  jnz     short loc_140015E73
0x140015e1a  lock inc dword ptr [rcx+rdi*4+4F0h]
0x140015e22  lea     rax, FIPfAllVolumeOpenAttemptsRundown; "\\FI_AllVolumeOpenAttemptsRundown"
0x140015e29  mov     ecx, 20h ; ' '
0x140015e2e  mov     [rsp+210h+var_1A0], rax
0x140015e33  lea     r12, qword_140009540
0x140015e3a  lea     rax, qword_140009528
0x140015e41  mov     word ptr [rsp+210h+var_1CC], cx
0x140015e46  lea     r13, byte_140009538
0x140015e4d  lea     rdi, dword_14000953C
0x140015e54  mov     [rsp+210h+var_1B0], rax
0x140015e59  lea     r14, qword_140009510
0x140015e60  movzx   eax, [rbp+110h+var_162]
0x140015e64  mov     rsi, r8
0x140015e67  mov     word ptr [rsp+210h+var_1D0], ax
0x140015e6c  mov     [rsp+210h+var_1A8], r8
0x140015e71  jmp     short loc_140015EEB
0x140015e73  lea     r14, [rsi+88h]
0x140015e7a  lock inc dword ptr [rsi+rdi*4+1B4h]
0x140015e82  lock inc dword ptr [rcx+rdi*4+504h]
0x140015e8a  lea     rcx, [rsi+18h]
0x140015e8e  call    FILockSharedAcquire
0x140015e93  movups  xmm7, xmmword ptr [rsi+50h]
0x140015e97  lea     rcx, [rsi+18h]
0x140015e9b  movups  xmm6, xmmword ptr [rsi+60h]
0x140015e9f  call    FILockExclusiveRelease
0x140015ea4  pextrw  eax, xmm7, 7
0x140015ea9  psrldq  xmm6, 8
0x140015eae  lea     r12, [rsi+108h]
0x140015eb5  movq    [rsp+210h+var_1A0], xmm6
0x140015ebb  lea     r13, [rsi+100h]
0x140015ec2  mov     r15d, 1
0x140015ec8  movq    [rsp+210h+var_1A8], xmm6
0x140015ece  mov     word ptr [rsp+210h+var_1D0], ax
0x140015ed3  lea     rdi, [rsi+104h]
0x140015eda  mov     word ptr [rsp+210h+var_1CC], ax
0x140015edf  lea     rax, [rsi+0F0h]
0x140015ee6  mov     [rsp+210h+var_1B0], rax
0x140015eeb  mov     rcx, r14
0x140015eee  call    FILockExclusiveAcquire
0x140015ef3  lock inc dword ptr [rdi]
0x140015ef6  xor     edi, edi
0x140015ef8  cmp     [r12], edi
0x140015efc  jnz     short loc_140015F05
0x140015efe  xor     esi, esi
0x140015f00  jmp     loc_140015FD3
0x140015f05  call    cs:__imp_PsIsCurrentThreadPrefetching
0x140015f0c  nop     dword ptr [rax+rax+00h]
0x140015f11  test    al, al
0x140015f13  jz      short loc_140015F2B
0x140015f15  lock inc cs:dword_1400098E0
0x140015f1c  xor     eax, eax
0x140015f1e  mov     edi, 0C0020049h
0x140015f23  movzx   esi, ax
0x140015f26  jmp     loc_140015FD3
0x140015f2b  movzx   eax, word ptr [r12]
0x140015f30  lea     r8, [rbp+110h+var_140]
0x140015f34  movzx   r12d, word ptr [rsp+210h+var_1C0]
0x140015f3a  mov     rdx, r13
0x140015f3d  mov     rcx, [rsp+210h+var_1B0]
0x140015f42  add     r12w, ax
0x140015f46  mov     word ptr [rsp+210h+var_1C0], r12w
0x140015f4c  mov     word ptr [rsp+210h+var_1C0+2], ax
0x140015f51  call    FIPfBlockedOpInsert
0x140015f56  mov     rcx, r14
0x140015f59  call    FILockExclusiveRelease
0x140015f5e  or      [rbp+110h+var_D0], 8
0x140015f62  mov     eax, dword ptr [rsp+210h+var_1C8]
0x140015f66  mov     [rbp+110h+var_E8], eax
0x140015f69  mov     [rbp+110h+var_E0], rsi
0x140015f6d  test    rsi, rsi
0x140015f70  jz      short loc_140015FAB
0x140015f72  movzx   r8d, word ptr [rsp+210h+var_1D0]
0x140015f78  mov     ecx, 31h ; '1'
0x140015f7d  cmp     r8d, ecx
0x140015f80  cmovb   ecx, r8d
0x140015f84  sub     r8d, ecx
0x140015f87  lea     rdi, [rcx+rcx]
0x140015f8b  mov     rcx, [rsp+210h+var_1A8]
0x140015f90  lea     rdx, [rcx+r8*2]; Src
0x140015f94  mov     r8, rdi; Size
0x140015f97  lea     rcx, [rbp+110h+var_CC]; void *
0x140015f9b  call    memmove
0x140015fa0  xor     eax, eax
0x140015fa2  mov     [rbp+rdi+110h+var_CC], ax
0x140015fa7  or      [rbp+110h+var_D0], 10h
0x140015fab  mov     edx, 1
0x140015fb0  lea     rcx, [rbp+110h+var_140]
0x140015fb4  call    FIPfBlockedOpBlock
0x140015fb9  mov     rcx, r14
0x140015fbc  mov     edi, eax
0x140015fbe  call    FILockExclusiveAcquire
0x140015fc3  lea     r8, [rbp+110h+var_140]
0x140015fc7  mov     rdx, r13
0x140015fca  call    FIPfBlockedOpRemove
0x140015fcf  movzx   esi, r12w
0x140015fd3  mov     rcx, r14
0x140015fd6  call    FILockExclusiveRelease
0x140015fdb  test    si, si
0x140015fde  jz      short loc_14001602E
0x140015fe0  mov     r10d, dword ptr [rsp+210h+var_1B8]
0x140015fe5  mov     r8d, r15d
0x140015fe8  mov     eax, dword ptr [rsp+210h+var_198+4]
0x140015fec  mov     r9d, dword ptr [rsp+210h+var_1C8]
0x140015ff1  movzx   edx, word ptr [rsp+210h+var_1CC]
0x140015ff6  mov     rcx, [rsp+210h+var_1A0]
0x140015ffb  imul    rax, r10
0x140015fff  mov     r11d, ebx
0x140016002  shl     rax, 8
0x140016006  imul    r11, r10
0x14001600a  shr     r11, 18h
0x14001600e  add     r11, rax
0x140016011  mov     rax, [rbp+110h+var_190]
0x140016015  mov     [rsp+210h+var_1E0], rax
0x14001601a  lea     rax, [rsp+210h+var_1C0]
0x14001601f  mov     [rsp+210h+var_1E8], rax
0x140016024  mov     [rsp+210h+var_1F0], r11
0x140016029  call    FIPfConflictTelemetryAccumulate
0x14001602e  mov     eax, edi
0x140016030  mov     rcx, [rbp+110h+var_60]
0x140016037  xor     rcx, rsp; StackCookie
0x14001603a  call    __security_check_cookie
0x14001603f  lea     r11, [rsp+210h+var_30]
0x140016047  mov     rbx, [r11+58h]
0x14001604b  movaps  xmm6, xmmword ptr [r11-10h]
0x140016050  movaps  xmm7, xmmword ptr [r11-20h]
0x140016055  mov     rsp, r11
0x140016058  pop     r15
0x14001605a  pop     r14
0x14001605c  pop     r13
0x14001605e  pop     r12
0x140016060  pop     rdi
0x140016061  pop     rsi
0x140016062  pop     rbp
0x140016063  retn
```
