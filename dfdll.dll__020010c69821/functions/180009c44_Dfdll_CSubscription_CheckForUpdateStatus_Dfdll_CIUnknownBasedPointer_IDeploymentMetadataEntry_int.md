# Dfdll::CSubscription::CheckForUpdateStatus(Dfdll::CIUnknownBasedPointer<IDeploymentMetadataEntry> &,int &)

- ea: `0x180009c44`
- end: `0x180009e09`
- name: `?CheckForUpdateStatus@CSubscription@Dfdll@@IEAAJAEAV?$CIUnknownBasedPointer@UIDeploymentMetadataEntry@@@2@AEAH@Z`
- size: `453`
- prototype: `__int64 __fastcall(Dfdll::CSubscription *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000a2ac`

## callees

- `0x180009c44`
- `0x18000a040`
- `0x18000d334`
- `0x18000d4c8`
- `0x180011ba8`
- `0x180012140`
- `0x180012b30`
- `0x180012bd0`
- `0x18001efd0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Dfdll::CSubscription::CheckForUpdateStatus(Dfdll::CSubscription *this, __int64 a2, _DWORD *a3)
{
  int MaximumAge; // ebx
  const struct std::nothrow_t *v7; // rdx
  const struct std::nothrow_t *v8; // rdx
  const struct std::nothrow_t *v9; // rdx
  unsigned __int8 v11[4]; // [rsp+40h] [rbp-49h] BYREF
  unsigned __int16 v12; // [rsp+44h] [rbp-45h] BYREF
  int v13; // [rsp+48h] [rbp-41h] BYREF
  void **v14; // [rsp+50h] [rbp-39h] BYREF
  void **v15; // [rsp+58h] [rbp-31h]
  unsigned __int16 *v16; // [rsp+60h] [rbp-29h]
  int v17; // [rsp+68h] [rbp-21h]
  int v18; // [rsp+70h] [rbp-19h]
  __int64 v19; // [rsp+78h] [rbp-11h] BYREF
  struct tagBLOB v20; // [rsp+80h] [rbp-9h] BYREF
  GUID v21; // [rsp+90h] [rbp+7h] BYREF

  MaximumAge = Dfdll::CSubscription::EnsureInitialization(this);
  if ( MaximumAge >= 0 )
  {
    v21 = CLSID_STORE_PROPSET;
    v12 = 0;
    v11[0] = 0;
    MaximumAge = Dfdll::CSubscription::GetMaximumAge(this, a2, &v12, v11);
    if ( MaximumAge >= 0 )
    {
      v13 = 0;
      MaximumAge = Dfdll::CSubscription::GetTimeInSeconds(this, &v13, v12, v11[0]);
      if ( MaximumAge >= 0 )
      {
        v14 = &Dfdll::CString::`vftable';
        v16 = 0;
        v17 = 0;
        v15 = &Dfdll::CBuffer<unsigned short>::`vftable';
        v18 = 0;
        MaximumAge = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, char *, GUID *, const wchar_t *, struct tagBLOB *))(**((_QWORD **)this + 16) + 136LL))(
                       *((_QWORD *)this + 16),
                       0,
                       *((_QWORD *)this + 8),
                       (char *)this + 200,
                       &v21,
                       L"LastCheckTime",
                       &v20);
        if ( MaximumAge >= 0 )
        {
          MaximumAge = Dfdll::CConvert::ToString(&v20, (struct Dfdll::CString *)&v14);
          if ( MaximumAge >= 0 )
          {
            v19 = 0;
            MaximumAge = Dfdll::CSubscription::TimeElapsedSince(this, &v19, v16);
            if ( MaximumAge >= 0 )
            {
              *a3 = v19 >= v13;
              MaximumAge = 0;
              v14 = &Dfdll::CString::`vftable';
              v15 = &Dfdll::CBuffer<unsigned short>::`vftable';
              if ( v16 )
                operator delete(v16, v9);
            }
            else
            {
              v14 = &Dfdll::CString::`vftable';
              v15 = &Dfdll::CBuffer<unsigned short>::`vftable';
              if ( v16 )
                operator delete(v16, v9);
            }
          }
          else
          {
            v14 = &Dfdll::CString::`vftable';
            v15 = &Dfdll::CBuffer<unsigned short>::`vftable';
            if ( v16 )
              operator delete(v16, v8);
          }
        }
        else
        {
          v14 = &Dfdll::CString::`vftable';
          v15 = &Dfdll::CBuffer<unsigned short>::`vftable';
          if ( v16 )
            operator delete(v16, v7);
        }
      }
    }
  }
  return (unsigned int)MaximumAge;
}

```

## disassembly

```asm
0x180009c44  push    rbp
0x180009c46  push    rbx
0x180009c47  push    rsi
0x180009c48  push    rdi
0x180009c49  push    r12
0x180009c4b  push    r14
0x180009c4d  push    r15
0x180009c4f  lea     rbp, [rsp-27h]
0x180009c54  sub     rsp, 0B0h
0x180009c5b  mov     rax, cs:__security_cookie
0x180009c62  xor     rax, rsp
0x180009c65  mov     [rbp+57h+var_40], rax
0x180009c69  mov     r14, r8
0x180009c6c  mov     rsi, rdx
0x180009c6f  mov     rdi, rcx
0x180009c72  call    ?EnsureInitialization@CSubscription@Dfdll@@IEAAJXZ; Dfdll::CSubscription::EnsureInitialization(void)
0x180009c77  mov     ebx, eax
0x180009c79  xor     r15d, r15d
0x180009c7c  test    eax, eax
0x180009c7e  js      loc_180009DE9
0x180009c84  movups  xmm0, xmmword ptr cs:CLSID_STORE_PROPSET.Data1
0x180009c8b  movdqu  [rbp+57h+var_50], xmm0
0x180009c90  mov     [rbp+57h+var_9C], r15w
0x180009c95  mov     [rbp+57h+var_A0], r15b
0x180009c99  lea     r9, [rbp+57h+var_A0]
0x180009c9d  lea     r8, [rbp+57h+var_9C]
0x180009ca1  mov     rdx, rsi
0x180009ca4  mov     rcx, rdi
0x180009ca7  call    ?GetMaximumAge@CSubscription@Dfdll@@IEAAJAEAV?$CIUnknownBasedPointer@UIDeploymentMetadataEntry@@@2@AEAGAEAE@Z; Dfdll::CSubscription::GetMaximumAge(Dfdll::CIUnknownBasedPointer<IDeploymentMetadataEntry> &,ushort &,uchar &)
0x180009cac  mov     ebx, eax
0x180009cae  test    eax, eax
0x180009cb0  js      loc_180009DE9
0x180009cb6  mov     [rbp+57h+var_98], r15d
0x180009cba  mov     r9b, [rbp+57h+var_A0]; unsigned __int8
0x180009cbe  movzx   r8d, [rbp+57h+var_9C]; unsigned __int16
0x180009cc3  lea     rdx, [rbp+57h+var_98]; int *
0x180009cc7  mov     rcx, rdi; this
0x180009cca  call    ?GetTimeInSeconds@CSubscription@Dfdll@@IEAAJAEAJGE@Z; Dfdll::CSubscription::GetTimeInSeconds(long &,ushort,uchar)
0x180009ccf  mov     ebx, eax
0x180009cd1  test    eax, eax
0x180009cd3  js      loc_180009DE9
0x180009cd9  lea     rsi, ??_7CString@Dfdll@@6B@; const Dfdll::CString::`vftable'
0x180009ce0  mov     [rbp+57h+var_90], rsi
0x180009ce4  mov     [rbp+57h+var_80], r15
0x180009ce8  mov     [rbp+57h+var_78], r15d
0x180009cec  lea     r12, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x180009cf3  mov     [rbp+57h+var_88], r12
0x180009cf7  mov     [rbp+57h+var_70], r15d
0x180009cfb  mov     rcx, [rdi+80h]
0x180009d02  mov     rax, [rcx]
0x180009d05  lea     r9, [rdi+0C8h]
0x180009d0c  lea     rdx, [rbp+57h+var_60]
0x180009d10  mov     [rsp+0E0h+var_B0], rdx
0x180009d15  lea     rdx, aLastchecktime; "LastCheckTime"
0x180009d1c  mov     [rsp+0E0h+var_B8], rdx
0x180009d21  lea     rdx, [rbp+57h+var_50]
0x180009d25  mov     [rsp+0E0h+var_C0], rdx
0x180009d2a  mov     r8, [rdi+40h]
0x180009d2e  xor     edx, edx
0x180009d30  mov     rax, [rax+88h]
0x180009d37  call    cs:__guard_dispatch_icall_fptr
0x180009d3d  mov     ebx, eax
0x180009d3f  test    eax, eax
0x180009d41  jns     short loc_180009D5F
0x180009d43  mov     [rbp+57h+var_90], rsi
0x180009d47  mov     [rbp+57h+var_88], r12
0x180009d4b  mov     rcx, [rbp+57h+var_80]; void *
0x180009d4f  test    rcx, rcx
0x180009d52  jz      short loc_180009D5A
0x180009d54  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009d59  nop
0x180009d5a  jmp     loc_180009DE9
0x180009d5f  lea     rdx, [rbp+57h+var_90]; struct Dfdll::CString *
0x180009d63  lea     rcx, [rbp+57h+var_60]; struct tagBLOB *
0x180009d67  call    ?ToString@CConvert@Dfdll@@SAJAEAUtagBLOB@@AEAVCString@2@@Z; Dfdll::CConvert::ToString(tagBLOB &,Dfdll::CString &)
0x180009d6c  mov     ebx, eax
0x180009d6e  test    eax, eax
0x180009d70  jns     short loc_180009D8B
0x180009d72  mov     [rbp+57h+var_90], rsi
0x180009d76  mov     [rbp+57h+var_88], r12
0x180009d7a  mov     rcx, [rbp+57h+var_80]; void *
0x180009d7e  test    rcx, rcx
0x180009d81  jz      short loc_180009D89
0x180009d83  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009d88  nop
0x180009d89  jmp     short loc_180009DE9
0x180009d8b  mov     [rbp+57h+var_68], r15
0x180009d8f  mov     r8, [rbp+57h+var_80]; unsigned __int16 *
0x180009d93  lea     rdx, [rbp+57h+var_68]; __int64 *
0x180009d97  mov     rcx, rdi; this
0x180009d9a  call    ?TimeElapsedSince@CSubscription@Dfdll@@IEAAJAEA_JPEBG@Z; Dfdll::CSubscription::TimeElapsedSince(__int64 &,ushort const *)
0x180009d9f  mov     ebx, eax
0x180009da1  test    eax, eax
0x180009da3  jns     short loc_180009DBE
0x180009da5  mov     [rbp+57h+var_90], rsi
0x180009da9  mov     [rbp+57h+var_88], r12
0x180009dad  mov     rcx, [rbp+57h+var_80]; void *
0x180009db1  test    rcx, rcx
0x180009db4  jz      short loc_180009DBC
0x180009db6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009dbb  nop
0x180009dbc  jmp     short loc_180009DE9
0x180009dbe  movsxd  rax, [rbp+57h+var_98]
0x180009dc2  mov     ecx, r15d
0x180009dc5  cmp     [rbp+57h+var_68], rax
0x180009dc9  setnl   cl
0x180009dcc  mov     [r14], ecx
0x180009dcf  mov     ebx, r15d
0x180009dd2  mov     [rbp+57h+var_90], rsi
0x180009dd6  mov     [rbp+57h+var_88], r12
0x180009dda  mov     rcx, [rbp+57h+var_80]; void *
0x180009dde  test    rcx, rcx
0x180009de1  jz      short loc_180009DE9
0x180009de3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009de8  nop
0x180009de9  mov     eax, ebx
0x180009deb  mov     rcx, [rbp+57h+var_40]
0x180009def  xor     rcx, rsp; StackCookie
0x180009df2  call    __security_check_cookie
0x180009df7  add     rsp, 0B0h
0x180009dfe  pop     r15
0x180009e00  pop     r14
0x180009e02  pop     r12
0x180009e04  pop     rdi
0x180009e05  pop     rsi
0x180009e06  pop     rbx
0x180009e07  pop     rbp
0x180009e08  retn
```
