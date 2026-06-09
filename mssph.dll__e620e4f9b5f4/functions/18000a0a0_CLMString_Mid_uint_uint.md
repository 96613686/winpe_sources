# CLMString::Mid(uint,uint)

- ea: `0x18000a0a0`
- end: `0x18000a0f0`
- name: `?Mid@CLMString@@QEBA?AVCLMSubStr@@II@Z`
- size: `80`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002aa0`
- `0x180005880`
- `0x180006660`
- `0x180007810`
- `0x18001d2f0`
- `0x180021724`

## callees

- `0x18000a0a0`
- `0x18000e878`
- `0x18001e194`

## string_xrefs

- `0x18000a0d8`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`

## pseudocode

```c
__int64 __fastcall CLMString::Mid(__int64 a1, __int64 a2, unsigned int a3, unsigned int a4)
{
  unsigned __int64 v4; // r11
  __int64 result; // rax
  unsigned int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = a3 + (unsigned __int64)a4;
  if ( v4 < a3 )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(a1, a2);
  if ( v4 > *(unsigned int *)(a1 + 20) )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x40C,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\lmstr.hxx",
      (const char *)0xCE,
      v6);
  *(_DWORD *)a2 = a3;
  result = a2;
  *(_DWORD *)(a2 + 4) = a4;
  *(_QWORD *)(a2 + 8) = a1;
  return result;
}

```

## disassembly

```asm
0x18000a0a0  sub     rsp, 28h
0x18000a0a4  mov     r10d, r8d
0x18000a0a7  mov     r11d, r9d
0x18000a0aa  add     r11, r10
0x18000a0ad  cmp     r11, r10
0x18000a0b0  jb      short loc_18000A0CD
0x18000a0b2  mov     eax, [rcx+14h]
0x18000a0b5  cmp     r11, rax
0x18000a0b8  ja      short loc_18000A0D3
0x18000a0ba  mov     [rdx], r8d
0x18000a0bd  mov     rax, rdx
0x18000a0c0  mov     [rdx+4], r9d
0x18000a0c4  mov     [rdx+8], rcx
0x18000a0c8  add     rsp, 28h
0x18000a0cc  retn
0x18000a0cd  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x18000a0d3  mov     rcx, [rsp+28h]; this
0x18000a0d8  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18000a0df  mov     r9d, 0CEh; char *
0x18000a0e5  mov     edx, 40Ch; void *
0x18000a0ea  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
