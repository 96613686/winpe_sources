# DfscInitDfsPath

- ea: `0x14001ef20`
- end: `0x14001f038`
- name: `DfscInitDfsPath`
- size: `280`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct _UNICODE_STRING *)`
- caller_count: `10`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140001df8`
- `0x140001f4c`
- `0x1400051d0`
- `0x140011494`
- `0x140016070`
- `0x140017798`
- `0x14001935c`
- `0x140022cd8`
- `0x14002774c`
- `0x140029160`

## callees

- `0x140002aa0`
- `0x14001ef20`
- `0x14001f540`

## pseudocode

```c
__int64 __fastcall DfscInitDfsPath(unsigned __int16 *a1, struct _UNICODE_STRING *a2)
{
  struct _UNICODE_STRING *v3; // rsi
  int PathComponents; // r9d
  PWSTR Buffer; // rcx
  char v7; // r10
  unsigned int Length; // r8d
  __int64 v9; // rax
  unsigned int v10; // r8d

  v3 = a2 + 2;
  a2[5] = *(struct _UNICODE_STRING *)a1;
  PathComponents = DfscGetPathComponents((__int16 *)&a2[5], a2, a2 + 1, a2 + 3, a2 + 2);
  if ( PathComponents >= 0 && a2 && a2->Length && (Buffer = a2->Buffer) != 0 && *Buffer )
  {
    if ( !v3->Length )
      goto LABEL_13;
    v7 = 0;
    Length = a2[3].Length;
    a2[4].Buffer = (PWSTR)*((_QWORD *)a1 + 1);
    v9 = (*a1 >> 1) - 1;
    v10 = Length >> 1;
    if ( (unsigned int)v9 < v10 )
      goto LABEL_13;
    do
    {
      if ( *(_WORD *)(2 * v9 + *((_QWORD *)a1 + 1)) == 58 )
      {
        v7 = 1;
        a2[4].MaximumLength = 2 * v9;
        a2[4].Length = 2 * v9;
      }
      if ( *(_WORD *)(2 * v9 + *((_QWORD *)a1 + 1)) == 92 )
        break;
      v9 = (unsigned int)(v9 - 1);
    }
    while ( (unsigned int)v9 >= v10 );
    if ( !v7 )
LABEL_13:
      a2[4] = *(struct _UNICODE_STRING *)a1;
    return (unsigned int)PathComponents;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
    {
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_1bce9a35ce9f35cd7964d25412ee5844_Traceguids, a1);
    }
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x14001ef20  push    rbx
0x14001ef22  push    rbp
0x14001ef23  push    rsi
0x14001ef24  push    rdi
0x14001ef25  sub     rsp, 38h
0x14001ef29  mov     rbx, rcx
0x14001ef2c  lea     rsi, [rdx+20h]
0x14001ef30  lea     rcx, [rdx+50h]
0x14001ef34  mov     [rsp+58h+var_38], rsi
0x14001ef39  lea     r8, [rdx+10h]
0x14001ef3d  mov     rdi, rdx
0x14001ef40  lea     r9, [rdx+30h]
0x14001ef44  movups  xmm0, xmmword ptr [rbx]
0x14001ef47  movups  xmmword ptr [rcx], xmm0
0x14001ef4a  call    DfscGetPathComponents
0x14001ef4f  mov     r9d, eax
0x14001ef52  test    eax, eax
0x14001ef54  js      loc_14001EFFD
0x14001ef5a  test    rdi, rdi
0x14001ef5d  jz      loc_14001EFFD
0x14001ef63  cmp     word ptr [rdi], 0
0x14001ef67  jz      loc_14001EFFD
0x14001ef6d  mov     rcx, [rdi+8]
0x14001ef71  test    rcx, rcx
0x14001ef74  jz      loc_14001EFFD
0x14001ef7a  cmp     word ptr [rcx], 0
0x14001ef7e  jz      short loc_14001EFFD
0x14001ef80  cmp     word ptr [rsi], 0
0x14001ef84  jz      short loc_14001EFD6
0x14001ef86  mov     rax, [rbx+8]
0x14001ef8a  xor     r10b, r10b
0x14001ef8d  movzx   r8d, word ptr [rdi+30h]
0x14001ef92  mov     [rdi+48h], rax
0x14001ef96  movzx   eax, word ptr [rbx]
0x14001ef99  shr     eax, 1
0x14001ef9b  dec     eax
0x14001ef9d  shr     r8d, 1
0x14001efa0  cmp     eax, r8d
0x14001efa3  jb      short loc_14001EFD6
0x14001efa5  nop     word ptr [rax+rax+00000000h]
0x14001efb0  mov     rcx, [rbx+8]
0x14001efb4  lea     rdx, [rax+rax]
0x14001efb8  cmp     word ptr [rdx+rcx], 3Ah ; ':'
0x14001efbd  jz      short loc_14001EFEA
0x14001efbf  mov     rcx, [rbx+8]
0x14001efc3  cmp     word ptr [rdx+rcx], 5Ch ; '\'
0x14001efc8  jz      short loc_14001EFD1
0x14001efca  dec     eax
0x14001efcc  cmp     eax, r8d
0x14001efcf  jnb     short loc_14001EFB0
0x14001efd1  test    r10b, r10b
0x14001efd4  jnz     short loc_14001EFDD
0x14001efd6  movups  xmm0, xmmword ptr [rbx]
0x14001efd9  movups  xmmword ptr [rdi+40h], xmm0
0x14001efdd  mov     eax, r9d
0x14001efe0  add     rsp, 38h
0x14001efe4  pop     rdi
0x14001efe5  pop     rsi
0x14001efe6  pop     rbp
0x14001efe7  pop     rbx
0x14001efe8  retn
0x14001efea  movzx   ecx, ax
0x14001efed  mov     r10b, 1
0x14001eff0  add     cx, cx
0x14001eff3  mov     [rdi+42h], cx
0x14001eff7  mov     [rdi+40h], cx
0x14001effb  jmp     short loc_14001EFBF
0x14001effd  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f004  lea     rax, WPP_GLOBAL_Control
0x14001f00b  cmp     rcx, rax
0x14001f00e  jz      short loc_14001F031
0x14001f010  test    dword ptr [rcx+2Ch], 100000h
0x14001f017  jz      short loc_14001F031
0x14001f019  mov     rcx, [rcx+18h]
0x14001f01d  lea     r8, WPP_1bce9a35ce9f35cd7964d25412ee5844_Traceguids
0x14001f024  mov     edx, 0Ah
0x14001f029  mov     r9, rbx
0x14001f02c  call    WPP_SF_Z
0x14001f031  mov     eax, 0C000000Dh
0x14001f036  jmp     short loc_14001EFE0
```
