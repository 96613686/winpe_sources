# RasLineMakeCall_postProcess

- ea: `0x18008d810`
- end: `0x18008db7f`
- name: `RasLineMakeCall_postProcess`
- size: `879`
- prototype: `__int64 __fastcall(__int64, unsigned int, _QWORD *)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x1800755b8`
- `0x18008d810`
- `0x18008ef04`
- `0x18008f388`
- `0x18008f50c`
- `0x18008fd44`
- `0x180090714`
- `0x180090834`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `rtutils!TracePrintfA` at `0x18008d8d6`
- `rtutils!TracePrintfA` at `0x18008d965`
- `rtutils!TracePrintfA` at `0x18008d9fc`
- `rtutils!TracePrintfA` at `0x18008dad7`
- `rtutils!TracePrintfA` at `0x18008d8d6`
- `rtutils!TracePrintfA` at `0x18008d965`
- `rtutils!TracePrintfA` at `0x18008d9fc`
- `rtutils!TracePrintfA` at `0x18008dad7`

## string_xrefs

- `0x18008d9ab`: `RasLineMakeCall_postProcess: GetLineObjWithReadLock failed with error (0x%x)`
- `0x18008da3b`: `RasLineMakeCall_postProcess: GetCallObjWithWriteLock failed with error (0x%x)`
- `0x18008d9f2`: `RasLineMakeCall_postProcess: GetLineObjWithReadLock failed with error (0x%x)`
- `0x18008da56`: `RasLineMakeCall_postProcess: GetCallObjWithWriteLock failed with error (0x%x)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RasLineMakeCall_postProcess(__int64 a1, unsigned int a2, _QWORD *a3)
{
  int v6; // r13d
  unsigned int v7; // esi
  unsigned int v8; // eax
  unsigned int v9; // ebx
  unsigned int LineObjWithReadLock; // eax
  __int64 v11; // r12
  unsigned int v12; // eax
  _DWORD *v13; // rdi
  int v14; // r8d
  unsigned int v16; // [rsp+20h] [rbp-E0h] BYREF
  _DWORD *v17; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  int v19; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v20[2044]; // [rsp+44h] [rbp-BCh] BYREF

  v16 = 0;
  v18 = 0;
  v17 = 0;
  v19 = 0;
  v6 = 0;
  memset_0(v20, 0, sizeof(v20));
  if ( gIsndpspEtwTracingAvailable )
  {
    if ( (_QWORD)xmmword_1800D0BE0 )
    {
      LOWORD(v19) = 0;
      FormatRRASErrorString(&v19, L"RasLineMakeCall_postProcess called with dwRetCode (0x%x)", a2);
      ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v19);
    }
  }
  else if ( dwTraceId != -1 )
  {
    TracePrintfA(dwTraceId, "RasLineMakeCall_postProcess called with dwRetCode (0x%x)", a2);
  }
  v7 = *(_DWORD *)(a1 + 96);
  v8 = GetLineHandleFromCallHandle(v7, &v16);
  v9 = v8;
  if ( v8 )
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800D0BE0 )
      {
        LOWORD(v19) = 0;
        FormatRRASErrorString(
          &v19,
          L"RasLineMakeCall_postProcess: GetLineHandleFromCallHandle failed with error (0x%x)",
          v8);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v19);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "RasLineMakeCall_postProcess: GetLineHandleFromCallHandle failed with error (0x%x)", v8);
    }
    return v9;
  }
  LineObjWithReadLock = GetLineObjWithReadLock(v16, &v18);
  v11 = v18;
  v9 = LineObjWithReadLock;
  if ( LineObjWithReadLock )
  {
    if ( !gIsndpspEtwTracingAvailable )
    {
      if ( dwTraceId != -1 )
        TracePrintfA(
          dwTraceId,
          "RasLineMakeCall_postProcess: GetLineObjWithReadLock failed with error (0x%x)",
          LineObjWithReadLock);
      goto LABEL_35;
    }
    if ( (_QWORD)xmmword_1800D0BE0 )
    {
      LOWORD(v19) = 0;
      FormatRRASErrorString(
        &v19,
        L"RasLineMakeCall_postProcess: GetLineObjWithReadLock failed with error (0x%x)",
        LineObjWithReadLock);
LABEL_16:
      ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v19);
    }
  }
  else
  {
    v12 = GetCallObjWithWriteLock(v7, &v17);
    v9 = v12;
    if ( !v12 )
    {
      if ( a2 )
      {
        *v17 = 1482184792;
        ReleaseObjWriteLock(v7, 0);
        v6 = 1;
      }
      else
      {
        v13 = v17;
        v14 = v17[9];
        if ( v14 )
        {
          if ( gIsndpspEtwTracingAvailable )
          {
            if ( (_QWORD)xmmword_1800D0BE0 )
            {
              LOWORD(v19) = 0;
              FormatRRASErrorString(
                &v19,
                L"RasLineMakeCall_postProcess: Executing the pending LINE_CALLSTATE message 0x%x",
                (unsigned int)v17[9]);
              ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(
                gNdpspEtwContext,
                xmmword_1800D0BE0,
                &v19);
            }
          }
          else if ( dwTraceId != -1 )
          {
            TracePrintfA(
              dwTraceId,
              "RasLineMakeCall_postProcess: Executing the pending LINE_CALLSTATE message 0x%x",
              v14);
          }
          *a3 = *(unsigned int *)(v11 + 8);
          a3[1] = (unsigned int)v13[2];
          a3[2] = (unsigned int)v13[9];
          a3[3] = (unsigned int)v13[10];
          a3[4] = (unsigned int)v13[11];
        }
        *((_QWORD *)v13 + 3) = *(_QWORD *)(a1 + 176);
        v13[16] = 0;
        ReleaseObjWriteLock(v7, 0);
      }
      goto LABEL_35;
    }
    if ( !gIsndpspEtwTracingAvailable )
    {
      if ( dwTraceId != -1 )
        TracePrintfA(dwTraceId, "RasLineMakeCall_postProcess: GetCallObjWithWriteLock failed with error (0x%x)", v12);
      goto LABEL_35;
    }
    if ( (_QWORD)xmmword_1800D0BE0 )
    {
      LOWORD(v19) = 0;
      FormatRRASErrorString(&v19, L"RasLineMakeCall_postProcess: GetCallObjWithWriteLock failed with error (0x%x)", v12);
      goto LABEL_16;
    }
  }
LABEL_35:
  if ( v11 )
    ReleaseObjReadLock(v16);
  if ( v6 )
    CloseObjHandle(v7);
  return v9;
}

```

## disassembly

```asm
0x18008d810  mov     [rsp-8+arg_18], rbx
0x18008d815  push    rbp
0x18008d816  push    rsi
0x18008d817  push    rdi
0x18008d818  push    r12
0x18008d81a  push    r13
0x18008d81c  push    r14
0x18008d81e  push    r15
0x18008d820  lea     rbp, [rsp-750h]
0x18008d828  sub     rsp, 850h
0x18008d82f  mov     rax, cs:__security_cookie
0x18008d836  xor     rax, rsp
0x18008d839  mov     [rbp+780h+var_40], rax
0x18008d840  xor     r12d, r12d
0x18008d843  mov     r14, r8
0x18008d846  mov     edi, edx
0x18008d848  mov     [rsp+880h+var_860], r12d
0x18008d84d  mov     r15, rcx
0x18008d850  mov     [rsp+880h+var_850], r12
0x18008d855  xor     edx, edx; Val
0x18008d857  mov     [rsp+880h+var_858], r12
0x18008d85c  mov     r8d, 7FCh; Size
0x18008d862  mov     [rsp+880h+var_840], r12d
0x18008d867  lea     rcx, [rsp+880h+var_83C]; void *
0x18008d86c  mov     r13d, r12d
0x18008d86f  call    memset_0
0x18008d874  cmp     cs:gIsndpspEtwTracingAvailable, r12d
0x18008d87b  jz      short loc_18008D8C1
0x18008d87d  cmp     qword ptr cs:xmmword_1800D0BE0, r12
0x18008d884  jz      short loc_18008D8E2
0x18008d886  mov     r8d, edi
0x18008d889  mov     word ptr [rsp+880h+var_840], r12w
0x18008d88f  lea     rdx, aRaslinemakecal_6; "RasLineMakeCall_postProcess called with"...
0x18008d896  lea     rcx, [rsp+880h+var_840]
0x18008d89b  call    FormatRRASErrorString
0x18008d8a0  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008d8a7  lea     r8, [rsp+880h+var_840]
0x18008d8ac  mov     rcx, cs:gNdpspEtwContext
0x18008d8b3  mov     rax, cs:gNdpspTemplateFunc
0x18008d8ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d8bf  jmp     short loc_18008D8E2
0x18008d8c1  mov     ecx, cs:dwTraceId; dwTraceID
0x18008d8c7  cmp     ecx, 0FFFFFFFFh
0x18008d8ca  jz      short loc_18008D8E2
0x18008d8cc  mov     r8d, edi
0x18008d8cf  lea     rdx, aRaslinemakecal_10; "RasLineMakeCall_postProcess called with"...
0x18008d8d6  call    cs:__imp_TracePrintfA
0x18008d8dd  nop     dword ptr [rax+rax+00h]
0x18008d8e2  mov     esi, [r15+60h]
0x18008d8e6  lea     rdx, [rsp+880h+var_860]
0x18008d8eb  mov     ecx, esi
0x18008d8ed  call    GetLineHandleFromCallHandle
0x18008d8f2  mov     ebx, eax
0x18008d8f4  test    eax, eax
0x18008d8f6  jz      short loc_18008D976
0x18008d8f8  cmp     cs:gIsndpspEtwTracingAvailable, r12d
0x18008d8ff  jz      short loc_18008D94C
0x18008d901  cmp     qword ptr cs:xmmword_1800D0BE0, r12
0x18008d908  jz      loc_18008DB52
0x18008d90e  mov     r8d, eax
0x18008d911  mov     word ptr [rsp+880h+var_840], r12w
0x18008d917  lea     rdx, aRaslinemakecal_3; "RasLineMakeCall_postProcess: GetLineHan"...
0x18008d91e  lea     rcx, [rsp+880h+var_840]
0x18008d923  call    FormatRRASErrorString
0x18008d928  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008d92f  lea     r8, [rsp+880h+var_840]
0x18008d934  mov     rcx, cs:gNdpspEtwContext
0x18008d93b  mov     rax, cs:gNdpspTemplateFunc
0x18008d942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d947  jmp     loc_18008DB52
0x18008d94c  mov     ecx, cs:dwTraceId; dwTraceID
0x18008d952  cmp     ecx, 0FFFFFFFFh
0x18008d955  jz      loc_18008DB52
0x18008d95b  mov     r8d, eax
0x18008d95e  lea     rdx, aRaslinemakecal_18; "RasLineMakeCall_postProcess: GetLineHan"...
0x18008d965  call    cs:__imp_TracePrintfA
0x18008d96c  nop     dword ptr [rax+rax+00h]
0x18008d971  jmp     loc_18008DB52
0x18008d976  mov     ecx, [rsp+880h+var_860]
0x18008d97a  lea     rdx, [rsp+880h+var_850]
0x18008d97f  call    GetLineObjWithReadLock
0x18008d984  mov     r12, [rsp+880h+var_850]
0x18008d989  xor     edx, edx
0x18008d98b  mov     ebx, eax
0x18008d98d  test    eax, eax
0x18008d98f  jz      short loc_18008DA0D
0x18008d991  cmp     cs:gIsndpspEtwTracingAvailable, edx
0x18008d997  jz      short loc_18008D9E3
0x18008d999  cmp     qword ptr cs:xmmword_1800D0BE0, rdx
0x18008d9a0  jz      loc_18008DB38
0x18008d9a6  mov     word ptr [rsp+880h+var_840], dx
0x18008d9ab  lea     rdx, aRaslinemakecal_2; "RasLineMakeCall_postProcess: GetLineObj"...
0x18008d9b2  mov     r8d, eax
0x18008d9b5  lea     rcx, [rsp+880h+var_840]
0x18008d9ba  call    FormatRRASErrorString
0x18008d9bf  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008d9c6  lea     r8, [rsp+880h+var_840]
0x18008d9cb  mov     rcx, cs:gNdpspEtwContext
0x18008d9d2  mov     rax, cs:gNdpspTemplateFunc
0x18008d9d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d9de  jmp     loc_18008DB38
0x18008d9e3  mov     ecx, cs:dwTraceId; dwTraceID
0x18008d9e9  cmp     ecx, 0FFFFFFFFh
0x18008d9ec  jz      loc_18008DB38
0x18008d9f2  lea     rdx, aRaslinemakecal_9; "RasLineMakeCall_postProcess: GetLineObj"...
0x18008d9f9  mov     r8d, eax
0x18008d9fc  call    cs:__imp_TracePrintfA
0x18008da03  nop     dword ptr [rax+rax+00h]
0x18008da08  jmp     loc_18008DB38
0x18008da0d  lea     rdx, [rsp+880h+var_858]
0x18008da12  mov     ecx, esi
0x18008da14  call    GetCallObjWithWriteLock
0x18008da19  xor     edx, edx
0x18008da1b  mov     ebx, eax
0x18008da1d  test    eax, eax
0x18008da1f  jz      short loc_18008DA5F
0x18008da21  cmp     cs:gIsndpspEtwTracingAvailable, edx
0x18008da27  jz      short loc_18008DA47
0x18008da29  cmp     qword ptr cs:xmmword_1800D0BE0, rdx
0x18008da30  jz      loc_18008DB38
0x18008da36  mov     word ptr [rsp+880h+var_840], dx
0x18008da3b  lea     rdx, aRaslinemakecal_16; "RasLineMakeCall_postProcess: GetCallObj"...
0x18008da42  jmp     loc_18008D9B2
0x18008da47  mov     ecx, cs:dwTraceId
0x18008da4d  cmp     ecx, 0FFFFFFFFh
0x18008da50  jz      loc_18008DB38
0x18008da56  lea     rdx, aRaslinemakecal_15; "RasLineMakeCall_postProcess: GetCallObj"...
0x18008da5d  jmp     short loc_18008D9F9
0x18008da5f  test    edi, edi
0x18008da61  jnz     loc_18008DB20
0x18008da67  mov     rdi, [rsp+880h+var_858]
0x18008da6c  mov     r8d, [rdi+24h]
0x18008da70  test    r8d, r8d
0x18008da73  jz      loc_18008DB09
0x18008da79  cmp     cs:gIsndpspEtwTracingAvailable, edx
0x18008da7f  jz      short loc_18008DAC5
0x18008da81  cmp     qword ptr cs:xmmword_1800D0BE0, rdx
0x18008da88  jz      short loc_18008DAE5
0x18008da8a  mov     word ptr [rsp+880h+var_840], dx
0x18008da8f  lea     rcx, [rsp+880h+var_840]
0x18008da94  mov     r8d, [rdi+24h]
0x18008da98  lea     rdx, aRaslinemakecal_7; "RasLineMakeCall_postProcess: Executing "...
0x18008da9f  call    FormatRRASErrorString
0x18008daa4  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008daab  lea     r8, [rsp+880h+var_840]
0x18008dab0  mov     rcx, cs:gNdpspEtwContext
0x18008dab7  mov     rax, cs:gNdpspTemplateFunc
0x18008dabe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008dac3  jmp     short loc_18008DAE3
0x18008dac5  mov     ecx, cs:dwTraceId; dwTraceID
0x18008dacb  cmp     ecx, 0FFFFFFFFh
0x18008dace  jz      short loc_18008DAE5
0x18008dad0  lea     rdx, aRaslinemakecal_1; "RasLineMakeCall_postProcess: Executing "...
0x18008dad7  call    cs:__imp_TracePrintfA
0x18008dade  nop     dword ptr [rax+rax+00h]
0x18008dae3  xor     edx, edx
0x18008dae5  mov     eax, [r12+8]
0x18008daea  mov     [r14], rax
0x18008daed  mov     eax, [rdi+8]
0x18008daf0  mov     [r14+8], rax
0x18008daf4  mov     eax, [rdi+24h]
0x18008daf7  mov     [r14+10h], rax
0x18008dafb  mov     eax, [rdi+28h]
0x18008dafe  mov     [r14+18h], rax
0x18008db02  mov     eax, [rdi+2Ch]
0x18008db05  mov     [r14+20h], rax
0x18008db09  mov     rax, [r15+0B0h]
0x18008db10  mov     ecx, esi
0x18008db12  mov     [rdi+18h], rax
0x18008db16  mov     [rdi+40h], edx
0x18008db19  call    ReleaseObjWriteLock
0x18008db1e  jmp     short loc_18008DB38
0x18008db20  mov     rax, [rsp+880h+var_858]
0x18008db25  mov     ecx, esi
0x18008db27  mov     dword ptr [rax], 58585858h
0x18008db2d  call    ReleaseObjWriteLock
0x18008db32  mov     r13d, 1
0x18008db38  test    r12, r12
0x18008db3b  jz      short loc_18008DB46
0x18008db3d  mov     ecx, [rsp+880h+var_860]
0x18008db41  call    ReleaseObjReadLock
0x18008db46  test    r13d, r13d
0x18008db49  jz      short loc_18008DB52
0x18008db4b  mov     ecx, esi
0x18008db4d  call    CloseObjHandle
0x18008db52  mov     eax, ebx
0x18008db54  mov     rcx, [rbp+780h+var_40]
0x18008db5b  xor     rcx, rsp; StackCookie
0x18008db5e  call    __security_check_cookie
0x18008db63  mov     rbx, [rsp+880h+arg_18]
0x18008db6b  add     rsp, 850h
0x18008db72  pop     r15
0x18008db74  pop     r14
0x18008db76  pop     r13
0x18008db78  pop     r12
0x18008db7a  pop     rdi
0x18008db7b  pop     rsi
0x18008db7c  pop     rbp
0x18008db7d  retn
```
