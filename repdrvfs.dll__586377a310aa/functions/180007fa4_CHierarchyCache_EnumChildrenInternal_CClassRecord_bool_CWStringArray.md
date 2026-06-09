# CHierarchyCache::EnumChildrenInternal(CClassRecord *,bool,CWStringArray &)

- ea: `0x180007fa4`
- end: `0x1800080ae`
- name: `?EnumChildrenInternal@CHierarchyCache@@IEAAJPEAVCClassRecord@@_NAEAVCWStringArray@@@Z`
- size: `266`
- prototype: `__int64 __fastcall(CHierarchyCache *__hidden this, struct CClassRecord *, bool, struct CWStringArray *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007770`
- `0x180007fa4`

## callees

- `0x1800012b8`
- `0x180007fa4`

## import_xrefs

- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180007fc6`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180007fc6`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180007fe4`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180007fe4`
- `wbemcomn!GetMemLogObject` at `0x180008007`
- `wbemcomn!GetMemLogObject` at `0x18000804b`
- `wbemcomn!GetMemLogObject` at `0x180008007`
- `wbemcomn!GetMemLogObject` at `0x18000804b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180008017`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180008056`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180008017`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180008056`
- `wbemcomn!?Add@CWStringArray@@QEAAHPEBG@Z` at `0x180007ff4`
- `wbemcomn!?Add@CWStringArray@@QEAAHPEBG@Z` at `0x180007ff4`

## pseudocode

```c
__int64 __fastcall CHierarchyCache::EnumChildrenInternal(
        CHierarchyCache *this,
        struct CClassRecord *a2,
        bool a3,
        struct CWStringArray *a4)
{
  CFlexArray *v5; // rbp
  int i; // edi
  const unsigned __int16 **v10; // rbx
  CMemoryLog *v11; // rax
  unsigned int v12; // ebx
  CVarObjHeap *v13; // rcx
  CMemoryLog *MemLogObject; // rax
  __int64 v15; // rdx
  __int64 v16; // r9

  v5 = (struct CClassRecord *)((char *)a2 + 208);
  for ( i = 0; ; ++i )
  {
    if ( i >= CFlexArray::Size(v5) )
      return 0;
    v10 = (const unsigned __int16 **)CFlexArray::GetAt(v5, i);
    if ( (int)CWStringArray::Add(a4, v10[4]) < 0 )
      break;
    if ( a3 )
    {
      v12 = CHierarchyCache::EnumChildrenInternal(this, (struct CClassRecord *)v10, a3, a4);
      if ( (v12 & 0x80000000) != 0 )
      {
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, v12);
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v15 = 19;
          v16 = v12;
LABEL_17:
          WPP_SF_d(*((_QWORD *)v13 + 2), v15, WPP_73e6a18982e8318987457e2893328bf6_Traceguids, v16);
          return v12;
        }
        return v12;
      }
    }
  }
  v11 = GetMemLogObject();
  v12 = -2147217402;
  CMemoryLog::Write(v11, -2147217402);
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v15 = 18;
    v16 = 2147749894LL;
    goto LABEL_17;
  }
  return v12;
}

```

## disassembly

```asm
0x180007fa4  push    rbx
0x180007fa6  push    rbp
0x180007fa7  push    rsi
0x180007fa8  push    rdi
0x180007fa9  push    r14
0x180007fab  push    r15
0x180007fad  sub     rsp, 28h
0x180007fb1  mov     r14, r9
0x180007fb4  lea     rbp, [rdx+0D0h]
0x180007fbb  mov     sil, r8b
0x180007fbe  mov     r15, rcx
0x180007fc1  xor     edi, edi
0x180007fc3  mov     rcx, rbp
0x180007fc6  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x180007fcc  cmp     edi, eax
0x180007fce  jl      short loc_180007FDF
0x180007fd0  xor     eax, eax
0x180007fd2  add     rsp, 28h
0x180007fd6  pop     r15
0x180007fd8  pop     r14
0x180007fda  pop     rdi
0x180007fdb  pop     rsi
0x180007fdc  pop     rbp
0x180007fdd  pop     rbx
0x180007fde  retn
0x180007fdf  mov     edx, edi
0x180007fe1  mov     rcx, rbp
0x180007fe4  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x180007fea  mov     rcx, r14
0x180007fed  mov     rbx, rax
0x180007ff0  mov     rdx, [rax+20h]
0x180007ff4  call    cs:__imp_?Add@CWStringArray@@QEAAHPEBG@Z; CWStringArray::Add(ushort const *)
0x180007ffa  test    eax, eax
0x180007ffc  js      short loc_180008007
0x180007ffe  test    sil, sil
0x180008001  jnz     short loc_180008034
0x180008003  inc     edi
0x180008005  jmp     short loc_180007FC3
0x180008007  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000800d  mov     ebx, 80041006h
0x180008012  mov     rcx, rax
0x180008015  mov     edx, ebx
0x180008017  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000801d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008024  lea     rax, WPP_GLOBAL_Control
0x18000802b  cmp     rcx, rax
0x18000802e  jnz     short loc_180008085
0x180008030  mov     eax, ebx
0x180008032  jmp     short loc_180007FD2
0x180008034  mov     r9, r14; struct CWStringArray *
0x180008037  mov     r8b, sil; bool
0x18000803a  mov     rdx, rbx; struct CClassRecord *
0x18000803d  mov     rcx, r15; this
0x180008040  call    ?EnumChildrenInternal@CHierarchyCache@@IEAAJPEAVCClassRecord@@_NAEAVCWStringArray@@@Z; CHierarchyCache::EnumChildrenInternal(CClassRecord *,bool,CWStringArray &)
0x180008045  mov     ebx, eax
0x180008047  test    eax, eax
0x180008049  jns     short loc_180008003
0x18000804b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180008051  mov     rcx, rax
0x180008054  mov     edx, ebx
0x180008056  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000805c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008063  lea     rax, WPP_GLOBAL_Control
0x18000806a  cmp     rcx, rax
0x18000806d  jz      short loc_180008030
0x18000806f  test    byte ptr [rcx+1Ch], 1
0x180008073  jz      short loc_180008030
0x180008075  cmp     byte ptr [rcx+19h], 2
0x180008079  jb      short loc_180008030
0x18000807b  mov     edx, 13h
0x180008080  mov     r9d, ebx
0x180008083  jmp     short loc_18000809C
0x180008085  test    byte ptr [rcx+1Ch], 1
0x180008089  jz      short loc_180008030
0x18000808b  cmp     byte ptr [rcx+19h], 2
0x18000808f  jb      short loc_180008030
0x180008091  mov     edx, 12h
0x180008096  mov     r9d, 80041006h
0x18000809c  mov     rcx, [rcx+10h]
0x1800080a0  lea     r8, WPP_73e6a18982e8318987457e2893328bf6_Traceguids
0x1800080a7  call    WPP_SF_d
0x1800080ac  jmp     short loc_180008030
```
