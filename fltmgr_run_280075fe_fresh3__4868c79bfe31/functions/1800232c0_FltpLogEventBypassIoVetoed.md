# FltpLogEventBypassIoVetoed

- ea: `0x1800232c0`
- end: `0x180023660`
- name: `FltpLogEventBypassIoVetoed`
- size: `928`
- prototype: `__int64 __fastcall(int, int, int, int, PCUNICODE_STRING SourceString)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800537e0`

## callees

- `0x180001e1c`
- `0x180009f20`
- `0x1800161f0`
- `0x18001eae0`
- `0x180020970`
- `0x180022dac`
- `0x1800232c0`
- `0x1800239e4`
- `0x1800247a0`
- `0x18004db20`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180023609`
- `ntoskrnl!ExFreePoolWithTag` at `0x180023609`
- `ntoskrnl!ObfDereferenceObject` at `0x180023629`
- `ntoskrnl!ObfDereferenceObject` at `0x180023629`
- `ntoskrnl!IoGetStackLimits` at `0x18002348d`
- `ntoskrnl!IoGetStackLimits` at `0x18002348d`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1800233c7`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1800233c7`
- `ntoskrnl!RtlSystemTimeToLocalTime` at `0x180023389`
- `ntoskrnl!RtlSystemTimeToLocalTime` at `0x180023389`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x18002339c`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x18002339c`
- `ntoskrnl!RtlSecondsSince1970ToTime` at `0x180023374`
- `ntoskrnl!RtlSecondsSince1970ToTime` at `0x180023374`

## pseudocode

```c
void __fastcall FltpLogEventBypassIoVetoed(
        struct _FLT_CALLBACK_DATA *a1,
        __int64 a2,
        ULONG a3,
        int a4,
        PCUNICODE_STRING SourceString)
{
  const UNICODE_STRING *v5; // r14
  __int16 *ProcessImageFileName; // rbx
  wchar_t *Buffer; // rcx
  unsigned int DriverVersion; // eax
  unsigned int v13; // eax
  __int64 v14; // r8
  int v15; // edx
  int v16; // ecx
  int v17; // r8d
  int v18; // edi
  int v19; // esi
  int v20; // r9d
  __int64 v21; // r9
  __int64 v22; // rcx
  __int64 v23; // r8
  char v24[4]; // [rsp+60h] [rbp-A0h] BYREF
  ULONG ElapsedSeconds; // [rsp+64h] [rbp-9Ch] BYREF
  int v26; // [rsp+68h] [rbp-98h] BYREF
  int v27; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned __int64 LowLimit; // [rsp+70h] [rbp-90h] BYREF
  LARGE_INTEGER LocalTime; // [rsp+78h] [rbp-88h] BYREF
  PEPROCESS Process; // [rsp+80h] [rbp-80h] BYREF
  PVOID P[2]; // [rsp+88h] [rbp-78h] BYREF
  LARGE_INTEGER Time; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 HighLimit; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v34; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v35; // [rsp+B0h] [rbp-50h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v36; // [rsp+C0h] [rbp-40h] BYREF
  __int64 *v37; // [rsp+E0h] [rbp-20h]
  __int64 v38; // [rsp+E8h] [rbp-18h]
  wchar_t **p_Buffer; // [rsp+F0h] [rbp-10h]
  __int64 v40; // [rsp+F8h] [rbp-8h]
  char v41[16]; // [rsp+100h] [rbp+0h] BYREF
  int *v42; // [rsp+110h] [rbp+10h]
  __int64 v43; // [rsp+118h] [rbp+18h]
  int *v44; // [rsp+120h] [rbp+20h]
  __int64 v45; // [rsp+128h] [rbp+28h]
  LARGE_INTEGER *p_LocalTime; // [rsp+130h] [rbp+30h]
  __int64 v47; // [rsp+138h] [rbp+38h]
  __int16 *v48; // [rsp+140h] [rbp+40h]
  int v49; // [rsp+148h] [rbp+48h]
  int v50; // [rsp+14Ch] [rbp+4Ch]
  ULONG *p_ElapsedSeconds; // [rsp+150h] [rbp+50h]
  __int64 v52; // [rsp+158h] [rbp+58h]
  unsigned __int64 *p_LowLimit; // [rsp+160h] [rbp+60h]
  __int64 v54; // [rsp+168h] [rbp+68h]
  char v55[16]; // [rsp+170h] [rbp+70h] BYREF
  __int64 *v56; // [rsp+180h] [rbp+80h]
  __int64 v57; // [rsp+188h] [rbp+88h]
  wchar_t pszDest[32]; // [rsp+190h] [rbp+90h] BYREF
  wchar_t v59[128]; // [rsp+1D0h] [rbp+D0h] BYREF

  v5 = *(const UNICODE_STRING **)(a2 + 8);
  ProcessImageFileName = &word_18002CAAA;
  Time.QuadPart = 0;
  LocalTime.QuadPart = 0;
  Process = 0;
  v26 = 0;
  v27 = 0;
  *(_OWORD *)P = 0;
  Buffer = v5[6].Buffer;
  ElapsedSeconds = 0;
  v24[0] = 0;
  DriverVersion = FltpGetDriverVersion(
                    (_DWORD)Buffer,
                    (unsigned int)&v26,
                    (unsigned int)&v27,
                    (unsigned int)&ElapsedSeconds,
                    0);
  if ( (int)FltpDbgStatus(DriverVersion, "minkernel\\fs\\filtermgr\\filter\\telemetrysup.c", 2730, 0) >= 0 )
  {
    RtlSecondsSince1970ToTime(ElapsedSeconds, &Time);
    RtlSystemTimeToLocalTime(&Time, &LocalTime);
  }
  v13 = PsLookupProcessByProcessId((HANDLE)*((unsigned int *)&a1[-1].RequestorMode + 1), &Process);
  if ( (int)FltpDbgStatus(v13, "minkernel\\fs\\filtermgr\\filter\\telemetrysup.c", 2744, 0) >= 0 )
    ProcessImageFileName = (__int16 *)PsGetProcessImageFileName(Process);
  FltpBuildPathNameForEventLog(a1, a2, v14, (UNICODE_STRING *)P, v24);
  RtlStringCbCopyUnicodeString(pszDest, 0x40u, v5 + 4);
  RtlStringCbCopyUnicodeString(v59, 0x100u, SourceString);
  v18 = v26;
  v19 = v27;
  if ( (Microsoft_Windows_FilterManagerEnableBits & 4) != 0 )
    McTemplateK0zqqmszqzd_EtwWriteTransfer(
      v16,
      v15,
      v17,
      (unsigned int)pszDest,
      v26,
      v27,
      (__int64)&LocalTime,
      (__int64)ProcessImageFileName,
      (__int64)P[1],
      a3,
      (__int64)v59,
      a4);
  if ( (unsigned int)dword_18003DAA8 > 5 )
  {
    HighLimit = 0;
    LowLimit = 0;
    IoGetStackLimits(&LowLimit, &HighLimit);
    if ( (unsigned __int64)&HighLimit - LowLimit >= 0x200 )
    {
      if ( (unsigned int)dword_18003DAA8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18003DAA8, 0x400000000000LL) )
      {
        v38 = 8;
        v37 = &v34;
        v40 = 16;
        p_Buffer = &v5[2].Buffer;
        v34 = 1;
        tlgCreate1Sz_wchar_t(v41, pszDest);
        v27 = v18;
        v42 = &v27;
        v44 = &v26;
        p_LocalTime = &LocalTime;
        v43 = 4;
        v26 = v19;
        v45 = 4;
        v47 = 8;
        if ( ProcessImageFileName )
        {
          v21 = -1;
          do
            ++v21;
          while ( *((_BYTE *)ProcessImageFileName + v21) );
          v20 = v21 + 1;
        }
        else
        {
          ProcessImageFileName = &word_18002CAAA;
        }
        v48 = ProcessImageFileName;
        p_ElapsedSeconds = &ElapsedSeconds;
        v49 = v20;
        p_LowLimit = &LowLimit;
        v50 = 0;
        ElapsedSeconds = a3;
        v52 = 4;
        LODWORD(LowLimit) = a4;
        v54 = 4;
        tlgCreate1Sz_wchar_t(v55, v59);
        v35 = 0x1000000;
        v56 = &v35;
        v57 = 8;
        tlgWriteAgg(v22, (unsigned __int8 *)&qword_180031FA0, v23, 0xDu, &v36);
      }
    }
    else
    {
      _InterlockedAdd(&dword_18003FFB0, 1u);
    }
  }
  if ( v24[0] )
  {
    ExFreePoolWithTag(P[1], 0);
    P[1] = 0;
    LODWORD(P[0]) = 0;
  }
  if ( Process )
    ObfDereferenceObject(Process);
}

```

## disassembly

```asm
0x1800232c0  mov     [rsp-8+arg_10], rbx
0x1800232c5  push    rbp
0x1800232c6  push    rsi
0x1800232c7  push    rdi
0x1800232c8  push    r12
0x1800232ca  push    r13
0x1800232cc  push    r14
0x1800232ce  push    r15
0x1800232d0  lea     rbp, [rsp-1E0h]
0x1800232d8  sub     rsp, 2E0h
0x1800232df  mov     rax, cs:__security_cookie
0x1800232e6  xor     rax, rsp
0x1800232e9  mov     [rbp+210h+var_40], rax
0x1800232f0  mov     r14, [rdx+8]
0x1800232f4  lea     rbx, word_18002CAAA
0x1800232fb  mov     r13, [rbp+210h+SourceString]
0x180023302  xor     eax, eax
0x180023304  xorps   xmm0, xmm0
0x180023307  mov     qword ptr [rbp+210h+Time], rax
0x18002330b  mov     r15d, r9d
0x18002330e  mov     qword ptr [rsp+310h+LocalTime], rax
0x180023313  mov     r12d, r8d
0x180023316  mov     [rbp+210h+Process], rax
0x18002331a  mov     rsi, rdx
0x18002331d  mov     [rsp+310h+var_2A8], eax
0x180023321  mov     rdi, rcx
0x180023324  mov     [rsp+310h+var_2A4], eax
0x180023328  movups  xmmword ptr [rbp+210h+P], xmm0
0x18002332c  mov     rcx, [r14+68h]
0x180023330  lea     r9, [rsp+310h+ElapsedSeconds]
0x180023335  lea     r8, [rsp+310h+var_2A4]
0x18002333a  mov     [rsp+310h+ElapsedSeconds], eax
0x18002333e  lea     rdx, [rsp+310h+var_2A8]
0x180023343  mov     [rsp+310h+var_2B0], al
0x180023347  mov     [rsp+310h+var_2F0], rax
0x18002334c  call    FltpGetDriverVersion
0x180023351  mov     r8d, 0AAAh
0x180023357  lea     rdx, aMinkernelFsFil_13; "minkernel\\fs\\filtermgr\\filter\\telem"...
0x18002335e  xor     r9d, r9d
0x180023361  mov     ecx, eax
0x180023363  call    FltpDbgStatus
0x180023368  test    eax, eax
0x18002336a  js      short loc_180023395
0x18002336c  mov     ecx, [rsp+310h+ElapsedSeconds]; ElapsedSeconds
0x180023370  lea     rdx, [rbp+210h+Time]; Time
0x180023374  call    cs:__imp_RtlSecondsSince1970ToTime
0x18002337b  nop     dword ptr [rax+rax+00h]
0x180023380  lea     rdx, [rsp+310h+LocalTime]; LocalTime
0x180023385  lea     rcx, [rbp+210h+Time]; SystemTime
0x180023389  call    cs:__imp_RtlSystemTimeToLocalTime
0x180023390  nop     dword ptr [rax+rax+00h]
0x180023395  mov     ecx, [rdi-4]; ProcessId
0x180023398  lea     rdx, [rbp+210h+Process]; Process
0x18002339c  call    cs:__imp_PsLookupProcessByProcessId
0x1800233a3  nop     dword ptr [rax+rax+00h]
0x1800233a8  xor     r9d, r9d
0x1800233ab  lea     rdx, aMinkernelFsFil_13; "minkernel\\fs\\filtermgr\\filter\\telem"...
0x1800233b2  mov     ecx, eax
0x1800233b4  mov     r8d, 0AB8h
0x1800233ba  call    FltpDbgStatus
0x1800233bf  test    eax, eax
0x1800233c1  js      short loc_1800233D6
0x1800233c3  mov     rcx, [rbp+210h+Process]
0x1800233c7  call    cs:__imp_PsGetProcessImageFileName
0x1800233ce  nop     dword ptr [rax+rax+00h]
0x1800233d3  mov     rbx, rax
0x1800233d6  lea     rax, [rsp+310h+var_2B0]
0x1800233db  mov     rdx, rsi
0x1800233de  lea     r9, [rbp+210h+P]
0x1800233e2  mov     [rsp+310h+var_2F0], rax
0x1800233e7  mov     rcx, rdi
0x1800233ea  call    FltpBuildPathNameForEventLog
0x1800233ef  lea     r8, [r14+40h]; SourceString
0x1800233f3  mov     edx, 40h ; '@'; cbDest
0x1800233f8  lea     rcx, [rbp+210h+pszDest]; pszDest
0x1800233ff  call    RtlStringCbCopyUnicodeString
0x180023404  mov     r8, r13; SourceString
0x180023407  lea     rcx, [rbp+210h+var_140]; pszDest
0x18002340e  mov     edx, 100h; cbDest
0x180023413  call    RtlStringCbCopyUnicodeString
0x180023418  test    cs:Microsoft_Windows_FilterManagerEnableBits, 4
0x18002341f  mov     edi, [rsp+310h+var_2A8]
0x180023423  mov     esi, [rsp+310h+var_2A4]
0x180023427  jz      short loc_18002346B
0x180023429  mov     [rsp+310h+var_2B8], r15d
0x18002342e  lea     rax, [rbp+210h+var_140]
0x180023435  mov     [rsp+310h+var_2C0], rax
0x18002343a  lea     r9, [rbp+210h+pszDest]
0x180023441  mov     rax, [rbp+210h+P+8]
0x180023445  mov     [rsp+310h+var_2C8], r12d
0x18002344a  mov     [rsp+310h+var_2D0], rax
0x18002344f  lea     rax, [rsp+310h+LocalTime]
0x180023454  mov     [rsp+310h+var_2D8], rbx
0x180023459  mov     [rsp+310h+var_2E0], rax
0x18002345e  mov     [rsp+310h+var_2E8], esi
0x180023462  mov     dword ptr [rsp+310h+var_2F0], edi
0x180023466  call    McTemplateK0zqqmszqzd_EtwWriteTransfer
0x18002346b  xor     r13d, r13d
0x18002346e  cmp     cs:dword_18003DAA8, 5
0x180023475  jbe     loc_1800235FC
0x18002347b  lea     rdx, [rbp+210h+HighLimit]; HighLimit
0x18002347f  mov     [rbp+210h+HighLimit], r13
0x180023483  lea     rcx, [rsp+310h+LowLimit]; LowLimit
0x180023488  mov     [rsp+310h+LowLimit], r13
0x18002348d  call    cs:__imp_IoGetStackLimits
0x180023494  nop     dword ptr [rax+rax+00h]
0x180023499  lea     rax, [rbp+210h+HighLimit]
0x18002349d  sub     rax, [rsp+310h+LowLimit]
0x1800234a2  cmp     rax, 200h
0x1800234a8  jnb     short loc_1800234BB
0x1800234aa  lea     r9d, [r13+1]
0x1800234ae  lock add cs:dword_18003FFB0, r9d
0x1800234b6  jmp     loc_1800235FC
0x1800234bb  mov     eax, cs:dword_18003DAA8
0x1800234c1  cmp     eax, 5
0x1800234c4  jbe     loc_1800235FC
0x1800234ca  mov     rdx, 400000000000h
0x1800234d4  lea     rcx, dword_18003DAA8
0x1800234db  call    _tlgKeywordOn
0x1800234e0  test    al, al
0x1800234e2  jz      loc_1800235FC
0x1800234e8  lea     rax, [rbp+210h+var_268]
0x1800234ec  mov     [rbp+210h+var_228], 8
0x1800234f4  mov     [rbp+210h+var_230], rax
0x1800234f8  lea     rdx, [rbp+210h+pszDest]
0x1800234ff  lea     rax, [r14+28h]
0x180023503  mov     [rbp+210h+var_218], 10h
0x18002350b  mov     r9d, 1
0x180023511  mov     [rbp+210h+var_220], rax
0x180023515  lea     rcx, [rbp+210h+var_210]
0x180023519  mov     [rbp+210h+var_268], r9
0x18002351d  call    _tlgCreate1Sz_wchar_t
0x180023522  mov     [rsp+310h+var_2A4], edi
0x180023526  lea     rax, [rsp+310h+var_2A4]
0x18002352b  mov     [rbp+210h+var_200], rax
0x18002352f  lea     rax, [rsp+310h+var_2A8]
0x180023534  mov     [rbp+210h+var_1F0], rax
0x180023538  lea     rax, [rsp+310h+LocalTime]
0x18002353d  mov     [rbp+210h+var_1E0], rax
0x180023541  mov     [rbp+210h+var_1F8], 4
0x180023549  mov     [rsp+310h+var_2A8], esi
0x18002354d  mov     [rbp+210h+var_1E8], 4
0x180023555  mov     [rbp+210h+var_1D8], 8
0x18002355d  test    rbx, rbx
0x180023560  jz      short loc_180023574
0x180023562  or      r9, 0FFFFFFFFFFFFFFFFh
0x180023566  inc     r9
0x180023569  cmp     [rbx+r9], r13b
0x18002356d  jnz     short loc_180023566
0x18002356f  inc     r9d
0x180023572  jmp     short loc_18002357B
0x180023574  lea     rbx, word_18002CAAA
0x18002357b  lea     rax, [rsp+310h+ElapsedSeconds]
0x180023580  mov     [rbp+210h+var_1D0], rbx
0x180023584  mov     [rbp+210h+var_1C0], rax
0x180023588  lea     rdx, [rbp+210h+var_140]
0x18002358f  lea     rax, [rsp+310h+LowLimit]
0x180023594  mov     [rbp+210h+var_1C8], r9d
0x180023598  lea     rcx, [rbp+210h+var_1A0]
0x18002359c  mov     [rbp+210h+var_1B0], rax
0x1800235a0  mov     [rbp+210h+var_1C4], r13d
0x1800235a4  mov     [rsp+310h+ElapsedSeconds], r12d
0x1800235a9  mov     [rbp+210h+var_1B8], 4
0x1800235b1  mov     dword ptr [rsp+310h+LowLimit], r15d
0x1800235b6  mov     [rbp+210h+var_1A8], 4
0x1800235be  call    _tlgCreate1Sz_wchar_t
0x1800235c3  lea     rax, [rbp+210h+var_260]
0x1800235c7  mov     [rbp+210h+var_260], 1000000h
0x1800235cf  mov     [rbp+210h+var_190], rax
0x1800235d6  lea     rdx, qword_180031FA0; int
0x1800235dd  lea     rax, [rbp+210h+var_250]
0x1800235e1  mov     [rbp+210h+var_188], 8
0x1800235ec  mov     r9d, 0Dh; int
0x1800235f2  mov     [rsp+310h+var_2F0], rax; PEVENT_DATA_DESCRIPTOR
0x1800235f7  call    _tlgWriteAgg
0x1800235fc  cmp     [rsp+310h+var_2B0], r13b
0x180023601  jz      short loc_180023620
0x180023603  mov     rcx, [rbp+210h+P+8]; P
0x180023607  xor     edx, edx; Tag
0x180023609  call    cs:__imp_ExFreePoolWithTag
0x180023610  nop     dword ptr [rax+rax+00h]
0x180023615  mov     [rbp+210h+P+8], r13
0x180023619  mov     dword ptr [rbp+210h+P], 0
0x180023620  mov     rcx, [rbp+210h+Process]; Object
0x180023624  test    rcx, rcx
0x180023627  jz      short loc_180023635
0x180023629  call    cs:__imp_ObfDereferenceObject
0x180023630  nop     dword ptr [rax+rax+00h]
0x180023635  mov     rcx, [rbp+210h+var_40]
0x18002363c  xor     rcx, rsp; StackCookie
0x18002363f  call    __security_check_cookie
0x180023644  mov     rbx, [rsp+310h+arg_10]
0x18002364c  add     rsp, 2E0h
0x180023653  pop     r15
0x180023655  pop     r14
0x180023657  pop     r13
0x180023659  pop     r12
0x18002365b  pop     rdi
0x18002365c  pop     rsi
0x18002365d  pop     rbp
0x18002365e  retn
```
