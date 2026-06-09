# SidToLuidTable::RemoveLogon(_SID const *,_LUID const *,ulong *)

- ea: `0x18002f3f4`
- end: `0x18002f4ba`
- name: `?RemoveLogon@SidToLuidTable@@QEAAJPEBU_SID@@PEBU_LUID@@PEAK@Z`
- size: `198`
- prototype: `int(SidToLuidTable *__hidden this, const struct _SID *, const struct _LUID *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000cc9c`

## callees

- `0x18002f3f4`
- `0x18002f610`
- `0x18002ffb0`
- `0x1800561f4`
- `0x180056218`

## import_xrefs

- `ntdll!RtlAvlRemoveNode` at `0x18002f491`
- `ntdll!RtlAvlRemoveNode` at `0x18002f491`

## pseudocode

```c
__int64 __fastcall SidToLuidTable::RemoveLogon(
        SidToLuidTable *this,
        struct _SID *a2,
        const struct _LUID *a3,
        unsigned int *a4)
{
  __int64 **v4; // rsi
  __int64 *v8; // rbx
  int v9; // eax
  struct SidToLuidTable::SidNode::LogonNode *Logon; // rax
  __int64 v11; // rdx
  struct SidToLuidTable::SidNode::LogonNode **v12; // r8
  unsigned int v13; // eax
  unsigned int v14; // edi
  unsigned int v15; // edx

  v4 = (__int64 **)qword_180089B08;
  *a4 = 0;
  v8 = *v4;
  if ( !*v4 )
    return (unsigned int)-1073741275;
  do
  {
    v9 = SidToLuidTable::CompareNode(a2, (struct _RTL_BALANCED_NODE *)v8);
    if ( v9 >= 0 )
    {
      if ( v9 <= 0 )
        break;
      v8 = (__int64 *)v8[1];
    }
    else
    {
      v8 = (__int64 *)*v8;
    }
  }
  while ( v8 );
  if ( v8 && (Logon = SidToLuidTable::SidNode::FindLogon((SidToLuidTable::SidNode *)v8, a3)) != 0 )
  {
    --*((_DWORD *)v8 + 28);
    v11 = *(_QWORD *)Logon;
    if ( *(struct SidToLuidTable::SidNode::LogonNode **)(*(_QWORD *)Logon + 8LL) != Logon
      || (v12 = (struct SidToLuidTable::SidNode::LogonNode **)*((_QWORD *)Logon + 1), *v12 != Logon) )
    {
      __fastfail(3u);
    }
    *v12 = (struct SidToLuidTable::SidNode::LogonNode *)v11;
    *(_QWORD *)(v11 + 8) = v12;
    operator delete(Logon, (const struct std::nothrow_t *)0x18);
    v13 = *((_DWORD *)v8 + 28);
    v14 = 0;
    *a4 = v13;
    if ( !v13 )
    {
      RtlAvlRemoveNode(v4, v8);
      SidToLuidTable::SidNode::`scalar deleting destructor'((SidToLuidTable::SidNode *)v8, v15);
    }
  }
  else
  {
    return (unsigned int)-1073741275;
  }
  return v14;
}

```

## disassembly

```asm
0x18002f3f4  push    rbx
0x18002f3f6  push    rbp
0x18002f3f7  push    rsi
0x18002f3f8  push    rdi
0x18002f3f9  push    r14
0x18002f3fb  sub     rsp, 20h
0x18002f3ff  mov     rsi, cs:qword_180089B08
0x18002f406  mov     r14, r9
0x18002f409  mov     rbp, r8
0x18002f40c  mov     dword ptr [r9], 0
0x18002f413  mov     rdi, rdx
0x18002f416  mov     rbx, [rsi]
0x18002f419  test    rbx, rbx
0x18002f41c  jz      loc_18002F4A8
0x18002f422  mov     rdx, rbx; struct _RTL_BALANCED_NODE *
0x18002f425  mov     rcx, rdi; void *
0x18002f428  call    ?CompareNode@SidToLuidTable@@CAJPEAXPEAU_RTL_BALANCED_NODE@@@Z; SidToLuidTable::CompareNode(void *,_RTL_BALANCED_NODE *)
0x18002f42d  test    eax, eax
0x18002f42f  jns     short loc_18002F436
0x18002f431  mov     rbx, [rbx]
0x18002f434  jmp     short loc_18002F43C
0x18002f436  jle     short loc_18002F441
0x18002f438  mov     rbx, [rbx+8]
0x18002f43c  test    rbx, rbx
0x18002f43f  jnz     short loc_18002F422
0x18002f441  test    rbx, rbx
0x18002f444  jz      short loc_18002F4A8
0x18002f446  mov     rdx, rbp; struct _LUID *
0x18002f449  mov     rcx, rbx; this
0x18002f44c  call    ?FindLogon@SidNode@SidToLuidTable@@AEAAPEAULogonNode@12@PEBU_LUID@@@Z; SidToLuidTable::SidNode::FindLogon(_LUID const *)
0x18002f451  test    rax, rax
0x18002f454  jz      short loc_18002F4A8
0x18002f456  dec     dword ptr [rbx+70h]
0x18002f459  mov     rdx, [rax]
0x18002f45c  cmp     [rdx+8], rax
0x18002f460  jnz     short loc_18002F4A1
0x18002f462  mov     r8, [rax+8]
0x18002f466  cmp     [r8], rax
0x18002f469  jnz     short loc_18002F4A1
0x18002f46b  mov     [r8], rdx
0x18002f46e  mov     rcx, rax; void *
0x18002f471  mov     [rdx+8], r8
0x18002f475  mov     edx, 18h; struct std::nothrow_t *
0x18002f47a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002f47f  mov     eax, [rbx+70h]
0x18002f482  xor     edi, edi
0x18002f484  mov     [r14], eax
0x18002f487  test    eax, eax
0x18002f489  jnz     short loc_18002F4AD
0x18002f48b  mov     rdx, rbx
0x18002f48e  mov     rcx, rsi
0x18002f491  call    cs:__imp_RtlAvlRemoveNode
0x18002f497  mov     rcx, rbx; this
0x18002f49a  call    ??_GSidNode@SidToLuidTable@@QEAAPEAXI@Z; SidToLuidTable::SidNode::`scalar deleting destructor'(uint)
0x18002f49f  jmp     short loc_18002F4AD
0x18002f4a1  mov     ecx, 3
0x18002f4a6  int     29h; Win8: RtlFailFast(ecx)
0x18002f4a8  mov     edi, 0C0000225h
0x18002f4ad  mov     eax, edi
0x18002f4af  add     rsp, 20h
0x18002f4b3  pop     r14
0x18002f4b5  pop     rdi
0x18002f4b6  pop     rsi
0x18002f4b7  pop     rbp
0x18002f4b8  pop     rbx
0x18002f4b9  retn
```
