# acmdStreamOpen

- ea: `0x180002988`
- end: `0x180002b54`
- name: `acmdStreamOpen`
- size: `460`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800020b0`

## callees

- `0x180002988`
- `0x180002ccc`
- `0x180002d70`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002b09`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002b09`

## pseudocode

```c
__int64 __fastcall acmdStreamOpen(_DWORD *a1, __int64 a2)
{
  __int64 v2; // rdi
  int v4; // r14d
  __int64 v6; // rsi
  __int16 v7; // cx
  bool v8; // zf
  __int64 (__fastcall *v9)(int, int, int, int, int); // rbx
  __int64 (__fastcall *v10)(int, int, int, int, int); // rax
  char *v12; // rax

  v2 = *(_QWORD *)(a2 + 4);
  v4 = *(_DWORD *)(a2 + 44);
  v6 = *(_QWORD *)(a2 + 12);
  if ( *(_WORD *)v2 == 1 )
  {
    if ( !(unsigned int)pcmIsValidFormat(v2) || !(unsigned int)imaadpcmIsValidFormat(v6) )
      return 512;
    if ( (v4 & 4) == 0
      && *((_DWORD *)&gaRateListFormat[1] + 3 * (unsigned int)a1[14]) / (unsigned int)*(unsigned __int16 *)(v2 + 2) < *(_DWORD *)(v2 + 4) )
    {
      return 8;
    }
    v7 = *(_WORD *)(v2 + 2);
    if ( v7 != 1 )
    {
      if ( *(_WORD *)(v2 + 2) == 2 )
      {
        v8 = *(_WORD *)(v2 + 14) == 8;
        v9 = (__int64 (__fastcall *)(int, int, int, int, int))imaadpcmEncode4Bit_S08;
        v10 = (__int64 (__fastcall *)(int, int, int, int, int))imaadpcmEncode4Bit_S16;
LABEL_20:
        if ( !v8 )
          v9 = v10;
        goto LABEL_25;
      }
      return 512;
    }
    v9 = (__int64 (__fastcall *)(int, int, int, int, int))imaadpcmEncode4Bit_M08;
    if ( *(_WORD *)(v2 + 14) != 8 )
      v9 = (__int64 (__fastcall *)(int, int, int, int, int))imaadpcmEncode4Bit_M16;
  }
  else
  {
    if ( *(_WORD *)v2 != 17 || !(unsigned int)imaadpcmIsValidFormat(v2) || !(unsigned int)pcmIsValidFormat(v6) )
      return 512;
    if ( (v4 & 4) == 0
      && *((_DWORD *)&gaRateListFormat[1] + 3 * (unsigned int)a1[15]) / (unsigned int)*(unsigned __int16 *)(v2 + 2) < *(_DWORD *)(v2 + 4) )
    {
      return 8;
    }
    v7 = *(_WORD *)(v2 + 2);
    if ( v7 != 1 )
    {
      if ( *(_WORD *)(v2 + 2) == 2 )
      {
        v8 = *(_WORD *)(v6 + 14) == 8;
        v9 = imaadpcmDecode4Bit_S08;
        v10 = imaadpcmDecode4Bit_S16;
        goto LABEL_20;
      }
      return 512;
    }
    v9 = imaadpcmDecode4Bit_M16;
    if ( *(_WORD *)(v6 + 14) == 8 )
      v9 = imaadpcmDecode4Bit_M08;
  }
LABEL_25:
  if ( v7 != *(_WORD *)(v6 + 2) || *(_DWORD *)(v2 + 4) != *(_DWORD *)(v6 + 4) )
    return 8;
  if ( (v4 & 1) != 0 )
    return 0;
  v12 = (char *)LocalAlloc(0x40u, 0x14u);
  if ( v12 )
  {
    *(_QWORD *)v12 = v9;
    *((_DWORD *)v12 + 2) = a1[9];
    *(_QWORD *)(v12 + 12) = 0;
    *(_DWORD *)(a2 + 48) = 0;
    *(_QWORD *)(a2 + 52) = v12;
    return 0;
  }
  return 7;
}

```

## disassembly

```asm
0x180002988  push    rbx
0x18000298a  push    rbp
0x18000298b  push    rsi
0x18000298c  push    rdi
0x18000298d  push    r12
0x18000298f  push    r14
0x180002991  push    r15
0x180002993  sub     rsp, 20h
0x180002997  mov     rdi, [rdx+4]
0x18000299b  mov     rbp, rdx
0x18000299e  mov     r14d, [rdx+2Ch]
0x1800029a2  mov     r15, rcx
0x1800029a5  mov     rsi, [rdx+0Ch]
0x1800029a9  mov     ebx, r14d
0x1800029ac  and     ebx, 4
0x1800029af  mov     r12d, 8
0x1800029b5  movzx   r8d, word ptr [rdi]
0x1800029b9  sub     r8d, 1
0x1800029bd  jz      loc_180002A5E
0x1800029c3  cmp     r8d, 10h
0x1800029c7  jnz     loc_180002B40
0x1800029cd  mov     rcx, rdi
0x1800029d0  call    imaadpcmIsValidFormat
0x1800029d5  test    eax, eax
0x1800029d7  jz      loc_180002B40
0x1800029dd  mov     rcx, rsi
0x1800029e0  call    pcmIsValidFormat
0x1800029e5  test    eax, eax
0x1800029e7  jz      loc_180002B40
0x1800029ed  test    ebx, ebx
0x1800029ef  jnz     short loc_180002A16
0x1800029f1  mov     eax, [r15+3Ch]
0x1800029f5  lea     r8, gaRateListFormat
0x1800029fc  movzx   ecx, word ptr [rdi+2]
0x180002a00  xor     edx, edx
0x180002a02  lea     rax, [rax+rax*2]
0x180002a06  mov     eax, [r8+rax*4+8]
0x180002a0b  div     ecx
0x180002a0d  cmp     eax, [rdi+4]
0x180002a10  jb      loc_180002B3B
0x180002a16  movzx   ecx, word ptr [rdi+2]
0x180002a1a  mov     edx, ecx
0x180002a1c  sub     edx, 1
0x180002a1f  jz      short loc_180002A42
0x180002a21  cmp     edx, 1
0x180002a24  jnz     loc_180002B40
0x180002a2a  cmp     r12w, [rsi+0Eh]
0x180002a2f  lea     rbx, imaadpcmDecode4Bit_S08
0x180002a36  lea     rax, imaadpcmDecode4Bit_S16
0x180002a3d  jmp     loc_180002ACE
0x180002a42  cmp     r12w, [rsi+0Eh]
0x180002a47  lea     rbx, imaadpcmDecode4Bit_M16
0x180002a4e  lea     rax, imaadpcmDecode4Bit_M08
0x180002a55  cmovz   rbx, rax
0x180002a59  jmp     loc_180002AE9
0x180002a5e  mov     rcx, rdi
0x180002a61  call    pcmIsValidFormat
0x180002a66  test    eax, eax
0x180002a68  jz      loc_180002B40
0x180002a6e  mov     rcx, rsi
0x180002a71  call    imaadpcmIsValidFormat
0x180002a76  test    eax, eax
0x180002a78  jz      loc_180002B40
0x180002a7e  test    ebx, ebx
0x180002a80  jnz     short loc_180002AA7
0x180002a82  mov     eax, [r15+38h]
0x180002a86  lea     r8, gaRateListFormat
0x180002a8d  movzx   ecx, word ptr [rdi+2]
0x180002a91  xor     edx, edx
0x180002a93  lea     rax, [rax+rax*2]
0x180002a97  mov     eax, [r8+rax*4+8]
0x180002a9c  div     ecx
0x180002a9e  cmp     eax, [rdi+4]
0x180002aa1  jb      loc_180002B3B
0x180002aa7  movzx   ecx, word ptr [rdi+2]
0x180002aab  mov     edx, ecx
0x180002aad  sub     edx, 1
0x180002ab0  jz      short loc_180002AD4
0x180002ab2  cmp     edx, 1
0x180002ab5  jnz     loc_180002B40
0x180002abb  cmp     r12w, [rdi+0Eh]
0x180002ac0  lea     rbx, imaadpcmEncode4Bit_S08
0x180002ac7  lea     rax, imaadpcmEncode4Bit_S16
0x180002ace  cmovnz  rbx, rax
0x180002ad2  jmp     short loc_180002AE9
0x180002ad4  lea     rbx, imaadpcmEncode4Bit_M08
0x180002adb  cmp     r12w, [rdi+0Eh]
0x180002ae0  jz      short loc_180002AE9
0x180002ae2  lea     rbx, imaadpcmEncode4Bit_M16
0x180002ae9  cmp     cx, [rsi+2]
0x180002aed  jnz     short loc_180002B3B
0x180002aef  mov     eax, [rsi+4]
0x180002af2  cmp     [rdi+4], eax
0x180002af5  jnz     short loc_180002B3B
0x180002af7  test    r14b, 1
0x180002afb  jz      short loc_180002B01
0x180002afd  xor     eax, eax
0x180002aff  jmp     short loc_180002B45
0x180002b01  mov     edx, 14h; uBytes
0x180002b06  lea     ecx, [rdx+2Ch]; uFlags
0x180002b09  call    cs:__imp_LocalAlloc
0x180002b0f  mov     rcx, rax
0x180002b12  test    rax, rax
0x180002b15  jnz     short loc_180002B1C
0x180002b17  lea     eax, [rcx+7]
0x180002b1a  jmp     short loc_180002B45
0x180002b1c  mov     [rax], rbx
0x180002b1f  mov     eax, [r15+24h]
0x180002b23  mov     [rcx+8], eax
0x180002b26  mov     qword ptr [rcx+0Ch], 0
0x180002b2e  mov     dword ptr [rbp+30h], 0
0x180002b35  mov     [rbp+34h], rcx
0x180002b39  jmp     short loc_180002AFD
0x180002b3b  mov     rax, r12
0x180002b3e  jmp     short loc_180002B45
0x180002b40  mov     eax, 200h
0x180002b45  add     rsp, 20h
0x180002b49  pop     r15
0x180002b4b  pop     r14
0x180002b4d  pop     r12
0x180002b4f  pop     rdi
0x180002b50  pop     rsi
0x180002b51  pop     rbp
0x180002b52  pop     rbx
0x180002b53  retn
```
