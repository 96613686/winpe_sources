# GetLineHandleFromCallHandle

- ea: `0x18008f388`
- end: `0x18008f506`
- name: `GetLineHandleFromCallHandle`
- size: `382`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18008beac`
- `0x18008d810`

## callees

- `0x1800755b8`
- `0x18008f388`
- `0x18008ff04`
- `0x180090714`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `rtutils!TracePrintfA` at `0x18008f453`
- `rtutils!TracePrintfA` at `0x18008f4bb`
- `rtutils!TracePrintfA` at `0x18008f453`
- `rtutils!TracePrintfA` at `0x18008f4bb`

## string_xrefs

- `0x18008f44c`: `GetLineHandleFromCallHandle: GetObjWithReadLock failed (0x%x)`
- `0x18008f405`: `GetLineHandleFromCallHandle: GetObjWithReadLock failed (0x%x)`

## pseudocode

```c
__int64 __fastcall GetLineHandleFromCallHandle(unsigned int a1, _DWORD *a2)
{
  unsigned int ObjWithReadLock; // eax
  unsigned int *v5; // rbx
  unsigned int v6; // edi
  unsigned int *v8; // [rsp+20h] [rbp-838h] BYREF
  int v9; // [rsp+30h] [rbp-828h] BYREF
  _BYTE v10[2044]; // [rsp+34h] [rbp-824h] BYREF

  v8 = 0;
  v9 = 0;
  memset_0(v10, 0, sizeof(v10));
  ObjWithReadLock = GetObjWithReadLock(a1, &v8);
  v5 = v8;
  v6 = ObjWithReadLock;
  if ( ObjWithReadLock )
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( !(_QWORD)xmmword_1800D0BE0 )
        goto LABEL_16;
      LOWORD(v9) = 0;
      FormatRRASErrorString(&v9, L"GetLineHandleFromCallHandle: GetObjWithReadLock failed (0x%x)", ObjWithReadLock);
      goto LABEL_5;
    }
    if ( dwTraceId != -1 )
      TracePrintfA(dwTraceId, "GetLineHandleFromCallHandle: GetObjWithReadLock failed (0x%x)", ObjWithReadLock);
  }
  else if ( *v8 == 1229144396 || *v8 == 1329807692 )
  {
    *a2 = v8[8];
  }
  else if ( gIsndpspEtwTracingAvailable )
  {
    if ( (_QWORD)xmmword_1800D0BE0 )
    {
      LOWORD(v9) = 0;
      FormatRRASErrorString(&v9, L"GetLineHandleFromCallHandle: Obj (0x%x) has bad key (0x%x)", a1, *v8);
LABEL_5:
      ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v9);
    }
  }
  else if ( dwTraceId != -1 )
  {
    TracePrintfA(dwTraceId, "GetLineHandleFromCallHandle: Obj (0x%x) has bad key (0x%x)", a1, *v8);
  }
LABEL_16:
  if ( v5 )
    ReleaseObjReadLock(a1);
  return v6;
}

```

## disassembly

```asm
0x18008f388  mov     [rsp+arg_10], rbx
0x18008f38d  mov     [rsp+arg_18], rbp
0x18008f392  push    rsi
0x18008f393  push    rdi
0x18008f394  push    r14
0x18008f396  sub     rsp, 840h
0x18008f39d  mov     rax, cs:__security_cookie
0x18008f3a4  xor     rax, rsp
0x18008f3a7  mov     [rsp+858h+var_28], rax
0x18008f3af  mov     r14, rdx
0x18008f3b2  mov     esi, ecx
0x18008f3b4  xor     ebp, ebp
0x18008f3b6  lea     rcx, [rsp+858h+var_824]; void *
0x18008f3bb  xor     edx, edx; Val
0x18008f3bd  mov     [rsp+858h+var_838], rbp
0x18008f3c2  mov     r8d, 7FCh; Size
0x18008f3c8  mov     [rsp+858h+var_828], ebp
0x18008f3cc  call    memset_0
0x18008f3d1  lea     rdx, [rsp+858h+var_838]
0x18008f3d6  mov     ecx, esi
0x18008f3d8  call    GetObjWithReadLock
0x18008f3dd  mov     rbx, [rsp+858h+var_838]
0x18008f3e2  mov     edi, eax
0x18008f3e4  test    eax, eax
0x18008f3e6  jz      short loc_18008F461
0x18008f3e8  cmp     cs:gIsndpspEtwTracingAvailable, ebp
0x18008f3ee  jz      short loc_18008F43A
0x18008f3f0  cmp     qword ptr cs:xmmword_1800D0BE0, rbp
0x18008f3f7  jz      loc_18008F4CF
0x18008f3fd  mov     r8d, eax
0x18008f400  mov     word ptr [rsp+858h+var_828], bp
0x18008f405  lea     rdx, aGetlinehandlef_2; "GetLineHandleFromCallHandle: GetObjWith"...
0x18008f40c  lea     rcx, [rsp+858h+var_828]
0x18008f411  call    FormatRRASErrorString
0x18008f416  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008f41d  lea     r8, [rsp+858h+var_828]
0x18008f422  mov     rcx, cs:gNdpspEtwContext
0x18008f429  mov     rax, cs:gNdpspTemplateFunc
0x18008f430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f435  jmp     loc_18008F4CF
0x18008f43a  mov     ecx, cs:dwTraceId; dwTraceID
0x18008f440  cmp     ecx, 0FFFFFFFFh
0x18008f443  jz      loc_18008F4CF
0x18008f449  mov     r8d, edi
0x18008f44c  lea     rdx, aGetlinehandlef_1; "GetLineHandleFromCallHandle: GetObjWith"...
0x18008f453  call    cs:__imp_TracePrintfA
0x18008f45a  nop     dword ptr [rax+rax+00h]
0x18008f45f  jmp     short loc_18008F4CF
0x18008f461  cmp     dword ptr [rbx], 4943414Ch
0x18008f467  jz      short loc_18008F4C9
0x18008f469  cmp     dword ptr [rbx], 4F43414Ch
0x18008f46f  jz      short loc_18008F4C9
0x18008f471  cmp     cs:gIsndpspEtwTracingAvailable, ebp
0x18008f477  jz      short loc_18008F4A3
0x18008f479  cmp     qword ptr cs:xmmword_1800D0BE0, rbp
0x18008f480  jz      short loc_18008F4CF
0x18008f482  mov     word ptr [rsp+858h+var_828], bp
0x18008f487  lea     rdx, aGetlinehandlef_0; "GetLineHandleFromCallHandle: Obj (0x%x)"...
0x18008f48e  mov     r9d, [rbx]
0x18008f491  lea     rcx, [rsp+858h+var_828]
0x18008f496  mov     r8d, esi
0x18008f499  call    FormatRRASErrorString
0x18008f49e  jmp     loc_18008F416
0x18008f4a3  mov     ecx, cs:dwTraceId; dwTraceID
0x18008f4a9  cmp     ecx, 0FFFFFFFFh
0x18008f4ac  jz      short loc_18008F4CF
0x18008f4ae  mov     r9d, [rbx]
0x18008f4b1  lea     rdx, aGetlinehandlef; "GetLineHandleFromCallHandle: Obj (0x%x)"...
0x18008f4b8  mov     r8d, esi
0x18008f4bb  call    cs:__imp_TracePrintfA
0x18008f4c2  nop     dword ptr [rax+rax+00h]
0x18008f4c7  jmp     short loc_18008F4CF
0x18008f4c9  mov     eax, [rbx+20h]
0x18008f4cc  mov     [r14], eax
0x18008f4cf  test    rbx, rbx
0x18008f4d2  jz      short loc_18008F4DB
0x18008f4d4  mov     ecx, esi
0x18008f4d6  call    ReleaseObjReadLock
0x18008f4db  mov     eax, edi
0x18008f4dd  mov     rcx, [rsp+858h+var_28]
0x18008f4e5  xor     rcx, rsp; StackCookie
0x18008f4e8  call    __security_check_cookie
0x18008f4ed  lea     r11, [rsp+858h+var_18]
0x18008f4f5  mov     rbx, [r11+30h]
0x18008f4f9  mov     rbp, [r11+38h]
0x18008f4fd  mov     rsp, r11
0x18008f500  pop     r14
0x18008f502  pop     rdi
0x18008f503  pop     rsi
0x18008f504  retn
```
