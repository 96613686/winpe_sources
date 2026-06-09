# ClearDispParams(tagDISPPARAMS *)

- ea: `0x18001b034`
- end: `0x18001b098`
- name: `?ClearDispParams@@YAXPEAUtagDISPPARAMS@@@Z`
- size: `100`
- prototype: `void __fastcall(struct tagDISPPARAMS *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18001ae44`
- `0x18007c884`

## callees

- `0x18001b034`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18001b059`
- `OLEAUT32!__imp_VariantClear` at `0x18001b059`
- `ole32!CoTaskMemFree` at `0x18001b069`
- `ole32!CoTaskMemFree` at `0x18001b07f`
- `ole32!CoTaskMemFree` at `0x18001b069`
- `ole32!CoTaskMemFree` at `0x18001b07f`

## pseudocode

```c
void __fastcall ClearDispParams(struct tagDISPPARAMS *a1)
{
  __int64 i; // rdi
  DISPID *rgdispidNamedArgs; // rcx

  if ( a1->rgvarg )
  {
    for ( i = 0; (unsigned int)i < a1->cArgs; i = (unsigned int)(i + 1) )
      VariantClear(&a1->rgvarg[i]);
    CoTaskMemFree(a1->rgvarg);
    a1->rgvarg = 0;
  }
  rgdispidNamedArgs = a1->rgdispidNamedArgs;
  if ( rgdispidNamedArgs )
  {
    CoTaskMemFree(rgdispidNamedArgs);
    a1->rgdispidNamedArgs = 0;
  }
}

```

## disassembly

```asm
0x18001b034  mov     [rsp+arg_0], rbx
0x18001b039  push    rdi
0x18001b03a  sub     rsp, 20h
0x18001b03e  cmp     qword ptr [rcx], 0
0x18001b042  mov     rbx, rcx
0x18001b045  jz      short loc_18001B076
0x18001b047  xor     edi, edi
0x18001b049  cmp     [rcx+10h], edi
0x18001b04c  jbe     short loc_18001B066
0x18001b04e  mov     rax, [rbx]
0x18001b051  lea     rcx, [rdi+rdi*2]
0x18001b055  lea     rcx, [rax+rcx*8]; pvarg
0x18001b059  call    cs:__imp_VariantClear
0x18001b05f  inc     edi
0x18001b061  cmp     edi, [rbx+10h]
0x18001b064  jb      short loc_18001B04E
0x18001b066  mov     rcx, [rbx]; pv
0x18001b069  call    cs:__imp_CoTaskMemFree
0x18001b06f  mov     qword ptr [rbx], 0
0x18001b076  mov     rcx, [rbx+8]; pv
0x18001b07a  test    rcx, rcx
0x18001b07d  jz      short loc_18001B08D
0x18001b07f  call    cs:__imp_CoTaskMemFree
0x18001b085  mov     qword ptr [rbx+8], 0
0x18001b08d  mov     rbx, [rsp+28h+arg_0]
0x18001b092  add     rsp, 20h
0x18001b096  pop     rdi
0x18001b097  retn
```
