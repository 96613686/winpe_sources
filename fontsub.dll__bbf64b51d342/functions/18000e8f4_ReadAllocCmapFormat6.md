# ReadAllocCmapFormat6

- ea: `0x18000e8f4`
- end: `0x18000e9df`
- name: `ReadAllocCmapFormat6`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800143f0`

## callees

- `0x18000db8c`
- `0x18000e8f4`
- `0x180011538`
- `0x180011574`
- `0x18001a3bc`
- `0x18001a578`

## pseudocode

```c
__int64 __fastcall ReadAllocCmapFormat6(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _WORD *a5, __int64 *a6)
{
  unsigned int CmapSubtable; // ebp
  __int64 result; // rax
  __int64 v9; // rdx
  unsigned __int16 GenericRepeat; // di
  _WORD v11[2]; // [rsp+40h] [rbp-38h] BYREF
  _DWORD v12[13]; // [rsp+44h] [rbp-34h] BYREF

  v11[0] = 0;
  v12[0] = 0;
  CmapSubtable = FindCmapSubtable();
  if ( !CmapSubtable )
    return 1006;
  result = ReadGeneric(a1, (__int64)a5, 0xAu, (unsigned __int8 *)&CMAP_FORMAT6_CONTROL, CmapSubtable, v11);
  if ( (_WORD)result )
    return result;
  if ( *a5 != 6 )
    return 1006;
  v9 = Mem_Alloc(2LL * (unsigned __int16)a5[4]);
  *a6 = v9;
  if ( !v9 )
    return 1005;
  GenericRepeat = ReadGenericRepeat(a1, v9, (unsigned __int8 *)&WORD_CONTROL, CmapSubtable + v11[0], v12, a5[4], 2u);
  if ( !GenericRepeat )
    return 0;
  Mem_Free(*a6);
  result = GenericRepeat;
  *a6 = 0;
  return result;
}

```

## disassembly

```asm
0x18000e8f4  push    rbx
0x18000e8f6  push    rbp
0x18000e8f7  push    rsi
0x18000e8f8  push    rdi
0x18000e8f9  push    r14
0x18000e8fb  sub     rsp, 50h
0x18000e8ff  xor     r14d, r14d
0x18000e902  mov     rsi, rcx
0x18000e905  mov     [rsp+78h+var_38], r14w
0x18000e90b  mov     [rsp+78h+var_34], r14d
0x18000e910  call    FindCmapSubtable
0x18000e915  mov     ebp, eax
0x18000e917  test    eax, eax
0x18000e919  jz      loc_18000E9CF
0x18000e91f  mov     rdi, [rsp+78h+arg_20]
0x18000e927  lea     rax, [rsp+78h+var_38]
0x18000e92c  mov     [rsp+78h+var_50], rax
0x18000e931  lea     r8d, [r14+0Ah]
0x18000e935  mov     rdx, rdi
0x18000e938  mov     dword ptr [rsp+78h+var_58], ebp
0x18000e93c  lea     r9, CMAP_FORMAT6_CONTROL
0x18000e943  mov     rcx, rsi
0x18000e946  call    ReadGeneric
0x18000e94b  test    ax, ax
0x18000e94e  jnz     loc_18000E9D4
0x18000e954  cmp     word ptr [rdi], 6
0x18000e958  jnz     short loc_18000E9CF
0x18000e95a  movzx   ecx, word ptr [rdi+8]
0x18000e95e  add     rcx, rcx; Size
0x18000e961  call    Mem_Alloc
0x18000e966  mov     rbx, [rsp+78h+arg_28]
0x18000e96e  mov     rdx, rax
0x18000e971  mov     [rbx], rax
0x18000e974  test    rax, rax
0x18000e977  jnz     short loc_18000E980
0x18000e979  mov     eax, 3EDh
0x18000e97e  jmp     short loc_18000E9D4
0x18000e980  movzx   eax, word ptr [rdi+8]
0x18000e984  lea     r8, WORD_CONTROL
0x18000e98b  movzx   r9d, [rsp+78h+var_38]
0x18000e991  mov     rcx, rsi
0x18000e994  mov     [rsp+78h+var_48], 2
0x18000e99b  add     r9d, ebp
0x18000e99e  mov     word ptr [rsp+78h+var_50], ax
0x18000e9a3  lea     rax, [rsp+78h+var_34]
0x18000e9a8  mov     [rsp+78h+var_58], rax
0x18000e9ad  call    ReadGenericRepeat
0x18000e9b2  movzx   edi, ax
0x18000e9b5  test    ax, ax
0x18000e9b8  jz      short loc_18000E9CA
0x18000e9ba  mov     rcx, [rbx]
0x18000e9bd  call    Mem_Free
0x18000e9c2  movzx   eax, di
0x18000e9c5  mov     [rbx], r14
0x18000e9c8  jmp     short loc_18000E9D4
0x18000e9ca  mov     eax, r14d
0x18000e9cd  jmp     short loc_18000E9D4
0x18000e9cf  mov     eax, 3EEh
0x18000e9d4  add     rsp, 50h
0x18000e9d8  pop     r14
0x18000e9da  pop     rdi
0x18000e9db  pop     rsi
0x18000e9dc  pop     rbp
0x18000e9dd  pop     rbx
0x18000e9de  retn
```
