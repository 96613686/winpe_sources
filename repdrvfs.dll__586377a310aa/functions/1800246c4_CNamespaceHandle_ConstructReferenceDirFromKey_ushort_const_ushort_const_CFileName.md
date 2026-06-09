# CNamespaceHandle::ConstructReferenceDirFromKey(ushort const *,ushort const *,CFileName &)

- ea: `0x1800246c4`
- end: `0x18002484d`
- name: `?ConstructReferenceDirFromKey@CNamespaceHandle@@IEAAJPEBG0AEAVCFileName@@@Z`
- size: `393`
- prototype: `__int64 __fastcall(__int16 **this, const unsigned __int16 *, const unsigned __int16 *, struct CFileName *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002435c`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x180006960`
- `0x1800080c0`
- `0x1800246c4`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180024725`
- `wbemcomn!GetMemLogObject` at `0x1800247f6`
- `wbemcomn!GetMemLogObject` at `0x180024725`
- `wbemcomn!GetMemLogObject` at `0x1800247f6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024730`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024806`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024730`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024806`

## pseudocode

```c
__int64 __fastcall CNamespaceHandle::ConstructReferenceDirFromKey(
        __int16 **this,
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
  __int64 v15; // r8
  unsigned __int64 v16; // r9
  _WORD *v17; // rdx
  __int64 v18; // rax
  const wchar_t *v19; // rcx
  _WORD *v20; // rcx
  CMemoryLog *v21; // rax

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 226, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
  }
  v8 = CNamespaceHandle::ConstructKeyRootDirFromClass(this, a4, a2);
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
    v11 = 227;
    v12 = v8;
LABEL_10:
    WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, v12);
    return v8;
  }
  v14 = *(_QWORD *)a4;
  v15 = -1;
  do
    ++v15;
  while ( *(_WORD *)(v14 + 2 * v15) );
  v16 = (unsigned int)(371 - v15);
  if ( (_DWORD)v15 != 371 )
  {
    v17 = (_WORD *)(v14 + 2LL * (int)v15);
    if ( v16 <= 0x7FFFFFFF )
    {
      v18 = 2147483646;
      v19 = L"\\IR_";
      do
      {
        if ( !v18 )
          break;
        if ( !*v19 )
          break;
        *v17++ = *v19++;
        --v18;
        --v16;
      }
      while ( v16 );
      v20 = v17 - 1;
      if ( v16 )
        v20 = v17;
      *v20 = 0;
    }
    else
    {
      *v17 = 0;
    }
  }
  if ( !A51Hash(a3, (unsigned __int16 *)(*(_QWORD *)a4 + 2LL * ((int)v15 + 4))) )
  {
    v21 = GetMemLogObject();
    v8 = -2147217402;
    CMemoryLog::Write(v21, -2147217402);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v8;
    }
    v11 = 228;
    v12 = 2147749894LL;
    goto LABEL_10;
  }
  return 0;
}

```

## disassembly

```asm
0x1800246c4  push    rbx
0x1800246c6  push    rbp
0x1800246c7  push    rsi
0x1800246c8  push    rdi
0x1800246c9  push    r15
0x1800246cb  sub     rsp, 20h
0x1800246cf  mov     rsi, r9
0x1800246d2  mov     rbp, r8
0x1800246d5  mov     rbx, rdx
0x1800246d8  mov     rdi, rcx
0x1800246db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800246e2  lea     r15, WPP_GLOBAL_Control
0x1800246e9  cmp     rcx, r15
0x1800246ec  jz      short loc_18002470F
0x1800246ee  test    byte ptr [rcx+1Ch], 1
0x1800246f2  jz      short loc_18002470F
0x1800246f4  cmp     byte ptr [rcx+19h], 5
0x1800246f8  jb      short loc_18002470F
0x1800246fa  mov     rcx, [rcx+10h]
0x1800246fe  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180024705  mov     edx, 0E2h
0x18002470a  call    WPP_SF_
0x18002470f  mov     r8, rbx; unsigned __int16 *
0x180024712  mov     rdx, rsi; struct CFileName *
0x180024715  mov     rcx, rdi; this
0x180024718  call    ?ConstructKeyRootDirFromClass@CNamespaceHandle@@IEAAJAEAVCFileName@@PEBG@Z; CNamespaceHandle::ConstructKeyRootDirFromClass(CFileName &,ushort const *)
0x18002471d  xor     edi, edi
0x18002471f  mov     ebx, eax
0x180024721  test    eax, eax
0x180024723  jns     short loc_18002476D
0x180024725  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002472b  mov     rcx, rax
0x18002472e  mov     edx, ebx
0x180024730  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180024736  mov     rcx, cs:WPP_GLOBAL_Control
0x18002473d  cmp     rcx, r15
0x180024740  jz      short loc_180024766
0x180024742  test    byte ptr [rcx+1Ch], 1
0x180024746  jz      short loc_180024766
0x180024748  cmp     byte ptr [rcx+19h], 2
0x18002474c  jb      short loc_180024766
0x18002474e  mov     edx, 0E3h
0x180024753  mov     r9d, ebx
0x180024756  mov     rcx, [rcx+10h]
0x18002475a  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180024761  call    WPP_SF_d
0x180024766  mov     eax, ebx
0x180024768  jmp     loc_180024842
0x18002476d  mov     rcx, [rsi]
0x180024770  or      r8, 0FFFFFFFFFFFFFFFFh
0x180024774  inc     r8
0x180024777  cmp     [rcx+r8*2], di
0x18002477c  jnz     short loc_180024774
0x18002477e  mov     r9d, 173h
0x180024784  sub     r9d, r8d
0x180024787  jz      short loc_1800247DC
0x180024789  movsxd  rax, r8d
0x18002478c  lea     rdx, [rcx+rax*2]
0x180024790  cmp     r9, 7FFFFFFFh
0x180024797  jbe     short loc_18002479E
0x180024799  mov     [rdx], di
0x18002479c  jmp     short loc_1800247DC
0x18002479e  mov     eax, 7FFFFFFEh
0x1800247a3  lea     rcx, aIr_0; "\\IR_"
0x1800247aa  test    rax, rax
0x1800247ad  jz      short loc_1800247CE
0x1800247af  movzx   r10d, word ptr [rcx]
0x1800247b3  test    r10w, r10w
0x1800247b7  jz      short loc_1800247CE
0x1800247b9  mov     [rdx], r10w
0x1800247bd  add     rcx, 2
0x1800247c1  add     rdx, 2
0x1800247c5  dec     rax
0x1800247c8  sub     r9, 1
0x1800247cc  jnz     short loc_1800247AA
0x1800247ce  test    r9, r9
0x1800247d1  lea     rcx, [rdx-2]
0x1800247d5  cmovnz  rcx, rdx
0x1800247d9  mov     [rcx], di
0x1800247dc  lea     eax, [r8+4]
0x1800247e0  movsxd  rcx, eax
0x1800247e3  mov     rax, [rsi]
0x1800247e6  lea     rdx, [rax+rcx*2]; unsigned __int16 *
0x1800247ea  mov     rcx, rbp; unsigned __int16 *
0x1800247ed  call    ?A51Hash@@YA_NPEBGPEAG@Z; A51Hash(ushort const *,ushort *)
0x1800247f2  test    al, al
0x1800247f4  jnz     short loc_180024840
0x1800247f6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800247fc  mov     ebx, 80041006h
0x180024801  mov     rcx, rax
0x180024804  mov     edx, ebx
0x180024806  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002480c  mov     rcx, cs:WPP_GLOBAL_Control
0x180024813  cmp     rcx, r15
0x180024816  jz      loc_180024766
0x18002481c  test    byte ptr [rcx+1Ch], 1
0x180024820  jz      loc_180024766
0x180024826  cmp     byte ptr [rcx+19h], 2
0x18002482a  jb      loc_180024766
0x180024830  mov     edx, 0E4h
0x180024835  mov     r9d, 80041006h
0x18002483b  jmp     loc_180024756
0x180024840  xor     eax, eax
0x180024842  add     rsp, 20h
0x180024846  pop     r15
0x180024848  pop     rdi
0x180024849  pop     rsi
0x18002484a  pop     rbp
0x18002484b  pop     rbx
0x18002484c  retn
```
