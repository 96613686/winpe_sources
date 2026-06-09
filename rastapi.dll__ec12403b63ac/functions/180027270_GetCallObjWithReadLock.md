# GetCallObjWithReadLock

- ea: `0x180027270`
- end: `0x18002740e`
- name: `GetCallObjWithReadLock`
- size: `414`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `7`
- tags: ``

## callers

- `0x1800231f8`
- `0x180023404`
- `0x180023a14`
- `0x180023e24`
- `0x1800244ec`
- `0x180024b38`
- `0x180025244`
- `0x1800275b8`
- `0x180027d38`

## callees

- `0x180027270`
- `0x180028398`
- `0x180028b5c`
- `0x180029130`
- `0x18002927e`
- `0x1800292b0`
- `0x18002a010`

## import_xrefs

- `rtutils!TracePrintfA` at `0x18002733f`
- `rtutils!TracePrintfA` at `0x1800273d3`
- `rtutils!TracePrintfA` at `0x18002733f`
- `rtutils!TracePrintfA` at `0x1800273d3`

## string_xrefs

- `0x1800272e9`: `GetCallObjWithReadLock: GetObjWithReadLock failed (0x%x)`
- `0x180027338`: `GetCallObjWithReadLock: GetObjWithReadLock failed (0x%x)`
- `0x18002737c`: `GetCallObjWithReadLock: RasTapi call handle (0x%x) has bad key (0x%x)`
- `0x1800273c7`: `GetCallObjWithReadLock: RasTapi call handle (0x%x) has bad key (0x%x)`

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
      if ( qword_18003EC40 )
      {
        LOWORD(v8) = 0;
        FormatRRASErrorString(&v8, L"GetCallObjWithReadLock: GetObjWithReadLock failed (0x%x)", ObjWithReadLock);
        ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v8);
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
      if ( qword_18003EC40 )
      {
        LOWORD(v8) = 0;
        FormatRRASErrorString(&v8, L"GetCallObjWithReadLock: RasTapi call handle (0x%x) has bad key (0x%x)", a1, *v7);
        ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v8);
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
0x180027270  mov     [rsp-8+arg_10], rbx
0x180027275  push    rbp
0x180027276  push    rsi
0x180027277  push    rdi
0x180027278  lea     rbp, [rsp-740h]
0x180027280  sub     rsp, 840h
0x180027287  mov     rax, cs:__security_cookie
0x18002728e  xor     rax, rsp
0x180027291  mov     [rbp+750h+var_20], rax
0x180027298  mov     rsi, rdx
0x18002729b  mov     [rsp+850h+var_830], 0
0x1800272a4  mov     edi, ecx
0x1800272a6  xor     eax, eax
0x1800272a8  xor     edx, edx; Val
0x1800272aa  mov     [rsp+850h+var_820], eax
0x1800272ae  lea     rcx, [rsp+850h+var_81C]; void *
0x1800272b3  mov     r8d, 7FCh; Size
0x1800272b9  call    memset_0
0x1800272be  lea     rdx, [rsp+850h+var_830]
0x1800272c3  mov     ecx, edi
0x1800272c5  call    GetObjWithReadLock
0x1800272ca  mov     ebx, eax
0x1800272cc  test    eax, eax
0x1800272ce  jz      short loc_18002734A
0x1800272d0  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x1800272d7  jz      short loc_180027326
0x1800272d9  cmp     cs:qword_18003EC40, 0
0x1800272e1  jz      loc_1800273EA
0x1800272e7  xor     ecx, ecx
0x1800272e9  lea     rdx, aGetcallobjwith; "GetCallObjWithReadLock: GetObjWithReadL"...
0x1800272f0  mov     word ptr [rsp+850h+var_820], cx
0x1800272f5  mov     r8d, eax
0x1800272f8  lea     rcx, [rsp+850h+var_820]
0x1800272fd  call    FormatRRASErrorString
0x180027302  mov     rdx, cs:qword_18003EC40
0x180027309  lea     r8, [rsp+850h+var_820]
0x18002730e  mov     rcx, cs:gNdpspEtwContext
0x180027315  mov     rax, cs:gNdpspTemplateFunc
0x18002731c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027321  jmp     loc_1800273EA
0x180027326  mov     ecx, cs:dwTraceId; dwTraceID
0x18002732c  cmp     ecx, 0FFFFFFFFh
0x18002732f  jz      loc_1800273EA
0x180027335  mov     r8d, eax
0x180027338  lea     rdx, aGetcallobjwith_4; "GetCallObjWithReadLock: GetObjWithReadL"...
0x18002733f  call    cs:__imp_TracePrintfA
0x180027345  jmp     loc_1800273EA
0x18002734a  mov     rcx, [rsp+850h+var_830]
0x18002734f  cmp     dword ptr [rcx], 4943414Ch
0x180027355  jz      loc_1800273E7
0x18002735b  cmp     dword ptr [rcx], 4F43414Ch
0x180027361  jz      loc_1800273E7
0x180027367  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x18002736e  jz      short loc_1800273B9
0x180027370  cmp     cs:qword_18003EC40, 0
0x180027378  jz      short loc_1800273D9
0x18002737a  xor     eax, eax
0x18002737c  lea     rdx, aGetcallobjwith_0; "GetCallObjWithReadLock: RasTapi call ha"...
0x180027383  mov     word ptr [rsp+850h+var_820], ax
0x180027388  mov     r8d, edi
0x18002738b  mov     r9d, [rcx]
0x18002738e  lea     rcx, [rsp+850h+var_820]
0x180027393  call    FormatRRASErrorString
0x180027398  mov     rdx, cs:qword_18003EC40
0x18002739f  lea     r8, [rsp+850h+var_820]
0x1800273a4  mov     rcx, cs:gNdpspEtwContext
0x1800273ab  mov     rax, cs:gNdpspTemplateFunc
0x1800273b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800273b7  jmp     short loc_1800273D9
0x1800273b9  mov     eax, cs:dwTraceId
0x1800273bf  cmp     eax, 0FFFFFFFFh
0x1800273c2  jz      short loc_1800273D9
0x1800273c4  mov     r9d, [rcx]
0x1800273c7  lea     rdx, aGetcallobjwith_3; "GetCallObjWithReadLock: RasTapi call ha"...
0x1800273ce  mov     ecx, eax; dwTraceID
0x1800273d0  mov     r8d, edi
0x1800273d3  call    cs:__imp_TracePrintfA
0x1800273d9  mov     ecx, edi
0x1800273db  mov     ebx, 6
0x1800273e0  call    ReleaseObjReadLock
0x1800273e5  jmp     short loc_1800273EA
0x1800273e7  mov     [rsi], rcx
0x1800273ea  mov     eax, ebx
0x1800273ec  mov     rcx, [rbp+750h+var_20]
0x1800273f3  xor     rcx, rsp; StackCookie
0x1800273f6  call    __security_check_cookie
0x1800273fb  mov     rbx, [rsp+850h+arg_10]
0x180027403  add     rsp, 840h
0x18002740a  pop     rdi
0x18002740b  pop     rsi
0x18002740c  pop     rbp
0x18002740d  retn
```
