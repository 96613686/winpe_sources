# Dfdll::CSubscription::LoadIdentities(void)

- ea: `0x180010f34`
- end: `0x180011225`
- name: `?LoadIdentities@CSubscription@Dfdll@@IEAAJXZ`
- size: `753`
- prototype: `__int64 __fastcall(Dfdll::CSubscription *__hidden this)`
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000a2ac`
- `0x18000aa14`
- `0x18000d9b8`
- `0x180010bf4`

## callees

- `0x18000a040`
- `0x18000c8e8`
- `0x180010f34`
- `0x180012140`
- `0x180012bd0`
- `0x18001efd0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Dfdll::CSubscription::LoadIdentities(Dfdll::CSubscription *this)
{
  int DefinitionAppIdentityFromText; // ebx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  int v7; // [rsp+40h] [rbp-40h] BYREF
  void **v8; // [rsp+48h] [rbp-38h]
  __int64 v9; // [rsp+50h] [rbp-30h] BYREF
  struct tagBLOB v10; // [rsp+58h] [rbp-28h] BYREF
  GUID v11; // [rsp+68h] [rbp-18h] BYREF

  if ( *((_QWORD *)this + 8) )
  {
    DefinitionAppIdentityFromText = Dfdll::CSubscription::EnsureInitialization(this);
    if ( DefinitionAppIdentityFromText >= 0 )
    {
      v11 = CLSID_STORE_PROPSET;
      v3 = *((_QWORD *)this + 10);
      if ( v3 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
      *((_QWORD *)this + 10) = 0;
      v4 = *((_QWORD *)this + 12);
      if ( v4 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
      *((_QWORD *)this + 12) = 0;
      v5 = *((_QWORD *)this + 14);
      if ( v5 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      *((_QWORD *)this + 14) = 0;
      DefinitionAppIdentityFromText = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, char *, GUID *, const wchar_t *, struct tagBLOB *))(**((_QWORD **)this + 16) + 136LL))(
                                        *((_QWORD *)this + 16),
                                        0,
                                        *((_QWORD *)this + 8),
                                        (char *)this + 200,
                                        &v11,
                                        L"CurrentBind",
                                        &v10);
      if ( DefinitionAppIdentityFromText >= 0 )
      {
        DefinitionAppIdentityFromText = Dfdll::CConvert::ToString(&v10, this);
        if ( DefinitionAppIdentityFromText >= 0 )
        {
          DefinitionAppIdentityFromText = Dfdll::CSubscription::GetDefinitionAppIdentityFromText(
                                            this,
                                            this,
                                            (char *)this + 72);
          if ( DefinitionAppIdentityFromText >= 0 )
          {
            v9 = 0;
            v8 = &Dfdll::CIUnknownBasedPointer<IEnumDefinitionIdentity>::`vftable';
            v7 = 0;
            DefinitionAppIdentityFromText = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 10)
                                                                                         + 56LL))(
                                              *((_QWORD *)this + 10),
                                              &v9);
            if ( DefinitionAppIdentityFromText >= 0 )
            {
              DefinitionAppIdentityFromText = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 40LL))(v9);
              if ( DefinitionAppIdentityFromText >= 0 )
              {
                DefinitionAppIdentityFromText = (*(__int64 (__fastcall **)(__int64, __int64, char *, int *))(*(_QWORD *)v9 + 24LL))(
                                                  v9,
                                                  1,
                                                  (char *)this + 96,
                                                  &v7);
                if ( DefinitionAppIdentityFromText >= 0 )
                {
                  if ( v7 )
                  {
                    DefinitionAppIdentityFromText = (*(__int64 (__fastcall **)(__int64, __int64, char *, int *))(*(_QWORD *)v9 + 24LL))(
                                                      v9,
                                                      1,
                                                      (char *)this + 112,
                                                      &v7);
                    if ( DefinitionAppIdentityFromText >= 0 )
                    {
                      if ( v7 )
                      {
                        DefinitionAppIdentityFromText = 0;
                        v8 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
                        if ( v9 )
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
                      }
                      else
                      {
                        DefinitionAppIdentityFromText = -2147024883;
                        v8 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
                        if ( v9 )
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
                      }
                    }
                    else
                    {
                      v8 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
                      if ( v9 )
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
                    }
                  }
                  else
                  {
                    DefinitionAppIdentityFromText = -2147024883;
                    v8 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
                    if ( v9 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
                  }
                }
                else
                {
                  v8 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
                  if ( v9 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
                }
              }
              else
              {
                v8 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
                if ( v9 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
              }
            }
            else
            {
              v8 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
              if ( v9 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
            }
          }
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147023893;
  }
  return (unsigned int)DefinitionAppIdentityFromText;
}

```

## disassembly

```asm
0x180010f34  mov     [rsp-18h+arg_8], rbx
0x180010f39  mov     [rsp-18h+arg_10], rsi
0x180010f3e  push    rbp
0x180010f3f  push    rdi
0x180010f40  push    r14
0x180010f42  mov     rbp, rsp
0x180010f45  sub     rsp, 80h
0x180010f4c  mov     rax, cs:__security_cookie
0x180010f53  xor     rax, rsp
0x180010f56  mov     [rbp+var_8], rax
0x180010f5a  mov     rdi, rcx
0x180010f5d  cmp     qword ptr [rcx+40h], 0
0x180010f62  jnz     short loc_180010F6E
0x180010f64  mov     ebx, 800703EBh
0x180010f69  jmp     loc_1800111FF
0x180010f6e  call    ?EnsureInitialization@CSubscription@Dfdll@@IEAAJXZ; Dfdll::CSubscription::EnsureInitialization(void)
0x180010f73  mov     ebx, eax
0x180010f75  test    eax, eax
0x180010f77  js      loc_1800111FF
0x180010f7d  movups  xmm0, xmmword ptr cs:CLSID_STORE_PROPSET.Data1
0x180010f84  movdqu  [rbp+var_18], xmm0
0x180010f89  mov     rcx, [rdi+50h]
0x180010f8d  test    rcx, rcx
0x180010f90  jz      short loc_180010F9F
0x180010f92  mov     rax, [rcx]
0x180010f95  mov     rax, [rax+10h]
0x180010f99  call    cs:__guard_dispatch_icall_fptr
0x180010f9f  and     qword ptr [rdi+50h], 0
0x180010fa4  lea     rsi, [rdi+60h]
0x180010fa8  mov     rcx, [rsi]
0x180010fab  test    rcx, rcx
0x180010fae  jz      short loc_180010FBD
0x180010fb0  mov     rax, [rcx]
0x180010fb3  mov     rax, [rax+10h]
0x180010fb7  call    cs:__guard_dispatch_icall_fptr
0x180010fbd  and     qword ptr [rsi], 0
0x180010fc1  mov     rcx, [rdi+70h]
0x180010fc5  test    rcx, rcx
0x180010fc8  jz      short loc_180010FD7
0x180010fca  mov     rax, [rcx]
0x180010fcd  mov     rax, [rax+10h]
0x180010fd1  call    cs:__guard_dispatch_icall_fptr
0x180010fd7  and     qword ptr [rdi+70h], 0
0x180010fdc  mov     rcx, [rdi+80h]
0x180010fe3  mov     rax, [rcx]
0x180010fe6  lea     r9, [rdi+0C8h]
0x180010fed  lea     rdx, [rbp+var_28]
0x180010ff1  mov     [rsp+80h+var_50], rdx
0x180010ff6  lea     rdx, aCurrentbind; "CurrentBind"
0x180010ffd  mov     [rsp+80h+var_58], rdx
0x180011002  lea     rdx, [rbp+var_18]
0x180011006  mov     [rsp+80h+var_60], rdx
0x18001100b  mov     r8, [rdi+40h]
0x18001100f  xor     edx, edx
0x180011011  mov     rax, [rax+88h]
0x180011018  call    cs:__guard_dispatch_icall_fptr
0x18001101e  mov     ebx, eax
0x180011020  test    eax, eax
0x180011022  js      loc_1800111FF
0x180011028  mov     rdx, rdi; struct Dfdll::CString *
0x18001102b  lea     rcx, [rbp+var_28]; struct tagBLOB *
0x18001102f  call    ?ToString@CConvert@Dfdll@@SAJAEAUtagBLOB@@AEAVCString@2@@Z; Dfdll::CConvert::ToString(tagBLOB &,Dfdll::CString &)
0x180011034  mov     ebx, eax
0x180011036  test    eax, eax
0x180011038  js      loc_1800111FF
0x18001103e  lea     r8, [rdi+48h]
0x180011042  mov     rdx, rdi
0x180011045  mov     rcx, rdi
0x180011048  call    ?GetDefinitionAppIdentityFromText@CSubscription@Dfdll@@IEAAJAEAVCString@2@AEAV?$CIUnknownBasedPointer@UIDefinitionAppId@@@2@@Z; Dfdll::CSubscription::GetDefinitionAppIdentityFromText(Dfdll::CString &,Dfdll::CIUnknownBasedPointer<IDefinitionAppId> &)
0x18001104d  mov     ebx, eax
0x18001104f  test    eax, eax
0x180011051  js      loc_1800111FF
0x180011057  and     [rbp+var_30], 0
0x18001105c  lea     rax, ??_7?$CIUnknownBasedPointer@UIEnumDefinitionIdentity@@@Dfdll@@6B@; const Dfdll::CIUnknownBasedPointer<IEnumDefinitionIdentity>::`vftable'
0x180011063  mov     [rbp+var_38], rax
0x180011067  and     [rbp+var_40], 0
0x18001106b  mov     rcx, [rdi+50h]
0x18001106f  mov     rax, [rcx]
0x180011072  lea     rdx, [rbp+var_30]
0x180011076  mov     rax, [rax+38h]
0x18001107a  call    cs:__guard_dispatch_icall_fptr
0x180011080  mov     ebx, eax
0x180011082  test    eax, eax
0x180011084  jns     short loc_1800110AD
0x180011086  lea     rax, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x18001108d  mov     [rbp+var_38], rax
0x180011091  mov     rcx, [rbp+var_30]
0x180011095  test    rcx, rcx
0x180011098  jz      short loc_1800110A8
0x18001109a  mov     rax, [rcx]
0x18001109d  mov     rax, [rax+10h]
0x1800110a1  call    cs:__guard_dispatch_icall_fptr
0x1800110a7  nop
0x1800110a8  jmp     loc_1800111FF
0x1800110ad  mov     rcx, [rbp+var_30]
0x1800110b1  mov     rax, [rcx]
0x1800110b4  mov     rax, [rax+28h]
0x1800110b8  call    cs:__guard_dispatch_icall_fptr
0x1800110be  mov     ebx, eax
0x1800110c0  test    eax, eax
0x1800110c2  jns     short loc_1800110EB
0x1800110c4  lea     rax, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x1800110cb  mov     [rbp+var_38], rax
0x1800110cf  mov     rcx, [rbp+var_30]
0x1800110d3  test    rcx, rcx
0x1800110d6  jz      short loc_1800110E6
0x1800110d8  mov     rax, [rcx]
0x1800110db  mov     rax, [rax+10h]
0x1800110df  call    cs:__guard_dispatch_icall_fptr
0x1800110e5  nop
0x1800110e6  jmp     loc_1800111FF
0x1800110eb  mov     rcx, [rbp+var_30]
0x1800110ef  mov     rax, [rcx]
0x1800110f2  lea     r9, [rbp+var_40]
0x1800110f6  mov     r8, rsi
0x1800110f9  mov     esi, 1
0x1800110fe  mov     edx, esi
0x180011100  mov     rax, [rax+18h]
0x180011104  call    cs:__guard_dispatch_icall_fptr
0x18001110a  mov     ebx, eax
0x18001110c  test    eax, eax
0x18001110e  jns     short loc_180011137
0x180011110  lea     rax, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x180011117  mov     [rbp+var_38], rax
0x18001111b  mov     rcx, [rbp+var_30]
0x18001111f  test    rcx, rcx
0x180011122  jz      short loc_180011132
0x180011124  mov     rax, [rcx]
0x180011127  mov     rax, [rax+10h]
0x18001112b  call    cs:__guard_dispatch_icall_fptr
0x180011131  nop
0x180011132  jmp     loc_1800111FF
0x180011137  cmp     [rbp+var_40], esi
0x18001113a  jnb     short loc_180011168
0x18001113c  mov     ebx, 8007000Dh
0x180011141  lea     rax, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x180011148  mov     [rbp+var_38], rax
0x18001114c  mov     rcx, [rbp+var_30]
0x180011150  test    rcx, rcx
0x180011153  jz      short loc_180011163
0x180011155  mov     rax, [rcx]
0x180011158  mov     rax, [rax+10h]
0x18001115c  call    cs:__guard_dispatch_icall_fptr
0x180011162  nop
0x180011163  jmp     loc_1800111FF
0x180011168  mov     rcx, [rbp+var_30]
0x18001116c  mov     rax, [rcx]
0x18001116f  lea     r8, [rdi+70h]
0x180011173  lea     r9, [rbp+var_40]
0x180011177  mov     edx, esi
0x180011179  mov     rax, [rax+18h]
0x18001117d  call    cs:__guard_dispatch_icall_fptr
0x180011183  mov     ebx, eax
0x180011185  test    eax, eax
0x180011187  jns     short loc_1800111AD
0x180011189  lea     rax, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x180011190  mov     [rbp+var_38], rax
0x180011194  mov     rcx, [rbp+var_30]
0x180011198  test    rcx, rcx
0x18001119b  jz      short loc_1800111AB
0x18001119d  mov     rax, [rcx]
0x1800111a0  mov     rax, [rax+10h]
0x1800111a4  call    cs:__guard_dispatch_icall_fptr
0x1800111aa  nop
0x1800111ab  jmp     short loc_1800111FF
0x1800111ad  cmp     [rbp+var_40], esi
0x1800111b0  jnb     short loc_1800111DB
0x1800111b2  mov     ebx, 8007000Dh
0x1800111b7  lea     rax, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x1800111be  mov     [rbp+var_38], rax
0x1800111c2  mov     rcx, [rbp+var_30]
0x1800111c6  test    rcx, rcx
0x1800111c9  jz      short loc_1800111D9
0x1800111cb  mov     rax, [rcx]
0x1800111ce  mov     rax, [rax+10h]
0x1800111d2  call    cs:__guard_dispatch_icall_fptr
0x1800111d8  nop
0x1800111d9  jmp     short loc_1800111FF
0x1800111db  xor     ebx, ebx
0x1800111dd  lea     rax, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x1800111e4  mov     [rbp+var_38], rax
0x1800111e8  mov     rcx, [rbp+var_30]
0x1800111ec  test    rcx, rcx
0x1800111ef  jz      short loc_1800111FF
0x1800111f1  mov     rax, [rcx]
0x1800111f4  mov     rax, [rax+10h]
0x1800111f8  call    cs:__guard_dispatch_icall_fptr
0x1800111fe  nop
0x1800111ff  mov     eax, ebx
0x180011201  mov     rcx, [rbp+var_8]
0x180011205  xor     rcx, rsp; StackCookie
0x180011208  call    __security_check_cookie
0x18001120d  lea     r11, [rsp+80h+var_s0]
0x180011215  mov     rbx, [r11+28h]
0x180011219  mov     rsi, [r11+30h]
0x18001121d  mov     rsp, r11
0x180011220  pop     r14
0x180011222  pop     rdi
0x180011223  pop     rbp
0x180011224  retn
```
