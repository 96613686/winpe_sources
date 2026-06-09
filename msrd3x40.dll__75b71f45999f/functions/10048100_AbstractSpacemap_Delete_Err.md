# AbstractSpacemap::Delete(Err &)

- ea: `0x10048100`
- end: `0x100481bd`
- name: `?Delete@AbstractSpacemap@@QAEXAAVErr@@@Z`
- size: `189`
- prototype: `void __thiscall(AbstractSpacemap *__hidden this, struct Err *)`
- caller_count: `6`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x10031300`
- `0x10031580`
- `0x10046bb0`
- `0x10054e90`
- `0x100577f0`
- `0x1005a7c0`

## callees

- `0x10025030`
- `0x10047a60`
- `0x10048100`
- `0x1005d1d0`

## pseudocode

```c
void __thiscall AbstractSpacemap::Delete(AbstractSpacemap *this, struct Err *a2)
{
  unsigned int i; // esi
  int v4; // eax
  int v5; // ecx
  int v6; // esi
  int v7; // eax

  AbstractSpacemap::Setup(this, 1, a2);
  if ( (*(_BYTE *)a2 & 8) == 0 )
  {
    if ( **((_BYTE **)this + 17) == 1 )
    {
      for ( i = 0; i < 0x21; ++i )
      {
        v4 = *(_DWORD *)(*((_DWORD *)this + 17) + 4 * i + 1);
        if ( v4 )
          Transaction::FreePage(*((_DWORD *)this + 1), v4, 1, a2);
      }
    }
    DataPage::Delete((AbstractSpacemap *)((char *)this + 28), *((_DWORD *)this + 2));
    v5 = *((_DWORD *)this + 7);
    *(_DWORD *)(v5 + 4 * *(_DWORD *)(v5 + 24) + 28) |= 8u;
    ++*(_DWORD *)(v5 + 64);
    v6 = *((_DWORD *)this + 7);
    *((_DWORD *)this + 9) = *(_DWORD *)(v6 + 64);
    if ( *(unsigned __int16 *)(*((_DWORD *)this + 8) + 2)
       + (unsigned int)(unsigned __int16)(2 * (*(_WORD *)(*((_DWORD *)this + 8) + 8) + 5)) >= 0x800 )
    {
      v7 = *((_DWORD *)this + 2) >> 8;
      if ( v6 )
        --*(_WORD *)(v6 + 76);
      *((_DWORD *)this + 8) = 0;
      *((_DWORD *)this + 7) = 0;
      Transaction::FreePage(*((_DWORD *)this + 1), v7, 1, a2);
    }
  }
}

```

## disassembly

```asm
0x10048100  mov     edi, edi
0x10048102  push    ebp
0x10048103  mov     ebp, esp
0x10048105  push    ebx
0x10048106  mov     ebx, [ebp+arg_0]
0x10048109  push    esi
0x1004810a  push    edi
0x1004810b  push    ebx
0x1004810c  push    1
0x1004810e  mov     edi, ecx
0x10048110  call    ?Setup@AbstractSpacemap@@IAEXW4SetupType@1@AAVErr@@@Z; AbstractSpacemap::Setup(AbstractSpacemap::SetupType,Err &)
0x10048115  test    byte ptr [ebx], 8
0x10048118  jnz     loc_100481B6
0x1004811e  mov     eax, [edi+44h]
0x10048121  cmp     byte ptr [eax], 1
0x10048124  jnz     short loc_1004814D
0x10048126  xor     esi, esi
0x10048128  nop     dword ptr [eax+eax+00000000h]
0x10048130  mov     eax, [edi+44h]
0x10048133  mov     eax, [eax+esi*4+1]
0x10048137  test    eax, eax
0x10048139  jz      short loc_10048147
0x1004813b  mov     ecx, [edi+4]
0x1004813e  push    ebx
0x1004813f  push    1
0x10048141  push    eax
0x10048142  call    ?FreePage@Transaction@@QAEXKW4FreeDisposition@@AAVErr@@@Z; Transaction::FreePage(ulong,FreeDisposition,Err &)
0x10048147  inc     esi
0x10048148  cmp     esi, 21h ; '!'
0x1004814b  jb      short loc_10048130
0x1004814d  push    dword ptr [edi+8]; unsigned int
0x10048150  lea     ecx, [edi+1Ch]; this
0x10048153  call    ?Delete@DataPage@@QAEXK@Z; DataPage::Delete(ulong)
0x10048158  mov     ecx, [edi+1Ch]
0x1004815b  mov     eax, [ecx+18h]
0x1004815e  or      dword ptr [ecx+eax*4+1Ch], 8
0x10048163  inc     dword ptr [ecx+40h]
0x10048166  mov     esi, [edi+1Ch]
0x10048169  mov     eax, [esi+40h]
0x1004816c  mov     [edi+24h], eax
0x1004816f  mov     edx, [edi+20h]
0x10048172  mov     ax, [edx+8]
0x10048176  add     ax, 5
0x1004817a  add     ax, ax
0x1004817d  movzx   ecx, ax
0x10048180  movzx   eax, word ptr [edx+2]
0x10048184  add     ecx, eax
0x10048186  cmp     ecx, 800h
0x1004818c  jb      short loc_100481B6
0x1004818e  mov     eax, [edi+8]
0x10048191  shr     eax, 8
0x10048194  test    esi, esi
0x10048196  jz      short loc_1004819C
0x10048198  dec     word ptr [esi+4Ch]
0x1004819c  push    ebx
0x1004819d  push    1
0x1004819f  mov     dword ptr [edi+20h], 0
0x100481a6  mov     dword ptr [edi+1Ch], 0
0x100481ad  mov     ecx, [edi+4]
0x100481b0  push    eax
0x100481b1  call    ?FreePage@Transaction@@QAEXKW4FreeDisposition@@AAVErr@@@Z; Transaction::FreePage(ulong,FreeDisposition,Err &)
0x100481b6  pop     edi
0x100481b7  pop     esi
0x100481b8  pop     ebx
0x100481b9  pop     ebp
0x100481ba  retn    4
```
