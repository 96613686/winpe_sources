# DfsRootFolder::SetApiInformation(_UNICODE_STRING *,ushort const *,ushort const *,ulong,void * *)

- ea: `0x14002f5b4`
- end: `0x14002f99c`
- name: `?SetApiInformation@DfsRootFolder@@QEAAKPEAU_UNICODE_STRING@@PEBG1KPEAPEAX@Z`
- size: `1000`
- prototype: `unsigned int __fastcall(DfsRootFolder *__hidden this, struct _UNICODE_STRING *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140012224`

## callees

- `0x14000a354`
- `0x14000abc4`
- `0x14001e3dc`
- `0x140029d04`
- `0x14002bec8`
- `0x14002f5b4`
- `0x140030e44`
- `0x1400310bc`
- `0x140032398`
- `0x140039f20`
- `0x14005e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002f65f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002f65f`
- `ADVAPI32!IsValidRelativeSecurityDescriptor` at `0x14002f85a`
- `ADVAPI32!IsValidRelativeSecurityDescriptor` at `0x14002f85a`

## pseudocode

```c
int __fastcall DfsRootFolder::SetApiInformation(
        RTL_SRWLOCK *this,
        struct _UNICODE_STRING *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        void **a6)
{
  char v6; // r15
  struct DfsFolder *v8; // r14
  int result; // eax
  unsigned int v13; // eax
  int updated; // ebx
  unsigned int *v15; // rdx
  unsigned int v16; // ecx
  unsigned int v17; // r8d
  unsigned int v18; // r9d
  void *v19; // rbx
  __int64 v20; // rdx
  unsigned int v21; // ecx
  DfsStore *v22; // rax
  unsigned __int16 *v23; // rsi
  int v24; // r8d
  __int64 v25; // r9
  struct DfsFolder *v26; // rdx
  unsigned __int8 v27; // [rsp+40h] [rbp-30h]
  unsigned __int8 v28; // [rsp+41h] [rbp-2Fh]
  unsigned __int64 v29; // [rsp+48h] [rbp-28h] BYREF
  DfsGeneric *v30; // [rsp+50h] [rbp-20h] BYREF
  unsigned __int16 *v31; // [rsp+58h] [rbp-18h]
  struct _UNICODE_STRING v32; // [rsp+60h] [rbp-10h] BYREF
  int v33; // [rsp+A8h] [rbp+38h]

  v33 = (int)a2;
  v6 = 0;
  v29 = 0;
  v30 = 0;
  v8 = 0;
  v27 = 0;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  result = DfsRootFolder::AcquireRootLock((DfsRootFolder *)this, 1u);
  if ( result )
    return result;
  if ( !a2->Length )
    goto LABEL_11;
  v6 = 1;
  v13 = DfsRootFolder::LookupFolderByLogicalName((DfsRootFolder *)this, a2, &v32, &v30, 0);
  v8 = v30;
  updated = v13;
  if ( !v13 )
  {
    if ( v32.Length )
    {
      updated = 1168;
      goto LABEL_6;
    }
    v31 = (unsigned __int16 *)*((_QWORD *)v30 + 9);
LABEL_11:
    v15 = (unsigned int *)*a6;
    if ( !*a6 )
    {
LABEL_12:
      updated = 87;
      goto LABEL_6;
    }
    if ( a5 == 101 || a5 == 106 )
    {
      v16 = *v15;
      if ( a3 || a4 )
      {
        if ( (a5 == 101 || v16) && v16 - 1 > 1 )
          goto LABEL_12;
      }
      else if ( !IsValidLinkState(v16) )
      {
        goto LABEL_12;
      }
      if ( !v6 && v16 >= 3 )
      {
        updated = IsValidLinkState(v16) != 0 ? 50 : 87;
        goto LABEL_6;
      }
    }
    if ( ((a5 - 103) & 0xFFFFFFF9) == 0 && a5 != 109 )
    {
      if ( a3 || a4 )
        goto LABEL_59;
      if ( a5 == 103 )
      {
        v17 = *v15;
        v18 = v15[1];
      }
      else
      {
        v17 = v15[4];
        v18 = v15[5];
        v21 = v15[2];
        if ( a5 == 105 )
        {
          if ( v21 && !IsValidLinkState(v21) )
            goto LABEL_12;
        }
        else
        {
          if ( v21 && !IsValidLinkState(v21) )
            goto LABEL_12;
          if ( !v6 && *((_QWORD *)v15 + 4) )
            goto LABEL_59;
        }
      }
      if ( (v18 & 0xFFFFFFC0) != 0 || (v17 & 0xFFFFFFC0) != 0 )
        goto LABEL_12;
      if ( (v17 & 2) != 0 && LODWORD(this[39].Ptr) != 512 || (v17 & 0x10) != 0 || (v17 & 0x26) != 0 && v6 )
      {
LABEL_59:
        updated = 50;
        goto LABEL_6;
      }
      if ( (v17 & 0x20) != 0 )
      {
        if ( ((__int64)this[29].Ptr & 1) == 0 )
          goto LABEL_59;
        v27 = 1;
      }
    }
    if ( ((a5 - 104) & 0xFFFFFFFD) == 0 && !a3 && !a4 )
      goto LABEL_59;
    if ( a5 == 150 )
    {
      if ( a3 || a4 || !v6 || ((__int64)this[29].Ptr & 1) == 0 )
        goto LABEL_59;
      v19 = (void *)*((_QWORD *)v15 + 1);
      v20 = *v15;
      if ( v19 )
        goto LABEL_64;
    }
    else
    {
      if ( a5 != 107 )
        goto LABEL_67;
      v19 = (void *)*((_QWORD *)v15 + 4);
      v20 = v15[6];
      if ( v19 )
      {
        if ( !v6 || ((__int64)this[29].Ptr & 1) == 0 )
          goto LABEL_59;
LABEL_64:
        if ( (unsigned int)IsValidRelativeSecurityDescriptor(v19, v20, 0) )
        {
          updated = DfspCheckLinkSecurityDescriptor(v19);
          if ( updated )
            goto LABEL_6;
          goto LABEL_66;
        }
        goto LABEL_59;
      }
    }
LABEL_66:
    v28 = 1;
LABEL_67:
    updated = (*((__int64 (__fastcall **)(RTL_SRWLOCK *, unsigned __int64 *))this->Ptr + 7))(this, &v29);
    if ( !updated )
    {
      v22 = (DfsStore *)(*((__int64 (__fastcall **)(RTL_SRWLOCK *))this->Ptr + 3))(this);
      v23 = v31;
      updated = DfsStore::SetStoreApiInformation(v22, v29, v31, a3, a4, a5, a6);
      if ( updated )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && pWppControl
          && (pWppControl[7] & 0x840) != 0
          && *((_BYTE *)pWppControl + 25) )
        {
          WPP_SF_ZSSD(*((_QWORD *)pWppControl + 2), 60, v24, v33, (__int64)a3, (__int64)a4, updated);
        }
        LOBYTE(v25) = 1;
        (*((void (__fastcall **)(RTL_SRWLOCK *, __int64, _QWORD, __int64))this->Ptr + 4))(this, 3, 0, v25);
      }
      else
      {
        updated = DfsRootFolder::UpdateFolderInformation((DfsRootFolder *)this, v29, v23, v8, v28, v27);
      }
      (*((void (__fastcall **)(RTL_SRWLOCK *, unsigned __int64))this->Ptr + 8))(this, v29);
      if ( !updated )
      {
        if ( v6 )
          v26 = v8;
        else
          v26 = (struct DfsFolder *)this;
        DfsRootFolder::UpdateLinkFolder((DfsRootFolder *)this, v26);
      }
    }
  }
LABEL_6:
  if ( v8 )
    DfsGeneric::ReleaseReference(v8);
  ++LODWORD(this[15].Ptr);
  ReleaseSRWLockExclusive(this + 14);
  return updated;
}

```

## disassembly

```asm
0x14002f5b4  mov     rax, rsp
0x14002f5b7  mov     [rax+8], rbx
0x14002f5bb  mov     [rax+18h], rsi
0x14002f5bf  mov     [rax+20h], rdi
0x14002f5c3  mov     [rax+10h], rdx
0x14002f5c7  push    rbp
0x14002f5c8  push    r12
0x14002f5ca  push    r13
0x14002f5cc  push    r14
0x14002f5ce  push    r15
0x14002f5d0  mov     rbp, rsp
0x14002f5d3  sub     rsp, 70h
0x14002f5d7  xor     r15d, r15d
0x14002f5da  mov     rbx, rdx
0x14002f5dd  xorps   xmm0, xmm0
0x14002f5e0  mov     [rbp+var_28], r15
0x14002f5e4  mov     dl, 1; unsigned __int8
0x14002f5e6  mov     [rbp+var_20], r15
0x14002f5ea  mov     r14d, r15d
0x14002f5ed  mov     [rbp+var_30], r15b
0x14002f5f1  mov     [rbp+var_2F], r15b
0x14002f5f5  mov     r12, r9
0x14002f5f8  mov     [rbp+var_18], r15
0x14002f5fc  mov     r13, r8
0x14002f5ff  movups  xmmword ptr [rbp+var_10.Length], xmm0
0x14002f603  mov     rdi, rcx
0x14002f606  call    ?AcquireRootLock@DfsRootFolder@@QEAAKE@Z; DfsRootFolder::AcquireRootLock(uchar)
0x14002f60b  test    eax, eax
0x14002f60d  jnz     short loc_14002F66D
0x14002f60f  cmp     [rbx], r15w
0x14002f613  jnz     short loc_14002F619
0x14002f615  xor     ebx, ebx
0x14002f617  jmp     short loc_14002F694
0x14002f619  lea     r9, [rbp+var_20]; struct DfsFolder **
0x14002f61d  mov     [rsp+70h+var_50], r14; unsigned __int8 *
0x14002f622  lea     r8, [rbp+var_10]; struct _UNICODE_STRING *
0x14002f626  mov     rdx, rbx; struct _UNICODE_STRING *
0x14002f629  mov     rcx, rdi; this
0x14002f62c  mov     r15b, 1
0x14002f62f  call    ?LookupFolderByLogicalName@DfsRootFolder@@QEAAKPEAU_UNICODE_STRING@@0PEAPEAVDfsFolder@@PEAE@Z; DfsRootFolder::LookupFolderByLogicalName(_UNICODE_STRING *,_UNICODE_STRING *,DfsFolder * *,uchar *)
0x14002f634  mov     r14, [rbp+var_20]
0x14002f638  mov     ebx, eax
0x14002f63a  test    eax, eax
0x14002f63c  jnz     short loc_14002F64B
0x14002f63e  xor     ebx, ebx
0x14002f640  cmp     [rbp+var_10.Length], bx
0x14002f644  jz      short loc_14002F68C
0x14002f646  mov     ebx, 490h
0x14002f64b  test    r14, r14
0x14002f64e  jz      short loc_14002F658
0x14002f650  mov     rcx, r14; this
0x14002f653  call    ?ReleaseReference@DfsGeneric@@QEAAJXZ; DfsGeneric::ReleaseReference(void)
0x14002f658  inc     dword ptr [rdi+78h]
0x14002f65b  lea     rcx, [rdi+70h]; SRWLock
0x14002f65f  call    cs:__imp_ReleaseSRWLockExclusive
0x14002f666  nop     dword ptr [rax+rax+00h]
0x14002f66b  mov     eax, ebx
0x14002f66d  lea     r11, [rsp+70h+var_s0]
0x14002f672  mov     rbx, [r11+30h]
0x14002f676  mov     rsi, [r11+40h]
0x14002f67a  mov     rdi, [r11+48h]
0x14002f67e  mov     rsp, r11
0x14002f681  pop     r15
0x14002f683  pop     r14
0x14002f685  pop     r13
0x14002f687  pop     r12
0x14002f689  pop     rbp
0x14002f68a  retn
0x14002f68c  mov     rax, [r14+48h]
0x14002f690  mov     [rbp+var_18], rax
0x14002f694  mov     rax, [rbp+arg_28]
0x14002f698  mov     rdx, [rax]
0x14002f69b  test    rdx, rdx
0x14002f69e  jnz     short loc_14002F6A7
0x14002f6a0  mov     ebx, 57h ; 'W'
0x14002f6a5  jmp     short loc_14002F64B
0x14002f6a7  mov     esi, [rbp+arg_20]
0x14002f6aa  cmp     esi, 65h ; 'e'
0x14002f6ad  jz      short loc_14002F6B4
0x14002f6af  cmp     esi, 6Ah ; 'j'
0x14002f6b2  jnz     short loc_14002F6FE
0x14002f6b4  mov     ecx, [rdx]; unsigned int
0x14002f6b6  test    r13, r13
0x14002f6b9  jnz     short loc_14002F6CB
0x14002f6bb  test    r12, r12
0x14002f6be  jnz     short loc_14002F6CB
0x14002f6c0  call    ?IsValidLinkState@@YAEK@Z; IsValidLinkState(ulong)
0x14002f6c5  test    al, al
0x14002f6c7  jnz     short loc_14002F6DC
0x14002f6c9  jmp     short loc_14002F6A0
0x14002f6cb  cmp     esi, 65h ; 'e'
0x14002f6ce  jz      short loc_14002F6D4
0x14002f6d0  test    ecx, ecx
0x14002f6d2  jz      short loc_14002F6DC
0x14002f6d4  lea     eax, [rcx-1]
0x14002f6d7  cmp     eax, 1
0x14002f6da  ja      short loc_14002F6A0
0x14002f6dc  test    r15b, r15b
0x14002f6df  jnz     short loc_14002F6FE
0x14002f6e1  cmp     ecx, 3
0x14002f6e4  jb      short loc_14002F6FE
0x14002f6e6  call    ?IsValidLinkState@@YAEK@Z; IsValidLinkState(ulong)
0x14002f6eb  neg     al
0x14002f6ed  mov     ebx, 57h ; 'W'
0x14002f6f2  sbb     ecx, ecx
0x14002f6f4  and     ecx, 0FFFFFFDBh
0x14002f6f7  add     ebx, ecx
0x14002f6f9  jmp     loc_14002F64B
0x14002f6fe  lea     eax, [rsi-67h]
0x14002f701  test    eax, 0FFFFFFF9h
0x14002f706  jnz     loc_14002F790
0x14002f70c  cmp     esi, 6Dh ; 'm'
0x14002f70f  jz      short loc_14002F790
0x14002f711  test    r13, r13
0x14002f714  jnz     loc_14002F82B
0x14002f71a  test    r12, r12
0x14002f71d  jnz     loc_14002F82B
0x14002f723  cmp     esi, 67h ; 'g'
0x14002f726  jnz     loc_14002F7DD
0x14002f72c  mov     r8d, [rdx]
0x14002f72f  mov     r9d, [rdx+4]
0x14002f733  mov     eax, 0FFFFFFC0h
0x14002f738  test    eax, r9d
0x14002f73b  jnz     loc_14002F6A0
0x14002f741  test    eax, r8d
0x14002f744  jnz     loc_14002F6A0
0x14002f74a  test    r8b, 2
0x14002f74e  jz      short loc_14002F760
0x14002f750  cmp     dword ptr [rdi+138h], 200h
0x14002f75a  jnz     loc_14002F82B
0x14002f760  test    r8b, 10h
0x14002f764  jnz     loc_14002F82B
0x14002f76a  test    r8b, 26h
0x14002f76e  jz      short loc_14002F779
0x14002f770  test    r15b, r15b
0x14002f773  jnz     loc_14002F82B
0x14002f779  test    r8b, 20h
0x14002f77d  jz      short loc_14002F790
0x14002f77f  test    byte ptr [rdi+0E8h], 1
0x14002f786  jz      loc_14002F82B
0x14002f78c  mov     [rbp+var_30], 1
0x14002f790  lea     eax, [rsi-68h]
0x14002f793  test    eax, 0FFFFFFFDh
0x14002f798  jnz     short loc_14002F7A8
0x14002f79a  test    r13, r13
0x14002f79d  jnz     short loc_14002F7A8
0x14002f79f  test    r12, r12
0x14002f7a2  jz      loc_14002F82B
0x14002f7a8  cmp     esi, 96h
0x14002f7ae  jnz     loc_14002F835
0x14002f7b4  test    r13, r13
0x14002f7b7  jnz     short loc_14002F82B
0x14002f7b9  test    r12, r12
0x14002f7bc  jnz     short loc_14002F82B
0x14002f7be  test    r15b, r15b
0x14002f7c1  jz      short loc_14002F82B
0x14002f7c3  test    byte ptr [rdi+0E8h], 1
0x14002f7ca  jz      short loc_14002F82B
0x14002f7cc  mov     rbx, [rdx+8]
0x14002f7d0  mov     edx, [rdx]
0x14002f7d2  test    rbx, rbx
0x14002f7d5  jz      loc_14002F87C
0x14002f7db  jmp     short loc_14002F854
0x14002f7dd  mov     r8d, [rdx+10h]
0x14002f7e1  mov     r9d, [rdx+14h]
0x14002f7e5  mov     ecx, [rdx+8]; unsigned int
0x14002f7e8  cmp     esi, 69h ; 'i'
0x14002f7eb  jnz     short loc_14002F807
0x14002f7ed  test    ecx, ecx
0x14002f7ef  jz      loc_14002F733
0x14002f7f5  call    ?IsValidLinkState@@YAEK@Z; IsValidLinkState(ulong)
0x14002f7fa  test    al, al
0x14002f7fc  jnz     loc_14002F733
0x14002f802  jmp     loc_14002F6A0
0x14002f807  test    ecx, ecx
0x14002f809  jz      short loc_14002F818
0x14002f80b  call    ?IsValidLinkState@@YAEK@Z; IsValidLinkState(ulong)
0x14002f810  test    al, al
0x14002f812  jz      loc_14002F6A0
0x14002f818  test    r15b, r15b
0x14002f81b  jnz     loc_14002F733
0x14002f821  cmp     [rdx+20h], rbx
0x14002f825  jz      loc_14002F733
0x14002f82b  mov     ebx, 32h ; '2'
0x14002f830  jmp     loc_14002F64B
0x14002f835  cmp     esi, 6Bh ; 'k'
0x14002f838  jnz     short loc_14002F880
0x14002f83a  mov     rbx, [rdx+20h]
0x14002f83e  mov     edx, [rdx+18h]
0x14002f841  test    rbx, rbx
0x14002f844  jz      short loc_14002F87C
0x14002f846  test    r15b, r15b
0x14002f849  jz      short loc_14002F82B
0x14002f84b  test    byte ptr [rdi+0E8h], 1
0x14002f852  jz      short loc_14002F82B
0x14002f854  xor     r8d, r8d
0x14002f857  mov     rcx, rbx
0x14002f85a  call    cs:__imp_IsValidRelativeSecurityDescriptor
0x14002f861  nop     dword ptr [rax+rax+00h]
0x14002f866  test    eax, eax
0x14002f868  jz      short loc_14002F82B
0x14002f86a  mov     rcx, rbx; pSecurityDescriptor
0x14002f86d  call    ?DfspCheckLinkSecurityDescriptor@@YAKPEAX@Z; DfspCheckLinkSecurityDescriptor(void *)
0x14002f872  mov     ebx, eax
0x14002f874  test    eax, eax
0x14002f876  jnz     loc_14002F64B
0x14002f87c  mov     [rbp+var_2F], 1
0x14002f880  mov     rax, [rdi]
0x14002f883  lea     rdx, [rbp+var_28]
0x14002f887  mov     rcx, rdi
0x14002f88a  mov     rax, [rax+38h]
0x14002f88e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f893  mov     ebx, eax
0x14002f895  test    eax, eax
0x14002f897  jnz     loc_14002F64B
0x14002f89d  mov     rax, [rdi]
0x14002f8a0  mov     rcx, rdi
0x14002f8a3  mov     rax, [rax+18h]
0x14002f8a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f8ac  mov     rcx, [rbp+arg_28]
0x14002f8b0  mov     r9, r13; unsigned __int16 *
0x14002f8b3  mov     rdx, [rbp+var_28]; unsigned __int64
0x14002f8b7  mov     [rsp+70h+var_40], rcx; void **
0x14002f8bc  mov     rcx, rax; this
0x14002f8bf  mov     dword ptr [rsp+70h+var_48], esi; unsigned int
0x14002f8c3  mov     rsi, [rbp+var_18]
0x14002f8c7  mov     r8, rsi; unsigned __int16 *
0x14002f8ca  mov     [rsp+70h+var_50], r12; unsigned __int16 *
0x14002f8cf  call    ?SetStoreApiInformation@DfsStore@@QEAAK_KPEBG11KPEAPEAX@Z; DfsStore::SetStoreApiInformation(unsigned __int64,ushort const *,ushort const *,ushort const *,ulong,void * *)
0x14002f8d4  mov     ebx, eax
0x14002f8d6  test    eax, eax
0x14002f8d8  jnz     short loc_14002F8FE
0x14002f8da  mov     al, [rbp+var_30]
0x14002f8dd  mov     r9, r14; struct DfsFolder *
0x14002f8e0  mov     rdx, [rbp+var_28]; unsigned __int64
0x14002f8e4  mov     r8, rsi; unsigned __int16 *
0x14002f8e7  mov     [rsp+70h+var_48], al; unsigned __int8
0x14002f8eb  mov     rcx, rdi; this
0x14002f8ee  mov     al, [rbp+var_2F]
0x14002f8f1  mov     byte ptr [rsp+70h+var_50], al; unsigned __int8
0x14002f8f5  call    ?UpdateFolderInformation@DfsRootFolder@@QEAAK_KPEBGPEAVDfsFolder@@EE@Z; DfsRootFolder::UpdateFolderInformation(unsigned __int64,ushort const *,DfsFolder *,uchar,uchar)
0x14002f8fa  mov     ebx, eax
0x14002f8fc  jmp     short loc_14002F967
0x14002f8fe  lea     rax, WPP_GLOBAL_Control
0x14002f905  cmp     cs:WPP_GLOBAL_Control, rax
0x14002f90c  jz      short loc_14002F94E
0x14002f90e  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14002f915  test    rcx, rcx
0x14002f918  jz      short loc_14002F94E
0x14002f91a  mov     eax, 40h ; '@'
0x14002f91f  bts     eax, 0Bh
0x14002f923  test    [rcx+1Ch], eax
0x14002f926  jz      short loc_14002F94E
0x14002f928  cmp     byte ptr [rcx+19h], 1
0x14002f92c  jb      short loc_14002F94E
0x14002f92e  mov     r9, [rbp+arg_8]
0x14002f932  mov     edx, 3Ch ; '<'
0x14002f937  mov     rcx, [rcx+10h]
0x14002f93b  mov     dword ptr [rsp+70h+var_40], ebx
0x14002f93f  mov     qword ptr [rsp+70h+var_48], r12
0x14002f944  mov     [rsp+70h+var_50], r13
0x14002f949  call    WPP_SF_ZSSD
0x14002f94e  mov     rax, [rdi]
0x14002f951  xor     r8d, r8d
0x14002f954  mov     r9b, 1
0x14002f957  mov     rcx, rdi
0x14002f95a  mov     rax, [rax+20h]
0x14002f95e  lea     edx, [r8+3]
0x14002f962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f967  mov     rax, [rdi]
0x14002f96a  mov     rcx, rdi
0x14002f96d  mov     rdx, [rbp+var_28]
0x14002f971  mov     rax, [rax+40h]
0x14002f975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f97a  test    ebx, ebx
0x14002f97c  jnz     loc_14002F64B
0x14002f982  mov     rcx, rdi; this
0x14002f985  test    r15b, r15b
0x14002f988  jz      short loc_14002F997
0x14002f98a  mov     rdx, r14; struct DfsFolder *
0x14002f98d  call    ?UpdateLinkFolder@DfsRootFolder@@QEAAKPEAVDfsFolder@@@Z; DfsRootFolder::UpdateLinkFolder(DfsFolder *)
0x14002f992  jmp     loc_14002F64B
0x14002f997  mov     rdx, rdi
0x14002f99a  jmp     short loc_14002F98D
```
