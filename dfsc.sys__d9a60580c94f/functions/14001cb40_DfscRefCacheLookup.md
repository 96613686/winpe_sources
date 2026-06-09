# DfscRefCacheLookup

- ea: `0x14001cb40`
- end: `0x14001ce3e`
- name: `DfscRefCacheLookup`
- size: `766`
- prototype: `__int64 __fastcall(__int64, const UNICODE_STRING *, _OWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140011f60`

## callees

- `0x1400050fc`
- `0x14001cb40`
- `0x14001cfd0`
- `0x14001d090`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001cbf6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001cc6d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001cd07`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001cbf6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001cc6d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001cd07`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001cbea`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001cc61`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001ccfb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001cbea`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001cc61`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001ccfb`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x14001cbcb`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x14001cbcb`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001cbb1`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001cc8e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001cbb1`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001cc8e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001cb9f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001cc79`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001cb9f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001cc79`
- `ntoskrnl!ExAllocatePool2` at `0x14001cd23`
- `ntoskrnl!ExAllocatePool2` at `0x14001cd23`

## pseudocode

```c
__int64 __fastcall DfscRefCacheLookup(__int64 a1, const UNICODE_STRING *a2, _OWORD *a3, __int64 *a4)
{
  __int64 v4; // rbx
  char *SecurityDescriptor; // rbx
  unsigned int v9; // esi
  PUNICODE_PREFIX_TABLE_ENTRY UnicodePrefix; // rax
  struct _RTL_SPLAY_LINKS **p_RightChild; // rdi
  unsigned __int64 Length; // rdx
  unsigned __int16 v14; // r8
  WCHAR *v15; // rcx
  struct _RTL_SPLAY_LINKS *v16; // rax
  struct _RTL_SPLAY_LINKS *v17; // rcx
  struct _RTL_SPLAY_LINKS *v18; // rdx
  __int64 v19; // rdx
  struct _RTL_SPLAY_LINKS *v20; // rax
  __int64 Pool2; // rax
  __int64 v22; // rbx
  int v23; // edx
  int v24; // r8d
  __int128 v25; // [rsp+40h] [rbp-38h]

  v4 = *(_QWORD *)(a1 + 240);
  if ( v4 )
    SecurityDescriptor = *(char **)(v4 + 136);
  else
    SecurityDescriptor = (char *)WPP_MAIN_CB.SecurityDescriptor;
  *((_QWORD *)&v25 + 1) = a2->Buffer;
  WORD1(v25) = a2->MaximumLength;
  DWORD1(v25) = 0;
  LOWORD(v25) = 0;
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite((PERESOURCE)(SecurityDescriptor + 56), 1u);
  v9 = -1073741766;
  UnicodePrefix = RtlFindUnicodePrefix((PUNICODE_PREFIX_TABLE)SecurityDescriptor, a2, 0);
  if ( !UnicodePrefix
    || (p_RightChild = &UnicodePrefix[-2].Links.RightChild, (BYTE4(UnicodePrefix[-2].Prefix) & 1) == 0) )
  {
    ExReleaseResourceLite((PERESOURCE)(SecurityDescriptor + 56));
    KeLeaveCriticalRegion();
    return v9;
  }
  Length = a2->Length;
  v14 = *((_WORD *)p_RightChild + 72);
  if ( v14 < (unsigned __int16)Length )
  {
    LOWORD(v25) = Length - v14;
    v15 = &a2->Buffer[(unsigned __int64)*((unsigned __int16 *)p_RightChild + 72) >> 1];
LABEL_9:
    *((_QWORD *)&v25 + 1) = v15;
    goto LABEL_10;
  }
  if ( v14 == (_WORD)Length )
  {
    v15 = &a2->Buffer[(Length >> 1) - 1];
    if ( *v15 == 92 )
    {
      LOWORD(v25) = 2;
      goto LABEL_9;
    }
  }
LABEL_10:
  _InterlockedIncrement((volatile signed __int32 *)p_RightChild + 1);
  ExReleaseResourceLite((PERESOURCE)(SecurityDescriptor + 56));
  KeLeaveCriticalRegion();
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite((PERESOURCE)(SecurityDescriptor + 160), 1u);
  if ( SecurityDescriptor != (char *)p_RightChild[8] )
    goto LABEL_18;
  v16 = p_RightChild[6];
  v17 = (struct _RTL_SPLAY_LINKS *)(p_RightChild + 6);
  if ( v16 )
  {
    if ( v16->LeftChild != v17 )
      goto LABEL_31;
    v18 = p_RightChild[7];
    if ( v18->Parent != v17 )
      goto LABEL_31;
    v18->Parent = v16;
    v16->LeftChild = v18;
    v17->Parent = 0;
  }
  if ( (*((_BYTE *)p_RightChild + 12) & 1) == 0 )
    goto LABEL_18;
  v19 = *((_QWORD *)SecurityDescriptor + 3);
  v20 = (struct _RTL_SPLAY_LINKS *)(SecurityDescriptor + 24);
  if ( *(char **)(v19 + 8) != SecurityDescriptor + 24 )
LABEL_31:
    __fastfail(3u);
  v17->Parent = (struct _RTL_SPLAY_LINKS *)v19;
  p_RightChild[7] = v20;
  *(_QWORD *)(v19 + 8) = v17;
  v20->Parent = v17;
LABEL_18:
  ExReleaseResourceLite((PERESOURCE)(SecurityDescriptor + 160));
  KeLeaveCriticalRegion();
  Pool2 = ExAllocatePool2(258, 40, 1648584260);
  v22 = Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)(Pool2 + 8) = 0;
    *(_QWORD *)(Pool2 + 24) = 0;
    *(_QWORD *)(Pool2 + 32) = 0;
    *(_DWORD *)Pool2 = 2654467;
    *(_DWORD *)(Pool2 + 4) = 1;
    *(_QWORD *)(Pool2 + 16) = p_RightChild;
    DfscRmIsTimeToRefresh(Pool2);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    {
      WPP_SF_qqDZ(
        WPP_GLOBAL_Control->AttachedDevice,
        v23,
        v24,
        v22,
        *(_QWORD *)(v22 + 16),
        *(_DWORD *)(v22 + 8),
        (__int64)(p_RightChild + 18));
    }
    if ( !*((_DWORD *)p_RightChild + 2) && !*((_WORD *)p_RightChild + 12) )
      *(_DWORD *)(v22 + 8) |= 2u;
    *(_WORD *)(v22 + 32) = -1;
    v9 = 0;
    if ( a3 )
      *a3 = v25;
    *a4 = v22;
  }
  else
  {
    v9 = -1073741670;
    DfscRmDereferenceReferral((volatile signed __int32 *)p_RightChild);
  }
  return v9;
}

```

## disassembly

```asm
0x14001cb40  mov     [rsp+arg_8], rbx
0x14001cb45  mov     [rsp+arg_10], rbp
0x14001cb4a  push    rsi
0x14001cb4b  push    r12
0x14001cb4d  push    r13
0x14001cb4f  push    r14
0x14001cb51  push    r15
0x14001cb53  sub     rsp, 50h
0x14001cb57  mov     rbx, [rcx+0F0h]
0x14001cb5e  mov     r12, r9
0x14001cb61  mov     r15, r8
0x14001cb64  mov     r14, rdx
0x14001cb67  test    rbx, rbx
0x14001cb6a  jnz     loc_14001CDB8
0x14001cb70  mov     rbx, cs:WPP_MAIN_CB.SecurityDescriptor
0x14001cb77  mov     rax, [rdx+8]
0x14001cb7b  xor     r13d, r13d
0x14001cb7e  mov     qword ptr [rsp+78h+var_38+8], rax
0x14001cb83  movzx   eax, word ptr [rdx+2]
0x14001cb87  mov     word ptr [rsp+78h+var_38+2], ax
0x14001cb8c  mov     [rsp+78h+arg_0], rdi
0x14001cb94  mov     dword ptr [rsp+78h+var_38+4], r13d
0x14001cb99  mov     word ptr [rsp+78h+var_38], r13w
0x14001cb9f  call    cs:__imp_KeEnterCriticalRegion
0x14001cba6  nop     dword ptr [rax+rax+00h]
0x14001cbab  mov     dl, 1; Wait
0x14001cbad  lea     rcx, [rbx+38h]; Resource
0x14001cbb1  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001cbb8  nop     dword ptr [rax+rax+00h]
0x14001cbbd  xor     r8d, r8d; CaseInsensitiveIndex
0x14001cbc0  mov     rdx, r14; FullName
0x14001cbc3  mov     rcx, rbx; PrefixTable
0x14001cbc6  mov     esi, 0C000003Ah
0x14001cbcb  call    cs:__imp_RtlFindUnicodePrefix
0x14001cbd2  nop     dword ptr [rax+rax+00h]
0x14001cbd7  test    rax, rax
0x14001cbda  jz      short loc_14001CBE6
0x14001cbdc  test    byte ptr [rax-3Ch], 1
0x14001cbe0  lea     rdi, [rax-48h]
0x14001cbe4  jnz     short loc_14001CC27
0x14001cbe6  lea     rcx, [rbx+38h]; Resource
0x14001cbea  call    cs:__imp_ExReleaseResourceLite
0x14001cbf1  nop     dword ptr [rax+rax+00h]
0x14001cbf6  call    cs:__imp_KeLeaveCriticalRegion
0x14001cbfd  nop     dword ptr [rax+rax+00h]
0x14001cc02  mov     rdi, [rsp+78h+arg_0]
0x14001cc0a  lea     r11, [rsp+78h+var_28]
0x14001cc0f  mov     rbx, [r11+38h]
0x14001cc13  mov     eax, esi
0x14001cc15  mov     rbp, [r11+40h]
0x14001cc19  mov     rsp, r11
0x14001cc1c  pop     r15
0x14001cc1e  pop     r14
0x14001cc20  pop     r13
0x14001cc22  pop     r12
0x14001cc24  pop     rsi
0x14001cc25  retn
0x14001cc27  movzx   edx, word ptr [r14]
0x14001cc2b  movzx   r8d, word ptr [rdi+90h]
0x14001cc33  cmp     r8w, dx
0x14001cc37  jnb     loc_14001CDC4
0x14001cc3d  mov     rax, [r14+8]
0x14001cc41  mov     ecx, r8d
0x14001cc44  shr     rcx, 1
0x14001cc47  sub     dx, r8w
0x14001cc4b  mov     word ptr [rsp+78h+var_38], dx
0x14001cc50  lea     rcx, [rax+rcx*2]
0x14001cc54  mov     qword ptr [rsp+78h+var_38+8], rcx
0x14001cc59  lock inc dword ptr [rdi+4]
0x14001cc5d  lea     rcx, [rbx+38h]; Resource
0x14001cc61  call    cs:__imp_ExReleaseResourceLite
0x14001cc68  nop     dword ptr [rax+rax+00h]
0x14001cc6d  call    cs:__imp_KeLeaveCriticalRegion
0x14001cc74  nop     dword ptr [rax+rax+00h]
0x14001cc79  call    cs:__imp_KeEnterCriticalRegion
0x14001cc80  nop     dword ptr [rax+rax+00h]
0x14001cc85  mov     dl, 1; Wait
0x14001cc87  lea     rcx, [rbx+0A0h]; Resource
0x14001cc8e  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001cc95  nop     dword ptr [rax+rax+00h]
0x14001cc9a  cmp     rbx, [rdi+40h]
0x14001cc9e  jnz     short loc_14001CCF4
0x14001cca0  mov     rax, [rdi+30h]
0x14001cca4  lea     rcx, [rdi+30h]
0x14001cca8  test    rax, rax
0x14001ccab  jz      short loc_14001CCCE
0x14001ccad  cmp     [rax+8], rcx
0x14001ccb1  jnz     loc_14001CDF6
0x14001ccb7  mov     rdx, [rcx+8]
0x14001ccbb  cmp     [rdx], rcx
0x14001ccbe  jnz     loc_14001CDF6
0x14001ccc4  mov     [rdx], rax
0x14001ccc7  mov     [rax+8], rdx
0x14001cccb  mov     [rcx], r13
0x14001ccce  test    byte ptr [rdi+0Ch], 1
0x14001ccd2  jz      short loc_14001CCF4
0x14001ccd4  mov     rdx, [rbx+18h]
0x14001ccd8  lea     rax, [rbx+18h]
0x14001ccdc  cmp     [rdx+8], rax
0x14001cce0  jnz     loc_14001CDF6
0x14001cce6  mov     [rcx], rdx
0x14001cce9  mov     [rcx+8], rax
0x14001cced  mov     [rdx+8], rcx
0x14001ccf1  mov     [rax], rcx
0x14001ccf4  lea     rcx, [rbx+0A0h]; Resource
0x14001ccfb  call    cs:__imp_ExReleaseResourceLite
0x14001cd02  nop     dword ptr [rax+rax+00h]
0x14001cd07  call    cs:__imp_KeLeaveCriticalRegion
0x14001cd0e  nop     dword ptr [rax+rax+00h]
0x14001cd13  mov     edx, 28h ; '('
0x14001cd18  mov     ecx, 102h
0x14001cd1d  mov     r8d, 62436644h
0x14001cd23  call    cs:__imp_ExAllocatePool2
0x14001cd2a  nop     dword ptr [rax+rax+00h]
0x14001cd2f  mov     rbx, rax
0x14001cd32  test    rax, rax
0x14001cd35  jz      short loc_14001CDA6
0x14001cd37  mov     [rax+8], r13
0x14001cd3b  mov     rcx, rax
0x14001cd3e  mov     [rax+18h], r13
0x14001cd42  mov     [rax+20h], r13
0x14001cd46  mov     dword ptr [rax], 288103h
0x14001cd4c  mov     dword ptr [rax+4], 1
0x14001cd53  mov     [rax+10h], rdi
0x14001cd57  call    DfscRmIsTimeToRefresh
0x14001cd5c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cd63  lea     rax, WPP_GLOBAL_Control
0x14001cd6a  cmp     rcx, rax
0x14001cd6d  jz      short loc_14001CD7C
0x14001cd6f  test    dword ptr [rcx+2Ch], 400000h
0x14001cd76  jnz     loc_14001CDFD
0x14001cd7c  cmp     [rdi+8], r13d
0x14001cd80  jz      loc_14001CE2A
0x14001cd86  mov     word ptr [rbx+20h], 0FFFFh
0x14001cd8c  mov     esi, r13d
0x14001cd8f  test    r15, r15
0x14001cd92  jz      short loc_14001CD9D
0x14001cd94  movups  xmm0, [rsp+78h+var_38]
0x14001cd99  movups  xmmword ptr [r15], xmm0
0x14001cd9d  mov     [r12], rbx
0x14001cda1  jmp     loc_14001CC02
0x14001cda6  mov     rcx, rdi; P
0x14001cda9  mov     esi, 0C000009Ah
0x14001cdae  call    DfscRmDereferenceReferral
0x14001cdb3  jmp     loc_14001CC02
0x14001cdb8  mov     rbx, [rbx+88h]
0x14001cdbf  jmp     loc_14001CB77
0x14001cdc4  jnz     loc_14001CC59
0x14001cdca  mov     rax, [r14+8]
0x14001cdce  mov     rcx, rdx
0x14001cdd1  shr     rcx, 1
0x14001cdd4  sub     rax, 2
0x14001cdd8  cmp     word ptr [rax+rcx*2], 5Ch ; '\'
0x14001cddd  lea     rcx, [rax+rcx*2]
0x14001cde1  jnz     loc_14001CC59
0x14001cde7  mov     eax, 2
0x14001cdec  mov     word ptr [rsp+78h+var_38], ax
0x14001cdf1  jmp     loc_14001CC54
0x14001cdf6  mov     ecx, 3
0x14001cdfb  int     29h; Win8: RtlFailFast(ecx)
0x14001cdfd  mov     rcx, [rcx+18h]
0x14001ce01  lea     rax, [rdi+90h]
0x14001ce08  mov     [rsp+78h+var_48], rax
0x14001ce0d  mov     r9, rbx
0x14001ce10  mov     eax, [rbx+8]
0x14001ce13  mov     [rsp+78h+var_50], eax
0x14001ce17  mov     rax, [rbx+10h]
0x14001ce1b  mov     [rsp+78h+var_58], rax
0x14001ce20  call    WPP_SF_qqDZ
0x14001ce25  jmp     loc_14001CD7C
0x14001ce2a  cmp     [rdi+18h], r13w
0x14001ce2f  jnz     loc_14001CD86
0x14001ce35  or      dword ptr [rbx+8], 2
0x14001ce39  jmp     loc_14001CD86
```
