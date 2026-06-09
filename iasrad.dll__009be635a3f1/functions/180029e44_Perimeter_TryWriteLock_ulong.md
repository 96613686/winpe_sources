# Perimeter::TryWriteLock(ulong)

- ea: `0x180029e44`
- end: `0x180029edd`
- name: `?TryWriteLock@Perimeter@@AEAAHK@Z`
- size: `153`
- prototype: `__int64 __fastcall(Perimeter *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180029d20`

## callees

- `0x1800299f4`
- `0x180029c34`
- `0x180029c74`
- `0x180029e44`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180029e65`
- `KERNEL32!EnterCriticalSection` at `0x180029e65`
- `KERNEL32!LeaveCriticalSection` at `0x180029ec8`
- `KERNEL32!LeaveCriticalSection` at `0x180029ec8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Perimeter::TryWriteLock(Perimeter *this, unsigned int a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbp
  __int64 v5; // r8
  unsigned int v6; // edi
  int v7; // esi
  char v9; // [rsp+20h] [rbp-38h]
  _BYTE v10[40]; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v11; // [rsp+68h] [rbp+10h] BYREF

  v11 = a2;
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( (unsigned int)Perimeter::HasReadLock(this, a2) )
  {
    v6 = 0;
  }
  else
  {
    v7 = *((_DWORD *)this + 18);
    if ( !v7 || v7 < 0 && (unsigned int)Perimeter::HasWriteLock(this, a2) )
    {
      v6 = 1;
      *((_DWORD *)this + 18) = v7 - 1;
      v9 = byte_180041EF9;
      std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,1>>::_Insert_nohint<unsigned long const &,std::_Nil>(
        (char *)this + 80,
        v10,
        v5,
        &v11,
        v9);
    }
    else
    {
      v6 = 0;
      ++*((_DWORD *)this + 17);
    }
  }
  LeaveCriticalSection(v4);
  return v6;
}

```

## disassembly

```asm
0x180029e44  mov     [rsp+arg_10], rbx
0x180029e49  mov     [rsp+arg_8], edx
0x180029e4d  push    rbp
0x180029e4e  push    rsi
0x180029e4f  push    rdi
0x180029e50  sub     rsp, 40h
0x180029e54  mov     edi, edx
0x180029e56  mov     rbx, rcx
0x180029e59  lea     rbp, [rcx+8]
0x180029e5d  mov     [rsp+58h+arg_0], rbp
0x180029e62  mov     rcx, rbp; lpCriticalSection
0x180029e65  call    cs:__imp_EnterCriticalSection
0x180029e6b  nop
0x180029e6c  mov     edx, edi; unsigned int
0x180029e6e  mov     rcx, rbx; this
0x180029e71  call    ?HasReadLock@Perimeter@@AEAAHK@Z; Perimeter::HasReadLock(ulong)
0x180029e76  test    eax, eax
0x180029e78  jz      short loc_180029E7E
0x180029e7a  xor     edi, edi
0x180029e7c  jmp     short loc_180029EC5
0x180029e7e  mov     esi, [rbx+48h]
0x180029e81  test    esi, esi
0x180029e83  jz      short loc_180029E9C
0x180029e85  jns     short loc_180029E95
0x180029e87  mov     edx, edi; unsigned int
0x180029e89  mov     rcx, rbx; this
0x180029e8c  call    ?HasWriteLock@Perimeter@@AEAAHK@Z; Perimeter::HasWriteLock(ulong)
0x180029e91  test    eax, eax
0x180029e93  jnz     short loc_180029E9C
0x180029e95  xor     edi, edi
0x180029e97  inc     dword ptr [rbx+44h]
0x180029e9a  jmp     short loc_180029EC5
0x180029e9c  mov     edi, 1
0x180029ea1  lea     eax, [rsi-1]
0x180029ea4  mov     [rbx+48h], eax
0x180029ea7  lea     rcx, [rbx+50h]
0x180029eab  mov     dl, cs:byte_180041EF9
0x180029eb1  mov     [rsp+58h+var_38], dl
0x180029eb5  lea     r9, [rsp+58h+arg_8]
0x180029eba  lea     rdx, [rsp+58h+var_28]
0x180029ebf  call    ??$_Insert_nohint@AEBKU_Nil@std@@@?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$00@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@K@std@@@std@@@std@@_N@1@_NAEBKU_Nil@1@@Z; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,1>>::_Insert_nohint<ulong const &,std::_Nil>(bool,ulong const &,std::_Nil)
0x180029ec4  nop
0x180029ec5  mov     rcx, rbp; lpCriticalSection
0x180029ec8  call    cs:__imp_LeaveCriticalSection
0x180029ece  mov     eax, edi
0x180029ed0  mov     rbx, [rsp+58h+arg_10]
0x180029ed5  add     rsp, 40h
0x180029ed9  pop     rdi
0x180029eda  pop     rsi
0x180029edb  pop     rbp
0x180029edc  retn
```
