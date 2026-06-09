# CClfsBaseFilePersisted::CreateSharedSecurityContext(uchar,void * const)

- ea: `0x140037c74`
- end: `0x140037d82`
- name: `?CreateSharedSecurityContext@CClfsBaseFilePersisted@@QEAAJEQEAX@Z`
- size: `270`
- prototype: `__int64 __fastcall(CClfsBaseFilePersisted *__hidden this, unsigned __int8, void *const)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140015480`

## callees

- `0x14000b6b0`
- `0x140037c74`
- `0x1400389ac`
- `0x140062980`
- `0x140062a30`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140037ca3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140037ca3`
- `ntoskrnl!RtlValidSecurityDescriptor` at `0x140037cb9`
- `ntoskrnl!RtlValidSecurityDescriptor` at `0x140037cb9`

## pseudocode

```c
__int64 __fastcall CClfsBaseFilePersisted::CreateSharedSecurityContext(
        PERESOURCE *this,
        unsigned __int8 a2,
        void *const a3)
{
  struct _CLFS_CLIENT_CONTEXT *v6; // rsi
  BOOLEAN v7; // r15
  int SharedSecurityDescriptor; // ebx
  void **v9; // r12
  struct _CLFS_CLIENT_CONTEXT *v11[6]; // [rsp+38h] [rbp-30h] BYREF
  unsigned __int8 v12; // [rsp+88h] [rbp+20h] BYREF

  v12 = 0;
  v6 = 0;
  v11[0] = 0;
  v7 = ExAcquireResourceExclusiveLite(this[4], 1u);
  if ( RtlValidSecurityDescriptor(a3) )
  {
    CClfsBaseFile::AcquireClientContext((CClfsBaseFile *)this, a2, v11);
    v6 = v11[0];
    v9 = (void **)((char *)v11[0] + 128);
    SharedSecurityDescriptor = CClfsBaseFile::FindSharedSecurityDescriptor(
                                 this,
                                 a3,
                                 1u,
                                 (bool *)&v12,
                                 (void **)v11[0] + 16);
    if ( SharedSecurityDescriptor == -1073741635 )
      SharedSecurityDescriptor = CClfsBaseFile::FindSharedSecurityDescriptor(this, a3, 0, (bool *)&v12, v9);
    if ( SharedSecurityDescriptor >= 0 )
    {
      CClfsBaseFile::ReleaseClientContext((CClfsBaseFile *)this, v11);
      v6 = v11[0];
    }
  }
  else
  {
    SharedSecurityDescriptor = -1073741703;
  }
  if ( v6 )
    CClfsBaseFile::ReleaseClientContext((CClfsBaseFile *)this, v11);
  if ( v7 )
    CClfsBaseFile::UnlockImage((CClfsBaseFile *)this);
  return (unsigned int)SharedSecurityDescriptor;
}

```

## disassembly

```asm
0x140037c74  mov     rax, rsp
0x140037c77  mov     [rax+10h], rbx
0x140037c7b  mov     [rax+8], rcx
0x140037c7f  push    rsi
0x140037c80  push    rdi
0x140037c81  push    r12
0x140037c83  push    r14
0x140037c85  push    r15
0x140037c87  sub     rsp, 40h
0x140037c8b  mov     r14, r8
0x140037c8e  mov     bl, dl
0x140037c90  mov     rdi, rcx
0x140037c93  mov     byte ptr [rax+20h], 0
0x140037c97  xor     esi, esi
0x140037c99  mov     [rax-30h], rsi
0x140037c9d  mov     dl, 1; Wait
0x140037c9f  mov     rcx, [rcx+20h]; Resource
0x140037ca3  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140037caa  nop     dword ptr [rax+rax+00h]
0x140037caf  mov     r15b, al
0x140037cb2  mov     [rsp+68h+var_38], al
0x140037cb6  mov     rcx, r14; SecurityDescriptor
0x140037cb9  call    cs:__imp_RtlValidSecurityDescriptor
0x140037cc0  nop     dword ptr [rax+rax+00h]
0x140037cc5  test    al, al
0x140037cc7  jnz     short loc_140037CD4
0x140037cc9  mov     ebx, 0C0000079h
0x140037cce  mov     [rsp+68h+var_34], ebx
0x140037cd2  jmp     short loc_140037D4E
0x140037cd4  lea     r8, [rsp+68h+var_30]; struct _CLFS_CLIENT_CONTEXT **
0x140037cd9  mov     dl, bl; unsigned __int8
0x140037cdb  mov     rcx, rdi; this
0x140037cde  call    ?AcquireClientContext@CClfsBaseFile@@QEAAJEPEAPEAU_CLFS_CLIENT_CONTEXT@@@Z; CClfsBaseFile::AcquireClientContext(uchar,_CLFS_CLIENT_CONTEXT * *)
0x140037ce3  mov     rsi, [rsp+68h+var_30]
0x140037ce8  lea     r12, [rsi+80h]
0x140037cef  mov     [rsp+68h+var_48], r12; void **
0x140037cf4  lea     r9, [rsp+68h+arg_18]; unsigned __int8 *
0x140037cfc  mov     r8b, 1; unsigned __int8
0x140037cff  mov     rdx, r14; Src
0x140037d02  mov     rcx, rdi; this
0x140037d05  call    ?FindSharedSecurityDescriptor@CClfsBaseFile@@QEAAJQEAXEAEAEAEAPEAX@Z; CClfsBaseFile::FindSharedSecurityDescriptor(void * const,uchar,uchar &,void * &)
0x140037d0a  mov     ebx, eax
0x140037d0c  mov     [rsp+68h+var_34], eax
0x140037d10  cmp     eax, 0C00000BDh
0x140037d15  jnz     short loc_140037D38
0x140037d17  mov     [rsp+68h+var_48], r12; void **
0x140037d1c  lea     r9, [rsp+68h+arg_18]; unsigned __int8 *
0x140037d24  xor     r8d, r8d; unsigned __int8
0x140037d27  mov     rdx, r14; Src
0x140037d2a  mov     rcx, rdi; this
0x140037d2d  call    ?FindSharedSecurityDescriptor@CClfsBaseFile@@QEAAJQEAXEAEAEAEAPEAX@Z; CClfsBaseFile::FindSharedSecurityDescriptor(void * const,uchar,uchar &,void * &)
0x140037d32  mov     ebx, eax
0x140037d34  mov     [rsp+68h+var_34], eax
0x140037d38  test    ebx, ebx
0x140037d3a  js      short loc_140037D4E
0x140037d3c  lea     rdx, [rsp+68h+var_30]; struct _CLFS_CLIENT_CONTEXT **
0x140037d41  mov     rcx, rdi; this
0x140037d44  call    ?ReleaseClientContext@CClfsBaseFile@@QEAAJPEAPEAU_CLFS_CLIENT_CONTEXT@@@Z; CClfsBaseFile::ReleaseClientContext(_CLFS_CLIENT_CONTEXT * *)
0x140037d49  mov     rsi, [rsp+68h+var_30]
0x140037d4e  test    rsi, rsi
0x140037d51  jz      short loc_140037D60
0x140037d53  lea     rdx, [rsp+68h+var_30]; struct _CLFS_CLIENT_CONTEXT **
0x140037d58  mov     rcx, rdi; this
0x140037d5b  call    ?ReleaseClientContext@CClfsBaseFile@@QEAAJPEAPEAU_CLFS_CLIENT_CONTEXT@@@Z; CClfsBaseFile::ReleaseClientContext(_CLFS_CLIENT_CONTEXT * *)
0x140037d60  test    r15b, r15b
0x140037d63  jz      short loc_140037D6D
0x140037d65  mov     rcx, rdi; this
0x140037d68  call    ?UnlockImage@CClfsBaseFile@@QEAAXXZ; CClfsBaseFile::UnlockImage(void)
0x140037d6d  mov     eax, ebx
0x140037d6f  mov     rbx, [rsp+68h+arg_8]
0x140037d74  add     rsp, 40h
0x140037d78  pop     r15
0x140037d7a  pop     r14
0x140037d7c  pop     r12
0x140037d7e  pop     rdi
0x140037d7f  pop     rsi
0x140037d80  retn
0x14007d2cc  push    rbp
0x14007d2ce  sub     rsp, 30h
0x14007d2d2  mov     rbp, rdx
0x14007d2d5  cmp     qword ptr [rbp+38h], 0
0x14007d2da  jz      short loc_14007D2EA
0x14007d2dc  lea     rdx, [rbp+38h]; struct _CLFS_CLIENT_CONTEXT **
0x14007d2e0  mov     rcx, [rbp+70h]; this
0x14007d2e4  call    ?ReleaseClientContext@CClfsBaseFile@@QEAAJPEAPEAU_CLFS_CLIENT_CONTEXT@@@Z; CClfsBaseFile::ReleaseClientContext(_CLFS_CLIENT_CONTEXT * *)
0x14007d2e9  nop
0x14007d2ea  cmp     byte ptr [rbp+30h], 0
0x14007d2ee  jz      short loc_14007D2FA
0x14007d2f0  mov     rcx, [rbp+70h]; this
0x14007d2f4  call    ?UnlockImage@CClfsBaseFile@@QEAAXXZ; CClfsBaseFile::UnlockImage(void)
0x14007d2f9  nop
0x14007d2fa  add     rsp, 30h
0x14007d2fe  pop     rbp
0x14007d2ff  retn
```
