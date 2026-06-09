# DfscDomainCacheLookup

- ea: `0x14001c8ac`
- end: `0x14001cb2b`
- name: `DfscDomainCacheLookup`
- size: `639`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x140011010`
- `0x14001109c`
- `0x14001d110`
- `0x14001fb50`

## callees

- `0x1400050fc`
- `0x14001c8ac`
- `0x14001cfd0`
- `0x14001d090`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001c959`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001c9fa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001c959`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001c9fa`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001c94d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001c9ee`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001c94d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001c9ee`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x14001c927`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x14001c927`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001c90d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001c985`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001c90d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001c985`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c8fb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c96d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c8fb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c96d`
- `ntoskrnl!ExAllocatePool2` at `0x14001ca16`
- `ntoskrnl!ExAllocatePool2` at `0x14001ca16`

## pseudocode

```c
__int64 __fastcall DfscDomainCacheLookup(__int64 a1, const UNICODE_STRING *a2, __int64 *a3)
{
  const UNICODE_STRING *v3; // rbx
  PWSTR Buffer; // rax
  __int64 v6; // rbp
  __int64 v7; // rbp
  int v8; // esi
  PUNICODE_PREFIX_TABLE_ENTRY UnicodePrefix; // rax
  struct _RTL_SPLAY_LINKS **p_RightChild; // rdi
  struct _ERESOURCE *v11; // rbx
  struct _RTL_SPLAY_LINKS *v12; // rcx
  struct _RTL_SPLAY_LINKS *v13; // rax
  struct _RTL_SPLAY_LINKS *v14; // rdx
  struct _RTL_SPLAY_LINKS *v15; // rbp
  struct _RTL_SPLAY_LINKS *Parent; // rax
  __int64 Pool2; // rax
  __int64 v18; // rbx
  int v19; // edx
  int v20; // r8d
  UNICODE_STRING v22; // xmm0
  __int128 v23; // [rsp+40h] [rbp-48h] BYREF

  v3 = a2;
  v23 = 0;
  if ( a2->Length > 2u )
  {
    Buffer = a2->Buffer;
    if ( *Buffer == 92 )
    {
      v22 = *a2;
      v3 = (const UNICODE_STRING *)&v23;
      DWORD1(v23) = HIDWORD(*(_QWORD *)&a2->Length);
      *((_QWORD *)&v23 + 1) = Buffer + 1;
      LOWORD(v23) = v22.Length - 2;
      WORD1(v23) = v22.MaximumLength - 2;
    }
  }
  v6 = *(_QWORD *)(a1 + 240);
  if ( v6 )
    v7 = *(_QWORD *)(v6 + 128);
  else
    v7 = *(_QWORD *)&WPP_MAIN_CB.ActiveThreadCount;
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite((PERESOURCE)(v7 + 56), 1u);
  v8 = -1073741766;
  UnicodePrefix = RtlFindUnicodePrefix((PUNICODE_PREFIX_TABLE)v7, v3, 0);
  if ( UnicodePrefix && (p_RightChild = &UnicodePrefix[-2].Links.RightChild, (BYTE4(UnicodePrefix[-2].Prefix) & 1) != 0) )
  {
    _InterlockedIncrement((volatile signed __int32 *)p_RightChild + 1);
    v8 = 0;
  }
  else
  {
    p_RightChild = 0;
  }
  ExReleaseResourceLite((PERESOURCE)(v7 + 56));
  KeLeaveCriticalRegion();
  if ( v8 >= 0 )
  {
    KeEnterCriticalRegion();
    v11 = (struct _ERESOURCE *)(v7 + 160);
    ExAcquireResourceExclusiveLite((PERESOURCE)(v7 + 160), 1u);
    if ( (struct _RTL_SPLAY_LINKS *)v7 != p_RightChild[8] )
      goto LABEL_18;
    v12 = (struct _RTL_SPLAY_LINKS *)(p_RightChild + 6);
    v13 = p_RightChild[6];
    if ( v13 )
    {
      if ( v13->LeftChild != v12 )
        goto LABEL_28;
      v14 = p_RightChild[7];
      if ( v14->Parent != v12 )
        goto LABEL_28;
      v14->Parent = v13;
      v13->LeftChild = v14;
      v12->Parent = 0;
    }
    if ( (*((_BYTE *)p_RightChild + 12) & 1) == 0 )
      goto LABEL_18;
    v15 = (struct _RTL_SPLAY_LINKS *)(v7 + 24);
    Parent = v15->Parent;
    if ( v15->Parent->LeftChild == v15 )
    {
      v12->Parent = Parent;
      p_RightChild[7] = v15;
      Parent->LeftChild = v12;
      v15->Parent = v12;
LABEL_18:
      ExReleaseResourceLite(v11);
      KeLeaveCriticalRegion();
      Pool2 = ExAllocatePool2(258, 40, 1648584260);
      v18 = Pool2;
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
            v19,
            v20,
            v18,
            *(_QWORD *)(v18 + 16),
            *(_DWORD *)(v18 + 8),
            (__int64)(p_RightChild + 18));
        }
        if ( !*((_DWORD *)p_RightChild + 2) && !*((_WORD *)p_RightChild + 12) )
          *(_DWORD *)(v18 + 8) |= 2u;
        *(_WORD *)(v18 + 32) = -1;
        v8 = 0;
        *a3 = v18;
      }
      else
      {
        v8 = -1073741670;
        DfscRmDereferenceReferral((volatile signed __int32 *)p_RightChild);
      }
      return (unsigned int)v8;
    }
LABEL_28:
    __fastfail(3u);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14001c8ac  push    rbx
0x14001c8ae  push    rbp
0x14001c8af  push    rsi
0x14001c8b0  push    rdi
0x14001c8b1  push    r12
0x14001c8b3  push    r14
0x14001c8b5  push    r15
0x14001c8b7  sub     rsp, 50h
0x14001c8bb  mov     rbx, rdx
0x14001c8be  xorps   xmm0, xmm0
0x14001c8c1  mov     edx, 2
0x14001c8c6  mov     r15, r8
0x14001c8c9  movups  [rsp+88h+var_48], xmm0
0x14001c8ce  cmp     [rbx], dx
0x14001c8d1  jbe     short loc_14001C8E1
0x14001c8d3  mov     rax, [rbx+8]
0x14001c8d7  cmp     word ptr [rax], 5Ch ; '\'
0x14001c8db  jz      loc_14001CABA
0x14001c8e1  mov     rbp, [rcx+0F0h]
0x14001c8e8  xor     r12d, r12d
0x14001c8eb  test    rbp, rbp
0x14001c8ee  jnz     loc_14001CAAE
0x14001c8f4  mov     rbp, qword ptr cs:WPP_MAIN_CB.ActiveThreadCount
0x14001c8fb  call    cs:__imp_KeEnterCriticalRegion
0x14001c902  nop     dword ptr [rax+rax+00h]
0x14001c907  mov     dl, 1; Wait
0x14001c909  lea     rcx, [rbp+38h]; Resource
0x14001c90d  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001c914  nop     dword ptr [rax+rax+00h]
0x14001c919  xor     r8d, r8d; CaseInsensitiveIndex
0x14001c91c  mov     rdx, rbx; FullName
0x14001c91f  mov     rcx, rbp; PrefixTable
0x14001c922  mov     esi, 0C000003Ah
0x14001c927  call    cs:__imp_RtlFindUnicodePrefix
0x14001c92e  nop     dword ptr [rax+rax+00h]
0x14001c933  test    rax, rax
0x14001c936  jz      short loc_14001C946
0x14001c938  lea     rdi, [rax-48h]
0x14001c93c  test    byte ptr [rdi+0Ch], 1
0x14001c940  jnz     loc_14001CA93
0x14001c946  mov     rdi, r12
0x14001c949  lea     rcx, [rbp+38h]; Resource
0x14001c94d  call    cs:__imp_ExReleaseResourceLite
0x14001c954  nop     dword ptr [rax+rax+00h]
0x14001c959  call    cs:__imp_KeLeaveCriticalRegion
0x14001c960  nop     dword ptr [rax+rax+00h]
0x14001c965  test    esi, esi
0x14001c967  js      loc_14001CA81
0x14001c96d  call    cs:__imp_KeEnterCriticalRegion
0x14001c974  nop     dword ptr [rax+rax+00h]
0x14001c979  lea     rbx, [rbp+0A0h]
0x14001c980  mov     dl, 1; Wait
0x14001c982  mov     rcx, rbx; Resource
0x14001c985  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001c98c  nop     dword ptr [rax+rax+00h]
0x14001c991  cmp     rbp, [rdi+40h]
0x14001c995  jnz     short loc_14001C9EB
0x14001c997  lea     rcx, [rdi+30h]
0x14001c99b  mov     rax, [rcx]
0x14001c99e  test    rax, rax
0x14001c9a1  jz      short loc_14001C9C4
0x14001c9a3  cmp     [rax+8], rcx
0x14001c9a7  jnz     loc_14001CAE3
0x14001c9ad  mov     rdx, [rcx+8]
0x14001c9b1  cmp     [rdx], rcx
0x14001c9b4  jnz     loc_14001CAE3
0x14001c9ba  mov     [rdx], rax
0x14001c9bd  mov     [rax+8], rdx
0x14001c9c1  mov     [rcx], r12
0x14001c9c4  test    byte ptr [rdi+0Ch], 1
0x14001c9c8  jz      short loc_14001C9EB
0x14001c9ca  add     rbp, 18h
0x14001c9ce  mov     rax, [rbp+0]
0x14001c9d2  cmp     [rax+8], rbp
0x14001c9d6  jnz     loc_14001CAE3
0x14001c9dc  mov     [rcx], rax
0x14001c9df  mov     [rcx+8], rbp
0x14001c9e3  mov     [rax+8], rcx
0x14001c9e7  mov     [rbp+0], rcx
0x14001c9eb  mov     rcx, rbx; Resource
0x14001c9ee  call    cs:__imp_ExReleaseResourceLite
0x14001c9f5  nop     dword ptr [rax+rax+00h]
0x14001c9fa  call    cs:__imp_KeLeaveCriticalRegion
0x14001ca01  nop     dword ptr [rax+rax+00h]
0x14001ca06  mov     edx, 28h ; '('
0x14001ca0b  mov     ecx, 102h
0x14001ca10  mov     r8d, 62436644h
0x14001ca16  call    cs:__imp_ExAllocatePool2
0x14001ca1d  nop     dword ptr [rax+rax+00h]
0x14001ca22  mov     rbx, rax
0x14001ca25  test    rax, rax
0x14001ca28  jz      short loc_14001CA9F
0x14001ca2a  mov     [rax+8], r12
0x14001ca2e  mov     rcx, rax
0x14001ca31  mov     [rax+18h], r12
0x14001ca35  mov     [rax+20h], r12
0x14001ca39  mov     dword ptr [rax], 288103h
0x14001ca3f  mov     dword ptr [rax+4], 1
0x14001ca46  mov     [rax+10h], rdi
0x14001ca4a  call    DfscRmIsTimeToRefresh
0x14001ca4f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ca56  lea     rax, WPP_GLOBAL_Control
0x14001ca5d  cmp     rcx, rax
0x14001ca60  jz      short loc_14001CA6B
0x14001ca62  test    dword ptr [rcx+2Ch], 400000h
0x14001ca69  jnz     short loc_14001CAEA
0x14001ca6b  cmp     [rdi+8], r12d
0x14001ca6f  jz      loc_14001CB17
0x14001ca75  mov     word ptr [rbx+20h], 0FFFFh
0x14001ca7b  mov     esi, r12d
0x14001ca7e  mov     [r15], rbx
0x14001ca81  mov     eax, esi
0x14001ca83  add     rsp, 50h
0x14001ca87  pop     r15
0x14001ca89  pop     r14
0x14001ca8b  pop     r12
0x14001ca8d  pop     rdi
0x14001ca8e  pop     rsi
0x14001ca8f  pop     rbp
0x14001ca90  pop     rbx
0x14001ca91  retn
0x14001ca93  lock inc dword ptr [rdi+4]
0x14001ca97  mov     esi, r12d
0x14001ca9a  jmp     loc_14001C949
0x14001ca9f  mov     rcx, rdi; P
0x14001caa2  mov     esi, 0C000009Ah
0x14001caa7  call    DfscRmDereferenceReferral
0x14001caac  jmp     short loc_14001CA81
0x14001caae  mov     rbp, [rbp+80h]
0x14001cab5  jmp     loc_14001C8FB
0x14001caba  movups  xmm0, xmmword ptr [rbx]
0x14001cabd  add     rax, rdx
0x14001cac0  lea     rbx, [rsp+88h+var_48]
0x14001cac5  movups  [rsp+88h+var_48], xmm0
0x14001caca  mov     qword ptr [rsp+88h+var_48+8], rax
0x14001cacf  mov     eax, 0FFFEh
0x14001cad4  add     word ptr [rsp+88h+var_48], ax
0x14001cad9  add     word ptr [rsp+88h+var_48+2], ax
0x14001cade  jmp     loc_14001C8E1
0x14001cae3  mov     ecx, 3
0x14001cae8  int     29h; Win8: RtlFailFast(ecx)
0x14001caea  mov     rcx, [rcx+18h]
0x14001caee  lea     rax, [rdi+90h]
0x14001caf5  mov     [rsp+88h+var_58], rax
0x14001cafa  mov     r9, rbx
0x14001cafd  mov     eax, [rbx+8]
0x14001cb00  mov     [rsp+88h+var_60], eax
0x14001cb04  mov     rax, [rbx+10h]
0x14001cb08  mov     [rsp+88h+var_68], rax
0x14001cb0d  call    WPP_SF_qqDZ
0x14001cb12  jmp     loc_14001CA6B
0x14001cb17  cmp     [rdi+18h], r12w
0x14001cb1c  jnz     loc_14001CA75
0x14001cb22  or      dword ptr [rbx+8], 2
0x14001cb26  jmp     loc_14001CA75
```
