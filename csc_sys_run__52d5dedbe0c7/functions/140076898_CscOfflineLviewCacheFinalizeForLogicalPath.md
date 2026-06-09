# CscOfflineLviewCacheFinalizeForLogicalPath

- ea: `0x140076898`
- end: `0x140076a30`
- name: `CscOfflineLviewCacheFinalizeForLogicalPath`
- size: `408`
- prototype: `__int64 __fastcall(PERESOURCE Resource)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400759d0`

## callees

- `0x14000a634`
- `0x14000f8b0`
- `0x140010ae8`
- `0x14001a624`
- `0x14001aae0`
- `0x140053018`
- `0x140076898`
- `0x140076e68`
- `0x14008d304`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400768c4`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400768c4`
- `ntoskrnl!ExReleaseResourceLite` at `0x140076968`
- `ntoskrnl!ExReleaseResourceLite` at `0x140076968`

## pseudocode

```c
void __fastcall CscOfflineLviewCacheFinalizeForLogicalPath(PERESOURCE Resource, _WORD *a2)
{
  __int64 v3; // rdi
  char v5; // si
  __int64 DeepPrefixEntry; // rax
  __int64 v7; // rbx
  __int64 v8; // rbp
  __int64 v9; // rbx
  int v10; // eax
  __int64 v11; // r9
  int v12; // ebx
  char v13; // [rsp+70h] [rbp+8h] BYREF
  __int64 v14; // [rsp+80h] [rbp+18h] BYREF

  v3 = 0;
  v14 = 0;
  v13 = 0;
  v5 = 0;
  ExAcquireResourceSharedLite(Resource, 1u);
  DeepPrefixEntry = CscOfflineLviewCachepFindDeepPrefixEntry(Resource, a2);
  v7 = DeepPrefixEntry;
  if ( DeepPrefixEntry && (v8 = DeepPrefixEntry + 176, *(_WORD *)(DeepPrefixEntry + 176) == *a2) )
  {
    v3 = *(_QWORD *)(DeepPrefixEntry + 32);
    v14 = v3;
    CscStoreReferenceEntry(v3);
    _m_prefetchw((const void *)(v7 + 8));
    if ( (_InterlockedXor((volatile signed __int32 *)(v7 + 8), 0) & 2) != 0 )
      v5 = 1;
    else
      CscOfflineLviewCachepClearIgnoreFlag(v7);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_e56e5c7c71ce3fc5dce6d5b40435d5ff_Traceguids, v8);
    v9 = v3;
  }
  else
  {
    v9 = 0;
  }
  ExReleaseResourceLite(Resource);
  if ( v9 )
  {
    v10 = CscStoreQueryInformationEntryEx(v3, 0, 0, 0, &v13, 0, 0);
    v12 = v10;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    {
      LOBYTE(v11) = v13 != 0 ? 89 : 78;
      WPP_SF_cD(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_e56e5c7c71ce3fc5dce6d5b40435d5ff_Traceguids, v11, v10);
    }
    if ( v12 >= 0 && (v13 || v5) )
      CscOfflineLviewCacheRemoveEntry(Resource);
  }
  if ( v3 )
    CscStoreDereferenceEntry(&v14);
}

```

## disassembly

```asm
0x140076898  mov     rax, rsp
0x14007689b  mov     [rax+10h], rbx
0x14007689f  mov     [rax+20h], rbp
0x1400768a3  push    rsi
0x1400768a4  push    rdi
0x1400768a5  push    r13
0x1400768a7  push    r14
0x1400768a9  push    r15
0x1400768ab  sub     rsp, 40h
0x1400768af  mov     r15, rdx
0x1400768b2  xor     edi, edi
0x1400768b4  mov     dl, 1; Wait
0x1400768b6  mov     [rax+18h], rdi
0x1400768ba  mov     [rax+8], dil
0x1400768be  mov     r14, rcx
0x1400768c1  xor     sil, sil
0x1400768c4  call    cs:__imp_ExAcquireResourceSharedLite
0x1400768cb  nop     dword ptr [rax+rax+00h]
0x1400768d0  mov     rdx, r15
0x1400768d3  mov     rcx, r14
0x1400768d6  call    CscOfflineLviewCachepFindDeepPrefixEntry
0x1400768db  lea     r13, WPP_GLOBAL_Control
0x1400768e2  mov     rbx, rax
0x1400768e5  test    rax, rax
0x1400768e8  jz      short loc_140076963
0x1400768ea  movzx   ecx, word ptr [r15]
0x1400768ee  lea     rbp, [rax+0B0h]
0x1400768f5  cmp     [rbp+0], cx
0x1400768f9  jnz     short loc_140076963
0x1400768fb  mov     rdi, [rax+20h]
0x1400768ff  mov     rcx, rdi
0x140076902  mov     [rsp+68h+arg_10], rdi
0x14007690a  call    CscStoreReferenceEntry
0x14007690f  prefetchw byte ptr [rbx+8]
0x140076913  mov     eax, [rbx+8]
0x140076916  mov     ecx, eax
0x140076918  xor     ecx, 0
0x14007691b  lock cmpxchg [rbx+8], ecx
0x140076920  jnz     short loc_140076916
0x140076922  test    al, 2
0x140076924  jz      short loc_14007692B
0x140076926  mov     sil, 1
0x140076929  jmp     short loc_140076933
0x14007692b  mov     rcx, rbx
0x14007692e  call    CscOfflineLviewCachepClearIgnoreFlag
0x140076933  mov     rcx, cs:WPP_GLOBAL_Control
0x14007693a  cmp     rcx, r13
0x14007693d  jz      short loc_14007695E
0x14007693f  mov     eax, [rcx+2Ch]
0x140076942  test    al, 40h
0x140076944  jz      short loc_14007695E
0x140076946  mov     rcx, [rcx+18h]
0x14007694a  lea     r8, WPP_e56e5c7c71ce3fc5dce6d5b40435d5ff_Traceguids
0x140076951  mov     edx, 1Ah
0x140076956  mov     r9, rbp
0x140076959  call    WPP_SF_Z
0x14007695e  mov     rbx, rdi
0x140076961  jmp     short loc_140076965
0x140076963  xor     ebx, ebx
0x140076965  mov     rcx, r14; Resource
0x140076968  call    cs:__imp_ExReleaseResourceLite
0x14007696f  nop     dword ptr [rax+rax+00h]
0x140076974  test    rbx, rbx
0x140076977  jz      loc_140076A04
0x14007697d  mov     [rsp+68h+var_38], 0
0x140076986  lea     rax, [rsp+68h+arg_0]
0x14007698b  mov     [rsp+68h+var_40], 0
0x140076994  xor     r9d, r9d
0x140076997  xor     r8d, r8d
0x14007699a  mov     [rsp+68h+var_48], rax
0x14007699f  xor     edx, edx
0x1400769a1  mov     rcx, rdi
0x1400769a4  call    CscStoreQueryInformationEntryEx
0x1400769a9  mov     ebx, eax
0x1400769ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400769b2  cmp     rcx, r13
0x1400769b5  jz      short loc_1400769E9
0x1400769b7  mov     edx, [rcx+2Ch]
0x1400769ba  test    dl, 40h
0x1400769bd  jz      short loc_1400769E9
0x1400769bf  mov     dl, [rsp+68h+arg_0]
0x1400769c3  lea     r8, WPP_e56e5c7c71ce3fc5dce6d5b40435d5ff_Traceguids
0x1400769ca  mov     rcx, [rcx+18h]
0x1400769ce  neg     dl
0x1400769d0  mov     edx, 1Bh
0x1400769d5  mov     dword ptr [rsp+68h+var_48], eax
0x1400769d9  sbb     r9b, r9b
0x1400769dc  and     r9b, 0Bh
0x1400769e0  add     r9b, 4Eh ; 'N'
0x1400769e4  call    WPP_SF_cD
0x1400769e9  test    ebx, ebx
0x1400769eb  js      short loc_140076A04
0x1400769ed  cmp     [rsp+68h+arg_0], 0
0x1400769f2  jnz     short loc_1400769F9
0x1400769f4  test    sil, sil
0x1400769f7  jz      short loc_140076A04
0x1400769f9  mov     rdx, r15
0x1400769fc  mov     rcx, r14; Resource
0x1400769ff  call    CscOfflineLviewCacheRemoveEntry
0x140076a04  test    rdi, rdi
0x140076a07  jz      short loc_140076A16
0x140076a09  lea     rcx, [rsp+68h+arg_10]
0x140076a11  call    CscStoreDereferenceEntry
0x140076a16  lea     r11, [rsp+68h+var_28]
0x140076a1b  mov     rbx, [r11+38h]
0x140076a1f  mov     rbp, [r11+48h]
0x140076a23  mov     rsp, r11
0x140076a26  pop     r15
0x140076a28  pop     r14
0x140076a2a  pop     r13
0x140076a2c  pop     rdi
0x140076a2d  pop     rsi
0x140076a2e  retn
```
