# AttemptToMerge

- ea: `0x10025a47`
- end: `0x10025ab1`
- name: `AttemptToMerge`
- size: `106`
- prototype: `int __fastcall(_DWORD, _DWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x10025ab7`

## callees

- `0x100259e1`
- `0x10025a47`

## pseudocode

```c
void __fastcall AttemptToMerge(_DWORD *a1, int a2)
{
  _DWORD *v3; // ecx
  _DWORD *v4; // edi
  int v5; // eax

  v3 = (_DWORD *)dword_1003AE64;
  v4 = 0;
  while ( v3 )
  {
    if ( a1 == (_DWORD *)((char *)v3 + v3[1]) )
    {
      if ( a2 )
        *(_DWORD *)(a2 + 8) = a1[2];
      else
        dword_1003AE64 = a1[2];
      v3[1] += a1[1];
      goto LABEL_11;
    }
    if ( (_DWORD *)((char *)a1 + a1[1]) == v3 )
    {
      if ( v4 )
        v4[2] = v3[2];
      else
        dword_1003AE64 = v3[2];
      v5 = v3[1];
      v3 = a1;
      a1[1] += v5;
LABEL_11:
      AttemptToFreePage(v3);
      return;
    }
    v4 = v3;
    v3 = (_DWORD *)v3[2];
  }
}

```

## disassembly

```asm
0x10025a47  mov     edi, edi
0x10025a49  push    ebx
0x10025a4a  push    esi
0x10025a4b  mov     esi, ecx
0x10025a4d  mov     ecx, dword_1003AE64
0x10025a53  push    edi
0x10025a54  mov     ebx, [esi+4]
0x10025a57  add     ebx, esi
0x10025a59  xor     edi, edi
0x10025a5b  jmp     short loc_10025A6F
0x10025a5d  mov     eax, [ecx+4]
0x10025a60  add     eax, ecx
0x10025a62  cmp     esi, eax
0x10025a64  jz      short loc_10025A98
0x10025a66  cmp     ebx, ecx
0x10025a68  jz      short loc_10025A77
0x10025a6a  mov     edi, ecx
0x10025a6c  mov     ecx, [ecx+8]
0x10025a6f  test    ecx, ecx
0x10025a71  jnz     short loc_10025A5D
0x10025a73  pop     edi
0x10025a74  pop     esi
0x10025a75  pop     ebx
0x10025a76  retn
0x10025a77  mov     eax, [ecx+8]
0x10025a7a  test    edi, edi
0x10025a7c  jnz     short loc_10025A85
0x10025a7e  mov     dword_1003AE64, eax
0x10025a83  jmp     short loc_10025A88
0x10025a85  mov     [edi+8], eax
0x10025a88  mov     eax, [ecx+4]
0x10025a8b  mov     ecx, esi
0x10025a8d  add     [esi+4], eax
0x10025a90  pop     edi
0x10025a91  pop     esi
0x10025a92  pop     ebx
0x10025a93  jmp     AttemptToFreePage
0x10025a98  mov     eax, [esi+8]
0x10025a9b  test    edx, edx
0x10025a9d  jnz     short loc_10025AA6
0x10025a9f  mov     dword_1003AE64, eax
0x10025aa4  jmp     short loc_10025AA9
0x10025aa6  mov     [edx+8], eax
0x10025aa9  mov     eax, [esi+4]
0x10025aac  add     [ecx+4], eax
0x10025aaf  jmp     short loc_10025A90
```
