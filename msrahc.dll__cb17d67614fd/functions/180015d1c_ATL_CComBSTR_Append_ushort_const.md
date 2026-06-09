# ATL::CComBSTR::Append(ushort const *)

- ea: `0x180015d1c`
- end: `0x180015d3d`
- name: `?Append@CComBSTR@ATL@@QEAAJPEBG@Z`
- size: `33`
- prototype: `int __fastcall(ATL::CComBSTR *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180015f1c`

## callees

- `0x18000c504`
- `0x180015d44`

## pseudocode

```c
int __fastcall ATL::CComBSTR::Append(ATL::CComBSTR *this, const unsigned __int16 *a2)
{
  int v2; // eax
  const unsigned __int16 *v3; // rcx
  ATL::CComBSTR *v4; // r10

  v2 = ocslen(a2);
  return ATL::CComBSTR::Append(v4, v3, v2);
}

```

## disassembly

```asm
0x180015d1c  sub     rsp, 28h
0x180015d20  mov     r10, rcx
0x180015d23  mov     rcx, rdx; unsigned __int16 *
0x180015d26  call    ?ocslen@@YAHPEBG@Z; ocslen(ushort const *)
0x180015d2b  mov     rdx, rcx; unsigned __int16 *
0x180015d2e  mov     r8d, eax; int
0x180015d31  mov     rcx, r10; this
0x180015d34  add     rsp, 28h
0x180015d38  jmp     ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
```
