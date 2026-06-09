# HandleConnectionRequest

- ea: `0x18000fe0c`
- end: `0x18001024f`
- name: `HandleConnectionRequest`
- size: `1091`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010260`

## callees

- `0x180001f30`
- `0x18000fe0c`
- `0x180011790`
- `0x1800118a4`
- `0x180011b38`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`
- `0x180059010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18001004b`
- `ntdll!RtlAcquireResourceExclusive` at `0x18001004b`
- `ntdll!RtlReleaseResource` at `0x180010028`
- `ntdll!RtlReleaseResource` at `0x180010028`

## string_xrefs

- `0x18000ff07`: `HandleConnectionRequest: Connection request for %ws but %ws is already UP`
- `0x18001007f`: `HandleConnectionRequest: Conn attempt for %ws pending`
- `0x1800100f7`: `HandleConnectionRequest: Interface %ws has already been marked as unreachable.`

## pseudocode

```c
__int64 __fastcall HandleConnectionRequest(__int64 a1, __int64 a2)
{
  char v4; // al
  __int64 v5; // r9
  __int64 v6; // r8
  __int128 *v7; // r9
  __int64 v8; // r8
  __int128 *v9; // r9
  int v10; // r14d
  __int64 result; // rax
  __int64 v12; // r8
  __int128 *v13; // r9
  __int64 v14; // rdi
  unsigned int v15; // esi
  unsigned int v16; // ebx
  int v17; // edi
  __int128 *v18; // r9
  __int64 v19; // r8
  __int128 *v20; // r9
  __int128 *v21; // r9
  __int128 v22; // [rsp+30h] [rbp-878h] BYREF
  int v23; // [rsp+40h] [rbp-868h] BYREF
  __int128 v24; // [rsp+44h] [rbp-864h]
  __int128 v25; // [rsp+54h] [rbp-854h]
  int v26; // [rsp+64h] [rbp-844h]
  int v27; // [rsp+70h] [rbp-838h] BYREF
  _BYTE v28[2044]; // [rsp+74h] [rbp-834h] BYREF

  v27 = 0;
  memset_0(v28, 0, sizeof(v28));
  v23 = 0;
  v26 = 0;
  v4 = Microsoft_Windows_RRASEnableBits;
  v24 = 0;
  v25 = 0;
  v22 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    v5 = *(unsigned int *)(a1 + 88);
    v6 = *(_QWORD *)(a1 + 72);
    LOWORD(v27) = 0;
    LOWORD(v23) = 0;
    FormatRRASErrorString(&v27, L"HandleConnectionRequest: Connection request for %ws, %d", v6, v5);
    v4 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v7 = &v22;
      if ( a1 != -688 )
        LODWORD(v7) = a1 + 688;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v27,
        (_DWORD)v7,
        *(_QWORD *)(a1 + 72),
        (__int64)&v23);
      v4 = Microsoft_Windows_RRASEnableBits;
    }
  }
  if ( *(_DWORD *)(a1 + 168) == 4 )
  {
    if ( v4 < 0 )
    {
      v8 = *(_QWORD *)(a1 + 72);
      LOWORD(v27) = 0;
      LOWORD(v23) = 0;
      FormatRRASErrorString(&v27, L"HandleConnectionRequest: Connection request for %ws but %ws is already UP", v8, v8);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v9 = &v22;
        if ( a1 != -688 )
          LODWORD(v9) = a1 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v27,
          (_DWORD)v9,
          *(_QWORD *)(a1 + 72),
          (__int64)&v23);
      }
    }
LABEL_39:
    result = NotifyWanarpOfFailure(a1);
    if ( (_DWORD)result != 259 )
    {
      if ( (_DWORD)result )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          LOWORD(v27) = 0;
          LOWORD(v23) = 0;
          result = FormatRRASErrorString(
                     &v27,
                     L"HandleConnectionRequest: %X for connection failed for %ws",
                     (unsigned int)result,
                     *(_QWORD *)(a1 + 72));
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          {
            v21 = &v22;
            if ( a1 != -688 )
              LODWORD(v21) = a1 + 688;
            return McTemplateU0zjzz_EventWriteTransfer(
                     (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                     (unsigned int)RasRtrmgrParamTraceInfo,
                     (unsigned int)&v27,
                     (_DWORD)v21,
                     *(_QWORD *)(a1 + 72),
                     (__int64)&v23);
          }
        }
      }
    }
    return result;
  }
  v10 = 0;
  result = ProcessPacketFromWanArp(a1, a2);
  if ( (_DWORD)result )
  {
LABEL_38:
    if ( v10 )
    {
      *(_DWORD *)(a1 + 168) = 3;
      return result;
    }
    goto LABEL_39;
  }
  if ( *(_DWORD *)(a1 + 172) == 2 || *(_DWORD *)(a1 + 168) == 1 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_38;
    v19 = *(_QWORD *)(a1 + 72);
    LOWORD(v27) = 0;
    LOWORD(v23) = 0;
    result = FormatRRASErrorString(
               &v27,
               L"HandleConnectionRequest: %ws has admin state %d and operational state %d. Failing connection request",
               v19);
    goto LABEL_34;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    v12 = *(_QWORD *)(a1 + 72);
    LOWORD(v27) = 0;
    LOWORD(v23) = 0;
    FormatRRASErrorString(&v27, L"Calling DIM to connect %ws", v12);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v13 = &v22;
      if ( a1 != -688 )
        LODWORD(v13) = a1 + 688;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v27,
        (_DWORD)v13,
        *(_QWORD *)(a1 + 72),
        (__int64)&v23);
    }
  }
  v14 = *(_QWORD *)(a1 + 184);
  v15 = *(_DWORD *)(a1 + 88);
  v16 = *(_DWORD *)(a1 + 516) != 0 ? 0xFFFFFFCA : 0;
  RtlReleaseResource(&Resource);
  v17 = ((__int64 (__fastcall *)(__int64, _QWORD))ConnectInterface)(v14, v16 + 87);
  RtlAcquireResourceExclusive(&Resource, 1u);
  result = InterfaceLookupByICBSeqNumber(v15);
  a1 = result;
  if ( result )
  {
    if ( v17 )
    {
      if ( v17 != 600 )
        goto LABEL_38;
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v27) = 0;
        LOWORD(v23) = 0;
        result = FormatRRASErrorString(
                   &v27,
                   L"HandleConnectionRequest: Conn attempt for %ws pending",
                   *(_QWORD *)(result + 72));
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v18 = &v22;
          if ( a1 != -688 )
            LODWORD(v18) = a1 + 688;
          result = McTemplateU0zjzz_EventWriteTransfer(
                     (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                     (unsigned int)RasRtrmgrParamTraceInfo,
                     (unsigned int)&v27,
                     (_DWORD)v18,
                     *(_QWORD *)(a1 + 72),
                     (__int64)&v23);
        }
      }
    }
    if ( *(_DWORD *)(a1 + 168) != 1 )
    {
      v10 = 1;
      goto LABEL_38;
    }
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_38;
    LOWORD(v27) = 0;
    LOWORD(v23) = 0;
    result = FormatRRASErrorString(
               &v27,
               L"HandleConnectionRequest: Interface %ws has already been marked as unreachable.",
               *(_QWORD *)(a1 + 72));
LABEL_34:
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v20 = &v22;
      if ( a1 != -688 )
        LODWORD(v20) = a1 + 688;
      result = McTemplateU0zjzz_EventWriteTransfer(
                 (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                 (unsigned int)RasRtrmgrParamTraceInfo,
                 (unsigned int)&v27,
                 (_DWORD)v20,
                 *(_QWORD *)(a1 + 72),
                 (__int64)&v23);
    }
    goto LABEL_38;
  }
  return result;
}

```

## disassembly

```asm
0x18000fe0c  mov     [rsp+arg_10], rbx
0x18000fe11  push    rsi
0x18000fe12  push    rdi
0x18000fe13  push    r12
0x18000fe15  push    r13
0x18000fe17  push    r14
0x18000fe19  sub     rsp, 880h
0x18000fe20  mov     rax, cs:__security_cookie
0x18000fe27  xor     rax, rsp
0x18000fe2a  mov     [rsp+8A8h+var_38], rax
0x18000fe32  mov     rdi, rdx
0x18000fe35  mov     rbx, rcx
0x18000fe38  xor     eax, eax
0x18000fe3a  lea     rcx, [rsp+8A8h+var_834]; void *
0x18000fe3f  xor     edx, edx; Val
0x18000fe41  mov     [rsp+8A8h+var_838], eax
0x18000fe45  mov     r8d, 7FCh; Size
0x18000fe4b  call    memset_0
0x18000fe50  xor     eax, eax
0x18000fe52  lea     r12, RasRtrmgrParamTraceInfo
0x18000fe59  xorps   xmm0, xmm0
0x18000fe5c  mov     [rsp+8A8h+var_868], eax
0x18000fe60  mov     [rsp+8A8h+var_844], eax
0x18000fe64  lea     r13, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000fe6b  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18000fe72  movups  [rsp+8A8h+var_864], xmm0
0x18000fe77  movups  [rsp+8A8h+var_854], xmm0
0x18000fe7c  movups  [rsp+8A8h+var_878], xmm0
0x18000fe81  test    al, al
0x18000fe83  jns     short loc_18000FEF2
0x18000fe85  mov     r9d, [rbx+58h]
0x18000fe89  lea     rdx, aHandleconnecti_4; "HandleConnectionRequest: Connection req"...
0x18000fe90  mov     r8, [rbx+48h]
0x18000fe94  lea     rcx, [rsp+8A8h+var_838]
0x18000fe99  xor     eax, eax
0x18000fe9b  mov     word ptr [rsp+8A8h+var_838], ax
0x18000fea0  mov     word ptr [rsp+8A8h+var_868], ax
0x18000fea5  call    FormatRRASErrorString
0x18000feaa  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18000feb1  test    al, al
0x18000feb3  jns     short loc_18000FEF2
0x18000feb5  lea     rax, [rbx+2B0h]
0x18000febc  mov     rdx, r12
0x18000febf  test    rax, rax
0x18000fec2  lea     r9, [rsp+8A8h+var_878]
0x18000fec7  lea     r8, [rsp+8A8h+var_838]
0x18000fecc  mov     rcx, r13
0x18000fecf  cmovnz  r9, rax
0x18000fed3  lea     rax, [rsp+8A8h+var_868]
0x18000fed8  mov     [rsp+8A8h+var_880], rax
0x18000fedd  mov     rax, [rbx+48h]
0x18000fee1  mov     [rsp+8A8h+var_888], rax
0x18000fee6  call    McTemplateU0zjzz_EventWriteTransfer
0x18000feeb  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18000fef2  cmp     dword ptr [rbx+0A8h], 4
0x18000fef9  jnz     short loc_18000FF6F
0x18000fefb  test    al, al
0x18000fefd  jns     loc_18001019C
0x18000ff03  mov     r8, [rbx+48h]
0x18000ff07  lea     rdx, aHandleconnecti_0; "HandleConnectionRequest: Connection req"...
0x18000ff0e  xor     eax, eax
0x18000ff10  lea     rcx, [rsp+8A8h+var_838]
0x18000ff15  mov     r9, r8
0x18000ff18  mov     word ptr [rsp+8A8h+var_838], ax
0x18000ff1d  mov     word ptr [rsp+8A8h+var_868], ax
0x18000ff22  call    FormatRRASErrorString
0x18000ff27  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18000ff2e  jge     loc_18001019C
0x18000ff34  lea     rax, [rbx+2B0h]
0x18000ff3b  mov     rdx, r12
0x18000ff3e  test    rax, rax
0x18000ff41  lea     r9, [rsp+8A8h+var_878]
0x18000ff46  lea     r8, [rsp+8A8h+var_838]
0x18000ff4b  mov     rcx, r13
0x18000ff4e  cmovnz  r9, rax
0x18000ff52  lea     rax, [rsp+8A8h+var_868]
0x18000ff57  mov     [rsp+8A8h+var_880], rax
0x18000ff5c  mov     rax, [rbx+48h]
0x18000ff60  mov     [rsp+8A8h+var_888], rax
0x18000ff65  call    McTemplateU0zjzz_EventWriteTransfer
0x18000ff6a  jmp     loc_18001019C
0x18000ff6f  mov     rdx, rdi
0x18000ff72  mov     rcx, rbx
0x18000ff75  xor     r14d, r14d
0x18000ff78  call    ProcessPacketFromWanArp
0x18000ff7d  test    eax, eax
0x18000ff7f  jnz     loc_180010193
0x18000ff85  mov     r9d, [rbx+0ACh]
0x18000ff8c  cmp     r9d, 2
0x18000ff90  jz      loc_180010120
0x18000ff96  cmp     dword ptr [rbx+0A8h], 1
0x18000ff9d  jz      loc_180010120
0x18000ffa3  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18000ffaa  jge     short loc_18001000A
0x18000ffac  mov     r8, [rbx+48h]
0x18000ffb0  lea     rdx, aCallingDimToCo; "Calling DIM to connect %ws"
0x18000ffb7  lea     rcx, [rsp+8A8h+var_838]
0x18000ffbc  mov     word ptr [rsp+8A8h+var_838], ax
0x18000ffc1  mov     word ptr [rsp+8A8h+var_868], ax
0x18000ffc6  call    FormatRRASErrorString
0x18000ffcb  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18000ffd2  jge     short loc_18001000A
0x18000ffd4  lea     rax, [rbx+2B0h]
0x18000ffdb  mov     rdx, r12
0x18000ffde  test    rax, rax
0x18000ffe1  lea     r9, [rsp+8A8h+var_878]
0x18000ffe6  lea     r8, [rsp+8A8h+var_838]
0x18000ffeb  mov     rcx, r13
0x18000ffee  cmovnz  r9, rax
0x18000fff2  lea     rax, [rsp+8A8h+var_868]
0x18000fff7  mov     [rsp+8A8h+var_880], rax
0x18000fffc  mov     rax, [rbx+48h]
0x180010000  mov     [rsp+8A8h+var_888], rax
0x180010005  call    McTemplateU0zjzz_EventWriteTransfer
0x18001000a  mov     eax, [rbx+204h]
0x180010010  lea     rcx, Resource; Resource
0x180010017  mov     rdi, [rbx+0B8h]
0x18001001e  neg     eax
0x180010020  mov     esi, [rbx+58h]
0x180010023  sbb     ebx, ebx
0x180010025  and     ebx, 0FFFFFFCAh
0x180010028  call    cs:__imp_RtlReleaseResource
0x18001002e  mov     rax, cs:ConnectInterface
0x180010035  lea     edx, [rbx+57h]
0x180010038  mov     rcx, rdi
0x18001003b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010040  mov     dl, 1; Wait
0x180010042  lea     rcx, Resource; Resource
0x180010049  mov     edi, eax
0x18001004b  call    cs:__imp_RtlAcquireResourceExclusive
0x180010051  mov     ecx, esi
0x180010053  call    InterfaceLookupByICBSeqNumber
0x180010058  mov     rbx, rax
0x18001005b  test    rax, rax
0x18001005e  jz      loc_180010227
0x180010064  test    edi, edi
0x180010066  jz      short loc_1800100DF
0x180010068  cmp     edi, 258h
0x18001006e  jnz     loc_180010193
0x180010074  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18001007b  jge     short loc_1800100DF
0x18001007d  xor     ecx, ecx
0x18001007f  lea     rdx, aHandleconnecti_3; "HandleConnectionRequest: Conn attempt f"...
0x180010086  mov     word ptr [rsp+8A8h+var_838], cx
0x18001008b  xor     eax, eax
0x18001008d  mov     word ptr [rsp+8A8h+var_868], ax
0x180010092  lea     rcx, [rsp+8A8h+var_838]
0x180010097  mov     r8, [rbx+48h]
0x18001009b  call    FormatRRASErrorString
0x1800100a0  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x1800100a7  jge     short loc_1800100DF
0x1800100a9  lea     rax, [rbx+2B0h]
0x1800100b0  mov     rdx, r12
0x1800100b3  test    rax, rax
0x1800100b6  lea     r9, [rsp+8A8h+var_878]
0x1800100bb  lea     r8, [rsp+8A8h+var_838]
0x1800100c0  mov     rcx, r13
0x1800100c3  cmovnz  r9, rax
0x1800100c7  lea     rax, [rsp+8A8h+var_868]
0x1800100cc  mov     [rsp+8A8h+var_880], rax
0x1800100d1  mov     rax, [rbx+48h]
0x1800100d5  mov     [rsp+8A8h+var_888], rax
0x1800100da  call    McTemplateU0zjzz_EventWriteTransfer
0x1800100df  cmp     dword ptr [rbx+0A8h], 1
0x1800100e6  jnz     short loc_180010118
0x1800100e8  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x1800100ef  jge     loc_180010193
0x1800100f5  xor     eax, eax
0x1800100f7  lea     rdx, aHandleconnecti_1; "HandleConnectionRequest: Interface %ws "...
0x1800100fe  mov     word ptr [rsp+8A8h+var_838], ax
0x180010103  lea     rcx, [rsp+8A8h+var_838]
0x180010108  mov     word ptr [rsp+8A8h+var_868], ax
0x18001010d  mov     r8, [rbx+48h]
0x180010111  call    FormatRRASErrorString
0x180010116  jmp     short loc_180010154
0x180010118  mov     r14d, 1
0x18001011e  jmp     short loc_180010193
0x180010120  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180010127  jge     short loc_180010193
0x180010129  mov     r8, [rbx+48h]
0x18001012d  lea     rdx, aHandleconnecti_2; "HandleConnectionRequest: %ws has admin "...
0x180010134  xor     eax, eax
0x180010136  lea     rcx, [rsp+8A8h+var_838]
0x18001013b  mov     word ptr [rsp+8A8h+var_838], ax
0x180010140  mov     word ptr [rsp+8A8h+var_868], ax
0x180010145  mov     eax, [rbx+0A8h]
0x18001014b  mov     dword ptr [rsp+8A8h+var_888], eax
0x18001014f  call    FormatRRASErrorString
0x180010154  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18001015b  jge     short loc_180010193
0x18001015d  lea     rax, [rbx+2B0h]
0x180010164  mov     rdx, r12
0x180010167  test    rax, rax
0x18001016a  lea     r9, [rsp+8A8h+var_878]
0x18001016f  lea     r8, [rsp+8A8h+var_838]
0x180010174  mov     rcx, r13
0x180010177  cmovnz  r9, rax
0x18001017b  lea     rax, [rsp+8A8h+var_868]
0x180010180  mov     [rsp+8A8h+var_880], rax
0x180010185  mov     rax, [rbx+48h]
0x180010189  mov     [rsp+8A8h+var_888], rax
0x18001018e  call    McTemplateU0zjzz_EventWriteTransfer
0x180010193  test    r14d, r14d
0x180010196  jnz     loc_18001021D
0x18001019c  mov     rcx, rbx
0x18001019f  call    NotifyWanarpOfFailure
0x1800101a4  cmp     eax, 103h
0x1800101a9  jz      short loc_180010227
0x1800101ab  test    eax, eax
0x1800101ad  jz      short loc_180010227
0x1800101af  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800101b6  jge     short loc_180010227
0x1800101b8  xor     ecx, ecx
0x1800101ba  lea     rdx, aHandleconnecti_5; "HandleConnectionRequest: %X for connect"...
0x1800101c1  mov     word ptr [rsp+8A8h+var_838], cx
0x1800101c6  mov     r8d, eax
0x1800101c9  mov     word ptr [rsp+8A8h+var_868], cx
0x1800101ce  lea     rcx, [rsp+8A8h+var_838]
0x1800101d3  mov     r9, [rbx+48h]
0x1800101d7  call    FormatRRASErrorString
0x1800101dc  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800101e3  jge     short loc_180010227
0x1800101e5  lea     rax, [rbx+2B0h]
0x1800101ec  mov     rdx, r12
0x1800101ef  test    rax, rax
0x1800101f2  lea     r9, [rsp+8A8h+var_878]
0x1800101f7  lea     r8, [rsp+8A8h+var_838]
0x1800101fc  mov     rcx, r13
0x1800101ff  cmovnz  r9, rax
0x180010203  lea     rax, [rsp+8A8h+var_868]
0x180010208  mov     [rsp+8A8h+var_880], rax
0x18001020d  mov     rax, [rbx+48h]
0x180010211  mov     [rsp+8A8h+var_888], rax
0x180010216  call    McTemplateU0zjzz_EventWriteTransfer
0x18001021b  jmp     short loc_180010227
0x18001021d  mov     dword ptr [rbx+0A8h], 3
0x180010227  mov     rcx, [rsp+8A8h+var_38]
0x18001022f  xor     rcx, rsp; StackCookie
0x180010232  call    __security_check_cookie
0x180010237  mov     rbx, [rsp+8A8h+arg_10]
0x18001023f  add     rsp, 880h
0x180010246  pop     r14
0x180010248  pop     r13
0x18001024a  pop     r12
0x18001024c  pop     rdi
0x18001024d  pop     rsi
0x18001024e  retn
```
