# AllocInterfaceLuidIndex

- ea: `0x18000e340`
- end: `0x18000e712`
- name: `AllocInterfaceLuidIndex`
- size: `978`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000d280`

## callees

- `0x18000e340`
- `0x180011790`
- `0x180052e48`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x18000e49c`
- `KERNEL32!DeviceIoControl` at `0x18000e591`
- `KERNEL32!DeviceIoControl` at `0x18000e49c`
- `KERNEL32!DeviceIoControl` at `0x18000e591`
- `KERNEL32!GetLastError` at `0x18000e4a6`
- `KERNEL32!GetLastError` at `0x18000e5b7`
- `KERNEL32!GetLastError` at `0x18000e4a6`
- `KERNEL32!GetLastError` at `0x18000e5b7`

## string_xrefs

- `0x18000e661`: `AllocInterfaceLuidIndex: Completes with status %x`

## pseudocode

```c
__int64 __fastcall AllocInterfaceLuidIndex(__int64 a1, int a2, __int128 *a3, _DWORD *a4)
{
  __int128 *v7; // r9
  char *v8; // rsi
  __int128 *v9; // r9
  DWORD v10; // edi
  const wchar_t *v11; // r8
  __int128 *v12; // r9
  DWORD v13; // eax
  __int128 *v14; // r9
  __int64 LastError; // r8
  __int64 v16; // r8
  __int128 *v17; // r9
  __int128 *v18; // r9
  __int128 *v19; // r9
  __int64 OutBuffer; // [rsp+48h] [rbp-B8h] BYREF
  DWORD BytesReturned; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v23; // [rsp+58h] [rbp-A8h] BYREF
  int v24; // [rsp+68h] [rbp-98h] BYREF
  __int128 v25; // [rsp+6Ch] [rbp-94h]
  __int128 v26; // [rsp+7Ch] [rbp-84h]
  int v27; // [rsp+8Ch] [rbp-74h]
  int v28; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v29[2044]; // [rsp+94h] [rbp-6Ch] BYREF

  BytesReturned = 0;
  OutBuffer = 0;
  v28 = 0;
  memset_0(v29, 0, sizeof(v29));
  v24 = 0;
  v25 = 0;
  v27 = 0;
  v26 = 0;
  v23 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v24) = 0;
    v7 = &v23;
    if ( a3 )
      v7 = a3;
    McTemplateU0zjzz_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)RasRtrmgrParamTraceInfo,
      L"Entered: AllocInterfaceLuidIndex",
      (__int64)v7,
      0,
      (const wchar_t *)&v24);
  }
  v8 = (char *)g_hWanarpWriteV6;
  if ( a2 )
    v8 = (char *)g_hWanarpWrite;
  LOWORD(OutBuffer) = 23;
  if ( (unsigned __int64)(v8 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v24) = 0;
      v17 = &v23;
      if ( a3 )
        v17 = a3;
      McTemplateU0zjzz_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasRtrmgrParamTraceInfo,
        L"AllocInterfaceLuidIndex: WANARP device is not Initialized",
        (__int64)v17,
        0,
        (const wchar_t *)&v24);
    }
    v10 = 6;
    goto LABEL_37;
  }
  if ( !a4 && (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v24) = 0;
    v9 = &v23;
    if ( a3 )
      v9 = a3;
    McTemplateU0zjzz_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)RasRtrmgrParamTraceInfo,
      L"AllocInterfaceLuidIndex: LuidIndex buffer not passed",
      (__int64)v9,
      0,
      (const wchar_t *)&v24);
  }
  if ( DeviceIoControl(v8, 0x9001801C, &OutBuffer, 8u, &OutBuffer, 8u, &BytesReturned, 0) )
  {
    v13 = DwAddLuidIfNotPresent(SHIDWORD(OutBuffer));
    v10 = v13;
    if ( v13 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v28) = 0;
        LOWORD(v24) = 0;
        FormatRRASErrorString(&v28, L"AllocateInterfaceLuidIndex: DwAddLuidIfNotPresent failed with %d", v13);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v14 = &v23;
          if ( a3 )
            v14 = a3;
          McTemplateU0zjzz_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (const EVENT_DESCRIPTOR *)RasRtrmgrParamTraceInfo,
            (const wchar_t *)&v28,
            (__int64)v14,
            0,
            (const wchar_t *)&v24);
        }
      }
      if ( DeviceIoControl(v8, 0x90018020, &OutBuffer, 8u, &OutBuffer, 8u, &BytesReturned, 0) )
        goto LABEL_37;
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
        goto LABEL_42;
      LOWORD(v28) = 0;
      LOWORD(v24) = 0;
      LastError = GetLastError();
      FormatRRASErrorString(&v28, L"AllocateInterfaceLuidIndex:  DeviceIoControl failed with %d", LastError);
    }
    else
    {
      v16 = HIDWORD(OutBuffer);
      *a4 = HIDWORD(OutBuffer);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
        goto LABEL_42;
      LOWORD(v28) = 0;
      LOWORD(v24) = 0;
      FormatRRASErrorString(&v28, L"AllocInterfaceLuidIndex: Allocated LUID index %d", v16);
    }
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_42;
    v11 = (const wchar_t *)&v28;
    goto LABEL_16;
  }
  v10 = GetLastError();
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v24) = 0;
    v11 = L"AllocInterfaceLuidIndex: DeviceIoControl fails";
LABEL_16:
    v12 = &v23;
    if ( a3 )
      v12 = a3;
    McTemplateU0zjzz_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)RasRtrmgrParamTraceInfo,
      v11,
      (__int64)v12,
      0,
      (const wchar_t *)&v24);
  }
LABEL_37:
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v28) = 0;
    LOWORD(v24) = 0;
    FormatRRASErrorString(&v28, L"AllocInterfaceLuidIndex: Completes with status %x", v10);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v18 = &v23;
      if ( a3 )
        v18 = a3;
      McTemplateU0zjzz_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasRtrmgrParamTraceInfo,
        (const wchar_t *)&v28,
        (__int64)v18,
        0,
        (const wchar_t *)&v24);
    }
  }
LABEL_42:
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v24) = 0;
    v19 = &v23;
    if ( a3 )
      v19 = a3;
    McTemplateU0zjzz_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)RasRtrmgrParamTraceInfo,
      L"Leaving: AllocInterfaceLuidIndex",
      (__int64)v19,
      0,
      (const wchar_t *)&v24);
  }
  return v10;
}

```

## disassembly

```asm
0x18000e340  mov     [rsp-8+arg_0], rbx
0x18000e345  push    rbp
0x18000e346  push    rsi
0x18000e347  push    rdi
0x18000e348  push    r12
0x18000e34a  push    r13
0x18000e34c  push    r14
0x18000e34e  push    r15
0x18000e350  lea     rbp, [rsp-7A0h]
0x18000e358  sub     rsp, 8A0h
0x18000e35f  mov     rax, cs:__security_cookie
0x18000e366  xor     rax, rsp
0x18000e369  mov     [rbp+7D0h+var_40], rax
0x18000e370  xor     r15d, r15d
0x18000e373  lea     rcx, [rbp+7D0h+var_83C]; void *
0x18000e377  mov     rbx, r8
0x18000e37a  mov     [rsp+8D0h+BytesReturned], r15d
0x18000e37f  mov     edi, edx
0x18000e381  mov     [rsp+8D0h+OutBuffer], r15
0x18000e386  xor     edx, edx; Val
0x18000e388  mov     [rbp+7D0h+var_840], r15d
0x18000e38c  mov     r8d, 7FCh; Size
0x18000e392  mov     r14, r9
0x18000e395  call    memset_0
0x18000e39a  xorps   xmm0, xmm0
0x18000e39d  mov     [rsp+8D0h+var_868], r15d
0x18000e3a2  xor     eax, eax
0x18000e3a4  lea     r12, RasRtrmgrParamTraceInfo
0x18000e3ab  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18000e3b2  lea     r13, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000e3b9  movups  [rsp+8D0h+var_864], xmm0
0x18000e3be  mov     [rbp+7D0h+var_844], eax
0x18000e3c1  movups  [rsp+8D0h+var_854], xmm0
0x18000e3c6  movups  [rsp+8D0h+var_878], xmm0
0x18000e3cb  jz      short loc_18000E400
0x18000e3cd  test    rbx, rbx
0x18000e3d0  mov     word ptr [rsp+8D0h+var_868], r15w
0x18000e3d6  lea     rax, [rsp+8D0h+var_868]
0x18000e3db  mov     rdx, r12
0x18000e3de  mov     qword ptr [rsp+8D0h+nOutBufferSize], rax
0x18000e3e3  lea     r9, [rsp+8D0h+var_878]
0x18000e3e8  cmovnz  r9, rbx
0x18000e3ec  mov     [rsp+8D0h+lpOutBuffer], r15
0x18000e3f1  lea     r8, aEnteredAllocin; "Entered: AllocInterfaceLuidIndex"
0x18000e3f8  mov     rcx, r13
0x18000e3fb  call    McTemplateU0zjzz_EventWriteTransfer
0x18000e400  mov     rsi, cs:g_hWanarpWriteV6
0x18000e407  test    edi, edi
0x18000e409  mov     eax, 17h
0x18000e40e  cmovnz  rsi, cs:g_hWanarpWrite
0x18000e416  mov     word ptr [rsp+8D0h+OutBuffer], ax
0x18000e41b  lea     rax, [rsi-1]
0x18000e41f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e423  ja      loc_18000E60F
0x18000e429  test    r14, r14
0x18000e42c  jnz     short loc_18000E46A
0x18000e42e  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18000e435  jz      short loc_18000E46A
0x18000e437  test    rbx, rbx
0x18000e43a  mov     word ptr [rsp+8D0h+var_868], r15w
0x18000e440  lea     rax, [rsp+8D0h+var_868]
0x18000e445  mov     rdx, r12
0x18000e448  mov     qword ptr [rsp+8D0h+nOutBufferSize], rax
0x18000e44d  lea     r9, [rsp+8D0h+var_878]
0x18000e452  cmovnz  r9, rbx
0x18000e456  mov     [rsp+8D0h+lpOutBuffer], r15
0x18000e45b  lea     r8, aAllocinterface; "AllocInterfaceLuidIndex: LuidIndex buff"...
0x18000e462  mov     rcx, r13
0x18000e465  call    McTemplateU0zjzz_EventWriteTransfer
0x18000e46a  mov     [rsp+8D0h+lpOverlapped], r15; lpOverlapped
0x18000e46f  lea     rax, [rsp+8D0h+BytesReturned]
0x18000e474  mov     [rsp+8D0h+lpBytesReturned], rax; lpBytesReturned
0x18000e479  lea     r8, [rsp+8D0h+OutBuffer]; lpInBuffer
0x18000e47e  mov     ecx, 8
0x18000e483  lea     rax, [rsp+8D0h+OutBuffer]
0x18000e488  mov     [rsp+8D0h+nOutBufferSize], ecx; nOutBufferSize
0x18000e48c  mov     r9d, ecx; nInBufferSize
0x18000e48f  mov     rcx, rsi; hDevice
0x18000e492  mov     [rsp+8D0h+lpOutBuffer], rax; lpOutBuffer
0x18000e497  mov     edx, 9001801Ch; dwIoControlCode
0x18000e49c  call    cs:__imp_DeviceIoControl
0x18000e4a2  test    eax, eax
0x18000e4a4  jnz     short loc_18000E4F3
0x18000e4a6  call    cs:__imp_GetLastError
0x18000e4ac  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18000e4b3  mov     edi, eax
0x18000e4b5  jz      loc_18000E650
0x18000e4bb  mov     word ptr [rsp+8D0h+var_868], r15w
0x18000e4c1  lea     r8, aAllocinterface_2; "AllocInterfaceLuidIndex: DeviceIoContro"...
0x18000e4c8  test    rbx, rbx
0x18000e4cb  lea     rax, [rsp+8D0h+var_868]
0x18000e4d0  mov     qword ptr [rsp+8D0h+nOutBufferSize], rax
0x18000e4d5  lea     r9, [rsp+8D0h+var_878]
0x18000e4da  cmovnz  r9, rbx
0x18000e4de  mov     [rsp+8D0h+lpOutBuffer], r15
0x18000e4e3  mov     rdx, r12
0x18000e4e6  mov     rcx, r13
0x18000e4e9  call    McTemplateU0zjzz_EventWriteTransfer
0x18000e4ee  jmp     loc_18000E650
0x18000e4f3  mov     ecx, dword ptr [rsp+8D0h+OutBuffer+4]
0x18000e4f7  call    DwAddLuidIfNotPresent
0x18000e4fc  mov     edi, eax
0x18000e4fe  test    eax, eax
0x18000e500  jz      loc_18000E5E6
0x18000e506  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18000e50d  jge     short loc_18000E560
0x18000e50f  mov     r8d, eax
0x18000e512  mov     word ptr [rbp+7D0h+var_840], r15w
0x18000e517  lea     rdx, aAllocateinterf_0; "AllocateInterfaceLuidIndex: DwAddLuidIf"...
0x18000e51e  mov     word ptr [rsp+8D0h+var_868], r15w
0x18000e524  lea     rcx, [rbp+7D0h+var_840]
0x18000e528  call    FormatRRASErrorString
0x18000e52d  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18000e534  jge     short loc_18000E560
0x18000e536  test    rbx, rbx
0x18000e539  lea     rax, [rsp+8D0h+var_868]
0x18000e53e  mov     qword ptr [rsp+8D0h+nOutBufferSize], rax
0x18000e543  lea     r9, [rsp+8D0h+var_878]
0x18000e548  cmovnz  r9, rbx
0x18000e54c  mov     [rsp+8D0h+lpOutBuffer], r15
0x18000e551  lea     r8, [rbp+7D0h+var_840]
0x18000e555  mov     rdx, r12
0x18000e558  mov     rcx, r13
0x18000e55b  call    McTemplateU0zjzz_EventWriteTransfer
0x18000e560  mov     [rsp+8D0h+lpOverlapped], r15; lpOverlapped
0x18000e565  lea     rax, [rsp+8D0h+BytesReturned]
0x18000e56a  mov     [rsp+8D0h+lpBytesReturned], rax; lpBytesReturned
0x18000e56f  lea     r8, [rsp+8D0h+OutBuffer]; lpInBuffer
0x18000e574  mov     r9d, 8; nInBufferSize
0x18000e57a  lea     rax, [rsp+8D0h+OutBuffer]
0x18000e57f  mov     [rsp+8D0h+nOutBufferSize], r9d; nOutBufferSize
0x18000e584  mov     edx, 90018020h; dwIoControlCode
0x18000e589  mov     rcx, rsi; hDevice
0x18000e58c  mov     [rsp+8D0h+lpOutBuffer], rax; lpOutBuffer
0x18000e591  call    cs:__imp_DeviceIoControl
0x18000e597  test    eax, eax
0x18000e599  jnz     loc_18000E650
0x18000e59f  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18000e5a6  jge     loc_18000E6AA
0x18000e5ac  mov     word ptr [rbp+7D0h+var_840], r15w
0x18000e5b1  mov     word ptr [rsp+8D0h+var_868], r15w
0x18000e5b7  call    cs:__imp_GetLastError
0x18000e5bd  mov     r8d, eax
0x18000e5c0  lea     rdx, aAllocateinterf; "AllocateInterfaceLuidIndex:  DeviceIoCo"...
0x18000e5c7  lea     rcx, [rbp+7D0h+var_840]
0x18000e5cb  call    FormatRRASErrorString
0x18000e5d0  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18000e5d7  jge     loc_18000E6AA
0x18000e5dd  lea     r8, [rbp+7D0h+var_840]
0x18000e5e1  jmp     loc_18000E4C8
0x18000e5e6  mov     r8d, dword ptr [rsp+8D0h+OutBuffer+4]
0x18000e5eb  mov     [r14], r8d
0x18000e5ee  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18000e5f5  jge     loc_18000E6AA
0x18000e5fb  mov     word ptr [rbp+7D0h+var_840], r15w
0x18000e600  lea     rdx, aAllocinterface_0; "AllocInterfaceLuidIndex: Allocated LUID"...
0x18000e607  mov     word ptr [rsp+8D0h+var_868], r15w
0x18000e60d  jmp     short loc_18000E5C7
0x18000e60f  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18000e616  jz      short loc_18000E64B
0x18000e618  test    rbx, rbx
0x18000e61b  mov     word ptr [rsp+8D0h+var_868], r15w
0x18000e621  lea     rax, [rsp+8D0h+var_868]
0x18000e626  mov     rdx, r12
0x18000e629  mov     qword ptr [rsp+8D0h+nOutBufferSize], rax
0x18000e62e  lea     r9, [rsp+8D0h+var_878]
0x18000e633  cmovnz  r9, rbx
0x18000e637  mov     [rsp+8D0h+lpOutBuffer], r15
0x18000e63c  lea     r8, aAllocinterface_1; "AllocInterfaceLuidIndex: WANARP device "...
0x18000e643  mov     rcx, r13
0x18000e646  call    McTemplateU0zjzz_EventWriteTransfer
0x18000e64b  mov     edi, 6
0x18000e650  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18000e657  jge     short loc_18000E6AA
0x18000e659  mov     r8d, edi
0x18000e65c  mov     word ptr [rbp+7D0h+var_840], r15w
0x18000e661  lea     rdx, aAllocinterface_3; "AllocInterfaceLuidIndex: Completes with"...
0x18000e668  mov     word ptr [rsp+8D0h+var_868], r15w
0x18000e66e  lea     rcx, [rbp+7D0h+var_840]
0x18000e672  call    FormatRRASErrorString
0x18000e677  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18000e67e  jge     short loc_18000E6AA
0x18000e680  test    rbx, rbx
0x18000e683  lea     rax, [rsp+8D0h+var_868]
0x18000e688  mov     qword ptr [rsp+8D0h+nOutBufferSize], rax
0x18000e68d  lea     r9, [rsp+8D0h+var_878]
0x18000e692  cmovnz  r9, rbx
0x18000e696  mov     [rsp+8D0h+lpOutBuffer], r15
0x18000e69b  lea     r8, [rbp+7D0h+var_840]
0x18000e69f  mov     rdx, r12
0x18000e6a2  mov     rcx, r13
0x18000e6a5  call    McTemplateU0zjzz_EventWriteTransfer
0x18000e6aa  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18000e6b1  jz      short loc_18000E6E6
0x18000e6b3  test    rbx, rbx
0x18000e6b6  mov     word ptr [rsp+8D0h+var_868], r15w
0x18000e6bc  lea     rax, [rsp+8D0h+var_868]
0x18000e6c1  mov     rdx, r12
0x18000e6c4  mov     qword ptr [rsp+8D0h+nOutBufferSize], rax
0x18000e6c9  lea     r9, [rsp+8D0h+var_878]
0x18000e6ce  cmovnz  r9, rbx
0x18000e6d2  mov     [rsp+8D0h+lpOutBuffer], r15
0x18000e6d7  lea     r8, aLeavingAllocin; "Leaving: AllocInterfaceLuidIndex"
0x18000e6de  mov     rcx, r13
0x18000e6e1  call    McTemplateU0zjzz_EventWriteTransfer
0x18000e6e6  mov     eax, edi
0x18000e6e8  mov     rcx, [rbp+7D0h+var_40]
0x18000e6ef  xor     rcx, rsp; StackCookie
0x18000e6f2  call    __security_check_cookie
0x18000e6f7  mov     rbx, [rsp+8D0h+arg_0]
0x18000e6ff  add     rsp, 8A0h
0x18000e706  pop     r15
0x18000e708  pop     r14
0x18000e70a  pop     r13
0x18000e70c  pop     r12
0x18000e70e  pop     rdi
0x18000e70f  pop     rsi
0x18000e710  pop     rbp
0x18000e711  retn
```
