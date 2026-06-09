# RasLineGetCallInfo

- ea: `0x1800244ec`
- end: `0x180024b32`
- name: `RasLineGetCallInfo`
- size: `1606`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `12`
- tags: ``

## callers

- `0x18000272c`
- `0x18000cb80`
- `0x1800118f0`
- `0x1800131f0`
- `0x1800226f0`

## callees

- `0x18002251c`
- `0x1800244ec`
- `0x180026c4c`
- `0x180026f9c`
- `0x180027140`
- `0x180027270`
- `0x180027d38`
- `0x180028b5c`
- `0x180029130`
- `0x18002927e`
- `0x1800292b0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024ae6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024ae6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024af4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024af4`
- `rtutils!TracePrintfA` at `0x1800245cf`
- `rtutils!TracePrintfA` at `0x18002466a`
- `rtutils!TracePrintfA` at `0x1800247d0`
- `rtutils!TracePrintfA` at `0x1800245cf`
- `rtutils!TracePrintfA` at `0x18002466a`
- `rtutils!TracePrintfA` at `0x1800247d0`

## string_xrefs

- `0x180024581`: `RasLineGetCallInfo: GetCallObjWithReadLock failed with error (0x%x)`
- `0x1800245c8`: `RasLineGetCallInfo: GetCallObjWithReadLock failed with error (0x%x)`

## pseudocode

```c
__int64 __fastcall RasLineGetCallInfo(unsigned int a1, __int64 a2)
{
  int v2; // edi
  unsigned int v4; // ebx
  unsigned int v5; // eax
  unsigned int *v6; // r12
  unsigned int v7; // esi
  unsigned int NDProxyHandle; // eax
  char *v9; // r13
  const wchar_t *v10; // rdx
  unsigned int *v11; // rdi
  int v12; // r15d
  unsigned int v13; // eax
  bool v14; // cf
  HANDLE ProcessHeap; // rax
  unsigned int *v18; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID lpMem[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v20; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v21[2044]; // [rsp+54h] [rbp-ACh] BYREF

  v2 = *(_DWORD *)a2;
  v4 = a1;
  lpMem[0] = 0;
  v18 = 0;
  v20 = 0;
  memset_0(v21, 0, sizeof(v21));
  v5 = GetCallObjWithReadLock(v4, &v18);
  v6 = v18;
  v7 = v5;
  if ( v5 )
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( qword_18003EC40 )
      {
        LOWORD(v20) = 0;
        FormatRRASErrorString(&v20, L"RasLineGetCallInfo: GetCallObjWithReadLock failed with error (0x%x)", v5);
        ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v20);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "RasLineGetCallInfo: GetCallObjWithReadLock failed with error (0x%x)", v5);
    }
    goto LABEL_39;
  }
  NDProxyHandle = PrepareSyncRequest(0x703010Eu, v18[1], v2 + 16, lpMem);
  v9 = (char *)lpMem[0];
  v7 = NDProxyHandle;
  if ( NDProxyHandle )
  {
    if ( !gIsndpspEtwTracingAvailable )
    {
      if ( dwTraceId != -1 )
        TracePrintfA(dwTraceId, "RasLineGetCallInfo: PrepareSyncRequest failed with error (0x%x)", NDProxyHandle);
      goto LABEL_37;
    }
    if ( qword_18003EC40 )
    {
      v10 = L"RasLineGetCallInfo: PrepareSyncRequest failed with error (0x%x)";
LABEL_11:
      LOWORD(v20) = 0;
      FormatRRASErrorString(&v20, v10, NDProxyHandle);
LABEL_12:
      ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v20);
    }
  }
  else
  {
    NDProxyHandle = GetNDProxyHandle(v6, (char *)lpMem[0] + 56);
    v7 = NDProxyHandle;
    if ( NDProxyHandle )
    {
      if ( !gIsndpspEtwTracingAvailable )
      {
        if ( dwTraceId != -1 )
          TracePrintfA(dwTraceId, "RasLineGetCallInfo: GetNDProxyHandle failed with error (0x%x)", NDProxyHandle);
        goto LABEL_37;
      }
      if ( qword_18003EC40 )
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
      v7 = NDProxyHandle;
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
        if ( qword_18003EC40 )
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
          CopyVariableData((_DWORD *)v9 + 16, (DWORD *)v9 + 44, a2, a2 + 112, 0x158u);
          ConvertWideStringVariableData(a2, a2 + 112);
          *(_DWORD *)(a2 + 324) = *((_DWORD *)v9 + 97);
          CopyVariableData((_DWORD *)v9 + 16, (DWORD *)v9 + 46, a2, a2 + 120, 0x158u);
          ConvertWideStringVariableData(a2, a2 + 120);
          *(_DWORD *)(a2 + 128) = *((_DWORD *)v9 + 48);
          CopyVariableData((_DWORD *)v9 + 16, (DWORD *)v9 + 49, a2, a2 + 132, 0x158u);
          ConvertWideStringVariableData(a2, a2 + 132);
          *(_DWORD *)(a2 + 328) = *((_DWORD *)v9 + 98);
          CopyVariableData((_DWORD *)v9 + 16, (DWORD *)v9 + 51, a2, a2 + 140, 0x158u);
          ConvertWideStringVariableData(a2, a2 + 140);
          *(_DWORD *)(a2 + 148) = *((_DWORD *)v9 + 53);
          CopyVariableData((_DWORD *)v9 + 16, (DWORD *)v9 + 54, a2, a2 + 152, 0x158u);
          ConvertWideStringVariableData(a2, a2 + 152);
          *(_DWORD *)(a2 + 332) = *((_DWORD *)v9 + 99);
          CopyVariableData((_DWORD *)v9 + 16, (DWORD *)v9 + 56, a2, a2 + 160, 0x158u);
          ConvertWideStringVariableData(a2, a2 + 160);
          *(_DWORD *)(a2 + 168) = *((_DWORD *)v9 + 58);
          CopyVariableData((_DWORD *)v9 + 16, (DWORD *)v9 + 59, a2, a2 + 172, 0x158u);
          ConvertWideStringVariableData(a2, a2 + 172);
          *(_DWORD *)(a2 + 336) = *((_DWORD *)v9 + 100);
          CopyVariableData((_DWORD *)v9 + 16, (DWORD *)v9 + 61, a2, a2 + 180, 0x158u);
          ConvertWideStringVariableData(a2, a2 + 180);
          *(_DWORD *)(a2 + 188) = *((_DWORD *)v9 + 63);
          CopyVariableData((_DWORD *)v9 + 16, (DWORD *)v9 + 64, a2, a2 + 192, 0x158u);
          ConvertWideStringVariableData(a2, a2 + 192);
          *(_DWORD *)(a2 + 340) = *((_DWORD *)v9 + 101);
          CopyVariableData((_DWORD *)v9 + 16, (DWORD *)v9 + 66, a2, a2 + 200, 0x158u);
          ConvertWideStringVariableData(a2, a2 + 200);
          CopyVariableData((_DWORD *)v9 + 16, (DWORD *)v9 + 76, a2, a2 + 240, 0x158u);
          CopyVariableData((_DWORD *)v9 + 16, (DWORD *)v9 + 78, a2, a2 + 248, 0x158u);
          CopyVariableData((_DWORD *)v9 + 16, (DWORD *)v9 + 80, a2, a2 + 256, 0x158u);
          CopyVariableData((_DWORD *)v9 + 16, (DWORD *)v9 + 82, a2, a2 + 264, 0x158u);
          CopyVariableData((_DWORD *)v9 + 16, (DWORD *)v9 + 84, a2, a2 + 272, 0x158u);
          CopyVariableData((_DWORD *)v9 + 16, (DWORD *)v9 + 86, a2, a2 + 280, 0x158u);
          CopyVariableData((_DWORD *)v9 + 16, (DWORD *)v9 + 88, a2, a2 + 288, 0x158u);
          v4 = a1;
          *(_DWORD *)(a2 + 4) = *(_DWORD *)(a2 + 8);
        }
        else
        {
          v14 = *(_DWORD *)a2 < 0x158u;
          *(_DWORD *)(a2 + 4) = v13;
          if ( v14 )
            v12 = *(_DWORD *)a2;
          *(_DWORD *)(a2 + 8) = v12;
          if ( !gIsndpspEtwTracingAvailable )
          {
            if ( dwTraceId != -1 )
              TracePrintfA(
                dwTraceId,
                "RasLineGetCallInfo: The needed size (0x%x) for LINECALLINFO is more than the allocated size (0x%x)",
                *((_DWORD *)v9 + 17),
                *v11);
            goto LABEL_37;
          }
          if ( qword_18003EC40 )
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
    ReleaseObjReadLock(v4);
  return v7;
}

```

## disassembly

```asm
0x1800244ec  mov     [rsp-8+arg_10], rbx
0x1800244f1  push    rbp
0x1800244f2  push    rsi
0x1800244f3  push    rdi
0x1800244f4  push    r12
0x1800244f6  push    r13
0x1800244f8  push    r14
0x1800244fa  push    r15
0x1800244fc  lea     rbp, [rsp-760h]
0x180024504  sub     rsp, 860h
0x18002450b  mov     rax, cs:__security_cookie
0x180024512  xor     rax, rsp
0x180024515  mov     [rbp+790h+var_40], rax
0x18002451c  mov     edi, [rdx]
0x18002451e  xor     r15d, r15d
0x180024521  mov     r14, rdx
0x180024524  mov     [rsp+890h+var_860], ecx
0x180024528  mov     ebx, ecx
0x18002452a  mov     [rsp+890h+lpMem], r15
0x18002452f  xor     edx, edx; Val
0x180024531  mov     [rsp+890h+var_858], r15
0x180024536  lea     rcx, [rsp+890h+var_83C]; void *
0x18002453b  mov     [rsp+890h+var_840], r15d
0x180024540  mov     r8d, 7FCh; Size
0x180024546  call    memset_0
0x18002454b  lea     rdx, [rsp+890h+var_858]
0x180024550  mov     ecx, ebx
0x180024552  call    GetCallObjWithReadLock
0x180024557  mov     r12, [rsp+890h+var_858]
0x18002455c  mov     esi, eax
0x18002455e  test    eax, eax
0x180024560  jz      short loc_1800245DA
0x180024562  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x180024569  jz      short loc_1800245B6
0x18002456b  cmp     cs:qword_18003EC40, r15
0x180024572  jz      loc_180024AFA
0x180024578  mov     r8d, eax
0x18002457b  mov     word ptr [rsp+890h+var_840], r15w
0x180024581  lea     rdx, aRaslinegetcall_17; "RasLineGetCallInfo: GetCallObjWithReadL"...
0x180024588  lea     rcx, [rsp+890h+var_840]
0x18002458d  call    FormatRRASErrorString
0x180024592  mov     rdx, cs:qword_18003EC40
0x180024599  lea     r8, [rsp+890h+var_840]
0x18002459e  mov     rcx, cs:gNdpspEtwContext
0x1800245a5  mov     rax, cs:gNdpspTemplateFunc
0x1800245ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800245b1  jmp     loc_180024AFA
0x1800245b6  mov     ecx, cs:dwTraceId; dwTraceID
0x1800245bc  cmp     ecx, 0FFFFFFFFh
0x1800245bf  jz      loc_180024AFA
0x1800245c5  mov     r8d, eax
0x1800245c8  lea     rdx, aRaslinegetcall_1; "RasLineGetCallInfo: GetCallObjWithReadL"...
0x1800245cf  call    cs:__imp_TracePrintfA
0x1800245d5  jmp     loc_180024AFA
0x1800245da  mov     edx, [r12+4]
0x1800245df  lea     r9, [rsp+890h+lpMem]
0x1800245e4  lea     r8d, [rdi+10h]
0x1800245e8  mov     ecx, 703010Eh
0x1800245ed  call    PrepareSyncRequest
0x1800245f2  mov     r13, [rsp+890h+lpMem]
0x1800245f7  mov     esi, eax
0x1800245f9  test    eax, eax
0x1800245fb  jz      short loc_180024675
0x1800245fd  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x180024604  jz      short loc_180024651
0x180024606  cmp     cs:qword_18003EC40, r15
0x18002460d  jz      loc_180024AE1
0x180024613  lea     rdx, aRaslinegetcall_18; "RasLineGetCallInfo: PrepareSyncRequest "...
0x18002461a  mov     r8d, eax
0x18002461d  mov     word ptr [rsp+890h+var_840], r15w
0x180024623  lea     rcx, [rsp+890h+var_840]
0x180024628  call    FormatRRASErrorString
0x18002462d  mov     rdx, cs:qword_18003EC40
0x180024634  lea     r8, [rsp+890h+var_840]
0x180024639  mov     rcx, cs:gNdpspEtwContext
0x180024640  mov     rax, cs:gNdpspTemplateFunc
0x180024647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002464c  jmp     loc_180024AE1
0x180024651  mov     ecx, cs:dwTraceId; dwTraceID
0x180024657  cmp     ecx, 0FFFFFFFFh
0x18002465a  jz      loc_180024AE1
0x180024660  lea     rdx, aRaslinegetcall_2; "RasLineGetCallInfo: PrepareSyncRequest "...
0x180024667  mov     r8d, eax
0x18002466a  call    cs:__imp_TracePrintfA
0x180024670  jmp     loc_180024AE1
0x180024675  lea     rdx, [r13+38h]
0x180024679  mov     rcx, r12
0x18002467c  call    GetNDProxyHandle
0x180024681  mov     esi, eax
0x180024683  test    eax, eax
0x180024685  jz      short loc_1800246C1
0x180024687  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x18002468e  jz      short loc_1800246A9
0x180024690  cmp     cs:qword_18003EC40, r15
0x180024697  jz      loc_180024AE1
0x18002469d  lea     rdx, aRaslinegetcall_0; "RasLineGetCallInfo: GetNDProxyHandle fa"...
0x1800246a4  jmp     loc_18002461A
0x1800246a9  mov     ecx, cs:dwTraceId
0x1800246af  cmp     ecx, 0FFFFFFFFh
0x1800246b2  jz      loc_180024AE1
0x1800246b8  lea     rdx, aRaslinegetcall_5; "RasLineGetCallInfo: GetNDProxyHandle fa"...
0x1800246bf  jmp     short loc_180024667
0x1800246c1  mov     eax, [r14]
0x1800246c4  lea     rdi, [r13+40h]
0x1800246c8  mov     r15d, 158h
0x1800246ce  mov     [rdi], eax
0x1800246d0  mov     rdx, r13; lpInBuffer
0x1800246d3  mov     [rdi+8], r15d
0x1800246d7  mov     ecx, 8FFF23C8h; dwIoControlCode
0x1800246dc  mov     [rdi+4], r15d
0x1800246e0  call    SyncDriverRequest
0x1800246e5  mov     esi, eax
0x1800246e7  test    eax, eax
0x1800246e9  jz      short loc_18002472B
0x1800246eb  xor     r15d, r15d
0x1800246ee  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x1800246f5  jz      short loc_180024710
0x1800246f7  cmp     cs:qword_18003EC40, r15
0x1800246fe  jz      loc_180024AE1
0x180024704  lea     rdx, aRaslinegetcall_7; "RasLineGetCallInfo: SyncDriverRequest(O"...
0x18002470b  jmp     loc_18002461A
0x180024710  mov     ecx, cs:dwTraceId
0x180024716  cmp     ecx, 0FFFFFFFFh
0x180024719  jz      loc_180024AE1
0x18002471f  lea     rdx, aRaslinegetcall_3; "RasLineGetCallInfo: SyncDriverRequest(O"...
0x180024726  jmp     loc_180024667
0x18002472b  movups  xmm0, xmmword ptr [rdi+10h]
0x18002472f  movups  xmmword ptr [r14+10h], xmm0
0x180024734  movups  xmm1, xmmword ptr [rdi+20h]
0x180024738  movups  xmmword ptr [r14+20h], xmm1
0x18002473d  movups  xmm0, xmmword ptr [rdi+30h]
0x180024741  movups  xmmword ptr [r14+30h], xmm0
0x180024746  movups  xmm1, xmmword ptr [rdi+40h]
0x18002474a  movups  xmmword ptr [r14+40h], xmm1
0x18002474f  movups  xmm0, xmmword ptr [rdi+50h]
0x180024753  movups  xmmword ptr [r14+50h], xmm0
0x180024758  movups  xmm1, xmmword ptr [rdi+5Ch]
0x18002475c  movups  xmmword ptr [r14+5Ch], xmm1
0x180024761  mov     eax, [rdi+4]
0x180024764  cmp     eax, [rdi]
0x180024766  jbe     short loc_1800247DB
0x180024768  cmp     [r14], r15d
0x18002476b  mov     [r14+4], eax
0x18002476f  cmovb   r15d, [r14]
0x180024773  mov     [r14+8], r15d
0x180024777  xor     r15d, r15d
0x18002477a  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x180024781  jz      short loc_1800247B3
0x180024783  cmp     cs:qword_18003EC40, r15
0x18002478a  jz      loc_180024AE1
0x180024790  mov     word ptr [rsp+890h+var_840], r15w
0x180024796  lea     rdx, aRaslinegetcall_16; "RasLineGetCallInfo: The needed size (0x"...
0x18002479d  mov     r9d, [rdi]
0x1800247a0  lea     rcx, [rsp+890h+var_840]
0x1800247a5  mov     r8d, [rdi+4]
0x1800247a9  call    FormatRRASErrorString
0x1800247ae  jmp     loc_18002462D
0x1800247b3  mov     ecx, cs:dwTraceId; dwTraceID
0x1800247b9  cmp     ecx, 0FFFFFFFFh
0x1800247bc  jz      loc_180024AE1
0x1800247c2  mov     r9d, [rdi]
0x1800247c5  lea     rdx, aRaslinegetcall_10; "RasLineGetCallInfo: The needed size (0x"...
0x1800247cc  mov     r8d, [rdi+4]
0x1800247d0  call    cs:__imp_TracePrintfA
0x1800247d6  jmp     loc_180024AE1
0x1800247db  mov     [r14+8], r15d
0x1800247df  lea     rdx, [rdi+70h]
0x1800247e3  mov     eax, [rdi+6Ch]
0x1800247e6  lea     r9, [r14+70h]
0x1800247ea  mov     r8, r14
0x1800247ed  mov     [r14+6Ch], eax
0x1800247f1  mov     rcx, rdi
0x1800247f4  mov     [rsp+890h+var_870], r15d
0x1800247f9  call    CopyVariableData
0x1800247fe  lea     rdx, [r14+70h]
0x180024802  mov     rcx, r14
0x180024805  call    ConvertWideStringVariableData
0x18002480a  mov     eax, [rdi+144h]
0x180024810  lea     rdx, [rdi+78h]
0x180024814  lea     r9, [r14+78h]
0x180024818  mov     [r14+144h], eax
0x18002481f  mov     r8, r14
0x180024822  mov     [rsp+890h+var_870], r15d
0x180024827  mov     rcx, rdi
0x18002482a  call    CopyVariableData
0x18002482f  lea     rdx, [r14+78h]
0x180024833  mov     rcx, r14
0x180024836  call    ConvertWideStringVariableData
0x18002483b  mov     eax, [rdi+80h]
0x180024841  lea     rbx, [r14+84h]
0x180024848  mov     r9, rbx
0x18002484b  mov     [r14+80h], eax
0x180024852  lea     rdx, [rdi+84h]
0x180024859  mov     [rsp+890h+var_870], r15d
0x18002485e  mov     r8, r14
0x180024861  mov     rcx, rdi
0x180024864  call    CopyVariableData
0x180024869  mov     rdx, rbx
0x18002486c  mov     rcx, r14
0x18002486f  call    ConvertWideStringVariableData
0x180024874  mov     eax, [rdi+148h]
0x18002487a  lea     rbx, [r14+8Ch]
0x180024881  mov     r9, rbx
0x180024884  mov     [r14+148h], eax
0x18002488b  lea     rdx, [rdi+8Ch]
0x180024892  mov     [rsp+890h+var_870], r15d
0x180024897  mov     r8, r14
0x18002489a  mov     rcx, rdi
0x18002489d  call    CopyVariableData
0x1800248a2  mov     rdx, rbx
0x1800248a5  mov     rcx, r14
0x1800248a8  call    ConvertWideStringVariableData
0x1800248ad  mov     eax, [rdi+94h]
0x1800248b3  lea     rbx, [r14+98h]
0x1800248ba  mov     r9, rbx
0x1800248bd  mov     [r14+94h], eax
0x1800248c4  lea     rdx, [rdi+98h]
0x1800248cb  mov     [rsp+890h+var_870], r15d
0x1800248d0  mov     r8, r14
0x1800248d3  mov     rcx, rdi
0x1800248d6  call    CopyVariableData
0x1800248db  mov     rdx, rbx
0x1800248de  mov     rcx, r14
0x1800248e1  call    ConvertWideStringVariableData
0x1800248e6  mov     eax, [rdi+14Ch]
0x1800248ec  lea     rbx, [r14+0A0h]
0x1800248f3  mov     r9, rbx
0x1800248f6  mov     [r14+14Ch], eax
0x1800248fd  lea     rdx, [rdi+0A0h]
0x180024904  mov     [rsp+890h+var_870], r15d
0x180024909  mov     r8, r14
0x18002490c  mov     rcx, rdi
0x18002490f  call    CopyVariableData
0x180024914  mov     rdx, rbx
0x180024917  mov     rcx, r14
0x18002491a  call    ConvertWideStringVariableData
0x18002491f  mov     eax, [rdi+0A8h]
0x180024925  lea     rbx, [r14+0ACh]
0x18002492c  mov     r9, rbx
0x18002492f  mov     [r14+0A8h], eax
0x180024936  lea     rdx, [rdi+0ACh]
0x18002493d  mov     [rsp+890h+var_870], r15d
0x180024942  mov     r8, r14
0x180024945  mov     rcx, rdi
0x180024948  call    CopyVariableData
0x18002494d  mov     rdx, rbx
0x180024950  mov     rcx, r14
0x180024953  call    ConvertWideStringVariableData
0x180024958  mov     eax, [rdi+150h]
0x18002495e  lea     rbx, [r14+0B4h]
0x180024965  mov     r9, rbx
0x180024968  mov     [r14+150h], eax
0x18002496f  lea     rdx, [rdi+0B4h]
0x180024976  mov     [rsp+890h+var_870], r15d
0x18002497b  mov     r8, r14
0x18002497e  mov     rcx, rdi
0x180024981  call    CopyVariableData
0x180024986  mov     rdx, rbx
0x180024989  mov     rcx, r14
0x18002498c  call    ConvertWideStringVariableData
0x180024991  mov     eax, [rdi+0BCh]
0x180024997  lea     rbx, [r14+0C0h]
0x18002499e  mov     r9, rbx
0x1800249a1  mov     [r14+0BCh], eax
0x1800249a8  lea     rdx, [rdi+0C0h]
0x1800249af  mov     [rsp+890h+var_870], r15d
0x1800249b4  mov     r8, r14
0x1800249b7  mov     rcx, rdi
0x1800249ba  call    CopyVariableData
0x1800249bf  mov     rdx, rbx
0x1800249c2  mov     rcx, r14
0x1800249c5  call    ConvertWideStringVariableData
0x1800249ca  mov     eax, [rdi+154h]
0x1800249d0  lea     rbx, [r14+0C8h]
0x1800249d7  mov     r9, rbx
0x1800249da  mov     [r14+154h], eax
0x1800249e1  lea     rdx, [rdi+0C8h]
0x1800249e8  mov     [rsp+890h+var_870], r15d
0x1800249ed  mov     r8, r14
0x1800249f0  mov     rcx, rdi
0x1800249f3  call    CopyVariableData
0x1800249f8  mov     rdx, rbx
0x1800249fb  mov     rcx, r14
0x1800249fe  call    ConvertWideStringVariableData
0x180024a03  lea     r9, [r14+0F0h]
0x180024a0a  mov     [rsp+890h+var_870], r15d
0x180024a0f  lea     rdx, [rdi+0F0h]
0x180024a16  mov     r8, r14
0x180024a19  mov     rcx, rdi
0x180024a1c  call    CopyVariableData
0x180024a21  lea     r9, [r14+0F8h]
0x180024a28  mov     [rsp+890h+var_870], r15d
0x180024a2d  lea     rdx, [rdi+0F8h]
0x180024a34  mov     r8, r14
0x180024a37  mov     rcx, rdi
0x180024a3a  call    CopyVariableData
0x180024a3f  lea     r9, [r14+100h]
0x180024a46  mov     [rsp+890h+var_870], r15d
0x180024a4b  lea     rdx, [rdi+100h]
0x180024a52  mov     r8, r14
  ... truncated ...
```
