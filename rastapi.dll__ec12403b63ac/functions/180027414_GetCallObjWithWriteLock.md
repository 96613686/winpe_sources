# GetCallObjWithWriteLock

- ea: `0x180027414`
- end: `0x1800275b2`
- name: `GetCallObjWithWriteLock`
- size: `414`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800226f0`
- `0x180025e40`

## callees

- `0x180027414`
- `0x1800284fc`
- `0x180028c70`
- `0x180029130`
- `0x18002927e`
- `0x1800292b0`
- `0x18002a010`

## import_xrefs

- `rtutils!TracePrintfA` at `0x1800274e3`
- `rtutils!TracePrintfA` at `0x180027577`
- `rtutils!TracePrintfA` at `0x1800274e3`
- `rtutils!TracePrintfA` at `0x180027577`

## string_xrefs

- `0x18002748d`: `GetCallObjWithWriteLock: GetObjWithWriteLock failed (0x%x)`
- `0x1800274dc`: `GetCallObjWithWriteLock: GetObjWithWriteLock failed (0x%x)`
- `0x180027520`: `GetCallObjWithWriteLock: RasTapi call handle (0x%x) has bad key (0x%x)`
- `0x18002756b`: `GetCallObjWithWriteLock: RasTapi call handle (0x%x) has bad key (0x%x)`

## pseudocode

```c
__int64 __fastcall GetCallObjWithWriteLock(unsigned int a1, unsigned int **a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  unsigned int *v7; // [rsp+20h] [rbp-E0h] BYREF
  int v8; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v9[2044]; // [rsp+34h] [rbp-CCh] BYREF

  v7 = 0;
  v8 = 0;
  memset_0(v9, 0, sizeof(v9));
  v4 = GetObjWithWriteLock(a1, &v7);
  v5 = v4;
  if ( v4 )
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( qword_18003EC40 )
      {
        LOWORD(v8) = 0;
        FormatRRASErrorString(&v8, L"GetCallObjWithWriteLock: GetObjWithWriteLock failed (0x%x)", v4);
        ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v8);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "GetCallObjWithWriteLock: GetObjWithWriteLock failed (0x%x)", v4);
    }
  }
  else if ( *v7 == 1229144396 || *v7 == 1329807692 )
  {
    *a2 = v7;
  }
  else
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( qword_18003EC40 )
      {
        LOWORD(v8) = 0;
        FormatRRASErrorString(&v8, L"GetCallObjWithWriteLock: RasTapi call handle (0x%x) has bad key (0x%x)", a1, *v7);
        ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v8);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "GetCallObjWithWriteLock: RasTapi call handle (0x%x) has bad key (0x%x)", a1, *v7);
    }
    v5 = 6;
    ReleaseObjWriteLock(a1);
  }
  return v5;
}

```

## disassembly

```asm
0x180027414  mov     [rsp-8+arg_10], rbx
0x180027419  push    rbp
0x18002741a  push    rsi
0x18002741b  push    rdi
0x18002741c  lea     rbp, [rsp-740h]
0x180027424  sub     rsp, 840h
0x18002742b  mov     rax, cs:__security_cookie
0x180027432  xor     rax, rsp
0x180027435  mov     [rbp+750h+var_20], rax
0x18002743c  mov     rsi, rdx
0x18002743f  mov     [rsp+850h+var_830], 0
0x180027448  mov     edi, ecx
0x18002744a  xor     eax, eax
0x18002744c  xor     edx, edx; Val
0x18002744e  mov     [rsp+850h+var_820], eax
0x180027452  lea     rcx, [rsp+850h+var_81C]; void *
0x180027457  mov     r8d, 7FCh; Size
0x18002745d  call    memset_0
0x180027462  lea     rdx, [rsp+850h+var_830]
0x180027467  mov     ecx, edi
0x180027469  call    GetObjWithWriteLock
0x18002746e  mov     ebx, eax
0x180027470  test    eax, eax
0x180027472  jz      short loc_1800274EE
0x180027474  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x18002747b  jz      short loc_1800274CA
0x18002747d  cmp     cs:qword_18003EC40, 0
0x180027485  jz      loc_18002758E
0x18002748b  xor     ecx, ecx
0x18002748d  lea     rdx, aGetcallobjwith_6; "GetCallObjWithWriteLock: GetObjWithWrit"...
0x180027494  mov     word ptr [rsp+850h+var_820], cx
0x180027499  mov     r8d, eax
0x18002749c  lea     rcx, [rsp+850h+var_820]
0x1800274a1  call    FormatRRASErrorString
0x1800274a6  mov     rdx, cs:qword_18003EC40
0x1800274ad  lea     r8, [rsp+850h+var_820]
0x1800274b2  mov     rcx, cs:gNdpspEtwContext
0x1800274b9  mov     rax, cs:gNdpspTemplateFunc
0x1800274c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800274c5  jmp     loc_18002758E
0x1800274ca  mov     ecx, cs:dwTraceId; dwTraceID
0x1800274d0  cmp     ecx, 0FFFFFFFFh
0x1800274d3  jz      loc_18002758E
0x1800274d9  mov     r8d, eax
0x1800274dc  lea     rdx, aGetcallobjwith_1; "GetCallObjWithWriteLock: GetObjWithWrit"...
0x1800274e3  call    cs:__imp_TracePrintfA
0x1800274e9  jmp     loc_18002758E
0x1800274ee  mov     rcx, [rsp+850h+var_830]
0x1800274f3  cmp     dword ptr [rcx], 4943414Ch
0x1800274f9  jz      loc_18002758B
0x1800274ff  cmp     dword ptr [rcx], 4F43414Ch
0x180027505  jz      loc_18002758B
0x18002750b  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x180027512  jz      short loc_18002755D
0x180027514  cmp     cs:qword_18003EC40, 0
0x18002751c  jz      short loc_18002757D
0x18002751e  xor     eax, eax
0x180027520  lea     rdx, aGetcallobjwith_2; "GetCallObjWithWriteLock: RasTapi call h"...
0x180027527  mov     word ptr [rsp+850h+var_820], ax
0x18002752c  mov     r8d, edi
0x18002752f  mov     r9d, [rcx]
0x180027532  lea     rcx, [rsp+850h+var_820]
0x180027537  call    FormatRRASErrorString
0x18002753c  mov     rdx, cs:qword_18003EC40
0x180027543  lea     r8, [rsp+850h+var_820]
0x180027548  mov     rcx, cs:gNdpspEtwContext
0x18002754f  mov     rax, cs:gNdpspTemplateFunc
0x180027556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002755b  jmp     short loc_18002757D
0x18002755d  mov     eax, cs:dwTraceId
0x180027563  cmp     eax, 0FFFFFFFFh
0x180027566  jz      short loc_18002757D
0x180027568  mov     r9d, [rcx]
0x18002756b  lea     rdx, aGetcallobjwith_5; "GetCallObjWithWriteLock: RasTapi call h"...
0x180027572  mov     ecx, eax; dwTraceID
0x180027574  mov     r8d, edi
0x180027577  call    cs:__imp_TracePrintfA
0x18002757d  mov     ecx, edi
0x18002757f  mov     ebx, 6
0x180027584  call    ReleaseObjWriteLock
0x180027589  jmp     short loc_18002758E
0x18002758b  mov     [rsi], rcx
0x18002758e  mov     eax, ebx
0x180027590  mov     rcx, [rbp+750h+var_20]
0x180027597  xor     rcx, rsp; StackCookie
0x18002759a  call    __security_check_cookie
0x18002759f  mov     rbx, [rsp+850h+arg_10]
0x1800275a7  add     rsp, 840h
0x1800275ae  pop     rdi
0x1800275af  pop     rsi
0x1800275b0  pop     rbp
0x1800275b1  retn
```
