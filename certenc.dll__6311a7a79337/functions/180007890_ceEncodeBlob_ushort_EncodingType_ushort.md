# ceEncodeBlob(ushort *,EncodingType,ushort * *)

- ea: `0x180007890`
- end: `0x1800078e0`
- name: `?ceEncodeBlob@@YAJPEAGW4EncodingType@@PEAPEAG@Z`
- size: `80`
- prototype: `__int64 __fastcall(unsigned __int16 *, DWORD dwFlags, unsigned __int16 **)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180001ee0`
- `0x180002730`
- `0x180002e60`
- `0x180003010`
- `0x180003be0`
- `0x180004f90`
- `0x1800051f0`
- `0x180007dd0`

## callees

- `0x180006234`
- `0x180007890`

## import_xrefs

- `OLEAUT32!__imp_SysStringByteLen` at `0x1800078ba`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800078ba`

## pseudocode

```c
__int64 __fastcall ceEncodeBlob(unsigned __int16 *a1, DWORD dwFlags, unsigned __int16 **a3)
{
  UINT v7; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = SysStringByteLen(a1);
  return ceEncodeCertString((const unsigned __int8 *)a1, v7, dwFlags, a3);
}

```

## disassembly

```asm
0x180007890  mov     [rsp+arg_0], rbx
0x180007895  mov     [rsp+arg_8], rsi
0x18000789a  push    rdi
0x18000789b  sub     rsp, 20h
0x18000789f  mov     rbx, r8
0x1800078a2  mov     esi, edx
0x1800078a4  mov     rdi, rcx
0x1800078a7  test    r8, r8
0x1800078aa  jnz     short loc_1800078B3
0x1800078ac  mov     eax, 80004003h
0x1800078b1  jmp     short loc_1800078D0
0x1800078b3  mov     qword ptr [r8], 0
0x1800078ba  call    cs:__imp_SysStringByteLen
0x1800078c0  mov     r9, rbx; unsigned __int16 **
0x1800078c3  mov     r8d, esi; dwFlags
0x1800078c6  mov     edx, eax; unsigned int
0x1800078c8  mov     rcx, rdi; unsigned __int8 *
0x1800078cb  call    ?ceEncodeCertString@@YAJPEBEKKPEAPEAG@Z; ceEncodeCertString(uchar const *,ulong,ulong,ushort * *)
0x1800078d0  mov     rbx, [rsp+28h+arg_0]
0x1800078d5  mov     rsi, [rsp+28h+arg_8]
0x1800078da  add     rsp, 20h
0x1800078de  pop     rdi
0x1800078df  retn
```
