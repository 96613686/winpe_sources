# SafeCoInit(void)

- ea: `0x18002c370`
- end: `0x18002c3cc`
- name: `?SafeCoInit@@YA?AV?$unique_call@P6AXXZ$1?CoUninitialize@@YAXXZ$00@wil@@XZ`
- size: `92`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000caa0`
- `0x1800118c0`
- `0x18002b9d0`
- `0x18002bb40`

## callees

- `0x18002a928`
- `0x18002c370`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002c394`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002c394`

## string_xrefs

- `0x18002c3ad`: `onecore\net\netprofiles\service\src\public\lib\netshhelperhandlers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_BYTE *__fastcall SafeCoInit(_BYTE *a1)
{
  HRESULT v2; // eax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *a1 = 1;
  v2 = CoInitializeEx(0, 0);
  if ( v2 < 0 )
  {
    if ( v2 != -2147417850 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x28,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\public\\lib\\netshhelperhandlers.cpp",
        (const char *)(unsigned int)v2,
        1);
    *a1 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x18002c370  mov     [rsp+arg_0], rcx
0x18002c375  push    rbx
0x18002c376  sub     rsp, 30h
0x18002c37a  mov     rbx, rcx
0x18002c37d  mov     [rsp+38h+var_18], 0
0x18002c385  mov     byte ptr [rcx], 1
0x18002c388  mov     [rsp+38h+var_18], 1; int
0x18002c390  xor     edx, edx; dwCoInit
0x18002c392  xor     ecx, ecx; pvReserved
0x18002c394  call    cs:__imp_CoInitializeEx
0x18002c39a  test    eax, eax
0x18002c39c  jns     short loc_18002C3C2
0x18002c39e  cmp     eax, 80010106h
0x18002c3a3  jz      short loc_18002C3BF
0x18002c3a5  mov     rcx, [rsp+38h]; this
0x18002c3aa  mov     r9d, eax; char *
0x18002c3ad  lea     r8, aOnecoreNetNetp; "onecore\\net\\netprofiles\\service\\src"...
0x18002c3b4  mov     edx, 28h ; '('; void *
0x18002c3b9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002c3bf  mov     byte ptr [rbx], 0
0x18002c3c2  mov     rax, rbx
0x18002c3c5  add     rsp, 30h
0x18002c3c9  pop     rbx
0x18002c3ca  retn
```
