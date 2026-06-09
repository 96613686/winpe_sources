# LdrpInitializeTls

- ea: `0x180068f24`
- end: `0x180069179`
- name: `LdrpInitializeTls`
- size: `597`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, service_task`

## callers

- `0x1800d6508`
- `0x180112488`

## callees

- `0x18001b984`
- `0x18001eb80`
- `0x18001f070`
- `0x180066020`
- `0x180067990`
- `0x180067dd0`
- `0x180068f24`
- `0x180069180`
- `0x180163a10`

## string_xrefs

- `0x180068fe6`: `DLL "%wZ" has TLS information at %p\n`

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
      qword_1801CA718 = Heap_0;
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
      v11 = (char *)qword_1801CA718 + (v9 >> 3);
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
      qword_1801CA718 = 0;
    }
    return LdrpAllocateTls();
  }
  return result;
}

```

## disassembly

```asm
0x180068f24  mov     rax, rsp
0x180068f27  push    rbx
0x180068f28  push    rbp
0x180068f29  push    rsi
0x180068f2a  push    rdi
0x180068f2b  push    r15
0x180068f2d  sub     rsp, 40h
0x180068f31  cmp     cs:LdrpActiveThreadCount, 0
0x180068f38  mov     qword ptr [rax+18h], 0
0x180068f40  jnz     loc_180069172
0x180068f46  call    LdrpInitializeTlsHeap
0x180068f4b  test    eax, eax
0x180068f4d  jns     short loc_180068F5B
0x180068f4f  add     rsp, 40h
0x180068f53  pop     r15
0x180068f55  pop     rdi
0x180068f56  pop     rsi
0x180068f57  pop     rbp
0x180068f58  pop     rbx
0x180068f59  retn
0x180068f5b  mov     rbx, cs:qword_1801CA8D0
0x180068f62  mov     esi, 1
0x180068f67  mov     [rsp+68h+arg_0], 0
0x180068f6f  lea     rax, qword_1801CA8D0
0x180068f76  cmp     rbx, rax
0x180068f79  jz      loc_18006903F
0x180068f7f  mov     rdi, rbx
0x180068f82  mov     rbx, [rbx]
0x180068f85  cmp     dword ptr [rdi+10Ch], 9
0x180068f8c  jz      short loc_180068F6F
0x180068f8e  mov     rdx, [rdi+30h]
0x180068f92  lea     r9, [rsp+68h+arg_10]
0x180068f9a  xor     r8d, r8d
0x180068f9d  lea     ecx, [r8+3]
0x180068fa1  call    RtlImageNtHeaderEx
0x180068fa6  mov     rax, [rsp+68h+arg_10]
0x180068fae  mov     ecx, 20Bh
0x180068fb3  cmp     [rax+18h], cx
0x180068fb7  jnz     short loc_180068F6F
0x180068fb9  mov     rcx, [rdi+30h]
0x180068fbd  lea     r9, [rsp+68h+arg_8]
0x180068fc2  mov     r8d, 9
0x180068fc8  mov     dl, sil
0x180068fcb  call    RtlImageDirectoryEntryToData
0x180068fd0  mov     rbp, rax
0x180068fd3  test    rax, rax
0x180068fd6  jz      short loc_180068F6F
0x180068fd8  mov     [rsp+68h+var_38], rax
0x180068fdd  lea     rcx, [rdi+48h]
0x180068fe1  mov     qword ptr [rsp+68h+ArgList], rcx; ArgList
0x180068fe6  lea     rax, aDllWzHasTlsInf; "DLL \"%wZ\" has TLS information at %p\n"
0x180068fed  lea     rcx, aMinkernelLdrLd_1; "minkernel\\ldr\\ldrtls.c"
0x180068ff4  mov     [rsp+68h+Format], rax; Format
0x180068ff9  mov     r9d, 2; int
0x180068fff  lea     r8, aLdrpinitialize_5; "LdrpInitializeTls"
0x180069006  mov     edx, 29Dh; int
0x18006900b  call    LdrpLogInternal
0x180069010  xor     r9d, r9d
0x180069013  mov     [rsp+68h+Format], 0
0x18006901c  lea     r8, [rsp+68h+arg_0]
0x180069021  mov     rdx, rdi
0x180069024  mov     rcx, rbp
0x180069027  call    LdrpAllocateTlsEntry
0x18006902c  test    eax, eax
0x18006902e  js      loc_180068F4F
0x180069034  mov     word ptr [rdi+6Eh], 0FFFFh
0x18006903a  jmp     loc_180068F6F
0x18006903f  mov     ebx, [rsp+68h+arg_0]
0x180069043  test    ebx, ebx
0x180069045  jz      loc_1800690E9
0x18006904b  lea     ebp, [rbx+8]
0x18006904e  cmp     ebp, 20h ; ' '
0x180069051  ja      loc_180069132
0x180069057  lea     rdi, LdrpStaticTlsBitmapVector
0x18006905e  mov     cs:LdrpTlsBitmap, ebp
0x180069064  mov     ebp, 8
0x180069069  mov     cs:LdrpActualBitmapSize, rsi
0x180069070  lea     r15, cs:180000000h
0x180069077  mov     cs:qword_1801CA718, rdi
0x18006907e  test    ebx, ebx
0x180069080  jz      short loc_180069095
0x180069082  mov     rsi, rbx
0x180069085  cmp     ebx, ebp
0x180069087  ja      short loc_180069100
0x180069089  mov     al, [rbx+r15+18A7F8h]
0x180069091  or      al, [rdi]
0x180069093  mov     [rdi], al
0x180069095  mov     r8, rbx
0x180069098  and     ebx, 7
0x18006909b  shr     r8, 3
0x18006909f  add     r8, cs:qword_1801CA718
0x1800690a6  lea     eax, [rbx+8]
0x1800690a9  cmp     eax, ebp
0x1800690ab  jbe     short loc_1800690DE
0x1800690ad  test    ebx, ebx
0x1800690af  jz      short loc_1800690C4
0x1800690b1  mov     al, [rbx+r15+18A7F8h]
0x1800690b9  mov     ebp, ebx
0x1800690bb  and     al, [r8]
0x1800690be  mov     [r8], al
0x1800690c1  inc     r8
0x1800690c4  mov     eax, ebp
0x1800690c6  mov     al, [rax+r15+18A808h]
0x1800690ce  and     al, [r8]
0x1800690d1  mov     [r8], al
0x1800690d4  call    LdrpAllocateTls
0x1800690d9  jmp     loc_180068F4F
0x1800690de  or      eax, 0FFFFFFFFh
0x1800690e1  mov     ecx, ebx
0x1800690e3  shl     al, cl
0x1800690e5  not     al
0x1800690e7  jmp     short loc_1800690CE
0x1800690e9  mov     cs:LdrpTlsBitmap, 0
0x1800690f3  mov     cs:qword_1801CA718, 0
0x1800690fe  jmp     short loc_1800690D4
0x180069100  shr     rsi, 3
0x180069104  mov     edx, 0FFh; Val
0x180069109  mov     r8, rsi; Size
0x18006910c  mov     rcx, rdi; void *
0x18006910f  call    RtlSetVolatileMemory
0x180069114  mov     eax, ebx
0x180069116  and     eax, 7
0x180069119  jbe     loc_180069095
0x18006911f  mov     al, [rax+r15+18A7F8h]
0x180069127  or      al, [rsi+rdi]
0x18006912a  mov     [rsi+rdi], al
0x18006912d  jmp     loc_180069095
0x180069132  mov     edx, cs:NtdllBaseTag
0x180069138  mov     rcx, cs:LdrpTlsHeap
0x18006913f  add     edx, 0C0000h
0x180069145  mov     esi, ebp
0x180069147  add     rsi, 1Fh
0x18006914b  shr     rsi, 5
0x18006914f  lea     r8, ds:0[rsi*4]
0x180069157  call    RtlAllocateHeap_0
0x18006915c  mov     rdi, rax
0x18006915f  test    rax, rax
0x180069162  jnz     loc_18006905E
0x180069168  mov     eax, 0C0000017h
0x18006916d  jmp     loc_180068F4F
0x180069172  xor     eax, eax
0x180069174  jmp     loc_180068F4F
```
