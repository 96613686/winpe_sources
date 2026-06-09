# FwppSubscriptionCreate

- ea: `0x180002930`
- end: `0x180002a0e`
- name: `FwppSubscriptionCreate`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180002008`

## callees

- `0x180002930`
- `0x1800034e0`
- `0x180005fc8`
- `0x180007e38`
- `0x18000e820`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800029bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800029bc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800029a7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800029a7`

## string_xrefs

- `0x1800029cb`: `CreateEventW`
- `0x1800029e9`: `FwppSubscriptionCreate`

## pseudocode

```c
__int64 __fastcall FwppSubscriptionCreate(__int64 a1, __int64 a2, __int64 a3, unsigned __int64 a4, _QWORD *a5)
{
  _QWORD *v5; // rsi
  SIZE_T v9; // rcx
  __int64 v10; // rbx
  __int64 v11; // rdi
  HANDLE EventW; // rax
  DWORD LastError; // eax
  __int64 v14; // rcx
  __int64 v16; // [rsp+78h] [rbp+20h] BYREF

  v5 = a5;
  v16 = 0;
  v9 = 72;
  *a5 = 0;
  if ( a4 > 8 )
    v9 = a4 + 64;
  v10 = WfpMemAlloc(v9, 8u);
  if ( v10 )
    goto LABEL_6;
  v11 = v16;
  *(_QWORD *)(v16 + 16) = a1;
  *(_QWORD *)(v11 + 24) = a1;
  *(_QWORD *)(v11 + 32) = a2;
  *(_QWORD *)(v11 + 40) = a3;
  *(_DWORD *)(v11 + 48) = 1;
  EventW = CreateEventW(0, 1, 0, 0);
  *(_QWORD *)(v11 + 56) = EventW;
  if ( EventW )
  {
    *v5 = v11;
    return v10;
  }
  LastError = GetLastError();
  v10 = WfpReportSysErrorAsWinError(v14, "CreateEventW", LastError);
  if ( v10 )
  {
LABEL_6:
    FwppSubscriptionDestroy(&v16);
    WfpReportError(v10, "FwppSubscriptionCreate");
  }
  return v10;
}

```

## disassembly

```asm
0x180002930  push    rbx
0x180002932  push    rbp
0x180002933  push    rsi
0x180002934  push    rdi
0x180002935  push    r14
0x180002937  push    r15
0x180002939  sub     rsp, 28h
0x18000293d  mov     rsi, [rsp+58h+arg_20]
0x180002945  mov     rbp, rcx
0x180002948  mov     [rsp+58h+arg_18], 0
0x180002951  mov     r14, r8
0x180002954  mov     r15, rdx
0x180002957  mov     ecx, 48h ; 'H'
0x18000295c  mov     qword ptr [rsi], 0
0x180002963  cmp     r9, 8
0x180002967  jbe     short loc_18000296D
0x180002969  lea     rcx, [r9+40h]; dwBytes
0x18000296d  lea     r8, [rsp+58h+arg_18]
0x180002972  mov     edx, 8; dwFlags
0x180002977  call    WfpMemAlloc
0x18000297c  mov     rbx, rax
0x18000297f  test    rax, rax
0x180002982  jnz     short loc_1800029DF
0x180002984  mov     rdi, [rsp+58h+arg_18]
0x180002989  lea     edx, [rax+1]; bManualReset
0x18000298c  xor     r9d, r9d; lpName
0x18000298f  xor     r8d, r8d; bInitialState
0x180002992  xor     ecx, ecx; lpEventAttributes
0x180002994  mov     [rdi+10h], rbp
0x180002998  mov     [rdi+18h], rbp
0x18000299c  mov     [rdi+20h], r15
0x1800029a0  mov     [rdi+28h], r14
0x1800029a4  mov     [rdi+30h], edx
0x1800029a7  call    cs:__imp_CreateEventW
0x1800029ae  nop     dword ptr [rax+rax+00h]
0x1800029b3  mov     [rdi+38h], rax
0x1800029b7  test    rax, rax
0x1800029ba  jnz     short loc_180002A09
0x1800029bc  call    cs:__imp_GetLastError
0x1800029c3  nop     dword ptr [rax+rax+00h]
0x1800029c8  mov     r8d, eax
0x1800029cb  lea     rdx, aCreateeventw; "CreateEventW"
0x1800029d2  call    WfpReportSysErrorAsWinError
0x1800029d7  mov     rbx, rax
0x1800029da  test    rax, rax
0x1800029dd  jz      short loc_1800029F8
0x1800029df  lea     rcx, [rsp+58h+arg_18]
0x1800029e4  call    FwppSubscriptionDestroy
0x1800029e9  lea     rdx, aFwppsubscripti; "FwppSubscriptionCreate"
0x1800029f0  mov     rcx, rbx
0x1800029f3  call    WfpReportError
0x1800029f8  mov     rax, rbx
0x1800029fb  add     rsp, 28h
0x1800029ff  pop     r15
0x180002a01  pop     r14
0x180002a03  pop     rdi
0x180002a04  pop     rsi
0x180002a05  pop     rbp
0x180002a06  pop     rbx
0x180002a07  retn
0x180002a09  mov     [rsi], rdi
0x180002a0c  jmp     short loc_1800029F8
```
