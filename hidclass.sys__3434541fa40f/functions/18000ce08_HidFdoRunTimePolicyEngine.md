# HidFdoRunTimePolicyEngine

- ea: `0x18000ce08`
- end: `0x18000d301`
- name: `HidFdoRunTimePolicyEngine`
- size: `1273`
- prototype: ``
- caller_count: `10`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000c5c0`
- `0x18000cdac`
- `0x18000df80`
- `0x180011738`
- `0x18001a708`
- `0x18001a7cc`
- `0x18001c264`
- `0x18001c4c0`
- `0x180024cb0`
- `0x180024d30`

## callees

- `0x180003b70`
- `0x180003f40`
- `0x18000ce08`
- `0x18000d308`
- `0x18000d3a4`
- `0x18000d628`
- `0x18000dbfc`
- `0x18000ff44`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x18000cea5`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000cea5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18000cff0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18000cff0`

## pseudocode

```c
__int64 __fastcall HidFdoRunTimePolicyEngine(_QWORD *a1, KIRQL *a2)
{
  char v2; // r12
  int v3; // eax
  KIRQL v5; // cl
  KSPIN_LOCK *v6; // r8
  unsigned int v7; // edi
  int v8; // eax
  __int128 v9; // xmm0
  int v10; // esi
  __int128 v11; // xmm1
  __m128i v12; // xmm6
  __int64 v13; // rbx
  unsigned int v14; // r14d
  int v15; // r14d
  unsigned int v16; // esi
  int v17; // edx
  __int64 v18; // r8
  __int64 result; // rax
  int v20; // r14d
  int v21; // eax
  int v22; // r14d
  int v23; // r14d
  int v24; // [rsp+28h] [rbp-99h]
  int v25; // [rsp+30h] [rbp-91h]
  int v26; // [rsp+38h] [rbp-89h]
  int v27; // [rsp+40h] [rbp-81h]
  __int128 v28; // [rsp+88h] [rbp-39h] BYREF
  __int128 v29; // [rsp+98h] [rbp-29h]
  __m128i v30; // [rsp+A8h] [rbp-19h]
  int v31; // [rsp+B8h] [rbp-9h]
  int v32; // [rsp+128h] [rbp+67h]
  KIRQL *v33; // [rsp+130h] [rbp+6Fh]
  __int64 v34; // [rsp+138h] [rbp+77h]

  v33 = a2;
  v2 = 1;
  v3 = *((_DWORD *)a1 + 450);
  if ( (v3 & 1) == 0 )
  {
    v5 = *a2;
    v6 = a1 + 224;
    v7 = 0;
    v8 = v3 | 1;
    while ( 1 )
    {
      v9 = *((_OWORD *)a1 + 108);
      v10 = *((_DWORD *)a1 + 62);
      v11 = *((_OWORD *)a1 + 109);
      *((_DWORD *)a1 + 450) = v8 & 0xFFFFFFFD;
      v12 = *((__m128i *)a1 + 110);
      v32 = *((_DWORD *)a1 + 444);
      v28 = v9;
      v31 = v32;
      v29 = v11;
      v30 = v12;
      KeReleaseSpinLock(v6, v5);
      v13 = *(_QWORD *)((char *)a1 + 1780);
      HidpWppDumpFdoPowerData(a1, a1[84], &v28);
      v14 = _mm_cvtsi128_si32(_mm_srli_si128(v12, 8));
      if ( (v14 & 2) == 0 )
        break;
      if ( v10 == 1 )
      {
        if ( (BYTE12(v29) & 0x30) == 0x10 && (BYTE12(v29) & 2) == 0 )
        {
          v16 = HIDWORD(v28);
          v7 &= 0xFFFFFFFC;
          v20 = v14 & 1;
          if ( v20 )
            v16 = DWORD2(v28);
          v15 = (v20 ^ 1) + 2;
          goto LABEL_16;
        }
      }
      else if ( !v30.m128i_i32[3] )
      {
        v16 = DWORD1(v28);
        v7 &= 0xFFFFFFFC;
        v15 = 14;
        goto LABEL_16;
      }
      if ( SBYTE12(v29) < 0 && (v14 & 4) != 0 )
      {
        v16 = DWORD1(v28);
        v7 &= 0xFFFFFFFC;
        v15 = 12;
        goto LABEL_16;
      }
      if ( v32 == 1 )
      {
        v16 = DWORD1(v28);
        v7 &= 0xFFFFFFFC;
        v15 = 13;
        goto LABEL_16;
      }
      if ( (v14 & 4) != 0 )
      {
        v21 = (HIDWORD(v29) >> 4) & 3;
        if ( v21 == 1 || *((_BYTE *)a1 + 2056) && v21 )
        {
          v16 = DWORD1(v28);
          v7 = v7 & 0xFFFFFFFC | 2;
          v15 = 4;
          goto LABEL_16;
        }
      }
      if ( (BYTE12(v29) & 1) != 0 )
      {
        v22 = (v14 >> 3) & 1;
        if ( v22 )
        {
          v16 = v29;
          v7 = v7 & 0xFFFFFFFC | 2;
        }
        else
        {
          v16 = HIDWORD(v13);
          v7 = v7 & 0xFFFFFFFC | 1;
        }
        v15 = (v22 ^ 1) + 5;
        goto LABEL_16;
      }
      if ( (BYTE12(v29) & 0x40) != 0 )
      {
        v23 = (v14 >> 4) & 1;
        if ( v23 )
        {
          v7 = v7 & 0xFFFFFFFC | 2;
          v16 = 0;
        }
        else
        {
          v16 = HIDWORD(v13);
          v7 = v7 & 0xFFFFFFFC | 1;
        }
        v15 = (v23 ^ 1) + 7;
        goto LABEL_16;
      }
      if ( (v14 & 0x10) != 0 && v30.m128i_i32[1] )
      {
        v16 = DWORD1(v29);
        v7 = v7 & 0xFFFFFFFC | 2;
        v15 = 15;
        goto LABEL_16;
      }
      if ( (BYTE12(v29) & 4) == 0 || (BYTE12(v29) & 8) == 0 || *((int *)a1 + 85) <= 0 || *((int *)a1 + 86) <= 0 )
      {
        v15 = 11;
        goto LABEL_15;
      }
      v16 = DWORD2(v29);
      v7 = v7 & 0xFFFFFFFC | 2;
      LODWORD(v34) = v7;
      if ( DWORD2(v29) )
      {
        v15 = 10;
      }
      else
      {
        v16 = v28;
        v15 = 9;
      }
LABEL_17:
      HIDWORD(v34) = v16;
      HidpWppDumpFdoPowerTracker(a1, a1[84]);
      LOBYTE(v17) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( (_BYTE)v17 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_qLDDLLDD(
          WPP_GLOBAL_Control->AttachedDevice,
          v17,
          v18,
          a1[84],
          v24,
          v25,
          v26,
          v27,
          *a1,
          v15,
          v13 & 1,
          v7 & 1,
          SBYTE4(v13),
          v16,
          (v13 & 2) != 0,
          (v7 & 2) != 0);
      _InterlockedExchange((volatile __int32 *)a1 + 452, v15);
      *(_QWORD *)((char *)a1 + 1780) = v34;
      if ( (v7 & 1) == (v13 & 1) )
      {
        if ( (((unsigned __int8)v7 ^ (unsigned __int8)v13) & 2) == 0 )
          goto LABEL_34;
        HidpFdoAcquirePoFxPowerReferenceWithTag((__int64)a1, 2u);
      }
      else if ( (v7 & 1) != 0 )
      {
        HidpFdoAcquirePoFxPowerReferenceWithTag((__int64)a1, 2u);
LABEL_34:
        if ( v16 != HIDWORD(v13) )
          HidpFdoPoFxUpdateIdleTimeout(a1, v16, v18);
        goto LABEL_26;
      }
      if ( v16 != HIDWORD(v13) )
        HidpFdoPoFxUpdateIdleTimeout(a1, v16, v18);
      HidpFdoReleasePoFxPowerReferenceWithTag((__int64)a1, 2);
LABEL_26:
      v5 = KeAcquireSpinLockRaiseToDpc(a1 + 224);
      v6 = a1 + 224;
      *v33 = v5;
      v8 = *((_DWORD *)a1 + 450);
      if ( (v8 & 2) == 0 )
      {
        result = v8 & 0xFFFFFFFE;
        *((_DWORD *)a1 + 450) = result;
        return result;
      }
    }
    v15 = 1;
LABEL_15:
    v16 = HIDWORD(v13);
    v7 = v7 & 0xFFFFFFFC | 1;
LABEL_16:
    LODWORD(v34) = v7;
    goto LABEL_17;
  }
  *((_DWORD *)a1 + 450) = v3 | 2;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
  {
    v2 = 0;
  }
  result = (__int64)&WPP_RECORDER_INITIALIZED;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = v2;
    return WPP_RECORDER_AND_TRACE_SF_q(
             WPP_GLOBAL_Control->AttachedDevice,
             (_DWORD)a2,
             WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
             a1[84],
             4,
             9,
             43,
             (__int64)WPP_5a2771af4cec3e744979769e1f191181_Traceguids,
             *a1);
  }
  return result;
}

```

## disassembly

```asm
0x18000ce08  mov     rax, rsp
0x18000ce0b  mov     [rax+10h], rdx
0x18000ce0f  push    rbp
0x18000ce10  push    rbx
0x18000ce11  push    rsi
0x18000ce12  push    rdi
0x18000ce13  push    r12
0x18000ce15  push    r13
0x18000ce17  push    r14
0x18000ce19  push    r15
0x18000ce1b  lea     rbp, [rax-5Fh]
0x18000ce1f  sub     rsp, 0D8h
0x18000ce26  movaps  xmmword ptr [rax-58h], xmm6
0x18000ce2a  mov     r12d, 1
0x18000ce30  mov     eax, [rcx+708h]
0x18000ce36  mov     r15, rcx
0x18000ce39  mov     [rbp+57h+arg_10], 0
0x18000ce41  test    r12b, al
0x18000ce44  jnz     loc_18000D1B7
0x18000ce4a  mov     cl, [rdx]
0x18000ce4c  lea     r8, [r15+700h]
0x18000ce53  mov     edi, dword ptr [rbp+57h+arg_10]
0x18000ce56  lea     r13d, [r12+1]
0x18000ce5b  or      eax, r12d
0x18000ce5e  movups  xmm0, xmmword ptr [r15+6C0h]
0x18000ce66  mov     esi, [r15+0F8h]
0x18000ce6d  and     eax, 0FFFFFFFDh
0x18000ce70  movups  xmm1, xmmword ptr [r15+6D0h]
0x18000ce78  mov     [r15+708h], eax
0x18000ce7f  mov     dl, cl; NewIrql
0x18000ce81  mov     eax, [r15+6F0h]
0x18000ce88  mov     rcx, r8; SpinLock
0x18000ce8b  movups  xmm6, xmmword ptr [r15+6E0h]
0x18000ce93  mov     [rbp+57h+arg_0], eax
0x18000ce96  movups  [rbp+57h+var_90], xmm0
0x18000ce9a  mov     [rbp+57h+var_60], eax
0x18000ce9d  movups  [rbp+57h+var_80], xmm1
0x18000cea1  movups  [rbp+57h+var_70], xmm6
0x18000cea5  call    cs:__imp_KeReleaseSpinLock
0x18000ceac  nop     dword ptr [rax+rax+00h]
0x18000ceb1  mov     rbx, [r15+6F4h]
0x18000ceb8  lea     r8, [rbp+57h+var_90]
0x18000cebc  mov     rdx, [r15+2A0h]
0x18000cec3  mov     rcx, r15
0x18000cec6  mov     [rbp+57h+arg_18], rbx
0x18000ceca  call    HidpWppDumpFdoPowerData
0x18000cecf  psrldq  xmm6, 8
0x18000ced4  movd    r14d, xmm6
0x18000ced9  test    r13b, r14b
0x18000cedc  jz      short loc_18000CF3D
0x18000cede  mov     ecx, dword ptr [rbp+57h+var_80+0Ch]
0x18000cee1  cmp     esi, r12d
0x18000cee4  jz      loc_18000D0EC
0x18000ceea  cmp     dword ptr [rbp+57h+var_70+0Ch], 0
0x18000ceee  jz      loc_18000D245
0x18000cef4  test    cl, cl
0x18000cef6  js      loc_18000D256
0x18000cefc  cmp     [rbp+57h+arg_0], r12d
0x18000cf00  jz      loc_18000D133
0x18000cf06  test    r14b, 4
0x18000cf0a  jnz     loc_18000D187
0x18000cf10  test    r12b, cl
0x18000cf13  jnz     loc_18000D28C
0x18000cf19  test    cl, 40h
0x18000cf1c  jnz     loc_18000D2B8
0x18000cf22  test    r14b, 10h
0x18000cf26  jnz     loc_18000D2E3
0x18000cf2c  test    cl, 4
0x18000cf2f  jnz     loc_18000D144
0x18000cf35  mov     r14d, 0Bh
0x18000cf3b  jmp     short loc_18000CF40
0x18000cf3d  mov     r14d, r12d
0x18000cf40  mov     esi, dword ptr [rbp+57h+arg_18+4]
0x18000cf46  and     edi, 0FFFFFFFDh
0x18000cf49  or      edi, r12d
0x18000cf4c  mov     dword ptr [rbp+57h+arg_10], edi
0x18000cf4f  mov     rdx, [r15+2A0h]
0x18000cf56  mov     rcx, r15
0x18000cf59  mov     dword ptr [rbp+57h+arg_10+4], esi
0x18000cf5c  call    HidpWppDumpFdoPowerTracker
0x18000cf61  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf68  lea     rax, WPP_GLOBAL_Control
0x18000cf6f  cmp     rcx, rax
0x18000cf72  jnz     loc_18000D042
0x18000cf78  xor     dl, dl
0x18000cf7a  lea     rax, WPP_RECORDER_INITIALIZED
0x18000cf81  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18000cf88  setnz   r8b
0x18000cf8c  test    dl, dl
0x18000cf8e  jnz     loc_18000D061
0x18000cf94  test    r8b, r8b
0x18000cf97  jnz     loc_18000D061
0x18000cf9d  mov     rax, [rbp+57h+arg_10]
0x18000cfa1  mov     ecx, edi
0x18000cfa3  xchg    r14d, [r15+710h]
0x18000cfaa  mov     [r15+6F4h], rax
0x18000cfb1  and     ecx, r12d
0x18000cfb4  mov     eax, ebx
0x18000cfb6  and     eax, r12d
0x18000cfb9  cmp     ecx, eax
0x18000cfbb  jz      loc_18000D119
0x18000cfc1  test    ecx, ecx
0x18000cfc3  jnz     loc_18000D0C3
0x18000cfc9  cmp     esi, dword ptr [rbp+57h+arg_18+4]
0x18000cfcf  jz      short loc_18000CFDB
0x18000cfd1  mov     edx, esi
0x18000cfd3  mov     rcx, r15
0x18000cfd6  call    HidpFdoPoFxUpdateIdleTimeout
0x18000cfdb  xor     r8d, r8d
0x18000cfde  mov     edx, r13d
0x18000cfe1  mov     rcx, r15
0x18000cfe4  call    HidpFdoReleasePoFxPowerReferenceWithTag
0x18000cfe9  lea     rcx, [r15+700h]; SpinLock
0x18000cff0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x18000cff7  nop     dword ptr [rax+rax+00h]
0x18000cffc  mov     cl, al
0x18000cffe  lea     r8, [r15+700h]
0x18000d005  mov     rax, [rbp+57h+arg_8]
0x18000d009  mov     [rax], cl
0x18000d00b  mov     eax, [r15+708h]
0x18000d012  test    r13b, al
0x18000d015  jnz     loc_18000CE5E
0x18000d01b  and     eax, 0FFFFFFFEh
0x18000d01e  mov     [r15+708h], eax
0x18000d025  movaps  xmm6, [rsp+110h+var_58+8]
0x18000d02d  add     rsp, 0D8h
0x18000d034  pop     r15
0x18000d036  pop     r14
0x18000d038  pop     r13
0x18000d03a  pop     r12
0x18000d03c  pop     rdi
0x18000d03d  pop     rsi
0x18000d03e  pop     rbx
0x18000d03f  pop     rbp
0x18000d040  retn
0x18000d042  test    dword ptr [rcx+2Ch], 100h
0x18000d049  jz      loc_18000CF78
0x18000d04f  cmp     byte ptr [rcx+29h], 4
0x18000d053  jb      loc_18000CF78
0x18000d059  mov     dl, r12b
0x18000d05c  jmp     loc_18000CF7A
0x18000d061  mov     rcx, [rcx+18h]
0x18000d065  mov     r11d, edi
0x18000d068  mov     r10d, ebx
0x18000d06b  shr     r11d, 1
0x18000d06e  shr     r10d, 1
0x18000d071  and     r11d, r12d
0x18000d074  mov     [rsp+78h], r11d
0x18000d079  and     r10d, r12d
0x18000d07c  mov     [rsp+110h+var_A0], r10d
0x18000d081  mov     r9d, edi
0x18000d084  mov     r10d, dword ptr [rbp+57h+arg_18+4]
0x18000d08b  and     r9d, r12d
0x18000d08e  mov     [rsp+110h+var_A8], esi
0x18000d092  mov     eax, ebx
0x18000d094  mov     [rsp+110h+var_B0], r10d
0x18000d099  and     eax, r12d
0x18000d09c  mov     [rsp+110h+var_B8], r9d
0x18000d0a1  mov     r9, [r15+2A0h]
0x18000d0a8  mov     [rsp+110h+var_C0], eax
0x18000d0ac  mov     rax, [r15]
0x18000d0af  mov     [rsp+110h+var_C8], r14d
0x18000d0b4  mov     qword ptr [rsp+110h+var_D0], rax
0x18000d0b9  call    WPP_RECORDER_AND_TRACE_SF_qLDDLLDD
0x18000d0be  jmp     loc_18000CF9D
0x18000d0c3  xor     r8d, r8d
0x18000d0c6  mov     edx, r13d
0x18000d0c9  mov     rcx, r15
0x18000d0cc  call    HidpFdoAcquirePoFxPowerReferenceWithTag
0x18000d0d1  cmp     esi, dword ptr [rbp+57h+arg_18+4]
0x18000d0d7  jz      loc_18000CFE9
0x18000d0dd  mov     edx, esi
0x18000d0df  mov     rcx, r15
0x18000d0e2  call    HidpFdoPoFxUpdateIdleTimeout
0x18000d0e7  jmp     loc_18000CFE9
0x18000d0ec  mov     eax, ecx
0x18000d0ee  and     al, 30h
0x18000d0f0  cmp     al, 10h
0x18000d0f2  jnz     loc_18000CEF4
0x18000d0f8  test    r13b, cl
0x18000d0fb  jnz     loc_18000CEF4
0x18000d101  mov     esi, dword ptr [rbp+57h+var_90+0Ch]
0x18000d104  and     edi, 0FFFFFFFCh
0x18000d107  and     r14d, r12d
0x18000d10a  cmovnz  esi, dword ptr [rbp+57h+var_90+8]
0x18000d10e  xor     r14d, r12d
0x18000d111  add     r14d, r13d
0x18000d114  jmp     loc_18000CF4C
0x18000d119  xor     ebx, edi
0x18000d11b  test    r13b, bl
0x18000d11e  jz      short loc_18000D0D1
0x18000d120  xor     r8d, r8d
0x18000d123  mov     edx, r13d
0x18000d126  mov     rcx, r15
0x18000d129  call    HidpFdoAcquirePoFxPowerReferenceWithTag
0x18000d12e  jmp     loc_18000CFC9
0x18000d133  mov     esi, dword ptr [rbp+57h+var_90+4]
0x18000d136  and     edi, 0FFFFFFFCh
0x18000d139  mov     r14d, 0Dh
0x18000d13f  jmp     loc_18000CF4C
0x18000d144  test    cl, 8
0x18000d147  jz      loc_18000CF35
0x18000d14d  cmp     dword ptr [r15+154h], 0
0x18000d155  jle     loc_18000CF35
0x18000d15b  cmp     dword ptr [r15+158h], 0
0x18000d163  jle     loc_18000CF35
0x18000d169  mov     esi, dword ptr [rbp+57h+var_80+8]
0x18000d16c  and     edi, 0FFFFFFFEh
0x18000d16f  or      edi, r13d
0x18000d172  mov     dword ptr [rbp+57h+arg_10], edi
0x18000d175  test    esi, esi
0x18000d177  jnz     short loc_18000D1AC
0x18000d179  mov     esi, dword ptr [rbp+57h+var_90]
0x18000d17c  mov     r14d, 9
0x18000d182  jmp     loc_18000CF4F
0x18000d187  mov     eax, ecx
0x18000d189  shr     eax, 4
0x18000d18c  and     eax, 3
0x18000d18f  cmp     eax, r12d
0x18000d192  jnz     loc_18000D271
0x18000d198  mov     esi, dword ptr [rbp+57h+var_90+4]
0x18000d19b  and     edi, 0FFFFFFFEh
0x18000d19e  or      edi, r13d
0x18000d1a1  mov     r14d, 4
0x18000d1a7  jmp     loc_18000CF4C
0x18000d1ac  mov     r14d, 0Ah
0x18000d1b2  jmp     loc_18000CF4F
0x18000d1b7  or      eax, 2
0x18000d1ba  mov     [rcx+708h], eax
0x18000d1c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d1c7  lea     rax, WPP_GLOBAL_Control
0x18000d1ce  cmp     rcx, rax
0x18000d1d1  jz      short loc_18000D1E2
0x18000d1d3  test    dword ptr [rcx+2Ch], 100h
0x18000d1da  jz      short loc_18000D1E2
0x18000d1dc  cmp     byte ptr [rcx+29h], 4
0x18000d1e0  jnb     short loc_18000D1E5
0x18000d1e2  xor     r12b, r12b
0x18000d1e5  lea     rax, WPP_RECORDER_INITIALIZED
0x18000d1ec  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18000d1f3  setnz   r8b
0x18000d1f7  test    r12b, r12b
0x18000d1fa  jnz     short loc_18000D205
0x18000d1fc  test    r8b, r8b
0x18000d1ff  jz      loc_18000D025
0x18000d205  mov     rax, [r15]
0x18000d208  mov     dl, r12b
0x18000d20b  mov     r9, [r15+2A0h]
0x18000d212  mov     rcx, [rcx+18h]
0x18000d216  mov     qword ptr [rsp+110h+var_D0], rax
0x18000d21b  lea     rax, WPP_5a2771af4cec3e744979769e1f191181_Traceguids
0x18000d222  mov     [rsp+110h+var_D8], rax
0x18000d227  mov     word ptr [rsp+110h+var_E0], 2Bh ; '+'
0x18000d22e  mov     dword ptr [rsp+110h+var_E8], 9
0x18000d236  mov     byte ptr [rsp+110h+var_F0], 4
0x18000d23b  call    WPP_RECORDER_AND_TRACE_SF_q
0x18000d240  jmp     loc_18000D025
0x18000d245  mov     esi, dword ptr [rbp+57h+var_90+4]
0x18000d248  and     edi, 0FFFFFFFCh
0x18000d24b  mov     r14d, 0Eh
0x18000d251  jmp     loc_18000CF4C
0x18000d256  test    r14b, 4
0x18000d25a  jz      loc_18000CEFC
0x18000d260  mov     esi, dword ptr [rbp+57h+var_90+4]
0x18000d263  and     edi, 0FFFFFFFCh
0x18000d266  mov     r14d, 0Ch
0x18000d26c  jmp     loc_18000CF4C
0x18000d271  cmp     byte ptr [r15+808h], 0
0x18000d279  jz      loc_18000CF10
0x18000d27f  test    eax, eax
0x18000d281  jz      loc_18000CF10
0x18000d287  jmp     loc_18000D198
0x18000d28c  shr     r14d, 3
0x18000d290  and     r14d, r12d
0x18000d293  jz      short loc_18000D2A0
0x18000d295  mov     esi, dword ptr [rbp+57h+var_80]
0x18000d298  and     edi, 0FFFFFFFEh
0x18000d29b  or      edi, r13d
0x18000d29e  jmp     short loc_18000D2AC
0x18000d2a0  mov     esi, dword ptr [rbp+57h+arg_18+4]
0x18000d2a6  and     edi, 0FFFFFFFDh
0x18000d2a9  or      edi, r12d
0x18000d2ac  xor     r14d, r12d
0x18000d2af  add     r14d, 5
0x18000d2b3  jmp     loc_18000CF4C
0x18000d2b8  shr     r14d, 4
0x18000d2bc  and     r14d, r12d
0x18000d2bf  jz      short loc_18000D2CB
0x18000d2c1  and     edi, 0FFFFFFFEh
0x18000d2c4  or      edi, r13d
0x18000d2c7  xor     esi, esi
0x18000d2c9  jmp     short loc_18000D2D7
0x18000d2cb  mov     esi, dword ptr [rbp+57h+arg_18+4]
0x18000d2d1  and     edi, 0FFFFFFFDh
0x18000d2d4  or      edi, r12d
0x18000d2d7  xor     r14d, r12d
0x18000d2da  add     r14d, 7
0x18000d2de  jmp     loc_18000CF4C
0x18000d2e3  cmp     dword ptr [rbp+57h+var_70+4], 0
0x18000d2e7  jz      loc_18000CF2C
  ... truncated ...
```
