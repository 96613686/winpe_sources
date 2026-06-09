# CTabsArray::Cache(long const *,long)

- ea: `0x18004670c`
- end: `0x18004683f`
- name: `?Cache@CTabsArray@@QEAAJPEBJJ@Z`
- size: `307`
- prototype: `__int64 __fastcall(CTabsArray *__hidden this, void *Src, int)`
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x180046484`
- `0x1800526fc`
- `0x180086f80`
- `0x180088040`
- `0x18008c3d0`

## callees

- `0x18001e3e0`
- `0x1800274a0`
- `0x18004670c`
- `0x180047f5c`
- `0x180093ba6`
- `0x180093bbe`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180046732`
- `KERNEL32!EnterCriticalSection` at `0x180046732`
- `KERNEL32!LeaveCriticalSection` at `0x18004680b`
- `KERNEL32!LeaveCriticalSection` at `0x180046822`
- `KERNEL32!LeaveCriticalSection` at `0x18004680b`
- `KERNEL32!LeaveCriticalSection` at `0x180046822`

## pseudocode

```c
__int64 __fastcall CTabsArray::Cache(CTabsArray *this, void *Src, int a3)
{
  __int64 v3; // rbp
  int i; // ebx
  const void **v7; // rax
  __int64 v8; // rcx
  int v9; // eax
  unsigned int v10; // esi
  _QWORD *v11; // r14
  void *v12; // rax

  v3 = a3;
  if ( a3 > 0 )
  {
    EnterCriticalSection(&g_CriticalSection);
    for ( i = 0; ; ++i )
    {
      if ( i >= *((_DWORD *)this + 2) )
        goto LABEL_10;
      if ( *(int *)(*((_DWORD *)this + 4) * (i + 1) + *(_QWORD *)this - 4LL) > 0 )
      {
        v7 = (const void **)CArrayBase::Elem(this, i);
        if ( *(_DWORD *)v7 == (_DWORD)v3 && !memcmp_0(v7[1], Src, 4 * v3) )
          break;
      }
    }
    if ( i >= 0 )
    {
      v8 = *((_DWORD *)this + 4) * (i + 1);
      ++*(_DWORD *)(v8 + *(_QWORD *)this - 4);
LABEL_16:
      LeaveCriticalSection(&g_CriticalSection);
      return (unsigned int)i;
    }
LABEL_10:
    v9 = CFixArrayBase::Add(this);
    i = v9;
    if ( v9 >= 0 )
    {
      v10 = 4 * v3;
      v11 = CArrayBase::Elem(this, v9);
      if ( (unsigned int)(4 * v3) >= 4 && v10 >= (unsigned int)v3 && v10 <= 0x7FFFFFFF )
      {
        v12 = CW32System::PvAlloc(v10, 0);
        v11[1] = v12;
        if ( v12 )
        {
          memmove_0(v12, Src, (int)v10);
          *(_DWORD *)v11 = v3;
          *(_DWORD *)(*((_DWORD *)this + 4) * (i + 1) + *(_QWORD *)this - 4LL) = 1;
          goto LABEL_16;
        }
      }
    }
    LeaveCriticalSection(&g_CriticalSection);
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x18004670c  push    rbx
0x18004670e  push    rbp
0x18004670f  push    rsi
0x180046710  push    rdi
0x180046711  push    r14
0x180046713  push    r15
0x180046715  sub     rsp, 28h
0x180046719  movsxd  rbp, r8d
0x18004671c  mov     r15, rdx
0x18004671f  mov     rdi, rcx
0x180046722  test    r8d, r8d
0x180046725  jle     loc_18004682E
0x18004672b  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180046732  call    cs:__imp_EnterCriticalSection
0x180046739  nop     dword ptr [rax+rax+00h]
0x18004673e  xor     ebx, ebx
0x180046740  cmp     ebx, [rdi+8]
0x180046743  jge     short loc_180046799
0x180046745  lea     eax, [rbx+1]
0x180046748  imul    eax, [rdi+10h]
0x18004674c  movsxd  rcx, eax
0x18004674f  mov     rax, [rdi]
0x180046752  cmp     dword ptr [rcx+rax-4], 0
0x180046757  jle     short loc_18004677E
0x180046759  mov     edx, ebx; int
0x18004675b  mov     rcx, rdi; this
0x18004675e  call    ?Elem@CArrayBase@@QEBAPEAXJ@Z; CArrayBase::Elem(long)
0x180046763  cmp     [rax], ebp
0x180046765  jnz     short loc_18004677E
0x180046767  mov     rcx, [rax+8]; Buf1
0x18004676b  mov     r8, rbp
0x18004676e  shl     r8, 2; Size
0x180046772  mov     rdx, r15; Buf2
0x180046775  call    memcmp_0
0x18004677a  test    eax, eax
0x18004677c  jz      short loc_180046782
0x18004677e  inc     ebx
0x180046780  jmp     short loc_180046740
0x180046782  test    ebx, ebx
0x180046784  js      short loc_180046799
0x180046786  lea     eax, [rbx+1]
0x180046789  imul    eax, [rdi+10h]
0x18004678d  movsxd  rcx, eax
0x180046790  mov     rax, [rdi]
0x180046793  inc     dword ptr [rcx+rax-4]
0x180046797  jmp     short loc_180046804
0x180046799  mov     rcx, rdi; this
0x18004679c  call    ?Add@CFixArrayBase@@QEAAJXZ; CFixArrayBase::Add(void)
0x1800467a1  mov     ebx, eax
0x1800467a3  test    eax, eax
0x1800467a5  js      short loc_18004681B
0x1800467a7  mov     edx, eax; int
0x1800467a9  mov     rcx, rdi; this
0x1800467ac  call    ?Elem@CArrayBase@@QEBAPEAXJ@Z; CArrayBase::Elem(long)
0x1800467b1  lea     esi, ds:0[rbp*4]
0x1800467b8  mov     r14, rax
0x1800467bb  cmp     esi, 4
0x1800467be  jb      short loc_18004681B
0x1800467c0  cmp     esi, ebp
0x1800467c2  jb      short loc_18004681B
0x1800467c4  cmp     esi, 7FFFFFFFh
0x1800467ca  ja      short loc_18004681B
0x1800467cc  xor     edx, edx; unsigned int
0x1800467ce  mov     ecx, esi; unsigned int
0x1800467d0  call    ?PvAlloc@CW32System@@SAPEAXKI@Z; CW32System::PvAlloc(ulong,uint)
0x1800467d5  mov     [r14+8], rax
0x1800467d9  test    rax, rax
0x1800467dc  jz      short loc_18004681B
0x1800467de  movsxd  r8, esi; Size
0x1800467e1  mov     rdx, r15; Src
0x1800467e4  mov     rcx, rax; void *
0x1800467e7  call    memmove_0
0x1800467ec  mov     [r14], ebp
0x1800467ef  lea     eax, [rbx+1]
0x1800467f2  imul    eax, [rdi+10h]
0x1800467f6  movsxd  rdx, eax
0x1800467f9  mov     rax, [rdi]
0x1800467fc  mov     dword ptr [rdx+rax-4], 1
0x180046804  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004680b  call    cs:__imp_LeaveCriticalSection
0x180046812  nop     dword ptr [rax+rax+00h]
0x180046817  mov     eax, ebx
0x180046819  jmp     short loc_180046831
0x18004681b  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180046822  call    cs:__imp_LeaveCriticalSection
0x180046829  nop     dword ptr [rax+rax+00h]
0x18004682e  or      eax, 0FFFFFFFFh
0x180046831  add     rsp, 28h
0x180046835  pop     r15
0x180046837  pop     r14
0x180046839  pop     rdi
0x18004683a  pop     rsi
0x18004683b  pop     rbp
0x18004683c  pop     rbx
0x18004683d  retn
```
