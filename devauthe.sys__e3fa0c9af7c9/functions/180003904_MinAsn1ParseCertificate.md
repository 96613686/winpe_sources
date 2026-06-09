# MinAsn1ParseCertificate

- ea: `0x180003904`
- end: `0x180003975`
- name: `MinAsn1ParseCertificate`
- size: `113`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002e70`
- `0x180002ef4`

## callees

- `0x180003904`
- `0x180003a4c`

## pseudocode

```c
__int64 __fastcall MinAsn1ParseCertificate(_BYTE *a1, unsigned int a2, __int64 a3)
{
  int v4; // ecx
  int v5; // eax
  int v6; // eax
  unsigned int v8; // [rsp+58h] [rbp+20h] BYREF

  v8 = 20;
  v4 = MinAsn1ExtractValues(a1, a2, &v8, (__int64)&qword_1800090E0, 0xFu, a3);
  if ( v4 > 0 )
  {
    v5 = *(_DWORD *)(a3 + 192);
    v4 = *(_DWORD *)(a3 + 16);
    if ( v5 )
    {
      ++*(_QWORD *)(a3 + 200);
      *(_DWORD *)(a3 + 192) = v5 - 1;
    }
    v6 = *(_DWORD *)(a3 + 208);
    if ( v6 )
    {
      ++*(_QWORD *)(a3 + 216);
      *(_DWORD *)(a3 + 208) = v6 - 1;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180003904  mov     rax, rsp
0x180003907  push    rbx
0x180003908  sub     rsp, 30h
0x18000390c  mov     rbx, r8
0x18000390f  mov     dword ptr [rax+20h], 14h
0x180003916  mov     [rax-10h], rbx
0x18000391a  lea     r9, qword_1800090E0
0x180003921  lea     r8, [rax+20h]
0x180003925  mov     dword ptr [rax-18h], 0Fh
0x18000392c  call    MinAsn1ExtractValues
0x180003931  mov     ecx, eax
0x180003933  test    eax, eax
0x180003935  jle     short loc_18000396C
0x180003937  mov     eax, [rbx+0C0h]
0x18000393d  mov     ecx, [rbx+10h]
0x180003940  test    eax, eax
0x180003942  jz      short loc_180003953
0x180003944  inc     qword ptr [rbx+0C8h]
0x18000394b  dec     eax
0x18000394d  mov     [rbx+0C0h], eax
0x180003953  mov     eax, [rbx+0D0h]
0x180003959  test    eax, eax
0x18000395b  jz      short loc_18000396C
0x18000395d  inc     qword ptr [rbx+0D8h]
0x180003964  dec     eax
0x180003966  mov     [rbx+0D0h], eax
0x18000396c  mov     eax, ecx
0x18000396e  add     rsp, 30h
0x180003972  pop     rbx
0x180003973  retn
```
