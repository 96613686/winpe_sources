# RasLineMakeCall_postProcess

- ea: `0x180025e40`
- end: `0x180026194`
- name: `RasLineMakeCall_postProcess`
- size: `852`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x180025e40`
- `0x180027414`
- `0x180027888`
- `0x180027a10`
- `0x1800281f0`
- `0x180028b5c`
- `0x180028c70`
- `0x180029130`
- `0x18002927e`
- `0x1800292b0`
- `0x18002a010`

## import_xrefs

- `rtutils!TracePrintfA` at `0x180025f07`
- `rtutils!TracePrintfA` at `0x180025f90`
- `rtutils!TracePrintfA` at `0x180026022`
- `rtutils!TracePrintfA` at `0x1800260f4`
- `rtutils!TracePrintfA` at `0x180025f07`
- `rtutils!TracePrintfA` at `0x180025f90`
- `rtutils!TracePrintfA` at `0x180026022`
- `rtutils!TracePrintfA` at `0x1800260f4`

## string_xrefs

- `0x180025fca`: `RasLineMakeCall_postProcess: GetLineObjWithReadLock failed with error (0x%x)`
- `0x180026018`: `RasLineMakeCall_postProcess: GetLineObjWithReadLock failed with error (0x%x)`
- `0x180026055`: `RasLineMakeCall_postProcess: GetCallObjWithWriteLock failed with error (0x%x)`
- `0x180026070`: `RasLineMakeCall_postProcess: GetCallObjWithWriteLock failed with error (0x%x)`

## pseudocode

```c
__int64 __fastcall RasLineMakeCall_postProcess(__int64 a1, unsigned int a2, _QWORD *a3)
{
  int v3; // r15d
  unsigned int v7; // esi
  unsigned int v8; // eax
  unsigned int v9; // ebx
  unsigned int LineObjWithReadLock; // eax
  unsigned int *v11; // r12
  const wchar_t *v12; // rdx
  unsigned int *v13; // rdi
  unsigned int v14; // r8d
  unsigned int v16; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int *v17; // [rsp+28h] [rbp-D8h] BYREF
  unsigned int *v18; // [rsp+30h] [rbp-D0h] BYREF
  int v19; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v20[2044]; // [rsp+44h] [rbp-BCh] BYREF

  v3 = 0;
  v16 = 0;
  v18 = 0;
  v17 = 0;
  v19 = 0;
  memset_0(v20, 0, sizeof(v20));
  if ( gIsndpspEtwTracingAvailable )
  {
    if ( qword_18003EC40 )
    {
      LOWORD(v19) = 0;
      FormatRRASErrorString(&v19, L"RasLineMakeCall_postProcess called with dwRetCode (0x%x)", a2);
      ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v19);
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
      if ( qword_18003EC40 )
      {
        LOWORD(v19) = 0;
        FormatRRASErrorString(
          &v19,
          L"RasLineMakeCall_postProcess: GetLineHandleFromCallHandle failed with error (0x%x)",
          v8);
        ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v19);
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
      goto LABEL_36;
    }
    if ( qword_18003EC40 )
    {
      v12 = L"RasLineMakeCall_postProcess: GetLineObjWithReadLock failed with error (0x%x)";
LABEL_16:
      LOWORD(v19) = 0;
      FormatRRASErrorString(&v19, v12, v9);
      ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v19);
    }
  }
  else
  {
    v9 = GetCallObjWithWriteLock(v7, &v17);
    if ( !v9 )
    {
      if ( a2 )
      {
        *v17 = 1482184792;
        ReleaseObjWriteLock(v7);
        v3 = 1;
      }
      else
      {
        v13 = v17;
        v14 = v17[9];
        if ( v14 )
        {
          if ( gIsndpspEtwTracingAvailable )
          {
            if ( qword_18003EC40 )
            {
              LOWORD(v19) = 0;
              FormatRRASErrorString(
                &v19,
                L"RasLineMakeCall_postProcess: Executing the pending LINE_CALLSTATE message 0x%x",
                v17[9]);
              ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(
                gNdpspEtwContext,
                qword_18003EC40,
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
          *a3 = v11[2];
          a3[1] = v13[2];
          a3[2] = v13[9];
          a3[3] = v13[10];
          a3[4] = v13[11];
        }
        *((_QWORD *)v13 + 3) = *(_QWORD *)(a1 + 176);
        v13[16] = 0;
        ReleaseObjWriteLock(v7);
      }
      goto LABEL_36;
    }
    if ( !gIsndpspEtwTracingAvailable )
    {
      if ( dwTraceId != -1 )
        TracePrintfA(dwTraceId, "RasLineMakeCall_postProcess: GetCallObjWithWriteLock failed with error (0x%x)", v9);
      goto LABEL_36;
    }
    if ( qword_18003EC40 )
    {
      v12 = L"RasLineMakeCall_postProcess: GetCallObjWithWriteLock failed with error (0x%x)";
      goto LABEL_16;
    }
  }
LABEL_36:
  if ( v11 )
    ReleaseObjReadLock(v16);
  if ( v3 )
    CloseObjHandle(v7);
  return v9;
}

```

## disassembly

```asm
0x180025e40  mov     [rsp-8+arg_18], rbx
0x180025e45  push    rbp
0x180025e46  push    rsi
0x180025e47  push    rdi
0x180025e48  push    r12
0x180025e4a  push    r13
0x180025e4c  push    r14
0x180025e4e  push    r15
0x180025e50  lea     rbp, [rsp-750h]
0x180025e58  sub     rsp, 850h
0x180025e5f  mov     rax, cs:__security_cookie
0x180025e66  xor     rax, rsp
0x180025e69  mov     [rbp+780h+var_40], rax
0x180025e70  xor     r15d, r15d
0x180025e73  mov     r14, r8
0x180025e76  mov     edi, edx
0x180025e78  mov     [rsp+880h+var_860], r15d
0x180025e7d  mov     r13, rcx
0x180025e80  mov     [rsp+880h+var_850], r15
0x180025e85  xor     edx, edx; Val
0x180025e87  mov     [rsp+880h+var_858], r15
0x180025e8c  mov     r8d, 7FCh; Size
0x180025e92  mov     [rsp+880h+var_840], r15d
0x180025e97  lea     rcx, [rsp+880h+var_83C]; void *
0x180025e9c  call    memset_0
0x180025ea1  or      r12d, 0FFFFFFFFh
0x180025ea5  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x180025eac  jz      short loc_180025EF2
0x180025eae  cmp     cs:qword_18003EC40, r15
0x180025eb5  jz      short loc_180025F0D
0x180025eb7  mov     r8d, edi
0x180025eba  mov     word ptr [rsp+880h+var_840], r15w
0x180025ec0  lea     rdx, aRaslinemakecal_6; "RasLineMakeCall_postProcess called with"...
0x180025ec7  lea     rcx, [rsp+880h+var_840]
0x180025ecc  call    FormatRRASErrorString
0x180025ed1  mov     rdx, cs:qword_18003EC40
0x180025ed8  lea     r8, [rsp+880h+var_840]
0x180025edd  mov     rcx, cs:gNdpspEtwContext
0x180025ee4  mov     rax, cs:gNdpspTemplateFunc
0x180025eeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ef0  jmp     short loc_180025F0D
0x180025ef2  mov     ecx, cs:dwTraceId; dwTraceID
0x180025ef8  cmp     ecx, r12d
0x180025efb  jz      short loc_180025F0D
0x180025efd  mov     r8d, edi
0x180025f00  lea     rdx, aRaslinemakecal_10; "RasLineMakeCall_postProcess called with"...
0x180025f07  call    cs:__imp_TracePrintfA
0x180025f0d  mov     esi, [r13+60h]
0x180025f11  lea     rdx, [rsp+880h+var_860]
0x180025f16  mov     ecx, esi
0x180025f18  call    GetLineHandleFromCallHandle
0x180025f1d  mov     ebx, eax
0x180025f1f  test    eax, eax
0x180025f21  jz      short loc_180025F9B
0x180025f23  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x180025f2a  jz      short loc_180025F77
0x180025f2c  cmp     cs:qword_18003EC40, r15
0x180025f33  jz      loc_180026168
0x180025f39  mov     r8d, eax
0x180025f3c  mov     word ptr [rsp+880h+var_840], r15w
0x180025f42  lea     rdx, aRaslinemakecal_3; "RasLineMakeCall_postProcess: GetLineHan"...
0x180025f49  lea     rcx, [rsp+880h+var_840]
0x180025f4e  call    FormatRRASErrorString
0x180025f53  mov     rdx, cs:qword_18003EC40
0x180025f5a  lea     r8, [rsp+880h+var_840]
0x180025f5f  mov     rcx, cs:gNdpspEtwContext
0x180025f66  mov     rax, cs:gNdpspTemplateFunc
0x180025f6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f72  jmp     loc_180026168
0x180025f77  mov     ecx, cs:dwTraceId; dwTraceID
0x180025f7d  cmp     ecx, r12d
0x180025f80  jz      loc_180026168
0x180025f86  mov     r8d, eax
0x180025f89  lea     rdx, aRaslinemakecal_18; "RasLineMakeCall_postProcess: GetLineHan"...
0x180025f90  call    cs:__imp_TracePrintfA
0x180025f96  jmp     loc_180026168
0x180025f9b  mov     ecx, [rsp+880h+var_860]
0x180025f9f  lea     rdx, [rsp+880h+var_850]
0x180025fa4  call    GetLineObjWithReadLock
0x180025fa9  mov     r12, [rsp+880h+var_850]
0x180025fae  mov     ebx, eax
0x180025fb0  test    eax, eax
0x180025fb2  jz      short loc_18002602D
0x180025fb4  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x180025fbb  jz      short loc_180026009
0x180025fbd  cmp     cs:qword_18003EC40, r15
0x180025fc4  jz      loc_18002614E
0x180025fca  lea     rdx, aRaslinemakecal_2; "RasLineMakeCall_postProcess: GetLineObj"...
0x180025fd1  xor     eax, eax
0x180025fd3  lea     rcx, [rsp+880h+var_840]
0x180025fd8  mov     r8d, ebx
0x180025fdb  mov     word ptr [rsp+880h+var_840], ax
0x180025fe0  call    FormatRRASErrorString
0x180025fe5  mov     rdx, cs:qword_18003EC40
0x180025fec  lea     r8, [rsp+880h+var_840]
0x180025ff1  mov     rcx, cs:gNdpspEtwContext
0x180025ff8  mov     rax, cs:gNdpspTemplateFunc
0x180025fff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026004  jmp     loc_18002614E
0x180026009  mov     ecx, cs:dwTraceId; dwTraceID
0x18002600f  cmp     ecx, 0FFFFFFFFh
0x180026012  jz      loc_18002614E
0x180026018  lea     rdx, aRaslinemakecal_9; "RasLineMakeCall_postProcess: GetLineObj"...
0x18002601f  mov     r8d, ebx
0x180026022  call    cs:__imp_TracePrintfA
0x180026028  jmp     loc_18002614E
0x18002602d  lea     rdx, [rsp+880h+var_858]
0x180026032  mov     ecx, esi
0x180026034  call    GetCallObjWithWriteLock
0x180026039  mov     ebx, eax
0x18002603b  test    eax, eax
0x18002603d  jz      short loc_180026079
0x18002603f  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x180026046  jz      short loc_180026061
0x180026048  cmp     cs:qword_18003EC40, r15
0x18002604f  jz      loc_18002614E
0x180026055  lea     rdx, aRaslinemakecal_16; "RasLineMakeCall_postProcess: GetCallObj"...
0x18002605c  jmp     loc_180025FD1
0x180026061  mov     ecx, cs:dwTraceId
0x180026067  cmp     ecx, 0FFFFFFFFh
0x18002606a  jz      loc_18002614E
0x180026070  lea     rdx, aRaslinemakecal_15; "RasLineMakeCall_postProcess: GetCallObj"...
0x180026077  jmp     short loc_18002601F
0x180026079  test    edi, edi
0x18002607b  jnz     loc_180026136
0x180026081  mov     rdi, [rsp+880h+var_858]
0x180026086  mov     r8d, [rdi+24h]
0x18002608a  test    r8d, r8d
0x18002608d  jz      loc_18002611E
0x180026093  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x18002609a  jz      short loc_1800260E2
0x18002609c  cmp     cs:qword_18003EC40, r15
0x1800260a3  jz      short loc_1800260FA
0x1800260a5  xor     eax, eax
0x1800260a7  lea     rdx, aRaslinemakecal_7; "RasLineMakeCall_postProcess: Executing "...
0x1800260ae  mov     word ptr [rsp+880h+var_840], ax
0x1800260b3  lea     rcx, [rsp+880h+var_840]
0x1800260b8  mov     r8d, [rdi+24h]
0x1800260bc  call    FormatRRASErrorString
0x1800260c1  mov     rdx, cs:qword_18003EC40
0x1800260c8  lea     r8, [rsp+880h+var_840]
0x1800260cd  mov     rcx, cs:gNdpspEtwContext
0x1800260d4  mov     rax, cs:gNdpspTemplateFunc
0x1800260db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800260e0  jmp     short loc_1800260FA
0x1800260e2  mov     ecx, cs:dwTraceId; dwTraceID
0x1800260e8  cmp     ecx, 0FFFFFFFFh
0x1800260eb  jz      short loc_1800260FA
0x1800260ed  lea     rdx, aRaslinemakecal_1; "RasLineMakeCall_postProcess: Executing "...
0x1800260f4  call    cs:__imp_TracePrintfA
0x1800260fa  mov     eax, [r12+8]
0x1800260ff  mov     [r14], rax
0x180026102  mov     eax, [rdi+8]
0x180026105  mov     [r14+8], rax
0x180026109  mov     eax, [rdi+24h]
0x18002610c  mov     [r14+10h], rax
0x180026110  mov     eax, [rdi+28h]
0x180026113  mov     [r14+18h], rax
0x180026117  mov     eax, [rdi+2Ch]
0x18002611a  mov     [r14+20h], rax
0x18002611e  mov     rax, [r13+0B0h]
0x180026125  mov     ecx, esi
0x180026127  mov     [rdi+18h], rax
0x18002612b  mov     [rdi+40h], r15d
0x18002612f  call    ReleaseObjWriteLock
0x180026134  jmp     short loc_18002614E
0x180026136  mov     rax, [rsp+880h+var_858]
0x18002613b  mov     ecx, esi
0x18002613d  mov     dword ptr [rax], 58585858h
0x180026143  call    ReleaseObjWriteLock
0x180026148  mov     r15d, 1
0x18002614e  test    r12, r12
0x180026151  jz      short loc_18002615C
0x180026153  mov     ecx, [rsp+880h+var_860]
0x180026157  call    ReleaseObjReadLock
0x18002615c  test    r15d, r15d
0x18002615f  jz      short loc_180026168
0x180026161  mov     ecx, esi
0x180026163  call    CloseObjHandle
0x180026168  mov     eax, ebx
0x18002616a  mov     rcx, [rbp+780h+var_40]
0x180026171  xor     rcx, rsp; StackCookie
0x180026174  call    __security_check_cookie
0x180026179  mov     rbx, [rsp+880h+arg_18]
0x180026181  add     rsp, 850h
0x180026188  pop     r15
0x18002618a  pop     r14
0x18002618c  pop     r13
0x18002618e  pop     r12
0x180026190  pop     rdi
0x180026191  pop     rsi
0x180026192  pop     rbp
0x180026193  retn
```
