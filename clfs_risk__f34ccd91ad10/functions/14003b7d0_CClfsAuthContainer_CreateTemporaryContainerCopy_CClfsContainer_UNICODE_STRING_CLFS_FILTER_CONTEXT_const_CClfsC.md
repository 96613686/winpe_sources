# CClfsAuthContainer::CreateTemporaryContainerCopy(CClfsContainer * &,_UNICODE_STRING &,_CLFS_FILTER_CONTEXT const &,CClfsContainer * &)

- ea: `0x14003b7d0`
- end: `0x14003ba48`
- name: `?CreateTemporaryContainerCopy@CClfsAuthContainer@@AEAAJAEAPEAVCClfsContainer@@AEAU_UNICODE_STRING@@AEBU_CLFS_FILTER_CONTEXT@@0@Z`
- size: `632`
- prototype: `__int64 __usercall@<rax>(CClfsAuthContainer *__hidden this@<rcx>, struct CClfsContainer **@<rdx>, struct _UNICODE_STRING *@<r8>, const struct _CLFS_FILTER_CONTEXT *@<r9>, struct CClfsContainer **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14003eb2c`

## callees

- `0x140001474`
- `0x14000d084`
- `0x140017f20`
- `0x140033a78`
- `0x14003a52c`
- `0x14003b7d0`
- `0x14003ba50`
- `0x14003cee8`
- `0x140073128`
- `0x14007536c`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14003b8b7`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14003b8b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003b9fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ba1f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007dcad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007dccc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003b9fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ba1f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007dcad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007dccc`

## pseudocode

```c
__int64 __fastcall CClfsAuthContainer::CreateTemporaryContainerCopy(
        CClfsAuthContainer *this,
        struct CClfsContainer **a2,
        struct _UNICODE_STRING *a3,
        const struct _CLFS_FILTER_CONTEXT *a4,
        struct CClfsContainer **a5)
{
  char v8; // r14
  ULONG_PTR *v9; // rsi
  int ContainerSize; // ebx
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rdi
  unsigned int i; // edi
  CClfsContainer *v14; // rax
  CClfsContainer *v15; // rcx
  struct _UNICODE_STRING *v16; // rdx
  CClfsAuthContainer *v17; // rcx
  unsigned int v18; // r8d
  unsigned int v20[2]; // [rsp+48h] [rbp-50h] BYREF
  PVOID v21; // [rsp+50h] [rbp-48h] BYREF
  unsigned __int64 v22; // [rsp+58h] [rbp-40h] BYREF
  struct _UNICODE_STRING v23; // [rsp+60h] [rbp-38h] BYREF
  struct _UNICODE_STRING *v24; // [rsp+B0h] [rbp+18h] BYREF

  v24 = a3;
  *(_QWORD *)&v23.Length = 0;
  v23.Buffer = 0;
  v22 = 0;
  v20[0] = 0;
  LOBYTE(v24) = 0;
  v8 = 0;
  v21 = 0;
  v9 = (ULONG_PTR *)a5;
  *a5 = 0;
  ContainerSize = CClfsContainer::GetContainerSize(*a2, &v22);
  if ( ContainerSize >= 0 )
  {
    v11 = v22;
    v12 = (v22 + 4095) & 0xFFFFFFFFFFFFF000uLL;
    v22 = v12;
    if ( v12 >= v11 )
    {
      ContainerSize = CClfsAuthContainer::CreateTempContainerSecurityDescriptor(&v21);
      if ( ContainerSize >= 0 )
      {
        ContainerSize = RtlULongLongToULong(v12 >> 9, v20);
        if ( ContainerSize >= 0 )
        {
          for ( i = 0; ; ++i )
          {
            v20[1] = i;
            if ( i >= 3 )
              break;
            v14 = (CClfsContainer *)ExAllocateFromPagedLookasideList(&CClfsContainer::m_laList);
            if ( v14 )
              v15 = CClfsContainer::CClfsContainer(v14, *((_DWORD *)this + 11), 1u);
            else
              v15 = 0;
            *v9 = (ULONG_PTR)v15;
            if ( !v15 )
              goto LABEL_17;
            (**(void (__fastcall ***)(CClfsContainer *))v15)(v15);
            ContainerSize = CClfsAuthContainer::CreateTemporaryContainerPath(v17, v16, v18, &v23);
            if ( ContainerSize < 0 )
              goto LABEL_20;
            ContainerSize = CClfsContainer::Create(*v9, &v23, &v22, a4, v21, 0, 0, (unsigned __int8 *)&v24);
            if ( ContainerSize >= 0 )
              break;
            (*(void (__fastcall **)(ULONG_PTR))(*(_QWORD *)*v9 + 8LL))(*v9);
            *v9 = 0;
          }
          if ( !*v9 )
          {
            if ( ContainerSize < 0 )
              goto LABEL_20;
LABEL_17:
            ContainerSize = -1073741670;
            goto LABEL_20;
          }
          v8 = 1;
          ContainerSize = CClfsContainer::InitializeFile(*v9);
          if ( ContainerSize >= 0 )
            ContainerSize = CClfsAuthContainer::CopyFileSegment(this, *a2, (struct CClfsContainer *)*v9, 0, 0, v20[0]);
        }
      }
    }
    else
    {
      ContainerSize = -1073741675;
    }
  }
LABEL_20:
  if ( ContainerSize < 0 && *v9 )
  {
    if ( v8 )
      (*(void (__fastcall **)(ULONG_PTR))(*(_QWORD *)*v9 + 24LL))(*v9);
    (*(void (__fastcall **)(ULONG_PTR))(*(_QWORD *)*v9 + 8LL))(*v9);
    *v9 = 0;
  }
  if ( v23.Buffer )
  {
    ExFreePoolWithTag(v23.Buffer, 0);
    v23.Buffer = 0;
  }
  if ( v21 )
    ExFreePoolWithTag(v21, 0);
  return (unsigned int)ContainerSize;
}

```

## disassembly

```asm
0x14003b7d0  mov     r11, rsp
0x14003b7d3  mov     [r11+8], rbx
0x14003b7d7  mov     [r11+10h], rsi
0x14003b7db  mov     [r11+18h], r8
0x14003b7df  push    rdi
0x14003b7e0  push    r12
0x14003b7e2  push    r13
0x14003b7e4  push    r14
0x14003b7e6  push    r15
0x14003b7e8  sub     rsp, 70h
0x14003b7ec  mov     r12, r9
0x14003b7ef  mov     r15, rdx
0x14003b7f2  mov     r13, rcx
0x14003b7f5  mov     [rsp+98h+var_54], 0
0x14003b7fd  xor     eax, eax
0x14003b7ff  mov     [r11-38h], rax
0x14003b803  mov     [r11-30h], rax
0x14003b807  mov     [r11-40h], rax
0x14003b80b  mov     [rsp+98h+var_50], eax
0x14003b80f  mov     [r11+18h], al
0x14003b813  xor     r14b, r14b
0x14003b816  mov     [r11-58h], r14b
0x14003b81a  mov     [r11-48h], rax
0x14003b81e  mov     rsi, [rsp+98h+arg_20]
0x14003b826  mov     [rsi], rax
0x14003b829  lea     rdx, [r11-40h]; unsigned __int64 *
0x14003b82d  mov     rcx, [r15]; this
0x14003b830  call    ?GetContainerSize@CClfsContainer@@QEAAJAEA_K@Z; CClfsContainer::GetContainerSize(unsigned __int64 &)
0x14003b835  mov     ebx, eax
0x14003b837  mov     [rsp+98h+var_54], eax
0x14003b83b  test    eax, eax
0x14003b83d  js      loc_14003B9BF
0x14003b843  mov     rax, [rsp+98h+var_40]
0x14003b848  lea     rdi, [rax+0FFFh]
0x14003b84f  and     rdi, 0FFFFFFFFFFFFF000h
0x14003b856  mov     [rsp+98h+var_40], rdi
0x14003b85b  cmp     rdi, rax
0x14003b85e  jnb     short loc_14003B86A
0x14003b860  mov     ebx, 0C0000095h
0x14003b865  jmp     loc_14003B97B
0x14003b86a  lea     rcx, [rsp+98h+var_48]; void **
0x14003b86f  call    ?CreateTempContainerSecurityDescriptor@CClfsAuthContainer@@CAJAEAPEAX@Z; CClfsAuthContainer::CreateTempContainerSecurityDescriptor(void * &)
0x14003b874  mov     ebx, eax
0x14003b876  mov     [rsp+98h+var_54], eax
0x14003b87a  test    eax, eax
0x14003b87c  js      loc_14003B9BF
0x14003b882  shr     rdi, 9
0x14003b886  lea     rdx, [rsp+98h+var_50]; unsigned int *
0x14003b88b  mov     rcx, rdi; unsigned __int64
0x14003b88e  call    ?RtlULongLongToULong@@YAJ_KPEAK@Z; RtlULongLongToULong(unsigned __int64,ulong *)
0x14003b893  mov     ebx, eax
0x14003b895  mov     [rsp+98h+var_54], eax
0x14003b899  test    eax, eax
0x14003b89b  js      loc_14003B9BF
0x14003b8a1  xor     edi, edi
0x14003b8a3  mov     [rsp+98h+var_4C], edi
0x14003b8a7  cmp     edi, 3
0x14003b8aa  jnb     loc_14003B96A
0x14003b8b0  lea     rcx, ?m_laList@CClfsContainer@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x14003b8b7  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14003b8be  nop     dword ptr [rax+rax+00h]
0x14003b8c3  test    rax, rax
0x14003b8c6  jz      short loc_14003B8DC
0x14003b8c8  mov     r8b, 1; unsigned __int8
0x14003b8cb  mov     edx, [r13+2Ch]; unsigned int
0x14003b8cf  mov     rcx, rax; this
0x14003b8d2  call    ??0CClfsContainer@@QEAA@KE@Z; CClfsContainer::CClfsContainer(ulong,uchar)
0x14003b8d7  mov     rcx, rax
0x14003b8da  jmp     short loc_14003B8DE
0x14003b8dc  xor     ecx, ecx
0x14003b8de  mov     [rsi], rcx
0x14003b8e1  test    rcx, rcx
0x14003b8e4  jz      loc_14003B976
0x14003b8ea  mov     rax, [rcx]
0x14003b8ed  mov     rax, [rax]
0x14003b8f0  call    _guard_dispatch_icall
0x14003b8f5  lea     r9, [rsp+98h+var_38]; struct _UNICODE_STRING *
0x14003b8fa  call    ?CreateTemporaryContainerPath@CClfsAuthContainer@@AEAAJAEAU_UNICODE_STRING@@K0@Z; CClfsAuthContainer::CreateTemporaryContainerPath(_UNICODE_STRING &,ulong,_UNICODE_STRING &)
0x14003b8ff  mov     ebx, eax
0x14003b901  mov     [rsp+98h+var_54], eax
0x14003b905  test    eax, eax
0x14003b907  js      loc_14003B9BF
0x14003b90d  lea     rax, [rsp+98h+arg_10]
0x14003b915  mov     [rsp+98h+var_60], rax; unsigned __int8 *
0x14003b91a  mov     [rsp+98h+var_68], 0; unsigned __int8
0x14003b91f  mov     byte ptr [rsp+98h+var_70], 0; unsigned __int8
0x14003b924  mov     rax, [rsp+98h+var_48]
0x14003b929  mov     [rsp+98h+var_78], rax; void *
0x14003b92e  mov     r9, r12; struct _CLFS_FILTER_CONTEXT *
0x14003b931  lea     r8, [rsp+98h+var_40]; unsigned __int64 *
0x14003b936  lea     rdx, [rsp+98h+var_38]; struct _UNICODE_STRING *
0x14003b93b  mov     rcx, [rsi]; BugCheckParameter4
0x14003b93e  call    ?Create@CClfsContainer@@QEAAJAEBU_UNICODE_STRING@@AEB_KAEBU_CLFS_FILTER_CONTEXT@@QEAXEEAEAE@Z; CClfsContainer::Create(_UNICODE_STRING const &,unsigned __int64 const &,_CLFS_FILTER_CONTEXT const &,void * const,uchar,uchar,uchar &)
0x14003b943  mov     ebx, eax
0x14003b945  mov     [rsp+98h+var_54], eax
0x14003b949  test    eax, eax
0x14003b94b  jns     short loc_14003B96A
0x14003b94d  mov     rcx, [rsi]
0x14003b950  mov     rax, [rcx]
0x14003b953  mov     rax, [rax+8]
0x14003b957  call    _guard_dispatch_icall
0x14003b95c  mov     qword ptr [rsi], 0
0x14003b963  inc     edi
0x14003b965  jmp     loc_14003B8A3
0x14003b96a  mov     rcx, [rsi]; BugCheckParameter4
0x14003b96d  test    rcx, rcx
0x14003b970  jnz     short loc_14003B981
0x14003b972  test    ebx, ebx
0x14003b974  js      short loc_14003B9BF
0x14003b976  mov     ebx, 0C000009Ah
0x14003b97b  mov     [rsp+98h+var_54], ebx
0x14003b97f  jmp     short loc_14003B9BF
0x14003b981  mov     r14b, 1
0x14003b984  mov     [rsp+98h+var_58], r14b
0x14003b989  call    ?InitializeFile@CClfsContainer@@QEAAJXZ; CClfsContainer::InitializeFile(void)
0x14003b98e  mov     ebx, eax
0x14003b990  mov     [rsp+98h+var_54], eax
0x14003b994  test    eax, eax
0x14003b996  js      short loc_14003B9BF
0x14003b998  mov     eax, [rsp+98h+var_50]
0x14003b99c  mov     [rsp+98h+var_70], eax; unsigned int
0x14003b9a0  mov     dword ptr [rsp+98h+var_78], 0; unsigned int
0x14003b9a8  xor     r9d, r9d; unsigned int
0x14003b9ab  mov     r8, [rsi]; struct CClfsContainer *
0x14003b9ae  mov     rdx, [r15]; struct CClfsContainer *
0x14003b9b1  mov     rcx, r13; this
0x14003b9b4  call    ?CopyFileSegment@CClfsAuthContainer@@AEAAJPEAVCClfsContainer@@0KKK@Z; CClfsAuthContainer::CopyFileSegment(CClfsContainer *,CClfsContainer *,ulong,ulong,ulong)
0x14003b9b9  mov     ebx, eax
0x14003b9bb  mov     [rsp+98h+var_54], eax
0x14003b9bf  test    ebx, ebx
0x14003b9c1  jns     short loc_14003B9F2
0x14003b9c3  mov     rcx, [rsi]
0x14003b9c6  test    rcx, rcx
0x14003b9c9  jz      short loc_14003B9F2
0x14003b9cb  test    r14b, r14b
0x14003b9ce  jz      short loc_14003B9DC
0x14003b9d0  mov     rax, [rcx]
0x14003b9d3  mov     rax, [rax+18h]
0x14003b9d7  call    _guard_dispatch_icall
0x14003b9dc  mov     rcx, [rsi]
0x14003b9df  mov     rax, [rcx]
0x14003b9e2  mov     rax, [rax+8]
0x14003b9e6  call    _guard_dispatch_icall
0x14003b9eb  mov     qword ptr [rsi], 0
0x14003b9f2  mov     rcx, [rsp+98h+var_38.Buffer]; P
0x14003b9f7  test    rcx, rcx
0x14003b9fa  jz      short loc_14003BA13
0x14003b9fc  xor     edx, edx; Tag
0x14003b9fe  call    cs:__imp_ExFreePoolWithTag
0x14003ba05  nop     dword ptr [rax+rax+00h]
0x14003ba0a  mov     [rsp+98h+var_38.Buffer], 0
0x14003ba13  mov     rcx, [rsp+98h+var_48]; P
0x14003ba18  test    rcx, rcx
0x14003ba1b  jz      short loc_14003BA2B
0x14003ba1d  xor     edx, edx; Tag
0x14003ba1f  call    cs:__imp_ExFreePoolWithTag
0x14003ba26  nop     dword ptr [rax+rax+00h]
0x14003ba2b  mov     eax, ebx
0x14003ba2d  lea     r11, [rsp+98h+var_28]
0x14003ba32  mov     rbx, [r11+30h]
0x14003ba36  mov     rsi, [r11+38h]
0x14003ba3a  mov     rsp, r11
0x14003ba3d  pop     r15
0x14003ba3f  pop     r14
0x14003ba41  pop     r13
0x14003ba43  pop     r12
0x14003ba45  pop     rdi
0x14003ba46  retn
0x14007dc53  push    rbx
0x14007dc55  push    rbp
0x14007dc56  sub     rsp, 48h
0x14007dc5a  mov     rbp, rdx
0x14007dc5d  cmp     dword ptr [rbp+44h], 0
0x14007dc61  jge     short loc_14007DCA2
0x14007dc63  mov     rbx, [rbp+0C0h]
0x14007dc6a  cmp     qword ptr [rbx], 0
0x14007dc6e  jz      short loc_14007DCA2
0x14007dc70  cmp     byte ptr [rbp+40h], 0
0x14007dc74  jz      short loc_14007DC89
0x14007dc76  mov     rax, [rbx]
0x14007dc79  mov     rcx, [rax]
0x14007dc7c  mov     rax, [rcx+18h]
0x14007dc80  mov     rcx, [rbx]
0x14007dc83  call    _guard_dispatch_icall
0x14007dc88  nop
0x14007dc89  mov     rax, [rbx]
0x14007dc8c  mov     rcx, [rax]
0x14007dc8f  mov     rax, [rcx+8]
0x14007dc93  mov     rcx, [rbx]
0x14007dc96  call    _guard_dispatch_icall
0x14007dc9b  mov     qword ptr [rbx], 0
0x14007dca2  mov     rcx, [rbp+68h]; P
0x14007dca6  test    rcx, rcx
0x14007dca9  jz      short loc_14007DCC1
0x14007dcab  xor     edx, edx; Tag
0x14007dcad  call    cs:__imp_ExFreePoolWithTag
0x14007dcb4  nop     dword ptr [rax+rax+00h]
0x14007dcb9  mov     qword ptr [rbp+68h], 0
0x14007dcc1  mov     rcx, [rbp+50h]; P
0x14007dcc5  test    rcx, rcx
0x14007dcc8  jz      short loc_14007DCD9
0x14007dcca  xor     edx, edx; Tag
0x14007dccc  call    cs:__imp_ExFreePoolWithTag
0x14007dcd3  nop     dword ptr [rax+rax+00h]
0x14007dcd8  nop
0x14007dcd9  add     rsp, 48h
0x14007dcdd  pop     rbp
0x14007dcde  pop     rbx
0x14007dcdf  retn
```
