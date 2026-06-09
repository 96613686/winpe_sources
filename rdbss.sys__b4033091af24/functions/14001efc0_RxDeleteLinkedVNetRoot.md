# RxDeleteLinkedVNetRoot

- ea: `0x14001efc0`
- end: `0x14001f0f6`
- name: `RxDeleteLinkedVNetRoot`
- size: `310`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation`

## callees

- `0x140011850`
- `0x14001e83c`
- `0x14001efc0`
- `0x1400221f4`
- `0x140022524`
- `0x140050910`

## import_xrefs

- `ntoskrnl!IoDeleteSymbolicLink` at `0x14001f091`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14001f0af`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14001f091`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14001f0af`

## pseudocode

```c
void __fastcall RxDeleteLinkedVNetRoot(__int64 a1, __int64 a2, LOGICAL a3, UNICODE_STRING *a4)
{
  __int64 v7; // rax
  struct _LUID v8; // [rsp+30h] [rbp-10h] BYREF
  void *v9; // [rsp+38h] [rbp-8h] BYREF
  struct _LUID v10; // [rsp+68h] [rbp+28h] BYREF

  v9 = 0;
  v10 = 0;
  v8 = 0;
  if ( RxEnableLinkedConnections && (int)RxImpersonateLinkedToken(&v9, &v10, &v8) >= 0 )
  {
    if ( v10 != v8 && (*(_QWORD *)(a2 + 72) == v10 || *(_QWORD *)(a2 + 72) == v8) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_Zq(
          WPP_GLOBAL_Control->AttachedDevice,
          13,
          (unsigned int)WPP_e01a4f2c5ae23c78cfc8b6f416d17e00_Traceguids,
          (_DWORD)a4,
          a2);
      }
      if ( a4->Length )
        IoDeleteSymbolicLink(a4);
      RxRevert(v9);
      if ( a4->Length )
        IoDeleteSymbolicLink(a4);
      v7 = RxpDetachLinkedVNetRoot(a2);
      if ( v7 )
        RxFinalizeConnection(*(PNET_ROOT *)(v7 + 32), (PV_NET_ROOT)v7, a3);
    }
    else
    {
      RxRevert(v9);
    }
  }
}

```

## disassembly

```asm
0x14001efc0  mov     [rsp-18h+arg_0], rbx
0x14001efc5  mov     [rsp-18h+arg_10], rsi
0x14001efca  push    rbp
0x14001efcb  push    rdi
0x14001efcc  push    r14
0x14001efce  mov     rbp, rsp
0x14001efd1  sub     rsp, 40h
0x14001efd5  xor     r14d, r14d
0x14001efd8  mov     rbx, r9
0x14001efdb  cmp     cs:RxEnableLinkedConnections, r14b
0x14001efe2  mov     esi, r8d
0x14001efe5  mov     rdi, rdx
0x14001efe8  mov     [rbp+var_8], r14
0x14001efec  mov     [rbp+arg_8], r14
0x14001eff0  mov     [rbp+var_10], r14
0x14001eff4  jz      loc_14001F0E2
0x14001effa  lea     r8, [rbp+var_10]
0x14001effe  lea     rdx, [rbp+arg_8]
0x14001f002  lea     rcx, [rbp+var_8]
0x14001f006  call    RxImpersonateLinkedToken
0x14001f00b  test    eax, eax
0x14001f00d  js      loc_14001F0E2
0x14001f013  mov     rax, [rbp+var_10]
0x14001f017  mov     ecx, dword ptr [rbp+arg_8+4]
0x14001f01a  mov     edx, dword ptr [rbp+var_10+4]
0x14001f01d  cmp     dword ptr [rbp+arg_8], eax
0x14001f020  jnz     short loc_14001F02A
0x14001f022  cmp     ecx, edx
0x14001f024  jz      loc_14001F0D9
0x14001f02a  mov     r8d, [rdi+48h]
0x14001f02e  cmp     r8d, dword ptr [rbp+arg_8]
0x14001f032  jnz     short loc_14001F039
0x14001f034  cmp     [rdi+4Ch], ecx
0x14001f037  jz      short loc_14001F04B
0x14001f039  cmp     r8d, eax
0x14001f03c  jnz     loc_14001F0D9
0x14001f042  cmp     [rdi+4Ch], edx
0x14001f045  jnz     loc_14001F0D9
0x14001f04b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f052  lea     rax, WPP_GLOBAL_Control
0x14001f059  cmp     rcx, rax
0x14001f05c  jz      short loc_14001F088
0x14001f05e  mov     eax, [rcx+2Ch]
0x14001f061  test    al, al
0x14001f063  jns     short loc_14001F088
0x14001f065  cmp     byte ptr [rcx+29h], 2
0x14001f069  jb      short loc_14001F088
0x14001f06b  mov     rcx, [rcx+18h]
0x14001f06f  lea     r8, WPP_e01a4f2c5ae23c78cfc8b6f416d17e00_Traceguids
0x14001f076  mov     edx, 0Dh
0x14001f07b  mov     [rsp+40h+var_20], rdi
0x14001f080  mov     r9, rbx
0x14001f083  call    WPP_SF_Zq
0x14001f088  cmp     [rbx], r14w
0x14001f08c  jz      short loc_14001F09D
0x14001f08e  mov     rcx, rbx; SymbolicLinkName
0x14001f091  call    cs:__imp_IoDeleteSymbolicLink
0x14001f098  nop     dword ptr [rax+rax+00h]
0x14001f09d  mov     rcx, [rbp+var_8]
0x14001f0a1  call    RxRevert
0x14001f0a6  cmp     [rbx], r14w
0x14001f0aa  jz      short loc_14001F0BB
0x14001f0ac  mov     rcx, rbx; SymbolicLinkName
0x14001f0af  call    cs:__imp_IoDeleteSymbolicLink
0x14001f0b6  nop     dword ptr [rax+rax+00h]
0x14001f0bb  mov     rcx, rdi
0x14001f0be  call    RxpDetachLinkedVNetRoot
0x14001f0c3  test    rax, rax
0x14001f0c6  jz      short loc_14001F0E2
0x14001f0c8  mov     rcx, [rax+20h]; NetRoot
0x14001f0cc  mov     r8d, esi; ForceFilesClosed
0x14001f0cf  mov     rdx, rax; VNetRoot
0x14001f0d2  call    RxFinalizeConnection
0x14001f0d7  jmp     short loc_14001F0E2
0x14001f0d9  mov     rcx, [rbp+var_8]
0x14001f0dd  call    RxRevert
0x14001f0e2  mov     rbx, [rsp+40h+arg_0]
0x14001f0e7  mov     rsi, [rsp+40h+arg_10]
0x14001f0ec  add     rsp, 40h
0x14001f0f0  pop     r14
0x14001f0f2  pop     rdi
0x14001f0f3  pop     rbp
0x14001f0f4  retn
```
