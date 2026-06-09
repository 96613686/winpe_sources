# GetCallObjWithWriteLock

- ea: `0x180088cc0`
- end: `0x180088e5e`
- name: `GetCallObjWithWriteLock`
- size: `414`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180084ae0`
- `0x1800876d0`

## callees

- `0x180071cec`
- `0x180088cc0`
- `0x180089da8`
- `0x18008a51c`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `rtutils!TracePrintfA` at `0x180088d8f`
- `rtutils!TracePrintfA` at `0x180088e23`
- `rtutils!TracePrintfA` at `0x180088d8f`
- `rtutils!TracePrintfA` at `0x180088e23`

## string_xrefs

- `0x180088d88`: `GetCallObjWithWriteLock: GetObjWithWriteLock failed (0x%x)`
- `0x180088d39`: `GetCallObjWithWriteLock: GetObjWithWriteLock failed (0x%x)`
- `0x180088e17`: `GetCallObjWithWriteLock: RasTapi call handle (0x%x) has bad key (0x%x)`
- `0x180088dcc`: `GetCallObjWithWriteLock: RasTapi call handle (0x%x) has bad key (0x%x)`

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
      if ( (_QWORD)xmmword_1800C9BE0 )
      {
        LOWORD(v8) = 0;
        FormatRRASErrorString(&v8, L"GetCallObjWithWriteLock: GetObjWithWriteLock failed (0x%x)", v4);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v8);
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
      if ( (_QWORD)xmmword_1800C9BE0 )
      {
        LOWORD(v8) = 0;
        FormatRRASErrorString(&v8, L"GetCallObjWithWriteLock: RasTapi call handle (0x%x) has bad key (0x%x)", a1, *v7);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v8);
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
0x180088cc0  mov     [rsp-8+arg_10], rbx
0x180088cc5  push    rbp
0x180088cc6  push    rsi
0x180088cc7  push    rdi
0x180088cc8  lea     rbp, [rsp-740h]
0x180088cd0  sub     rsp, 840h
0x180088cd7  mov     rax, cs:__security_cookie
0x180088cde  xor     rax, rsp
0x180088ce1  mov     [rbp+750h+var_20], rax
0x180088ce8  mov     rsi, rdx
0x180088ceb  mov     [rsp+850h+var_830], 0
0x180088cf4  mov     edi, ecx
0x180088cf6  xor     eax, eax
0x180088cf8  xor     edx, edx; Val
0x180088cfa  mov     [rsp+850h+var_820], eax
0x180088cfe  lea     rcx, [rsp+850h+var_81C]; void *
0x180088d03  mov     r8d, 7FCh; Size
0x180088d09  call    memset_0
0x180088d0e  lea     rdx, [rsp+850h+var_830]
0x180088d13  mov     ecx, edi
0x180088d15  call    GetObjWithWriteLock
0x180088d1a  mov     ebx, eax
0x180088d1c  test    eax, eax
0x180088d1e  jz      short loc_180088D9A
0x180088d20  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x180088d27  jz      short loc_180088D76
0x180088d29  cmp     qword ptr cs:xmmword_1800C9BE0, 0
0x180088d31  jz      loc_180088E3A
0x180088d37  xor     ecx, ecx
0x180088d39  lea     rdx, aGetcallobjwith_6; "GetCallObjWithWriteLock: GetObjWithWrit"...
0x180088d40  mov     word ptr [rsp+850h+var_820], cx
0x180088d45  mov     r8d, eax
0x180088d48  lea     rcx, [rsp+850h+var_820]
0x180088d4d  call    FormatRRASErrorString
0x180088d52  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180088d59  lea     r8, [rsp+850h+var_820]
0x180088d5e  mov     rcx, cs:gNdpspEtwContext
0x180088d65  mov     rax, cs:gNdpspTemplateFunc
0x180088d6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088d71  jmp     loc_180088E3A
0x180088d76  mov     ecx, cs:dwTraceId; dwTraceID
0x180088d7c  cmp     ecx, 0FFFFFFFFh
0x180088d7f  jz      loc_180088E3A
0x180088d85  mov     r8d, eax
0x180088d88  lea     rdx, aGetcallobjwith_1; "GetCallObjWithWriteLock: GetObjWithWrit"...
0x180088d8f  call    cs:__imp_TracePrintfA
0x180088d95  jmp     loc_180088E3A
0x180088d9a  mov     rcx, [rsp+850h+var_830]
0x180088d9f  cmp     dword ptr [rcx], 4943414Ch
0x180088da5  jz      loc_180088E37
0x180088dab  cmp     dword ptr [rcx], 4F43414Ch
0x180088db1  jz      loc_180088E37
0x180088db7  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x180088dbe  jz      short loc_180088E09
0x180088dc0  cmp     qword ptr cs:xmmword_1800C9BE0, 0
0x180088dc8  jz      short loc_180088E29
0x180088dca  xor     eax, eax
0x180088dcc  lea     rdx, aGetcallobjwith_2; "GetCallObjWithWriteLock: RasTapi call h"...
0x180088dd3  mov     word ptr [rsp+850h+var_820], ax
0x180088dd8  mov     r8d, edi
0x180088ddb  mov     r9d, [rcx]
0x180088dde  lea     rcx, [rsp+850h+var_820]
0x180088de3  call    FormatRRASErrorString
0x180088de8  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180088def  lea     r8, [rsp+850h+var_820]
0x180088df4  mov     rcx, cs:gNdpspEtwContext
0x180088dfb  mov     rax, cs:gNdpspTemplateFunc
0x180088e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088e07  jmp     short loc_180088E29
0x180088e09  mov     eax, cs:dwTraceId
0x180088e0f  cmp     eax, 0FFFFFFFFh
0x180088e12  jz      short loc_180088E29
0x180088e14  mov     r9d, [rcx]
0x180088e17  lea     rdx, aGetcallobjwith_5; "GetCallObjWithWriteLock: RasTapi call h"...
0x180088e1e  mov     ecx, eax; dwTraceID
0x180088e20  mov     r8d, edi
0x180088e23  call    cs:__imp_TracePrintfA
0x180088e29  mov     ecx, edi
0x180088e2b  mov     ebx, 6
0x180088e30  call    ReleaseObjWriteLock
0x180088e35  jmp     short loc_180088E3A
0x180088e37  mov     [rsi], rcx
0x180088e3a  mov     eax, ebx
0x180088e3c  mov     rcx, [rbp+750h+var_20]
0x180088e43  xor     rcx, rsp; StackCookie
0x180088e46  call    __security_check_cookie
0x180088e4b  mov     rbx, [rsp+850h+arg_10]
0x180088e53  add     rsp, 840h
0x180088e5a  pop     rdi
0x180088e5b  pop     rsi
0x180088e5c  pop     rbp
0x180088e5d  retn
```
