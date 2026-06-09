# CNamespaceHandle::DeleteDerivedClasses(ushort const *,CEventCollector &,bool,ulong)

- ea: `0x180033a0c`
- end: `0x180033b7d`
- name: `?DeleteDerivedClasses@CNamespaceHandle@@IEAAJPEBGAEAVCEventCollector@@_NK@Z`
- size: `369`
- prototype: `__int64 __fastcall(CNamespaceHandle *__hidden this, const unsigned __int16 *, struct CEventCollector *, bool, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800253d4`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x180032f08`
- `0x180033a0c`
- `0x1800355a8`

## import_xrefs

- `wbemcomn!??ACWStringArray@@QEBAPEAGH@Z` at `0x180033ae4`
- `wbemcomn!??ACWStringArray@@QEBAPEAGH@Z` at `0x180033ae4`
- `wbemcomn!?Size@CWStringArray@@QEBAHXZ` at `0x180033ad3`
- `wbemcomn!?Size@CWStringArray@@QEBAHXZ` at `0x180033ad3`
- `wbemcomn!??0CWStringArray@@QEAA@HH@Z` at `0x180033a69`
- `wbemcomn!??0CWStringArray@@QEAA@HH@Z` at `0x180033a69`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180033b63`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180033b63`
- `wbemcomn!GetMemLogObject` at `0x180033a90`
- `wbemcomn!GetMemLogObject` at `0x180033b19`
- `wbemcomn!GetMemLogObject` at `0x180033a90`
- `wbemcomn!GetMemLogObject` at `0x180033b19`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180033a9b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180033b24`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180033a9b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180033b24`

## pseudocode

```c
__int64 __fastcall CNamespaceHandle::DeleteDerivedClasses(
        CNamespaceHandle *this,
        const unsigned __int16 *a2,
        struct CEventCollector *a3,
        bool a4,
        unsigned int a5)
{
  int ChildHashes; // ebx
  CMemoryLog *v10; // rax
  CVarObjHeap *v11; // rcx
  __int64 v12; // rdx
  unsigned int i; // edi
  const unsigned __int16 *v14; // rax
  CMemoryLog *MemLogObject; // rax
  _BYTE v17[152]; // [rsp+30h] [rbp-98h] BYREF

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 385, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
  }
  CWStringArray::CWStringArray((CWStringArray *)v17, 0, 100);
  ChildHashes = CNamespaceHandle::GetChildHashes(this, a2, (struct CWStringArray *)v17, a5);
  if ( ChildHashes >= 0 )
  {
    for ( i = 0; ; ++i )
    {
      if ( (signed int)i >= CWStringArray::Size((CWStringArray *)v17) )
      {
        ChildHashes = 0;
        goto LABEL_21;
      }
      v14 = (const unsigned __int16 *)CWStringArray::operator[](v17, i);
      ChildHashes = CNamespaceHandle::DeleteClassByHash(this, v14, a3, a4, a5);
      if ( (int)(ChildHashes + 0x80000000) >= 0 && ChildHashes != -2147217406 )
        break;
    }
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, ChildHashes);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = 387;
      goto LABEL_19;
    }
  }
  else
  {
    v10 = GetMemLogObject();
    CMemoryLog::Write(v10, ChildHashes);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = 386;
LABEL_19:
      WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, (unsigned int)ChildHashes);
    }
  }
LABEL_21:
  CWStringArray::~CWStringArray((CWStringArray *)v17);
  return (unsigned int)ChildHashes;
}

```

## disassembly

```asm
0x180033a0c  push    rbx
0x180033a0e  push    rbp
0x180033a0f  push    rsi
0x180033a10  push    rdi
0x180033a11  push    r13
0x180033a13  push    r14
0x180033a15  push    r15
0x180033a17  sub     rsp, 90h
0x180033a1e  mov     r14b, r9b
0x180033a21  mov     r15, r8
0x180033a24  mov     rbx, rdx
0x180033a27  mov     rsi, rcx
0x180033a2a  lea     r13, WPP_GLOBAL_Control
0x180033a31  mov     rcx, cs:WPP_GLOBAL_Control
0x180033a38  cmp     rcx, r13
0x180033a3b  jz      short loc_180033A5E
0x180033a3d  test    byte ptr [rcx+1Ch], 1
0x180033a41  jz      short loc_180033A5E
0x180033a43  cmp     byte ptr [rcx+19h], 5
0x180033a47  jb      short loc_180033A5E
0x180033a49  mov     edx, 181h
0x180033a4e  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180033a55  mov     rcx, [rcx+10h]
0x180033a59  call    WPP_SF_
0x180033a5e  xor     edx, edx
0x180033a60  lea     r8d, [rdx+64h]
0x180033a64  lea     rcx, [rsp+0C8h+var_98]
0x180033a69  call    cs:__imp_??0CWStringArray@@QEAA@HH@Z; CWStringArray::CWStringArray(int,int)
0x180033a6f  nop
0x180033a70  mov     ebp, [rsp+0C8h+arg_20]
0x180033a77  mov     r9d, ebp; unsigned int
0x180033a7a  lea     r8, [rsp+0C8h+var_98]; struct CWStringArray *
0x180033a7f  mov     rdx, rbx; unsigned __int16 *
0x180033a82  mov     rcx, rsi; this
0x180033a85  call    ?GetChildHashes@CNamespaceHandle@@IEAAJPEBGAEAVCWStringArray@@K@Z; CNamespaceHandle::GetChildHashes(ushort const *,CWStringArray &,ulong)
0x180033a8a  mov     ebx, eax
0x180033a8c  test    eax, eax
0x180033a8e  jns     short loc_180033ACC
0x180033a90  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180033a96  mov     edx, ebx
0x180033a98  mov     rcx, rax
0x180033a9b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180033aa1  mov     rcx, cs:WPP_GLOBAL_Control
0x180033aa8  cmp     rcx, r13
0x180033aab  jz      loc_180033B5E
0x180033ab1  test    byte ptr [rcx+1Ch], 1
0x180033ab5  jz      loc_180033B5E
0x180033abb  cmp     byte ptr [rcx+19h], 2
0x180033abf  jb      loc_180033B5E
0x180033ac5  mov     edx, 182h
0x180033aca  jmp     short loc_180033B47
0x180033acc  xor     edi, edi
0x180033ace  lea     rcx, [rsp+0C8h+var_98]
0x180033ad3  call    cs:__imp_?Size@CWStringArray@@QEBAHXZ; CWStringArray::Size(void)
0x180033ad9  cmp     edi, eax
0x180033adb  jge     short loc_180033B5C
0x180033add  mov     edx, edi
0x180033adf  lea     rcx, [rsp+0C8h+var_98]
0x180033ae4  call    cs:__imp_??ACWStringArray@@QEBAPEAGH@Z; CWStringArray::operator[](int)
0x180033aea  mov     rdx, rax; unsigned __int16 *
0x180033aed  mov     [rsp+0C8h+var_A8], ebp; unsigned int
0x180033af1  mov     r9b, r14b; bool
0x180033af4  mov     r8, r15; struct CEventCollector *
0x180033af7  mov     rcx, rsi; this
0x180033afa  call    ?DeleteClassByHash@CNamespaceHandle@@IEAAJPEBGAEAVCEventCollector@@_NK@Z; CNamespaceHandle::DeleteClassByHash(ushort const *,CEventCollector &,bool,ulong)
0x180033aff  mov     ebx, eax
0x180033b01  mov     eax, 80000000h
0x180033b06  lea     ecx, [rbx+rax]
0x180033b09  test    eax, ecx
0x180033b0b  jnz     short loc_180033B15
0x180033b0d  cmp     ebx, 80041002h
0x180033b13  jnz     short loc_180033B19
0x180033b15  inc     edi
0x180033b17  jmp     short loc_180033ACE
0x180033b19  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180033b1f  mov     edx, ebx
0x180033b21  mov     rcx, rax
0x180033b24  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180033b2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180033b31  cmp     rcx, r13
0x180033b34  jz      short loc_180033B5E
0x180033b36  test    byte ptr [rcx+1Ch], 1
0x180033b3a  jz      short loc_180033B5E
0x180033b3c  cmp     byte ptr [rcx+19h], 2
0x180033b40  jb      short loc_180033B5E
0x180033b42  mov     edx, 183h
0x180033b47  mov     r9d, ebx
0x180033b4a  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180033b51  mov     rcx, [rcx+10h]
0x180033b55  call    WPP_SF_d
0x180033b5a  jmp     short loc_180033B5E
0x180033b5c  xor     ebx, ebx
0x180033b5e  lea     rcx, [rsp+0C8h+var_98]
0x180033b63  call    cs:__imp_??1CWStringArray@@QEAA@XZ; CWStringArray::~CWStringArray(void)
0x180033b69  mov     eax, ebx
0x180033b6b  add     rsp, 90h
0x180033b72  pop     r15
0x180033b74  pop     r14
0x180033b76  pop     r13
0x180033b78  pop     rdi
0x180033b79  pop     rsi
0x180033b7a  pop     rbp
0x180033b7b  pop     rbx
0x180033b7c  retn
```
