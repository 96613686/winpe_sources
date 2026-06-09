# _CopyCollection_CCommand_

- ea: `0x18000160c`
- end: `0x180001746`
- name: `_CopyCollection_CCommand_`
- size: `314`
- prototype: `__int64 __fastcall(CStdCollection *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180001c98`

## callees

- `0x18000160c`
- `0x180002840`
- `0x180057c10`
- `0x18005b724`
- `0x1800cdaea`
- `0x1800d0010`

## import_xrefs

- `MSDART!?ReadLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180001637`
- `MSDART!?ReadLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180001637`
- `MSDART!?ReadUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180001722`
- `MSDART!?ReadUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180001722`
- `MSDART!MpHeapAlloc` at `0x180001684`
- `MSDART!MpHeapAlloc` at `0x180001684`

## pseudocode

```c
__int64 __fastcall CopyCollection_CCommand_(CStdCollection *this, _QWORD *a2, unsigned int *a3)
{
  unsigned int Element; // ebx
  unsigned int Count; // eax
  unsigned int v7; // esi
  _QWORD *v8; // rax
  _QWORD *v9; // rdi
  __int64 i; // rbp
  size_t v11; // rax
  size_t Size; // [rsp+60h] [rbp+8h] BYREF
  _QWORD *v14; // [rsp+68h] [rbp+10h]

  v14 = a2;
  Element = 0;
  *a2 = 0;
  *a3 = 0;
  CReaderWriterLock3AR::ReadLock((CStdCollection *)((char *)this + 72));
  Count = CStdCollection::GetCount(this);
  v7 = Count;
  if ( Count )
  {
    Size = 0;
    Element = ULongLongMult(Count, 8u, &Size);
    if ( !Element )
    {
      v8 = (_QWORD *)MpHeapAlloc(g_hHeapHandle, 10485760, Size);
      v9 = v8;
      if ( v8 )
      {
        memset_0(v8, 0, Size);
        for ( i = 0; (unsigned int)i < v7; i = (unsigned int)(i + 1) )
        {
          Size = 0;
          Element = CStdCollection::GetElement(this, (unsigned int)i, (struct CStdComObjectRoot **)&Size);
          v11 = Size;
          if ( Size )
            v11 = Size - 32;
          v9[i] = v11;
          if ( v11
            && (*(_DWORD *)(v11 + 80)
             || !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)(v9[i] + 32LL) + 80LL))(v9[i] + 32LL)) )
          {
            v9[i] = 0;
          }
        }
        *v14 = v9;
        *a3 = v7;
      }
      else
      {
        Element = -2147024882;
      }
    }
  }
  CReaderWriterLock3AR::ReadUnlock((CStdCollection *)((char *)this + 72));
  return Element;
}

```

## disassembly

```asm
0x18000160c  mov     [rsp+arg_10], rbx
0x180001611  mov     [rsp+arg_8], rdx
0x180001616  push    rbp
0x180001617  push    rsi
0x180001618  push    rdi
0x180001619  push    r12
0x18000161b  push    r13
0x18000161d  push    r14
0x18000161f  push    r15
0x180001621  sub     rsp, 20h
0x180001625  xor     ebx, ebx
0x180001627  mov     r13, rcx
0x18000162a  mov     [rdx], rbx
0x18000162d  add     rcx, 48h ; 'H'
0x180001631  mov     [r8], ebx
0x180001634  mov     r12, r8
0x180001637  call    cs:__imp_?ReadLock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::ReadLock(void)
0x18000163e  nop     dword ptr [rax+rax+00h]
0x180001643  mov     rcx, r13; this
0x180001646  call    ?GetCount@CStdCollection@@UEAAKXZ; CStdCollection::GetCount(void)
0x18000164b  mov     esi, eax
0x18000164d  test    eax, eax
0x18000164f  jz      loc_18000171E
0x180001655  mov     ecx, esi; unsigned __int64
0x180001657  mov     [rsp+58h+Size], rbx
0x18000165c  lea     r8, [rsp+58h+Size]; unsigned __int64 *
0x180001661  lea     edx, [rbx+8]; unsigned __int64
0x180001664  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180001669  mov     ebx, eax
0x18000166b  test    eax, eax
0x18000166d  jnz     loc_18000171E
0x180001673  mov     r8, [rsp+58h+Size]
0x180001678  mov     edx, 0A00000h
0x18000167d  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180001684  call    cs:__imp_MpHeapAlloc
0x18000168b  nop     dword ptr [rax+rax+00h]
0x180001690  mov     rdi, rax
0x180001693  test    rax, rax
0x180001696  jnz     short loc_18000169F
0x180001698  mov     ebx, 8007000Eh
0x18000169d  jmp     short loc_18000171E
0x18000169f  mov     r8, [rsp+58h+Size]; Size
0x1800016a4  xor     edx, edx; Val
0x1800016a6  mov     rcx, rdi; void *
0x1800016a9  call    memset_0
0x1800016ae  xor     ebp, ebp
0x1800016b0  test    esi, esi
0x1800016b2  jz      short loc_180001712
0x1800016b4  lea     r8, [rsp+58h+Size]; struct CStdComObjectRoot **
0x1800016b9  mov     edx, ebp; unsigned __int64
0x1800016bb  mov     rcx, r13; this
0x1800016be  mov     [rsp+58h+Size], 0
0x1800016c7  call    ?GetElement@CStdCollection@@QEAAJ_KPEAPEAVCStdComObjectRoot@@@Z; CStdCollection::GetElement(unsigned __int64,CStdComObjectRoot * *)
0x1800016cc  mov     ebx, eax
0x1800016ce  mov     rax, [rsp+58h+Size]
0x1800016d3  test    rax, rax
0x1800016d6  jz      short loc_1800016DC
0x1800016d8  add     rax, 0FFFFFFFFFFFFFFE0h
0x1800016dc  mov     [rdi+rbp*8], rax
0x1800016e0  test    rax, rax
0x1800016e3  jz      short loc_18000170C
0x1800016e5  mov     eax, [rax+50h]
0x1800016e8  test    eax, eax
0x1800016ea  jnz     short loc_180001704
0x1800016ec  mov     rcx, [rdi+rbp*8]
0x1800016f0  add     rcx, 20h ; ' '
0x1800016f4  mov     rax, [rcx]
0x1800016f7  mov     rax, [rax+50h]
0x1800016fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001700  test    eax, eax
0x180001702  jnz     short loc_18000170C
0x180001704  mov     qword ptr [rdi+rbp*8], 0
0x18000170c  inc     ebp
0x18000170e  cmp     ebp, esi
0x180001710  jb      short loc_1800016B4
0x180001712  mov     rax, [rsp+58h+arg_8]
0x180001717  mov     [rax], rdi
0x18000171a  mov     [r12], esi
0x18000171e  lea     rcx, [r13+48h]
0x180001722  call    cs:__imp_?ReadUnlock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::ReadUnlock(void)
0x180001729  nop     dword ptr [rax+rax+00h]
0x18000172e  mov     eax, ebx
0x180001730  mov     rbx, [rsp+58h+arg_10]
0x180001735  add     rsp, 20h
0x180001739  pop     r15
0x18000173b  pop     r14
0x18000173d  pop     r13
0x18000173f  pop     r12
0x180001741  pop     rdi
0x180001742  pop     rsi
0x180001743  pop     rbp
0x180001744  retn
```
