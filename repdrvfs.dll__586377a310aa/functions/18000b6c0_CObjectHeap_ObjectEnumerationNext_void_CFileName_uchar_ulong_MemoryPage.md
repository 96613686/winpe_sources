# CObjectHeap::ObjectEnumerationNext(void *,CFileName &,uchar * *,ulong *,MemoryPage * *)

- ea: `0x18000b6c0`
- end: `0x18000bc01`
- name: `?ObjectEnumerationNext@CObjectHeap@@QEAAJPEAXAEAVCFileName@@PEAPEAEPEAKPEAPEAVMemoryPage@@@Z`
- size: `1345`
- prototype: `__int64 __usercall@<rax>(CObjectHeap *__hidden this@<rcx>, void *@<rdx>, struct CFileName *@<r8>, unsigned __int8 **@<r9>, unsigned int *, struct MemoryPage **)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000a9b0`
- `0x1800345c0`

## callees

- `0x1800012b8`
- `0x18000b6c0`
- `0x18000bc10`
- `0x180010fa0`
- `0x180022e40`
- `0x18003d184`

## import_xrefs

- `msvcrt!wcschr` at `0x18000b7b3`
- `msvcrt!wcschr` at `0x18000b7b3`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18000b702`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18000b702`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x18000b715`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x18000b715`
- `wbemcomn!?RemoveAt@CFlexArray@@QEAAHH@Z` at `0x18000b723`
- `wbemcomn!?RemoveAt@CFlexArray@@QEAAHH@Z` at `0x18000b723`
- `wbemcomn!GetMemLogObject` at `0x18000b818`
- `wbemcomn!GetMemLogObject` at `0x18000ba4e`
- `wbemcomn!GetMemLogObject` at `0x18000baa6`
- `wbemcomn!GetMemLogObject` at `0x18000bb35`
- `wbemcomn!GetMemLogObject` at `0x18000bb86`
- `wbemcomn!GetMemLogObject` at `0x18000bbe4`
- `wbemcomn!GetMemLogObject` at `0x18000b818`
- `wbemcomn!GetMemLogObject` at `0x18000ba4e`
- `wbemcomn!GetMemLogObject` at `0x18000baa6`
- `wbemcomn!GetMemLogObject` at `0x18000bb35`
- `wbemcomn!GetMemLogObject` at `0x18000bb86`
- `wbemcomn!GetMemLogObject` at `0x18000bbe4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000b828`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000ba5c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000bab6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000bb43`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000bb96`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000bbef`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000b828`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000ba5c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000bab6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000bb43`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000bb96`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000bbef`

## pseudocode

```c
__int64 __fastcall CObjectHeap::ObjectEnumerationNext(
        CObjectHeap *this,
        CFlexArray *a2,
        const wchar_t **a3,
        unsigned __int8 **a4,
        unsigned int *a5,
        struct MemoryPage **a6)
{
  _BYTE *v10; // rbx
  wchar_t *v11; // r8
  __int64 v12; // rdi
  __int64 v13; // rax
  _BYTE *i; // rcx
  unsigned int v15; // edx
  wchar_t *v16; // rax
  wchar_t *v17; // rdx
  unsigned int v18; // r15d
  wchar_t v19; // ax
  unsigned __int16 v20; // ax
  unsigned __int16 *v21; // rdx
  unsigned int v22; // ebx
  CMemoryLog *v23; // rax
  CVarObjHeap *v24; // rcx
  unsigned int Buffer; // ebx
  unsigned __int16 v26; // ax
  unsigned __int16 *v27; // rdx
  int v28; // r12d
  const wchar_t *v29; // rcx
  int v30; // r8d
  void *v31; // rdx
  __int64 v33; // rdx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v35; // rax
  CMemoryLog *v36; // rax
  CMemoryLog *v37; // rax
  CMemoryLog *v38; // rax

  if ( !*((_DWORD *)this + 2) )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, 4317);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids, 4317);
    }
    return 4317;
  }
  if ( (unsigned __int64)a2 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v37 = GetMemLogObject();
    Buffer = 87;
    CMemoryLog::Write(v37, 87);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_4468c7411f373aed0078c9b7f9420cb4_Traceguids, 87);
    }
    goto LABEL_35;
  }
  if ( !CFlexArray::Size(a2) )
  {
    Buffer = 18;
LABEL_35:
    if ( Buffer == 18 )
      return 18;
    v38 = GetMemLogObject();
    CMemoryLog::Write(v38, Buffer);
    goto LABEL_82;
  }
  v10 = *(_BYTE **)CFlexArray::operator[](a2, 0);
  CFlexArray::RemoveAt(a2, 0);
  v11 = (wchar_t *)*a3;
  v12 = -1;
  v13 = -1;
  do
    ++v13;
  while ( v10[v13] );
  for ( i = &v10[v13 - 1]; *(i - 1) != 92; --i )
  {
    if ( i <= v10 )
      break;
  }
  v15 = 0;
  if ( *i )
  {
    while ( v15 < 0x173 )
    {
      ++v15;
      *v11++ = (char)*i++;
      if ( !*i )
      {
        if ( v15 >= 0x173 )
          break;
        goto LABEL_13;
      }
    }
  }
  else
  {
LABEL_13:
    *v11 = 0;
  }
  if ( v10 )
    _BtrMemFree(v10);
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_4468c7411f373aed0078c9b7f9420cb4_Traceguids, 0);
  }
  v16 = wcschr(*a3, 0x2Eu);
  if ( !v16 )
    goto LABEL_60;
  v17 = v16 + 1;
  v18 = 0;
  v19 = v16[1];
  if ( v19 )
  {
    do
    {
      if ( v19 == 46 )
        break;
      ++v17;
      v18 = v19 + 2 * (5 * v18 - 24);
      v19 = *v17;
    }
    while ( *v17 );
  }
  if ( *v17 != 46 )
  {
    v35 = GetMemLogObject();
    CMemoryLog::Write(v35, 87);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_26;
    }
    v33 = 19;
LABEL_59:
    WPP_SF_d(*((_QWORD *)v24 + 2), v33, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids, 87);
LABEL_60:
    v24 = WPP_GLOBAL_Control;
LABEL_26:
    Buffer = 0;
    goto LABEL_37;
  }
  v20 = v17[1];
  v21 = v17 + 1;
  v22 = 0;
  if ( v20 )
  {
    do
    {
      if ( v20 == 46 )
        break;
      ++v21;
      v22 = v20 + 2 * (5 * v22 - 24);
      v20 = *v21;
    }
    while ( *v21 );
  }
  if ( *v21 != 46 )
  {
    v23 = GetMemLogObject();
    CMemoryLog::Write(v23, 87);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_26;
    }
    v33 = 20;
    goto LABEL_59;
  }
  v26 = v21[1];
  v27 = v21 + 1;
  v28 = 0;
  if ( v26 )
  {
    do
    {
      if ( v26 == 46 )
        break;
      ++v27;
      v28 = v26 + 2 * (5 * v28 - 24);
      v26 = *v27;
    }
    while ( *v27 );
  }
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids, 0);
  }
  v29 = *a3;
  v30 = 0;
  do
    ++v12;
  while ( v29[v12] );
  while ( 1 )
  {
    while ( v29[(int)v12 - 1] != 46 )
      LODWORD(v12) = v12 - 1;
    if ( ++v30 == 3 )
      break;
    LODWORD(v12) = v12 - 1;
  }
  v29[(int)v12 - 1] = 0;
  *a5 = 0;
  Buffer = CVarObjHeap::ReadBuffer((CObjectHeap *)((char *)this + 16), v18, v22, a4, a5, a6);
  if ( Buffer )
    goto LABEL_35;
  if ( *a5 == v28 )
  {
LABEL_82:
    v24 = WPP_GLOBAL_Control;
LABEL_37:
    if ( v24 != (CVarObjHeap *)&WPP_GLOBAL_Control && (*((_BYTE *)v24 + 28) & 1) != 0 && *((_BYTE *)v24 + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)v24 + 2), 62, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids, Buffer);
    return Buffer;
  }
  CObjectHeap::ObjectEnumerationFree(this, v31, *a4, *a6);
  *a4 = 0;
  *a6 = 0;
  *a5 = 0;
  CRepositoryCorruption::SetRepositoryCorrupted(3, 0, 0);
  v36 = GetMemLogObject();
  CMemoryLog::Write(v36, 1358);
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids, 1358);
  }
  return 1358;
}

```

## disassembly

```asm
0x18000b6c0  push    rbp
0x18000b6c2  push    rsi
0x18000b6c3  push    rdi
0x18000b6c4  push    r13
0x18000b6c6  push    r14
0x18000b6c8  sub     rsp, 30h
0x18000b6cc  cmp     dword ptr [rcx+8], 0
0x18000b6d0  mov     r13, r9
0x18000b6d3  mov     r14, r8
0x18000b6d6  mov     rdi, rdx
0x18000b6d9  mov     rbp, rcx
0x18000b6dc  jz      loc_18000BA4E
0x18000b6e2  mov     [rsp+58h+arg_0], rbx
0x18000b6e7  lea     rax, [rdx-1]
0x18000b6eb  mov     [rsp+58h+arg_8], r12
0x18000b6f0  mov     [rsp+58h+arg_10], r15
0x18000b6f5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b6f9  ja      loc_18000BB86
0x18000b6ff  mov     rcx, rdx
0x18000b702  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x18000b708  test    eax, eax
0x18000b70a  jz      loc_18000B9E8
0x18000b710  xor     edx, edx
0x18000b712  mov     rcx, rdi
0x18000b715  call    cs:__imp_??ACFlexArray@@QEAAAEAPEAXH@Z; CFlexArray::operator[](int)
0x18000b71b  xor     edx, edx
0x18000b71d  mov     rcx, rdi
0x18000b720  mov     rbx, [rax]
0x18000b723  call    cs:__imp_?RemoveAt@CFlexArray@@QEAAHH@Z; CFlexArray::RemoveAt(int)
0x18000b729  mov     r8, [r14]
0x18000b72c  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18000b733  mov     rax, rdi
0x18000b736  inc     rax
0x18000b739  cmp     byte ptr [rbx+rax], 0
0x18000b73d  jnz     short loc_18000B736
0x18000b73f  lea     rcx, [rbx-1]
0x18000b743  add     rcx, rax
0x18000b746  cmp     byte ptr [rcx-1], 5Ch ; '\'
0x18000b74a  jz      short loc_18000B75A
0x18000b74c  cmp     rcx, rbx
0x18000b74f  jbe     short loc_18000B75A
0x18000b751  dec     rcx
0x18000b754  cmp     byte ptr [rcx-1], 5Ch ; '\'
0x18000b758  jnz     short loc_18000B74C
0x18000b75a  xor     edx, edx
0x18000b75c  cmp     [rcx], dl
0x18000b75e  jz      short loc_18000B785
0x18000b760  cmp     edx, 173h
0x18000b766  jnb     short loc_18000B78B
0x18000b768  movsx   eax, byte ptr [rcx]
0x18000b76b  inc     edx
0x18000b76d  mov     [r8], ax
0x18000b771  inc     rcx
0x18000b774  add     r8, 2
0x18000b778  cmp     byte ptr [rcx], 0
0x18000b77b  jnz     short loc_18000B760
0x18000b77d  cmp     edx, 173h
0x18000b783  jnb     short loc_18000B78B
0x18000b785  xor     eax, eax
0x18000b787  mov     [r8], ax
0x18000b78b  test    rbx, rbx
0x18000b78e  jnz     loc_18000B9DB
0x18000b794  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b79b  lea     rsi, WPP_GLOBAL_Control
0x18000b7a2  cmp     rcx, rsi
0x18000b7a5  jnz     loc_18000B9AA
0x18000b7ab  mov     rcx, [r14]; Str
0x18000b7ae  mov     edx, 2Eh ; '.'; Ch
0x18000b7b3  call    cs:__imp_wcschr
0x18000b7b9  test    rax, rax
0x18000b7bc  jz      loc_18000BA42
0x18000b7c2  lea     rdx, [rax+2]
0x18000b7c6  xor     r15d, r15d
0x18000b7c9  movzx   eax, word ptr [rdx]
0x18000b7cc  test    ax, ax
0x18000b7cf  jz      short loc_18000B7DB
0x18000b7d1  cmp     ax, 2Eh ; '.'
0x18000b7d5  jnz     loc_18000B97F
0x18000b7db  cmp     word ptr [rdx], 2Eh ; '.'
0x18000b7df  jnz     loc_18000BAA6
0x18000b7e5  movzx   eax, word ptr [rdx+2]
0x18000b7e9  add     rdx, 2
0x18000b7ed  xor     ebx, ebx
0x18000b7ef  test    ax, ax
0x18000b7f2  jz      short loc_18000B812
0x18000b7f4  cmp     ax, 2Eh ; '.'
0x18000b7f8  jz      short loc_18000B812
0x18000b7fa  movzx   eax, ax
0x18000b7fd  lea     ebx, [rbx+rbx*4]
0x18000b800  add     rdx, 2
0x18000b804  lea     ebx, [rbx-18h]
0x18000b807  lea     ebx, [rax+rbx*2]
0x18000b80a  movzx   eax, word ptr [rdx]
0x18000b80d  test    ax, ax
0x18000b810  jnz     short loc_18000B7F4
0x18000b812  cmp     word ptr [rdx], 2Eh ; '.'
0x18000b816  jz      short loc_18000B845
0x18000b818  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000b81e  mov     ebx, 57h ; 'W'
0x18000b823  mov     rcx, rax
0x18000b826  mov     edx, ebx
0x18000b828  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000b82e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b835  cmp     rcx, rsi
0x18000b838  jnz     loc_18000BAEA
0x18000b83e  xor     ebx, ebx
0x18000b840  jmp     loc_18000B8EE
0x18000b845  movzx   eax, word ptr [rdx+2]
0x18000b849  add     rdx, 2
0x18000b84d  xor     r12d, r12d
0x18000b850  test    ax, ax
0x18000b853  jnz     loc_18000B954
0x18000b859  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b860  cmp     rcx, rsi
0x18000b863  jz      short loc_18000B86F
0x18000b865  test    byte ptr [rcx+1Ch], 1
0x18000b869  jnz     loc_18000B9F9
0x18000b86f  mov     rcx, [r14]
0x18000b872  xor     r9d, r9d
0x18000b875  mov     r8d, r9d
0x18000b878  nop     dword ptr [rax+rax+00000000h]
0x18000b880  inc     rdi
0x18000b883  cmp     [rcx+rdi*2], r8w
0x18000b888  jnz     short loc_18000B880
0x18000b88a  movsxd  rax, edi
0x18000b88d  cmp     word ptr [rcx+rax*2-2], 2Eh ; '.'
0x18000b893  lea     rdx, [rcx+rax*2]
0x18000b897  jz      short loc_18000B910
0x18000b899  dec     edi
0x18000b89b  cmp     r8d, 3
0x18000b89f  jnz     short loc_18000B88A
0x18000b8a1  mov     rdi, [rsp+58h+arg_20]
0x18000b8a9  lea     rcx, [rbp+10h]; this
0x18000b8ad  mov     r14, [rsp+58h+arg_28]
0x18000b8b5  mov     r8d, ebx; unsigned int
0x18000b8b8  mov     [rsp+58h+var_30], r14; struct MemoryPage **
0x18000b8bd  mov     edx, r15d; unsigned int
0x18000b8c0  mov     [rsp+58h+var_38], rdi; unsigned int *
0x18000b8c5  mov     [rdi], r9d
0x18000b8c8  mov     r9, r13; unsigned __int8 **
0x18000b8cb  call    ?ReadBuffer@CVarObjHeap@@QEAAKKKPEAPEAEPEAKPEAPEAVMemoryPage@@@Z; CVarObjHeap::ReadBuffer(ulong,ulong,uchar * *,ulong *,MemoryPage * *)
0x18000b8d0  mov     ebx, eax
0x18000b8d2  test    eax, eax
0x18000b8d4  jz      loc_18000BAF9
0x18000b8da  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b8e1  cmp     ebx, 12h
0x18000b8e4  jz      short loc_18000B927
0x18000b8e6  test    ebx, ebx
0x18000b8e8  jnz     loc_18000BBE4
0x18000b8ee  cmp     rcx, rsi
0x18000b8f1  jnz     short loc_18000B92E
0x18000b8f3  mov     eax, ebx
0x18000b8f5  mov     r12, [rsp+58h+arg_8]
0x18000b8fa  mov     rbx, [rsp+58h+arg_0]
0x18000b8ff  mov     r15, [rsp+58h+arg_10]
0x18000b904  add     rsp, 30h
0x18000b908  pop     r14
0x18000b90a  pop     r13
0x18000b90c  pop     rdi
0x18000b90d  pop     rsi
0x18000b90e  pop     rbp
0x18000b90f  retn
0x18000b910  inc     r8d
0x18000b913  cmp     r8d, 3
0x18000b917  jnz     loc_18000B9A3
0x18000b91d  mov     [rdx-2], r9w
0x18000b922  jmp     loc_18000B8A1
0x18000b927  mov     eax, 12h
0x18000b92c  jmp     short loc_18000B8F5
0x18000b92e  test    byte ptr [rcx+1Ch], 1
0x18000b932  jz      short loc_18000B8F3
0x18000b934  cmp     byte ptr [rcx+19h], 2
0x18000b938  jb      short loc_18000B8F3
0x18000b93a  mov     rcx, [rcx+10h]
0x18000b93e  lea     r8, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids
0x18000b945  mov     edx, 3Eh ; '>'
0x18000b94a  mov     r9d, ebx
0x18000b94d  call    WPP_SF_d
0x18000b952  jmp     short loc_18000B8F3
0x18000b954  cmp     ax, 2Eh ; '.'
0x18000b958  jz      loc_18000B859
0x18000b95e  movzx   eax, ax
0x18000b961  lea     r12d, [r12+r12*4]
0x18000b965  add     rdx, 2
0x18000b969  lea     r12d, [r12-18h]
0x18000b96e  lea     r12d, [rax+r12*2]
0x18000b972  movzx   eax, word ptr [rdx]
0x18000b975  test    ax, ax
0x18000b978  jnz     short loc_18000B954
0x18000b97a  jmp     loc_18000B859
0x18000b97f  movzx   eax, ax
0x18000b982  lea     r15d, [r15+r15*4]
0x18000b986  add     rdx, 2
0x18000b98a  lea     r15d, [r15-18h]
0x18000b98e  lea     r15d, [rax+r15*2]
0x18000b992  movzx   eax, word ptr [rdx]
0x18000b995  test    ax, ax
0x18000b998  jz      loc_18000B7DB
0x18000b99e  jmp     loc_18000B7D1
0x18000b9a3  dec     edi
0x18000b9a5  jmp     loc_18000B88A
0x18000b9aa  test    byte ptr [rcx+1Ch], 1
0x18000b9ae  jz      loc_18000B7AB
0x18000b9b4  cmp     byte ptr [rcx+19h], 2
0x18000b9b8  jb      loc_18000B7AB
0x18000b9be  mov     rcx, [rcx+10h]
0x18000b9c2  lea     r8, WPP_4468c7411f373aed0078c9b7f9420cb4_Traceguids
0x18000b9c9  mov     edx, 1Fh
0x18000b9ce  xor     r9d, r9d
0x18000b9d1  call    WPP_SF_d
0x18000b9d6  jmp     loc_18000B7AB
0x18000b9db  mov     rcx, rbx; void *
0x18000b9de  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x18000b9e3  jmp     loc_18000B794
0x18000b9e8  mov     ebx, 12h
0x18000b9ed  lea     rsi, WPP_GLOBAL_Control
0x18000b9f4  jmp     loc_18000B8DA
0x18000b9f9  cmp     byte ptr [rcx+19h], 2
0x18000b9fd  jb      loc_18000B86F
0x18000ba03  mov     rcx, [rcx+10h]
0x18000ba07  lea     r8, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids
0x18000ba0e  mov     edx, 15h
0x18000ba13  xor     r9d, r9d
0x18000ba16  call    WPP_SF_d
0x18000ba1b  jmp     loc_18000B86F
0x18000ba20  cmp     byte ptr [rcx+19h], 2
0x18000ba24  jb      loc_18000B83E
0x18000ba2a  mov     edx, 14h
0x18000ba2f  mov     rcx, [rcx+10h]
0x18000ba33  lea     r8, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids
0x18000ba3a  mov     r9d, ebx
0x18000ba3d  call    WPP_SF_d
0x18000ba42  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ba49  jmp     loc_18000B83E
0x18000ba4e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000ba54  mov     rcx, rax
0x18000ba57  mov     edx, 10DDh
0x18000ba5c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000ba62  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ba69  lea     rsi, WPP_GLOBAL_Control
0x18000ba70  cmp     rcx, rsi
0x18000ba73  jz      short loc_18000BA9C
0x18000ba75  test    byte ptr [rcx+1Ch], 1
0x18000ba79  jz      short loc_18000BA9C
0x18000ba7b  cmp     byte ptr [rcx+19h], 2
0x18000ba7f  jb      short loc_18000BA9C
0x18000ba81  mov     rcx, [rcx+10h]
0x18000ba85  lea     r8, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids
0x18000ba8c  mov     edx, 3Ch ; '<'
0x18000ba91  mov     r9d, 10DDh
0x18000ba97  call    WPP_SF_d
0x18000ba9c  mov     eax, 10DDh
0x18000baa1  jmp     loc_18000B904
0x18000baa6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000baac  mov     ebx, 57h ; 'W'
0x18000bab1  mov     rcx, rax
0x18000bab4  mov     edx, ebx
0x18000bab6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000babc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bac3  cmp     rcx, rsi
0x18000bac6  jz      loc_18000B83E
0x18000bacc  test    byte ptr [rcx+1Ch], 1
0x18000bad0  jz      loc_18000B83E
0x18000bad6  cmp     byte ptr [rcx+19h], 2
0x18000bada  jb      loc_18000B83E
0x18000bae0  mov     edx, 13h
0x18000bae5  jmp     loc_18000BA2F
0x18000baea  test    byte ptr [rcx+1Ch], 1
0x18000baee  jz      loc_18000B83E
0x18000baf4  jmp     loc_18000BA20
0x18000baf9  cmp     [rdi], r12d
0x18000bafc  jz      loc_18000BBF5
0x18000bb02  mov     r9, [r14]; struct MemoryPage *
0x18000bb05  mov     rcx, rbp; this
0x18000bb08  mov     r8, [r13+0]; unsigned __int8 *
0x18000bb0c  call    ?ObjectEnumerationFree@CObjectHeap@@QEAAJPEAXPEAEPEAVMemoryPage@@@Z; CObjectHeap::ObjectEnumerationFree(void *,uchar *,MemoryPage *)
0x18000bb11  mov     qword ptr [r13+0], 0
0x18000bb19  xor     r8d, r8d; unsigned int
0x18000bb1c  mov     qword ptr [r14], 0
0x18000bb23  xor     edx, edx; bool
0x18000bb25  mov     ecx, 3; int
0x18000bb2a  mov     dword ptr [rdi], 0
0x18000bb30  call    ?SetRepositoryCorrupted@CRepositoryCorruption@@SAJJ_NK@Z; CRepositoryCorruption::SetRepositoryCorrupted(long,bool,ulong)
0x18000bb35  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000bb3b  mov     rcx, rax
0x18000bb3e  mov     edx, 54Eh
0x18000bb43  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000bb49  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bb50  cmp     rcx, rsi
0x18000bb53  jz      short loc_18000BB7C
0x18000bb55  test    byte ptr [rcx+1Ch], 1
0x18000bb59  jz      short loc_18000BB7C
0x18000bb5b  cmp     byte ptr [rcx+19h], 2
0x18000bb5f  jb      short loc_18000BB7C
0x18000bb61  mov     rcx, [rcx+10h]
0x18000bb65  lea     r8, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids
0x18000bb6c  mov     edx, 3Dh ; '='
0x18000bb71  mov     r9d, 54Eh
0x18000bb77  call    WPP_SF_d
0x18000bb7c  mov     eax, 54Eh
  ... truncated ...
```
