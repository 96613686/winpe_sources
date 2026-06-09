# CNamespaceHandle::DeleteInstanceReferences(_IWmiObject *,ushort const *)

- ea: `0x1800149cc`
- end: `0x180014bab`
- name: `?DeleteInstanceReferences@CNamespaceHandle@@IEAAJPEAU_IWmiObject@@PEBG@Z`
- size: `479`
- prototype: `__int64 __fastcall(CRepository **this, struct _IWmiObject *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001404c`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x1800149cc`
- `0x180034080`
- `0x180048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180014a34`
- `wbemcomn!GetMemLogObject` at `0x180014af8`
- `wbemcomn!GetMemLogObject` at `0x180014b4e`
- `wbemcomn!GetMemLogObject` at `0x180014a34`
- `wbemcomn!GetMemLogObject` at `0x180014af8`
- `wbemcomn!GetMemLogObject` at `0x180014b4e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180014a3f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180014b03`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180014b59`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180014a3f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180014b03`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180014b59`
- `OLEAUT32!__imp_VariantClear` at `0x180014af0`
- `OLEAUT32!__imp_VariantClear` at `0x180014b3f`
- `OLEAUT32!__imp_VariantClear` at `0x180014af0`
- `OLEAUT32!__imp_VariantClear` at `0x180014b3f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CNamespaceHandle::DeleteInstanceReferences(
        CRepository **this,
        struct _IWmiObject *a2,
        const unsigned __int16 *a3)
{
  int v6; // ebx
  CMemoryLog *v7; // rax
  CVarObjHeap *v8; // rcx
  __int64 v9; // rdx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v12; // rax
  VARIANTARG pvarg; // [rsp+40h] [rbp-58h] BYREF

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 362, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
  }
  v6 = (*(__int64 (__fastcall **)(struct _IWmiObject *, __int64))(*(_QWORD *)a2 + 64LL))(a2, 8);
  if ( v6 >= 0 )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    while ( 1 )
    {
      v6 = (*(__int64 (__fastcall **)(struct _IWmiObject *, _QWORD, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)a2 + 72LL))(
             a2,
             0,
             0,
             &pvarg,
             0,
             0);
      if ( v6 )
        break;
      if ( pvarg.vt == 8 )
      {
        v6 = CNamespaceHandle::DeleteInstanceReference(this, a3, pvarg.bstrVal);
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
              364,
              WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
              (unsigned int)v6);
          }
          VariantClear(&pvarg);
          return (unsigned int)v6;
        }
      }
      VariantClear(&pvarg);
    }
    if ( v6 >= 0 )
    {
      (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)a2 + 80LL))(a2);
      return 0;
    }
    v12 = GetMemLogObject();
    CMemoryLog::Write(v12, v6);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = 365;
      goto LABEL_10;
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
      v9 = 363;
LABEL_10:
      WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, (unsigned int)v6);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800149cc  push    rbx
0x1800149ce  push    rbp
0x1800149cf  push    rsi
0x1800149d0  push    rdi
0x1800149d1  push    r12
0x1800149d3  push    r13
0x1800149d5  sub     rsp, 68h
0x1800149d9  mov     rsi, r8
0x1800149dc  mov     rdi, rdx
0x1800149df  mov     rbp, rcx
0x1800149e2  lea     r12, WPP_GLOBAL_Control
0x1800149e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800149f0  cmp     rcx, r12
0x1800149f3  jz      short loc_180014A16
0x1800149f5  test    byte ptr [rcx+1Ch], 1
0x1800149f9  jz      short loc_180014A16
0x1800149fb  cmp     byte ptr [rcx+19h], 5
0x1800149ff  jb      short loc_180014A16
0x180014a01  mov     edx, 16Ah
0x180014a06  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180014a0d  mov     rcx, [rcx+10h]
0x180014a11  call    WPP_SF_
0x180014a16  mov     rax, [rdi]
0x180014a19  mov     r13d, 8
0x180014a1f  mov     edx, r13d
0x180014a22  mov     rcx, rdi
0x180014a25  mov     rax, [rax+40h]
0x180014a29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a2e  mov     ebx, eax
0x180014a30  test    eax, eax
0x180014a32  jns     short loc_180014A7C
0x180014a34  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180014a3a  mov     edx, ebx
0x180014a3c  mov     rcx, rax
0x180014a3f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180014a45  mov     rcx, cs:WPP_GLOBAL_Control
0x180014a4c  cmp     rcx, r12
0x180014a4f  jz      short loc_180014A75
0x180014a51  test    byte ptr [rcx+1Ch], 1
0x180014a55  jz      short loc_180014A75
0x180014a57  cmp     byte ptr [rcx+19h], 2
0x180014a5b  jb      short loc_180014A75
0x180014a5d  mov     edx, 16Bh
0x180014a62  mov     r9d, ebx
0x180014a65  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180014a6c  mov     rcx, [rcx+10h]
0x180014a70  call    WPP_SF_d
0x180014a75  mov     eax, ebx
0x180014a77  jmp     loc_180014B9E
0x180014a7c  xorps   xmm0, xmm0
0x180014a7f  xor     eax, eax
0x180014a81  movups  xmmword ptr [rsp+98h+pvarg], xmm0
0x180014a86  mov     qword ptr [rsp+98h+pvarg+10h], rax
0x180014a8b  mov     rax, [rdi]
0x180014a8e  mov     [rsp+98h+var_70], 0
0x180014a97  mov     [rsp+98h+var_78], 0
0x180014aa0  lea     r9, [rsp+98h+pvarg]
0x180014aa5  xor     r8d, r8d
0x180014aa8  xor     edx, edx
0x180014aaa  mov     rcx, rdi
0x180014aad  mov     rax, [rax+48h]
0x180014ab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ab6  mov     ebx, eax
0x180014ab8  test    eax, eax
0x180014aba  jnz     loc_180014B4A
0x180014ac0  lea     rax, [rsp+98h+pvarg]
0x180014ac5  mov     [rsp+98h+arg_8], rax
0x180014acd  cmp     word ptr [rsp+98h+pvarg], r13w
0x180014ad3  jnz     short loc_180014AEB
0x180014ad5  mov     r8, qword ptr [rsp+98h+pvarg+8]; unsigned __int16 *
0x180014ada  mov     rdx, rsi; unsigned __int16 *
0x180014add  mov     rcx, rbp; this
0x180014ae0  call    ?DeleteInstanceReference@CNamespaceHandle@@IEAAJPEBGPEAG@Z; CNamespaceHandle::DeleteInstanceReference(ushort const *,ushort *)
0x180014ae5  mov     ebx, eax
0x180014ae7  test    eax, eax
0x180014ae9  js      short loc_180014AF8
0x180014aeb  lea     rcx, [rsp+98h+pvarg]; pvarg
0x180014af0  call    cs:__imp_VariantClear
0x180014af6  jmp     short loc_180014A8B
0x180014af8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180014afe  mov     edx, ebx
0x180014b00  mov     rcx, rax
0x180014b03  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180014b09  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b10  cmp     rcx, r12
0x180014b13  jz      short loc_180014B3A
0x180014b15  test    byte ptr [rcx+1Ch], 1
0x180014b19  jz      short loc_180014B3A
0x180014b1b  cmp     byte ptr [rcx+19h], 2
0x180014b1f  jb      short loc_180014B3A
0x180014b21  mov     edx, 16Ch
0x180014b26  mov     r9d, ebx
0x180014b29  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180014b30  mov     rcx, [rcx+10h]
0x180014b34  call    WPP_SF_d
0x180014b39  nop
0x180014b3a  lea     rcx, [rsp+98h+pvarg]; pvarg
0x180014b3f  call    cs:__imp_VariantClear
0x180014b45  jmp     loc_180014A75
0x180014b4a  test    ebx, ebx
0x180014b4c  jns     short loc_180014B8D
0x180014b4e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180014b54  mov     edx, ebx
0x180014b56  mov     rcx, rax
0x180014b59  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180014b5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b66  cmp     rcx, r12
0x180014b69  jz      loc_180014A75
0x180014b6f  test    byte ptr [rcx+1Ch], 1
0x180014b73  jz      loc_180014A75
0x180014b79  cmp     byte ptr [rcx+19h], 2
0x180014b7d  jb      loc_180014A75
0x180014b83  mov     edx, 16Dh
0x180014b88  jmp     loc_180014A62
0x180014b8d  mov     rax, [rdi]
0x180014b90  mov     rcx, rdi
0x180014b93  mov     rax, [rax+50h]
0x180014b97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b9c  xor     eax, eax
0x180014b9e  add     rsp, 68h
0x180014ba2  pop     r13
0x180014ba4  pop     r12
0x180014ba6  pop     rdi
0x180014ba7  pop     rsi
0x180014ba8  pop     rbp
0x180014ba9  pop     rbx
0x180014baa  retn
```
