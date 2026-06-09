# DfsGetPathComponents

- ea: `0x1400583f4`
- end: `0x140058586`
- name: `DfsGetPathComponents`
- size: `402`
- prototype: ``
- caller_count: `13`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000a9e0`
- `0x14000e39c`
- `0x140010f9c`
- `0x140012224`
- `0x14001b020`
- `0x14001bc08`
- `0x14001be88`
- `0x14001c664`
- `0x14001cafc`
- `0x14001cbd8`
- `0x14001d384`
- `0x14004079c`
- `0x1400476b0`

## callees

- `0x1400583f4`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x140058427`
- `ntdll!RtlInitUnicodeString` at `0x14005843d`
- `ntdll!RtlInitUnicodeString` at `0x140058453`
- `ntdll!RtlInitUnicodeString` at `0x140058427`
- `ntdll!RtlInitUnicodeString` at `0x14005843d`
- `ntdll!RtlInitUnicodeString` at `0x140058453`

## pseudocode

```c
void __fastcall DfsGetPathComponents(
        __int64 a1,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4)
{
  unsigned __int16 v8; // bx
  unsigned __int16 v9; // cx
  unsigned __int16 i; // r8
  USHORT v11; // ax
  unsigned __int16 v12; // r8
  unsigned __int16 v13; // cx
  unsigned __int16 j; // dx
  USHORT v15; // ax
  unsigned __int16 v16; // dx
  unsigned __int16 v17; // r8
  __int64 v18; // rax
  USHORT v19; // r8

  v8 = 0;
  if ( a2 )
    RtlInitUnicodeString(a2, 0);
  if ( a3 )
    RtlInitUnicodeString(a3, 0);
  if ( a4 )
    RtlInitUnicodeString(a4, 0);
  v9 = *(_WORD *)a1 >> 1;
  if ( v9 )
  {
    do
    {
      if ( *(_WORD *)(*(_QWORD *)(a1 + 8) + 2LL * v8) != 92 )
        break;
      if ( v8 >= 2u )
        break;
      ++v8;
    }
    while ( v8 < v9 );
  }
  for ( i = v8; i < v9; ++i )
  {
    if ( *(_WORD *)(*(_QWORD *)(a1 + 8) + 2LL * i) == 92 )
      break;
  }
  if ( a2 && i > v8 )
  {
    a2->Buffer = (PWSTR)(*(_QWORD *)(a1 + 8) + 2LL * v8);
    v11 = 2 * (i - v8);
    a2->Length = v11;
    a2->MaximumLength = v11;
  }
  v12 = i + 1;
  v13 = *(_WORD *)a1 >> 1;
  for ( j = v12; j < v13; ++j )
  {
    if ( *(_WORD *)(*(_QWORD *)(a1 + 8) + 2LL * j) == 92 )
      break;
  }
  if ( a3 && j > v12 )
  {
    a3->Buffer = (PWSTR)(*(_QWORD *)(a1 + 8) + 2LL * v12);
    v15 = 2 * (j - v12);
    a3->Length = v15;
    a3->MaximumLength = v15;
  }
  v16 = j + 1;
  v17 = *(_WORD *)a1 >> 1;
  if ( a4 )
  {
    if ( v17 > v16 )
    {
      v18 = *(_QWORD *)(a1 + 8);
      v19 = 2 * (v17 - v16);
      a4->Length = v19;
      a4->MaximumLength = v19;
      a4->Buffer = (PWSTR)(v18 + 2LL * v16);
    }
  }
}

```

## disassembly

```asm
0x1400583f4  mov     [rsp+arg_0], rbx
0x1400583f9  mov     [rsp+arg_8], rbp
0x1400583fe  mov     [rsp+arg_10], rsi
0x140058403  push    rdi
0x140058404  push    r14
0x140058406  push    r15
0x140058408  sub     rsp, 20h
0x14005840c  xor     ebp, ebp
0x14005840e  mov     rsi, r9
0x140058411  mov     r14, r8
0x140058414  mov     r15, rdx
0x140058417  mov     rdi, rcx
0x14005841a  movzx   ebx, bp
0x14005841d  test    rdx, rdx
0x140058420  jz      short loc_140058433
0x140058422  xor     edx, edx; SourceString
0x140058424  mov     rcx, r15; DestinationString
0x140058427  call    cs:__imp_RtlInitUnicodeString
0x14005842e  nop     dword ptr [rax+rax+00h]
0x140058433  test    r14, r14
0x140058436  jz      short loc_140058449
0x140058438  xor     edx, edx; SourceString
0x14005843a  mov     rcx, r14; DestinationString
0x14005843d  call    cs:__imp_RtlInitUnicodeString
0x140058444  nop     dword ptr [rax+rax+00h]
0x140058449  test    rsi, rsi
0x14005844c  jz      short loc_14005845F
0x14005844e  xor     edx, edx; SourceString
0x140058450  mov     rcx, rsi; DestinationString
0x140058453  call    cs:__imp_RtlInitUnicodeString
0x14005845a  nop     dword ptr [rax+rax+00h]
0x14005845f  movzx   ecx, word ptr [rdi]
0x140058462  mov     r10w, 1
0x140058467  shr     cx, 1
0x14005846a  cmp     bp, cx
0x14005846d  jnb     short loc_14005848C
0x14005846f  mov     rdx, [rdi+8]
0x140058473  movzx   eax, bx
0x140058476  cmp     word ptr [rdx+rax*2], 5Ch ; '\'
0x14005847b  jnz     short loc_14005848C
0x14005847d  cmp     bx, 2
0x140058481  jnb     short loc_14005848C
0x140058483  add     bx, r10w
0x140058487  cmp     bx, cx
0x14005848a  jb      short loc_140058473
0x14005848c  movzx   r8d, bx
0x140058490  cmp     bx, cx
0x140058493  jnb     short loc_1400584AE
0x140058495  mov     rdx, [rdi+8]
0x140058499  movzx   eax, r8w
0x14005849d  cmp     word ptr [rdx+rax*2], 5Ch ; '\'
0x1400584a2  jz      short loc_1400584AE
0x1400584a4  add     r8w, r10w
0x1400584a8  cmp     r8w, cx
0x1400584ac  jb      short loc_140058499
0x1400584ae  test    r15, r15
0x1400584b1  jz      short loc_1400584DB
0x1400584b3  cmp     r8w, bx
0x1400584b7  jbe     short loc_1400584DB
0x1400584b9  mov     rax, [rdi+8]
0x1400584bd  movzx   ecx, bx
0x1400584c0  lea     rcx, [rax+rcx*2]
0x1400584c4  movzx   eax, r8w
0x1400584c8  sub     ax, bx
0x1400584cb  mov     [r15+8], rcx
0x1400584cf  add     ax, ax
0x1400584d2  mov     [r15], ax
0x1400584d6  mov     [r15+2], ax
0x1400584db  movzx   ecx, word ptr [rdi]
0x1400584de  add     r8w, r10w
0x1400584e2  shr     cx, 1
0x1400584e5  movzx   edx, r8w
0x1400584e9  cmp     r8w, cx
0x1400584ed  jnb     short loc_140058507
0x1400584ef  mov     r9, [rdi+8]
0x1400584f3  movzx   eax, dx
0x1400584f6  cmp     word ptr [r9+rax*2], 5Ch ; '\'
0x1400584fc  jz      short loc_140058507
0x1400584fe  add     dx, r10w
0x140058502  cmp     dx, cx
0x140058505  jb      short loc_1400584F3
0x140058507  test    r14, r14
0x14005850a  jz      short loc_140058535
0x14005850c  cmp     dx, r8w
0x140058510  jbe     short loc_140058535
0x140058512  mov     rax, [rdi+8]
0x140058516  movzx   ecx, r8w
0x14005851a  lea     rcx, [rax+rcx*2]
0x14005851e  movzx   eax, dx
0x140058521  sub     ax, r8w
0x140058525  mov     [r14+8], rcx
0x140058529  add     ax, ax
0x14005852c  mov     [r14], ax
0x140058530  mov     [r14+2], ax
0x140058535  movzx   r8d, word ptr [rdi]
0x140058539  add     dx, r10w
0x14005853d  shr     r8w, 1
0x140058541  test    rsi, rsi
0x140058544  jz      short loc_14005856C
0x140058546  cmp     r8w, dx
0x14005854a  jbe     short loc_14005856C
0x14005854c  mov     rax, [rdi+8]
0x140058550  sub     r8w, dx
0x140058554  add     r8w, r8w
0x140058558  movzx   ecx, dx
0x14005855b  mov     [rsi], r8w
0x14005855f  mov     [rsi+2], r8w
0x140058564  lea     rcx, [rax+rcx*2]
0x140058568  mov     [rsi+8], rcx
0x14005856c  mov     rbx, [rsp+38h+arg_0]
0x140058571  mov     rbp, [rsp+38h+arg_8]
0x140058576  mov     rsi, [rsp+38h+arg_10]
0x14005857b  add     rsp, 20h
0x14005857f  pop     r15
0x140058581  pop     r14
0x140058583  pop     rdi
0x140058584  retn
```
