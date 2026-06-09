# BwcCleanupQoSPolicy

- ea: `0x140013ae0`
- end: `0x140013b61`
- name: `BwcCleanupQoSPolicy`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callees

- `0x140012258`
- `0x140013ae0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140013b47`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140013b47`

## pseudocode

```c
void __fastcall BwcCleanupQoSPolicy(__int64 a1)
{
  _QWORD *v1; // rbx
  int v2; // ecx
  __int64 *v3; // rdx
  __int64 *i; // rax
  __int64 v5; // rcx
  _QWORD *v6; // rdx
  void *v7; // rcx

  v1 = (_QWORD *)(a1 - 24);
  v2 = *(_DWORD *)(a1 - 24 + 12);
  v3 = &QoSPoliciesHashListHead[2 * (v2 & 0x1F)];
  for ( i = (__int64 *)*v3; i != v3; i = (__int64 *)*i )
  {
    if ( *((_DWORD *)i - 13) == v2 )
    {
      v5 = v1[8];
      if ( *(_QWORD **)(v5 + 8) != v1 + 8 || (v6 = (_QWORD *)v1[9], (_QWORD *)*v6 != v1 + 8) )
        __fastfail(3u);
      *v6 = v5;
      *(_QWORD *)(v5 + 8) = v6;
      break;
    }
  }
  v7 = (void *)v1[2];
  if ( v7 )
    BwcDeleteFlow(v7);
  ExFreeToNPagedLookasideList(&QoSPolicyList, v1);
}

```

## disassembly

```asm
0x140013ae0  push    rbx
0x140013ae2  sub     rsp, 20h
0x140013ae6  lea     rbx, [rcx-18h]
0x140013aea  mov     ecx, [rbx+0Ch]
0x140013aed  lea     rdx, QoSPoliciesHashListHead
0x140013af4  mov     eax, ecx
0x140013af6  and     eax, 1Fh
0x140013af9  shl     rax, 4
0x140013afd  add     rdx, rax
0x140013b00  mov     rax, [rdx]
0x140013b03  cmp     rax, rdx
0x140013b06  jz      short loc_140013B2F
0x140013b08  cmp     [rax-34h], ecx
0x140013b0b  jz      short loc_140013B12
0x140013b0d  mov     rax, [rax]
0x140013b10  jmp     short loc_140013B03
0x140013b12  lea     rax, [rbx+40h]
0x140013b16  mov     rcx, [rax]
0x140013b19  cmp     [rcx+8], rax
0x140013b1d  jnz     short loc_140013B5A
0x140013b1f  mov     rdx, [rax+8]
0x140013b23  cmp     [rdx], rax
0x140013b26  jnz     short loc_140013B5A
0x140013b28  mov     [rdx], rcx
0x140013b2b  mov     [rcx+8], rdx
0x140013b2f  mov     rcx, [rbx+10h]; P
0x140013b33  test    rcx, rcx
0x140013b36  jz      short loc_140013B3D
0x140013b38  call    BwcDeleteFlow
0x140013b3d  mov     rdx, rbx; Entry
0x140013b40  lea     rcx, QoSPolicyList; Lookaside
0x140013b47  call    cs:__imp_ExFreeToNPagedLookasideList
0x140013b4e  nop     dword ptr [rax+rax+00h]
0x140013b53  add     rsp, 20h
0x140013b57  pop     rbx
0x140013b58  retn
0x140013b5a  mov     ecx, 3
0x140013b5f  int     29h; Win8: RtlFailFast(ecx)
```
