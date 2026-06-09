# CNamespaceHandle::DeleteObjectByPath(ulong,ushort const *,CEventCollector &)

- ea: `0x18001c67c`
- end: `0x18001c892`
- name: `?DeleteObjectByPath@CNamespaceHandle@@QEAAJKPEBGAEAVCEventCollector@@@Z`
- size: `534`
- prototype: `__int64 __fastcall(CNamespaceHandle *this, __int16, const unsigned __int16 *, struct CEventCollector *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001c070`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x180004310`
- `0x180014290`
- `0x18001c67c`
- `0x180025180`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001c70b`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001c70b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001c80b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001c843`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001c84d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001c866`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001c870`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001c80b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001c843`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001c84d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001c866`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001c870`
- `wbemcomn!GetMemLogObject` at `0x18001c719`
- `wbemcomn!GetMemLogObject` at `0x18001c7bf`
- `wbemcomn!GetMemLogObject` at `0x18001c719`
- `wbemcomn!GetMemLogObject` at `0x18001c7bf`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001c729`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001c7ca`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001c729`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001c7ca`

## pseudocode

```c
__int64 __fastcall CNamespaceHandle::DeleteObjectByPath(
        CNamespaceHandle *this,
        __int16 a2,
        const unsigned __int16 *a3,
        struct CEventCollector *a4)
{
  bool v8; // bp
  __int64 v9; // rax
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rbx
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // rsi
  CMemoryLog *v14; // rax
  int v15; // ebx
  CMemoryLog *MemLogObject; // rax
  unsigned __int16 *v17; // rdi
  unsigned __int16 *v19[4]; // [rsp+40h] [rbp-48h] BYREF
  bool v20; // [rsp+98h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 308, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
  }
  v8 = (a2 & 0x1000) != 0;
  v9 = -1;
  do
    ++v9;
  while ( a3[v9] );
  v10 = v9 + 1;
  if ( v10 <= 2 )
    LODWORD(v10) = 2;
  v11 = (unsigned int)v10;
  v12 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((unsigned int)v10, 2u));
  v13 = v12;
  if ( v12 )
  {
    v19[1] = v12;
    v20 = 0;
    v19[0] = 0;
    v15 = CNamespaceHandle::ComputeKeyFromPath(this, a3, v12, v11, v19, &v20, 0);
    if ( v15 >= 0 )
    {
      v17 = v19[0];
      v19[2] = v19[0];
      if ( v20 )
        v15 = CNamespaceHandle::DeleteClass(this, v19[0], a4, v8, 0);
      else
        v15 = CNamespaceHandle::DeleteInstance(this, v19[0], v13, a4);
      CWin32DefaultArena::WbemMemFree(v17);
      CWin32DefaultArena::WbemMemFree(v13);
    }
    else
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v15);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          310,
          WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
          (unsigned int)v15);
      }
      CWin32DefaultArena::WbemMemFree(v13);
    }
  }
  else
  {
    v14 = GetMemLogObject();
    v15 = -2147217402;
    CMemoryLog::Write(v14, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 309, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749894LL);
    }
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18001c67c  mov     [rsp+arg_0], rbx
0x18001c681  mov     [rsp+arg_10], rbp
0x18001c686  push    rsi
0x18001c687  push    rdi
0x18001c688  push    r13
0x18001c68a  push    r14
0x18001c68c  push    r15
0x18001c68e  sub     rsp, 60h
0x18001c692  mov     r15, r9
0x18001c695  mov     rdi, r8
0x18001c698  mov     ebp, edx
0x18001c69a  mov     r14, rcx
0x18001c69d  lea     rax, WPP_GLOBAL_Control
0x18001c6a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c6ab  cmp     rcx, rax
0x18001c6ae  jz      short loc_18001C6D1
0x18001c6b0  test    byte ptr [rcx+1Ch], 1
0x18001c6b4  jz      short loc_18001C6D1
0x18001c6b6  cmp     byte ptr [rcx+19h], 5
0x18001c6ba  jb      short loc_18001C6D1
0x18001c6bc  mov     edx, 134h
0x18001c6c1  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18001c6c8  mov     rcx, [rcx+10h]
0x18001c6cc  call    WPP_SF_
0x18001c6d1  shr     ebp, 0Ch
0x18001c6d4  and     bpl, 1
0x18001c6d8  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001c6dc  mov     rax, rcx
0x18001c6df  xor     r13d, r13d
0x18001c6e2  inc     rax
0x18001c6e5  cmp     [rdi+rax*2], r13w
0x18001c6ea  jnz     short loc_18001C6E2
0x18001c6ec  inc     rax
0x18001c6ef  cmp     rax, 2
0x18001c6f3  ja      short loc_18001C6FA
0x18001c6f5  mov     eax, 2
0x18001c6fa  mov     ebx, eax
0x18001c6fc  mov     eax, 2
0x18001c701  mul     rbx
0x18001c704  cmovb   rax, rcx
0x18001c708  mov     rcx, rax
0x18001c70b  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001c711  mov     rsi, rax
0x18001c714  test    rax, rax
0x18001c717  jnz     short loc_18001C77A
0x18001c719  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001c71f  mov     ebx, 80041006h
0x18001c724  mov     edx, ebx
0x18001c726  mov     rcx, rax
0x18001c729  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001c72f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c736  lea     rax, WPP_GLOBAL_Control
0x18001c73d  cmp     rcx, rax
0x18001c740  jz      loc_18001C877
0x18001c746  test    byte ptr [rcx+1Ch], 1
0x18001c74a  jz      loc_18001C877
0x18001c750  cmp     byte ptr [rcx+19h], 2
0x18001c754  jb      loc_18001C877
0x18001c75a  mov     edx, 135h
0x18001c75f  mov     r9d, 80041006h
0x18001c765  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18001c76c  mov     rcx, [rcx+10h]
0x18001c770  call    WPP_SF_d
0x18001c775  jmp     loc_18001C877
0x18001c77a  mov     [rsp+88h+var_40], rsi
0x18001c77f  mov     [rsp+88h+arg_8], r13b
0x18001c787  mov     [rsp+88h+var_48], r13
0x18001c78c  mov     [rsp+88h+var_58], r13; unsigned __int16 **
0x18001c791  lea     rax, [rsp+88h+arg_8]
0x18001c799  mov     [rsp+88h+var_60], rax; bool *
0x18001c79e  lea     rax, [rsp+88h+var_48]
0x18001c7a3  mov     [rsp+88h+var_68], rax; unsigned __int16 **
0x18001c7a8  mov     r9, rbx; unsigned __int64
0x18001c7ab  mov     r8, rsi; unsigned __int16 *
0x18001c7ae  mov     rdx, rdi; unsigned __int16 *
0x18001c7b1  mov     rcx, r14; this
0x18001c7b4  call    ?ComputeKeyFromPath@CNamespaceHandle@@IEAAJPEBGPEAG_KPEAPEAGPEA_N3@Z; CNamespaceHandle::ComputeKeyFromPath(ushort const *,ushort *,unsigned __int64,ushort * *,bool *,ushort * *)
0x18001c7b9  mov     ebx, eax
0x18001c7bb  test    eax, eax
0x18001c7bd  jns     short loc_18001C814
0x18001c7bf  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001c7c5  mov     edx, ebx
0x18001c7c7  mov     rcx, rax
0x18001c7ca  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001c7d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c7d7  lea     rax, WPP_GLOBAL_Control
0x18001c7de  cmp     rcx, rax
0x18001c7e1  jz      short loc_18001C808
0x18001c7e3  test    byte ptr [rcx+1Ch], 1
0x18001c7e7  jz      short loc_18001C808
0x18001c7e9  cmp     byte ptr [rcx+19h], 2
0x18001c7ed  jb      short loc_18001C808
0x18001c7ef  mov     edx, 136h
0x18001c7f4  mov     r9d, ebx
0x18001c7f7  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18001c7fe  mov     rcx, [rcx+10h]
0x18001c802  call    WPP_SF_d
0x18001c807  nop
0x18001c808  mov     rcx, rsi
0x18001c80b  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18001c811  nop
0x18001c812  jmp     short loc_18001C877
0x18001c814  mov     rdi, [rsp+88h+var_48]
0x18001c819  mov     [rsp+88h+var_38], rdi
0x18001c81e  mov     rdx, rdi; unsigned __int16 *
0x18001c821  mov     rcx, r14; this
0x18001c824  cmp     [rsp+88h+arg_8], r13b
0x18001c82c  jz      short loc_18001C856
0x18001c82e  mov     dword ptr [rsp+88h+var_68], r13d; unsigned int
0x18001c833  mov     r9b, bpl; bool
0x18001c836  mov     r8, r15; struct CEventCollector *
0x18001c839  call    ?DeleteClass@CNamespaceHandle@@IEAAJPEBGAEAVCEventCollector@@_NK@Z; CNamespaceHandle::DeleteClass(ushort const *,CEventCollector &,bool,ulong)
0x18001c83e  mov     ebx, eax
0x18001c840  mov     rcx, rdi
0x18001c843  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18001c849  nop
0x18001c84a  mov     rcx, rsi
0x18001c84d  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18001c853  nop
0x18001c854  jmp     short loc_18001C877
0x18001c856  mov     r9, r15; struct CEventCollector *
0x18001c859  mov     r8, rsi; unsigned __int16 *
0x18001c85c  call    ?DeleteInstance@CNamespaceHandle@@IEAAJPEBG0AEAVCEventCollector@@@Z; CNamespaceHandle::DeleteInstance(ushort const *,ushort const *,CEventCollector &)
0x18001c861  mov     ebx, eax
0x18001c863  mov     rcx, rdi
0x18001c866  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18001c86c  nop
0x18001c86d  mov     rcx, rsi
0x18001c870  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18001c876  nop
0x18001c877  mov     eax, ebx
0x18001c879  lea     r11, [rsp+88h+var_28]
0x18001c87e  mov     rbx, [r11+30h]
0x18001c882  mov     rbp, [r11+40h]
0x18001c886  mov     rsp, r11
0x18001c889  pop     r15
0x18001c88b  pop     r14
0x18001c88d  pop     r13
0x18001c88f  pop     rdi
0x18001c890  pop     rsi
0x18001c891  retn
```
