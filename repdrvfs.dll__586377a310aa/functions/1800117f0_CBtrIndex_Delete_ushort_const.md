# CBtrIndex::Delete(ushort const *)

- ea: `0x1800117f0`
- end: `0x1800118fd`
- name: `?Delete@CBtrIndex@@QEAAJPEBG@Z`
- size: `269`
- prototype: `__int64 __fastcall(CBtrIndex *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180013558`
- `0x180013974`
- `0x180030a90`

## callees

- `0x1800012b8`
- `0x1800117f0`
- `0x180011904`
- `0x180012f4c`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001181d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001181d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180011867`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180011867`
- `wbemcomn!GetMemLogObject` at `0x180011880`
- `wbemcomn!GetMemLogObject` at `0x180011880`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001188e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001188e`

## pseudocode

```c
__int64 __fastcall CBtrIndex::Delete(struct SIdxKeyTable **this, const unsigned __int16 *a2)
{
  const unsigned __int16 *v2; // rbx
  __int64 v4; // rcx
  char *v5; // rax
  char *v6; // rdi
  char *v7; // rcx
  unsigned __int16 i; // dx
  unsigned int v9; // ebx
  CMemoryLog *MemLogObject; // rax
  char *v12; // [rsp+48h] [rbp+20h]

  v2 = a2;
  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  v5 = (char *)CWin32DefaultArena::WbemMemAlloc(v4 + 1);
  v6 = v5;
  v12 = v5;
  if ( v5 )
  {
    v7 = v5;
    for ( i = *v2; *v2; LOBYTE(i) = *v2 )
    {
      ++v2;
      *v7++ = i;
    }
    try
    {
      *v7 = 0;
      v9 = CBTree::DeleteKey(this + 1, v5);
      if ( !v9 )
        CIteratorBatch::PurgeAll(v6);
    }
    catch ( CX_MemoryException )
    {
      v9 = 14;
      v6 = v12;
    }
    CWin32DefaultArena::WbemMemFree(v6);
    return v9;
  }
  else
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, 8);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_4468c7411f373aed0078c9b7f9420cb4_Traceguids, 8);
    }
    return 8;
  }
}

```

## disassembly

```asm
0x1800117f0  mov     [rsp+arg_0], rbx
0x1800117f5  mov     [rsp+arg_8], rsi
0x1800117fa  push    rdi
0x1800117fb  sub     rsp, 20h
0x1800117ff  mov     rbx, rdx
0x180011802  mov     rsi, rcx
0x180011805  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001180c  nop     dword ptr [rax+00h]
0x180011810  inc     rcx
0x180011813  cmp     word ptr [rdx+rcx*2], 0
0x180011818  jnz     short loc_180011810
0x18001181a  inc     rcx
0x18001181d  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180011823  mov     rdi, rax
0x180011826  mov     [rsp+28h+arg_18], rax
0x18001182b  test    rax, rax
0x18001182e  jz      short loc_180011880
0x180011830  mov     rcx, rax
0x180011833  movzx   edx, word ptr [rbx]
0x180011836  test    dx, dx
0x180011839  jz      short loc_18001184F
0x18001183b  lea     rbx, [rbx+2]
0x18001183f  mov     [rcx], dl
0x180011841  inc     rcx
0x180011844  movzx   eax, word ptr [rbx]
0x180011847  movzx   edx, al
0x18001184a  test    ax, ax
0x18001184d  jnz     short loc_18001183B
0x18001184f  mov     byte ptr [rcx], 0
0x180011852  lea     rcx, [rsi+8]; this
0x180011856  mov     rdx, rdi; char *
0x180011859  call    ?DeleteKey@CBTree@@QEAAKPEAD@Z; CBTree::DeleteKey(char *)
0x18001185e  mov     ebx, eax
0x180011860  test    eax, eax
0x180011862  jz      short loc_1800118BC
0x180011864  mov     rcx, rdi
0x180011867  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18001186d  nop
0x18001186e  mov     eax, ebx
0x180011870  mov     rbx, [rsp+28h+arg_0]
0x180011875  mov     rsi, [rsp+28h+arg_8]
0x18001187a  add     rsp, 20h
0x18001187e  pop     rdi
0x18001187f  retn
0x180011880  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180011886  mov     edx, 8
0x18001188b  mov     rcx, rax
0x18001188e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180011894  lea     rax, WPP_GLOBAL_Control
0x18001189b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800118a2  cmp     rcx, rax
0x1800118a5  jnz     short loc_1800118C6
0x1800118a7  mov     eax, 8
0x1800118ac  mov     rbx, [rsp+28h+arg_0]
0x1800118b1  mov     rsi, [rsp+28h+arg_8]
0x1800118b6  add     rsp, 20h
0x1800118ba  pop     rdi
0x1800118bb  retn
0x1800118bc  mov     rcx, rdi; char *
0x1800118bf  call    ?PurgeAll@CIteratorBatch@@SAKPEAD@Z; CIteratorBatch::PurgeAll(char *)
0x1800118c4  jmp     short loc_180011864
0x1800118c6  test    byte ptr [rcx+1Ch], 1
0x1800118ca  jz      short loc_1800118A7
0x1800118cc  cmp     byte ptr [rcx+19h], 2
0x1800118d0  jb      short loc_1800118A7
0x1800118d2  mov     edx, 10h
0x1800118d7  mov     r9d, 8
0x1800118dd  lea     r8, WPP_4468c7411f373aed0078c9b7f9420cb4_Traceguids
0x1800118e4  mov     rcx, [rcx+10h]
0x1800118e8  call    WPP_SF_d
0x1800118ed  jmp     short loc_1800118A7
0x1800118ef  mov     ebx, [rsp+28h+arg_10]
0x1800118f3  mov     rdi, [rsp+28h+arg_18]
0x1800118f8  jmp     loc_180011864
```
