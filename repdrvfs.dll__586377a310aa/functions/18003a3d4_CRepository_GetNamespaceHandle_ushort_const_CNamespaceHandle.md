# CRepository::GetNamespaceHandle(ushort const *,CNamespaceHandle * *)

- ea: `0x18003a3d4`
- end: `0x18003a548`
- name: `?GetNamespaceHandle@CRepository@@QEAAJPEBGPEAPEAVCNamespaceHandle@@@Z`
- size: `372`
- prototype: `__int64 __fastcall(struct CLifeControl **this, const unsigned __int16 *, struct CNamespaceHandle **)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180008730`
- `0x18002435c`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x1800161e0`
- `0x180023170`
- `0x18003a3d4`
- `0x180048010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003a420`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003a420`
- `wbemcomn!GetMemLogObject` at `0x18003a44b`
- `wbemcomn!GetMemLogObject` at `0x18003a4c3`
- `wbemcomn!GetMemLogObject` at `0x18003a44b`
- `wbemcomn!GetMemLogObject` at `0x18003a4c3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003a45b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003a4ce`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003a45b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003a4ce`

## pseudocode

```c
__int64 __fastcall CRepository::GetNamespaceHandle(
        struct CLifeControl **this,
        const unsigned __int16 *a2,
        struct CNamespaceHandle **a3)
{
  CNamespaceHandle *v6; // rax
  CNamespaceHandle *v7; // rbx
  CMemoryLog *v8; // rax
  int v10; // edi
  CMemoryLog *MemLogObject; // rax

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids);
  }
  v6 = (CNamespaceHandle *)CWin32DefaultArena::WbemMemAlloc(0x70u);
  if ( v6 )
    v7 = CNamespaceHandle::CNamespaceHandle(v6, this[2], (struct CRepository *)this);
  else
    v7 = 0;
  if ( v7 )
  {
    (*(void (__fastcall **)(CNamespaceHandle *))(*(_QWORD *)v7 + 8LL))(v7);
    v10 = CNamespaceHandle::Initialize(v7, a2, 0);
    if ( v10 >= 0 )
    {
      *a3 = v7;
      (*(void (__fastcall **)(CNamespaceHandle *))(*(_QWORD *)v7 + 8LL))(v7);
      (*(void (__fastcall **)(CNamespaceHandle *))(*(_QWORD *)v7 + 16LL))(v7);
      return 0;
    }
    else
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v10);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          74,
          WPP_53e1474670223052d7bc731b72ed24d6_Traceguids,
          (unsigned int)v10);
      }
      (*(void (__fastcall **)(CNamespaceHandle *))(*(_QWORD *)v7 + 16LL))(v7);
      return (unsigned int)v10;
    }
  }
  else
  {
    v8 = GetMemLogObject();
    CMemoryLog::Write(v8, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
}

```

## disassembly

```asm
0x18003a3d4  push    rbx
0x18003a3d6  push    rsi
0x18003a3d7  push    rdi
0x18003a3d8  push    r15
0x18003a3da  sub     rsp, 28h
0x18003a3de  mov     rsi, r8
0x18003a3e1  mov     rdi, rdx
0x18003a3e4  mov     rbx, rcx
0x18003a3e7  lea     r15, WPP_GLOBAL_Control
0x18003a3ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a3f5  cmp     rcx, r15
0x18003a3f8  jz      short loc_18003A41B
0x18003a3fa  test    byte ptr [rcx+1Ch], 1
0x18003a3fe  jz      short loc_18003A41B
0x18003a400  cmp     byte ptr [rcx+19h], 5
0x18003a404  jb      short loc_18003A41B
0x18003a406  mov     edx, 48h ; 'H'
0x18003a40b  lea     r8, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids
0x18003a412  mov     rcx, [rcx+10h]
0x18003a416  call    WPP_SF_
0x18003a41b  mov     ecx, 70h ; 'p'
0x18003a420  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003a426  mov     [rsp+48h+arg_18], rax
0x18003a42b  test    rax, rax
0x18003a42e  jz      short loc_18003A444
0x18003a430  mov     r8, rbx; struct CRepository *
0x18003a433  mov     rdx, [rbx+10h]; struct CLifeControl *
0x18003a437  mov     rcx, rax; this
0x18003a43a  call    ??0CNamespaceHandle@@QEAA@PEAVCLifeControl@@PEAVCRepository@@@Z; CNamespaceHandle::CNamespaceHandle(CLifeControl *,CRepository *)
0x18003a43f  mov     rbx, rax
0x18003a442  jmp     short loc_18003A446
0x18003a444  xor     ebx, ebx
0x18003a446  test    rbx, rbx
0x18003a449  jnz     short loc_18003A49B
0x18003a44b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003a451  mov     ebx, 80041006h
0x18003a456  mov     edx, ebx
0x18003a458  mov     rcx, rax
0x18003a45b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003a461  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a468  cmp     rcx, r15
0x18003a46b  jz      short loc_18003A494
0x18003a46d  test    byte ptr [rcx+1Ch], 1
0x18003a471  jz      short loc_18003A494
0x18003a473  cmp     byte ptr [rcx+19h], 2
0x18003a477  jb      short loc_18003A494
0x18003a479  mov     edx, 49h ; 'I'
0x18003a47e  mov     r9d, 80041006h
0x18003a484  lea     r8, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids
0x18003a48b  mov     rcx, [rcx+10h]
0x18003a48f  call    WPP_SF_d
0x18003a494  mov     eax, ebx
0x18003a496  jmp     loc_18003A53E
0x18003a49b  mov     rax, [rbx]
0x18003a49e  mov     rcx, rbx
0x18003a4a1  mov     rax, [rax+8]
0x18003a4a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a4aa  mov     [rsp+48h+arg_18], rbx
0x18003a4af  xor     r8d, r8d; unsigned __int16 *
0x18003a4b2  mov     rdx, rdi; unsigned __int16 *
0x18003a4b5  mov     rcx, rbx; this
0x18003a4b8  call    ?Initialize@CNamespaceHandle@@QEAAJPEBG0@Z; CNamespaceHandle::Initialize(ushort const *,ushort const *)
0x18003a4bd  mov     edi, eax
0x18003a4bf  test    eax, eax
0x18003a4c1  jns     short loc_18003A519
0x18003a4c3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003a4c9  mov     edx, edi
0x18003a4cb  mov     rcx, rax
0x18003a4ce  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003a4d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a4db  cmp     rcx, r15
0x18003a4de  jz      short loc_18003A505
0x18003a4e0  test    byte ptr [rcx+1Ch], 1
0x18003a4e4  jz      short loc_18003A505
0x18003a4e6  cmp     byte ptr [rcx+19h], 2
0x18003a4ea  jb      short loc_18003A505
0x18003a4ec  mov     edx, 4Ah ; 'J'
0x18003a4f1  mov     r9d, edi
0x18003a4f4  lea     r8, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids
0x18003a4fb  mov     rcx, [rcx+10h]
0x18003a4ff  call    WPP_SF_d
0x18003a504  nop
0x18003a505  mov     rax, [rbx]
0x18003a508  mov     rcx, rbx
0x18003a50b  mov     rax, [rax+10h]
0x18003a50f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a514  nop
0x18003a515  mov     eax, edi
0x18003a517  jmp     short loc_18003A53E
0x18003a519  mov     [rsi], rbx
0x18003a51c  mov     rax, [rbx]
0x18003a51f  mov     rcx, rbx
0x18003a522  mov     rax, [rax+8]
0x18003a526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a52b  nop
0x18003a52c  mov     rax, [rbx]
0x18003a52f  mov     rcx, rbx
0x18003a532  mov     rax, [rax+10h]
0x18003a536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a53b  nop
0x18003a53c  xor     eax, eax
0x18003a53e  add     rsp, 28h
0x18003a542  pop     r15
0x18003a544  pop     rdi
0x18003a545  pop     rsi
0x18003a546  pop     rbx
0x18003a547  retn
```
