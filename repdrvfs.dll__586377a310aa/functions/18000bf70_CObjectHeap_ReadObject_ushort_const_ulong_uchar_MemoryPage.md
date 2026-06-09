# CObjectHeap::ReadObject(ushort const *,ulong *,uchar * *,MemoryPage * *)

- ea: `0x18000bf70`
- end: `0x18000c4f4`
- name: `?ReadObject@CObjectHeap@@QEAAJPEBGPEAKPEAPEAEPEAPEAVMemoryPage@@@Z`
- size: `1412`
- prototype: `int(CObjectHeap *__hidden this, const unsigned __int16 *, unsigned int *, unsigned __int8 **, struct MemoryPage **)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000954c`
- `0x18000b260`
- `0x1800178e0`

## callees

- `0x1800012b8`
- `0x18000bc10`
- `0x18000bf70`
- `0x18000cb50`
- `0x18000f8f0`
- `0x1800443df`
- `0x180044420`

## import_xrefs

- `msvcrt!wcschr` at `0x18000c05a`
- `msvcrt!wcschr` at `0x18000c05a`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000bfbb`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000bfbb`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000c0f3`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000c216`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000c31a`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000c3f6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000c493`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000c0f3`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000c216`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000c31a`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000c3f6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000c493`
- `wbemcomn!GetMemLogObject` at `0x18000c0ca`
- `wbemcomn!GetMemLogObject` at `0x18000c132`
- `wbemcomn!GetMemLogObject` at `0x18000c272`
- `wbemcomn!GetMemLogObject` at `0x18000c2ca`
- `wbemcomn!GetMemLogObject` at `0x18000c321`
- `wbemcomn!GetMemLogObject` at `0x18000c369`
- `wbemcomn!GetMemLogObject` at `0x18000c3b1`
- `wbemcomn!GetMemLogObject` at `0x18000c40c`
- `wbemcomn!GetMemLogObject` at `0x18000c4a3`
- `wbemcomn!GetMemLogObject` at `0x18000c0ca`
- `wbemcomn!GetMemLogObject` at `0x18000c132`
- `wbemcomn!GetMemLogObject` at `0x18000c272`
- `wbemcomn!GetMemLogObject` at `0x18000c2ca`
- `wbemcomn!GetMemLogObject` at `0x18000c321`
- `wbemcomn!GetMemLogObject` at `0x18000c369`
- `wbemcomn!GetMemLogObject` at `0x18000c3b1`
- `wbemcomn!GetMemLogObject` at `0x18000c40c`
- `wbemcomn!GetMemLogObject` at `0x18000c4a3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000c0da`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000c13d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000c280`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000c2da`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000c32c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000c374`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000c3bc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000c41c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000c4b1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000c0da`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000c13d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000c280`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000c2da`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000c32c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000c374`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000c3bc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000c41c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000c4b1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CObjectHeap::ReadObject(
        CObjectHeap *this,
        const unsigned __int16 *a2,
        unsigned int *a3,
        unsigned __int8 **a4,
        struct MemoryPage **a5)
{
  _WORD *v8; // rbx
  void **v9; // r9
  unsigned int First; // edi
  unsigned int v11; // r15d
  __int64 v12; // rcx
  WCHAR *cFileName; // rdx
  __int64 v14; // r9
  WCHAR *v15; // r8
  WCHAR v16; // ax
  WCHAR *v17; // rcx
  wchar_t *v18; // rax
  unsigned int v19; // r14d
  _WORD *v20; // rdx
  wchar_t v21; // ax
  unsigned __int16 *v22; // rdx
  unsigned __int16 i; // ax
  CMemoryLog *v24; // rax
  CVarObjHeap *v25; // rcx
  void **v26; // rdi
  unsigned int Buffer; // ebx
  CMemoryLog *v28; // rax
  unsigned __int16 *v30; // rdx
  unsigned __int16 v31; // ax
  int v32; // ecx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v34; // rax
  CMemoryLog *v35; // rax
  CMemoryLog *v36; // rax
  CMemoryLog *v37; // rax
  CMemoryLog *v38; // rax
  __int64 v39; // rdx
  CMemoryLog *v40; // rax
  unsigned int v41[2]; // [rsp+30h] [rbp-2B8h] BYREF
  unsigned __int8 **v42; // [rsp+38h] [rbp-2B0h]
  struct _WIN32_FIND_DATAW v43; // [rsp+40h] [rbp-2A8h] BYREF

  v42 = a4;
  if ( !*((_DWORD *)this + 2) )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, 4317);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids, 4317);
    }
    return 4317;
  }
  v8 = CWin32DefaultArena::WbemMemAlloc(0x2E6u);
  *(_QWORD *)v41 = v8;
  if ( !v8 )
  {
    v34 = GetMemLogObject();
    First = 14;
    CMemoryLog::Write(v34, 14);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids, 14);
    }
    CWin32DefaultArena::WbemMemFree(0);
    goto LABEL_52;
  }
  *v8 = 0;
  memset_0(&v43, 0, sizeof(v43));
  First = CBtrIndex::FindFirst((CObjectHeap *)((char *)this + 32), a2, &v43, v9);
  if ( First )
  {
    if ( First == 2 )
    {
      CWin32DefaultArena::WbemMemFree(v8);
      return 2;
    }
    v36 = GetMemLogObject();
    CMemoryLog::Write(v36, First);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids, First);
    }
    v37 = GetMemLogObject();
    CMemoryLog::Write(v37, First);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids, First);
    }
    CWin32DefaultArena::WbemMemFree(v8);
    goto LABEL_52;
  }
  v11 = 0;
  v12 = 2147483646;
  cFileName = v43.cFileName;
  v14 = 371;
  v15 = v8;
  do
  {
    if ( !v12 )
      break;
    v16 = *cFileName;
    if ( !*cFileName )
      break;
    ++cFileName;
    *v15++ = v16;
    --v12;
    --v14;
  }
  while ( v14 );
  v17 = v15 - 1;
  if ( v14 )
    v17 = v15;
  *v17 = 0;
  v18 = wcschr(v8, 0x2Eu);
  v19 = 0;
  if ( !v18 )
  {
    First = 87;
    goto LABEL_19;
  }
  v20 = v18 + 1;
  v21 = v18[1];
  if ( v21 )
  {
    do
    {
      if ( v21 == 46 )
        break;
      v19 = v21 + 2 * (5 * v19 - 24);
      v21 = *++v20;
    }
    while ( *v20 );
  }
  if ( *v20 == 46 )
  {
    v22 = v20 + 1;
    for ( i = *v22; *v22; i = *v22 )
    {
      if ( i == 46 )
        break;
      v11 = i + 2 * (5 * v11 - 24);
      ++v22;
    }
    if ( *v22 == 46 )
    {
      v30 = v22 + 1;
      *a3 = 0;
      v31 = *v30;
      if ( *v30 )
      {
        v32 = 0;
        do
        {
          if ( v31 == 46 )
            break;
          v32 = v31 + 2 * (5 * v32 - 24);
          *a3 = v32;
          v31 = *++v30;
        }
        while ( *v30 );
      }
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids, 0);
      }
      First = 0;
    }
    else
    {
      v24 = GetMemLogObject();
      First = 87;
      CMemoryLog::Write(v24, 87);
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v39 = 20;
        goto LABEL_71;
      }
    }
  }
  else
  {
    v38 = GetMemLogObject();
    First = 87;
    CMemoryLog::Write(v38, 87);
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v39 = 19;
LABEL_71:
      WPP_SF_d(*((_QWORD *)v25 + 2), v39, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids, 87);
    }
  }
LABEL_19:
  CWin32DefaultArena::WbemMemFree(v8);
  if ( First )
  {
LABEL_52:
    v35 = GetMemLogObject();
    CMemoryLog::Write(v35, First);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids, First);
    }
    return First;
  }
  v41[0] = 0;
  v26 = (void **)v42;
  Buffer = CVarObjHeap::ReadBuffer((CObjectHeap *)((char *)this + 16), v19, v11, v42, v41, a5);
  if ( Buffer )
  {
    v28 = GetMemLogObject();
    CMemoryLog::Write(v28, Buffer);
    goto LABEL_23;
  }
  if ( v41[0] == *a3 )
  {
LABEL_23:
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids, Buffer);
    }
    return Buffer;
  }
  if ( a5 )
    MemoryPage::Release(*a5);
  else
    CWin32DefaultArena::WbemMemFree(*v26);
  *a5 = 0;
  *v26 = 0;
  v40 = GetMemLogObject();
  CMemoryLog::Write(v40, 1358);
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids, 1358);
  }
  return 1358;
}

```

## disassembly

```asm
0x18000bf70  push    rbx
0x18000bf72  push    rbp
0x18000bf73  push    rsi
0x18000bf74  push    rdi
0x18000bf75  push    r12
0x18000bf77  push    r13
0x18000bf79  push    r14
0x18000bf7b  push    r15
0x18000bf7d  sub     rsp, 2A8h
0x18000bf84  mov     rax, cs:__security_cookie
0x18000bf8b  xor     rax, rsp
0x18000bf8e  mov     [rsp+2E8h+var_58], rax
0x18000bf96  mov     [rsp+2E8h+var_2B0], r9
0x18000bf9b  mov     r12, r8
0x18000bf9e  mov     rdi, rdx
0x18000bfa1  mov     rbp, rcx
0x18000bfa4  mov     r13, [rsp+2E8h+arg_20]
0x18000bfac  cmp     dword ptr [rcx+8], 0
0x18000bfb0  jz      loc_18000C272
0x18000bfb6  mov     ecx, 2E6h
0x18000bfbb  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000bfc1  mov     rbx, rax
0x18000bfc4  mov     qword ptr [rsp+2E8h+var_2B8], rax
0x18000bfc9  test    rax, rax
0x18000bfcc  jz      short loc_18000BFD3
0x18000bfce  xor     eax, eax
0x18000bfd0  mov     [rbx], ax
0x18000bfd3  test    rbx, rbx
0x18000bfd6  jz      loc_18000C2CA
0x18000bfdc  xor     edx, edx; Val
0x18000bfde  mov     r8d, 250h; Size
0x18000bfe4  lea     rcx, [rsp+2E8h+var_2A8]; void *
0x18000bfe9  call    memset_0
0x18000bfee  lea     rcx, [rbp+20h]; this
0x18000bff2  lea     r8, [rsp+2E8h+var_2A8]; struct _WIN32_FIND_DATAW *
0x18000bff7  mov     rdx, rdi; unsigned __int16 *
0x18000bffa  call    ?FindFirst@CBtrIndex@@QEAAJPEBGPEAU_WIN32_FIND_DATAW@@PEAPEAX@Z; CBtrIndex::FindFirst(ushort const *,_WIN32_FIND_DATAW *,void * *)
0x18000bfff  mov     edi, eax
0x18000c001  test    eax, eax
0x18000c003  jnz     loc_18000C20A
0x18000c009  xor     r15d, r15d
0x18000c00c  mov     ecx, 7FFFFFFEh
0x18000c011  lea     rdx, [rsp+2E8h+var_2A8.cFileName]
0x18000c016  mov     r9d, 173h
0x18000c01c  mov     r8, rbx
0x18000c01f  nop
0x18000c020  test    rcx, rcx
0x18000c023  jz      short loc_18000C042
0x18000c025  movzx   eax, word ptr [rdx]
0x18000c028  test    ax, ax
0x18000c02b  jz      short loc_18000C042
0x18000c02d  add     rdx, 2
0x18000c031  mov     [r8], ax
0x18000c035  add     r8, 2
0x18000c039  dec     rcx
0x18000c03c  sub     r9, 1
0x18000c040  jnz     short loc_18000C020
0x18000c042  lea     rcx, [r8-2]
0x18000c046  test    r9, r9
0x18000c049  cmovnz  rcx, r8
0x18000c04d  xor     eax, eax
0x18000c04f  mov     [rcx], ax
0x18000c052  mov     edx, 2Eh ; '.'; Ch
0x18000c057  mov     rcx, rbx; Str
0x18000c05a  call    cs:__imp_wcschr
0x18000c060  lea     rsi, WPP_GLOBAL_Control
0x18000c067  xor     r14d, r14d
0x18000c06a  test    rax, rax
0x18000c06d  jz      loc_18000C402
0x18000c073  lea     rdx, [rax+2]
0x18000c077  movzx   eax, word ptr [rdx]
0x18000c07a  test    ax, ax
0x18000c07d  jz      short loc_18000C089
0x18000c07f  cmp     ax, 2Eh ; '.'
0x18000c083  jnz     loc_18000C1E6
0x18000c089  cmp     word ptr [rdx], 2Eh ; '.'
0x18000c08d  jnz     loc_18000C40C
0x18000c093  add     rdx, 2
0x18000c097  movzx   eax, word ptr [rdx]
0x18000c09a  test    ax, ax
0x18000c09d  jz      short loc_18000C0C0
0x18000c09f  cmp     ax, 2Eh ; '.'
0x18000c0a3  jz      short loc_18000C0C0
0x18000c0a5  lea     r15d, [r15+r15*4]
0x18000c0a9  movzx   eax, ax
0x18000c0ac  lea     r15d, [r15-18h]
0x18000c0b0  lea     r15d, [rax+r15*2]
0x18000c0b4  add     rdx, 2
0x18000c0b8  movzx   eax, word ptr [rdx]
0x18000c0bb  test    ax, ax
0x18000c0be  jnz     short loc_18000C09F
0x18000c0c0  cmp     word ptr [rdx], 2Eh ; '.'
0x18000c0c4  jz      loc_18000C18F
0x18000c0ca  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000c0d0  mov     edi, 57h ; 'W'
0x18000c0d5  mov     edx, edi
0x18000c0d7  mov     rcx, rax
0x18000c0da  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000c0e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c0e7  cmp     rcx, rsi
0x18000c0ea  jnz     loc_18000C46A
0x18000c0f0  mov     rcx, rbx
0x18000c0f3  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000c0f9  nop
0x18000c0fa  test    edi, edi
0x18000c0fc  jnz     loc_18000C321
0x18000c102  mov     [rsp+2E8h+var_2B8], edi
0x18000c106  lea     rcx, [rbp+10h]; this
0x18000c10a  mov     [rsp+2E8h+var_2C0], r13; struct MemoryPage **
0x18000c10f  lea     rax, [rsp+2E8h+var_2B8]
0x18000c114  mov     [rsp+2E8h+var_2C8], rax; unsigned int *
0x18000c119  mov     rdi, [rsp+2E8h+var_2B0]
0x18000c11e  mov     r9, rdi; unsigned __int8 **
0x18000c121  mov     r8d, r15d; unsigned int
0x18000c124  mov     edx, r14d; unsigned int
0x18000c127  call    ?ReadBuffer@CVarObjHeap@@QEAAKKKPEAPEAEPEAKPEAPEAVMemoryPage@@@Z; CVarObjHeap::ReadBuffer(ulong,ulong,uchar * *,ulong *,MemoryPage * *)
0x18000c12c  mov     ebx, eax
0x18000c12e  test    eax, eax
0x18000c130  jz      short loc_18000C145
0x18000c132  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000c138  mov     edx, ebx
0x18000c13a  mov     rcx, rax
0x18000c13d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000c143  jmp     short loc_18000C153
0x18000c145  mov     ecx, [r12]
0x18000c149  cmp     [rsp+2E8h+var_2B8], ecx
0x18000c14d  jnz     loc_18000C480
0x18000c153  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c15a  cmp     rcx, rsi
0x18000c15d  jz      short loc_18000C169
0x18000c15f  test    byte ptr [rcx+1Ch], 1
0x18000c163  jnz     loc_18000C224
0x18000c169  mov     eax, ebx
0x18000c16b  mov     rcx, [rsp+2E8h+var_58]
0x18000c173  xor     rcx, rsp; StackCookie
0x18000c176  call    __security_check_cookie
0x18000c17b  add     rsp, 2A8h
0x18000c182  pop     r15
0x18000c184  pop     r14
0x18000c186  pop     r13
0x18000c188  pop     r12
0x18000c18a  pop     rdi
0x18000c18b  pop     rsi
0x18000c18c  pop     rbp
0x18000c18d  pop     rbx
0x18000c18e  retn
0x18000c18f  add     rdx, 2
0x18000c193  mov     dword ptr [r12], 0
0x18000c19b  movzx   eax, word ptr [rdx]
0x18000c19e  test    ax, ax
0x18000c1a1  jnz     short loc_18000C1C0
0x18000c1a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c1aa  cmp     rcx, rsi
0x18000c1ad  jz      short loc_18000C1B9
0x18000c1af  test    byte ptr [rcx+1Ch], 1
0x18000c1b3  jnz     loc_18000C24B
0x18000c1b9  xor     edi, edi
0x18000c1bb  jmp     loc_18000C0F0
0x18000c1c0  xor     ecx, ecx
0x18000c1c2  cmp     ax, 2Eh ; '.'
0x18000c1c6  jz      short loc_18000C1A3
0x18000c1c8  lea     ecx, [rcx+rcx*4]
0x18000c1cb  movzx   eax, ax
0x18000c1ce  lea     ecx, [rcx-18h]
0x18000c1d1  lea     ecx, [rax+rcx*2]
0x18000c1d4  mov     [r12], ecx
0x18000c1d8  add     rdx, 2
0x18000c1dc  movzx   eax, word ptr [rdx]
0x18000c1df  test    ax, ax
0x18000c1e2  jnz     short loc_18000C1C2
0x18000c1e4  jmp     short loc_18000C1A3
0x18000c1e6  lea     r14d, [r14+r14*4]
0x18000c1ea  movzx   eax, ax
0x18000c1ed  lea     r14d, [r14-18h]
0x18000c1f1  lea     r14d, [rax+r14*2]
0x18000c1f5  add     rdx, 2
0x18000c1f9  movzx   eax, word ptr [rdx]
0x18000c1fc  test    ax, ax
0x18000c1ff  jz      loc_18000C089
0x18000c205  jmp     loc_18000C07F
0x18000c20a  cmp     edi, 2
0x18000c20d  jnz     loc_18000C369
0x18000c213  mov     rcx, rbx
0x18000c216  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000c21c  nop
0x18000c21d  mov     eax, edi
0x18000c21f  jmp     loc_18000C16B
0x18000c224  cmp     byte ptr [rcx+19h], 2
0x18000c228  jb      loc_18000C169
0x18000c22e  mov     edx, 2Ch ; ','
0x18000c233  mov     r9d, ebx
0x18000c236  lea     r8, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids
0x18000c23d  mov     rcx, [rcx+10h]
0x18000c241  call    WPP_SF_d
0x18000c246  jmp     loc_18000C169
0x18000c24b  cmp     byte ptr [rcx+19h], 2
0x18000c24f  jb      loc_18000C1B9
0x18000c255  mov     edx, 15h
0x18000c25a  xor     r9d, r9d
0x18000c25d  lea     r8, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids
0x18000c264  mov     rcx, [rcx+10h]
0x18000c268  call    WPP_SF_d
0x18000c26d  jmp     loc_18000C1B9
0x18000c272  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000c278  mov     edx, 10DDh
0x18000c27d  mov     rcx, rax
0x18000c280  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000c286  lea     rsi, WPP_GLOBAL_Control
0x18000c28d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c294  cmp     rcx, rsi
0x18000c297  jz      short loc_18000C2C0
0x18000c299  test    byte ptr [rcx+1Ch], 1
0x18000c29d  jz      short loc_18000C2C0
0x18000c29f  cmp     byte ptr [rcx+19h], 2
0x18000c2a3  jb      short loc_18000C2C0
0x18000c2a5  mov     edx, 29h ; ')'
0x18000c2aa  mov     r9d, 10DDh
0x18000c2b0  lea     r8, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids
0x18000c2b7  mov     rcx, [rcx+10h]
0x18000c2bb  call    WPP_SF_d
0x18000c2c0  mov     eax, 10DDh
0x18000c2c5  jmp     loc_18000C16B
0x18000c2ca  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000c2d0  mov     edi, 0Eh
0x18000c2d5  mov     edx, edi
0x18000c2d7  mov     rcx, rax
0x18000c2da  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000c2e0  lea     rsi, WPP_GLOBAL_Control
0x18000c2e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c2ee  cmp     rcx, rsi
0x18000c2f1  jz      short loc_18000C318
0x18000c2f3  test    byte ptr [rcx+1Ch], 1
0x18000c2f7  jz      short loc_18000C318
0x18000c2f9  cmp     byte ptr [rcx+19h], 2
0x18000c2fd  jb      short loc_18000C318
0x18000c2ff  mov     edx, 11h
0x18000c304  mov     r9d, edi
0x18000c307  lea     r8, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids
0x18000c30e  mov     rcx, [rcx+10h]
0x18000c312  call    WPP_SF_d
0x18000c317  nop
0x18000c318  xor     ecx, ecx
0x18000c31a  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000c320  nop
0x18000c321  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000c327  mov     edx, edi
0x18000c329  mov     rcx, rax
0x18000c32c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000c332  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c339  cmp     rcx, rsi
0x18000c33c  jz      short loc_18000C362
0x18000c33e  test    byte ptr [rcx+1Ch], 1
0x18000c342  jz      short loc_18000C362
0x18000c344  cmp     byte ptr [rcx+19h], 2
0x18000c348  jb      short loc_18000C362
0x18000c34a  mov     edx, 2Ah ; '*'
0x18000c34f  mov     r9d, edi
0x18000c352  lea     r8, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids
0x18000c359  mov     rcx, [rcx+10h]
0x18000c35d  call    WPP_SF_d
0x18000c362  mov     eax, edi
0x18000c364  jmp     loc_18000C16B
0x18000c369  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000c36f  mov     edx, edi
0x18000c371  mov     rcx, rax
0x18000c374  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000c37a  lea     rsi, WPP_GLOBAL_Control
0x18000c381  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c388  cmp     rcx, rsi
0x18000c38b  jz      short loc_18000C3B1
0x18000c38d  test    byte ptr [rcx+1Ch], 1
0x18000c391  jz      short loc_18000C3B1
0x18000c393  cmp     byte ptr [rcx+19h], 2
0x18000c397  jb      short loc_18000C3B1
0x18000c399  mov     edx, 10h
0x18000c39e  mov     r9d, edi
0x18000c3a1  lea     r8, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids
0x18000c3a8  mov     rcx, [rcx+10h]
0x18000c3ac  call    WPP_SF_d
0x18000c3b1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000c3b7  mov     edx, edi
0x18000c3b9  mov     rcx, rax
0x18000c3bc  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000c3c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c3c9  cmp     rcx, rsi
0x18000c3cc  jz      short loc_18000C3F3
0x18000c3ce  test    byte ptr [rcx+1Ch], 1
0x18000c3d2  jz      short loc_18000C3F3
0x18000c3d4  cmp     byte ptr [rcx+19h], 2
0x18000c3d8  jb      short loc_18000C3F3
0x18000c3da  mov     edx, 12h
0x18000c3df  mov     r9d, edi
0x18000c3e2  lea     r8, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids
0x18000c3e9  mov     rcx, [rcx+10h]
0x18000c3ed  call    WPP_SF_d
0x18000c3f2  nop
0x18000c3f3  mov     rcx, rbx
0x18000c3f6  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000c3fc  nop
0x18000c3fd  jmp     loc_18000C321
  ... truncated ...
```
