# GetCallObjWithReadLock

- ea: `0x18008ed64`
- end: `0x18008eefb`
- name: `GetCallObjWithReadLock`
- size: `407`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `7`
- tags: ``

## callers

- `0x18008b5f8`
- `0x18008b828`
- `0x18008beac`
- `0x18008c2d8`
- `0x18008c578`
- `0x18008cb84`
- `0x18008f0a4`
- `0x18008f82c`

## callees

- `0x1800755b8`
- `0x18008ed64`
- `0x18008ff04`
- `0x180090714`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `rtutils!TracePrintfA` at `0x18008ee24`
- `rtutils!TracePrintfA` at `0x18008eebd`
- `rtutils!TracePrintfA` at `0x18008ee24`
- `rtutils!TracePrintfA` at `0x18008eebd`

## string_xrefs

- `0x18008ee1d`: `GetCallObjWithReadLock: GetObjWithReadLock failed (0x%x)`
- `0x18008edd6`: `GetCallObjWithReadLock: GetObjWithReadLock failed (0x%x)`
- `0x18008eeb3`: `GetCallObjWithReadLock: RasTapi call handle (0x%x) has bad key (0x%x)`
- `0x18008ee6d`: `GetCallObjWithReadLock: RasTapi call handle (0x%x) has bad key (0x%x)`

## pseudocode

```c
__int64 __fastcall GetCallObjWithReadLock(unsigned int a1, unsigned int **a2)
{
  unsigned int ObjWithReadLock; // eax
  unsigned int v5; // ebx
  unsigned int *v7; // [rsp+20h] [rbp-838h] BYREF
  int v8; // [rsp+30h] [rbp-828h] BYREF
  _BYTE v9[2044]; // [rsp+34h] [rbp-824h] BYREF

  v7 = 0;
  v8 = 0;
  memset_0(v9, 0, sizeof(v9));
  ObjWithReadLock = GetObjWithReadLock(a1, &v7);
  v5 = ObjWithReadLock;
  if ( ObjWithReadLock )
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800D0BE0 )
      {
        LOWORD(v8) = 0;
        FormatRRASErrorString(&v8, L"GetCallObjWithReadLock: GetObjWithReadLock failed (0x%x)", ObjWithReadLock);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v8);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "GetCallObjWithReadLock: GetObjWithReadLock failed (0x%x)", ObjWithReadLock);
    }
  }
  else if ( *v7 == 1229144396 || *v7 == 1329807692 )
  {
    *a2 = v7;
  }
  else
  {
    v5 = 6;
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800D0BE0 )
      {
        LOWORD(v8) = 0;
        FormatRRASErrorString(&v8, L"GetCallObjWithReadLock: RasTapi call handle (0x%x) has bad key (0x%x)", a1, *v7);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v8);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "GetCallObjWithReadLock: RasTapi call handle (0x%x) has bad key (0x%x)", a1, *v7);
    }
    ReleaseObjReadLock(a1);
  }
  return v5;
}

```

## disassembly

```asm
0x18008ed64  mov     [rsp+arg_10], rbx
0x18008ed69  push    rbp
0x18008ed6a  push    rsi
0x18008ed6b  push    rdi
0x18008ed6c  sub     rsp, 840h
0x18008ed73  mov     rax, cs:__security_cookie
0x18008ed7a  xor     rax, rsp
0x18008ed7d  mov     [rsp+858h+var_28], rax
0x18008ed85  mov     rsi, rdx
0x18008ed88  mov     edi, ecx
0x18008ed8a  xor     ebp, ebp
0x18008ed8c  lea     rcx, [rsp+858h+var_824]; void *
0x18008ed91  xor     edx, edx; Val
0x18008ed93  mov     [rsp+858h+var_838], rbp
0x18008ed98  mov     r8d, 7FCh; Size
0x18008ed9e  mov     [rsp+858h+var_828], ebp
0x18008eda2  call    memset_0
0x18008eda7  lea     rdx, [rsp+858h+var_838]
0x18008edac  mov     ecx, edi
0x18008edae  call    GetObjWithReadLock
0x18008edb3  mov     ebx, eax
0x18008edb5  test    eax, eax
0x18008edb7  jz      short loc_18008EE35
0x18008edb9  cmp     cs:gIsndpspEtwTracingAvailable, ebp
0x18008edbf  jz      short loc_18008EE0B
0x18008edc1  cmp     qword ptr cs:xmmword_1800D0BE0, rbp
0x18008edc8  jz      loc_18008EED5
0x18008edce  mov     r8d, eax
0x18008edd1  mov     word ptr [rsp+858h+var_828], bp
0x18008edd6  lea     rdx, aGetcallobjwith; "GetCallObjWithReadLock: GetObjWithReadL"...
0x18008eddd  lea     rcx, [rsp+858h+var_828]
0x18008ede2  call    FormatRRASErrorString
0x18008ede7  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008edee  lea     r8, [rsp+858h+var_828]
0x18008edf3  mov     rcx, cs:gNdpspEtwContext
0x18008edfa  mov     rax, cs:gNdpspTemplateFunc
0x18008ee01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ee06  jmp     loc_18008EED5
0x18008ee0b  mov     ecx, cs:dwTraceId; dwTraceID
0x18008ee11  cmp     ecx, 0FFFFFFFFh
0x18008ee14  jz      loc_18008EED5
0x18008ee1a  mov     r8d, eax
0x18008ee1d  lea     rdx, aGetcallobjwith_4; "GetCallObjWithReadLock: GetObjWithReadL"...
0x18008ee24  call    cs:__imp_TracePrintfA
0x18008ee2b  nop     dword ptr [rax+rax+00h]
0x18008ee30  jmp     loc_18008EED5
0x18008ee35  mov     rax, [rsp+858h+var_838]
0x18008ee3a  cmp     dword ptr [rax], 4943414Ch
0x18008ee40  jz      loc_18008EED2
0x18008ee46  cmp     dword ptr [rax], 4F43414Ch
0x18008ee4c  jz      loc_18008EED2
0x18008ee52  cmp     cs:gIsndpspEtwTracingAvailable, ebp
0x18008ee58  mov     ebx, 6
0x18008ee5d  jz      short loc_18008EEA5
0x18008ee5f  cmp     qword ptr cs:xmmword_1800D0BE0, rbp
0x18008ee66  jz      short loc_18008EEC9
0x18008ee68  mov     word ptr [rsp+858h+var_828], bp
0x18008ee6d  lea     rdx, aGetcallobjwith_0; "GetCallObjWithReadLock: RasTapi call ha"...
0x18008ee74  mov     r9d, [rax]
0x18008ee77  lea     rcx, [rsp+858h+var_828]
0x18008ee7c  mov     r8d, edi
0x18008ee7f  call    FormatRRASErrorString
0x18008ee84  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008ee8b  lea     r8, [rsp+858h+var_828]
0x18008ee90  mov     rcx, cs:gNdpspEtwContext
0x18008ee97  mov     rax, cs:gNdpspTemplateFunc
0x18008ee9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008eea3  jmp     short loc_18008EEC9
0x18008eea5  mov     ecx, cs:dwTraceId; dwTraceID
0x18008eeab  cmp     ecx, 0FFFFFFFFh
0x18008eeae  jz      short loc_18008EEC9
0x18008eeb0  mov     r9d, [rax]
0x18008eeb3  lea     rdx, aGetcallobjwith_3; "GetCallObjWithReadLock: RasTapi call ha"...
0x18008eeba  mov     r8d, edi
0x18008eebd  call    cs:__imp_TracePrintfA
0x18008eec4  nop     dword ptr [rax+rax+00h]
0x18008eec9  mov     ecx, edi
0x18008eecb  call    ReleaseObjReadLock
0x18008eed0  jmp     short loc_18008EED5
0x18008eed2  mov     [rsi], rax
0x18008eed5  mov     eax, ebx
0x18008eed7  mov     rcx, [rsp+858h+var_28]
0x18008eedf  xor     rcx, rsp; StackCookie
0x18008eee2  call    __security_check_cookie
0x18008eee7  mov     rbx, [rsp+858h+arg_10]
0x18008eeef  add     rsp, 840h
0x18008eef6  pop     rdi
0x18008eef7  pop     rsi
0x18008eef8  pop     rbp
0x18008eef9  retn
```
