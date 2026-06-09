# CBTree::InsertPhase2(SIdxKeyTable *,ushort,char *,ulong,ulong * const,long &)

- ea: `0x180010fe4`
- end: `0x180011296`
- name: `?InsertPhase2@CBTree@@AEAAKPEAVSIdxKeyTable@@GPEADKQEAKAEAJ@Z`
- size: `690`
- prototype: `unsigned int __usercall@<eax>(CBTree *__hidden this@<rcx>, struct SIdxKeyTable *@<rdx>, unsigned __int16@<r8w>, char *@<r9>, unsigned int, unsigned int *const, int *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180011904`
- `0x1800213c8`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x18000d7e0`
- `0x1800109d0`
- `0x180010fa0`
- `0x180010fe4`
- `0x1800129a0`
- `0x180012aac`
- `0x180037748`
- `0x180037da8`
- `0x180037fb0`
- `0x180038410`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180011056`
- `wbemcomn!GetMemLogObject` at `0x18001123b`
- `wbemcomn!GetMemLogObject` at `0x180011056`
- `wbemcomn!GetMemLogObject` at `0x18001123b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180011061`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180011246`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180011061`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180011246`

## pseudocode

```c
__int64 __fastcall CBTree::InsertPhase2(
        CBTreeFile **this,
        void **a2,
        unsigned __int16 a3,
        char *a4,
        unsigned int a5,
        unsigned int *const a6,
        int *a7)
{
  unsigned int v11; // ebx
  CMemoryLog *MemLogObject; // rax
  CVarObjHeap *v13; // rcx
  __int64 v14; // rdx
  int *v15; // r12
  unsigned int *v16; // r13
  _DWORD *v17; // rdx
  struct SIdxKeyTable *v18; // rsi
  SIdxKeyTable *v19; // rdi
  int v20; // eax
  __int64 v21; // rcx
  unsigned int v22; // edx
  CBTreeFile *v23; // rcx
  unsigned int v24; // edi
  CBTreeFile *v25; // rcx
  int v26; // ebx
  unsigned int v27; // eax
  CMemoryLog *v28; // rax
  SIdxKeyTable *v30; // [rsp+20h] [rbp-18h] BYREF
  void *v31; // [rsp+28h] [rbp-10h] BYREF
  SIdxKeyTable *v32; // [rsp+98h] [rbp+60h] BYREF

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids);
  }
  if ( a4 )
  {
    v11 = SIdxKeyTable::AddKey(a2, a4, a3, 0);
    if ( v11 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v11);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = 117;
        goto LABEL_40;
      }
      return v11;
    }
  }
  _InterlockedIncrement((volatile signed __int32 *)a2);
  v15 = a7;
  v16 = a6;
  while ( 1 )
  {
    v17 = a2[8];
    v18 = 0;
    v19 = 0;
    v20 = *((_DWORD *)a2 + 3) + 5;
    v32 = 0;
    v30 = 0;
    if ( (unsigned int)(v17[9] + 2 * (*v17 + *((_DWORD *)a2 + 15) + 5 * v20)) <= 0x2000 )
      break;
    v21 = *v15;
    v22 = v16[v21];
    *v15 = v21 - 1;
    if ( !(_DWORD)v21 )
    {
      v23 = *this;
      v31 = 0;
      v11 = CBTreeFile::NewPage(v23, &v31);
      if ( v11 )
        goto LABEL_32;
      v24 = *((_DWORD *)v31 + 1);
      _BtrMemFree(v31);
      v11 = SIdxKeyTable::Create(v24, &v32);
      if ( v11 || (v11 = CBTreeFile::SetRootPage(*this, v24)) != 0 )
      {
LABEL_28:
        v19 = v32;
        goto LABEL_30;
      }
      SIdxKeyTable::Release(this[1]);
      v19 = v32;
      this[1] = v32;
LABEL_19:
      _InterlockedIncrement((volatile signed __int32 *)v19);
      goto LABEL_22;
    }
    v19 = this[1];
    if ( v22 == *((_DWORD *)v19 + 1) )
      goto LABEL_19;
    v11 = CBTree::ReadIdxPage((CBTree *)this, v22, 0, &v32);
    if ( v11 )
      goto LABEL_28;
    v19 = v32;
LABEL_22:
    v25 = *this;
    v32 = 0;
    v11 = CBTreeFile::NewPage(v25, (void **)&v32);
    if ( v11 )
      goto LABEL_30;
    v26 = *((_DWORD *)v32 + 1);
    _BtrMemFree(v32);
    v27 = SIdxKeyTable::Create(v26, &v30);
    v18 = v30;
    v11 = v27;
    if ( v27 )
      goto LABEL_30;
    v11 = SIdxKeyTable::Redist((SIdxKeyTable *)a2, v19, v30);
    if ( v11 )
      goto LABEL_30;
    v11 = CBTree::WriteIdxPage((CBTree *)this, (struct SIdxKeyTable *)a2);
    if ( v11 )
      goto LABEL_30;
    v11 = CBTree::WriteIdxPage((CBTree *)this, v18);
    if ( v11 )
      goto LABEL_30;
    SIdxKeyTable::Release((SIdxKeyTable *)a2);
    SIdxKeyTable::Release(v18);
    a2 = (void **)v19;
  }
  v11 = CBTree::WriteIdxPage((CBTree *)this, (struct SIdxKeyTable *)a2);
LABEL_30:
  if ( v19 )
    SIdxKeyTable::Release(v19);
LABEL_32:
  SIdxKeyTable::Release((SIdxKeyTable *)a2);
  if ( v18 )
    SIdxKeyTable::Release(v18);
  if ( v11 )
  {
    v28 = GetMemLogObject();
    CMemoryLog::Write(v28, v11);
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v14 = 118;
LABEL_40:
    WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, v11);
  }
  return v11;
}

```

## disassembly

```asm
0x180010fe4  push    rbp
0x180010fe6  push    rbx
0x180010fe7  push    rsi
0x180010fe8  push    rdi
0x180010fe9  push    r12
0x180010feb  push    r13
0x180010fed  push    r14
0x180010fef  push    r15
0x180010ff1  mov     rbp, rsp
0x180010ff4  sub     rsp, 38h
0x180010ff8  mov     rbx, r9
0x180010ffb  movzx   edi, r8w
0x180010fff  mov     r14, rdx
0x180011002  mov     r15, rcx
0x180011005  mov     rcx, cs:WPP_GLOBAL_Control
0x18001100c  lea     rsi, WPP_GLOBAL_Control
0x180011013  cmp     rcx, rsi
0x180011016  jz      short loc_180011039
0x180011018  test    byte ptr [rcx+1Ch], 1
0x18001101c  jz      short loc_180011039
0x18001101e  cmp     byte ptr [rcx+19h], 5
0x180011022  jb      short loc_180011039
0x180011024  mov     rcx, [rcx+10h]
0x180011028  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x18001102f  mov     edx, 74h ; 't'
0x180011034  call    WPP_SF_
0x180011039  test    rbx, rbx
0x18001103c  jz      short loc_180011095
0x18001103e  xor     r9d, r9d; unsigned int
0x180011041  movzx   r8d, di; unsigned __int16
0x180011045  mov     rdx, rbx; char *
0x180011048  mov     rcx, r14; this
0x18001104b  call    ?AddKey@SIdxKeyTable@@QEAAKPEADGK@Z; SIdxKeyTable::AddKey(char *,ushort,ulong)
0x180011050  mov     ebx, eax
0x180011052  test    eax, eax
0x180011054  jz      short loc_180011095
0x180011056  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001105c  mov     rcx, rax
0x18001105f  mov     edx, ebx
0x180011061  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180011067  mov     rcx, cs:WPP_GLOBAL_Control
0x18001106e  cmp     rcx, rsi
0x180011071  jz      loc_180011283
0x180011077  test    byte ptr [rcx+1Ch], 1
0x18001107b  jz      loc_180011283
0x180011081  cmp     byte ptr [rcx+19h], 2
0x180011085  jb      loc_180011283
0x18001108b  mov     edx, 75h ; 'u'
0x180011090  jmp     loc_180011270
0x180011095  lock inc dword ptr [r14]
0x180011099  mov     r12, [rbp+arg_30]
0x18001109d  mov     r13, [rbp+arg_28]
0x1800110a1  mov     rdx, [r14+40h]
0x1800110a5  xor     esi, esi
0x1800110a7  mov     eax, [r14+0Ch]
0x1800110ab  xor     edi, edi
0x1800110ad  add     eax, 5
0x1800110b0  mov     [rbp+arg_18], rdi
0x1800110b4  mov     [rbp+var_18], rsi
0x1800110b8  lea     ecx, [rax+rax*4]
0x1800110bb  mov     eax, [rdx+24h]
0x1800110be  add     ecx, [r14+3Ch]
0x1800110c2  add     ecx, [rdx]
0x1800110c4  lea     ecx, [rax+rcx*2]
0x1800110c7  cmp     ecx, 2000h
0x1800110cd  jbe     loc_180011208
0x1800110d3  movsxd  rcx, dword ptr [r12]
0x1800110d7  mov     edx, [r13+rcx*4+0]; unsigned int
0x1800110dc  lea     eax, [rcx-1]
0x1800110df  mov     [r12], eax
0x1800110e3  cmp     eax, 0FFFFFFFFh
0x1800110e6  jnz     short loc_18001114A
0x1800110e8  mov     rcx, [r15]; this
0x1800110eb  lea     rdx, [rbp+var_10]; void **
0x1800110ef  mov     [rbp+var_10], rdi
0x1800110f3  call    ?NewPage@CBTreeFile@@QEAAKPEAPEAX@Z; CBTreeFile::NewPage(void * *)
0x1800110f8  mov     ebx, eax
0x1800110fa  test    eax, eax
0x1800110fc  jnz     loc_180011222
0x180011102  mov     rcx, [rbp+var_10]; void *
0x180011106  mov     edi, [rcx+4]
0x180011109  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x18001110e  lea     rdx, [rbp+arg_18]; struct SIdxKeyTable **
0x180011112  mov     ecx, edi; unsigned int
0x180011114  call    ?Create@SIdxKeyTable@@SAKKPEAPEAV1@@Z; SIdxKeyTable::Create(ulong,SIdxKeyTable * *)
0x180011119  mov     ebx, eax
0x18001111b  test    eax, eax
0x18001111d  jnz     loc_180011202
0x180011123  mov     rcx, [r15]; this
0x180011126  mov     edx, edi; unsigned int
0x180011128  call    ?SetRootPage@CBTreeFile@@QEAAKK@Z; CBTreeFile::SetRootPage(ulong)
0x18001112d  mov     ebx, eax
0x18001112f  test    eax, eax
0x180011131  jnz     loc_180011202
0x180011137  mov     rcx, [r15+8]; this
0x18001113b  call    ?Release@SIdxKeyTable@@QEAAKXZ; SIdxKeyTable::Release(void)
0x180011140  mov     rdi, [rbp+arg_18]
0x180011144  mov     [r15+8], rdi
0x180011148  jmp     short loc_180011153
0x18001114a  mov     rdi, [r15+8]
0x18001114e  cmp     edx, [rdi+4]
0x180011151  jnz     short loc_180011158
0x180011153  lock inc dword ptr [rdi]
0x180011156  jmp     short loc_180011175
0x180011158  lea     r9, [rbp+arg_18]; struct SIdxKeyTable **
0x18001115c  xor     r8d, r8d; bool
0x18001115f  mov     rcx, r15; this
0x180011162  call    ?ReadIdxPage@CBTree@@AEAAKK_NPEAPEAVSIdxKeyTable@@@Z; CBTree::ReadIdxPage(ulong,bool,SIdxKeyTable * *)
0x180011167  mov     ebx, eax
0x180011169  test    eax, eax
0x18001116b  jnz     loc_180011202
0x180011171  mov     rdi, [rbp+arg_18]
0x180011175  mov     rcx, [r15]; this
0x180011178  lea     rdx, [rbp+arg_18]; void **
0x18001117c  mov     [rbp+arg_18], 0
0x180011184  call    ?NewPage@CBTreeFile@@QEAAKPEAPEAX@Z; CBTreeFile::NewPage(void * *)
0x180011189  mov     ebx, eax
0x18001118b  test    eax, eax
0x18001118d  jnz     loc_180011215
0x180011193  mov     rcx, [rbp+arg_18]; void *
0x180011197  mov     ebx, [rcx+4]
0x18001119a  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x18001119f  lea     rdx, [rbp+var_18]; struct SIdxKeyTable **
0x1800111a3  mov     ecx, ebx; unsigned int
0x1800111a5  call    ?Create@SIdxKeyTable@@SAKKPEAPEAV1@@Z; SIdxKeyTable::Create(ulong,SIdxKeyTable * *)
0x1800111aa  mov     rsi, [rbp+var_18]
0x1800111ae  mov     ebx, eax
0x1800111b0  test    eax, eax
0x1800111b2  jnz     short loc_180011215
0x1800111b4  mov     r8, rsi; struct SIdxKeyTable *
0x1800111b7  mov     rdx, rdi; struct SIdxKeyTable *
0x1800111ba  mov     rcx, r14; this
0x1800111bd  call    ?Redist@SIdxKeyTable@@QEAAKPEAV1@0@Z; SIdxKeyTable::Redist(SIdxKeyTable *,SIdxKeyTable *)
0x1800111c2  mov     ebx, eax
0x1800111c4  test    eax, eax
0x1800111c6  jnz     short loc_180011215
0x1800111c8  mov     rdx, r14; struct SIdxKeyTable *
0x1800111cb  mov     rcx, r15; this
0x1800111ce  call    ?WriteIdxPage@CBTree@@AEAAKPEAVSIdxKeyTable@@@Z; CBTree::WriteIdxPage(SIdxKeyTable *)
0x1800111d3  mov     ebx, eax
0x1800111d5  test    eax, eax
0x1800111d7  jnz     short loc_180011215
0x1800111d9  mov     rdx, rsi; struct SIdxKeyTable *
0x1800111dc  mov     rcx, r15; this
0x1800111df  call    ?WriteIdxPage@CBTree@@AEAAKPEAVSIdxKeyTable@@@Z; CBTree::WriteIdxPage(SIdxKeyTable *)
0x1800111e4  mov     ebx, eax
0x1800111e6  test    eax, eax
0x1800111e8  jnz     short loc_180011215
0x1800111ea  mov     rcx, r14; this
0x1800111ed  call    ?Release@SIdxKeyTable@@QEAAKXZ; SIdxKeyTable::Release(void)
0x1800111f2  mov     rcx, rsi; this
0x1800111f5  call    ?Release@SIdxKeyTable@@QEAAKXZ; SIdxKeyTable::Release(void)
0x1800111fa  mov     r14, rdi
0x1800111fd  jmp     loc_1800110A1
0x180011202  mov     rdi, [rbp+arg_18]
0x180011206  jmp     short loc_180011215
0x180011208  mov     rdx, r14; struct SIdxKeyTable *
0x18001120b  mov     rcx, r15; this
0x18001120e  call    ?WriteIdxPage@CBTree@@AEAAKPEAVSIdxKeyTable@@@Z; CBTree::WriteIdxPage(SIdxKeyTable *)
0x180011213  mov     ebx, eax
0x180011215  test    rdi, rdi
0x180011218  jz      short loc_180011222
0x18001121a  mov     rcx, rdi; this
0x18001121d  call    ?Release@SIdxKeyTable@@QEAAKXZ; SIdxKeyTable::Release(void)
0x180011222  mov     rcx, r14; this
0x180011225  call    ?Release@SIdxKeyTable@@QEAAKXZ; SIdxKeyTable::Release(void)
0x18001122a  test    rsi, rsi
0x18001122d  jz      short loc_180011237
0x18001122f  mov     rcx, rsi; this
0x180011232  call    ?Release@SIdxKeyTable@@QEAAKXZ; SIdxKeyTable::Release(void)
0x180011237  test    ebx, ebx
0x180011239  jz      short loc_18001124C
0x18001123b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180011241  mov     rcx, rax
0x180011244  mov     edx, ebx
0x180011246  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001124c  mov     rcx, cs:WPP_GLOBAL_Control
0x180011253  lea     rax, WPP_GLOBAL_Control
0x18001125a  cmp     rcx, rax
0x18001125d  jz      short loc_180011283
0x18001125f  test    byte ptr [rcx+1Ch], 1
0x180011263  jz      short loc_180011283
0x180011265  cmp     byte ptr [rcx+19h], 2
0x180011269  jb      short loc_180011283
0x18001126b  mov     edx, 76h ; 'v'
0x180011270  mov     rcx, [rcx+10h]
0x180011274  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x18001127b  mov     r9d, ebx
0x18001127e  call    WPP_SF_d
0x180011283  mov     eax, ebx
0x180011285  add     rsp, 38h
0x180011289  pop     r15
0x18001128b  pop     r14
0x18001128d  pop     r13
0x18001128f  pop     r12
0x180011291  pop     rdi
0x180011292  pop     rsi
0x180011293  pop     rbx
0x180011294  pop     rbp
0x180011295  retn
```
