# Dfdll::CSubscription::CheckShellVisibility(int &)

- ea: `0x180009e0c`
- end: `0x180009f9c`
- name: `?CheckShellVisibility@CSubscription@Dfdll@@IEAAJAEAH@Z`
- size: `400`
- prototype: `__int64 __fastcall(Dfdll::CSubscription *__hidden this, int *)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000a2ac`
- `0x18000aa14`
- `0x18000ab8c`
- `0x18000cac8`

## callees

- `0x180009e0c`
- `0x18000a040`
- `0x18000a21c`
- `0x180012140`
- `0x180012b30`
- `0x180012bd0`
- `0x18001efd0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Dfdll::CSubscription::CheckShellVisibility(Dfdll::CSubscription *this, int *a2)
{
  int v4; // ebx
  const struct std::nothrow_t *v5; // rdx
  const struct std::nothrow_t *v6; // rdx
  bool v8; // [rsp+40h] [rbp-29h] BYREF
  void **v9; // [rsp+48h] [rbp-21h] BYREF
  void **v10; // [rsp+50h] [rbp-19h]
  void *v11; // [rsp+58h] [rbp-11h]
  int v12; // [rsp+60h] [rbp-9h]
  int v13; // [rsp+68h] [rbp-1h]
  struct tagBLOB v14; // [rsp+70h] [rbp+7h] BYREF
  GUID v15; // [rsp+80h] [rbp+17h] BYREF

  v4 = Dfdll::CSubscription::EnsureInitialization(this);
  if ( v4 >= 0 )
  {
    if ( *((_QWORD *)this + 8) )
    {
      v15 = CLSID_STORE_PROPSET;
      *a2 = 1;
      v9 = &Dfdll::CString::`vftable';
      v11 = 0;
      v12 = 0;
      v10 = &Dfdll::CBuffer<unsigned short>::`vftable';
      v13 = 0;
      v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, char *, GUID *, const wchar_t *, struct tagBLOB *))(**((_QWORD **)this + 16) + 136LL))(
             *((_QWORD *)this + 16),
             0,
             *((_QWORD *)this + 8),
             (char *)this + 200,
             &v15,
             L"IsShellVisible",
             &v14);
      if ( v4 >= 0 )
      {
        v4 = Dfdll::CConvert::ToString(&v14, (struct Dfdll::CString *)&v9);
        if ( v4 >= 0 )
        {
          v8 = 0;
          v4 = Dfdll::CString::Equals((Dfdll::CString *)&v9, L"True", &v8);
          if ( v4 < 0 )
          {
            v9 = &Dfdll::CString::`vftable';
            v10 = &Dfdll::CBuffer<unsigned short>::`vftable';
            if ( v11 )
              operator delete(v11, v6);
          }
          else
          {
            *a2 = v8;
            v4 = 0;
            v9 = &Dfdll::CString::`vftable';
            v10 = &Dfdll::CBuffer<unsigned short>::`vftable';
            if ( v11 )
              operator delete(v11, v6);
          }
        }
        else
        {
          v9 = &Dfdll::CString::`vftable';
          v10 = &Dfdll::CBuffer<unsigned short>::`vftable';
          if ( v11 )
            operator delete(v11, v5);
        }
      }
      else
      {
        v9 = &Dfdll::CString::`vftable';
        v10 = &Dfdll::CBuffer<unsigned short>::`vftable';
      }
    }
    else
    {
      return (unsigned int)-2147023537;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180009e0c  mov     [rsp-8+arg_10], rbx
0x180009e11  push    rbp
0x180009e12  push    rsi
0x180009e13  push    rdi
0x180009e14  push    r12
0x180009e16  push    r15
0x180009e18  lea     rbp, [rsp-37h]
0x180009e1d  sub     rsp, 0A0h
0x180009e24  mov     rax, cs:__security_cookie
0x180009e2b  xor     rax, rsp
0x180009e2e  mov     [rbp+57h+var_30], rax
0x180009e32  mov     rsi, rdx
0x180009e35  mov     rdi, rcx
0x180009e38  call    ?EnsureInitialization@CSubscription@Dfdll@@IEAAJXZ; Dfdll::CSubscription::EnsureInitialization(void)
0x180009e3d  mov     ebx, eax
0x180009e3f  test    eax, eax
0x180009e41  js      loc_180009F77
0x180009e47  cmp     qword ptr [rdi+40h], 0
0x180009e4c  jnz     short loc_180009E58
0x180009e4e  mov     ebx, 8007054Fh
0x180009e53  jmp     loc_180009F77
0x180009e58  movups  xmm0, xmmword ptr cs:CLSID_STORE_PROPSET.Data1
0x180009e5f  movdqu  [rbp+57h+var_40], xmm0
0x180009e64  mov     dword ptr [rsi], 1
0x180009e6a  lea     r15, ??_7CString@Dfdll@@6B@; const Dfdll::CString::`vftable'
0x180009e71  mov     [rbp+57h+var_78], r15
0x180009e75  and     [rbp+57h+var_68], 0
0x180009e7a  and     [rbp+57h+var_60], 0
0x180009e7e  lea     r12, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x180009e85  mov     [rbp+57h+var_70], r12
0x180009e89  and     [rbp+57h+var_58], 0
0x180009e8d  mov     rcx, [rdi+80h]
0x180009e94  mov     rax, [rcx]
0x180009e97  lea     r9, [rdi+0C8h]
0x180009e9e  lea     rdx, [rbp+57h+var_50]
0x180009ea2  mov     [rsp+0C0h+var_90], rdx
0x180009ea7  lea     rdx, aIsshellvisible; "IsShellVisible"
0x180009eae  mov     [rsp+0C0h+var_98], rdx
0x180009eb3  lea     rdx, [rbp+57h+var_40]
0x180009eb7  mov     [rsp+0C0h+var_A0], rdx
0x180009ebc  mov     r8, [rdi+40h]
0x180009ec0  xor     edx, edx
0x180009ec2  mov     rax, [rax+88h]
0x180009ec9  call    cs:__guard_dispatch_icall_fptr
0x180009ecf  mov     ebx, eax
0x180009ed1  test    eax, eax
0x180009ed3  jns     short loc_180009EF1
0x180009ed5  mov     [rbp+57h+var_78], r15
0x180009ed9  mov     [rbp+57h+var_70], r12
0x180009edd  mov     rcx, [rbp+57h+var_68]; void *
0x180009ee1  test    rcx, rcx
0x180009ee4  jz      short loc_180009EEC
0x180009ee6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009eeb  nop
0x180009eec  jmp     loc_180009F77
0x180009ef1  lea     rdx, [rbp+57h+var_78]; struct Dfdll::CString *
0x180009ef5  lea     rcx, [rbp+57h+var_50]; struct tagBLOB *
0x180009ef9  call    ?ToString@CConvert@Dfdll@@SAJAEAUtagBLOB@@AEAVCString@2@@Z; Dfdll::CConvert::ToString(tagBLOB &,Dfdll::CString &)
0x180009efe  mov     ebx, eax
0x180009f00  test    eax, eax
0x180009f02  jns     short loc_180009F1D
0x180009f04  mov     [rbp+57h+var_78], r15
0x180009f08  mov     [rbp+57h+var_70], r12
0x180009f0c  mov     rcx, [rbp+57h+var_68]; void *
0x180009f10  test    rcx, rcx
0x180009f13  jz      short loc_180009F1B
0x180009f15  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009f1a  nop
0x180009f1b  jmp     short loc_180009F77
0x180009f1d  mov     [rbp+57h+var_80], 0
0x180009f21  lea     r8, [rbp+57h+var_80]; bool *
0x180009f25  lea     rdx, aTrue; "True"
0x180009f2c  lea     rcx, [rbp+57h+var_78]; this
0x180009f30  call    ?Equals@CString@Dfdll@@QEAAJPEBGAEA_N@Z; Dfdll::CString::Equals(ushort const *,bool &)
0x180009f35  mov     ebx, eax
0x180009f37  test    eax, eax
0x180009f39  js      short loc_180009F60
0x180009f3b  xor     eax, eax
0x180009f3d  cmp     [rbp+57h+var_80], al
0x180009f40  setnz   al
0x180009f43  mov     [rsi], eax
0x180009f45  xor     ebx, ebx
0x180009f47  mov     [rbp+57h+var_78], r15
0x180009f4b  mov     [rbp+57h+var_70], r12
0x180009f4f  mov     rcx, [rbp+57h+var_68]; void *
0x180009f53  test    rcx, rcx
0x180009f56  jz      short loc_180009F5E
0x180009f58  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009f5d  nop
0x180009f5e  jmp     short loc_180009F77
0x180009f60  mov     [rbp+57h+var_78], r15
0x180009f64  mov     [rbp+57h+var_70], r12
0x180009f68  mov     rcx, [rbp+57h+var_68]; void *
0x180009f6c  test    rcx, rcx
0x180009f6f  jz      short loc_180009F77
0x180009f71  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009f76  nop
0x180009f77  mov     eax, ebx
0x180009f79  mov     rcx, [rbp+57h+var_30]
0x180009f7d  xor     rcx, rsp; StackCookie
0x180009f80  call    __security_check_cookie
0x180009f85  mov     rbx, [rsp+0C0h+arg_10]
0x180009f8d  add     rsp, 0A0h
0x180009f94  pop     r15
0x180009f96  pop     r12
0x180009f98  pop     rdi
0x180009f99  pop     rsi
0x180009f9a  pop     rbp
0x180009f9b  retn
```
