# EaDeleteAggregatedEventParametersNextChild

- ea: `0x180009130`
- end: `0x180009223`
- name: `EaDeleteAggregatedEventParametersNextChild`
- size: `243`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180009130`
- `0x180009940`

## import_xrefs

- `ntdll!ZwClose` at `0x180009206`
- `ntdll!ZwClose` at `0x180009206`
- `ntdll!ZwOpenKey` at `0x1800091e2`
- `ntdll!ZwOpenKey` at `0x1800091e2`

## pseudocode

```c
__int64 __fastcall EaDeleteAggregatedEventParametersNextChild(__int64 *a1, void *a2, __int64 a3, void **a4)
{
  int v7; // eax
  NTSTATUS v8; // ebx
  __int64 v9; // rcx
  __int128 v11; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+80h] [rbp+20h] BYREF

  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  v11 = 0;
  v7 = EapEnumerateKey(a2, 0);
  v8 = v7;
  if ( v7 == -2147483622 )
  {
    *a4 = 0;
    v8 = 0;
  }
  else if ( v7 >= 0 )
  {
    v9 = *a1;
    if ( *(_DWORD *)(*a1 + 12) <= 0xFFFFu )
    {
      *((_QWORD *)&v11 + 1) = v9 + 16;
      LOWORD(v11) = *(_WORD *)(v9 + 12);
      WORD1(v11) = v11;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&v11;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = a2;
      ObjectAttributes.Attributes = 64;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v8 = ZwOpenKey(&KeyHandle, 0xF003Fu, &ObjectAttributes);
      if ( v8 >= 0 )
      {
        *a4 = KeyHandle;
        KeyHandle = 0;
      }
    }
    else
    {
      v8 = -2147483643;
    }
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180009130  mov     [rsp-18h+arg_8], rbx
0x180009135  mov     [rsp-18h+arg_10], rsi
0x18000913a  push    rbp
0x18000913b  push    rdi
0x18000913c  push    r14
0x18000913e  mov     rbp, rsp
0x180009141  sub     rsp, 60h
0x180009145  xorps   xmm0, xmm0
0x180009148  mov     r14, rdx
0x18000914b  mov     rsi, rcx
0x18000914e  xor     eax, eax
0x180009150  mov     r8, rcx
0x180009153  mov     [rbp+KeyHandle], rax
0x180009157  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18000915b  mov     rcx, r14; KeyHandle
0x18000915e  xor     edx, edx; Index
0x180009160  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180009164  mov     rdi, r9
0x180009167  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18000916b  movups  [rbp+var_40], xmm0
0x18000916f  call    EapEnumerateKey
0x180009174  mov     ebx, eax
0x180009176  cmp     eax, 8000001Ah
0x18000917b  jnz     short loc_180009188
0x18000917d  mov     qword ptr [rdi], 0
0x180009184  xor     ebx, ebx
0x180009186  jmp     short loc_1800091FD
0x180009188  test    eax, eax
0x18000918a  js      short loc_1800091FD
0x18000918c  mov     rcx, [rsi]
0x18000918f  cmp     dword ptr [rcx+0Ch], 0FFFFh
0x180009196  jbe     short loc_18000919F
0x180009198  mov     ebx, 80000005h
0x18000919d  jmp     short loc_1800091FD
0x18000919f  lea     rax, [rcx+10h]
0x1800091a3  xorps   xmm0, xmm0
0x1800091a6  mov     qword ptr [rbp+var_40+8], rax
0x1800091aa  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800091ae  movzx   eax, word ptr [rcx+0Ch]
0x1800091b2  mov     edx, 0F003Fh; DesiredAccess
0x1800091b7  mov     word ptr [rbp+var_40], ax
0x1800091bb  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1800091bf  mov     word ptr [rbp+var_40+2], ax
0x1800091c3  lea     rax, [rbp+var_40]
0x1800091c7  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800091cb  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800091d2  mov     [rbp+ObjectAttributes.RootDirectory], r14
0x1800091d6  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1800091dd  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800091e2  call    cs:__imp_ZwOpenKey
0x1800091e8  mov     ebx, eax
0x1800091ea  test    eax, eax
0x1800091ec  js      short loc_1800091FD
0x1800091ee  mov     rax, [rbp+KeyHandle]
0x1800091f2  mov     [rdi], rax
0x1800091f5  mov     [rbp+KeyHandle], 0
0x1800091fd  mov     rcx, [rbp+KeyHandle]; Handle
0x180009201  test    rcx, rcx
0x180009204  jz      short loc_18000920C
0x180009206  call    cs:__imp_ZwClose
0x18000920c  lea     r11, [rsp+60h+var_s0]
0x180009211  mov     eax, ebx
0x180009213  mov     rbx, [r11+28h]
0x180009217  mov     rsi, [r11+30h]
0x18000921b  mov     rsp, r11
0x18000921e  pop     r14
0x180009220  pop     rdi
0x180009221  pop     rbp
0x180009222  retn
```
