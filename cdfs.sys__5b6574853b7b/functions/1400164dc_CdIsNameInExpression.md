# CdIsNameInExpression

- ea: `0x1400164dc`
- end: `0x1400165a0`
- name: `CdIsNameInExpression`
- size: `196`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140010f68`
- `0x1400120cc`
- `0x140012198`
- `0x14001233c`
- `0x1400166ac`

## callees

- `0x140002ee0`
- `0x1400164dc`

## import_xrefs

- `ntoskrnl!FsRtlIsNameInExpression` at `0x140016500`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x140016561`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x140016500`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x140016561`

## pseudocode

```c
BOOLEAN __fastcall CdIsNameInExpression(
        __int64 a1,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3,
        int a4,
        char a5)
{
  BOOLEAN IsNameInExpression; // di
  USHORT Length; // ax
  struct _UNICODE_STRING *v10; // rdx

  if ( (a4 & 0x10000) != 0 )
  {
    IsNameInExpression = FsRtlIsNameInExpression(a3, a2, 0, 0);
    if ( !IsNameInExpression )
      return IsNameInExpression;
  }
  else
  {
    if ( a2->Length != a3->Length )
      return 0;
    IsNameInExpression = 1;
    if ( memcmp(a2->Buffer, a3->Buffer, a2->Length) )
      return 0;
  }
  if ( a5 )
  {
    Length = a3[1].Length;
    if ( Length )
    {
      if ( (a4 & 0x80000) == 0 )
      {
        v10 = a2 + 1;
        if ( (a4 & 0x20000) != 0 )
          return FsRtlIsNameInExpression(a3 + 1, v10, 0, 0);
        if ( v10->Length != Length || memcmp(a2[1].Buffer, a3[1].Buffer, v10->Length) )
          return 0;
      }
    }
  }
  return IsNameInExpression;
}

```

## disassembly

```asm
0x1400164dc  push    rbx
0x1400164de  push    rbp
0x1400164df  push    rsi
0x1400164e0  push    rdi
0x1400164e1  push    r14
0x1400164e3  sub     rsp, 20h
0x1400164e7  mov     ebp, r9d
0x1400164ea  mov     rsi, r8
0x1400164ed  mov     r14, rdx
0x1400164f0  bt      r9d, 10h
0x1400164f5  jnb     short loc_140016517
0x1400164f7  xor     r9d, r9d; UpcaseTable
0x1400164fa  xor     r8d, r8d; IgnoreCase
0x1400164fd  mov     rcx, rsi; Expression
0x140016500  call    cs:__imp_FsRtlIsNameInExpression
0x140016507  nop     dword ptr [rax+rax+00h]
0x14001650c  xor     ebx, ebx
0x14001650e  mov     dil, al
0x140016511  test    al, al
0x140016513  jz      short loc_140016591
0x140016515  jmp     short loc_140016539
0x140016517  movzx   eax, word ptr [rdx]
0x14001651a  xor     ebx, ebx
0x14001651c  cmp     ax, [r8]
0x140016520  jnz     short loc_14001658E
0x140016522  mov     rdx, [rsi+8]; Buf2
0x140016526  mov     r8d, eax; Size
0x140016529  mov     rcx, [r14+8]; Buf1
0x14001652d  mov     dil, 1
0x140016530  call    memcmp
0x140016535  test    eax, eax
0x140016537  jnz     short loc_14001658E
0x140016539  cmp     [rsp+48h+arg_20], bl
0x14001653d  jz      short loc_140016591
0x14001653f  lea     rcx, [rsi+10h]; Expression
0x140016543  movzx   eax, word ptr [rcx]
0x140016546  test    ax, ax
0x140016549  jz      short loc_140016591
0x14001654b  bt      ebp, 13h
0x14001654f  jb      short loc_140016591
0x140016551  lea     rdx, [r14+10h]; Name
0x140016555  bt      ebp, 11h
0x140016559  jnb     short loc_140016572
0x14001655b  xor     r9d, r9d; UpcaseTable
0x14001655e  xor     r8d, r8d; IgnoreCase
0x140016561  call    cs:__imp_FsRtlIsNameInExpression
0x140016568  nop     dword ptr [rax+rax+00h]
0x14001656d  mov     dil, al
0x140016570  jmp     short loc_140016591
0x140016572  movzx   ecx, word ptr [rdx]
0x140016575  cmp     cx, ax
0x140016578  jnz     short loc_14001658E
0x14001657a  mov     rdx, [rsi+18h]; Buf2
0x14001657e  mov     r8d, ecx; Size
0x140016581  mov     rcx, [r14+18h]; Buf1
0x140016585  call    memcmp
0x14001658a  test    eax, eax
0x14001658c  jz      short loc_140016591
0x14001658e  mov     dil, bl
0x140016591  mov     al, dil
0x140016594  add     rsp, 20h
0x140016598  pop     r14
0x14001659a  pop     rdi
0x14001659b  pop     rsi
0x14001659c  pop     rbp
0x14001659d  pop     rbx
0x14001659e  retn
```
