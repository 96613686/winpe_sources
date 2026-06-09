# DfscNetUseTableConflictDetect

- ea: `0x140017dfc`
- end: `0x140017faf`
- name: `DfscNetUseTableConflictDetect`
- size: `435`
- prototype: `__int64 __fastcall(struct _RTL_AVL_TABLE *, __int64, int, _DWORD *, const char *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140017458`

## callees

- `0x1400049a8`
- `0x140004e30`
- `0x140004ea4`
- `0x140017c68`
- `0x140017dfc`

## import_xrefs

- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140017e21`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140017f9b`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140017e21`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140017f9b`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140017f6b`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140017f6b`

## pseudocode

```c
__int64 __fastcall DfscNetUseTableConflictDetect(
        struct _RTL_AVL_TABLE *a1,
        __int64 a2,
        int a3,
        _DWORD *a4,
        const char *a5)
{
  int v6; // ebp
  int v7; // r15d
  PVOID v10; // rax
  __int64 v11; // r8
  unsigned int *v12; // rbx
  __int64 v13; // r14
  __int64 v14; // rdi
  _DWORD *v15; // rax

  v6 = 0;
  v7 = 0;
  v10 = RtlEnumerateGenericTableAvl(a1, 1u);
  while ( 1 )
  {
    v12 = (unsigned int *)v10;
    if ( !v10 )
      return (unsigned int)v6;
    v13 = *((_QWORD *)v10 + 4);
    v14 = *(_QWORD *)(v13 + 112);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
        WPP_SF_dqZq(WPP_GLOBAL_Control->AttachedDevice, 18, v11, v7, v13, (__int64)v10, *(_QWORD *)(v13 + 112));
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
      {
        WPP_SF_dDDd(WPP_GLOBAL_Control->AttachedDevice, 19, v11, v12[4], v12[6], v12[5], *(_DWORD *)(v13 + 4));
      }
    }
    if ( a3 != -1 && a3 != v12[4]
      || *a4 != v12[5]
      || a4[1] != v12[6]
      || DfscIsPathEqualString((__m128i *)(a2 + 8), (UNICODE_STRING *)(v13 + 8)) )
    {
      goto LABEL_31;
    }
    if ( v14 )
    {
      v15 = (_DWORD *)(v14 + 40);
      if ( *(_DWORD *)(v14 + 40) == 1 )
      {
        if ( !*(_DWORD *)(v14 + 44) && !a2 )
          return (unsigned int)-1073741419;
        goto LABEL_25;
      }
    }
    else if ( a2 && *(_DWORD *)(a2 + 40) == 1 && !*(_DWORD *)(a2 + 44) )
    {
      return (unsigned int)-1073741419;
    }
    v15 = (_DWORD *)(v14 + 40);
LABEL_25:
    if ( a2
      && *(_DWORD *)(a2 + 40) == 1
      && v14
      && *v15 == 1
      && RtlCompareUnicodeString((PCUNICODE_STRING)(a2 + 56), (PCUNICODE_STRING)(v14 + 56), 1u) )
    {
      return (unsigned int)-1073741419;
    }
    v6 = DfscTransportConflictDetect(v13, a5);
    if ( v6 < 0 )
      return (unsigned int)v6;
LABEL_31:
    v10 = RtlEnumerateGenericTableAvl(a1, 0);
    ++v7;
  }
}

```

## disassembly

```asm
0x140017dfc  mov     [rsp+Table], rcx
0x140017e01  push    rbx
0x140017e02  push    rbp
0x140017e03  push    rsi
0x140017e04  push    rdi
0x140017e05  push    r12
0x140017e07  push    r13
0x140017e09  push    r14
0x140017e0b  push    r15
0x140017e0d  sub     rsp, 48h
0x140017e11  mov     rsi, rdx
0x140017e14  xor     ebp, ebp
0x140017e16  mov     dl, 1; Restart
0x140017e18  xor     r15d, r15d
0x140017e1b  mov     r13, r9
0x140017e1e  mov     r12d, r8d
0x140017e21  call    cs:__imp_RtlEnumerateGenericTableAvl
0x140017e28  nop     dword ptr [rax+rax+00h]
0x140017e2d  mov     rbx, rax
0x140017e30  lea     rax, WPP_GLOBAL_Control
0x140017e37  test    rbx, rbx
0x140017e3a  jz      loc_140017F33
0x140017e40  mov     r14, [rbx+20h]
0x140017e44  mov     rdi, [r14+70h]
0x140017e48  mov     rcx, cs:WPP_GLOBAL_Control
0x140017e4f  cmp     rcx, rax
0x140017e52  jz      short loc_140017EC1
0x140017e54  test    dword ptr [rcx+2Ch], 200000h
0x140017e5b  jz      short loc_140017E7D
0x140017e5d  mov     rcx, [rcx+18h]
0x140017e61  mov     edx, 12h
0x140017e66  mov     [rsp+88h+var_58], rdi
0x140017e6b  mov     r9d, r15d
0x140017e6e  mov     [rsp+88h+var_60], rbx
0x140017e73  mov     [rsp+88h+var_68], r14
0x140017e78  call    WPP_SF_dqZq
0x140017e7d  mov     rcx, cs:WPP_GLOBAL_Control
0x140017e84  lea     rax, WPP_GLOBAL_Control
0x140017e8b  cmp     rcx, rax
0x140017e8e  jz      short loc_140017EC1
0x140017e90  test    dword ptr [rcx+2Ch], 200000h
0x140017e97  jz      short loc_140017EC1
0x140017e99  mov     eax, [r14+4]
0x140017e9d  mov     edx, 13h
0x140017ea2  mov     r9d, [rbx+10h]
0x140017ea6  mov     rcx, [rcx+18h]
0x140017eaa  mov     dword ptr [rsp+88h+var_58], eax
0x140017eae  mov     eax, [rbx+14h]
0x140017eb1  mov     dword ptr [rsp+88h+var_60], eax
0x140017eb5  mov     eax, [rbx+18h]
0x140017eb8  mov     dword ptr [rsp+88h+var_68], eax
0x140017ebc  call    WPP_SF_dDDd
0x140017ec1  cmp     r12d, 0FFFFFFFFh
0x140017ec5  jz      short loc_140017ED1
0x140017ec7  cmp     r12d, [rbx+10h]
0x140017ecb  jnz     loc_140017F91
0x140017ed1  mov     eax, [rbx+14h]
0x140017ed4  cmp     [r13+0], eax
0x140017ed8  jnz     loc_140017F91
0x140017ede  mov     eax, [rbx+18h]
0x140017ee1  cmp     [r13+4], eax
0x140017ee5  jnz     loc_140017F91
0x140017eeb  lea     rdx, [r14+8]
0x140017eef  lea     rcx, [rsi+8]
0x140017ef3  call    DfscIsPathEqualString
0x140017ef8  test    eax, eax
0x140017efa  jnz     loc_140017F91
0x140017f00  test    rdi, rdi
0x140017f03  jnz     short loc_140017F1A
0x140017f05  test    rsi, rsi
0x140017f08  jz      short loc_140017F47
0x140017f0a  cmp     dword ptr [rsi+28h], 1
0x140017f0e  jnz     short loc_140017F47
0x140017f10  cmp     [rsi+2Ch], edi
0x140017f13  jz      short loc_140017F2E
0x140017f15  test    rdi, rdi
0x140017f18  jz      short loc_140017F47
0x140017f1a  lea     rax, [rdi+28h]
0x140017f1e  cmp     dword ptr [rax], 1
0x140017f21  jnz     short loc_140017F47
0x140017f23  cmp     dword ptr [rdi+2Ch], 0
0x140017f27  jnz     short loc_140017F4B
0x140017f29  test    rsi, rsi
0x140017f2c  jnz     short loc_140017F4B
0x140017f2e  mov     ebp, 0C0000195h
0x140017f33  mov     eax, ebp
0x140017f35  add     rsp, 48h
0x140017f39  pop     r15
0x140017f3b  pop     r14
0x140017f3d  pop     r13
0x140017f3f  pop     r12
0x140017f41  pop     rdi
0x140017f42  pop     rsi
0x140017f43  pop     rbp
0x140017f44  pop     rbx
0x140017f45  retn
0x140017f47  lea     rax, [rdi+28h]
0x140017f4b  test    rsi, rsi
0x140017f4e  jz      short loc_140017F7B
0x140017f50  cmp     dword ptr [rsi+28h], 1
0x140017f54  jnz     short loc_140017F7B
0x140017f56  test    rdi, rdi
0x140017f59  jz      short loc_140017F7B
0x140017f5b  cmp     dword ptr [rax], 1
0x140017f5e  jnz     short loc_140017F7B
0x140017f60  lea     rdx, [rdi+38h]; String2
0x140017f64  mov     r8b, 1; CaseInSensitive
0x140017f67  lea     rcx, [rsi+38h]; String1
0x140017f6b  call    cs:__imp_RtlCompareUnicodeString
0x140017f72  nop     dword ptr [rax+rax+00h]
0x140017f77  test    eax, eax
0x140017f79  jnz     short loc_140017F2E
0x140017f7b  mov     rdx, [rsp+88h+arg_20]
0x140017f83  mov     rcx, r14
0x140017f86  call    DfscTransportConflictDetect
0x140017f8b  mov     ebp, eax
0x140017f8d  test    eax, eax
0x140017f8f  js      short loc_140017F33
0x140017f91  mov     rcx, [rsp+88h+Table]; Table
0x140017f99  xor     edx, edx; Restart
0x140017f9b  call    cs:__imp_RtlEnumerateGenericTableAvl
0x140017fa2  nop     dword ptr [rax+rax+00h]
0x140017fa7  inc     r15d
0x140017faa  jmp     loc_140017E2D
```
