# CDSLink::SampleToRefTime(__int64,__int64 *)

- ea: `0x180010180`
- end: `0x1800101b4`
- name: `?SampleToRefTime@CDSLink@@UEAAJ_JPEA_J@Z`
- size: `52`
- prototype: `__int64 __fastcall(CDSLink *__hidden this, __int64, __int64 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180010180`

## pseudocode

```c
__int64 __fastcall CDSLink::SampleToRefTime(CDSLink *this, __int64 a2, __int64 *a3)
{
  __int64 result; // rax

  if ( !a3 )
    return 2147500035LL;
  result = 0;
  *a3 = *((_QWORD *)this + 8) + 1000 * (10000 * (a2 - *((unsigned int *)this + 18)) / *((unsigned int *)this + 19));
  return result;
}

```

## disassembly

```asm
0x180010180  mov     r9, rcx
0x180010183  test    r8, r8
0x180010186  jnz     short loc_18001018E
0x180010188  mov     eax, 80004003h
0x18001018d  retn
0x18001018e  mov     eax, [rcx+48h]
0x180010191  mov     ecx, [rcx+4Ch]
0x180010194  sub     rdx, rax
0x180010197  imul    rax, rdx, 2710h
0x18001019e  cqo
0x1800101a0  idiv    rcx
0x1800101a3  imul    rcx, rax, 3E8h
0x1800101aa  xor     eax, eax
0x1800101ac  add     rcx, [r9+40h]
0x1800101b0  mov     [r8], rcx
0x1800101b3  retn
```
