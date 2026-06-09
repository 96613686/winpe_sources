# CWbemInstance::CopyTransferArrayBlob(CWbemInstance *,long,long,uchar *,CFlexArray &,long *)

- ea: `0x1800774d0`
- end: `0x1800777ae`
- name: `?CopyTransferArrayBlob@CWbemInstance@@SAJPEAV1@JJPEAEAEAVCFlexArray@@PEAJ@Z`
- size: `734`
- prototype: `__int64 __fastcall(struct CWbemInstance *, int, int, unsigned __int8 *, struct CFlexArray *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180071574`

## callees

- `0x180037120`
- `0x180077140`
- `0x1800774d0`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180077514`
- `wbemcomn!GetMemLogObject` at `0x18007760e`
- `wbemcomn!GetMemLogObject` at `0x1800776b1`
- `wbemcomn!GetMemLogObject` at `0x18007774e`
- `wbemcomn!GetMemLogObject` at `0x180077514`
- `wbemcomn!GetMemLogObject` at `0x18007760e`
- `wbemcomn!GetMemLogObject` at `0x1800776b1`
- `wbemcomn!GetMemLogObject` at `0x18007774e`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18007758a`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800775a5`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18007758a`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800775a5`
- `wbemcomn!?InsertAt@CFlexArray@@QEAAHHPEAX@Z` at `0x1800775f3`
- `wbemcomn!?InsertAt@CFlexArray@@QEAAHHPEAX@Z` at `0x1800775f3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180077524`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007761c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800776c1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180077759`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180077524`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007761c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800776c1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180077759`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x18007769f`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x18007769f`

## pseudocode

```c
__int64 __fastcall CWbemInstance::CopyTransferArrayBlob(
        struct CWbemInstance *a1,
        int a2,
        unsigned int a3,
        unsigned __int8 *a4,
        struct CFlexArray *a5,
        int *a6)
{
  __int64 v6; // r15
  __int64 result; // rax
  int v9; // ebx
  unsigned __int64 v10; // rsi
  CMemoryLog *MemLogObject; // rax
  unsigned __int8 *v12; // r14
  unsigned int v13; // edi
  CMemoryLog *v14; // rax
  __int64 v15; // r15
  unsigned int v16; // edi
  CWbemInstance **v17; // rax
  unsigned __int64 v18; // r13
  CMemoryLog *v19; // rax
  unsigned __int8 *v20; // r14
  CMemoryLog *v21; // rax
  CMemoryLog *v22; // rax
  void *v23; // [rsp+28h] [rbp-50h] BYREF
  unsigned __int8 *v24; // [rsp+30h] [rbp-48h]

  v6 = (int)a3;
  try
  {
    if ( a2 == 3 )
      return a3;
    v9 = 0;
    if ( !a4 )
      goto LABEL_37;
    v10 = *((unsigned int *)a4 + 1);
    if ( ((unsigned __int64)a3 - 8) >> 2 < v10 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2147217379);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          135,
          WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
          2147749917LL);
      }
      return 2147749917LL;
    }
    v12 = a4 + 8;
    v24 = a4 + 8;
    if ( *(_DWORD *)a4 == 1 )
    {
      if ( CFlexArray::Size(a5) >= (unsigned int)v10 )
      {
LABEL_24:
        *a6 = v10;
        v15 = v6 - 8;
        v16 = 0;
        while ( v9 >= 0 )
        {
          if ( v16 >= (unsigned int)v10 )
            goto LABEL_35;
          v17 = (CWbemInstance **)CFlexArray::operator[](a5, v16);
          v18 = *(unsigned int *)v12;
          if ( v18 > v15 - 4 )
          {
            v19 = GetMemLogObject();
            CMemoryLog::Write(v19, -2147217379);
            if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                137,
                WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
                2147749917LL);
            }
            return 2147749917LL;
          }
          v20 = v12 + 4;
          v24 = v20;
          v9 = CWbemInstance::CopyActualTransferBlob(*v17, v18, v20);
          v12 = &v20[v18];
          v24 = v12;
          v15 += -4LL - v18;
          ++v16;
        }
      }
      else
      {
        v23 = 0;
        v13 = CFlexArray::Size(a5);
        while ( v9 >= 0 )
        {
          if ( v13 >= (unsigned int)v10 )
            goto LABEL_24;
          v9 = (*(__int64 (__fastcall **)(struct CWbemInstance *, void **))(*(_QWORD *)a1 + 96LL))(a1, &v23);
          if ( v9 >= 0 && CFlexArray::InsertAt(a5, v13, v23) )
          {
            (*(void (__fastcall **)(void *))(*(_QWORD *)v23 + 16LL))(v23);
            v14 = GetMemLogObject();
            CMemoryLog::Write(v14, -2147217402);
            if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                136,
                WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
                2147749894LL);
            }
            return 2147749894LL;
          }
          ++v13;
        }
      }
    }
    else
    {
      v9 = -2147217379;
LABEL_35:
      if ( v9 >= 0 )
        goto LABEL_37;
    }
    v21 = GetMemLogObject();
    CMemoryLog::Write(v21, v9);
LABEL_37:
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        138,
        WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
        (unsigned int)v9);
    }
    result = (unsigned int)v9;
  }
  catch ( CX_MemoryException )
  {
    v22 = GetMemLogObject();
    CMemoryLog::Write(v22, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800774d0  push    rbx
0x1800774d2  push    rsi
0x1800774d3  push    rdi
0x1800774d4  push    r13
0x1800774d6  push    r14
0x1800774d8  push    r15
0x1800774da  sub     rsp, 48h
0x1800774de  movsxd  r15, r8d
0x1800774e1  mov     r13, rcx
0x1800774e4  cmp     edx, 3
0x1800774e7  jnz     short loc_1800774F1
0x1800774e9  mov     eax, r15d
0x1800774ec  jmp     loc_18007779F
0x1800774f1  xor     ebx, ebx
0x1800774f3  mov     [rsp+78h+var_54], ebx
0x1800774f7  test    r9, r9
0x1800774fa  jz      loc_18007775F
0x180077500  mov     esi, [r9+4]
0x180077504  mov     ecx, r15d
0x180077507  sub     rcx, 8
0x18007750b  shr     rcx, 2
0x18007750f  cmp     rcx, rsi
0x180077512  jnb     short loc_18007756B
0x180077514  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007751a  mov     ebx, 8004101Dh
0x18007751f  mov     edx, ebx
0x180077521  mov     rcx, rax
0x180077524  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007752a  lea     rax, WPP_GLOBAL_Control
0x180077531  mov     rcx, cs:WPP_GLOBAL_Control
0x180077538  cmp     rcx, rax
0x18007753b  jz      short loc_180077564
0x18007753d  test    byte ptr [rcx+1Ch], 1
0x180077541  jz      short loc_180077564
0x180077543  cmp     byte ptr [rcx+19h], 2
0x180077547  jb      short loc_180077564
0x180077549  mov     edx, 87h
0x18007754e  mov     r9d, 8004101Dh
0x180077554  lea     r8, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids
0x18007755b  mov     rcx, [rcx+10h]
0x18007755f  call    WPP_SF_d
0x180077564  mov     eax, ebx
0x180077566  jmp     loc_18007779F
0x18007756b  lea     r14, [r9+8]
0x18007756f  mov     [rsp+78h+var_48], r14
0x180077574  mov     [rsp+78h+var_58], ebx
0x180077578  cmp     dword ptr [r9], 1
0x18007757c  jnz     loc_180077741
0x180077582  mov     rcx, [rsp+78h+arg_20]
0x18007758a  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x180077590  cmp     eax, esi
0x180077592  jnb     loc_180077671
0x180077598  mov     [rsp+78h+var_50], rbx
0x18007759d  mov     rcx, [rsp+78h+arg_20]
0x1800775a5  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x1800775ab  mov     edi, eax
0x1800775ad  mov     [rsp+78h+var_58], eax
0x1800775b1  test    ebx, ebx
0x1800775b3  js      loc_18007774E
0x1800775b9  cmp     edi, esi
0x1800775bb  jnb     loc_180077671
0x1800775c1  mov     rax, [r13+0]
0x1800775c5  lea     rdx, [rsp+78h+var_50]
0x1800775ca  mov     rcx, r13
0x1800775cd  mov     rax, [rax+60h]
0x1800775d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800775d6  mov     ebx, eax
0x1800775d8  mov     [rsp+78h+var_54], eax
0x1800775dc  test    eax, eax
0x1800775de  js      loc_180077666
0x1800775e4  mov     r8, [rsp+78h+var_50]
0x1800775e9  mov     edx, edi
0x1800775eb  mov     rcx, [rsp+78h+arg_20]
0x1800775f3  call    cs:__imp_?InsertAt@CFlexArray@@QEAAHHPEAX@Z; CFlexArray::InsertAt(int,void *)
0x1800775f9  test    eax, eax
0x1800775fb  jz      short loc_180077666
0x1800775fd  mov     rcx, [rsp+78h+var_50]
0x180077602  mov     rax, [rcx]
0x180077605  mov     rax, [rax+10h]
0x180077609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007760e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180077614  mov     edx, 80041006h
0x180077619  mov     rcx, rax
0x18007761c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180077622  lea     rax, WPP_GLOBAL_Control
0x180077629  mov     rcx, cs:WPP_GLOBAL_Control
0x180077630  cmp     rcx, rax
0x180077633  jz      short loc_18007765C
0x180077635  test    byte ptr [rcx+1Ch], 1
0x180077639  jz      short loc_18007765C
0x18007763b  cmp     byte ptr [rcx+19h], 2
0x18007763f  jb      short loc_18007765C
0x180077641  mov     edx, 88h
0x180077646  mov     r9d, 80041006h
0x18007764c  lea     r8, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids
0x180077653  mov     rcx, [rcx+10h]
0x180077657  call    WPP_SF_d
0x18007765c  mov     eax, 80041006h
0x180077661  jmp     loc_18007779F
0x180077666  inc     edi
0x180077668  mov     [rsp+78h+var_58], edi
0x18007766c  jmp     loc_1800775B1
0x180077671  mov     rax, [rsp+78h+arg_28]
0x180077679  mov     [rax], esi
0x18007767b  sub     r15, 8
0x18007767f  xor     edi, edi
0x180077681  mov     [rsp+78h+var_58], edi
0x180077685  test    ebx, ebx
0x180077687  js      loc_18007774E
0x18007768d  cmp     edi, esi
0x18007768f  jnb     loc_18007774A
0x180077695  mov     edx, edi
0x180077697  mov     rcx, [rsp+78h+arg_20]
0x18007769f  call    cs:__imp_??ACFlexArray@@QEAAAEAPEAXH@Z; CFlexArray::operator[](int)
0x1800776a5  mov     r13d, [r14]
0x1800776a8  lea     rcx, [r15-4]
0x1800776ac  cmp     r13, rcx
0x1800776af  jbe     short loc_180077708
0x1800776b1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800776b7  mov     ebx, 8004101Dh
0x1800776bc  mov     edx, ebx
0x1800776be  mov     rcx, rax
0x1800776c1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800776c7  lea     rax, WPP_GLOBAL_Control
0x1800776ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800776d5  cmp     rcx, rax
0x1800776d8  jz      short loc_180077701
0x1800776da  test    byte ptr [rcx+1Ch], 1
0x1800776de  jz      short loc_180077701
0x1800776e0  cmp     byte ptr [rcx+19h], 2
0x1800776e4  jb      short loc_180077701
0x1800776e6  mov     edx, 89h
0x1800776eb  mov     r9d, 8004101Dh
0x1800776f1  lea     r8, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids
0x1800776f8  mov     rcx, [rcx+10h]
0x1800776fc  call    WPP_SF_d
0x180077701  mov     eax, ebx
0x180077703  jmp     loc_18007779F
0x180077708  add     r14, 4
0x18007770c  mov     [rsp+78h+var_48], r14
0x180077711  mov     r8, r14; unsigned __int8 *
0x180077714  mov     edx, r13d; int
0x180077717  mov     rcx, [rax]; this
0x18007771a  call    ?CopyActualTransferBlob@CWbemInstance@@QEAAJJPEAE@Z; CWbemInstance::CopyActualTransferBlob(long,uchar *)
0x18007771f  mov     ebx, eax
0x180077721  mov     [rsp+78h+var_54], eax
0x180077725  add     r14, r13
0x180077728  mov     [rsp+78h+var_48], r14
0x18007772d  mov     rax, 0FFFFFFFFFFFFFFFCh
0x180077734  sub     rax, r13
0x180077737  add     r15, rax
0x18007773a  inc     edi
0x18007773c  jmp     loc_180077681
0x180077741  mov     ebx, 8004101Dh
0x180077746  mov     [rsp+78h+var_54], ebx
0x18007774a  test    ebx, ebx
0x18007774c  jns     short loc_18007775F
0x18007774e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180077754  mov     edx, ebx
0x180077756  mov     rcx, rax
0x180077759  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007775f  lea     rax, WPP_GLOBAL_Control
0x180077766  mov     rcx, cs:WPP_GLOBAL_Control
0x18007776d  cmp     rcx, rax
0x180077770  jz      short loc_180077796
0x180077772  test    byte ptr [rcx+1Ch], 1
0x180077776  jz      short loc_180077796
0x180077778  cmp     byte ptr [rcx+19h], 2
0x18007777c  jb      short loc_180077796
0x18007777e  mov     edx, 8Ah
0x180077783  mov     r9d, ebx
0x180077786  lea     r8, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids
0x18007778d  mov     rcx, [rcx+10h]
0x180077791  call    WPP_SF_d
0x180077796  mov     eax, ebx
0x180077798  jmp     short loc_18007779F
0x18007779a  mov     eax, 80041006h
0x18007779f  add     rsp, 48h
0x1800777a3  pop     r15
0x1800777a5  pop     r14
0x1800777a7  pop     r13
0x1800777a9  pop     rdi
0x1800777aa  pop     rsi
0x1800777ab  pop     rbx
0x1800777ac  retn
```
