# CWbemObject::Get(ushort const *,long,tagVARIANT *,long *,long *)

- ea: `0x180052290`
- end: `0x1800525bf`
- name: `?Get@CWbemObject@@UEAAJPEBGJPEAUtagVARIANT@@PEAJ2@Z`
- size: `815`
- prototype: `__int64 __fastcall(CWbemObject *this, const unsigned __int16 *, int, struct tagVARIANT *, int *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180037120`
- `0x180052290`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1800523b7`
- `wbemcomn!GetMemLogObject` at `0x180052408`
- `wbemcomn!GetMemLogObject` at `0x18005249d`
- `wbemcomn!GetMemLogObject` at `0x18005250a`
- `wbemcomn!GetMemLogObject` at `0x1800523b7`
- `wbemcomn!GetMemLogObject` at `0x180052408`
- `wbemcomn!GetMemLogObject` at `0x18005249d`
- `wbemcomn!GetMemLogObject` at `0x18005250a`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800522db`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800522db`
- `wbemcomn!?FillVariant@CVar@@QEAAXPEAUtagVARIANT@@H@Z` at `0x180052319`
- `wbemcomn!?FillVariant@CVar@@QEAAXPEAUtagVARIANT@@H@Z` at `0x180052319`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800523c5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180052413`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800524ab`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180052515`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800523c5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180052413`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800524ab`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180052515`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180052325`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18005237b`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180052558`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180052325`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18005237b`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180052558`
- `OLEAUT32!__imp_VariantInit` at `0x180052305`
- `OLEAUT32!__imp_VariantInit` at `0x180052305`

## pseudocode

```c
__int64 __fastcall CWbemObject::Get(
        CWbemObject *this,
        const unsigned __int16 *a2,
        int a3,
        struct tagVARIANT *a4,
        int *a5,
        int *a6)
{
  int v10; // esi
  int *v11; // r8
  int *v12; // r9
  __int64 result; // rax
  int v14; // edi
  CMemoryLog *v15; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v17; // rax
  CMemoryLog *v18; // rax
  CMemoryLog *v19; // rax
  CMemoryLog *v20; // rax
  _BYTE v21[80]; // [rsp+38h] [rbp-50h] BYREF

  try
  {
    (*(void (__fastcall **)(CWbemObject *, __int64))(*(_QWORD *)this + 280LL))(this, 1);
    if ( a2 )
    {
      if ( !a3 )
      {
        if ( !a4 )
          goto LABEL_7;
        CVar::CVar((CVar *)v21);
        v10 = (*(__int64 (__fastcall **)(CWbemObject *, const unsigned __int16 *, _BYTE *))(*(_QWORD *)this + 776LL))(
                this,
                a2,
                v21);
        if ( v10 >= 0 )
        {
          VariantInit(a4);
          CVar::FillVariant((CVar *)v21, a4, 1);
          CVar::~CVar((CVar *)v21);
LABEL_7:
          v11 = a5;
          v12 = a6;
          if ( __PAIR128__((unsigned __int64)a6, (unsigned __int64)a5) == 0 && a4
            || (v14 = (*(__int64 (__fastcall **)(CWbemObject *, const unsigned __int16 *, int *, int *))(*(_QWORD *)this + 864LL))(
                        this,
                        a2,
                        a5,
                        a6),
                v14 >= 0) )
          {
            (*(void (__fastcall **)(CWbemObject *, _QWORD, int *, int *))(*(_QWORD *)this + 288LL))(this, 0, v11, v12);
            return 0;
          }
          else if ( v14 == -2147217406 )
          {
            (*(void (__fastcall **)(CWbemObject *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
            return 2147749890LL;
          }
          else
          {
            MemLogObject = GetMemLogObject();
            CMemoryLog::Write(MemLogObject, v14);
            if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                18,
                WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids,
                (unsigned int)v14);
            }
            (*(void (__fastcall **)(CWbemObject *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
            return (unsigned int)v14;
          }
        }
        if ( v10 == -2147217406 )
        {
          CVar::~CVar((CVar *)v21);
          (*(void (__fastcall **)(CWbemObject *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
          return 2147749890LL;
        }
        else
        {
          v18 = GetMemLogObject();
          CMemoryLog::Write(v18, v10);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              17,
              WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids,
              (unsigned int)v10);
          }
          CVar::~CVar((CVar *)v21);
          (*(void (__fastcall **)(CWbemObject *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
          return (unsigned int)v10;
        }
      }
      v17 = GetMemLogObject();
      CMemoryLog::Write(v17, -2147217400);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids, 2147749896LL);
      }
    }
    else
    {
      v15 = GetMemLogObject();
      CMemoryLog::Write(v15, -2147217400);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids, 2147749896LL);
      }
    }
    (*(void (__fastcall **)(CWbemObject *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
    result = 2147749896LL;
  }
  catch ( CX_MemoryException )
  {
    v19 = GetMemLogObject();
    CMemoryLog::Write(v19, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  catch ( CX_Exception )
  {
    v20 = GetMemLogObject();
    CMemoryLog::Write(v20, -2147217398);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids, 2147749898LL);
    }
    return 2147749898LL;
  }
  (*(void (__fastcall **)(CWbemObject *, __int64))(*(_QWORD *)this + 280LL))(this, 1);
}

```

## disassembly

```asm
0x180052290  push    rbx
0x180052292  push    rsi
0x180052293  push    rdi
0x180052294  push    r14
0x180052296  sub     rsp, 68h
0x18005229a  mov     rdi, r9
0x18005229d  mov     esi, r8d
0x1800522a0  mov     r14, rdx
0x1800522a3  mov     rbx, rcx
0x1800522a6  mov     [rsp+88h+var_58], rcx
0x1800522ab  mov     rax, [rcx]
0x1800522ae  mov     edx, 1
0x1800522b3  mov     rax, [rax+118h]
0x1800522ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800522bf  nop
0x1800522c0  test    r14, r14
0x1800522c3  jz      loc_1800523B7
0x1800522c9  test    esi, esi
0x1800522cb  jnz     loc_18005249D
0x1800522d1  test    rdi, rdi
0x1800522d4  jz      short loc_18005232B
0x1800522d6  lea     rcx, [rsp+88h+var_50]
0x1800522db  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x1800522e1  nop
0x1800522e2  mov     rax, [rbx]
0x1800522e5  lea     r8, [rsp+88h+var_50]
0x1800522ea  mov     rdx, r14
0x1800522ed  mov     rcx, rbx
0x1800522f0  mov     rax, [rax+308h]
0x1800522f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800522fc  mov     esi, eax
0x1800522fe  test    eax, eax
0x180052300  js      short loc_18005236A
0x180052302  mov     rcx, rdi; pvarg
0x180052305  call    cs:__imp_VariantInit
0x18005230b  mov     r8d, 1
0x180052311  mov     rdx, rdi
0x180052314  lea     rcx, [rsp+88h+var_50]
0x180052319  call    cs:__imp_?FillVariant@CVar@@QEAAXPEAUtagVARIANT@@H@Z; CVar::FillVariant(tagVARIANT *,int)
0x18005231f  nop
0x180052320  lea     rcx, [rsp+88h+var_50]
0x180052325  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18005232b  mov     r8, [rsp+88h+arg_20]
0x180052333  mov     r9, [rsp+88h+arg_28]
0x18005233b  test    r8, r8
0x18005233e  jnz     short loc_18005239A
0x180052340  test    r9, r9
0x180052343  jnz     short loc_18005239A
0x180052345  test    rdi, rdi
0x180052348  jz      short loc_18005239A
0x18005234a  mov     rax, [rbx]
0x18005234d  xor     edx, edx
0x18005234f  mov     rcx, rbx
0x180052352  mov     rax, [rax+120h]
0x180052359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005235e  xor     eax, eax
0x180052360  add     rsp, 68h
0x180052364  pop     r14
0x180052366  pop     rdi
0x180052367  pop     rsi
0x180052368  pop     rbx
0x180052369  retn
0x18005236a  cmp     esi, 80041002h
0x180052370  jnz     loc_18005250A
0x180052376  lea     rcx, [rsp+88h+var_50]
0x18005237b  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180052381  nop
0x180052382  mov     rcx, [rbx]
0x180052385  mov     rax, [rcx+120h]
0x18005238c  xor     edx, edx
0x18005238e  mov     rcx, rbx
0x180052391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052396  mov     eax, esi
0x180052398  jmp     short loc_180052360
0x18005239a  mov     rax, [rbx]
0x18005239d  mov     rdx, r14
0x1800523a0  mov     rcx, rbx
0x1800523a3  mov     rax, [rax+360h]
0x1800523aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800523af  mov     edi, eax
0x1800523b1  test    eax, eax
0x1800523b3  jns     short loc_18005234A
0x1800523b5  jmp     short loc_180052400
0x1800523b7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800523bd  mov     edx, 80041008h
0x1800523c2  mov     rcx, rax
0x1800523c5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800523cb  lea     rax, WPP_GLOBAL_Control
0x1800523d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800523d9  cmp     rcx, rax
0x1800523dc  jnz     loc_180052469
0x1800523e2  mov     rcx, [rbx]
0x1800523e5  mov     rax, [rcx+120h]
0x1800523ec  xor     edx, edx
0x1800523ee  mov     rcx, rbx
0x1800523f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800523f6  mov     eax, 80041008h
0x1800523fb  jmp     loc_180052360
0x180052400  cmp     edi, 80041002h
0x180052406  jz      short loc_18005244B
0x180052408  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18005240e  mov     edx, edi
0x180052410  mov     rcx, rax
0x180052413  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180052419  lea     rax, WPP_GLOBAL_Control
0x180052420  mov     rcx, cs:WPP_GLOBAL_Control
0x180052427  cmp     rcx, rax
0x18005242a  jnz     loc_18005257A
0x180052430  mov     rax, [rbx]
0x180052433  xor     edx, edx
0x180052435  mov     rcx, rbx
0x180052438  mov     rax, [rax+120h]
0x18005243f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052444  mov     eax, edi
0x180052446  jmp     loc_180052360
0x18005244b  mov     rax, [rbx]
0x18005244e  xor     edx, edx
0x180052450  mov     rcx, rbx
0x180052453  mov     rax, [rax+120h]
0x18005245a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005245f  mov     eax, 80041002h
0x180052464  jmp     loc_180052360
0x180052469  test    byte ptr [rcx+1Ch], 1
0x18005246d  jz      loc_1800523E2
0x180052473  cmp     byte ptr [rcx+19h], 2
0x180052477  jb      loc_1800523E2
0x18005247d  mov     edx, 0Fh
0x180052482  mov     r9d, 80041008h
0x180052488  lea     r8, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids
0x18005248f  mov     rcx, [rcx+10h]
0x180052493  call    WPP_SF_d
0x180052498  jmp     loc_1800523E2
0x18005249d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800524a3  mov     edx, 80041008h
0x1800524a8  mov     rcx, rax
0x1800524ab  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800524b1  lea     rax, WPP_GLOBAL_Control
0x1800524b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800524bf  cmp     rcx, rax
0x1800524c2  jz      short loc_1800524EC
0x1800524c4  test    byte ptr [rcx+1Ch], 1
0x1800524c8  jz      short loc_1800524EC
0x1800524ca  cmp     byte ptr [rcx+19h], 2
0x1800524ce  jb      short loc_1800524EC
0x1800524d0  mov     edx, 10h
0x1800524d5  mov     r9d, 80041008h
0x1800524db  lea     r8, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids
0x1800524e2  mov     rcx, [rcx+10h]
0x1800524e6  call    WPP_SF_d
0x1800524eb  nop
0x1800524ec  mov     rax, [rbx]
0x1800524ef  xor     edx, edx
0x1800524f1  mov     rcx, rbx
0x1800524f4  mov     rax, [rax+120h]
0x1800524fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052500  mov     eax, 80041008h
0x180052505  jmp     loc_180052360
0x18005250a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180052510  mov     edx, esi
0x180052512  mov     rcx, rax
0x180052515  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18005251b  lea     rax, WPP_GLOBAL_Control
0x180052522  mov     rcx, cs:WPP_GLOBAL_Control
0x180052529  cmp     rcx, rax
0x18005252c  jz      short loc_180052553
0x18005252e  test    byte ptr [rcx+1Ch], 1
0x180052532  jz      short loc_180052553
0x180052534  cmp     byte ptr [rcx+19h], 2
0x180052538  jb      short loc_180052553
0x18005253a  mov     edx, 11h
0x18005253f  mov     r9d, esi
0x180052542  lea     r8, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids
0x180052549  mov     rcx, [rcx+10h]
0x18005254d  call    WPP_SF_d
0x180052552  nop
0x180052553  lea     rcx, [rsp+88h+var_50]
0x180052558  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18005255e  nop
0x18005255f  mov     rax, [rbx]
0x180052562  xor     edx, edx
0x180052564  mov     rcx, rbx
0x180052567  mov     rax, [rax+120h]
0x18005256e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052573  mov     eax, esi
0x180052575  jmp     loc_180052360
0x18005257a  test    byte ptr [rcx+1Ch], 1
0x18005257e  jz      loc_180052430
0x180052584  cmp     byte ptr [rcx+19h], 2
0x180052588  jb      loc_180052430
0x18005258e  mov     edx, 12h
0x180052593  mov     r9d, edi
0x180052596  lea     r8, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids
0x18005259d  mov     rcx, [rcx+10h]
0x1800525a1  call    WPP_SF_d
0x1800525a6  jmp     loc_180052430
0x1800525ab  mov     eax, 80041006h
0x1800525b0  jmp     loc_180052360
0x1800525b5  mov     eax, 8004100Ah
0x1800525ba  jmp     loc_180052360
```
