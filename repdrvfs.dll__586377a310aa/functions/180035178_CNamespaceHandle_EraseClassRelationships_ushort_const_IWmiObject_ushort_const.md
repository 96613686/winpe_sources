# CNamespaceHandle::EraseClassRelationships(ushort const *,_IWmiObject *,ushort const *)

- ea: `0x180035178`
- end: `0x180035435`
- name: `?EraseClassRelationships@CNamespaceHandle@@IEAAJPEBGPEAU_IWmiObject@@0@Z`
- size: `701`
- prototype: `__int64 __fastcall(CNamespaceHandle *this, unsigned __int16 *, struct _IWmiObject *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800253d4`
- `0x180027150`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x180030fcc`
- `0x180034de0`
- `0x180035178`
- `0x18003543c`
- `0x180048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180035224`
- `wbemcomn!GetMemLogObject` at `0x1800352a0`
- `wbemcomn!GetMemLogObject` at `0x1800352fd`
- `wbemcomn!GetMemLogObject` at `0x1800353b4`
- `wbemcomn!GetMemLogObject` at `0x180035224`
- `wbemcomn!GetMemLogObject` at `0x1800352a0`
- `wbemcomn!GetMemLogObject` at `0x1800352fd`
- `wbemcomn!GetMemLogObject` at `0x1800353b4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003522f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800352ab`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180035308`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800353bf`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003522f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800352ab`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180035308`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800353bf`
- `OLEAUT32!__imp_VariantInit` at `0x1800351e1`
- `OLEAUT32!__imp_VariantInit` at `0x1800351e1`
- `OLEAUT32!__imp_VariantClear` at `0x180035419`
- `OLEAUT32!__imp_VariantClear` at `0x180035419`

## pseudocode

```c
__int64 __fastcall CNamespaceHandle::EraseClassRelationships(
        CNamespaceHandle *this,
        unsigned __int16 *a2,
        struct _IWmiObject *a3,
        const unsigned __int16 *a4)
{
  int v7; // ebx
  CMemoryLog *v8; // rax
  CVarObjHeap *v9; // rcx
  __int64 v10; // rdx
  const unsigned __int16 *bstrVal; // r8
  CMemoryLog *v12; // rax
  CMemoryLog *v13; // rax
  CMemoryLog *MemLogObject; // rax
  VARIANTARG pvarg; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int16 *v17; // [rsp+98h] [rbp+38h] BYREF
  unsigned __int16 *v18; // [rsp+A0h] [rbp+40h] BYREF

  v17 = a2;
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 419, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
  }
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v7 = (*(__int64 (__fastcall **)(struct _IWmiObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)a3 + 32LL))(
         a3,
         L"__SUPERCLASS",
         0,
         &pvarg,
         0,
         0);
  if ( v7 >= 0 )
  {
    bstrVal = pvarg.bstrVal;
    if ( pvarg.vt != 8 )
      bstrVal = &qword_18004AEE0;
    v7 = CNamespaceHandle::EraseParentChildRelationship(this, a4, bstrVal);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(struct _IWmiObject *, __int64))(*(_QWORD *)a3 + 64LL))(a3, 8);
      if ( v7 >= 0 )
      {
        v17 = 0;
        while ( 1 )
        {
          if ( (*(unsigned int (__fastcall **)(struct _IWmiObject *, _QWORD, unsigned __int16 **, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a3 + 72LL))(
                 a3,
                 0,
                 &v17,
                 0,
                 0,
                 0) )
          {
            (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)a3 + 80LL))(a3);
            v7 = 0;
            goto LABEL_34;
          }
          v18 = v17;
          v7 = CNamespaceHandle::EraseClassReference(this, a3, a4, v17);
          if ( (int)(v7 + 0x80000000) >= 0 && v7 != -2147217406 )
            break;
          CSysFreeMe::~CSysFreeMe((CSysFreeMe *)&v18);
        }
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, v7);
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            423,
            WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
            (unsigned int)v7);
        }
        CSysFreeMe::~CSysFreeMe((CSysFreeMe *)&v18);
      }
      else
      {
        v13 = GetMemLogObject();
        CMemoryLog::Write(v13, v7);
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v10 = 422;
          goto LABEL_10;
        }
      }
    }
    else
    {
      v12 = GetMemLogObject();
      CMemoryLog::Write(v12, v7);
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = 421;
        goto LABEL_10;
      }
    }
  }
  else
  {
    v8 = GetMemLogObject();
    CMemoryLog::Write(v8, v7);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 420;
LABEL_10:
      WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, (unsigned int)v7);
    }
  }
LABEL_34:
  VariantClear(&pvarg);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180035178  mov     [rsp-28h+arg_0], rbx
0x18003517d  mov     [rsp-28h+arg_8], rdx
0x180035182  push    rbp
0x180035183  push    rsi
0x180035184  push    rdi
0x180035185  push    r13
0x180035187  push    r14
0x180035189  mov     rbp, rsp
0x18003518c  sub     rsp, 60h
0x180035190  mov     rsi, r9
0x180035193  mov     rdi, r8
0x180035196  mov     r14, rcx
0x180035199  lea     rax, WPP_GLOBAL_Control
0x1800351a0  lea     r13, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x1800351a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800351ae  cmp     rcx, rax
0x1800351b1  jz      short loc_1800351D0
0x1800351b3  test    byte ptr [rcx+1Ch], 1
0x1800351b7  jz      short loc_1800351D0
0x1800351b9  cmp     byte ptr [rcx+19h], 5
0x1800351bd  jb      short loc_1800351D0
0x1800351bf  mov     edx, 1A3h
0x1800351c4  mov     r8, r13
0x1800351c7  mov     rcx, [rcx+10h]
0x1800351cb  call    WPP_SF_
0x1800351d0  xorps   xmm0, xmm0
0x1800351d3  xor     eax, eax
0x1800351d5  movups  xmmword ptr [rbp+pvarg], xmm0
0x1800351d9  mov     qword ptr [rbp+pvarg+10h], rax
0x1800351dd  lea     rcx, [rbp+pvarg]; pvarg
0x1800351e1  call    cs:__imp_VariantInit
0x1800351e7  mov     rax, [rdi]
0x1800351ea  mov     [rsp+60h+var_38], 0
0x1800351f3  mov     [rsp+60h+var_40], 0
0x1800351fc  lea     r9, [rbp+pvarg]
0x180035200  xor     r8d, r8d
0x180035203  lea     rdx, aSuperclass; "__SUPERCLASS"
0x18003520a  mov     rcx, rdi
0x18003520d  mov     rax, [rax+20h]
0x180035211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035216  mov     ebx, eax
0x180035218  lea     rax, [rbp+pvarg]
0x18003521c  mov     [rbp+var_20], rax
0x180035220  test    ebx, ebx
0x180035222  jns     short loc_180035279
0x180035224  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003522a  mov     edx, ebx
0x18003522c  mov     rcx, rax
0x18003522f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180035235  mov     rcx, cs:WPP_GLOBAL_Control
0x18003523c  lea     rax, WPP_GLOBAL_Control
0x180035243  cmp     rcx, rax
0x180035246  jz      loc_180035415
0x18003524c  test    byte ptr [rcx+1Ch], 1
0x180035250  jz      loc_180035415
0x180035256  cmp     byte ptr [rcx+19h], 2
0x18003525a  jb      loc_180035415
0x180035260  mov     edx, 1A4h
0x180035265  mov     r9d, ebx
0x180035268  mov     r8, r13
0x18003526b  mov     rcx, [rcx+10h]
0x18003526f  call    WPP_SF_d
0x180035274  jmp     loc_180035415
0x180035279  mov     eax, 8
0x18003527e  mov     rdx, rsi; unsigned __int16 *
0x180035281  mov     rcx, r14; this
0x180035284  cmp     word ptr [rbp+pvarg], ax
0x180035288  mov     r8, qword ptr [rbp+pvarg+8]
0x18003528c  jz      short loc_180035295
0x18003528e  lea     r8, qword_18004AEE0; unsigned __int16 *
0x180035295  call    ?EraseParentChildRelationship@CNamespaceHandle@@IEAAJPEBG0@Z; CNamespaceHandle::EraseParentChildRelationship(ushort const *,ushort const *)
0x18003529a  mov     ebx, eax
0x18003529c  test    eax, eax
0x18003529e  jns     short loc_1800352E3
0x1800352a0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800352a6  mov     edx, ebx
0x1800352a8  mov     rcx, rax
0x1800352ab  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800352b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800352b8  lea     rax, WPP_GLOBAL_Control
0x1800352bf  cmp     rcx, rax
0x1800352c2  jz      loc_180035415
0x1800352c8  test    byte ptr [rcx+1Ch], 1
0x1800352cc  jz      loc_180035415
0x1800352d2  cmp     byte ptr [rcx+19h], 2
0x1800352d6  jb      loc_180035415
0x1800352dc  mov     edx, 1A5h
0x1800352e1  jmp     short loc_180035265
0x1800352e3  mov     rax, [rdi]
0x1800352e6  mov     edx, 8
0x1800352eb  mov     rcx, rdi
0x1800352ee  mov     rax, [rax+40h]
0x1800352f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800352f7  mov     ebx, eax
0x1800352f9  test    eax, eax
0x1800352fb  jns     short loc_180035343
0x1800352fd  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180035303  mov     edx, ebx
0x180035305  mov     rcx, rax
0x180035308  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003530e  mov     rcx, cs:WPP_GLOBAL_Control
0x180035315  lea     rax, WPP_GLOBAL_Control
0x18003531c  cmp     rcx, rax
0x18003531f  jz      loc_180035415
0x180035325  test    byte ptr [rcx+1Ch], 1
0x180035329  jz      loc_180035415
0x18003532f  cmp     byte ptr [rcx+19h], 2
0x180035333  jb      loc_180035415
0x180035339  mov     edx, 1A6h
0x18003533e  jmp     loc_180035265
0x180035343  mov     [rbp+arg_8], 0
0x18003534b  mov     rax, [rdi]
0x18003534e  mov     [rsp+60h+var_38], 0
0x180035357  mov     [rsp+60h+var_40], 0
0x180035360  xor     r9d, r9d
0x180035363  lea     r8, [rbp+arg_8]
0x180035367  xor     edx, edx
0x180035369  mov     rcx, rdi
0x18003536c  mov     rax, [rax+48h]
0x180035370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035375  test    eax, eax
0x180035377  jnz     loc_180035404
0x18003537d  mov     r9, [rbp+arg_8]; unsigned __int16 *
0x180035381  mov     [rbp+arg_10], r9
0x180035385  mov     r8, rsi; unsigned __int16 *
0x180035388  mov     rdx, rdi; struct _IWmiObject *
0x18003538b  mov     rcx, r14; this
0x18003538e  call    ?EraseClassReference@CNamespaceHandle@@IEAAJPEAU_IWmiObject@@PEBG1@Z; CNamespaceHandle::EraseClassReference(_IWmiObject *,ushort const *,ushort const *)
0x180035393  mov     ebx, eax
0x180035395  mov     eax, 80000000h
0x18003539a  lea     ecx, [rbx+rax]
0x18003539d  test    eax, ecx
0x18003539f  jnz     short loc_1800353A9
0x1800353a1  cmp     ebx, 80041002h
0x1800353a7  jnz     short loc_1800353B4
0x1800353a9  lea     rcx, [rbp+arg_10]; this
0x1800353ad  call    ??1CSysFreeMe@@QEAA@XZ; CSysFreeMe::~CSysFreeMe(void)
0x1800353b2  jmp     short loc_18003534B
0x1800353b4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800353ba  mov     edx, ebx
0x1800353bc  mov     rcx, rax
0x1800353bf  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800353c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800353cc  lea     rax, WPP_GLOBAL_Control
0x1800353d3  cmp     rcx, rax
0x1800353d6  jz      short loc_1800353F9
0x1800353d8  test    byte ptr [rcx+1Ch], 1
0x1800353dc  jz      short loc_1800353F9
0x1800353de  cmp     byte ptr [rcx+19h], 2
0x1800353e2  jb      short loc_1800353F9
0x1800353e4  mov     edx, 1A7h
0x1800353e9  mov     r9d, ebx
0x1800353ec  mov     r8, r13
0x1800353ef  mov     rcx, [rcx+10h]
0x1800353f3  call    WPP_SF_d
0x1800353f8  nop
0x1800353f9  lea     rcx, [rbp+arg_10]; this
0x1800353fd  call    ??1CSysFreeMe@@QEAA@XZ; CSysFreeMe::~CSysFreeMe(void)
0x180035402  jmp     short loc_180035415
0x180035404  mov     rax, [rdi]
0x180035407  mov     rcx, rdi
0x18003540a  mov     rax, [rax+50h]
0x18003540e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035413  xor     ebx, ebx
0x180035415  lea     rcx, [rbp+pvarg]; pvarg
0x180035419  call    cs:__imp_VariantClear
0x18003541f  mov     eax, ebx
0x180035421  mov     rbx, [rsp+60h+arg_0]
0x180035429  add     rsp, 60h
0x18003542d  pop     r14
0x18003542f  pop     r13
0x180035431  pop     rdi
0x180035432  pop     rsi
0x180035433  pop     rbp
0x180035434  retn
```
