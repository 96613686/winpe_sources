# HandleDialOutLinkUp

- ea: `0x180010cd8`
- end: `0x180011213`
- name: `HandleDialOutLinkUp`
- size: `1339`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180010260`

## callees

- `0x18000eb50`
- `0x18000ec98`
- `0x180010cd8`
- `0x180011790`
- `0x18003e450`
- `0x18003f1a4`
- `0x18003f7c8`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `iprtprio!ComputeRouteMetric` at `0x180010efc`
- `iprtprio!ComputeRouteMetric` at `0x180011021`
- `iprtprio!ComputeRouteMetric` at `0x180011118`
- `iprtprio!ComputeRouteMetric` at `0x180010efc`
- `iprtprio!ComputeRouteMetric` at `0x180011021`
- `iprtprio!ComputeRouteMetric` at `0x180011118`

## string_xrefs

- `0x180010e22`: `DialOutLinkUp: Connection notification for 0x%x %d.%d.%d.%d/%d.%d.%d.%d %d.%d.%d.%d`
- `0x180010f7e`: `HandleDialOutLinkUp: Couldnt add server route for 0x%x`
- `0x180011090`: `HandleDialOutLinkUp: Couldnt add default route for 0x%x`
- `0x180011190`: `HandleDialOutLinkUp: Couldnt add subnet route for 0x%x`

## pseudocode

```c
__int64 __fastcall HandleDialOutLinkUp(int a1, __int64 a2)
{
  int v3; // esi
  __int64 v4; // rdx
  __int64 v5; // rcx
  unsigned int *v6; // rbx
  __int64 result; // rax
  __int64 v8; // r13
  int v9; // ecx
  int v10; // edx
  int v11; // r8d
  int v12; // r15d
  int v13; // r10d
  int v14; // r11d
  int v15; // ebx
  int v16; // edi
  int v17; // eax
  __int64 v18; // r9
  __int128 *v19; // r9
  int v20; // eax
  __int128 *v21; // r9
  int v22; // eax
  int v23; // ecx
  __int64 v24; // r8
  __int128 *v25; // r9
  char v26; // cl
  int v27; // edx
  int v28; // eax
  int v29; // eax
  int v30; // ecx
  __int64 v31; // r8
  int v32[2]; // [rsp+20h] [rbp-E0h]
  int v33[2]; // [rsp+28h] [rbp-D8h]
  int v34; // [rsp+70h] [rbp-90h]
  unsigned int v35; // [rsp+80h] [rbp-80h]
  int v37[2]; // [rsp+90h] [rbp-70h] BYREF
  int v38; // [rsp+98h] [rbp-68h]
  int v39; // [rsp+9Ch] [rbp-64h]
  __int64 v40; // [rsp+A0h] [rbp-60h]
  __int64 v41; // [rsp+A8h] [rbp-58h]
  int v42; // [rsp+B0h] [rbp-50h]
  int v43; // [rsp+C0h] [rbp-40h]
  int v44; // [rsp+C4h] [rbp-3Ch]
  int v45; // [rsp+C8h] [rbp-38h]
  int v46; // [rsp+CCh] [rbp-34h]
  int v47; // [rsp+D0h] [rbp-30h]
  __int64 v48; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v49; // [rsp+E8h] [rbp-18h] BYREF
  int v50; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v51; // [rsp+FCh] [rbp-4h]
  __int128 v52; // [rsp+10Ch] [rbp+Ch]
  int v53; // [rsp+11Ch] [rbp+1Ch]
  int v54; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v55[2044]; // [rsp+124h] [rbp+24h] BYREF

  v48 = 0;
  v3 = a1;
  memset_0(v37, 0, 0x48u);
  v54 = 0;
  memset_0(v55, 0, sizeof(v55));
  v4 = *(unsigned int *)(a2 + 8);
  v5 = a2 + 32;
  v50 = 0;
  v53 = 0;
  v6 = (unsigned int *)(a2 + 16);
  v51 = 0;
  v52 = 0;
  v49 = 0;
  if ( v3 )
  {
    result = CreateDialOutInterfaceV4(v5, v4, *v6, *(unsigned int *)(a2 + 20), *(_DWORD *)(a2 + 24), &v48);
    v8 = v48;
    v35 = result;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v9 = *(unsigned __int8 *)(a2 + 19);
      v10 = *(unsigned __int8 *)(a2 + 18);
      v11 = *(unsigned __int8 *)(a2 + 17);
      v12 = *(unsigned __int8 *)(a2 + 25);
      v13 = *(unsigned __int8 *)(a2 + 24);
      v14 = *(unsigned __int8 *)(a2 + 23);
      v15 = *(unsigned __int8 *)(a2 + 22);
      v16 = *(unsigned __int8 *)(a2 + 21);
      v17 = *(unsigned __int8 *)(a2 + 20);
      v18 = *(unsigned __int8 *)(a2 + 16);
      v34 = *(unsigned __int8 *)(a2 + 27);
      LOWORD(v54) = 0;
      LOWORD(v50) = 0;
      v33[0] = v10;
      v32[0] = v11;
      FormatRRASErrorString(
        &v54,
        L"DialOutLinkUp: Connection notification for 0x%x %d.%d.%d.%d/%d.%d.%d.%d %d.%d.%d.%d",
        *(unsigned int *)(a2 + 8),
        v18,
        *(_QWORD *)v32,
        *(_QWORD *)v33,
        v9,
        v17,
        v16,
        v15,
        v14,
        v13,
        v12,
        *(unsigned __int8 *)(a2 + 26),
        v34);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v19 = &v49;
        if ( v8 != -688 )
          LODWORD(v19) = v8 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v54,
          (_DWORD)v19,
          *(_QWORD *)(v8 + 72),
          (__int64)&v50);
      }
      result = v35;
      v6 = (unsigned int *)(a2 + 16);
      v3 = a1;
    }
  }
  else
  {
    result = CreateDialOutInterfaceV6(v5, v4, &v48);
    v8 = v48;
  }
  if ( !(_DWORD)result )
  {
    if ( v3 )
    {
      if ( *(_DWORD *)(v8 + 672) )
      {
        v37[1] = -1;
        v39 = *(_DWORD *)(v8 + 672);
        v37[0] = *(_DWORD *)(v8 + 672);
        v43 = *(_DWORD *)(v8 + 16);
        v41 = 1;
        v42 = 0;
        v20 = ComputeRouteMetric(3);
        v47 = 3;
        v46 = v20;
        v44 = 3;
        v45 = 3;
        v40 = 0;
        v38 = 0;
        if ( (unsigned int)AddSingleRoute(
                             *(_DWORD *)(v8 + 16),
                             (int)v37,
                             *(_DWORD *)(*(_QWORD *)(v8 + 712) + 4LL),
                             0,
                             1,
                             1,
                             1,
                             *(_DWORD *)(v8 + 516),
                             (struct _GUID *)(v8 + 688),
                             0) )
        {
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          {
            LOWORD(v54) = 0;
            LOWORD(v50) = 0;
            FormatRRASErrorString(
              &v54,
              L"HandleDialOutLinkUp: Couldnt add server route for 0x%x",
              *(unsigned int *)(v8 + 16));
            if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
            {
              v21 = &v49;
              if ( v8 != -688 )
                LODWORD(v21) = v8 + 688;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasRtrmgrParamTraceInfo,
                (unsigned int)&v54,
                (_DWORD)v21,
                *(_QWORD *)(v8 + 72),
                (__int64)&v50);
            }
          }
        }
      }
      if ( *(_DWORD *)(a2 + 28) )
      {
        ChangeDefaultRouteMetrics(1, *(unsigned int *)(v8 + 516), v8 + 688);
        *(_DWORD *)(v8 + 520) = 1;
        v39 = *v6;
        v43 = *(_DWORD *)(a2 + 8);
        *(_QWORD *)v37 = 0;
        v41 = 1;
        v42 = 0;
        v22 = ComputeRouteMetric(2);
        v23 = *(_DWORD *)(a2 + 8);
        v46 = v22;
        v47 = 3;
        v44 = 3;
        v45 = 3;
        v40 = 0xFFFFFFFFLL;
        v38 = 0;
        if ( !(unsigned int)AddSingleRoute(v23, (int)v37, -1, 0, 1, 0, 0, v3, (struct _GUID *)(v8 + 688), 0) )
          return 0;
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
          return 0;
        v24 = *(unsigned int *)(a2 + 8);
        LOWORD(v54) = 0;
        LOWORD(v50) = 0;
        FormatRRASErrorString(&v54, L"HandleDialOutLinkUp: Couldnt add default route for 0x%x", v24);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
          return 0;
        v25 = &v49;
        if ( v8 != -688 )
          LODWORD(v25) = v8 + 688;
      }
      else
      {
        v26 = *(_BYTE *)v6;
        if ( *(char *)v6 < 0 )
        {
          if ( (v26 & 0xC0) == 0x80 )
          {
            v27 = 0xFFFF;
          }
          else
          {
            v27 = -1;
            if ( (v26 & 0xE0) == 0xC0 )
              v27 = 0xFFFFFF;
          }
        }
        else
        {
          v27 = 255;
        }
        v28 = v27 & *v6;
        v39 = *v6;
        v37[0] = v28;
        v43 = *(_DWORD *)(a2 + 8);
        v37[1] = v27;
        v41 = 1;
        v42 = 0;
        v29 = ComputeRouteMetric(2);
        v30 = *(_DWORD *)(a2 + 8);
        v46 = v29;
        v47 = 3;
        v44 = 3;
        v45 = 2;
        v40 = 0xFFFFFFFFLL;
        v38 = 0;
        if ( !(unsigned int)AddSingleRoute(v30, (int)v37, -1, 0, 1, 0, 0, v3, (struct _GUID *)(v8 + 688), 0) )
          return 0;
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
          return 0;
        v31 = *(unsigned int *)(a2 + 8);
        LOWORD(v54) = 0;
        LOWORD(v50) = 0;
        FormatRRASErrorString(&v54, L"HandleDialOutLinkUp: Couldnt add subnet route for 0x%x", v31);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
          return 0;
        v25 = &v49;
        if ( v8 != -688 )
          LODWORD(v25) = v8 + 688;
      }
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v54,
        (_DWORD)v25,
        *(_QWORD *)(v8 + 72),
        (__int64)&v50);
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180010cd8  mov     [rsp-8+arg_10], rbx
0x180010cdd  push    rbp
0x180010cde  push    rsi
0x180010cdf  push    rdi
0x180010ce0  push    r12
0x180010ce2  push    r13
0x180010ce4  push    r14
0x180010ce6  push    r15
0x180010ce8  lea     rbp, [rsp-830h]
0x180010cf0  sub     rsp, 930h
0x180010cf7  mov     rax, cs:__security_cookie
0x180010cfe  xor     rax, rsp
0x180010d01  mov     [rbp+860h+var_40], rax
0x180010d08  xor     r14d, r14d
0x180010d0b  mov     [rbp+860h+var_8DC], ecx
0x180010d0e  mov     r12, rdx
0x180010d11  mov     [rbp+860h+var_880], r14
0x180010d15  mov     esi, ecx
0x180010d17  xor     edx, edx; Val
0x180010d19  lea     rcx, [rbp+860h+var_8D0]; void *
0x180010d1d  lea     r8d, [r14+48h]; Size
0x180010d21  call    memset_0
0x180010d26  xor     edx, edx; Val
0x180010d28  mov     [rbp+860h+var_840], r14d
0x180010d2c  mov     r8d, 7FCh; Size
0x180010d32  lea     rcx, [rbp+860h+var_83C]; void *
0x180010d36  call    memset_0
0x180010d3b  mov     edx, [r12+8]
0x180010d40  lea     rcx, [r12+20h]
0x180010d45  xorps   xmm0, xmm0
0x180010d48  mov     [rbp+860h+var_868], r14d
0x180010d4c  xor     eax, eax
0x180010d4e  lea     rdi, [r12+14h]
0x180010d53  mov     [rbp+860h+var_844], eax
0x180010d56  lea     rbx, [r12+10h]
0x180010d5b  movups  [rbp+860h+var_864], xmm0
0x180010d5f  movups  [rbp+860h+var_854], xmm0
0x180010d63  movups  [rbp+860h+var_878], xmm0
0x180010d67  test    esi, esi
0x180010d69  jz      loc_180010E91
0x180010d6f  mov     r9d, [rdi]
0x180010d72  lea     rax, [rbp+860h+var_880]
0x180010d76  mov     r8d, [rbx]
0x180010d79  mov     qword ptr [rsp+960h+var_938], rax
0x180010d7e  mov     eax, [r12+18h]
0x180010d83  mov     [rsp+960h+var_940], eax
0x180010d87  call    CreateDialOutInterfaceV4
0x180010d8c  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180010d93  mov     r13, [rbp+860h+var_880]
0x180010d97  mov     [rbp+860h+var_8E0], eax
0x180010d9a  jge     loc_180010E9E
0x180010da0  movzx   ecx, byte ptr [r12+13h]
0x180010da6  movzx   edx, byte ptr [r12+12h]
0x180010dac  movzx   r8d, byte ptr [r12+11h]
0x180010db2  movzx   esi, byte ptr [r12+1Bh]
0x180010db8  movzx   r15d, byte ptr [r12+19h]
0x180010dbe  movzx   r10d, byte ptr [r12+18h]
0x180010dc4  movzx   r11d, byte ptr [r12+17h]
0x180010dca  movzx   ebx, byte ptr [r12+16h]
0x180010dd0  movzx   edi, byte ptr [r12+15h]
0x180010dd6  movzx   eax, byte ptr [r12+14h]
0x180010ddc  movzx   r9d, byte ptr [r12+10h]
0x180010de2  mov     [rsp+960h+var_8F0], esi
0x180010de6  mov     word ptr [rbp+860h+var_840], r14w
0x180010deb  mov     word ptr [rbp+860h+var_868], r14w
0x180010df0  movzx   r14d, byte ptr [r12+1Ah]
0x180010df6  mov     [rsp+960h+var_8F8], r14d
0x180010dfb  mov     [rsp+960h+var_900], r15d
0x180010e00  mov     [rsp+960h+var_908], r10d
0x180010e05  mov     [rsp+960h+var_910], r11d
0x180010e0a  mov     dword ptr [rsp+960h+var_918], ebx
0x180010e0e  mov     dword ptr [rsp+960h+var_920], edi
0x180010e12  mov     [rsp+960h+var_928], eax
0x180010e16  mov     [rsp+960h+var_930], ecx
0x180010e1a  lea     rcx, [rbp+860h+var_840]
0x180010e1e  mov     [rsp+960h+var_938], edx
0x180010e22  lea     rdx, aDialoutlinkupC; "DialOutLinkUp: Connection notification "...
0x180010e29  mov     [rsp+960h+var_940], r8d
0x180010e2e  mov     r8d, [r12+8]
0x180010e33  call    FormatRRASErrorString
0x180010e38  xor     r14d, r14d
0x180010e3b  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180010e42  jge     short loc_180010E7F
0x180010e44  lea     rax, [r13+2B0h]
0x180010e4b  test    rax, rax
0x180010e4e  lea     r9, [rbp+860h+var_878]
0x180010e52  lea     r8, [rbp+860h+var_840]
0x180010e56  cmovnz  r9, rax
0x180010e5a  lea     rdx, RasRtrmgrParamTraceInfo
0x180010e61  lea     rax, [rbp+860h+var_868]
0x180010e65  mov     qword ptr [rsp+960h+var_938], rax
0x180010e6a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180010e71  mov     rax, [r13+48h]
0x180010e75  mov     qword ptr [rsp+960h+var_940], rax
0x180010e7a  call    McTemplateU0zjzz_EventWriteTransfer
0x180010e7f  mov     eax, [rbp+860h+var_8E0]
0x180010e82  lea     rbx, [r12+10h]
0x180010e87  mov     esi, [rbp+860h+var_8DC]
0x180010e8a  lea     rdi, [r12+14h]
0x180010e8f  jmp     short loc_180010E9E
0x180010e91  lea     r8, [rbp+860h+var_880]
0x180010e95  call    CreateDialOutInterfaceV6
0x180010e9a  mov     r13, [rbp+860h+var_880]
0x180010e9e  test    eax, eax
0x180010ea0  jnz     loc_1800111E9
0x180010ea6  test    esi, esi
0x180010ea8  jz      loc_1800111E7
0x180010eae  mov     r8d, [rdi]
0x180010eb1  mov     rcx, r13
0x180010eb4  mov     edx, [rbx]
0x180010eb6  call    _guard_check_icall_nop
0x180010ebb  mov     r15d, 1
0x180010ec1  cmp     [r13+2A0h], r14d
0x180010ec8  jz      loc_180010FD4
0x180010ece  mov     [rbp+860h+var_8D0+4], 0FFFFFFFFh
0x180010ed5  lea     ecx, [r15+2]
0x180010ed9  mov     eax, [r13+2A0h]
0x180010ee0  mov     [rbp+860h+var_8C4], eax
0x180010ee3  mov     eax, [r13+2A0h]
0x180010eea  mov     [rbp+860h+var_8D0], eax
0x180010eed  mov     eax, [r13+10h]
0x180010ef1  mov     [rbp+860h+var_8A0], eax
0x180010ef4  mov     [rbp+860h+var_8B8], r15
0x180010ef8  mov     [rbp+860h+var_8B0], r14d
0x180010efc  call    cs:__imp_ComputeRouteMetric
0x180010f02  mov     [rbp+860h+var_890], 3
0x180010f09  lea     rdi, [r13+2B0h]
0x180010f10  mov     [rbp+860h+var_894], eax
0x180010f13  lea     rdx, [rbp+860h+var_8D0]; int
0x180010f17  mov     [rbp+860h+var_89C], 3
0x180010f1e  xor     r9d, r9d; int
0x180010f21  mov     [rbp+860h+var_898], 3
0x180010f28  mov     [rbp+860h+var_8C0], 0
0x180010f30  mov     [rbp+860h+var_8C8], r14d
0x180010f34  mov     r8, [r13+2C8h]
0x180010f3b  mov     eax, [r13+204h]
0x180010f42  mov     ecx, [r13+10h]; int
0x180010f46  mov     [rsp+960h+var_918], r14; __int64
0x180010f4b  mov     r8d, [r8+4]; int
0x180010f4f  mov     [rsp+960h+var_920], rdi; struct _GUID *
0x180010f54  mov     [rsp+960h+var_928], eax; int
0x180010f58  mov     [rsp+960h+var_930], r15d; int
0x180010f5d  mov     [rsp+960h+var_938], r15d; int
0x180010f62  mov     [rsp+960h+var_940], r15d; int
0x180010f67  call    AddSingleRoute
0x180010f6c  test    eax, eax
0x180010f6e  jz      short loc_180010FD4
0x180010f70  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180010f77  jge     short loc_180010FD4
0x180010f79  mov     word ptr [rbp+860h+var_840], r14w
0x180010f7e  lea     rdx, aHandledialoutl_1; "HandleDialOutLinkUp: Couldnt add server"...
0x180010f85  mov     word ptr [rbp+860h+var_868], r14w
0x180010f8a  lea     rcx, [rbp+860h+var_840]
0x180010f8e  mov     r8d, [r13+10h]
0x180010f92  call    FormatRRASErrorString
0x180010f97  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180010f9e  jge     short loc_180010FD4
0x180010fa0  lea     rax, [rbp+860h+var_868]
0x180010fa4  test    rdi, rdi
0x180010fa7  mov     qword ptr [rsp+960h+var_938], rax
0x180010fac  lea     r9, [rbp+860h+var_878]
0x180010fb0  mov     rax, [r13+48h]
0x180010fb4  lea     r8, [rbp+860h+var_840]
0x180010fb8  cmovnz  r9, rdi
0x180010fbc  mov     qword ptr [rsp+960h+var_940], rax
0x180010fc1  lea     rdx, RasRtrmgrParamTraceInfo
0x180010fc8  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180010fcf  call    McTemplateU0zjzz_EventWriteTransfer
0x180010fd4  cmp     [r12+1Ch], r14d
0x180010fd9  jz      loc_1800110C7
0x180010fdf  mov     edx, [r13+204h]
0x180010fe6  lea     rdi, [r13+2B0h]
0x180010fed  mov     r8, rdi
0x180010ff0  mov     ecx, r15d
0x180010ff3  call    ChangeDefaultRouteMetrics
0x180010ff8  mov     [r13+208h], r15d
0x180010fff  mov     ecx, 2
0x180011004  mov     eax, [rbx]
0x180011006  mov     [rbp+860h+var_8C4], eax
0x180011009  mov     eax, [r12+8]
0x18001100e  mov     [rbp+860h+var_8A0], eax
0x180011011  mov     qword ptr [rbp+860h+var_8D0], 0
0x180011019  mov     [rbp+860h+var_8B8], r15
0x18001101d  mov     [rbp+860h+var_8B0], r14d
0x180011021  call    cs:__imp_ComputeRouteMetric
0x180011027  mov     ecx, [r12+8]; int
0x18001102c  lea     rdx, [rbp+860h+var_8D0]; int
0x180011030  mov     [rsp+960h+var_918], r14; __int64
0x180011035  or      r8d, 0FFFFFFFFh; int
0x180011039  mov     [rsp+960h+var_920], rdi; struct _GUID *
0x18001103e  xor     r9d, r9d; int
0x180011041  mov     [rsp+960h+var_928], esi; int
0x180011045  mov     [rbp+860h+var_894], eax
0x180011048  mov     eax, 3
0x18001104d  mov     [rsp+960h+var_930], r14d; int
0x180011052  mov     [rsp+960h+var_938], r14d; int
0x180011057  mov     [rbp+860h+var_890], eax
0x18001105a  mov     [rbp+860h+var_89C], eax
0x18001105d  mov     [rbp+860h+var_898], eax
0x180011060  mov     [rsp+960h+var_940], r15d; int
0x180011065  mov     dword ptr [rbp+860h+var_8C0], r8d
0x180011069  mov     dword ptr [rbp+860h+var_8C0+4], r14d
0x18001106d  mov     [rbp+860h+var_8C8], r14d
0x180011071  call    AddSingleRoute
0x180011076  test    eax, eax
0x180011078  jz      loc_1800111E7
0x18001107e  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180011085  jge     loc_1800111E7
0x18001108b  mov     r8d, [r12+8]
0x180011090  lea     rdx, aHandledialoutl_0; "HandleDialOutLinkUp: Couldnt add defaul"...
0x180011097  lea     rcx, [rbp+860h+var_840]
0x18001109b  mov     word ptr [rbp+860h+var_840], r14w
0x1800110a0  mov     word ptr [rbp+860h+var_868], r14w
0x1800110a5  call    FormatRRASErrorString
0x1800110aa  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x1800110b1  jge     loc_1800111E7
0x1800110b7  test    rdi, rdi
0x1800110ba  lea     r9, [rbp+860h+var_878]
0x1800110be  cmovnz  r9, rdi
0x1800110c2  jmp     loc_1800111BE
0x1800110c7  mov     cl, [rbx]
0x1800110c9  test    cl, cl
0x1800110cb  js      short loc_1800110D4
0x1800110cd  mov     edx, 0FFh
0x1800110d2  jmp     short loc_1800110F4
0x1800110d4  mov     al, cl
0x1800110d6  and     al, 0C0h
0x1800110d8  cmp     al, 80h
0x1800110da  jnz     short loc_1800110E3
0x1800110dc  mov     edx, 0FFFFh
0x1800110e1  jmp     short loc_1800110F4
0x1800110e3  or      edx, 0FFFFFFFFh
0x1800110e6  and     cl, 0E0h
0x1800110e9  cmp     cl, 0C0h
0x1800110ec  mov     eax, 0FFFFFFh
0x1800110f1  cmovz   edx, eax
0x1800110f4  mov     ecx, [rbx]
0x1800110f6  mov     eax, ecx
0x1800110f8  and     eax, edx
0x1800110fa  mov     [rbp+860h+var_8C4], ecx
0x1800110fd  mov     [rbp+860h+var_8D0], eax
0x180011100  mov     ecx, 2
0x180011105  mov     eax, [r12+8]
0x18001110a  mov     [rbp+860h+var_8A0], eax
0x18001110d  mov     [rbp+860h+var_8D0+4], edx
0x180011110  mov     [rbp+860h+var_8B8], r15
0x180011114  mov     [rbp+860h+var_8B0], r14d
0x180011118  call    cs:__imp_ComputeRouteMetric
0x18001111e  mov     ecx, [r12+8]; int
0x180011123  lea     rbx, [r13+2B0h]
0x18001112a  mov     [rsp+960h+var_918], r14; __int64
0x18001112f  lea     rdx, [rbp+860h+var_8D0]; int
0x180011133  mov     [rsp+960h+var_920], rbx; struct _GUID *
0x180011138  xor     r9d, r9d; int
0x18001113b  mov     [rsp+960h+var_928], esi; int
0x18001113f  or      r8d, 0FFFFFFFFh; int
0x180011143  mov     [rsp+960h+var_930], r14d; int
0x180011148  mov     [rsp+960h+var_938], r14d; int
0x18001114d  mov     [rsp+960h+var_940], r15d; int
0x180011152  mov     [rbp+860h+var_894], eax
0x180011155  mov     [rbp+860h+var_890], 3
0x18001115c  mov     [rbp+860h+var_89C], 3
0x180011163  mov     [rbp+860h+var_898], 2
0x18001116a  mov     dword ptr [rbp+860h+var_8C0], 0FFFFFFFFh
0x180011171  mov     dword ptr [rbp+860h+var_8C0+4], r14d
0x180011175  mov     [rbp+860h+var_8C8], r14d
0x180011179  call    AddSingleRoute
0x18001117e  test    eax, eax
0x180011180  jz      short loc_1800111E7
0x180011182  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180011189  jge     short loc_1800111E7
0x18001118b  mov     r8d, [r12+8]
0x180011190  lea     rdx, aHandledialoutl; "HandleDialOutLinkUp: Couldnt add subnet"...
0x180011197  lea     rcx, [rbp+860h+var_840]
0x18001119b  mov     word ptr [rbp+860h+var_840], r14w
0x1800111a0  mov     word ptr [rbp+860h+var_868], r14w
0x1800111a5  call    FormatRRASErrorString
0x1800111aa  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x1800111b1  jge     short loc_1800111E7
0x1800111b3  test    rbx, rbx
0x1800111b6  lea     r9, [rbp+860h+var_878]
0x1800111ba  cmovnz  r9, rbx
0x1800111be  lea     rax, [rbp+860h+var_868]
0x1800111c2  mov     qword ptr [rsp+960h+var_938], rax
0x1800111c7  lea     r8, [rbp+860h+var_840]
0x1800111cb  mov     rax, [r13+48h]
0x1800111cf  lea     rdx, RasRtrmgrParamTraceInfo
0x1800111d6  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800111dd  mov     qword ptr [rsp+960h+var_940], rax
0x1800111e2  call    McTemplateU0zjzz_EventWriteTransfer
0x1800111e7  xor     eax, eax
0x1800111e9  mov     rcx, [rbp+860h+var_40]
0x1800111f0  xor     rcx, rsp; StackCookie
0x1800111f3  call    __security_check_cookie
0x1800111f8  mov     rbx, [rsp+960h+arg_10]
0x180011200  add     rsp, 930h
0x180011207  pop     r15
0x180011209  pop     r14
0x18001120b  pop     r13
0x18001120d  pop     r12
  ... truncated ...
```
