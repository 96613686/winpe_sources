# CServiceProvider::GetInstallableChildDevices(CChildDeviceInfo * *,ulong *)

- ea: `0x18000a9e8`
- end: `0x18000ad4c`
- name: `?GetInstallableChildDevices@CServiceProvider@@IEAAJPEAPEAVCChildDeviceInfo@@PEAK@Z`
- size: `868`
- prototype: `__int64 __fastcall(CServiceProvider *__hidden this, struct CChildDeviceInfo **, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, service_task, installer_update`

## callers

- `0x18000b2e4`

## callees

- `0x1800019bc`
- `0x1800019c8`
- `0x1800098b0`
- `0x180009970`
- `0x18000a9e8`
- `0x18000bae8`
- `0x18000bc98`
- `0x18000bce4`
- `0x18000bd30`
- `0x180012dce`
- `0x180014010`

## import_xrefs

- `ole32!PropVariantClear` at `0x18000ac10`
- `ole32!PropVariantClear` at `0x18000ac1a`
- `ole32!PropVariantClear` at `0x18000ac10`
- `ole32!PropVariantClear` at `0x18000ac1a`

## pseudocode

```c
__int64 __fastcall CServiceProvider::GetInstallableChildDevices(
        CServiceProvider *this,
        struct CChildDeviceInfo **a2,
        unsigned int *a3)
{
  unsigned int v3; // r15d
  char *v4; // rdi
  __int64 v8; // rcx
  unsigned int v9; // ebx
  __int64 v10; // rsi
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rax
  _QWORD *v13; // rax
  CChildDeviceInfo *i; // r14
  unsigned int v15; // r14d
  __int64 v16; // rsi
  _BYTE *v17; // rcx
  struct CChildDeviceInfo **v18; // rax
  __int64 v19; // r14
  CChildDeviceInfo *j; // rsi
  int v21; // eax
  bool v22; // cf
  CServiceProvider *v24; // [rsp+20h] [rbp-58h]
  __int64 v25; // [rsp+30h] [rbp-48h] BYREF
  PROPVARIANT pvar[2]; // [rsp+38h] [rbp-40h] BYREF
  __int64 v27; // [rsp+48h] [rbp-30h]
  PROPVARIANT v28[2]; // [rsp+50h] [rbp-28h] BYREF
  __int64 v29; // [rsp+60h] [rbp-18h]
  unsigned int v30; // [rsp+C0h] [rbp+48h] BYREF
  struct CChildDeviceInfo **v31; // [rsp+C8h] [rbp+50h]
  __int64 v32; // [rsp+D0h] [rbp+58h] BYREF
  __int64 v33; // [rsp+D8h] [rbp+60h] BYREF

  v31 = a2;
  v3 = 0;
  v30 = 0;
  v33 = 0;
  v4 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v24 = this;
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_8299e7f36ddb39903502156c86dec960_Traceguids);
  }
  v8 = *((_QWORD *)this + 11);
  *a2 = 0;
  *a3 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, SID *, GUID *, __int64 *, CServiceProvider *))(*(_QWORD *)v8 + 24LL))(
         v8,
         &SID_PNPXServiceCollection,
         &IID_IFunctionInstanceCollection,
         &v33,
         v24);
  if ( !v9 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v33 + 24LL))(v33, &v30);
    if ( !v9 )
    {
      if ( v30 )
      {
        v10 = v30;
        v11 = v30 * (unsigned __int64)(v9 + 16);
        if ( !is_mul_ok(v30, v9 + 16) )
          v11 = -1;
        v22 = __CFADD__(v11, 8);
        v12 = v11 + 8;
        if ( v22 )
          v12 = -1;
        v13 = operator new[](v12);
        if ( !v13 )
          goto LABEL_16;
        *v13 = v10;
        v4 = (char *)(v13 + 1);
        for ( i = (CChildDeviceInfo *)(v13 + 1); v10; --v10 )
        {
          CChildDeviceInfo::CChildDeviceInfo(i);
          i = (CChildDeviceInfo *)((char *)i + 16);
        }
        if ( v4 )
          memset_0(v4, 0, 16LL * v30);
        else
LABEL_16:
          v9 = -2147024882;
      }
    }
  }
  v15 = 0;
  if ( v30 )
  {
    while ( !v9 )
    {
      v25 = 0;
      v27 = 0;
      v29 = 0;
      v32 = 0;
      *(_OWORD *)pvar = 0;
      *(_OWORD *)v28 = 0;
      v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v33 + 40LL))(v33, v15, &v25);
      if ( !v9 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v25 + 48LL))(v25, 0, &v32);
        if ( !v9 )
        {
          v9 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v32 + 40LL))(
                 v32,
                 &PKEY_PNPX_Installable,
                 v28);
          if ( !v9 && LOWORD(v28[0]) == 11 && LOWORD(v28[1]) == 0xFFFF )
          {
            v9 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v32 + 40LL))(
                   v32,
                   &PKEY_PNPX_ID,
                   pvar);
            if ( !v9 && LOWORD(pvar[0]) == 31 )
            {
              if ( pvar[1] )
              {
                v16 = 16LL * v3;
                v9 = MyDuplicateString(pvar[1], &v4[v16 + 8]);
                if ( !v9 )
                {
                  *(_DWORD *)&v4[v16] = 0;
                  ++v3;
                }
              }
            }
          }
        }
      }
      PropVariantClear(pvar);
      PropVariantClear(v28);
      if ( v25 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      if ( v32 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      if ( ++v15 >= v30 )
        goto LABEL_34;
    }
  }
  else
  {
LABEL_34:
    if ( !v9 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_8299e7f36ddb39903502156c86dec960_Traceguids);
        v17 = WPP_GLOBAL_Control;
      }
      v18 = v31;
      *a3 = v3;
      *v18 = (struct CChildDeviceInfo *)v4;
      goto LABEL_44;
    }
  }
  if ( v4 )
  {
    v19 = *((_QWORD *)v4 - 1);
    for ( j = (CChildDeviceInfo *)&v4[16 * v19]; v19; --v19 )
    {
      j = (CChildDeviceInfo *)((char *)j - 16);
      CChildDeviceInfo::~CChildDeviceInfo(j);
    }
    operator delete[](v4 - 8);
  }
  v17 = WPP_GLOBAL_Control;
LABEL_44:
  if ( v33 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    v17 = WPP_GLOBAL_Control;
  }
  v21 = 0;
  if ( v9 )
    v22 = v17[25] < 2u;
  else
    v22 = v17[25] < 4u;
  if ( v17 != (_BYTE *)&WPP_GLOBAL_Control )
  {
    LOBYTE(v21) = !v22;
    if ( v21 )
      WPP_SF_sqd(*((_QWORD *)v17 + 2), 32, WPP_8299e7f36ddb39903502156c86dec960_Traceguids);
  }
  return v9;
}

```

## disassembly

```asm
0x18000a9e8  mov     [rsp-40h+arg_8], rdx
0x18000a9ed  push    rbp
0x18000a9ee  push    rbx
0x18000a9ef  push    rsi
0x18000a9f0  push    rdi
0x18000a9f1  push    r12
0x18000a9f3  push    r13
0x18000a9f5  push    r14
0x18000a9f7  push    r15
0x18000a9f9  mov     rbp, rsp
0x18000a9fc  sub     rsp, 78h
0x18000aa00  xor     r15d, r15d
0x18000aa03  mov     [rbp+arg_0], 0
0x18000aa0a  mov     [rbp+arg_18], r15
0x18000aa0e  xor     edi, edi
0x18000aa10  mov     r12, r8
0x18000aa13  mov     rbx, rdx
0x18000aa16  mov     r13, rcx
0x18000aa19  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa20  lea     rax, WPP_GLOBAL_Control
0x18000aa27  cmp     rcx, rax
0x18000aa2a  jz      short loc_18000AA4A
0x18000aa2c  cmp     byte ptr [rcx+19h], 4
0x18000aa30  jb      short loc_18000AA4A
0x18000aa32  mov     rcx, [rcx+10h]
0x18000aa36  lea     edx, [rdi+1Eh]
0x18000aa39  lea     r8, WPP_8299e7f36ddb39903502156c86dec960_Traceguids
0x18000aa40  mov     [rsp+78h+var_58], r13
0x18000aa45  call    WPP_SF_sq
0x18000aa4a  mov     rcx, [r13+58h]
0x18000aa4e  lea     r9, [rbp+arg_18]
0x18000aa52  lea     r8, IID_IFunctionInstanceCollection
0x18000aa59  mov     [rbx], rdi
0x18000aa5c  lea     rdx, SID_PNPXServiceCollection
0x18000aa63  mov     [r12], edi
0x18000aa67  mov     rax, [rcx]
0x18000aa6a  mov     rax, [rax+18h]
0x18000aa6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa73  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000aa77  mov     ebx, eax
0x18000aa79  test    eax, eax
0x18000aa7b  jnz     loc_18000AB02
0x18000aa81  mov     rcx, [rbp+arg_18]
0x18000aa85  lea     rdx, [rbp+arg_0]
0x18000aa89  mov     rax, [rcx]
0x18000aa8c  mov     rax, [rax+18h]
0x18000aa90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa95  mov     ebx, eax
0x18000aa97  test    eax, eax
0x18000aa99  jnz     short loc_18000AB02
0x18000aa9b  mov     eax, [rbp+arg_0]
0x18000aa9e  test    eax, eax
0x18000aaa0  jz      short loc_18000AB02
0x18000aaa2  mov     esi, eax
0x18000aaa4  lea     eax, [rbx+10h]
0x18000aaa7  mul     rsi
0x18000aaaa  cmovb   rax, r14
0x18000aaae  add     rax, 8
0x18000aab2  cmovb   rax, r14
0x18000aab6  mov     rcx, rax; unsigned __int64
0x18000aab9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000aabe  test    rax, rax
0x18000aac1  jz      short loc_18000AAFD
0x18000aac3  mov     [rax], rsi
0x18000aac6  lea     rdi, [rax+8]
0x18000aaca  mov     r14, rdi
0x18000aacd  test    rsi, rsi
0x18000aad0  jz      short loc_18000AAE4
0x18000aad2  mov     rcx, r14; this
0x18000aad5  call    ??0CChildDeviceInfo@@QEAA@XZ; CChildDeviceInfo::CChildDeviceInfo(void)
0x18000aada  add     r14, 10h
0x18000aade  sub     rsi, 1
0x18000aae2  jnz     short loc_18000AAD2
0x18000aae4  test    rdi, rdi
0x18000aae7  jz      short loc_18000AAFD
0x18000aae9  mov     r8d, [rbp+arg_0]
0x18000aaed  xor     edx, edx; Val
0x18000aaef  shl     r8, 4; Size
0x18000aaf3  mov     rcx, rdi; void *
0x18000aaf6  call    memset_0
0x18000aafb  jmp     short loc_18000AB02
0x18000aafd  mov     ebx, 8007000Eh
0x18000ab02  xor     r14d, r14d
0x18000ab05  lea     esi, [r14+1Fh]
0x18000ab09  cmp     [rbp+arg_0], r14d
0x18000ab0d  jbe     loc_18000AC57
0x18000ab13  test    ebx, ebx
0x18000ab15  jnz     loc_18000AC9F
0x18000ab1b  mov     rcx, [rbp+arg_18]
0x18000ab1f  lea     r8, [rbp+var_48]
0x18000ab23  xor     eax, eax
0x18000ab25  mov     [rbp+var_48], 0
0x18000ab2d  mov     [rbp+var_30], rax
0x18000ab31  xorps   xmm0, xmm0
0x18000ab34  mov     [rbp+var_18], rax
0x18000ab38  xorps   xmm1, xmm1
0x18000ab3b  mov     [rbp+arg_10], 0
0x18000ab43  mov     edx, r14d
0x18000ab46  movups  xmmword ptr [rbp+pvar], xmm0
0x18000ab4a  movups  xmmword ptr [rbp+var_28], xmm1
0x18000ab4e  mov     rax, [rcx]
0x18000ab51  mov     rax, [rax+28h]
0x18000ab55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab5a  mov     ebx, eax
0x18000ab5c  test    eax, eax
0x18000ab5e  jnz     loc_18000AC0C
0x18000ab64  mov     rcx, [rbp+var_48]
0x18000ab68  lea     r8, [rbp+arg_10]
0x18000ab6c  xor     edx, edx
0x18000ab6e  mov     rax, [rcx]
0x18000ab71  mov     rax, [rax+30h]
0x18000ab75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab7a  mov     ebx, eax
0x18000ab7c  test    eax, eax
0x18000ab7e  jnz     loc_18000AC0C
0x18000ab84  mov     rcx, [rbp+arg_10]
0x18000ab88  lea     r8, [rbp+var_28]
0x18000ab8c  lea     rdx, PKEY_PNPX_Installable
0x18000ab93  mov     rax, [rcx]
0x18000ab96  mov     rax, [rax+28h]
0x18000ab9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab9f  mov     ebx, eax
0x18000aba1  test    eax, eax
0x18000aba3  jnz     short loc_18000AC0C
0x18000aba5  lea     eax, [rbx+0Bh]
0x18000aba8  cmp     ax, word ptr [rbp+var_28]
0x18000abac  jnz     short loc_18000AC0C
0x18000abae  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000abb2  cmp     ax, word ptr [rbp+var_28+8]
0x18000abb6  jnz     short loc_18000AC0C
0x18000abb8  mov     rcx, [rbp+arg_10]
0x18000abbc  lea     r8, [rbp+pvar]
0x18000abc0  lea     rdx, PKEY_PNPX_ID
0x18000abc7  mov     rax, [rcx]
0x18000abca  mov     rax, [rax+28h]
0x18000abce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abd3  mov     ebx, eax
0x18000abd5  test    eax, eax
0x18000abd7  jnz     short loc_18000AC0C
0x18000abd9  cmp     si, word ptr [rbp+pvar]
0x18000abdd  jnz     short loc_18000AC0C
0x18000abdf  mov     rcx, [rbp+pvar+8]
0x18000abe3  test    rcx, rcx
0x18000abe6  jz      short loc_18000AC0C
0x18000abe8  mov     esi, r15d
0x18000abeb  shl     rsi, 4
0x18000abef  lea     rdx, [rsi+8]
0x18000abf3  add     rdx, rdi
0x18000abf6  call    _MyDuplicateString
0x18000abfb  mov     ebx, eax
0x18000abfd  test    eax, eax
0x18000abff  jnz     short loc_18000AC07
0x18000ac01  mov     [rsi+rdi], eax
0x18000ac04  inc     r15d
0x18000ac07  mov     esi, 1Fh
0x18000ac0c  lea     rcx, [rbp+pvar]; pvar
0x18000ac10  call    cs:__imp_PropVariantClear
0x18000ac16  lea     rcx, [rbp+var_28]; pvar
0x18000ac1a  call    cs:__imp_PropVariantClear
0x18000ac20  mov     rcx, [rbp+var_48]
0x18000ac24  test    rcx, rcx
0x18000ac27  jz      short loc_18000AC35
0x18000ac29  mov     rax, [rcx]
0x18000ac2c  mov     rax, [rax+10h]
0x18000ac30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac35  mov     rcx, [rbp+arg_10]
0x18000ac39  test    rcx, rcx
0x18000ac3c  jz      short loc_18000AC4A
0x18000ac3e  mov     rax, [rcx]
0x18000ac41  mov     rax, [rax+10h]
0x18000ac45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac4a  inc     r14d
0x18000ac4d  cmp     r14d, [rbp+arg_0]
0x18000ac51  jb      loc_18000AB13
0x18000ac57  test    ebx, ebx
0x18000ac59  jnz     short loc_18000AC9F
0x18000ac5b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ac62  lea     r14, WPP_GLOBAL_Control
0x18000ac69  cmp     rcx, r14
0x18000ac6c  jz      short loc_18000AC92
0x18000ac6e  cmp     byte ptr [rcx+19h], 4
0x18000ac72  jb      short loc_18000AC92
0x18000ac74  mov     rcx, [rcx+10h]
0x18000ac78  lea     r8, WPP_8299e7f36ddb39903502156c86dec960_Traceguids
0x18000ac7f  mov     edx, esi
0x18000ac81  mov     dword ptr [rsp+78h+var_58], r15d
0x18000ac86  call    WPP_SF_sd
0x18000ac8b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ac92  mov     rax, [rbp+arg_8]
0x18000ac96  mov     [r12], r15d
0x18000ac9a  mov     [rax], rdi
0x18000ac9d  jmp     short loc_18000ACE0
0x18000ac9f  test    rdi, rdi
0x18000aca2  jz      short loc_18000ACD2
0x18000aca4  mov     r14, [rdi-8]
0x18000aca8  mov     rsi, r14
0x18000acab  shl     rsi, 4
0x18000acaf  add     rsi, rdi
0x18000acb2  test    r14, r14
0x18000acb5  jz      short loc_18000ACC9
0x18000acb7  sub     rsi, 10h
0x18000acbb  mov     rcx, rsi; this
0x18000acbe  call    ??1CChildDeviceInfo@@QEAA@XZ; CChildDeviceInfo::~CChildDeviceInfo(void)
0x18000acc3  sub     r14, 1
0x18000acc7  jnz     short loc_18000ACB7
0x18000acc9  lea     rcx, [rdi-8]; Block
0x18000accd  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18000acd2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000acd9  lea     r14, WPP_GLOBAL_Control
0x18000ace0  mov     rdx, [rbp+arg_18]
0x18000ace4  test    rdx, rdx
0x18000ace7  jz      short loc_18000ACFF
0x18000ace9  mov     rax, [rdx]
0x18000acec  mov     rcx, rdx
0x18000acef  mov     rax, [rax+10h]
0x18000acf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acf8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000acff  xor     eax, eax
0x18000ad01  test    ebx, ebx
0x18000ad03  jnz     short loc_18000AD0B
0x18000ad05  cmp     byte ptr [rcx+19h], 4
0x18000ad09  jmp     short loc_18000AD0F
0x18000ad0b  cmp     byte ptr [rcx+19h], 2
0x18000ad0f  setnb   al
0x18000ad12  cmp     rcx, r14
0x18000ad15  jz      short loc_18000AD39
0x18000ad17  test    eax, eax
0x18000ad19  jz      short loc_18000AD39
0x18000ad1b  mov     rcx, [rcx+10h]
0x18000ad1f  lea     r8, WPP_8299e7f36ddb39903502156c86dec960_Traceguids
0x18000ad26  mov     edx, 20h ; ' '
0x18000ad2b  mov     [rsp+78h+var_50], ebx
0x18000ad2f  mov     [rsp+78h+var_58], r13
0x18000ad34  call    WPP_SF_sqd
0x18000ad39  mov     eax, ebx
0x18000ad3b  add     rsp, 78h
0x18000ad3f  pop     r15
0x18000ad41  pop     r14
0x18000ad43  pop     r13
0x18000ad45  pop     r12
0x18000ad47  pop     rdi
0x18000ad48  pop     rsi
0x18000ad49  pop     rbx
0x18000ad4a  pop     rbp
0x18000ad4b  retn
```
