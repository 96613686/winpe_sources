# RasLineGetCallInfo

- ea: `0x18008c578`
- end: `0x18008cb7c`
- name: `RasLineGetCallInfo`
- size: `1540`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x18002a7b0`
- `0x18008aa50`

## callees

- `0x1800755b8`
- `0x18008a88c`
- `0x18008c578`
- `0x18008e6f4`
- `0x18008ea64`
- `0x18008ec34`
- `0x18008ed64`
- `0x18008f82c`
- `0x180090714`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18008cb22`
- `KERNEL32!GetProcessHeap` at `0x18008cb22`
- `KERNEL32!HeapFree` at `0x18008cb36`
- `KERNEL32!HeapFree` at `0x18008cb36`
- `rtutils!TracePrintfA` at `0x18008c655`
- `rtutils!TracePrintfA` at `0x18008c6f3`
- `rtutils!TracePrintfA` at `0x18008c85f`
- `rtutils!TracePrintfA` at `0x18008c655`
- `rtutils!TracePrintfA` at `0x18008c6f3`
- `rtutils!TracePrintfA` at `0x18008c85f`

## string_xrefs

- `0x18008c607`: `RasLineGetCallInfo: GetCallObjWithReadLock failed with error (0x%x)`
- `0x18008c64e`: `RasLineGetCallInfo: GetCallObjWithReadLock failed with error (0x%x)`

## pseudocode

```c
__int64 __fastcall RasLineGetCallInfo(unsigned int a1, __int64 a2)
{
  int v2; // ebx
  unsigned int v5; // eax
  unsigned int *v6; // r13
  unsigned int v7; // esi
  unsigned int NDProxyHandle; // eax
  unsigned int *v9; // r15
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
  char v21[2044]; // [rsp+44h] [rbp-BCh] BYREF

  v2 = *(_DWORD *)a2;
  lpMem = 0;
  v18 = 0;
  v20 = 0;
  memset_0(v21, 0, sizeof(v21));
  v5 = GetCallObjWithReadLock(a1, &v18);
  v6 = v18;
  v7 = v5;
  if ( v5 )
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800D0BE0 )
      {
        LOWORD(v20) = 0;
        FormatRRASErrorString(&v20, L"RasLineGetCallInfo: GetCallObjWithReadLock failed with error (0x%x)", v5);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v20);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "RasLineGetCallInfo: GetCallObjWithReadLock failed with error (0x%x)", v5);
    }
    goto LABEL_39;
  }
  NDProxyHandle = PrepareSyncRequest(117637390, v18[1], (unsigned int)(v2 + 16), &lpMem);
  v9 = (unsigned int *)lpMem;
  v7 = NDProxyHandle;
  if ( NDProxyHandle )
  {
    if ( !gIsndpspEtwTracingAvailable )
    {
      if ( dwTraceId != -1 )
        TracePrintfA(dwTraceId, "RasLineGetCallInfo: PrepareSyncRequest failed with error (0x%x)", NDProxyHandle);
      goto LABEL_37;
    }
    if ( (_QWORD)xmmword_1800D0BE0 )
    {
      v10 = L"RasLineGetCallInfo: PrepareSyncRequest failed with error (0x%x)";
LABEL_11:
      LOWORD(v20) = 0;
      FormatRRASErrorString(&v20, v10, NDProxyHandle);
LABEL_12:
      ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v20);
    }
  }
  else
  {
    NDProxyHandle = GetNDProxyHandle((__int64)v6, (_QWORD *)lpMem + 7);
    v7 = NDProxyHandle;
    if ( NDProxyHandle )
    {
      if ( !gIsndpspEtwTracingAvailable )
      {
        if ( dwTraceId != -1 )
          TracePrintfA(dwTraceId, "RasLineGetCallInfo: GetNDProxyHandle failed with error (0x%x)", NDProxyHandle);
        goto LABEL_37;
      }
      if ( (_QWORD)xmmword_1800D0BE0 )
      {
        v10 = L"RasLineGetCallInfo: GetNDProxyHandle failed with error (0x%x)";
        goto LABEL_11;
      }
    }
    else
    {
      v11 = v9 + 16;
      v12 = 344;
      v9[16] = *(_DWORD *)a2;
      v9[18] = 344;
      v9[17] = 344;
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
        if ( (_QWORD)xmmword_1800D0BE0 )
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
        *(_QWORD *)(a2 + 96) = *((_QWORD *)v9 + 20);
        *(_DWORD *)(a2 + 104) = v9[42];
        v13 = v9[17];
        if ( v13 <= *v11 )
        {
          *(_DWORD *)(a2 + 8) = 344;
          *(_DWORD *)(a2 + 108) = v9[43];
          CopyVariableData(v9 + 16, v9 + 44, a2, a2 + 112);
          ConvertWideStringVariableData(a2, a2 + 112);
          *(_DWORD *)(a2 + 324) = v9[97];
          CopyVariableData(v9 + 16, v9 + 46, a2, a2 + 120);
          ConvertWideStringVariableData(a2, a2 + 120);
          *(_DWORD *)(a2 + 128) = v9[48];
          CopyVariableData(v9 + 16, v9 + 49, a2, a2 + 132);
          ConvertWideStringVariableData(a2, a2 + 132);
          *(_DWORD *)(a2 + 328) = v9[98];
          CopyVariableData(v9 + 16, v9 + 51, a2, a2 + 140);
          ConvertWideStringVariableData(a2, a2 + 140);
          *(_DWORD *)(a2 + 148) = v9[53];
          CopyVariableData(v9 + 16, v9 + 54, a2, a2 + 152);
          ConvertWideStringVariableData(a2, a2 + 152);
          *(_DWORD *)(a2 + 332) = v9[99];
          CopyVariableData(v9 + 16, v9 + 56, a2, a2 + 160);
          ConvertWideStringVariableData(a2, a2 + 160);
          *(_DWORD *)(a2 + 168) = v9[58];
          CopyVariableData(v9 + 16, v9 + 59, a2, a2 + 172);
          ConvertWideStringVariableData(a2, a2 + 172);
          *(_DWORD *)(a2 + 336) = v9[100];
          CopyVariableData(v9 + 16, v9 + 61, a2, a2 + 180);
          ConvertWideStringVariableData(a2, a2 + 180);
          *(_DWORD *)(a2 + 188) = v9[63];
          CopyVariableData(v9 + 16, v9 + 64, a2, a2 + 192);
          ConvertWideStringVariableData(a2, a2 + 192);
          *(_DWORD *)(a2 + 340) = v9[101];
          CopyVariableData(v9 + 16, v9 + 66, a2, a2 + 200);
          ConvertWideStringVariableData(a2, a2 + 200);
          CopyVariableData(v9 + 16, v9 + 76, a2, a2 + 240);
          CopyVariableData(v9 + 16, v9 + 78, a2, a2 + 248);
          CopyVariableData(v9 + 16, v9 + 80, a2, a2 + 256);
          CopyVariableData(v9 + 16, v9 + 82, a2, a2 + 264);
          CopyVariableData(v9 + 16, v9 + 84, a2, a2 + 272);
          CopyVariableData(v9 + 16, v9 + 86, a2, a2 + 280);
          CopyVariableData(v9 + 16, v9 + 88, a2, a2 + 288);
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
                v9[17],
                *v11);
            goto LABEL_37;
          }
          if ( (_QWORD)xmmword_1800D0BE0 )
          {
            LOWORD(v20) = 0;
            FormatRRASErrorString(
              &v20,
              L"RasLineGetCallInfo: The needed size (0x%x) for LINECALLINFO is more than the allocated size (0x%x)",
              v9[17],
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
  return v7;
}

```

## disassembly

```asm
0x18008c578  mov     [rsp-8+arg_10], rbx
0x18008c57d  push    rbp
0x18008c57e  push    rsi
0x18008c57f  push    rdi
0x18008c580  push    r12
0x18008c582  push    r13
0x18008c584  push    r14
0x18008c586  push    r15
0x18008c588  lea     rbp, [rsp-750h]
0x18008c590  sub     rsp, 850h
0x18008c597  mov     rax, cs:__security_cookie
0x18008c59e  xor     rax, rsp
0x18008c5a1  mov     [rbp+780h+var_40], rax
0x18008c5a8  mov     ebx, [rdx]
0x18008c5aa  xor     edi, edi
0x18008c5ac  mov     r14, rdx
0x18008c5af  mov     [rsp+880h+lpMem], rdi
0x18008c5b4  mov     r12d, ecx
0x18008c5b7  mov     [rsp+880h+var_850], rdi
0x18008c5bc  xor     edx, edx; Val
0x18008c5be  mov     [rsp+880h+var_840], edi
0x18008c5c2  lea     rcx, [rsp+880h+var_83C]; void *
0x18008c5c7  mov     r8d, 7FCh; Size
0x18008c5cd  call    memset_0
0x18008c5d2  lea     rdx, [rsp+880h+var_850]
0x18008c5d7  mov     ecx, r12d
0x18008c5da  call    GetCallObjWithReadLock
0x18008c5df  mov     r13, [rsp+880h+var_850]
0x18008c5e4  mov     esi, eax
0x18008c5e6  test    eax, eax
0x18008c5e8  jz      short loc_18008C666
0x18008c5ea  cmp     cs:gIsndpspEtwTracingAvailable, edi
0x18008c5f0  jz      short loc_18008C63C
0x18008c5f2  cmp     qword ptr cs:xmmword_1800D0BE0, rdi
0x18008c5f9  jz      loc_18008CB42
0x18008c5ff  mov     r8d, eax
0x18008c602  mov     word ptr [rsp+880h+var_840], di
0x18008c607  lea     rdx, aRaslinegetcall_7; "RasLineGetCallInfo: GetCallObjWithReadL"...
0x18008c60e  lea     rcx, [rsp+880h+var_840]
0x18008c613  call    FormatRRASErrorString
0x18008c618  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008c61f  lea     r8, [rsp+880h+var_840]
0x18008c624  mov     rcx, cs:gNdpspEtwContext
0x18008c62b  mov     rax, cs:gNdpspTemplateFunc
0x18008c632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c637  jmp     loc_18008CB42
0x18008c63c  mov     ecx, cs:dwTraceId; dwTraceID
0x18008c642  cmp     ecx, 0FFFFFFFFh
0x18008c645  jz      loc_18008CB42
0x18008c64b  mov     r8d, eax
0x18008c64e  lea     rdx, aRaslinegetcall_0; "RasLineGetCallInfo: GetCallObjWithReadL"...
0x18008c655  call    cs:__imp_TracePrintfA
0x18008c65c  nop     dword ptr [rax+rax+00h]
0x18008c661  jmp     loc_18008CB42
0x18008c666  mov     edx, [r13+4]
0x18008c66a  lea     r9, [rsp+880h+lpMem]
0x18008c66f  lea     r8d, [rbx+10h]
0x18008c673  mov     ecx, 703010Eh
0x18008c678  call    PrepareSyncRequest
0x18008c67d  mov     r15, [rsp+880h+lpMem]
0x18008c682  mov     esi, eax
0x18008c684  test    eax, eax
0x18008c686  jz      short loc_18008C704
0x18008c688  cmp     cs:gIsndpspEtwTracingAvailable, edi
0x18008c68e  jz      short loc_18008C6DA
0x18008c690  cmp     qword ptr cs:xmmword_1800D0BE0, rdi
0x18008c697  jz      loc_18008CB1D
0x18008c69d  lea     rdx, aRaslinegetcall_8; "RasLineGetCallInfo: PrepareSyncRequest "...
0x18008c6a4  mov     r8d, eax
0x18008c6a7  mov     word ptr [rsp+880h+var_840], di
0x18008c6ac  lea     rcx, [rsp+880h+var_840]
0x18008c6b1  call    FormatRRASErrorString
0x18008c6b6  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008c6bd  lea     r8, [rsp+880h+var_840]
0x18008c6c2  mov     rcx, cs:gNdpspEtwContext
0x18008c6c9  mov     rax, cs:gNdpspTemplateFunc
0x18008c6d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c6d5  jmp     loc_18008CB1D
0x18008c6da  mov     ecx, cs:dwTraceId; dwTraceID
0x18008c6e0  cmp     ecx, 0FFFFFFFFh
0x18008c6e3  jz      loc_18008CB1D
0x18008c6e9  lea     rdx, aRaslinegetcall_1; "RasLineGetCallInfo: PrepareSyncRequest "...
0x18008c6f0  mov     r8d, eax
0x18008c6f3  call    cs:__imp_TracePrintfA
0x18008c6fa  nop     dword ptr [rax+rax+00h]
0x18008c6ff  jmp     loc_18008CB1D
0x18008c704  lea     rdx, [r15+38h]
0x18008c708  mov     rcx, r13
0x18008c70b  call    GetNDProxyHandle
0x18008c710  mov     esi, eax
0x18008c712  test    eax, eax
0x18008c714  jz      short loc_18008C74F
0x18008c716  cmp     cs:gIsndpspEtwTracingAvailable, edi
0x18008c71c  jz      short loc_18008C737
0x18008c71e  cmp     qword ptr cs:xmmword_1800D0BE0, rdi
0x18008c725  jz      loc_18008CB1D
0x18008c72b  lea     rdx, aRaslinegetcall; "RasLineGetCallInfo: GetNDProxyHandle fa"...
0x18008c732  jmp     loc_18008C6A4
0x18008c737  mov     ecx, cs:dwTraceId
0x18008c73d  cmp     ecx, 0FFFFFFFFh
0x18008c740  jz      loc_18008CB1D
0x18008c746  lea     rdx, aRaslinegetcall_3; "RasLineGetCallInfo: GetNDProxyHandle fa"...
0x18008c74d  jmp     short loc_18008C6F0
0x18008c74f  mov     eax, [r14]
0x18008c752  lea     rdi, [r15+40h]
0x18008c756  mov     ebx, 158h
0x18008c75b  mov     [rdi], eax
0x18008c75d  mov     rdx, r15; lpInBuffer
0x18008c760  mov     [rdi+8], ebx
0x18008c763  mov     ecx, 8FFF23C8h; dwIoControlCode
0x18008c768  mov     [rdi+4], ebx
0x18008c76b  call    SyncDriverRequest
0x18008c770  xor     ecx, ecx
0x18008c772  mov     esi, eax
0x18008c774  test    eax, eax
0x18008c776  jz      short loc_18008C7B6
0x18008c778  xor     edi, edi
0x18008c77a  cmp     cs:gIsndpspEtwTracingAvailable, edi
0x18008c780  jz      short loc_18008C79B
0x18008c782  cmp     qword ptr cs:xmmword_1800D0BE0, rdi
0x18008c789  jz      loc_18008CB1D
0x18008c78f  lea     rdx, aRaslinegetcall_4; "RasLineGetCallInfo: SyncDriverRequest(O"...
0x18008c796  jmp     loc_18008C6A4
0x18008c79b  mov     ecx, cs:dwTraceId
0x18008c7a1  cmp     ecx, 0FFFFFFFFh
0x18008c7a4  jz      loc_18008CB1D
0x18008c7aa  lea     rdx, aRaslinegetcall_2; "RasLineGetCallInfo: SyncDriverRequest(O"...
0x18008c7b1  jmp     loc_18008C6F0
0x18008c7b6  movups  xmm0, xmmword ptr [rdi+10h]
0x18008c7ba  movups  xmmword ptr [r14+10h], xmm0
0x18008c7bf  movups  xmm1, xmmword ptr [rdi+20h]
0x18008c7c3  movups  xmmword ptr [r14+20h], xmm1
0x18008c7c8  movups  xmm0, xmmword ptr [rdi+30h]
0x18008c7cc  movups  xmmword ptr [r14+30h], xmm0
0x18008c7d1  movups  xmm1, xmmword ptr [rdi+40h]
0x18008c7d5  movups  xmmword ptr [r14+40h], xmm1
0x18008c7da  movups  xmm0, xmmword ptr [rdi+50h]
0x18008c7de  movups  xmmword ptr [r14+50h], xmm0
0x18008c7e3  movsd   xmm1, qword ptr [rdi+60h]
0x18008c7e8  movsd   qword ptr [r14+60h], xmm1
0x18008c7ee  mov     eax, [rdi+68h]
0x18008c7f1  mov     [r14+68h], eax
0x18008c7f5  mov     eax, [rdi+4]
0x18008c7f8  cmp     eax, [rdi]
0x18008c7fa  jbe     short loc_18008C870
0x18008c7fc  cmp     [r14], ebx
0x18008c7ff  mov     [r14+4], eax
0x18008c803  cmovb   ebx, [r14]
0x18008c807  cmp     cs:gIsndpspEtwTracingAvailable, ecx
0x18008c80d  mov     [r14+8], ebx
0x18008c811  jz      short loc_18008C842
0x18008c813  cmp     qword ptr cs:xmmword_1800D0BE0, rcx
0x18008c81a  jz      loc_18008CB1D
0x18008c820  mov     word ptr [rsp+880h+var_840], cx
0x18008c825  lea     rdx, aRaslinegetcall_6; "RasLineGetCallInfo: The needed size (0x"...
0x18008c82c  mov     r9d, [rdi]
0x18008c82f  lea     rcx, [rsp+880h+var_840]
0x18008c834  mov     r8d, [rdi+4]
0x18008c838  call    FormatRRASErrorString
0x18008c83d  jmp     loc_18008C6B6
0x18008c842  mov     ecx, cs:dwTraceId; dwTraceID
0x18008c848  cmp     ecx, 0FFFFFFFFh
0x18008c84b  jz      loc_18008CB1D
0x18008c851  mov     r9d, [rdi]
0x18008c854  lea     rdx, aRaslinegetcall_5; "RasLineGetCallInfo: The needed size (0x"...
0x18008c85b  mov     r8d, [rdi+4]
0x18008c85f  call    cs:__imp_TracePrintfA
0x18008c866  nop     dword ptr [rax+rax+00h]
0x18008c86b  jmp     loc_18008CB1D
0x18008c870  mov     [r14+8], ebx
0x18008c874  lea     rdx, [rdi+70h]
0x18008c878  mov     eax, [rdi+6Ch]
0x18008c87b  lea     r9, [r14+70h]
0x18008c87f  mov     r8, r14
0x18008c882  mov     [r14+6Ch], eax
0x18008c886  mov     rcx, rdi
0x18008c889  call    CopyVariableData
0x18008c88e  lea     rdx, [r14+70h]
0x18008c892  mov     rcx, r14
0x18008c895  call    ConvertWideStringVariableData
0x18008c89a  mov     eax, [rdi+144h]
0x18008c8a0  lea     rdx, [rdi+78h]
0x18008c8a4  lea     r9, [r14+78h]
0x18008c8a8  mov     [r14+144h], eax
0x18008c8af  mov     r8, r14
0x18008c8b2  mov     rcx, rdi
0x18008c8b5  call    CopyVariableData
0x18008c8ba  lea     rdx, [r14+78h]
0x18008c8be  mov     rcx, r14
0x18008c8c1  call    ConvertWideStringVariableData
0x18008c8c6  mov     eax, [rdi+80h]
0x18008c8cc  lea     rbx, [r14+84h]
0x18008c8d3  mov     r9, rbx
0x18008c8d6  mov     [r14+80h], eax
0x18008c8dd  lea     rdx, [rdi+84h]
0x18008c8e4  mov     r8, r14
0x18008c8e7  mov     rcx, rdi
0x18008c8ea  call    CopyVariableData
0x18008c8ef  mov     rdx, rbx
0x18008c8f2  mov     rcx, r14
0x18008c8f5  call    ConvertWideStringVariableData
0x18008c8fa  mov     eax, [rdi+148h]
0x18008c900  lea     rbx, [r14+8Ch]
0x18008c907  mov     r9, rbx
0x18008c90a  mov     [r14+148h], eax
0x18008c911  lea     rdx, [rdi+8Ch]
0x18008c918  mov     r8, r14
0x18008c91b  mov     rcx, rdi
0x18008c91e  call    CopyVariableData
0x18008c923  mov     rdx, rbx
0x18008c926  mov     rcx, r14
0x18008c929  call    ConvertWideStringVariableData
0x18008c92e  mov     eax, [rdi+94h]
0x18008c934  lea     rbx, [r14+98h]
0x18008c93b  mov     r9, rbx
0x18008c93e  mov     [r14+94h], eax
0x18008c945  lea     rdx, [rdi+98h]
0x18008c94c  mov     r8, r14
0x18008c94f  mov     rcx, rdi
0x18008c952  call    CopyVariableData
0x18008c957  mov     rdx, rbx
0x18008c95a  mov     rcx, r14
0x18008c95d  call    ConvertWideStringVariableData
0x18008c962  mov     eax, [rdi+14Ch]
0x18008c968  lea     rbx, [r14+0A0h]
0x18008c96f  mov     r9, rbx
0x18008c972  mov     [r14+14Ch], eax
0x18008c979  lea     rdx, [rdi+0A0h]
0x18008c980  mov     r8, r14
0x18008c983  mov     rcx, rdi
0x18008c986  call    CopyVariableData
0x18008c98b  mov     rdx, rbx
0x18008c98e  mov     rcx, r14
0x18008c991  call    ConvertWideStringVariableData
0x18008c996  mov     eax, [rdi+0A8h]
0x18008c99c  lea     rbx, [r14+0ACh]
0x18008c9a3  mov     r9, rbx
0x18008c9a6  mov     [r14+0A8h], eax
0x18008c9ad  lea     rdx, [rdi+0ACh]
0x18008c9b4  mov     r8, r14
0x18008c9b7  mov     rcx, rdi
0x18008c9ba  call    CopyVariableData
0x18008c9bf  mov     rdx, rbx
0x18008c9c2  mov     rcx, r14
0x18008c9c5  call    ConvertWideStringVariableData
0x18008c9ca  mov     eax, [rdi+150h]
0x18008c9d0  lea     rbx, [r14+0B4h]
0x18008c9d7  mov     [r14+150h], eax
0x18008c9de  lea     rdx, [rdi+0B4h]
0x18008c9e5  mov     r9, rbx
0x18008c9e8  mov     r8, r14
0x18008c9eb  mov     rcx, rdi
0x18008c9ee  call    CopyVariableData
0x18008c9f3  mov     rdx, rbx
0x18008c9f6  mov     rcx, r14
0x18008c9f9  call    ConvertWideStringVariableData
0x18008c9fe  mov     eax, [rdi+0BCh]
0x18008ca04  lea     rbx, [r14+0C0h]
0x18008ca0b  mov     r9, rbx
0x18008ca0e  mov     [r14+0BCh], eax
0x18008ca15  lea     rdx, [rdi+0C0h]
0x18008ca1c  mov     r8, r14
0x18008ca1f  mov     rcx, rdi
0x18008ca22  call    CopyVariableData
0x18008ca27  mov     rdx, rbx
0x18008ca2a  mov     rcx, r14
0x18008ca2d  call    ConvertWideStringVariableData
0x18008ca32  mov     eax, [rdi+154h]
0x18008ca38  lea     rbx, [r14+0C8h]
0x18008ca3f  mov     r9, rbx
0x18008ca42  mov     [r14+154h], eax
0x18008ca49  lea     rdx, [rdi+0C8h]
0x18008ca50  mov     r8, r14
0x18008ca53  mov     rcx, rdi
0x18008ca56  call    CopyVariableData
0x18008ca5b  mov     rdx, rbx
0x18008ca5e  mov     rcx, r14
0x18008ca61  call    ConvertWideStringVariableData
0x18008ca66  lea     r9, [r14+0F0h]
0x18008ca6d  mov     r8, r14
0x18008ca70  lea     rdx, [rdi+0F0h]
0x18008ca77  mov     rcx, rdi
0x18008ca7a  call    CopyVariableData
0x18008ca7f  lea     r9, [r14+0F8h]
0x18008ca86  mov     r8, r14
0x18008ca89  lea     rdx, [rdi+0F8h]
0x18008ca90  mov     rcx, rdi
0x18008ca93  call    CopyVariableData
0x18008ca98  lea     r9, [r14+100h]
0x18008ca9f  mov     r8, r14
0x18008caa2  lea     rdx, [rdi+100h]
0x18008caa9  mov     rcx, rdi
0x18008caac  call    CopyVariableData
0x18008cab1  lea     r9, [r14+108h]
0x18008cab8  mov     r8, r14
0x18008cabb  lea     rdx, [rdi+108h]
0x18008cac2  mov     rcx, rdi
0x18008cac5  call    CopyVariableData
0x18008caca  lea     r9, [r14+110h]
0x18008cad1  mov     r8, r14
  ... truncated ...
```
