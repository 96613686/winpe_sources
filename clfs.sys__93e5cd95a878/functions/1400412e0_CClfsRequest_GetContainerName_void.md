# CClfsRequest::GetContainerName(void)

- ea: `0x1400412e0`
- end: `0x140041461`
- name: `?GetContainerName@CClfsRequest@@AEAAJXZ`
- size: `385`
- prototype: `__int64 __fastcall(CClfsRequest *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14006c874`

## callees

- `0x140005840`
- `0x140017f20`
- `0x140018280`
- `0x1400412e0`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14004136e`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14004136e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400413be`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400413be`

## pseudocode

```c
__int64 __fastcall CClfsRequest::GetContainerName(CClfsRequest *this)
{
  BOOLEAN v2; // si
  __int64 v3; // rax
  __int64 v4; // rcx
  unsigned int v5; // edi
  unsigned int v6; // edi
  __int64 v7; // rcx
  unsigned __int16 v8; // dx
  __int64 v9; // r10
  PVOID v10; // rax
  __int64 v12; // [rsp+38h] [rbp-20h] BYREF
  void *v13; // [rsp+40h] [rbp-18h]
  unsigned int v14; // [rsp+68h] [rbp+10h] BYREF

  v12 = 0;
  v13 = 0;
  v2 = 0;
  v14 = 0;
  v3 = *((_QWORD *)this + 6);
  v4 = *(_QWORD *)(v3 + 184);
  if ( *(_DWORD *)(v4 + 16) >= 4u )
  {
    v6 = **(_DWORD **)(v3 + 24);
    WORD1(v12) = *(_WORD *)(v4 + 8);
    v7 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 48) + 24LL) + 120LL);
    *((_QWORD *)this + 18) = v7;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 64LL))(v7);
    v2 = ExAcquireResourceSharedLite((PERESOURCE)(*((_QWORD *)this + 18) + 200LL), 1u);
    v8 = WORD1(v12);
    if ( !WORD1(v12)
      || ((v9 = *(_QWORD *)(*((_QWORD *)this + 6) + 8LL), (*(_BYTE *)(v9 + 10) & 5) == 0)
        ? (PVOID)(v10 = MmMapLockedPagesSpecifyCache((PMDL)v9, 0, MmCached, 0, 0, 0x40000010u), v8 = WORD1(v12))
        : (v10 = *(PVOID *)(v9 + 24)),
          (v13 = v10) != 0) )
    {
      memset(v13, 0, v8);
      v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *, unsigned int *))(**((_QWORD **)this + 18) + 360LL))(
             *((_QWORD *)this + 18),
             v6,
             &v12,
             &v14);
    }
    else
    {
      v5 = -1073741670;
    }
  }
  else
  {
    v5 = -1073741306;
  }
  if ( (*((_DWORD *)this + 4) & 4) == 0 )
  {
    *(_DWORD *)(*((_QWORD *)this + 6) + 48LL) = v5;
    *(_QWORD *)(*((_QWORD *)this + 6) + 56LL) = v14;
  }
  if ( v2 )
    ClfsReleaseResourceLite((struct _ERESOURCE *)(*((_QWORD *)this + 18) + 200LL));
  return v5;
}

```

## disassembly

```asm
0x1400412e0  mov     r11, rsp
0x1400412e3  mov     [r11+18h], rbx
0x1400412e7  mov     [r11+20h], rsi
0x1400412eb  mov     [r11+8], rcx
0x1400412ef  push    rdi
0x1400412f0  sub     rsp, 50h
0x1400412f4  mov     rbx, rcx
0x1400412f7  xor     eax, eax
0x1400412f9  mov     [r11-20h], rax
0x1400412fd  mov     [r11-18h], rax
0x140041301  mov     [rsp+58h+var_24], eax
0x140041305  xor     sil, sil
0x140041308  mov     [rsp+58h+var_28], sil
0x14004130d  mov     [rsp+58h+arg_8], eax
0x140041311  mov     rax, [rcx+30h]
0x140041315  mov     rcx, [rax+0B8h]
0x14004131c  cmp     dword ptr [rcx+10h], 4
0x140041320  jnb     short loc_140041330
0x140041322  mov     edi, 0C0000206h
0x140041327  mov     [rsp+58h+var_24], edi
0x14004132b  jmp     loc_14004141B
0x140041330  mov     rax, [rax+18h]
0x140041334  mov     edi, [rax]
0x140041336  movzx   eax, word ptr [rcx+8]
0x14004133a  mov     [rsp+58h+var_1E], ax
0x14004133f  mov     rax, [rcx+30h]
0x140041343  mov     rcx, [rax+18h]
0x140041347  mov     rcx, [rcx+78h]
0x14004134b  mov     [rbx+90h], rcx
0x140041352  mov     rax, [rcx]
0x140041355  mov     rax, [rax+40h]
0x140041359  call    _guard_dispatch_icall
0x14004135e  mov     rcx, [rbx+90h]
0x140041365  add     rcx, 0C8h; Resource
0x14004136c  mov     dl, 1; Wait
0x14004136e  call    cs:__imp_ExAcquireResourceSharedLite
0x140041375  nop     dword ptr [rax+rax+00h]
0x14004137a  mov     sil, al
0x14004137d  mov     [rsp+58h+var_28], al
0x140041381  xor     ecx, ecx
0x140041383  movzx   edx, [rsp+58h+var_1E]
0x140041388  cmp     cx, dx
0x14004138b  jnb     short loc_1400413E3
0x14004138d  mov     rcx, [rbx+30h]
0x140041391  mov     r10, [rcx+8]
0x140041395  test    byte ptr [r10+0Ah], 5
0x14004139a  jz      short loc_1400413A2
0x14004139c  mov     rax, [r10+18h]
0x1400413a0  jmp     short loc_1400413CF
0x1400413a2  mov     [rsp+58h+Priority], 40000010h; Priority
0x1400413aa  mov     [rsp+58h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400413b2  xor     r9d, r9d; RequestedAddress
0x1400413b5  xor     edx, edx; AccessMode
0x1400413b7  lea     r8d, [r9+1]; CacheType
0x1400413bb  mov     rcx, r10; MemoryDescriptorList
0x1400413be  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400413c5  nop     dword ptr [rax+rax+00h]
0x1400413ca  movzx   edx, [rsp+58h+var_1E]
0x1400413cf  mov     [rsp+58h+var_18], rax
0x1400413d4  test    rax, rax
0x1400413d7  jnz     short loc_1400413E3
0x1400413d9  mov     edi, 0C000009Ah
0x1400413de  jmp     loc_140041327
0x1400413e3  movzx   r8d, dx; Size
0x1400413e7  xor     edx, edx; Val
0x1400413e9  mov     rcx, [rsp+58h+var_18]; void *
0x1400413ee  call    memset
0x1400413f3  mov     rcx, [rbx+90h]
0x1400413fa  mov     rax, [rcx]
0x1400413fd  mov     rax, [rax+168h]
0x140041404  lea     r9, [rsp+58h+arg_8]
0x140041409  lea     r8, [rsp+58h+var_20]
0x14004140e  mov     edx, edi
0x140041410  call    _guard_dispatch_icall
0x140041415  mov     edi, eax
0x140041417  mov     [rsp+58h+var_24], eax
0x14004141b  mov     ecx, [rbx+10h]
0x14004141e  test    cl, 4
0x140041421  jnz     short loc_140041436
0x140041423  mov     rax, [rbx+30h]
0x140041427  mov     [rax+30h], edi
0x14004142a  mov     ecx, [rsp+58h+arg_8]
0x14004142e  mov     rax, [rbx+30h]
0x140041432  mov     [rax+38h], rcx
0x140041436  test    sil, sil
0x140041439  jz      short loc_14004144E
0x14004143b  mov     rcx, [rbx+90h]
0x140041442  add     rcx, 0C8h
0x140041449  call    ClfsReleaseResourceLite
0x14004144e  mov     eax, edi
0x140041450  mov     rbx, [rsp+58h+arg_10]
0x140041455  mov     rsi, [rsp+58h+arg_18]
0x14004145a  add     rsp, 50h
0x14004145e  pop     rdi
0x14004145f  retn
0x14007eb80  push    rbp
0x14007eb82  sub     rsp, 30h
0x14007eb86  mov     rbp, rdx
0x14007eb89  xor     cl, cl
0x14007eb8b  mov     rdx, [rbp+60h]
0x14007eb8f  test    byte ptr [rdx+10h], 4
0x14007eb93  movzx   eax, cl
0x14007eb96  mov     ecx, 1
0x14007eb9b  cmovnz  eax, ecx
0x14007eb9e  test    al, al
0x14007eba0  jnz     short loc_14007EBB7
0x14007eba2  mov     rcx, [rdx+30h]
0x14007eba6  mov     eax, [rbp+34h]
0x14007eba9  mov     [rcx+30h], eax
0x14007ebac  mov     ecx, [rbp+68h]
0x14007ebaf  mov     rax, [rdx+30h]
0x14007ebb3  mov     [rax+38h], rcx
0x14007ebb7  cmp     byte ptr [rbp+30h], 0
0x14007ebbb  jz      short loc_14007EBD4
0x14007ebbd  mov     rcx, [rdx+90h]
0x14007ebc4  add     rcx, 0C8h
0x14007ebcb  call    ClfsReleaseResourceLite
0x14007ebd0  mov     byte ptr [rbp+30h], 0
0x14007ebd4  add     rsp, 30h
0x14007ebd8  pop     rbp
0x14007ebd9  retn
```
