# DeleteSymbolicLinkNameFromMemory

- ea: `0x140019e30`
- end: `0x140019f65`
- name: `DeleteSymbolicLinkNameFromMemory`
- size: `309`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x14000c528`
- `0x140018560`

## callees

- `0x140001ae0`
- `0x140019e30`
- `0x14001a8a0`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x140019e71`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140019e71`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019edf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019ef0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019edf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019ef0`

## pseudocode

```c
__int64 __fastcall DeleteSymbolicLinkNameFromMemory(__int64 a1, const UNICODE_STRING *a2, char a3)
{
  _QWORD *v3; // rsi
  _QWORD *v4; // r15
  char *i; // rdi
  char *v10; // rax
  void **v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // ebx
  __int64 v15; // r8

  v3 = *(_QWORD **)(a1 + 16);
  v4 = (_QWORD *)(a1 + 16);
LABEL_2:
  if ( v3 == v4 )
    return 0;
  for ( i = (char *)v3[2]; ; i = *(char **)i )
  {
    if ( i == (char *)(v3 + 2) )
    {
      v3 = (_QWORD *)*v3;
      goto LABEL_2;
    }
    if ( !RtlCompareUnicodeString(a2, (PCUNICODE_STRING)(i + 24), 1u) )
      break;
  }
  v3[22] = ++*(_QWORD *)(a1 + 336);
  if ( a3 )
  {
    i[16] = 0;
    return 0;
  }
  else
  {
    v10 = *(char **)i;
    if ( *(char **)(*(_QWORD *)i + 8LL) != i || (v11 = (void **)*((_QWORD *)i + 1), *v11 != i) )
      __fastfail(3u);
    *v11 = v10;
    *((_QWORD *)v10 + 1) = v11;
    ExFreePoolWithTag(*((PVOID *)i + 4), 0);
    ExFreePoolWithTag(i, 0);
    v14 = SendLinkDeleted(v13, v12, v3 + 8, a2);
    if ( v14 < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 221, v15, (unsigned int)v14);
    }
    return (unsigned int)v14;
  }
}

```

## disassembly

```asm
0x140019e30  push    rbx
0x140019e32  push    rbp
0x140019e33  push    rsi
0x140019e34  push    rdi
0x140019e35  push    r12
0x140019e37  push    r14
0x140019e39  push    r15
0x140019e3b  sub     rsp, 20h
0x140019e3f  mov     rsi, [rcx+10h]
0x140019e43  lea     r15, [rcx+10h]
0x140019e47  movzx   ebp, r8b
0x140019e4b  mov     r12, rdx
0x140019e4e  mov     rbx, rcx
0x140019e51  cmp     rsi, r15
0x140019e54  jz      loc_140019F53
0x140019e5a  mov     rdi, [rsi+10h]
0x140019e5e  lea     r14, [rsi+10h]
0x140019e62  cmp     rdi, r14
0x140019e65  jz      short loc_140019E86
0x140019e67  lea     rdx, [rdi+18h]; String2
0x140019e6b  mov     r8b, 1; CaseInSensitive
0x140019e6e  mov     rcx, r12; String1
0x140019e71  call    cs:__imp_RtlCompareUnicodeString
0x140019e78  nop     dword ptr [rax+rax+00h]
0x140019e7d  test    eax, eax
0x140019e7f  jz      short loc_140019E8B
0x140019e81  mov     rdi, [rdi]
0x140019e84  jmp     short loc_140019E62
0x140019e86  mov     rsi, [rsi]
0x140019e89  jmp     short loc_140019E51
0x140019e8b  inc     qword ptr [rbx+150h]
0x140019e92  mov     rax, [rbx+150h]
0x140019e99  mov     [rsi+0B0h], rax
0x140019ea0  test    bpl, bpl
0x140019ea3  jz      short loc_140019EBC
0x140019ea5  xor     ebx, ebx
0x140019ea7  mov     [rdi+10h], bl
0x140019eaa  mov     eax, ebx
0x140019eac  add     rsp, 20h
0x140019eb0  pop     r15
0x140019eb2  pop     r14
0x140019eb4  pop     r12
0x140019eb6  pop     rdi
0x140019eb7  pop     rsi
0x140019eb8  pop     rbp
0x140019eb9  pop     rbx
0x140019eba  retn
0x140019ebc  mov     rax, [rdi]
0x140019ebf  cmp     [rax+8], rdi
0x140019ec3  jnz     loc_140019F4C
0x140019ec9  mov     rcx, [rdi+8]
0x140019ecd  cmp     [rcx], rdi
0x140019ed0  jnz     short loc_140019F4C
0x140019ed2  mov     [rcx], rax
0x140019ed5  xor     edx, edx; Tag
0x140019ed7  mov     [rax+8], rcx
0x140019edb  mov     rcx, [rdi+20h]; P
0x140019edf  call    cs:__imp_ExFreePoolWithTag
0x140019ee6  nop     dword ptr [rax+rax+00h]
0x140019eeb  xor     edx, edx; Tag
0x140019eed  mov     rcx, rdi; P
0x140019ef0  call    cs:__imp_ExFreePoolWithTag
0x140019ef7  nop     dword ptr [rax+rax+00h]
0x140019efc  lea     r8, [rsi+40h]
0x140019f00  mov     r9, r12
0x140019f03  call    SendLinkDeleted
0x140019f08  mov     ebx, eax
0x140019f0a  test    eax, eax
0x140019f0c  jns     short loc_140019F3A
0x140019f0e  mov     rcx, cs:WPP_GLOBAL_Control
0x140019f15  lea     rax, WPP_GLOBAL_Control
0x140019f1c  cmp     rcx, rax
0x140019f1f  jz      short loc_140019F3A
0x140019f21  mov     edx, [rcx+2Ch]
0x140019f24  test    dl, 1
0x140019f27  jz      short loc_140019F3A
0x140019f29  mov     rcx, [rcx+18h]
0x140019f2d  mov     edx, 0DDh
0x140019f32  mov     r9d, ebx
0x140019f35  call    WPP_SF_L
0x140019f3a  mov     eax, ebx
0x140019f3c  add     rsp, 20h
0x140019f40  pop     r15
0x140019f42  pop     r14
0x140019f44  pop     r12
0x140019f46  pop     rdi
0x140019f47  pop     rsi
0x140019f48  pop     rbp
0x140019f49  pop     rbx
0x140019f4a  retn
0x140019f4c  mov     ecx, 3
0x140019f51  int     29h; Win8: RtlFailFast(ecx)
0x140019f53  xor     eax, eax
0x140019f55  add     rsp, 20h
0x140019f59  pop     r15
0x140019f5b  pop     r14
0x140019f5d  pop     r12
0x140019f5f  pop     rdi
0x140019f60  pop     rsi
0x140019f61  pop     rbp
0x140019f62  pop     rbx
0x140019f63  retn
```
