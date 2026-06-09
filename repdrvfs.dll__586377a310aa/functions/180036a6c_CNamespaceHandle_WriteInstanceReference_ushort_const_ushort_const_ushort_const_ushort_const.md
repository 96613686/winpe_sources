# CNamespaceHandle::WriteInstanceReference(ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x180036a6c`
- end: `0x180036dd0`
- name: `?WriteInstanceReference@CNamespaceHandle@@IEAAJPEBG000@Z`
- size: `868`
- prototype: `__int64 __usercall@<rax>(CNamespaceHandle *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *Src@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001fcbc`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x18001e134`
- `0x1800203a0`
- `0x180023bf0`
- `0x18002b7b6`
- `0x1800329f4`
- `0x180036a6c`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180036c1b`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180036c1b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180036b2b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180036b63`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180036bb9`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180036c7f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180036d93`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180036d9d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180036dac`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180036db6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180036b2b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180036b63`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180036bb9`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180036c7f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180036d93`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180036d9d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180036dac`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180036db6`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x180036bf8`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x180036c93`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x180036cb5`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x180036bf8`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x180036c93`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x180036cb5`
- `wbemcomn!GetMemLogObject` at `0x180036adc`
- `wbemcomn!GetMemLogObject` at `0x180036b6f`
- `wbemcomn!GetMemLogObject` at `0x180036c29`
- `wbemcomn!GetMemLogObject` at `0x180036adc`
- `wbemcomn!GetMemLogObject` at `0x180036b6f`
- `wbemcomn!GetMemLogObject` at `0x180036c29`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036aec`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036b7a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036c39`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036aec`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036b7a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036c39`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CNamespaceHandle::WriteInstanceReference(
        CRepository **this,
        const unsigned __int16 *a2,
        const unsigned __int16 *Src,
        const unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  CMemoryLog *MemLogObject; // rax
  unsigned int v10; // ebx
  int v12; // eax
  CMemoryLog *v13; // rax
  char *v14; // r12
  __int64 v15; // rbx
  __int64 v16; // rbp
  __int64 v17; // rsi
  __int64 v18; // rdi
  __int64 v19; // rax
  __int64 v20; // rcx
  unsigned __int64 v21; // rbp
  unsigned __int16 *v22; // rax
  unsigned __int8 *Buf2; // rdi
  CMemoryLog *v24; // rax
  __int64 v25; // rax
  __int64 v26; // rdx
  size_t v27; // r14
  const void *v28; // rax
  __int64 v29; // rax
  unsigned __int8 *v30; // rsi
  size_t v31; // r14
  __int64 v32; // rax
  unsigned __int8 *v33; // rsi
  size_t v34; // r14
  __int64 v35; // rdx
  __int64 v36; // r8
  unsigned __int16 *v37; // rsi
  unsigned int v38; // eax
  unsigned __int16 *v39[11]; // [rsp+30h] [rbp-58h] BYREF

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 232, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
  }
  CFileName::CFileName((CFileName *)v39);
  if ( !v39[0] )
  {
    MemLogObject = GetMemLogObject();
    v10 = -2147217402;
    CMemoryLog::Write(MemLogObject, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 233, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749894LL);
    }
    CWin32DefaultArena::WbemMemFree(0);
    return v10;
  }
  v12 = CNamespaceHandle::ConstructReferenceFileName(this, a5, a2, (struct CFileName *)v39);
  v10 = v12;
  if ( v12 >= 0 )
  {
    v14 = (char *)(this + 4);
    v15 = -1;
    v16 = -1;
    do
      ++v16;
    while ( a4[v16] );
    v17 = -1;
    do
      ++v17;
    while ( Src[v17] );
    v18 = -1;
    do
      ++v18;
    while ( a2[v18] );
    v19 = WString::operator unsigned short *(v14);
    v20 = -1;
    do
      ++v20;
    while ( *(_WORD *)(v19 + 2 * v20) );
    v21 = (unsigned int)(2 * (v16 + v17 + v18 + v20) + 24);
    v22 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(v21);
    Buf2 = (unsigned __int8 *)v22;
    if ( v22 )
    {
      v39[1] = v22;
      v25 = WString::operator unsigned short *(v14);
      v26 = -1;
      do
        ++v26;
      while ( *(_WORD *)(v25 + 2 * v26) );
      *(_DWORD *)Buf2 = v26;
      v27 = 2LL * (unsigned int)v26;
      v28 = (const void *)WString::operator unsigned short *(v14);
      memcpy_0(Buf2 + 4, v28, v27);
      v29 = -1;
      do
        ++v29;
      while ( Src[v29] );
      *(_DWORD *)&Buf2[v27 + 4] = v29;
      v30 = &Buf2[v27 + 8];
      v31 = 2LL * (unsigned int)v29;
      memcpy_0(v30, Src, v31);
      v32 = -1;
      do
        ++v32;
      while ( a4[v32] );
      *(_DWORD *)&v30[v31] = v32;
      v33 = &v30[v31];
      v34 = 2LL * (unsigned int)v32;
      memcpy_0(v33 + 4, a4, v34);
      do
        ++v15;
      while ( a2[v15] );
      *(_DWORD *)&v33[v34 + 4] = v15;
      memcpy_0(&v33[v34 + 8], a2, 2LL * (unsigned int)v15);
      v37 = v39[0];
      if ( !dword_180058AFC || g_bShuttingDown )
      {
        v38 = 1255;
      }
      else
      {
        v38 = CObjectHeap::WriteObject((CObjectHeap *)&qword_180058EF8, v39[0], 0, v21, Buf2);
        if ( !v38 )
        {
          CWin32DefaultArena::WbemMemFree(Buf2);
          CWin32DefaultArena::WbemMemFree(v37);
          return 0;
        }
      }
      v10 = A51TranslateErrorCode(v38, v35, v36);
      CWin32DefaultArena::WbemMemFree(Buf2);
      CWin32DefaultArena::WbemMemFree(v37);
      return v10;
    }
    v24 = GetMemLogObject();
    v10 = -2147217402;
    CMemoryLog::Write(v24, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 235, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749894LL);
    }
LABEL_19:
    CWin32DefaultArena::WbemMemFree(v39[0]);
    return v10;
  }
  if ( v12 != -2147217406 )
  {
    v13 = GetMemLogObject();
    CMemoryLog::Write(v13, v10);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 234, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, v10);
    }
    goto LABEL_19;
  }
  CWin32DefaultArena::WbemMemFree(v39[0]);
  return 0;
}

```

## disassembly

```asm
0x180036a6c  mov     [rsp+Src], r9
0x180036a71  push    rbx
0x180036a72  push    rbp
0x180036a73  push    rsi
0x180036a74  push    rdi
0x180036a75  push    r12
0x180036a77  push    r13
0x180036a79  push    r14
0x180036a7b  push    r15
0x180036a7d  sub     rsp, 48h
0x180036a81  mov     rsi, r9
0x180036a84  mov     r13, r8
0x180036a87  mov     r15, rdx
0x180036a8a  mov     rdi, rcx
0x180036a8d  lea     rax, WPP_GLOBAL_Control
0x180036a94  lea     r12, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180036a9b  mov     bpl, 1
0x180036a9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180036aa5  cmp     rcx, rax
0x180036aa8  jz      short loc_180036AC7
0x180036aaa  test    [rcx+1Ch], bpl
0x180036aae  jz      short loc_180036AC7
0x180036ab0  cmp     byte ptr [rcx+19h], 5
0x180036ab4  jb      short loc_180036AC7
0x180036ab6  mov     edx, 0E8h
0x180036abb  mov     r8, r12
0x180036abe  mov     rcx, [rcx+10h]
0x180036ac2  call    WPP_SF_
0x180036ac7  lea     rcx, [rsp+88h+var_58]; this
0x180036acc  call    ??0CFileName@@QEAA@XZ; CFileName::CFileName(void)
0x180036ad1  nop
0x180036ad2  xor     r14d, r14d
0x180036ad5  cmp     [rsp+88h+var_58], r14
0x180036ada  jnz     short loc_180036B39
0x180036adc  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180036ae2  mov     ebx, 80041006h
0x180036ae7  mov     edx, ebx
0x180036ae9  mov     rcx, rax
0x180036aec  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180036af2  mov     rcx, cs:WPP_GLOBAL_Control
0x180036af9  lea     rax, WPP_GLOBAL_Control
0x180036b00  cmp     rcx, rax
0x180036b03  jz      short loc_180036B29
0x180036b05  test    [rcx+1Ch], bpl
0x180036b09  jz      short loc_180036B29
0x180036b0b  cmp     byte ptr [rcx+19h], 2
0x180036b0f  jb      short loc_180036B29
0x180036b11  mov     edx, 0E9h
0x180036b16  mov     r9d, 80041006h
0x180036b1c  mov     r8, r12
0x180036b1f  mov     rcx, [rcx+10h]
0x180036b23  call    WPP_SF_d
0x180036b28  nop
0x180036b29  xor     ecx, ecx
0x180036b2b  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180036b31  nop
0x180036b32  mov     eax, ebx
0x180036b34  jmp     loc_180036DBF
0x180036b39  lea     r9, [rsp+88h+var_58]; struct CFileName *
0x180036b3e  mov     r8, r15; unsigned __int16 *
0x180036b41  mov     rdx, [rsp+88h+arg_20]; unsigned __int16 *
0x180036b49  mov     rcx, rdi; this
0x180036b4c  call    ?ConstructReferenceFileName@CNamespaceHandle@@IEAAJPEBG0AEAVCFileName@@@Z; CNamespaceHandle::ConstructReferenceFileName(ushort const *,ushort const *,CFileName &)
0x180036b51  mov     ebx, eax
0x180036b53  test    eax, eax
0x180036b55  jns     short loc_180036BC5
0x180036b57  cmp     eax, 80041002h
0x180036b5c  jnz     short loc_180036B6F
0x180036b5e  mov     rcx, [rsp+88h+var_58]
0x180036b63  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180036b69  nop
0x180036b6a  jmp     loc_180036DBD
0x180036b6f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180036b75  mov     edx, ebx
0x180036b77  mov     rcx, rax
0x180036b7a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180036b80  mov     rcx, cs:WPP_GLOBAL_Control
0x180036b87  lea     rax, WPP_GLOBAL_Control
0x180036b8e  cmp     rcx, rax
0x180036b91  jz      short loc_180036BB4
0x180036b93  test    [rcx+1Ch], bpl
0x180036b97  jz      short loc_180036BB4
0x180036b99  cmp     byte ptr [rcx+19h], 2
0x180036b9d  jb      short loc_180036BB4
0x180036b9f  mov     edx, 0EAh
0x180036ba4  mov     r9d, ebx
0x180036ba7  mov     r8, r12
0x180036baa  mov     rcx, [rcx+10h]
0x180036bae  call    WPP_SF_d
0x180036bb3  nop
0x180036bb4  mov     rcx, [rsp+88h+var_58]
0x180036bb9  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180036bbf  nop
0x180036bc0  jmp     loc_180036B32
0x180036bc5  lea     r12, [rdi+20h]
0x180036bc9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180036bcd  mov     rbp, rbx
0x180036bd0  inc     rbp
0x180036bd3  cmp     [rsi+rbp*2], r14w
0x180036bd8  jnz     short loc_180036BD0
0x180036bda  mov     rsi, rbx
0x180036bdd  inc     rsi
0x180036be0  cmp     [r13+rsi*2+0], r14w
0x180036be6  jnz     short loc_180036BDD
0x180036be8  mov     rdi, rbx
0x180036beb  inc     rdi
0x180036bee  cmp     [r15+rdi*2], r14w
0x180036bf3  jnz     short loc_180036BEB
0x180036bf5  mov     rcx, r12
0x180036bf8  call    cs:__imp_??BWString@@QEAAPEAGXZ; WString::operator ushort *(void)
0x180036bfe  mov     rcx, rbx
0x180036c01  inc     rcx
0x180036c04  cmp     [rax+rcx*2], r14w
0x180036c09  jnz     short loc_180036C01
0x180036c0b  lea     eax, [rdi+rcx]
0x180036c0e  add     eax, esi
0x180036c10  add     eax, ebp
0x180036c12  lea     ebp, ds:18h[rax*2]
0x180036c19  mov     ecx, ebp
0x180036c1b  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180036c21  mov     rdi, rax
0x180036c24  test    rax, rax
0x180036c27  jnz     short loc_180036C8B
0x180036c29  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180036c2f  mov     ebx, 80041006h
0x180036c34  mov     edx, ebx
0x180036c36  mov     rcx, rax
0x180036c39  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180036c3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180036c46  lea     rax, WPP_GLOBAL_Control
0x180036c4d  cmp     rcx, rax
0x180036c50  jz      short loc_180036C7A
0x180036c52  test    byte ptr [rcx+1Ch], 1
0x180036c56  jz      short loc_180036C7A
0x180036c58  cmp     byte ptr [rcx+19h], 2
0x180036c5c  jb      short loc_180036C7A
0x180036c5e  mov     edx, 0EBh
0x180036c63  mov     r9d, 80041006h
0x180036c69  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180036c70  mov     rcx, [rcx+10h]
0x180036c74  call    WPP_SF_d
0x180036c79  nop
0x180036c7a  mov     rcx, [rsp+88h+var_58]
0x180036c7f  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180036c85  nop
0x180036c86  jmp     loc_180036B32
0x180036c8b  mov     [rsp+88h+var_50], rdi
0x180036c90  mov     rcx, r12
0x180036c93  call    cs:__imp_??BWString@@QEAAPEAGXZ; WString::operator ushort *(void)
0x180036c99  mov     rdx, rbx
0x180036c9c  inc     rdx
0x180036c9f  cmp     [rax+rdx*2], r14w
0x180036ca4  jnz     short loc_180036C9C
0x180036ca6  mov     [rdi], edx
0x180036ca8  lea     rsi, [rdi+4]
0x180036cac  mov     eax, edx
0x180036cae  lea     r14, [rax+rax]
0x180036cb2  mov     rcx, r12
0x180036cb5  call    cs:__imp_??BWString@@QEAAPEAGXZ; WString::operator ushort *(void)
0x180036cbb  mov     rdx, rax; Src
0x180036cbe  mov     r8, r14; Size
0x180036cc1  mov     rcx, rsi; void *
0x180036cc4  call    memcpy_0
0x180036cc9  mov     rax, rbx
0x180036ccc  xor     r12d, r12d
0x180036ccf  inc     rax
0x180036cd2  cmp     [r13+rax*2+0], r12w
0x180036cd8  jnz     short loc_180036CCF
0x180036cda  mov     [r14+rsi], eax
0x180036cde  add     rsi, 4
0x180036ce2  add     rsi, r14
0x180036ce5  mov     eax, eax
0x180036ce7  lea     r14, [rax+rax]
0x180036ceb  mov     r8, r14; Size
0x180036cee  mov     rdx, r13; Src
0x180036cf1  mov     rcx, rsi; void *
0x180036cf4  call    memcpy_0
0x180036cf9  mov     rax, rbx
0x180036cfc  mov     rdx, [rsp+88h+Src]; Src
0x180036d04  inc     rax
0x180036d07  cmp     [rdx+rax*2], r12w
0x180036d0c  jnz     short loc_180036D04
0x180036d0e  mov     [r14+rsi], eax
0x180036d12  add     rsi, r14
0x180036d15  mov     eax, eax
0x180036d17  lea     r14, [rax+rax]
0x180036d1b  mov     r8, r14; Size
0x180036d1e  lea     rcx, [rsi+4]; void *
0x180036d22  call    memcpy_0
0x180036d27  inc     rbx
0x180036d2a  cmp     [r15+rbx*2], r12w
0x180036d2f  jnz     short loc_180036D27
0x180036d31  mov     [r14+rsi+4], ebx
0x180036d36  mov     r8d, ebx
0x180036d39  add     r8, r8; Size
0x180036d3c  lea     rcx, [rsi+8]
0x180036d40  add     rcx, r14; void *
0x180036d43  mov     rdx, r15; Src
0x180036d46  call    memcpy_0
0x180036d4b  mov     rsi, [rsp+88h+var_58]
0x180036d50  cmp     cs:dword_180058AFC, r12d
0x180036d57  jnz     short loc_180036D60
0x180036d59  mov     eax, 4E7h
0x180036d5e  jmp     short loc_180036D87
0x180036d60  cmp     cs:?g_bShuttingDown@@3_NA, r12b; bool g_bShuttingDown
0x180036d67  jnz     short loc_180036D59
0x180036d69  mov     [rsp+88h+Buf2], rdi; Buf2
0x180036d6e  mov     r9d, ebp; unsigned int
0x180036d71  xor     r8d, r8d; unsigned __int16 *
0x180036d74  mov     rdx, rsi; unsigned __int16 *
0x180036d77  lea     rcx, qword_180058EF8; this
0x180036d7e  call    ?WriteObject@CObjectHeap@@QEAAJPEBG0KPEAE@Z; CObjectHeap::WriteObject(ushort const *,ushort const *,ulong,uchar *)
0x180036d83  test    eax, eax
0x180036d85  jz      short loc_180036DA9
0x180036d87  mov     ecx, eax; int
0x180036d89  call    ?A51TranslateErrorCode@@YAJJ@Z; A51TranslateErrorCode(long)
0x180036d8e  mov     ebx, eax
0x180036d90  mov     rcx, rdi
0x180036d93  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180036d99  nop
0x180036d9a  mov     rcx, rsi
0x180036d9d  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180036da3  nop
0x180036da4  jmp     loc_180036B32
0x180036da9  mov     rcx, rdi
0x180036dac  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180036db2  nop
0x180036db3  mov     rcx, rsi
0x180036db6  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180036dbc  nop
0x180036dbd  xor     eax, eax
0x180036dbf  add     rsp, 48h
0x180036dc3  pop     r15
0x180036dc5  pop     r14
0x180036dc7  pop     r13
0x180036dc9  pop     r12
0x180036dcb  pop     rdi
0x180036dcc  pop     rsi
0x180036dcd  pop     rbp
0x180036dce  pop     rbx
0x180036dcf  retn
```
