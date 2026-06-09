# CObjectHeap::CreateIndexFile(ushort const *,ulong,ulong,ulong)

- ea: `0x180021168`
- end: `0x180021249`
- name: `?CreateIndexFile@CObjectHeap@@IEAAJPEBGKKK@Z`
- size: `225`
- prototype: `__int64 __fastcall(CObjectHeap *this, const unsigned __int16 *, int, int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800203a0`

## callees

- `0x1800012b8`
- `0x180021168`
- `0x180021250`
- `0x1800216c8`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180021184`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180021184`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800211ef`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180021235`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800211ef`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180021235`
- `wbemcomn!GetMemLogObject` at `0x1800211a1`
- `wbemcomn!GetMemLogObject` at `0x1800211a1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800211b1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800211b1`

## pseudocode

```c
__int64 __fastcall CObjectHeap::CreateIndexFile(
        CObjectHeap *this,
        const unsigned __int16 *a2,
        int a3,
        int a4,
        unsigned int a5)
{
  unsigned __int16 *v9; // rbx
  CMemoryLog *MemLogObject; // rax
  unsigned int v11; // edi

  v9 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(0x2E6u);
  if ( v9 )
  {
    *v9 = 0;
    StringCchPrintfW(v9, 0x173u, L"%s.%u.%u.%u", a2, a3, a4, a5);
    v11 = CBtrIndex::Create((CObjectHeap *)((char *)this + 32), v9);
    CWin32DefaultArena::WbemMemFree(v9);
    return v11;
  }
  else
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, 14);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids, 14);
    }
    CWin32DefaultArena::WbemMemFree(0);
    return 14;
  }
}

```

## disassembly

```asm
0x180021168  push    rbx
0x18002116a  push    rbp
0x18002116b  push    rsi
0x18002116c  push    rdi
0x18002116d  push    r14
0x18002116f  sub     rsp, 50h
0x180021173  mov     edi, r9d
0x180021176  mov     esi, r8d
0x180021179  mov     rbp, rdx
0x18002117c  mov     r14, rcx
0x18002117f  mov     ecx, 2E6h
0x180021184  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18002118a  mov     rbx, rax
0x18002118d  mov     [rsp+78h+var_38], rax
0x180021192  test    rax, rax
0x180021195  jz      short loc_18002119C
0x180021197  xor     eax, eax
0x180021199  mov     [rbx], ax
0x18002119c  test    rbx, rbx
0x18002119f  jnz     short loc_1800211FA
0x1800211a1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800211a7  mov     ebx, 0Eh
0x1800211ac  mov     edx, ebx
0x1800211ae  mov     rcx, rax
0x1800211b1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800211b7  lea     rax, WPP_GLOBAL_Control
0x1800211be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800211c5  cmp     rcx, rax
0x1800211c8  jz      short loc_1800211ED
0x1800211ca  test    byte ptr [rcx+1Ch], 1
0x1800211ce  jz      short loc_1800211ED
0x1800211d0  cmp     byte ptr [rcx+19h], 2
0x1800211d4  jb      short loc_1800211ED
0x1800211d6  lea     edx, [rbx+8]
0x1800211d9  mov     r9d, ebx
0x1800211dc  lea     r8, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids
0x1800211e3  mov     rcx, [rcx+10h]
0x1800211e7  call    WPP_SF_d
0x1800211ec  nop
0x1800211ed  xor     ecx, ecx
0x1800211ef  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800211f5  nop
0x1800211f6  mov     eax, ebx
0x1800211f8  jmp     short loc_18002123E
0x1800211fa  mov     eax, [rsp+78h+arg_20]
0x180021201  mov     [rsp+78h+var_48], eax
0x180021205  mov     [rsp+78h+var_50], edi
0x180021209  mov     [rsp+78h+var_58], esi
0x18002120d  mov     r9, rbp
0x180021210  lea     r8, aSUUU; "%s.%u.%u.%u"
0x180021217  mov     edx, 173h; unsigned __int64
0x18002121c  mov     rcx, rbx; unsigned __int16 *
0x18002121f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180021224  lea     rcx, [r14+20h]; this
0x180021228  mov     rdx, rbx; unsigned __int16 *
0x18002122b  call    ?Create@CBtrIndex@@QEAAJPEBG@Z; CBtrIndex::Create(ushort const *)
0x180021230  mov     edi, eax
0x180021232  mov     rcx, rbx
0x180021235  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18002123b  nop
0x18002123c  mov     eax, edi
0x18002123e  add     rsp, 50h
0x180021242  pop     r14
0x180021244  pop     rdi
0x180021245  pop     rsi
0x180021246  pop     rbp
0x180021247  pop     rbx
0x180021248  retn
```
