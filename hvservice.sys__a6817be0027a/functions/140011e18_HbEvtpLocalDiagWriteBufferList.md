# HbEvtpLocalDiagWriteBufferList

- ea: `0x140011e18`
- end: `0x140012075`
- name: `HbEvtpLocalDiagWriteBufferList`
- size: `605`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140001900`

## callees

- `0x140001600`
- `0x140001aec`
- `0x140001b50`
- `0x140001bfc`
- `0x140011e18`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtection` at `0x140011ede`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140011ede`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140011f8d`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140011f8d`

## string_xrefs

- `0x140011e4f`: `Entering with cached logger ID 0x%x, mode %d, buffer %d, state %d`
- `0x140011e40`: `HbEvtpLocalDiagWriteBufferList`
- `0x140011f49`: `HbEvtpLocalDiagWriteBufferList`
- `0x140011fc0`: `HbEvtpLocalDiagWriteBufferList`
- `0x140012034`: `Invalid cached logger ID (0x%x)`

## pseudocode

```c
__int64 __fastcall HbEvtpLocalDiagWriteBufferList(__int64 a1, __int64 a2, unsigned int a3)
{
  unsigned int v3; // ebx
  unsigned int v6; // ebp
  __int64 v7; // r13
  __int64 v8; // r15
  _DWORD *v9; // rsi
  __int64 v10; // r12
  int v11; // ecx
  int v12; // eax
  __int64 *v15; // [rsp+88h] [rbp+10h]
  unsigned int v16; // [rsp+90h] [rbp+18h]

  v3 = a3;
  v6 = 0;
  HbpTraceEvent(
    3,
    "HbEvtpLocalDiagWriteBufferList",
    3983,
    "Entering with cached logger ID 0x%x, mode %d, buffer %d, state %d",
    *(_QWORD *)(a1 + 328),
    *(_DWORD *)(a2 + 48),
    a3,
    *(_DWORD *)(*(_QWORD *)(112LL * a3 + *(_QWORD *)(a2 + 32)) + 44LL));
  if ( (unsigned __int64)(*(_QWORD *)(a1 + 328) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    HbpTraceEvent(0, "HbEvtpLocalDiagWriteBufferList", 3988, "Invalid cached logger ID (0x%x)", *(_QWORD *)(a1 + 328));
LABEL_15:
    if ( v3 != -1 )
LABEL_16:
      HbEvtpLocalDiagReleaseBufferList(a2, v3);
    return v6;
  }
  if ( HbEvtpLocalDiagnosticsDisableSession && *(_DWORD *)(a2 + 48) == 1 )
  {
    HbpTraceEvent(3, "HbEvtpLocalDiagWriteBufferList", 3997, "Session disabled in circular mode; cleaning up");
    goto LABEL_15;
  }
  while ( v3 != -1 )
  {
    if ( !ExAcquireRundownProtection((PEX_RUNDOWN_REF)(*(_QWORD *)(a2 + 40) + 8LL * v3)) )
      goto LABEL_16;
    v7 = *(_QWORD *)(a2 + 136);
    v15 = (__int64 *)(112LL * v3 + *(_QWORD *)(a2 + 32));
    v8 = *v15;
    v9 = (_DWORD *)(*v15 + 60);
    v10 = *(unsigned __int16 *)(*v15 + 40);
    v16 = *(_DWORD *)(*v15 + 56);
    if ( *(_DWORD *)(a2 + 48) == 1 || (v11 = *(_DWORD *)(v7 + 4 * v10), *v9 <= (unsigned int)(v11 + 1)) )
    {
      HbpTraceEvent(
        3,
        "HbEvtpLocalDiagWriteBufferList",
        4055,
        "Writing buffer %d (LP %d, lastSeq = 0x%x, bufferSeq = 0x%x)",
        *(_DWORD *)(v8 + 4),
        v10,
        *(_DWORD *)(v7 + 4 * v10),
        *v9);
      *(_DWORD *)(v7 + 4 * v10) = *v9;
      v12 = HbEvtpLocalDiagWriteBuffer(a1, a2, v15);
      v6 = v12;
      if ( v12 < 0 )
      {
        HbpTraceEvent(1, "HbEvtpLocalDiagWriteBufferList", 4062, "Error writing event (0x%x)", v12);
        goto LABEL_15;
      }
    }
    else
    {
      HbpTraceEvent(
        1,
        "HbEvtpLocalDiagWriteBufferList",
        4076,
        "Found out-of-order buffer %d (LP %d, lastSeq = 0x%x, bufferSeq = 0x%x)",
        *(_DWORD *)(v8 + 4),
        v10,
        v11,
        *v9);
      *(_DWORD *)(v8 + 56) = -1;
      HbEvtpLocalDiagInsertOutOfOrderBufferInList(a2, v15);
      ExReleaseRundownProtection((PEX_RUNDOWN_REF)(*(_QWORD *)(a2 + 40) + 8LL * v3));
    }
    v3 = v16;
  }
  return v6;
}

```

## disassembly

```asm
0x140011e18  mov     [rsp+arg_18], rbx
0x140011e1d  mov     [rsp+arg_0], rcx
0x140011e22  push    rbp
0x140011e23  push    rsi
0x140011e24  push    rdi
0x140011e25  push    r12
0x140011e27  push    r13
0x140011e29  push    r14
0x140011e2b  push    r15
0x140011e2d  sub     rsp, 40h
0x140011e31  mov     ebx, r8d
0x140011e34  mov     rdi, rdx
0x140011e37  mov     rsi, rcx
0x140011e3a  xor     ebp, ebp
0x140011e3c  mov     rax, [rdx+20h]
0x140011e40  lea     r15, aHbevtplocaldia_0; "HbEvtpLocalDiagWriteBufferList"
0x140011e47  imul    r8, rbx, 70h ; 'p'
0x140011e4b  lea     r14d, [rbp+3]
0x140011e4f  lea     r9, aEnteringWithCa; "Entering with cached logger ID 0x%x, mo"...
0x140011e56  mov     r8, [r8+rax]
0x140011e5a  mov     eax, [r8+2Ch]
0x140011e5e  mov     r8d, 0F8Fh
0x140011e64  mov     [rsp+78h+var_40], eax
0x140011e68  mov     eax, [rdx+30h]
0x140011e6b  mov     rdx, r15
0x140011e6e  mov     [rsp+78h+var_48], ebx
0x140011e72  mov     [rsp+78h+var_50], eax
0x140011e76  mov     rax, [rcx+148h]
0x140011e7d  mov     ecx, r14d
0x140011e80  mov     [rsp+78h+var_58], rax
0x140011e85  call    HbpTraceEvent
0x140011e8a  mov     r8, [rsi+148h]
0x140011e91  lea     rax, [r8-1]
0x140011e95  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140011e99  ja      loc_14001202F
0x140011e9f  cmp     cs:HbEvtpLocalDiagnosticsDisableSession, bpl
0x140011ea6  jz      loc_140012004
0x140011eac  cmp     dword ptr [rdi+30h], 1
0x140011eb0  jnz     loc_140012004
0x140011eb6  lea     r9, aSessionDisable; "Session disabled in circular mode; clea"...
0x140011ebd  mov     r8d, 0F9Dh
0x140011ec3  mov     rdx, r15
0x140011ec6  mov     ecx, r14d
0x140011ec9  call    HbpTraceEvent
0x140011ece  jmp     loc_14001204B
0x140011ed3  mov     rax, [rdi+28h]
0x140011ed7  mov     r14d, ebx
0x140011eda  lea     rcx, [rax+r14*8]; RunRef
0x140011ede  call    cs:__imp_ExAcquireRundownProtection
0x140011ee5  nop     dword ptr [rax+rax+00h]
0x140011eea  test    al, al
0x140011eec  jz      loc_140012050
0x140011ef2  mov     rax, [rdi+20h]
0x140011ef6  mov     r13, [rdi+88h]
0x140011efd  imul    rcx, r14, 70h ; 'p'
0x140011f01  add     rax, rcx
0x140011f04  cmp     dword ptr [rdi+30h], 1
0x140011f08  mov     [rsp+78h+arg_8], rax
0x140011f10  mov     r15, [rax]
0x140011f13  mov     eax, [r15+38h]
0x140011f17  lea     rsi, [r15+3Ch]
0x140011f1b  movzx   r12d, word ptr [r15+28h]
0x140011f20  mov     [rsp+78h+arg_10], eax
0x140011f27  jz      short loc_140011F9B
0x140011f29  mov     ecx, [r13+r12*4+0]
0x140011f2e  mov     r8d, [rsi]
0x140011f31  lea     eax, [rcx+1]
0x140011f34  cmp     r8d, eax
0x140011f37  jbe     short loc_140011F9B
0x140011f39  mov     eax, [r15+4]
0x140011f3d  lea     r9, aFoundOutOfOrde; "Found out-of-order buffer %d (LP %d, la"...
0x140011f44  mov     [rsp+78h+var_40], r8d
0x140011f49  lea     rdx, aHbevtplocaldia_0; "HbEvtpLocalDiagWriteBufferList"
0x140011f50  mov     [rsp+78h+var_48], ecx
0x140011f54  mov     r8d, 0FECh
0x140011f5a  mov     [rsp+78h+var_50], r12d
0x140011f5f  mov     ecx, 1
0x140011f64  mov     dword ptr [rsp+78h+var_58], eax
0x140011f68  call    HbpTraceEvent
0x140011f6d  mov     rdx, [rsp+78h+arg_8]
0x140011f75  mov     rcx, rdi
0x140011f78  mov     dword ptr [r15+38h], 0FFFFFFFFh
0x140011f80  call    HbEvtpLocalDiagInsertOutOfOrderBufferInList
0x140011f85  mov     rdx, [rdi+28h]
0x140011f89  lea     rcx, [rdx+r14*8]; RunRef
0x140011f8d  call    cs:__imp_ExReleaseRundownProtection
0x140011f94  nop     dword ptr [rax+rax+00h]
0x140011f99  jmp     short loc_140011FFD
0x140011f9b  mov     eax, [rsi]
0x140011f9d  lea     r9, aWritingBufferD; "Writing buffer %d (LP %d, lastSeq = 0x%"...
0x140011fa4  mov     [rsp+78h+var_40], eax
0x140011fa8  mov     r8d, 0FD7h
0x140011fae  mov     eax, [r13+r12*4+0]
0x140011fb3  mov     ecx, 3
0x140011fb8  mov     [rsp+78h+var_48], eax
0x140011fbc  mov     eax, [r15+4]
0x140011fc0  lea     r15, aHbevtplocaldia_0; "HbEvtpLocalDiagWriteBufferList"
0x140011fc7  mov     rdx, r15
0x140011fca  mov     [rsp+78h+var_50], r12d
0x140011fcf  mov     dword ptr [rsp+78h+var_58], eax
0x140011fd3  call    HbpTraceEvent
0x140011fd8  mov     eax, [rsi]
0x140011fda  mov     rdx, rdi
0x140011fdd  mov     r8, [rsp+78h+arg_8]
0x140011fe5  mov     rcx, [rsp+78h+arg_0]
0x140011fed  mov     [r13+r12*4+0], eax
0x140011ff2  call    HbEvtpLocalDiagWriteBuffer
0x140011ff7  mov     ebp, eax
0x140011ff9  test    eax, eax
0x140011ffb  js      short loc_14001200F
0x140011ffd  mov     ebx, [rsp+78h+arg_10]
0x140012004  cmp     ebx, 0FFFFFFFFh
0x140012007  jnz     loc_140011ED3
0x14001200d  jmp     short loc_14001205A
0x14001200f  lea     r9, aErrorWritingEv; "Error writing event (0x%x)"
0x140012016  mov     dword ptr [rsp+78h+var_58], eax
0x14001201a  mov     r8d, 0FDEh
0x140012020  mov     rdx, r15
0x140012023  mov     ecx, 1
0x140012028  call    HbpTraceEvent
0x14001202d  jmp     short loc_14001204B
0x14001202f  mov     [rsp+78h+var_58], r8
0x140012034  lea     r9, aInvalidCachedL; "Invalid cached logger ID (0x%x)"
0x14001203b  mov     r8d, 0F94h
0x140012041  mov     rdx, r15
0x140012044  xor     ecx, ecx
0x140012046  call    HbpTraceEvent
0x14001204b  cmp     ebx, 0FFFFFFFFh
0x14001204e  jz      short loc_14001205A
0x140012050  mov     edx, ebx
0x140012052  mov     rcx, rdi
0x140012055  call    HbEvtpLocalDiagReleaseBufferList
0x14001205a  mov     rbx, [rsp+78h+arg_18]
0x140012062  mov     eax, ebp
0x140012064  add     rsp, 40h
0x140012068  pop     r15
0x14001206a  pop     r14
0x14001206c  pop     r13
0x14001206e  pop     r12
0x140012070  pop     rdi
0x140012071  pop     rsi
0x140012072  pop     rbp
0x140012073  retn
```
