# CNamespaceHandle::WriteInstanceReferences(_IWmiObject *,ushort const *,ushort const *)

- ea: `0x18001fcbc`
- end: `0x18001fed4`
- name: `?WriteInstanceReferences@CNamespaceHandle@@IEAAJPEAU_IWmiObject@@PEBG1@Z`
- size: `536`
- prototype: `__int64 __fastcall(CNamespaceHandle *__hidden this, struct _IWmiObject *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001e370`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x18001fcbc`
- `0x180030fcc`
- `0x180036a6c`
- `0x180048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18001fd26`
- `wbemcomn!GetMemLogObject` at `0x18001fe0a`
- `wbemcomn!GetMemLogObject` at `0x18001fe70`
- `wbemcomn!GetMemLogObject` at `0x18001fd26`
- `wbemcomn!GetMemLogObject` at `0x18001fe0a`
- `wbemcomn!GetMemLogObject` at `0x18001fe70`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001fd31`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001fe15`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001fe7b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001fd31`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001fe15`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001fe7b`
- `OLEAUT32!__imp_VariantClear` at `0x18001fdf5`
- `OLEAUT32!__imp_VariantClear` at `0x18001fe57`
- `OLEAUT32!__imp_VariantClear` at `0x18001fdf5`
- `OLEAUT32!__imp_VariantClear` at `0x18001fe57`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CNamespaceHandle::WriteInstanceReferences(
        CRepository **this,
        struct _IWmiObject *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  int v8; // ebx
  CMemoryLog *v9; // rax
  CVarObjHeap *v10; // rcx
  __int64 v11; // rdx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v14; // rax
  _QWORD v15[2]; // [rsp+40h] [rbp-38h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-28h] BYREF
  unsigned __int16 *v17; // [rsp+B8h] [rbp+40h] BYREF

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 217, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
  }
  v8 = (*(__int64 (__fastcall **)(struct _IWmiObject *, __int64))(*(_QWORD *)a2 + 64LL))(a2, 8);
  if ( v8 >= 0 )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    v17 = 0;
    while ( 1 )
    {
      v8 = (*(__int64 (__fastcall **)(struct _IWmiObject *, _QWORD, unsigned __int16 **, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)a2 + 72LL))(
             a2,
             0,
             &v17,
             &pvarg,
             0,
             0);
      if ( v8 )
        break;
      v15[0] = v17;
      v15[1] = &pvarg;
      if ( pvarg.vt == 8 )
      {
        v8 = CNamespaceHandle::WriteInstanceReference(this, a4, a3, v17, pvarg.bstrVal);
        if ( v8 < 0 )
        {
          MemLogObject = GetMemLogObject();
          CMemoryLog::Write(MemLogObject, v8);
          if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              219,
              WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
              (unsigned int)v8);
          }
          VariantClear(&pvarg);
          CSysFreeMe::~CSysFreeMe((CSysFreeMe *)v15);
          return (unsigned int)v8;
        }
      }
      VariantClear(&pvarg);
      CSysFreeMe::~CSysFreeMe((CSysFreeMe *)v15);
    }
    if ( v8 >= 0 )
    {
      (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)a2 + 80LL))(a2);
      return 0;
    }
    v14 = GetMemLogObject();
    CMemoryLog::Write(v14, v8);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = 220;
      goto LABEL_10;
    }
  }
  else
  {
    v9 = GetMemLogObject();
    CMemoryLog::Write(v9, v8);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = 218;
LABEL_10:
      WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, (unsigned int)v8);
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001fcbc  push    rbp
0x18001fcbe  push    rbx
0x18001fcbf  push    rsi
0x18001fcc0  push    rdi
0x18001fcc1  push    r14
0x18001fcc3  push    r15
0x18001fcc5  mov     rbp, rsp
0x18001fcc8  sub     rsp, 78h
0x18001fccc  mov     rsi, r9
0x18001fccf  mov     r14, r8
0x18001fcd2  mov     rdi, rdx
0x18001fcd5  mov     r15, rcx
0x18001fcd8  lea     rax, WPP_GLOBAL_Control
0x18001fcdf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fce6  cmp     rcx, rax
0x18001fce9  jz      short loc_18001FD0C
0x18001fceb  test    byte ptr [rcx+1Ch], 1
0x18001fcef  jz      short loc_18001FD0C
0x18001fcf1  cmp     byte ptr [rcx+19h], 5
0x18001fcf5  jb      short loc_18001FD0C
0x18001fcf7  mov     edx, 0D9h
0x18001fcfc  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18001fd03  mov     rcx, [rcx+10h]
0x18001fd07  call    WPP_SF_
0x18001fd0c  mov     rax, [rdi]
0x18001fd0f  mov     edx, 8
0x18001fd14  mov     rcx, rdi
0x18001fd17  mov     rax, [rax+40h]
0x18001fd1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd20  mov     ebx, eax
0x18001fd22  test    eax, eax
0x18001fd24  jns     short loc_18001FD75
0x18001fd26  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001fd2c  mov     edx, ebx
0x18001fd2e  mov     rcx, rax
0x18001fd31  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001fd37  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fd3e  lea     rax, WPP_GLOBAL_Control
0x18001fd45  cmp     rcx, rax
0x18001fd48  jz      short loc_18001FD6E
0x18001fd4a  test    byte ptr [rcx+1Ch], 1
0x18001fd4e  jz      short loc_18001FD6E
0x18001fd50  cmp     byte ptr [rcx+19h], 2
0x18001fd54  jb      short loc_18001FD6E
0x18001fd56  mov     edx, 0DAh
0x18001fd5b  mov     r9d, ebx
0x18001fd5e  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18001fd65  mov     rcx, [rcx+10h]
0x18001fd69  call    WPP_SF_d
0x18001fd6e  mov     eax, ebx
0x18001fd70  jmp     loc_18001FEC7
0x18001fd75  xorps   xmm0, xmm0
0x18001fd78  xor     eax, eax
0x18001fd7a  movups  xmmword ptr [rbp+pvarg], xmm0
0x18001fd7e  mov     qword ptr [rbp+pvarg+10h], rax
0x18001fd82  mov     [rbp+arg_8], rax
0x18001fd86  mov     rax, [rdi]
0x18001fd89  mov     [rsp+78h+var_50], 0
0x18001fd92  mov     [rsp+78h+var_58], 0
0x18001fd9b  lea     r9, [rbp+pvarg]
0x18001fd9f  lea     r8, [rbp+arg_8]
0x18001fda3  xor     edx, edx
0x18001fda5  mov     rcx, rdi
0x18001fda8  mov     rax, [rax+48h]
0x18001fdac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fdb1  mov     ebx, eax
0x18001fdb3  test    eax, eax
0x18001fdb5  jnz     loc_18001FE6C
0x18001fdbb  mov     r9, [rbp+arg_8]; unsigned __int16 *
0x18001fdbf  mov     [rbp+var_38], r9
0x18001fdc3  lea     rax, [rbp+pvarg]
0x18001fdc7  mov     [rbp+var_30], rax
0x18001fdcb  lea     eax, [rbx+8]
0x18001fdce  cmp     word ptr [rbp+pvarg], ax
0x18001fdd2  jnz     short loc_18001FDF1
0x18001fdd4  mov     rax, qword ptr [rbp+pvarg+8]
0x18001fdd8  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x18001fddd  mov     r8, r14; Src
0x18001fde0  mov     rdx, rsi; unsigned __int16 *
0x18001fde3  mov     rcx, r15; this
0x18001fde6  call    ?WriteInstanceReference@CNamespaceHandle@@IEAAJPEBG000@Z; CNamespaceHandle::WriteInstanceReference(ushort const *,ushort const *,ushort const *,ushort const *)
0x18001fdeb  mov     ebx, eax
0x18001fded  test    eax, eax
0x18001fdef  js      short loc_18001FE0A
0x18001fdf1  lea     rcx, [rbp+pvarg]; pvarg
0x18001fdf5  call    cs:__imp_VariantClear
0x18001fdfb  nop
0x18001fdfc  lea     rcx, [rbp+var_38]; this
0x18001fe00  call    ??1CSysFreeMe@@QEAA@XZ; CSysFreeMe::~CSysFreeMe(void)
0x18001fe05  jmp     loc_18001FD86
0x18001fe0a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001fe10  mov     edx, ebx
0x18001fe12  mov     rcx, rax
0x18001fe15  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001fe1b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fe22  lea     rax, WPP_GLOBAL_Control
0x18001fe29  cmp     rcx, rax
0x18001fe2c  jz      short loc_18001FE53
0x18001fe2e  test    byte ptr [rcx+1Ch], 1
0x18001fe32  jz      short loc_18001FE53
0x18001fe34  cmp     byte ptr [rcx+19h], 2
0x18001fe38  jb      short loc_18001FE53
0x18001fe3a  mov     edx, 0DBh
0x18001fe3f  mov     r9d, ebx
0x18001fe42  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18001fe49  mov     rcx, [rcx+10h]
0x18001fe4d  call    WPP_SF_d
0x18001fe52  nop
0x18001fe53  lea     rcx, [rbp+pvarg]; pvarg
0x18001fe57  call    cs:__imp_VariantClear
0x18001fe5d  nop
0x18001fe5e  lea     rcx, [rbp+var_38]; this
0x18001fe62  call    ??1CSysFreeMe@@QEAA@XZ; CSysFreeMe::~CSysFreeMe(void)
0x18001fe67  jmp     loc_18001FD6E
0x18001fe6c  test    ebx, ebx
0x18001fe6e  jns     short loc_18001FEB6
0x18001fe70  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001fe76  mov     edx, ebx
0x18001fe78  mov     rcx, rax
0x18001fe7b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001fe81  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fe88  lea     rax, WPP_GLOBAL_Control
0x18001fe8f  cmp     rcx, rax
0x18001fe92  jz      loc_18001FD6E
0x18001fe98  test    byte ptr [rcx+1Ch], 1
0x18001fe9c  jz      loc_18001FD6E
0x18001fea2  cmp     byte ptr [rcx+19h], 2
0x18001fea6  jb      loc_18001FD6E
0x18001feac  mov     edx, 0DCh
0x18001feb1  jmp     loc_18001FD5B
0x18001feb6  mov     rax, [rdi]
0x18001feb9  mov     rcx, rdi
0x18001febc  mov     rax, [rax+50h]
0x18001fec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fec5  xor     eax, eax
0x18001fec7  add     rsp, 78h
0x18001fecb  pop     r15
0x18001fecd  pop     r14
0x18001fecf  pop     rdi
0x18001fed0  pop     rsi
0x18001fed1  pop     rbx
0x18001fed2  pop     rbp
0x18001fed3  retn
```
