# PageDesc::Write(Err &)

- ea: `0x10042760`
- end: `0x10042959`
- name: `?Write@PageDesc@@QAEXAAVErr@@@Z`
- size: `505`
- prototype: `void __thiscall(PageDesc *__hidden this, struct Err *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x10023bb0`

## callees

- `0x1000f750`
- `0x10023f60`
- `0x10025e60`
- `0x10025ee0`
- `0x1002e5c0`
- `0x1002e740`
- `0x10041bb0`
- `0x10041c70`
- `0x10042760`
- `0x1004e980`
- `0x1004ebd0`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005f064`

## pseudocode

```c
void __thiscall PageDesc::Write(PageDesc *this, struct Err *a2)
{
  int v3; // edx
  int v4; // ebx
  struct Page *Pages; // ebx
  int v6; // eax
  int v7; // eax
  Database **v8; // ecx
  struct Page *v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // [esp-10h] [ebp-48h]
  _DWORD v12[3]; // [esp+10h] [ebp-28h] BYREF
  void *Block; // [esp+1Ch] [ebp-1Ch]
  void *v14; // [esp+20h] [ebp-18h]
  struct Page *v15; // [esp+24h] [ebp-14h]
  int v16; // [esp+28h] [ebp-10h]
  int v17; // [esp+34h] [ebp-4h]

  v12[0] = 1;
  v17 = 0;
  v3 = 0;
  v4 = *((_DWORD *)this + 7);
  v16 = 0;
  if ( (v4 & 8) == 0 || (*((_BYTE *)this + 82) & 1) != 0 && *((__int16 *)this + 38) > 0 )
    goto LABEL_27;
  if ( (v4 & 7) != 0 )
  {
    if ( (v4 & 7) == 4 )
    {
      Pages = System::AllocatePages((struct QMsg *)&Sys, (struct Err *)1);
      v6 = *(_DWORD *)(*((_DWORD *)this + 5) + 60);
      v11 = *((_DWORD *)this + 7) >> 8 << 11;
      v16 = 1;
      File::Read((File *)(*(_DWORD *)(v6 + 24) + 4), v11, Pages, 0x800u, (struct Err *)v12);
      if ( (v12[0] & 8) != 0 )
      {
LABEL_24:
        System::FreePages((struct Page *)&Sys, (unsigned int)Pages);
        goto LABEL_25;
      }
      v3 = v16;
    }
    else
    {
      Pages = 0;
    }
  }
  else
  {
    Pages = (struct Page *)(v4 & 0xFFFFFF00);
  }
  v7 = *((_DWORD *)this + 5);
  v8 = (Database **)((char *)this + 20);
  v15 = (PageDesc *)((char *)this + 20);
  if ( !*(_DWORD *)(v7 + 168) )
  {
LABEL_18:
    File::Write((File *)(*(_DWORD *)v15 + 4), *((_DWORD *)this + 3) << 11, Pages, 0x800u, (struct Err *)v12);
    if ( (v12[0] & 8) == 0 )
    {
      v10 = *((_DWORD *)this + 7) & 0xFFFFFFF7;
      *((_DWORD *)this + 7) = v10;
      if ( *((_BYTE *)this + 80) == 1 )
        *((_BYTE *)this + 80) = 0;
      if ( (v10 & 7) == 4 )
      {
        PageVersion::Discard((PageDesc *)((char *)this + 28), *((struct Database **)this + 5));
        *((_DWORD *)this + 7) = *((_DWORD *)this + 7) & 0xF8 | (*((_DWORD *)this + 3) << 8) | 3;
      }
    }
    if ( !v16 )
      goto LABEL_25;
    goto LABEL_24;
  }
  if ( v3 )
  {
LABEL_17:
    Database::Encrypt(*v8, Pages, *((_DWORD *)this + 3));
    goto LABEL_18;
  }
  if ( !Pages )
  {
    Err::SetError(v12, -1003, (char *)this + 20);
    goto LABEL_25;
  }
  v9 = System::AllocatePages((struct QMsg *)&Sys, (struct Err *)1);
  v15 = v9;
  if ( (v12[0] & 8) == 0 )
  {
    Page::operator=(v9, Pages);
    Pages = v15;
    v16 = 1;
    v8 = (Database **)((char *)this + 20);
    v15 = (PageDesc *)((char *)this + 20);
    goto LABEL_17;
  }
LABEL_25:
  if ( v12[0] > *(_DWORD *)a2 )
    Err::operator=(v12);
LABEL_27:
  if ( (v12[0] & 0xFFFFFFFE) != 0 )
  {
    if ( Block )
      operator delete[](Block);
    if ( v14 )
      operator delete[](v14);
  }
}

```

## disassembly

```asm
0x10042760  mov     edi, edi
0x10042762  push    ebp
0x10042763  mov     ebp, esp
0x10042765  push    0FFFFFFFFh
0x10042767  push    offset ?Write@PageDesc@@QAEXAAVErr@@@Z_SEH
0x1004276c  mov     eax, large fs:0
0x10042772  push    eax
0x10042773  sub     esp, 1Ch
0x10042776  push    ebx
0x10042777  push    esi
0x10042778  push    edi
0x10042779  mov     eax, ___security_cookie
0x1004277e  xor     eax, ebp
0x10042780  push    eax
0x10042781  lea     eax, [ebp+var_C]
0x10042784  mov     large fs:0, eax
0x1004278a  mov     esi, ecx
0x1004278c  mov     [ebp+var_28], 1
0x10042793  mov     [ebp+var_4], 0
0x1004279a  xor     edx, edx
0x1004279c  mov     ebx, [esi+1Ch]
0x1004279f  mov     [ebp+var_10], edx
0x100427a2  test    bl, 8
0x100427a5  jz      loc_1004291C
0x100427ab  test    byte ptr [esi+52h], 1
0x100427af  jz      short loc_100427BB
0x100427b1  cmp     [esi+4Ch], dx
0x100427b5  jg      loc_1004291C
0x100427bb  mov     eax, ebx
0x100427bd  and     eax, 7
0x100427c0  jz      short loc_10042822
0x100427c2  cmp     eax, 4
0x100427c5  jz      short loc_100427CB
0x100427c7  xor     ebx, ebx
0x100427c9  jmp     short loc_10042828
0x100427cb  lea     eax, [ebp+var_28]
0x100427ce  mov     ecx, offset ?Sys@@3VSystem@@A; lpParameter
0x100427d3  push    eax
0x100427d4  push    1; struct Err *
0x100427d6  call    ?AllocatePages@System@@QAEPAVPage@@KAAVErr@@@Z; System::AllocatePages(ulong,Err &)
0x100427db  test    byte ptr [ebp+var_28], 8
0x100427df  mov     ebx, eax
0x100427e1  jnz     loc_10042909
0x100427e7  mov     ecx, [esi+1Ch]
0x100427ea  lea     eax, [ebp+var_28]
0x100427ed  push    eax; struct Err *
0x100427ee  mov     eax, [esi+14h]
0x100427f1  shr     ecx, 8
0x100427f4  push    800h; nNumberOfBytesToRead
0x100427f9  shl     ecx, 0Bh
0x100427fc  mov     eax, [eax+3Ch]
0x100427ff  push    ebx; lpBuffer
0x10042800  push    ecx; lDistanceToMove
0x10042801  mov     [ebp+var_10], 1
0x10042808  mov     ecx, [eax+18h]
0x1004280b  add     ecx, 4; this
0x1004280e  call    ?Read@File@@QAEXKPAXKAAVErr@@@Z; File::Read(ulong,void *,ulong,Err &)
0x10042813  test    byte ptr [ebp+var_28], 8
0x10042817  jnz     loc_100428FC
0x1004281d  mov     edx, [ebp+var_10]
0x10042820  jmp     short loc_10042828
0x10042822  and     ebx, 0FFFFFF00h
0x10042828  mov     eax, [esi+14h]
0x1004282b  lea     ecx, [esi+14h]
0x1004282e  mov     [ebp+var_14], ecx
0x10042831  cmp     dword ptr [eax+0A8h], 0
0x10042838  jz      short loc_10042898
0x1004283a  test    edx, edx
0x1004283c  jnz     short loc_1004288D
0x1004283e  test    ebx, ebx
0x10042840  jnz     short loc_10042855
0x10042842  push    ecx
0x10042843  push    0FFFFFC15h
0x10042848  lea     ecx, [ebp+var_28]
0x1004284b  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10042850  jmp     loc_10042909
0x10042855  lea     eax, [ebp+var_28]
0x10042858  mov     ecx, offset ?Sys@@3VSystem@@A; lpParameter
0x1004285d  push    eax
0x1004285e  push    1; struct Err *
0x10042860  call    ?AllocatePages@System@@QAEPAVPage@@KAAVErr@@@Z; System::AllocatePages(ulong,Err &)
0x10042865  test    byte ptr [ebp+var_28], 8
0x10042869  mov     [ebp+var_14], eax
0x1004286c  jnz     loc_10042909
0x10042872  push    ebx; Src
0x10042873  mov     ecx, eax; void *
0x10042875  call    ??4Page@@QAEABV0@ABV0@@Z; Page::operator=(Page const &)
0x1004287a  mov     ebx, [ebp+var_14]
0x1004287d  lea     eax, [esi+14h]
0x10042880  mov     [ebp+var_10], 1
0x10042887  lea     ecx, [esi+14h]
0x1004288a  mov     [ebp+var_14], eax
0x1004288d  push    dword ptr [esi+0Ch]; unsigned int
0x10042890  mov     ecx, [ecx]; this
0x10042892  push    ebx; struct Page *
0x10042893  call    ?Encrypt@Database@@QAEXPAVPage@@K@Z; Database::Encrypt(Page *,ulong)
0x10042898  mov     ecx, [ebp+var_14]
0x1004289b  lea     eax, [ebp+var_28]
0x1004289e  push    eax; struct Err *
0x1004289f  mov     eax, [esi+0Ch]
0x100428a2  push    800h; nNumberOfBytesToWrite
0x100428a7  mov     ecx, [ecx]
0x100428a9  push    ebx; lpBuffer
0x100428aa  shl     eax, 0Bh
0x100428ad  add     ecx, 4; this
0x100428b0  push    eax; lDistanceToMove
0x100428b1  call    ?Write@File@@QAEXKPAXKAAVErr@@@Z; File::Write(ulong,void *,ulong,Err &)
0x100428b6  test    byte ptr [ebp+var_28], 8
0x100428ba  jnz     short loc_100428F6
0x100428bc  mov     eax, [esi+1Ch]
0x100428bf  and     eax, 0FFFFFFF7h
0x100428c2  mov     [esi+1Ch], eax
0x100428c5  cmp     byte ptr [esi+50h], 1
0x100428c9  jnz     short loc_100428CF
0x100428cb  mov     byte ptr [esi+50h], 0
0x100428cf  and     al, 7
0x100428d1  cmp     al, 4
0x100428d3  jnz     short loc_100428F6
0x100428d5  push    dword ptr [esi+14h]; struct Database *
0x100428d8  lea     ecx, [esi+1Ch]; this
0x100428db  call    ?Discard@PageVersion@@QAEXAAVDatabase@@@Z; PageVersion::Discard(Database &)
0x100428e0  mov     eax, [esi+1Ch]
0x100428e3  mov     edx, [esi+0Ch]
0x100428e6  and     eax, 0F8h
0x100428eb  shl     edx, 8
0x100428ee  or      edx, eax
0x100428f0  or      edx, 3
0x100428f3  mov     [esi+1Ch], edx
0x100428f6  cmp     [ebp+var_10], 0
0x100428fa  jz      short loc_10042909
0x100428fc  push    1
0x100428fe  push    ebx; unsigned int
0x100428ff  mov     ecx, offset ?Sys@@3VSystem@@A; struct Page *
0x10042904  call    ?FreePages@System@@QAEXPAVPage@@K@Z; System::FreePages(Page *,ulong)
0x10042909  mov     ecx, [ebp+arg_0]
0x1004290c  mov     eax, [ebp+var_28]
0x1004290f  cmp     eax, [ecx]
0x10042911  jle     short loc_1004291C
0x10042913  lea     eax, [ebp+var_28]
0x10042916  push    eax
0x10042917  call    ??4Err@@QAEAAV0@ABV0@@Z; Err::operator=(Err const &)
0x1004291c  test    [ebp+var_28], 0FFFFFFFEh
0x10042923  jz      short loc_10042945
0x10042925  mov     eax, [ebp+Block]
0x10042928  test    eax, eax
0x1004292a  jz      short loc_10042935
0x1004292c  push    eax; Block
0x1004292d  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10042932  add     esp, 4
0x10042935  mov     eax, [ebp+var_18]
0x10042938  test    eax, eax
0x1004293a  jz      short loc_10042945
0x1004293c  push    eax; Block
0x1004293d  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10042942  add     esp, 4
0x10042945  mov     ecx, [ebp+var_C]
0x10042948  mov     large fs:0, ecx
0x1004294f  pop     ecx
0x10042950  pop     edi
0x10042951  pop     esi
0x10042952  pop     ebx
0x10042953  mov     esp, ebp
0x10042955  pop     ebp
0x10042956  retn    4
0x100608b0  lea     ecx, [ebp+Block]; this
0x100608b3  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x100608bd  nop
0x100608be  nop
0x100608bf  mov     edx, dword ptr [esp-4+arg_4]
0x100608c3  lea     eax, [edx+0Ch]
0x100608c6  mov     ecx, [edx-2Ch]
0x100608c9  xor     ecx, eax; StackCookie
0x100608cb  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100608d0  mov     eax, offset stru_10063688
0x100608d5  jmp     ___CxxFrameHandler3
```
