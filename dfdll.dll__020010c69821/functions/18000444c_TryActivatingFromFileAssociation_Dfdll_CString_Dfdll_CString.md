# TryActivatingFromFileAssociation(Dfdll::CString &,Dfdll::CString &)

- ea: `0x18000444c`
- end: `0x180004580`
- name: `?TryActivatingFromFileAssociation@@YAJAEAVCString@Dfdll@@0@Z`
- size: `308`
- prototype: `__int64 __fastcall(struct Dfdll::CString *, struct Dfdll::CString *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180005400`

## callees

- `0x18000190c`
- `0x180002720`
- `0x180003168`
- `0x18000444c`
- `0x180008a14`
- `0x180008d34`
- `0x18000a2ac`
- `0x180010ea8`
- `0x180012bd0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TryActivatingFromFileAssociation(struct Dfdll::CString *a1, HKEY *a2)
{
  int ActivationInformation; // ebx
  __int64 v6; // [rsp+20h] [rbp-E0h] BYREF
  int v7; // [rsp+28h] [rbp-D8h]
  _QWORD v8[3]; // [rsp+30h] [rbp-D0h] BYREF
  int v9; // [rsp+48h] [rbp-B8h]
  int v10; // [rsp+50h] [rbp-B0h]
  _QWORD v11[3]; // [rsp+58h] [rbp-A8h] BYREF
  int v12; // [rsp+70h] [rbp-90h]
  int v13; // [rsp+78h] [rbp-88h]
  void **v14; // [rsp+80h] [rbp-80h]
  void **v15; // [rsp+88h] [rbp-78h]
  __int64 v16; // [rsp+90h] [rbp-70h]
  int v17; // [rsp+98h] [rbp-68h]
  int v18; // [rsp+A0h] [rbp-60h]
  int v19; // [rsp+A8h] [rbp-58h]
  _BYTE v20[240]; // [rsp+B0h] [rbp-50h] BYREF

  Dfdll::CSubscription::CSubscription((Dfdll::CSubscription *)v20);
  ActivationInformation = Dfdll::CSubscription::LoadFromSubscriptionId((Dfdll::CSubscription *)v20, a1);
  if ( ActivationInformation >= 0 )
  {
    v6 = 0;
    v7 = 0;
    v8[0] = &Dfdll::CString::`vftable';
    v8[2] = 0;
    v9 = 0;
    v8[1] = &Dfdll::CBuffer<unsigned short>::`vftable';
    v10 = 0;
    v11[0] = &Dfdll::CString::`vftable';
    v11[2] = 0;
    v12 = 0;
    v11[1] = &Dfdll::CBuffer<unsigned short>::`vftable';
    v13 = 0;
    v14 = &Dfdll::CString::`vftable';
    v16 = 0;
    v17 = 0;
    v15 = &Dfdll::CBuffer<unsigned short>::`vftable';
    v18 = 0;
    ActivationInformation = Dfdll::CSubscription::GetActivationInformation(
                              (Dfdll::CSubscription *)v20,
                              (struct Dfdll::ActivationInfo *)&v6);
    if ( ActivationInformation >= 0 )
    {
      if ( (_DWORD)v6 == 1 || v7 == 1 )
      {
        ActivationInformation = -2147024895;
      }
      else
      {
        ActivationInformation = LaunchApplication(v19, (__int64)v11, a2[2], 0);
        if ( ActivationInformation >= 0 )
        {
          if ( HIDWORD(v6) )
            CheckForUpdate((struct Dfdll::CString *)v8);
          ActivationInformation = 0;
        }
      }
    }
    Dfdll::ActivationInfo::~ActivationInfo((Dfdll::ActivationInfo *)&v6);
  }
  Dfdll::CSubscription::~CSubscription((Dfdll::CSubscription *)v20);
  return (unsigned int)ActivationInformation;
}

```

## disassembly

```asm
0x18000444c  mov     [rsp-8+arg_10], rbx
0x180004451  push    rbp
0x180004452  push    rsi
0x180004453  push    rdi
0x180004454  lea     rbp, [rsp-0B0h]
0x18000445c  sub     rsp, 1B0h
0x180004463  mov     rax, cs:__security_cookie
0x18000446a  xor     rax, rsp
0x18000446d  mov     [rbp+0C0h+var_20], rax
0x180004474  mov     rdi, rdx
0x180004477  mov     rbx, rcx
0x18000447a  lea     rcx, [rbp+0C0h+var_110]; this
0x18000447e  call    ??0CSubscription@Dfdll@@QEAA@XZ; Dfdll::CSubscription::CSubscription(void)
0x180004483  nop
0x180004484  mov     rdx, rbx; struct Dfdll::CString *
0x180004487  lea     rcx, [rbp+0C0h+var_110]; this
0x18000448b  call    ?LoadFromSubscriptionId@CSubscription@Dfdll@@QEAAJAEAVCString@2@@Z; Dfdll::CSubscription::LoadFromSubscriptionId(Dfdll::CString &)
0x180004490  mov     ebx, eax
0x180004492  xor     esi, esi
0x180004494  test    eax, eax
0x180004496  js      loc_180004553
0x18000449c  mov     [rsp+1C0h+var_1A0], rsi
0x1800044a1  mov     [rsp+1C0h+var_198], esi
0x1800044a5  lea     rcx, ??_7CString@Dfdll@@6B@; const Dfdll::CString::`vftable'
0x1800044ac  mov     [rsp+1C0h+var_190], rcx
0x1800044b1  mov     [rsp+1C0h+var_180], rsi
0x1800044b6  mov     [rsp+1C0h+var_178], esi
0x1800044ba  lea     rax, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x1800044c1  mov     [rsp+1C0h+var_188], rax
0x1800044c6  mov     [rsp+1C0h+var_170], esi
0x1800044ca  mov     [rsp+1C0h+var_168], rcx
0x1800044cf  mov     [rsp+1C0h+var_158], rsi
0x1800044d4  mov     [rsp+1C0h+var_150], esi
0x1800044d8  mov     [rsp+1C0h+var_160], rax
0x1800044dd  mov     [rsp+1C0h+var_148], esi
0x1800044e1  mov     [rbp+0C0h+var_140], rcx
0x1800044e5  mov     [rbp+0C0h+var_130], rsi
0x1800044e9  mov     [rbp+0C0h+var_128], esi
0x1800044ec  mov     [rbp+0C0h+var_138], rax
0x1800044f0  mov     [rbp+0C0h+var_120], esi
0x1800044f3  lea     rdx, [rsp+1C0h+var_1A0]; struct Dfdll::ActivationInfo *
0x1800044f8  lea     rcx, [rbp+0C0h+var_110]; this
0x1800044fc  call    ?GetActivationInformation@CSubscription@Dfdll@@QEAAJAEAUActivationInfo@2@@Z; Dfdll::CSubscription::GetActivationInformation(Dfdll::ActivationInfo &)
0x180004501  mov     ebx, eax
0x180004503  test    eax, eax
0x180004505  js      short loc_180004548
0x180004507  cmp     dword ptr [rsp+1C0h+var_1A0], 1
0x18000450c  jnz     short loc_180004515
0x18000450e  mov     ebx, 80070001h
0x180004513  jmp     short loc_180004548
0x180004515  cmp     [rsp+1C0h+var_198], 1
0x18000451a  jz      short loc_18000450E
0x18000451c  xor     r9d, r9d
0x18000451f  mov     r8, [rdi+10h]
0x180004523  lea     rdx, [rsp+1C0h+var_168]
0x180004528  mov     ecx, [rbp+0C0h+var_118]
0x18000452b  call    ?LaunchApplication@@YAJW4__MIDL___MIDL_itf_mscoree_0000_0000_0001@@AEAVCString@Dfdll@@PEBGI@Z; LaunchApplication(__MIDL___MIDL_itf_mscoree_0000_0000_0001,Dfdll::CString &,ushort const *,uint)
0x180004530  mov     ebx, eax
0x180004532  test    eax, eax
0x180004534  js      short loc_180004548
0x180004536  cmp     dword ptr [rsp+1C0h+var_1A0+4], esi
0x18000453a  jz      short loc_180004546
0x18000453c  lea     rcx, [rsp+1C0h+var_190]; struct Dfdll::CString *
0x180004541  call    ?CheckForUpdate@@YAJAEAVCString@Dfdll@@@Z; CheckForUpdate(Dfdll::CString &)
0x180004546  mov     ebx, esi
0x180004548  lea     rcx, [rsp+1C0h+var_1A0]; this
0x18000454d  call    ??1ActivationInfo@Dfdll@@QEAA@XZ; Dfdll::ActivationInfo::~ActivationInfo(void)
0x180004552  nop
0x180004553  lea     rcx, [rbp+0C0h+var_110]; this
0x180004557  call    ??1CSubscription@Dfdll@@QEAA@XZ; Dfdll::CSubscription::~CSubscription(void)
0x18000455c  mov     eax, ebx
0x18000455e  mov     rcx, [rbp+0C0h+var_20]
0x180004565  xor     rcx, rsp; StackCookie
0x180004568  call    __security_check_cookie
0x18000456d  mov     rbx, [rsp+1C0h+arg_10]
0x180004575  add     rsp, 1B0h
0x18000457c  pop     rdi
0x18000457d  pop     rsi
0x18000457e  pop     rbp
0x18000457f  retn
```
