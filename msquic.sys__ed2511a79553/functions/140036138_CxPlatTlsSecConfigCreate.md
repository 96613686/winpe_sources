# CxPlatTlsSecConfigCreate

- ea: `0x140036138`
- end: `0x1400368ea`
- name: `CxPlatTlsSecConfigCreate`
- size: `1970`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140020010`

## callees

- `0x1400356ac`
- `0x140035800`
- `0x140035908`
- `0x140036138`
- `0x140036db8`
- `0x14003c8e0`
- `0x14003ce00`
- `0x14003e928`
- `0x14003ead8`
- `0x14003ed00`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14003686d`
- `ntoskrnl!_snprintf_s` at `0x14003686d`
- `ntoskrnl!strnlen` at `0x1400366b1`
- `ntoskrnl!strnlen` at `0x1400366b1`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003681e`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003681e`
- `ntoskrnl!RtlUTF8ToUnicodeN` at `0x1400366d3`
- `ntoskrnl!RtlUTF8ToUnicodeN` at `0x1400366d3`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14003682d`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14003682d`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x1400367f9`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x1400367f9`
- `ntoskrnl!ExAllocatePool2` at `0x140036273`
- `ntoskrnl!ExAllocatePool2` at `0x140036273`
- `ksecdd!SspiSetAsyncNotifyCallback` at `0x1400367b2`
- `ksecdd!SspiSetAsyncNotifyCallback` at `0x1400367b2`
- `ksecdd!SspiCreateAsyncContext` at `0x14003676b`
- `ksecdd!SspiCreateAsyncContext` at `0x14003676b`

## string_xrefs

- `0x14003629c`: `CXPLAT_SEC_CONFIG`
- `0x1400368be`: `Invalid flags passed in to CxPlatTlsSecConfigCreate`
- `0x14003678d`: `SspiCreateAsyncContext`

## pseudocode

```c
__int64 __fastcall CxPlatTlsSecConfigCreate(unsigned int *a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v4; // r8d
  char v5; // r15
  char v6; // di
  bool v8; // zf
  __int64 v9; // rcx
  bool v10; // zf
  __int64 v11; // r8
  __int64 AchContext; // rbx
  void *Pool2; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  unsigned int v17; // edi
  __int64 v18; // rax
  unsigned int v19; // edx
  __int64 v20; // rcx
  unsigned int v21; // eax
  __int64 v22; // rax
  __int128 v23; // xmm0
  unsigned __int8 v24; // dl
  __int128 v25; // xmm0
  __int128 v26; // xmm0
  __int128 v27; // xmm0
  __int128 v28; // xmm0
  __int64 v29; // rax
  unsigned __int8 v30; // dl
  __int128 v31; // xmm0
  __int64 v32; // rcx
  __int128 v33; // xmm0
  __int64 v34; // rax
  __int64 v35; // rcx
  const CHAR *v36; // rdi
  ULONG UTF8StringByteCount; // eax
  int v38; // eax
  __int64 v39; // rdx
  __int64 v40; // rcx
  const char *v41; // r9
  const CHAR *v42; // rcx
  SspiAsyncContext *AsyncContext; // rax
  __int64 v44; // rcx
  struct _KPROCESS *CurrentProcess; // rax
  __int64 v46; // rcx
  __int128 v47; // [rsp+30h] [rbp-81h] BYREF
  char DstBuf[128]; // [rsp+50h] [rbp-61h] BYREF

  v4 = a1[1];
  v5 = a2;
  v6 = v4 & 1;
  if ( *((_QWORD *)a1 + 3) || (v4 & 0x30) == 0x20 )
    return 3221225485LL;
  v8 = v6 ? (v4 & 0x10040) == 0 : (v4 & 0x8000) == 0;
  if ( !v8 || (v4 & 0x80u) != 0 )
    return 3221225485LL;
  if ( (v4 & 0x100000) == 0 && (v4 & 0x4000) == 0 )
  {
    v9 = *a1;
    if ( !(_DWORD)v9 )
    {
      v10 = v6 == 0;
      goto LABEL_16;
    }
    v9 = (unsigned int)(v9 - 1);
    if ( !(_DWORD)v9 || (v9 = (unsigned int)(v9 - 1), !(_DWORD)v9) )
    {
      if ( *((_QWORD *)a1 + 1) )
        goto LABEL_17;
      v10 = *((_QWORD *)a1 + 2) == 0;
LABEL_16:
      if ( v10 )
        return 3221225485LL;
LABEL_17:
      if ( (v4 & 0x2000) != 0 )
      {
        v11 = a1[10];
        if ( (v11 & 3) == 0 || (v11 & 4) != 0 )
        {
          if ( (Microsoft_QuicEnableBits & 4) != 0 )
            McTemplateU0qs_EtwWriteTransfer(v9, a2, v11, "No valid cipher suites presented");
          return 3221225485LL;
        }
      }
      AchContext = CxPlatTlsAllocateAchContext(a1, a4);
      if ( !AchContext )
        return 3221225495LL;
      Pool2 = (void *)ExAllocatePool2(66, 64, 825385809);
      *(_QWORD *)(AchContext + 424) = Pool2;
      if ( !Pool2 )
      {
        if ( (Microsoft_QuicEnableBits & 2) != 0 )
          McTemplateU0sx_EtwWriteTransfer(v16, v15, "CXPLAT_SEC_CONFIG", 64);
LABEL_28:
        v17 = -1073741801;
        goto LABEL_101;
      }
      memset(Pool2, 0, 0x40u);
      *(_QWORD *)(*(_QWORD *)(AchContext + 424) + 8LL) = -1;
      **(_QWORD **)(AchContext + 424) = -1;
      *(_DWORD *)(*(_QWORD *)(AchContext + 424) + 16LL) = a1[1];
      v18 = *(_QWORD *)(AchContext + 424);
      *(_OWORD *)(v18 + 24) = *(_OWORD *)&QuicTlsCallbacks;
      *(_QWORD *)(v18 + 40) = off_14005C118;
      v19 = *(_DWORD *)(AchContext + 484) | 0x400000;
      *(_DWORD *)(AchContext + 432) = 5;
      *(_DWORD *)(AchContext + 484) = v19;
      if ( (a1[1] & 4) != 0 )
      {
        v19 |= 8u;
        *(_DWORD *)(AchContext + 484) = v19;
      }
      if ( (a1[1] & 8) != 0 )
      {
        v19 |= 0x100000u;
        *(_DWORD *)(AchContext + 484) = v19;
      }
      v20 = v19;
      if ( (a1[1] & 0x20) != 0 && v6 )
      {
        LODWORD(v20) = v19 | 0x4000000;
        *(_DWORD *)(AchContext + 484) = v19 | 0x4000000;
      }
      if ( (a1[1] & 0x100) != 0 )
      {
        v20 = (unsigned int)v20 | 0x100;
        *(_DWORD *)(AchContext + 484) = v20;
      }
      if ( (a1[1] & 0x200) != 0 )
      {
        v20 = (unsigned int)v20 | 0x200;
        *(_DWORD *)(AchContext + 484) = v20;
      }
      if ( (a1[1] & 0x400) != 0 )
      {
        v20 = (unsigned int)v20 | 0x400;
        *(_DWORD *)(AchContext + 484) = v20;
      }
      if ( (a1[1] & 0x800) != 0 )
      {
        v20 = (unsigned int)v20 | 0x800;
        *(_DWORD *)(AchContext + 484) = v20;
      }
      if ( (a1[1] & 0x1000) != 0 )
      {
        v20 = (unsigned int)v20 | 0x1000;
        *(_DWORD *)(AchContext + 484) = v20;
      }
      if ( (a1[1] & 0x20000) != 0 )
      {
        LODWORD(v20) = v20 | 0x8000;
        *(_DWORD *)(AchContext + 484) = v20;
      }
      v21 = a1[1];
      if ( (v21 & 0x40000) != 0 )
      {
        LODWORD(v20) = v20 | 0x4000;
        *(_DWORD *)(AchContext + 484) = v20;
        v21 = a1[1];
      }
      if ( v6 )
      {
        v22 = *(_QWORD *)(AchContext + 496);
        v20 = (unsigned int)v20 | 0x10;
        *(_DWORD *)(AchContext + 484) = v20;
        *(_DWORD *)(v22 + 16) = -8193;
      }
      else
      {
        if ( (v21 & 0x10000) == 0 )
        {
          v20 = (unsigned int)v20 | 2;
          *(_DWORD *)(AchContext + 484) = v20;
        }
        *(_DWORD *)(*(_QWORD *)(AchContext + 496) + 16LL) = -4097;
        if ( (v5 & 1) != 0 )
          *(_DWORD *)(AchContext + 484) |= 0x80u;
      }
      *(_DWORD *)(AchContext + 544) = 2;
      *((_QWORD *)&v47 + 1) = L"CHACHA20_POLY1305";
      *(_QWORD *)&v47 = 2359332;
      v23 = v47;
      *((_QWORD *)&v47 + 1) = L"ChainingModeCCM";
      v24 = 2;
      *(_QWORD *)&v47 = 2097184;
      *(_OWORD *)(AchContext + 552) = v23;
      v25 = v47;
      *(_QWORD *)&v47 = 524296;
      *((_QWORD *)&v47 + 1) = L"AES";
      *(_OWORD *)(AchContext + 736) = v25;
      *(_DWORD *)(AchContext + 592) = 2;
      v26 = v47;
      *(_QWORD *)(AchContext + 624) = AchContext + 736;
      *(_DWORD *)(AchContext + 616) = 1;
      *(_OWORD *)(AchContext + 600) = v26;
      if ( (a1[1] & 0x2000) != 0 )
      {
        v20 = ~a1[10];
        if ( (~*((_BYTE *)a1 + 40) & 3) == 3 )
        {
          if ( (Microsoft_QuicEnableBits & 4) != 0 )
            McTemplateU0s_EtwWriteTransfer(v20, QuicLibraryError, "No Allowed TLS Cipher Suites");
          v17 = -1073741811;
          goto LABEL_101;
        }
        if ( (~*((_BYTE *)a1 + 40) & 2) != 0 )
        {
          *(_QWORD *)&v47 = 524296;
          *((_QWORD *)&v47 + 1) = L"AES";
          v24 = 4;
          v27 = v47;
          *(_DWORD *)(AchContext + 640) = 2;
          *(_DWORD *)(AchContext + 684) = 128;
          *(_OWORD *)(AchContext + 648) = v27;
          *(_DWORD *)(AchContext + 680) = 128;
          *(_QWORD *)&v47 = 917518;
          *((_QWORD *)&v47 + 1) = L"SHA384";
          v28 = v47;
          *(_DWORD *)(AchContext + 688) = 3;
          *(_OWORD *)(AchContext + 696) = v28;
        }
        if ( (v20 & 1) != 0 )
        {
          v29 = v24;
          v30 = v24 + 1;
          *(_QWORD *)&v47 = 524296;
          *((_QWORD *)&v47 + 1) = L"AES";
          v31 = v47;
          *(_QWORD *)&v47 = 917518;
          v32 = 6 * v29;
          *(_DWORD *)(AchContext + 8 * v32 + 588) = 256;
          *(_DWORD *)(AchContext + 8 * v32 + 584) = 256;
          *(_OWORD *)(AchContext + 8 * v32 + 552) = v31;
          *(_DWORD *)(AchContext + 8 * v32 + 544) = 2;
          v20 = 6LL * v30;
          *((_QWORD *)&v47 + 1) = L"SHA256";
          v24 = v30 + 1;
          v33 = v47;
          *(_DWORD *)(AchContext + 8 * v20 + 544) = 3;
          *(_OWORD *)(AchContext + 8 * v20 + 552) = v33;
        }
      }
      *(_DWORD *)(AchContext + 524) = v24;
      if ( v6 && !*a1 )
        goto LABEL_82;
      if ( *a1 == 1 )
      {
        v34 = *((_QWORD *)a1 + 1);
        *(_DWORD *)(AchContext + 132) |= 1u;
        *(_QWORD *)(AchContext + 136) = 0;
        *(_DWORD *)(AchContext + 128) = 296;
        *(_OWORD *)(AchContext + 144) = *(_OWORD *)v34;
        *(_DWORD *)(AchContext + 160) = *(_DWORD *)(v34 + 16);
        *(_DWORD *)(AchContext + 164) = *(_DWORD *)L"MY";
        *(_WORD *)(AchContext + 168) = aMy[2];
        *(_QWORD *)(AchContext + 448) = AchContext + 128;
      }
      else
      {
        if ( *a1 != 2 )
        {
          if ( !*((_QWORD *)a1 + 2) )
          {
            v17 = -1073741811;
            if ( (Microsoft_QuicEnableBits & 4) != 0 )
              McTemplateU0s_EtwWriteTransfer(
                v20,
                QuicLibraryError,
                "Invalid flags passed in to CxPlatTlsSecConfigCreate");
            goto LABEL_101;
          }
          goto LABEL_82;
        }
        v35 = *((_QWORD *)a1 + 1);
        *(_DWORD *)(AchContext + 128) = 296;
        if ( (*(_DWORD *)v35 & 1) != 0 )
          *(_DWORD *)(AchContext + 132) |= 1u;
        v36 = (const CHAR *)(v35 + 24);
        *(_OWORD *)(AchContext + 144) = *(_OWORD *)(v35 + 4);
        *(_DWORD *)(AchContext + 160) = *(_DWORD *)(v35 + 20);
        if ( v35 == -24 )
          UTF8StringByteCount = 0;
        else
          UTF8StringByteCount = strnlen((const char *)(v35 + 24), 0x80u);
        v38 = RtlUTF8ToUnicodeN((PWSTR)(AchContext + 164), 0x100u, 0, v36, UTF8StringByteCount);
        v17 = v38;
        if ( v38 < 0 )
        {
          if ( (Microsoft_QuicEnableBits & 4) == 0 )
            goto LABEL_101;
          v41 = "Convert cert store name to unicode";
          goto LABEL_78;
        }
        *(_QWORD *)(AchContext + 448) = AchContext + 128;
      }
      *(_DWORD *)(AchContext + 484) |= 1u;
      *(_DWORD *)(AchContext + 440) = 1;
      *(_DWORD *)(AchContext + 436) = 2;
LABEL_82:
      v42 = (const CHAR *)*((_QWORD *)a1 + 2);
      if ( v42 )
      {
        v38 = CxPlatTlsUtf8ToUnicodeString(v42, AchContext + 80, 0x44316351u);
        v17 = v38;
        if ( v38 < 0 )
        {
          if ( (Microsoft_QuicEnableBits & 4) == 0 )
            goto LABEL_101;
          v41 = "Convert principal to unicode";
          goto LABEL_78;
        }
        *(_DWORD *)(AchContext + 484) |= 0x80000u;
      }
      AsyncContext = SspiCreateAsyncContext();
      *(_QWORD *)(AchContext + 72) = AsyncContext;
      if ( !AsyncContext )
      {
        if ( (Microsoft_QuicEnableBits & 4) != 0 )
          McTemplateU0s_EtwWriteTransfer(v44, QuicLibraryError, "SspiCreateAsyncContext");
        goto LABEL_28;
      }
      v38 = SspiSetAsyncNotifyCallback(AsyncContext, CxPlatTlsSspiNotifyCallback, (void *)AchContext);
      v17 = v38;
      if ( !v38 )
      {
        *(_QWORD *)(*(_QWORD *)(AchContext + 424) + 48LL) = PsReferenceImpersonationToken(
                                                              KeGetCurrentThread(),
                                                              (PBOOLEAN)(*(_QWORD *)(AchContext + 424) + 57LL),
                                                              (PBOOLEAN)(*(_QWORD *)(AchContext + 424) + 58LL),
                                                              (PSECURITY_IMPERSONATION_LEVEL)(*(_QWORD *)(AchContext + 424)
                                                                                            + 60LL));
        if ( !*(_QWORD *)(*(_QWORD *)(AchContext + 424) + 48LL) )
        {
          CurrentProcess = IoGetCurrentProcess();
          *(_QWORD *)(*(_QWORD *)(AchContext + 424) + 48LL) = PsReferencePrimaryToken(CurrentProcess);
          *(_BYTE *)(*(_QWORD *)(AchContext + 424) + 56LL) = 1;
        }
        if ( byte_14005C48E < 0 )
        {
          _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[ tls] Starting ACH worker");
          McTemplateU0s_EtwWriteTransfer(v46, QuicLogVerbose, DstBuf);
        }
        *(_QWORD *)&v47 = 0;
        *((_QWORD *)&v47 + 1) = AchContext;
        CxPlatTlsAchHelper(&v47);
        v17 = v47;
        AchContext = *((_QWORD *)&v47 + 1);
        if ( !*((_QWORD *)&v47 + 1) )
          return v17;
        goto LABEL_101;
      }
      if ( (Microsoft_QuicEnableBits & 4) == 0 )
      {
LABEL_101:
        CxPlatTlsFreeAchContext((PVOID)AchContext);
        return v17;
      }
      v41 = "SspiSetAsyncNotifyCallback";
LABEL_78:
      McTemplateU0qs_EtwWriteTransfer(v40, v39, (unsigned int)v38, v41);
      goto LABEL_101;
    }
  }
  return 3221225659LL;
}

```

## disassembly

```asm
0x140036138  mov     [rsp-8+arg_8], rbx
0x14003613d  mov     [rsp-8+arg_10], rsi
0x140036142  push    rbp
0x140036143  push    rdi
0x140036144  push    r13
0x140036146  push    r14
0x140036148  push    r15
0x14003614a  lea     rbp, [rsp-2Fh]
0x14003614f  sub     rsp, 0E0h
0x140036156  mov     rax, cs:__security_cookie
0x14003615d  xor     rax, rsp
0x140036160  mov     [rbp+4Fh+var_30], rax
0x140036164  mov     r8d, [rcx+4]
0x140036168  mov     r13d, 1
0x14003616e  mov     dil, r8b
0x140036171  mov     r15d, edx
0x140036174  and     dil, r13b
0x140036177  mov     rsi, rcx
0x14003617a  cmp     qword ptr [rcx+18h], 0
0x14003617f  jnz     loc_14003621D
0x140036185  mov     eax, r8d
0x140036188  lea     ecx, [r13+1Fh]
0x14003618c  and     al, 30h
0x14003618e  cmp     al, cl
0x140036190  jz      loc_14003621D
0x140036196  test    dil, dil
0x140036199  jz      short loc_1400361A4
0x14003619b  test    r8d, 10040h
0x1400361a2  jmp     short loc_1400361AB
0x1400361a4  test    r8d, 8000h
0x1400361ab  jnz     short loc_14003621D
0x1400361ad  test    r8b, r8b
0x1400361b0  js      short loc_14003621D
0x1400361b2  bt      r8d, 14h
0x1400361b7  jb      loc_1400368E0
0x1400361bd  bt      r8d, 0Eh
0x1400361c2  jb      loc_1400368E0
0x1400361c8  mov     ecx, [rsi]
0x1400361ca  test    ecx, ecx
0x1400361cc  jz      short loc_1400361EA
0x1400361ce  sub     ecx, r13d
0x1400361d1  jz      short loc_1400361DC
0x1400361d3  sub     ecx, r13d
0x1400361d6  jnz     loc_1400368E0
0x1400361dc  cmp     qword ptr [rsi+8], 0
0x1400361e1  jnz     short loc_1400361EF
0x1400361e3  cmp     qword ptr [rsi+10h], 0
0x1400361e8  jmp     short loc_1400361ED
0x1400361ea  test    dil, dil
0x1400361ed  jz      short loc_14003621D
0x1400361ef  mov     r14b, 4
0x1400361f2  bt      r8d, 0Dh
0x1400361f7  jnb     short loc_14003624B
0x1400361f9  mov     r8d, [rsi+28h]
0x1400361fd  test    r8b, 3
0x140036201  jz      short loc_140036208
0x140036203  test    r14b, r8b
0x140036206  jz      short loc_14003624B
0x140036208  test    cs:Microsoft_QuicEnableBits, r14b
0x14003620f  jz      short loc_14003621D
0x140036211  lea     r9, aNoValidCipherS; "No valid cipher suites presented"
0x140036218  call    McTemplateU0qs_EtwWriteTransfer
0x14003621d  mov     eax, 0C000000Dh
0x140036222  mov     rcx, [rbp+4Fh+var_30]
0x140036226  xor     rcx, rsp; StackCookie
0x140036229  call    __security_check_cookie
0x14003622e  lea     r11, [rsp+100h+var_20]
0x140036236  mov     rbx, [r11+38h]
0x14003623a  mov     rsi, [r11+40h]
0x14003623e  mov     rsp, r11
0x140036241  pop     r15
0x140036243  pop     r14
0x140036245  pop     r13
0x140036247  pop     rdi
0x140036248  pop     rbp
0x140036249  retn
0x14003624b  mov     rdx, r9
0x14003624e  mov     rcx, rsi
0x140036251  call    CxPlatTlsAllocateAchContext
0x140036256  mov     rbx, rax
0x140036259  test    rax, rax
0x14003625c  jnz     short loc_140036265
0x14003625e  mov     eax, 0C0000017h
0x140036263  jmp     short loc_140036222
0x140036265  mov     edx, 40h ; '@'
0x14003626a  mov     r8d, 31326351h
0x140036270  lea     ecx, [rdx+2]
0x140036273  call    cs:__imp_ExAllocatePool2
0x14003627a  nop     dword ptr [rax+rax+00h]
0x14003627f  mov     [rbx+1A8h], rax
0x140036286  test    rax, rax
0x140036289  jnz     short loc_1400362B2
0x14003628b  lea     r14d, [rax+2]
0x14003628f  test    cs:Microsoft_QuicEnableBits, r14b
0x140036296  jz      short loc_1400362A8
0x140036298  lea     r9d, [rax+40h]
0x14003629c  lea     r8, aCxplatSecConfi; "CXPLAT_SEC_CONFIG"
0x1400362a3  call    McTemplateU0sx_EtwWriteTransfer
0x1400362a8  mov     edi, 0C0000017h
0x1400362ad  jmp     loc_1400368D1
0x1400362b2  xor     edx, edx; Val
0x1400362b4  mov     rcx, rax; void *
0x1400362b7  lea     r8d, [rdx+40h]; Size
0x1400362bb  call    memset
0x1400362c0  mov     rax, [rbx+1A8h]
0x1400362c7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400362cb  mov     r9d, 8
0x1400362d1  mov     [rax+8], rcx
0x1400362d5  mov     rax, [rbx+1A8h]
0x1400362dc  mov     [rax], rcx
0x1400362df  mov     eax, [rsi+4]
0x1400362e2  mov     rcx, [rbx+1A8h]
0x1400362e9  mov     [rcx+10h], eax
0x1400362ec  mov     rax, [rbx+1A8h]
0x1400362f3  movups  xmm0, xmmword ptr cs:QuicTlsCallbacks
0x1400362fa  movups  xmmword ptr [rax+18h], xmm0
0x1400362fe  movsd   xmm0, cs:off_14005C118
0x140036306  movsd   qword ptr [rax+28h], xmm0
0x14003630b  mov     edx, [rbx+1E4h]
0x140036311  bts     edx, 16h
0x140036315  mov     dword ptr [rbx+1B0h], 5
0x14003631f  mov     [rbx+1E4h], edx
0x140036325  mov     eax, [rsi+4]
0x140036328  test    r14b, al
0x14003632b  jz      short loc_140036336
0x14003632d  or      edx, r9d
0x140036330  mov     [rbx+1E4h], edx
0x140036336  mov     eax, [rsi+4]
0x140036339  test    r9b, al
0x14003633c  jz      short loc_140036348
0x14003633e  bts     edx, 14h
0x140036342  mov     [rbx+1E4h], edx
0x140036348  mov     eax, [rsi+4]
0x14003634b  mov     r8d, 20h ; ' '
0x140036351  mov     ecx, edx
0x140036353  test    r8b, al
0x140036356  jz      short loc_140036367
0x140036358  test    dil, dil
0x14003635b  jz      short loc_140036367
0x14003635d  bts     ecx, 1Ah
0x140036361  mov     [rbx+1E4h], ecx
0x140036367  mov     edx, 100h
0x14003636c  test    [rsi+4], edx
0x14003636f  jz      short loc_140036379
0x140036371  or      ecx, edx
0x140036373  mov     [rbx+1E4h], ecx
0x140036379  mov     edx, 200h
0x14003637e  test    [rsi+4], edx
0x140036381  jz      short loc_14003638B
0x140036383  or      ecx, edx
0x140036385  mov     [rbx+1E4h], ecx
0x14003638b  mov     edx, 400h
0x140036390  test    [rsi+4], edx
0x140036393  jz      short loc_14003639D
0x140036395  or      ecx, edx
0x140036397  mov     [rbx+1E4h], ecx
0x14003639d  mov     edx, 800h
0x1400363a2  test    [rsi+4], edx
0x1400363a5  jz      short loc_1400363AF
0x1400363a7  or      ecx, edx
0x1400363a9  mov     [rbx+1E4h], ecx
0x1400363af  mov     edx, 1000h
0x1400363b4  test    [rsi+4], edx
0x1400363b7  jz      short loc_1400363C1
0x1400363b9  or      ecx, edx
0x1400363bb  mov     [rbx+1E4h], ecx
0x1400363c1  test    dword ptr [rsi+4], 20000h
0x1400363c8  jz      short loc_1400363D4
0x1400363ca  bts     ecx, 0Fh
0x1400363ce  mov     [rbx+1E4h], ecx
0x1400363d4  mov     eax, [rsi+4]
0x1400363d7  bt      eax, 12h
0x1400363db  jnb     short loc_1400363EA
0x1400363dd  bts     ecx, 0Eh
0x1400363e1  mov     [rbx+1E4h], ecx
0x1400363e7  mov     eax, [rsi+4]
0x1400363ea  mov     r14d, 2
0x1400363f0  test    dil, dil
0x1400363f3  jz      short loc_14003640E
0x1400363f5  mov     rax, [rbx+1F0h]
0x1400363fc  or      ecx, 10h
0x1400363ff  mov     [rbx+1E4h], ecx
0x140036405  mov     dword ptr [rax+10h], 0FFFFDFFFh
0x14003640c  jmp     short loc_140036438
0x14003640e  bt      eax, 10h
0x140036412  jb      short loc_14003641D
0x140036414  or      ecx, r14d
0x140036417  mov     [rbx+1E4h], ecx
0x14003641d  mov     rax, [rbx+1F0h]
0x140036424  mov     dword ptr [rax+10h], 0FFFFEFFFh
0x14003642b  test    r13b, r15b
0x14003642e  jz      short loc_140036438
0x140036430  bts     dword ptr [rbx+1E4h], 7
0x140036438  mov     [rbx+220h], r14d
0x14003643f  lea     rax, aChacha20Poly13; "CHACHA20_POLY1305"
0x140036446  mov     qword ptr [rbp+4Fh+var_D0+8], rax
0x14003644a  lea     r11, Str2; "AES"
0x140036451  mov     qword ptr [rsp+100h+var_D0], 240024h
0x14003645a  lea     rax, aChainingmodecc; "ChainingModeCCM"
0x140036461  movups  xmm0, [rsp+100h+var_D0]
0x140036466  mov     qword ptr [rbp+4Fh+var_D0+8], rax
0x14003646a  mov     dl, r14b
0x14003646d  mov     qword ptr [rsp+100h+var_D0], 200020h
0x140036476  lea     rax, [rbx+2E0h]
0x14003647d  movdqu  xmmword ptr [rbx+228h], xmm0
0x140036485  movups  xmm0, [rsp+100h+var_D0]
0x14003648a  mov     qword ptr [rsp+100h+var_D0], 80008h
0x140036493  mov     qword ptr [rbp+4Fh+var_D0+8], r11
0x140036497  movdqu  xmmword ptr [rax], xmm0
0x14003649b  mov     [rbx+250h], r14d
0x1400364a2  movups  xmm0, [rsp+100h+var_D0]
0x1400364a7  mov     [rbx+270h], rax
0x1400364ae  mov     [rbx+268h], r13d
0x1400364b5  movdqu  xmmword ptr [rbx+258h], xmm0
0x1400364bd  test    dword ptr [rsi+4], 2000h
0x1400364c4  jz      loc_1400365E8
0x1400364ca  mov     ecx, [rsi+28h]
0x1400364cd  mov     r10d, 3
0x1400364d3  not     ecx
0x1400364d5  mov     eax, ecx
0x1400364d7  and     eax, r10d
0x1400364da  cmp     al, r10b
0x1400364dd  jnz     short loc_140036505
0x1400364df  test    cs:Microsoft_QuicEnableBits, 4
0x1400364e6  jz      short loc_1400364FB
0x1400364e8  lea     r8, aNoAllowedTlsCi; "No Allowed TLS Cipher Suites"
0x1400364ef  lea     rdx, QuicLibraryError
0x1400364f6  call    McTemplateU0s_EtwWriteTransfer
0x1400364fb  mov     edi, 0C000000Dh
0x140036500  jmp     loc_1400368D1
0x140036505  test    r14b, cl
0x140036508  jz      short loc_140036569
0x14003650a  mov     qword ptr [rsp+100h+var_D0], 80008h
0x140036513  lea     rax, aSha384; "SHA384"
0x14003651a  mov     qword ptr [rbp+4Fh+var_D0+8], r11
0x14003651e  mov     dl, 4
0x140036520  movups  xmm0, [rsp+100h+var_D0]
0x140036525  mov     [rbx+280h], r14d
0x14003652c  mov     dword ptr [rbx+2ACh], 80h
0x140036536  movdqu  xmmword ptr [rbx+288h], xmm0
0x14003653e  mov     dword ptr [rbx+2A8h], 80h
0x140036548  mov     qword ptr [rsp+100h+var_D0], 0E000Eh
0x140036551  mov     qword ptr [rbp+4Fh+var_D0+8], rax
0x140036555  movups  xmm0, [rsp+100h+var_D0]
0x14003655a  mov     [rbx+2B0h], r10d
0x140036561  movdqu  xmmword ptr [rbx+2B8h], xmm0
0x140036569  test    r13b, cl
0x14003656c  jz      short loc_1400365E8
0x14003656e  movzx   eax, dl
0x140036571  add     dl, r13b
0x140036574  mov     qword ptr [rsp+100h+var_D0], 80008h
0x14003657d  mov     qword ptr [rbp+4Fh+var_D0+8], r11
0x140036581  movups  xmm0, [rsp+100h+var_D0]
0x140036586  lea     rcx, [rax+rax*2]
0x14003658a  mov     qword ptr [rsp+100h+var_D0], 0E000Eh
0x140036593  add     rcx, rcx
0x140036596  mov     eax, 100h
0x14003659b  mov     [rbx+rcx*8+24Ch], eax
0x1400365a2  mov     [rbx+rcx*8+248h], eax
0x1400365a9  movdqu  xmmword ptr [rbx+rcx*8+228h], xmm0
0x1400365b2  mov     [rbx+rcx*8+220h], r14d
0x1400365ba  movzx   eax, dl
0x1400365bd  lea     rcx, [rax+rax*2]
0x1400365c1  add     rcx, rcx
0x1400365c4  lea     rax, pszAlgId; "SHA256"
0x1400365cb  mov     qword ptr [rbp+4Fh+var_D0+8], rax
0x1400365cf  add     dl, r13b
0x1400365d2  movups  xmm0, [rsp+100h+var_D0]
0x1400365d7  mov     [rbx+rcx*8+220h], r10d
0x1400365df  movdqu  xmmword ptr [rbx+rcx*8+228h], xmm0
0x1400365e8  movzx   eax, dl
0x1400365eb  mov     [rbx+20Ch], eax
0x1400365f1  test    dil, dil
0x1400365f4  jz      short loc_1400365FF
0x1400365f6  cmp     dword ptr [rsi], 0
0x1400365f9  jz      loc_14003672F
0x1400365ff  mov     eax, [rsi]
0x140036601  cmp     eax, r13d
0x140036604  jnz     short loc_14003665F
0x140036606  mov     rax, [rsi+8]
0x14003660a  lea     rcx, [rbx+80h]
0x140036611  or      [rbx+84h], r13d
0x140036618  and     qword ptr [rbx+88h], 0
0x140036620  mov     dword ptr [rcx], 128h
0x140036626  movups  xmm0, xmmword ptr [rax]
0x140036629  movups  xmmword ptr [rbx+90h], xmm0
0x140036630  mov     eax, [rax+10h]
0x140036633  mov     [rbx+0A0h], eax
0x140036639  mov     eax, dword ptr cs:aMy; "MY"
0x14003663f  mov     [rbx+0A4h], eax
0x140036645  movzx   eax, word ptr cs:aMy+4; ""
0x14003664c  mov     [rbx+0A8h], ax
0x140036653  mov     [rbx+1C0h], rcx
0x14003665a  jmp     loc_14003670D
0x14003665f  cmp     eax, r14d
0x140036662  jnz     loc_140036724
0x140036668  mov     rcx, [rsi+8]
0x14003666c  lea     r15, [rbx+80h]
0x140036673  mov     dword ptr [r15], 128h
0x14003667a  mov     eax, [rcx]
  ... truncated ...
```
