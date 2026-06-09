# NcaUserStoreCreateEvColls(NCA_USER_ *)

- ea: `0x180017bc8`
- end: `0x180017c72`
- name: `?NcaUserStoreCreateEvColls@@YAKPEAUNCA_USER_@@@Z`
- size: `170`
- prototype: `__int64 __fastcall(struct NCA_USER_ *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180017708`
- `0x180018200`

## callees

- `0x180004f34`
- `0x1800127ec`
- `0x1800169b0`
- `0x180016ca8`
- `0x180017bc8`

## pseudocode

```c
__int64 __fastcall NcaUserStoreCreateEvColls(struct NCA_USER_ *a1)
{
  unsigned int v2; // ebx
  __int64 result; // rax

  v2 = NcaDAPEvidenceUserSnapshotCreate((PVOID)*((unsigned int *)a1 + 4));
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_f6fba97516d23319eaec26e747470e80_Traceguids, v2);
  }
  else
  {
    v2 = NcaEvCollProbesCreate(*((_DWORD *)a1 + 4));
    if ( v2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_f6fba97516d23319eaec26e747470e80_Traceguids, v2);
      NcaDAPEvidenceUserSnapshotRemove(*((unsigned int *)a1 + 4));
    }
  }
  result = v2;
  *((_DWORD *)a1 + 12) = 1;
  return result;
}

```

## disassembly

```asm
0x180017bc8  mov     [rsp+arg_0], rbx
0x180017bcd  push    rdi
0x180017bce  sub     rsp, 20h
0x180017bd2  mov     rdi, rcx
0x180017bd5  mov     ecx, [rcx+10h]; pv
0x180017bd8  call    NcaDAPEvidenceUserSnapshotCreate
0x180017bdd  mov     ebx, eax
0x180017bdf  test    eax, eax
0x180017be1  jz      short loc_180017C16
0x180017be3  mov     rcx, cs:WPP_GLOBAL_Control
0x180017bea  lea     rax, WPP_GLOBAL_Control
0x180017bf1  cmp     rcx, rax
0x180017bf4  jz      short loc_180017C5D
0x180017bf6  test    byte ptr [rcx+1Ch], 1
0x180017bfa  jz      short loc_180017C5D
0x180017bfc  mov     rcx, [rcx+10h]
0x180017c00  lea     r8, WPP_f6fba97516d23319eaec26e747470e80_Traceguids
0x180017c07  mov     edx, 0Eh
0x180017c0c  mov     r9d, ebx
0x180017c0f  call    WPP_SF_d
0x180017c14  jmp     short loc_180017C5D
0x180017c16  mov     ecx, [rdi+10h]; unsigned int
0x180017c19  call    NcaEvCollProbesCreate
0x180017c1e  mov     ebx, eax
0x180017c20  test    eax, eax
0x180017c22  jz      short loc_180017C5D
0x180017c24  mov     rcx, cs:WPP_GLOBAL_Control
0x180017c2b  lea     rax, WPP_GLOBAL_Control
0x180017c32  cmp     rcx, rax
0x180017c35  jz      short loc_180017C55
0x180017c37  test    byte ptr [rcx+1Ch], 1
0x180017c3b  jz      short loc_180017C55
0x180017c3d  mov     rcx, [rcx+10h]
0x180017c41  lea     r8, WPP_f6fba97516d23319eaec26e747470e80_Traceguids
0x180017c48  mov     edx, 0Fh
0x180017c4d  mov     r9d, ebx
0x180017c50  call    WPP_SF_d
0x180017c55  mov     ecx, [rdi+10h]
0x180017c58  call    NcaDAPEvidenceUserSnapshotRemove
0x180017c5d  mov     eax, ebx
0x180017c5f  mov     dword ptr [rdi+30h], 1
0x180017c66  mov     rbx, [rsp+28h+arg_0]
0x180017c6b  add     rsp, 20h
0x180017c6f  pop     rdi
0x180017c70  retn
```
