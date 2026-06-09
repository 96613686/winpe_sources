# VmbusTlTransitionDisconnectState

- ea: `0x1400049a0`
- end: `0x140004de3`
- name: `VmbusTlTransitionDisconnectState`
- size: `1091`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1400042d0`
- `0x14000440c`
- `0x1400045c0`
- `0x14000483c`
- `0x140004898`
- `0x140006290`
- `0x14000ab50`
- `0x14000b220`

## callees

- `0x140001008`
- `0x140003ee8`
- `0x140004354`
- `0x140004898`
- `0x1400049a0`
- `0x140004e9c`
- `0x1400058d0`
- `0x14000975c`
- `0x140009834`
- `0x14000a048`
- `0x14000bfa0`

## string_xrefs

- `0x140004c2f`: `VmbusTlShutdownStreamComplete`

## pseudocode

```c
int __fastcall VmbusTlTransitionDisconnectState(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  int result; // eax
  int v7; // edi
  int v8; // edi
  int v9; // edi
  int v10; // edi
  int v11; // edi
  int v12; // edi
  int v13; // eax
  int v14; // eax
  bool v15; // cf
  __int64 v16; // rdx
  signed __int64 v17; // rax
  bool v18; // cc
  signed __int64 v19; // rax
  signed __int32 v20; // ett
  __int64 v21; // rdx
  int v22; // [rsp+30h] [rbp-79h] BYREF
  int v23; // [rsp+34h] [rbp-75h] BYREF
  int v24; // [rsp+38h] [rbp-71h] BYREF
  __int64 v25; // [rsp+40h] [rbp-69h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v26; // [rsp+50h] [rbp-59h] BYREF
  __int64 *v27; // [rsp+70h] [rbp-39h]
  __int64 v28; // [rsp+78h] [rbp-31h]
  int *v29; // [rsp+80h] [rbp-29h]
  __int64 v30; // [rsp+88h] [rbp-21h]
  int *v31; // [rsp+90h] [rbp-19h]
  __int64 v32; // [rsp+98h] [rbp-11h]
  int *v33; // [rsp+A0h] [rbp-9h]
  __int64 v34; // [rsp+A8h] [rbp-1h]
  __int64 v35; // [rsp+B0h] [rbp+7h]
  __int64 v36; // [rsp+B8h] [rbp+Fh]
  __int64 v37; // [rsp+C0h] [rbp+17h]
  __int64 v38; // [rsp+C8h] [rbp+1Fh]

  while ( 1 )
  {
    result = dword_140013058;
    if ( (unsigned int)dword_140013058 > 5 )
    {
      v25 = a1;
      v27 = &v25;
      v22 = *(_DWORD *)(a1 + 520);
      v29 = &v22;
      v23 = *(_DWORD *)(a1 + 524);
      v31 = &v23;
      v33 = &v24;
      v35 = a1 + 140;
      v37 = a1 + 156;
      v28 = 8;
      v30 = 4;
      v32 = 4;
      v24 = a2;
      v34 = 4;
      v36 = 16;
      v38 = 16;
      result = tlgWriteTransfer_EtwWriteTransfer(
                 (__int64)&dword_140013058,
                 (unsigned __int8 *)&byte_140011403,
                 a3,
                 a4,
                 8u,
                 &v26);
    }
    v7 = a2 - 1;
    if ( !v7 )
      break;
    v8 = v7 - 1;
    if ( v8 )
    {
      v9 = v8 - 1;
      if ( v9 )
      {
        v10 = v9 - 1;
        if ( !v10 )
        {
          if ( *(_DWORD *)(a1 + 520) != 3 )
          {
            result = dword_140013058;
            if ( (unsigned int)dword_140013058 <= 2 )
              return result;
            v16 = 141;
            return HvsocketTraceEndpointError("VmbusTlTransitionDisconnectState", v16, 3221225860LL, a1);
          }
          *(_DWORD *)(a1 + 520) = 4;
          goto LABEL_24;
        }
        v11 = v10 - 13;
        if ( !v11 )
        {
          if ( !*(_DWORD *)(a1 + 524) )
          {
            *(_DWORD *)(a1 + 524) = 17;
            result = VmbusTlAllocateAndQueueEndpointAction(a1, 5u, 0);
            if ( result < 0 )
            {
              if ( (unsigned int)dword_140013058 > 2 )
              {
                v21 = 153;
                goto LABEL_54;
              }
              return VmbusTlDisconnectAbort(a1);
            }
          }
          return result;
        }
        v12 = v11 - 1;
        if ( v12 )
        {
          if ( v12 != 1 )
            __fastfail(5u);
          if ( *(_DWORD *)(a1 + 524) != 18 )
          {
            result = dword_140013058;
            if ( (unsigned int)dword_140013058 <= 2 )
              return result;
            v16 = 180;
            return HvsocketTraceEndpointError("VmbusTlTransitionDisconnectState", v16, 3221225860LL, a1);
          }
          *(_DWORD *)(a1 + 524) = 19;
LABEL_24:
          result = *(_DWORD *)(a1 + 528) & 0x118;
          if ( result == 24 )
          {
            v15 = *(_BYTE *)(a1 + 532) != 0;
            *(_DWORD *)(a1 + 528) |= 0x100u;
            HvSocketCompleteDisconnectRequest(a1, v15 ? 0xC0000241 : 0, a1 + 544);
            HvSocketCompleteDisconnectRequest(a1, 0, a1 + 608);
            *(_DWORD *)(a1 + 528) |= 0x800u;
            if ( (*(_DWORD *)(a1 + 516) & 0x40) != 0 && *(int *)(a1 + 952) >= 0 )
            {
              if ( (unsigned int)dword_140013058 > 5 )
                HvsocketTraceReferenceCount(
                  (unsigned int)"VmbusTlShutdownStreamComplete",
                  259,
                  a1,
                  *(_QWORD *)(a1 + 304),
                  (__int64)"Connection reference. (deref)");
              v17 = _InterlockedExchangeAdd64((volatile signed __int64 *)(a1 + 304), 0xFFFFFFFFFFFFFFFFuLL);
              v18 = v17 <= 1;
              v19 = v17 - 1;
              if ( v18 )
              {
                if ( v19 )
                  __fastfail(0xEu);
                if ( (unsigned int)dword_140013058 > 4 )
                  HvsocketTraceEndpointEvent("VmbusTlDereferenceEndpointInternal cleaning up the endpoint.", a1, 9);
                VmbusTlQueueEndpointAction(a1, a1 + 200, 9, 0);
              }
            }
            v20 = *(_DWORD *)(a1 + 1072) & 0x7FFFFFFF;
            result = _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 1072), (v20 + 1) | 0x80000000, v20);
            if ( v20 == result )
              return VmbusTlQueueEndpointAction(a1, a1 + 1016, 6, 0);
          }
          return result;
        }
        v13 = *(_DWORD *)(a1 + 524);
        if ( v13 != 17 && v13 != 255 )
        {
          result = dword_140013058;
          if ( (unsigned int)dword_140013058 <= 2 )
            return result;
          v16 = 168;
          return HvsocketTraceEndpointError("VmbusTlTransitionDisconnectState", v16, 3221225860LL, a1);
        }
        *(_DWORD *)(a1 + 528) |= 0x10u;
        *(_DWORD *)(a1 + 524) = 18;
        VmbusTlIndicateDisconnectEventToClient(a1);
        a2 = 19;
      }
      else
      {
        v14 = *(_DWORD *)(a1 + 520);
        if ( v14 != 2 && v14 != 255 )
        {
          result = dword_140013058;
          if ( (unsigned int)dword_140013058 <= 2 )
            return result;
          v16 = 129;
          return HvsocketTraceEndpointError("VmbusTlTransitionDisconnectState", v16, 3221225860LL, a1);
        }
        *(_DWORD *)(a1 + 528) |= 8u;
        v15 = *(_BYTE *)(a1 + 532) != 0;
        *(_DWORD *)(a1 + 520) = 3;
        HvSocketCompleteDisconnectRequest(a1, v15 ? 0xC0000241 : 0, a1 + 544);
        a2 = 4;
      }
    }
    else
    {
      if ( *(_DWORD *)(a1 + 520) != 1 )
        return result;
      result = *(_DWORD *)(a1 + 528);
      *(_DWORD *)(a1 + 520) = 2;
      if ( (result & 4) == 0 )
        return result;
      a2 = 3;
    }
  }
  if ( !*(_DWORD *)(a1 + 520) )
  {
    *(_DWORD *)(a1 + 520) = 1;
    result = VmbusTlAllocateAndQueueEndpointAction(a1, 4u, 0);
    if ( result < 0 )
    {
      if ( (unsigned int)dword_140013058 > 2 )
      {
        v21 = 106;
LABEL_54:
        HvsocketTraceEndpointError("VmbusTlTransitionDisconnectState", v21, (unsigned int)result, a1);
      }
      return VmbusTlDisconnectAbort(a1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400049a0  push    rbp
0x1400049a2  push    rbx
0x1400049a3  push    rdi
0x1400049a4  push    r15
0x1400049a6  lea     rbp, [rsp-3Fh]
0x1400049ab  sub     rsp, 0E8h
0x1400049b2  mov     rax, cs:__security_cookie
0x1400049b9  xor     rax, rsp
0x1400049bc  mov     [rbp+57h+var_30], rax
0x1400049c0  mov     edi, edx
0x1400049c2  mov     rbx, rcx
0x1400049c5  mov     r15d, 4
0x1400049cb  mov     eax, cs:dword_140013058
0x1400049d1  cmp     eax, 5
0x1400049d4  jbe     loc_140004A71
0x1400049da  lea     rax, [rbp+57h+var_C0]
0x1400049de  mov     [rbp+57h+var_C0], rbx
0x1400049e2  mov     [rbp+57h+var_90], rax
0x1400049e6  lea     rdx, byte_140011403; int
0x1400049ed  mov     eax, [rbx+208h]
0x1400049f3  lea     rcx, dword_140013058; int
0x1400049fa  mov     [rbp+57h+var_D0], eax
0x1400049fd  lea     rax, [rbp+57h+var_D0]
0x140004a01  mov     [rbp+57h+var_80], rax
0x140004a05  mov     eax, [rbx+20Ch]
0x140004a0b  mov     [rbp+57h+var_CC], eax
0x140004a0e  lea     rax, [rbp+57h+var_CC]
0x140004a12  mov     [rbp+57h+var_70], rax
0x140004a16  lea     rax, [rbp+57h+var_C8]
0x140004a1a  mov     [rbp+57h+var_60], rax
0x140004a1e  lea     rax, [rbx+8Ch]
0x140004a25  mov     [rbp+57h+var_50], rax
0x140004a29  lea     rax, [rbx+9Ch]
0x140004a30  mov     [rbp+57h+var_40], rax
0x140004a34  lea     rax, [rbp+57h+var_B0]
0x140004a38  mov     [rsp+100h+var_D8], rax; __int64
0x140004a3d  mov     [rsp+100h+var_E0], 8; ULONG
0x140004a45  mov     [rbp+57h+var_88], 8
0x140004a4d  mov     [rbp+57h+var_78], r15
0x140004a51  mov     [rbp+57h+var_68], r15
0x140004a55  mov     [rbp+57h+var_C8], edi
0x140004a58  mov     [rbp+57h+var_58], r15
0x140004a5c  mov     [rbp+57h+var_48], 10h
0x140004a64  mov     [rbp+57h+var_38], 10h
0x140004a6c  call    _tlgWriteTransfer_EtwWriteTransfer
0x140004a71  sub     edi, 1
0x140004a74  jz      loc_140004D7A
0x140004a7a  sub     edi, 1
0x140004a7d  jz      loc_140004B2A
0x140004a83  sub     edi, 1
0x140004a86  jz      short loc_140004ADC
0x140004a88  sub     edi, 1
0x140004a8b  jz      loc_140004D2C
0x140004a91  sub     edi, 0Dh
0x140004a94  jz      loc_140004CE5
0x140004a9a  sub     edi, 1
0x140004a9d  jnz     loc_140004B73
0x140004aa3  mov     eax, [rbx+20Ch]
0x140004aa9  cmp     eax, 11h
0x140004aac  jz      short loc_140004AB9
0x140004aae  cmp     eax, 0FFh
0x140004ab3  jnz     loc_140004B5A
0x140004ab9  or      dword ptr [rbx+210h], 10h
0x140004ac0  mov     rcx, rbx
0x140004ac3  mov     dword ptr [rbx+20Ch], 12h
0x140004acd  call    VmbusTlIndicateDisconnectEventToClient
0x140004ad2  mov     edi, 13h
0x140004ad7  jmp     loc_1400049CB
0x140004adc  mov     eax, [rbx+208h]
0x140004ae2  cmp     eax, 2
0x140004ae5  jz      short loc_140004AF2
0x140004ae7  cmp     eax, 0FFh
0x140004aec  jnz     loc_140004D53
0x140004af2  or      dword ptr [rbx+210h], 8
0x140004af9  lea     r8, [rbx+220h]
0x140004b00  mov     al, [rbx+214h]
0x140004b06  mov     rcx, rbx
0x140004b09  neg     al
0x140004b0b  mov     dword ptr [rbx+208h], 3
0x140004b15  sbb     edx, edx
0x140004b17  and     edx, 0C0000241h
0x140004b1d  call    HvSocketCompleteDisconnectRequest
0x140004b22  mov     edi, r15d
0x140004b25  jmp     loc_1400049CB
0x140004b2a  cmp     dword ptr [rbx+208h], 1
0x140004b31  jnz     loc_140004DC9
0x140004b37  mov     eax, [rbx+210h]
0x140004b3d  mov     dword ptr [rbx+208h], 2
0x140004b47  test    r15b, al
0x140004b4a  jz      loc_140004DC9
0x140004b50  mov     edi, 3
0x140004b55  jmp     loc_1400049CB
0x140004b5a  mov     eax, cs:dword_140013058
0x140004b60  cmp     eax, 2
0x140004b63  jbe     loc_140004DC9
0x140004b69  mov     edx, 0A8h
0x140004b6e  jmp     loc_140004D63
0x140004b73  cmp     edi, 1
0x140004b76  jz      short loc_140004B7F
0x140004b78  mov     ecx, 5
0x140004b7d  int     29h; Win8: RtlFailFast(ecx)
0x140004b7f  cmp     dword ptr [rbx+20Ch], 12h
0x140004b86  jnz     loc_140004CCF
0x140004b8c  mov     dword ptr [rbx+20Ch], 13h
0x140004b96  mov     ecx, [rbx+210h]
0x140004b9c  mov     eax, ecx
0x140004b9e  and     eax, 118h
0x140004ba3  cmp     eax, 18h
0x140004ba6  jnz     loc_140004DC9
0x140004bac  mov     al, [rbx+214h]
0x140004bb2  lea     r8, [rbx+220h]
0x140004bb9  bts     ecx, 8
0x140004bbd  neg     al
0x140004bbf  mov     [rbx+210h], ecx
0x140004bc5  mov     rcx, rbx
0x140004bc8  sbb     edx, edx
0x140004bca  and     edx, 0C0000241h
0x140004bd0  call    HvSocketCompleteDisconnectRequest
0x140004bd5  lea     r8, [rbx+260h]
0x140004bdc  xor     edx, edx
0x140004bde  mov     rcx, rbx
0x140004be1  call    HvSocketCompleteDisconnectRequest
0x140004be6  bts     dword ptr [rbx+210h], 0Bh
0x140004bee  mov     eax, [rbx+204h]
0x140004bf4  test    al, 40h
0x140004bf6  jz      loc_140004C93
0x140004bfc  cmp     dword ptr [rbx+3B8h], 0
0x140004c03  jl      loc_140004C93
0x140004c09  mov     eax, cs:dword_140013058
0x140004c0f  cmp     eax, 5
0x140004c12  jbe     short loc_140004C3B
0x140004c14  mov     r9, [rbx+130h]
0x140004c1b  lea     rax, aConnectionRefe; "Connection reference. (deref)"
0x140004c22  mov     r8, rbx
0x140004c25  mov     qword ptr [rsp+100h+var_E0], rax
0x140004c2a  mov     edx, 103h
0x140004c2f  lea     rcx, aVmbustlshutdow; "VmbusTlShutdownStreamComplete"
0x140004c36  call    HvsocketTraceReferenceCount
0x140004c3b  or      rax, 0FFFFFFFFFFFFFFFFh
0x140004c3f  lock xadd [rbx+130h], rax
0x140004c48  sub     rax, 1
0x140004c4c  jg      short loc_140004C93
0x140004c4e  test    rax, rax
0x140004c51  jnz     short loc_140004C8C
0x140004c53  mov     eax, cs:dword_140013058
0x140004c59  mov     edi, 9
0x140004c5e  cmp     eax, r15d
0x140004c61  jbe     short loc_140004C75
0x140004c63  mov     r8d, edi
0x140004c66  lea     rcx, aVmbustlderefer; "VmbusTlDereferenceEndpointInternal clea"...
0x140004c6d  mov     rdx, rbx
0x140004c70  call    HvsocketTraceEndpointEvent
0x140004c75  lea     rdx, [rbx+0C8h]
0x140004c7c  xor     r9d, r9d
0x140004c7f  mov     r8d, edi
0x140004c82  mov     rcx, rbx
0x140004c85  call    VmbusTlQueueEndpointAction
0x140004c8a  jmp     short loc_140004C93
0x140004c8c  mov     ecx, 0Eh
0x140004c91  int     29h; Win8: RtlFailFast(ecx)
0x140004c93  mov     eax, [rbx+430h]
0x140004c99  btr     eax, 1Fh
0x140004c9d  lea     ecx, [rax+1]
0x140004ca0  or      ecx, 80000000h
0x140004ca6  lock cmpxchg [rbx+430h], ecx
0x140004cae  jnz     loc_140004DC9
0x140004cb4  xor     r9d, r9d
0x140004cb7  lea     rdx, [rbx+3F8h]
0x140004cbe  mov     rcx, rbx
0x140004cc1  lea     r8d, [r9+6]
0x140004cc5  call    VmbusTlQueueEndpointAction
0x140004cca  jmp     loc_140004DC9
0x140004ccf  mov     eax, cs:dword_140013058
0x140004cd5  cmp     eax, 2
0x140004cd8  jbe     loc_140004DC9
0x140004cde  mov     edx, 0B4h
0x140004ce3  jmp     short loc_140004D63
0x140004ce5  cmp     dword ptr [rbx+20Ch], 0
0x140004cec  jnz     loc_140004DC9
0x140004cf2  xor     r8d, r8d
0x140004cf5  mov     dword ptr [rbx+20Ch], 11h
0x140004cff  mov     rcx, rbx
0x140004d02  lea     edx, [r8+5]
0x140004d06  call    VmbusTlAllocateAndQueueEndpointAction
0x140004d0b  test    eax, eax
0x140004d0d  jns     loc_140004DC9
0x140004d13  mov     ecx, cs:dword_140013058
0x140004d19  cmp     ecx, 2
0x140004d1c  jbe     loc_140004DC1
0x140004d22  mov     edx, 99h
0x140004d27  jmp     loc_140004DAF
0x140004d2c  cmp     dword ptr [rbx+208h], 3
0x140004d33  jnz     short loc_140004D41
0x140004d35  mov     [rbx+208h], r15d
0x140004d3c  jmp     loc_140004B96
0x140004d41  mov     eax, cs:dword_140013058
0x140004d47  cmp     eax, 2
0x140004d4a  jbe     short loc_140004DC9
0x140004d4c  mov     edx, 8Dh
0x140004d51  jmp     short loc_140004D63
0x140004d53  mov     eax, cs:dword_140013058
0x140004d59  cmp     eax, 2
0x140004d5c  jbe     short loc_140004DC9
0x140004d5e  mov     edx, 81h
0x140004d63  mov     r9, rbx
0x140004d66  lea     rcx, aVmbustltransit; "VmbusTlTransitionDisconnectState"
0x140004d6d  mov     r8d, 0C0000184h
0x140004d73  call    HvsocketTraceEndpointError
0x140004d78  jmp     short loc_140004DC9
0x140004d7a  cmp     dword ptr [rbx+208h], 0
0x140004d81  jnz     short loc_140004DC9
0x140004d83  xor     r8d, r8d
0x140004d86  mov     dword ptr [rbx+208h], 1
0x140004d90  mov     edx, r15d
0x140004d93  mov     rcx, rbx
0x140004d96  call    VmbusTlAllocateAndQueueEndpointAction
0x140004d9b  test    eax, eax
0x140004d9d  jns     short loc_140004DC9
0x140004d9f  mov     ecx, cs:dword_140013058
0x140004da5  cmp     ecx, 2
0x140004da8  jbe     short loc_140004DC1
0x140004daa  mov     edx, 6Ah ; 'j'
0x140004daf  mov     r9, rbx
0x140004db2  lea     rcx, aVmbustltransit; "VmbusTlTransitionDisconnectState"
0x140004db9  mov     r8d, eax
0x140004dbc  call    HvsocketTraceEndpointError
0x140004dc1  mov     rcx, rbx
0x140004dc4  call    VmbusTlDisconnectAbort
0x140004dc9  mov     rcx, [rbp+57h+var_30]
0x140004dcd  xor     rcx, rsp; StackCookie
0x140004dd0  call    __security_check_cookie
0x140004dd5  add     rsp, 0E8h
0x140004ddc  pop     r15
0x140004dde  pop     rdi
0x140004ddf  pop     rbx
0x140004de0  pop     rbp
0x140004de1  retn
```
