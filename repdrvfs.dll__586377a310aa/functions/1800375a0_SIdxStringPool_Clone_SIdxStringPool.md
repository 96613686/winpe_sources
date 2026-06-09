# SIdxStringPool::Clone(SIdxStringPool * *)

- ea: `0x1800375a0`
- end: `0x180037741`
- name: `?Clone@SIdxStringPool@@QEAAKPEAPEAU1@@Z`
- size: `417`
- prototype: `__int64 __fastcall(const void **this, struct SIdxStringPool **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180037278`

## callees

- `0x1800012b8`
- `0x18000fcf0`
- `0x1800225c0`
- `0x18002b7b6`
- `0x1800375a0`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800375ba`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800375ba`
- `wbemcomn!GetMemLogObject` at `0x18003760c`
- `wbemcomn!GetMemLogObject` at `0x180037687`
- `wbemcomn!GetMemLogObject` at `0x1800376e4`
- `wbemcomn!GetMemLogObject` at `0x18003760c`
- `wbemcomn!GetMemLogObject` at `0x180037687`
- `wbemcomn!GetMemLogObject` at `0x1800376e4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003761c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180037697`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800376f4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003761c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180037697`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800376f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SIdxStringPool::Clone(const void **this, struct SIdxStringPool **a2)
{
  _OWORD *v4; // rax
  _OWORD *v5; // rbx
  void *v6; // rax
  CMemoryLog *v7; // rax
  CVarObjHeap *v8; // rcx
  __int64 v9; // rdx
  void *v10; // rax
  CMemoryLog *v11; // rax
  __int64 result; // rax
  CMemoryLog *MemLogObject; // rax

  v4 = CWin32DefaultArena::WbemMemAlloc(0x30u);
  v5 = v4;
  if ( !v4 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, 8);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 8;
    }
    v9 = 71;
    goto LABEL_17;
  }
  *v4 = 0;
  v4[1] = 0;
  v4[2] = 0;
  *((_BYTE *)v4 + 40) = 1;
  *(_DWORD *)v4 = *(_DWORD *)this;
  v6 = _BtrMemAlloc(2LL * *((unsigned int *)this + 4));
  *((_QWORD *)v5 + 1) = v6;
  if ( !v6 )
  {
    SIdxStringPool::`scalar deleting destructor'((SIdxStringPool *)v5);
    v7 = GetMemLogObject();
    CMemoryLog::Write(v7, 8);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 8;
    }
    v9 = 72;
    goto LABEL_17;
  }
  memcpy_0(v6, this[1], 2LL * *((unsigned int *)this + 4));
  *((_DWORD *)v5 + 4) = *((_DWORD *)this + 4);
  v10 = _BtrMemAlloc(*((unsigned int *)this + 8));
  *((_QWORD *)v5 + 3) = v10;
  if ( v10 )
  {
    memcpy_0(v10, this[3], *((unsigned int *)this + 8));
    *((_DWORD *)v5 + 8) = *((_DWORD *)this + 8);
    *((_DWORD *)v5 + 9) = *((_DWORD *)this + 9);
    result = 0;
    *a2 = (struct SIdxStringPool *)v5;
    return result;
  }
  SIdxStringPool::`scalar deleting destructor'((SIdxStringPool *)v5);
  v11 = GetMemLogObject();
  CMemoryLog::Write(v11, 8);
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v9 = 73;
LABEL_17:
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, 8);
  }
  return 8;
}

```

## disassembly

```asm
0x1800375a0  mov     [rsp+arg_0], rbx
0x1800375a5  mov     [rsp+arg_8], rsi
0x1800375aa  push    rdi
0x1800375ab  sub     rsp, 20h
0x1800375af  mov     rdi, rcx
0x1800375b2  mov     rsi, rdx
0x1800375b5  mov     ecx, 30h ; '0'
0x1800375ba  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800375c0  mov     [rsp+28h+arg_10], rax
0x1800375c5  mov     rbx, rax
0x1800375c8  test    rax, rax
0x1800375cb  jz      loc_1800376E4
0x1800375d1  xorps   xmm0, xmm0
0x1800375d4  movups  xmmword ptr [rax], xmm0
0x1800375d7  movups  xmmword ptr [rax+10h], xmm0
0x1800375db  movups  xmmword ptr [rax+20h], xmm0
0x1800375df  mov     byte ptr [rax+28h], 1
0x1800375e3  test    rax, rax
0x1800375e6  jz      loc_1800376E4
0x1800375ec  mov     eax, [rdi]
0x1800375ee  mov     [rbx], eax
0x1800375f0  mov     ecx, [rdi+10h]
0x1800375f3  add     rcx, rcx; unsigned __int64
0x1800375f6  call    ?_BtrMemAlloc@@YAPEAX_K@Z; _BtrMemAlloc(unsigned __int64)
0x1800375fb  mov     [rbx+8], rax
0x1800375ff  test    rax, rax
0x180037602  jnz     short loc_180037655
0x180037604  mov     rcx, rbx; this
0x180037607  call    ??_GSIdxStringPool@@QEAAPEAXI@Z; SIdxStringPool::`scalar deleting destructor'(uint)
0x18003760c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180037612  mov     ebx, 8
0x180037617  mov     rcx, rax
0x18003761a  mov     edx, ebx
0x18003761c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180037622  mov     rcx, cs:WPP_GLOBAL_Control
0x180037629  lea     rax, WPP_GLOBAL_Control
0x180037630  cmp     rcx, rax
0x180037633  jz      loc_18003772F
0x180037639  test    byte ptr [rcx+1Ch], 1
0x18003763d  jz      loc_18003772F
0x180037643  cmp     byte ptr [rcx+19h], 2
0x180037647  jb      loc_18003772F
0x18003764d  lea     edx, [rbx+40h]
0x180037650  jmp     loc_18003771C
0x180037655  mov     r8d, [rdi+10h]
0x180037659  mov     rcx, rax; void *
0x18003765c  mov     rdx, [rdi+8]; Src
0x180037660  add     r8, r8; Size
0x180037663  call    memcpy_0
0x180037668  mov     eax, [rdi+10h]
0x18003766b  mov     [rbx+10h], eax
0x18003766e  mov     ecx, [rdi+20h]; unsigned __int64
0x180037671  call    ?_BtrMemAlloc@@YAPEAX_K@Z; _BtrMemAlloc(unsigned __int64)
0x180037676  mov     [rbx+18h], rax
0x18003767a  test    rax, rax
0x18003767d  jnz     short loc_1800376C1
0x18003767f  mov     rcx, rbx; this
0x180037682  call    ??_GSIdxStringPool@@QEAAPEAXI@Z; SIdxStringPool::`scalar deleting destructor'(uint)
0x180037687  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003768d  mov     ebx, 8
0x180037692  mov     rcx, rax
0x180037695  mov     edx, ebx
0x180037697  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003769d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800376a4  lea     rax, WPP_GLOBAL_Control
0x1800376ab  cmp     rcx, rax
0x1800376ae  jz      short loc_18003772F
0x1800376b0  test    byte ptr [rcx+1Ch], 1
0x1800376b4  jz      short loc_18003772F
0x1800376b6  cmp     byte ptr [rcx+19h], 2
0x1800376ba  jb      short loc_18003772F
0x1800376bc  lea     edx, [rbx+41h]
0x1800376bf  jmp     short loc_18003771C
0x1800376c1  mov     r8d, [rdi+20h]; Size
0x1800376c5  mov     rcx, rax; void *
0x1800376c8  mov     rdx, [rdi+18h]; Src
0x1800376cc  call    memcpy_0
0x1800376d1  mov     eax, [rdi+20h]
0x1800376d4  mov     [rbx+20h], eax
0x1800376d7  mov     eax, [rdi+24h]
0x1800376da  mov     [rbx+24h], eax
0x1800376dd  xor     eax, eax
0x1800376df  mov     [rsi], rbx
0x1800376e2  jmp     short loc_180037731
0x1800376e4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800376ea  mov     ebx, 8
0x1800376ef  mov     rcx, rax
0x1800376f2  mov     edx, ebx
0x1800376f4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800376fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180037701  lea     rax, WPP_GLOBAL_Control
0x180037708  cmp     rcx, rax
0x18003770b  jz      short loc_18003772F
0x18003770d  test    byte ptr [rcx+1Ch], 1
0x180037711  jz      short loc_18003772F
0x180037713  cmp     byte ptr [rcx+19h], 2
0x180037717  jb      short loc_18003772F
0x180037719  lea     edx, [rbx+3Fh]
0x18003771c  mov     rcx, [rcx+10h]
0x180037720  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x180037727  mov     r9d, ebx
0x18003772a  call    WPP_SF_d
0x18003772f  mov     eax, ebx
0x180037731  mov     rbx, [rsp+28h+arg_0]
0x180037736  mov     rsi, [rsp+28h+arg_8]
0x18003773b  add     rsp, 20h
0x18003773f  pop     rdi
0x180037740  retn
```
