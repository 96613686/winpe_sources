# GetCallObjWithWriteLock

- ea: `0x18008ef04`
- end: `0x18008f09b`
- name: `GetCallObjWithWriteLock`
- size: `407`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18008aa50`
- `0x18008d810`

## callees

- `0x1800755b8`
- `0x18008ef04`
- `0x180090048`
- `0x180090834`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `rtutils!TracePrintfA` at `0x18008efc4`
- `rtutils!TracePrintfA` at `0x18008f05d`
- `rtutils!TracePrintfA` at `0x18008efc4`
- `rtutils!TracePrintfA` at `0x18008f05d`

## string_xrefs

- `0x18008efbd`: `GetCallObjWithWriteLock: GetObjWithWriteLock failed (0x%x)`
- `0x18008ef76`: `GetCallObjWithWriteLock: GetObjWithWriteLock failed (0x%x)`
- `0x18008f053`: `GetCallObjWithWriteLock: RasTapi call handle (0x%x) has bad key (0x%x)`
- `0x18008f00d`: `GetCallObjWithWriteLock: RasTapi call handle (0x%x) has bad key (0x%x)`

## pseudocode

```c
__int64 __fastcall GetCallObjWithWriteLock(unsigned int a1, unsigned int **a2)
{
  unsigned int v4; // eax
  __int64 v5; // rdx
  unsigned int v6; // ebx
  unsigned int *v8; // [rsp+20h] [rbp-838h] BYREF
  int v9; // [rsp+30h] [rbp-828h] BYREF
  _BYTE v10[2044]; // [rsp+34h] [rbp-824h] BYREF

  v8 = 0;
  v9 = 0;
  memset_0(v10, 0, sizeof(v10));
  v4 = GetObjWithWriteLock(a1, &v8);
  v6 = v4;
  if ( v4 )
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800D0BE0 )
      {
        LOWORD(v9) = 0;
        FormatRRASErrorString(&v9, L"GetCallObjWithWriteLock: GetObjWithWriteLock failed (0x%x)", v4);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v9);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "GetCallObjWithWriteLock: GetObjWithWriteLock failed (0x%x)", v4);
    }
  }
  else if ( *v8 == 1229144396 || *v8 == 1329807692 )
  {
    *a2 = v8;
  }
  else
  {
    v6 = 6;
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800D0BE0 )
      {
        LOWORD(v9) = 0;
        FormatRRASErrorString(&v9, L"GetCallObjWithWriteLock: RasTapi call handle (0x%x) has bad key (0x%x)", a1, *v8);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v9);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "GetCallObjWithWriteLock: RasTapi call handle (0x%x) has bad key (0x%x)", a1, *v8);
    }
    ReleaseObjWriteLock(a1, v5);
  }
  return v6;
}

```

## disassembly

```asm
0x18008ef04  mov     [rsp+arg_10], rbx
0x18008ef09  push    rbp
0x18008ef0a  push    rsi
0x18008ef0b  push    rdi
0x18008ef0c  sub     rsp, 840h
0x18008ef13  mov     rax, cs:__security_cookie
0x18008ef1a  xor     rax, rsp
0x18008ef1d  mov     [rsp+858h+var_28], rax
0x18008ef25  mov     rsi, rdx
0x18008ef28  mov     edi, ecx
0x18008ef2a  xor     ebp, ebp
0x18008ef2c  lea     rcx, [rsp+858h+var_824]; void *
0x18008ef31  xor     edx, edx; Val
0x18008ef33  mov     [rsp+858h+var_838], rbp
0x18008ef38  mov     r8d, 7FCh; Size
0x18008ef3e  mov     [rsp+858h+var_828], ebp
0x18008ef42  call    memset_0
0x18008ef47  lea     rdx, [rsp+858h+var_838]
0x18008ef4c  mov     ecx, edi
0x18008ef4e  call    GetObjWithWriteLock
0x18008ef53  mov     ebx, eax
0x18008ef55  test    eax, eax
0x18008ef57  jz      short loc_18008EFD5
0x18008ef59  cmp     cs:gIsndpspEtwTracingAvailable, ebp
0x18008ef5f  jz      short loc_18008EFAB
0x18008ef61  cmp     qword ptr cs:xmmword_1800D0BE0, rbp
0x18008ef68  jz      loc_18008F075
0x18008ef6e  mov     r8d, eax
0x18008ef71  mov     word ptr [rsp+858h+var_828], bp
0x18008ef76  lea     rdx, aGetcallobjwith_6; "GetCallObjWithWriteLock: GetObjWithWrit"...
0x18008ef7d  lea     rcx, [rsp+858h+var_828]
0x18008ef82  call    FormatRRASErrorString
0x18008ef87  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008ef8e  lea     r8, [rsp+858h+var_828]
0x18008ef93  mov     rcx, cs:gNdpspEtwContext
0x18008ef9a  mov     rax, cs:gNdpspTemplateFunc
0x18008efa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008efa6  jmp     loc_18008F075
0x18008efab  mov     ecx, cs:dwTraceId; dwTraceID
0x18008efb1  cmp     ecx, 0FFFFFFFFh
0x18008efb4  jz      loc_18008F075
0x18008efba  mov     r8d, eax
0x18008efbd  lea     rdx, aGetcallobjwith_1; "GetCallObjWithWriteLock: GetObjWithWrit"...
0x18008efc4  call    cs:__imp_TracePrintfA
0x18008efcb  nop     dword ptr [rax+rax+00h]
0x18008efd0  jmp     loc_18008F075
0x18008efd5  mov     rax, [rsp+858h+var_838]
0x18008efda  cmp     dword ptr [rax], 4943414Ch
0x18008efe0  jz      loc_18008F072
0x18008efe6  cmp     dword ptr [rax], 4F43414Ch
0x18008efec  jz      loc_18008F072
0x18008eff2  cmp     cs:gIsndpspEtwTracingAvailable, ebp
0x18008eff8  mov     ebx, 6
0x18008effd  jz      short loc_18008F045
0x18008efff  cmp     qword ptr cs:xmmword_1800D0BE0, rbp
0x18008f006  jz      short loc_18008F069
0x18008f008  mov     word ptr [rsp+858h+var_828], bp
0x18008f00d  lea     rdx, aGetcallobjwith_2; "GetCallObjWithWriteLock: RasTapi call h"...
0x18008f014  mov     r9d, [rax]
0x18008f017  lea     rcx, [rsp+858h+var_828]
0x18008f01c  mov     r8d, edi
0x18008f01f  call    FormatRRASErrorString
0x18008f024  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008f02b  lea     r8, [rsp+858h+var_828]
0x18008f030  mov     rcx, cs:gNdpspEtwContext
0x18008f037  mov     rax, cs:gNdpspTemplateFunc
0x18008f03e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f043  jmp     short loc_18008F069
0x18008f045  mov     ecx, cs:dwTraceId; dwTraceID
0x18008f04b  cmp     ecx, 0FFFFFFFFh
0x18008f04e  jz      short loc_18008F069
0x18008f050  mov     r9d, [rax]
0x18008f053  lea     rdx, aGetcallobjwith_5; "GetCallObjWithWriteLock: RasTapi call h"...
0x18008f05a  mov     r8d, edi
0x18008f05d  call    cs:__imp_TracePrintfA
0x18008f064  nop     dword ptr [rax+rax+00h]
0x18008f069  mov     ecx, edi
0x18008f06b  call    ReleaseObjWriteLock
0x18008f070  jmp     short loc_18008F075
0x18008f072  mov     [rsi], rax
0x18008f075  mov     eax, ebx
0x18008f077  mov     rcx, [rsp+858h+var_28]
0x18008f07f  xor     rcx, rsp; StackCookie
0x18008f082  call    __security_check_cookie
0x18008f087  mov     rbx, [rsp+858h+arg_10]
0x18008f08f  add     rsp, 840h
0x18008f096  pop     rdi
0x18008f097  pop     rsi
0x18008f098  pop     rbp
0x18008f099  retn
```
