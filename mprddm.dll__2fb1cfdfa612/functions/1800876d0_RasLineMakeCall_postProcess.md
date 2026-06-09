# RasLineMakeCall_postProcess

- ea: `0x1800876d0`
- end: `0x180087a24`
- name: `RasLineMakeCall_postProcess`
- size: `852`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x180071cec`
- `0x1800876d0`
- `0x180088cc0`
- `0x180089134`
- `0x1800892bc`
- `0x180089a9c`
- `0x18008a408`
- `0x18008a51c`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `rtutils!TracePrintfA` at `0x180087797`
- `rtutils!TracePrintfA` at `0x180087820`
- `rtutils!TracePrintfA` at `0x1800878b2`
- `rtutils!TracePrintfA` at `0x180087984`
- `rtutils!TracePrintfA` at `0x180087797`
- `rtutils!TracePrintfA` at `0x180087820`
- `rtutils!TracePrintfA` at `0x1800878b2`
- `rtutils!TracePrintfA` at `0x180087984`

## string_xrefs

- `0x1800878a8`: `RasLineMakeCall_postProcess: GetLineObjWithReadLock failed with error (0x%x)`
- `0x18008785a`: `RasLineMakeCall_postProcess: GetLineObjWithReadLock failed with error (0x%x)`
- `0x180087900`: `RasLineMakeCall_postProcess: GetCallObjWithWriteLock failed with error (0x%x)`
- `0x1800878e5`: `RasLineMakeCall_postProcess: GetCallObjWithWriteLock failed with error (0x%x)`

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
    if ( (_QWORD)xmmword_1800C9BE0 )
    {
      LOWORD(v19) = 0;
      FormatRRASErrorString(&v19, L"RasLineMakeCall_postProcess called with dwRetCode (0x%x)", a2);
      ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v19);
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
      if ( (_QWORD)xmmword_1800C9BE0 )
      {
        LOWORD(v19) = 0;
        FormatRRASErrorString(
          &v19,
          L"RasLineMakeCall_postProcess: GetLineHandleFromCallHandle failed with error (0x%x)",
          v8);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v19);
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
    if ( (_QWORD)xmmword_1800C9BE0 )
    {
      v12 = L"RasLineMakeCall_postProcess: GetLineObjWithReadLock failed with error (0x%x)";
LABEL_16:
      LOWORD(v19) = 0;
      FormatRRASErrorString(&v19, v12, v9);
      ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v19);
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
            if ( (_QWORD)xmmword_1800C9BE0 )
            {
              LOWORD(v19) = 0;
              FormatRRASErrorString(
                &v19,
                L"RasLineMakeCall_postProcess: Executing the pending LINE_CALLSTATE message 0x%x",
                v17[9]);
              ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(
                gNdpspEtwContext,
                xmmword_1800C9BE0,
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
    if ( (_QWORD)xmmword_1800C9BE0 )
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
0x1800876d0  mov     [rsp-8+arg_18], rbx
0x1800876d5  push    rbp
0x1800876d6  push    rsi
0x1800876d7  push    rdi
0x1800876d8  push    r12
0x1800876da  push    r13
0x1800876dc  push    r14
0x1800876de  push    r15
0x1800876e0  lea     rbp, [rsp-750h]
0x1800876e8  sub     rsp, 850h
0x1800876ef  mov     rax, cs:__security_cookie
0x1800876f6  xor     rax, rsp
0x1800876f9  mov     [rbp+780h+var_40], rax
0x180087700  xor     r15d, r15d
0x180087703  mov     r14, r8
0x180087706  mov     edi, edx
0x180087708  mov     [rsp+880h+var_860], r15d
0x18008770d  mov     r13, rcx
0x180087710  mov     [rsp+880h+var_850], r15
0x180087715  xor     edx, edx; Val
0x180087717  mov     [rsp+880h+var_858], r15
0x18008771c  mov     r8d, 7FCh; Size
0x180087722  mov     [rsp+880h+var_840], r15d
0x180087727  lea     rcx, [rsp+880h+var_83C]; void *
0x18008772c  call    memset_0
0x180087731  or      r12d, 0FFFFFFFFh
0x180087735  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x18008773c  jz      short loc_180087782
0x18008773e  cmp     qword ptr cs:xmmword_1800C9BE0, r15
0x180087745  jz      short loc_18008779D
0x180087747  mov     r8d, edi
0x18008774a  mov     word ptr [rsp+880h+var_840], r15w
0x180087750  lea     rdx, aRaslinemakecal_6; "RasLineMakeCall_postProcess called with"...
0x180087757  lea     rcx, [rsp+880h+var_840]
0x18008775c  call    FormatRRASErrorString
0x180087761  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180087768  lea     r8, [rsp+880h+var_840]
0x18008776d  mov     rcx, cs:gNdpspEtwContext
0x180087774  mov     rax, cs:gNdpspTemplateFunc
0x18008777b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087780  jmp     short loc_18008779D
0x180087782  mov     ecx, cs:dwTraceId; dwTraceID
0x180087788  cmp     ecx, r12d
0x18008778b  jz      short loc_18008779D
0x18008778d  mov     r8d, edi
0x180087790  lea     rdx, aRaslinemakecal_10; "RasLineMakeCall_postProcess called with"...
0x180087797  call    cs:__imp_TracePrintfA
0x18008779d  mov     esi, [r13+60h]
0x1800877a1  lea     rdx, [rsp+880h+var_860]
0x1800877a6  mov     ecx, esi
0x1800877a8  call    GetLineHandleFromCallHandle
0x1800877ad  mov     ebx, eax
0x1800877af  test    eax, eax
0x1800877b1  jz      short loc_18008782B
0x1800877b3  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x1800877ba  jz      short loc_180087807
0x1800877bc  cmp     qword ptr cs:xmmword_1800C9BE0, r15
0x1800877c3  jz      loc_1800879F8
0x1800877c9  mov     r8d, eax
0x1800877cc  mov     word ptr [rsp+880h+var_840], r15w
0x1800877d2  lea     rdx, aRaslinemakecal_3; "RasLineMakeCall_postProcess: GetLineHan"...
0x1800877d9  lea     rcx, [rsp+880h+var_840]
0x1800877de  call    FormatRRASErrorString
0x1800877e3  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x1800877ea  lea     r8, [rsp+880h+var_840]
0x1800877ef  mov     rcx, cs:gNdpspEtwContext
0x1800877f6  mov     rax, cs:gNdpspTemplateFunc
0x1800877fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087802  jmp     loc_1800879F8
0x180087807  mov     ecx, cs:dwTraceId; dwTraceID
0x18008780d  cmp     ecx, r12d
0x180087810  jz      loc_1800879F8
0x180087816  mov     r8d, eax
0x180087819  lea     rdx, aRaslinemakecal_18; "RasLineMakeCall_postProcess: GetLineHan"...
0x180087820  call    cs:__imp_TracePrintfA
0x180087826  jmp     loc_1800879F8
0x18008782b  mov     ecx, [rsp+880h+var_860]
0x18008782f  lea     rdx, [rsp+880h+var_850]
0x180087834  call    GetLineObjWithReadLock
0x180087839  mov     r12, [rsp+880h+var_850]
0x18008783e  mov     ebx, eax
0x180087840  test    eax, eax
0x180087842  jz      short loc_1800878BD
0x180087844  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x18008784b  jz      short loc_180087899
0x18008784d  cmp     qword ptr cs:xmmword_1800C9BE0, r15
0x180087854  jz      loc_1800879DE
0x18008785a  lea     rdx, aRaslinemakecal_2; "RasLineMakeCall_postProcess: GetLineObj"...
0x180087861  xor     eax, eax
0x180087863  lea     rcx, [rsp+880h+var_840]
0x180087868  mov     r8d, ebx
0x18008786b  mov     word ptr [rsp+880h+var_840], ax
0x180087870  call    FormatRRASErrorString
0x180087875  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x18008787c  lea     r8, [rsp+880h+var_840]
0x180087881  mov     rcx, cs:gNdpspEtwContext
0x180087888  mov     rax, cs:gNdpspTemplateFunc
0x18008788f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087894  jmp     loc_1800879DE
0x180087899  mov     ecx, cs:dwTraceId; dwTraceID
0x18008789f  cmp     ecx, 0FFFFFFFFh
0x1800878a2  jz      loc_1800879DE
0x1800878a8  lea     rdx, aRaslinemakecal_9; "RasLineMakeCall_postProcess: GetLineObj"...
0x1800878af  mov     r8d, ebx
0x1800878b2  call    cs:__imp_TracePrintfA
0x1800878b8  jmp     loc_1800879DE
0x1800878bd  lea     rdx, [rsp+880h+var_858]
0x1800878c2  mov     ecx, esi
0x1800878c4  call    GetCallObjWithWriteLock
0x1800878c9  mov     ebx, eax
0x1800878cb  test    eax, eax
0x1800878cd  jz      short loc_180087909
0x1800878cf  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x1800878d6  jz      short loc_1800878F1
0x1800878d8  cmp     qword ptr cs:xmmword_1800C9BE0, r15
0x1800878df  jz      loc_1800879DE
0x1800878e5  lea     rdx, aRaslinemakecal_16; "RasLineMakeCall_postProcess: GetCallObj"...
0x1800878ec  jmp     loc_180087861
0x1800878f1  mov     ecx, cs:dwTraceId
0x1800878f7  cmp     ecx, 0FFFFFFFFh
0x1800878fa  jz      loc_1800879DE
0x180087900  lea     rdx, aRaslinemakecal_15; "RasLineMakeCall_postProcess: GetCallObj"...
0x180087907  jmp     short loc_1800878AF
0x180087909  test    edi, edi
0x18008790b  jnz     loc_1800879C6
0x180087911  mov     rdi, [rsp+880h+var_858]
0x180087916  mov     r8d, [rdi+24h]
0x18008791a  test    r8d, r8d
0x18008791d  jz      loc_1800879AE
0x180087923  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x18008792a  jz      short loc_180087972
0x18008792c  cmp     qword ptr cs:xmmword_1800C9BE0, r15
0x180087933  jz      short loc_18008798A
0x180087935  xor     eax, eax
0x180087937  lea     rdx, aRaslinemakecal_7; "RasLineMakeCall_postProcess: Executing "...
0x18008793e  mov     word ptr [rsp+880h+var_840], ax
0x180087943  lea     rcx, [rsp+880h+var_840]
0x180087948  mov     r8d, [rdi+24h]
0x18008794c  call    FormatRRASErrorString
0x180087951  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180087958  lea     r8, [rsp+880h+var_840]
0x18008795d  mov     rcx, cs:gNdpspEtwContext
0x180087964  mov     rax, cs:gNdpspTemplateFunc
0x18008796b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087970  jmp     short loc_18008798A
0x180087972  mov     ecx, cs:dwTraceId; dwTraceID
0x180087978  cmp     ecx, 0FFFFFFFFh
0x18008797b  jz      short loc_18008798A
0x18008797d  lea     rdx, aRaslinemakecal_1; "RasLineMakeCall_postProcess: Executing "...
0x180087984  call    cs:__imp_TracePrintfA
0x18008798a  mov     eax, [r12+8]
0x18008798f  mov     [r14], rax
0x180087992  mov     eax, [rdi+8]
0x180087995  mov     [r14+8], rax
0x180087999  mov     eax, [rdi+24h]
0x18008799c  mov     [r14+10h], rax
0x1800879a0  mov     eax, [rdi+28h]
0x1800879a3  mov     [r14+18h], rax
0x1800879a7  mov     eax, [rdi+2Ch]
0x1800879aa  mov     [r14+20h], rax
0x1800879ae  mov     rax, [r13+0B0h]
0x1800879b5  mov     ecx, esi
0x1800879b7  mov     [rdi+18h], rax
0x1800879bb  mov     [rdi+40h], r15d
0x1800879bf  call    ReleaseObjWriteLock
0x1800879c4  jmp     short loc_1800879DE
0x1800879c6  mov     rax, [rsp+880h+var_858]
0x1800879cb  mov     ecx, esi
0x1800879cd  mov     dword ptr [rax], 58585858h
0x1800879d3  call    ReleaseObjWriteLock
0x1800879d8  mov     r15d, 1
0x1800879de  test    r12, r12
0x1800879e1  jz      short loc_1800879EC
0x1800879e3  mov     ecx, [rsp+880h+var_860]
0x1800879e7  call    ReleaseObjReadLock
0x1800879ec  test    r15d, r15d
0x1800879ef  jz      short loc_1800879F8
0x1800879f1  mov     ecx, esi
0x1800879f3  call    CloseObjHandle
0x1800879f8  mov     eax, ebx
0x1800879fa  mov     rcx, [rbp+780h+var_40]
0x180087a01  xor     rcx, rsp; StackCookie
0x180087a04  call    __security_check_cookie
0x180087a09  mov     rbx, [rsp+880h+arg_18]
0x180087a11  add     rsp, 850h
0x180087a18  pop     r15
0x180087a1a  pop     r14
0x180087a1c  pop     r13
0x180087a1e  pop     r12
0x180087a20  pop     rdi
0x180087a21  pop     rsi
0x180087a22  pop     rbp
0x180087a23  retn
```
