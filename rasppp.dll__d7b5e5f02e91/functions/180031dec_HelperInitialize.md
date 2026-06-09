# HelperInitialize

- ea: `0x180031dec`
- end: `0x18003201e`
- name: `HelperInitialize`
- size: `562`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001e4d0`
- `0x180023270`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18002b0dc`
- `0x180031dec`
- `0x18003230c`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180031eab`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180031eab`
- `rtutils!TraceRegisterExA` at `0x180031e2f`
- `rtutils!TraceRegisterExA` at `0x180031e2f`

## string_xrefs

- `0x180031fb2`: `HelperInitialize completed %d`
- `0x180031ff7`: `HelperInitialize completed %d`

## pseudocode

```c
__int64 HelperInitialize()
{
  int v1; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v2[2044]; // [rsp+24h] [rbp-DCh] BYREF

  v1 = 0;
  memset_0(v2, 0, sizeof(v2));
  HelperTraceId = TraceRegisterExA("RASIPHLP", 0);
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( (_QWORD)xmmword_18004D648 )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gIphlpTemplateFunc)(
        gIphlpEtwContext,
        xmmword_18004D648,
        L"HelperInitialize");
  }
  else
  {
    TraceHlp("HelperInitialize");
  }
  while ( _InterlockedIncrement(&HelperLock) > 1 )
  {
    _InterlockedDecrement(&HelperLock);
    if ( HelperInitialized )
    {
      _InterlockedIncrement(&HelperLock);
      if ( gIsIphlpEtwTracingAvailable )
      {
        if ( (_QWORD)xmmword_18004D648 )
        {
          LOWORD(v1) = 0;
          FormatRRASErrorString((wchar_t *)&v1, L"HelperInitialize ref count is  %d", (unsigned int)HelperLock);
          ((void (__fastcall *)(__int64, _QWORD, int *))gIphlpTemplateFunc)(gIphlpEtwContext, xmmword_18004D648, &v1);
        }
      }
      else
      {
        TraceHlp("HelperInitialize ref count is  %d");
      }
      goto LABEL_17;
    }
    Sleep(0x3E8u);
  }
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( (_QWORD)xmmword_18004D648 )
    {
      LOWORD(v1) = 0;
      FormatRRASErrorString((wchar_t *)&v1, L"HelperInitialize ref count is  %d", (unsigned int)HelperLock);
      ((void (__fastcall *)(__int64, _QWORD, int *))gIphlpTemplateFunc)(gIphlpEtwContext, xmmword_18004D648, &v1);
    }
  }
  else
  {
    TraceHlp("HelperInitialize ref count is  %d");
  }
  HelperInitialized = 1;
LABEL_17:
  if ( !gIsIphlpEtwTracingAvailable )
    goto LABEL_21;
  if ( !(_QWORD)xmmword_18004D648 )
  {
    if ( gIsIphlpEtwTracingAvailable )
      return 0;
LABEL_21:
    TraceHlp("HelperInitialize completed %d");
    return 0;
  }
  LOWORD(v1) = 0;
  FormatRRASErrorString((wchar_t *)&v1, L"HelperInitialize completed %d", 0);
  ((void (__fastcall *)(__int64, _QWORD, int *))gIphlpTemplateFunc)(gIphlpEtwContext, xmmword_18004D648, &v1);
  return 0;
}

```

## disassembly

```asm
0x180031dec  push    rbp
0x180031dee  lea     rbp, [rsp-730h]
0x180031df6  sub     rsp, 830h
0x180031dfd  mov     rax, cs:__security_cookie
0x180031e04  xor     rax, rsp
0x180031e07  mov     [rbp+730h+var_10], rax
0x180031e0e  xor     eax, eax
0x180031e10  lea     rcx, [rsp+830h+var_80C]; void *
0x180031e15  xor     edx, edx; Val
0x180031e17  mov     [rsp+830h+var_810], eax
0x180031e1b  mov     r8d, 7FCh; Size
0x180031e21  call    memset_0
0x180031e26  xor     edx, edx; dwFlags
0x180031e28  lea     rcx, szCallerName; "RASIPHLP"
0x180031e2f  call    cs:__imp_TraceRegisterExA
0x180031e36  nop     dword ptr [rax+rax+00h]
0x180031e3b  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x180031e42  mov     cs:HelperTraceId, eax
0x180031e48  jz      short loc_180031E72
0x180031e4a  mov     rdx, qword ptr cs:xmmword_18004D648
0x180031e51  test    rdx, rdx
0x180031e54  jz      short loc_180031E7E
0x180031e56  mov     rcx, cs:gIphlpEtwContext
0x180031e5d  lea     r8, aHelperinitiali_4; "HelperInitialize"
0x180031e64  mov     rax, cs:gIphlpTemplateFunc
0x180031e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031e70  jmp     short loc_180031E7E
0x180031e72  lea     rcx, aHelperinitiali; "HelperInitialize"
0x180031e79  call    TraceHlp
0x180031e7e  mov     eax, 1
0x180031e83  lock xadd cs:HelperLock, eax
0x180031e8b  inc     eax
0x180031e8d  cmp     eax, 1
0x180031e90  jle     loc_180031F2E
0x180031e96  lock dec cs:HelperLock
0x180031e9d  cmp     cs:HelperInitialized, 0
0x180031ea4  jnz     short loc_180031EB9
0x180031ea6  mov     ecx, 3E8h; dwMilliseconds
0x180031eab  call    cs:__imp_Sleep
0x180031eb2  nop     dword ptr [rax+rax+00h]
0x180031eb7  jmp     short loc_180031E7E
0x180031eb9  lock inc cs:HelperLock
0x180031ec0  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x180031ec7  jz      short loc_180031F1A
0x180031ec9  cmp     qword ptr cs:xmmword_18004D648, 0
0x180031ed1  jz      loc_180031F9D
0x180031ed7  mov     r8d, cs:HelperLock
0x180031ede  lea     rdx, aHelperinitiali_1; "HelperInitialize ref count is  %d"
0x180031ee5  xor     eax, eax
0x180031ee7  lea     rcx, [rsp+830h+var_810]
0x180031eec  mov     word ptr [rsp+830h+var_810], ax
0x180031ef1  call    FormatRRASErrorString
0x180031ef6  mov     rdx, qword ptr cs:xmmword_18004D648
0x180031efd  lea     r8, [rsp+830h+var_810]
0x180031f02  mov     rcx, cs:gIphlpEtwContext
0x180031f09  mov     rax, cs:gIphlpTemplateFunc
0x180031f10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f15  jmp     loc_180031F9D
0x180031f1a  mov     edx, cs:HelperLock
0x180031f20  lea     rcx, aHelperinitiali_0; "HelperInitialize ref count is  %d"
0x180031f27  call    TraceHlp
0x180031f2c  jmp     short loc_180031F9D
0x180031f2e  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x180031f35  jz      short loc_180031F81
0x180031f37  cmp     qword ptr cs:xmmword_18004D648, 0
0x180031f3f  jz      short loc_180031F93
0x180031f41  mov     r8d, cs:HelperLock
0x180031f48  lea     rdx, aHelperinitiali_1; "HelperInitialize ref count is  %d"
0x180031f4f  xor     eax, eax
0x180031f51  lea     rcx, [rsp+830h+var_810]
0x180031f56  mov     word ptr [rsp+830h+var_810], ax
0x180031f5b  call    FormatRRASErrorString
0x180031f60  mov     rdx, qword ptr cs:xmmword_18004D648
0x180031f67  lea     r8, [rsp+830h+var_810]
0x180031f6c  mov     rcx, cs:gIphlpEtwContext
0x180031f73  mov     rax, cs:gIphlpTemplateFunc
0x180031f7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f7f  jmp     short loc_180031F93
0x180031f81  mov     edx, cs:HelperLock
0x180031f87  lea     rcx, aHelperinitiali_0; "HelperInitialize ref count is  %d"
0x180031f8e  call    TraceHlp
0x180031f93  mov     cs:HelperInitialized, 1
0x180031f9d  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x180031fa4  jz      short loc_180031FF5
0x180031fa6  cmp     qword ptr cs:xmmword_18004D648, 0
0x180031fae  jz      short loc_180031FEC
0x180031fb0  xor     eax, eax
0x180031fb2  lea     rdx, aHelperinitiali_3; "HelperInitialize completed %d"
0x180031fb9  xor     r8d, r8d
0x180031fbc  mov     word ptr [rsp+830h+var_810], ax
0x180031fc1  lea     rcx, [rsp+830h+var_810]
0x180031fc6  call    FormatRRASErrorString
0x180031fcb  mov     rdx, qword ptr cs:xmmword_18004D648
0x180031fd2  lea     r8, [rsp+830h+var_810]
0x180031fd7  mov     rcx, cs:gIphlpEtwContext
0x180031fde  mov     rax, cs:gIphlpTemplateFunc
0x180031fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031fea  jmp     short loc_180032003
0x180031fec  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x180031ff3  jnz     short loc_180032003
0x180031ff5  xor     edx, edx
0x180031ff7  lea     rcx, aHelperinitiali_2; "HelperInitialize completed %d"
0x180031ffe  call    TraceHlp
0x180032003  xor     eax, eax
0x180032005  mov     rcx, [rbp+730h+var_10]
0x18003200c  xor     rcx, rsp; StackCookie
0x18003200f  call    __security_check_cookie
0x180032014  add     rsp, 830h
0x18003201b  pop     rbp
0x18003201c  retn
```
