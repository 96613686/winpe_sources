# DeleteInterfaceWithWanArp

- ea: `0x18000ef08`
- end: `0x18000f2a6`
- name: `DeleteInterfaceWithWanArp`
- size: `926`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180016734`

## callees

- `0x180001f30`
- `0x18000ef08`
- `0x18000f2ac`
- `0x180011790`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`
- `0x180059010`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x18000f03a`
- `KERNEL32!DeviceIoControl` at `0x18000f03a`
- `KERNEL32!GetLastError` at `0x18000f044`
- `KERNEL32!GetLastError` at `0x18000f044`

## string_xrefs

- `0x18000efaa`: `Entered: DeleteInterfaceWithWANARP`
- `0x18000f059`: `DeleteInterfaceWithWANARP: Error %d deleting %ws`
- `0x18000f153`: `DeleteInterfaceWithWanarp not deleting the interface LUID for If %ws [%d] as there is another transport active`
- `0x18000f247`: `Leaving: DeleteInterfaceWithWANARP`

## pseudocode

```c
__int64 __fastcall DeleteInterfaceWithWanArp(__int64 a1)
{
  unsigned int v1; // esi
  __int128 *v3; // r9
  HANDLE v4; // rcx
  DWORD LastError; // eax
  DWORD v6; // edi
  __int64 v7; // r9
  __int128 *v8; // r9
  _QWORD *v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  int v13; // edx
  __int64 v14; // rcx
  __int64 v15; // r9
  __int64 v16; // r8
  __int128 *v17; // r9
  __int64 *v18; // rdx
  unsigned int v19; // eax
  __int64 v20; // r8
  __int128 *v21; // r9
  int InBuffer; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v23; // [rsp+48h] [rbp-B8h] BYREF
  DWORD BytesReturned; // [rsp+50h] [rbp-B0h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v26; // [rsp+78h] [rbp-88h] BYREF
  int v27; // [rsp+88h] [rbp-78h] BYREF
  __int128 v28; // [rsp+8Ch] [rbp-74h]
  __int128 v29; // [rsp+9Ch] [rbp-64h]
  int v30; // [rsp+ACh] [rbp-54h]
  int v31; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v32[2044]; // [rsp+B4h] [rbp-4Ch] BYREF

  v1 = *(_DWORD *)(a1 + 516);
  BytesReturned = 0;
  InBuffer = 0;
  v31 = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  memset_0(v32, 0, sizeof(v32));
  v27 = 0;
  v30 = 0;
  LOBYTE(v23) = Microsoft_Windows_RRASEnableBits & 0x80;
  v28 = 0;
  v29 = 0;
  v26 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    v3 = &v26;
    LOWORD(v27) = 0;
    if ( a1 != -688 )
      LODWORD(v3) = a1 + 688;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Entered: DeleteInterfaceWithWANARP",
      (_DWORD)v3,
      *(_QWORD *)(a1 + 72),
      (__int64)&v27);
  }
  v4 = (HANDLE)g_hWanarpWriteV6;
  InBuffer = *(_DWORD *)(a1 + 88);
  if ( v1 )
    v4 = g_hWanarpWrite;
  memset(&Overlapped, 0, sizeof(Overlapped));
  if ( !DeviceIoControl(v4, 0x90018008, &InBuffer, 4u, 0, 0, &BytesReturned, &Overlapped) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v7 = *(_QWORD *)(a1 + 72);
      LOWORD(v31) = 0;
      LOWORD(v27) = 0;
      FormatRRASErrorString(&v31, L"DeleteInterfaceWithWANARP: Error %d deleting %ws", LastError, v7);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v8 = &v26;
        if ( a1 != -688 )
          LODWORD(v8) = a1 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v31,
          (_DWORD)v8,
          *(_QWORD *)(a1 + 72),
          (__int64)&v27);
      }
    }
    return v6;
  }
  if ( *(_DWORD *)(a1 + 144) != 4 )
    goto LABEL_19;
  v10 = (_QWORD *)(a1 + 688);
  if ( a1 != -688 )
  {
    v11 = *v10 - *(_QWORD *)&GUID_NULL.Data1;
    if ( *v10 == *(_QWORD *)&GUID_NULL.Data1 )
      v11 = *(_QWORD *)(a1 + 696) - *(_QWORD *)GUID_NULL.Data4;
    if ( v11 )
    {
LABEL_19:
      v12 = *(_QWORD *)(a1 + 72);
      v13 = -(*(_DWORD *)(a1 + 516) != 0);
      v23 = 0;
      if ( (unsigned int)((__int64 (__fastcall *)(__int64, _QWORD, __int64 *))GetInterfaceHandle)(
                           v12,
                           (v13 & 0x36u) + 33,
                           &v23)
        || (v14 = v23, (unsigned __int64)(v23 - 1) > 0xFFFFFFFFFFFFFFFDuLL)
        || !InterfaceLookupByICBSeqNumber(v23) )
      {
        v19 = FreeInterfaceLuidIndex(v14, v1, a1 + 688, (*(_QWORD *)(a1 + 160) >> 24) & 0xFFFFFFLL);
        if ( !v19 )
          goto LABEL_33;
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
          goto LABEL_33;
        v20 = *(_QWORD *)(a1 + 160) >> 24;
        LOWORD(v31) = 0;
        LOWORD(v27) = 0;
        FormatRRASErrorString(&v31, L"RasFreeInterfaceLuidIndex: %x fails with error %d", v20 & 0xFFFFFF, v19);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
          goto LABEL_33;
        v17 = &v26;
        v18 = RasRtrMgrParamTraceError;
        if ( a1 != -688 )
          LODWORD(v17) = a1 + 688;
      }
      else
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
          goto LABEL_33;
        v15 = *(unsigned int *)(a1 + 16);
        v16 = *(_QWORD *)(a1 + 72);
        LOWORD(v31) = 0;
        LOWORD(v27) = 0;
        FormatRRASErrorString(
          &v31,
          L"DeleteInterfaceWithWanarp not deleting the interface LUID for If %ws [%d] as there is another transport active",
          v16,
          v15);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
          goto LABEL_33;
        v17 = &v26;
        v18 = RasRtrmgrParamTraceInfo;
        if ( a1 != -688 )
          LODWORD(v17) = a1 + 688;
      }
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (_DWORD)v18,
        (unsigned int)&v31,
        (_DWORD)v17,
        *(_QWORD *)(a1 + 72),
        (__int64)&v27);
    }
  }
LABEL_33:
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    v21 = &v26;
    LOWORD(v27) = 0;
    if ( a1 != -688 )
      LODWORD(v21) = a1 + 688;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Leaving: DeleteInterfaceWithWANARP",
      (_DWORD)v21,
      *(_QWORD *)(a1 + 72),
      (__int64)&v27);
  }
  return 0;
}

```

## disassembly

```asm
0x18000ef08  mov     [rsp-8+arg_8], rbx
0x18000ef0d  mov     [rsp-8+arg_10], rsi
0x18000ef12  push    rbp
0x18000ef13  push    rdi
0x18000ef14  push    r12
0x18000ef16  lea     rbp, [rsp-7C0h]
0x18000ef1e  sub     rsp, 8C0h
0x18000ef25  mov     rax, cs:__security_cookie
0x18000ef2c  xor     rax, rsp
0x18000ef2f  mov     [rbp+7D0h+var_20], rax
0x18000ef36  mov     esi, [rcx+204h]
0x18000ef3c  xorps   xmm0, xmm0
0x18000ef3f  mov     rbx, rcx
0x18000ef42  mov     [rsp+8D0h+BytesReturned], 0
0x18000ef4a  xor     eax, eax
0x18000ef4c  mov     [rsp+8D0h+InBuffer], 0
0x18000ef54  lea     rcx, [rbp+7D0h+var_81C]; void *
0x18000ef58  mov     [rbp+7D0h+var_820], eax
0x18000ef5b  xor     edx, edx; Val
0x18000ef5d  mov     r8d, 7FCh; Size
0x18000ef63  movups  xmmword ptr [rsp+8D0h+Overlapped.Internal], xmm0
0x18000ef68  movups  xmmword ptr [rsp+8D0h+Overlapped.10h], xmm0
0x18000ef6d  call    memset_0
0x18000ef72  xor     eax, eax
0x18000ef74  lea     r12, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000ef7b  xorps   xmm0, xmm0
0x18000ef7e  mov     [rbp+7D0h+var_848], eax
0x18000ef81  mov     [rbp+7D0h+var_824], eax
0x18000ef84  mov     al, byte ptr cs:Microsoft_Windows_RRASEnableBits
0x18000ef8a  and     al, 80h
0x18000ef8c  mov     byte ptr [rsp+8D0h+var_888], al
0x18000ef90  movups  [rbp+7D0h+var_844], xmm0
0x18000ef94  movups  [rbp+7D0h+var_834], xmm0
0x18000ef98  movups  [rsp+8D0h+var_858], xmm0
0x18000ef9d  jz      short loc_18000EFE0
0x18000ef9f  xor     eax, eax
0x18000efa1  lea     r9, [rsp+8D0h+var_858]
0x18000efa6  mov     word ptr [rbp+7D0h+var_848], ax
0x18000efaa  lea     r8, aEnteredDeletei_0; "Entered: DeleteInterfaceWithWANARP"
0x18000efb1  lea     rax, [rbx+2B0h]
0x18000efb8  mov     rcx, r12
0x18000efbb  test    rax, rax
0x18000efbe  lea     rdx, RasRtrmgrParamTraceInfo
0x18000efc5  cmovnz  r9, rax
0x18000efc9  lea     rax, [rbp+7D0h+var_848]
0x18000efcd  mov     qword ptr [rsp+8D0h+nOutBufferSize], rax
0x18000efd2  mov     rax, [rbx+48h]
0x18000efd6  mov     [rsp+8D0h+lpOutBuffer], rax
0x18000efdb  call    McTemplateU0zjzz_EventWriteTransfer
0x18000efe0  mov     eax, [rbx+58h]
0x18000efe3  lea     r8, [rsp+8D0h+InBuffer]; lpInBuffer
0x18000efe8  mov     rcx, cs:g_hWanarpWriteV6
0x18000efef  xorps   xmm0, xmm0
0x18000eff2  mov     [rsp+8D0h+InBuffer], eax
0x18000eff6  test    esi, esi
0x18000eff8  lea     rax, [rsp+8D0h+Overlapped]
0x18000effd  mov     r9d, 4; nInBufferSize
0x18000f003  cmovnz  rcx, cs:g_hWanarpWrite; hDevice
0x18000f00b  mov     edx, 90018008h; dwIoControlCode
0x18000f010  mov     [rsp+8D0h+lpOverlapped], rax; lpOverlapped
0x18000f015  lea     rax, [rsp+8D0h+BytesReturned]
0x18000f01a  mov     [rsp+8D0h+lpBytesReturned], rax; lpBytesReturned
0x18000f01f  mov     [rsp+8D0h+nOutBufferSize], 0; nOutBufferSize
0x18000f027  mov     [rsp+8D0h+lpOutBuffer], 0; lpOutBuffer
0x18000f030  movups  xmmword ptr [rsp+8D0h+Overlapped.Internal], xmm0
0x18000f035  movups  xmmword ptr [rsp+8D0h+Overlapped.10h], xmm0
0x18000f03a  call    cs:__imp_DeviceIoControl
0x18000f040  test    eax, eax
0x18000f042  jnz     short loc_18000F0BE
0x18000f044  call    cs:__imp_GetLastError
0x18000f04a  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18000f051  mov     edi, eax
0x18000f053  jz      short loc_18000F0B7
0x18000f055  mov     r9, [rbx+48h]
0x18000f059  lea     rdx, aDeleteinterfac_4; "DeleteInterfaceWithWANARP: Error %d del"...
0x18000f060  xor     ecx, ecx
0x18000f062  mov     r8d, eax
0x18000f065  mov     word ptr [rbp+7D0h+var_820], cx
0x18000f069  mov     word ptr [rbp+7D0h+var_848], cx
0x18000f06d  lea     rcx, [rbp+7D0h+var_820]
0x18000f071  call    FormatRRASErrorString
0x18000f076  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18000f07d  jz      short loc_18000F0B7
0x18000f07f  lea     rax, [rbx+2B0h]
0x18000f086  mov     rcx, r12
0x18000f089  test    rax, rax
0x18000f08c  lea     r9, [rsp+8D0h+var_858]
0x18000f091  lea     r8, [rbp+7D0h+var_820]
0x18000f095  cmovnz  r9, rax
0x18000f099  lea     rdx, RasRtrMgrParamTraceError
0x18000f0a0  lea     rax, [rbp+7D0h+var_848]
0x18000f0a4  mov     qword ptr [rsp+8D0h+nOutBufferSize], rax
0x18000f0a9  mov     rax, [rbx+48h]
0x18000f0ad  mov     [rsp+8D0h+lpOutBuffer], rax
0x18000f0b2  call    McTemplateU0zjzz_EventWriteTransfer
0x18000f0b7  mov     eax, edi
0x18000f0b9  jmp     loc_18000F27F
0x18000f0be  cmp     dword ptr [rbx+90h], 4
0x18000f0c5  jnz     short loc_18000F0F7
0x18000f0c7  lea     rcx, [rbx+2B0h]
0x18000f0ce  test    rcx, rcx
0x18000f0d1  jz      loc_18000F233
0x18000f0d7  mov     rax, [rcx]
0x18000f0da  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18000f0e1  jnz     short loc_18000F0EE
0x18000f0e3  mov     rax, [rcx+8]
0x18000f0e7  sub     rax, qword ptr cs:GUID_NULL.Data4
0x18000f0ee  test    rax, rax
0x18000f0f1  jz      loc_18000F233
0x18000f0f7  mov     eax, [rbx+204h]
0x18000f0fd  lea     r8, [rsp+8D0h+var_888]
0x18000f102  mov     rcx, [rbx+48h]
0x18000f106  neg     eax
0x18000f108  mov     rax, cs:GetInterfaceHandle
0x18000f10f  sbb     edx, edx
0x18000f111  mov     [rsp+8D0h+var_888], 0
0x18000f11a  and     edx, 36h
0x18000f11d  add     edx, 21h ; '!'
0x18000f120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f125  test    eax, eax
0x18000f127  jnz     short loc_18000F19A
0x18000f129  mov     rcx, [rsp+8D0h+var_888]
0x18000f12e  lea     rax, [rcx-1]
0x18000f132  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000f136  ja      short loc_18000F19A
0x18000f138  call    InterfaceLookupByICBSeqNumber
0x18000f13d  test    rax, rax
0x18000f140  jz      short loc_18000F19A
0x18000f142  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18000f149  jge     loc_18000F233
0x18000f14f  mov     r9d, [rbx+10h]
0x18000f153  lea     rdx, aDeleteinterfac; "DeleteInterfaceWithWanarp not deleting "...
0x18000f15a  mov     r8, [rbx+48h]
0x18000f15e  lea     rcx, [rbp+7D0h+var_820]
0x18000f162  xor     eax, eax
0x18000f164  mov     word ptr [rbp+7D0h+var_820], ax
0x18000f168  mov     word ptr [rbp+7D0h+var_848], ax
0x18000f16c  call    FormatRRASErrorString
0x18000f171  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18000f178  jge     loc_18000F233
0x18000f17e  lea     rax, [rbx+2B0h]
0x18000f185  test    rax, rax
0x18000f188  lea     r9, [rsp+8D0h+var_858]
0x18000f18d  lea     rdx, RasRtrmgrParamTraceInfo
0x18000f194  cmovnz  r9, rax
0x18000f198  jmp     short loc_18000F215
0x18000f19a  mov     r9, [rbx+0A0h]
0x18000f1a1  lea     rdi, [rbx+2B0h]
0x18000f1a8  shr     r9, 18h
0x18000f1ac  mov     r8, rdi
0x18000f1af  and     r9d, 0FFFFFFh
0x18000f1b6  mov     edx, esi
0x18000f1b8  call    FreeInterfaceLuidIndex
0x18000f1bd  test    eax, eax
0x18000f1bf  jz      short loc_18000F233
0x18000f1c1  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18000f1c8  jz      short loc_18000F233
0x18000f1ca  mov     r8, [rbx+0A0h]
0x18000f1d1  lea     rdx, aRasfreeinterfa; "RasFreeInterfaceLuidIndex: %x fails wit"...
0x18000f1d8  xor     ecx, ecx
0x18000f1da  shr     r8, 18h
0x18000f1de  mov     word ptr [rbp+7D0h+var_820], cx
0x18000f1e2  and     r8d, 0FFFFFFh
0x18000f1e9  mov     word ptr [rbp+7D0h+var_848], cx
0x18000f1ed  mov     r9d, eax
0x18000f1f0  lea     rcx, [rbp+7D0h+var_820]
0x18000f1f4  call    FormatRRASErrorString
0x18000f1f9  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18000f200  jz      short loc_18000F233
0x18000f202  test    rdi, rdi
0x18000f205  lea     r9, [rsp+8D0h+var_858]
0x18000f20a  lea     rdx, RasRtrMgrParamTraceError
0x18000f211  cmovnz  r9, rdi
0x18000f215  lea     rax, [rbp+7D0h+var_848]
0x18000f219  mov     rcx, r12
0x18000f21c  mov     qword ptr [rsp+8D0h+nOutBufferSize], rax
0x18000f221  lea     r8, [rbp+7D0h+var_820]
0x18000f225  mov     rax, [rbx+48h]
0x18000f229  mov     [rsp+8D0h+lpOutBuffer], rax
0x18000f22e  call    McTemplateU0zjzz_EventWriteTransfer
0x18000f233  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18000f23a  jz      short loc_18000F27D
0x18000f23c  xor     eax, eax
0x18000f23e  lea     r9, [rsp+8D0h+var_858]
0x18000f243  mov     word ptr [rbp+7D0h+var_848], ax
0x18000f247  lea     r8, aLeavingDeletei; "Leaving: DeleteInterfaceWithWANARP"
0x18000f24e  lea     rax, [rbx+2B0h]
0x18000f255  mov     rcx, r12
0x18000f258  test    rax, rax
0x18000f25b  lea     rdx, RasRtrmgrParamTraceInfo
0x18000f262  cmovnz  r9, rax
0x18000f266  lea     rax, [rbp+7D0h+var_848]
0x18000f26a  mov     qword ptr [rsp+8D0h+nOutBufferSize], rax
0x18000f26f  mov     rax, [rbx+48h]
0x18000f273  mov     [rsp+8D0h+lpOutBuffer], rax
0x18000f278  call    McTemplateU0zjzz_EventWriteTransfer
0x18000f27d  xor     eax, eax
0x18000f27f  mov     rcx, [rbp+7D0h+var_20]
0x18000f286  xor     rcx, rsp; StackCookie
0x18000f289  call    __security_check_cookie
0x18000f28e  lea     r11, [rsp+8D0h+var_10]
0x18000f296  mov     rbx, [r11+28h]
0x18000f29a  mov     rsi, [r11+30h]
0x18000f29e  mov     rsp, r11
0x18000f2a1  pop     r12
0x18000f2a3  pop     rdi
0x18000f2a4  pop     rbp
0x18000f2a5  retn
```
