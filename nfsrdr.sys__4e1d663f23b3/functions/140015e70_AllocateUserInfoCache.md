# AllocateUserInfoCache

- ea: `0x140015e70`
- end: `0x140015f7b`
- name: `AllocateUserInfoCache`
- size: `267`
- prototype: `unsigned int *__fastcall(_QWORD *, const void **, const void **, const void **, int, __int64, _OWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14001643c`

## callees

- `0x1400159cc`
- `0x140015b48`
- `0x140015e70`
- `0x1400173f8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140015edb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015edb`
- `ntoskrnl!ExAllocatePool2` at `0x140015e97`
- `ntoskrnl!ExAllocatePool2` at `0x140015e97`

## pseudocode

```c
unsigned int *__fastcall AllocateUserInfoCache(
        _QWORD *a1,
        const void **a2,
        const void **a3,
        const void **a4,
        int a5,
        __int64 a6,
        _OWORD *a7)
{
  unsigned int *Pool2; // rbx
  void *UserCredential; // rdi
  int v14; // [rsp+20h] [rbp-48h]

  Pool2 = (unsigned int *)ExAllocatePool2(258, 24, 1129473614);
  if ( !Pool2 )
  {
LABEL_4:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_6e2ab52aad8b3bbfdaad4cd7cd77f43e_Traceguids);
    return Pool2;
  }
  UserCredential = AllocateUserCredential(a2, a3, a4, a5, v14, a7);
  if ( !UserCredential )
  {
    ExFreePoolWithTag(Pool2, 0);
    Pool2 = 0;
    goto LABEL_4;
  }
  *(_OWORD *)Pool2 = 0;
  *((_QWORD *)Pool2 + 2) = 0;
  *(_QWORD *)Pool2 = *a1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
    WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_6e2ab52aad8b3bbfdaad4cd7cd77f43e_Traceguids, *Pool2, Pool2[1]);
  *((_QWORD *)Pool2 + 1) = UserCredential;
  return Pool2;
}

```

## disassembly

```asm
0x140015e70  push    rbx
0x140015e72  push    rbp
0x140015e73  push    rsi
0x140015e74  push    rdi
0x140015e75  push    r14
0x140015e77  sub     rsp, 40h
0x140015e7b  mov     rbp, r8
0x140015e7e  mov     r14, rdx
0x140015e81  mov     rsi, rcx
0x140015e84  mov     edx, 18h
0x140015e89  mov     ecx, 102h
0x140015e8e  mov     r8d, 4352664Eh
0x140015e94  mov     rdi, r9
0x140015e97  call    cs:__imp_ExAllocatePool2
0x140015e9e  nop     dword ptr [rax+rax+00h]
0x140015ea3  mov     rbx, rax
0x140015ea6  test    rax, rax
0x140015ea9  jz      short loc_140015EE9
0x140015eab  mov     rax, [rsp+68h+arg_30]
0x140015eb3  mov     r8, rdi
0x140015eb6  mov     r9d, [rsp+68h+arg_20]
0x140015ebe  mov     rdx, rbp
0x140015ec1  mov     rcx, r14
0x140015ec4  mov     [rsp+68h+var_40], rax
0x140015ec9  call    AllocateUserCredential
0x140015ece  mov     rdi, rax
0x140015ed1  test    rax, rax
0x140015ed4  jnz     short loc_140015F28
0x140015ed6  xor     edx, edx; Tag
0x140015ed8  mov     rcx, rbx; P
0x140015edb  call    cs:__imp_ExFreePoolWithTag
0x140015ee2  nop     dword ptr [rax+rax+00h]
0x140015ee7  xor     ebx, ebx
0x140015ee9  mov     rcx, cs:WPP_GLOBAL_Control
0x140015ef0  lea     rax, WPP_GLOBAL_Control
0x140015ef7  cmp     rcx, rax
0x140015efa  jz      short loc_140015F19
0x140015efc  mov     edx, [rcx+2Ch]
0x140015eff  test    dl, 1
0x140015f02  jz      short loc_140015F19
0x140015f04  mov     rcx, [rcx+18h]
0x140015f08  lea     r8, WPP_6e2ab52aad8b3bbfdaad4cd7cd77f43e_Traceguids
0x140015f0f  mov     edx, 11h
0x140015f14  call    WPP_SF_
0x140015f19  mov     rax, rbx
0x140015f1c  add     rsp, 40h
0x140015f20  pop     r14
0x140015f22  pop     rdi
0x140015f23  pop     rsi
0x140015f24  pop     rbp
0x140015f25  pop     rbx
0x140015f26  retn
0x140015f28  xor     eax, eax
0x140015f2a  xorps   xmm0, xmm0
0x140015f2d  movups  xmmword ptr [rbx], xmm0
0x140015f30  mov     [rbx+10h], rax
0x140015f34  mov     rax, [rsi]
0x140015f37  mov     [rbx], rax
0x140015f3a  mov     rcx, cs:WPP_GLOBAL_Control
0x140015f41  lea     rax, WPP_GLOBAL_Control
0x140015f48  cmp     rcx, rax
0x140015f4b  jz      short loc_140015F75
0x140015f4d  test    dword ptr [rcx+2Ch], 20000h
0x140015f54  jz      short loc_140015F75
0x140015f56  mov     eax, [rbx+4]
0x140015f59  lea     r8, WPP_6e2ab52aad8b3bbfdaad4cd7cd77f43e_Traceguids
0x140015f60  mov     r9d, [rbx]
0x140015f63  mov     edx, 10h
0x140015f68  mov     rcx, [rcx+18h]
0x140015f6c  mov     [rsp+68h+var_48], eax
0x140015f70  call    WPP_SF_dd
0x140015f75  mov     [rbx+8], rdi
0x140015f79  jmp     short loc_140015F19
```
