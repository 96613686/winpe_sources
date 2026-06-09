# FwppDeepCopyToVerIndependent_FWP_CONDITION_VALUE0

- ea: `0x18003231c`
- end: `0x180032714`
- name: `FwppDeepCopyToVerIndependent_FWP_CONDITION_VALUE0`
- size: `1016`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation`

## callers

- `0x180025630`

## callees

- `0x18000648c`
- `0x180006e40`
- `0x1800071fc`
- `0x180007e38`
- `0x1800101a8`
- `0x180011500`
- `0x18002368c`
- `0x180023710`
- `0x180023794`
- `0x180023b58`
- `0x180024484`
- `0x180024504`
- `0x18003231c`
- `0x18003271c`
- `0x180032818`
- `0x18003295c`
- `0x1800329e8`
- `0x180034118`
- `0x18003416c`
- `0x180034214`
- `0x180035cf4`
- `0x180035d48`
- `0x180035df0`
- `0x180035eec`
- `0x1800367f4`
- `0x1800375d8`
- `0x1800376d4`

## string_xrefs

- `0x1800325c0`: `FwppAllocAndDeepCopyToVerIndependent_FWP_V4_ADDR_AND_MASK`
- `0x1800326b2`: `FwppAllocAndDeepCopyToVerIndependent_FWP_V6_ADDR_AND_MASK`
- `0x180032645`: `FwppAllocAndDeepCopyToVerIndependent_FWP_RANGE0`
- `0x1800326cd`: `FwppDeepCopyToVerIndependent_FWP_CONDITION_VALUE0`
- `0x1800326ee`: `FwppDeepCopyToVerIndependent_FWP_CONDITION_VALUE0`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyToVerIndependent_FWP_CONDITION_VALUE0(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  void *v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rbp
  _QWORD *v32; // r14
  const char *v33; // rdx
  int v34; // ecx
  __int64 v35; // rbp
  __int64 v36; // rbp

  if ( !a1 || !a2 )
  {
    v4 = WfpReportSysErrorAsNtStatus(a1, "FwppDeepCopyToVerIndependent_FWP_CONDITION_VALUE0", 3223453724LL);
LABEL_74:
    if ( !v4 )
      return v4;
    goto LABEL_75;
  }
  v4 = FwppDeepCopyToVerIndependent_FWP_DATA_TYPE();
  if ( v4 )
    goto LABEL_75;
  v5 = *(_DWORD *)a1;
  if ( *(int *)a1 <= 256 )
  {
    if ( v5 != 256 )
    {
      if ( v5 <= 10 )
      {
        if ( v5 == 10 )
        {
          v17 = *(_QWORD *)(a1 + 8);
          if ( !v17 )
            return v4;
          v14 = FwppAllocAndDeepCopyToVerIndependent_double(v17, a2 + 8);
        }
        else
        {
          v6 = v5 - 1;
          if ( v6 )
          {
            v7 = v6 - 1;
            if ( v7 )
            {
              v8 = v7 - 1;
              if ( v8 )
              {
                v9 = v8 - 1;
                if ( v9 )
                {
                  v10 = v9 - 1;
                  if ( v10 )
                  {
                    v11 = v10 - 1;
                    if ( v11 )
                    {
                      v12 = v11 - 1;
                      if ( v12 )
                      {
                        v13 = v12 - 1;
                        if ( v13 )
                        {
                          if ( v13 != 1 )
                            return v4;
                          v14 = FwppDeepCopyToVerIndependent_float(a1 + 8, a2 + 8);
                        }
                        else
                        {
                          v15 = *(_QWORD *)(a1 + 8);
                          if ( !v15 )
                            return v4;
                          v14 = FwppAllocAndDeepCopyToVerIndependent_INT64(v15, a2 + 8);
                        }
                      }
                      else
                      {
                        v14 = FwppDeepCopyToVerIndependent_INT32(a1 + 8, a2 + 8);
                      }
                    }
                    else
                    {
                      v14 = FwppDeepCopyToVerIndependent_INT16(a1 + 8, a2 + 8);
                    }
                  }
                  else
                  {
                    v14 = FwppDeepCopyToVerIndependent_INT8(a1 + 8, a2 + 8);
                  }
                }
                else
                {
                  v16 = *(_QWORD *)(a1 + 8);
                  if ( !v16 )
                    return v4;
                  v14 = FwppAllocAndDeepCopyToVerIndependent_UINT64(v16, a2 + 8);
                }
              }
              else
              {
                v14 = FwppDeepCopyToVerIndependent_UINT32(a1 + 8, a2 + 8);
              }
            }
            else
            {
              v14 = FwppDeepCopyToVerIndependent_UINT16(a1 + 8, a2 + 8);
            }
          }
          else
          {
            v14 = FwppDeepCopyToVerIndependent_UINT8(a1 + 8, a2 + 8);
          }
        }
        goto LABEL_18;
      }
      v18 = v5 - 11;
      if ( v18 )
      {
        v19 = v18 - 1;
        if ( !v19 )
          goto LABEL_44;
        v20 = v19 - 1;
        if ( !v20 )
        {
          v29 = *(void **)(a1 + 8);
          if ( !v29 )
            return v4;
          v14 = FwppAllocAndDeepCopyToVerIndependent_SID(v29, (_QWORD *)(a2 + 8));
          goto LABEL_18;
        }
        v21 = v20 - 1;
        if ( !v21 )
        {
LABEL_44:
          v27 = *(_QWORD *)(a1 + 8);
          if ( !v27 )
            return v4;
          v14 = FwppAllocAndDeepCopyToVerIndependent_FWP_BYTE_BLOB(v27, a2 + 8);
          goto LABEL_18;
        }
        v22 = v21 - 1;
        if ( v22 )
        {
          v23 = v22 - 1;
          if ( v23 )
          {
            v24 = v23 - 1;
            if ( v24 )
            {
              if ( v24 != 1 )
                return v4;
              v25 = *(_QWORD *)(a1 + 8);
              if ( !v25 )
                return v4;
              v14 = FwppAllocAndDeepCopyToVerIndependent_FWP_BYTE_ARRAY6(v25, a2 + 8);
            }
            else
            {
              v26 = *(_QWORD *)(a1 + 8);
              if ( !v26 )
                return v4;
              v14 = FwppAllocAndDeepCopyToVerIndependent_WSTR(v26, a2 + 8);
            }
            goto LABEL_18;
          }
          goto LABEL_44;
        }
        v28 = *(_QWORD *)(a1 + 8);
        if ( !v28 )
          return v4;
        v14 = FwppAllocAndDeepCopyToVerIndependent_FWP_TOKEN_INFORMATION(v28, a2 + 8);
      }
      else
      {
        v30 = *(_QWORD *)(a1 + 8);
        if ( !v30 )
          return v4;
        v14 = FwppAllocAndDeepCopyToVerIndependent_FWP_BYTE_ARRAY16(v30, a2 + 8);
      }
LABEL_18:
      v4 = v14;
      if ( !v14 )
        return v4;
      goto LABEL_75;
    }
    v31 = *(_QWORD *)(a1 + 8);
    if ( !v31 )
      return v4;
    v32 = (_QWORD *)(a2 + 8);
    if ( a2 != -8 )
    {
      v4 = WfpPoolAllocNonPaged(8u);
      if ( !v4 )
      {
        MEMORY[0] = 0;
        v4 = FwppDeepCopyToVerIndependent_FWP_V4_ADDR_AND_MASK(v31, 0);
        if ( !v4 )
        {
LABEL_56:
          *v32 = 0;
          return v4;
        }
      }
      FwppDeepFree_FWPM_NET_EVENT_CAPABILITY_DROP0(0);
      v33 = "FwppAllocAndDeepCopyToVerIndependent_FWP_V4_ADDR_AND_MASK";
      goto LABEL_71;
    }
    goto LABEL_72;
  }
  v34 = v5 - 257;
  if ( v34 )
  {
    if ( v34 != 1 )
      return v4;
    v35 = *(_QWORD *)(a1 + 8);
    if ( !v35 )
      return v4;
    v32 = (_QWORD *)(a2 + 8);
    if ( a2 != -8 )
    {
      v4 = WfpPoolAllocNonPaged(0x20u);
      if ( !v4 )
      {
        MEMORY[0] = 0;
        MEMORY[0x10] = 0;
        v4 = FwppDeepCopyToVerIndependent_FWP_RANGE0(v35, 0);
        if ( !v4 )
          goto LABEL_56;
      }
      FwppDeepFree_FWP_RANGE0(0);
      v33 = "FwppAllocAndDeepCopyToVerIndependent_FWP_RANGE0";
      goto LABEL_71;
    }
LABEL_72:
    v4 = 0;
    goto LABEL_74;
  }
  v36 = *(_QWORD *)(a1 + 8);
  if ( !v36 )
    return v4;
  if ( a2 == -8 )
    goto LABEL_72;
  v4 = WfpPoolAllocNonPaged(0x11u);
  if ( !v4 )
  {
    MEMORY[0] = 0;
    MEMORY[0x10] = 0;
    v4 = FwppDeepCopyToVerIndependent_FWP_V6_ADDR_AND_MASK(v36, 0);
    if ( !v4 )
    {
      *(_QWORD *)(a2 + 8) = 0;
      goto LABEL_74;
    }
  }
  FwppDeepFree_FWPM_NET_EVENT_CAPABILITY_DROP0(0);
  v33 = "FwppAllocAndDeepCopyToVerIndependent_FWP_V6_ADDR_AND_MASK";
LABEL_71:
  WfpReportError(v4, v33);
LABEL_75:
  FwppDeepFreeContentsOnly_FWP_CONDITION_VALUE0(a2);
  if ( v4 )
    WfpReportError(v4, "FwppDeepCopyToVerIndependent_FWP_CONDITION_VALUE0");
  return v4;
}

```

## disassembly

```asm
0x18003231c  mov     [rsp+arg_8], rbx
0x180032321  mov     [rsp+arg_10], rbp
0x180032326  push    rsi
0x180032327  push    rdi
0x180032328  push    r14
0x18003232a  sub     rsp, 20h
0x18003232e  mov     rsi, rdx
0x180032331  mov     rdi, rcx
0x180032334  test    rcx, rcx
0x180032337  jz      loc_1800326C7
0x18003233d  test    rdx, rdx
0x180032340  jz      loc_1800326C7
0x180032346  call    FwppDeepCopyToVerIndependent_FWP_DATA_TYPE
0x18003234b  mov     rbx, rax
0x18003234e  test    rax, rax
0x180032351  jnz     loc_1800326E1
0x180032357  mov     ecx, [rdi]
0x180032359  mov     eax, 100h
0x18003235e  cmp     ecx, eax
0x180032360  jg      loc_1800325CC
0x180032366  jz      loc_18003255B
0x18003236c  cmp     ecx, 0Ah
0x18003236f  jg      loc_180032485
0x180032375  jz      loc_18003246A
0x18003237b  sub     ecx, 1
0x18003237e  jz      loc_180032458
0x180032384  sub     ecx, 1
0x180032387  jz      loc_180032446
0x18003238d  sub     ecx, 1
0x180032390  jz      loc_180032437
0x180032396  sub     ecx, 1
0x180032399  jz      loc_18003241F
0x18003239f  sub     ecx, 1
0x1800323a2  jz      short loc_180032410
0x1800323a4  sub     ecx, 1
0x1800323a7  jz      short loc_180032401
0x1800323a9  sub     ecx, 1
0x1800323ac  jz      short loc_1800323F2
0x1800323ae  sub     ecx, 1
0x1800323b1  jz      short loc_1800323DA
0x1800323b3  cmp     ecx, 1
0x1800323b6  jnz     loc_1800326FD
0x1800323bc  lea     rdx, [rsi+8]
0x1800323c0  lea     rcx, [rdi+8]
0x1800323c4  call    FwppDeepCopyToVerIndependent_float
0x1800323c9  mov     rbx, rax
0x1800323cc  test    rax, rax
0x1800323cf  jnz     loc_1800326E1
0x1800323d5  jmp     loc_1800326FD
0x1800323da  mov     rcx, [rdi+8]
0x1800323de  test    rcx, rcx
0x1800323e1  jz      loc_1800326FD
0x1800323e7  lea     rdx, [rsi+8]
0x1800323eb  call    FwppAllocAndDeepCopyToVerIndependent_INT64
0x1800323f0  jmp     short loc_1800323C9
0x1800323f2  lea     rdx, [rsi+8]
0x1800323f6  lea     rcx, [rdi+8]
0x1800323fa  call    FwppDeepCopyToVerIndependent_INT32
0x1800323ff  jmp     short loc_1800323C9
0x180032401  lea     rdx, [rsi+8]
0x180032405  lea     rcx, [rdi+8]
0x180032409  call    FwppDeepCopyToVerIndependent_INT16
0x18003240e  jmp     short loc_1800323C9
0x180032410  lea     rdx, [rsi+8]
0x180032414  lea     rcx, [rdi+8]
0x180032418  call    FwppDeepCopyToVerIndependent_INT8
0x18003241d  jmp     short loc_1800323C9
0x18003241f  mov     rcx, [rdi+8]
0x180032423  test    rcx, rcx
0x180032426  jz      loc_1800326FD
0x18003242c  lea     rdx, [rsi+8]
0x180032430  call    FwppAllocAndDeepCopyToVerIndependent_UINT64
0x180032435  jmp     short loc_1800323C9
0x180032437  lea     rdx, [rsi+8]
0x18003243b  lea     rcx, [rdi+8]
0x18003243f  call    FwppDeepCopyToVerIndependent_UINT32
0x180032444  jmp     short loc_1800323C9
0x180032446  lea     rdx, [rsi+8]
0x18003244a  lea     rcx, [rdi+8]
0x18003244e  call    FwppDeepCopyToVerIndependent_UINT16
0x180032453  jmp     loc_1800323C9
0x180032458  lea     rdx, [rsi+8]
0x18003245c  lea     rcx, [rdi+8]
0x180032460  call    FwppDeepCopyToVerIndependent_UINT8
0x180032465  jmp     loc_1800323C9
0x18003246a  mov     rcx, [rdi+8]
0x18003246e  test    rcx, rcx
0x180032471  jz      loc_1800326FD
0x180032477  lea     rdx, [rsi+8]
0x18003247b  call    FwppAllocAndDeepCopyToVerIndependent_double
0x180032480  jmp     loc_1800323C9
0x180032485  sub     ecx, 0Bh
0x180032488  jz      loc_180032540
0x18003248e  sub     ecx, 1
0x180032491  jz      short loc_1800324EF
0x180032493  sub     ecx, 1
0x180032496  jz      loc_180032525
0x18003249c  sub     ecx, 1
0x18003249f  jz      short loc_1800324EF
0x1800324a1  sub     ecx, 1
0x1800324a4  jz      short loc_18003250A
0x1800324a6  sub     ecx, 1
0x1800324a9  jz      short loc_1800324EF
0x1800324ab  sub     ecx, 1
0x1800324ae  jz      short loc_1800324D4
0x1800324b0  cmp     ecx, 1
0x1800324b3  jnz     loc_1800326FD
0x1800324b9  mov     rcx, [rdi+8]
0x1800324bd  test    rcx, rcx
0x1800324c0  jz      loc_1800326FD
0x1800324c6  lea     rdx, [rsi+8]
0x1800324ca  call    FwppAllocAndDeepCopyToVerIndependent_FWP_BYTE_ARRAY6
0x1800324cf  jmp     loc_1800323C9
0x1800324d4  mov     rcx, [rdi+8]
0x1800324d8  test    rcx, rcx
0x1800324db  jz      loc_1800326FD
0x1800324e1  lea     rdx, [rsi+8]
0x1800324e5  call    FwppAllocAndDeepCopyToVerIndependent_WSTR
0x1800324ea  jmp     loc_1800323C9
0x1800324ef  mov     rcx, [rdi+8]
0x1800324f3  test    rcx, rcx
0x1800324f6  jz      loc_1800326FD
0x1800324fc  lea     rdx, [rsi+8]
0x180032500  call    FwppAllocAndDeepCopyToVerIndependent_FWP_BYTE_BLOB
0x180032505  jmp     loc_1800323C9
0x18003250a  mov     rcx, [rdi+8]
0x18003250e  test    rcx, rcx
0x180032511  jz      loc_1800326FD
0x180032517  lea     rdx, [rsi+8]
0x18003251b  call    FwppAllocAndDeepCopyToVerIndependent_FWP_TOKEN_INFORMATION
0x180032520  jmp     loc_1800323C9
0x180032525  mov     rcx, [rdi+8]; SourceSid
0x180032529  test    rcx, rcx
0x18003252c  jz      loc_1800326FD
0x180032532  lea     rdx, [rsi+8]
0x180032536  call    FwppAllocAndDeepCopyToVerIndependent_SID
0x18003253b  jmp     loc_1800323C9
0x180032540  mov     rcx, [rdi+8]
0x180032544  test    rcx, rcx
0x180032547  jz      loc_1800326FD
0x18003254d  lea     rdx, [rsi+8]
0x180032551  call    FwppAllocAndDeepCopyToVerIndependent_FWP_BYTE_ARRAY16
0x180032556  jmp     loc_1800323C9
0x18003255b  mov     rbp, [rdi+8]
0x18003255f  test    rbp, rbp
0x180032562  jz      loc_1800326FD
0x180032568  lea     r14, [rsi+8]
0x18003256c  mov     [rsp+38h+arg_0], 0
0x180032575  test    r14, r14
0x180032578  jz      loc_1800326C3
0x18003257e  lea     r8, [rsp+38h+arg_0]
0x180032583  mov     ecx, 8; dwBytes
0x180032588  call    WfpPoolAllocNonPaged
0x18003258d  mov     rdi, [rsp+38h+arg_0]
0x180032592  mov     rbx, rax
0x180032595  test    rax, rax
0x180032598  jnz     short loc_1800325B8
0x18003259a  mov     rdx, rdi
0x18003259d  mov     [rdi], rax
0x1800325a0  mov     rcx, rbp
0x1800325a3  call    FwppDeepCopyToVerIndependent_FWP_V4_ADDR_AND_MASK
0x1800325a8  mov     rbx, rax
0x1800325ab  test    rax, rax
0x1800325ae  jnz     short loc_1800325B8
0x1800325b0  mov     [r14], rdi
0x1800325b3  jmp     loc_1800326FD
0x1800325b8  mov     rcx, rdi
0x1800325bb  call    FwppDeepFree_FWPM_NET_EVENT_CAPABILITY_DROP0
0x1800325c0  lea     rdx, aFwppallocandde_18; "FwppAllocAndDeepCopyToVerIndependent_FW"...
0x1800325c7  jmp     loc_1800326B9
0x1800325cc  sub     ecx, 101h
0x1800325d2  jz      short loc_18003264E
0x1800325d4  cmp     ecx, 1
0x1800325d7  jnz     loc_1800326FD
0x1800325dd  mov     rbp, [rdi+8]
0x1800325e1  test    rbp, rbp
0x1800325e4  jz      loc_1800326FD
0x1800325ea  lea     r14, [rsi+8]
0x1800325ee  mov     [rsp+38h+arg_0], 0
0x1800325f7  test    r14, r14
0x1800325fa  jz      loc_1800326C3
0x180032600  lea     r8, [rsp+38h+arg_0]
0x180032605  mov     ecx, 20h ; ' '; dwBytes
0x18003260a  call    WfpPoolAllocNonPaged
0x18003260f  mov     rdi, [rsp+38h+arg_0]
0x180032614  mov     rbx, rax
0x180032617  test    rax, rax
0x18003261a  jnz     short loc_18003263D
0x18003261c  xorps   xmm0, xmm0
0x18003261f  mov     rdx, rdi
0x180032622  movups  xmmword ptr [rdi], xmm0
0x180032625  mov     rcx, rbp
0x180032628  movups  xmmword ptr [rdi+10h], xmm0
0x18003262c  call    FwppDeepCopyToVerIndependent_FWP_RANGE0
0x180032631  mov     rbx, rax
0x180032634  test    rax, rax
0x180032637  jz      loc_1800325B0
0x18003263d  mov     rcx, rdi
0x180032640  call    FwppDeepFree_FWP_RANGE0
0x180032645  lea     rdx, aFwppallocandde_31; "FwppAllocAndDeepCopyToVerIndependent_FW"...
0x18003264c  jmp     short loc_1800326B9
0x18003264e  mov     rbp, [rdi+8]
0x180032652  test    rbp, rbp
0x180032655  jz      loc_1800326FD
0x18003265b  lea     r14, [rsi+8]
0x18003265f  mov     [rsp+38h+arg_0], 0
0x180032668  test    r14, r14
0x18003266b  jz      short loc_1800326C3
0x18003266d  lea     r8, [rsp+38h+arg_0]
0x180032672  mov     ecx, 11h; dwBytes
0x180032677  call    WfpPoolAllocNonPaged
0x18003267c  mov     rdi, [rsp+38h+arg_0]
0x180032681  mov     rbx, rax
0x180032684  test    rax, rax
0x180032687  jnz     short loc_1800326AA
0x180032689  xorps   xmm0, xmm0
0x18003268c  mov     rdx, rdi
0x18003268f  movups  xmmword ptr [rdi], xmm0
0x180032692  mov     rcx, rbp
0x180032695  mov     [rdi+10h], al
0x180032698  call    FwppDeepCopyToVerIndependent_FWP_V6_ADDR_AND_MASK
0x18003269d  mov     rbx, rax
0x1800326a0  test    rax, rax
0x1800326a3  jnz     short loc_1800326AA
0x1800326a5  mov     [r14], rdi
0x1800326a8  jmp     short loc_1800326DC
0x1800326aa  mov     rcx, rdi
0x1800326ad  call    FwppDeepFree_FWPM_NET_EVENT_CAPABILITY_DROP0
0x1800326b2  lea     rdx, aFwppallocandde_5; "FwppAllocAndDeepCopyToVerIndependent_FW"...
0x1800326b9  mov     rcx, rbx
0x1800326bc  call    WfpReportError
0x1800326c1  jmp     short loc_1800326E1
0x1800326c3  xor     ebx, ebx
0x1800326c5  jmp     short loc_1800326DC
0x1800326c7  mov     r8d, 0C022001Ch
0x1800326cd  lea     rdx, aFwppdeepcopyto_7; "FwppDeepCopyToVerIndependent_FWP_CONDIT"...
0x1800326d4  call    WfpReportSysErrorAsNtStatus
0x1800326d9  mov     rbx, rax
0x1800326dc  test    rbx, rbx
0x1800326df  jz      short loc_1800326FD
0x1800326e1  mov     rcx, rsi
0x1800326e4  call    FwppDeepFreeContentsOnly_FWP_CONDITION_VALUE0
0x1800326e9  test    rbx, rbx
0x1800326ec  jz      short loc_1800326FD
0x1800326ee  lea     rdx, aFwppdeepcopyto_7; "FwppDeepCopyToVerIndependent_FWP_CONDIT"...
0x1800326f5  mov     rcx, rbx
0x1800326f8  call    WfpReportError
0x1800326fd  mov     rbp, [rsp+38h+arg_10]
0x180032702  mov     rax, rbx
0x180032705  mov     rbx, [rsp+38h+arg_8]
0x18003270a  add     rsp, 20h
0x18003270e  pop     r14
0x180032710  pop     rdi
0x180032711  pop     rsi
0x180032712  retn
```
