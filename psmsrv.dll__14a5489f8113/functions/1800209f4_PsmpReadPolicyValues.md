# PsmpReadPolicyValues

- ea: `0x1800209f4`
- end: `0x180020f36`
- name: `PsmpReadPolicyValues`
- size: `1346`
- prototype: `__int64 __fastcall(char)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180020460`
- `0x1800220b4`

## callees

- `0x18001622c`
- `0x180017650`
- `0x180017ca4`
- `0x180017f60`
- `0x180020400`
- `0x1800209f4`
- `0x180020f3c`

## import_xrefs

- `ntdll!TpSetTimer` at `0x180020f1f`
- `ntdll!TpSetTimer` at `0x180020f1f`
- `ntdll!TpWaitForTimer` at `0x180020ef0`
- `ntdll!TpWaitForTimer` at `0x180020ef0`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180020bc9`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180020bc9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180020cee`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180020cee`

## pseudocode

```c
__int64 __fastcall PsmpReadPolicyValues(char a1)
{
  __int16 v2; // bx
  __int16 v3; // di
  __int16 v4; // bx
  __int16 v5; // di
  __int16 v6; // bx
  __int16 v7; // di
  __int16 v8; // bx
  __int16 v9; // di
  __int16 v10; // bx
  unsigned int v11; // ecx
  int i; // edi
  __int64 result; // rax
  _QWORD *v14; // rcx
  __int64 v15; // [rsp+98h] [rbp+50h] BYREF
  int v16; // [rsp+A0h] [rbp+58h]
  unsigned int v17; // [rsp+A8h] [rbp+60h]

  v17 = 0;
  LODWORD(v15) = 0;
  v16 = 0;
  if ( (int)PsmpReadRegUlongWithPrefix(KeyHandle, 0, L"DebugTimeout") >= 0 )
    PsmpDebugTimeoutSeconds = 2;
  v2 = (int)PsmpReadRegUlongWithPrefix(KeyHandle, 0, L"Enable") >= 0;
  v3 = v2 | 0x10;
  if ( (int)PsmpReadRegUlongWithPrefix(KeyHandle, 0, L"QuotaPeriodGeneral") < 0 )
    v3 = v2;
  v4 = v3 | 0x20;
  if ( (int)PsmpReadRegUlongWithPrefix(KeyHandle, 0, L"QuotaPeriodRtc") < 0 )
    v4 = v3;
  v5 = v4 | 2;
  if ( (int)PsmpReadRegUlongWithPrefix(KeyHandle, 0, L"PolicyPeriod") < 0 )
    v5 = v4;
  v6 = v5 | 8;
  if ( (int)PsmpReadRegUlongWithPrefix(KeyHandle, 0, L"EnableRankBias") < 0 )
    v6 = v5;
  v7 = v6 | 4;
  if ( (int)PsmpReadRegUlongWithPrefix(KeyHandle, 0, L"EnableBackgroundMode") < 0 )
    v7 = v6;
  v8 = v7 | 0x40;
  if ( (int)PsmpReadRegUlongWithPrefix(KeyHandle, 0, L"AntiStarvationTimeout") < 0 )
    v8 = v7;
  v9 = v8 | 0x80;
  if ( (int)PsmpReadRegUlongWithPrefix(KeyHandle, 0, L"BackgroundQuotaRate") < 0 )
    v9 = v8;
  v10 = v9 | 0x100;
  if ( (int)PsmpReadRegUlongWithPrefix(KeyHandle, 0, L"BackgroundMinimumBitRate") < 0 )
    v10 = v9;
  RtlAcquireSRWLockExclusive(&PsmpPolicyLock);
  if ( (v10 & 0x10) != 0 && (_DWORD)v15 )
  {
    dword_18003FE58 = v15;
    dword_18003FE60 = v15;
  }
  if ( (v10 & 0x20) != 0 && v16 )
  {
    dword_18003FE54 = v16;
    dword_18003FE5C = v16;
  }
  if ( (v10 & 2) != 0 )
  {
    v11 = v17;
    if ( dword_18003FE50 == v17 )
    {
      v10 &= ~2u;
    }
    else
    {
      if ( v17 - 1 <= 0xEA5E )
        v11 = 60000;
      if ( v11 > 0x1B7740 )
        v11 = 1800000;
      dword_18003FE50 = v11;
    }
  }
  if ( (v10 & 8) != 0 )
    LOBYTE(word_18003FE7B) = 0;
  if ( (v10 & 4) != 0 )
    HIBYTE(word_18003FE7B) = 0;
  if ( (v10 & 0x40) != 0 )
    dword_18003FE6C = 0;
  if ( (v10 & 0x80) != 0 )
    qword_18003FC80 = 0;
  if ( (v10 & 0x100) != 0 )
    dword_18003FDA0 = 0;
  if ( (v10 & 1) != 0 && a1 )
  {
    if ( (unsigned __int8)PsmpIsDfssActive() )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, &WPP_c1878895bf8430c1024ddd3cf0a685b6_Traceguids);
    }
    else
    {
      byte_18003FE7D = 0;
    }
  }
  RtlReleaseSRWLockExclusive(&PsmpPolicyLock);
  for ( i = 0; i < 2; ++i )
    result = PsmpReadQuotaValues(&PsmpPolicy[280 * i], (unsigned int)i);
  if ( v10 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        result = WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_c1878895bf8430c1024ddd3cf0a685b6_Traceguids);
        v14 = WPP_GLOBAL_Control;
      }
      if ( (*((_BYTE *)v14 + 28) & 1) != 0 )
      {
        if ( *((_BYTE *)v14 + 25) >= 4u )
        {
          result = WPP_SF_d(
                     v14[2],
                     91,
                     &WPP_c1878895bf8430c1024ddd3cf0a685b6_Traceguids,
                     (unsigned __int8)byte_18003FE7D);
          v14 = WPP_GLOBAL_Control;
        }
        if ( (*((_BYTE *)v14 + 28) & 1) != 0 )
        {
          if ( *((_BYTE *)v14 + 25) >= 4u )
          {
            result = WPP_SF_d(
                       v14[2],
                       92,
                       &WPP_c1878895bf8430c1024ddd3cf0a685b6_Traceguids,
                       (unsigned int)dword_18003FE58);
            v14 = WPP_GLOBAL_Control;
          }
          if ( (*((_BYTE *)v14 + 28) & 1) != 0 )
          {
            if ( *((_BYTE *)v14 + 25) >= 4u )
            {
              result = WPP_SF_d(
                         v14[2],
                         93,
                         &WPP_c1878895bf8430c1024ddd3cf0a685b6_Traceguids,
                         (unsigned int)dword_18003FE54);
              v14 = WPP_GLOBAL_Control;
            }
            if ( (*((_BYTE *)v14 + 28) & 1) != 0 )
            {
              if ( *((_BYTE *)v14 + 25) >= 4u )
              {
                result = WPP_SF_d(
                           v14[2],
                           94,
                           &WPP_c1878895bf8430c1024ddd3cf0a685b6_Traceguids,
                           dword_18003FE50 / 0xEA60u);
                v14 = WPP_GLOBAL_Control;
              }
              if ( (*((_BYTE *)v14 + 28) & 1) != 0 )
              {
                if ( *((_BYTE *)v14 + 25) >= 4u )
                {
                  result = WPP_SF_d(
                             v14[2],
                             95,
                             &WPP_c1878895bf8430c1024ddd3cf0a685b6_Traceguids,
                             (unsigned __int8)word_18003FE7B);
                  v14 = WPP_GLOBAL_Control;
                }
                if ( (*((_BYTE *)v14 + 28) & 1) != 0 )
                {
                  if ( *((_BYTE *)v14 + 25) >= 4u )
                  {
                    result = WPP_SF_d(
                               v14[2],
                               96,
                               &WPP_c1878895bf8430c1024ddd3cf0a685b6_Traceguids,
                               HIBYTE(word_18003FE7B));
                    v14 = WPP_GLOBAL_Control;
                  }
                  if ( (*((_BYTE *)v14 + 28) & 1) != 0 && *((_BYTE *)v14 + 25) >= 4u )
                  {
                    result = WPP_SF_d(
                               v14[2],
                               97,
                               &WPP_c1878895bf8430c1024ddd3cf0a685b6_Traceguids,
                               dword_18003FE6C / 0x3E8u);
                    v14 = WPP_GLOBAL_Control;
                  }
                }
              }
            }
          }
        }
      }
    }
    if ( (v10 & 0x80) != 0 && (*((_BYTE *)v14 + 28) & 1) != 0 && *((_BYTE *)v14 + 25) >= 4u )
      result = WPP_SF_i(v14[2], 98, &WPP_c1878895bf8430c1024ddd3cf0a685b6_Traceguids, qword_18003FC80);
  }
  if ( !a1 && (v10 & 2) != 0 )
  {
    v15 = 0;
    TpWaitForTimer(qword_18003FE28, 1);
    result = (unsigned int)dword_18003FE50;
    if ( dword_18003FE50 )
    {
      v15 = -10000LL * (unsigned int)dword_18003FE50;
      return TpSetTimer(qword_18003FE28, &v15, 0, 1000);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800209f4  push    rbp
0x1800209f6  push    rbx
0x1800209f7  push    rsi
0x1800209f8  push    rdi
0x1800209f9  push    r12
0x1800209fb  push    r13
0x1800209fd  push    r14
0x1800209ff  push    r15
0x180020a01  mov     rbp, rsp
0x180020a04  sub     rsp, 48h
0x180020a08  xor     r15d, r15d
0x180020a0b  lea     r9, [rbp+arg_0]
0x180020a0f  mov     r14b, cl
0x180020a12  mov     [rbp+arg_0], r15d
0x180020a16  mov     rcx, cs:KeyHandle; KeyHandle
0x180020a1d  lea     r8, aDebugtimeout; "DebugTimeout"
0x180020a24  xor     edx, edx; pszSrc
0x180020a26  mov     [rbp+var_20], r15d
0x180020a2a  mov     [rbp+var_1C], r15d
0x180020a2e  mov     [rbp+var_18], r15d
0x180020a32  mov     [rbp+var_14], r15d
0x180020a36  mov     [rbp+var_24], r15d
0x180020a3a  mov     [rbp+var_28], r15d
0x180020a3e  mov     [rbp+arg_18], r15d
0x180020a42  mov     dword ptr [rbp+arg_8], r15d
0x180020a46  mov     [rbp+arg_10], r15d
0x180020a4a  call    PsmpReadRegUlongWithPrefix
0x180020a4f  lea     esi, [r15+2]
0x180020a53  test    eax, eax
0x180020a55  js      short loc_180020A65
0x180020a57  mov     eax, [rbp+arg_0]
0x180020a5a  cmp     eax, esi
0x180020a5c  cmovb   eax, esi
0x180020a5f  mov     cs:PsmpDebugTimeoutSeconds, eax
0x180020a65  mov     rcx, cs:KeyHandle; KeyHandle
0x180020a6c  lea     r9, [rbp+var_14]
0x180020a70  lea     r8, aEnable; "Enable"
0x180020a77  xor     edx, edx; pszSrc
0x180020a79  call    PsmpReadRegUlongWithPrefix
0x180020a7e  mov     rcx, cs:KeyHandle; KeyHandle
0x180020a85  lea     r9, [rbp+arg_8]
0x180020a89  mov     ebx, eax
0x180020a8b  lea     r8, aQuotaperiodgen; "QuotaPeriodGeneral"
0x180020a92  shr     ebx, 1Fh
0x180020a95  mov     r12d, 1
0x180020a9b  xor     edx, edx; pszSrc
0x180020a9d  xor     bx, r12w
0x180020aa1  call    PsmpReadRegUlongWithPrefix
0x180020aa6  mov     rcx, cs:KeyHandle; KeyHandle
0x180020aad  lea     r9, [rbp+arg_10]
0x180020ab1  movzx   edi, bx
0x180020ab4  lea     r8, aQuotaperiodrtc; "QuotaPeriodRtc"
0x180020abb  or      di, 10h
0x180020abf  test    eax, eax
0x180020ac1  cmovs   di, bx
0x180020ac5  xor     edx, edx; pszSrc
0x180020ac7  call    PsmpReadRegUlongWithPrefix
0x180020acc  mov     rcx, cs:KeyHandle; KeyHandle
0x180020ad3  lea     r9, [rbp+arg_18]
0x180020ad7  movzx   ebx, di
0x180020ada  lea     r8, aPolicyperiod; "PolicyPeriod"
0x180020ae1  or      bx, 20h
0x180020ae5  test    eax, eax
0x180020ae7  cmovs   bx, di
0x180020aeb  xor     edx, edx; pszSrc
0x180020aed  call    PsmpReadRegUlongWithPrefix
0x180020af2  mov     rcx, cs:KeyHandle; KeyHandle
0x180020af9  lea     r9, [rbp+var_28]
0x180020afd  movzx   edi, bx
0x180020b00  lea     r8, aEnablerankbias; "EnableRankBias"
0x180020b07  or      di, si
0x180020b0a  test    eax, eax
0x180020b0c  cmovs   di, bx
0x180020b10  xor     edx, edx; pszSrc
0x180020b12  call    PsmpReadRegUlongWithPrefix
0x180020b17  mov     rcx, cs:KeyHandle; KeyHandle
0x180020b1e  lea     r9, [rbp+var_24]
0x180020b22  movzx   ebx, di
0x180020b25  lea     r8, aEnablebackgrou; "EnableBackgroundMode"
0x180020b2c  or      bx, 8
0x180020b30  test    eax, eax
0x180020b32  cmovs   bx, di
0x180020b36  xor     edx, edx; pszSrc
0x180020b38  call    PsmpReadRegUlongWithPrefix
0x180020b3d  mov     rcx, cs:KeyHandle; KeyHandle
0x180020b44  lea     r9, [rbp+var_20]
0x180020b48  movzx   edi, bx
0x180020b4b  lea     r8, aAntistarvation; "AntiStarvationTimeout"
0x180020b52  or      di, 4
0x180020b56  test    eax, eax
0x180020b58  cmovs   di, bx
0x180020b5c  xor     edx, edx; pszSrc
0x180020b5e  call    PsmpReadRegUlongWithPrefix
0x180020b63  mov     rcx, cs:KeyHandle; KeyHandle
0x180020b6a  lea     r9, [rbp+var_1C]
0x180020b6e  movzx   ebx, di
0x180020b71  lea     r8, aBackgroundquot_0; "BackgroundQuotaRate"
0x180020b78  or      bx, 40h
0x180020b7c  test    eax, eax
0x180020b7e  cmovs   bx, di
0x180020b82  xor     edx, edx; pszSrc
0x180020b84  call    PsmpReadRegUlongWithPrefix
0x180020b89  mov     rcx, cs:KeyHandle; KeyHandle
0x180020b90  lea     r13d, [r12+7Fh]
0x180020b95  movzx   edi, bx
0x180020b98  lea     r9, [rbp+var_18]
0x180020b9c  or      di, r13w
0x180020ba0  lea     r8, aBackgroundmini; "BackgroundMinimumBitRate"
0x180020ba7  test    eax, eax
0x180020ba9  cmovs   di, bx
0x180020bad  xor     edx, edx; pszSrc
0x180020baf  call    PsmpReadRegUlongWithPrefix
0x180020bb4  movzx   ebx, di
0x180020bb7  or      bx, 100h
0x180020bbc  test    eax, eax
0x180020bbe  lea     rcx, PsmpPolicyLock
0x180020bc5  cmovs   bx, di
0x180020bc9  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180020bcf  test    bl, 10h
0x180020bd2  jz      short loc_180020BE7
0x180020bd4  mov     eax, dword ptr [rbp+arg_8]
0x180020bd7  test    eax, eax
0x180020bd9  jz      short loc_180020BE7
0x180020bdb  mov     cs:dword_18003FE58, eax
0x180020be1  mov     cs:dword_18003FE60, eax
0x180020be7  test    bl, 20h
0x180020bea  jz      short loc_180020BFF
0x180020bec  mov     eax, [rbp+arg_10]
0x180020bef  test    eax, eax
0x180020bf1  jz      short loc_180020BFF
0x180020bf3  mov     cs:dword_18003FE54, eax
0x180020bf9  mov     cs:dword_18003FE5C, eax
0x180020bff  test    sil, bl
0x180020c02  jz      short loc_180020C39
0x180020c04  mov     ecx, [rbp+arg_18]
0x180020c07  cmp     cs:dword_18003FE50, ecx
0x180020c0d  jz      short loc_180020C31
0x180020c0f  lea     eax, [rcx-1]
0x180020c12  mov     edx, 0EA60h
0x180020c17  cmp     eax, 0EA5Eh
0x180020c1c  mov     eax, 1B7740h
0x180020c21  cmovbe  ecx, edx
0x180020c24  cmp     ecx, eax
0x180020c26  cmova   ecx, eax
0x180020c29  mov     cs:dword_18003FE50, ecx
0x180020c2f  jmp     short loc_180020C39
0x180020c31  mov     eax, 0FFFDh
0x180020c36  and     bx, ax
0x180020c39  test    bl, 8
0x180020c3c  jz      short loc_180020C47
0x180020c3e  mov     al, byte ptr [rbp+var_28]
0x180020c41  mov     byte ptr cs:word_18003FE7B, al
0x180020c47  test    bl, 4
0x180020c4a  jz      short loc_180020C55
0x180020c4c  mov     al, byte ptr [rbp+var_24]
0x180020c4f  mov     byte ptr cs:word_18003FE7B+1, al
0x180020c55  test    bl, 40h
0x180020c58  jz      short loc_180020C63
0x180020c5a  mov     eax, [rbp+var_20]
0x180020c5d  mov     cs:dword_18003FE6C, eax
0x180020c63  movzx   esi, bx
0x180020c66  and     si, r13w
0x180020c6a  jz      short loc_180020C80
0x180020c6c  mov     ecx, cs:dword_18003FBE4
0x180020c72  mov     eax, [rbp+var_1C]
0x180020c75  imul    rcx, rax
0x180020c79  mov     cs:qword_18003FC80, rcx
0x180020c80  bt      bx, 8
0x180020c85  jnb     short loc_180020C90
0x180020c87  mov     eax, [rbp+var_18]
0x180020c8a  mov     cs:dword_18003FDA0, eax
0x180020c90  lea     r13, WPP_c1878895bf8430c1024ddd3cf0a685b6_Traceguids
0x180020c97  test    r12b, bl
0x180020c9a  jz      short loc_180020CE7
0x180020c9c  cmp     cs:byte_18003FE7D, r15b
0x180020ca3  mov     edi, [rbp+var_14]
0x180020ca6  jnz     short loc_180020CAC
0x180020ca8  test    edi, edi
0x180020caa  jnz     short loc_180020CB1
0x180020cac  test    r14b, r14b
0x180020caf  jz      short loc_180020CE7
0x180020cb1  call    PsmpIsDfssActive
0x180020cb6  test    al, al
0x180020cb8  jnz     short loc_180020CC3
0x180020cba  mov     cs:byte_18003FE7D, dil
0x180020cc1  jmp     short loc_180020CE7
0x180020cc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180020cca  test    [rcx+1Ch], r12b
0x180020cce  jz      short loc_180020CE7
0x180020cd0  cmp     byte ptr [rcx+19h], 3
0x180020cd4  jb      short loc_180020CE7
0x180020cd6  mov     rcx, [rcx+10h]
0x180020cda  mov     edx, 59h ; 'Y'
0x180020cdf  mov     r8, r13
0x180020ce2  call    WPP_SF_
0x180020ce7  lea     rcx, PsmpPolicyLock
0x180020cee  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180020cf4  mov     edi, r15d
0x180020cf7  mov     eax, edi
0x180020cf9  mov     edx, edi
0x180020cfb  imul    rcx, rax, 118h
0x180020d02  lea     rax, PsmpPolicy
0x180020d09  add     rcx, rax
0x180020d0c  call    PsmpReadQuotaValues
0x180020d11  add     edi, r12d
0x180020d14  cmp     edi, 2
0x180020d17  jl      short loc_180020CF7
0x180020d19  test    bx, bx
0x180020d1c  jz      loc_180020ED8
0x180020d22  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d29  mov     di, 4
0x180020d2d  test    [rcx+1Ch], r12b
0x180020d31  jz      loc_180020EAF
0x180020d37  cmp     [rcx+19h], dil
0x180020d3b  jb      short loc_180020D55
0x180020d3d  mov     rcx, [rcx+10h]
0x180020d41  mov     edx, 5Ah ; 'Z'
0x180020d46  mov     r8, r13
0x180020d49  call    WPP_SF_
0x180020d4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d55  test    [rcx+1Ch], r12b
0x180020d59  jz      loc_180020EAF
0x180020d5f  cmp     [rcx+19h], dil
0x180020d63  jb      short loc_180020D85
0x180020d65  movzx   r9d, cs:byte_18003FE7D
0x180020d6d  mov     edx, 5Bh ; '['
0x180020d72  mov     rcx, [rcx+10h]
0x180020d76  mov     r8, r13
0x180020d79  call    WPP_SF_d
0x180020d7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d85  test    [rcx+1Ch], r12b
0x180020d89  jz      loc_180020EAF
0x180020d8f  cmp     [rcx+19h], dil
0x180020d93  jb      short loc_180020DB4
0x180020d95  mov     r9d, cs:dword_18003FE58
0x180020d9c  mov     edx, 5Ch ; '\'
0x180020da1  mov     rcx, [rcx+10h]
0x180020da5  mov     r8, r13
0x180020da8  call    WPP_SF_d
0x180020dad  mov     rcx, cs:WPP_GLOBAL_Control
0x180020db4  test    [rcx+1Ch], r12b
0x180020db8  jz      loc_180020EAF
0x180020dbe  cmp     [rcx+19h], dil
0x180020dc2  jb      short loc_180020DE3
0x180020dc4  mov     r9d, cs:dword_18003FE54
0x180020dcb  mov     edx, 5Dh ; ']'
0x180020dd0  mov     rcx, [rcx+10h]
0x180020dd4  mov     r8, r13
0x180020dd7  call    WPP_SF_d
0x180020ddc  mov     rcx, cs:WPP_GLOBAL_Control
0x180020de3  test    [rcx+1Ch], r12b
0x180020de7  jz      loc_180020EAF
0x180020ded  cmp     [rcx+19h], dil
0x180020df1  jb      short loc_180020E1D
0x180020df3  mov     rcx, [rcx+10h]
0x180020df7  mov     eax, 45E7B273h
0x180020dfc  mul     cs:dword_18003FE50
0x180020e02  mov     r8, r13
0x180020e05  mov     r9d, edx
0x180020e08  mov     edx, 5Eh ; '^'
0x180020e0d  shr     r9d, 0Eh
0x180020e11  call    WPP_SF_d
0x180020e16  mov     rcx, cs:WPP_GLOBAL_Control
0x180020e1d  test    [rcx+1Ch], r12b
0x180020e21  jz      loc_180020EAF
0x180020e27  cmp     [rcx+19h], dil
0x180020e2b  jb      short loc_180020E4D
0x180020e2d  movzx   r9d, byte ptr cs:word_18003FE7B
0x180020e35  mov     edx, 5Fh ; '_'
0x180020e3a  mov     rcx, [rcx+10h]
0x180020e3e  mov     r8, r13
0x180020e41  call    WPP_SF_d
0x180020e46  mov     rcx, cs:WPP_GLOBAL_Control
0x180020e4d  test    [rcx+1Ch], r12b
0x180020e51  jz      short loc_180020EAF
0x180020e53  cmp     [rcx+19h], dil
0x180020e57  jb      short loc_180020E79
0x180020e59  movzx   r9d, byte ptr cs:word_18003FE7B+1
0x180020e61  mov     edx, 60h ; '`'
0x180020e66  mov     rcx, [rcx+10h]
0x180020e6a  mov     r8, r13
0x180020e6d  call    WPP_SF_d
0x180020e72  mov     rcx, cs:WPP_GLOBAL_Control
0x180020e79  test    [rcx+1Ch], r12b
0x180020e7d  jz      short loc_180020EAF
0x180020e7f  cmp     [rcx+19h], dil
0x180020e83  jb      short loc_180020EAF
0x180020e85  mov     rcx, [rcx+10h]
0x180020e89  mov     eax, 10624DD3h
0x180020e8e  mul     cs:dword_18003FE6C
0x180020e94  mov     r8, r13
0x180020e97  mov     r9d, edx
0x180020e9a  mov     edx, 61h ; 'a'
0x180020e9f  shr     r9d, 6
0x180020ea3  call    WPP_SF_d
0x180020ea8  mov     rcx, cs:WPP_GLOBAL_Control
0x180020eaf  test    si, si
0x180020eb2  jz      short loc_180020ED8
0x180020eb4  test    [rcx+1Ch], r12b
0x180020eb8  jz      short loc_180020ED8
  ... truncated ...
```
