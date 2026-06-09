# DfscGetDomainCacheNames

- ea: `0x140016de8`
- end: `0x140016f6d`
- name: `DfscGetDomainCacheNames`
- size: `389`
- prototype: `__int64 __fastcall(PUNICODE_PREFIX_TABLE PrefixTable, __int64, unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400282f4`

## callees

- `0x140006080`
- `0x140006380`
- `0x140016de8`

## import_xrefs

- `ntoskrnl!RtlNextUnicodePrefix` at `0x140016e43`
- `ntoskrnl!RtlNextUnicodePrefix` at `0x140016eb1`
- `ntoskrnl!RtlNextUnicodePrefix` at `0x140016e43`
- `ntoskrnl!RtlNextUnicodePrefix` at `0x140016eb1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140016e84`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140016f43`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140016e84`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140016f43`
- `ntoskrnl!ExReleaseResourceLite` at `0x140016e78`
- `ntoskrnl!ExReleaseResourceLite` at `0x140016f37`
- `ntoskrnl!ExReleaseResourceLite` at `0x140016e78`
- `ntoskrnl!ExReleaseResourceLite` at `0x140016f37`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140016e1a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140016e1a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140016e05`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140016e05`

## pseudocode

```c
__int64 __fastcall DfscGetDomainCacheNames(
        PUNICODE_PREFIX_TABLE PrefixTable,
        __int64 a2,
        unsigned int *a3,
        unsigned int a4)
{
  size_t v4; // rbx
  BOOLEAN v8; // dl
  unsigned int v9; // esi
  PUNICODE_PREFIX_TABLE_ENTRY UnicodePrefix; // rax
  int v11; // edi
  BOOLEAN v12; // dl
  unsigned int *v13; // rbx
  PUNICODE_PREFIX_TABLE_ENTRY v14; // rax
  PUNICODE_PREFIX_TABLE_ENTRY v15; // rbp
  char *v16; // rbx
  unsigned __int64 v17; // rcx
  size_t v19; // [rsp+70h] [rbp+8h]

  v4 = a4;
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite((PERESOURCE)&PrefixTable[2].NextPrefixTree, 1u);
  v8 = 1;
  v9 = 2;
  while ( 1 )
  {
    UnicodePrefix = RtlNextUnicodePrefix(PrefixTable, v8);
    if ( !UnicodePrefix )
      break;
    if ( (BYTE4(UnicodePrefix[-2].Prefix) & 1) != 0 )
      v9 += LOWORD(UnicodePrefix[1].CaseMatch) + 4;
    v8 = 0;
  }
  if ( v9 <= (unsigned int)v4 )
  {
    v11 = 0;
    v19 = v4;
    memset(a3, 0, v4);
    v12 = 1;
    v13 = a3;
    while ( 1 )
    {
      v14 = RtlNextUnicodePrefix(PrefixTable, v12);
      v15 = v14;
      if ( !v14 )
        break;
      if ( (BYTE4(v14[-2].Prefix) & 1) != 0 )
      {
        *(_WORD *)v13 = LOWORD(v14[-1].NextPrefixTree) != 0 ? 43 : 45;
        if ( (char *)a3 + v19 < (char *)v13 + ((__int64)v14[1].CaseMatch & 0xFFFE) + 6 )
        {
          v11 = -2147483643;
          break;
        }
        v16 = (char *)v13 + 2;
        memmove(v16, v14[1].Links.Parent, LOWORD(v14[1].CaseMatch));
        v17 = (unsigned __int64)LOWORD(v15[1].CaseMatch) >> 1;
        *(_WORD *)&v16[2 * v17] = 0;
        v13 = (unsigned int *)&v16[2 * v17 + 2];
      }
      v12 = 0;
    }
    *(_WORD *)v13 = 0;
    ExReleaseResourceLite((PERESOURCE)&PrefixTable[2].NextPrefixTree);
    KeLeaveCriticalRegion();
    if ( v11 >= 0 )
      *(_QWORD *)(a2 + 56) = v9;
  }
  else
  {
    if ( (unsigned int)v4 >= 4 )
    {
      *a3 = v9;
      v11 = -2147483643;
      *(_QWORD *)(a2 + 56) = 4;
    }
    else
    {
      v11 = -1073741789;
    }
    ExReleaseResourceLite((PERESOURCE)&PrefixTable[2].NextPrefixTree);
    KeLeaveCriticalRegion();
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140016de8  push    rbx
0x140016dea  push    rbp
0x140016deb  push    rsi
0x140016dec  push    rdi
0x140016ded  push    r12
0x140016def  push    r13
0x140016df1  push    r14
0x140016df3  push    r15
0x140016df5  sub     rsp, 28h
0x140016df9  mov     ebx, r9d
0x140016dfc  mov     r12, r8
0x140016dff  mov     r13, rdx
0x140016e02  mov     r14, rcx
0x140016e05  call    cs:__imp_KeEnterCriticalRegion
0x140016e0c  nop     dword ptr [rax+rax+00h]
0x140016e11  lea     r15, [r14+38h]
0x140016e15  mov     dl, 1; Wait
0x140016e17  mov     rcx, r15; Resource
0x140016e1a  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140016e21  nop     dword ptr [rax+rax+00h]
0x140016e26  mov     dl, 1
0x140016e28  mov     esi, 2
0x140016e2d  jmp     short loc_140016E40
0x140016e2f  test    byte ptr [rax-3Ch], 1
0x140016e33  jz      short loc_140016E3E
0x140016e35  movzx   eax, word ptr [rax+48h]
0x140016e39  add     esi, 4
0x140016e3c  add     esi, eax
0x140016e3e  xor     edx, edx; Restart
0x140016e40  mov     rcx, r14; PrefixTable
0x140016e43  call    cs:__imp_RtlNextUnicodePrefix
0x140016e4a  nop     dword ptr [rax+rax+00h]
0x140016e4f  test    rax, rax
0x140016e52  jnz     short loc_140016E2F
0x140016e54  cmp     esi, ebx
0x140016e56  jbe     short loc_140016E95
0x140016e58  cmp     ebx, 4
0x140016e5b  jnb     short loc_140016E64
0x140016e5d  mov     edi, 0C0000023h
0x140016e62  jmp     short loc_140016E75
0x140016e64  mov     [r12], esi
0x140016e68  mov     edi, 80000005h
0x140016e6d  mov     qword ptr [r13+38h], 4
0x140016e75  mov     rcx, r15; Resource
0x140016e78  call    cs:__imp_ExReleaseResourceLite
0x140016e7f  nop     dword ptr [rax+rax+00h]
0x140016e84  call    cs:__imp_KeLeaveCriticalRegion
0x140016e8b  nop     dword ptr [rax+rax+00h]
0x140016e90  jmp     loc_140016F59
0x140016e95  xor     edi, edi
0x140016e97  mov     [rsp+68h+arg_0], rbx
0x140016e9c  mov     r8, rbx; Size
0x140016e9f  xor     edx, edx; Val
0x140016ea1  mov     rcx, r12; void *
0x140016ea4  call    memset
0x140016ea9  mov     dl, 1; Restart
0x140016eab  mov     rbx, r12
0x140016eae  mov     rcx, r14; PrefixTable
0x140016eb1  call    cs:__imp_RtlNextUnicodePrefix
0x140016eb8  nop     dword ptr [rax+rax+00h]
0x140016ebd  mov     rbp, rax
0x140016ec0  test    rax, rax
0x140016ec3  jz      short loc_140016F2F
0x140016ec5  test    byte ptr [rax-3Ch], 1
0x140016ec9  jz      short loc_140016F26
0x140016ecb  movzx   ecx, word ptr [rax-30h]
0x140016ecf  neg     cx
0x140016ed2  sbb     dx, dx
0x140016ed5  and     dx, 0FFFEh
0x140016eda  add     dx, 2Dh ; '-'
0x140016ede  mov     [rbx], dx
0x140016ee1  movzx   r8d, word ptr [rax+48h]; Size
0x140016ee6  mov     rax, [rsp+68h+arg_0]
0x140016eeb  mov     ecx, r8d
0x140016eee  and     rcx, 0FFFFFFFFFFFFFFFEh
0x140016ef2  add     rax, r12
0x140016ef5  add     rcx, 6
0x140016ef9  add     rcx, rbx
0x140016efc  cmp     rax, rcx
0x140016eff  jb      short loc_140016F2A
0x140016f01  mov     rdx, [rbp+50h]; Src
0x140016f05  add     rbx, 2
0x140016f09  mov     rcx, rbx; void *
0x140016f0c  call    memmove
0x140016f11  movzx   ecx, word ptr [rbp+48h]
0x140016f15  xor     eax, eax
0x140016f17  shr     rcx, 1
0x140016f1a  mov     [rbx+rcx*2], ax
0x140016f1e  lea     rbx, [rbx+rcx*2]
0x140016f22  add     rbx, 2
0x140016f26  xor     edx, edx
0x140016f28  jmp     short loc_140016EAE
0x140016f2a  mov     edi, 80000005h
0x140016f2f  xor     edx, edx
0x140016f31  mov     rcx, r15; Resource
0x140016f34  mov     [rbx], dx
0x140016f37  call    cs:__imp_ExReleaseResourceLite
0x140016f3e  nop     dword ptr [rax+rax+00h]
0x140016f43  call    cs:__imp_KeLeaveCriticalRegion
0x140016f4a  nop     dword ptr [rax+rax+00h]
0x140016f4f  test    edi, edi
0x140016f51  js      short loc_140016F59
0x140016f53  mov     ecx, esi
0x140016f55  mov     [r13+38h], rcx
0x140016f59  mov     eax, edi
0x140016f5b  add     rsp, 28h
0x140016f5f  pop     r15
0x140016f61  pop     r14
0x140016f63  pop     r13
0x140016f65  pop     r12
0x140016f67  pop     rdi
0x140016f68  pop     rsi
0x140016f69  pop     rbp
0x140016f6a  pop     rbx
0x140016f6b  retn
```
