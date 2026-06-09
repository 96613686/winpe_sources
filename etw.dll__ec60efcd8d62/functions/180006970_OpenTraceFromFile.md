# OpenTraceFromFile

- ea: `0x180006970`
- end: `0x180006c2c`
- name: `OpenTraceFromFile`
- size: `700`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct ETW_OPEN_TRACE_OPTIONS *)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180001008`
- `0x180001560`
- `0x180002ec4`
- `0x180003a8c`
- `0x180003fa8`
- `0x1800049dc`
- `0x180004ea8`
- `0x1800052b4`
- `0x180006970`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006bd0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006bd0`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800069ea`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800069ea`

## pseudocode

```c
unsigned __int64 __fastcall OpenTraceFromFile(unsigned __int16 *a1, struct ETW_OPEN_TRACE_OPTIONS *a2, _OWORD *a3)
{
  __int64 *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  struct _TRACELOG_CONTEXT *TraceHandle; // rax
  __int64 v10; // rcx
  _OWORD *v11; // rax
  __int128 v12; // xmm1
  unsigned __int64 v13; // rbx
  DWORD dwErrCode; // [rsp+30h] [rbp-69h] BYREF
  unsigned __int64 v16; // [rsp+38h] [rbp-61h] BYREF
  struct _TRACELOG_CONTEXT *v17; // [rsp+40h] [rbp-59h] BYREF
  _QWORD v18[3]; // [rsp+48h] [rbp-51h] BYREF
  char v19; // [rsp+60h] [rbp-39h]
  int v20; // [rsp+68h] [rbp-31h] BYREF
  char v21; // [rsp+6Ch] [rbp-2Dh]
  GUID ActivityId; // [rsp+70h] [rbp-29h] BYREF
  _BYTE v23[32]; // [rsp+90h] [rbp-9h] BYREF
  __int64 *v24; // [rsp+B0h] [rbp+17h]
  int v25; // [rsp+B8h] [rbp+1Fh]
  int v26; // [rsp+BCh] [rbp+23h]

  dwErrCode = 0;
  v16 = -1;
  v17 = 0;
  v20 = 0;
  v21 = 0;
  if ( (unsigned int)dword_18001D020 > 5 && (qword_18001D030 & 0x10) != 0 && (qword_18001D038 & 0x10) == qword_18001D038 )
    EventActivityIdControl(3u, &ActivityId);
  else
    ActivityId = 0;
  v20 = 1;
  if ( (unsigned int)dword_18001D020 > 5 && (qword_18001D030 & 0x10) != 0 && (qword_18001D038 & 0x10) == qword_18001D038 )
  {
    if ( a1 )
    {
      v6 = (__int64 *)a1;
      v7 = -1;
      do
        ++v7;
      while ( a1[v7] );
      v8 = 2 * v7 + 2;
    }
    else
    {
      v6 = &qword_180017B18;
      v8 = 2;
    }
    v25 = v8;
    v24 = v6;
    v26 = 0;
    tlgWriteTransfer_EtwEventWriteTransfer(
      (__int64)&dword_18001D020,
      (unsigned __int8 *)byte_180018921,
      (__int64)&ActivityId,
      0,
      3,
      (__int64)v23);
  }
  v19 = 1;
  v18[0] = &v20;
  v18[1] = &dwErrCode;
  v18[2] = &v16;
  if ( !a2 )
  {
    dwErrCode = 87;
LABEL_26:
    if ( v16 != -1 )
      EtwpFreeTraceHandle(v16);
    v16 = -1;
    goto LABEL_29;
  }
  TraceHandle = EtwpAllocateTraceHandle(0);
  v17 = TraceHandle;
  if ( !TraceHandle )
  {
    dwErrCode = 14;
    goto LABEL_26;
  }
  v16 = *((_QWORD *)TraceHandle + 2);
  dwErrCode = EtwpCopyLogfileInfoFromOptions(TraceHandle, a2, a1, 0);
  if ( !dwErrCode )
  {
    dwErrCode = EtwpProcessLogHeader(&v17, 1u, 1);
    if ( !dwErrCode )
    {
      *((_BYTE *)v17 + 552) = 0;
      if ( a3 )
      {
        v10 = 2;
        v11 = (_OWORD *)((char *)v17 + 200);
        do
        {
          *a3 = *v11;
          a3[1] = v11[1];
          a3[2] = v11[2];
          a3[3] = v11[3];
          a3[4] = v11[4];
          a3[5] = v11[5];
          a3[6] = v11[6];
          v12 = v11[7];
          v11 += 8;
          a3[7] = v12;
          a3 += 8;
          --v10;
        }
        while ( v10 );
        *a3 = *v11;
        *((_QWORD *)a3 + 2) = *((_QWORD *)v11 + 2);
      }
    }
  }
  if ( dwErrCode )
    goto LABEL_26;
LABEL_29:
  SetLastError(dwErrCode);
  v13 = v16;
  if ( v19 )
    lambda_3631f005b4eb95777f89d995bc4613ca_::operator()(v18);
  if ( v20 == 1 )
  {
    v20 = 2;
    _tlgWriteActivityAutoStop<16,5>((unsigned int *)&dword_18001D020, (__int64)&ActivityId);
  }
  return v13;
}

```

## disassembly

```asm
0x180006970  mov     [rsp-8+arg_18], rbx
0x180006975  push    rbp
0x180006976  push    rsi
0x180006977  push    rdi
0x180006978  push    r12
0x18000697a  push    r14
0x18000697c  lea     rbp, [rsp-37h]
0x180006981  sub     rsp, 0D0h
0x180006988  mov     rax, cs:__security_cookie
0x18000698f  xor     rax, rsp
0x180006992  mov     [rbp+57h+var_30], rax
0x180006996  mov     eax, cs:dword_18001D020
0x18000699c  xor     r14d, r14d
0x18000699f  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800069a3  mov     [rbp+57h+dwErrCode], r14d
0x1800069a7  mov     [rbp+57h+var_B8], r12
0x1800069ab  mov     rbx, r8
0x1800069ae  mov     [rbp+57h+var_B0], r14
0x1800069b2  mov     rsi, rdx
0x1800069b5  mov     [rbp+57h+var_88], r14d
0x1800069b9  mov     rdi, rcx
0x1800069bc  mov     [rbp+57h+var_84], r14b
0x1800069c0  cmp     eax, 5
0x1800069c3  jbe     short loc_1800069F2
0x1800069c5  mov     rcx, cs:qword_18001D038
0x1800069cc  mov     rax, cs:qword_18001D030
0x1800069d3  test    al, 10h
0x1800069d5  jz      short loc_1800069F2
0x1800069d7  mov     rax, rcx
0x1800069da  and     eax, 10h
0x1800069dd  cmp     rax, rcx
0x1800069e0  jnz     short loc_1800069F2
0x1800069e2  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x1800069e6  lea     ecx, [r14+3]; ControlCode
0x1800069ea  call    cs:__imp_EventActivityIdControl
0x1800069f0  jmp     short loc_1800069F9
0x1800069f2  xorps   xmm0, xmm0
0x1800069f5  movups  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x1800069f9  mov     eax, cs:dword_18001D020
0x1800069ff  mov     [rbp+57h+var_88], 1
0x180006a06  cmp     eax, 5
0x180006a09  jbe     loc_180006AB8
0x180006a0f  mov     rcx, cs:qword_18001D038
0x180006a16  mov     rax, cs:qword_18001D030
0x180006a1d  test    al, 10h
0x180006a1f  jz      loc_180006AB8
0x180006a25  mov     rax, rcx
0x180006a28  and     eax, 10h
0x180006a2b  cmp     rax, rcx
0x180006a2e  jnz     loc_180006AB8
0x180006a34  cmp     [rbp+57h+var_84], r14b
0x180006a38  jz      short loc_180006A58
0x180006a3a  cmp     [rbp+57h+var_70], r14d
0x180006a3e  jnz     short loc_180006A52
0x180006a40  cmp     [rbp+57h+var_6C], r14d
0x180006a44  jnz     short loc_180006A52
0x180006a46  cmp     [rbp+57h+var_68], r14d
0x180006a4a  jnz     short loc_180006A52
0x180006a4c  cmp     [rbp+57h+var_64], r14d
0x180006a50  jz      short loc_180006A58
0x180006a52  lea     r9, [rbp+57h+var_70]
0x180006a56  jmp     short loc_180006A5B
0x180006a58  mov     r9, r14
0x180006a5b  test    rdi, rdi
0x180006a5e  jz      short loc_180006A79
0x180006a60  mov     rcx, rdi
0x180006a63  mov     rax, r12
0x180006a66  inc     rax
0x180006a69  cmp     [rdi+rax*2], r14w
0x180006a6e  jnz     short loc_180006A66
0x180006a70  lea     eax, ds:2[rax*2]
0x180006a77  jmp     short loc_180006A85
0x180006a79  lea     rcx, qword_180017B18
0x180006a80  mov     eax, 2
0x180006a85  mov     [rbp+57h+var_38], eax
0x180006a88  lea     r8, [rbp+57h+ActivityId]
0x180006a8c  lea     rax, [rbp+57h+var_60]
0x180006a90  mov     [rbp+57h+var_40], rcx
0x180006a94  mov     [rsp+0F0h+var_C8], rax
0x180006a99  lea     rdx, byte_180018921
0x180006aa0  lea     rcx, dword_18001D020
0x180006aa7  mov     [rsp+0F0h+var_D0], 3
0x180006aaf  mov     [rbp+57h+var_34], r14d
0x180006ab3  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180006ab8  mov     [rbp+57h+var_90], 1
0x180006abc  lea     rax, [rbp+57h+var_88]
0x180006ac0  mov     [rbp+57h+var_A8], rax
0x180006ac4  lea     rax, [rbp+57h+dwErrCode]
0x180006ac8  mov     [rbp+57h+var_A0], rax
0x180006acc  lea     rax, [rbp+57h+var_B8]
0x180006ad0  mov     [rbp+57h+var_98], rax
0x180006ad4  test    rsi, rsi
0x180006ad7  jnz     short loc_180006AE5
0x180006ad9  mov     [rbp+57h+dwErrCode], 57h ; 'W'
0x180006ae0  jmp     loc_180006BBB
0x180006ae5  xor     ecx, ecx; unsigned int
0x180006ae7  call    ?EtwpAllocateTraceHandle@@YAPEAU_TRACELOG_CONTEXT@@K@Z; EtwpAllocateTraceHandle(ulong)
0x180006aec  mov     [rbp+57h+var_B0], rax
0x180006af0  mov     rcx, rax; struct _TRACELOG_CONTEXT *
0x180006af3  test    rax, rax
0x180006af6  jnz     short loc_180006B04
0x180006af8  mov     [rbp+57h+dwErrCode], 0Eh
0x180006aff  jmp     loc_180006BBB
0x180006b04  mov     rax, [rax+10h]
0x180006b08  xor     r9d, r9d; unsigned __int16 *
0x180006b0b  mov     r8, rdi; unsigned __int16 *
0x180006b0e  mov     [rbp+57h+var_B8], rax
0x180006b12  mov     rdx, rsi; struct ETW_OPEN_TRACE_OPTIONS *
0x180006b15  call    ?EtwpCopyLogfileInfoFromOptions@@YAKPEAU_TRACELOG_CONTEXT@@PEBUETW_OPEN_TRACE_OPTIONS@@PEBG2@Z; EtwpCopyLogfileInfoFromOptions(_TRACELOG_CONTEXT *,ETW_OPEN_TRACE_OPTIONS const *,ushort const *,ushort const *)
0x180006b1a  mov     [rbp+57h+dwErrCode], eax
0x180006b1d  test    eax, eax
0x180006b1f  jnz     loc_180006BB5
0x180006b25  mov     r8b, 1; unsigned __int8
0x180006b28  lea     edx, [rax+1]; unsigned int
0x180006b2b  lea     rcx, [rbp+57h+var_B0]; struct _TRACELOG_CONTEXT **
0x180006b2f  call    ?EtwpProcessLogHeader@@YAKPEAPEAU_TRACELOG_CONTEXT@@KE@Z; EtwpProcessLogHeader(_TRACELOG_CONTEXT * *,ulong,uchar)
0x180006b34  mov     [rbp+57h+dwErrCode], eax
0x180006b37  test    eax, eax
0x180006b39  jnz     short loc_180006BB5
0x180006b3b  mov     rax, [rbp+57h+var_B0]
0x180006b3f  mov     [rax+228h], r14b
0x180006b46  test    rbx, rbx
0x180006b49  jz      short loc_180006BB5
0x180006b4b  mov     rax, [rbp+57h+var_B0]
0x180006b4f  mov     ecx, 2
0x180006b54  add     rax, 0C8h
0x180006b5a  lea     edx, [rcx+7Eh]
0x180006b5d  movups  xmm0, xmmword ptr [rax]
0x180006b60  movups  xmmword ptr [rbx], xmm0
0x180006b63  movups  xmm1, xmmword ptr [rax+10h]
0x180006b67  movups  xmmword ptr [rbx+10h], xmm1
0x180006b6b  movups  xmm0, xmmword ptr [rax+20h]
0x180006b6f  movups  xmmword ptr [rbx+20h], xmm0
0x180006b73  movups  xmm1, xmmword ptr [rax+30h]
0x180006b77  movups  xmmword ptr [rbx+30h], xmm1
0x180006b7b  movups  xmm0, xmmword ptr [rax+40h]
0x180006b7f  movups  xmmword ptr [rbx+40h], xmm0
0x180006b83  movups  xmm1, xmmword ptr [rax+50h]
0x180006b87  movups  xmmword ptr [rbx+50h], xmm1
0x180006b8b  movups  xmm0, xmmword ptr [rax+60h]
0x180006b8f  movups  xmmword ptr [rbx+60h], xmm0
0x180006b93  movups  xmm1, xmmword ptr [rax+70h]
0x180006b97  add     rax, rdx
0x180006b9a  movups  xmmword ptr [rbx+70h], xmm1
0x180006b9e  add     rbx, rdx
0x180006ba1  sub     rcx, 1
0x180006ba5  jnz     short loc_180006B5D
0x180006ba7  movups  xmm0, xmmword ptr [rax]
0x180006baa  movups  xmmword ptr [rbx], xmm0
0x180006bad  mov     rax, [rax+10h]
0x180006bb1  mov     [rbx+10h], rax
0x180006bb5  cmp     [rbp+57h+dwErrCode], r14d
0x180006bb9  jz      short loc_180006BCD
0x180006bbb  mov     rcx, [rbp+57h+var_B8]; unsigned __int64
0x180006bbf  cmp     rcx, r12
0x180006bc2  jz      short loc_180006BC9
0x180006bc4  call    ?EtwpFreeTraceHandle@@YAK_K@Z; EtwpFreeTraceHandle(unsigned __int64)
0x180006bc9  mov     [rbp+57h+var_B8], r12
0x180006bcd  mov     ecx, [rbp+57h+dwErrCode]; dwErrCode
0x180006bd0  call    cs:__imp_SetLastError
0x180006bd6  mov     rbx, [rbp+57h+var_B8]
0x180006bda  cmp     [rbp+57h+var_90], r14b
0x180006bde  jz      short loc_180006BE9
0x180006be0  lea     rcx, [rbp+57h+var_A8]
0x180006be4  call    _lambda_3631f005b4eb95777f89d995bc4613ca___operator__
0x180006be9  cmp     [rbp+57h+var_88], 1
0x180006bed  jnz     short loc_180006C06
0x180006bef  lea     rdx, [rbp+57h+ActivityId]
0x180006bf3  mov     [rbp+57h+var_88], 2
0x180006bfa  lea     rcx, dword_18001D020
0x180006c01  call    ??$_tlgWriteActivityAutoStop@$0BA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<16,5>(_tlgProvider_t const *,_GUID const *)
0x180006c06  mov     rax, rbx
0x180006c09  mov     rcx, [rbp+57h+var_30]
0x180006c0d  xor     rcx, rsp; StackCookie
0x180006c10  call    __security_check_cookie
0x180006c15  mov     rbx, [rsp+0F0h+arg_18]
0x180006c1d  add     rsp, 0D0h
0x180006c24  pop     r14
0x180006c26  pop     r12
0x180006c28  pop     rdi
0x180006c29  pop     rsi
0x180006c2a  pop     rbp
0x180006c2b  retn
```
