# RasLineGetCallInfo

- ea: `0x1800864d8`
- end: `0x180086ac8`
- name: `RasLineGetCallInfo`
- size: `1520`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x180028570`
- `0x180084ae0`

## callees

- `0x180071cec`
- `0x18008490c`
- `0x1800864d8`
- `0x1800884f8`
- `0x180088848`
- `0x1800889ec`
- `0x180088b1c`
- `0x1800895e4`
- `0x18008a408`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180086a7b`
- `KERNEL32!GetProcessHeap` at `0x180086a7b`
- `KERNEL32!HeapFree` at `0x180086a89`
- `KERNEL32!HeapFree` at `0x180086a89`
- `rtutils!TracePrintfA` at `0x1800865c1`
- `rtutils!TracePrintfA` at `0x18008665d`
- `rtutils!TracePrintfA` at `0x1800867be`
- `rtutils!TracePrintfA` at `0x1800865c1`
- `rtutils!TracePrintfA` at `0x18008665d`
- `rtutils!TracePrintfA` at `0x1800867be`

## string_xrefs

- `0x1800865ba`: `RasLineGetCallInfo: GetCallObjWithReadLock failed with error (0x%x)`
- `0x18008656b`: `RasLineGetCallInfo: GetCallObjWithReadLock failed with error (0x%x)`

## pseudocode

```c
__int64 __fastcall RasLineGetCallInfo(unsigned int a1, __int64 a2)
{
  int v2; // ebx
  unsigned int v5; // eax
  unsigned int *v6; // r13
  unsigned int NDProxyHandle; // esi
  unsigned int v8; // eax
  char *v9; // r15
  const wchar_t *v10; // rdx
  unsigned int *v11; // rdi
  int v12; // ebx
  unsigned int v13; // eax
  bool v14; // cf
  bool v15; // zf
  HANDLE ProcessHeap; // rax
  unsigned int *v18; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-C8h] BYREF
  int v20; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v21[2044]; // [rsp+44h] [rbp-BCh] BYREF

  v2 = *(_DWORD *)a2;
  lpMem = 0;
  v18 = 0;
  v20 = 0;
  memset_0(v21, 0, sizeof(v21));
  v5 = GetCallObjWithReadLock(a1, &v18);
  v6 = v18;
  NDProxyHandle = v5;
  if ( v5 )
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800C9BE0 )
      {
        LOWORD(v20) = 0;
        FormatRRASErrorString(&v20, L"RasLineGetCallInfo: GetCallObjWithReadLock failed with error (0x%x)", v5);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v20);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "RasLineGetCallInfo: GetCallObjWithReadLock failed with error (0x%x)", v5);
    }
    goto LABEL_39;
  }
  v8 = PrepareSyncRequest(117637390, v18[1], (unsigned int)(v2 + 16), &lpMem);
  v9 = (char *)lpMem;
  NDProxyHandle = v8;
  if ( v8 )
  {
    if ( !gIsndpspEtwTracingAvailable )
    {
      if ( dwTraceId != -1 )
        TracePrintfA(dwTraceId, "RasLineGetCallInfo: PrepareSyncRequest failed with error (0x%x)", v8);
      goto LABEL_37;
    }
    if ( (_QWORD)xmmword_1800C9BE0 )
    {
      v10 = L"RasLineGetCallInfo: PrepareSyncRequest failed with error (0x%x)";
LABEL_11:
      LOWORD(v20) = 0;
      FormatRRASErrorString(&v20, v10, NDProxyHandle);
LABEL_12:
      ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v20);
    }
  }
  else
  {
    NDProxyHandle = GetNDProxyHandle(v6, (char *)lpMem + 56);
    if ( NDProxyHandle )
    {
      if ( !gIsndpspEtwTracingAvailable )
      {
        if ( dwTraceId != -1 )
          TracePrintfA(dwTraceId, "RasLineGetCallInfo: GetNDProxyHandle failed with error (0x%x)", NDProxyHandle);
        goto LABEL_37;
      }
      if ( (_QWORD)xmmword_1800C9BE0 )
      {
        v10 = L"RasLineGetCallInfo: GetNDProxyHandle failed with error (0x%x)";
        goto LABEL_11;
      }
    }
    else
    {
      v11 = (unsigned int *)(v9 + 64);
      v12 = 344;
      *((_DWORD *)v9 + 16) = *(_DWORD *)a2;
      *((_DWORD *)v9 + 18) = 344;
      *((_DWORD *)v9 + 17) = 344;
      NDProxyHandle = SyncDriverRequest(0x8FFF23C8, v9);
      if ( NDProxyHandle )
      {
        if ( !gIsndpspEtwTracingAvailable )
        {
          if ( dwTraceId != -1 )
            TracePrintfA(
              dwTraceId,
              "RasLineGetCallInfo: SyncDriverRequest(OID_TAPI_GET_CALL_INFO) failed with error (0x%x)",
              NDProxyHandle);
          goto LABEL_37;
        }
        if ( (_QWORD)xmmword_1800C9BE0 )
        {
          v10 = L"RasLineGetCallInfo: SyncDriverRequest(OID_TAPI_GET_CALL_INFO) failed with error (0x%x)";
          goto LABEL_11;
        }
      }
      else
      {
        *(_OWORD *)(a2 + 16) = *((_OWORD *)v9 + 5);
        *(_OWORD *)(a2 + 32) = *((_OWORD *)v9 + 6);
        *(_OWORD *)(a2 + 48) = *((_OWORD *)v9 + 7);
        *(_OWORD *)(a2 + 64) = *((_OWORD *)v9 + 8);
        *(_OWORD *)(a2 + 80) = *((_OWORD *)v9 + 9);
        *(_OWORD *)(a2 + 92) = *(_OWORD *)(v9 + 156);
        v13 = *((_DWORD *)v9 + 17);
        if ( v13 <= *v11 )
        {
          *(_DWORD *)(a2 + 8) = 344;
          *(_DWORD *)(a2 + 108) = *((_DWORD *)v9 + 43);
          CopyVariableData((unsigned int *)v9 + 16, (DWORD *)v9 + 44, a2, a2 + 112);
          ConvertWideStringVariableData(a2, a2 + 112);
          *(_DWORD *)(a2 + 324) = *((_DWORD *)v9 + 97);
          CopyVariableData((unsigned int *)v9 + 16, (DWORD *)v9 + 46, a2, a2 + 120);
          ConvertWideStringVariableData(a2, a2 + 120);
          *(_DWORD *)(a2 + 128) = *((_DWORD *)v9 + 48);
          CopyVariableData((unsigned int *)v9 + 16, (DWORD *)v9 + 49, a2, a2 + 132);
          ConvertWideStringVariableData(a2, a2 + 132);
          *(_DWORD *)(a2 + 328) = *((_DWORD *)v9 + 98);
          CopyVariableData((unsigned int *)v9 + 16, (DWORD *)v9 + 51, a2, a2 + 140);
          ConvertWideStringVariableData(a2, a2 + 140);
          *(_DWORD *)(a2 + 148) = *((_DWORD *)v9 + 53);
          CopyVariableData((unsigned int *)v9 + 16, (DWORD *)v9 + 54, a2, a2 + 152);
          ConvertWideStringVariableData(a2, a2 + 152);
          *(_DWORD *)(a2 + 332) = *((_DWORD *)v9 + 99);
          CopyVariableData((unsigned int *)v9 + 16, (DWORD *)v9 + 56, a2, a2 + 160);
          ConvertWideStringVariableData(a2, a2 + 160);
          *(_DWORD *)(a2 + 168) = *((_DWORD *)v9 + 58);
          CopyVariableData((unsigned int *)v9 + 16, (DWORD *)v9 + 59, a2, a2 + 172);
          ConvertWideStringVariableData(a2, a2 + 172);
          *(_DWORD *)(a2 + 336) = *((_DWORD *)v9 + 100);
          CopyVariableData((unsigned int *)v9 + 16, (DWORD *)v9 + 61, a2, a2 + 180);
          ConvertWideStringVariableData(a2, a2 + 180);
          *(_DWORD *)(a2 + 188) = *((_DWORD *)v9 + 63);
          CopyVariableData((unsigned int *)v9 + 16, (DWORD *)v9 + 64, a2, a2 + 192);
          ConvertWideStringVariableData(a2, a2 + 192);
          *(_DWORD *)(a2 + 340) = *((_DWORD *)v9 + 101);
          CopyVariableData((unsigned int *)v9 + 16, (DWORD *)v9 + 66, a2, a2 + 200);
          ConvertWideStringVariableData(a2, a2 + 200);
          CopyVariableData((unsigned int *)v9 + 16, (DWORD *)v9 + 76, a2, a2 + 240);
          CopyVariableData((unsigned int *)v9 + 16, (DWORD *)v9 + 78, a2, a2 + 248);
          CopyVariableData((unsigned int *)v9 + 16, (DWORD *)v9 + 80, a2, a2 + 256);
          CopyVariableData((unsigned int *)v9 + 16, (DWORD *)v9 + 82, a2, a2 + 264);
          CopyVariableData((unsigned int *)v9 + 16, (DWORD *)v9 + 84, a2, a2 + 272);
          CopyVariableData((unsigned int *)v9 + 16, (DWORD *)v9 + 86, a2, a2 + 280);
          CopyVariableData((unsigned int *)v9 + 16, (DWORD *)v9 + 88, a2, a2 + 288);
          *(_DWORD *)(a2 + 4) = *(_DWORD *)(a2 + 8);
        }
        else
        {
          v14 = *(_DWORD *)a2 < 0x158u;
          *(_DWORD *)(a2 + 4) = v13;
          if ( v14 )
            v12 = *(_DWORD *)a2;
          v15 = gIsndpspEtwTracingAvailable == 0;
          *(_DWORD *)(a2 + 8) = v12;
          if ( v15 )
          {
            if ( dwTraceId != -1 )
              TracePrintfA(
                dwTraceId,
                "RasLineGetCallInfo: The needed size (0x%x) for LINECALLINFO is more than the allocated size (0x%x)",
                *((_DWORD *)v9 + 17),
                *v11);
            goto LABEL_37;
          }
          if ( (_QWORD)xmmword_1800C9BE0 )
          {
            LOWORD(v20) = 0;
            FormatRRASErrorString(
              &v20,
              L"RasLineGetCallInfo: The needed size (0x%x) for LINECALLINFO is more than the allocated size (0x%x)",
              *((unsigned int *)v9 + 17),
              *v11);
            goto LABEL_12;
          }
        }
      }
    }
  }
LABEL_37:
  if ( v9 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v9);
  }
LABEL_39:
  if ( v6 )
    ReleaseObjReadLock(a1);
  return NDProxyHandle;
}

```

## disassembly

```asm
0x1800864d8  mov     [rsp-8+arg_10], rbx
0x1800864dd  push    rbp
0x1800864de  push    rsi
0x1800864df  push    rdi
0x1800864e0  push    r12
0x1800864e2  push    r13
0x1800864e4  push    r14
0x1800864e6  push    r15
0x1800864e8  lea     rbp, [rsp-750h]
0x1800864f0  sub     rsp, 850h
0x1800864f7  mov     rax, cs:__security_cookie
0x1800864fe  xor     rax, rsp
0x180086501  mov     [rbp+780h+var_40], rax
0x180086508  mov     ebx, [rdx]
0x18008650a  mov     r14, rdx
0x18008650d  mov     r12d, ecx
0x180086510  mov     [rsp+880h+lpMem], 0
0x180086519  xor     eax, eax
0x18008651b  mov     [rsp+880h+var_850], 0
0x180086524  xor     edx, edx; Val
0x180086526  mov     [rsp+880h+var_840], eax
0x18008652a  lea     rcx, [rsp+880h+var_83C]; void *
0x18008652f  mov     r8d, 7FCh; Size
0x180086535  call    memset_0
0x18008653a  lea     rdx, [rsp+880h+var_850]
0x18008653f  mov     ecx, r12d
0x180086542  call    GetCallObjWithReadLock
0x180086547  mov     r13, [rsp+880h+var_850]
0x18008654c  mov     esi, eax
0x18008654e  test    eax, eax
0x180086550  jz      short loc_1800865CC
0x180086552  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x180086559  jz      short loc_1800865A8
0x18008655b  cmp     qword ptr cs:xmmword_1800C9BE0, 0
0x180086563  jz      loc_180086A8F
0x180086569  xor     ecx, ecx
0x18008656b  lea     rdx, aRaslinegetcall_7; "RasLineGetCallInfo: GetCallObjWithReadL"...
0x180086572  mov     word ptr [rsp+880h+var_840], cx
0x180086577  mov     r8d, eax
0x18008657a  lea     rcx, [rsp+880h+var_840]
0x18008657f  call    FormatRRASErrorString
0x180086584  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x18008658b  lea     r8, [rsp+880h+var_840]
0x180086590  mov     rcx, cs:gNdpspEtwContext
0x180086597  mov     rax, cs:gNdpspTemplateFunc
0x18008659e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800865a3  jmp     loc_180086A8F
0x1800865a8  mov     ecx, cs:dwTraceId; dwTraceID
0x1800865ae  cmp     ecx, 0FFFFFFFFh
0x1800865b1  jz      loc_180086A8F
0x1800865b7  mov     r8d, eax
0x1800865ba  lea     rdx, aRaslinegetcall_0; "RasLineGetCallInfo: GetCallObjWithReadL"...
0x1800865c1  call    cs:__imp_TracePrintfA
0x1800865c7  jmp     loc_180086A8F
0x1800865cc  mov     edx, [r13+4]
0x1800865d0  lea     r9, [rsp+880h+lpMem]
0x1800865d5  lea     r8d, [rbx+10h]
0x1800865d9  mov     ecx, 703010Eh
0x1800865de  call    PrepareSyncRequest
0x1800865e3  mov     r15, [rsp+880h+lpMem]
0x1800865e8  mov     esi, eax
0x1800865ea  test    eax, eax
0x1800865ec  jz      short loc_180086668
0x1800865ee  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x1800865f5  jz      short loc_180086644
0x1800865f7  cmp     qword ptr cs:xmmword_1800C9BE0, 0
0x1800865ff  jz      loc_180086A76
0x180086605  lea     rdx, aRaslinegetcall_8; "RasLineGetCallInfo: PrepareSyncRequest "...
0x18008660c  xor     eax, eax
0x18008660e  lea     rcx, [rsp+880h+var_840]
0x180086613  mov     r8d, esi
0x180086616  mov     word ptr [rsp+880h+var_840], ax
0x18008661b  call    FormatRRASErrorString
0x180086620  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180086627  lea     r8, [rsp+880h+var_840]
0x18008662c  mov     rcx, cs:gNdpspEtwContext
0x180086633  mov     rax, cs:gNdpspTemplateFunc
0x18008663a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008663f  jmp     loc_180086A76
0x180086644  mov     ecx, cs:dwTraceId; dwTraceID
0x18008664a  cmp     ecx, 0FFFFFFFFh
0x18008664d  jz      loc_180086A76
0x180086653  lea     rdx, aRaslinegetcall_1; "RasLineGetCallInfo: PrepareSyncRequest "...
0x18008665a  mov     r8d, esi
0x18008665d  call    cs:__imp_TracePrintfA
0x180086663  jmp     loc_180086A76
0x180086668  lea     rdx, [r15+38h]
0x18008666c  mov     rcx, r13
0x18008666f  call    GetNDProxyHandle
0x180086674  mov     esi, eax
0x180086676  test    eax, eax
0x180086678  jz      short loc_1800866B5
0x18008667a  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x180086681  jz      short loc_18008669D
0x180086683  cmp     qword ptr cs:xmmword_1800C9BE0, 0
0x18008668b  jz      loc_180086A76
0x180086691  lea     rdx, aRaslinegetcall; "RasLineGetCallInfo: GetNDProxyHandle fa"...
0x180086698  jmp     loc_18008660C
0x18008669d  mov     ecx, cs:dwTraceId
0x1800866a3  cmp     ecx, 0FFFFFFFFh
0x1800866a6  jz      loc_180086A76
0x1800866ac  lea     rdx, aRaslinegetcall_3; "RasLineGetCallInfo: GetNDProxyHandle fa"...
0x1800866b3  jmp     short loc_18008665A
0x1800866b5  mov     eax, [r14]
0x1800866b8  lea     rdi, [r15+40h]
0x1800866bc  mov     ebx, 158h
0x1800866c1  mov     [rdi], eax
0x1800866c3  mov     rdx, r15; lpInBuffer
0x1800866c6  mov     [rdi+8], ebx
0x1800866c9  mov     ecx, 8FFF23C8h; dwIoControlCode
0x1800866ce  mov     [rdi+4], ebx
0x1800866d1  call    SyncDriverRequest
0x1800866d6  mov     esi, eax
0x1800866d8  test    eax, eax
0x1800866da  jz      short loc_18008671A
0x1800866dc  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x1800866e3  jz      short loc_1800866FF
0x1800866e5  cmp     qword ptr cs:xmmword_1800C9BE0, 0
0x1800866ed  jz      loc_180086A76
0x1800866f3  lea     rdx, aRaslinegetcall_4; "RasLineGetCallInfo: SyncDriverRequest(O"...
0x1800866fa  jmp     loc_18008660C
0x1800866ff  mov     ecx, cs:dwTraceId
0x180086705  cmp     ecx, 0FFFFFFFFh
0x180086708  jz      loc_180086A76
0x18008670e  lea     rdx, aRaslinegetcall_2; "RasLineGetCallInfo: SyncDriverRequest(O"...
0x180086715  jmp     loc_18008665A
0x18008671a  movups  xmm0, xmmword ptr [rdi+10h]
0x18008671e  movups  xmmword ptr [r14+10h], xmm0
0x180086723  movups  xmm1, xmmword ptr [rdi+20h]
0x180086727  movups  xmmword ptr [r14+20h], xmm1
0x18008672c  movups  xmm0, xmmword ptr [rdi+30h]
0x180086730  movups  xmmword ptr [r14+30h], xmm0
0x180086735  movups  xmm1, xmmword ptr [rdi+40h]
0x180086739  movups  xmmword ptr [r14+40h], xmm1
0x18008673e  movups  xmm0, xmmword ptr [rdi+50h]
0x180086742  movups  xmmword ptr [r14+50h], xmm0
0x180086747  movups  xmm1, xmmword ptr [rdi+5Ch]
0x18008674b  movups  xmmword ptr [r14+5Ch], xmm1
0x180086750  mov     eax, [rdi+4]
0x180086753  cmp     eax, [rdi]
0x180086755  jbe     short loc_1800867C9
0x180086757  cmp     [r14], ebx
0x18008675a  mov     [r14+4], eax
0x18008675e  cmovb   ebx, [r14]
0x180086762  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x180086769  mov     [r14+8], ebx
0x18008676d  jz      short loc_1800867A1
0x18008676f  cmp     qword ptr cs:xmmword_1800C9BE0, 0
0x180086777  jz      loc_180086A76
0x18008677d  xor     eax, eax
0x18008677f  lea     rdx, aRaslinegetcall_6; "RasLineGetCallInfo: The needed size (0x"...
0x180086786  mov     word ptr [rsp+880h+var_840], ax
0x18008678b  lea     rcx, [rsp+880h+var_840]
0x180086790  mov     r9d, [rdi]
0x180086793  mov     r8d, [rdi+4]
0x180086797  call    FormatRRASErrorString
0x18008679c  jmp     loc_180086620
0x1800867a1  mov     ecx, cs:dwTraceId; dwTraceID
0x1800867a7  cmp     ecx, 0FFFFFFFFh
0x1800867aa  jz      loc_180086A76
0x1800867b0  mov     r9d, [rdi]
0x1800867b3  lea     rdx, aRaslinegetcall_5; "RasLineGetCallInfo: The needed size (0x"...
0x1800867ba  mov     r8d, [rdi+4]
0x1800867be  call    cs:__imp_TracePrintfA
0x1800867c4  jmp     loc_180086A76
0x1800867c9  mov     [r14+8], ebx
0x1800867cd  lea     rdx, [rdi+70h]
0x1800867d1  mov     eax, [rdi+6Ch]
0x1800867d4  lea     r9, [r14+70h]
0x1800867d8  mov     r8, r14
0x1800867db  mov     [r14+6Ch], eax
0x1800867df  mov     rcx, rdi
0x1800867e2  call    CopyVariableData
0x1800867e7  lea     rdx, [r14+70h]
0x1800867eb  mov     rcx, r14
0x1800867ee  call    ConvertWideStringVariableData
0x1800867f3  mov     eax, [rdi+144h]
0x1800867f9  lea     rdx, [rdi+78h]
0x1800867fd  lea     r9, [r14+78h]
0x180086801  mov     [r14+144h], eax
0x180086808  mov     r8, r14
0x18008680b  mov     rcx, rdi
0x18008680e  call    CopyVariableData
0x180086813  lea     rdx, [r14+78h]
0x180086817  mov     rcx, r14
0x18008681a  call    ConvertWideStringVariableData
0x18008681f  mov     eax, [rdi+80h]
0x180086825  lea     rbx, [r14+84h]
0x18008682c  mov     r9, rbx
0x18008682f  mov     [r14+80h], eax
0x180086836  lea     rdx, [rdi+84h]
0x18008683d  mov     r8, r14
0x180086840  mov     rcx, rdi
0x180086843  call    CopyVariableData
0x180086848  mov     rdx, rbx
0x18008684b  mov     rcx, r14
0x18008684e  call    ConvertWideStringVariableData
0x180086853  mov     eax, [rdi+148h]
0x180086859  lea     rbx, [r14+8Ch]
0x180086860  mov     r9, rbx
0x180086863  mov     [r14+148h], eax
0x18008686a  lea     rdx, [rdi+8Ch]
0x180086871  mov     r8, r14
0x180086874  mov     rcx, rdi
0x180086877  call    CopyVariableData
0x18008687c  mov     rdx, rbx
0x18008687f  mov     rcx, r14
0x180086882  call    ConvertWideStringVariableData
0x180086887  mov     eax, [rdi+94h]
0x18008688d  lea     rbx, [r14+98h]
0x180086894  mov     r9, rbx
0x180086897  mov     [r14+94h], eax
0x18008689e  lea     rdx, [rdi+98h]
0x1800868a5  mov     r8, r14
0x1800868a8  mov     rcx, rdi
0x1800868ab  call    CopyVariableData
0x1800868b0  mov     rdx, rbx
0x1800868b3  mov     rcx, r14
0x1800868b6  call    ConvertWideStringVariableData
0x1800868bb  mov     eax, [rdi+14Ch]
0x1800868c1  lea     rbx, [r14+0A0h]
0x1800868c8  mov     r9, rbx
0x1800868cb  mov     [r14+14Ch], eax
0x1800868d2  lea     rdx, [rdi+0A0h]
0x1800868d9  mov     r8, r14
0x1800868dc  mov     rcx, rdi
0x1800868df  call    CopyVariableData
0x1800868e4  mov     rdx, rbx
0x1800868e7  mov     rcx, r14
0x1800868ea  call    ConvertWideStringVariableData
0x1800868ef  mov     eax, [rdi+0A8h]
0x1800868f5  lea     rbx, [r14+0ACh]
0x1800868fc  mov     r9, rbx
0x1800868ff  mov     [r14+0A8h], eax
0x180086906  lea     rdx, [rdi+0ACh]
0x18008690d  mov     r8, r14
0x180086910  mov     rcx, rdi
0x180086913  call    CopyVariableData
0x180086918  mov     rdx, rbx
0x18008691b  mov     rcx, r14
0x18008691e  call    ConvertWideStringVariableData
0x180086923  mov     eax, [rdi+150h]
0x180086929  lea     rbx, [r14+0B4h]
0x180086930  mov     [r14+150h], eax
0x180086937  lea     rdx, [rdi+0B4h]
0x18008693e  mov     r9, rbx
0x180086941  mov     r8, r14
0x180086944  mov     rcx, rdi
0x180086947  call    CopyVariableData
0x18008694c  mov     rdx, rbx
0x18008694f  mov     rcx, r14
0x180086952  call    ConvertWideStringVariableData
0x180086957  mov     eax, [rdi+0BCh]
0x18008695d  lea     rbx, [r14+0C0h]
0x180086964  mov     r9, rbx
0x180086967  mov     [r14+0BCh], eax
0x18008696e  lea     rdx, [rdi+0C0h]
0x180086975  mov     r8, r14
0x180086978  mov     rcx, rdi
0x18008697b  call    CopyVariableData
0x180086980  mov     rdx, rbx
0x180086983  mov     rcx, r14
0x180086986  call    ConvertWideStringVariableData
0x18008698b  mov     eax, [rdi+154h]
0x180086991  lea     rbx, [r14+0C8h]
0x180086998  mov     r9, rbx
0x18008699b  mov     [r14+154h], eax
0x1800869a2  lea     rdx, [rdi+0C8h]
0x1800869a9  mov     r8, r14
0x1800869ac  mov     rcx, rdi
0x1800869af  call    CopyVariableData
0x1800869b4  mov     rdx, rbx
0x1800869b7  mov     rcx, r14
0x1800869ba  call    ConvertWideStringVariableData
0x1800869bf  lea     r9, [r14+0F0h]
0x1800869c6  mov     r8, r14
0x1800869c9  lea     rdx, [rdi+0F0h]
0x1800869d0  mov     rcx, rdi
0x1800869d3  call    CopyVariableData
0x1800869d8  lea     r9, [r14+0F8h]
0x1800869df  mov     r8, r14
0x1800869e2  lea     rdx, [rdi+0F8h]
0x1800869e9  mov     rcx, rdi
0x1800869ec  call    CopyVariableData
0x1800869f1  lea     r9, [r14+100h]
0x1800869f8  mov     r8, r14
0x1800869fb  lea     rdx, [rdi+100h]
0x180086a02  mov     rcx, rdi
0x180086a05  call    CopyVariableData
0x180086a0a  lea     r9, [r14+108h]
0x180086a11  mov     r8, r14
0x180086a14  lea     rdx, [rdi+108h]
0x180086a1b  mov     rcx, rdi
0x180086a1e  call    CopyVariableData
0x180086a23  lea     r9, [r14+110h]
0x180086a2a  mov     r8, r14
0x180086a2d  lea     rdx, [rdi+110h]
0x180086a34  mov     rcx, rdi
0x180086a37  call    CopyVariableData
0x180086a3c  lea     r9, [r14+118h]
  ... truncated ...
```
