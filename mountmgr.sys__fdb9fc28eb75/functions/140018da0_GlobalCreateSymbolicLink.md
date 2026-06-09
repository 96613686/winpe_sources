# GlobalCreateSymbolicLink

- ea: `0x140018da0`
- end: `0x140018e76`
- name: `GlobalCreateSymbolicLink`
- size: `214`
- prototype: `__int64 __fastcall(const UNICODE_STRING *, __int128 *)`
- caller_count: `7`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x140001ebc`
- `0x14000be4c`
- `0x14000c2d4`
- `0x14000ff00`
- `0x140014fc0`
- `0x140018af0`
- `0x14001b078`

## callees

- `0x140001ae0`
- `0x140018da0`
- `0x140018e80`

## import_xrefs

- `ntoskrnl!IoCreateSymbolicLink2` at `0x140018dea`
- `ntoskrnl!IoCreateSymbolicLink2` at `0x140018dea`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018e08`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018e08`

## pseudocode

```c
__int64 __fastcall GlobalCreateSymbolicLink(const UNICODE_STRING *a1, __int128 *a2)
{
  int StringWithGlobal; // ebx
  __int64 v4; // r8
  __int128 v5; // xmm0
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // rdx
  PVOID P[2]; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v10[24]; // [rsp+30h] [rbp-28h] BYREF

  *(_OWORD *)P = 0;
  memset(v10, 0, 20);
  StringWithGlobal = CreateStringWithGlobal(a1);
  if ( StringWithGlobal < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v8 = 13;
LABEL_13:
      WPP_SF_L(v7->AttachedDevice, v8, v4, (unsigned int)StringWithGlobal);
    }
  }
  else
  {
    v5 = *a2;
    *(_DWORD *)v10 = 1;
    *(_OWORD *)&v10[8] = v5;
    StringWithGlobal = IoCreateSymbolicLink2(P, v10);
    if ( StringWithGlobal < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        v8 = 14;
        goto LABEL_13;
      }
    }
  }
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0);
  return (unsigned int)StringWithGlobal;
}

```

## disassembly

```asm
0x140018da0  mov     [rsp+arg_0], rbx
0x140018da5  push    rdi
0x140018da6  sub     rsp, 50h
0x140018daa  xorps   xmm0, xmm0
0x140018dad  mov     rdi, rdx
0x140018db0  xor     eax, eax
0x140018db2  lea     rdx, [rsp+58h+P]
0x140018db7  movups  xmmword ptr [rsp+58h+P], xmm0
0x140018dbc  mov     [rsp+58h+var_18], eax
0x140018dc0  movups  [rsp+58h+var_28], xmm0
0x140018dc5  call    CreateStringWithGlobal
0x140018dca  mov     ebx, eax
0x140018dcc  test    eax, eax
0x140018dce  js      short loc_140018E22
0x140018dd0  movups  xmm0, xmmword ptr [rdi]
0x140018dd3  lea     rdx, [rsp+58h+var_28]
0x140018dd8  mov     dword ptr [rsp+58h+var_28], 1
0x140018de0  lea     rcx, [rsp+58h+P]
0x140018de5  movups  [rsp+58h+var_28+8], xmm0
0x140018dea  call    cs:__imp_IoCreateSymbolicLink2
0x140018df1  nop     dword ptr [rax+rax+00h]
0x140018df6  mov     ebx, eax
0x140018df8  test    eax, eax
0x140018dfa  js      short loc_140018E43
0x140018dfc  mov     rcx, [rsp+58h+P+8]; P
0x140018e01  test    rcx, rcx
0x140018e04  jz      short loc_140018E14
0x140018e06  xor     edx, edx; Tag
0x140018e08  call    cs:__imp_ExFreePoolWithTag
0x140018e0f  nop     dword ptr [rax+rax+00h]
0x140018e14  mov     eax, ebx
0x140018e16  mov     rbx, [rsp+58h+arg_0]
0x140018e1b  add     rsp, 50h
0x140018e1f  pop     rdi
0x140018e20  retn
0x140018e22  mov     rcx, cs:WPP_GLOBAL_Control
0x140018e29  lea     rax, WPP_GLOBAL_Control
0x140018e30  cmp     rcx, rax
0x140018e33  jz      short loc_140018DFC
0x140018e35  mov     eax, [rcx+2Ch]
0x140018e38  test    al, 1
0x140018e3a  jz      short loc_140018DFC
0x140018e3c  mov     edx, 0Dh
0x140018e41  jmp     short loc_140018E68
0x140018e43  mov     rcx, cs:WPP_GLOBAL_Control
0x140018e4a  lea     rax, WPP_GLOBAL_Control
0x140018e51  cmp     rcx, rax
0x140018e54  jz      short loc_140018DFC
0x140018e56  mov     eax, [rcx+2Ch]
0x140018e59  test    al, 1
0x140018e5b  jz      short loc_140018DFC
0x140018e5d  cmp     byte ptr [rcx+29h], 1
0x140018e61  jb      short loc_140018DFC
0x140018e63  mov     edx, 0Eh
0x140018e68  mov     rcx, [rcx+18h]
0x140018e6c  mov     r9d, ebx
0x140018e6f  call    WPP_SF_L
0x140018e74  jmp     short loc_140018DFC
```
