# NfsReadDirectoryQuit

- ea: `0x140014970`
- end: `0x140014a7d`
- name: `NfsReadDirectoryQuit`
- size: `269`
- prototype: `void __fastcall(PVOID *, char)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x140003510`
- `0x140004530`
- `0x140005de0`
- `0x1400070a0`
- `0x14002a9e0`
- `0x140030b60`
- `0x1400372e8`

## callees

- `0x140014970`
- `0x1400159cc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400149ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014a37`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400149ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014a37`
- `rpcxdr!OncRpcDestroy` at `0x140014a19`
- `rpcxdr!OncRpcDestroy` at `0x140014a19`

## pseudocode

```c
void __fastcall NfsReadDirectoryQuit(PVOID *a1, char a2)
{
  _QWORD *v4; // rbx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 205, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
  v4 = *a1;
  if ( *a1 )
  {
    if ( *(_DWORD *)v4 == 4 )
    {
      if ( a2 )
      {
        ExFreePoolWithTag(*a1, 0);
        *a1 = 0;
      }
      return;
    }
    if ( v4[1] )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 206, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
      OncRpcDestroy(v4[1]);
      v4[1] = 0;
    }
    if ( a2 )
    {
      ExFreePoolWithTag(v4, 0);
      *a1 = 0;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 207, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
}

```

## disassembly

```asm
0x140014970  push    rbx
0x140014972  push    rsi
0x140014973  push    rdi
0x140014974  push    r14
0x140014976  sub     rsp, 28h
0x14001497a  movzx   esi, dl
0x14001497d  mov     rdi, rcx
0x140014980  mov     rcx, cs:WPP_GLOBAL_Control
0x140014987  lea     r14, WPP_GLOBAL_Control
0x14001498e  cmp     rcx, r14
0x140014991  jz      short loc_1400149AF
0x140014993  mov     eax, [rcx+2Ch]
0x140014996  test    al, 40h
0x140014998  jz      short loc_1400149AF
0x14001499a  mov     rcx, [rcx+18h]
0x14001499e  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x1400149a5  mov     edx, 0CDh
0x1400149aa  call    WPP_SF_
0x1400149af  mov     rbx, [rdi]
0x1400149b2  test    rbx, rbx
0x1400149b5  jz      loc_140014A4A
0x1400149bb  cmp     dword ptr [rbx], 4
0x1400149be  jnz     short loc_1400149E6
0x1400149c0  test    sil, sil
0x1400149c3  jz      loc_140014A72
0x1400149c9  xor     edx, edx; Tag
0x1400149cb  mov     rcx, rbx; P
0x1400149ce  call    cs:__imp_ExFreePoolWithTag
0x1400149d5  nop     dword ptr [rax+rax+00h]
0x1400149da  mov     qword ptr [rdi], 0
0x1400149e1  jmp     loc_140014A72
0x1400149e6  cmp     qword ptr [rbx+8], 0
0x1400149eb  jz      short loc_140014A2D
0x1400149ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400149f4  cmp     rcx, r14
0x1400149f7  jz      short loc_140014A15
0x1400149f9  mov     eax, [rcx+2Ch]
0x1400149fc  test    al, 2
0x1400149fe  jz      short loc_140014A15
0x140014a00  mov     rcx, [rcx+18h]
0x140014a04  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x140014a0b  mov     edx, 0CEh
0x140014a10  call    WPP_SF_
0x140014a15  mov     rcx, [rbx+8]
0x140014a19  call    cs:__imp_OncRpcDestroy
0x140014a20  nop     dword ptr [rax+rax+00h]
0x140014a25  mov     qword ptr [rbx+8], 0
0x140014a2d  test    sil, sil
0x140014a30  jz      short loc_140014A4A
0x140014a32  xor     edx, edx; Tag
0x140014a34  mov     rcx, rbx; P
0x140014a37  call    cs:__imp_ExFreePoolWithTag
0x140014a3e  nop     dword ptr [rax+rax+00h]
0x140014a43  mov     qword ptr [rdi], 0
0x140014a4a  mov     rcx, cs:WPP_GLOBAL_Control
0x140014a51  cmp     rcx, r14
0x140014a54  jz      short loc_140014A72
0x140014a56  mov     eax, [rcx+2Ch]
0x140014a59  test    al, 40h
0x140014a5b  jz      short loc_140014A72
0x140014a5d  mov     rcx, [rcx+18h]
0x140014a61  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x140014a68  mov     edx, 0CFh
0x140014a6d  call    WPP_SF_
0x140014a72  add     rsp, 28h
0x140014a76  pop     r14
0x140014a78  pop     rdi
0x140014a79  pop     rsi
0x140014a7a  pop     rbx
0x140014a7b  retn
```
