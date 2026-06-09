# KerberosCryptoPolicy::Create(Kerb3961PolicyType)

- ea: `0x140007f68`
- end: `0x1400080fe`
- name: `?Create@KerberosCryptoPolicy@@SA?AV?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@W4Kerb3961PolicyType@@@Z`
- size: `406`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140008104`

## callees

- `0x1400055f0`
- `0x140005ff8`
- `0x140007f68`
- `0x140010240`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140007fac`
- `ntoskrnl!ExAllocatePool2` at `0x140007fac`
- `Kerb3961Kernel!__imp_GetLocalCipherPolicy` at `0x140007f80`
- `Kerb3961Kernel!__imp_GetLocalCipherPolicy` at `0x140007f80`

## pseudocode

```c
_QWORD *__fastcall KerberosCryptoPolicy::Create(_QWORD *a1)
{
  __int64 LocalCipherPolicy; // rax
  __int64 v3; // rcx
  __int64 v4; // rbx
  __int64 Pool2; // rax
  _QWORD *v6; // rdi
  __int64 v7; // rcx
  __int64 v8; // rbx
  __int64 v10; // [rsp+20h] [rbp-30h] BYREF
  __int64 v11; // [rsp+28h] [rbp-28h]
  int v12; // [rsp+30h] [rbp-20h]
  _BYTE v13[24]; // [rsp+38h] [rbp-18h] BYREF
  KerberosCryptoPolicy *v14; // [rsp+80h] [rbp+30h] BYREF

  LocalCipherPolicy = GetLocalCipherPolicy();
  v3 = 64;
  v4 = LocalCipherPolicy;
  if ( KerbPoolType == PagedPool )
    v3 = 256;
  Pool2 = ExAllocatePool2(v3, 128, 1130525259);
  v6 = (_QWORD *)Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)Pool2 = v4;
    *(_BYTE *)(Pool2 + 8) = 0;
    *(_QWORD *)(Pool2 + 16) = 0;
    *(_QWORD *)(Pool2 + 24) = 0;
    *(_QWORD *)(Pool2 + 32) = 0;
    *(_QWORD *)(Pool2 + 40) = 0;
    *(_QWORD *)(Pool2 + 48) = 0;
    *(_DWORD *)(Pool2 + 56) = 0;
    *(_BYTE *)(Pool2 + 64) = 0;
    *(_QWORD *)(Pool2 + 72) = 0;
    *(_DWORD *)(Pool2 + 80) = 0;
    *(_BYTE *)(Pool2 + 88) = 0;
    *(_QWORD *)(Pool2 + 96) = 0;
    *(_BYTE *)(Pool2 + 104) = 0;
    *(_QWORD *)(Pool2 + 112) = 0;
    *(_QWORD *)(Pool2 + 120) = 0;
    v7 = *(_QWORD *)Pool2;
    v14 = (KerberosCryptoPolicy *)Pool2;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 56LL))(v7, &v10);
    if ( v12 < 0 )
      goto LABEL_5;
    Kerb3961::CipherPartnerHandle::~CipherPartnerHandle((Kerb3961::CipherPartnerHandle *)(v6 + 2));
    v6[2] = v10;
    v6[3] = v11;
    v11 = 0;
    v10 = 0;
    v8 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v6 + 56LL))(*v6, v13);
    Kerb3961::CipherPartnerHandle::~CipherPartnerHandle((Kerb3961::CipherPartnerHandle *)&v10);
    v10 = *(_QWORD *)v8;
    v11 = *(_QWORD *)(v8 + 8);
    *(_QWORD *)(v8 + 8) = 0;
    *(_QWORD *)v8 = 0;
    v12 = *(_DWORD *)(v8 + 16);
    *(_DWORD *)(v8 + 16) = -1073741823;
    Kerb3961::CipherPartnerHandle::~CipherPartnerHandle((Kerb3961::CipherPartnerHandle *)v13);
    if ( v12 < 0 )
    {
LABEL_5:
      *a1 = 0;
    }
    else
    {
      Kerb3961::CipherPartnerHandle::~CipherPartnerHandle((Kerb3961::CipherPartnerHandle *)(v6 + 4));
      v6[4] = v10;
      v6[5] = v11;
      v11 = 0;
      v10 = 0;
      *a1 = v6;
      v14 = 0;
    }
    Kerb3961::CipherPartnerHandle::~CipherPartnerHandle((Kerb3961::CipherPartnerHandle *)&v10);
  }
  else
  {
    v14 = 0;
    *a1 = 0;
  }
  utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v14);
  return a1;
}

```

## disassembly

```asm
0x140007f68  mov     [rsp-18h+arg_0], rbx
0x140007f6d  mov     [rsp-18h+arg_8], rsi
0x140007f72  push    rbp
0x140007f73  push    rdi
0x140007f74  push    r14
0x140007f76  mov     rbp, rsp
0x140007f79  sub     rsp, 50h
0x140007f7d  mov     rsi, rcx
0x140007f80  call    cs:__imp_GetLocalCipherPolicy
0x140007f87  nop     dword ptr [rax+rax+00h]
0x140007f8c  cmp     cs:?KerbPoolType@@3W4_POOL_TYPE@@A, 1; _POOL_TYPE KerbPoolType
0x140007f93  mov     ecx, 40h ; '@'
0x140007f98  mov     rbx, rax
0x140007f9b  mov     r8d, 4362724Bh
0x140007fa1  mov     eax, 100h
0x140007fa6  cmovz   ecx, eax
0x140007fa9  lea     edx, [rax-80h]
0x140007fac  call    cs:__imp_ExAllocatePool2
0x140007fb3  nop     dword ptr [rax+rax+00h]
0x140007fb8  xor     r14d, r14d
0x140007fbb  mov     rdi, rax
0x140007fbe  test    rax, rax
0x140007fc1  jz      loc_1400080D7
0x140007fc7  mov     [rax], rbx
0x140007fca  lea     rdx, [rbp+var_30]
0x140007fce  mov     [rax+8], r14b
0x140007fd2  mov     [rax+10h], r14
0x140007fd6  mov     [rax+18h], r14
0x140007fda  mov     [rax+20h], r14
0x140007fde  mov     [rax+28h], r14
0x140007fe2  mov     [rax+30h], r14
0x140007fe6  mov     [rax+38h], r14d
0x140007fea  mov     [rax+40h], r14b
0x140007fee  mov     [rax+48h], r14
0x140007ff2  mov     [rax+50h], r14d
0x140007ff6  mov     [rax+58h], r14b
0x140007ffa  mov     [rax+60h], r14
0x140007ffe  mov     [rax+68h], r14b
0x140008002  mov     [rax+70h], r14
0x140008006  mov     [rax+78h], r14
0x14000800a  mov     rcx, [rax]
0x14000800d  mov     [rbp+arg_10], rax
0x140008011  mov     rax, [rcx]
0x140008014  mov     rax, [rax+38h]
0x140008018  call    _guard_dispatch_icall
0x14000801d  cmp     [rbp+var_20], r14d
0x140008021  jge     short loc_140008034
0x140008023  mov     [rsi], r14
0x140008026  lea     rcx, [rbp+var_30]; this
0x14000802a  call    ??1CipherPartnerHandle@Kerb3961@@QEAA@XZ; Kerb3961::CipherPartnerHandle::~CipherPartnerHandle(void)
0x14000802f  jmp     loc_1400080DE
0x140008034  lea     rcx, [rdi+10h]; this
0x140008038  call    ??1CipherPartnerHandle@Kerb3961@@QEAA@XZ; Kerb3961::CipherPartnerHandle::~CipherPartnerHandle(void)
0x14000803d  mov     rax, [rbp+var_30]
0x140008041  lea     rdx, [rbp+var_18]
0x140008045  mov     [rdi+10h], rax
0x140008049  mov     rax, [rbp+var_28]
0x14000804d  mov     [rdi+18h], rax
0x140008051  mov     [rbp+var_28], r14
0x140008055  mov     [rbp+var_30], r14
0x140008059  mov     rcx, [rdi]
0x14000805c  mov     rax, [rcx]
0x14000805f  mov     rax, [rax+38h]
0x140008063  call    _guard_dispatch_icall
0x140008068  lea     rcx, [rbp+var_30]; this
0x14000806c  mov     rbx, rax
0x14000806f  call    ??1CipherPartnerHandle@Kerb3961@@QEAA@XZ; Kerb3961::CipherPartnerHandle::~CipherPartnerHandle(void)
0x140008074  mov     rcx, [rbx]
0x140008077  mov     [rbp+var_30], rcx
0x14000807b  mov     rcx, [rbx+8]
0x14000807f  mov     [rbp+var_28], rcx
0x140008083  mov     [rbx+8], r14
0x140008087  mov     [rbx], r14
0x14000808a  mov     ecx, [rbx+10h]
0x14000808d  mov     [rbp+var_20], ecx
0x140008090  lea     rcx, [rbp+var_18]; this
0x140008094  mov     dword ptr [rbx+10h], 0C0000001h
0x14000809b  call    ??1CipherPartnerHandle@Kerb3961@@QEAA@XZ; Kerb3961::CipherPartnerHandle::~CipherPartnerHandle(void)
0x1400080a0  cmp     [rbp+var_20], r14d
0x1400080a4  jl      loc_140008023
0x1400080aa  lea     rcx, [rdi+20h]; this
0x1400080ae  call    ??1CipherPartnerHandle@Kerb3961@@QEAA@XZ; Kerb3961::CipherPartnerHandle::~CipherPartnerHandle(void)
0x1400080b3  mov     rax, [rbp+var_30]
0x1400080b7  mov     [rdi+20h], rax
0x1400080bb  mov     rax, [rbp+var_28]
0x1400080bf  mov     [rdi+28h], rax
0x1400080c3  mov     [rbp+var_28], r14
0x1400080c7  mov     [rbp+var_30], r14
0x1400080cb  mov     [rsi], rdi
0x1400080ce  mov     [rbp+arg_10], r14
0x1400080d2  jmp     loc_140008026
0x1400080d7  mov     [rbp+arg_10], r14
0x1400080db  mov     [rsi], r14
0x1400080de  lea     rcx, [rbp+arg_10]
0x1400080e2  call    ??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)
0x1400080e7  mov     rbx, [rsp+50h+arg_0]
0x1400080ec  mov     rax, rsi
0x1400080ef  mov     rsi, [rsp+50h+arg_8]
0x1400080f4  add     rsp, 50h
0x1400080f8  pop     r14
0x1400080fa  pop     rdi
0x1400080fb  pop     rbp
0x1400080fc  retn
```
