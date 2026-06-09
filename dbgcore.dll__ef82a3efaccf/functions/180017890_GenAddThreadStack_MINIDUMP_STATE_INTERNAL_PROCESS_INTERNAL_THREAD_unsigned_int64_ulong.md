# GenAddThreadStack(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,unsigned __int64,ulong)

- ea: `0x180017890`
- end: `0x180017a32`
- name: `?GenAddThreadStack@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@_KK@Z`
- size: `418`
- prototype: `__int64 __usercall@<rax>(struct _MINIDUMP_STATE *@<rcx>, struct _INTERNAL_PROCESS *@<rdx>, struct _INTERNAL_THREAD *@<r8>, unsigned __int64@<r9>, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001ad48`

## callees

- `0x180016930`
- `0x180017890`
- `0x18001f334`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall GenAddThreadStack(
        struct _MINIDUMP_STATE *a1,
        struct _INTERNAL_PROCESS *a2,
        struct _INTERNAL_THREAD *a3,
        unsigned __int64 a4,
        unsigned int a5)
{
  unsigned int v8; // ecx
  int v9; // r15d

  if ( a4 && a5 || (v8 = 0, ((*((_DWORD *)a1 + 39) - 1) & (unsigned int)a4) == 0) )
  {
    v9 = *((_DWORD *)a1 + 14) & 0x100000;
    if ( v9
      && a5
      && !(*(unsigned int (__fastcall **)(_QWORD, _QWORD, unsigned __int64, char *))(**((_QWORD **)a1 + 2) + 232LL))(
            *((_QWORD *)a1 + 2),
            *(_QWORD *)a1,
            a4,
            (char *)a2 + 7608) )
    {
      return (unsigned int)-2147467259;
    }
    else
    {
      return (unsigned int)GenAddMemoryBlock(a1, (__int64)a2, 2u, v9 != 0, a4, a5);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180017890  mov     [rsp+arg_8], rbx
0x180017895  mov     [rsp+arg_10], r8
0x18001789a  push    rbp
0x18001789b  push    rsi
0x18001789c  push    rdi
0x18001789d  push    r12
0x18001789f  push    r13
0x1800178a1  push    r14
0x1800178a3  push    r15
0x1800178a5  sub     rsp, 40h
0x1800178a9  mov     esi, [rsp+78h+arg_20]
0x1800178b0  mov     rdi, r9
0x1800178b3  mov     r13, rdx
0x1800178b6  mov     rbx, rcx
0x1800178b9  test    r9, r9
0x1800178bc  jz      short loc_1800178C2
0x1800178be  test    esi, esi
0x1800178c0  jnz     short loc_1800178D5
0x1800178c2  mov     eax, [rbx+9Ch]
0x1800178c8  xor     ecx, ecx
0x1800178ca  dec     eax
0x1800178cc  test    rdi, rax
0x1800178cf  jnz     loc_180017A11
0x1800178d5  mov     r15d, [rbx+38h]
0x1800178d9  and     r15d, 100000h
0x1800178e0  jz      loc_1800179EB
0x1800178e6  mov     dword ptr [rsp+78h+arg_0], 0
0x1800178f1  mov     rdx, rdi
0x1800178f4  mov     [rsp+78h+arg_18], rdx
0x1800178fc  mov     r12d, esi
0x1800178ff  test    esi, esi
0x180017901  jz      loc_1800179EB
0x180017907  lea     r14, [r13+1DB8h]
0x18001790e  mov     eax, 10000h
0x180017913  mov     rcx, [rbx+10h]
0x180017917  lea     r8, [rsp+78h+arg_0]
0x18001791f  cmp     r12d, eax
0x180017922  mov     qword ptr [rsp+78h+var_50], r8; unsigned __int8
0x180017927  mov     r8, rdx
0x18001792a  mov     ebp, r12d
0x18001792d  mov     rdx, [rbx]
0x180017930  cmova   ebp, eax
0x180017933  mov     rax, [rcx]
0x180017936  mov     r9, r14
0x180017939  mov     dword ptr [rsp+78h+var_58], ebp; unsigned __int8
0x18001793d  mov     rax, [rax+0E8h]
0x180017944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017949  test    eax, eax
0x18001794b  jnz     loc_1800179EB
0x180017951  mov     ecx, dword ptr [rsp+78h+arg_0]
0x180017958  cmp     ecx, ebp
0x18001795a  jnz     loc_180017A2B
0x180017960  test    dword ptr [rbx+38h], 100000h
0x180017967  jz      short loc_1800179C8
0x180017969  mov     r8d, [rbx+9Ch]
0x180017970  xor     edx, edx
0x180017972  mov     eax, ecx
0x180017974  div     r8d
0x180017977  mov     ebp, eax
0x180017979  test    eax, eax
0x18001797b  jz      short loc_1800179C8
0x18001797d  mov     rsi, [rsp+78h+arg_10]
0x180017985  dec     ebp
0x180017987  cmp     r8d, 8
0x18001798b  jnz     short loc_180017992
0x18001798d  mov     r9, [r14]
0x180017990  jmp     short loc_180017995
0x180017992  movsxd  r9, dword ptr [r14]; unsigned __int64
0x180017995  mov     r8, rsi; struct _INTERNAL_THREAD *
0x180017998  mov     rdx, r13; struct _INTERNAL_PROCESS *
0x18001799b  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18001799e  call    ?AddressReferenced@@YAEPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@_KEE@Z; AddressReferenced(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,unsigned __int64,uchar,uchar)
0x1800179a3  mov     eax, [rbx+9Ch]
0x1800179a9  add     r14, rax
0x1800179ac  mov     r8d, eax
0x1800179af  test    ebp, ebp
0x1800179b1  jnz     short loc_180017985
0x1800179b3  mov     ecx, dword ptr [rsp+78h+arg_0]
0x1800179ba  lea     r14, [r13+1DB8h]
0x1800179c1  mov     esi, [rsp+78h+arg_20]
0x1800179c8  mov     rdx, [rsp+78h+arg_18]
0x1800179d0  mov     eax, ecx
0x1800179d2  add     rdx, rax
0x1800179d5  mov     eax, 10000h
0x1800179da  mov     [rsp+78h+arg_18], rdx
0x1800179e2  sub     r12d, ecx
0x1800179e5  jnz     loc_180017913
0x1800179eb  xor     r9d, r9d
0x1800179ee  mov     dword ptr [rsp+78h+var_50], esi
0x1800179f2  test    r15d, r15d
0x1800179f5  mov     qword ptr [rsp+78h+var_58], rdi
0x1800179fa  mov     r8d, 2
0x180017a00  mov     rdx, r13
0x180017a03  setnz   r9b
0x180017a07  mov     rcx, rbx
0x180017a0a  call    ?GenAddMemoryBlock@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@W4MEMBLOCK_TYPE@@W4MEMBLOCK_FILTER_TYPE@@_KK@Z; GenAddMemoryBlock(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,MEMBLOCK_TYPE,MEMBLOCK_FILTER_TYPE,unsigned __int64,ulong)
0x180017a0f  mov     ecx, eax
0x180017a11  mov     rbx, [rsp+78h+arg_8]
0x180017a19  mov     eax, ecx
0x180017a1b  add     rsp, 40h
0x180017a1f  pop     r15
0x180017a21  pop     r14
0x180017a23  pop     r13
0x180017a25  pop     r12
0x180017a27  pop     rdi
0x180017a28  pop     rsi
0x180017a29  pop     rbp
0x180017a2a  retn
0x180017a2b  mov     ecx, 80004005h
0x180017a30  jmp     short loc_180017A11
```
