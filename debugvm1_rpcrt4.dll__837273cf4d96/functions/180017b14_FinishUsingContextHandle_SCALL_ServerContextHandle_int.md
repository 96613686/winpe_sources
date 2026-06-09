# FinishUsingContextHandle(SCALL *,ServerContextHandle *,int)

- ea: `0x180017b14`
- end: `0x180017da3`
- name: `?FinishUsingContextHandle@@YAXPEAVSCALL@@PEAVServerContextHandle@@H@Z`
- size: `655`
- prototype: `void(struct SCALL *, struct ServerContextHandle *, int)`
- caller_count: `6`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016cd0`
- `0x1800172a0`
- `0x180017880`
- `0x180065a10`
- `0x18007bb40`
- `0x1800bcf84`

## callees

- `0x1800167c0`
- `0x180016858`
- `0x180017b14`
- `0x180017dac`
- `0x180017f48`
- `0x1800d2010`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180017d15`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180017d15`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180017cf1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180017cf1`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180017c07`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180017c07`

## pseudocode

```c
void __fastcall FinishUsingContextHandle(struct SCALL *a1, struct ServerContextHandle *a2, int a3)
{
  unsigned int i; // eax
  __int64 v5; // rdx
  struct ServerContextHandle *v6; // rdi
  volatile signed __int32 *v7; // r8
  signed __int32 k; // ecx
  signed __int32 v9; // eax
  unsigned int v10; // edx
  int v11; // esi
  int v12; // eax
  PRTL_AVL_TABLE v13; // rcx
  int RightChild; // r8d
  struct _RTL_BALANCED_LINKS *j; // r8
  CHAR *p_Balance; // r10
  unsigned __int64 v17; // rdx
  signed __int32 v18; // eax
  struct _RTL_BALANCED_LINKS *v19; // rax
  struct _RTL_BALANCED_LINKS *Parent; // r8
  struct _RTL_BALANCED_LINKS *v21; // rdx
  struct _RTL_BALANCED_LINKS *v22; // rax
  __int64 v23; // rdx
  signed __int32 v24; // edx
  PRTL_AVL_TABLE Table; // [rsp+40h] [rbp+8h] BYREF
  signed __int32 v26; // [rsp+50h] [rbp+18h]

  Table = 0;
  if ( a2 )
  {
    for ( i = 0; i < *((_DWORD *)a1 + 64); ++i )
    {
      v5 = *((_QWORD *)a1 + 31);
      if ( *(struct ServerContextHandle **)(v5 + 8LL * i) == a2 )
      {
        *(_QWORD *)(v5 + 8LL * i) = 0;
        v6 = a2;
        --*((_DWORD *)a1 + 65);
        if ( (*((_DWORD *)a1 + 58) & 2) != 0 )
        {
          do
          {
            v24 = *((_DWORD *)a2 + 48);
            v26 = v24;
            if ( !(_WORD)v24 )
              break;
            LOWORD(v26) = v24 - 1;
          }
          while ( v24 != _InterlockedCompareExchange((volatile signed __int32 *)a2 + 48, v26, v24) );
          if ( !*((_DWORD *)a1 + 65) )
            *((_DWORD *)a1 + 58) &= ~2u;
        }
        goto LABEL_6;
      }
    }
  }
  v6 = 0;
LABEL_6:
  if ( a3 )
  {
    (*(void (__fastcall **)(struct SCALL *, PRTL_AVL_TABLE *))(*(_QWORD *)a1 + 360LL))(a1, &Table);
    v11 = 0;
    RtlAcquireSRWLockExclusive(&Table[1].BalancedRoot.LeftChild);
    v12 = *((_DWORD *)a2 + 47);
    if ( (v12 & 2) == 0 )
    {
      v13 = Table;
      *((_DWORD *)a2 + 47) = v12 | 2;
      v11 = 1;
      RightChild = (int)v13[1].BalancedRoot.RightChild;
      if ( RightChild )
      {
        if ( RightChild == 1 )
          RtlDeleteElementGenericTableAvl(v13, (char *)a2 + 104);
      }
      else
      {
        for ( j = v13->BalancedRoot.Parent; j != (struct _RTL_BALANCED_LINKS *)v13; j = j->Parent )
        {
          p_Balance = &j[-3].Balance;
          v17 = (unsigned __int64)j[1].Parent - *((_QWORD *)a2 + 13);
          if ( !v17 )
          {
            v17 = (unsigned __int64)j[1].LeftChild - *((_QWORD *)a2 + 14);
            if ( !v17 )
              v17 = LODWORD(j[1].RightChild) - (unsigned __int64)*((unsigned int *)a2 + 30);
          }
          if ( !v17 )
          {
            if ( j != (struct _RTL_BALANCED_LINKS *)72 )
            {
              v19 = j;
              Parent = j->Parent;
              if ( (CHAR *)Parent->LeftChild != p_Balance + 72
                || (v21 = (struct _RTL_BALANCED_LINKS *)*((_QWORD *)p_Balance + 10), v21->Parent != v19) )
              {
                __fastfail(3u);
              }
              v21->Parent = Parent;
              Parent->LeftChild = v21;
              v22 = v13->BalancedRoot.Parent;
              --LODWORD(v13->BalancedRoot.RightChild);
              *(_QWORD *)&v13->BalancedRoot.Balance = v22;
            }
            break;
          }
        }
      }
    }
    RtlReleaseSRWLockExclusive(&Table[1].BalancedRoot.LeftChild);
    if ( v11 )
      ServerContextHandle::RemoveReference(a2);
  }
  if ( !v6 )
    goto LABEL_13;
  v7 = (volatile signed __int32 *)((char *)a2 + 136);
  if ( *((_DWORD *)a2 + 42) )
  {
    *((_DWORD *)a2 + 42) = 0;
    for ( k = 1; (k & 2) == 0; k = v9 )
    {
      v9 = _InterlockedCompareExchange(v7, 0, k);
      if ( k == v9 )
      {
        if ( (k & 1) != 0 )
          goto LABEL_13;
LABEL_30:
        __fastfail(0x24u);
      }
    }
    v23 = 1;
    goto LABEL_40;
  }
  v18 = _InterlockedExchangeAdd(v7, 0xFFFFFFFC);
  if ( (v18 & 2) != 0 )
  {
    v23 = 0;
LABEL_40:
    SWMRLock::Wake((char *)a2 + 136, v23);
    goto LABEL_13;
  }
  if ( (v18 & 0xFFFFFFFC) == 0 || (v18 & 1) != 0 )
    goto LABEL_30;
LABEL_13:
  if ( !(unsigned int)ServerContextHandle::RemoveReference(a2) )
  {
    if ( (*((_BYTE *)a2 + 188) & 4) != 0 )
      NDRSRundownContextHandle(a2);
    ServerContextHandle::`scalar deleting destructor'(a2, v10);
  }
}

```

## disassembly

```asm
0x180017b14  mov     [rsp+arg_8], rbx
0x180017b19  mov     [rsp+arg_18], rbp
0x180017b1e  push    rsi
0x180017b1f  push    rdi
0x180017b20  push    r14
0x180017b22  sub     rsp, 20h
0x180017b26  xor     ebp, ebp
0x180017b28  mov     rbx, rdx
0x180017b2b  mov     [rsp+38h+Table], rbp
0x180017b30  mov     r9, rcx
0x180017b33  lea     r14d, [rbp+1]
0x180017b37  test    rdx, rdx
0x180017b3a  jz      loc_180017D87
0x180017b40  mov     eax, ebp
0x180017b42  cmp     eax, [r9+100h]
0x180017b49  jnb     loc_180017D87
0x180017b4f  mov     rdx, [r9+0F8h]
0x180017b56  mov     ecx, eax
0x180017b58  cmp     [rdx+rcx*8], rbx
0x180017b5c  jnz     loc_180017D94
0x180017b62  mov     [rdx+rcx*8], rbp
0x180017b66  mov     rdi, rbx
0x180017b69  dec     dword ptr [r9+104h]
0x180017b70  mov     eax, [r9+0E8h]
0x180017b77  test    al, 2
0x180017b79  jnz     loc_180017D39
0x180017b7f  test    r8d, r8d
0x180017b82  jnz     short loc_180017BE5
0x180017b84  test    rdi, rdi
0x180017b87  jz      short loc_180017BC2
0x180017b89  lea     r8, [rbx+88h]
0x180017b90  cmp     [r8+20h], ebp
0x180017b94  jz      loc_180017C8B
0x180017b9a  mov     [r8+20h], ebp
0x180017b9e  mov     ecx, r14d
0x180017ba1  test    cl, 2
0x180017ba4  jnz     loc_180017D8F
0x180017baa  mov     edx, ebp
0x180017bac  mov     eax, ecx
0x180017bae  lock cmpxchg [r8], edx
0x180017bb3  jnz     loc_180017D80
0x180017bb9  test    r14b, cl
0x180017bbc  jz      loc_180017CAD
0x180017bc2  mov     rcx, rbx; this
0x180017bc5  call    ?RemoveReference@ServerContextHandle@@QEAAJXZ; ServerContextHandle::RemoveReference(void)
0x180017bca  test    eax, eax
0x180017bcc  jz      loc_180017C71
0x180017bd2  mov     rbx, [rsp+38h+arg_8]
0x180017bd7  mov     rbp, [rsp+38h+arg_18]
0x180017bdc  add     rsp, 20h
0x180017be0  pop     r14
0x180017be2  pop     rdi
0x180017be3  pop     rsi
0x180017be4  retn
0x180017be5  mov     rax, [r9]
0x180017be8  lea     rdx, [rsp+38h+Table]
0x180017bed  mov     rcx, r9
0x180017bf0  mov     rax, [rax+168h]
0x180017bf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017bfc  mov     rcx, [rsp+38h+Table]
0x180017c01  mov     esi, ebp
0x180017c03  add     rcx, 70h ; 'p'
0x180017c07  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180017c0d  mov     eax, [rbx+0BCh]
0x180017c13  test    al, 2
0x180017c15  jnz     loc_180017CE8
0x180017c1b  mov     rcx, [rsp+38h+Table]; Table
0x180017c20  or      eax, 2
0x180017c23  mov     [rbx+0BCh], eax
0x180017c29  mov     esi, r14d
0x180017c2c  mov     r8d, [rcx+78h]
0x180017c30  test    r8d, r8d
0x180017c33  jnz     loc_180017D0C
0x180017c39  mov     r8, [rcx]
0x180017c3c  cmp     r8, rcx
0x180017c3f  jz      loc_180017CE8
0x180017c45  mov     rdx, [r8+20h]
0x180017c49  lea     r10, [r8-48h]
0x180017c4d  sub     rdx, [rbx+68h]
0x180017c51  jnz     short loc_180017C67
0x180017c53  mov     rdx, [r8+28h]
0x180017c57  sub     rdx, [rbx+70h]
0x180017c5b  jnz     short loc_180017C67
0x180017c5d  mov     edx, [r8+30h]
0x180017c61  mov     eax, [rbx+78h]
0x180017c64  sub     rdx, rax
0x180017c67  test    rdx, rdx
0x180017c6a  jz      short loc_180017CB4
0x180017c6c  mov     r8, [r8]
0x180017c6f  jmp     short loc_180017C3C
0x180017c71  test    byte ptr [rbx+0BCh], 4
0x180017c78  jnz     loc_180017D2C
0x180017c7e  mov     rcx, rbx; this
0x180017c81  call    ??_GServerContextHandle@@QEAAPEAXI@Z; ServerContextHandle::`scalar deleting destructor'(uint)
0x180017c86  jmp     loc_180017BD2
0x180017c8b  mov     eax, 0FFFFFFFCh
0x180017c90  lock xadd [r8], eax
0x180017c95  test    al, 2
0x180017c97  jnz     loc_180017D1D
0x180017c9d  test    eax, 0FFFFFFFCh
0x180017ca2  jbe     short loc_180017CAD
0x180017ca4  test    r14b, al
0x180017ca7  jz      loc_180017BC2
0x180017cad  mov     ecx, 24h ; '$'
0x180017cb2  int     29h; Win8: RtlFailFast(ecx)
0x180017cb4  test    r10, r10
0x180017cb7  jz      short loc_180017CE8
0x180017cb9  lea     rax, [r10+48h]
0x180017cbd  mov     r8, [rax]
0x180017cc0  cmp     [r8+8], rax
0x180017cc4  jnz     loc_180017D9C
0x180017cca  mov     rdx, [rax+8]
0x180017cce  cmp     [rdx], rax
0x180017cd1  jnz     loc_180017D9C
0x180017cd7  mov     [rdx], r8
0x180017cda  mov     [r8+8], rdx
0x180017cde  mov     rax, [rcx]
0x180017ce1  dec     dword ptr [rcx+10h]
0x180017ce4  mov     [rcx+18h], rax
0x180017ce8  mov     rcx, [rsp+38h+Table]
0x180017ced  add     rcx, 70h ; 'p'
0x180017cf1  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180017cf7  test    esi, esi
0x180017cf9  jz      loc_180017B84
0x180017cff  mov     rcx, rbx; this
0x180017d02  call    ?RemoveReference@ServerContextHandle@@QEAAJXZ; ServerContextHandle::RemoveReference(void)
0x180017d07  jmp     loc_180017B84
0x180017d0c  cmp     r8d, esi
0x180017d0f  jnz     short loc_180017CE8
0x180017d11  lea     rdx, [rbx+68h]; Buffer
0x180017d15  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180017d1b  jmp     short loc_180017CE8
0x180017d1d  xor     edx, edx
0x180017d1f  mov     rcx, r8
0x180017d22  call    ?Wake@SWMRLock@@AEAAXW4RequestorType@1@@Z; SWMRLock::Wake(SWMRLock::RequestorType)
0x180017d27  jmp     loc_180017BC2
0x180017d2c  mov     rcx, rbx; struct ServerContextHandle *
0x180017d2f  call    ?NDRSRundownContextHandle@@YAXPEAVServerContextHandle@@@Z; NDRSRundownContextHandle(ServerContextHandle *)
0x180017d34  jmp     loc_180017C7E
0x180017d39  mov     edx, [rbx+0C0h]
0x180017d3f  mov     [rsp+38h+arg_10], edx
0x180017d43  test    dx, dx
0x180017d46  jz      short loc_180017D66
0x180017d48  movzx   eax, dx
0x180017d4b  sub     ax, r14w
0x180017d4f  mov     word ptr [rsp+38h+arg_10], ax
0x180017d54  mov     eax, edx
0x180017d56  mov     ecx, [rsp+38h+arg_10]
0x180017d5a  lock cmpxchg [rbx+0C0h], ecx
0x180017d62  cmp     edx, eax
0x180017d64  jnz     short loc_180017D39
0x180017d66  cmp     [r9+104h], ebp
0x180017d6d  jnz     loc_180017B7F
0x180017d73  and     dword ptr [r9+0E8h], 0FFFFFFFDh
0x180017d7b  jmp     loc_180017B7F
0x180017d80  mov     ecx, eax
0x180017d82  jmp     loc_180017BA1
0x180017d87  mov     rdi, rbp
0x180017d8a  jmp     loc_180017B7F
0x180017d8f  mov     edx, r14d
0x180017d92  jmp     short loc_180017D1F
0x180017d94  add     eax, r14d
0x180017d97  jmp     loc_180017B42
0x180017d9c  mov     ecx, 3
0x180017da1  int     29h; Win8: RtlFailFast(ecx)
```
