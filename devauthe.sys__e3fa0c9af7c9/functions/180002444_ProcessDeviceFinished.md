# _ProcessDeviceFinished

- ea: `0x180002444`
- end: `0x180002586`
- name: `_ProcessDeviceFinished`
- size: `322`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800020e4`

## callees

- `0x180002444`
- `0x1800027dc`
- `0x180002888`
- `0x1800035bc`
- `0x180005020`
- `0x1800067e0`

## pseudocode

```c
__int64 __fastcall ProcessDeviceFinished(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbx
  __int64 v5; // rdx
  int v6; // ecx
  __int64 v7; // rdx
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  unsigned int v11; // eax
  unsigned __int128 v12; // xmm0
  __int64 v13; // r8
  size_t Size; // [rsp+30h] [rbp-59h]
  unsigned __int128 v15; // [rsp+40h] [rbp-49h] BYREF
  __int128 v16; // [rsp+50h] [rbp-39h]
  _OWORD v17[2]; // [rsp+60h] [rbp-29h] BYREF
  _OWORD v18[2]; // [rsp+80h] [rbp-9h] BYREF
  int v19[8]; // [rsp+A0h] [rbp+17h] BYREF

  v3 = a1;
  LOBYTE(a1) = 8;
  v15 = 0;
  v16 = 0;
  if ( (unsigned int)DevAuthValidateHeader(a1, a2, a3) )
  {
    if ( (unsigned int)DevAuthGetRunningHash(*(_QWORD *)(v3 + 1224), v19) )
    {
      LODWORD(Size) = 32;
      if ( (unsigned int)DevAuthPesudoRandomFunction(
                           (__int64)"Device Finished",
                           (int)v3 + 1168,
                           48,
                           (__int64)v19,
                           32,
                           v17,
                           Size) )
      {
        v5 = 0;
        while ( *((_BYTE *)v17 + v5) == *(_BYTE *)(v5 + a2 + 4) )
        {
          v5 = (unsigned int)(v5 + 1);
          if ( (unsigned int)v5 >= 0x20 )
          {
            v6 = 0;
            while ( 1 )
            {
              v7 = 34LL * v6;
              if ( *(_WORD *)(v3 + 124) == *(_WORD *)((char *)qword_18000C010 + v7) )
                break;
              if ( (unsigned int)++v6 >= 5 )
                return 0;
            }
            v9 = *(_OWORD *)((char *)qword_18000C010 + v7 + 2);
            v10 = *(_OWORD *)((char *)&qword_18000C010[2] + v7 + 2);
            LODWORD(v16) = *(_DWORD *)(v3 + 97);
            *(_QWORD *)((char *)&v16 + 4) = *(_QWORD *)(v3 + 101);
            v11 = *(_DWORD *)(v3 + 120);
            v18[0] = v9;
            v12 = *(_OWORD *)(v3 + 81);
            HIDWORD(v16) = _byteswap_ulong(v11);
            v18[1] = v10;
            v15 = v12;
            GetMsftVerifyData((unsigned __int128 *)(a2 + 4), (unsigned __int64)v18, &v15, (__int64)v17);
            v13 = 0;
            while ( *((_BYTE *)v17 + v13) == *(_BYTE *)(v13 + a2 + 36) )
            {
              v13 = (unsigned int)(v13 + 1);
              if ( (unsigned int)v13 >= 0x20 )
                return 1;
            }
            return 0;
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180002444  push    rbp
0x180002446  push    rbx
0x180002447  push    rdi
0x180002448  lea     rbp, [rsp-47h]
0x18000244d  sub     rsp, 0D0h
0x180002454  mov     rax, cs:__security_cookie
0x18000245b  xor     rax, rsp
0x18000245e  mov     [rbp+57h+var_20], rax
0x180002462  mov     rbx, rcx
0x180002465  xorps   xmm0, xmm0
0x180002468  mov     cl, 8
0x18000246a  mov     rdi, rdx
0x18000246d  movups  [rbp+57h+var_A0], xmm0
0x180002471  movups  [rbp+57h+var_90], xmm0
0x180002475  call    DevAuthValidateHeader
0x18000247a  test    eax, eax
0x18000247c  jz      loc_180002506
0x180002482  mov     rcx, [rbx+4C8h]
0x180002489  lea     rdx, [rbp+57h+var_40]
0x18000248d  call    DevAuthGetRunningHash
0x180002492  test    eax, eax
0x180002494  jz      short loc_180002506
0x180002496  lea     rax, [rbp+57h+var_80]
0x18000249a  mov     dword ptr [rsp+0E0h+Size], 20h ; ' '; Size
0x1800024a2  mov     [rsp+0E0h+var_B8], rax; void *
0x1800024a7  lea     rdx, [rbx+490h]; int
0x1800024ae  lea     r9, [rbp+57h+var_40]; int
0x1800024b2  mov     [rsp+0E0h+var_C0], 20h ; ' '; int
0x1800024ba  mov     r8d, 30h ; '0'; int
0x1800024c0  lea     rcx, aDeviceFinished; "Device Finished"
0x1800024c7  call    DevAuthPesudoRandomFunction
0x1800024cc  test    eax, eax
0x1800024ce  jz      short loc_180002506
0x1800024d0  xor     edx, edx
0x1800024d2  mov     al, [rdx+rdi+4]
0x1800024d6  cmp     [rbp+rdx+57h+var_80], al
0x1800024da  jnz     short loc_180002506
0x1800024dc  inc     edx
0x1800024de  cmp     edx, 20h ; ' '
0x1800024e1  jb      short loc_1800024D2
0x1800024e3  movzx   r8d, word ptr [rbx+7Ch]
0x1800024e8  lea     r9, qword_18000C010
0x1800024ef  xor     ecx, ecx
0x1800024f1  movsxd  rax, ecx
0x1800024f4  imul    rdx, rax, 22h ; '"'
0x1800024f8  cmp     r8w, [rdx+r9]
0x1800024fd  jz      short loc_180002520
0x1800024ff  inc     ecx
0x180002501  cmp     ecx, 5
0x180002504  jb      short loc_1800024F1
0x180002506  xor     eax, eax
0x180002508  mov     rcx, [rbp+57h+var_20]
0x18000250c  xor     rcx, rsp; StackCookie
0x18000250f  call    __security_check_cookie
0x180002514  add     rsp, 0D0h
0x18000251b  pop     rdi
0x18000251c  pop     rbx
0x18000251d  pop     rbp
0x18000251e  retn
0x180002520  movups  xmm0, xmmword ptr [rdx+r9+2]
0x180002526  mov     eax, [rbx+61h]
0x180002529  lea     r8, [rbp+57h+var_A0]
0x18000252d  movups  xmm1, xmmword ptr [rdx+r9+12h]
0x180002533  mov     dword ptr [rbp+57h+var_90], eax
0x180002536  lea     r9, [rbp+57h+var_80]
0x18000253a  mov     rax, [rbx+65h]
0x18000253e  lea     rdx, [rbp+57h+var_60]
0x180002542  mov     qword ptr [rbp+57h+var_90+4], rax
0x180002546  lea     rcx, [rdi+4]
0x18000254a  mov     eax, [rbx+78h]
0x18000254d  movups  [rbp+57h+var_60], xmm0
0x180002551  bswap   eax
0x180002553  movups  xmm0, xmmword ptr [rbx+51h]
0x180002557  mov     dword ptr [rbp+57h+var_90+0Ch], eax
0x18000255a  movups  [rbp+57h+var_50], xmm1
0x18000255e  movups  [rbp+57h+var_A0], xmm0
0x180002562  call    GetMsftVerifyData
0x180002567  xor     r8d, r8d
0x18000256a  mov     cl, [r8+rdi+24h]
0x18000256f  cmp     [rbp+r8+57h+var_80], cl
0x180002574  jnz     short loc_180002506
0x180002576  inc     r8d
0x180002579  cmp     r8d, 20h ; ' '
0x18000257d  jb      short loc_18000256A
0x18000257f  mov     eax, 1
0x180002584  jmp     short loc_180002508
```
