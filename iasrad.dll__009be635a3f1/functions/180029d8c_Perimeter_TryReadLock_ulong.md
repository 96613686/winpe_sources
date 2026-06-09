# Perimeter::TryReadLock(ulong)

- ea: `0x180029d8c`
- end: `0x180029e3e`
- name: `?TryReadLock@Perimeter@@AEAAHK@Z`
- size: `178`
- prototype: `__int64 __fastcall(Perimeter *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180029cb4`

## callees

- `0x1800299f4`
- `0x180029c34`
- `0x180029c74`
- `0x180029d8c`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180029dad`
- `KERNEL32!EnterCriticalSection` at `0x180029dad`
- `KERNEL32!LeaveCriticalSection` at `0x180029e29`
- `KERNEL32!LeaveCriticalSection` at `0x180029e29`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_BOOL8 __fastcall Perimeter::TryReadLock(Perimeter *this, unsigned int a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  int v5; // ebp
  __int64 v6; // r8
  BOOL v7; // edi
  _BYTE v9[40]; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v10; // [rsp+68h] [rbp+10h] BYREF

  v10 = a2;
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v5 = Perimeter::HasWriteLock(this, a2);
  v7 = (unsigned int)Perimeter::HasWriteLock(this, a2)
    || (unsigned int)Perimeter::HasReadLock(this, a2)
    || !*((_DWORD *)this + 17) && *((int *)this + 18) >= 0;
  if ( v5 )
  {
    --*((_DWORD *)this + 18);
    if ( v7 )
      goto LABEL_13;
  }
  else
  {
    if ( v7 )
    {
      ++*((_DWORD *)this + 18);
LABEL_13:
      std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,1>>::_Insert_nohint<unsigned long const &,std::_Nil>(
        (char *)this + 80,
        v9,
        v6,
        &v10,
        byte_180041EF9);
      goto LABEL_14;
    }
    ++*((_DWORD *)this + 16);
  }
LABEL_14:
  LeaveCriticalSection(v4);
  return v7;
}

```

## disassembly

```asm
0x180029d8c  mov     [rsp+arg_10], rbx
0x180029d91  mov     [rsp+arg_8], edx
0x180029d95  push    rbp
0x180029d96  push    rsi
0x180029d97  push    rdi
0x180029d98  sub     rsp, 40h
0x180029d9c  mov     edi, edx
0x180029d9e  mov     rbx, rcx
0x180029da1  lea     rsi, [rcx+8]
0x180029da5  mov     [rsp+58h+arg_0], rsi
0x180029daa  mov     rcx, rsi; lpCriticalSection
0x180029dad  call    cs:__imp_EnterCriticalSection
0x180029db3  nop
0x180029db4  mov     edx, edi; unsigned int
0x180029db6  mov     rcx, rbx; this
0x180029db9  call    ?HasWriteLock@Perimeter@@AEAAHK@Z; Perimeter::HasWriteLock(ulong)
0x180029dbe  mov     ebp, eax
0x180029dc0  mov     edx, edi; unsigned int
0x180029dc2  mov     rcx, rbx; this
0x180029dc5  call    ?HasWriteLock@Perimeter@@AEAAHK@Z; Perimeter::HasWriteLock(ulong)
0x180029dca  test    eax, eax
0x180029dcc  jnz     short loc_180029DEA
0x180029dce  mov     edx, edi; unsigned int
0x180029dd0  mov     rcx, rbx; this
0x180029dd3  call    ?HasReadLock@Perimeter@@AEAAHK@Z; Perimeter::HasReadLock(ulong)
0x180029dd8  test    eax, eax
0x180029dda  jnz     short loc_180029DEA
0x180029ddc  cmp     [rbx+44h], eax
0x180029ddf  jnz     short loc_180029DE6
0x180029de1  cmp     [rbx+48h], eax
0x180029de4  jge     short loc_180029DEA
0x180029de6  xor     edi, edi
0x180029de8  jmp     short loc_180029DEF
0x180029dea  mov     edi, 1
0x180029def  test    ebp, ebp
0x180029df1  jz      short loc_180029DFC
0x180029df3  dec     dword ptr [rbx+48h]
0x180029df6  test    edi, edi
0x180029df8  jz      short loc_180029E26
0x180029dfa  jmp     short loc_180029E08
0x180029dfc  test    edi, edi
0x180029dfe  jnz     short loc_180029E05
0x180029e00  inc     dword ptr [rbx+40h]
0x180029e03  jmp     short loc_180029E26
0x180029e05  inc     dword ptr [rbx+48h]
0x180029e08  lea     rcx, [rbx+50h]
0x180029e0c  mov     dl, cs:byte_180041EF9
0x180029e12  mov     [rsp+58h+var_38], dl
0x180029e16  lea     r9, [rsp+58h+arg_8]
0x180029e1b  lea     rdx, [rsp+58h+var_28]
0x180029e20  call    ??$_Insert_nohint@AEBKU_Nil@std@@@?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$00@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@K@std@@@std@@@std@@_N@1@_NAEBKU_Nil@1@@Z; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,1>>::_Insert_nohint<ulong const &,std::_Nil>(bool,ulong const &,std::_Nil)
0x180029e25  nop
0x180029e26  mov     rcx, rsi; lpCriticalSection
0x180029e29  call    cs:__imp_LeaveCriticalSection
0x180029e2f  mov     eax, edi
0x180029e31  mov     rbx, [rsp+58h+arg_10]
0x180029e36  add     rsp, 40h
0x180029e3a  pop     rdi
0x180029e3b  pop     rsi
0x180029e3c  pop     rbp
0x180029e3d  retn
```
