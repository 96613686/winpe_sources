# WanDeallocateECP

- ea: `0x140024e48`
- end: `0x140024f4c`
- name: `WanDeallocateECP`
- size: `260`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140005568`
- `0x14002aa40`

## callees

- `0x14000a290`
- `0x140024e48`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140024ea5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140024edf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140024ea5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140024edf`

## pseudocode

```c
void __fastcall WanDeallocateECP(__int64 a1, __int64 a2, _QWORD *a3)
{
  void *v5; // rdx
  void *v6; // rdx
  struct _NPAGED_LOOKASIDE_LIST *v7; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_e3dccf6fd86a38f3a431f6838d605fbf_Traceguids);
  }
  v5 = (void *)a3[5];
  if ( v5 )
  {
    ExFreeToNPagedLookasideList(&EncryptCtxList, v5);
    a3[6] = 0;
    a3[5] = 0;
  }
  v6 = (void *)a3[7];
  if ( v6 )
  {
    v7 = &CachedKeyListLong;
    if ( (*(_DWORD *)(a2 + 56) & 0x40) == 0 )
      v7 = &CachedKeyList;
    ExFreeToNPagedLookasideList(v7, v6);
    a3[7] = 0;
    a3[9] = 0;
    a3[8] = 0;
  }
  *(_DWORD *)(a2 + 56) &= 0xFFFFFF0F;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_e3dccf6fd86a38f3a431f6838d605fbf_Traceguids);
  }
}

```

## disassembly

```asm
0x140024e48  mov     [rsp+arg_0], rbx
0x140024e4d  mov     [rsp+arg_8], rdi
0x140024e52  push    r14
0x140024e54  sub     rsp, 20h
0x140024e58  mov     rbx, r8
0x140024e5b  mov     rdi, rdx
0x140024e5e  mov     rcx, cs:WPP_GLOBAL_Control
0x140024e65  lea     r14, WPP_GLOBAL_Control
0x140024e6c  cmp     rcx, r14
0x140024e6f  jz      short loc_140024E95
0x140024e71  test    dword ptr [rcx+2Ch], 200h
0x140024e78  jz      short loc_140024E95
0x140024e7a  cmp     byte ptr [rcx+29h], 5
0x140024e7e  jb      short loc_140024E95
0x140024e80  mov     rcx, [rcx+18h]
0x140024e84  lea     r8, WPP_e3dccf6fd86a38f3a431f6838d605fbf_Traceguids
0x140024e8b  mov     edx, 10h
0x140024e90  call    WPP_SF_
0x140024e95  mov     rdx, [rbx+28h]; Entry
0x140024e99  test    rdx, rdx
0x140024e9c  jz      short loc_140024EC1
0x140024e9e  lea     rcx, EncryptCtxList; Lookaside
0x140024ea5  call    cs:__imp_ExFreeToNPagedLookasideList
0x140024eac  nop     dword ptr [rax+rax+00h]
0x140024eb1  mov     qword ptr [rbx+30h], 0
0x140024eb9  mov     qword ptr [rbx+28h], 0
0x140024ec1  mov     rdx, [rbx+38h]; Entry
0x140024ec5  test    rdx, rdx
0x140024ec8  jz      short loc_140024F03
0x140024eca  mov     eax, [rdi+38h]
0x140024ecd  lea     rcx, CachedKeyListLong
0x140024ed4  test    al, 40h
0x140024ed6  jnz     short loc_140024EDF
0x140024ed8  lea     rcx, CachedKeyList; Lookaside
0x140024edf  call    cs:__imp_ExFreeToNPagedLookasideList
0x140024ee6  nop     dword ptr [rax+rax+00h]
0x140024eeb  mov     qword ptr [rbx+38h], 0
0x140024ef3  mov     qword ptr [rbx+48h], 0
0x140024efb  mov     qword ptr [rbx+40h], 0
0x140024f03  and     dword ptr [rdi+38h], 0FFFFFF0Fh
0x140024f0a  mov     rcx, cs:WPP_GLOBAL_Control
0x140024f11  cmp     rcx, r14
0x140024f14  jz      short loc_140024F3A
0x140024f16  test    dword ptr [rcx+2Ch], 200h
0x140024f1d  jz      short loc_140024F3A
0x140024f1f  cmp     byte ptr [rcx+29h], 5
0x140024f23  jb      short loc_140024F3A
0x140024f25  mov     rcx, [rcx+18h]
0x140024f29  lea     r8, WPP_e3dccf6fd86a38f3a431f6838d605fbf_Traceguids
0x140024f30  mov     edx, 11h
0x140024f35  call    WPP_SF_
0x140024f3a  mov     rbx, [rsp+28h+arg_0]
0x140024f3f  mov     rdi, [rsp+28h+arg_8]
0x140024f44  add     rsp, 20h
0x140024f48  pop     r14
0x140024f4a  retn
```
