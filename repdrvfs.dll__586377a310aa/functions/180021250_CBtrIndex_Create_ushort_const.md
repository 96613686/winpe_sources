# CBtrIndex::Create(ushort const *)

- ea: `0x180021250`
- end: `0x1800213c0`
- name: `?Create@CBtrIndex@@QEAAJPEBG@Z`
- size: `368`
- prototype: `__int64 __fastcall(CBtrIndex *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800203a0`
- `0x180021168`
- `0x180036dd8`

## callees

- `0x1800012b8`
- `0x180021250`
- `0x1800213c8`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180021282`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180021282`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180021308`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180021308`
- `wbemcomn!GetMemLogObject` at `0x180021295`
- `wbemcomn!GetMemLogObject` at `0x18002131f`
- `wbemcomn!GetMemLogObject` at `0x180021295`
- `wbemcomn!GetMemLogObject` at `0x18002131f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800212a3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002132d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800212a3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002132d`

## pseudocode

```c
__int64 __fastcall CBtrIndex::Create(CBtrIndex *this, const unsigned __int16 *a2)
{
  const unsigned __int16 *v2; // rbx
  __int64 v4; // rcx
  char *v5; // rax
  unsigned int v6; // r8d
  char *v7; // rdi
  CMemoryLog *MemLogObject; // rax
  char *v10; // rcx
  unsigned __int16 i; // dx
  CMemoryLog *v12; // rax
  unsigned int inserted; // ebx
  char *v14; // [rsp+40h] [rbp+18h]

  v2 = a2;
  if ( a2 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a2[v4] );
    v5 = (char *)CWin32DefaultArena::WbemMemAlloc(v4 + 1);
    v7 = v5;
    v14 = v5;
    if ( v5 )
    {
      v10 = v5;
      for ( i = *v2; *v2; LOBYTE(i) = *v2 )
      {
        ++v2;
        *v10++ = i;
      }
      *v10 = 0;
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        inserted = CBTree::InsertKey((CBtrIndex *)((char *)this + 8), v5, v6);
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_type(0, &CX_MemoryException `RTTI Type Descriptor', 0) )
        {
          inserted = 14;
          v7 = v14;
          __eh34_try_continuation(0, &CX_MemoryException `RTTI Type Descriptor', &loc_1800213AB);
        }
      }
      CWin32DefaultArena::WbemMemFree(v7);
      if ( inserted == 183 )
        return 0;
      return inserted;
    }
    else
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, 8);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_4468c7411f373aed0078c9b7f9420cb4_Traceguids, 8);
      }
      return 8;
    }
  }
  else
  {
    v12 = GetMemLogObject();
    CMemoryLog::Write(v12, 87);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_4468c7411f373aed0078c9b7f9420cb4_Traceguids, 87);
    }
    return 87;
  }
}

```

## disassembly

```asm
0x180021250  mov     [rsp+arg_0], rbx
0x180021255  mov     [rsp+arg_18], rsi
0x18002125a  push    rdi
0x18002125b  sub     rsp, 20h
0x18002125f  mov     rbx, rdx
0x180021262  mov     rsi, rcx
0x180021265  test    rdx, rdx
0x180021268  jz      loc_18002131F
0x18002126e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180021275  inc     rcx
0x180021278  cmp     word ptr [rdx+rcx*2], 0
0x18002127d  jnz     short loc_180021275
0x18002127f  inc     rcx
0x180021282  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180021288  mov     rdi, rax
0x18002128b  mov     [rsp+28h+arg_10], rax
0x180021290  test    rax, rax
0x180021293  jnz     short loc_1800212D5
0x180021295  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002129b  mov     edx, 8
0x1800212a0  mov     rcx, rax
0x1800212a3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800212a9  lea     rax, WPP_GLOBAL_Control
0x1800212b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800212b7  cmp     rcx, rax
0x1800212ba  jnz     loc_180021377
0x1800212c0  mov     eax, 8
0x1800212c5  mov     rbx, [rsp+28h+arg_0]
0x1800212ca  mov     rsi, [rsp+28h+arg_18]
0x1800212cf  add     rsp, 20h
0x1800212d3  pop     rdi
0x1800212d4  retn
0x1800212d5  mov     rcx, rdi
0x1800212d8  movzx   edx, word ptr [rbx]
0x1800212db  test    dx, dx
0x1800212de  jz      short loc_1800212F4
0x1800212e0  lea     rbx, [rbx+2]
0x1800212e4  mov     [rcx], dl
0x1800212e6  inc     rcx
0x1800212e9  movzx   eax, word ptr [rbx]
0x1800212ec  movzx   edx, al
0x1800212ef  test    ax, ax
0x1800212f2  jnz     short loc_1800212E0
0x1800212f4  mov     byte ptr [rcx], 0
0x1800212f7  lea     rcx, [rsi+8]; this
0x1800212fb  mov     rdx, rdi; char *
0x1800212fe  call    ?InsertKey@CBTree@@QEAAKPEADK@Z; CBTree::InsertKey(char *,ulong)
0x180021303  mov     ebx, eax
0x180021305  mov     rcx, rdi
0x180021308  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18002130e  nop
0x18002130f  cmp     ebx, 0B7h
0x180021315  jz      loc_1800213B9
0x18002131b  mov     eax, ebx
0x18002131d  jmp     short loc_1800212C5
0x18002131f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180021325  mov     edx, 57h ; 'W'
0x18002132a  mov     rcx, rax
0x18002132d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180021333  lea     rax, WPP_GLOBAL_Control
0x18002133a  mov     rcx, cs:WPP_GLOBAL_Control
0x180021341  cmp     rcx, rax
0x180021344  jz      short loc_18002136D
0x180021346  test    byte ptr [rcx+1Ch], 1
0x18002134a  jz      short loc_18002136D
0x18002134c  cmp     byte ptr [rcx+19h], 2
0x180021350  jb      short loc_18002136D
0x180021352  mov     edx, 0Eh
0x180021357  mov     r9d, 57h ; 'W'
0x18002135d  lea     r8, WPP_4468c7411f373aed0078c9b7f9420cb4_Traceguids
0x180021364  mov     rcx, [rcx+10h]
0x180021368  call    WPP_SF_d
0x18002136d  mov     eax, 57h ; 'W'
0x180021372  jmp     loc_1800212C5
0x180021377  test    byte ptr [rcx+1Ch], 1
0x18002137b  jz      loc_1800212C0
0x180021381  cmp     byte ptr [rcx+19h], 2
0x180021385  jb      loc_1800212C0
0x18002138b  mov     edx, 0Fh
0x180021390  mov     r9d, 8
0x180021396  lea     r8, WPP_4468c7411f373aed0078c9b7f9420cb4_Traceguids
0x18002139d  mov     rcx, [rcx+10h]
0x1800213a1  call    WPP_SF_d
0x1800213a6  jmp     loc_1800212C0
0x1800213ab  mov     ebx, [rsp+28h+arg_8]
0x1800213af  mov     rdi, [rsp+28h+arg_10]
0x1800213b4  jmp     loc_180021305
0x1800213b9  xor     ebx, ebx
0x1800213bb  jmp     loc_18002131B
```
