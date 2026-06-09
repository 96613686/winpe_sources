# _lambda_103564c3136a6d89c1bf4e8d5a4b0eab_::operator()(void)

- ea: `0x18000cb50`
- end: `0x18000cbd5`
- name: `??R_lambda_103564c3136a6d89c1bf4e8d5a4b0eab_@@QEBA@XZ`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c994`

## callees

- `0x18000c548`
- `0x18000cb50`
- `0x18000ccc8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000cb6c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000cb6c`
- `api-ms-win-shcore-thread-l1-1-0!SHSetThreadRef` at `0x18000cbb5`
- `api-ms-win-shcore-thread-l1-1-0!SHSetThreadRef` at `0x18000cbb5`

## string_xrefs

- `0x18000cb82`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`

## pseudocode

```c
__int64 __fastcall _lambda_103564c3136a6d89c1bf4e8d5a4b0eab_::operator()(__int64 a1)
{
  HRESULT v2; // ebx
  __int64 v3; // rdx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = CoInitializeEx(0, *(_DWORD *)(*(_QWORD *)a1 + 72LL) != 0 ? 2 : 0);
  if ( v2 < 0 )
  {
    v3 = 947;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
      (const char *)(unsigned int)v2,
      v5);
    return (unsigned int)v2;
  }
  v2 = SetTlsSlotData((LPVOID)(*(_QWORD *)a1 + 128LL));
  if ( v2 < 0 )
  {
    v3 = 948;
    goto LABEL_3;
  }
  v2 = SHSetThreadRef(*(IUnknown **)(*(_QWORD *)a1 + 120LL));
  if ( v2 < 0 )
  {
    v3 = 949;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x18000cb50  mov     [rsp+arg_0], rbx
0x18000cb55  push    rdi; int
0x18000cb56  sub     rsp, 20h
0x18000cb5a  mov     rax, [rcx]
0x18000cb5d  mov     rdi, rcx
0x18000cb60  mov     edx, [rax+48h]
0x18000cb63  neg     edx
0x18000cb65  sbb     edx, edx
0x18000cb67  xor     ecx, ecx; pvReserved
0x18000cb69  and     edx, 2; dwCoInit
0x18000cb6c  call    cs:__imp_CoInitializeEx
0x18000cb72  mov     ebx, eax
0x18000cb74  test    eax, eax
0x18000cb76  jns     short loc_18000CB95
0x18000cb78  mov     edx, 3B3h; void *
0x18000cb7d  mov     rcx, [rsp+28h]; this
0x18000cb82  lea     r8, aOnecoreShellSh; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x18000cb89  mov     r9d, ebx; char *
0x18000cb8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cb91  mov     eax, ebx
0x18000cb93  jmp     short loc_18000CBCA
0x18000cb95  mov     rcx, [rdi]
0x18000cb98  sub     rcx, 0FFFFFFFFFFFFFF80h; lpTlsValue
0x18000cb9c  call    SetTlsSlotData
0x18000cba1  mov     ebx, eax
0x18000cba3  test    eax, eax
0x18000cba5  jns     short loc_18000CBAE
0x18000cba7  mov     edx, 3B4h
0x18000cbac  jmp     short loc_18000CB7D
0x18000cbae  mov     rcx, [rdi]
0x18000cbb1  mov     rcx, [rcx+78h]; punk
0x18000cbb5  call    cs:__imp_SHSetThreadRef
0x18000cbbb  mov     ebx, eax
0x18000cbbd  test    eax, eax
0x18000cbbf  jns     short loc_18000CBC8
0x18000cbc1  mov     edx, 3B5h
0x18000cbc6  jmp     short loc_18000CB7D
0x18000cbc8  xor     eax, eax
0x18000cbca  mov     rbx, [rsp+28h+arg_0]
0x18000cbcf  add     rsp, 20h
0x18000cbd3  pop     rdi
0x18000cbd4  retn
```
