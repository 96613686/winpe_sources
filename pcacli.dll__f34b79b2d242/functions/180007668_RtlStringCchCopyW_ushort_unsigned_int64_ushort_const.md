# RtlStringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180007668`
- end: `0x1800076a5`
- name: `?RtlStringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `61`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800092ac`
- `0x18000a7c4`
- `0x18000b0e0`
- `0x18000bb94`

## callees

- `0x180006fb8`
- `0x180007668`

## pseudocode

```c
__int64 __fastcall RtlStringCchCopyW(unsigned __int16 *a1, unsigned __int64 a2, const unsigned __int16 *a3)
{
  unsigned int v3; // edx

  if ( a2 )
  {
    if ( a2 <= 0x7FFFFFFF )
    {
      return (unsigned int)RtlStringCopyWorkerW(a1, a2, a3, a3);
    }
    else
    {
      v3 = -1073741811;
      *a1 = 0;
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return v3;
}

```

## disassembly

```asm
0x180007668  sub     rsp, 38h
0x18000766c  mov     rax, rdx
0x18000766f  test    rdx, rdx
0x180007672  jz      short loc_18000768F
0x180007674  cmp     rax, 7FFFFFFFh
0x18000767a  jbe     short loc_180007683
0x18000767c  mov     edx, 0C000000Dh
0x180007681  jmp     short loc_180007699
0x180007683  mov     r9, r8
0x180007686  call    RtlStringCopyWorkerW
0x18000768b  mov     edx, eax
0x18000768d  jmp     short loc_18000769E
0x18000768f  mov     edx, 0C000000Dh
0x180007694  test    rax, rax
0x180007697  jz      short loc_18000769E
0x180007699  xor     eax, eax
0x18000769b  mov     [rcx], ax
0x18000769e  mov     eax, edx
0x1800076a0  add     rsp, 38h
0x1800076a4  retn
```
