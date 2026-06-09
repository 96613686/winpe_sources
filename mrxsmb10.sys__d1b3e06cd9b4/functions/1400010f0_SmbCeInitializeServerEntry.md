# SmbCeInitializeServerEntry

- ea: `0x1400010f0`
- end: `0x1400012ac`
- name: `SmbCeInitializeServerEntry`
- size: `444`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140013700`
- `0x14003f910`

## callees

- `0x1400010f0`
- `0x1400012b4`
- `0x14001221c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400011ba`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400011ba`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400011ae`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400011ae`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140001176`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140001176`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140001161`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140001161`
- `rdbss!RxReferenceCredential` at `0x140001219`
- `rdbss!RxReferenceCredential` at `0x140001219`
- `rdbss!RxFinalizeSecurityContext` at `0x1400011eb`
- `rdbss!RxFinalizeSecurityContext` at `0x1400011eb`
- `mrxsmb!SmbCepDereferenceTransport` at `0x14000127a`
- `mrxsmb!SmbCepDereferenceTransport` at `0x14000127a`
- `mrxsmb!SmbCeFindTransport` at `0x140001143`
- `mrxsmb!SmbCeFindTransport` at `0x140001143`

## pseudocode

```c
__int64 __fastcall SmbCeInitializeServerEntry(__int64 a1, __int64 a2, _QWORD *a3, int a4, char *a5)
{
  __int64 v5; // r15
  __int64 Transport; // rsi
  char v11; // r14
  _WORD *v12; // r8
  unsigned int v13; // ebx
  __int64 v14; // rdx
  __int64 v15; // rdi
  __int64 v16; // rcx
  char v18; // [rsp+70h] [rbp+8h] BYREF
  __int64 v19; // [rsp+78h] [rbp+10h] BYREF

  v5 = *(_QWORD *)(a2 + 112);
  v19 = 0;
  v18 = 0;
  Transport = 0;
  v11 = 0;
  if ( v5 )
  {
    v12 = *(_WORD **)(v5 + 48);
    if ( v12 )
    {
      if ( *v12 )
      {
        Transport = SmbCeFindTransport(*(_QWORD *)(*(_QWORD *)(a2 + 32) + 80LL), 0);
        if ( !Transport )
        {
          v13 = -1073741252;
          goto LABEL_18;
        }
      }
    }
  }
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(&s_SmbCeDbResource, 1u);
  v13 = SmbCeFindOrConstructServerEntry(
          *(const UNICODE_STRING **)(a1 + 64),
          v14,
          &v19,
          &v18,
          (UNICODE_STRING *)(a1 + 208),
          a4);
  ExReleaseResourceLite(&s_SmbCeDbResource);
  KeLeaveCriticalRegion();
  v15 = v19;
  v11 = v18;
  *a3 = v19;
  if ( v13 )
    goto LABEL_16;
  if ( v5 )
  {
    RxFinalizeSecurityContext(v15 + 560);
    v16 = *(_QWORD *)(a2 + 112);
    *(_OWORD *)(v15 + 560) = *(_OWORD *)(a2 + 80);
    *(_OWORD *)(v15 + 576) = *(_OWORD *)(a2 + 96);
    *(_QWORD *)(v15 + 592) = *(_QWORD *)(a2 + 112);
    if ( v16 )
      RxReferenceCredential();
  }
  _InterlockedExchange64((volatile __int64 *)(v15 + 48), a1);
  v13 = SmbCeUpdateSrvCall(v15);
  if ( v13 )
    goto LABEL_16;
  if ( Transport )
  {
    *(_QWORD *)(v15 + 336) = Transport;
    Transport = 0;
  }
  else
  {
    *(_QWORD *)(v15 + 336) = 0;
  }
  if ( v11 )
  {
    *(_DWORD *)(v15 + 12) = 1;
    *(_DWORD *)(v15 + 416) = 4;
    *(_DWORD *)(v15 + 468) = 0xFFFF;
LABEL_16:
    if ( Transport )
      SmbCepDereferenceTransport(Transport);
  }
LABEL_18:
  *a5 = v11;
  return v13;
}

```

## disassembly

```asm
0x1400010f0  mov     [rsp+arg_10], rbx
0x1400010f5  push    rbp
0x1400010f6  push    rsi
0x1400010f7  push    rdi
0x1400010f8  push    r12
0x1400010fa  push    r13
0x1400010fc  push    r14
0x1400010fe  push    r15
0x140001100  sub     rsp, 30h
0x140001104  mov     r15, [rdx+70h]
0x140001108  xor     edi, edi
0x14000110a  mov     [rsp+68h+arg_8], rdi
0x14000110f  mov     ebx, r9d
0x140001112  mov     [rsp+68h+arg_0], dil
0x140001117  mov     r12, r8
0x14000111a  mov     rbp, rdx
0x14000111d  mov     r13, rcx
0x140001120  mov     esi, edi
0x140001122  mov     r14b, dil
0x140001125  test    r15, r15
0x140001128  jz      short loc_140001161
0x14000112a  mov     r8, [r15+30h]
0x14000112e  test    r8, r8
0x140001131  jz      short loc_140001161
0x140001133  cmp     [r8], di
0x140001137  jbe     short loc_140001161
0x140001139  mov     rcx, [rdx+20h]
0x14000113d  xor     edx, edx
0x14000113f  mov     rcx, [rcx+50h]
0x140001143  call    cs:__imp_SmbCeFindTransport
0x14000114a  nop     dword ptr [rax+rax+00h]
0x14000114f  mov     rsi, rax
0x140001152  test    rax, rax
0x140001155  jnz     short loc_140001161
0x140001157  mov     ebx, 0C000023Ch
0x14000115c  jmp     loc_140001286
0x140001161  call    cs:__imp_KeEnterCriticalRegion
0x140001168  nop     dword ptr [rax+rax+00h]
0x14000116d  mov     dl, 1; Wait
0x14000116f  lea     rcx, s_SmbCeDbResource; Resource
0x140001176  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000117d  nop     dword ptr [rax+rax+00h]
0x140001182  mov     rcx, [r13+40h]
0x140001186  lea     rax, [r13+0D0h]
0x14000118d  mov     [rsp+68h+var_40], ebx
0x140001191  lea     r9, [rsp+68h+arg_0]
0x140001196  lea     r8, [rsp+68h+arg_8]
0x14000119b  mov     [rsp+68h+var_48], rax
0x1400011a0  call    SmbCeFindOrConstructServerEntry
0x1400011a5  lea     rcx, s_SmbCeDbResource; Resource
0x1400011ac  mov     ebx, eax
0x1400011ae  call    cs:__imp_ExReleaseResourceLite
0x1400011b5  nop     dword ptr [rax+rax+00h]
0x1400011ba  call    cs:__imp_KeLeaveCriticalRegion
0x1400011c1  nop     dword ptr [rax+rax+00h]
0x1400011c6  mov     rdi, [rsp+68h+arg_8]
0x1400011cb  mov     r14b, [rsp+68h+arg_0]
0x1400011d0  mov     [r12], rdi
0x1400011d4  test    ebx, ebx
0x1400011d6  jnz     loc_140001272
0x1400011dc  test    r15, r15
0x1400011df  jz      short loc_140001225
0x1400011e1  lea     rbx, [rdi+230h]
0x1400011e8  mov     rcx, rbx
0x1400011eb  call    cs:__imp_RxFinalizeSecurityContext
0x1400011f2  nop     dword ptr [rax+rax+00h]
0x1400011f7  movups  xmm0, xmmword ptr [rbp+50h]
0x1400011fb  mov     rcx, [rbp+70h]
0x1400011ff  movups  xmmword ptr [rbx], xmm0
0x140001202  movups  xmm1, xmmword ptr [rbp+60h]
0x140001206  movups  xmmword ptr [rbx+10h], xmm1
0x14000120a  movsd   xmm0, qword ptr [rbp+70h]
0x14000120f  movsd   qword ptr [rbx+20h], xmm0
0x140001214  test    rcx, rcx
0x140001217  jz      short loc_140001225
0x140001219  call    cs:__imp_RxReferenceCredential
0x140001220  nop     dword ptr [rax+rax+00h]
0x140001225  xchg    r13, [rdi+30h]
0x140001229  mov     rcx, rdi
0x14000122c  call    SmbCeUpdateSrvCall
0x140001231  mov     ebx, eax
0x140001233  test    eax, eax
0x140001235  jnz     short loc_140001272
0x140001237  test    rsi, rsi
0x14000123a  jz      short loc_140001247
0x14000123c  mov     [rdi+150h], rsi
0x140001243  xor     esi, esi
0x140001245  jmp     short loc_140001252
0x140001247  mov     qword ptr [rdi+150h], 0
0x140001252  test    r14b, r14b
0x140001255  jz      short loc_140001286
0x140001257  mov     dword ptr [rdi+0Ch], 1
0x14000125e  mov     dword ptr [rdi+1A0h], 4
0x140001268  mov     dword ptr [rdi+1D4h], 0FFFFh
0x140001272  test    rsi, rsi
0x140001275  jz      short loc_140001286
0x140001277  mov     rcx, rsi
0x14000127a  call    cs:__imp_SmbCepDereferenceTransport
0x140001281  nop     dword ptr [rax+rax+00h]
0x140001286  mov     rax, [rsp+68h+arg_20]
0x14000128e  mov     [rax], r14b
0x140001291  mov     eax, ebx
0x140001293  mov     rbx, [rsp+68h+arg_10]
0x14000129b  add     rsp, 30h
0x14000129f  pop     r15
0x1400012a1  pop     r14
0x1400012a3  pop     r13
0x1400012a5  pop     r12
0x1400012a7  pop     rdi
0x1400012a8  pop     rsi
0x1400012a9  pop     rbp
0x1400012aa  retn
```
