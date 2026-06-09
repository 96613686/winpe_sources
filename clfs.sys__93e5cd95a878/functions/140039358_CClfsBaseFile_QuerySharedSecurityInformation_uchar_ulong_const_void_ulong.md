# CClfsBaseFile::QuerySharedSecurityInformation(uchar,ulong const &,void *,ulong &)

- ea: `0x140039358`
- end: `0x1400394dc`
- name: `?QuerySharedSecurityInformation@CClfsBaseFile@@QEAAJEAEBKPEAXAEAK@Z`
- size: `388`
- prototype: `__int64 __usercall@<rax>(CClfsBaseFile *__hidden this@<rcx>, unsigned __int8@<dl>, const unsigned int *@<r8>, void *@<r9>, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140046f70`

## callees

- `0x14000b6b0`
- `0x140011cec`
- `0x140036a14`
- `0x140039358`
- `0x1400396b8`
- `0x140062980`
- `0x140062a30`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140039396`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140039396`
- `ntoskrnl!RtlValidSecurityDescriptor` at `0x14003941a`
- `ntoskrnl!RtlValidSecurityDescriptor` at `0x14003941a`
- `ntoskrnl!SeQuerySecurityDescriptorInfo` at `0x140039444`
- `ntoskrnl!SeQuerySecurityDescriptorInfo` at `0x140039444`
- `ntoskrnl!DbgPrint` at `0x140039467`
- `ntoskrnl!DbgPrint` at `0x140039467`

## string_xrefs

- `0x140039460`: `Exception when querying security: %lx\n`

## pseudocode

```c
__int64 __fastcall CClfsBaseFile::QuerySharedSecurityInformation(
        PERESOURCE *this,
        unsigned __int8 a2,
        DWORD *a3,
        void *a4,
        unsigned int *Length)
{
  BOOLEAN v9; // r14
  struct _CLFS_CLIENT_CONTEXT *v10; // rsi
  NTSTATUS SecurityDescriptorInfo; // edi
  CClfsBaseFile *v12; // rcx
  unsigned int v14; // [rsp+28h] [rbp-60h] BYREF
  struct _CLFS_SHARED_SECURITY_CONTEXT *v15; // [rsp+30h] [rbp-58h] BYREF
  struct _CLFS_CLIENT_CONTEXT *v16; // [rsp+38h] [rbp-50h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor[9]; // [rsp+40h] [rbp-48h] BYREF

  v16 = 0;
  v15 = 0;
  SecurityDescriptor[0] = 0;
  v9 = ExAcquireResourceExclusiveLite(this[4], 1u);
  CClfsBaseFile::AcquireClientContext((CClfsBaseFile *)this, a2, &v16);
  v10 = v16;
  if ( v16 )
  {
    SecurityDescriptorInfo = CClfsBaseFile::AcquireSharedSecurityContext(
                               (CClfsBaseFile *)this,
                               *((void *const *)v16 + 16),
                               &v15);
    if ( SecurityDescriptorInfo >= 0 )
    {
      SecurityDescriptorInfo = CClfsBaseFile::GetSecurityDescriptor(v12, v15, SecurityDescriptor, &v14);
      if ( SecurityDescriptorInfo >= 0 )
      {
        if ( RtlValidSecurityDescriptor(SecurityDescriptor[0]) )
          SecurityDescriptorInfo = SeQuerySecurityDescriptorInfo(a3, a4, Length, SecurityDescriptor);
        else
          SecurityDescriptorInfo = -1073741703;
      }
    }
  }
  else
  {
    SecurityDescriptorInfo = -1073741811;
  }
  if ( v15 )
    CClfsBaseFile::ReleaseSharedSecurityContext((CClfsBaseFile *)this, &v15);
  if ( v10 )
    CClfsBaseFile::ReleaseClientContext((CClfsBaseFile *)this, &v16);
  if ( v9 )
    CClfsBaseFile::UnlockImage((CClfsBaseFile *)this);
  return (unsigned int)SecurityDescriptorInfo;
}

```

## disassembly

```asm
0x140039358  mov     rax, rsp
0x14003935b  mov     [rax+8], rcx
0x14003935f  push    rbx
0x140039360  push    rsi
0x140039361  push    rdi
0x140039362  push    r12
0x140039364  push    r14
0x140039366  push    r15
0x140039368  sub     rsp, 58h
0x14003936c  mov     r15, r9
0x14003936f  mov     r12, r8
0x140039372  mov     dil, dl
0x140039375  mov     rbx, rcx
0x140039378  mov     qword ptr [rax-50h], 0
0x140039380  mov     qword ptr [rax-58h], 0
0x140039388  mov     qword ptr [rax-48h], 0
0x140039390  mov     dl, 1; Wait
0x140039392  mov     rcx, [rcx+20h]; Resource
0x140039396  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14003939d  nop     dword ptr [rax+rax+00h]
0x1400393a2  mov     r14b, al
0x1400393a5  mov     [rsp+88h+var_68], al
0x1400393a9  lea     r8, [rsp+88h+var_50]; struct _CLFS_CLIENT_CONTEXT **
0x1400393ae  mov     dl, dil; unsigned __int8
0x1400393b1  mov     rcx, rbx; this
0x1400393b4  call    ?AcquireClientContext@CClfsBaseFile@@QEAAJEPEAPEAU_CLFS_CLIENT_CONTEXT@@@Z; CClfsBaseFile::AcquireClientContext(uchar,_CLFS_CLIENT_CONTEXT * *)
0x1400393b9  mov     rsi, [rsp+88h+var_50]
0x1400393be  test    rsi, rsi
0x1400393c1  jnz     short loc_1400393D1
0x1400393c3  mov     edi, 0C000000Dh
0x1400393c8  mov     [rsp+88h+var_64], edi
0x1400393cc  jmp     loc_140039497
0x1400393d1  lea     r8, [rsp+88h+var_58]; struct _CLFS_SHARED_SECURITY_CONTEXT **
0x1400393d6  mov     rdx, [rsi+80h]; void *
0x1400393dd  mov     rcx, rbx; this
0x1400393e0  call    ?AcquireSharedSecurityContext@CClfsBaseFile@@QEAAJQEAXAEAPEAU_CLFS_SHARED_SECURITY_CONTEXT@@@Z; CClfsBaseFile::AcquireSharedSecurityContext(void * const,_CLFS_SHARED_SECURITY_CONTEXT * &)
0x1400393e5  mov     edi, eax
0x1400393e7  mov     [rsp+88h+var_64], eax
0x1400393eb  test    eax, eax
0x1400393ed  js      loc_140039497
0x1400393f3  lea     r9, [rsp+88h+var_60]; unsigned int *
0x1400393f8  lea     r8, [rsp+88h+SecurityDescriptor]; void **
0x1400393fd  mov     rdx, [rsp+88h+var_58]; struct _CLFS_SHARED_SECURITY_CONTEXT *
0x140039402  call    ?GetSecurityDescriptor@CClfsBaseFile@@IEAAJAEBU_CLFS_SHARED_SECURITY_CONTEXT@@AEAPEAXAEAK@Z; CClfsBaseFile::GetSecurityDescriptor(_CLFS_SHARED_SECURITY_CONTEXT const &,void * &,ulong &)
0x140039407  mov     edi, eax
0x140039409  mov     [rsp+88h+var_64], eax
0x14003940d  test    eax, eax
0x14003940f  js      loc_140039497
0x140039415  mov     rcx, [rsp+88h+SecurityDescriptor]; SecurityDescriptor
0x14003941a  call    cs:__imp_RtlValidSecurityDescriptor
0x140039421  nop     dword ptr [rax+rax+00h]
0x140039426  test    al, al
0x140039428  jnz     short loc_140039431
0x14003942a  mov     edi, 0C0000079h
0x14003942f  jmp     short loc_1400393C8
0x140039431  lea     r9, [rsp+88h+SecurityDescriptor]; ObjectsSecurityDescriptor
0x140039436  mov     r8, [rsp+88h+Length]; Length
0x14003943e  mov     rdx, r15; SecurityDescriptor
0x140039441  mov     rcx, r12; SecurityInformation
0x140039444  call    cs:__imp_SeQuerySecurityDescriptorInfo
0x14003944b  nop     dword ptr [rax+rax+00h]
0x140039450  mov     edi, eax
0x140039452  mov     [rsp+88h+var_64], eax
0x140039456  jmp     short loc_140039497
0x140039458  mov     ebx, eax
0x14003945a  mov     edi, [rsp+88h+var_64]
0x14003945e  mov     edx, edi
0x140039460  lea     rcx, Format; "Exception when querying security: %lx\n"
0x140039467  call    cs:__imp_DbgPrint
0x14003946e  nop     dword ptr [rax+rax+00h]
0x140039473  mov     eax, 0C00000E8h
0x140039478  cmp     ebx, 0C0000005h
0x14003947e  cmovz   edi, eax
0x140039481  mov     [rsp+88h+var_64], edi
0x140039485  mov     rbx, [rsp+88h+arg_0]
0x14003948d  mov     rsi, [rsp+88h+var_50]
0x140039492  mov     r14b, [rsp+88h+var_68]
0x140039497  cmp     [rsp+88h+var_58], 0
0x14003949d  jz      short loc_1400394AC
0x14003949f  lea     rdx, [rsp+88h+var_58]; struct _CLFS_SHARED_SECURITY_CONTEXT **
0x1400394a4  mov     rcx, rbx; this
0x1400394a7  call    ?ReleaseSharedSecurityContext@CClfsBaseFile@@QEAAJAEAPEAU_CLFS_SHARED_SECURITY_CONTEXT@@@Z; CClfsBaseFile::ReleaseSharedSecurityContext(_CLFS_SHARED_SECURITY_CONTEXT * &)
0x1400394ac  test    rsi, rsi
0x1400394af  jz      short loc_1400394BE
0x1400394b1  lea     rdx, [rsp+88h+var_50]; struct _CLFS_CLIENT_CONTEXT **
0x1400394b6  mov     rcx, rbx; this
0x1400394b9  call    ?ReleaseClientContext@CClfsBaseFile@@QEAAJPEAPEAU_CLFS_CLIENT_CONTEXT@@@Z; CClfsBaseFile::ReleaseClientContext(_CLFS_CLIENT_CONTEXT * *)
0x1400394be  test    r14b, r14b
0x1400394c1  jz      short loc_1400394CB
0x1400394c3  mov     rcx, rbx; this
0x1400394c6  call    ?UnlockImage@CClfsBaseFile@@QEAAXXZ; CClfsBaseFile::UnlockImage(void)
0x1400394cb  mov     eax, edi
0x1400394cd  add     rsp, 58h
0x1400394d1  pop     r15
0x1400394d3  pop     r14
0x1400394d5  pop     r12
0x1400394d7  pop     rdi
0x1400394d8  pop     rsi
0x1400394d9  pop     rbx
0x1400394da  retn
0x14007d67a  push    rbp
0x14007d67c  sub     rsp, 20h
0x14007d680  mov     rbp, rdx
0x14007d683  cmp     qword ptr [rbp+30h], 0
0x14007d688  jz      short loc_14007D69B
0x14007d68a  lea     rdx, [rbp+30h]; struct _CLFS_SHARED_SECURITY_CONTEXT **
0x14007d68e  mov     rcx, [rbp+90h]; this
0x14007d695  call    ?ReleaseSharedSecurityContext@CClfsBaseFile@@QEAAJAEAPEAU_CLFS_SHARED_SECURITY_CONTEXT@@@Z; CClfsBaseFile::ReleaseSharedSecurityContext(_CLFS_SHARED_SECURITY_CONTEXT * &)
0x14007d69a  nop
0x14007d69b  cmp     qword ptr [rbp+38h], 0
0x14007d6a0  jz      short loc_14007D6B3
0x14007d6a2  lea     rdx, [rbp+38h]; struct _CLFS_CLIENT_CONTEXT **
0x14007d6a6  mov     rcx, [rbp+90h]; this
0x14007d6ad  call    ?ReleaseClientContext@CClfsBaseFile@@QEAAJPEAPEAU_CLFS_CLIENT_CONTEXT@@@Z; CClfsBaseFile::ReleaseClientContext(_CLFS_CLIENT_CONTEXT * *)
0x14007d6b2  nop
0x14007d6b3  cmp     byte ptr [rbp+20h], 0
0x14007d6b7  jz      short loc_14007D6C6
0x14007d6b9  mov     rcx, [rbp+90h]; this
0x14007d6c0  call    ?UnlockImage@CClfsBaseFile@@QEAAXXZ; CClfsBaseFile::UnlockImage(void)
0x14007d6c5  nop
0x14007d6c6  add     rsp, 20h
0x14007d6ca  pop     rbp
0x14007d6cb  retn
```
