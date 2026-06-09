# GetCallObjWithReadLock

- ea: `0x180088b1c`
- end: `0x180088cba`
- name: `GetCallObjWithReadLock`
- size: `414`
- prototype: ``
- caller_count: `8`
- callee_count: `7`
- tags: ``

## callers

- `0x1800855e8`
- `0x180085818`
- `0x180085e4c`
- `0x18008625c`
- `0x1800864d8`
- `0x180086ad0`
- `0x180088e64`
- `0x1800895e4`

## callees

- `0x180071cec`
- `0x180088b1c`
- `0x180089c44`
- `0x18008a408`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `rtutils!TracePrintfA` at `0x180088beb`
- `rtutils!TracePrintfA` at `0x180088c7f`
- `rtutils!TracePrintfA` at `0x180088beb`
- `rtutils!TracePrintfA` at `0x180088c7f`

## string_xrefs

- `0x180088be4`: `GetCallObjWithReadLock: GetObjWithReadLock failed (0x%x)`
- `0x180088b95`: `GetCallObjWithReadLock: GetObjWithReadLock failed (0x%x)`
- `0x180088c73`: `GetCallObjWithReadLock: RasTapi call handle (0x%x) has bad key (0x%x)`
- `0x180088c28`: `GetCallObjWithReadLock: RasTapi call handle (0x%x) has bad key (0x%x)`

## pseudocode

```c
__int64 __fastcall GetCallObjWithReadLock(unsigned int a1, unsigned int **a2)
{
  unsigned int ObjWithReadLock; // eax
  unsigned int v5; // ebx
  unsigned int *v7; // [rsp+20h] [rbp-E0h] BYREF
  int v8; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v9[2044]; // [rsp+34h] [rbp-CCh] BYREF

  v7 = 0;
  v8 = 0;
  memset_0(v9, 0, sizeof(v9));
  ObjWithReadLock = GetObjWithReadLock(a1, &v7);
  v5 = ObjWithReadLock;
  if ( ObjWithReadLock )
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800C9BE0 )
      {
        LOWORD(v8) = 0;
        FormatRRASErrorString(&v8, L"GetCallObjWithReadLock: GetObjWithReadLock failed (0x%x)", ObjWithReadLock);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v8);
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
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800C9BE0 )
      {
        LOWORD(v8) = 0;
        FormatRRASErrorString(&v8, L"GetCallObjWithReadLock: RasTapi call handle (0x%x) has bad key (0x%x)", a1, *v7);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v8);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "GetCallObjWithReadLock: RasTapi call handle (0x%x) has bad key (0x%x)", a1, *v7);
    }
    v5 = 6;
    ReleaseObjReadLock(a1);
  }
  return v5;
}

```

## disassembly

```asm
0x180088b1c  mov     [rsp-8+arg_10], rbx
0x180088b21  push    rbp
0x180088b22  push    rsi
0x180088b23  push    rdi
0x180088b24  lea     rbp, [rsp-740h]
0x180088b2c  sub     rsp, 840h
0x180088b33  mov     rax, cs:__security_cookie
0x180088b3a  xor     rax, rsp
0x180088b3d  mov     [rbp+750h+var_20], rax
0x180088b44  mov     rsi, rdx
0x180088b47  mov     [rsp+850h+var_830], 0
0x180088b50  mov     edi, ecx
0x180088b52  xor     eax, eax
0x180088b54  xor     edx, edx; Val
0x180088b56  mov     [rsp+850h+var_820], eax
0x180088b5a  lea     rcx, [rsp+850h+var_81C]; void *
0x180088b5f  mov     r8d, 7FCh; Size
0x180088b65  call    memset_0
0x180088b6a  lea     rdx, [rsp+850h+var_830]
0x180088b6f  mov     ecx, edi
0x180088b71  call    GetObjWithReadLock
0x180088b76  mov     ebx, eax
0x180088b78  test    eax, eax
0x180088b7a  jz      short loc_180088BF6
0x180088b7c  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x180088b83  jz      short loc_180088BD2
0x180088b85  cmp     qword ptr cs:xmmword_1800C9BE0, 0
0x180088b8d  jz      loc_180088C96
0x180088b93  xor     ecx, ecx
0x180088b95  lea     rdx, aGetcallobjwith; "GetCallObjWithReadLock: GetObjWithReadL"...
0x180088b9c  mov     word ptr [rsp+850h+var_820], cx
0x180088ba1  mov     r8d, eax
0x180088ba4  lea     rcx, [rsp+850h+var_820]
0x180088ba9  call    FormatRRASErrorString
0x180088bae  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180088bb5  lea     r8, [rsp+850h+var_820]
0x180088bba  mov     rcx, cs:gNdpspEtwContext
0x180088bc1  mov     rax, cs:gNdpspTemplateFunc
0x180088bc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088bcd  jmp     loc_180088C96
0x180088bd2  mov     ecx, cs:dwTraceId; dwTraceID
0x180088bd8  cmp     ecx, 0FFFFFFFFh
0x180088bdb  jz      loc_180088C96
0x180088be1  mov     r8d, eax
0x180088be4  lea     rdx, aGetcallobjwith_4; "GetCallObjWithReadLock: GetObjWithReadL"...
0x180088beb  call    cs:__imp_TracePrintfA
0x180088bf1  jmp     loc_180088C96
0x180088bf6  mov     rcx, [rsp+850h+var_830]
0x180088bfb  cmp     dword ptr [rcx], 4943414Ch
0x180088c01  jz      loc_180088C93
0x180088c07  cmp     dword ptr [rcx], 4F43414Ch
0x180088c0d  jz      loc_180088C93
0x180088c13  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x180088c1a  jz      short loc_180088C65
0x180088c1c  cmp     qword ptr cs:xmmword_1800C9BE0, 0
0x180088c24  jz      short loc_180088C85
0x180088c26  xor     eax, eax
0x180088c28  lea     rdx, aGetcallobjwith_0; "GetCallObjWithReadLock: RasTapi call ha"...
0x180088c2f  mov     word ptr [rsp+850h+var_820], ax
0x180088c34  mov     r8d, edi
0x180088c37  mov     r9d, [rcx]
0x180088c3a  lea     rcx, [rsp+850h+var_820]
0x180088c3f  call    FormatRRASErrorString
0x180088c44  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180088c4b  lea     r8, [rsp+850h+var_820]
0x180088c50  mov     rcx, cs:gNdpspEtwContext
0x180088c57  mov     rax, cs:gNdpspTemplateFunc
0x180088c5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088c63  jmp     short loc_180088C85
0x180088c65  mov     eax, cs:dwTraceId
0x180088c6b  cmp     eax, 0FFFFFFFFh
0x180088c6e  jz      short loc_180088C85
0x180088c70  mov     r9d, [rcx]
0x180088c73  lea     rdx, aGetcallobjwith_3; "GetCallObjWithReadLock: RasTapi call ha"...
0x180088c7a  mov     ecx, eax; dwTraceID
0x180088c7c  mov     r8d, edi
0x180088c7f  call    cs:__imp_TracePrintfA
0x180088c85  mov     ecx, edi
0x180088c87  mov     ebx, 6
0x180088c8c  call    ReleaseObjReadLock
0x180088c91  jmp     short loc_180088C96
0x180088c93  mov     [rsi], rcx
0x180088c96  mov     eax, ebx
0x180088c98  mov     rcx, [rbp+750h+var_20]
0x180088c9f  xor     rcx, rsp; StackCookie
0x180088ca2  call    __security_check_cookie
0x180088ca7  mov     rbx, [rsp+850h+arg_10]
0x180088caf  add     rsp, 840h
0x180088cb6  pop     rdi
0x180088cb7  pop     rsi
0x180088cb8  pop     rbp
0x180088cb9  retn
```
