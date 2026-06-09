# Database::CommitPDs(Transaction &,TransactionType,Err &)

- ea: `0x10024070`
- end: `0x1002429e`
- name: `?CommitPDs@Database@@QAEXAAVTransaction@@W4TransactionType@@AAVErr@@@Z`
- size: `558`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1005d310`

## callees

- `0x1000f750`
- `0x10012dd0`
- `0x10024070`
- `0x10024450`
- `0x10025e60`
- `0x1002e740`
- `0x100422a0`
- `0x10042520`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005f064`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100240d1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100240d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1002425c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1002425c`

## pseudocode

```c
void __thiscall Database::CommitPDs(int this, struct Transaction *a2, int a3, struct Err *a4)
{
  int v5; // esi
  int v6; // eax
  Collection *v7; // ecx
  int v8; // edx
  struct Err *v9; // ebx
  unsigned int v10; // eax
  _DWORD *v11; // eax
  unsigned int v12; // edx
  int v13; // ecx
  int v14; // eax
  unsigned int v15; // eax
  int v16; // esi
  int v17; // ebx
  bool v18; // zf
  int i; // esi
  Collection *v20; // ecx
  int v21; // edx
  int v22; // edi
  _DWORD *v23; // esi
  int v24; // eax
  _DWORD v25[3]; // [esp+10h] [ebp-3Ch] BYREF
  void *Block; // [esp+1Ch] [ebp-30h]
  void *v27; // [esp+20h] [ebp-2Ch]
  LPCRITICAL_SECTION lpCriticalSection; // [esp+24h] [ebp-28h]
  int v29; // [esp+28h] [ebp-24h]
  Collection *v30; // [esp+2Ch] [ebp-20h]
  int v31; // [esp+30h] [ebp-1Ch]
  _DWORD *v32; // [esp+34h] [ebp-18h]
  _DWORD *v33; // [esp+38h] [ebp-14h]
  char Buffer; // [esp+3Fh] [ebp-Dh] BYREF
  int v35; // [esp+48h] [ebp-4h]

  v32 = (_DWORD *)this;
  v25[0] = 1;
  v35 = 0;
  v5 = *(_DWORD *)a2;
  v6 = *((_DWORD *)a2 + 9);
  v31 = v5;
  v33 = (_DWORD *)(v6 + 56 * v5 - 56);
  lpCriticalSection = (LPCRITICAL_SECTION)(this + 112);
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 112));
  if ( v5 == 1 )
    v7 = (Collection *)(this + 376);
  else
    v7 = (Collection *)(*((_DWORD *)a2 + 9) + 56 * (v5 - 2));
  v8 = *((_DWORD *)v7 + 2);
  v9 = a4;
  v10 = v8 + v33[2];
  v30 = v7;
  v29 = v8;
  Collection::Grow(v7, v10, a4);
  if ( (*(_BYTE *)a4 & 8) == 0 && v5 == 1 && !a3 )
  {
    v11 = v33;
    if ( v32[17] == 1 )
      goto LABEL_17;
    v12 = 0;
    v13 = v33[2] - 1;
    if ( v13 < 0 )
      goto LABEL_17;
    do
    {
      v14 = *(_DWORD *)(*v33 + 4 * v13);
      if ( *(_BYTE *)(v14 + 80) )
      {
        v15 = *(_DWORD *)(v14 + 12);
        if ( v15 <= v12 )
          v15 = v12;
        v12 = v15;
      }
      --v13;
    }
    while ( v13 >= 0 );
    if ( v12 )
    {
      Buffer = 0;
      File::Write((File *)(v32 + 1), (v12 << 11) + 2047, &Buffer, 1u, a4);
    }
  }
  v11 = v33;
LABEL_17:
  if ( (*(_BYTE *)a4 & 8) != 0 )
    goto LABEL_27;
  v16 = v11[2] - 1;
  if ( v16 >= 0 )
  {
    v17 = v31;
    do
    {
      PageDesc::Commit(*(PageDesc **)(*v11 + 4 * v16--), a2, v17, (struct Err *)v25);
      v11 = v33;
    }
    while ( v16 >= 0 );
    v9 = a4;
  }
  v18 = v31 == 1;
  v11[2] = 0;
  if ( !v18 )
  {
LABEL_27:
    v22 = v25[0];
  }
  else
  {
    for ( i = *((_DWORD *)a2 + 8) - 1; i >= 0; --i )
      PageDesc::DecrementLock(*(_DWORD *)(*((_DWORD *)a2 + 6) + 4 * i), a2, v9, 0);
    v20 = v30;
    v21 = v29;
    *((_DWORD *)a2 + 8) = 0;
    Database::ScheduleFlush(v32, a3, v21 != *((_DWORD *)v20 + 2), v25);
    v22 = v25[0];
    if ( v25[0] > *(_DWORD *)v9 )
      Err::operator=(v25);
  }
  v23 = v32 + 49;
  v24 = v32[49];
  if ( (v24 & 8) != 0 )
  {
    if ( v24 > *(_DWORD *)v9 )
      Err::operator=(v32 + 49);
    if ( (*v23 & 0xFFFFFFFE) != 0 )
    {
      if ( v23[3] )
        operator delete[]((void *)v23[3]);
      if ( v23[4] )
        operator delete[]((void *)v23[4]);
    }
    *v23 = 1;
  }
  LeaveCriticalSection(lpCriticalSection);
  if ( (v22 & 0xFFFFFFFE) != 0 )
  {
    if ( Block )
      operator delete[](Block);
    if ( v27 )
      operator delete[](v27);
  }
}

```

## disassembly

```asm
0x10024070  mov     edi, edi
0x10024072  push    ebp
0x10024073  mov     ebp, esp
0x10024075  push    0FFFFFFFFh
0x10024077  push    offset ?CommitPDs@Database@@QAEXAAVTransaction@@W4TransactionType@@AAVErr@@@Z_SEH
0x1002407c  mov     eax, large fs:0
0x10024082  push    eax
0x10024083  sub     esp, 30h
0x10024086  push    ebx
0x10024087  push    esi
0x10024088  push    edi
0x10024089  mov     eax, ___security_cookie
0x1002408e  xor     eax, ebp
0x10024090  push    eax
0x10024091  lea     eax, [ebp+var_C]
0x10024094  mov     large fs:0, eax
0x1002409a  mov     ebx, ecx
0x1002409c  mov     [ebp+var_18], ebx
0x1002409f  mov     [ebp+var_3C], 1
0x100240a6  mov     edi, [ebp+arg_0]
0x100240a9  mov     [ebp+var_4], 0
0x100240b0  mov     esi, [edi]
0x100240b2  mov     eax, [edi+24h]
0x100240b5  mov     [ebp+var_1C], esi
0x100240b8  lea     ecx, ds:0[esi*8]
0x100240bf  sub     ecx, esi
0x100240c1  lea     eax, [eax+ecx*8]
0x100240c4  add     eax, 0FFFFFFC8h
0x100240c7  mov     [ebp+var_14], eax
0x100240ca  lea     eax, [ebx+70h]
0x100240cd  push    eax; lpCriticalSection
0x100240ce  mov     [ebp+lpCriticalSection], eax
0x100240d1  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100240d7  cmp     esi, 1
0x100240da  jnz     short loc_100240E4
0x100240dc  lea     ecx, [ebx+178h]
0x100240e2  jmp     short loc_100240F6
0x100240e4  lea     eax, [esi-2]
0x100240e7  lea     ecx, ds:0[eax*8]
0x100240ee  sub     ecx, eax
0x100240f0  mov     eax, [edi+24h]
0x100240f3  lea     ecx, [eax+ecx*8]; this
0x100240f6  mov     eax, [ebp+var_14]
0x100240f9  mov     edx, [ecx+8]
0x100240fc  mov     ebx, [ebp+arg_8]
0x100240ff  push    ebx; struct Err *
0x10024100  mov     eax, [eax+8]
0x10024103  add     eax, edx
0x10024105  mov     [ebp+var_20], ecx
0x10024108  push    eax; unsigned int
0x10024109  mov     [ebp+var_24], edx
0x1002410c  call    ?Grow@Collection@@QAEXKAAVErr@@@Z; Collection::Grow(ulong,Err &)
0x10024111  test    byte ptr [ebx], 8
0x10024114  jnz     short loc_10024173
0x10024116  cmp     esi, 1
0x10024119  jnz     short loc_10024173
0x1002411b  cmp     [ebp+arg_4], 0
0x1002411f  jnz     short loc_10024173
0x10024121  mov     eax, [ebp+var_18]
0x10024124  cmp     [eax+44h], esi
0x10024127  mov     eax, [ebp+var_14]
0x1002412a  jz      short loc_10024176
0x1002412c  mov     ecx, [eax+8]
0x1002412f  xor     edx, edx
0x10024131  sub     ecx, esi
0x10024133  js      short loc_10024176
0x10024135  mov     esi, [eax]
0x10024137  mov     eax, [esi+ecx*4]
0x1002413a  cmp     byte ptr [eax+50h], 0
0x1002413e  jz      short loc_1002414A
0x10024140  mov     eax, [eax+0Ch]
0x10024143  cmp     eax, edx
0x10024145  cmovbe  eax, edx
0x10024148  mov     edx, eax
0x1002414a  sub     ecx, 1
0x1002414d  jns     short loc_10024137
0x1002414f  test    edx, edx
0x10024151  jz      short loc_10024173
0x10024153  mov     ecx, [ebp+var_18]
0x10024156  lea     eax, [ebp+Buffer]
0x10024159  push    ebx; struct Err *
0x1002415a  push    1; nNumberOfBytesToWrite
0x1002415c  shl     edx, 0Bh
0x1002415f  push    eax; lpBuffer
0x10024160  add     edx, 7FFh
0x10024166  mov     [ebp+Buffer], 0
0x1002416a  push    edx; lDistanceToMove
0x1002416b  lea     ecx, [ecx+4]; this
0x1002416e  call    ?Write@File@@QAEXKPAXKAAVErr@@@Z; File::Write(ulong,void *,ulong,Err &)
0x10024173  mov     eax, [ebp+var_14]
0x10024176  test    byte ptr [ebx], 8
0x10024179  jnz     loc_1002420D
0x1002417f  mov     esi, [eax+8]
0x10024182  sub     esi, 1
0x10024185  js      short loc_100241AB
0x10024187  mov     ebx, [ebp+var_1C]
0x1002418a  nop     word ptr [eax+eax+00h]
0x10024190  lea     ecx, [ebp+var_3C]
0x10024193  push    ecx; struct Err *
0x10024194  mov     ecx, [eax]
0x10024196  push    ebx; int
0x10024197  push    edi; struct Transaction *
0x10024198  mov     ecx, [ecx+esi*4]; this
0x1002419b  call    ?Commit@PageDesc@@QAEXPAVTransaction@@HAAVErr@@@Z; PageDesc::Commit(Transaction *,int,Err &)
0x100241a0  sub     esi, 1
0x100241a3  mov     eax, [ebp+var_14]
0x100241a6  jns     short loc_10024190
0x100241a8  mov     ebx, [ebp+arg_8]
0x100241ab  cmp     [ebp+var_1C], 1
0x100241af  mov     dword ptr [eax+8], 0
0x100241b6  jnz     short loc_1002420D
0x100241b8  mov     esi, [edi+20h]
0x100241bb  sub     esi, 1
0x100241be  js      short loc_100241D4
0x100241c0  mov     ecx, [edi+18h]
0x100241c3  push    0
0x100241c5  push    ebx
0x100241c6  push    edi
0x100241c7  mov     ecx, [ecx+esi*4]
0x100241ca  call    ?DecrementLock@PageDesc@@QAEXPAVTransaction@@AAVErr@@W4UnlockType@@@Z; PageDesc::DecrementLock(Transaction *,Err &,UnlockType)
0x100241cf  sub     esi, 1
0x100241d2  jns     short loc_100241C0
0x100241d4  mov     ecx, [ebp+var_20]
0x100241d7  lea     eax, [ebp+var_3C]
0x100241da  mov     edx, [ebp+var_24]
0x100241dd  push    eax
0x100241de  xor     eax, eax
0x100241e0  mov     dword ptr [edi+20h], 0
0x100241e7  cmp     edx, [ecx+8]
0x100241ea  mov     ecx, [ebp+var_18]
0x100241ed  setnz   al
0x100241f0  push    eax
0x100241f1  push    [ebp+arg_4]
0x100241f4  call    ?ScheduleFlush@Database@@IAEXW4TransactionType@@W4DBCommitStatus@@AAVErr@@@Z; Database::ScheduleFlush(TransactionType,DBCommitStatus,Err &)
0x100241f9  mov     edi, [ebp+var_3C]
0x100241fc  cmp     edi, [ebx]
0x100241fe  jle     short loc_10024210
0x10024200  lea     eax, [ebp+var_3C]
0x10024203  mov     ecx, ebx
0x10024205  push    eax
0x10024206  call    ??4Err@@QAEAAV0@ABV0@@Z; Err::operator=(Err const &)
0x1002420b  jmp     short loc_10024210
0x1002420d  mov     edi, [ebp+var_3C]
0x10024210  mov     esi, [ebp+var_18]
0x10024213  add     esi, 0C4h
0x10024219  mov     eax, [esi]
0x1002421b  test    al, 8
0x1002421d  jz      short loc_10024259
0x1002421f  cmp     eax, [ebx]
0x10024221  jle     short loc_1002422B
0x10024223  push    esi
0x10024224  mov     ecx, ebx
0x10024226  call    ??4Err@@QAEAAV0@ABV0@@Z; Err::operator=(Err const &)
0x1002422b  test    dword ptr [esi], 0FFFFFFFEh
0x10024231  jz      short loc_10024253
0x10024233  mov     eax, [esi+0Ch]
0x10024236  test    eax, eax
0x10024238  jz      short loc_10024243
0x1002423a  push    eax; Block
0x1002423b  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10024240  add     esp, 4
0x10024243  mov     eax, [esi+10h]
0x10024246  test    eax, eax
0x10024248  jz      short loc_10024253
0x1002424a  push    eax; Block
0x1002424b  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10024250  add     esp, 4
0x10024253  mov     dword ptr [esi], 1
0x10024259  push    [ebp+lpCriticalSection]; lpCriticalSection
0x1002425c  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10024262  test    edi, 0FFFFFFFEh
0x10024268  jz      short loc_1002428A
0x1002426a  mov     eax, [ebp+Block]
0x1002426d  test    eax, eax
0x1002426f  jz      short loc_1002427A
0x10024271  push    eax; Block
0x10024272  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10024277  add     esp, 4
0x1002427a  mov     eax, [ebp+var_2C]
0x1002427d  test    eax, eax
0x1002427f  jz      short loc_1002428A
0x10024281  push    eax; Block
0x10024282  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10024287  add     esp, 4
0x1002428a  mov     ecx, [ebp+var_C]
0x1002428d  mov     large fs:0, ecx
0x10024294  pop     ecx
0x10024295  pop     edi
0x10024296  pop     esi
0x10024297  pop     ebx
0x10024298  mov     esp, ebp
0x1002429a  pop     ebp
0x1002429b  retn    0Ch
0x100605f0  lea     ecx, [ebp+var_3C]; this
0x100605f3  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x100605fd  nop
0x100605fe  nop
0x100605ff  mov     edx, [esp-4+arg_4]
0x10060603  lea     eax, [edx+0Ch]
0x10060606  mov     ecx, [edx-40h]
0x10060609  xor     ecx, eax; StackCookie
0x1006060b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10060610  mov     eax, offset stru_100634A0
0x10060615  jmp     ___CxxFrameHandler3
```
