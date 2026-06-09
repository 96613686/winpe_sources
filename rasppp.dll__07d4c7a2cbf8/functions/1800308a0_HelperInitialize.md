# HelperInitialize

- ea: `0x1800308a0`
- end: `0x180030ac5`
- name: `HelperInitialize`
- size: `549`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001d9c0`
- `0x180022590`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18002a138`
- `0x1800308a0`
- `0x180030da4`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180030959`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180030959`
- `rtutils!TraceRegisterExA` at `0x1800308e3`
- `rtutils!TraceRegisterExA` at `0x1800308e3`

## string_xrefs

- `0x180030a5a`: `HelperInitialize completed %d`
- `0x180030a9f`: `HelperInitialize completed %d`

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
    if ( qword_18004C648 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(
        gIphlpEtwContext,
        qword_18004C648,
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
        if ( qword_18004C648 )
        {
          LOWORD(v1) = 0;
          FormatRRASErrorString(&v1, L"HelperInitialize ref count is  %d", (unsigned int)HelperLock);
          ((void (__fastcall *)(__int64, __int64, int *))gIphlpTemplateFunc)(gIphlpEtwContext, qword_18004C648, &v1);
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
    if ( qword_18004C648 )
    {
      LOWORD(v1) = 0;
      FormatRRASErrorString(&v1, L"HelperInitialize ref count is  %d", (unsigned int)HelperLock);
      ((void (__fastcall *)(__int64, __int64, int *))gIphlpTemplateFunc)(gIphlpEtwContext, qword_18004C648, &v1);
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
  if ( !qword_18004C648 )
  {
    if ( gIsIphlpEtwTracingAvailable )
      return 0;
LABEL_21:
    TraceHlp("HelperInitialize completed %d");
    return 0;
  }
  LOWORD(v1) = 0;
  FormatRRASErrorString(&v1, L"HelperInitialize completed %d", 0);
  ((void (__fastcall *)(__int64, __int64, int *))gIphlpTemplateFunc)(gIphlpEtwContext, qword_18004C648, &v1);
  return 0;
}

```

## disassembly

```asm
0x1800308a0  push    rbp
0x1800308a2  lea     rbp, [rsp-730h]
0x1800308aa  sub     rsp, 830h
0x1800308b1  mov     rax, cs:__security_cookie
0x1800308b8  xor     rax, rsp
0x1800308bb  mov     [rbp+730h+var_10], rax
0x1800308c2  xor     eax, eax
0x1800308c4  lea     rcx, [rsp+830h+var_80C]; void *
0x1800308c9  xor     edx, edx; Val
0x1800308cb  mov     [rsp+830h+var_810], eax
0x1800308cf  mov     r8d, 7FCh; Size
0x1800308d5  call    memset_0
0x1800308da  xor     edx, edx; dwFlags
0x1800308dc  lea     rcx, szCallerName; "RASIPHLP"
0x1800308e3  call    cs:__imp_TraceRegisterExA
0x1800308e9  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x1800308f0  mov     cs:HelperTraceId, eax
0x1800308f6  jz      short loc_180030920
0x1800308f8  mov     rdx, cs:qword_18004C648
0x1800308ff  test    rdx, rdx
0x180030902  jz      short loc_18003092C
0x180030904  mov     rcx, cs:gIphlpEtwContext
0x18003090b  lea     r8, aHelperinitiali_4; "HelperInitialize"
0x180030912  mov     rax, cs:gIphlpTemplateFunc
0x180030919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003091e  jmp     short loc_18003092C
0x180030920  lea     rcx, aHelperinitiali; "HelperInitialize"
0x180030927  call    TraceHlp
0x18003092c  mov     eax, 1
0x180030931  lock xadd cs:HelperLock, eax
0x180030939  inc     eax
0x18003093b  cmp     eax, 1
0x18003093e  jle     loc_1800309D6
0x180030944  lock dec cs:HelperLock
0x18003094b  cmp     cs:HelperInitialized, 0
0x180030952  jnz     short loc_180030961
0x180030954  mov     ecx, 3E8h; dwMilliseconds
0x180030959  call    cs:__imp_Sleep
0x18003095f  jmp     short loc_18003092C
0x180030961  lock inc cs:HelperLock
0x180030968  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x18003096f  jz      short loc_1800309C2
0x180030971  cmp     cs:qword_18004C648, 0
0x180030979  jz      loc_180030A45
0x18003097f  mov     r8d, cs:HelperLock
0x180030986  lea     rdx, aHelperinitiali_1; "HelperInitialize ref count is  %d"
0x18003098d  xor     eax, eax
0x18003098f  lea     rcx, [rsp+830h+var_810]
0x180030994  mov     word ptr [rsp+830h+var_810], ax
0x180030999  call    FormatRRASErrorString
0x18003099e  mov     rdx, cs:qword_18004C648
0x1800309a5  lea     r8, [rsp+830h+var_810]
0x1800309aa  mov     rcx, cs:gIphlpEtwContext
0x1800309b1  mov     rax, cs:gIphlpTemplateFunc
0x1800309b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800309bd  jmp     loc_180030A45
0x1800309c2  mov     edx, cs:HelperLock
0x1800309c8  lea     rcx, aHelperinitiali_0; "HelperInitialize ref count is  %d"
0x1800309cf  call    TraceHlp
0x1800309d4  jmp     short loc_180030A45
0x1800309d6  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x1800309dd  jz      short loc_180030A29
0x1800309df  cmp     cs:qword_18004C648, 0
0x1800309e7  jz      short loc_180030A3B
0x1800309e9  mov     r8d, cs:HelperLock
0x1800309f0  lea     rdx, aHelperinitiali_1; "HelperInitialize ref count is  %d"
0x1800309f7  xor     eax, eax
0x1800309f9  lea     rcx, [rsp+830h+var_810]
0x1800309fe  mov     word ptr [rsp+830h+var_810], ax
0x180030a03  call    FormatRRASErrorString
0x180030a08  mov     rdx, cs:qword_18004C648
0x180030a0f  lea     r8, [rsp+830h+var_810]
0x180030a14  mov     rcx, cs:gIphlpEtwContext
0x180030a1b  mov     rax, cs:gIphlpTemplateFunc
0x180030a22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a27  jmp     short loc_180030A3B
0x180030a29  mov     edx, cs:HelperLock
0x180030a2f  lea     rcx, aHelperinitiali_0; "HelperInitialize ref count is  %d"
0x180030a36  call    TraceHlp
0x180030a3b  mov     cs:HelperInitialized, 1
0x180030a45  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x180030a4c  jz      short loc_180030A9D
0x180030a4e  cmp     cs:qword_18004C648, 0
0x180030a56  jz      short loc_180030A94
0x180030a58  xor     eax, eax
0x180030a5a  lea     rdx, aHelperinitiali_3; "HelperInitialize completed %d"
0x180030a61  xor     r8d, r8d
0x180030a64  mov     word ptr [rsp+830h+var_810], ax
0x180030a69  lea     rcx, [rsp+830h+var_810]
0x180030a6e  call    FormatRRASErrorString
0x180030a73  mov     rdx, cs:qword_18004C648
0x180030a7a  lea     r8, [rsp+830h+var_810]
0x180030a7f  mov     rcx, cs:gIphlpEtwContext
0x180030a86  mov     rax, cs:gIphlpTemplateFunc
0x180030a8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a92  jmp     short loc_180030AAB
0x180030a94  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x180030a9b  jnz     short loc_180030AAB
0x180030a9d  xor     edx, edx
0x180030a9f  lea     rcx, aHelperinitiali_2; "HelperInitialize completed %d"
0x180030aa6  call    TraceHlp
0x180030aab  xor     eax, eax
0x180030aad  mov     rcx, [rbp+730h+var_10]
0x180030ab4  xor     rcx, rsp; StackCookie
0x180030ab7  call    __security_check_cookie
0x180030abc  add     rsp, 830h
0x180030ac3  pop     rbp
0x180030ac4  retn
```
