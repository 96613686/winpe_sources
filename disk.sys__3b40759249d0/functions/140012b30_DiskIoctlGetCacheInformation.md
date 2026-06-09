# DiskIoctlGetCacheInformation

- ea: `0x140012b30`
- end: `0x140012c98`
- name: `DiskIoctlGetCacheInformation`
- size: `360`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400014a0`

## callees

- `0x140004078`
- `0x14000431c`
- `0x140012b30`
- `0x140012ca0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140012b57`
- `ntoskrnl!KeGetCurrentIrql` at `0x140012b57`

## pseudocode

```c
__int64 __fastcall DiskIoctlGetCacheInformation(__int64 a1, _QWORD *a2)
{
  __int64 v2; // rbx
  __int64 v4; // r14
  __int64 v6; // rbp
  int CacheInformation; // edx

  v2 = *(_QWORD *)(a1 + 64);
  v4 = a2[23];
  v6 = a2[3];
  if ( KeGetCurrentIrql() >= 2u )
    return 3221225800LL;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 59, WPP_0d021951613e35be7880fae860fb7f50_Traceguids, a1, a2);
  }
  if ( *(_DWORD *)(v4 + 8) < 0x18u )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 60, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
    }
    return 3221225507LL;
  }
  else
  {
    CacheInformation = DiskGetCacheInformation(v2, v6);
    if ( CacheInformation >= 0 )
    {
      a2[7] = 24;
      if ( *(_BYTE *)(v6 + 2) )
        *(_WORD *)(v2 + 640) |= 1u;
      else
        *(_WORD *)(v2 + 640) &= ~1u;
      *(_BYTE *)(v2 + 643) = (*(_WORD *)(v2 + 640) & 1) != 0
                          && (*(_WORD *)(v2 + 640) & 0x10) == 0
                          && (*(_DWORD *)(v2 + 876) & 0x80u) == 0;
    }
    return (unsigned int)CacheInformation;
  }
}

```

## disassembly

```asm
0x140012b30  mov     [rsp+arg_8], rbx
0x140012b35  mov     [rsp+arg_10], rbp
0x140012b3a  push    rsi
0x140012b3b  push    rdi
0x140012b3c  push    r14
0x140012b3e  sub     rsp, 30h
0x140012b42  mov     rbx, [rcx+40h]
0x140012b46  mov     rdi, rdx
0x140012b49  mov     r14, [rdx+0B8h]
0x140012b50  mov     rsi, rcx
0x140012b53  mov     rbp, [rdx+18h]
0x140012b57  call    cs:__imp_KeGetCurrentIrql
0x140012b5e  nop     dword ptr [rax+rax+00h]
0x140012b63  cmp     al, 2
0x140012b65  jnb     loc_140012C0C
0x140012b6b  mov     rcx, cs:WPP_GLOBAL_Control
0x140012b72  mov     [rsp+48h+arg_0], r15
0x140012b77  lea     r15, WPP_GLOBAL_Control
0x140012b7e  cmp     rcx, r15
0x140012b81  jz      short loc_140012B8E
0x140012b83  mov     eax, [rcx+2Ch]
0x140012b86  test    al, 10h
0x140012b88  jnz     loc_140012C34
0x140012b8e  cmp     dword ptr [r14+8], 18h
0x140012b93  jb      loc_140012C60
0x140012b99  mov     rdx, rbp
0x140012b9c  mov     rcx, rbx
0x140012b9f  call    DiskGetCacheInformation
0x140012ba4  mov     edx, eax
0x140012ba6  test    eax, eax
0x140012ba8  js      short loc_140012BF1
0x140012baa  mov     qword ptr [rdi+38h], 18h
0x140012bb2  cmp     byte ptr [rbp+2], 0
0x140012bb6  jz      short loc_140012C1C
0x140012bb8  movzx   ecx, word ptr [rbx+280h]
0x140012bbf  or      cx, 1
0x140012bc3  mov     [rbx+280h], cx
0x140012bca  movzx   eax, word ptr [rbx+280h]
0x140012bd1  test    al, 1
0x140012bd3  jz      short loc_140012C13
0x140012bd5  movzx   eax, word ptr [rbx+280h]
0x140012bdc  test    al, 10h
0x140012bde  jnz     short loc_140012C13
0x140012be0  mov     eax, [rbx+36Ch]
0x140012be6  test    al, al
0x140012be8  js      short loc_140012C13
0x140012bea  mov     byte ptr [rbx+283h], 1
0x140012bf1  mov     eax, edx
0x140012bf3  mov     r15, [rsp+48h+arg_0]
0x140012bf8  mov     rbx, [rsp+48h+arg_8]
0x140012bfd  mov     rbp, [rsp+48h+arg_10]
0x140012c02  add     rsp, 30h
0x140012c06  pop     r14
0x140012c08  pop     rdi
0x140012c09  pop     rsi
0x140012c0a  retn
0x140012c0c  mov     eax, 0C0000148h
0x140012c11  jmp     short loc_140012BF8
0x140012c13  mov     byte ptr [rbx+283h], 0
0x140012c1a  jmp     short loc_140012BF1
0x140012c1c  movzx   eax, word ptr [rbx+280h]
0x140012c23  mov     ecx, 0FFFEh
0x140012c28  and     ax, cx
0x140012c2b  mov     [rbx+280h], ax
0x140012c32  jmp     short loc_140012BCA
0x140012c34  cmp     byte ptr [rcx+29h], 4
0x140012c38  jb      loc_140012B8E
0x140012c3e  mov     rcx, [rcx+18h]
0x140012c42  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x140012c49  mov     edx, 3Bh ; ';'
0x140012c4e  mov     [rsp+48h+var_28], rdi
0x140012c53  mov     r9, rsi
0x140012c56  call    WPP_SF_qq
0x140012c5b  jmp     loc_140012B8E
0x140012c60  mov     rcx, cs:WPP_GLOBAL_Control
0x140012c67  cmp     rcx, r15
0x140012c6a  jz      short loc_140012C8E
0x140012c6c  mov     eax, [rcx+2Ch]
0x140012c6f  test    al, 10h
0x140012c71  jz      short loc_140012C8E
0x140012c73  cmp     byte ptr [rcx+29h], 2
0x140012c77  jb      short loc_140012C8E
0x140012c79  mov     rcx, [rcx+18h]
0x140012c7d  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x140012c84  mov     edx, 3Ch ; '<'
0x140012c89  call    WPP_SF_
0x140012c8e  mov     eax, 0C0000023h
0x140012c93  jmp     loc_140012BF3
```
