# CNamespaceHandle::WriteClassRelationships(_IWmiObject *,ushort const *)

- ea: `0x180036780`
- end: `0x180036a64`
- name: `?WriteClassRelationships@CNamespaceHandle@@IEAAJPEAU_IWmiObject@@PEBG@Z`
- size: `740`
- prototype: `__int64 __fastcall(CNamespaceHandle *__hidden this, struct _IWmiObject *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180027150`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x180030fcc`
- `0x1800363e8`
- `0x180036780`
- `0x180036e68`
- `0x180048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180036827`
- `wbemcomn!GetMemLogObject` at `0x180036894`
- `wbemcomn!GetMemLogObject` at `0x1800368f4`
- `wbemcomn!GetMemLogObject` at `0x180036999`
- `wbemcomn!GetMemLogObject` at `0x1800369fc`
- `wbemcomn!GetMemLogObject` at `0x180036827`
- `wbemcomn!GetMemLogObject` at `0x180036894`
- `wbemcomn!GetMemLogObject` at `0x1800368f4`
- `wbemcomn!GetMemLogObject` at `0x180036999`
- `wbemcomn!GetMemLogObject` at `0x1800369fc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036832`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003689f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800368ff`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800369a4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036a07`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036832`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003689f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800368ff`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800369a4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036a07`
- `OLEAUT32!__imp_VariantInit` at `0x1800367e4`
- `OLEAUT32!__imp_VariantInit` at `0x1800367e4`
- `OLEAUT32!__imp_VariantClear` at `0x180036a48`
- `OLEAUT32!__imp_VariantClear` at `0x180036a48`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CNamespaceHandle::WriteClassRelationships(
        CNamespaceHandle *this,
        struct _IWmiObject *a2,
        const unsigned __int16 *a3)
{
  int v6; // ebx
  CMemoryLog *v7; // rax
  CVarObjHeap *v8; // rcx
  __int64 v9; // rdx
  const unsigned __int16 *bstrVal; // r8
  CMemoryLog *v11; // rax
  CMemoryLog *v12; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v14; // rax
  VARIANTARG pvarg; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int16 *v17; // [rsp+98h] [rbp+38h] BYREF
  unsigned __int16 *v18; // [rsp+A8h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 289, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
  }
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v6 = (*(__int64 (__fastcall **)(struct _IWmiObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)a2 + 32LL))(
         a2,
         L"__SUPERCLASS",
         0,
         &pvarg,
         0,
         0);
  if ( v6 >= 0 )
  {
    bstrVal = pvarg.bstrVal;
    if ( pvarg.vt != 8 )
      bstrVal = &qword_18004AEE0;
    v6 = CNamespaceHandle::WriteParentChildRelationship(this, a3, bstrVal);
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(struct _IWmiObject *, __int64))(*(_QWORD *)a2 + 64LL))(a2, 8);
      if ( v6 >= 0 )
      {
        v17 = 0;
        while ( 1 )
        {
          v6 = (*(__int64 (__fastcall **)(struct _IWmiObject *, _QWORD, unsigned __int16 **, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a2 + 72LL))(
                 a2,
                 0,
                 &v17,
                 0,
                 0,
                 0);
          if ( v6 )
            break;
          v18 = v17;
          v6 = CNamespaceHandle::WriteClassReference(this, a2, a3, v17);
          if ( v6 < 0 )
          {
            MemLogObject = GetMemLogObject();
            CMemoryLog::Write(MemLogObject, v6);
            if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                293,
                WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
                (unsigned int)v6);
            }
            CSysFreeMe::~CSysFreeMe((CSysFreeMe *)&v18);
            goto LABEL_38;
          }
          CSysFreeMe::~CSysFreeMe((CSysFreeMe *)&v18);
        }
        (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)a2 + 80LL))(a2);
        if ( v6 >= 0 )
        {
          v6 = 0;
        }
        else
        {
          v14 = GetMemLogObject();
          CMemoryLog::Write(v14, v6);
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v9 = 294;
            goto LABEL_36;
          }
        }
      }
      else
      {
        v12 = GetMemLogObject();
        CMemoryLog::Write(v12, v6);
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v9 = 292;
          goto LABEL_36;
        }
      }
    }
    else
    {
      v11 = GetMemLogObject();
      CMemoryLog::Write(v11, v6);
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v9 = 291;
        goto LABEL_36;
      }
    }
  }
  else
  {
    v7 = GetMemLogObject();
    CMemoryLog::Write(v7, v6);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = 290;
LABEL_36:
      WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, (unsigned int)v6);
    }
  }
LABEL_38:
  VariantClear(&pvarg);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180036780  mov     [rsp-28h+arg_0], rbx
0x180036785  push    rbp
0x180036786  push    rsi
0x180036787  push    rdi
0x180036788  push    r13
0x18003678a  push    r14
0x18003678c  mov     rbp, rsp
0x18003678f  sub     rsp, 60h
0x180036793  mov     rsi, r8
0x180036796  mov     rdi, rdx
0x180036799  mov     r14, rcx
0x18003679c  lea     rax, WPP_GLOBAL_Control
0x1800367a3  lea     r13, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x1800367aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800367b1  cmp     rcx, rax
0x1800367b4  jz      short loc_1800367D3
0x1800367b6  test    byte ptr [rcx+1Ch], 1
0x1800367ba  jz      short loc_1800367D3
0x1800367bc  cmp     byte ptr [rcx+19h], 5
0x1800367c0  jb      short loc_1800367D3
0x1800367c2  mov     edx, 121h
0x1800367c7  mov     r8, r13
0x1800367ca  mov     rcx, [rcx+10h]
0x1800367ce  call    WPP_SF_
0x1800367d3  xorps   xmm0, xmm0
0x1800367d6  xor     eax, eax
0x1800367d8  movups  xmmword ptr [rbp+pvarg], xmm0
0x1800367dc  mov     qword ptr [rbp+pvarg+10h], rax
0x1800367e0  lea     rcx, [rbp+pvarg]; pvarg
0x1800367e4  call    cs:__imp_VariantInit
0x1800367ea  mov     rax, [rdi]
0x1800367ed  mov     [rsp+60h+var_38], 0
0x1800367f6  mov     [rsp+60h+var_40], 0
0x1800367ff  lea     r9, [rbp+pvarg]
0x180036803  xor     r8d, r8d
0x180036806  lea     rdx, aSuperclass; "__SUPERCLASS"
0x18003680d  mov     rcx, rdi
0x180036810  mov     rax, [rax+20h]
0x180036814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036819  mov     ebx, eax
0x18003681b  lea     rax, [rbp+pvarg]
0x18003681f  mov     [rbp+var_20], rax
0x180036823  test    ebx, ebx
0x180036825  jns     short loc_18003686D
0x180036827  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003682d  mov     edx, ebx
0x18003682f  mov     rcx, rax
0x180036832  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180036838  mov     rcx, cs:WPP_GLOBAL_Control
0x18003683f  lea     rax, WPP_GLOBAL_Control
0x180036846  cmp     rcx, rax
0x180036849  jz      loc_180036A44
0x18003684f  test    byte ptr [rcx+1Ch], 1
0x180036853  jz      loc_180036A44
0x180036859  cmp     byte ptr [rcx+19h], 2
0x18003685d  jb      loc_180036A44
0x180036863  mov     edx, 122h
0x180036868  jmp     loc_180036A31
0x18003686d  mov     eax, 8
0x180036872  mov     rdx, rsi; unsigned __int16 *
0x180036875  mov     rcx, r14; this
0x180036878  cmp     word ptr [rbp+pvarg], ax
0x18003687c  mov     r8, qword ptr [rbp+pvarg+8]
0x180036880  jz      short loc_180036889
0x180036882  lea     r8, qword_18004AEE0; unsigned __int16 *
0x180036889  call    ?WriteParentChildRelationship@CNamespaceHandle@@IEAAJPEBG0@Z; CNamespaceHandle::WriteParentChildRelationship(ushort const *,ushort const *)
0x18003688e  mov     ebx, eax
0x180036890  test    eax, eax
0x180036892  jns     short loc_1800368DA
0x180036894  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003689a  mov     edx, ebx
0x18003689c  mov     rcx, rax
0x18003689f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800368a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800368ac  lea     rax, WPP_GLOBAL_Control
0x1800368b3  cmp     rcx, rax
0x1800368b6  jz      loc_180036A44
0x1800368bc  test    byte ptr [rcx+1Ch], 1
0x1800368c0  jz      loc_180036A44
0x1800368c6  cmp     byte ptr [rcx+19h], 2
0x1800368ca  jb      loc_180036A44
0x1800368d0  mov     edx, 123h
0x1800368d5  jmp     loc_180036A31
0x1800368da  mov     rax, [rdi]
0x1800368dd  mov     edx, 8
0x1800368e2  mov     rcx, rdi
0x1800368e5  mov     rax, [rax+40h]
0x1800368e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800368ee  mov     ebx, eax
0x1800368f0  test    eax, eax
0x1800368f2  jns     short loc_18003693A
0x1800368f4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800368fa  mov     edx, ebx
0x1800368fc  mov     rcx, rax
0x1800368ff  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180036905  mov     rcx, cs:WPP_GLOBAL_Control
0x18003690c  lea     rax, WPP_GLOBAL_Control
0x180036913  cmp     rcx, rax
0x180036916  jz      loc_180036A44
0x18003691c  test    byte ptr [rcx+1Ch], 1
0x180036920  jz      loc_180036A44
0x180036926  cmp     byte ptr [rcx+19h], 2
0x18003692a  jb      loc_180036A44
0x180036930  mov     edx, 124h
0x180036935  jmp     loc_180036A31
0x18003693a  mov     [rbp+arg_8], 0
0x180036942  mov     rax, [rdi]
0x180036945  mov     [rsp+60h+var_38], 0
0x18003694e  mov     [rsp+60h+var_40], 0
0x180036957  xor     r9d, r9d
0x18003695a  lea     r8, [rbp+arg_8]
0x18003695e  xor     edx, edx
0x180036960  mov     rcx, rdi
0x180036963  mov     rax, [rax+48h]
0x180036967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003696c  mov     ebx, eax
0x18003696e  test    eax, eax
0x180036970  jnz     short loc_1800369E9
0x180036972  mov     r9, [rbp+arg_8]; unsigned __int16 *
0x180036976  mov     [rbp+arg_18], r9
0x18003697a  mov     r8, rsi; unsigned __int16 *
0x18003697d  mov     rdx, rdi; struct _IWmiObject *
0x180036980  mov     rcx, r14; this
0x180036983  call    ?WriteClassReference@CNamespaceHandle@@IEAAJPEAU_IWmiObject@@PEBG1@Z; CNamespaceHandle::WriteClassReference(_IWmiObject *,ushort const *,ushort const *)
0x180036988  mov     ebx, eax
0x18003698a  test    eax, eax
0x18003698c  js      short loc_180036999
0x18003698e  lea     rcx, [rbp+arg_18]; this
0x180036992  call    ??1CSysFreeMe@@QEAA@XZ; CSysFreeMe::~CSysFreeMe(void)
0x180036997  jmp     short loc_180036942
0x180036999  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003699f  mov     edx, ebx
0x1800369a1  mov     rcx, rax
0x1800369a4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800369aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800369b1  lea     rax, WPP_GLOBAL_Control
0x1800369b8  cmp     rcx, rax
0x1800369bb  jz      short loc_1800369DE
0x1800369bd  test    byte ptr [rcx+1Ch], 1
0x1800369c1  jz      short loc_1800369DE
0x1800369c3  cmp     byte ptr [rcx+19h], 2
0x1800369c7  jb      short loc_1800369DE
0x1800369c9  mov     edx, 125h
0x1800369ce  mov     r9d, ebx
0x1800369d1  mov     r8, r13
0x1800369d4  mov     rcx, [rcx+10h]
0x1800369d8  call    WPP_SF_d
0x1800369dd  nop
0x1800369de  lea     rcx, [rbp+arg_18]; this
0x1800369e2  call    ??1CSysFreeMe@@QEAA@XZ; CSysFreeMe::~CSysFreeMe(void)
0x1800369e7  jmp     short loc_180036A44
0x1800369e9  mov     rax, [rdi]
0x1800369ec  mov     rcx, rdi
0x1800369ef  mov     rax, [rax+50h]
0x1800369f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800369f8  test    ebx, ebx
0x1800369fa  jns     short loc_180036A42
0x1800369fc  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180036a02  mov     edx, ebx
0x180036a04  mov     rcx, rax
0x180036a07  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180036a0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180036a14  lea     rax, WPP_GLOBAL_Control
0x180036a1b  cmp     rcx, rax
0x180036a1e  jz      short loc_180036A44
0x180036a20  test    byte ptr [rcx+1Ch], 1
0x180036a24  jz      short loc_180036A44
0x180036a26  cmp     byte ptr [rcx+19h], 2
0x180036a2a  jb      short loc_180036A44
0x180036a2c  mov     edx, 126h
0x180036a31  mov     r9d, ebx
0x180036a34  mov     r8, r13
0x180036a37  mov     rcx, [rcx+10h]
0x180036a3b  call    WPP_SF_d
0x180036a40  jmp     short loc_180036A44
0x180036a42  xor     ebx, ebx
0x180036a44  lea     rcx, [rbp+pvarg]; pvarg
0x180036a48  call    cs:__imp_VariantClear
0x180036a4e  mov     eax, ebx
0x180036a50  mov     rbx, [rsp+60h+arg_0]
0x180036a58  add     rsp, 60h
0x180036a5c  pop     r14
0x180036a5e  pop     r13
0x180036a60  pop     rdi
0x180036a61  pop     rsi
0x180036a62  pop     rbp
0x180036a63  retn
```
