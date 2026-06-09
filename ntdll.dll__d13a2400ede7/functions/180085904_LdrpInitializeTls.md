# LdrpInitializeTls

- ea: `0x180085904`
- end: `0x180085b59`
- name: `LdrpInitializeTls`
- size: `597`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, service_task`

## callers

- `0x180050718`
- `0x180113878`

## callees

- `0x18001b984`
- `0x18001eb80`
- `0x18001f070`
- `0x180082a00`
- `0x180084370`
- `0x1800847b0`
- `0x180085904`
- `0x180085b60`
- `0x180164220`

## string_xrefs

- `0x1800859c6`: `DLL "%wZ" has TLS information at %p\n`

## pseudocode

```c
__int64 LdrpInitializeTls()
{
  __int64 result; // rax
  __int64 *v1; // rbx
  unsigned __int64 v2; // rsi
  __int64 *v3; // rdi
  __int64 v4; // rax
  int v5; // ebp
  unsigned __int64 v6; // rbx
  char *Heap_0; // rdi
  unsigned int v8; // ebp
  unsigned __int64 v9; // r8
  __int64 v10; // rbx
  _BYTE *v11; // r8
  char v12; // al
  unsigned int v13; // [rsp+70h] [rbp+8h] BYREF
  int v14; // [rsp+78h] [rbp+10h] BYREF
  __int64 v15; // [rsp+80h] [rbp+18h] BYREF

  v15 = 0;
  if ( LdrpActiveThreadCount )
    return 0;
  result = LdrpInitializeTlsHeap();
  if ( (int)result >= 0 )
  {
    v1 = (__int64 *)qword_1801CA8D0;
    v2 = 1;
    v13 = 0;
    while ( v1 != &qword_1801CA8D0 )
    {
      v3 = v1;
      v1 = (__int64 *)*v1;
      if ( *((_DWORD *)v3 + 67) != 9 )
      {
        RtlImageNtHeaderEx(3, v3[6], 0, &v15);
        if ( *(_WORD *)(v15 + 24) == 523 )
        {
          v4 = RtlImageDirectoryEntryToData(v3[6], 1, 9u, &v14);
          v5 = v4;
          if ( v4 )
          {
            LdrpLogInternal(
              (int)"minkernel\\ldr\\ldrtls.c",
              669,
              (int)"LdrpInitializeTls",
              2,
              "DLL \"%wZ\" has TLS information at %p\n",
              (_BYTE)v3 + 72);
            result = LdrpAllocateTlsEntry(v5, (_DWORD)v3, (unsigned int)&v13, 0, 0);
            if ( (int)result < 0 )
              return result;
            *((_WORD *)v3 + 55) = -1;
          }
        }
      }
    }
    v6 = v13;
    if ( v13 )
    {
      if ( v13 + 8 > 0x20 )
      {
        v2 = ((unsigned __int64)(v13 + 8) + 31) >> 5;
        Heap_0 = (char *)RtlAllocateHeap_0(LdrpTlsHeap, (unsigned int)(NtdllBaseTag + 786432), 4 * v2);
        if ( !Heap_0 )
          return 3221225495LL;
      }
      else
      {
        Heap_0 = LdrpStaticTlsBitmapVector;
      }
      LdrpTlsBitmap = v6 + 8;
      v8 = 8;
      LdrpActualBitmapSize = v2;
      qword_1801CA728 = Heap_0;
      if ( (_DWORD)v6 )
      {
        if ( (unsigned int)v6 > 8 )
        {
          RtlSetVolatileMemory(Heap_0, 255, v6 >> 3);
          if ( (v6 & 7) != 0 )
            Heap_0[v6 >> 3] |= *((_BYTE *)FillMask + (v6 & 7));
        }
        else
        {
          *Heap_0 |= *((_BYTE *)FillMask + v6);
        }
      }
      v9 = v6;
      v10 = v6 & 7;
      v11 = (char *)qword_1801CA728 + (v9 >> 3);
      if ( (unsigned int)(v10 + 8) <= 8 )
      {
        v12 = ~(-1 << v10);
      }
      else
      {
        if ( (_DWORD)v10 )
        {
          v8 = v10;
          *v11++ &= *((_BYTE *)FillMask + v10);
        }
        v12 = *((_BYTE *)&ZeroMask + v8);
      }
      *v11 &= v12;
    }
    else
    {
      LdrpTlsBitmap = 0;
      qword_1801CA728 = 0;
    }
    return LdrpAllocateTls();
  }
  return result;
}

```

## disassembly

```asm
0x180085904  mov     rax, rsp
0x180085907  push    rbx
0x180085908  push    rbp
0x180085909  push    rsi
0x18008590a  push    rdi
0x18008590b  push    r15
0x18008590d  sub     rsp, 40h
0x180085911  cmp     cs:LdrpActiveThreadCount, 0
0x180085918  mov     qword ptr [rax+18h], 0
0x180085920  jnz     loc_180085B52
0x180085926  call    LdrpInitializeTlsHeap
0x18008592b  test    eax, eax
0x18008592d  jns     short loc_18008593B
0x18008592f  add     rsp, 40h
0x180085933  pop     r15
0x180085935  pop     rdi
0x180085936  pop     rsi
0x180085937  pop     rbp
0x180085938  pop     rbx
0x180085939  retn
0x18008593b  mov     rbx, cs:qword_1801CA8D0
0x180085942  mov     esi, 1
0x180085947  mov     [rsp+68h+arg_0], 0
0x18008594f  lea     rax, qword_1801CA8D0
0x180085956  cmp     rbx, rax
0x180085959  jz      loc_180085A1F
0x18008595f  mov     rdi, rbx
0x180085962  mov     rbx, [rbx]
0x180085965  cmp     dword ptr [rdi+10Ch], 9
0x18008596c  jz      short loc_18008594F
0x18008596e  mov     rdx, [rdi+30h]
0x180085972  lea     r9, [rsp+68h+arg_10]
0x18008597a  xor     r8d, r8d
0x18008597d  lea     ecx, [r8+3]
0x180085981  call    RtlImageNtHeaderEx
0x180085986  mov     rax, [rsp+68h+arg_10]
0x18008598e  mov     ecx, 20Bh
0x180085993  cmp     [rax+18h], cx
0x180085997  jnz     short loc_18008594F
0x180085999  mov     rcx, [rdi+30h]
0x18008599d  lea     r9, [rsp+68h+arg_8]
0x1800859a2  mov     r8d, 9
0x1800859a8  mov     dl, sil
0x1800859ab  call    RtlImageDirectoryEntryToData
0x1800859b0  mov     rbp, rax
0x1800859b3  test    rax, rax
0x1800859b6  jz      short loc_18008594F
0x1800859b8  mov     [rsp+68h+var_38], rax
0x1800859bd  lea     rcx, [rdi+48h]
0x1800859c1  mov     qword ptr [rsp+68h+ArgList], rcx; ArgList
0x1800859c6  lea     rax, aDllWzHasTlsInf; "DLL \"%wZ\" has TLS information at %p\n"
0x1800859cd  lea     rcx, aMinkernelLdrLd_1; "minkernel\\ldr\\ldrtls.c"
0x1800859d4  mov     [rsp+68h+Format], rax; Format
0x1800859d9  mov     r9d, 2; int
0x1800859df  lea     r8, aLdrpinitialize_5; "LdrpInitializeTls"
0x1800859e6  mov     edx, 29Dh; int
0x1800859eb  call    LdrpLogInternal
0x1800859f0  xor     r9d, r9d
0x1800859f3  mov     [rsp+68h+Format], 0
0x1800859fc  lea     r8, [rsp+68h+arg_0]
0x180085a01  mov     rdx, rdi
0x180085a04  mov     rcx, rbp
0x180085a07  call    LdrpAllocateTlsEntry
0x180085a0c  test    eax, eax
0x180085a0e  js      loc_18008592F
0x180085a14  mov     word ptr [rdi+6Eh], 0FFFFh
0x180085a1a  jmp     loc_18008594F
0x180085a1f  mov     ebx, [rsp+68h+arg_0]
0x180085a23  test    ebx, ebx
0x180085a25  jz      loc_180085AC9
0x180085a2b  lea     ebp, [rbx+8]
0x180085a2e  cmp     ebp, 20h ; ' '
0x180085a31  ja      loc_180085B12
0x180085a37  lea     rdi, LdrpStaticTlsBitmapVector
0x180085a3e  mov     cs:LdrpTlsBitmap, ebp
0x180085a44  mov     ebp, 8
0x180085a49  mov     cs:LdrpActualBitmapSize, rsi
0x180085a50  lea     r15, cs:180000000h
0x180085a57  mov     cs:qword_1801CA728, rdi
0x180085a5e  test    ebx, ebx
0x180085a60  jz      short loc_180085A75
0x180085a62  mov     rsi, rbx
0x180085a65  cmp     ebx, ebp
0x180085a67  ja      short loc_180085AE0
0x180085a69  mov     al, [rbx+r15+18AC38h]
0x180085a71  or      al, [rdi]
0x180085a73  mov     [rdi], al
0x180085a75  mov     r8, rbx
0x180085a78  and     ebx, 7
0x180085a7b  shr     r8, 3
0x180085a7f  add     r8, cs:qword_1801CA728
0x180085a86  lea     eax, [rbx+8]
0x180085a89  cmp     eax, ebp
0x180085a8b  jbe     short loc_180085ABE
0x180085a8d  test    ebx, ebx
0x180085a8f  jz      short loc_180085AA4
0x180085a91  mov     al, [rbx+r15+18AC38h]
0x180085a99  mov     ebp, ebx
0x180085a9b  and     al, [r8]
0x180085a9e  mov     [r8], al
0x180085aa1  inc     r8
0x180085aa4  mov     eax, ebp
0x180085aa6  mov     al, [rax+r15+18AC48h]
0x180085aae  and     al, [r8]
0x180085ab1  mov     [r8], al
0x180085ab4  call    LdrpAllocateTls
0x180085ab9  jmp     loc_18008592F
0x180085abe  or      eax, 0FFFFFFFFh
0x180085ac1  mov     ecx, ebx
0x180085ac3  shl     al, cl
0x180085ac5  not     al
0x180085ac7  jmp     short loc_180085AAE
0x180085ac9  mov     cs:LdrpTlsBitmap, 0
0x180085ad3  mov     cs:qword_1801CA728, 0
0x180085ade  jmp     short loc_180085AB4
0x180085ae0  shr     rsi, 3
0x180085ae4  mov     edx, 0FFh; Val
0x180085ae9  mov     r8, rsi; Size
0x180085aec  mov     rcx, rdi; void *
0x180085aef  call    RtlSetVolatileMemory
0x180085af4  mov     eax, ebx
0x180085af6  and     eax, 7
0x180085af9  jbe     loc_180085A75
0x180085aff  mov     al, [rax+r15+18AC38h]
0x180085b07  or      al, [rsi+rdi]
0x180085b0a  mov     [rsi+rdi], al
0x180085b0d  jmp     loc_180085A75
0x180085b12  mov     edx, cs:NtdllBaseTag
0x180085b18  mov     rcx, cs:LdrpTlsHeap
0x180085b1f  add     edx, 0C0000h
0x180085b25  mov     esi, ebp
0x180085b27  add     rsi, 1Fh
0x180085b2b  shr     rsi, 5
0x180085b2f  lea     r8, ds:0[rsi*4]
0x180085b37  call    RtlAllocateHeap_0
0x180085b3c  mov     rdi, rax
0x180085b3f  test    rax, rax
0x180085b42  jnz     loc_180085A3E
0x180085b48  mov     eax, 0C0000017h
0x180085b4d  jmp     loc_18008592F
0x180085b52  xor     eax, eax
0x180085b54  jmp     loc_18008592F
```
