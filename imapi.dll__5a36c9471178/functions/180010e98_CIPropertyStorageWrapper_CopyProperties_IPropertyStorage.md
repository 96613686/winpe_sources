# CIPropertyStorageWrapper::CopyProperties(IPropertyStorage * *)

- ea: `0x180010e98`
- end: `0x1800110a2`
- name: `?CopyProperties@CIPropertyStorageWrapper@@QEAAJPEAPEAUIPropertyStorage@@@Z`
- size: `522`
- prototype: `__int64 __fastcall(CIPropertyStorageWrapper *__hidden this, struct IPropertyStorage **)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, service_task`

## callers

- `0x1800064e0`
- `0x18000f850`

## callees

- `0x180001144`
- `0x18000115c`
- `0x18000b03c`
- `0x180010d40`
- `0x180010db8`
- `0x180010e98`
- `0x180019010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18001100d`
- `ole32!CoTaskMemFree` at `0x18001100d`
- `ole32!PropVariantClear` at `0x180011003`
- `ole32!PropVariantClear` at `0x180011003`

## pseudocode

```c
__int64 __fastcall CIPropertyStorageWrapper::CopyProperties(
        CIPropertyStorageWrapper *this,
        struct IPropertyStorage **a2)
{
  CIPropertyStorageWrapper *v5; // rax
  CIPropertyStorageWrapper *v6; // rax
  CIPropertyStorageWrapper *v7; // rbx
  __int64 v8; // rax
  BOOL v9; // esi
  unsigned int v10; // edi
  __int64 v11; // rcx
  __int128 v12; // [rsp+30h] [rbp-40h] BYREF
  LPVOID pv[2]; // [rsp+40h] [rbp-30h] BYREF
  PROPVARIANT pvar[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v15; // [rsp+60h] [rbp-10h]
  int v16; // [rsp+A8h] [rbp+38h] BYREF
  __int64 v17; // [rsp+B0h] [rbp+40h] BYREF

  if ( !a2 )
    return 2147944180LL;
  v5 = (CIPropertyStorageWrapper *)operator new(0x30u);
  if ( v5 && (v6 = CIPropertyStorageWrapper::CIPropertyStorageWrapper(v5), (v7 = v6) != 0) )
  {
    v8 = *(_QWORD *)v6;
    v17 = 0;
    v9 = 1;
    (*(void (__fastcall **)(CIPropertyStorageWrapper *))(v8 + 8))(v7);
    v10 = (*(__int64 (__fastcall **)(CIPropertyStorageWrapper *, __int64 *))(*(_QWORD *)this + 88LL))(this, &v17);
    if ( !v10 )
    {
      v11 = v17;
      if ( v17 )
      {
        v16 = 0;
        v9 = 0;
        v15 = 0;
        *(_OWORD *)pv = 0;
        v12 = 0;
        *(_OWORD *)pvar = 0;
        while ( !(*(unsigned int (__fastcall **)(__int64, __int64, LPVOID *, int *))(*(_QWORD *)v11 + 24LL))(
                   v11,
                   1,
                   pv,
                   &v16) )
        {
          LODWORD(v12) = 0;
          *((LPVOID *)&v12 + 1) = pv[0];
          v10 = (*(__int64 (__fastcall **)(CIPropertyStorageWrapper *, __int64, __int128 *, PROPVARIANT *))(*(_QWORD *)this + 24LL))(
                  this,
                  1,
                  &v12,
                  pvar);
          if ( v10 )
            goto LABEL_14;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
            WPP_SF_SD(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              v10 + 13,
              (unsigned int)WPP_de07cdecc1bf34ac651f6376ad8c6e00_Traceguids,
              DWORD2(v12),
              (char)pvar[1]);
          v10 = (*(__int64 (__fastcall **)(CIPropertyStorageWrapper *, __int64, __int128 *, PROPVARIANT *, _DWORD))(*(_QWORD *)v7 + 32LL))(
                  v7,
                  1,
                  &v12,
                  pvar,
                  pv[1]);
          if ( v10 )
LABEL_14:
            v9 = 1;
          PropVariantClear(pvar);
          CoTaskMemFree(pv[0]);
          pv[0] = 0;
          if ( v10 )
            break;
          v11 = v17;
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        if ( !v9 )
        {
          v10 = (**(__int64 (__fastcall ***)(CIPropertyStorageWrapper *, GUID *, struct IPropertyStorage **))v7)(
                  v7,
                  &GUID_00000138_0000_0000_c000_000000000046,
                  a2);
          v9 = v10 != 0;
        }
      }
    }
    (*(void (__fastcall **)(CIPropertyStorageWrapper *))(*(_QWORD *)v7 + 16LL))(v7);
    if ( v9 )
    {
      CIPropertyStorageWrapper::~CIPropertyStorageWrapper(v7);
      operator delete(v7);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v10;
}

```

## disassembly

```asm
0x180010e98  mov     [rsp-28h+arg_0], rbx
0x180010e9d  mov     [rsp-28h+arg_18], rsi
0x180010ea2  push    rbp
0x180010ea3  push    rdi
0x180010ea4  push    r13
0x180010ea6  push    r14
0x180010ea8  push    r15
0x180010eaa  mov     rbp, rsp
0x180010ead  sub     rsp, 70h
0x180010eb1  mov     r14, rdx
0x180010eb4  mov     r15, rcx
0x180010eb7  test    rdx, rdx
0x180010eba  jnz     short loc_180010EC6
0x180010ebc  mov     eax, 800706F4h
0x180010ec1  jmp     loc_180011089
0x180010ec6  mov     ecx, 30h ; '0'; Size
0x180010ecb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010ed0  test    rax, rax
0x180010ed3  jz      loc_180011082
0x180010ed9  mov     rcx, rax; this
0x180010edc  call    ??0CIPropertyStorageWrapper@@QEAA@XZ; CIPropertyStorageWrapper::CIPropertyStorageWrapper(void)
0x180010ee1  mov     rbx, rax
0x180010ee4  test    rax, rax
0x180010ee7  jz      loc_180011082
0x180010eed  mov     rax, [rax]
0x180010ef0  mov     r13d, 1
0x180010ef6  mov     rcx, rbx
0x180010ef9  mov     [rbp+arg_10], 0
0x180010f01  mov     esi, r13d
0x180010f04  mov     rax, [rax+8]
0x180010f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f0d  mov     rax, [r15]
0x180010f10  lea     rdx, [rbp+arg_10]
0x180010f14  mov     rcx, r15
0x180010f17  mov     rax, [rax+58h]
0x180010f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f20  mov     edi, eax
0x180010f22  test    eax, eax
0x180010f24  jnz     loc_18001105D
0x180010f2a  mov     rcx, [rbp+arg_10]
0x180010f2e  test    rcx, rcx
0x180010f31  jz      loc_18001105D
0x180010f37  xorps   xmm0, xmm0
0x180010f3a  mov     [rbp+arg_8], eax
0x180010f3d  xor     esi, esi
0x180010f3f  xorps   xmm1, xmm1
0x180010f42  xor     eax, eax
0x180010f44  mov     [rbp+var_10], rax
0x180010f48  movups  xmmword ptr [rbp+pv], xmm0
0x180010f4c  movups  [rbp+var_40], xmm1
0x180010f50  movups  xmmword ptr [rbp+pvar], xmm0
0x180010f54  mov     rax, [rcx]
0x180010f57  lea     r9, [rbp+arg_8]
0x180010f5b  lea     r8, [rbp+pv]
0x180010f5f  mov     edx, r13d
0x180010f62  mov     rax, [rax+18h]
0x180010f66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f6b  test    eax, eax
0x180010f6d  jnz     loc_180011028
0x180010f73  mov     dword ptr [rbp+var_40], eax
0x180010f76  lea     r9, [rbp+pvar]
0x180010f7a  mov     rax, [rbp+pv]
0x180010f7e  lea     r8, [rbp+var_40]
0x180010f82  mov     qword ptr [rbp+var_40+8], rax
0x180010f86  mov     edx, r13d
0x180010f89  mov     rax, [r15]
0x180010f8c  mov     rcx, r15
0x180010f8f  mov     rax, [rax+18h]
0x180010f93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f98  mov     edi, eax
0x180010f9a  test    eax, eax
0x180010f9c  jnz     short loc_180010FFC
0x180010f9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180010fa5  lea     rax, WPP_GLOBAL_Control
0x180010fac  cmp     rcx, rax
0x180010faf  jz      short loc_180010FD5
0x180010fb1  test    [rcx+44h], r13b
0x180010fb5  jz      short loc_180010FD5
0x180010fb7  mov     eax, dword ptr [rbp+pvar+8]
0x180010fba  lea     edx, [rdi+0Dh]
0x180010fbd  mov     r9, qword ptr [rbp+var_40+8]
0x180010fc1  lea     r8, WPP_de07cdecc1bf34ac651f6376ad8c6e00_Traceguids
0x180010fc8  mov     rcx, [rcx+38h]
0x180010fcc  mov     [rsp+70h+var_50], eax
0x180010fd0  call    WPP_SF_SD
0x180010fd5  mov     ecx, dword ptr [rbp+pv+8]
0x180010fd8  lea     r9, [rbp+pvar]
0x180010fdc  mov     rax, [rbx]
0x180010fdf  lea     r8, [rbp+var_40]
0x180010fe3  mov     [rsp+70h+var_50], ecx
0x180010fe7  mov     edx, r13d
0x180010fea  mov     rcx, rbx
0x180010fed  mov     rax, [rax+20h]
0x180010ff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ff6  mov     edi, eax
0x180010ff8  test    eax, eax
0x180010ffa  jz      short loc_180010FFF
0x180010ffc  mov     esi, r13d
0x180010fff  lea     rcx, [rbp+pvar]; pvar
0x180011003  call    cs:__imp_PropVariantClear
0x180011009  mov     rcx, [rbp+pv]; pv
0x18001100d  call    cs:__imp_CoTaskMemFree
0x180011013  mov     [rbp+pv], 0
0x18001101b  test    edi, edi
0x18001101d  jnz     short loc_180011028
0x18001101f  mov     rcx, [rbp+arg_10]
0x180011023  jmp     loc_180010F54
0x180011028  mov     rcx, [rbp+arg_10]
0x18001102c  mov     rax, [rcx]
0x18001102f  mov     rax, [rax+10h]
0x180011033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011038  test    esi, esi
0x18001103a  jnz     short loc_18001105D
0x18001103c  mov     rax, [rbx]
0x18001103f  lea     rdx, _GUID_00000138_0000_0000_c000_000000000046
0x180011046  mov     r8, r14
0x180011049  mov     rcx, rbx
0x18001104c  mov     rax, [rax]
0x18001104f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011054  mov     edi, eax
0x180011056  test    eax, eax
0x180011058  jz      short loc_18001105D
0x18001105a  mov     esi, r13d
0x18001105d  mov     rax, [rbx]
0x180011060  mov     rcx, rbx
0x180011063  mov     rax, [rax+10h]
0x180011067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001106c  test    esi, esi
0x18001106e  jz      short loc_180011087
0x180011070  mov     rcx, rbx; this
0x180011073  call    ??1CIPropertyStorageWrapper@@QEAA@XZ; CIPropertyStorageWrapper::~CIPropertyStorageWrapper(void)
0x180011078  mov     rcx, rbx; Block
0x18001107b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011080  jmp     short loc_180011087
0x180011082  mov     edi, 8007000Eh
0x180011087  mov     eax, edi
0x180011089  lea     r11, [rsp+70h+var_s0]
0x18001108e  mov     rbx, [r11+30h]
0x180011092  mov     rsi, [r11+48h]
0x180011096  mov     rsp, r11
0x180011099  pop     r15
0x18001109b  pop     r14
0x18001109d  pop     r13
0x18001109f  pop     rdi
0x1800110a0  pop     rbp
0x1800110a1  retn
```
