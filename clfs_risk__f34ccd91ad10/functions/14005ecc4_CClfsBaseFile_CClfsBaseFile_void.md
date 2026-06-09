# CClfsBaseFile::~CClfsBaseFile(void)

- ea: `0x14005ecc4`
- end: `0x14005ed6a`
- name: `??1CClfsBaseFile@@UEAA@XZ`
- size: `166`
- prototype: `void __fastcall(CClfsBaseFile *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140011910`
- `0x1400369a8`
- `0x14005eb90`

## callees

- `0x14005ecc4`
- `0x14005ff58`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x14005ece0`
- `ntoskrnl!ExDeleteResourceLite` at `0x14005ece0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ecf2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ed1a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ed39`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ecf2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ed1a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ed39`

## pseudocode

```c
void __fastcall CClfsBaseFile::~CClfsBaseFile(CClfsBaseFile *this)
{
  struct _ERESOURCE *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx

  *(_QWORD *)this = &CClfsBaseFile::`vftable';
  v2 = (struct _ERESOURCE *)*((_QWORD *)this + 4);
  if ( v2 )
  {
    ExDeleteResourceLite(v2);
    ExFreePoolWithTag(*((PVOID *)this + 4), 0);
    *((_QWORD *)this + 4) = 0;
  }
  if ( *((_BYTE *)this + 148) )
  {
    CClfsBaseFile::ReleaseMetadataBlock(this, 2);
    *((_BYTE *)this + 148) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 6);
  if ( v3 )
  {
    ExFreePoolWithTag(v3, 0);
    *((_QWORD *)this + 6) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 7);
  if ( v4 )
  {
    ExFreePoolWithTag(v4, 0);
    *((_QWORD *)this + 7) = 0;
  }
}

```

## disassembly

```asm
0x14005ecc4  push    rbx
0x14005ecc6  sub     rsp, 20h
0x14005ecca  lea     rax, ??_7CClfsBaseFile@@6B@; const CClfsBaseFile::`vftable'
0x14005ecd1  mov     rbx, rcx
0x14005ecd4  mov     [rcx], rax
0x14005ecd7  mov     rcx, [rcx+20h]; Resource
0x14005ecdb  test    rcx, rcx
0x14005ecde  jz      short loc_14005ED06
0x14005ece0  call    cs:__imp_ExDeleteResourceLite
0x14005ece7  nop     dword ptr [rax+rax+00h]
0x14005ecec  mov     rcx, [rbx+20h]; P
0x14005ecf0  xor     edx, edx; Tag
0x14005ecf2  call    cs:__imp_ExFreePoolWithTag
0x14005ecf9  nop     dword ptr [rax+rax+00h]
0x14005ecfe  mov     qword ptr [rbx+20h], 0
0x14005ed06  cmp     byte ptr [rbx+94h], 0
0x14005ed0d  jnz     short loc_14005ED54
0x14005ed0f  mov     rcx, [rbx+30h]; P
0x14005ed13  test    rcx, rcx
0x14005ed16  jz      short loc_14005ED2E
0x14005ed18  xor     edx, edx; Tag
0x14005ed1a  call    cs:__imp_ExFreePoolWithTag
0x14005ed21  nop     dword ptr [rax+rax+00h]
0x14005ed26  mov     qword ptr [rbx+30h], 0
0x14005ed2e  mov     rcx, [rbx+38h]; P
0x14005ed32  test    rcx, rcx
0x14005ed35  jz      short loc_14005ED4D
0x14005ed37  xor     edx, edx; Tag
0x14005ed39  call    cs:__imp_ExFreePoolWithTag
0x14005ed40  nop     dword ptr [rax+rax+00h]
0x14005ed45  mov     qword ptr [rbx+38h], 0
0x14005ed4d  add     rsp, 20h
0x14005ed51  pop     rbx
0x14005ed52  retn
0x14005ed54  mov     edx, 2
0x14005ed59  mov     rcx, rbx
0x14005ed5c  call    ?ReleaseMetadataBlock@CClfsBaseFile@@IEAAXW4_CLFS_METADATA_BLOCK_TYPE@@@Z; CClfsBaseFile::ReleaseMetadataBlock(_CLFS_METADATA_BLOCK_TYPE)
0x14005ed61  mov     byte ptr [rbx+94h], 0
0x14005ed68  jmp     short loc_14005ED0F
```
