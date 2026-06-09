# CNamespaceHandle::GetChildDefs(ushort const *,bool,IWbemObjectSink *,bool)

- ea: `0x1800219a8`
- end: `0x180021ad6`
- name: `?GetChildDefs@CNamespaceHandle@@IEAAJPEBG_NPEAUIWbemObjectSink@@1@Z`
- size: `302`
- prototype: `__int64 __fastcall(CNamespaceHandle *this, const unsigned __int16 *, bool, struct IWbemObjectSink *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007770`

## callees

- `0x1800012b8`
- `0x180006960`
- `0x1800219a8`
- `0x180021adc`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800219c4`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800219c4`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180021a34`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180021aa3`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180021ac2`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180021a34`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180021aa3`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180021ac2`
- `wbemcomn!GetMemLogObject` at `0x1800219e1`
- `wbemcomn!GetMemLogObject` at `0x180021a4f`
- `wbemcomn!GetMemLogObject` at `0x1800219e1`
- `wbemcomn!GetMemLogObject` at `0x180021a4f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800219f1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021a5f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800219f1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021a5f`

## pseudocode

```c
__int64 __fastcall CNamespaceHandle::GetChildDefs(
        CNamespaceHandle *this,
        const unsigned __int16 *a2,
        bool a3,
        struct IWbemObjectSink *a4)
{
  unsigned __int16 *v8; // rbx
  CMemoryLog *v9; // rax
  unsigned int ChildDefsByHash; // edi
  CMemoryLog *MemLogObject; // rax
  bool v13; // [rsp+20h] [rbp-48h]

  v8 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(0x2E6u);
  if ( v8 )
  {
    *v8 = 0;
    if ( A51Hash(a2, v8) )
    {
      ChildDefsByHash = CNamespaceHandle::GetChildDefsByHash(this, v8, a3, a4, v13);
      CWin32DefaultArena::WbemMemFree(v8);
    }
    else
    {
      MemLogObject = GetMemLogObject();
      ChildDefsByHash = -2147217402;
      CMemoryLog::Write(MemLogObject, -2147217402);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          389,
          WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
          2147749894LL);
      }
      CWin32DefaultArena::WbemMemFree(v8);
    }
  }
  else
  {
    v9 = GetMemLogObject();
    ChildDefsByHash = -2147217402;
    CMemoryLog::Write(v9, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 388, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749894LL);
    }
    CWin32DefaultArena::WbemMemFree(0);
  }
  return ChildDefsByHash;
}

```

## disassembly

```asm
0x1800219a8  push    rbx
0x1800219aa  push    rbp
0x1800219ab  push    rsi
0x1800219ac  push    rdi
0x1800219ad  push    r14
0x1800219af  sub     rsp, 40h
0x1800219b3  mov     rsi, r9
0x1800219b6  mov     bpl, r8b
0x1800219b9  mov     rdi, rdx
0x1800219bc  mov     r14, rcx
0x1800219bf  mov     ecx, 2E6h
0x1800219c4  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800219ca  mov     rbx, rax
0x1800219cd  mov     [rsp+68h+var_38], rax
0x1800219d2  test    rax, rax
0x1800219d5  jz      short loc_1800219DC
0x1800219d7  xor     eax, eax
0x1800219d9  mov     [rbx], ax
0x1800219dc  test    rbx, rbx
0x1800219df  jnz     short loc_180021A40
0x1800219e1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800219e7  mov     edi, 80041006h
0x1800219ec  mov     edx, edi
0x1800219ee  mov     rcx, rax
0x1800219f1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800219f7  lea     rax, WPP_GLOBAL_Control
0x1800219fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180021a05  cmp     rcx, rax
0x180021a08  jz      short loc_180021A32
0x180021a0a  test    byte ptr [rcx+1Ch], 1
0x180021a0e  jz      short loc_180021A32
0x180021a10  cmp     byte ptr [rcx+19h], 2
0x180021a14  jb      short loc_180021A32
0x180021a16  mov     edx, 184h
0x180021a1b  mov     r9d, 80041006h
0x180021a21  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180021a28  mov     rcx, [rcx+10h]
0x180021a2c  call    WPP_SF_d
0x180021a31  nop
0x180021a32  xor     ecx, ecx
0x180021a34  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180021a3a  nop
0x180021a3b  jmp     loc_180021AC9
0x180021a40  mov     rdx, rbx; unsigned __int16 *
0x180021a43  mov     rcx, rdi; unsigned __int16 *
0x180021a46  call    ?A51Hash@@YA_NPEBGPEAG@Z; A51Hash(ushort const *,ushort *)
0x180021a4b  test    al, al
0x180021a4d  jnz     short loc_180021AAC
0x180021a4f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180021a55  mov     edi, 80041006h
0x180021a5a  mov     edx, edi
0x180021a5c  mov     rcx, rax
0x180021a5f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180021a65  lea     rax, WPP_GLOBAL_Control
0x180021a6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180021a73  cmp     rcx, rax
0x180021a76  jz      short loc_180021AA0
0x180021a78  test    byte ptr [rcx+1Ch], 1
0x180021a7c  jz      short loc_180021AA0
0x180021a7e  cmp     byte ptr [rcx+19h], 2
0x180021a82  jb      short loc_180021AA0
0x180021a84  mov     edx, 185h
0x180021a89  mov     r9d, 80041006h
0x180021a8f  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180021a96  mov     rcx, [rcx+10h]
0x180021a9a  call    WPP_SF_d
0x180021a9f  nop
0x180021aa0  mov     rcx, rbx
0x180021aa3  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180021aa9  nop
0x180021aaa  jmp     short loc_180021AC9
0x180021aac  mov     r9, rsi; struct IWbemObjectSink *
0x180021aaf  mov     r8b, bpl; bool
0x180021ab2  mov     rdx, rbx; unsigned __int16 *
0x180021ab5  mov     rcx, r14; this
0x180021ab8  call    ?GetChildDefsByHash@CNamespaceHandle@@IEAAJPEBG_NPEAUIWbemObjectSink@@1@Z; CNamespaceHandle::GetChildDefsByHash(ushort const *,bool,IWbemObjectSink *,bool)
0x180021abd  mov     edi, eax
0x180021abf  mov     rcx, rbx
0x180021ac2  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180021ac8  nop
0x180021ac9  mov     eax, edi
0x180021acb  add     rsp, 40h
0x180021acf  pop     r14
0x180021ad1  pop     rdi
0x180021ad2  pop     rsi
0x180021ad3  pop     rbp
0x180021ad4  pop     rbx
0x180021ad5  retn
```
