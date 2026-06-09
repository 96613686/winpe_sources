# CWbemInstance::GetPropertyQualifierSet(ushort const *,IWbemQualifierSet * *)

- ea: `0x18004c1e0`
- end: `0x18004c57f`
- name: `?GetPropertyQualifierSet@CWbemInstance@@UEAAJPEBGPEAPEAUIWbemQualifierSet@@@Z`
- size: `927`
- prototype: `int(CWbemInstance *__hidden this, const unsigned __int16 *, struct IWbemQualifierSet **)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18000d230`
- `0x180013de0`
- `0x180037120`
- `0x18004c1e0`
- `0x18004c590`
- `0x180050360`
- `0x180050490`
- `0x180091966`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18004c235`
- `wbemcomn!GetMemLogObject` at `0x18004c3f1`
- `wbemcomn!GetMemLogObject` at `0x18004c46a`
- `wbemcomn!GetMemLogObject` at `0x18004c4de`
- `wbemcomn!GetMemLogObject` at `0x18004c235`
- `wbemcomn!GetMemLogObject` at `0x18004c3f1`
- `wbemcomn!GetMemLogObject` at `0x18004c46a`
- `wbemcomn!GetMemLogObject` at `0x18004c4de`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004c243`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004c3ff`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004c478`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004c4ec`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004c243`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004c3ff`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004c478`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004c4ec`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18004c2a0`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18004c2a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWbemInstance::GetPropertyQualifierSet(
        CWbemInstance *this,
        const unsigned __int16 *a2,
        struct IWbemQualifierSet **a3)
{
  __int64 v6; // rax
  CMemoryLog *v7; // rax
  __int64 result; // rax
  CInstancePropertyQualifierSet *v9; // rax
  struct IWbemQualifierSet *v10; // r15
  unsigned int v11; // r13d
  struct CPropertyInformation *PropertyInfo; // rax
  unsigned int v13; // edx
  int v14; // ecx
  __int64 v15; // rcx
  __int64 v16; // rdx
  unsigned __int8 *QualifierSetStart; // rbx
  __int64 v18; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v20; // rax
  CMemoryLog *v21; // rax
  CMemoryLog *v22; // rax
  CWbemInstance *v23; // [rsp+78h] [rbp+20h] BYREF

  try
  {
    v23 = this;
    (*(void (__fastcall **)(CWbemInstance *, __int64))(*(_QWORD *)this + 280LL))(this, 1);
    if ( !a2 )
      goto LABEL_6;
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
    if ( v6 )
    {
      if ( *a2 == 95 )
      {
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, -2147217360);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            17,
            WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
            2147749936LL);
        }
        (*(void (__fastcall **)(CWbemInstance *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
        result = 2147749936LL;
      }
      else
      {
        v9 = (CInstancePropertyQualifierSet *)CWin32DefaultArena::WbemMemAlloc(0x90u);
        if ( v9 )
        {
          v10 = (struct IWbemQualifierSet *)CInstancePropertyQualifierSet::CInstancePropertyQualifierSet(v9);
          v11 = 0;
        }
        else
        {
          v11 = 0;
          v10 = 0;
        }
        if ( v10 )
        {
          PropertyInfo = CClassPart::FindPropertyInfo((CWbemInstance *)((char *)this + 400), a2);
          if ( PropertyInfo )
          {
            v13 = (_DWORD)PropertyInfo - *((_DWORD *)this + 112) + 14;
            v14 = *((unsigned __int16 *)PropertyInfo + 2);
            v10[11].lpVtbl = (struct IWbemQualifierSetVtbl *)((char *)this + 336);
            LODWORD(v10[12].lpVtbl) = v14;
            v10[13].lpVtbl = (struct IWbemQualifierSetVtbl *)((char *)this + 400);
            LODWORD(v10[14].lpVtbl) = v13;
            v15 = v13;
            v16 = *((_QWORD *)this + 56);
            LODWORD(v10[15].lpVtbl) = *(_DWORD *)(v16 + v15);
            v10[16].lpVtbl = (struct IWbemQualifierSetVtbl *)(v15 + v16 + 4);
            v10[17].lpVtbl = (struct IWbemQualifierSetVtbl *)((char *)this + 600);
            QualifierSetStart = CInstancePQSContainer::GetQualifierSetStart((CInstancePQSContainer *)&v10[10]);
            v18 = ((__int64 (__fastcall *)(struct IWbemQualifierSet *))v10[10].lpVtbl->QueryInterface)(&v10[10]);
            LODWORD(v10[1].lpVtbl) = *(_DWORD *)QualifierSetStart;
            v10[2].lpVtbl = (struct IWbemQualifierSetVtbl *)(QualifierSetStart + 4);
            v10[3].lpVtbl = (struct IWbemQualifierSetVtbl *)v18;
            v10[6].lpVtbl = (struct IWbemQualifierSetVtbl *)&v10[10];
            v10[7].lpVtbl = (struct IWbemQualifierSetVtbl *)&v10[15];
            v10[5].lpVtbl = (struct IWbemQualifierSetVtbl *)((__int64 (__fastcall *)(struct IWbemQualifierSet *))v10[10].lpVtbl->AddRef)(&v10[10]);
            *a3 = 0;
            if ( !memcmp_0(&IID_IWbemQualifierSet, &IID_IWbemQualifierSet, 0x10u)
              || !memcmp_0(&IID_IWbemQualifierSet, &IID_IUnknown, 0x10u) )
            {
              ((void (__fastcall *)(struct IWbemQualifierSet *))v10->lpVtbl->AddRef)(v10);
              *a3 = v10;
            }
            else
            {
              v11 = -2147467262;
            }
            (*(void (__fastcall **)(CWbemInstance *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
            result = v11;
          }
          else
          {
            CInstancePropertyQualifierSet::`scalar deleting destructor'((CInstancePropertyQualifierSet *)v10, 1u);
            *a3 = 0;
            v21 = GetMemLogObject();
            CMemoryLog::Write(v21, -2147217406);
            if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                19,
                WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
                2147749890LL);
            }
            CWbemObject::CLock::~CLock((CWbemObject::CLock *)&v23);
            result = 2147749890LL;
          }
        }
        else
        {
          v20 = GetMemLogObject();
          CMemoryLog::Write(v20, -2147217402);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              18,
              WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
              2147749894LL);
          }
          CWbemObject::CLock::~CLock((CWbemObject::CLock *)&v23);
          result = 2147749894LL;
        }
      }
    }
    else
    {
LABEL_6:
      v7 = GetMemLogObject();
      CMemoryLog::Write(v7, -2147217400);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids, 2147749896LL);
      }
      (*(void (__fastcall **)(CWbemInstance *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
      result = 2147749896LL;
    }
  }
  catch ( CX_MemoryException )
  {
    v22 = GetMemLogObject();
    CMemoryLog::Write(v22, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  return result;
}

```

## disassembly

```asm
0x18004c1e0  mov     [rsp+arg_0], rbx
0x18004c1e5  mov     [rsp+arg_8], rsi
0x18004c1ea  push    rdi
0x18004c1eb  push    r12
0x18004c1ed  push    r13
0x18004c1ef  push    r14
0x18004c1f1  push    r15
0x18004c1f3  sub     rsp, 30h
0x18004c1f7  mov     r12, r8
0x18004c1fa  mov     rbx, rdx
0x18004c1fd  mov     r14, rcx
0x18004c200  mov     [rsp+58h+arg_18], rcx
0x18004c205  mov     rax, [rcx]
0x18004c208  mov     edx, 1
0x18004c20d  mov     rax, [rax+118h]
0x18004c214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c219  nop
0x18004c21a  test    rbx, rbx
0x18004c21d  jz      short loc_18004C235
0x18004c21f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18004c226  inc     rax
0x18004c229  cmp     word ptr [rbx+rax*2], 0
0x18004c22e  jnz     short loc_18004C226
0x18004c230  test    rax, rax
0x18004c233  jnz     short loc_18004C291
0x18004c235  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004c23b  mov     edx, 80041008h
0x18004c240  mov     rcx, rax
0x18004c243  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004c249  lea     rax, WPP_GLOBAL_Control
0x18004c250  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c257  cmp     rcx, rax
0x18004c25a  jnz     loc_18004C541
0x18004c260  mov     rcx, [r14]
0x18004c263  mov     rax, [rcx+120h]
0x18004c26a  xor     edx, edx
0x18004c26c  mov     rcx, r14
0x18004c26f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c274  mov     eax, 80041008h
0x18004c279  mov     rbx, [rsp+58h+arg_0]
0x18004c27e  mov     rsi, [rsp+58h+arg_8]
0x18004c283  add     rsp, 30h
0x18004c287  pop     r15
0x18004c289  pop     r14
0x18004c28b  pop     r13
0x18004c28d  pop     r12
0x18004c28f  pop     rdi
0x18004c290  retn
0x18004c291  cmp     word ptr [rbx], 5Fh ; '_'
0x18004c295  jz      loc_18004C3F1
0x18004c29b  mov     ecx, 90h
0x18004c2a0  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18004c2a6  mov     [rsp+58h+var_38], rax
0x18004c2ab  test    rax, rax
0x18004c2ae  jz      loc_18004C45F
0x18004c2b4  mov     rcx, rax; this
0x18004c2b7  call    ??0CInstancePropertyQualifierSet@@QEAA@XZ; CInstancePropertyQualifierSet::CInstancePropertyQualifierSet(void)
0x18004c2bc  mov     r15, rax
0x18004c2bf  xor     r13d, r13d
0x18004c2c2  test    r15, r15
0x18004c2c5  jz      loc_18004C46A
0x18004c2cb  lea     rdi, [r14+190h]
0x18004c2d2  mov     rdx, rbx; unsigned __int16 *
0x18004c2d5  mov     rcx, rdi; this
0x18004c2d8  call    ?FindPropertyInfo@CClassPart@@QEAAPEAVCPropertyInformation@@PEBG@Z; CClassPart::FindPropertyInfo(ushort const *)
0x18004c2dd  test    rax, rax
0x18004c2e0  jz      loc_18004C4CD
0x18004c2e6  mov     edx, eax
0x18004c2e8  sub     edx, [r14+1C0h]
0x18004c2ef  add     edx, 0Eh
0x18004c2f2  movzx   ecx, word ptr [rax+4]
0x18004c2f6  lea     rax, [r14+150h]
0x18004c2fd  mov     [r15+58h], rax
0x18004c301  mov     [r15+60h], ecx
0x18004c305  mov     [r15+68h], rdi
0x18004c309  mov     [r15+70h], edx
0x18004c30d  lea     rsi, [r15+78h]
0x18004c311  mov     ecx, edx
0x18004c313  mov     rdx, [rdi+30h]
0x18004c317  mov     eax, [rdx+rcx]
0x18004c31a  mov     [rsi], eax
0x18004c31c  lea     rax, [rdx+4]
0x18004c320  add     rax, rcx
0x18004c323  mov     [rsi+8], rax
0x18004c327  lea     rax, [rdi+0C8h]
0x18004c32e  mov     [rsi+10h], rax
0x18004c332  lea     rdi, [r15+50h]
0x18004c336  mov     rcx, rdi; this
0x18004c339  call    ?GetQualifierSetStart@CInstancePQSContainer@@UEAAPEAEXZ; CInstancePQSContainer::GetQualifierSetStart(void)
0x18004c33e  mov     rbx, rax
0x18004c341  mov     rcx, [rdi]
0x18004c344  mov     rax, [rcx]
0x18004c347  mov     rcx, rdi
0x18004c34a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c34f  mov     edx, [rbx]
0x18004c351  mov     [r15+8], edx
0x18004c355  lea     rdx, [rbx+4]
0x18004c359  mov     [r15+10h], rdx
0x18004c35d  mov     [r15+18h], rax
0x18004c361  mov     [r15+30h], rdi
0x18004c365  mov     [r15+38h], rsi
0x18004c369  mov     rax, [rdi]
0x18004c36c  mov     rcx, rdi
0x18004c36f  mov     rax, [rax+8]
0x18004c373  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c378  mov     [r15+28h], rax
0x18004c37c  mov     [r12], r13
0x18004c380  mov     r8d, 10h; Size
0x18004c386  lea     rdx, IID_IWbemQualifierSet; Buf2
0x18004c38d  lea     rcx, IID_IWbemQualifierSet; Buf1
0x18004c394  call    memcmp_0
0x18004c399  test    eax, eax
0x18004c39b  jnz     short loc_18004C3CC
0x18004c39d  mov     rax, [r15]
0x18004c3a0  mov     rcx, r15
0x18004c3a3  mov     rax, [rax+8]
0x18004c3a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c3ac  mov     [r12], r15
0x18004c3b0  mov     rcx, [r14]
0x18004c3b3  mov     rax, [rcx+120h]
0x18004c3ba  xor     edx, edx
0x18004c3bc  mov     rcx, r14
0x18004c3bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c3c4  mov     eax, r13d
0x18004c3c7  jmp     loc_18004C279
0x18004c3cc  mov     r8d, 10h; Size
0x18004c3d2  lea     rdx, IID_IUnknown; Buf2
0x18004c3d9  lea     rcx, IID_IWbemQualifierSet; Buf1
0x18004c3e0  call    memcmp_0
0x18004c3e5  test    eax, eax
0x18004c3e7  jz      short loc_18004C39D
0x18004c3e9  mov     r13d, 80004002h
0x18004c3ef  jmp     short loc_18004C3B0
0x18004c3f1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004c3f7  mov     edx, 80041030h
0x18004c3fc  mov     rcx, rax
0x18004c3ff  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004c405  lea     rax, WPP_GLOBAL_Control
0x18004c40c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c413  cmp     rcx, rax
0x18004c416  jnz     short loc_18004C436
0x18004c418  mov     rcx, [r14]
0x18004c41b  mov     rax, [rcx+120h]
0x18004c422  xor     edx, edx
0x18004c424  mov     rcx, r14
0x18004c427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c42c  mov     eax, 80041030h
0x18004c431  jmp     loc_18004C279
0x18004c436  test    byte ptr [rcx+1Ch], 1
0x18004c43a  jz      short loc_18004C418
0x18004c43c  cmp     byte ptr [rcx+19h], 2
0x18004c440  jb      short loc_18004C418
0x18004c442  mov     edx, 11h
0x18004c447  mov     r9d, 80041030h
0x18004c44d  lea     r8, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids
0x18004c454  mov     rcx, [rcx+10h]
0x18004c458  call    WPP_SF_d
0x18004c45d  jmp     short loc_18004C418
0x18004c45f  xor     r13d, r13d
0x18004c462  mov     r15d, r13d
0x18004c465  jmp     loc_18004C2C2
0x18004c46a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004c470  mov     edx, 80041006h
0x18004c475  mov     rcx, rax
0x18004c478  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004c47e  lea     rax, WPP_GLOBAL_Control
0x18004c485  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c48c  cmp     rcx, rax
0x18004c48f  jz      short loc_18004C4B9
0x18004c491  test    byte ptr [rcx+1Ch], 1
0x18004c495  jz      short loc_18004C4B9
0x18004c497  cmp     byte ptr [rcx+19h], 2
0x18004c49b  jb      short loc_18004C4B9
0x18004c49d  mov     edx, 12h
0x18004c4a2  mov     r9d, 80041006h
0x18004c4a8  lea     r8, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids
0x18004c4af  mov     rcx, [rcx+10h]
0x18004c4b3  call    WPP_SF_d
0x18004c4b8  nop
0x18004c4b9  lea     rcx, [rsp+58h+arg_18]; this
0x18004c4be  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x18004c4c3  mov     eax, 80041006h
0x18004c4c8  jmp     loc_18004C279
0x18004c4cd  mov     edx, 1; unsigned int
0x18004c4d2  mov     rcx, r15; this
0x18004c4d5  call    ??_GCInstancePropertyQualifierSet@@UEAAPEAXI@Z; CInstancePropertyQualifierSet::`scalar deleting destructor'(uint)
0x18004c4da  mov     [r12], r13
0x18004c4de  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004c4e4  mov     edx, 80041002h
0x18004c4e9  mov     rcx, rax
0x18004c4ec  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004c4f2  lea     rax, WPP_GLOBAL_Control
0x18004c4f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c500  cmp     rcx, rax
0x18004c503  jz      short loc_18004C52D
0x18004c505  test    byte ptr [rcx+1Ch], 1
0x18004c509  jz      short loc_18004C52D
0x18004c50b  cmp     byte ptr [rcx+19h], 2
0x18004c50f  jb      short loc_18004C52D
0x18004c511  mov     edx, 13h
0x18004c516  mov     r9d, 80041002h
0x18004c51c  lea     r8, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids
0x18004c523  mov     rcx, [rcx+10h]
0x18004c527  call    WPP_SF_d
0x18004c52c  nop
0x18004c52d  lea     rcx, [rsp+58h+arg_18]; this
0x18004c532  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x18004c537  mov     eax, 80041002h
0x18004c53c  jmp     loc_18004C279
0x18004c541  test    byte ptr [rcx+1Ch], 1
0x18004c545  jz      loc_18004C260
0x18004c54b  cmp     byte ptr [rcx+19h], 2
0x18004c54f  jb      loc_18004C260
0x18004c555  mov     edx, 10h
0x18004c55a  mov     r9d, 80041008h
0x18004c560  lea     r8, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids
0x18004c567  mov     rcx, [rcx+10h]
0x18004c56b  call    WPP_SF_d
0x18004c570  jmp     loc_18004C260
0x18004c575  mov     eax, 80041006h
0x18004c57a  jmp     loc_18004C279
```
