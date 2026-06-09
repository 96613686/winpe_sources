# Table::Release(Instance *)

- ea: `0x10052140`
- end: `0x10052315`
- name: `?Release@Table@@QAEJPAVInstance@@@Z`
- size: `469`
- prototype: `int __thiscall(Table *__hidden this, struct Instance *)`
- caller_count: `16`
- callee_count: `19`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10019960`
- `0x10033a50`
- `0x10034160`
- `0x10034bd0`
- `0x10035650`
- `0x10035e10`
- `0x10035f50`
- `0x10036160`
- `0x100364e0`
- `0x10044e20`
- `0x1004fcc0`
- `0x100502f0`
- `0x10050880`
- `0x10050bc0`
- `0x10053950`
- `0x10055ed0`

## callees

- `0x1000f750`
- `0x1001df90`
- `0x10026020`
- `0x10037470`
- `0x10044860`
- `0x10044950`
- `0x100451d0`
- `0x10051510`
- `0x10051e80`
- `0x10052140`
- `0x10057b70`
- `0x10057ce0`
- `0x10057d80`
- `0x10057dd0`
- `0x100591e0`
- `0x1005e3b0`
- `0x1005e74d`
- `0x1005e7e8`
- `0x1005f064`

## pseudocode

```c
int __thiscall Table::Release(Table *this, struct Instance *a2)
{
  int v3; // edi
  Session *v4; // ebx
  struct Database *v5; // edx
  struct IAccMeth *AccessMethod; // ebx
  struct Err *v7; // ecx
  int v8; // eax
  unsigned int v9; // ecx
  int v10; // eax
  int v11; // edx
  void *v13[3]; // [esp+14h] [ebp-20h] BYREF
  void *Block; // [esp+20h] [ebp-14h]
  void *v15; // [esp+24h] [ebp-10h]
  int v16; // [esp+30h] [ebp-4h]

  v3 = 0;
  v13[0] = (void *)1;
  v16 = 0;
  v4 = (Session *)*((_DWORD *)a2 + 3);
  if ( *((_BYTE *)this + 132) )
    goto LABEL_33;
  v5 = (struct Database *)*((_DWORD *)this + 9);
  v3 = *((_DWORD *)this + 19) - 1;
  *((_DWORD *)this + 19) = v3;
  if ( *((_DWORD *)v5 + 17) == 1 && !v3 )
  {
    AccessMethod = Session::GetAccessMethod(v4, v5, (struct Err *)v13);
    if ( ((int)v13[0] & 8) == 0 )
    {
      Table::FreeAllocations(this, AccessMethod, (struct Err *)v13);
      IAccMeth::Release(AccessMethod);
    }
LABEL_14:
    Table::~Table(this);
    operator delete(this);
    goto LABEL_33;
  }
  if ( !*((_DWORD *)v4 + 14) )
  {
    if ( v3 )
      goto LABEL_33;
    Session::BeginTransaction(v4, 1, v13);
    if ( ((int)v13[0] & 8) == 0 )
    {
      *((_DWORD *)this + 17) = *((_DWORD *)v4 + 14);
      Table::CleanupAllocations(this, v4, (struct Err *)v13);
      Err::Reset((Err *)v13);
      if ( ((int)v13[0] & 8) != 0
        || (Table::Persist(this, v4, (struct Err *)v13), ((int)v13[0] & 8) != 0)
        || (Session::CommitTransaction(v4, v13, 0), ((int)v13[0] & 8) != 0) )
      {
        Table::AbortTransaction(this, v4, v7);
      }
      else
      {
        *((_DWORD *)this + 17) = -1;
      }
    }
    goto LABEL_14;
  }
  if ( *((_DWORD *)this + 12) )
    goto LABEL_19;
  if ( !v3 )
  {
    v8 = *((_DWORD *)this + 11);
    if ( !v8 || v8 >= 7 )
      goto LABEL_21;
LABEL_19:
    if ( !v3 )
    {
      if ( *((_DWORD *)this + 11) == 9 )
      {
LABEL_21:
        Table::`scalar deleting destructor'(this, (unsigned int)this);
        goto LABEL_33;
      }
      *((_DWORD *)this + 11) = 0;
    }
  }
  v9 = *((_DWORD *)v5 + 14);
  v10 = 0;
  if ( v9 )
  {
    v11 = *((_DWORD *)v5 + 12);
    while ( *(Table **)(v11 + 4 * v10) != this )
    {
      if ( ++v10 >= v9 )
        goto LABEL_27;
    }
  }
  else
  {
LABEL_27:
    if ( v10 == v9 && !v3 )
    {
      Table::`scalar deleting destructor'(this, v9);
      goto LABEL_33;
    }
  }
  if ( !Session::IsNotifyMember(v4, this) && *((_DWORD *)this + 17) == -1 )
    Table::AddNotify(this, v4);
LABEL_33:
  if ( ((int)v13[0] & 0xFFFFFFFE) != 0 )
  {
    if ( Block )
      operator delete[](Block);
    if ( v15 )
      operator delete[](v15);
  }
  return v3;
}

```

## disassembly

```asm
0x10052140  mov     edi, edi
0x10052142  push    ebp
0x10052143  mov     ebp, esp
0x10052145  push    0FFFFFFFFh
0x10052147  push    offset ?Release@Table@@QAEJPAVInstance@@@Z_SEH
0x1005214c  mov     eax, large fs:0
0x10052152  push    eax
0x10052153  sub     esp, 18h
0x10052156  push    ebx
0x10052157  push    esi
0x10052158  push    edi
0x10052159  mov     eax, ___security_cookie
0x1005215e  xor     eax, ebp
0x10052160  push    eax
0x10052161  lea     eax, [ebp+var_C]
0x10052164  mov     large fs:0, eax
0x1005216a  mov     esi, ecx
0x1005216c  xor     edi, edi
0x1005216e  mov     [ebp+var_20], 1
0x10052175  mov     eax, [ebp+arg_0]
0x10052178  mov     [ebp+var_4], edi
0x1005217b  cmp     byte ptr [esi+84h], 0
0x10052182  mov     ebx, [eax+0Ch]
0x10052185  jnz     loc_100522D6
0x1005218b  mov     edi, [esi+4Ch]
0x1005218e  mov     edx, [esi+24h]
0x10052191  dec     edi
0x10052192  mov     [esi+4Ch], edi
0x10052195  cmp     dword ptr [edx+44h], 1
0x10052199  jnz     short loc_100521CC
0x1005219b  test    edi, edi
0x1005219d  jnz     short loc_100521CC
0x1005219f  lea     eax, [ebp+var_20]
0x100521a2  mov     ecx, ebx; this
0x100521a4  push    eax; struct Err *
0x100521a5  push    edx; struct Database *
0x100521a6  call    ?GetAccessMethod@Session@@QAEPAVIAccMeth@@PAVDatabase@@AAVErr@@@Z; Session::GetAccessMethod(Database *,Err &)
0x100521ab  test    byte ptr [ebp+var_20], 8
0x100521af  mov     ebx, eax
0x100521b1  jnz     loc_1005224A
0x100521b7  lea     eax, [ebp+var_20]
0x100521ba  mov     ecx, esi; this
0x100521bc  push    eax; struct Err *
0x100521bd  push    ebx; struct IAccMeth *
0x100521be  call    ?FreeAllocations@Table@@AAEXPAVIAccMeth@@AAVErr@@@Z; Table::FreeAllocations(IAccMeth *,Err &)
0x100521c3  mov     ecx, ebx; this
0x100521c5  call    ?Release@IAccMeth@@QAEXXZ; IAccMeth::Release(void)
0x100521ca  jmp     short loc_1005224A
0x100521cc  cmp     dword ptr [ebx+38h], 0
0x100521d0  jnz     loc_10052261
0x100521d6  test    edi, edi
0x100521d8  jnz     loc_100522D6
0x100521de  lea     eax, [ebp+var_20]
0x100521e1  mov     ecx, ebx
0x100521e3  push    eax
0x100521e4  push    1
0x100521e6  call    ?BeginTransaction@Session@@QAEXW4TransactionType@@AAVErr@@@Z; Session::BeginTransaction(TransactionType,Err &)
0x100521eb  test    byte ptr [ebp+var_20], 8
0x100521ef  jnz     short loc_1005224A
0x100521f1  mov     eax, [ebx+38h]
0x100521f4  mov     ecx, esi; this
0x100521f6  mov     [esi+44h], eax
0x100521f9  lea     eax, [ebp+var_20]
0x100521fc  push    eax; struct Err *
0x100521fd  push    ebx; struct Session *
0x100521fe  call    ?CleanupAllocations@Table@@AAEXPAVSession@@AAVErr@@@Z; Table::CleanupAllocations(Session *,Err &)
0x10052203  lea     ecx, [ebp+var_20]; this
0x10052206  call    ?Reset@Err@@QAEXXZ; Err::Reset(void)
0x1005220b  mov     eax, [ebp+var_20]
0x1005220e  test    al, 8
0x10052210  jnz     short loc_10052241
0x10052212  lea     eax, [ebp+var_20]
0x10052215  mov     ecx, esi; this
0x10052217  push    eax; struct Err *
0x10052218  push    ebx; struct Session *
0x10052219  call    ?Persist@Table@@AAEXPAVSession@@AAVErr@@@Z; Table::Persist(Session *,Err &)
0x1005221e  mov     eax, [ebp+var_20]
0x10052221  test    al, 8
0x10052223  jnz     short loc_10052241
0x10052225  push    edi; unsigned int
0x10052226  lea     eax, [ebp+var_20]
0x10052229  mov     ecx, ebx; this
0x1005222b  push    eax; struct Err *
0x1005222c  call    ?CommitTransaction@Session@@QAEXAAVErr@@K@Z; Session::CommitTransaction(Err &,ulong)
0x10052231  mov     eax, [ebp+var_20]
0x10052234  test    al, 8
0x10052236  jnz     short loc_10052241
0x10052238  mov     dword ptr [esi+44h], 0FFFFFFFFh
0x1005223f  jmp     short loc_1005224A
0x10052241  push    ecx; struct Err *
0x10052242  push    ebx; struct Session *
0x10052243  mov     ecx, esi; this
0x10052245  call    ?AbortTransaction@Table@@AAEXPAVSession@@AAVErr@@@Z; Table::AbortTransaction(Session *,Err &)
0x1005224a  mov     ecx, esi; this
0x1005224c  call    ??1Table@@QAE@XZ; Table::~Table(void)
0x10052251  push    778h; unsigned int
0x10052256  push    esi; Block
0x10052257  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1005225c  add     esp, 8
0x1005225f  jmp     short loc_100522D6
0x10052261  cmp     dword ptr [esi+30h], 0
0x10052265  jnz     short loc_10052277
0x10052267  test    edi, edi
0x10052269  jnz     short loc_10052292
0x1005226b  mov     eax, [esi+2Ch]
0x1005226e  test    eax, eax
0x10052270  jz      short loc_10052281
0x10052272  cmp     eax, 7
0x10052275  jge     short loc_10052281
0x10052277  test    edi, edi
0x10052279  jnz     short loc_10052292
0x1005227b  cmp     dword ptr [esi+2Ch], 9
0x1005227f  jnz     short loc_1005228B
0x10052281  push    ecx; unsigned int
0x10052282  mov     ecx, esi; this
0x10052284  call    ??_GTable@@QAEPAXI@Z; Table::`scalar deleting destructor'(uint)
0x10052289  jmp     short loc_100522D6
0x1005228b  mov     dword ptr [esi+2Ch], 0
0x10052292  mov     ecx, [edx+38h]
0x10052295  xor     eax, eax
0x10052297  test    ecx, ecx
0x10052299  jz      short loc_100522AA
0x1005229b  mov     edx, [edx+30h]
0x1005229e  mov     edi, edi
0x100522a0  cmp     [edx+eax*4], esi
0x100522a3  jz      short loc_100522BC
0x100522a5  inc     eax
0x100522a6  cmp     eax, ecx
0x100522a8  jb      short loc_100522A0
0x100522aa  cmp     eax, ecx
0x100522ac  jnz     short loc_100522BC
0x100522ae  test    edi, edi
0x100522b0  jnz     short loc_100522BC
0x100522b2  push    ecx; unsigned int
0x100522b3  mov     ecx, esi; this
0x100522b5  call    ??_GTable@@QAEPAXI@Z; Table::`scalar deleting destructor'(uint)
0x100522ba  jmp     short loc_100522D6
0x100522bc  push    esi
0x100522bd  mov     ecx, ebx
0x100522bf  call    ?IsNotifyMember@Session@@QAE?AW4SessBool@@PAVTable@@@Z; Session::IsNotifyMember(Table *)
0x100522c4  test    eax, eax
0x100522c6  jnz     short loc_100522D6
0x100522c8  cmp     dword ptr [esi+44h], 0FFFFFFFFh
0x100522cc  jnz     short loc_100522D6
0x100522ce  push    ebx; struct Session *
0x100522cf  mov     ecx, esi; this
0x100522d1  call    ?AddNotify@Table@@AAEXPAVSession@@@Z; Table::AddNotify(Session *)
0x100522d6  test    [ebp+var_20], 0FFFFFFFEh
0x100522dd  jz      short loc_100522FF
0x100522df  mov     eax, [ebp+Block]
0x100522e2  test    eax, eax
0x100522e4  jz      short loc_100522EF
0x100522e6  push    eax; Block
0x100522e7  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100522ec  add     esp, 4
0x100522ef  mov     ecx, [ebp+var_10]
0x100522f2  test    ecx, ecx
0x100522f4  jz      short loc_100522FF
0x100522f6  push    ecx; Block
0x100522f7  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100522fc  add     esp, 4
0x100522ff  mov     eax, edi
0x10052301  mov     ecx, [ebp+var_C]
0x10052304  mov     large fs:0, ecx
0x1005230b  pop     ecx
0x1005230c  pop     edi
0x1005230d  pop     esi
0x1005230e  pop     ebx
0x1005230f  mov     esp, ebp
0x10052311  pop     ebp
0x10052312  retn    4
0x10060f20  lea     ecx, [ebp+var_20]; this
0x10060f23  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x10060f2d  nop
0x10060f2e  nop
0x10060f2f  mov     edx, [esp-4+arg_4]
0x10060f33  lea     eax, [edx+0Ch]
0x10060f36  mov     ecx, [edx-28h]
0x10060f39  xor     ecx, eax; StackCookie
0x10060f3b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10060f40  mov     eax, offset stru_10063AF8
0x10060f45  jmp     ___CxxFrameHandler3
```
