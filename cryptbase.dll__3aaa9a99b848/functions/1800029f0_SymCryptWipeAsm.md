# SymCryptWipeAsm

- ea: `0x1800029f0`
- end: `0x180002aa1`
- name: `SymCryptWipeAsm`
- size: `177`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001a50`
- `0x180002350`

## callees

- `0x1800029f0`

## pseudocode

```c
__int64 __fastcall SymCryptWipeAsm(__int64 a1, unsigned __int64 a2)
{
  bool v2; // cf
  unsigned __int64 i; // rdx
  unsigned int v4; // edx
  __int64 result; // rax

  if ( a2 < 0x10 )
  {
    result = 0;
    if ( (unsigned int)a2 < 8 )
    {
      if ( (unsigned int)a2 < 4 )
      {
        if ( (unsigned int)a2 < 2 )
        {
          if ( (_DWORD)a2 )
            *(_BYTE *)a1 = 0;
        }
        else
        {
          *(_WORD *)a1 = 0;
          *(_WORD *)(a1 + a2 - 2) = 0;
        }
      }
      else
      {
        *(_DWORD *)a1 = 0;
        *(_DWORD *)(a1 + a2 - 4) = 0;
      }
    }
    else
    {
      *(_QWORD *)a1 = 0;
      *(_QWORD *)(a1 + a2 - 8) = 0;
    }
  }
  else if ( (a1 & 0xF) != 0
         && (*(_QWORD *)a1 = 0, *(_QWORD *)(a1 + 8) = 0, result = -(int)a1 & 0xF, a1 += result, a2 -= result, a2 < 0x10) )
  {
    result = 0;
    *(_QWORD *)(a1 + a2 - 16) = 0;
    *(_QWORD *)(a1 + a2 - 8) = 0;
  }
  else
  {
    *(_OWORD *)a1 = 0;
    if ( (a2 & 0x10) != 0 )
      a1 += 16;
    v2 = a2 < 0x20;
    for ( i = a2 - 32; !v2; i -= 32LL )
    {
      *(_OWORD *)a1 = 0;
      *(_OWORD *)(a1 + 16) = 0;
      a1 += 32;
      v2 = i < 0x20;
    }
    v4 = i & 0xF;
    if ( v4 )
    {
      result = 0;
      *(_QWORD *)(a1 + v4 - 16) = 0;
      *(_QWORD *)(a1 + v4 - 8) = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800029f0  xorps   xmm0, xmm0
0x1800029f3  cmp     rdx, 10h
0x1800029f7  jb      loc_180002A70
0x1800029fd  test    rcx, 0Fh
0x180002a04  jnz     short loc_180002A44
0x180002a06  test    rdx, 10h
0x180002a0d  movaps  xmmword ptr [rcx], xmm0
0x180002a10  lea     r8, [rcx+10h]
0x180002a14  cmovnz  rcx, r8
0x180002a18  sub     rdx, 20h ; ' '
0x180002a1c  jb      short loc_180002A31
0x180002a1e  xchg    ax, ax
0x180002a20  movaps  xmmword ptr [rcx], xmm0
0x180002a23  movaps  xmmword ptr [rcx+10h], xmm0
0x180002a27  add     rcx, 20h ; ' '
0x180002a2b  sub     rdx, 20h ; ' '
0x180002a2f  jnb     short loc_180002A20
0x180002a31  and     edx, 0Fh
0x180002a34  jnz     short loc_180002A37
0x180002a36  retn
0x180002a37  xor     eax, eax
0x180002a39  mov     [rcx+rdx-10h], rax
0x180002a3e  mov     [rcx+rdx-8], rax
0x180002a43  retn
0x180002a44  xor     eax, eax
0x180002a46  mov     [rcx], rax
0x180002a49  mov     [rcx+8], rax
0x180002a4d  mov     eax, ecx
0x180002a4f  neg     eax
0x180002a51  and     eax, 0Fh
0x180002a54  add     rcx, rax
0x180002a57  sub     rdx, rax
0x180002a5a  cmp     rdx, 10h
0x180002a5e  jnb     short loc_180002A06
0x180002a60  xor     eax, eax
0x180002a62  mov     [rcx+rdx-10h], rax
0x180002a67  mov     [rcx+rdx-8], rax
0x180002a6c  retn
0x180002a70  xor     eax, eax
0x180002a72  cmp     edx, 8
0x180002a75  jb      short loc_180002A80
0x180002a77  mov     [rcx], rax
0x180002a7a  mov     [rcx+rdx-8], rax
0x180002a7f  retn
0x180002a80  cmp     edx, 4
0x180002a83  jb      short loc_180002A8C
0x180002a85  mov     [rcx], eax
0x180002a87  mov     [rcx+rdx-4], eax
0x180002a8b  retn
0x180002a8c  cmp     edx, 2
0x180002a8f  jb      short loc_180002A9A
0x180002a91  mov     [rcx], ax
0x180002a94  mov     [rcx+rdx-2], ax
0x180002a99  retn
0x180002a9a  or      edx, edx
0x180002a9c  jz      short locret_180002AA0
0x180002a9e  mov     [rcx], al
0x180002aa0  retn
```
