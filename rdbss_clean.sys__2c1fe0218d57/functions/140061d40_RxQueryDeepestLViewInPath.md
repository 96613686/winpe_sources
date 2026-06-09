# RxQueryDeepestLViewInPath

- ea: `0x140061d40`
- end: `0x140061ed8`
- name: `RxQueryDeepestLViewInPath`
- size: `408`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140016e70`
- `0x140017310`
- `0x140058f00`
- `0x140060f10`
- `0x140061d40`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140061dd2`
- `ntoskrnl!ExReleaseResourceLite` at `0x140061dd2`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140061d87`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140061d87`

## pseudocode

```c
__int64 __fastcall RxQueryDeepestLViewInPath(__int64 a1, _WORD *a2, _QWORD *a3)
{
  unsigned int v6; // ebp
  PERESOURCE *p_PagingIoResource; // r15
  __int64 v8; // rbx
  _BYTE v10[40]; // [rsp+30h] [rbp-28h] BYREF

  if ( !Fcb )
    return 3221225485LL;
  v6 = -1073741275;
  p_PagingIoResource = &Fcb[1].Header.PagingIoResource;
  ExAcquireResourceSharedLite((PERESOURCE)&Fcb[1].spacer.ValidDataLength, 1u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      173,
      &WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids,
      p_PagingIoResource);
  }
  v8 = RxPrefixTableLookupNameEx(p_PagingIoResource, a1, v10, 0, 1);
  ExReleaseResourceLite((PERESOURCE)(p_PagingIoResource + 3));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      174,
      &WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids,
      p_PagingIoResource);
  }
  if ( v8 )
  {
    v6 = 0;
    *a2 = *(_WORD *)(v8 + 112);
    *a3 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v8 + 32) + 32LL) + 48LL);
    RxDereference((PVOID)v8, LHS_LockNotHeld);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      175,
      &WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids,
      v6,
      (unsigned __int16)*a2);
  }
  return v6;
}

```

## disassembly

```asm
0x140061d40  push    rbx
0x140061d42  push    rsi
0x140061d43  push    rdi
0x140061d44  sub     rsp, 40h
0x140061d48  mov     rax, cs:Fcb
0x140061d4f  mov     rdi, r8
0x140061d52  mov     rsi, rdx
0x140061d55  mov     rbx, rcx
0x140061d58  test    rax, rax
0x140061d5b  jz      loc_140061E1E
0x140061d61  mov     [rsp+58h+arg_0], rbp
0x140061d66  mov     dl, 1; Wait
0x140061d68  mov     [rsp+58h+arg_8], r12
0x140061d6d  mov     ebp, 0C0000225h
0x140061d72  mov     [rsp+58h+arg_10], r14
0x140061d77  mov     [rsp+58h+arg_18], r15
0x140061d7c  lea     r15, [rax+2A0h]
0x140061d83  lea     rcx, [r15+18h]; Resource
0x140061d87  call    cs:__imp_ExAcquireResourceSharedLite
0x140061d8e  nop     dword ptr [rax+rax+00h]
0x140061d93  mov     rcx, cs:WPP_GLOBAL_Control
0x140061d9a  lea     r12, WPP_GLOBAL_Control
0x140061da1  cmp     rcx, r12
0x140061da4  jz      short loc_140061DB3
0x140061da6  test    dword ptr [rcx+2Ch], 400h
0x140061dad  jnz     loc_140061E8A
0x140061db3  xor     r9d, r9d
0x140061db6  mov     byte ptr [rsp+58h+var_38], 1
0x140061dbb  lea     r8, [rsp+58h+var_28]
0x140061dc0  mov     rdx, rbx
0x140061dc3  mov     rcx, r15
0x140061dc6  call    RxPrefixTableLookupNameEx
0x140061dcb  lea     rcx, [r15+18h]; Resource
0x140061dcf  mov     rbx, rax
0x140061dd2  call    cs:__imp_ExReleaseResourceLite
0x140061dd9  nop     dword ptr [rax+rax+00h]
0x140061dde  mov     rcx, cs:WPP_GLOBAL_Control
0x140061de5  mov     r14, [rsp+58h+arg_10]
0x140061dea  cmp     rcx, r12
0x140061ded  jnz     short loc_140061E5E
0x140061def  mov     r15, [rsp+58h+arg_18]
0x140061df4  test    rbx, rbx
0x140061df7  jnz     loc_140061EB1
0x140061dfd  mov     rcx, cs:WPP_GLOBAL_Control
0x140061e04  cmp     rcx, r12
0x140061e07  mov     r12, [rsp+58h+arg_8]
0x140061e0c  jnz     short loc_140061E2C
0x140061e0e  mov     eax, ebp
0x140061e10  mov     rbp, [rsp+58h+arg_0]
0x140061e15  add     rsp, 40h
0x140061e19  pop     rdi
0x140061e1a  pop     rsi
0x140061e1b  pop     rbx
0x140061e1c  retn
0x140061e1e  mov     eax, 0C000000Dh
0x140061e23  add     rsp, 40h
0x140061e27  pop     rdi
0x140061e28  pop     rsi
0x140061e29  pop     rbx
0x140061e2a  retn
0x140061e2c  test    dword ptr [rcx+2Ch], 400h
0x140061e33  jz      short loc_140061E0E
0x140061e35  cmp     byte ptr [rcx+29h], 2
0x140061e39  jb      short loc_140061E0E
0x140061e3b  movzx   r9d, word ptr [rsi]
0x140061e3f  lea     r8, WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids
0x140061e46  mov     rcx, [rcx+18h]
0x140061e4a  mov     edx, 0AFh
0x140061e4f  mov     [rsp+58h+var_38], r9d
0x140061e54  mov     r9d, ebp
0x140061e57  call    WPP_SF_Dd
0x140061e5c  jmp     short loc_140061E0E
0x140061e5e  test    dword ptr [rcx+2Ch], 400h
0x140061e65  jz      short loc_140061DEF
0x140061e67  cmp     byte ptr [rcx+29h], 4
0x140061e6b  jb      short loc_140061DEF
0x140061e6d  mov     rcx, [rcx+18h]
0x140061e71  lea     r8, WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids
0x140061e78  mov     edx, 0AEh
0x140061e7d  mov     r9, r15
0x140061e80  call    WPP_SF_q
0x140061e85  jmp     loc_140061DEF
0x140061e8a  cmp     byte ptr [rcx+29h], 4
0x140061e8e  jb      loc_140061DB3
0x140061e94  mov     rcx, [rcx+18h]
0x140061e98  lea     r8, WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids
0x140061e9f  mov     edx, 0ADh
0x140061ea4  mov     r9, r15
0x140061ea7  call    WPP_SF_q
0x140061eac  jmp     loc_140061DB3
0x140061eb1  movzx   eax, word ptr [rbx+70h]
0x140061eb5  xor     ebp, ebp
0x140061eb7  mov     [rsi], ax
0x140061eba  xor     edx, edx; LockHoldingState
0x140061ebc  mov     rax, [rbx+20h]
0x140061ec0  mov     rcx, [rax+20h]
0x140061ec4  mov     rax, [rcx+30h]
0x140061ec8  mov     rcx, rbx; Instance
0x140061ecb  mov     [rdi], rax
0x140061ece  call    RxDereference
0x140061ed3  jmp     loc_140061DFD
```
