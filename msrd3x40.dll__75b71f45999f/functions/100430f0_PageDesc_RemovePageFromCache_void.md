# PageDesc::RemovePageFromCache(void)

- ea: `0x100430f0`
- end: `0x100431e9`
- name: `?RemovePageFromCache@PageDesc@@QAEXXZ`
- size: `249`
- prototype: `void __thiscall(PageDesc *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1001f7e0`
- `0x10020780`
- `0x10042d20`

## callees

- `0x1000f750`
- `0x10041c70`
- `0x10042440`
- `0x100430f0`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005f064`

## pseudocode

```c
void __thiscall PageDesc::RemovePageFromCache(PageDesc *this)
{
  int v2; // edi
  char *i; // edx
  int v4; // ebx
  int v5; // ecx
  unsigned int v6; // eax
  PageDesc **v7; // edx
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  int v10[3]; // [esp+10h] [ebp-20h] BYREF
  void *Block; // [esp+1Ch] [ebp-14h]
  void *v12; // [esp+20h] [ebp-10h]
  int v13; // [esp+2Ch] [ebp-4h]

  v10[0] = 1;
  v2 = 0;
  v13 = 0;
  for ( i = (char *)this + 28; v2 <= *((_DWORD *)this + 6); i = (char *)this + 28 )
  {
    if ( v2 > 0 )
    {
      v4 = *(_DWORD *)(*((_DWORD *)this + 15) + 36) + 56 * v2;
      v5 = *(_DWORD *)(v4 - 48);
      if ( v5 )
      {
        *(_DWORD *)(*(_DWORD *)(v4 - 56) + 4 * v5) = this;
        v6 = 0;
        v7 = *(PageDesc ***)(v4 - 56);
        if ( *v7 != this )
        {
          do
            ++v6;
          while ( v7[v6] != this );
        }
        v8 = *(_DWORD *)(v4 - 48);
        if ( v6 < v8 )
        {
          v9 = v8 - 1;
          *(_DWORD *)(v4 - 48) = v9;
          v7[v6] = v7[v9];
        }
        i = (char *)this + 28;
      }
    }
    PageVersion::Discard((PageVersion *)&i[4 * v2++], *((struct Database **)this + 5));
  }
  *((_DWORD *)this + 7) &= ~8u;
  *((_DWORD *)this + 15) = 0;
  *((_DWORD *)this + 6) = 0;
  PageDesc::Unlock(this, (struct Err *)v10);
  if ( (v10[0] & 0xFFFFFFFE) != 0 )
  {
    if ( Block )
      operator delete[](Block);
    if ( v12 )
      operator delete[](v12);
  }
}

```

## disassembly

```asm
0x100430f0  mov     edi, edi
0x100430f2  push    ebp
0x100430f3  mov     ebp, esp
0x100430f5  push    0FFFFFFFFh
0x100430f7  push    offset ?Close@Sort@@QAEXXZ_SEH
0x100430fc  mov     eax, large fs:0
0x10043102  push    eax
0x10043103  sub     esp, 14h
0x10043106  push    ebx
0x10043107  push    esi
0x10043108  push    edi
0x10043109  mov     eax, ___security_cookie
0x1004310e  xor     eax, ebp
0x10043110  push    eax
0x10043111  lea     eax, [ebp+var_C]
0x10043114  mov     large fs:0, eax
0x1004311a  mov     esi, ecx
0x1004311c  mov     [ebp+var_20], 1
0x10043123  xor     edi, edi
0x10043125  mov     [ebp+var_4], 0
0x1004312c  lea     edx, [esi+1Ch]
0x1004312f  cmp     [esi+18h], edi
0x10043132  jl      short loc_1004318E
0x10043134  test    edi, edi
0x10043136  jle     short loc_1004317A
0x10043138  mov     eax, [esi+3Ch]
0x1004313b  lea     ecx, ds:0[edi*8]
0x10043142  sub     ecx, edi
0x10043144  mov     eax, [eax+24h]
0x10043147  lea     ebx, [eax+ecx*8]
0x1004314a  mov     ecx, [ebx-30h]
0x1004314d  test    ecx, ecx
0x1004314f  jz      short loc_1004317A
0x10043151  mov     eax, [ebx-38h]
0x10043154  mov     [eax+ecx*4], esi
0x10043157  xor     eax, eax
0x10043159  mov     edx, [ebx-38h]
0x1004315c  cmp     [edx], esi
0x1004315e  jz      short loc_10043166
0x10043160  inc     eax
0x10043161  cmp     [edx+eax*4], esi
0x10043164  jnz     short loc_10043160
0x10043166  mov     ecx, [ebx-30h]
0x10043169  cmp     eax, ecx
0x1004316b  jnb     short loc_10043177
0x1004316d  dec     ecx
0x1004316e  mov     [ebx-30h], ecx
0x10043171  mov     ecx, [edx+ecx*4]
0x10043174  mov     [edx+eax*4], ecx
0x10043177  lea     edx, [esi+1Ch]
0x1004317a  push    dword ptr [esi+14h]; struct Database *
0x1004317d  lea     ecx, [edx+edi*4]; this
0x10043180  call    ?Discard@PageVersion@@QAEXAAVDatabase@@@Z; PageVersion::Discard(Database &)
0x10043185  inc     edi
0x10043186  lea     edx, [esi+1Ch]
0x10043189  cmp     edi, [esi+18h]
0x1004318c  jle     short loc_10043134
0x1004318e  and     dword ptr [esi+1Ch], 0FFFFFFF7h
0x10043192  lea     eax, [ebp+var_20]
0x10043195  lea     edi, [esi+1Ch]
0x10043198  mov     dword ptr [esi+3Ch], 0
0x1004319f  push    eax; struct Err *
0x100431a0  mov     ecx, esi; this
0x100431a2  mov     dword ptr [esi+18h], 0
0x100431a9  call    ?Unlock@PageDesc@@QAEIAAVErr@@@Z; PageDesc::Unlock(Err &)
0x100431ae  test    [ebp+var_20], 0FFFFFFFEh
0x100431b5  jz      short loc_100431D7
0x100431b7  mov     eax, [ebp+Block]
0x100431ba  test    eax, eax
0x100431bc  jz      short loc_100431C7
0x100431be  push    eax; Block
0x100431bf  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100431c4  add     esp, 4
0x100431c7  mov     eax, [ebp+var_10]
0x100431ca  test    eax, eax
0x100431cc  jz      short loc_100431D7
0x100431ce  push    eax; Block
0x100431cf  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100431d4  add     esp, 4
0x100431d7  mov     ecx, [ebp+var_C]
0x100431da  mov     large fs:0, ecx
0x100431e1  pop     ecx
0x100431e2  pop     edi
0x100431e3  pop     esi
0x100431e4  pop     ebx
0x100431e5  mov     esp, ebp
0x100431e7  pop     ebp
0x100431e8  retn
0x1005ffc0  lea     ecx, [ebp+var_20]; this
0x1005ffc3  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x1005ffcd  nop
0x1005ffce  nop
0x1005ffcf  mov     edx, [esp-4+arg_4]
0x1005ffd3  lea     eax, [edx+0Ch]
0x1005ffd6  mov     ecx, [edx-24h]
0x1005ffd9  xor     ecx, eax; StackCookie
0x1005ffdb  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1005ffe0  mov     eax, offset stru_10063014
0x1005ffe5  jmp     ___CxxFrameHandler3
```
