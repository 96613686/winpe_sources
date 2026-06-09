# CObjectHeap::DeleteIndexFile(ushort const *,ushort const *)

- ea: `0x180013558`
- end: `0x1800136af`
- name: `?DeleteIndexFile@CObjectHeap@@IEAAJPEBG0@Z`
- size: `343`
- prototype: `__int64 __fastcall(CObjectHeap *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180013048`
- `0x1800203a0`

## callees

- `0x1800012b8`
- `0x1800117f0`
- `0x180013558`
- `0x180013880`
- `0x18002b7b6`

## import_xrefs

- `msvcrt!wcsrchr` at `0x1800135f4`
- `msvcrt!wcsrchr` at `0x1800135f4`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180013573`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180013573`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800135de`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001364e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013699`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800135de`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001364e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013699`
- `wbemcomn!GetMemLogObject` at `0x180013590`
- `wbemcomn!GetMemLogObject` at `0x1800135ff`
- `wbemcomn!GetMemLogObject` at `0x180013590`
- `wbemcomn!GetMemLogObject` at `0x1800135ff`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800135a0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001360f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800135a0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001360f`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CObjectHeap::DeleteIndexFile(
        CObjectHeap *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  _WORD *v6; // rbx
  CMemoryLog *v7; // rax
  wchar_t *v9; // rax
  CMemoryLog *MemLogObject; // rax
  unsigned int v11; // edi
  int v12; // edi

  v6 = CWin32DefaultArena::WbemMemAlloc(0x2E6u);
  if ( v6 )
  {
    *v6 = 0;
    v9 = wcsrchr(a2, 0x5Cu);
    if ( v9 )
    {
      v12 = v9 - a2 + 1;
      memcpy_0(v6, a2, 2LL * v12);
      StringCchCopyW(&v6[v12], (unsigned int)(371 - v12), a3);
      v11 = CBtrIndex::Delete((CObjectHeap *)((char *)this + 32), v6);
      CWin32DefaultArena::WbemMemFree(v6);
    }
    else
    {
      MemLogObject = GetMemLogObject();
      v11 = 87;
      CMemoryLog::Write(MemLogObject, 87);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids, 87);
      }
      CWin32DefaultArena::WbemMemFree(v6);
    }
    return v11;
  }
  else
  {
    v7 = GetMemLogObject();
    CMemoryLog::Write(v7, 14);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids, 14);
    }
    CWin32DefaultArena::WbemMemFree(0);
    return 14;
  }
}

```

## disassembly

```asm
0x180013558  push    rbx
0x18001355a  push    rbp
0x18001355b  push    rsi
0x18001355c  push    rdi
0x18001355d  push    r14
0x18001355f  push    r15
0x180013561  sub     rsp, 28h
0x180013565  mov     r14, r8
0x180013568  mov     rbp, rdx
0x18001356b  mov     r15, rcx
0x18001356e  mov     ecx, 2E6h
0x180013573  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180013579  mov     rbx, rax
0x18001357c  mov     [rsp+58h+arg_18], rax
0x180013581  test    rax, rax
0x180013584  jz      short loc_18001358B
0x180013586  xor     eax, eax
0x180013588  mov     [rbx], ax
0x18001358b  test    rbx, rbx
0x18001358e  jnz     short loc_1800135EC
0x180013590  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180013596  mov     ebx, 0Eh
0x18001359b  mov     edx, ebx
0x18001359d  mov     rcx, rax
0x1800135a0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800135a6  lea     rax, WPP_GLOBAL_Control
0x1800135ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800135b4  cmp     rcx, rax
0x1800135b7  jz      short loc_1800135DC
0x1800135b9  test    byte ptr [rcx+1Ch], 1
0x1800135bd  jz      short loc_1800135DC
0x1800135bf  cmp     byte ptr [rcx+19h], 2
0x1800135c3  jb      short loc_1800135DC
0x1800135c5  lea     edx, [rbx+9]
0x1800135c8  mov     r9d, ebx
0x1800135cb  lea     r8, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids
0x1800135d2  mov     rcx, [rcx+10h]
0x1800135d6  call    WPP_SF_d
0x1800135db  nop
0x1800135dc  xor     ecx, ecx
0x1800135de  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800135e4  nop
0x1800135e5  mov     eax, ebx
0x1800135e7  jmp     loc_1800136A2
0x1800135ec  mov     edx, 5Ch ; '\'; Ch
0x1800135f1  mov     rcx, rbp; Str
0x1800135f4  call    cs:__imp_wcsrchr
0x1800135fa  test    rax, rax
0x1800135fd  jnz     short loc_180013657
0x1800135ff  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180013605  mov     edi, 57h ; 'W'
0x18001360a  mov     edx, edi
0x18001360c  mov     rcx, rax
0x18001360f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180013615  lea     rax, WPP_GLOBAL_Control
0x18001361c  mov     rcx, cs:WPP_GLOBAL_Control
0x180013623  cmp     rcx, rax
0x180013626  jz      short loc_18001364B
0x180013628  test    byte ptr [rcx+1Ch], 1
0x18001362c  jz      short loc_18001364B
0x18001362e  cmp     byte ptr [rcx+19h], 2
0x180013632  jb      short loc_18001364B
0x180013634  lea     edx, [rdi-3Fh]
0x180013637  mov     r9d, edi
0x18001363a  lea     r8, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids
0x180013641  mov     rcx, [rcx+10h]
0x180013645  call    WPP_SF_d
0x18001364a  nop
0x18001364b  mov     rcx, rbx
0x18001364e  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180013654  nop
0x180013655  jmp     short loc_1800136A0
0x180013657  sub     rax, rbp
0x18001365a  sar     rax, 1
0x18001365d  lea     edi, [rax+1]
0x180013660  movsxd  rax, edi
0x180013663  lea     rsi, [rax+rax]
0x180013667  mov     r8, rsi; Size
0x18001366a  mov     rdx, rbp; Src
0x18001366d  mov     rcx, rbx; void *
0x180013670  call    memcpy_0
0x180013675  mov     edx, 173h
0x18001367a  sub     edx, edi; unsigned __int64
0x18001367c  lea     rcx, [rsi+rbx]; unsigned __int16 *
0x180013680  mov     r8, r14; unsigned __int16 *
0x180013683  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180013688  lea     rcx, [r15+20h]; this
0x18001368c  mov     rdx, rbx; unsigned __int16 *
0x18001368f  call    ?Delete@CBtrIndex@@QEAAJPEBG@Z; CBtrIndex::Delete(ushort const *)
0x180013694  mov     edi, eax
0x180013696  mov     rcx, rbx
0x180013699  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18001369f  nop
0x1800136a0  mov     eax, edi
0x1800136a2  add     rsp, 28h
0x1800136a6  pop     r15
0x1800136a8  pop     r14
0x1800136aa  pop     rdi
0x1800136ab  pop     rsi
0x1800136ac  pop     rbp
0x1800136ad  pop     rbx
0x1800136ae  retn
```
