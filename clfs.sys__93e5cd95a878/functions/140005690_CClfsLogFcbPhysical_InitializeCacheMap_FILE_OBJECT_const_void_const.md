# CClfsLogFcbPhysical::InitializeCacheMap(_FILE_OBJECT * const,void * const)

- ea: `0x140005690`
- end: `0x14000577a`
- name: `?InitializeCacheMap@CClfsLogFcbPhysical@@UEAAJQEAU_FILE_OBJECT@@QEAX@Z`
- size: `234`
- prototype: `int(CClfsLogFcbPhysical *__hidden this, struct _FILE_OBJECT *const, void *const)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140005690`
- `0x140005840`

## import_xrefs

- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140018b6e`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140018b6e`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400056d2`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400056d2`
- `ntoskrnl!CcSetReadAheadGranularity` at `0x140005744`
- `ntoskrnl!CcSetReadAheadGranularity` at `0x140005744`
- `ntoskrnl!CcSetAdditionalCacheAttributes` at `0x140005730`
- `ntoskrnl!CcSetAdditionalCacheAttributes` at `0x140005730`
- `ntoskrnl!CcInitializeCacheMap` at `0x1400056fe`
- `ntoskrnl!CcInitializeCacheMap` at `0x1400056fe`

## pseudocode

```c
__int64 __fastcall CClfsLogFcbPhysical::InitializeCacheMap(
        CClfsLogFcbPhysical *this,
        struct _FILE_OBJECT *const a2,
        void *const a3)
{
  char *v6; // rsi
  BOOLEAN v7; // r15

  if ( a2->PrivateCacheMap )
    return 0;
  v6 = (char *)this + 200;
  v7 = ExAcquireResourceSharedLite((PERESOURCE)((char *)this + 200), 1u);
  CcInitializeCacheMap(a2, (PCC_FILE_SIZES)((char *)this + 80), 1u, &CClfsLogFcbPhysical::m_gpfnCacheCallbacks, a3);
  CcSetAdditionalCacheAttributes(a2, 0, 0);
  CcSetReadAheadGranularity(a2, 0x80000u);
  if ( v7 )
    ClfsReleaseResourceLite(v6);
  return 0;
}

```

## disassembly

```asm
0x140005690  mov     [rsp+arg_10], rbx
0x140005695  mov     [rsp+arg_8], rdx
0x14000569a  mov     [rsp+arg_0], rcx
0x14000569f  push    rsi
0x1400056a0  push    rdi
0x1400056a1  push    r12
0x1400056a3  push    r14
0x1400056a5  push    r15
0x1400056a7  sub     rsp, 40h
0x1400056ab  mov     r12, r8
0x1400056ae  mov     rbx, rdx
0x1400056b1  mov     r14, rcx
0x1400056b4  cmp     qword ptr [rdx+30h], 0
0x1400056b9  jnz     loc_140005776
0x1400056bf  xor     edi, edi
0x1400056c1  lea     rsi, [rcx+0C8h]
0x1400056c8  mov     [rsp+68h+var_30], rsi
0x1400056cd  mov     dl, 1; Wait
0x1400056cf  mov     rcx, rsi; Resource
0x1400056d2  call    cs:__imp_ExAcquireResourceSharedLite
0x1400056d9  nop     dword ptr [rax+rax+00h]
0x1400056de  mov     r15b, al
0x1400056e1  mov     [rsp+68h+arg_18], al
0x1400056e8  lea     rdx, [r14+50h]; FileSizes
0x1400056ec  mov     [rsp+68h+LazyWriteContext], r12; LazyWriteContext
0x1400056f1  lea     r9, ?m_gpfnCacheCallbacks@CClfsLogFcbPhysical@@0U_CACHE_MANAGER_CALLBACKS@@A; Callbacks
0x1400056f8  mov     r8b, 1; PinAccess
0x1400056fb  mov     rcx, rbx; FileObject
0x1400056fe  call    cs:__imp_CcInitializeCacheMap
0x140005705  nop     dword ptr [rax+rax+00h]
0x14000570a  jmp     short loc_140005724
0x14000570c  mov     edi, eax
0x14000570e  mov     [rsp+68h+var_38], eax
0x140005712  mov     rbx, [rsp+68h+arg_8]
0x140005717  mov     r15b, [rsp+68h+arg_18]
0x14000571f  mov     rsi, [rsp+68h+var_30]
0x140005724  test    edi, edi
0x140005726  js      short loc_140005751
0x140005728  xor     r8d, r8d; DisableWriteBehind
0x14000572b  xor     edx, edx; DisableReadAhead
0x14000572d  mov     rcx, rbx; FileObject
0x140005730  call    cs:__imp_CcSetAdditionalCacheAttributes
0x140005737  nop     dword ptr [rax+rax+00h]
0x14000573c  mov     edx, 80000h; Granularity
0x140005741  mov     rcx, rbx; FileObject
0x140005744  call    cs:__imp_CcSetReadAheadGranularity
0x14000574b  nop     dword ptr [rax+rax+00h]
0x140005750  nop
0x140005751  test    r15b, r15b
0x140005754  jz      short loc_14000575E
0x140005756  mov     rcx, rsi
0x140005759  call    ClfsReleaseResourceLite
0x14000575e  mov     eax, edi
0x140005760  mov     rbx, [rsp+68h+arg_10]
0x140005768  add     rsp, 40h
0x14000576c  pop     r15
0x14000576e  pop     r14
0x140005770  pop     r12
0x140005772  pop     rdi
0x140005773  pop     rsi
0x140005774  retn
0x140005776  xor     eax, eax
0x140005778  jmp     short loc_140005760
0x140018b60  push    rbp
0x140018b62  sub     rsp, 30h
0x140018b66  mov     rbp, rdx
0x140018b69  mov     rcx, [rcx]
0x140018b6c  mov     ecx, [rcx]; Exception
0x140018b6e  call    cs:__imp_FsRtlIsNtstatusExpected
0x140018b75  nop     dword ptr [rax+rax+00h]
0x140018b7a  xor     ecx, ecx
0x140018b7c  test    al, al
0x140018b7e  setnz   cl
0x140018b81  mov     eax, ecx
0x140018b83  add     rsp, 30h
0x140018b87  pop     rbp
0x140018b88  retn
0x140018b8a  push    rbp
0x140018b8c  sub     rsp, 30h
0x140018b90  mov     rbp, rdx
0x140018b93  cmp     byte ptr [rbp+88h], 0
0x140018b9a  jz      short loc_140018BAD
0x140018b9c  mov     rcx, [rbp+70h]
0x140018ba0  add     rcx, 0C8h
0x140018ba7  call    ClfsReleaseResourceLite
0x140018bac  nop
0x140018bad  add     rsp, 30h
0x140018bb1  pop     rbp
0x140018bb2  retn
```
