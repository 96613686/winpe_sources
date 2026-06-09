# CClfsAuthContainer::Remove(_UNICODE_STRING &)

- ea: `0x14003ed2c`
- end: `0x14003ee62`
- name: `?Remove@CClfsAuthContainer@@QEAAJAEAU_UNICODE_STRING@@@Z`
- size: `310`
- prototype: `int(CClfsAuthContainer *__hidden this, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, installer_update`

## callers

- `0x14005ed70`

## callees

- `0x14000ed04`
- `0x14003b718`
- `0x14003ed2c`
- `0x14003ee68`
- `0x140076b4c`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14003ed74`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14003edea`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14003ed74`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14003edea`

## pseudocode

```c
__int64 __fastcall CClfsAuthContainer::Remove(CClfsAuthContainer *this, struct _UNICODE_STRING *a2)
{
  bool v2; // cc
  int v5; // edi
  _QWORD *v6; // rax
  unsigned int v7; // edx
  void *v8; // rbx
  int v9; // ecx
  _QWORD *v10; // rax
  void *v11; // rdi
  unsigned int v12; // ebx
  unsigned int v13; // edx
  struct _UNICODE_STRING v15; // [rsp+20h] [rbp-48h] BYREF

  v2 = *((_DWORD *)this + 34) <= 1u;
  v15 = 0;
  if ( v2 )
  {
    v5 = CClfsAuthContainer::CreatePatchFilePath(a2, &v15);
    v6 = ExAllocateFromPagedLookasideList(&CClfsContainer::m_laList);
    v8 = v6;
    if ( v6 )
    {
      v9 = *((_DWORD *)this + 11);
      *v6 = &CClfsContainer::`vftable';
      v6[1] = 0;
      v6[2] = 0;
      v6[4] = 0;
      v6[5] = 0;
      v6[6] = 0;
      v6[7] = 0;
      *((_DWORD *)v6 + 16) = 0;
      v6[9] = 0;
      *((_DWORD *)v6 + 20) = 0;
      *((_BYTE *)v6 + 128) = 0;
      *((_DWORD *)v6 + 17) = v9;
      v6[14] = v6;
      if ( v5 >= 0 )
        CClfsContainer::Remove((CClfsContainer *)v6, &v15);
      CClfsContainer::`scalar deleting destructor'(v8, v7);
    }
    CClfsAuthContainer::ReleasePatchFilePath(&v15);
  }
  v10 = ExAllocateFromPagedLookasideList(&CClfsContainer::m_laList);
  v11 = v10;
  if ( !v10 )
    return 3221225626LL;
  *((_DWORD *)v10 + 17) = *((_DWORD *)this + 11);
  *v10 = &CClfsContainer::`vftable';
  v10[1] = 0;
  v10[2] = 0;
  v10[4] = 0;
  v10[5] = 0;
  v10[6] = 0;
  v10[7] = 0;
  *((_DWORD *)v10 + 16) = 0;
  v10[9] = 0;
  *((_DWORD *)v10 + 20) = 0;
  *((_BYTE *)v10 + 128) = 0;
  v10[14] = v10;
  v12 = CClfsContainer::Remove((CClfsContainer *)v10, a2);
  CClfsContainer::`scalar deleting destructor'(v11, v13);
  return v12;
}

```

## disassembly

```asm
0x14003ed2c  push    rbx
0x14003ed2e  push    rbp
0x14003ed2f  push    rsi
0x14003ed30  push    rdi
0x14003ed31  push    r14
0x14003ed33  push    r15
0x14003ed35  sub     rsp, 38h
0x14003ed39  xor     r14d, r14d
0x14003ed3c  lea     r15, ??_7CClfsContainer@@6B@; const CClfsContainer::`vftable'
0x14003ed43  cmp     dword ptr [rcx+88h], 1
0x14003ed4a  xorps   xmm0, xmm0
0x14003ed4d  mov     rbp, rdx
0x14003ed50  mov     rsi, rcx
0x14003ed53  movups  xmmword ptr [rsp+68h+var_48.Length], xmm0
0x14003ed58  ja      loc_14003EDE3
0x14003ed5e  lea     rdx, [rsp+68h+var_48]; struct _UNICODE_STRING *
0x14003ed63  mov     rcx, rbp; struct _UNICODE_STRING *
0x14003ed66  call    ?CreatePatchFilePath@CClfsAuthContainer@@CAJAEBU_UNICODE_STRING@@AEAU2@@Z; CClfsAuthContainer::CreatePatchFilePath(_UNICODE_STRING const &,_UNICODE_STRING &)
0x14003ed6b  lea     rcx, ?m_laList@CClfsContainer@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x14003ed72  mov     edi, eax
0x14003ed74  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14003ed7b  nop     dword ptr [rax+rax+00h]
0x14003ed80  mov     rbx, rax
0x14003ed83  test    rax, rax
0x14003ed86  jz      short loc_14003EDD9
0x14003ed88  mov     ecx, [rsi+2Ch]
0x14003ed8b  mov     [rax], r15
0x14003ed8e  mov     [rax+8], r14
0x14003ed92  mov     [rax+10h], r14
0x14003ed96  mov     [rax+20h], r14
0x14003ed9a  mov     [rax+28h], r14
0x14003ed9e  mov     [rax+30h], r14
0x14003eda2  mov     [rax+38h], r14
0x14003eda6  mov     [rax+40h], r14d
0x14003edaa  mov     [rax+48h], r14
0x14003edae  mov     [rax+50h], r14d
0x14003edb2  mov     [rax+80h], r14b
0x14003edb9  mov     [rax+44h], ecx
0x14003edbc  mov     [rax+70h], rax
0x14003edc0  test    edi, edi
0x14003edc2  js      short loc_14003EDD1
0x14003edc4  lea     rdx, [rsp+68h+var_48]; struct _UNICODE_STRING *
0x14003edc9  mov     rcx, rax; this
0x14003edcc  call    ?Remove@CClfsContainer@@QEAAJAEAU_UNICODE_STRING@@@Z; CClfsContainer::Remove(_UNICODE_STRING &)
0x14003edd1  mov     rcx, rbx; Entry
0x14003edd4  call    ??_GCClfsContainer@@QEAAPEAXI@Z; CClfsContainer::`scalar deleting destructor'(uint)
0x14003edd9  lea     rcx, [rsp+68h+var_48]; struct _UNICODE_STRING *
0x14003edde  call    ?ReleasePatchFilePath@CClfsAuthContainer@@CAXAEAU_UNICODE_STRING@@@Z; CClfsAuthContainer::ReleasePatchFilePath(_UNICODE_STRING &)
0x14003ede3  lea     rcx, ?m_laList@CClfsContainer@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x14003edea  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14003edf1  nop     dword ptr [rax+rax+00h]
0x14003edf6  mov     rdi, rax
0x14003edf9  test    rax, rax
0x14003edfc  jz      short loc_14003EE4F
0x14003edfe  mov     ecx, [rsi+2Ch]
0x14003ee01  mov     rdx, rbp; struct _UNICODE_STRING *
0x14003ee04  mov     [rax+44h], ecx
0x14003ee07  mov     rcx, rax; this
0x14003ee0a  mov     [rax], r15
0x14003ee0d  mov     [rax+8], r14
0x14003ee11  mov     [rax+10h], r14
0x14003ee15  mov     [rax+20h], r14
0x14003ee19  mov     [rax+28h], r14
0x14003ee1d  mov     [rax+30h], r14
0x14003ee21  mov     [rax+38h], r14
0x14003ee25  mov     [rax+40h], r14d
0x14003ee29  mov     [rax+48h], r14
0x14003ee2d  mov     [rax+50h], r14d
0x14003ee31  mov     [rax+80h], r14b
0x14003ee38  mov     [rax+70h], rax
0x14003ee3c  call    ?Remove@CClfsContainer@@QEAAJAEAU_UNICODE_STRING@@@Z; CClfsContainer::Remove(_UNICODE_STRING &)
0x14003ee41  mov     rcx, rdi; Entry
0x14003ee44  mov     ebx, eax
0x14003ee46  call    ??_GCClfsContainer@@QEAAPEAXI@Z; CClfsContainer::`scalar deleting destructor'(uint)
0x14003ee4b  mov     eax, ebx
0x14003ee4d  jmp     short loc_14003EE54
0x14003ee4f  mov     eax, 0C000009Ah
0x14003ee54  add     rsp, 38h
0x14003ee58  pop     r15
0x14003ee5a  pop     r14
0x14003ee5c  pop     rdi
0x14003ee5d  pop     rsi
0x14003ee5e  pop     rbp
0x14003ee5f  pop     rbx
0x14003ee60  retn
```
