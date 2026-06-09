# LdrpProcessDetachNode

- ea: `0x1800ced58`
- end: `0x1800ceec3`
- name: `LdrpProcessDetachNode`
- size: `363`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180069678`

## callees

- `0x18001a0d0`
- `0x18001a420`
- `0x18001eb80`
- `0x18006d6e8`
- `0x18006d980`
- `0x1800ced58`
- `0x1800ceed0`
- `0x18010a200`

## string_xrefs

- `0x1800cee0d`: `Uninitializing DLL "%wZ" (Init routine: %p)\n`

## pseudocode

```c
void __fastcall LdrpProcessDetachNode(_QWORD **a1)
{
  _QWORD *i; // rdi
  _QWORD *v3; // rbx
  __int64 *v4; // rax
  __int64 v5; // rcx
  __int64 **v6; // rdx
  __int64 v7; // r15
  _QWORD v8[2]; // [rsp+50h] [rbp-68h] BYREF
  __int128 v9; // [rsp+60h] [rbp-58h]
  __int128 v10; // [rsp+70h] [rbp-48h]
  __int128 v11; // [rsp+80h] [rbp-38h]
  __int64 v12; // [rsp+90h] [rbp-28h]

  for ( i = *a1; i != a1; i = (_QWORD *)*i )
  {
    v3 = i - 20;
    *((_WORD *)i - 26) = 0;
    LdrpRecordUnloadEvent(i - 20);
    v4 = i - 16;
    v5 = *v4;
    if ( *v4 )
    {
      if ( *(__int64 **)(v5 + 8) != v4 || (v6 = (__int64 **)v3[5], *v6 != v4) )
        __fastfail(3u);
      *v6 = (__int64 *)v5;
      *(_QWORD *)(v5 + 8) = v6;
      *v4 = 1;
    }
    v7 = v3[7];
    if ( v7 && (v3[13] & 0x80000) != 0 )
    {
      LdrpLogInternal(
        (int)"minkernel\\ldr\\ldrsnap.c",
        2769,
        (int)"LdrpProcessDetachNode",
        2,
        "Uninitializing DLL \"%wZ\" (Init routine: %p)\n",
        (_BYTE)i - 88);
      v8[0] = 72;
      v8[1] = 1;
      v9 = 0;
      v10 = 0;
      v11 = 0;
      v12 = 0;
      RtlActivateActivationContextUnsafeFast(v8, v3[17]);
      if ( *((_WORD *)v3 + 55) )
        LdrpCallTlsInitializers(0, (__int64)(i - 20));
      LdrpCallInitRoutine(v7, v3[6], 0, 0);
      RtlDeactivateActivationContextUnsafeFast(v8);
    }
  }
}

```

## disassembly

```asm
0x1800ced58  mov     [rsp+arg_10], rbx
0x1800ced5d  mov     [rsp+arg_18], rsi
0x1800ced62  mov     [rsp+arg_0], rcx
0x1800ced67  push    rdi
0x1800ced68  push    r14
0x1800ced6a  push    r15
0x1800ced6c  sub     rsp, 0A0h
0x1800ced73  mov     r14, rcx
0x1800ced76  mov     rdi, [rcx]
0x1800ced79  xor     esi, esi
0x1800ced7b  mov     [rsp+0B8h+arg_8], rdi
0x1800ced83  cmp     rdi, r14
0x1800ced86  jz      short loc_1800CEDBD
0x1800ced88  lea     rbx, [rdi-0A0h]
0x1800ced8f  mov     [rbx+6Ch], si
0x1800ced93  mov     rcx, rbx
0x1800ced96  call    LdrpRecordUnloadEvent
0x1800ced9b  lea     rax, [rbx+20h]
0x1800ced9f  mov     rcx, [rax]
0x1800ceda2  test    rcx, rcx
0x1800ceda5  jz      short loc_1800CEDE5
0x1800ceda7  cmp     [rcx+8], rax
0x1800cedab  jnz     short loc_1800CEDB6
0x1800cedad  mov     rdx, [rax+8]
0x1800cedb1  cmp     [rdx], rax
0x1800cedb4  jz      short loc_1800CEDD7
0x1800cedb6  mov     ecx, 3
0x1800cedbb  int     29h; Win8: RtlFailFast(ecx)
0x1800cedbd  lea     r11, [rsp+0B8h+var_18]
0x1800cedc5  mov     rbx, [r11+30h]
0x1800cedc9  mov     rsi, [r11+38h]
0x1800cedcd  mov     rsp, r11
0x1800cedd0  pop     r15
0x1800cedd2  pop     r14
0x1800cedd4  pop     rdi
0x1800cedd5  retn
0x1800cedd7  mov     [rdx], rcx
0x1800cedda  mov     [rcx+8], rdx
0x1800cedde  mov     qword ptr [rax], 1
0x1800cede5  mov     r15, [rbx+38h]
0x1800cede9  test    r15, r15
0x1800cedec  jz      loc_1800CEEBB
0x1800cedf2  mov     eax, [rbx+68h]
0x1800cedf5  bt      eax, 13h
0x1800cedf9  jnb     loc_1800CEEBB
0x1800cedff  lea     rax, [rbx+48h]
0x1800cee03  mov     [rsp+0B8h+var_88], r15
0x1800cee08  mov     qword ptr [rsp+0B8h+ArgList], rax; ArgList
0x1800cee0d  lea     rax, aUninitializing; "Uninitializing DLL \"%wZ\" (Init routin"...
0x1800cee14  mov     [rsp+0B8h+Format], rax; Format
0x1800cee19  mov     r9d, 2; int
0x1800cee1f  lea     r8, aLdrpprocessdet; "LdrpProcessDetachNode"
0x1800cee26  mov     edx, 0AD1h; int
0x1800cee2b  lea     rcx, aMinkernelLdrLd_4; "minkernel\\ldr\\ldrsnap.c"
0x1800cee32  call    LdrpLogInternal
0x1800cee37  mov     [rsp+0B8h+var_68], 48h ; 'H'
0x1800cee40  mov     [rsp+0B8h+var_60], 1
0x1800cee49  xorps   xmm0, xmm0
0x1800cee4c  xor     eax, eax
0x1800cee4e  movups  [rsp+0B8h+var_58], xmm0
0x1800cee53  movups  [rsp+0B8h+var_48], xmm0
0x1800cee58  movups  [rsp+0B8h+var_38], xmm0
0x1800cee60  mov     [rsp+0B8h+var_28], rax
0x1800cee68  mov     rdx, [rbx+88h]
0x1800cee6f  lea     rcx, [rsp+0B8h+var_68]
0x1800cee74  call    RtlActivateActivationContextUnsafeFast
0x1800cee79  nop
0x1800cee7a  cmp     [rbx+6Eh], si
0x1800cee7e  jz      short loc_1800CEE8B
0x1800cee80  mov     rdx, rbx
0x1800cee83  xor     ecx, ecx
0x1800cee85  call    LdrpCallTlsInitializers
0x1800cee8a  nop
0x1800cee8b  xor     r9d, r9d
0x1800cee8e  xor     r8d, r8d
0x1800cee91  mov     rdx, [rbx+30h]
0x1800cee95  mov     rcx, r15
0x1800cee98  call    LdrpCallInitRoutine
0x1800cee9d  jmp     short loc_1800CEEB1
0x1800cee9f  xor     esi, esi
0x1800ceea1  mov     r14, [rsp+0B8h+arg_0]
0x1800ceea9  mov     rdi, [rsp+0B8h+arg_8]
0x1800ceeb1  lea     rcx, [rsp+0B8h+var_68]
0x1800ceeb6  call    RtlDeactivateActivationContextUnsafeFast
0x1800ceebb  mov     rdi, [rdi]
0x1800ceebe  jmp     loc_1800CED7B
0x1801681c0  push    rbp
0x1801681c2  sub     rsp, 40h
0x1801681c6  mov     rbp, rdx
0x1801681c9  mov     [rbp+48h], rcx
0x1801681cd  mov     dword ptr [rbp+40h], 0Bh
0x1801681d4  mov     rax, [rbp+48h]
0x1801681d8  mov     rdx, [rax+8]
0x1801681dc  mov     rax, [rbp+48h]
0x1801681e0  mov     rcx, [rax]
0x1801681e3  mov     r8d, [rbp+40h]
0x1801681e7  call    RtlReportException
0x1801681ec  mov     dword ptr [rbp+44h], 1
0x1801681f3  mov     eax, [rbp+44h]
0x1801681f6  add     rsp, 40h
0x1801681fa  pop     rbp
0x1801681fb  retn
0x1801681fd  push    rbp
0x1801681ff  sub     rsp, 40h
0x180168203  mov     rbp, rdx
0x180168206  lea     rcx, [rbp+50h]
0x18016820a  call    RtlDeactivateActivationContextUnsafeFast
0x18016820f  nop
0x180168210  add     rsp, 40h
0x180168214  pop     rbp
0x180168215  retn
```
