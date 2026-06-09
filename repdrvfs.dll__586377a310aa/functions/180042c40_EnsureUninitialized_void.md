# EnsureUninitialized(void)

- ea: `0x180042c40`
- end: `0x180042d25`
- name: `?EnsureUninitialized@@YAJXZ`
- size: `229`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180026150`

## callees

- `0x1800012b8`
- `0x180042b58`
- `0x180042c40`
- `0x180048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180042c77`
- `wbemcomn!GetMemLogObject` at `0x180042cc8`
- `wbemcomn!GetMemLogObject` at `0x180042c77`
- `wbemcomn!GetMemLogObject` at `0x180042cc8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180042c82`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180042cd4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180042c82`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180042cd4`

## pseudocode

```c
__int64 EnsureUninitialized(void)
{
  int v0; // ebx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v2; // rax

  if ( dword_180059C7C )
  {
    v0 = (*(__int64 (__fastcall **)(struct CComServer *))(*(_QWORD *)g_pServer + 8LL))(g_pServer);
    if ( v0 >= 0
      || (MemLogObject = GetMemLogObject(),
          CMemoryLog::Write(MemLogObject, v0),
          WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control)
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      EmptyList();
      if ( v0 >= 0 )
      {
LABEL_12:
        dword_180059C7C = 0;
        return (unsigned int)v0;
      }
    }
    else
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        47,
        WPP_caca780cf7163dbe62a4352f30d6adcd_Traceguids,
        (unsigned int)v0);
      EmptyList();
    }
    v2 = GetMemLogObject();
    CMemoryLog::Write(v2, -1);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_b1551c743f9f3b83c2bb722e23d745b2_Traceguids,
        (unsigned int)v0);
    }
    goto LABEL_12;
  }
  return 0;
}

```

## disassembly

```asm
0x180042c40  mov     [rsp+arg_0], rbx
0x180042c45  push    rdi
0x180042c46  sub     rsp, 20h
0x180042c4a  cmp     cs:dword_180059C7C, 0
0x180042c51  jz      loc_180042D18
0x180042c57  mov     rcx, cs:?g_pServer@@3PEAVCComServer@@EA; CComServer * g_pServer
0x180042c5e  mov     rax, [rcx]
0x180042c61  mov     rax, [rax+8]
0x180042c65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042c6a  lea     rdi, WPP_GLOBAL_Control
0x180042c71  mov     ebx, eax
0x180042c73  test    eax, eax
0x180042c75  jns     short loc_180042CBF
0x180042c77  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180042c7d  mov     rcx, rax
0x180042c80  mov     edx, ebx
0x180042c82  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180042c88  mov     rcx, cs:WPP_GLOBAL_Control
0x180042c8f  cmp     rcx, rdi
0x180042c92  jz      short loc_180042CBF
0x180042c94  test    byte ptr [rcx+1Ch], 1
0x180042c98  jz      short loc_180042CBF
0x180042c9a  cmp     byte ptr [rcx+19h], 2
0x180042c9e  jb      short loc_180042CBF
0x180042ca0  mov     rcx, [rcx+10h]
0x180042ca4  lea     r8, WPP_caca780cf7163dbe62a4352f30d6adcd_Traceguids
0x180042cab  mov     edx, 2Fh ; '/'
0x180042cb0  mov     r9d, ebx
0x180042cb3  call    WPP_SF_d
0x180042cb8  call    ?EmptyList@@YAXXZ; EmptyList(void)
0x180042cbd  jmp     short loc_180042CC8
0x180042cbf  call    ?EmptyList@@YAXXZ; EmptyList(void)
0x180042cc4  test    ebx, ebx
0x180042cc6  jns     short loc_180042D0A
0x180042cc8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180042cce  mov     rcx, rax
0x180042cd1  or      edx, 0FFFFFFFFh
0x180042cd4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180042cda  mov     rcx, cs:WPP_GLOBAL_Control
0x180042ce1  cmp     rcx, rdi
0x180042ce4  jz      short loc_180042D0A
0x180042ce6  test    byte ptr [rcx+1Ch], 1
0x180042cea  jz      short loc_180042D0A
0x180042cec  cmp     byte ptr [rcx+19h], 2
0x180042cf0  jb      short loc_180042D0A
0x180042cf2  mov     rcx, [rcx+10h]
0x180042cf6  lea     r8, WPP_b1551c743f9f3b83c2bb722e23d745b2_Traceguids
0x180042cfd  mov     edx, 0Bh
0x180042d02  mov     r9d, ebx
0x180042d05  call    WPP_SF_d
0x180042d0a  mov     cs:dword_180059C7C, 0
0x180042d14  mov     eax, ebx
0x180042d16  jmp     short loc_180042D1A
0x180042d18  xor     eax, eax
0x180042d1a  mov     rbx, [rsp+28h+arg_0]
0x180042d1f  add     rsp, 20h
0x180042d23  pop     rdi
0x180042d24  retn
```
