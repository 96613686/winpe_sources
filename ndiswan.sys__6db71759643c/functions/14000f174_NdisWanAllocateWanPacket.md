# NdisWanAllocateWanPacket

- ea: `0x14000f174`
- end: `0x14000f24e`
- name: `NdisWanAllocateWanPacket`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140010150`

## callees

- `0x14000a290`
- `0x14000f174`
- `0x140016700`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14000f1a7`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14000f1a7`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000f192`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000f192`

## pseudocode

```c
_QWORD *__fastcall NdisWanAllocateWanPacket(__int64 a1)
{
  __int64 v1; // rbx
  _QWORD *v2; // rax
  _QWORD *v3; // rdi
  _QWORD *result; // rax

  v1 = *(_QWORD *)(a1 + 72);
  if ( *(_DWORD *)(v1 + 188) )
    v2 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v1 + 336));
  else
    v2 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v1 + 320));
  v3 = v2;
  if ( v2 )
  {
    memset(v2, 0, *(unsigned int *)(v1 + 256));
    v3[4] = v3 + 14;
    v3[5] = (char *)v3 + *(unsigned int *)(v1 + 168) + *(unsigned int *)(v1 + 180) + *(unsigned int *)(v1 + 176) + 112;
    result = v3;
    v3[2] = (char *)v3 + *(unsigned int *)(v1 + 176) + 112;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_714410adb39534c9cec6a41078899c0f_Traceguids);
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000f174  mov     [rsp+arg_0], rbx
0x14000f179  push    rdi
0x14000f17a  sub     rsp, 20h
0x14000f17e  mov     rbx, [rcx+48h]
0x14000f182  cmp     dword ptr [rbx+0BCh], 0
0x14000f189  jnz     short loc_14000F1A0
0x14000f18b  lea     rcx, [rbx+140h]; Lookaside
0x14000f192  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14000f199  nop     dword ptr [rax+rax+00h]
0x14000f19e  jmp     short loc_14000F1B3
0x14000f1a0  lea     rcx, [rbx+150h]; ListHead
0x14000f1a7  call    cs:__imp_ExpInterlockedPopEntrySList
0x14000f1ae  nop     dword ptr [rax+rax+00h]
0x14000f1b3  mov     rdi, rax
0x14000f1b6  test    rax, rax
0x14000f1b9  jnz     short loc_14000F1F2
0x14000f1bb  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f1c2  lea     rax, WPP_GLOBAL_Control
0x14000f1c9  cmp     rcx, rax
0x14000f1cc  jz      short loc_14000F1EE
0x14000f1ce  mov     eax, [rcx+2Ch]
0x14000f1d1  test    al, 40h
0x14000f1d3  jz      short loc_14000F1EE
0x14000f1d5  cmp     byte ptr [rcx+29h], 2
0x14000f1d9  jb      short loc_14000F1EE
0x14000f1db  mov     rcx, [rcx+18h]
0x14000f1df  lea     edx, [rdi+2Eh]
0x14000f1e2  lea     r8, WPP_714410adb39534c9cec6a41078899c0f_Traceguids
0x14000f1e9  call    WPP_SF_
0x14000f1ee  xor     eax, eax
0x14000f1f0  jmp     short loc_14000F242
0x14000f1f2  mov     r8d, [rbx+100h]; Size
0x14000f1f9  xor     edx, edx; Val
0x14000f1fb  mov     rcx, rdi; void *
0x14000f1fe  call    memset
0x14000f203  lea     rax, [rdi+70h]
0x14000f207  mov     [rdi+20h], rax
0x14000f20b  mov     ecx, [rbx+0B4h]
0x14000f211  mov     edx, [rbx+0A8h]
0x14000f217  mov     eax, [rbx+0B0h]
0x14000f21d  add     rdx, rdi
0x14000f220  add     rdx, rcx
0x14000f223  add     rax, 70h ; 'p'
0x14000f227  add     rax, rdx
0x14000f22a  mov     [rdi+28h], rax
0x14000f22e  mov     rax, rdi
0x14000f231  mov     ecx, [rbx+0B0h]
0x14000f237  add     rcx, 70h ; 'p'
0x14000f23b  add     rcx, rdi
0x14000f23e  mov     [rdi+10h], rcx
0x14000f242  mov     rbx, [rsp+28h+arg_0]
0x14000f247  add     rsp, 20h
0x14000f24b  pop     rdi
0x14000f24c  retn
```
