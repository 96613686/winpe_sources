# CNamespaceHandle::ConstructReferenceFileName(ushort const *,ushort const *,CFileName &)

- ea: `0x1800329f4`
- end: `0x180032b1b`
- name: `?ConstructReferenceFileName@CNamespaceHandle@@IEAAJPEBG0AEAVCFileName@@@Z`
- size: `295`
- prototype: `__int64 __fastcall(CRepository **this, const unsigned __int16 *, const unsigned __int16 *, struct CFileName *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180034080`
- `0x180036a6c`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x180006960`
- `0x180013f90`
- `0x18002435c`
- `0x1800329f4`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180032a55`
- `wbemcomn!GetMemLogObject` at `0x180032ad0`
- `wbemcomn!GetMemLogObject` at `0x180032a55`
- `wbemcomn!GetMemLogObject` at `0x180032ad0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180032a60`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180032ae0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180032a60`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180032ae0`

## pseudocode

```c
__int64 __fastcall CNamespaceHandle::ConstructReferenceFileName(
        CRepository **this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct CFileName *a4)
{
  unsigned int v8; // ebx
  CMemoryLog *MemLogObject; // rax
  CVarObjHeap *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  __int64 v14; // rcx
  __int64 v15; // rax
  CMemoryLog *v16; // rax

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 229, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
  }
  v8 = CNamespaceHandle::ConstructReferenceDir(this, a2, a4);
  if ( (v8 & 0x80000000) != 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v8);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v8;
    }
    v11 = 230;
    v12 = v8;
LABEL_10:
    WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, v12);
    return v8;
  }
  StringCchCatW(*(unsigned __int16 **)a4, 0x173u, L"\\R_");
  v14 = *(_QWORD *)a4;
  v15 = -1;
  do
    ++v15;
  while ( *(_WORD *)(v14 + 2 * v15) );
  if ( !A51Hash(a3, (unsigned __int16 *)(v14 + 2LL * (unsigned int)v15)) )
  {
    v16 = GetMemLogObject();
    v8 = -2147217402;
    CMemoryLog::Write(v16, -2147217402);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v8;
    }
    v11 = 231;
    v12 = 2147749894LL;
    goto LABEL_10;
  }
  return 0;
}

```

## disassembly

```asm
0x1800329f4  push    rbx
0x1800329f6  push    rbp
0x1800329f7  push    rsi
0x1800329f8  push    rdi
0x1800329f9  push    r12
0x1800329fb  sub     rsp, 20h
0x1800329ff  mov     rdi, r9
0x180032a02  mov     rbp, r8
0x180032a05  mov     rbx, rdx
0x180032a08  mov     rsi, rcx
0x180032a0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180032a12  lea     r12, WPP_GLOBAL_Control
0x180032a19  cmp     rcx, r12
0x180032a1c  jz      short loc_180032A3F
0x180032a1e  test    byte ptr [rcx+1Ch], 1
0x180032a22  jz      short loc_180032A3F
0x180032a24  cmp     byte ptr [rcx+19h], 5
0x180032a28  jb      short loc_180032A3F
0x180032a2a  mov     rcx, [rcx+10h]
0x180032a2e  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180032a35  mov     edx, 0E5h
0x180032a3a  call    WPP_SF_
0x180032a3f  mov     r8, rdi; struct CFileName *
0x180032a42  mov     rdx, rbx; unsigned __int16 *
0x180032a45  mov     rcx, rsi; this
0x180032a48  call    ?ConstructReferenceDir@CNamespaceHandle@@IEAAJPEBGAEAVCFileName@@@Z; CNamespaceHandle::ConstructReferenceDir(ushort const *,CFileName &)
0x180032a4d  xor     esi, esi
0x180032a4f  mov     ebx, eax
0x180032a51  test    eax, eax
0x180032a53  jns     short loc_180032A9A
0x180032a55  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180032a5b  mov     rcx, rax
0x180032a5e  mov     edx, ebx
0x180032a60  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180032a66  mov     rcx, cs:WPP_GLOBAL_Control
0x180032a6d  cmp     rcx, r12
0x180032a70  jz      short loc_180032A96
0x180032a72  test    byte ptr [rcx+1Ch], 1
0x180032a76  jz      short loc_180032A96
0x180032a78  cmp     byte ptr [rcx+19h], 2
0x180032a7c  jb      short loc_180032A96
0x180032a7e  mov     edx, 0E6h
0x180032a83  mov     r9d, ebx
0x180032a86  mov     rcx, [rcx+10h]
0x180032a8a  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180032a91  call    WPP_SF_d
0x180032a96  mov     eax, ebx
0x180032a98  jmp     short loc_180032B10
0x180032a9a  mov     rcx, [rdi]; unsigned __int16 *
0x180032a9d  lea     r8, aR; "\\R_"
0x180032aa4  mov     edx, 173h; unsigned __int64
0x180032aa9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180032aae  mov     rcx, [rdi]
0x180032ab1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180032ab5  inc     rax
0x180032ab8  cmp     [rcx+rax*2], si
0x180032abc  jnz     short loc_180032AB5
0x180032abe  mov     eax, eax
0x180032ac0  lea     rdx, [rcx+rax*2]; unsigned __int16 *
0x180032ac4  mov     rcx, rbp; unsigned __int16 *
0x180032ac7  call    ?A51Hash@@YA_NPEBGPEAG@Z; A51Hash(ushort const *,ushort *)
0x180032acc  test    al, al
0x180032ace  jnz     short loc_180032B0E
0x180032ad0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180032ad6  mov     ebx, 80041006h
0x180032adb  mov     rcx, rax
0x180032ade  mov     edx, ebx
0x180032ae0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180032ae6  mov     rcx, cs:WPP_GLOBAL_Control
0x180032aed  cmp     rcx, r12
0x180032af0  jz      short loc_180032A96
0x180032af2  test    byte ptr [rcx+1Ch], 1
0x180032af6  jz      short loc_180032A96
0x180032af8  cmp     byte ptr [rcx+19h], 2
0x180032afc  jb      short loc_180032A96
0x180032afe  mov     edx, 0E7h
0x180032b03  mov     r9d, 80041006h
0x180032b09  jmp     loc_180032A86
0x180032b0e  xor     eax, eax
0x180032b10  add     rsp, 20h
0x180032b14  pop     r12
0x180032b16  pop     rdi
0x180032b17  pop     rsi
0x180032b18  pop     rbp
0x180032b19  pop     rbx
0x180032b1a  retn
```
