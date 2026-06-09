# CClfsBaseFilePersisted::CreateContainer(_UNICODE_STRING const &,unsigned __int64 const &,ulong,uchar,uchar,ulong,CClfsAuthContainer * &)

- ea: `0x140062ef8`
- end: `0x14006327a`
- name: `?CreateContainer@CClfsBaseFilePersisted@@AEAAJAEBU_UNICODE_STRING@@AEB_KKEEKAEAPEAVCClfsAuthContainer@@@Z`
- size: `898`
- prototype: `__int64 __usercall@<rax>(CClfsBaseFilePersisted *__hidden this@<rcx>, const struct _UNICODE_STRING *@<rdx>, const unsigned __int64 *@<r8>, unsigned int@<r9d>, unsigned __int8, char, unsigned int, struct CClfsAuthContainer **)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140061f34`

## callees

- `0x14000b6b0`
- `0x14000d71c`
- `0x140017f20`
- `0x140034190`
- `0x14003a7cc`
- `0x14003be24`
- `0x14003be98`
- `0x140062ef8`
- `0x140063844`
- `0x140063b84`
- `0x14006a6fc`
- `0x14006e00c`
- `0x140075d10`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140062fe3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140062fe3`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140062f6c`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140062f6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006325b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a8cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006325b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a8cf`

## pseudocode

```c
__int64 __fastcall CClfsBaseFilePersisted::CreateContainer(
        CClfsBaseFilePersisted *this,
        const struct _UNICODE_STRING *a2,
        unsigned __int64 *a3,
        char a4,
        unsigned __int8 a5,
        char a6,
        unsigned int a7,
        struct CClfsAuthContainer **a8)
{
  BOOLEAN v10; // r15
  char v11; // r13
  char v12; // r12
  PVOID v13; // rax
  __int64 v14; // rdx
  struct CClfsAuthContainer *v15; // rcx
  int v16; // edi
  unsigned int *v17; // r8
  int v18; // eax
  _WORD *v19; // rbx
  __int16 v20; // ax
  unsigned __int64 *v21; // rbx
  int v22; // ebx
  void *v24; // [rsp+20h] [rbp-88h]
  unsigned __int8 v25; // [rsp+41h] [rbp-67h] BYREF
  char v26; // [rsp+42h] [rbp-66h]
  char v27; // [rsp+43h] [rbp-65h]
  int v28; // [rsp+44h] [rbp-64h]
  PVOID P; // [rsp+48h] [rbp-60h] BYREF
  struct _UNICODE_STRING v30; // [rsp+50h] [rbp-58h] BYREF
  unsigned __int64 v31[9]; // [rsp+60h] [rbp-48h] BYREF

  P = 0;
  *(_QWORD *)&v30.Length = 0;
  v30.Buffer = 0;
  v28 = 0;
  v10 = 0;
  v25 = 0;
  v11 = 0;
  v26 = 0;
  v12 = 0;
  v27 = 0;
  v31[0] = 2;
  v31[1] = a7;
  *a8 = 0;
  v13 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceQueue.32);
  if ( v13 )
    v15 = (struct CClfsAuthContainer *)CClfsAuthContainer::CClfsAuthContainer(
                                         v13,
                                         v14,
                                         *((unsigned int *)this + 58),
                                         *((_QWORD *)this + 30));
  else
    v15 = 0;
  *a8 = v15;
  if ( !v15 )
  {
    v16 = -1073741670;
LABEL_6:
    v28 = v16;
    goto LABEL_33;
  }
  (**(void (__fastcall ***)(struct CClfsAuthContainer *))v15)(v15);
  v16 = CClfsAuthContainer::Initialize(*a8, v31, 2u);
  v28 = v16;
  if ( v16 >= 0 )
  {
    v10 = ExAcquireResourceExclusiveLite(*((PERESOURCE *)this + 4), 1u);
    if ( a6 )
    {
      v15 = *(struct CClfsAuthContainer **)(*((_QWORD *)this + 19) + 120LL);
      if ( !v15 || (int)CClfsContainer::DuplicateSecurityDescriptor(v15, &P, v17, 1) < 0 )
      {
        v16 = -1073741703;
        goto LABEL_6;
      }
    }
    else
    {
      v18 = CClfsContainer::DuplicateNullSecurityDescriptor(&P, 0);
      v16 = v18;
      if ( v18 < 0 )
      {
LABEL_13:
        v28 = v18;
        goto LABEL_33;
      }
    }
    if ( v10 )
    {
      CClfsBaseFile::UnlockImage(this);
      v10 = 0;
    }
    if ( ClfsIsContainerPathRelative(a2) )
    {
      v16 = CClfsBaseFilePersisted::CreateAbsoluteContainerPath(this, a2, &v30);
      v28 = v16;
      if ( v16 < 0 )
        goto LABEL_33;
      v12 = 1;
      v27 = 1;
    }
    else
    {
      v30 = *a2;
    }
    v19 = P;
    v16 = CClfsAuthContainer::Create(
            *a8,
            &v30,
            a3,
            (CClfsBaseFilePersisted *)((char *)this + 176),
            P,
            a5,
            *((_QWORD *)this + 31),
            &v25);
    v28 = v16;
    if ( v16 == -1073741727 && (v20 = v19[1], (v20 & 0x2000) != 0) )
    {
      v19[1] = v20 & 0xDFFF;
      v24 = v19;
      v21 = a3;
      v16 = CClfsAuthContainer::Create(
              *a8,
              &v30,
              a3,
              (CClfsBaseFilePersisted *)((char *)this + 176),
              v24,
              a5,
              *((_QWORD *)this + 31),
              &v25);
      v28 = v16;
    }
    else
    {
      v21 = a3;
    }
    if ( v16 == -1073741609 && !a6 )
    {
      v16 = CClfsAuthContainer::Create(
              *a8,
              &v30,
              v21,
              (CClfsBaseFilePersisted *)((char *)this + 176),
              0,
              a5,
              *((_QWORD *)this + 31),
              &v25);
      v28 = v16;
    }
    if ( v16 < 0 )
    {
      v11 = v26;
    }
    else
    {
      v11 = 1;
      v26 = 1;
      v22 = *((_DWORD *)this + 36);
      if ( CClfsAuthContainer::GetRawSectorSize(*a8) != v22 )
      {
        v16 = -1072037887;
        goto LABEL_6;
      }
      if ( (a4 & 8) != 0 )
      {
        v18 = CClfsAuthContainer::MarkSystemLogContainer(*a8);
        v16 = v18;
        goto LABEL_13;
      }
    }
  }
LABEL_33:
  if ( v10 )
    CClfsBaseFile::UnlockImage(this);
  if ( v12 )
    CClfsBaseFilePersisted::DestroyAbsoluteContainerPath(v15, &v30);
  if ( v16 < 0 && *a8 )
  {
    if ( v11 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a8 + 24LL))(*a8);
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a8 + 8LL))(*a8);
    *a8 = 0;
  }
  if ( P )
    ExFreePoolWithTag(P, 0);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x140062ef8  mov     rax, rsp
0x140062efb  mov     [rax+20h], r9d
0x140062eff  mov     [rax+18h], r8
0x140062f03  mov     [rax+8], rcx
0x140062f07  push    rbx
0x140062f08  push    rsi
0x140062f09  push    rdi
0x140062f0a  push    r12
0x140062f0c  push    r13
0x140062f0e  push    r14
0x140062f10  push    r15
0x140062f12  sub     rsp, 70h
0x140062f16  mov     rbx, rdx
0x140062f19  mov     rsi, rcx
0x140062f1c  xor     edi, edi
0x140062f1e  mov     [rax-60h], rdi
0x140062f22  mov     [rax-58h], rdi
0x140062f26  mov     [rax-50h], rdi
0x140062f2a  mov     [rax-64h], edi
0x140062f2d  mov     r15b, dil
0x140062f30  mov     [rax-68h], dil
0x140062f34  mov     [rax-67h], dil
0x140062f38  mov     r13b, dil
0x140062f3b  mov     [rax-66h], dil
0x140062f3f  mov     r12b, dil
0x140062f42  mov     [rax-65h], dil
0x140062f46  mov     qword ptr [rax-48h], 2
0x140062f4e  mov     eax, [rsp+0A8h+arg_30]
0x140062f55  mov     [rsp+0A8h+var_40], rax
0x140062f5a  mov     r14, [rsp+0A8h+arg_38]
0x140062f62  mov     [r14], rdi
0x140062f65  lea     rcx, WPP_MAIN_CB.DeviceQueue.20h; Lookaside
0x140062f6c  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140062f73  nop     dword ptr [rax+rax+00h]
0x140062f78  test    rax, rax
0x140062f7b  jz      short loc_140062F98
0x140062f7d  mov     r9, [rsi+0F0h]
0x140062f84  mov     r8d, [rsi+0E8h]
0x140062f8b  mov     rcx, rax
0x140062f8e  call    ??0CClfsAuthContainer@@QEAA@KW4_CLFS_AUTHENTICATION_MODE@@PEAU_DEVICE_OBJECT@@@Z; CClfsAuthContainer::CClfsAuthContainer(ulong,_CLFS_AUTHENTICATION_MODE,_DEVICE_OBJECT *)
0x140062f93  mov     rcx, rax
0x140062f96  jmp     short loc_140062F9B
0x140062f98  mov     rcx, rdi
0x140062f9b  mov     [r14], rcx
0x140062f9e  test    rcx, rcx
0x140062fa1  jnz     short loc_140062FB1
0x140062fa3  mov     edi, 0C000009Ah
0x140062fa8  mov     [rsp+0A8h+var_64], edi
0x140062fac  jmp     loc_1400631FD
0x140062fb1  mov     rax, [rcx]
0x140062fb4  mov     rax, [rax]
0x140062fb7  call    _guard_dispatch_icall
0x140062fbc  mov     r8d, 2; unsigned int
0x140062fc2  lea     rdx, [rsp+0A8h+var_48]; unsigned __int64 *
0x140062fc7  mov     rcx, [r14]; this
0x140062fca  call    ?Initialize@CClfsAuthContainer@@QEAAJPEA_KK@Z; CClfsAuthContainer::Initialize(unsigned __int64 *,ulong)
0x140062fcf  mov     edi, eax
0x140062fd1  mov     [rsp+0A8h+var_64], eax
0x140062fd5  test    eax, eax
0x140062fd7  js      loc_1400631FD
0x140062fdd  mov     dl, 1; Wait
0x140062fdf  mov     rcx, [rsi+20h]; Resource
0x140062fe3  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140062fea  nop     dword ptr [rax+rax+00h]
0x140062fef  mov     r15b, al
0x140062ff2  mov     [rsp+0A8h+var_68], al
0x140062ff6  cmp     [rsp+0A8h+arg_28], 0
0x140062ffe  jz      short loc_140063036
0x140063000  mov     [rsp+0A8h+arg_30], 0
0x14006300b  mov     rcx, [rsi+98h]
0x140063012  mov     rcx, [rcx+78h]; this
0x140063016  test    rcx, rcx
0x140063019  jz      short loc_14006302C
0x14006301b  mov     r9b, 1; unsigned __int8
0x14006301e  lea     rdx, [rsp+0A8h+P]; void **
0x140063023  call    ?DuplicateSecurityDescriptor@CClfsContainer@@QEAAJAEAPEAXAEAKE@Z; CClfsContainer::DuplicateSecurityDescriptor(void * &,ulong &,uchar)
0x140063028  test    eax, eax
0x14006302a  jns     short loc_140063051
0x14006302c  mov     edi, 0C0000079h
0x140063031  jmp     loc_140062FA8
0x140063036  xor     edx, edx; unsigned int *
0x140063038  lea     rcx, [rsp+0A8h+P]; void **
0x14006303d  call    ?DuplicateNullSecurityDescriptor@CClfsContainer@@SAJAEAPEAXPEAK@Z; CClfsContainer::DuplicateNullSecurityDescriptor(void * &,ulong *)
0x140063042  mov     edi, eax
0x140063044  test    eax, eax
0x140063046  jns     short loc_140063051
0x140063048  mov     [rsp+0A8h+var_64], eax
0x14006304c  jmp     loc_1400631FD
0x140063051  test    r15b, r15b
0x140063054  jz      short loc_140063066
0x140063056  mov     rcx, rsi; this
0x140063059  call    ?UnlockImage@CClfsBaseFile@@QEAAXXZ; CClfsBaseFile::UnlockImage(void)
0x14006305e  xor     r15b, r15b
0x140063061  mov     [rsp+0A8h+var_68], r15b
0x140063066  mov     rcx, rbx; String2
0x140063069  call    ?ClfsIsContainerPathRelative@@YAEAEBU_UNICODE_STRING@@@Z; ClfsIsContainerPathRelative(_UNICODE_STRING const &)
0x14006306e  test    al, al
0x140063070  jz      short loc_14006309A
0x140063072  lea     r8, [rsp+0A8h+var_58]; struct _UNICODE_STRING *
0x140063077  mov     rdx, rbx; struct _UNICODE_STRING *
0x14006307a  mov     rcx, rsi; this
0x14006307d  call    ?CreateAbsoluteContainerPath@CClfsBaseFilePersisted@@AEAAJAEBU_UNICODE_STRING@@AEAU2@@Z; CClfsBaseFilePersisted::CreateAbsoluteContainerPath(_UNICODE_STRING const &,_UNICODE_STRING &)
0x140063082  mov     edi, eax
0x140063084  mov     [rsp+0A8h+var_64], eax
0x140063088  test    eax, eax
0x14006308a  js      loc_1400631FD
0x140063090  mov     r12b, 1
0x140063093  mov     [rsp+0A8h+var_65], r12b
0x140063098  jmp     short loc_1400630A3
0x14006309a  movups  xmm0, xmmword ptr [rbx]
0x14006309d  movdqu  xmmword ptr [rsp+0A8h+var_58.Length], xmm0
0x1400630a3  lea     r13, [rsi+0B0h]
0x1400630aa  lea     rax, [rsp+0A8h+var_67]
0x1400630af  mov     [rsp+0A8h+var_70], rax; unsigned __int8 *
0x1400630b4  mov     rax, [rsi+0F8h]
0x1400630bb  mov     [rsp+0A8h+var_78], rax; unsigned __int64
0x1400630c0  mov     al, [rsp+0A8h+arg_20]
0x1400630c7  mov     [rsp+0A8h+var_80], al; unsigned __int8
0x1400630cb  mov     rbx, [rsp+0A8h+P]
0x1400630d0  mov     [rsp+0A8h+var_88], rbx; void *
0x1400630d5  mov     r9, r13; struct _CLFS_FILTER_CONTEXT *
0x1400630d8  mov     r8, [rsp+0A8h+arg_10]; unsigned __int64 *
0x1400630e0  lea     rdx, [rsp+0A8h+var_58]; struct _UNICODE_STRING *
0x1400630e5  mov     rcx, [r14]; this
0x1400630e8  call    ?Create@CClfsAuthContainer@@QEAAJAEBU_UNICODE_STRING@@AEB_KAEBU_CLFS_FILTER_CONTEXT@@QEAXE_KAEAE@Z; CClfsAuthContainer::Create(_UNICODE_STRING const &,unsigned __int64 const &,_CLFS_FILTER_CONTEXT const &,void * const,uchar,unsigned __int64,uchar &)
0x1400630ed  mov     edi, eax
0x1400630ef  mov     [rsp+0A8h+var_64], eax
0x1400630f3  cmp     eax, 0C0000061h
0x1400630f8  jnz     short loc_14006315A
0x1400630fa  movzx   eax, word ptr [rbx+2]
0x1400630fe  bt      ax, 0Dh
0x140063103  jnb     short loc_14006315A
0x140063105  mov     ecx, 0DFFFh
0x14006310a  and     ax, cx
0x14006310d  mov     [rbx+2], ax
0x140063111  lea     rax, [rsp+0A8h+var_67]
0x140063116  mov     [rsp+0A8h+var_70], rax; unsigned __int8 *
0x14006311b  mov     rax, [rsi+0F8h]
0x140063122  mov     [rsp+0A8h+var_78], rax; unsigned __int64
0x140063127  mov     al, [rsp+0A8h+arg_20]
0x14006312e  mov     [rsp+0A8h+var_80], al; unsigned __int8
0x140063132  mov     [rsp+0A8h+var_88], rbx; void *
0x140063137  mov     r9, r13; struct _CLFS_FILTER_CONTEXT *
0x14006313a  mov     rbx, [rsp+0A8h+arg_10]
0x140063142  mov     r8, rbx; unsigned __int64 *
0x140063145  lea     rdx, [rsp+0A8h+var_58]; struct _UNICODE_STRING *
0x14006314a  mov     rcx, [r14]; this
0x14006314d  call    ?Create@CClfsAuthContainer@@QEAAJAEBU_UNICODE_STRING@@AEB_KAEBU_CLFS_FILTER_CONTEXT@@QEAXE_KAEAE@Z; CClfsAuthContainer::Create(_UNICODE_STRING const &,unsigned __int64 const &,_CLFS_FILTER_CONTEXT const &,void * const,uchar,unsigned __int64,uchar &)
0x140063152  mov     edi, eax
0x140063154  mov     [rsp+0A8h+var_64], eax
0x140063158  jmp     short loc_140063162
0x14006315a  mov     rbx, [rsp+0A8h+arg_10]
0x140063162  cmp     edi, 0C00000D7h
0x140063168  jnz     short loc_1400631B7
0x14006316a  cmp     [rsp+0A8h+arg_28], 0
0x140063172  jnz     short loc_1400631B7
0x140063174  lea     rax, [rsp+0A8h+var_67]
0x140063179  mov     [rsp+0A8h+var_70], rax; unsigned __int8 *
0x14006317e  mov     rax, [rsi+0F8h]
0x140063185  mov     [rsp+0A8h+var_78], rax; unsigned __int64
0x14006318a  mov     al, [rsp+0A8h+arg_20]
0x140063191  mov     [rsp+0A8h+var_80], al; unsigned __int8
0x140063195  mov     [rsp+0A8h+var_88], 0; void *
0x14006319e  mov     r9, r13; struct _CLFS_FILTER_CONTEXT *
0x1400631a1  mov     r8, rbx; unsigned __int64 *
0x1400631a4  lea     rdx, [rsp+0A8h+var_58]; struct _UNICODE_STRING *
0x1400631a9  mov     rcx, [r14]; this
0x1400631ac  call    ?Create@CClfsAuthContainer@@QEAAJAEBU_UNICODE_STRING@@AEB_KAEBU_CLFS_FILTER_CONTEXT@@QEAXE_KAEAE@Z; CClfsAuthContainer::Create(_UNICODE_STRING const &,unsigned __int64 const &,_CLFS_FILTER_CONTEXT const &,void * const,uchar,unsigned __int64,uchar &)
0x1400631b1  mov     edi, eax
0x1400631b3  mov     [rsp+0A8h+var_64], eax
0x1400631b7  test    edi, edi
0x1400631b9  js      short loc_1400631F8
0x1400631bb  mov     r13b, 1
0x1400631be  mov     [rsp+0A8h+var_66], r13b
0x1400631c3  mov     ebx, [rsi+90h]
0x1400631c9  mov     rcx, [r14]; this
0x1400631cc  call    ?GetRawSectorSize@CClfsAuthContainer@@QEAAKXZ; CClfsAuthContainer::GetRawSectorSize(void)
0x1400631d1  cmp     eax, ebx
0x1400631d3  jz      short loc_1400631DF
0x1400631d5  mov     edi, 0C01A0001h
0x1400631da  jmp     loc_140062FA8
0x1400631df  test    [rsp+0A8h+arg_18], 8
0x1400631e7  jz      short loc_1400631FD
0x1400631e9  mov     rcx, [r14]; this
0x1400631ec  call    ?MarkSystemLogContainer@CClfsAuthContainer@@QEAAJXZ; CClfsAuthContainer::MarkSystemLogContainer(void)
0x1400631f1  mov     edi, eax
0x1400631f3  jmp     loc_140063048
0x1400631f8  mov     r13b, [rsp+0A8h+var_66]
0x1400631fd  test    r15b, r15b
0x140063200  jz      short loc_14006320A
0x140063202  mov     rcx, rsi; this
0x140063205  call    ?UnlockImage@CClfsBaseFile@@QEAAXXZ; CClfsBaseFile::UnlockImage(void)
0x14006320a  test    r12b, r12b
0x14006320d  jz      short loc_140063219
0x14006320f  lea     rdx, [rsp+0A8h+var_58]; struct _UNICODE_STRING *
0x140063214  call    ?DestroyAbsoluteContainerPath@CClfsBaseFilePersisted@@AEAAXAEAU_UNICODE_STRING@@@Z; CClfsBaseFilePersisted::DestroyAbsoluteContainerPath(_UNICODE_STRING &)
0x140063219  test    edi, edi
0x14006321b  jns     short loc_14006324C
0x14006321d  mov     rcx, [r14]
0x140063220  test    rcx, rcx
0x140063223  jz      short loc_14006324C
0x140063225  test    r13b, r13b
0x140063228  jz      short loc_140063236
0x14006322a  mov     rax, [rcx]
0x14006322d  mov     rax, [rax+18h]
0x140063231  call    _guard_dispatch_icall
0x140063236  mov     rcx, [r14]
0x140063239  mov     rax, [rcx]
0x14006323c  mov     rax, [rax+8]
0x140063240  call    _guard_dispatch_icall
0x140063245  mov     qword ptr [r14], 0
0x14006324c  mov     rbx, [rsp+0A8h+P]
0x140063251  test    rbx, rbx
0x140063254  jz      short loc_140063267
0x140063256  xor     edx, edx; Tag
0x140063258  mov     rcx, rbx; P
0x14006325b  call    cs:__imp_ExFreePoolWithTag
0x140063262  nop     dword ptr [rax+rax+00h]
0x140063267  mov     eax, edi
0x140063269  add     rsp, 70h
0x14006326d  pop     r15
0x14006326f  pop     r14
0x140063271  pop     r13
0x140063273  pop     r12
0x140063275  pop     rdi
0x140063276  pop     rsi
0x140063277  pop     rbx
0x140063278  retn
0x14007a84f  push    rbx
0x14007a851  push    rbp
0x14007a852  sub     rsp, 48h
0x14007a856  mov     rbp, rdx
0x14007a859  cmp     byte ptr [rbp+40h], 0
0x14007a85d  jz      short loc_14007A86F
0x14007a85f  mov     rcx, [rbp+0B0h]; this
0x14007a866  call    ?UnlockImage@CClfsBaseFile@@QEAAXXZ; CClfsBaseFile::UnlockImage(void)
0x14007a86b  mov     byte ptr [rbp+40h], 0
0x14007a86f  cmp     byte ptr [rbp+43h], 0
0x14007a873  jz      short loc_14007A87F
0x14007a875  lea     rdx, [rbp+50h]; struct _UNICODE_STRING *
0x14007a879  call    ?DestroyAbsoluteContainerPath@CClfsBaseFilePersisted@@AEAAXAEAU_UNICODE_STRING@@@Z; CClfsBaseFilePersisted::DestroyAbsoluteContainerPath(_UNICODE_STRING &)
0x14007a87e  nop
0x14007a87f  cmp     dword ptr [rbp+44h], 0
0x14007a883  jge     short loc_14007A8C4
0x14007a885  mov     rbx, [rbp+0E8h]
0x14007a88c  cmp     qword ptr [rbx], 0
0x14007a890  jz      short loc_14007A8C4
0x14007a892  cmp     byte ptr [rbp+42h], 0
0x14007a896  jz      short loc_14007A8AB
0x14007a898  mov     rax, [rbx]
0x14007a89b  mov     rcx, [rax]
0x14007a89e  mov     rax, [rcx+18h]
0x14007a8a2  mov     rcx, [rbx]
0x14007a8a5  call    _guard_dispatch_icall
0x14007a8aa  nop
0x14007a8ab  mov     rax, [rbx]
0x14007a8ae  mov     rcx, [rax]
0x14007a8b1  mov     rax, [rcx+8]
0x14007a8b5  mov     rcx, [rbx]
0x14007a8b8  call    _guard_dispatch_icall
0x14007a8bd  mov     qword ptr [rbx], 0
0x14007a8c4  mov     rcx, [rbp+48h]; P
0x14007a8c8  test    rcx, rcx
0x14007a8cb  jz      short loc_14007A8DC
0x14007a8cd  xor     edx, edx; Tag
0x14007a8cf  call    cs:__imp_ExFreePoolWithTag
0x14007a8d6  nop     dword ptr [rax+rax+00h]
0x14007a8db  nop
0x14007a8dc  add     rsp, 48h
0x14007a8e0  pop     rbp
0x14007a8e1  pop     rbx
0x14007a8e2  retn
```
