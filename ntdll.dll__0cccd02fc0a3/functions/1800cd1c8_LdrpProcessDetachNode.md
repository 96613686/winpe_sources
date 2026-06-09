# LdrpProcessDetachNode

- ea: `0x1800cd1c8`
- end: `0x1800cd333`
- name: `LdrpProcessDetachNode`
- size: `363`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18004ca78`

## callees

- `0x18001a0d0`
- `0x18001a420`
- `0x18001eb80`
- `0x180050d08`
- `0x180050fa0`
- `0x1800cd1c8`
- `0x1800cd340`
- `0x180109270`

## string_xrefs

- `0x1800cd27d`: `Uninitializing DLL "%wZ" (Init routine: %p)\n`

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
0x1800cd1c8  mov     [rsp+arg_10], rbx
0x1800cd1cd  mov     [rsp+arg_18], rsi
0x1800cd1d2  mov     [rsp+arg_0], rcx
0x1800cd1d7  push    rdi
0x1800cd1d8  push    r14
0x1800cd1da  push    r15
0x1800cd1dc  sub     rsp, 0A0h
0x1800cd1e3  mov     r14, rcx
0x1800cd1e6  mov     rdi, [rcx]
0x1800cd1e9  xor     esi, esi
0x1800cd1eb  mov     [rsp+0B8h+arg_8], rdi
0x1800cd1f3  cmp     rdi, r14
0x1800cd1f6  jz      short loc_1800CD22D
0x1800cd1f8  lea     rbx, [rdi-0A0h]
0x1800cd1ff  mov     [rbx+6Ch], si
0x1800cd203  mov     rcx, rbx
0x1800cd206  call    LdrpRecordUnloadEvent
0x1800cd20b  lea     rax, [rbx+20h]
0x1800cd20f  mov     rcx, [rax]
0x1800cd212  test    rcx, rcx
0x1800cd215  jz      short loc_1800CD255
0x1800cd217  cmp     [rcx+8], rax
0x1800cd21b  jnz     short loc_1800CD226
0x1800cd21d  mov     rdx, [rax+8]
0x1800cd221  cmp     [rdx], rax
0x1800cd224  jz      short loc_1800CD247
0x1800cd226  mov     ecx, 3
0x1800cd22b  int     29h; Win8: RtlFailFast(ecx)
0x1800cd22d  lea     r11, [rsp+0B8h+var_18]
0x1800cd235  mov     rbx, [r11+30h]
0x1800cd239  mov     rsi, [r11+38h]
0x1800cd23d  mov     rsp, r11
0x1800cd240  pop     r15
0x1800cd242  pop     r14
0x1800cd244  pop     rdi
0x1800cd245  retn
0x1800cd247  mov     [rdx], rcx
0x1800cd24a  mov     [rcx+8], rdx
0x1800cd24e  mov     qword ptr [rax], 1
0x1800cd255  mov     r15, [rbx+38h]
0x1800cd259  test    r15, r15
0x1800cd25c  jz      loc_1800CD32B
0x1800cd262  mov     eax, [rbx+68h]
0x1800cd265  bt      eax, 13h
0x1800cd269  jnb     loc_1800CD32B
0x1800cd26f  lea     rax, [rbx+48h]
0x1800cd273  mov     [rsp+0B8h+var_88], r15
0x1800cd278  mov     qword ptr [rsp+0B8h+ArgList], rax; ArgList
0x1800cd27d  lea     rax, aUninitializing; "Uninitializing DLL \"%wZ\" (Init routin"...
0x1800cd284  mov     [rsp+0B8h+Format], rax; Format
0x1800cd289  mov     r9d, 2; int
0x1800cd28f  lea     r8, aLdrpprocessdet; "LdrpProcessDetachNode"
0x1800cd296  mov     edx, 0AD1h; int
0x1800cd29b  lea     rcx, aMinkernelLdrLd_4; "minkernel\\ldr\\ldrsnap.c"
0x1800cd2a2  call    LdrpLogInternal
0x1800cd2a7  mov     [rsp+0B8h+var_68], 48h ; 'H'
0x1800cd2b0  mov     [rsp+0B8h+var_60], 1
0x1800cd2b9  xorps   xmm0, xmm0
0x1800cd2bc  xor     eax, eax
0x1800cd2be  movups  [rsp+0B8h+var_58], xmm0
0x1800cd2c3  movups  [rsp+0B8h+var_48], xmm0
0x1800cd2c8  movups  [rsp+0B8h+var_38], xmm0
0x1800cd2d0  mov     [rsp+0B8h+var_28], rax
0x1800cd2d8  mov     rdx, [rbx+88h]
0x1800cd2df  lea     rcx, [rsp+0B8h+var_68]
0x1800cd2e4  call    RtlActivateActivationContextUnsafeFast
0x1800cd2e9  nop
0x1800cd2ea  cmp     [rbx+6Eh], si
0x1800cd2ee  jz      short loc_1800CD2FB
0x1800cd2f0  mov     rdx, rbx
0x1800cd2f3  xor     ecx, ecx
0x1800cd2f5  call    LdrpCallTlsInitializers
0x1800cd2fa  nop
0x1800cd2fb  xor     r9d, r9d
0x1800cd2fe  xor     r8d, r8d
0x1800cd301  mov     rdx, [rbx+30h]
0x1800cd305  mov     rcx, r15
0x1800cd308  call    LdrpCallInitRoutine
0x1800cd30d  jmp     short loc_1800CD321
0x1800cd30f  xor     esi, esi
0x1800cd311  mov     r14, [rsp+0B8h+arg_0]
0x1800cd319  mov     rdi, [rsp+0B8h+arg_8]
0x1800cd321  lea     rcx, [rsp+0B8h+var_68]
0x1800cd326  call    RtlDeactivateActivationContextUnsafeFast
0x1800cd32b  mov     rdi, [rdi]
0x1800cd32e  jmp     loc_1800CD1EB
0x1801678e0  push    rbp
0x1801678e2  sub     rsp, 40h
0x1801678e6  mov     rbp, rdx
0x1801678e9  mov     [rbp+48h], rcx
0x1801678ed  mov     dword ptr [rbp+40h], 0Bh
0x1801678f4  mov     rax, [rbp+48h]
0x1801678f8  mov     rdx, [rax+8]
0x1801678fc  mov     rax, [rbp+48h]
0x180167900  mov     rcx, [rax]
0x180167903  mov     r8d, [rbp+40h]
0x180167907  call    RtlReportException
0x18016790c  mov     dword ptr [rbp+44h], 1
0x180167913  mov     eax, [rbp+44h]
0x180167916  add     rsp, 40h
0x18016791a  pop     rbp
0x18016791b  retn
0x18016791d  push    rbp
0x18016791f  sub     rsp, 40h
0x180167923  mov     rbp, rdx
0x180167926  lea     rcx, [rbp+50h]
0x18016792a  call    RtlDeactivateActivationContextUnsafeFast
0x18016792f  nop
0x180167930  add     rsp, 40h
0x180167934  pop     rbp
0x180167935  retn
```
