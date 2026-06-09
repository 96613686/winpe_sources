# RasLineGetCallStatus

- ea: `0x180024b38`
- end: `0x180024e57`
- name: `RasLineGetCallStatus`
- size: `799`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: ``

## callers

- `0x180002b20`
- `0x18000cb80`
- `0x180010330`
- `0x180014780`

## callees

- `0x18002251c`
- `0x180024b38`
- `0x180026c4c`
- `0x180027140`
- `0x180027270`
- `0x180027d38`
- `0x180028b5c`
- `0x180029130`
- `0x18002927e`
- `0x1800292b0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024e0a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024e0a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024e18`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024e18`
- `rtutils!TracePrintfA` at `0x180024c19`
- `rtutils!TracePrintfA` at `0x180024cb3`
- `rtutils!TracePrintfA` at `0x180024ddb`
- `rtutils!TracePrintfA` at `0x180024c19`
- `rtutils!TracePrintfA` at `0x180024cb3`
- `rtutils!TracePrintfA` at `0x180024ddb`

## string_xrefs

- `0x180024bcb`: `RasLineGetCallStatus: GetCallObjWithReadLock failed with error (0x%x)`
- `0x180024c12`: `RasLineGetCallStatus: GetCallObjWithReadLock failed with error (0x%x)`

## pseudocode

```c
__int64 __fastcall RasLineGetCallStatus(unsigned int a1, __int64 a2)
{
  int v2; // edi
  unsigned int v5; // eax
  unsigned int *v6; // r15
  unsigned int v7; // ebx
  unsigned int NDProxyHandle; // eax
  char *v9; // r14
  const wchar_t *v10; // rdx
  unsigned int *v11; // rdi
  unsigned int v12; // eax
  int v13; // eax
  bool v14; // zf
  HANDLE ProcessHeap; // rax
  unsigned int *v17; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-C8h] BYREF
  int v19; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v20[2044]; // [rsp+44h] [rbp-BCh] BYREF

  v2 = *(_DWORD *)a2;
  lpMem = 0;
  v17 = 0;
  v19 = 0;
  memset_0(v20, 0, sizeof(v20));
  v5 = GetCallObjWithReadLock(a1, &v17);
  v6 = v17;
  v7 = v5;
  if ( v5 )
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( qword_18003EC40 )
      {
        LOWORD(v19) = 0;
        FormatRRASErrorString(&v19, L"RasLineGetCallStatus: GetCallObjWithReadLock failed with error (0x%x)", v5);
        ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v19);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "RasLineGetCallStatus: GetCallObjWithReadLock failed with error (0x%x)", v5);
    }
    goto LABEL_39;
  }
  NDProxyHandle = PrepareSyncRequest(0x703010Fu, v17[1], v2 + 20, &lpMem);
  v9 = (char *)lpMem;
  v7 = NDProxyHandle;
  if ( NDProxyHandle )
  {
    if ( !gIsndpspEtwTracingAvailable )
    {
      if ( dwTraceId != -1 )
        TracePrintfA(dwTraceId, "RasLineGetCallStatus: PrepareSyncRequest failed with error (0x%x)", NDProxyHandle);
      goto LABEL_37;
    }
    if ( qword_18003EC40 )
    {
      v10 = L"RasLineGetCallStatus: PrepareSyncRequest failed with error (0x%x)";
LABEL_11:
      LOWORD(v19) = 0;
      FormatRRASErrorString(&v19, v10, NDProxyHandle);
LABEL_12:
      ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v19);
    }
  }
  else
  {
    NDProxyHandle = GetNDProxyHandle(v6, (char *)lpMem + 56);
    v7 = NDProxyHandle;
    if ( NDProxyHandle )
    {
      if ( !gIsndpspEtwTracingAvailable )
      {
        if ( dwTraceId != -1 )
          TracePrintfA(dwTraceId, "RasLineGetCallStatus: GetNDProxyHandle failed with error (0x%x)", NDProxyHandle);
        goto LABEL_37;
      }
      if ( qword_18003EC40 )
      {
        v10 = L"RasLineGetCallStatus: GetNDProxyHandle failed with error (0x%x)";
        goto LABEL_11;
      }
    }
    else
    {
      v11 = (unsigned int *)(v9 + 64);
      *((_DWORD *)v9 + 16) = *(_DWORD *)a2;
      *((_DWORD *)v9 + 18) = 36;
      *((_DWORD *)v9 + 17) = 36;
      NDProxyHandle = SyncDriverRequest(0x8FFF23C8, v9);
      v7 = NDProxyHandle;
      if ( NDProxyHandle )
      {
        if ( !gIsndpspEtwTracingAvailable )
        {
          if ( dwTraceId != -1 )
            TracePrintfA(
              dwTraceId,
              "RasLineGetCallStatus: SyncDriverRequest(OID_TAPI_GET_CALL_STATUS) failed with error (0x%x)",
              NDProxyHandle);
          goto LABEL_37;
        }
        if ( qword_18003EC40 )
        {
          v10 = L"RasLineGetCallStatus: SyncDriverRequest(OID_TAPI_GET_CALL_STATUS) failed with error (0x%x)";
          goto LABEL_11;
        }
      }
      else
      {
        *(_OWORD *)(a2 + 12) = *(_OWORD *)(v9 + 76);
        v12 = *((_DWORD *)v9 + 17);
        if ( v12 <= *v11 )
        {
          *(_DWORD *)(a2 + 8) = 56;
          CopyVariableData((_DWORD *)v9 + 16, (DWORD *)v9 + 23, a2, a2 + 28, 0x24u);
        }
        else
        {
          *(_DWORD *)(a2 + 4) = v12;
          v13 = 56;
          if ( *(_DWORD *)a2 < 0x38u )
            v13 = *(_DWORD *)a2;
          v14 = gIsndpspEtwTracingAvailable == 0;
          *(_DWORD *)(a2 + 8) = v13;
          if ( v14 )
          {
            if ( dwTraceId != -1 )
              TracePrintfA(
                dwTraceId,
                "RasLineGetCallStatus: The needed size (0x%x) for LINECALLSTATUS is more than the allocated size (0x%x)",
                *((_DWORD *)v9 + 17),
                *v11);
            goto LABEL_37;
          }
          if ( qword_18003EC40 )
          {
            LOWORD(v19) = 0;
            FormatRRASErrorString(
              &v19,
              L"RasLineGetCallStatus: The needed size (0x%x) for LINECALLSTATUS is more than the allocated size (0x%x)",
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
  return v7;
}

```

## disassembly

```asm
0x180024b38  mov     [rsp-8+arg_10], rbx
0x180024b3d  push    rbp
0x180024b3e  push    rsi
0x180024b3f  push    rdi
0x180024b40  push    r12
0x180024b42  push    r13
0x180024b44  push    r14
0x180024b46  push    r15
0x180024b48  lea     rbp, [rsp-750h]
0x180024b50  sub     rsp, 850h
0x180024b57  mov     rax, cs:__security_cookie
0x180024b5e  xor     rax, rsp
0x180024b61  mov     [rbp+780h+var_40], rax
0x180024b68  mov     edi, [rdx]
0x180024b6a  xor     r13d, r13d
0x180024b6d  mov     rsi, rdx
0x180024b70  mov     [rsp+880h+lpMem], r13
0x180024b75  mov     r12d, ecx
0x180024b78  mov     [rsp+880h+var_850], r13
0x180024b7d  xor     edx, edx; Val
0x180024b7f  mov     [rsp+880h+var_840], r13d
0x180024b84  lea     rcx, [rsp+880h+var_83C]; void *
0x180024b89  mov     r8d, 7FCh; Size
0x180024b8f  call    memset_0
0x180024b94  lea     rdx, [rsp+880h+var_850]
0x180024b99  mov     ecx, r12d
0x180024b9c  call    GetCallObjWithReadLock
0x180024ba1  mov     r15, [rsp+880h+var_850]
0x180024ba6  mov     ebx, eax
0x180024ba8  test    eax, eax
0x180024baa  jz      short loc_180024C24
0x180024bac  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180024bb3  jz      short loc_180024C00
0x180024bb5  cmp     cs:qword_18003EC40, r13
0x180024bbc  jz      loc_180024E1E
0x180024bc2  mov     r8d, eax
0x180024bc5  mov     word ptr [rsp+880h+var_840], r13w
0x180024bcb  lea     rdx, aRaslinegetcall_12; "RasLineGetCallStatus: GetCallObjWithRea"...
0x180024bd2  lea     rcx, [rsp+880h+var_840]
0x180024bd7  call    FormatRRASErrorString
0x180024bdc  mov     rdx, cs:qword_18003EC40
0x180024be3  lea     r8, [rsp+880h+var_840]
0x180024be8  mov     rcx, cs:gNdpspEtwContext
0x180024bef  mov     rax, cs:gNdpspTemplateFunc
0x180024bf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024bfb  jmp     loc_180024E1E
0x180024c00  mov     ecx, cs:dwTraceId; dwTraceID
0x180024c06  cmp     ecx, 0FFFFFFFFh
0x180024c09  jz      loc_180024E1E
0x180024c0f  mov     r8d, eax
0x180024c12  lea     rdx, aRaslinegetcall_13; "RasLineGetCallStatus: GetCallObjWithRea"...
0x180024c19  call    cs:__imp_TracePrintfA
0x180024c1f  jmp     loc_180024E1E
0x180024c24  mov     edx, [r15+4]
0x180024c28  lea     r9, [rsp+880h+lpMem]
0x180024c2d  lea     r8d, [rdi+14h]
0x180024c31  mov     ecx, 703010Fh
0x180024c36  call    PrepareSyncRequest
0x180024c3b  mov     r14, [rsp+880h+lpMem]
0x180024c40  mov     ebx, eax
0x180024c42  test    eax, eax
0x180024c44  jz      short loc_180024CBE
0x180024c46  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180024c4d  jz      short loc_180024C9A
0x180024c4f  cmp     cs:qword_18003EC40, r13
0x180024c56  jz      loc_180024E05
0x180024c5c  lea     rdx, aRaslinegetcall_14; "RasLineGetCallStatus: PrepareSyncReques"...
0x180024c63  mov     r8d, eax
0x180024c66  mov     word ptr [rsp+880h+var_840], r13w
0x180024c6c  lea     rcx, [rsp+880h+var_840]
0x180024c71  call    FormatRRASErrorString
0x180024c76  mov     rdx, cs:qword_18003EC40
0x180024c7d  lea     r8, [rsp+880h+var_840]
0x180024c82  mov     rcx, cs:gNdpspEtwContext
0x180024c89  mov     rax, cs:gNdpspTemplateFunc
0x180024c90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c95  jmp     loc_180024E05
0x180024c9a  mov     ecx, cs:dwTraceId; dwTraceID
0x180024ca0  cmp     ecx, 0FFFFFFFFh
0x180024ca3  jz      loc_180024E05
0x180024ca9  lea     rdx, aRaslinegetcall_4; "RasLineGetCallStatus: PrepareSyncReques"...
0x180024cb0  mov     r8d, eax
0x180024cb3  call    cs:__imp_TracePrintfA
0x180024cb9  jmp     loc_180024E05
0x180024cbe  lea     rdx, [r14+38h]
0x180024cc2  mov     rcx, r15
0x180024cc5  call    GetNDProxyHandle
0x180024cca  mov     ebx, eax
0x180024ccc  test    eax, eax
0x180024cce  jz      short loc_180024D0A
0x180024cd0  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180024cd7  jz      short loc_180024CF2
0x180024cd9  cmp     cs:qword_18003EC40, r13
0x180024ce0  jz      loc_180024E05
0x180024ce6  lea     rdx, aRaslinegetcall; "RasLineGetCallStatus: GetNDProxyHandle "...
0x180024ced  jmp     loc_180024C63
0x180024cf2  mov     ecx, cs:dwTraceId
0x180024cf8  cmp     ecx, 0FFFFFFFFh
0x180024cfb  jz      loc_180024E05
0x180024d01  lea     rdx, aRaslinegetcall_15; "RasLineGetCallStatus: GetNDProxyHandle "...
0x180024d08  jmp     short loc_180024CB0
0x180024d0a  mov     eax, [rsi]
0x180024d0c  lea     rdi, [r14+40h]
0x180024d10  mov     [rdi], eax
0x180024d12  mov     rdx, r14; lpInBuffer
0x180024d15  mov     eax, 24h ; '$'
0x180024d1a  mov     ecx, 8FFF23C8h; dwIoControlCode
0x180024d1f  mov     [rdi+8], eax
0x180024d22  mov     [rdi+4], eax
0x180024d25  call    SyncDriverRequest
0x180024d2a  mov     ebx, eax
0x180024d2c  test    eax, eax
0x180024d2e  jz      short loc_180024D6D
0x180024d30  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180024d37  jz      short loc_180024D52
0x180024d39  cmp     cs:qword_18003EC40, r13
0x180024d40  jz      loc_180024E05
0x180024d46  lea     rdx, aRaslinegetcall_9; "RasLineGetCallStatus: SyncDriverRequest"...
0x180024d4d  jmp     loc_180024C63
0x180024d52  mov     ecx, cs:dwTraceId
0x180024d58  cmp     ecx, 0FFFFFFFFh
0x180024d5b  jz      loc_180024E05
0x180024d61  lea     rdx, aRaslinegetcall_11; "RasLineGetCallStatus: SyncDriverRequest"...
0x180024d68  jmp     loc_180024CB0
0x180024d6d  movups  xmm0, xmmword ptr [rdi+0Ch]
0x180024d71  movdqu  xmmword ptr [rsi+0Ch], xmm0
0x180024d76  mov     eax, [rdi+4]
0x180024d79  cmp     eax, [rdi]
0x180024d7b  jbe     short loc_180024DE3
0x180024d7d  mov     [rsi+4], eax
0x180024d80  mov     eax, 38h ; '8'
0x180024d85  cmp     [rsi], eax
0x180024d87  cmovb   eax, [rsi]
0x180024d8a  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180024d91  mov     [rsi+8], eax
0x180024d94  jz      short loc_180024DC2
0x180024d96  cmp     cs:qword_18003EC40, r13
0x180024d9d  jz      short loc_180024E05
0x180024d9f  mov     word ptr [rsp+880h+var_840], r13w
0x180024da5  lea     rdx, aRaslinegetcall_6; "RasLineGetCallStatus: The needed size ("...
0x180024dac  mov     r9d, [rdi]
0x180024daf  lea     rcx, [rsp+880h+var_840]
0x180024db4  mov     r8d, [rdi+4]
0x180024db8  call    FormatRRASErrorString
0x180024dbd  jmp     loc_180024C76
0x180024dc2  mov     ecx, cs:dwTraceId; dwTraceID
0x180024dc8  cmp     ecx, 0FFFFFFFFh
0x180024dcb  jz      short loc_180024E05
0x180024dcd  mov     r9d, [rdi]
0x180024dd0  lea     rdx, aRaslinegetcall_8; "RasLineGetCallStatus: The needed size ("...
0x180024dd7  mov     r8d, [rdi+4]
0x180024ddb  call    cs:__imp_TracePrintfA
0x180024de1  jmp     short loc_180024E05
0x180024de3  lea     r9, [rsi+1Ch]
0x180024de7  mov     dword ptr [rsi+8], 38h ; '8'
0x180024dee  lea     rdx, [rdi+1Ch]
0x180024df2  mov     [rsp+880h+var_860], 24h ; '$'
0x180024dfa  mov     r8, rsi
0x180024dfd  mov     rcx, rdi
0x180024e00  call    CopyVariableData
0x180024e05  test    r14, r14
0x180024e08  jz      short loc_180024E1E
0x180024e0a  call    cs:__imp_GetProcessHeap
0x180024e10  mov     r8, r14; lpMem
0x180024e13  xor     edx, edx; dwFlags
0x180024e15  mov     rcx, rax; hHeap
0x180024e18  call    cs:__imp_HeapFree
0x180024e1e  test    r15, r15
0x180024e21  jz      short loc_180024E2B
0x180024e23  mov     ecx, r12d
0x180024e26  call    ReleaseObjReadLock
0x180024e2b  mov     eax, ebx
0x180024e2d  mov     rcx, [rbp+780h+var_40]
0x180024e34  xor     rcx, rsp; StackCookie
0x180024e37  call    __security_check_cookie
0x180024e3c  mov     rbx, [rsp+880h+arg_10]
0x180024e44  add     rsp, 850h
0x180024e4b  pop     r15
0x180024e4d  pop     r14
0x180024e4f  pop     r13
0x180024e51  pop     r12
0x180024e53  pop     rdi
0x180024e54  pop     rsi
0x180024e55  pop     rbp
0x180024e56  retn
```
