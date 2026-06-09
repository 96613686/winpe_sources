# SspLogAuthEventCommon(_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,int,int)

- ea: `0x180050e28`
- end: `0x1800510fd`
- name: `?SspLogAuthEventCommon@@YAXPEAU_UNICODE_STRING@@000HH@Z`
- size: `725`
- prototype: `void __fastcall(struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022220`

## callees

- `0x18000cba0`
- `0x18002e3e8`
- `0x18002fb50`
- `0x180050e28`
- `0x18006d010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180050f0b`
- `ntdll!EtwEventEnabled` at `0x180050f0b`
- `ntdll!EtwEventWrite` at `0x18005100f`
- `ntdll!EtwEventWrite` at `0x18005100f`
- `LSASRV!LsaIAuditAccountLogonEx` at `0x180051069`
- `LSASRV!LsaIAuditAccountLogonEx` at `0x180051069`

## pseudocode

```c
void __fastcall SspLogAuthEventCommon(
        struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4,
        int a5,
        int a6)
{
  __int64 *v10; // rdi
  int v11; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v12; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v13; // [rsp+68h] [rbp-98h] BYREF
  __int128 v14; // [rsp+78h] [rbp-88h] BYREF
  __int128 v15; // [rsp+88h] [rbp-78h] BYREF
  const wchar_t *v16; // [rsp+A0h] [rbp-60h]
  __int64 v17; // [rsp+A8h] [rbp-58h]
  const wchar_t *v18; // [rsp+B0h] [rbp-50h]
  __int64 v19; // [rsp+B8h] [rbp-48h]
  int *v20; // [rsp+C0h] [rbp-40h]
  __int64 v21; // [rsp+C8h] [rbp-38h]
  const wchar_t *v22; // [rsp+D0h] [rbp-30h]
  __int64 v23; // [rsp+D8h] [rbp-28h]
  const wchar_t *v24; // [rsp+E0h] [rbp-20h]
  __int64 v25; // [rsp+E8h] [rbp-18h]

  v11 = -1073741714;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  if ( (int)SspInitEtwLogHandle() >= 0
    && (int)NtLmDuplicateUnicodeString(&v12, a1) >= 0
    && (int)NtLmDuplicateUnicodeString(&v13, a2) >= 0
    && (int)NtLmDuplicateUnicodeString(&v14, a3) >= 0
    && (int)NtLmDuplicateUnicodeString(&v15, a4) >= 0 )
  {
    if ( a5 )
    {
      v10 = AccessControlRestrictionNTLMAccountLogonWarning;
      if ( !a6 )
        v10 = AccessControlRestrictionNTLMAccountLogonFailure;
    }
    else
    {
      v10 = ProtectedUserNTLMAccountLogonFailure;
    }
    if ( (unsigned __int8)EtwEventEnabled(MsvEtwLogHandle, v10) )
    {
      if ( *((_QWORD *)&v12 + 1) && (_WORD)v12 )
      {
        v16 = (const wchar_t *)*((_QWORD *)&v12 + 1);
        v17 = (unsigned int)(unsigned __int16)v12 + 2;
      }
      else
      {
        v16 = L"(NULL)";
        v17 = 14;
      }
      if ( *((_QWORD *)&v13 + 1) && (_WORD)v13 )
      {
        v18 = (const wchar_t *)*((_QWORD *)&v13 + 1);
        v19 = (unsigned int)(unsigned __int16)v13 + 2;
      }
      else
      {
        v18 = L"(NULL)";
        v19 = 14;
      }
      v21 = 4;
      v20 = &v11;
      if ( a5 )
      {
        if ( *((_QWORD *)&v14 + 1) && (_WORD)v14 )
        {
          v22 = (const wchar_t *)*((_QWORD *)&v14 + 1);
          v23 = (unsigned int)(unsigned __int16)v14 + 2;
        }
        else
        {
          v22 = L"(NULL)";
          v23 = 14;
        }
        if ( *((_QWORD *)&v15 + 1) && (_WORD)v15 )
        {
          v24 = (const wchar_t *)*((_QWORD *)&v15 + 1);
          v25 = (unsigned int)(unsigned __int16)v15 + 2;
        }
        else
        {
          v24 = L"(NULL)";
          v25 = 14;
        }
      }
      EtwEventWrite(MsvEtwLogHandle, v10, a5 != 0 ? 5 : 3);
    }
    LsaIAuditAccountLogonEx(
      (unsigned int)(a5 != 0) + 726,
      0,
      0,
      &v12,
      &v13,
      (unsigned __int64)&v14 & -(__int64)(a5 != 0),
      (unsigned __int64)&v15 & -(__int64)(a5 != 0),
      -1073741714,
      0);
  }
  if ( *((_QWORD *)&v12 + 1) )
    ((void (*)(void))LsaFunctions->FreePrivateHeap)();
  if ( *((_QWORD *)&v13 + 1) )
    ((void (*)(void))LsaFunctions->FreePrivateHeap)();
  if ( *((_QWORD *)&v14 + 1) )
    ((void (*)(void))LsaFunctions->FreePrivateHeap)();
  if ( *((_QWORD *)&v15 + 1) )
    ((void (*)(void))LsaFunctions->FreePrivateHeap)();
}

```

## disassembly

```asm
0x180050e28  push    rbp
0x180050e2a  push    rbx
0x180050e2b  push    rsi
0x180050e2c  push    rdi
0x180050e2d  push    r14
0x180050e2f  push    r15
0x180050e31  lea     rbp, [rsp-8]
0x180050e36  sub     rsp, 108h
0x180050e3d  mov     rax, cs:__security_cookie
0x180050e44  xor     rax, rsp
0x180050e47  mov     [rbp+30h+var_40], rax
0x180050e4b  xorps   xmm0, xmm0
0x180050e4e  mov     [rsp+130h+var_E0], 0C000006Eh
0x180050e56  xorps   xmm1, xmm1
0x180050e59  mov     rdi, r9
0x180050e5c  movups  [rsp+130h+var_D8], xmm0
0x180050e61  mov     r14, r8
0x180050e64  mov     rsi, rdx
0x180050e67  movups  [rsp+130h+var_C8], xmm1
0x180050e6c  mov     rbx, rcx
0x180050e6f  movups  [rsp+130h+var_B8], xmm0
0x180050e74  movups  [rbp+30h+var_A8], xmm1
0x180050e78  call    SspInitEtwLogHandle
0x180050e7d  xor     r15d, r15d
0x180050e80  test    eax, eax
0x180050e82  js      loc_18005106F
0x180050e88  mov     rdx, rbx
0x180050e8b  lea     rcx, [rsp+130h+var_D8]
0x180050e90  call    NtLmDuplicateUnicodeString
0x180050e95  test    eax, eax
0x180050e97  js      loc_18005106F
0x180050e9d  mov     rdx, rsi
0x180050ea0  lea     rcx, [rsp+130h+var_C8]
0x180050ea5  call    NtLmDuplicateUnicodeString
0x180050eaa  test    eax, eax
0x180050eac  js      loc_18005106F
0x180050eb2  mov     rdx, r14
0x180050eb5  lea     rcx, [rsp+130h+var_B8]
0x180050eba  call    NtLmDuplicateUnicodeString
0x180050ebf  test    eax, eax
0x180050ec1  js      loc_18005106F
0x180050ec7  mov     rdx, rdi
0x180050eca  lea     rcx, [rbp+30h+var_A8]
0x180050ece  call    NtLmDuplicateUnicodeString
0x180050ed3  test    eax, eax
0x180050ed5  js      loc_18005106F
0x180050edb  mov     ebx, [rbp+30h+arg_20]
0x180050ede  test    ebx, ebx
0x180050ee0  jz      short loc_180050EFA
0x180050ee2  cmp     [rbp+30h+arg_28], r15d
0x180050ee6  lea     rdi, AccessControlRestrictionNTLMAccountLogonWarning
0x180050eed  lea     rax, AccessControlRestrictionNTLMAccountLogonFailure
0x180050ef4  cmovz   rdi, rax
0x180050ef8  jmp     short loc_180050F01
0x180050efa  lea     rdi, ProtectedUserNTLMAccountLogonFailure
0x180050f01  mov     rcx, cs:MsvEtwLogHandle
0x180050f08  mov     rdx, rdi
0x180050f0b  call    cs:__imp_EtwEventEnabled
0x180050f11  test    al, al
0x180050f13  jz      loc_180051015
0x180050f19  mov     rax, qword ptr [rsp+130h+var_D8+8]
0x180050f1e  lea     rdx, aNull; "(NULL)"
0x180050f25  test    rax, rax
0x180050f28  jz      short loc_180050F44
0x180050f2a  movzx   ecx, word ptr [rsp+130h+var_D8]
0x180050f2f  test    cx, cx
0x180050f32  jz      short loc_180050F44
0x180050f34  mov     [rbp+30h+var_90], rax
0x180050f38  lea     eax, [rcx+2]
0x180050f3b  mov     dword ptr [rbp+30h+var_88], eax
0x180050f3e  mov     dword ptr [rbp+30h+var_88+4], r15d
0x180050f42  jmp     short loc_180050F50
0x180050f44  mov     [rbp+30h+var_90], rdx
0x180050f48  mov     [rbp+30h+var_88], 0Eh
0x180050f50  mov     rax, qword ptr [rsp+130h+var_C8+8]
0x180050f55  test    rax, rax
0x180050f58  jz      short loc_180050F74
0x180050f5a  movzx   ecx, word ptr [rsp+130h+var_C8]
0x180050f5f  test    cx, cx
0x180050f62  jz      short loc_180050F74
0x180050f64  mov     [rbp+30h+var_80], rax
0x180050f68  lea     eax, [rcx+2]
0x180050f6b  mov     dword ptr [rbp+30h+var_78], eax
0x180050f6e  mov     dword ptr [rbp+30h+var_78+4], r15d
0x180050f72  jmp     short loc_180050F80
0x180050f74  mov     [rbp+30h+var_80], rdx
0x180050f78  mov     [rbp+30h+var_78], 0Eh
0x180050f80  mov     [rbp+30h+var_68], 4
0x180050f88  lea     rax, [rsp+130h+var_E0]
0x180050f8d  mov     [rbp+30h+var_70], rax
0x180050f91  test    ebx, ebx
0x180050f93  jz      short loc_180050FF2
0x180050f95  mov     rax, qword ptr [rbp+30h+var_B8+8]
0x180050f99  test    rax, rax
0x180050f9c  jz      short loc_180050FB8
0x180050f9e  movzx   ecx, word ptr [rsp+130h+var_B8]
0x180050fa3  test    cx, cx
0x180050fa6  jz      short loc_180050FB8
0x180050fa8  mov     [rbp+30h+var_60], rax
0x180050fac  lea     eax, [rcx+2]
0x180050faf  mov     dword ptr [rbp+30h+var_58], eax
0x180050fb2  mov     dword ptr [rbp+30h+var_58+4], r15d
0x180050fb6  jmp     short loc_180050FC4
0x180050fb8  mov     [rbp+30h+var_60], rdx
0x180050fbc  mov     [rbp+30h+var_58], 0Eh
0x180050fc4  mov     rax, qword ptr [rbp+30h+var_A8+8]
0x180050fc8  test    rax, rax
0x180050fcb  jz      short loc_180050FE6
0x180050fcd  movzx   ecx, word ptr [rbp+30h+var_A8]
0x180050fd1  test    cx, cx
0x180050fd4  jz      short loc_180050FE6
0x180050fd6  mov     [rbp+30h+var_50], rax
0x180050fda  lea     eax, [rcx+2]
0x180050fdd  mov     dword ptr [rbp+30h+var_48], eax
0x180050fe0  mov     dword ptr [rbp+30h+var_48+4], r15d
0x180050fe4  jmp     short loc_180050FF2
0x180050fe6  mov     [rbp+30h+var_50], rdx
0x180050fea  mov     [rbp+30h+var_48], 0Eh
0x180050ff2  mov     rcx, cs:MsvEtwLogHandle
0x180050ff9  lea     r9, [rbp+30h+var_90]
0x180050ffd  mov     eax, ebx
0x180050fff  mov     rdx, rdi
0x180051002  neg     eax
0x180051004  sbb     r8d, r8d
0x180051007  and     r8d, 2
0x18005100b  add     r8d, 3
0x18005100f  call    cs:__imp_EtwEventWrite
0x180051015  mov     [rsp+130h+var_F0], r15
0x18005101a  lea     r9, [rsp+130h+var_D8]
0x18005101f  mov     eax, ebx
0x180051021  mov     [rsp+130h+var_F8], 0C000006Eh
0x180051029  neg     eax
0x18005102b  lea     rax, [rbp+30h+var_A8]
0x18005102f  sbb     r8, r8
0x180051032  and     r8, rax
0x180051035  mov     eax, ebx
0x180051037  neg     eax
0x180051039  mov     [rsp+130h+var_100], r8
0x18005103e  lea     rax, [rsp+130h+var_B8]
0x180051043  sbb     rdx, rdx
0x180051046  and     rdx, rax
0x180051049  lea     rax, [rsp+130h+var_C8]
0x18005104e  mov     [rsp+130h+var_108], rdx
0x180051053  neg     ebx
0x180051055  mov     [rsp+130h+var_110], rax
0x18005105a  sbb     ecx, ecx
0x18005105c  xor     r8d, r8d
0x18005105f  neg     ecx
0x180051061  xor     edx, edx
0x180051063  add     ecx, 2D6h
0x180051069  call    cs:__imp_LsaIAuditAccountLogonEx
0x18005106f  mov     rcx, qword ptr [rsp+130h+var_D8+8]
0x180051074  test    rcx, rcx
0x180051077  jz      short loc_18005108C
0x180051079  mov     rax, cs:LsaFunctions
0x180051080  mov     rax, [rax+188h]
0x180051087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005108c  mov     rcx, qword ptr [rsp+130h+var_C8+8]
0x180051091  test    rcx, rcx
0x180051094  jz      short loc_1800510A9
0x180051096  mov     rax, cs:LsaFunctions
0x18005109d  mov     rax, [rax+188h]
0x1800510a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800510a9  mov     rcx, qword ptr [rbp+30h+var_B8+8]
0x1800510ad  test    rcx, rcx
0x1800510b0  jz      short loc_1800510C5
0x1800510b2  mov     rax, cs:LsaFunctions
0x1800510b9  mov     rax, [rax+188h]
0x1800510c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800510c5  mov     rcx, qword ptr [rbp+30h+var_A8+8]
0x1800510c9  test    rcx, rcx
0x1800510cc  jz      short loc_1800510E1
0x1800510ce  mov     rax, cs:LsaFunctions
0x1800510d5  mov     rax, [rax+188h]
0x1800510dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800510e1  mov     rcx, [rbp+30h+var_40]
0x1800510e5  xor     rcx, rsp; StackCookie
0x1800510e8  call    __security_check_cookie
0x1800510ed  add     rsp, 108h
0x1800510f4  pop     r15
0x1800510f6  pop     r14
0x1800510f8  pop     rdi
0x1800510f9  pop     rsi
0x1800510fa  pop     rbx
0x1800510fb  pop     rbp
0x1800510fc  retn
```
