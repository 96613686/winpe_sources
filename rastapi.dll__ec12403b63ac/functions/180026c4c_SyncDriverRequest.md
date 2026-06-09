# SyncDriverRequest

- ea: `0x180026c4c`
- end: `0x180026f95`
- name: `SyncDriverRequest`
- size: `841`
- prototype: `__int64 __fastcall(DWORD dwIoControlCode, _DWORD *lpInBuffer)`
- caller_count: `10`
- callee_count: `6`
- tags: ``

## callers

- `0x1800226f0`
- `0x180023610`
- `0x180023a14`
- `0x1800240a8`
- `0x1800244ec`
- `0x180024b38`
- `0x180024e60`
- `0x180025244`
- `0x18002619c`
- `0x180026a2c`

## callees

- `0x180026c4c`
- `0x180027e38`
- `0x180029130`
- `0x18002927e`
- `0x1800292b0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026e32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026e32`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180026e23`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180026e23`
- `rtutils!TracePrintfA` at `0x180026df0`
- `rtutils!TracePrintfA` at `0x180026ec3`
- `rtutils!TracePrintfA` at `0x180026f5a`
- `rtutils!TracePrintfA` at `0x180026df0`
- `rtutils!TracePrintfA` at `0x180026ec3`
- `rtutils!TracePrintfA` at `0x180026f5a`

## pseudocode

```c
__int64 __fastcall SyncDriverRequest(DWORD dwIoControlCode, _DWORD *lpInBuffer)
{
  __int64 v4; // r8
  const wchar_t *v5; // rdx
  DWORD v6; // ecx
  const CHAR *v7; // rdx
  __int64 v8; // r9
  char *v9; // r8
  DWORD LastError; // eax
  DWORD v11; // edi
  int v12; // ecx
  unsigned int v13; // esi
  int v14; // eax
  int lpOutBuffer; // [rsp+20h] [rbp-E0h]
  DWORD nOutBufferSize[2]; // [rsp+28h] [rbp-D8h]
  DWORD BytesReturned[4]; // [rsp+40h] [rbp-C0h] BYREF
  int v19; // [rsp+50h] [rbp-B0h] BYREF
  char v20[2044]; // [rsp+54h] [rbp-ACh] BYREF

  BytesReturned[0] = 0;
  v19 = 0;
  memset_0(v20, 0, sizeof(v20));
  v4 = (unsigned int)(lpInBuffer[8] - 117637377);
  if ( dword_180037370[v4] == 2 )
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( !qword_18003EC40 )
        goto LABEL_23;
      v5 = L"SyncDriverRequest: Oid(%hs), devID(%x), reqID(%x), hCall(%p)";
      goto LABEL_17;
    }
    v6 = dwTraceId;
    if ( dwTraceId == -1 )
      goto LABEL_23;
    v7 = "SyncDriverRequest: Oid(%hs), devID(%x), reqID(%x), hCall(%p)";
  }
  else
  {
    if ( dword_180037370[lpInBuffer[8] - 117637377] != 3 )
    {
      if ( dword_180037370[lpInBuffer[8] - 117637377] != 4 )
        goto LABEL_23;
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( !qword_18003EC40 )
          goto LABEL_23;
        v5 = L"SyncDriverRequest: Oid(%hs), devID(%x), reqID(%x), deviceID(%x)";
        nOutBufferSize[0] = lpInBuffer[13];
        goto LABEL_18;
      }
      v6 = dwTraceId;
      if ( dwTraceId == -1 )
        goto LABEL_23;
      v7 = "SyncDriverRequest: Oid(%hs), devID(%x), reqID(%x), deviceID(%x)";
      nOutBufferSize[0] = lpInBuffer[13];
      goto LABEL_22;
    }
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( !qword_18003EC40 )
        goto LABEL_23;
      v5 = L"SyncDriverRequest: Oid(%hs), devID(%x), reqID(%x), hLine(%p)";
LABEL_17:
      *(_QWORD *)nOutBufferSize = *((_QWORD *)lpInBuffer + 7);
LABEL_18:
      v8 = (unsigned int)lpInBuffer[9];
      v9 = off_18002B190[v4];
      lpOutBuffer = lpInBuffer[12];
      LOWORD(v19) = 0;
      FormatRRASErrorString(&v19, v5, v9, v8, lpOutBuffer, *(_QWORD *)nOutBufferSize);
      ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v19);
      goto LABEL_23;
    }
    v6 = dwTraceId;
    if ( dwTraceId == -1 )
      goto LABEL_23;
    v7 = "SyncDriverRequest: Oid(%hs), devID(%x), reqID(%x), hLine(%p)";
  }
  *(_QWORD *)nOutBufferSize = *((_QWORD *)lpInBuffer + 7);
LABEL_22:
  TracePrintfA(v6, v7, off_18002B190[v4], (unsigned int)lpInBuffer[9], lpInBuffer[12], *(_QWORD *)nOutBufferSize);
LABEL_23:
  if ( DeviceIoControl(
         g_hDriverSync,
         dwIoControlCode,
         lpInBuffer,
         lpInBuffer[10] + 56,
         lpInBuffer,
         lpInBuffer[10] + 56,
         BytesReturned,
         0) )
  {
    v13 = lpInBuffer[7];
    v11 = 0;
    if ( v13 )
    {
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( qword_18003EC40 )
        {
          v14 = lpInBuffer[8] - 117637377;
          LOWORD(v19) = 0;
          FormatRRASErrorString(
            &v19,
            L"SyncDriverRequest: Oid (%hs) returns with NDIS status (0x%x)",
            off_18002B190[v14],
            v13);
          ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v19);
        }
      }
      else if ( dwTraceId != -1 )
      {
        TracePrintfA(
          dwTraceId,
          "SyncDriverRequest: Oid (%hs) returns with NDIS status (0x%x)",
          off_18002B190[lpInBuffer[8] - 117637377],
          v13);
      }
      return (unsigned int)TranslateDriverResult(v13);
    }
  }
  else
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( qword_18003EC40 )
      {
        v12 = lpInBuffer[8] - 117637377;
        LOWORD(v19) = 0;
        FormatRRASErrorString(&v19, L"SyncDriverRequest: IoCtl (Oid %hs) failed (0x%x)", off_18002B190[v12], LastError);
        ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v19);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(
        dwTraceId,
        "SyncDriverRequest: IoCtl (Oid %hs) failed (0x%x)",
        off_18002B190[lpInBuffer[8] - 117637377],
        LastError);
    }
  }
  return v11;
}

```

## disassembly

```asm
0x180026c4c  mov     [rsp-8+arg_10], rbx
0x180026c51  push    rbp
0x180026c52  push    rsi
0x180026c53  push    rdi
0x180026c54  push    r12
0x180026c56  push    r13
0x180026c58  push    r14
0x180026c5a  push    r15
0x180026c5c  lea     rbp, [rsp-760h]
0x180026c64  sub     rsp, 860h
0x180026c6b  mov     rax, cs:__security_cookie
0x180026c72  xor     rax, rsp
0x180026c75  mov     [rbp+790h+var_40], rax
0x180026c7c  mov     rbx, rdx
0x180026c7f  mov     edi, ecx
0x180026c81  xor     r14d, r14d
0x180026c84  lea     rcx, [rsp+890h+var_83C]; void *
0x180026c89  xor     edx, edx; Val
0x180026c8b  mov     [rsp+890h+BytesReturned], r14d
0x180026c90  mov     r8d, 7FCh; Size
0x180026c96  mov     [rsp+890h+var_840], r14d
0x180026c9b  call    memset_0
0x180026ca0  mov     eax, [rbx+20h]
0x180026ca3  lea     r15, __ImageBase
0x180026caa  mov     r13d, 7030101h
0x180026cb0  or      r12d, 0FFFFFFFFh
0x180026cb4  sub     eax, r13d
0x180026cb7  mov     r8d, eax
0x180026cba  mov     ecx, ds:rva dword_180037370[r15+rax*4]
0x180026cc2  sub     ecx, 2
0x180026cc5  jz      loc_180026D58
0x180026ccb  sub     ecx, 1
0x180026cce  jz      short loc_180026D21
0x180026cd0  cmp     ecx, 1
0x180026cd3  jnz     loc_180026DF6
0x180026cd9  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x180026ce0  jz      short loc_180026CFF
0x180026ce2  cmp     cs:qword_18003EC40, r14
0x180026ce9  jz      loc_180026DF6
0x180026cef  mov     eax, [rbx+34h]
0x180026cf2  lea     rdx, aSyncdriverrequ_4; "SyncDriverRequest: Oid(%hs), devID(%x),"...
0x180026cf9  mov     [rsp+890h+nOutBufferSize], eax
0x180026cfd  jmp     short loc_180026D7E
0x180026cff  mov     ecx, cs:dwTraceId
0x180026d05  cmp     ecx, r12d
0x180026d08  jz      loc_180026DF6
0x180026d0e  mov     eax, [rbx+34h]
0x180026d11  lea     rdx, aSyncdriverrequ_5; "SyncDriverRequest: Oid(%hs), devID(%x),"...
0x180026d18  mov     [rsp+890h+nOutBufferSize], eax
0x180026d1c  jmp     loc_180026DDD
0x180026d21  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x180026d28  jz      short loc_180026D40
0x180026d2a  cmp     cs:qword_18003EC40, r14
0x180026d31  jz      loc_180026DF6
0x180026d37  lea     rdx, aSyncdriverrequ_6; "SyncDriverRequest: Oid(%hs), devID(%x),"...
0x180026d3e  jmp     short loc_180026D75
0x180026d40  mov     ecx, cs:dwTraceId
0x180026d46  cmp     ecx, r12d
0x180026d49  jz      loc_180026DF6
0x180026d4f  lea     rdx, aSyncdriverrequ_0; "SyncDriverRequest: Oid(%hs), devID(%x),"...
0x180026d56  jmp     short loc_180026DD4
0x180026d58  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x180026d5f  jz      short loc_180026DC2
0x180026d61  cmp     cs:qword_18003EC40, r14
0x180026d68  jz      loc_180026DF6
0x180026d6e  lea     rdx, aSyncdriverrequ_2; "SyncDriverRequest: Oid(%hs), devID(%x),"...
0x180026d75  mov     rax, [rbx+38h]
0x180026d79  mov     qword ptr [rsp+890h+nOutBufferSize], rax
0x180026d7e  mov     eax, [rbx+30h]
0x180026d81  lea     rcx, [rsp+890h+var_840]
0x180026d86  mov     r9d, [rbx+24h]
0x180026d8a  mov     r8, ds:rva off_18002B190[r15+r8*8]; "Accept" ...
0x180026d92  mov     dword ptr [rsp+890h+lpOutBuffer], eax
0x180026d96  mov     word ptr [rsp+890h+var_840], r14w
0x180026d9c  call    FormatRRASErrorString
0x180026da1  mov     rdx, cs:qword_18003EC40
0x180026da8  lea     r8, [rsp+890h+var_840]
0x180026dad  mov     rcx, cs:gNdpspEtwContext
0x180026db4  mov     rax, cs:gNdpspTemplateFunc
0x180026dbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026dc0  jmp     short loc_180026DF6
0x180026dc2  mov     ecx, cs:dwTraceId; dwTraceID
0x180026dc8  cmp     ecx, r12d
0x180026dcb  jz      short loc_180026DF6
0x180026dcd  lea     rdx, aSyncdriverrequ_7; "SyncDriverRequest: Oid(%hs), devID(%x),"...
0x180026dd4  mov     rax, [rbx+38h]
0x180026dd8  mov     qword ptr [rsp+890h+nOutBufferSize], rax
0x180026ddd  mov     eax, [rbx+30h]
0x180026de0  mov     r9d, [rbx+24h]
0x180026de4  mov     r8, ds:rva off_18002B190[r15+r8*8]; "Accept" ...
0x180026dec  mov     dword ptr [rsp+890h+lpOutBuffer], eax
0x180026df0  call    cs:__imp_TracePrintfA
0x180026df6  mov     r9d, [rbx+28h]
0x180026dfa  lea     rax, [rsp+890h+BytesReturned]
0x180026dff  mov     rcx, cs:g_hDriverSync; hDevice
0x180026e06  add     r9d, 38h ; '8'; nInBufferSize
0x180026e0a  mov     [rsp+890h+lpOverlapped], r14; lpOverlapped
0x180026e0f  mov     r8, rbx; lpInBuffer
0x180026e12  mov     [rsp+890h+lpBytesReturned], rax; lpBytesReturned
0x180026e17  mov     edx, edi; dwIoControlCode
0x180026e19  mov     [rsp+890h+nOutBufferSize], r9d; nOutBufferSize
0x180026e1e  mov     [rsp+890h+lpOutBuffer], rbx; lpOutBuffer
0x180026e23  call    cs:__imp_DeviceIoControl
0x180026e29  cmp     eax, 1
0x180026e2c  jz      loc_180026ECE
0x180026e32  call    cs:__imp_GetLastError
0x180026e38  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x180026e3f  mov     edi, eax
0x180026e41  jz      short loc_180026E9C
0x180026e43  cmp     cs:qword_18003EC40, r14
0x180026e4a  jz      loc_180026F69
0x180026e50  mov     ecx, [rbx+20h]
0x180026e53  lea     rdx, aSyncdriverrequ_1; "SyncDriverRequest: IoCtl (Oid %hs) fail"...
0x180026e5a  sub     ecx, r13d
0x180026e5d  mov     word ptr [rsp+890h+var_840], r14w
0x180026e63  mov     r9d, eax
0x180026e66  mov     r8, ds:rva off_18002B190[r15+rcx*8]; "Accept" ...
0x180026e6e  lea     rcx, [rsp+890h+var_840]
0x180026e73  call    FormatRRASErrorString
0x180026e78  mov     rdx, cs:qword_18003EC40
0x180026e7f  lea     r8, [rsp+890h+var_840]
0x180026e84  mov     rcx, cs:gNdpspEtwContext
0x180026e8b  mov     rax, cs:gNdpspTemplateFunc
0x180026e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e97  jmp     loc_180026F69
0x180026e9c  mov     ecx, cs:dwTraceId; dwTraceID
0x180026ea2  cmp     ecx, r12d
0x180026ea5  jz      loc_180026F69
0x180026eab  mov     eax, [rbx+20h]
0x180026eae  lea     rdx, aSyncdriverrequ; "SyncDriverRequest: IoCtl (Oid %hs) fail"...
0x180026eb5  sub     eax, r13d
0x180026eb8  mov     r9d, edi
0x180026ebb  mov     r8, ds:rva off_18002B190[r15+rax*8]; "Accept" ...
0x180026ec3  call    cs:__imp_TracePrintfA
0x180026ec9  jmp     loc_180026F69
0x180026ece  mov     esi, [rbx+1Ch]
0x180026ed1  mov     edi, r14d
0x180026ed4  test    esi, esi
0x180026ed6  jz      loc_180026F69
0x180026edc  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x180026ee3  jz      short loc_180026F37
0x180026ee5  cmp     cs:qword_18003EC40, r14
0x180026eec  jz      short loc_180026F60
0x180026eee  mov     eax, [rbx+20h]
0x180026ef1  lea     rdx, aSyncdriverrequ_3; "SyncDriverRequest: Oid (%hs) returns wi"...
0x180026ef8  sub     eax, r13d
0x180026efb  mov     word ptr [rsp+890h+var_840], r14w
0x180026f01  mov     r9d, esi
0x180026f04  lea     rcx, [rsp+890h+var_840]
0x180026f09  mov     r8, ds:rva off_18002B190[r15+rax*8]; "Accept" ...
0x180026f11  call    FormatRRASErrorString
0x180026f16  mov     rdx, cs:qword_18003EC40
0x180026f1d  lea     r8, [rsp+890h+var_840]
0x180026f22  mov     rcx, cs:gNdpspEtwContext
0x180026f29  mov     rax, cs:gNdpspTemplateFunc
0x180026f30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f35  jmp     short loc_180026F60
0x180026f37  mov     ecx, cs:dwTraceId; dwTraceID
0x180026f3d  cmp     ecx, r12d
0x180026f40  jz      short loc_180026F60
0x180026f42  mov     eax, [rbx+20h]
0x180026f45  lea     rdx, aSyncdriverrequ_8; "SyncDriverRequest: Oid (%hs) returns wi"...
0x180026f4c  sub     eax, r13d
0x180026f4f  mov     r9d, esi
0x180026f52  mov     r8, ds:rva off_18002B190[r15+rax*8]; "Accept" ...
0x180026f5a  call    cs:__imp_TracePrintfA
0x180026f60  mov     ecx, esi
0x180026f62  call    TranslateDriverResult
0x180026f67  mov     edi, eax
0x180026f69  mov     eax, edi
0x180026f6b  mov     rcx, [rbp+790h+var_40]
0x180026f72  xor     rcx, rsp; StackCookie
0x180026f75  call    __security_check_cookie
0x180026f7a  mov     rbx, [rsp+890h+arg_10]
0x180026f82  add     rsp, 860h
0x180026f89  pop     r15
0x180026f8b  pop     r14
0x180026f8d  pop     r13
0x180026f8f  pop     r12
0x180026f91  pop     rdi
0x180026f92  pop     rsi
0x180026f93  pop     rbp
0x180026f94  retn
```
