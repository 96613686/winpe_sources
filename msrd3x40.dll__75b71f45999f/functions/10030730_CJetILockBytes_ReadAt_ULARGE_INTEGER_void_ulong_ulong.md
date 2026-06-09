# CJetILockBytes::ReadAt(_ULARGE_INTEGER,void *,ulong,ulong *)

- ea: `0x10030730`
- end: `0x10030949`
- name: `?ReadAt@CJetILockBytes@@UAGJT_ULARGE_INTEGER@@PAXKPAK@Z`
- size: `537`
- prototype: `int(CJetILockBytes *__hidden this, union _ULARGE_INTEGER, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops`

## callees

- `0x1000eb60`
- `0x1000f750`
- `0x10018200`
- `0x100261a0`
- `0x10030730`
- `0x1003e9a0`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005f064`

## pseudocode

```c
int __stdcall CJetILockBytes::ReadAt(
        CJetILockBytes *this,
        union _ULARGE_INTEGER a2,
        void *a3,
        unsigned int a4,
        unsigned int *a5)
{
  int v5; // ecx
  CJetILockBytes *v6; // esi
  int v7; // ebx
  int v8; // esi
  int v9; // eax
  int v10; // edx
  int v11; // esi
  int v12; // eax
  int v13; // ecx
  int v14; // eax
  int v15; // ecx
  ColumnLv *v16; // ecx
  LongValue *LvObject; // eax
  unsigned int v18; // eax
  unsigned int v20; // [esp+0h] [ebp-38h]
  struct Err *v21; // [esp+4h] [ebp-34h]
  void *Block[4]; // [esp+10h] [ebp-28h] BYREF
  void *v23; // [esp+20h] [ebp-18h]
  int v24; // [esp+24h] [ebp-14h]
  unsigned int v25; // [esp+28h] [ebp-10h]
  int v26; // [esp+34h] [ebp-4h]

  v5 = 1;
  v25 = 0;
  Block[0] = (void *)1;
  v6 = this;
  v26 = 0;
  v7 = *(_DWORD *)(*((_DWORD *)this + 4) + 8);
  if ( a5 )
    *a5 = 0;
  if ( *((_DWORD *)this + 3) )
  {
    v8 = -2147418113;
  }
  else if ( a2.HighPart )
  {
    v8 = -2147467259;
  }
  else
  {
    if ( *(_DWORD *)(v7 + 44) )
    {
      (*(void (__thiscall **)(_DWORD, void **))(**(_DWORD **)(v7 + 32) + 48))(*(_DWORD *)(v7 + 32), Block);
      v5 = (int)Block[0];
      v6 = this;
    }
    if ( (v5 & 8) != 0 )
      goto LABEL_31;
    v9 = *((_DWORD *)v6 + 4);
    v25 = 0;
    v10 = *(_DWORD *)(v9 + 12);
    v24 = v10;
    if ( v10 <= -1 || v10 >= *(_DWORD *)(*(_DWORD *)(v7 + 12) + 12) )
    {
      if ( v5 < 8 )
      {
        if ( (v5 & 0xFFFFFFFE) != 0 )
        {
          if ( Block[3] )
            operator delete[](Block[3]);
          if ( v23 )
            operator delete[](v23);
        }
        *(_OWORD *)Block = _xmm;
        v5 = _xmm;
        v23 = 0;
      }
      v25 = 0;
    }
    else
    {
      v11 = v7 + 96;
      if ( *(_DWORD *)(v7 + 44) == 3 )
      {
        v12 = (*(int (__thiscall **)(_DWORD, void **))(**(_DWORD **)(v7 + 32) + 48))(*(_DWORD *)(v7 + 32), Block);
        v10 = v24;
        v11 = v7 + 96;
        v13 = v12;
        v14 = 1;
      }
      else
      {
        v13 = *(_DWORD *)(v7 + 52);
        v14 = 0;
      }
      *(_DWORD *)v11 = v13;
      *(_DWORD *)(v7 + 124) = v14;
      v5 = (int)Block[0];
      if ( ((int)Block[0] & 8) == 0 )
      {
        v15 = *(_DWORD *)(v7 + 12);
        *(_DWORD *)(v7 + 100) = a3;
        *(_DWORD *)(v7 + 104) = a4;
        *(_DWORD *)(v7 + 112) = a2.LowPart;
        v16 = (unsigned int)v10 >= 0xFF ? 0 : *(ColumnLv **)(v15 + 4 * v10 + 376);
        v25 = 0;
        *(_DWORD *)(v11 + 20) = v16;
        LvObject = ColumnLv::FindOrCreateLvObject(v16, (struct tagColParams *)v11, (struct Err *)Block);
        v5 = (int)Block[0];
        if ( ((int)Block[0] & 8) == 0 )
        {
          v18 = LongValue::ReadAt(LvObject, (struct tagColParams *)v11, (struct Err *)Block, 0);
          v5 = (int)Block[0];
          v25 = v18;
        }
      }
    }
    if ( (v5 & 8) != 0 )
    {
LABEL_31:
      ErrIsamErrToJetErr(v20, v21);
      v5 = (int)Block[0];
      v8 = -2147467259;
    }
    else
    {
      if ( a5 )
        *a5 = v25;
      v8 = 0;
    }
  }
  if ( (v5 & 0xFFFFFFFE) != 0 )
  {
    if ( Block[3] )
      operator delete[](Block[3]);
    if ( v23 )
      operator delete[](v23);
  }
  return v8;
}

```

## disassembly

```asm
0x10030730  mov     edi, edi
0x10030732  push    ebp
0x10030733  mov     ebp, esp
0x10030735  push    0FFFFFFFFh
0x10030737  push    offset ?Write@PageDesc@@QAEXAAVErr@@@Z_SEH
0x1003073c  mov     eax, large fs:0
0x10030742  push    eax
0x10030743  sub     esp, 1Ch
0x10030746  push    ebx
0x10030747  push    esi
0x10030748  push    edi; struct Err *
0x10030749  mov     eax, ___security_cookie
0x1003074e  xor     eax, ebp
0x10030750  push    eax; unsigned int
0x10030751  lea     eax, [ebp+var_C]
0x10030754  mov     large fs:0, eax
0x1003075a  mov     ecx, 1
0x1003075f  mov     [ebp+var_10], 0
0x10030766  mov     [ebp+Block], ecx
0x10030769  mov     esi, [ebp+this]
0x1003076c  mov     [ebp+var_4], 0
0x10030773  mov     eax, [esi+10h]
0x10030776  mov     ebx, [eax+8]
0x10030779  mov     eax, [ebp+arg_14]
0x1003077c  test    eax, eax
0x1003077e  jz      short loc_10030786
0x10030780  mov     dword ptr [eax], 0
0x10030786  cmp     dword ptr [esi+0Ch], 0
0x1003078a  jz      short loc_10030796
0x1003078c  mov     esi, 8000FFFFh
0x10030791  jmp     loc_1003090B
0x10030796  cmp     dword ptr [ebp+arg_4+4], 0
0x1003079a  jz      short loc_100307A6
0x1003079c  mov     esi, 80004005h
0x100307a1  jmp     loc_1003090B
0x100307a6  cmp     dword ptr [ebx+2Ch], 0
0x100307aa  jz      short loc_100307CA
0x100307ac  mov     edi, [ebx+20h]
0x100307af  lea     ecx, [ebp+Block]
0x100307b2  push    ecx; void *
0x100307b3  mov     eax, [edi]
0x100307b5  mov     esi, [eax+30h]
0x100307b8  mov     ecx, esi
0x100307ba  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100307c0  mov     ecx, edi
0x100307c2  call    esi
0x100307c4  mov     ecx, [ebp+Block]
0x100307c7  mov     esi, [ebp+this]
0x100307ca  test    cl, 8
0x100307cd  jnz     loc_100308E5
0x100307d3  mov     eax, [esi+10h]
0x100307d6  mov     [ebp+var_10], 0
0x100307dd  mov     edx, [eax+0Ch]
0x100307e0  mov     [ebp+var_14], edx
0x100307e3  cmp     edx, 0FFFFFFFFh
0x100307e6  jle     loc_10030897
0x100307ec  mov     eax, [ebx+0Ch]
0x100307ef  cmp     edx, [eax+0Ch]
0x100307f2  jge     loc_10030897
0x100307f8  cmp     dword ptr [ebx+2Ch], 3
0x100307fc  lea     esi, [ebx+60h]
0x100307ff  jnz     short loc_10030828
0x10030801  mov     edi, [ebx+20h]
0x10030804  mov     eax, [edi]
0x10030806  mov     esi, [eax+30h]
0x10030809  lea     eax, [ebp+Block]
0x1003080c  push    eax; void *
0x1003080d  mov     ecx, esi
0x1003080f  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10030815  mov     ecx, edi
0x10030817  call    esi
0x10030819  mov     edx, [ebp+var_14]
0x1003081c  lea     esi, [ebx+60h]
0x1003081f  mov     ecx, eax
0x10030821  mov     eax, 1
0x10030826  jmp     short loc_1003082D
0x10030828  mov     ecx, [ebx+34h]
0x1003082b  xor     eax, eax
0x1003082d  mov     [esi], ecx
0x1003082f  mov     [ebx+7Ch], eax
0x10030832  mov     ecx, [ebp+Block]
0x10030835  test    cl, 8
0x10030838  jnz     short loc_10030892
0x1003083a  mov     eax, [ebp+arg_C]
0x1003083d  mov     ecx, [ebx+0Ch]
0x10030840  mov     [ebx+64h], eax
0x10030843  mov     eax, [ebp+arg_10]
0x10030846  mov     [ebx+68h], eax
0x10030849  mov     eax, dword ptr [ebp+arg_4]
0x1003084c  mov     [ebx+70h], eax
0x1003084f  cmp     edx, 0FFh
0x10030855  jnb     short loc_10030860
0x10030857  mov     ecx, [ecx+edx*4+178h]
0x1003085e  jmp     short loc_10030862
0x10030860  xor     ecx, ecx; this
0x10030862  lea     eax, [ebp+Block]
0x10030865  mov     [ebp+var_10], 0
0x1003086c  push    eax; struct Err *
0x1003086d  push    esi; struct tagColParams *
0x1003086e  mov     [esi+14h], ecx
0x10030871  call    ?FindOrCreateLvObject@ColumnLv@@QAEPAVLongValue@@PAUtagColParams@@AAVErr@@@Z; ColumnLv::FindOrCreateLvObject(tagColParams *,Err &)
0x10030876  mov     ecx, [ebp+Block]
0x10030879  test    cl, 8
0x1003087c  jnz     short loc_10030892
0x1003087e  push    0; unsigned int *
0x10030880  lea     ecx, [ebp+Block]
0x10030883  push    ecx; struct Err *
0x10030884  push    esi; struct tagColParams *
0x10030885  mov     ecx, eax; this
0x10030887  call    ?ReadAt@LongValue@@QAEKPAUtagColParams@@AAVErr@@PAK@Z; LongValue::ReadAt(tagColParams *,Err &,ulong *)
0x1003088c  mov     ecx, [ebp+Block]
0x1003088f  mov     [ebp+var_10], eax
0x10030892  mov     esi, [ebp+this]
0x10030895  jmp     short loc_100308E0
0x10030897  cmp     ecx, 8
0x1003089a  jge     short loc_100308D9
0x1003089c  test    ecx, 0FFFFFFFEh
0x100308a2  jz      short loc_100308C4
0x100308a4  mov     eax, [ebp+Block+0Ch]
0x100308a7  test    eax, eax
0x100308a9  jz      short loc_100308B4
0x100308ab  push    eax; Block
0x100308ac  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100308b1  add     esp, 4
0x100308b4  mov     eax, [ebp+var_18]
0x100308b7  test    eax, eax
0x100308b9  jz      short loc_100308C4
0x100308bb  push    eax; Block
0x100308bc  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100308c1  add     esp, 4
0x100308c4  movaps  xmm0, ds:__xmm@0000000000000000fffffb4a00000008
0x100308cb  movups  xmmword ptr [ebp+Block], xmm0
0x100308cf  mov     ecx, [ebp+Block]
0x100308d2  mov     [ebp+var_18], 0
0x100308d9  mov     [ebp+var_10], 0
0x100308e0  test    cl, 8
0x100308e3  jz      short loc_100308FD
0x100308e5  mov     ecx, [esi+10h]
0x100308e8  lea     edx, [ebp+Block]
0x100308eb  mov     ecx, [ecx+4]
0x100308ee  call    ?ErrIsamErrToJetErr@@YGJKAAVErr@@@Z; ErrIsamErrToJetErr(ulong,Err &)
0x100308f3  mov     ecx, [ebp+Block]
0x100308f6  mov     esi, 80004005h
0x100308fb  jmp     short loc_1003090B
0x100308fd  mov     edx, [ebp+arg_14]
0x10030900  test    edx, edx
0x10030902  jz      short loc_10030909
0x10030904  mov     eax, [ebp+var_10]
0x10030907  mov     [edx], eax
0x10030909  xor     esi, esi
0x1003090b  test    ecx, 0FFFFFFFEh
0x10030911  jz      short loc_10030933
0x10030913  mov     eax, [ebp+Block+0Ch]
0x10030916  test    eax, eax
0x10030918  jz      short loc_10030923
0x1003091a  push    eax; Block
0x1003091b  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10030920  add     esp, 4
0x10030923  mov     eax, [ebp+var_18]
0x10030926  test    eax, eax
0x10030928  jz      short loc_10030933
0x1003092a  push    eax; Block
0x1003092b  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10030930  add     esp, 4
0x10030933  mov     eax, esi
0x10030935  mov     ecx, [ebp+var_C]
0x10030938  mov     large fs:0, ecx
0x1003093f  pop     ecx
0x10030940  pop     edi
0x10030941  pop     esi
0x10030942  pop     ebx
0x10030943  mov     esp, ebp
0x10030945  pop     ebp
0x10030946  retn    18h
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
