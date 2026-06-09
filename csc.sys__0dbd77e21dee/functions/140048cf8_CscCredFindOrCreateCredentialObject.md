# CscCredFindOrCreateCredentialObject

- ea: `0x140048cf8`
- end: `0x140048e86`
- name: `CscCredFindOrCreateCredentialObject`
- size: `398`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140052194`
- `0x140086b70`

## callees

- `0x140013f5c`
- `0x140015a94`
- `0x140016ff0`
- `0x1400190ec`
- `0x140019220`
- `0x14001b568`
- `0x140048cf8`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140048e36`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048e36`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140048d51`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140048d51`
- `rdbss!RxReferenceCredential` at `0x140048dfc`
- `rdbss!RxReferenceCredential` at `0x140048dfc`

## pseudocode

```c
__int64 __fastcall CscCredFindOrCreateCredentialObject(__int64 a1, __int64 a2, __int64 *a3)
{
  int v6; // r14d
  __int64 CredentialObject; // rax
  __int64 v8; // rbx
  int IsCredentialConflict; // edi
  int v10; // eax
  __int64 v11; // rcx
  __int64 *v12; // rax
  __int64 v13; // rcx
  __int64 v15; // [rsp+80h] [rbp+8h] BYREF

  v6 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_d765a1722ddb33a90f589cef06fc1524_Traceguids, a1, a2);
  ExAcquireResourceExclusiveLite((PERESOURCE)(a1 + 8), 1u);
  CredentialObject = CscCredpFindCredentialObject(a1, a2, *(unsigned int *)(a2 + 16));
  v15 = CredentialObject;
  v8 = CredentialObject;
  if ( CredentialObject )
  {
    IsCredentialConflict = CscCredpIsCredentialConflict(CredentialObject + 24, a2);
    if ( IsCredentialConflict >= 0 )
      goto LABEL_16;
    v6 = 477;
    goto LABEL_9;
  }
  v10 = CscCredpCreateCredentialObject(&v15);
  v8 = v15;
  IsCredentialConflict = v10;
  if ( v10 < 0 )
  {
    v6 = 485;
LABEL_9:
    if ( v8 )
    {
      CscCredpDerefCredentialObject(a1, &v15);
      v8 = v15;
    }
    goto LABEL_16;
  }
  v11 = *(_QWORD *)(a2 + 32);
  *(_OWORD *)(v15 + 24) = *(_OWORD *)a2;
  *(_OWORD *)(v8 + 40) = *(_OWORD *)(a2 + 16);
  *(_QWORD *)(v8 + 56) = *(_QWORD *)(a2 + 32);
  if ( v11 )
    RxReferenceCredential();
  v12 = (__int64 *)(a1 + 112);
  *(_DWORD *)(v8 + 52) = 0;
  v13 = *(_QWORD *)(a1 + 112);
  if ( *(_QWORD *)(v13 + 8) != a1 + 112 )
    __fastfail(3u);
  *(_QWORD *)v8 = v13;
  *(_QWORD *)(v8 + 8) = v12;
  *(_QWORD *)(v13 + 8) = v8;
  *v12 = v8;
LABEL_16:
  *a3 = v8;
  ExReleaseResourceLite((PERESOURCE)(a1 + 8));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      18,
      WPP_d765a1722ddb33a90f589cef06fc1524_Traceguids,
      (unsigned int)IsCredentialConflict,
      v6);
  return (unsigned int)IsCredentialConflict;
}

```

## disassembly

```asm
0x140048cf8  push    rbx
0x140048cfa  push    rbp
0x140048cfb  push    rsi
0x140048cfc  push    rdi
0x140048cfd  push    r12
0x140048cff  push    r13
0x140048d01  push    r14
0x140048d03  push    r15
0x140048d05  sub     rsp, 38h
0x140048d09  mov     r12, r8
0x140048d0c  mov     rsi, rdx
0x140048d0f  mov     rbp, rcx
0x140048d12  xor     r14d, r14d
0x140048d15  mov     rcx, cs:WPP_GLOBAL_Control
0x140048d1c  lea     r13, WPP_GLOBAL_Control
0x140048d23  cmp     rcx, r13
0x140048d26  jz      short loc_140048D4B
0x140048d28  mov     eax, [rcx+2Ch]
0x140048d2b  test    al, 20h
0x140048d2d  jz      short loc_140048D4B
0x140048d2f  mov     rcx, [rcx+18h]
0x140048d33  lea     edx, [r14+11h]
0x140048d37  mov     r9, rbp
0x140048d3a  mov     [rsp+78h+var_58], rsi
0x140048d3f  lea     r8, WPP_d765a1722ddb33a90f589cef06fc1524_Traceguids
0x140048d46  call    WPP_SF_qq
0x140048d4b  mov     dl, 1; Wait
0x140048d4d  lea     rcx, [rbp+8]; Resource
0x140048d51  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140048d58  nop     dword ptr [rax+rax+00h]
0x140048d5d  mov     r8d, [rsi+10h]
0x140048d61  mov     rdx, rsi
0x140048d64  mov     rcx, rbp
0x140048d67  call    CscCredpFindCredentialObject
0x140048d6c  mov     [rsp+78h+arg_0], rax
0x140048d74  mov     rbx, rax
0x140048d77  test    rax, rax
0x140048d7a  jz      short loc_140048D9A
0x140048d7c  lea     rcx, [rax+18h]
0x140048d80  mov     rdx, rsi
0x140048d83  call    CscCredpIsCredentialConflict
0x140048d88  mov     edi, eax
0x140048d8a  test    eax, eax
0x140048d8c  jns     loc_140048E2E
0x140048d92  mov     r14d, 1DDh
0x140048d98  jmp     short loc_140048DBB
0x140048d9a  lea     rcx, [rsp+78h+arg_0]
0x140048da2  call    CscCredpCreateCredentialObject
0x140048da7  mov     rbx, [rsp+78h+arg_0]
0x140048daf  mov     edi, eax
0x140048db1  test    eax, eax
0x140048db3  jns     short loc_140048DDA
0x140048db5  mov     r14d, 1E5h
0x140048dbb  test    rbx, rbx
0x140048dbe  jz      short loc_140048E2E
0x140048dc0  lea     rdx, [rsp+78h+arg_0]
0x140048dc8  mov     rcx, rbp
0x140048dcb  call    CscCredpDerefCredentialObject
0x140048dd0  mov     rbx, [rsp+78h+arg_0]
0x140048dd8  jmp     short loc_140048E2E
0x140048dda  movups  xmm0, xmmword ptr [rsi]
0x140048ddd  mov     rcx, [rsi+20h]
0x140048de1  movups  xmmword ptr [rbx+18h], xmm0
0x140048de5  movups  xmm1, xmmword ptr [rsi+10h]
0x140048de9  movups  xmmword ptr [rbx+28h], xmm1
0x140048ded  movsd   xmm0, qword ptr [rsi+20h]
0x140048df2  movsd   qword ptr [rbx+38h], xmm0
0x140048df7  test    rcx, rcx
0x140048dfa  jz      short loc_140048E08
0x140048dfc  call    cs:__imp_RxReferenceCredential
0x140048e03  nop     dword ptr [rax+rax+00h]
0x140048e08  lea     rax, [rbp+70h]
0x140048e0c  mov     [rbx+34h], r14d
0x140048e10  mov     rcx, [rax]
0x140048e13  cmp     [rcx+8], rax
0x140048e17  jz      short loc_140048E20
0x140048e19  mov     ecx, 3
0x140048e1e  int     29h; Win8: RtlFailFast(ecx)
0x140048e20  mov     [rbx], rcx
0x140048e23  mov     [rbx+8], rax
0x140048e27  mov     [rcx+8], rbx
0x140048e2b  mov     [rax], rbx
0x140048e2e  lea     rcx, [rbp+8]; Resource
0x140048e32  mov     [r12], rbx
0x140048e36  call    cs:__imp_ExReleaseResourceLite
0x140048e3d  nop     dword ptr [rax+rax+00h]
0x140048e42  mov     rcx, cs:WPP_GLOBAL_Control
0x140048e49  cmp     rcx, r13
0x140048e4c  jz      short loc_140048E72
0x140048e4e  mov     eax, [rcx+2Ch]
0x140048e51  test    al, 20h
0x140048e53  jz      short loc_140048E72
0x140048e55  mov     rcx, [rcx+18h]
0x140048e59  lea     r8, WPP_d765a1722ddb33a90f589cef06fc1524_Traceguids
0x140048e60  mov     edx, 12h
0x140048e65  mov     dword ptr [rsp+78h+var_58], r14d
0x140048e6a  mov     r9d, edi
0x140048e6d  call    WPP_SF_Dd
0x140048e72  mov     eax, edi
0x140048e74  add     rsp, 38h
0x140048e78  pop     r15
0x140048e7a  pop     r14
0x140048e7c  pop     r13
0x140048e7e  pop     r12
0x140048e80  pop     rdi
0x140048e81  pop     rsi
0x140048e82  pop     rbp
0x140048e83  pop     rbx
0x140048e84  retn
```
