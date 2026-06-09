# GetLineAndCallObjWithReadLock

- ea: `0x180088e64`
- end: `0x18008912c`
- name: `GetLineAndCallObjWithReadLock`
- size: `712`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180084ae0`

## callees

- `0x180071cec`
- `0x180088b1c`
- `0x180088e64`
- `0x1800892bc`
- `0x1800897d8`
- `0x18008a408`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `rtutils!TracePrintfA` at `0x180088f46`
- `rtutils!TracePrintfA` at `0x18008904e`
- `rtutils!TracePrintfA` at `0x1800890d7`
- `rtutils!TracePrintfA` at `0x180088f46`
- `rtutils!TracePrintfA` at `0x18008904e`
- `rtutils!TracePrintfA` at `0x1800890d7`

## string_xrefs

- `0x180088f3f`: `GetLineAndCallObjWithReadLock: GetLineObjWithReadLock failed with error (0x%x)`
- `0x180088ef5`: `GetLineAndCallObjWithReadLock: GetLineObjWithReadLock failed with error (0x%x)`
- `0x180089047`: `GetLineAndCallObjWithReadLock: Inbound ht_call(%p) closed already`
- `0x180088f9d`: `GetLineAndCallObjWithReadLock: Inbound ht_call(%p) closed already`
- `0x18008902d`: `GetLineAndCallObjWithReadLock: Failed to reacquire read lock for obj (%p)`
- `0x180089005`: `GetLineAndCallObjWithReadLock: Failed to reacquire read lock for obj (%p)`
- `0x1800890d0`: `GetLineAndCallObjWithReadLock: GetCallObjWithReadLock failed with error (0x%x)`
- `0x180089088`: `GetLineAndCallObjWithReadLock: GetCallObjWithReadLock failed with error (0x%x)`

## pseudocode

```c
__int64 __fastcall GetLineAndCallObjWithReadLock(unsigned int a1, const void *a2, _QWORD *a3, _QWORD *a4)
{
  _DWORD *v7; // rbx
  unsigned int LineObjWithReadLock; // eax
  __int64 v10; // r15
  unsigned int Lock; // edi
  _DWORD *v12; // rsi
  unsigned int v13; // eax
  _DWORD *v15; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v16; // [rsp+28h] [rbp-D8h] BYREF
  int v17; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v18[2044]; // [rsp+34h] [rbp-CCh] BYREF

  v7 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  memset_0(v18, 0, sizeof(v18));
  LineObjWithReadLock = GetLineObjWithReadLock(a1, &v16);
  v10 = v16;
  Lock = LineObjWithReadLock;
  if ( LineObjWithReadLock )
  {
    if ( !gIsndpspEtwTracingAvailable )
    {
      if ( dwTraceId != -1 )
        TracePrintfA(
          dwTraceId,
          "GetLineAndCallObjWithReadLock: GetLineObjWithReadLock failed with error (0x%x)",
          LineObjWithReadLock);
      goto LABEL_34;
    }
    if ( (_QWORD)xmmword_1800C9BE0 )
    {
      LOWORD(v17) = 0;
      FormatRRASErrorString(
        &v17,
        L"GetLineAndCallObjWithReadLock: GetLineObjWithReadLock failed with error (0x%x)",
        LineObjWithReadLock);
LABEL_5:
      ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v17);
      goto LABEL_34;
    }
    goto LABEL_34;
  }
  *a3 = v16;
  if ( ((unsigned __int8)a2 & 1) == 0 )
  {
    v13 = GetCallObjWithReadLock((unsigned int)a2, &v15);
    Lock = v13;
    if ( v13 )
    {
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( (_QWORD)xmmword_1800C9BE0 )
        {
          LOWORD(v17) = 0;
          FormatRRASErrorString(
            &v17,
            L"GetLineAndCallObjWithReadLock: GetCallObjWithReadLock failed with error (0x%x)",
            v13);
          ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v17);
        }
      }
      else if ( dwTraceId != -1 )
      {
        TracePrintfA(dwTraceId, "GetLineAndCallObjWithReadLock: GetCallObjWithReadLock failed with error (0x%x)", v13);
      }
      v7 = v15;
      goto LABEL_34;
    }
    v7 = v15;
    goto LABEL_39;
  }
  v7 = *(_DWORD **)(v10 + 24);
  if ( !v7 )
    goto LABEL_14;
  v12 = *(_DWORD **)(v10 + 24);
  while ( *((const void **)v12 + 2) != a2 )
  {
    v7 = (_DWORD *)*((_QWORD *)v12 + 7);
    v12 = v7;
    if ( !v7 )
      goto LABEL_14;
  }
  if ( *v7 != 1229144396 )
  {
LABEL_14:
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800C9BE0 )
      {
        LOWORD(v17) = 0;
        FormatRRASErrorString(&v17, L"GetLineAndCallObjWithReadLock: Inbound ht_call(%p) closed already", a2);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v17);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "GetLineAndCallObjWithReadLock: Inbound ht_call(%p) closed already", a2);
    }
    Lock = -2147483624;
    goto LABEL_34;
  }
  Lock = AcquireObjReadLock((unsigned int)v12[2]);
  if ( !Lock )
  {
LABEL_39:
    *a4 = v7;
    return Lock;
  }
  if ( !gIsndpspEtwTracingAvailable )
  {
    if ( dwTraceId != -1 )
      TracePrintfA(
        dwTraceId,
        "GetLineAndCallObjWithReadLock: Failed to reacquire read lock for obj (%p)",
        (unsigned int)v12[2]);
    goto LABEL_34;
  }
  if ( (_QWORD)xmmword_1800C9BE0 )
  {
    LOWORD(v17) = 0;
    FormatRRASErrorString(
      &v17,
      L"GetLineAndCallObjWithReadLock: Failed to reacquire read lock for obj (%p)",
      (unsigned int)v12[2]);
    goto LABEL_5;
  }
LABEL_34:
  if ( v10 )
    ReleaseObjReadLock(a1);
  if ( v7 )
    ReleaseObjReadLock((unsigned int)v7[2]);
  return Lock;
}

```

## disassembly

```asm
0x180088e64  push    rbp
0x180088e66  push    rbx
0x180088e67  push    rsi
0x180088e68  push    rdi
0x180088e69  push    r12
0x180088e6b  push    r13
0x180088e6d  push    r14
0x180088e6f  push    r15
0x180088e71  lea     rbp, [rsp-748h]
0x180088e79  sub     rsp, 848h
0x180088e80  mov     rax, cs:__security_cookie
0x180088e87  xor     rax, rsp
0x180088e8a  mov     [rbp+780h+var_50], rax
0x180088e91  mov     rsi, r8
0x180088e94  mov     r14, rdx
0x180088e97  mov     r13d, ecx
0x180088e9a  xor     ebx, ebx
0x180088e9c  xor     eax, eax
0x180088e9e  mov     [rsp+880h+var_860], rbx
0x180088ea3  xor     edx, edx; Val
0x180088ea5  mov     [rsp+880h+var_858], rbx
0x180088eaa  mov     r8d, 7FCh; Size
0x180088eb0  mov     [rsp+880h+var_850], eax
0x180088eb4  lea     rcx, [rsp+880h+var_84C]; void *
0x180088eb9  mov     r12, r9
0x180088ebc  call    memset_0
0x180088ec1  lea     rdx, [rsp+880h+var_858]
0x180088ec6  mov     ecx, r13d
0x180088ec9  call    GetLineObjWithReadLock
0x180088ece  mov     r15, [rsp+880h+var_858]
0x180088ed3  mov     edi, eax
0x180088ed5  xor     eax, eax
0x180088ed7  test    edi, edi
0x180088ed9  jz      short loc_180088F51
0x180088edb  cmp     cs:gIsndpspEtwTracingAvailable, eax
0x180088ee1  jz      short loc_180088F2D
0x180088ee3  cmp     qword ptr cs:xmmword_1800C9BE0, rax
0x180088eea  jz      loc_1800890E2
0x180088ef0  mov     word ptr [rsp+880h+var_850], ax
0x180088ef5  lea     rdx, aGetlineandcall_0; "GetLineAndCallObjWithReadLock: GetLineO"...
0x180088efc  mov     r8d, edi
0x180088eff  lea     rcx, [rsp+880h+var_850]
0x180088f04  call    FormatRRASErrorString
0x180088f09  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180088f10  lea     r8, [rsp+880h+var_850]
0x180088f15  mov     rcx, cs:gNdpspEtwContext
0x180088f1c  mov     rax, cs:gNdpspTemplateFunc
0x180088f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088f28  jmp     loc_1800890E2
0x180088f2d  mov     ecx, cs:dwTraceId; dwTraceID
0x180088f33  cmp     ecx, 0FFFFFFFFh
0x180088f36  jz      loc_1800890E2
0x180088f3c  mov     r8d, edi
0x180088f3f  lea     rdx, aGetlineandcall_2; "GetLineAndCallObjWithReadLock: GetLineO"...
0x180088f46  call    cs:__imp_TracePrintfA
0x180088f4c  jmp     loc_1800890E2
0x180088f51  mov     [rsi], r15
0x180088f54  test    r14b, 1
0x180088f58  jz      loc_18008905E
0x180088f5e  mov     rbx, [r15+18h]
0x180088f62  test    rbx, rbx
0x180088f65  jz      short loc_180088F7C
0x180088f67  mov     rsi, rbx
0x180088f6a  cmp     [rsi+10h], r14
0x180088f6e  jz      short loc_180088FD2
0x180088f70  mov     rbx, [rsi+38h]
0x180088f74  mov     rsi, rbx
0x180088f77  test    rbx, rbx
0x180088f7a  jnz     short loc_180088F6A
0x180088f7c  cmp     cs:gIsndpspEtwTracingAvailable, eax
0x180088f82  jz      loc_180089039
0x180088f88  cmp     qword ptr cs:xmmword_1800C9BE0, rax
0x180088f8f  jz      loc_180089054
0x180088f95  mov     r8, r14
0x180088f98  mov     word ptr [rsp+880h+var_850], ax
0x180088f9d  lea     rdx, aGetlineandcall_6; "GetLineAndCallObjWithReadLock: Inbound "...
0x180088fa4  lea     rcx, [rsp+880h+var_850]
0x180088fa9  call    FormatRRASErrorString
0x180088fae  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180088fb5  lea     r8, [rsp+880h+var_850]
0x180088fba  mov     rcx, cs:gNdpspEtwContext
0x180088fc1  mov     rax, cs:gNdpspTemplateFunc
0x180088fc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088fcd  jmp     loc_180089054
0x180088fd2  cmp     dword ptr [rbx], 4943414Ch
0x180088fd8  jnz     short loc_180088F7C
0x180088fda  mov     ecx, [rsi+8]
0x180088fdd  call    AcquireObjReadLock
0x180088fe2  mov     edi, eax
0x180088fe4  test    eax, eax
0x180088fe6  jz      loc_180089103
0x180088fec  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x180088ff3  jz      short loc_18008901A
0x180088ff5  cmp     qword ptr cs:xmmword_1800C9BE0, 0
0x180088ffd  jz      loc_1800890E2
0x180089003  xor     eax, eax
0x180089005  lea     rdx, aGetlineandcall; "GetLineAndCallObjWithReadLock: Failed t"...
0x18008900c  mov     word ptr [rsp+880h+var_850], ax
0x180089011  mov     r8d, [rsi+8]
0x180089015  jmp     loc_180088EFF
0x18008901a  mov     ecx, cs:dwTraceId
0x180089020  cmp     ecx, 0FFFFFFFFh
0x180089023  jz      loc_1800890E2
0x180089029  mov     r8d, [rsi+8]
0x18008902d  lea     rdx, aGetlineandcall_3; "GetLineAndCallObjWithReadLock: Failed t"...
0x180089034  jmp     loc_180088F46
0x180089039  mov     ecx, cs:dwTraceId; dwTraceID
0x18008903f  cmp     ecx, 0FFFFFFFFh
0x180089042  jz      short loc_180089054
0x180089044  mov     r8, r14
0x180089047  lea     rdx, aGetlineandcall_4; "GetLineAndCallObjWithReadLock: Inbound "...
0x18008904e  call    cs:__imp_TracePrintfA
0x180089054  mov     edi, 80000018h
0x180089059  jmp     loc_1800890E2
0x18008905e  mov     ecx, r14d
0x180089061  lea     rdx, [rsp+880h+var_860]
0x180089066  call    GetCallObjWithReadLock
0x18008906b  mov     edi, eax
0x18008906d  test    eax, eax
0x18008906f  jz      loc_1800890FE
0x180089075  cmp     cs:gIsndpspEtwTracingAvailable, ebx
0x18008907b  jz      short loc_1800890C2
0x18008907d  cmp     qword ptr cs:xmmword_1800C9BE0, rbx
0x180089084  jz      short loc_1800890DD
0x180089086  xor     eax, eax
0x180089088  lea     rdx, aGetlineandcall_1; "GetLineAndCallObjWithReadLock: GetCallO"...
0x18008908f  mov     r8d, edi
0x180089092  mov     word ptr [rsp+880h+var_850], ax
0x180089097  lea     rcx, [rsp+880h+var_850]
0x18008909c  call    FormatRRASErrorString
0x1800890a1  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x1800890a8  lea     r8, [rsp+880h+var_850]
0x1800890ad  mov     rcx, cs:gNdpspEtwContext
0x1800890b4  mov     rax, cs:gNdpspTemplateFunc
0x1800890bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800890c0  jmp     short loc_1800890DD
0x1800890c2  mov     ecx, cs:dwTraceId; dwTraceID
0x1800890c8  cmp     ecx, 0FFFFFFFFh
0x1800890cb  jz      short loc_1800890DD
0x1800890cd  mov     r8d, edi
0x1800890d0  lea     rdx, aGetlineandcall_5; "GetLineAndCallObjWithReadLock: GetCallO"...
0x1800890d7  call    cs:__imp_TracePrintfA
0x1800890dd  mov     rbx, [rsp+880h+var_860]
0x1800890e2  test    r15, r15
0x1800890e5  jz      short loc_1800890EF
0x1800890e7  mov     ecx, r13d
0x1800890ea  call    ReleaseObjReadLock
0x1800890ef  test    rbx, rbx
0x1800890f2  jz      short loc_180089107
0x1800890f4  mov     ecx, [rbx+8]
0x1800890f7  call    ReleaseObjReadLock
0x1800890fc  jmp     short loc_180089107
0x1800890fe  mov     rbx, [rsp+880h+var_860]
0x180089103  mov     [r12], rbx
0x180089107  mov     eax, edi
0x180089109  mov     rcx, [rbp+780h+var_50]
0x180089110  xor     rcx, rsp; StackCookie
0x180089113  call    __security_check_cookie
0x180089118  add     rsp, 848h
0x18008911f  pop     r15
0x180089121  pop     r14
0x180089123  pop     r13
0x180089125  pop     r12
0x180089127  pop     rdi
0x180089128  pop     rsi
0x180089129  pop     rbx
0x18008912a  pop     rbp
0x18008912b  retn
```
