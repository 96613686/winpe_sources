# FreeInterfaceLuidIndex

- ea: `0x18000f2ac`
- end: `0x18000f5c7`
- name: `FreeInterfaceLuidIndex`
- size: `795`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000d280`
- `0x18000ef08`

## callees

- `0x18000f2ac`
- `0x180011790`
- `0x180053014`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x18000f421`
- `KERNEL32!DeviceIoControl` at `0x18000f421`
- `KERNEL32!GetLastError` at `0x18000f42b`
- `KERNEL32!GetLastError` at `0x18000f42b`

## string_xrefs

- `0x18000f498`: `FreeInterfaceLuidIndex: dwRemoveLuid: failed with error %d`
- `0x18000f516`: `FreeInterfaceLuidIndex: Completes with status %x`

## pseudocode

```c
__int64 __fastcall FreeInterfaceLuidIndex(__int64 a1, int a2, __int64 a3, unsigned int a4)
{
  __int128 *v7; // r9
  char *v8; // rdi
  __int128 *v9; // r9
  DWORD LastError; // edi
  const wchar_t *v11; // r8
  __int64 *v12; // rdx
  __int128 *v13; // r9
  DWORD v14; // eax
  __int128 *v15; // r9
  __int128 *v16; // r9
  __int128 *v17; // r9
  __int64 InBuffer; // [rsp+48h] [rbp-B8h] BYREF
  DWORD BytesReturned; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v21; // [rsp+58h] [rbp-A8h] BYREF
  int v22; // [rsp+68h] [rbp-98h] BYREF
  __int128 v23; // [rsp+6Ch] [rbp-94h]
  __int128 v24; // [rsp+7Ch] [rbp-84h]
  int v25; // [rsp+8Ch] [rbp-74h]
  int v26; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v27[2044]; // [rsp+94h] [rbp-6Ch] BYREF

  BytesReturned = 0;
  InBuffer = 0;
  v26 = 0;
  memset_0(v27, 0, sizeof(v27));
  v22 = 0;
  v23 = 0;
  v25 = 0;
  v24 = 0;
  v21 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v22) = 0;
    v7 = &v21;
    if ( a3 )
      LODWORD(v7) = a3;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Entered: FreeInterfaceLuidIndex",
      (_DWORD)v7,
      0,
      (__int64)&v22);
  }
  v8 = (char *)g_hWanarpWriteV6;
  HIDWORD(InBuffer) = a4;
  if ( a2 )
    v8 = (char *)g_hWanarpWrite;
  LOWORD(InBuffer) = 23;
  if ( (unsigned __int64)(v8 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v22) = 0;
      v15 = &v21;
      if ( a3 )
        LODWORD(v15) = a3;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)L"FreeInterfaceLuidIndex: Helper is not Initialized",
        (_DWORD)v15,
        0,
        (__int64)&v22);
    }
    LastError = 6;
  }
  else
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v26) = 0;
      LOWORD(v22) = 0;
      FormatRRASErrorString(&v26, L"FreeInterfaceLuidIndex: Freeing LUID index %d", a4);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v9 = &v21;
        if ( a3 )
          LODWORD(v9) = a3;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v26,
          (_DWORD)v9,
          0,
          (__int64)&v22);
      }
    }
    if ( DeviceIoControl(v8, 0x90018020, &InBuffer, 8u, 0, 0, &BytesReturned, 0) )
    {
      v14 = DwRemoveLuid(SHIDWORD(InBuffer));
      LastError = v14;
      if ( !v14 )
        goto LABEL_28;
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
        goto LABEL_28;
      LOWORD(v26) = 0;
      LOWORD(v22) = 0;
      FormatRRASErrorString(&v26, L"FreeInterfaceLuidIndex: dwRemoveLuid: failed with error %d", v14);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
        goto LABEL_28;
      v11 = (const wchar_t *)&v26;
      v12 = RasRtrMgrParamTraceError;
    }
    else
    {
      LastError = GetLastError();
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
        goto LABEL_28;
      LOWORD(v22) = 0;
      v11 = L"FreeInterfaceLuidIndex: DeviceIoControl fails";
      v12 = RasRtrmgrParamTraceInfo;
    }
    v13 = &v21;
    if ( a3 )
      LODWORD(v13) = a3;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (_DWORD)v12,
      (_DWORD)v11,
      (_DWORD)v13,
      0,
      (__int64)&v22);
  }
LABEL_28:
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v26) = 0;
    LOWORD(v22) = 0;
    FormatRRASErrorString(&v26, L"FreeInterfaceLuidIndex: Completes with status %x", LastError);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v16 = &v21;
      if ( a3 )
        LODWORD(v16) = a3;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v26,
        (_DWORD)v16,
        0,
        (__int64)&v22);
    }
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v22) = 0;
    v17 = &v21;
    if ( a3 )
      LODWORD(v17) = a3;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Leaving: FreeInterfaceLuidIndex",
      (_DWORD)v17,
      0,
      (__int64)&v22);
  }
  return LastError;
}

```

## disassembly

```asm
0x18000f2ac  mov     [rsp-8+arg_0], rbx
0x18000f2b1  push    rbp
0x18000f2b2  push    rsi
0x18000f2b3  push    rdi
0x18000f2b4  push    r12
0x18000f2b6  push    r13
0x18000f2b8  push    r14
0x18000f2ba  push    r15
0x18000f2bc  lea     rbp, [rsp-7A0h]
0x18000f2c4  sub     rsp, 8A0h
0x18000f2cb  mov     rax, cs:__security_cookie
0x18000f2d2  xor     rax, rsp
0x18000f2d5  mov     [rbp+7D0h+var_40], rax
0x18000f2dc  xor     r15d, r15d
0x18000f2df  lea     rcx, [rbp+7D0h+var_83C]; void *
0x18000f2e3  mov     rbx, r8
0x18000f2e6  mov     [rsp+8D0h+BytesReturned], r15d
0x18000f2eb  mov     r14d, edx
0x18000f2ee  mov     [rsp+8D0h+InBuffer], r15
0x18000f2f3  xor     edx, edx; Val
0x18000f2f5  mov     [rbp+7D0h+var_840], r15d
0x18000f2f9  mov     r8d, 7FCh; Size
0x18000f2ff  mov     esi, r9d
0x18000f302  call    memset_0
0x18000f307  xorps   xmm0, xmm0
0x18000f30a  mov     [rsp+8D0h+var_868], r15d
0x18000f30f  xor     eax, eax
0x18000f311  lea     r13, RasRtrmgrParamTraceInfo
0x18000f318  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18000f31f  lea     r12, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000f326  movups  [rsp+8D0h+var_864], xmm0
0x18000f32b  mov     [rbp+7D0h+var_844], eax
0x18000f32e  movups  [rsp+8D0h+var_854], xmm0
0x18000f333  movups  [rsp+8D0h+var_878], xmm0
0x18000f338  jz      short loc_18000F36D
0x18000f33a  test    rbx, rbx
0x18000f33d  mov     word ptr [rsp+8D0h+var_868], r15w
0x18000f343  lea     rax, [rsp+8D0h+var_868]
0x18000f348  mov     rdx, r13
0x18000f34b  mov     qword ptr [rsp+8D0h+nOutBufferSize], rax
0x18000f350  lea     r9, [rsp+8D0h+var_878]
0x18000f355  cmovnz  r9, rbx
0x18000f359  mov     [rsp+8D0h+lpOutBuffer], r15
0x18000f35e  lea     r8, aEnteredFreeint; "Entered: FreeInterfaceLuidIndex"
0x18000f365  mov     rcx, r12
0x18000f368  call    McTemplateU0zjzz_EventWriteTransfer
0x18000f36d  mov     rdi, cs:g_hWanarpWriteV6
0x18000f374  test    r14d, r14d
0x18000f377  mov     eax, 17h
0x18000f37c  mov     dword ptr [rsp+8D0h+InBuffer+4], esi
0x18000f380  cmovnz  rdi, cs:g_hWanarpWrite
0x18000f388  mov     word ptr [rsp+8D0h+InBuffer], ax
0x18000f38d  lea     rax, [rdi-1]
0x18000f391  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000f395  ja      loc_18000F4C4
0x18000f39b  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18000f3a2  jge     short loc_18000F3F5
0x18000f3a4  mov     r8d, esi
0x18000f3a7  mov     word ptr [rbp+7D0h+var_840], r15w
0x18000f3ac  lea     rdx, aFreeinterfacel_0; "FreeInterfaceLuidIndex: Freeing LUID in"...
0x18000f3b3  mov     word ptr [rsp+8D0h+var_868], r15w
0x18000f3b9  lea     rcx, [rbp+7D0h+var_840]
0x18000f3bd  call    FormatRRASErrorString
0x18000f3c2  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18000f3c9  jge     short loc_18000F3F5
0x18000f3cb  test    rbx, rbx
0x18000f3ce  lea     rax, [rsp+8D0h+var_868]
0x18000f3d3  mov     qword ptr [rsp+8D0h+nOutBufferSize], rax
0x18000f3d8  lea     r9, [rsp+8D0h+var_878]
0x18000f3dd  cmovnz  r9, rbx
0x18000f3e1  mov     [rsp+8D0h+lpOutBuffer], r15
0x18000f3e6  lea     r8, [rbp+7D0h+var_840]
0x18000f3ea  mov     rdx, r13
0x18000f3ed  mov     rcx, r12
0x18000f3f0  call    McTemplateU0zjzz_EventWriteTransfer
0x18000f3f5  mov     [rsp+8D0h+lpOverlapped], r15; lpOverlapped
0x18000f3fa  lea     rax, [rsp+8D0h+BytesReturned]
0x18000f3ff  mov     [rsp+8D0h+lpBytesReturned], rax; lpBytesReturned
0x18000f404  lea     r8, [rsp+8D0h+InBuffer]; lpInBuffer
0x18000f409  mov     [rsp+8D0h+nOutBufferSize], r15d; nOutBufferSize
0x18000f40e  mov     r9d, 8; nInBufferSize
0x18000f414  mov     edx, 90018020h; dwIoControlCode
0x18000f419  mov     [rsp+8D0h+lpOutBuffer], r15; lpOutBuffer
0x18000f41e  mov     rcx, rdi; hDevice
0x18000f421  call    cs:__imp_DeviceIoControl
0x18000f427  test    eax, eax
0x18000f429  jnz     short loc_18000F478
0x18000f42b  call    cs:__imp_GetLastError
0x18000f431  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18000f438  mov     edi, eax
0x18000f43a  jz      loc_18000F505
0x18000f440  mov     word ptr [rsp+8D0h+var_868], r15w
0x18000f446  lea     r8, aFreeinterfacel; "FreeInterfaceLuidIndex: DeviceIoControl"...
0x18000f44d  mov     rdx, r13
0x18000f450  test    rbx, rbx
0x18000f453  lea     rax, [rsp+8D0h+var_868]
0x18000f458  mov     qword ptr [rsp+8D0h+nOutBufferSize], rax
0x18000f45d  lea     r9, [rsp+8D0h+var_878]
0x18000f462  cmovnz  r9, rbx
0x18000f466  mov     [rsp+8D0h+lpOutBuffer], r15
0x18000f46b  mov     rcx, r12
0x18000f46e  call    McTemplateU0zjzz_EventWriteTransfer
0x18000f473  jmp     loc_18000F505
0x18000f478  mov     ecx, dword ptr [rsp+8D0h+InBuffer+4]
0x18000f47c  call    DwRemoveLuid
0x18000f481  mov     edi, eax
0x18000f483  test    eax, eax
0x18000f485  jz      short loc_18000F505
0x18000f487  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18000f48e  jz      short loc_18000F505
0x18000f490  mov     r8d, eax
0x18000f493  mov     word ptr [rbp+7D0h+var_840], r15w
0x18000f498  lea     rdx, aFreeinterfacel_3; "FreeInterfaceLuidIndex: dwRemoveLuid: f"...
0x18000f49f  mov     word ptr [rsp+8D0h+var_868], r15w
0x18000f4a5  lea     rcx, [rbp+7D0h+var_840]
0x18000f4a9  call    FormatRRASErrorString
0x18000f4ae  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18000f4b5  jz      short loc_18000F505
0x18000f4b7  lea     r8, [rbp+7D0h+var_840]
0x18000f4bb  lea     rdx, RasRtrMgrParamTraceError
0x18000f4c2  jmp     short loc_18000F450
0x18000f4c4  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18000f4cb  jz      short loc_18000F500
0x18000f4cd  test    rbx, rbx
0x18000f4d0  mov     word ptr [rsp+8D0h+var_868], r15w
0x18000f4d6  lea     rax, [rsp+8D0h+var_868]
0x18000f4db  mov     rdx, r13
0x18000f4de  mov     qword ptr [rsp+8D0h+nOutBufferSize], rax
0x18000f4e3  lea     r9, [rsp+8D0h+var_878]
0x18000f4e8  cmovnz  r9, rbx
0x18000f4ec  mov     [rsp+8D0h+lpOutBuffer], r15
0x18000f4f1  lea     r8, aFreeinterfacel_1; "FreeInterfaceLuidIndex: Helper is not I"...
0x18000f4f8  mov     rcx, r12
0x18000f4fb  call    McTemplateU0zjzz_EventWriteTransfer
0x18000f500  mov     edi, 6
0x18000f505  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18000f50c  jge     short loc_18000F55F
0x18000f50e  mov     r8d, edi
0x18000f511  mov     word ptr [rbp+7D0h+var_840], r15w
0x18000f516  lea     rdx, aFreeinterfacel_2; "FreeInterfaceLuidIndex: Completes with "...
0x18000f51d  mov     word ptr [rsp+8D0h+var_868], r15w
0x18000f523  lea     rcx, [rbp+7D0h+var_840]
0x18000f527  call    FormatRRASErrorString
0x18000f52c  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18000f533  jge     short loc_18000F55F
0x18000f535  test    rbx, rbx
0x18000f538  lea     rax, [rsp+8D0h+var_868]
0x18000f53d  mov     qword ptr [rsp+8D0h+nOutBufferSize], rax
0x18000f542  lea     r9, [rsp+8D0h+var_878]
0x18000f547  cmovnz  r9, rbx
0x18000f54b  mov     [rsp+8D0h+lpOutBuffer], r15
0x18000f550  lea     r8, [rbp+7D0h+var_840]
0x18000f554  mov     rdx, r13
0x18000f557  mov     rcx, r12
0x18000f55a  call    McTemplateU0zjzz_EventWriteTransfer
0x18000f55f  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18000f566  jz      short loc_18000F59B
0x18000f568  test    rbx, rbx
0x18000f56b  mov     word ptr [rsp+8D0h+var_868], r15w
0x18000f571  lea     rax, [rsp+8D0h+var_868]
0x18000f576  mov     rdx, r13
0x18000f579  mov     qword ptr [rsp+8D0h+nOutBufferSize], rax
0x18000f57e  lea     r9, [rsp+8D0h+var_878]
0x18000f583  cmovnz  r9, rbx
0x18000f587  mov     [rsp+8D0h+lpOutBuffer], r15
0x18000f58c  lea     r8, aLeavingFreeint; "Leaving: FreeInterfaceLuidIndex"
0x18000f593  mov     rcx, r12
0x18000f596  call    McTemplateU0zjzz_EventWriteTransfer
0x18000f59b  mov     eax, edi
0x18000f59d  mov     rcx, [rbp+7D0h+var_40]
0x18000f5a4  xor     rcx, rsp; StackCookie
0x18000f5a7  call    __security_check_cookie
0x18000f5ac  mov     rbx, [rsp+8D0h+arg_0]
0x18000f5b4  add     rsp, 8A0h
0x18000f5bb  pop     r15
0x18000f5bd  pop     r14
0x18000f5bf  pop     r13
0x18000f5c1  pop     r12
0x18000f5c3  pop     rdi
0x18000f5c4  pop     rsi
0x18000f5c5  pop     rbp
0x18000f5c6  retn
```
