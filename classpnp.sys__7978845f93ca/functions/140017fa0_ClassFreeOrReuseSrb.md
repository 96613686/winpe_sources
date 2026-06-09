# ClassFreeOrReuseSrb

- ea: `0x140017fa0`
- end: `0x140018010`
- name: `ClassFreeOrReuseSrb`
- size: `112`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140012a00`
- `0x140016350`
- `0x140037e10`
- `0x14005e53c`

## callees

- `0x140017fa0`
- `0x14001feac`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400411b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400411b0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140017fb6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140017fb6`

## pseudocode

```c
void __fastcall ClassFreeOrReuseSrb(__int64 a1, void *a2)
{
  if ( (*(_BYTE *)(a1 + 104) & 4) != 0 )
  {
    ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 256), a2);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_fdfccdbcc72438cfb0f431eafc7dd1cf_Traceguids);
    }
    if ( a2 )
      ExFreePoolWithTag(a2, 0);
  }
}

```

## disassembly

```asm
0x140017fa0  push    rbx
0x140017fa2  sub     rsp, 20h
0x140017fa6  test    byte ptr [rcx+68h], 4
0x140017faa  mov     rbx, rdx
0x140017fad  jz      short loc_140017FC9
0x140017faf  add     rcx, 100h; Lookaside
0x140017fb6  call    cs:__imp_ExFreeToNPagedLookasideList
0x140017fbd  nop     dword ptr [rax+rax+00h]
0x140017fc2  add     rsp, 20h
0x140017fc6  pop     rbx
0x140017fc7  retn
0x140017fc9  mov     rcx, cs:WPP_GLOBAL_Control
0x140017fd0  lea     rax, WPP_GLOBAL_Control
0x140017fd7  cmp     rcx, rax
0x140017fda  jz      loc_1400411A2
0x140017fe0  mov     eax, [rcx+2Ch]
0x140017fe3  test    al, 1
0x140017fe5  jz      loc_1400411A2
0x140017feb  cmp     byte ptr [rcx+29h], 2
0x140017fef  jb      loc_1400411A2
0x140017ff5  mov     rcx, [rcx+18h]
0x140017ff9  lea     r8, WPP_fdfccdbcc72438cfb0f431eafc7dd1cf_Traceguids
0x140018000  mov     edx, 16h
0x140018005  call    WPP_SF_
0x14001800a  nop
0x14001800b  jmp     loc_1400411A2
0x1400411a2  test    rbx, rbx
0x1400411a5  jz      loc_140017FC2
0x1400411ab  xor     edx, edx; Tag
0x1400411ad  mov     rcx, rbx; P
0x1400411b0  call    cs:__imp_ExFreePoolWithTag
0x1400411b7  nop     dword ptr [rax+rax+00h]
0x1400411bc  nop
0x1400411bd  jmp     loc_140017FC2
```
