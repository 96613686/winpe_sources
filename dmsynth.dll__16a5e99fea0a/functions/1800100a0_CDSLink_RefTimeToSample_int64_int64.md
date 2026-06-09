# CDSLink::RefTimeToSample(__int64,__int64 *)

- ea: `0x1800100a0`
- end: `0x1800100f8`
- name: `?RefTimeToSample@CDSLink@@UEAAJ_JPEA_J@Z`
- size: `88`
- prototype: `__int64 __fastcall(CDSLink *__hidden this, __int64, __int64 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800100a0`

## pseudocode

```c
__int64 __fastcall CDSLink::RefTimeToSample(CDSLink *this, __int64 a2, __int64 *a3)
{
  __int64 result; // rax
  unsigned __int64 v4; // rdx
  unsigned __int64 v5; // rdx

  if ( !a3 )
    return 2147500035LL;
  v4 = (__int64)((unsigned __int128)((a2 - *((_QWORD *)this + 8)) * (__int128)0x20C49BA5E353F7CFLL) >> 64) >> 7;
  v5 = (__int64)((unsigned __int128)((__int64)(*((unsigned int *)this + 19) * ((v4 >> 63) + v4))
                                   * (__int128)0x346DC5D63886594BLL) >> 64) >> 11;
  result = 0;
  *a3 = *((unsigned int *)this + 18) + (v5 >> 63) + v5;
  return result;
}

```

## disassembly

```asm
0x1800100a0  test    r8, r8
0x1800100a3  jnz     short loc_1800100AB
0x1800100a5  mov     eax, 80004003h
0x1800100aa  retn
0x1800100ab  sub     rdx, [rcx+40h]
0x1800100af  mov     rax, 20C49BA5E353F7CFh
0x1800100b9  imul    rdx
0x1800100bc  sar     rdx, 7
0x1800100c0  mov     rax, rdx
0x1800100c3  shr     rax, 3Fh
0x1800100c7  add     rdx, rax
0x1800100ca  mov     eax, [rcx+4Ch]
0x1800100cd  imul    rdx, rax
0x1800100d1  mov     rax, 346DC5D63886594Bh
0x1800100db  imul    rdx
0x1800100de  sar     rdx, 0Bh
0x1800100e2  mov     rax, rdx
0x1800100e5  shr     rax, 3Fh
0x1800100e9  add     rdx, rax
0x1800100ec  mov     eax, [rcx+48h]
0x1800100ef  add     rdx, rax
0x1800100f2  xor     eax, eax
0x1800100f4  mov     [r8], rdx
0x1800100f7  retn
```
