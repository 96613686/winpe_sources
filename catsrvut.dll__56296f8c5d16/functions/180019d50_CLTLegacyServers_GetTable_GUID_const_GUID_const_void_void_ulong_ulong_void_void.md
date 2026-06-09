# CLTLegacyServers::GetTable(_GUID const &,_GUID const &,void *,void *,ulong,ulong,void *,void * *)

- ea: `0x180019d50`
- end: `0x18001a0b2`
- name: `?GetTable@CLTLegacyServers@@UEAAJAEBU_GUID@@0PEAX1KK1PEAPEAX@Z`
- size: `866`
- prototype: `__int64 __fastcall(CLTLegacyServers *__hidden this, const struct _GUID *, const struct _GUID *, void *, void *, unsigned int, unsigned int, void *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180019d50`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019de5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019de5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a041`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a041`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019e6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019e6e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLTLegacyServers::GetTable(
        CLTLegacyServers *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        _DWORD *a4,
        void *a5,
        unsigned int a6,
        unsigned int a7,
        void *a8,
        void **a9)
{
  HRESULT v10; // ebx
  __int64 (**v11)[2]; // r9
  _DWORD *v12; // rdi
  __int64 i; // rsi
  HRESULT v14; // eax
  unsigned __int64 v15; // rcx
  _DWORD *v17; // [rsp+50h] [rbp-10h] BYREF
  __int64 v18; // [rsp+58h] [rbp-8h] BYREF
  __int64 v19; // [rsp+90h] [rbp+30h] BYREF
  LPVOID ppv; // [rsp+A8h] [rbp+48h] BYREF

  ppv = 0;
  v19 = 0;
  v18 = 0;
  v17 = 0;
  if ( a6 == 1 && (!(_DWORD)a5 || (_DWORD)a5 == 1 && a4[4] == 130 && !a4[2] && a4[3] == -268435454) )
  {
    v10 = CoCreateInstance(&CLSID_STDispenser, 0, 1u, &IID_ISimpleTableDispenser, &ppv);
    if ( v10 >= 0 )
    {
      v11 = &off_18005B9C0;
      if ( !*((_DWORD *)this + 5) )
        v11 = &off_18005B9D8;
      v10 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, __int64 *, __int64 (**)[2], __int64, int, int, __int64 *))(*(_QWORD *)ppv + 24LL))(
              ppv,
              didCOMCLASSIC,
              tidMETA,
              v11,
              1,
              1,
              3,
              &v19);
      if ( v10 >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 32LL))(v19);
        if ( v10 >= 0 )
        {
          v12 = CoTaskMemAlloc(0x60u);
          if ( v12 )
          {
            for ( i = 0; ; i = (unsigned int)(i + 1) )
            {
              v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 40LL))(v19);
              v10 = v14;
              if ( v14 )
                break;
              v10 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, _DWORD **))(*(_QWORD *)v19 + 64LL))(
                      v19,
                      1,
                      0,
                      0,
                      &v17);
              if ( v10 < 0 )
                goto LABEL_28;
              v12[3 * i] = *v17;
              v10 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v19 + 64LL))(v19, 2, 0);
              if ( v10 < 0 )
                goto LABEL_28;
              v12[3 * i + 1] = *v17;
              v10 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v19 + 64LL))(v19, 3, 0);
              if ( v10 < 0 )
                goto LABEL_28;
              v12[3 * i + 2] = *v17;
            }
            if ( v14 == -2146367487 )
            {
              if ( (_DWORD)i == 8 )
              {
                v10 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, __int64 *, _QWORD, _QWORD, int, int, char *))(*(_QWORD *)ppv + 24LL))(
                        ppv,
                        didMEMORY,
                        tidMEMORY_SHAPEABLE,
                        0,
                        0,
                        1,
                        8,
                        (char *)this + 24);
                if ( v10 >= 0 )
                {
                  v10 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 3))(
                          *((_QWORD *)this + 3),
                          &IID_ISimpleTableControl,
                          &v18);
                  if ( v10 >= 0 )
                  {
                    v10 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _DWORD *))(*(_QWORD *)v18 + 24LL))(
                            v18,
                            8,
                            8,
                            v12);
                    if ( v10 >= 0 )
                    {
                      *a9 = (void *)(((unsigned __int64)this - 16) & -(__int64)(this != (CLTLegacyServers *)24));
                      v15 = ((unsigned __int64)this - 16) & -(__int64)(this != (CLTLegacyServers *)24);
                      (*(void (__fastcall **)(unsigned __int64, __int64))(*(_QWORD *)v15 + 8LL))(
                        v15,
                        24LL - (_QWORD)this);
                      _InterlockedAdd((volatile signed __int32 *)this + 3, 1u);
                      *((_QWORD *)this + 4) = ppv;
                      ppv = 0;
                    }
                  }
                }
              }
              else
              {
                v10 = -2147418113;
              }
            }
LABEL_28:
            CoTaskMemFree(v12);
          }
          else
          {
            v10 = -2147024882;
          }
        }
      }
    }
    if ( ppv )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      ppv = 0;
    }
    if ( v19 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      v19 = 0;
    }
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180019d50  mov     [rsp-28h+arg_8], rbx
0x180019d55  mov     [rsp-28h+arg_10], rsi
0x180019d5a  push    rbp
0x180019d5b  push    rdi
0x180019d5c  push    r13
0x180019d5e  push    r14
0x180019d60  push    r15
0x180019d62  mov     rbp, rsp
0x180019d65  sub     rsp, 60h
0x180019d69  mov     r14, rcx
0x180019d6c  mov     [rbp+arg_18], 0
0x180019d74  mov     [rbp+arg_0], 0
0x180019d7c  mov     [rbp+var_8], 0
0x180019d84  mov     [rbp+var_10], 0
0x180019d8c  mov     r13d, 1
0x180019d92  cmp     [rbp+arg_28], r13d
0x180019d96  jz      short loc_180019DA2
0x180019d98  mov     ebx, 80070057h
0x180019d9d  jmp     loc_18001A097
0x180019da2  mov     eax, dword ptr [rbp+arg_20]
0x180019da5  test    eax, eax
0x180019da7  jz      short loc_180019DC9
0x180019da9  cmp     eax, r13d
0x180019dac  jnz     short loc_180019D98
0x180019dae  cmp     dword ptr [r9+10h], 82h
0x180019db6  jnz     short loc_180019D98
0x180019db8  cmp     dword ptr [r9+8], 0
0x180019dbd  jnz     short loc_180019D98
0x180019dbf  cmp     dword ptr [r9+0Ch], 0F0000002h
0x180019dc7  jnz     short loc_180019D98
0x180019dc9  lea     rax, [rbp+arg_18]
0x180019dcd  mov     [rsp+60h+ppv], rax; ppv
0x180019dd2  lea     r9, IID_ISimpleTableDispenser; riid
0x180019dd9  mov     r8d, r13d; dwClsContext
0x180019ddc  xor     edx, edx; pUnkOuter
0x180019dde  lea     rcx, CLSID_STDispenser; rclsid
0x180019de5  call    cs:__imp_CoCreateInstance
0x180019deb  mov     ebx, eax
0x180019ded  test    eax, eax
0x180019def  js      loc_18001A048
0x180019df5  mov     rcx, [rbp+arg_18]
0x180019df9  mov     rax, [rcx]
0x180019dfc  lea     rdx, off_18005B9D8
0x180019e03  lea     r9, off_18005B9C0
0x180019e0a  cmp     dword ptr [r14+14h], 0
0x180019e0f  cmovz   r9, rdx
0x180019e13  lea     rdx, [rbp+arg_0]
0x180019e17  mov     [rsp+60h+var_28], rdx
0x180019e1c  mov     [rsp+60h+var_30], 3
0x180019e24  mov     [rsp+60h+var_38], r13d
0x180019e29  mov     [rsp+60h+ppv], r13
0x180019e2e  lea     r8, tidMETA
0x180019e35  lea     rdx, didCOMCLASSIC
0x180019e3c  mov     rax, [rax+18h]
0x180019e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e45  mov     ebx, eax
0x180019e47  test    eax, eax
0x180019e49  js      loc_18001A048
0x180019e4f  mov     rcx, [rbp+arg_0]
0x180019e53  mov     rax, [rcx]
0x180019e56  mov     rax, [rax+20h]
0x180019e5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e5f  mov     ebx, eax
0x180019e61  test    eax, eax
0x180019e63  js      loc_18001A048
0x180019e69  mov     ecx, 60h ; '`'; cb
0x180019e6e  call    cs:__imp_CoTaskMemAlloc
0x180019e74  mov     rdi, rax
0x180019e77  test    rax, rax
0x180019e7a  jnz     short loc_180019E86
0x180019e7c  mov     ebx, 8007000Eh
0x180019e81  jmp     loc_18001A048
0x180019e86  xor     esi, esi
0x180019e88  mov     rcx, [rbp+arg_0]
0x180019e8c  mov     rax, [rcx]
0x180019e8f  mov     rax, [rax+28h]
0x180019e93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e98  mov     ebx, eax
0x180019e9a  test    eax, eax
0x180019e9c  jnz     loc_180019F54
0x180019ea2  mov     rcx, [rbp+arg_0]
0x180019ea6  mov     rax, [rcx]
0x180019ea9  lea     rdx, [rbp+var_10]
0x180019ead  mov     [rsp+60h+ppv], rdx
0x180019eb2  xor     r9d, r9d
0x180019eb5  xor     r8d, r8d
0x180019eb8  mov     edx, r13d
0x180019ebb  mov     rax, [rax+40h]
0x180019ebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ec4  mov     ebx, eax
0x180019ec6  test    eax, eax
0x180019ec8  js      loc_18001A03E
0x180019ece  lea     r15, [rsi+rsi*2]
0x180019ed2  mov     rax, [rbp+var_10]
0x180019ed6  mov     ecx, [rax]
0x180019ed8  mov     [rdi+r15*4], ecx
0x180019edc  mov     rcx, [rbp+arg_0]
0x180019ee0  mov     rax, [rcx]
0x180019ee3  lea     rdx, [rbp+var_10]
0x180019ee7  mov     [rsp+60h+ppv], rdx
0x180019eec  xor     r9d, r9d
0x180019eef  xor     r8d, r8d
0x180019ef2  lea     edx, [r9+2]
0x180019ef6  mov     rax, [rax+40h]
0x180019efa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019eff  mov     ebx, eax
0x180019f01  test    eax, eax
0x180019f03  js      loc_18001A03E
0x180019f09  mov     rax, [rbp+var_10]
0x180019f0d  mov     ecx, [rax]
0x180019f0f  mov     [rdi+r15*4+4], ecx
0x180019f14  mov     rcx, [rbp+arg_0]
0x180019f18  mov     rax, [rcx]
0x180019f1b  lea     rdx, [rbp+var_10]
0x180019f1f  mov     [rsp+60h+ppv], rdx
0x180019f24  xor     r9d, r9d
0x180019f27  xor     r8d, r8d
0x180019f2a  lea     edx, [r9+3]
0x180019f2e  mov     rax, [rax+40h]
0x180019f32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f37  mov     ebx, eax
0x180019f39  test    eax, eax
0x180019f3b  js      loc_18001A03E
0x180019f41  mov     rax, [rbp+var_10]
0x180019f45  mov     ecx, [rax]
0x180019f47  mov     [rdi+r15*4+8], ecx
0x180019f4c  add     esi, r13d
0x180019f4f  jmp     loc_180019E88
0x180019f54  cmp     eax, 80110801h
0x180019f59  jnz     loc_18001A03E
0x180019f5f  mov     r15d, 8
0x180019f65  cmp     esi, r15d
0x180019f68  jz      short loc_180019F74
0x180019f6a  mov     ebx, 8000FFFFh
0x180019f6f  jmp     loc_18001A03E
0x180019f74  lea     rsi, [r14+18h]
0x180019f78  mov     rcx, [rbp+arg_18]
0x180019f7c  mov     rax, [rcx]
0x180019f7f  mov     [rsp+60h+var_28], rsi
0x180019f84  mov     [rsp+60h+var_30], r15d
0x180019f89  mov     [rsp+60h+var_38], r13d
0x180019f8e  mov     [rsp+60h+ppv], 0
0x180019f97  xor     r9d, r9d
0x180019f9a  lea     r8, tidMEMORY_SHAPEABLE
0x180019fa1  lea     rdx, didMEMORY
0x180019fa8  mov     rax, [rax+18h]
0x180019fac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019fb1  mov     ebx, eax
0x180019fb3  test    eax, eax
0x180019fb5  js      loc_18001A03E
0x180019fbb  mov     rcx, [rsi]
0x180019fbe  mov     rax, [rcx]
0x180019fc1  lea     r8, [rbp+var_8]
0x180019fc5  lea     rdx, IID_ISimpleTableControl
0x180019fcc  mov     rax, [rax]
0x180019fcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019fd4  mov     ebx, eax
0x180019fd6  test    eax, eax
0x180019fd8  js      short loc_18001A03E
0x180019fda  mov     rcx, [rbp+var_8]
0x180019fde  mov     rax, [rcx]
0x180019fe1  mov     r9, rdi
0x180019fe4  mov     r8d, r15d
0x180019fe7  mov     edx, r15d
0x180019fea  mov     rax, [rax+18h]
0x180019fee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ff3  mov     ebx, eax
0x180019ff5  test    eax, eax
0x180019ff7  js      short loc_18001A03E
0x180019ff9  lea     rdx, [r14-18h]
0x180019ffd  lea     r8, [r14-10h]
0x18001a001  mov     rax, rdx
0x18001a004  neg     rax
0x18001a007  sbb     rcx, rcx
0x18001a00a  and     rcx, r8
0x18001a00d  mov     rax, [rbp+arg_40]
0x18001a011  mov     [rax], rcx
0x18001a014  neg     rdx
0x18001a017  sbb     rcx, rcx
0x18001a01a  and     rcx, r8
0x18001a01d  mov     rax, [rcx]
0x18001a020  mov     rax, [rax+8]
0x18001a024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a029  lock add [r14+0Ch], r13d
0x18001a02e  mov     rax, [rbp+arg_18]
0x18001a032  mov     [r14+20h], rax
0x18001a036  mov     [rbp+arg_18], 0
0x18001a03e  mov     rcx, rdi; pv
0x18001a041  call    cs:__imp_CoTaskMemFree
0x18001a047  nop
0x18001a048  mov     rcx, [rbp+arg_18]
0x18001a04c  test    rcx, rcx
0x18001a04f  jz      short loc_18001A065
0x18001a051  mov     rax, [rcx]
0x18001a054  mov     rax, [rax+10h]
0x18001a058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a05d  mov     [rbp+arg_18], 0
0x18001a065  mov     rcx, [rbp+arg_0]
0x18001a069  test    rcx, rcx
0x18001a06c  jz      short loc_18001A082
0x18001a06e  mov     rax, [rcx]
0x18001a071  mov     rax, [rax+10h]
0x18001a075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a07a  mov     [rbp+arg_0], 0
0x18001a082  mov     rcx, [rbp+var_8]
0x18001a086  test    rcx, rcx
0x18001a089  jz      short loc_18001A097
0x18001a08b  mov     rax, [rcx]
0x18001a08e  mov     rax, [rax+10h]
0x18001a092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a097  mov     eax, ebx
0x18001a099  lea     r11, [rsp+60h+var_s0]
0x18001a09e  mov     rbx, [r11+38h]
0x18001a0a2  mov     rsi, [r11+40h]
0x18001a0a6  mov     rsp, r11
0x18001a0a9  pop     r15
0x18001a0ab  pop     r14
0x18001a0ad  pop     r13
0x18001a0af  pop     rdi
0x18001a0b0  pop     rbp
0x18001a0b1  retn
```
