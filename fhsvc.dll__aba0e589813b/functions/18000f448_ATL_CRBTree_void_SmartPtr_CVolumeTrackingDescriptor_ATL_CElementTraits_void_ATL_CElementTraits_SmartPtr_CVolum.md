# ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::Find(void *)

- ea: `0x18000f448`
- end: `0x18000f4dc`
- name: `?Find@?$CRBTree@PEAXV?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@PEAX@ATL@@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@3@@ATL@@IEBAPEAVCNode@12@PEAX@Z`
- size: `148`
- prototype: `unsigned __int64 *__fastcall(unsigned __int64 **, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ac48`
- `0x18000fe58`

## callees

- `0x18000f448`

## pseudocode

```c
unsigned __int64 *__fastcall ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::Find(
        unsigned __int64 **a1,
        unsigned __int64 a2)
{
  unsigned __int64 *v2; // rax
  unsigned __int64 *v4; // r9
  unsigned __int64 *v5; // r8
  unsigned __int64 *v7; // rax
  unsigned __int64 *v8; // rcx
  unsigned __int64 *v9; // rax
  char v10; // dl

  v2 = *a1;
  v4 = a1[5];
  v5 = 0;
  while ( v2 != v4 )
  {
    if ( v5 )
      goto LABEL_11;
    if ( a2 < *v2 )
    {
      v2 = (unsigned __int64 *)v2[3];
    }
    else if ( a2 == *v2 )
    {
      v5 = v2;
    }
    else
    {
      v2 = (unsigned __int64 *)v2[4];
    }
  }
  if ( !v5 )
    return 0;
  while ( 1 )
  {
LABEL_11:
    v7 = (unsigned __int64 *)v5[3];
    if ( v7 == v4 )
    {
      v8 = (unsigned __int64 *)v5[5];
      v9 = v5;
      while ( v8 != v4 )
      {
        if ( v9 != (unsigned __int64 *)v8[3] )
        {
          v10 = 0;
          goto LABEL_21;
        }
        v9 = v8;
        v8 = (unsigned __int64 *)v8[5];
      }
      v10 = 1;
LABEL_21:
      v7 = 0;
      if ( !v10 )
        v7 = v8;
    }
    else if ( v7 )
    {
      while ( (unsigned __int64 *)v7[4] != v4 )
        v7 = (unsigned __int64 *)v7[4];
    }
    if ( !v7 || a2 != *v7 )
      return v5;
    v5 = v7;
  }
}

```

## disassembly

```asm
0x18000f448  mov     rax, [rcx]
0x18000f44b  mov     r10, rdx
0x18000f44e  mov     r9, [rcx+28h]
0x18000f452  xor     r8d, r8d
0x18000f455  cmp     rax, r9
0x18000f458  jz      short loc_18000F477
0x18000f45a  test    r8, r8
0x18000f45d  jnz     short loc_18000F484
0x18000f45f  cmp     r10, [rax]
0x18000f462  jb      short loc_18000F471
0x18000f464  jnz     short loc_18000F46B
0x18000f466  mov     r8, rax
0x18000f469  jmp     short loc_18000F455
0x18000f46b  mov     rax, [rax+20h]
0x18000f46f  jmp     short loc_18000F455
0x18000f471  mov     rax, [rax+18h]
0x18000f475  jmp     short loc_18000F455
0x18000f477  test    r8, r8
0x18000f47a  jnz     short loc_18000F484
0x18000f47c  xor     eax, eax
0x18000f47e  retn
0x18000f47f  test    r8, r8
0x18000f482  jz      short loc_18000F4D8
0x18000f484  mov     rax, [r8+18h]
0x18000f488  cmp     rax, r9
0x18000f48b  jz      short loc_18000F4A0
0x18000f48d  test    rax, rax
0x18000f490  jz      short loc_18000F4C9
0x18000f492  mov     rcx, [rax+20h]
0x18000f496  cmp     rcx, r9
0x18000f499  jz      short loc_18000F4C9
0x18000f49b  mov     rax, rcx
0x18000f49e  jmp     short loc_18000F492
0x18000f4a0  mov     rcx, [r8+28h]
0x18000f4a4  mov     rax, r8
0x18000f4a7  cmp     rcx, r9
0x18000f4aa  jz      short loc_18000F4BF
0x18000f4ac  cmp     rax, [rcx+18h]
0x18000f4b0  jnz     short loc_18000F4BB
0x18000f4b2  mov     rax, rcx
0x18000f4b5  mov     rcx, [rcx+28h]
0x18000f4b9  jmp     short loc_18000F4A7
0x18000f4bb  xor     dl, dl
0x18000f4bd  jmp     short loc_18000F4C1
0x18000f4bf  mov     dl, 1
0x18000f4c1  xor     eax, eax
0x18000f4c3  test    dl, dl
0x18000f4c5  cmovz   rax, rcx
0x18000f4c9  test    rax, rax
0x18000f4cc  jz      short loc_18000F4D8
0x18000f4ce  cmp     r10, [rax]
0x18000f4d1  jnz     short loc_18000F4D8
0x18000f4d3  mov     r8, rax
0x18000f4d6  jmp     short loc_18000F47F
0x18000f4d8  mov     rax, r8
0x18000f4db  retn
```
