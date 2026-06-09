# CNamespaceHandle::ConstructClassReferenceFileName(ushort const *,ushort const *,ushort const *,CFileName &)

- ea: `0x180032690`
- end: `0x18003278f`
- name: `?ConstructClassReferenceFileName@CNamespaceHandle@@IEAAJPEBG00AEAVCFileName@@@Z`
- size: `255`
- prototype: `__int64 __fastcall(CNamespaceHandle *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct CFileName *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180034de0`
- `0x1800363e8`

## callees

- `0x1800012b8`
- `0x180013f90`
- `0x180023c5c`
- `0x180032690`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180032709`
- `msvcrt!wcsrchr` at `0x180032709`
- `wbemcomn!GetMemLogObject` at `0x1800326b5`
- `wbemcomn!GetMemLogObject` at `0x180032717`
- `wbemcomn!GetMemLogObject` at `0x1800326b5`
- `wbemcomn!GetMemLogObject` at `0x180032717`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800326c0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180032727`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800326c0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180032727`

## pseudocode

```c
__int64 __fastcall CNamespaceHandle::ConstructClassReferenceFileName(
        CNamespaceHandle *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct CFileName *a5)
{
  unsigned int v6; // ebx
  CMemoryLog *MemLogObject; // rax
  CVarObjHeap *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  wchar_t *v12; // rbx
  CMemoryLog *v13; // rax

  v6 = CNamespaceHandle::ConstructClassRelationshipsDir(this, a2, a5);
  if ( (v6 & 0x80000000) != 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v6);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v6;
    }
    v9 = 306;
    v10 = v6;
LABEL_6:
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, v10);
    return v6;
  }
  v12 = wcsrchr(a3, 0x5Fu);
  if ( !v12 )
  {
    v13 = GetMemLogObject();
    v6 = -2147217398;
    CMemoryLog::Write(v13, -2147217398);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v6;
    }
    v9 = 307;
    v10 = 2147749898LL;
    goto LABEL_6;
  }
  StringCchCatW(*(unsigned __int16 **)a5, 0x173u, L"\\R_");
  StringCchCatW(*(unsigned __int16 **)a5, 0x173u, v12 + 1);
  return 0;
}

```

## disassembly

```asm
0x180032690  mov     [rsp+arg_0], rbx
0x180032695  mov     [rsp+arg_8], rsi
0x18003269a  push    rdi
0x18003269b  sub     rsp, 20h
0x18003269f  mov     rdi, [rsp+28h+arg_20]
0x1800326a4  mov     rsi, r8
0x1800326a7  mov     r8, rdi; struct CFileName *
0x1800326aa  call    ?ConstructClassRelationshipsDir@CNamespaceHandle@@IEAAJPEBGAEAVCFileName@@@Z; CNamespaceHandle::ConstructClassRelationshipsDir(ushort const *,CFileName &)
0x1800326af  mov     ebx, eax
0x1800326b1  test    eax, eax
0x1800326b3  jns     short loc_180032701
0x1800326b5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800326bb  mov     rcx, rax
0x1800326be  mov     edx, ebx
0x1800326c0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800326c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800326cd  lea     rax, WPP_GLOBAL_Control
0x1800326d4  cmp     rcx, rax
0x1800326d7  jz      short loc_1800326FD
0x1800326d9  test    byte ptr [rcx+1Ch], 1
0x1800326dd  jz      short loc_1800326FD
0x1800326df  cmp     byte ptr [rcx+19h], 2
0x1800326e3  jb      short loc_1800326FD
0x1800326e5  mov     edx, 132h
0x1800326ea  mov     r9d, ebx
0x1800326ed  mov     rcx, [rcx+10h]
0x1800326f1  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x1800326f8  call    WPP_SF_d
0x1800326fd  mov     eax, ebx
0x1800326ff  jmp     short loc_18003277F
0x180032701  mov     edx, 5Fh ; '_'; Ch
0x180032706  mov     rcx, rsi; Str
0x180032709  call    cs:__imp_wcsrchr
0x18003270f  mov     rbx, rax
0x180032712  test    rax, rax
0x180032715  jnz     short loc_180032759
0x180032717  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003271d  mov     ebx, 8004100Ah
0x180032722  mov     rcx, rax
0x180032725  mov     edx, ebx
0x180032727  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003272d  mov     rcx, cs:WPP_GLOBAL_Control
0x180032734  lea     rax, WPP_GLOBAL_Control
0x18003273b  cmp     rcx, rax
0x18003273e  jz      short loc_1800326FD
0x180032740  test    byte ptr [rcx+1Ch], 1
0x180032744  jz      short loc_1800326FD
0x180032746  cmp     byte ptr [rcx+19h], 2
0x18003274a  jb      short loc_1800326FD
0x18003274c  mov     edx, 133h
0x180032751  mov     r9d, 8004100Ah
0x180032757  jmp     short loc_1800326ED
0x180032759  mov     rcx, [rdi]; unsigned __int16 *
0x18003275c  lea     r8, aR; "\\R_"
0x180032763  mov     esi, 173h
0x180032768  mov     edx, esi; unsigned __int64
0x18003276a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003276f  mov     rcx, [rdi]; unsigned __int16 *
0x180032772  lea     r8, [rbx+2]; unsigned __int16 *
0x180032776  mov     edx, esi; unsigned __int64
0x180032778  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003277d  xor     eax, eax
0x18003277f  mov     rbx, [rsp+28h+arg_0]
0x180032784  mov     rsi, [rsp+28h+arg_8]
0x180032789  add     rsp, 20h
0x18003278d  pop     rdi
0x18003278e  retn
```
