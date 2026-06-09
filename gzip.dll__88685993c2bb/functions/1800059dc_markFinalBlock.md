# markFinalBlock

- ea: `0x1800059dc`
- end: `0x180005a8c`
- name: `markFinalBlock`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800028e0`

## callees

- `0x180004be0`
- `0x1800059dc`

## pseudocode

```c
__int64 __fastcall markFinalBlock(__int64 a1)
{
  __int64 result; // rax
  __int64 v2; // r9
  int v3; // r10d
  int v4; // r10d
  _BYTE *v5; // rcx

  result = outputBits(a1, *(_QWORD *)(a1 + 96) != 0 ? 14 : 10, *(_QWORD *)(a1 + 96) != 0 ? 4095 : 3);
  v3 = *(_DWORD *)(v2 + 68);
  if ( v3 > 0 )
  {
    result = outputBits(v2, 16 - v3, 0);
    if ( v4 <= 8 )
      --*(_QWORD *)(v2 + 40);
  }
  if ( *(_DWORD *)(v2 + 116) )
  {
    v5 = *(_BYTE **)(v2 + 40);
    *v5 = *(_BYTE *)(v2 + 124);
    v5[1] = *(_BYTE *)(v2 + 125);
    v5[2] = *(_BYTE *)(v2 + 126);
    v5[3] = *(_BYTE *)(v2 + 127);
    v5[4] = *(_BYTE *)(v2 + 128);
    v5[5] = *(_BYTE *)(v2 + 129);
    v5[6] = *(_BYTE *)(v2 + 130);
    v5[7] = *(_BYTE *)(v2 + 131);
    result = (__int64)(v5 + 8);
    *(_QWORD *)(v2 + 40) = v5 + 8;
  }
  return result;
}

```

## disassembly

```asm
0x1800059dc  sub     rsp, 28h
0x1800059e0  mov     rdx, [rcx+60h]
0x1800059e4  mov     r9, rcx
0x1800059e7  mov     rax, rdx
0x1800059ea  neg     rax
0x1800059ed  sbb     r8d, r8d
0x1800059f0  and     r8d, 0FFCh
0x1800059f7  add     r8d, 3
0x1800059fb  neg     rdx
0x1800059fe  sbb     edx, edx
0x180005a00  and     edx, 4
0x180005a03  add     edx, 0Ah
0x180005a06  call    outputBits
0x180005a0b  mov     r10d, [r9+44h]
0x180005a0f  test    r10d, r10d
0x180005a12  jle     short loc_180005A31
0x180005a14  mov     edx, 10h
0x180005a19  xor     r8d, r8d
0x180005a1c  sub     edx, r10d
0x180005a1f  mov     rcx, r9
0x180005a22  call    outputBits
0x180005a27  cmp     r10d, 8
0x180005a2b  jg      short loc_180005A31
0x180005a2d  dec     qword ptr [r9+28h]
0x180005a31  cmp     dword ptr [r9+74h], 0
0x180005a36  jz      short loc_180005A87
0x180005a38  mov     rcx, [r9+28h]
0x180005a3c  mov     al, [r9+7Ch]
0x180005a40  mov     [rcx], al
0x180005a42  mov     al, [r9+7Dh]
0x180005a46  mov     [rcx+1], al
0x180005a49  mov     al, [r9+7Eh]
0x180005a4d  mov     [rcx+2], al
0x180005a50  mov     al, [r9+7Fh]
0x180005a54  mov     [rcx+3], al
0x180005a57  mov     al, [r9+80h]
0x180005a5e  mov     [rcx+4], al
0x180005a61  mov     al, [r9+81h]
0x180005a68  mov     [rcx+5], al
0x180005a6b  mov     al, [r9+82h]
0x180005a72  mov     [rcx+6], al
0x180005a75  mov     al, [r9+83h]
0x180005a7c  mov     [rcx+7], al
0x180005a7f  lea     rax, [rcx+8]
0x180005a83  mov     [r9+28h], rax
0x180005a87  add     rsp, 28h
0x180005a8b  retn
```
