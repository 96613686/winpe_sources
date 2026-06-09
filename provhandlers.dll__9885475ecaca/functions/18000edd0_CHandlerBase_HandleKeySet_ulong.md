# CHandlerBase::HandleKeySet(ulong)

- ea: `0x18000edd0`
- end: `0x18000ee05`
- name: `?HandleKeySet@CHandlerBase@@UEAAJK@Z`
- size: `53`
- prototype: `__int64 __fastcall(CHandlerBase *this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800076a4`
- `0x18000edd0`

## string_xrefs

- `0x18000eddd`: `onecoreuap\admin\prov\multivariant\handlers\common\handlerbase.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CHandlerBase::HandleKeySet(CHandlerBase *this, int a2)
{
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\handlerbase.cpp",
      (const char *)0x80070057LL,
      v3);
    return 2147942487LL;
  }
  else
  {
    *((_DWORD *)this + 7) = 0;
    return 0;
  }
}

```

## disassembly

```asm
0x18000edd0  sub     rsp, 28h
0x18000edd4  test    edx, edx
0x18000edd6  jz      short loc_18000EDFB
0x18000edd8  mov     rcx, [rsp+28h]; this
0x18000eddd  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000ede4  mov     r9d, 80070057h; char *
0x18000edea  mov     edx, 3Ah ; ':'; void *
0x18000edef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000edf4  mov     eax, 80070057h
0x18000edf9  jmp     short loc_18000EE00
0x18000edfb  mov     [rcx+1Ch], edx
0x18000edfe  xor     eax, eax
0x18000ee00  add     rsp, 28h
0x18000ee04  retn
```
