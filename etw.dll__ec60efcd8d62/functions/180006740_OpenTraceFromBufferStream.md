# OpenTraceFromBufferStream

- ea: `0x180006740`
- end: `0x18000695c`
- name: `OpenTraceFromBufferStream`
- size: `540`
- prototype: `__int64 __fastcall(struct ETW_OPEN_TRACE_OPTIONS *)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180001008`
- `0x180001560`
- `0x180002050`
- `0x180002ec4`
- `0x180003b58`
- `0x180003fa8`
- `0x1800049dc`
- `0x180004ea8`
- `0x180006740`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006907`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006907`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800067b7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800067b7`

## pseudocode

```c
unsigned __int64 __fastcall OpenTraceFromBufferStream(struct ETW_OPEN_TRACE_OPTIONS *a1, __int64 a2, __int64 a3)
{
  struct _TRACELOG_CONTEXT *TraceHandle; // rax
  struct _TRACELOG_CONTEXT *v7; // rbx
  unsigned int v8; // eax
  _QWORD *v9; // rax
  unsigned __int64 v10; // rbx
  DWORD dwErrCode; // [rsp+30h] [rbp-59h] BYREF
  unsigned __int64 v13; // [rsp+38h] [rbp-51h] BYREF
  _QWORD v14[3]; // [rsp+40h] [rbp-49h] BYREF
  char v15; // [rsp+58h] [rbp-31h]
  int v16; // [rsp+60h] [rbp-29h] BYREF
  char v17; // [rsp+64h] [rbp-25h]
  GUID ActivityId; // [rsp+68h] [rbp-21h] BYREF
  _BYTE v19[32]; // [rsp+88h] [rbp-1h] BYREF

  dwErrCode = 0;
  v13 = -1;
  v16 = 0;
  v17 = 0;
  if ( (unsigned int)dword_18001D020 > 5 && (qword_18001D030 & 0x10) != 0 && (qword_18001D038 & 0x10) == qword_18001D038 )
    EventActivityIdControl(3u, &ActivityId);
  else
    ActivityId = 0;
  v16 = 1;
  if ( (unsigned int)dword_18001D020 > 5 && (qword_18001D030 & 0x10) != 0 && (qword_18001D038 & 0x10) == qword_18001D038 )
    tlgWriteTransfer_EtwEventWriteTransfer(
      (__int64)&dword_18001D020,
      (unsigned __int8 *)&word_180018A4E,
      (__int64)&ActivityId,
      0,
      2,
      (__int64)v19);
  v15 = 1;
  v14[0] = &v16;
  v14[1] = &dwErrCode;
  v14[2] = &v13;
  if ( !a1 || !a2 )
  {
    v8 = 87;
    dwErrCode = 87;
    goto LABEL_17;
  }
  TraceHandle = EtwpAllocateTraceHandle(0);
  v7 = TraceHandle;
  if ( TraceHandle )
  {
    v13 = *((_QWORD *)TraceHandle + 2);
    v8 = EtwpCopyLogfileInfoFromOptions(TraceHandle, a1, 0, 0);
    dwErrCode = v8;
    if ( v8 )
      goto LABEL_18;
    v9 = operator new(0x20u);
    *v9 = -1;
    v9[1] = -1;
    v9[2] = -1;
    v9[3] = 0;
    *((_QWORD *)v7 + 125) = v9;
    *((_BYTE *)v7 + 1024) = 1;
    *((_QWORD *)v7 + 123) = a2;
    *((_QWORD *)v7 + 124) = a3;
    *((_BYTE *)v7 + 552) = 2;
    v8 = dwErrCode;
LABEL_17:
    if ( !v8 )
      goto LABEL_21;
    goto LABEL_18;
  }
  v8 = 14;
  dwErrCode = 14;
LABEL_18:
  if ( v13 != -1 )
  {
    EtwpFreeTraceHandle(v13);
    v8 = dwErrCode;
  }
  v13 = -1;
LABEL_21:
  SetLastError(v8);
  v10 = v13;
  if ( v15 )
    lambda_5f04944841c5194099299c287b6faf92_::operator()(v14);
  if ( v16 == 1 )
  {
    v16 = 2;
    _tlgWriteActivityAutoStop<16,5>((unsigned int *)&dword_18001D020, (__int64)&ActivityId);
  }
  return v10;
}

```

## disassembly

```asm
0x180006740  push    rbp
0x180006742  push    rbx
0x180006743  push    rsi
0x180006744  push    rdi
0x180006745  push    r12
0x180006747  push    r14
0x180006749  lea     rbp, [rsp-2Fh]
0x18000674e  sub     rsp, 0B8h
0x180006755  mov     rax, cs:__security_cookie
0x18000675c  xor     rax, rsp
0x18000675f  mov     [rbp+57h+var_38], rax
0x180006763  mov     eax, cs:dword_18001D020
0x180006769  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000676d  mov     [rbp+57h+dwErrCode], 0
0x180006774  mov     r14, r8
0x180006777  mov     [rbp+57h+var_A8], r12
0x18000677b  mov     rdi, rdx
0x18000677e  mov     [rbp+57h+var_80], 0
0x180006785  mov     rsi, rcx
0x180006788  mov     [rbp+57h+var_7C], 0
0x18000678c  cmp     eax, 5
0x18000678f  jbe     short loc_1800067BF
0x180006791  mov     rcx, cs:qword_18001D038
0x180006798  mov     rax, cs:qword_18001D030
0x18000679f  test    al, 10h
0x1800067a1  jz      short loc_1800067BF
0x1800067a3  mov     rax, rcx
0x1800067a6  and     eax, 10h
0x1800067a9  cmp     rax, rcx
0x1800067ac  jnz     short loc_1800067BF
0x1800067ae  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x1800067b2  lea     ecx, [r12+4]; ControlCode
0x1800067b7  call    cs:__imp_EventActivityIdControl
0x1800067bd  jmp     short loc_1800067C6
0x1800067bf  xorps   xmm0, xmm0
0x1800067c2  movups  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x1800067c6  mov     eax, cs:dword_18001D020
0x1800067cc  mov     [rbp+57h+var_80], 1
0x1800067d3  cmp     eax, 5
0x1800067d6  jbe     short loc_180006844
0x1800067d8  mov     rcx, cs:qword_18001D038
0x1800067df  mov     rax, cs:qword_18001D030
0x1800067e6  test    al, 10h
0x1800067e8  jz      short loc_180006844
0x1800067ea  mov     rax, rcx
0x1800067ed  and     eax, 10h
0x1800067f0  cmp     rax, rcx
0x1800067f3  jnz     short loc_180006844
0x1800067f5  cmp     [rbp+57h+var_7C], 0
0x1800067f9  jz      short loc_180006819
0x1800067fb  cmp     [rbp+57h+var_68], 0
0x1800067ff  jnz     short loc_180006813
0x180006801  cmp     [rbp+57h+var_64], 0
0x180006805  jnz     short loc_180006813
0x180006807  cmp     [rbp+57h+var_60], 0
0x18000680b  jnz     short loc_180006813
0x18000680d  cmp     [rbp+57h+var_5C], 0
0x180006811  jz      short loc_180006819
0x180006813  lea     r9, [rbp+57h+var_68]
0x180006817  jmp     short loc_18000681C
0x180006819  xor     r9d, r9d
0x18000681c  lea     rax, [rbp+57h+var_58]
0x180006820  mov     [rsp+0E0h+var_B8], rax
0x180006825  lea     r8, [rbp+57h+ActivityId]
0x180006829  lea     rdx, word_180018A4E
0x180006830  mov     [rsp+0E0h+var_C0], 2
0x180006838  lea     rcx, dword_18001D020
0x18000683f  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180006844  mov     [rbp+57h+var_88], 1
0x180006848  lea     rax, [rbp+57h+var_80]
0x18000684c  mov     [rbp+57h+var_A0], rax
0x180006850  lea     rax, [rbp+57h+dwErrCode]
0x180006854  mov     [rbp+57h+var_98], rax
0x180006858  lea     rax, [rbp+57h+var_A8]
0x18000685c  mov     [rbp+57h+var_90], rax
0x180006860  test    rsi, rsi
0x180006863  jz      short loc_1800068E4
0x180006865  test    rdi, rdi
0x180006868  jz      short loc_1800068E4
0x18000686a  xor     ecx, ecx; unsigned int
0x18000686c  call    ?EtwpAllocateTraceHandle@@YAPEAU_TRACELOG_CONTEXT@@K@Z; EtwpAllocateTraceHandle(ulong)
0x180006871  mov     rbx, rax
0x180006874  test    rax, rax
0x180006877  jnz     short loc_180006881
0x180006879  lea     eax, [rbx+0Eh]
0x18000687c  mov     [rbp+57h+dwErrCode], eax
0x18000687f  jmp     short loc_1800068F0
0x180006881  mov     rax, [rax+10h]
0x180006885  xor     r9d, r9d; unsigned __int16 *
0x180006888  xor     r8d, r8d; unsigned __int16 *
0x18000688b  mov     [rbp+57h+var_A8], rax
0x18000688f  mov     rdx, rsi; struct ETW_OPEN_TRACE_OPTIONS *
0x180006892  mov     rcx, rbx; struct _TRACELOG_CONTEXT *
0x180006895  call    ?EtwpCopyLogfileInfoFromOptions@@YAKPEAU_TRACELOG_CONTEXT@@PEBUETW_OPEN_TRACE_OPTIONS@@PEBG2@Z; EtwpCopyLogfileInfoFromOptions(_TRACELOG_CONTEXT *,ETW_OPEN_TRACE_OPTIONS const *,ushort const *,ushort const *)
0x18000689a  mov     [rbp+57h+dwErrCode], eax
0x18000689d  test    eax, eax
0x18000689f  jnz     short loc_1800068F0
0x1800068a1  lea     ecx, [rax+20h]; Size
0x1800068a4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800068a9  mov     [rax], r12
0x1800068ac  mov     [rax+8], r12
0x1800068b0  mov     [rax+10h], r12
0x1800068b4  mov     qword ptr [rax+18h], 0
0x1800068bc  mov     [rbx+3E8h], rax
0x1800068c3  mov     byte ptr [rbx+400h], 1
0x1800068ca  mov     [rbx+3D8h], rdi
0x1800068d1  mov     [rbx+3E0h], r14
0x1800068d8  mov     byte ptr [rbx+228h], 2
0x1800068df  mov     eax, [rbp+57h+dwErrCode]
0x1800068e2  jmp     short loc_1800068EC
0x1800068e4  mov     eax, 57h ; 'W'
0x1800068e9  mov     [rbp+57h+dwErrCode], eax
0x1800068ec  test    eax, eax
0x1800068ee  jz      short loc_180006905
0x1800068f0  mov     rcx, [rbp+57h+var_A8]; unsigned __int64
0x1800068f4  cmp     rcx, r12
0x1800068f7  jz      short loc_180006901
0x1800068f9  call    ?EtwpFreeTraceHandle@@YAK_K@Z; EtwpFreeTraceHandle(unsigned __int64)
0x1800068fe  mov     eax, [rbp+57h+dwErrCode]
0x180006901  mov     [rbp+57h+var_A8], r12
0x180006905  mov     ecx, eax; dwErrCode
0x180006907  call    cs:__imp_SetLastError
0x18000690d  cmp     [rbp+57h+var_88], 0
0x180006911  mov     rbx, [rbp+57h+var_A8]
0x180006915  jz      short loc_180006920
0x180006917  lea     rcx, [rbp+57h+var_A0]
0x18000691b  call    _lambda_5f04944841c5194099299c287b6faf92___operator__
0x180006920  cmp     [rbp+57h+var_80], 1
0x180006924  jnz     short loc_18000693D
0x180006926  lea     rdx, [rbp+57h+ActivityId]
0x18000692a  mov     [rbp+57h+var_80], 2
0x180006931  lea     rcx, dword_18001D020
0x180006938  call    ??$_tlgWriteActivityAutoStop@$0BA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<16,5>(_tlgProvider_t const *,_GUID const *)
0x18000693d  mov     rax, rbx
0x180006940  mov     rcx, [rbp+57h+var_38]
0x180006944  xor     rcx, rsp; StackCookie
0x180006947  call    __security_check_cookie
0x18000694c  add     rsp, 0B8h
0x180006953  pop     r14
0x180006955  pop     r12
0x180006957  pop     rdi
0x180006958  pop     rsi
0x180006959  pop     rbx
0x18000695a  pop     rbp
0x18000695b  retn
```
