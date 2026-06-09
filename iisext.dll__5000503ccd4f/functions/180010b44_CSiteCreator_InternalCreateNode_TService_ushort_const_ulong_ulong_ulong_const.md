# CSiteCreator::InternalCreateNode(TService *,ushort const *,ulong *,ulong *,ulong * const)

- ea: `0x180010b44`
- end: `0x180010e78`
- name: `?InternalCreateNode@CSiteCreator@@AEAAJPEAUTService@@PEBGPEAK2QEAK@Z`
- size: `820`
- prototype: `__int64 __fastcall(CSiteCreator *__hidden this, struct TService *, const unsigned __int16 *, unsigned int *, unsigned int *, unsigned int *const)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180010638`

## callees

- `0x18001060c`
- `0x180010b44`
- `0x1800111e0`
- `0x180012010`

## import_xrefs

- `msvcrt!_ultow` at `0x180010d61`
- `msvcrt!_ultow` at `0x180010ddc`
- `msvcrt!_ultow` at `0x180010e10`
- `msvcrt!_ultow` at `0x180010d61`
- `msvcrt!_ultow` at `0x180010ddc`
- `msvcrt!_ultow` at `0x180010e10`
- `ole32!CoCreateInstance` at `0x180010c32`
- `ole32!CoCreateInstance` at `0x180010c32`
- `KERNEL32!LeaveCriticalSection` at `0x180010c03`
- `KERNEL32!LeaveCriticalSection` at `0x180010c56`
- `KERNEL32!LeaveCriticalSection` at `0x180010c72`
- `KERNEL32!LeaveCriticalSection` at `0x180010c03`
- `KERNEL32!LeaveCriticalSection` at `0x180010c56`
- `KERNEL32!LeaveCriticalSection` at `0x180010c72`

## pseudocode

```c
__int64 __fastcall CSiteCreator::InternalCreateNode(
        CSiteCreator *this,
        struct TService *a2,
        const unsigned __int16 *a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned int *const a6)
{
  unsigned int *v9; // rax
  int Instance; // ebx
  BOOL v11; // esi
  bool v12; // sf
  int v13; // ebx
  __int64 result; // rax
  unsigned int v15; // esi
  unsigned int v16; // r15d
  unsigned int v17; // esi
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, _QWORD, wchar_t *); // rbx
  wchar_t *v20; // rax
  int v21; // eax
  bool v22; // sf
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, _QWORD, wchar_t *); // rbx
  wchar_t *v25; // rax
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, _QWORD, wchar_t *, _DWORD *); // rbx
  wchar_t *v28; // rax
  unsigned int v29; // [rsp+40h] [rbp-79h] BYREF
  int v30; // [rsp+44h] [rbp-75h] BYREF
  struct TService *v31; // [rsp+48h] [rbp-71h]
  unsigned int *v32; // [rsp+50h] [rbp-69h]
  _DWORD v33[4]; // [rsp+58h] [rbp-61h] BYREF
  __int64 v34; // [rsp+68h] [rbp-51h]
  int *v35; // [rsp+70h] [rbp-49h]
  __int64 v36; // [rsp+78h] [rbp-41h]
  BOOL v37; // [rsp+80h] [rbp-39h]
  char *v38; // [rsp+88h] [rbp-31h]
  wchar_t Buffer[8]; // [rsp+90h] [rbp-29h] BYREF
  __int128 v40; // [rsp+A0h] [rbp-19h]
  __int64 v41; // [rsp+B0h] [rbp-9h]

  v31 = a2;
  v9 = a5;
  v32 = a5;
  v30 = 0;
  v33[0] = 1017;
  v33[1] = 1;
  v33[2] = 1;
  v33[3] = 1;
  v34 = 4;
  v35 = &v30;
  v36 = 0;
  v37 = 0;
  v38 = (char *)this + 8;
  if ( !*((_BYTE *)this + 64) )
  {
    Instance = CSafeAutoCriticalSection::Lock((CSiteCreator *)((char *)this + 8));
    v11 = Instance == 0;
    v37 = v11;
    v12 = Instance < 0;
    if ( Instance > 0 )
    {
      Instance = (unsigned __int16)Instance | 0x80070000;
      v12 = Instance < 0;
    }
    if ( v12 )
    {
      if ( v11 )
      {
        if ( *((_DWORD *)this + 12) == 1 )
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
      }
      return (unsigned int)Instance;
    }
    if ( !*((_BYTE *)this + 64) )
    {
      Instance = CoCreateInstance(&CLSID_MSAdminBase_W, 0, 0x17u, &IID_IMSAdminBase_W, (LPVOID *)this + 7);
      *((_BYTE *)this + 64) = Instance >= 0;
    }
    if ( v11 && *((_DWORD *)this + 12) == 1 )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    if ( Instance < 0 )
      return (unsigned int)Instance;
    v9 = v32;
    a2 = v31;
  }
  *v9 = 0;
  *a4 = 0;
  v29 = 0;
  *(_OWORD *)Buffer = 0;
  v40 = 0;
  v41 = 0;
  v13 = 0;
  while ( 1 )
  {
    result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, int, unsigned int *))(**((_QWORD **)this + 7)
                                                                                             + 136LL))(
               *((_QWORD *)this + 7),
               0,
               *((_QWORD *)a2 + 1),
               3,
               30000,
               &v29);
    if ( (_DWORD)result != -2147024748 )
      break;
    ++v13;
    a2 = v31;
    if ( v13 )
      return 2147942548LL;
  }
  if ( (int)result >= 0 )
  {
    if ( a6 )
    {
      v17 = *a6;
      v23 = *((_QWORD *)this + 7);
      v24 = *(__int64 (__fastcall **)(__int64, _QWORD, wchar_t *))(*(_QWORD *)v23 + 24LL);
      v25 = _ultow(*a6, Buffer, 10);
      Instance = v24(v23, v29, v25);
      v22 = Instance < 0;
    }
    else
    {
      v15 = 0;
      while ( *a3 )
        v15 = (*a3++ & 0xFFDF) + 101 * v15;
      v16 = 0;
      v17 = v15 % 0x7FFFFFFF + 1;
      while ( 1 )
      {
        v18 = *((_QWORD *)this + 7);
        v19 = *(__int64 (__fastcall **)(__int64, _QWORD, wchar_t *))(*(_QWORD *)v18 + 24LL);
        v20 = _ultow(v17, Buffer, 10);
        v21 = v19(v18, v29, v20);
        Instance = v21;
        if ( v21 != -2147024844 && v21 != -2147024713 )
          break;
        ++v16;
        v17 += 1 - 0x7FFFFFFF * (v17 / 0x7FFFFFFF);
        if ( v16 >= 0x7FFFFFFF )
          goto LABEL_31;
      }
      if ( v21 < 0 )
        goto LABEL_36;
LABEL_31:
      v22 = v21 < 0;
    }
    if ( v22
      || (v26 = *((_QWORD *)this + 7),
          v27 = *(__int64 (__fastcall **)(__int64, _QWORD, wchar_t *, _DWORD *))(*(_QWORD *)v26 + 72LL),
          v28 = _ultow(v17, Buffer, 10),
          Instance = v27(v26, v29, v28, v33),
          Instance < 0) )
    {
LABEL_36:
      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 7) + 144LL))(*((_QWORD *)this + 7), v29);
    }
    else
    {
      *v32 = v17;
      *a4 = v29;
    }
    return (unsigned int)Instance;
  }
  return result;
}

```

## disassembly

```asm
0x180010b44  push    rbp
0x180010b46  push    rbx
0x180010b47  push    rsi
0x180010b48  push    rdi
0x180010b49  push    r12
0x180010b4b  push    r13
0x180010b4d  push    r14
0x180010b4f  push    r15
0x180010b51  lea     rbp, [rsp-0Fh]
0x180010b56  sub     rsp, 0C8h
0x180010b5d  mov     rax, cs:__security_cookie
0x180010b64  xor     rax, rsp
0x180010b67  mov     [rbp+47h+var_48], rax
0x180010b6b  mov     r13, r9
0x180010b6e  mov     r15, r8
0x180010b71  mov     [rbp+47h+var_B8], rdx
0x180010b75  mov     r14, rcx
0x180010b78  mov     rax, [rbp+47h+arg_20]
0x180010b7c  mov     [rbp+47h+var_B0], rax
0x180010b80  mov     r12, [rbp+47h+arg_28]
0x180010b84  xor     r8d, r8d
0x180010b87  mov     [rbp+47h+var_BC], r8d
0x180010b8b  mov     [rbp+47h+var_A8], 3F9h
0x180010b92  lea     ecx, [r8+1]
0x180010b96  mov     [rbp+47h+var_A4], ecx
0x180010b99  mov     [rbp+47h+var_A0], ecx
0x180010b9c  mov     [rbp+47h+var_9C], ecx
0x180010b9f  mov     [rbp+47h+var_98], 4
0x180010ba7  lea     rcx, [rbp+47h+var_BC]
0x180010bab  mov     [rbp+47h+var_90], rcx
0x180010baf  mov     [rbp+47h+var_88], r8
0x180010bb3  mov     esi, r8d
0x180010bb6  mov     [rbp+47h+var_80], r8d
0x180010bba  lea     rdi, [r14+8]
0x180010bbe  mov     [rbp+47h+var_78], rdi
0x180010bc2  cmp     [r14+40h], r8b
0x180010bc6  jz      short loc_180010BCD
0x180010bc8  jmp     loc_180010C8B
0x180010bcd  mov     rcx, rdi; this
0x180010bd0  call    ?Lock@CSafeAutoCriticalSection@@QEAAKXZ; CSafeAutoCriticalSection::Lock(void)
0x180010bd5  mov     ebx, eax
0x180010bd7  xor     r8d, r8d
0x180010bda  test    eax, eax
0x180010bdc  lea     eax, [r8+1]
0x180010be0  cmovz   esi, eax
0x180010be3  mov     [rbp+47h+var_80], esi
0x180010be6  test    ebx, ebx
0x180010be8  jle     short loc_180010BF5
0x180010bea  movzx   ebx, bx
0x180010bed  or      ebx, 80070000h
0x180010bf3  test    ebx, ebx
0x180010bf5  jns     short loc_180010C0F
0x180010bf7  test    esi, esi
0x180010bf9  jz      short loc_180010C0A
0x180010bfb  cmp     [rdi+28h], eax
0x180010bfe  jnz     short loc_180010C0A
0x180010c00  mov     rcx, rdi; lpCriticalSection
0x180010c03  call    cs:__imp_LeaveCriticalSection
0x180010c09  nop
0x180010c0a  jmp     loc_180010E56
0x180010c0f  cmp     [r14+40h], r8b
0x180010c13  jnz     short loc_180010C4A
0x180010c15  lea     rax, [r14+38h]
0x180010c19  mov     [rsp+100h+ppv], rax; ppv
0x180010c1e  lea     r9, IID_IMSAdminBase_W; riid
0x180010c25  xor     edx, edx; pUnkOuter
0x180010c27  lea     r8d, [rdx+17h]; dwClsContext
0x180010c2b  lea     rcx, CLSID_MSAdminBase_W; rclsid
0x180010c32  call    cs:__imp_CoCreateInstance
0x180010c38  mov     ebx, eax
0x180010c3a  xor     r8d, r8d
0x180010c3d  test    eax, eax
0x180010c3f  setns   al
0x180010c42  mov     [r14+40h], al
0x180010c46  lea     eax, [r8+1]
0x180010c4a  test    esi, esi
0x180010c4c  jz      short loc_180010C66
0x180010c4e  cmp     [rdi+28h], eax
0x180010c51  jnz     short loc_180010C63
0x180010c53  mov     rcx, rdi; lpCriticalSection
0x180010c56  call    cs:__imp_LeaveCriticalSection
0x180010c5c  xor     r8d, r8d
0x180010c5f  lea     eax, [r8+1]
0x180010c63  mov     esi, r8d
0x180010c66  test    esi, esi
0x180010c68  jz      short loc_180010C7B
0x180010c6a  cmp     [rdi+28h], eax
0x180010c6d  jnz     short loc_180010C7B
0x180010c6f  mov     rcx, rdi; lpCriticalSection
0x180010c72  call    cs:__imp_LeaveCriticalSection
0x180010c78  xor     r8d, r8d
0x180010c7b  test    ebx, ebx
0x180010c7d  js      loc_180010E56
0x180010c83  mov     rax, [rbp+47h+var_B0]
0x180010c87  mov     rdx, [rbp+47h+var_B8]
0x180010c8b  mov     [rax], r8d
0x180010c8e  mov     [r13+0], r8d
0x180010c92  mov     [rbp+47h+var_C0], r8d
0x180010c96  xorps   xmm0, xmm0
0x180010c99  xor     eax, eax
0x180010c9b  movups  xmmword ptr [rbp+47h+Buffer], xmm0
0x180010c9f  movups  [rbp+47h+var_60], xmm0
0x180010ca3  mov     [rbp+47h+var_50], rax
0x180010ca7  mov     ebx, r8d
0x180010caa  mov     edi, 80070094h
0x180010caf  mov     rcx, [r14+38h]
0x180010cb3  mov     rax, [rcx]
0x180010cb6  lea     r8, [rbp+47h+var_C0]
0x180010cba  mov     [rsp+100h+var_D8], r8
0x180010cbf  mov     dword ptr [rsp+100h+ppv], 7530h
0x180010cc7  mov     r9d, 3
0x180010ccd  mov     r8, [rdx+8]
0x180010cd1  xor     edx, edx
0x180010cd3  mov     rax, [rax+88h]
0x180010cda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010cdf  cmp     eax, edi
0x180010ce1  jnz     short loc_180010CF5
0x180010ce3  inc     ebx
0x180010ce5  cmp     ebx, 1
0x180010ce8  mov     rdx, [rbp+47h+var_B8]
0x180010cec  jb      short loc_180010CAF
0x180010cee  mov     eax, edi
0x180010cf0  jmp     loc_180010E58
0x180010cf5  xor     edx, edx
0x180010cf7  test    eax, eax
0x180010cf9  js      loc_180010E58
0x180010cff  test    r12, r12
0x180010d02  jnz     loc_180010DC1
0x180010d08  mov     esi, edx
0x180010d0a  jmp     short loc_180010D1E
0x180010d0c  movzx   ecx, ax
0x180010d0f  and     ecx, 0FFDFh
0x180010d15  imul    esi, 65h ; 'e'
0x180010d18  add     esi, ecx
0x180010d1a  lea     r15, [r15+2]
0x180010d1e  movzx   eax, word ptr [r15]
0x180010d22  test    ax, ax
0x180010d25  jnz     short loc_180010D0C
0x180010d27  mov     r15d, edx
0x180010d2a  mov     r12d, 3
0x180010d30  mov     eax, r12d
0x180010d33  mul     esi
0x180010d35  mov     eax, esi
0x180010d37  sub     eax, edx
0x180010d39  shr     eax, 1
0x180010d3b  add     eax, edx
0x180010d3d  shr     eax, 1Eh
0x180010d40  imul    eax, 7FFFFFFFh
0x180010d46  sub     esi, eax
0x180010d48  inc     esi
0x180010d4a  mov     rdi, [r14+38h]
0x180010d4e  mov     rax, [rdi]
0x180010d51  mov     rbx, [rax+18h]
0x180010d55  mov     r8d, 0Ah; Radix
0x180010d5b  lea     rdx, [rbp+47h+Buffer]; Buffer
0x180010d5f  mov     ecx, esi; Value
0x180010d61  call    cs:__imp__ultow
0x180010d67  mov     r8, rax
0x180010d6a  mov     edx, [rbp+47h+var_C0]
0x180010d6d  mov     rcx, rdi
0x180010d70  mov     rax, rbx
0x180010d73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d78  mov     ebx, eax
0x180010d7a  cmp     eax, 80070034h
0x180010d7f  jz      short loc_180010D88
0x180010d81  cmp     eax, 800700B7h
0x180010d86  jnz     short loc_180010DB5
0x180010d88  inc     r15d
0x180010d8b  mov     eax, r12d
0x180010d8e  mul     esi
0x180010d90  mov     ecx, esi
0x180010d92  sub     ecx, edx
0x180010d94  shr     ecx, 1
0x180010d96  add     ecx, edx
0x180010d98  shr     ecx, 1Eh
0x180010d9b  imul    eax, ecx, 7FFFFFFFh
0x180010da1  mov     ecx, 1
0x180010da6  sub     ecx, eax
0x180010da8  add     esi, ecx
0x180010daa  cmp     r15d, 7FFFFFFFh
0x180010db1  jb      short loc_180010D4A
0x180010db3  jmp     short loc_180010DBD
0x180010db5  test    ebx, ebx
0x180010db7  js      loc_180010E40
0x180010dbd  test    ebx, ebx
0x180010dbf  jmp     short loc_180010DF7
0x180010dc1  mov     esi, [r12]
0x180010dc5  mov     rdi, [r14+38h]
0x180010dc9  mov     rax, [rdi]
0x180010dcc  mov     rbx, [rax+18h]
0x180010dd0  mov     r8d, 0Ah; Radix
0x180010dd6  lea     rdx, [rbp+47h+Buffer]; Buffer
0x180010dda  mov     ecx, esi; Value
0x180010ddc  call    cs:__imp__ultow
0x180010de2  mov     r8, rax
0x180010de5  mov     edx, [rbp+47h+var_C0]
0x180010de8  mov     rcx, rdi
0x180010deb  mov     rax, rbx
0x180010dee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010df3  mov     ebx, eax
0x180010df5  test    eax, eax
0x180010df7  js      short loc_180010E40
0x180010df9  mov     rdi, [r14+38h]
0x180010dfd  mov     rax, [rdi]
0x180010e00  mov     rbx, [rax+48h]
0x180010e04  mov     r8d, 0Ah; Radix
0x180010e0a  lea     rdx, [rbp+47h+Buffer]; Buffer
0x180010e0e  mov     ecx, esi; Value
0x180010e10  call    cs:__imp__ultow
0x180010e16  lea     r9, [rbp+47h+var_A8]
0x180010e1a  mov     r8, rax
0x180010e1d  mov     edx, [rbp+47h+var_C0]
0x180010e20  mov     rcx, rdi
0x180010e23  mov     rax, rbx
0x180010e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e2b  mov     ebx, eax
0x180010e2d  test    eax, eax
0x180010e2f  js      short loc_180010E40
0x180010e31  mov     rax, [rbp+47h+var_B0]
0x180010e35  mov     [rax], esi
0x180010e37  mov     eax, [rbp+47h+var_C0]
0x180010e3a  mov     [r13+0], eax
0x180010e3e  jmp     short loc_180010E56
0x180010e40  mov     rcx, [r14+38h]
0x180010e44  mov     rax, [rcx]
0x180010e47  mov     edx, [rbp+47h+var_C0]
0x180010e4a  mov     rax, [rax+90h]
0x180010e51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e56  mov     eax, ebx
0x180010e58  mov     rcx, [rbp+47h+var_48]
0x180010e5c  xor     rcx, rsp; StackCookie
0x180010e5f  call    __security_check_cookie
0x180010e64  add     rsp, 0C8h
0x180010e6b  pop     r15
0x180010e6d  pop     r14
0x180010e6f  pop     r13
0x180010e71  pop     r12
0x180010e73  pop     rdi
0x180010e74  pop     rsi
0x180010e75  pop     rbx
0x180010e76  pop     rbp
0x180010e77  retn
```
