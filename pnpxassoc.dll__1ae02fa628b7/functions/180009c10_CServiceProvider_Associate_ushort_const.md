# CServiceProvider::Associate(ushort const *)

- ea: `0x180009c10`
- end: `0x18000a05e`
- name: `?Associate@CServiceProvider@@UEAAJPEBG@Z`
- size: `1102`
- prototype: `__int64 __fastcall(CServiceProvider *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180006150`

## callees

- `0x18000959c`
- `0x180009c10`
- `0x18000a854`
- `0x18000b2e4`
- `0x18000bce4`
- `0x18000bd30`
- `0x18000f4a0`
- `0x18000f6a0`
- `0x18000f748`
- `0x18000f95c`
- `0x18000fc84`
- `0x180014010`

## import_xrefs

- `ole32!PropVariantClear` at `0x180009f8b`
- `ole32!PropVariantClear` at `0x180009f95`
- `ole32!PropVariantClear` at `0x180009f9f`
- `ole32!PropVariantClear` at `0x180009fa9`
- `ole32!PropVariantClear` at `0x180009fb3`
- `ole32!PropVariantClear` at `0x180009f8b`
- `ole32!PropVariantClear` at `0x180009f95`
- `ole32!PropVariantClear` at `0x180009f9f`
- `ole32!PropVariantClear` at `0x180009fa9`
- `ole32!PropVariantClear` at `0x180009fb3`
- `ole32!CoTaskMemFree` at `0x180009fc3`
- `ole32!CoTaskMemFree` at `0x180009fdc`
- `ole32!CoTaskMemFree` at `0x180009fc3`
- `ole32!CoTaskMemFree` at `0x180009fdc`

## pseudocode

```c
__int64 __fastcall CServiceProvider::Associate(CServiceProvider *this, const unsigned __int16 *a2)
{
  __int64 *v3; // rcx
  int v4; // edi
  __int64 v5; // rax
  unsigned int FiCategory; // ebx
  struct IFunctionDiscoveryNotification *v7; // r9
  unsigned __int16 *bstrVal; // rdx
  int v9; // ecx
  int v10; // r9d
  const unsigned __int16 *v11; // r8
  int v12; // eax
  PROPVARIANT v13; // rax
  LARGE_INTEGER hVal; // rax
  int v15; // eax
  int v16; // eax
  bool v17; // cf
  LPVOID pv; // [rsp+30h] [rbp-89h] BYREF
  unsigned __int16 *v20; // [rsp+38h] [rbp-81h] BYREF
  struct tagPROPVARIANT v21; // [rsp+40h] [rbp-79h] BYREF
  PROPVARIANT v22[2]; // [rsp+58h] [rbp-61h] BYREF
  __int64 v23; // [rsp+68h] [rbp-51h]
  struct tagPROPVARIANT pvar; // [rsp+70h] [rbp-49h] BYREF
  __int128 v25; // [rsp+88h] [rbp-31h] BYREF
  struct tagPROPVARIANT v26; // [rsp+98h] [rbp-21h] BYREF
  struct tagPROPVARIANT v27; // [rsp+B0h] [rbp-9h] BYREF
  PROPVARIANT v28; // [rsp+C8h] [rbp+Fh] BYREF
  LARGE_INTEGER v29; // [rsp+D0h] [rbp+17h] BYREF
  int v30; // [rsp+120h] [rbp+67h] BYREF
  const unsigned __int16 *v31; // [rsp+128h] [rbp+6Fh] BYREF
  int v32; // [rsp+130h] [rbp+77h] BYREF
  __int64 v33; // [rsp+138h] [rbp+7Fh] BYREF

  v31 = a2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_8299e7f36ddb39903502156c86dec960_Traceguids);
  v33 = 0;
  v23 = 0;
  v3 = (__int64 *)*((_QWORD *)this + 10);
  v4 = 0;
  pv = 0;
  v20 = 0;
  memset(&pvar, 0, sizeof(pvar));
  *(_OWORD *)v22 = 0;
  memset(&v21, 0, sizeof(v21));
  memset(&v26, 0, sizeof(v26));
  memset(&v27, 0, sizeof(v27));
  v5 = *v3;
  v25 = 0;
  FiCategory = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v5 + 48))(v3, 0, &v33);
  if ( !FiCategory )
  {
    FiCategory = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, struct tagPROPVARIANT *))(*(_QWORD *)v33 + 40LL))(
                   v33,
                   &PKEY_PNPX_RemoteAddress,
                   &pvar);
    if ( !FiCategory )
    {
      FiCategory = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, struct tagPROPVARIANT *))(*(_QWORD *)v33 + 40LL))(
                     v33,
                     &PKEY_PNPX_SecureChannel,
                     &v21);
      if ( !FiCategory )
      {
        FiCategory = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, struct tagPROPVARIANT *))(*(_QWORD *)v33 + 40LL))(
                       v33,
                       &PKEY_PNPX_CompactSignature,
                       &v26);
        if ( !FiCategory )
        {
          FiCategory = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, struct tagPROPVARIANT *))(*(_QWORD *)v33 + 40LL))(
                         v33,
                         &PKEY_PNPX_DeviceCertHash,
                         &v27);
          if ( !FiCategory )
          {
            FiCategory = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v33 + 40LL))(
                           v33,
                           &PKEY_PNPX_GlobalIdentity,
                           v22);
            if ( !FiCategory )
            {
              FiCategory = CServiceProvider::GetFiCategory(
                             (CServiceProvider *)((char *)this - 8),
                             (unsigned __int16 **)&pv,
                             &v20);
              if ( !FiCategory )
              {
                v7 = (struct IFunctionDiscoveryNotification *)*((_QWORD *)this + 11);
                if ( v7 )
                {
                  FiCategory = CServiceProvider::SetupPnpNotification(
                                 (CServiceProvider *)((char *)this - 8),
                                 1,
                                 QUA_ADD,
                                 v7,
                                 (const unsigned __int16 *)v22[1]);
                  if ( FiCategory )
                    goto LABEL_41;
                  v4 = 1;
                }
                FiCategory = ValidateKey(&v21, 0xBu);
                if ( !FiCategory )
                {
                  FiCategory = ValidateKey(&v26, 0xBu);
                  if ( !FiCategory )
                  {
                    FiCategory = ValidateKey(&v27, 0x1Fu);
                    if ( !FiCategory )
                    {
                      FiCategory = ValidateKey(&pvar, 0x1Fu);
                      if ( !FiCategory )
                      {
                        FiCategory = CPnpxDafHelper::Init((CPnpxDafHelper *)&v25, (const unsigned __int16 *)pv);
                        if ( !FiCategory )
                        {
                          if ( v21.vt == 11 && v21.iVal == -1 || pvar.vt == 31 && pvar.hVal.QuadPart )
                          {
                            bstrVal = 0;
                            if ( v27.vt )
                              bstrVal = v27.bstrVal;
                            v9 = 0;
                            if ( v26.vt )
                              LOBYTE(v9) = v26.iVal == 0xFFFF;
                            v10 = 0;
                            if ( v21.vt )
                              LOBYTE(v10) = v21.iVal == 0xFFFF;
                            v11 = 0;
                            if ( pvar.vt )
                              v11 = pvar.bstrVal;
                            v12 = CPnpxDafHelper::DoDafWsdGenericAssociation(
                                    (CPnpxDafHelper *)&v25,
                                    (const unsigned __int16 *)v22[1],
                                    v11,
                                    v10,
                                    v9,
                                    bstrVal);
                          }
                          else
                          {
                            v12 = CPnpxDafHelper::DoDafJustWorksAssociation(
                                    (CPnpxDafHelper *)&v25,
                                    (const unsigned __int16 *)v22[1]);
                          }
                          FiCategory = v12;
                          v30 = v12;
                          v13 = 0;
                          if ( LOWORD(v22[0]) )
                            v13 = v22[1];
                          v28 = v13;
                          hVal.QuadPart = 0;
                          if ( pvar.vt )
                            hVal = pvar.hVal;
                          v29 = hVal;
                          v15 = 0;
                          if ( v21.vt )
                            LOBYTE(v15) = v21.iVal == 0xFFFF;
                          v32 = v15;
                          PnpxTelemetry::Associate<unsigned short * &,unsigned short const * &,int,unsigned short *,unsigned short *,long &>(
                            (unsigned int)&pv,
                            (unsigned int)&v31,
                            (unsigned int)&v32,
                            (unsigned int)&v29,
                            (__int64)&v28,
                            (__int64)&v30);
                          if ( FiCategory == -2140930032 )
                            FiCategory = 0;
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_41:
  if ( FiCategory )
  {
    if ( v4 )
      CServiceProvider::SetupPnpNotification(
        (CServiceProvider *)((char *)this - 8),
        0,
        QUA_ADD,
        *((struct IFunctionDiscoveryNotification **)this + 11),
        (const unsigned __int16 *)v22[1]);
  }
  else if ( *((_QWORD *)this + 11) )
  {
    FiCategory = -2147483638;
  }
  PropVariantClear((PROPVARIANT *)&pvar);
  PropVariantClear(v22);
  PropVariantClear((PROPVARIANT *)&v21);
  PropVariantClear((PROPVARIANT *)&v26);
  PropVariantClear((PROPVARIANT *)&v27);
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v20 )
  {
    CoTaskMemFree(v20);
    v20 = 0;
  }
  v16 = 0;
  if ( FiCategory )
    v17 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u;
  else
    v17 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    LOBYTE(v16) = !v17;
    if ( v16 )
      WPP_SF_sqd(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_8299e7f36ddb39903502156c86dec960_Traceguids);
  }
  CPnpxDafHelper::~CPnpxDafHelper((CPnpxDafHelper *)&v25);
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  return FiCategory;
}

```

## disassembly

```asm
0x180009c10  mov     [rsp-8+arg_8], rdx
0x180009c15  push    rbp
0x180009c16  push    rbx
0x180009c17  push    rsi
0x180009c18  push    rdi
0x180009c19  push    r12
0x180009c1b  push    r13
0x180009c1d  push    r14
0x180009c1f  lea     rbp, [rsp-27h]
0x180009c24  sub     rsp, 0E0h
0x180009c2b  mov     rsi, rcx
0x180009c2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c35  lea     r13, WPP_GLOBAL_Control
0x180009c3c  cmp     rcx, r13
0x180009c3f  jz      short loc_180009C65
0x180009c41  cmp     byte ptr [rcx+19h], 4
0x180009c45  jb      short loc_180009C65
0x180009c47  mov     rcx, [rcx+10h]
0x180009c4b  lea     rax, [rsi-8]
0x180009c4f  mov     edx, 14h
0x180009c54  mov     [rsp+110h+var_F0], rax
0x180009c59  lea     r8, WPP_8299e7f36ddb39903502156c86dec960_Traceguids
0x180009c60  call    WPP_SF_sq
0x180009c65  xor     eax, eax
0x180009c67  mov     [rbp+57h+arg_18], 0
0x180009c6f  xorps   xmm0, xmm0
0x180009c72  mov     [rbp+57h+var_90], rax
0x180009c76  xorps   xmm1, xmm1
0x180009c79  mov     [rbp+57h+var_A8], rax
0x180009c7d  mov     [rbp+57h+var_C0], rax
0x180009c81  lea     r14, [rsi-8]
0x180009c85  mov     rcx, [r14+58h]
0x180009c89  lea     r8, [rbp+57h+arg_18]
0x180009c8d  mov     [rbp+57h+var_68], rax
0x180009c91  xor     edi, edi
0x180009c93  mov     [rbp+57h+var_50], rax
0x180009c97  xor     edx, edx
0x180009c99  mov     [rsp+110h+pv], rdi
0x180009c9e  mov     [rsp+110h+var_D8], rdi
0x180009ca3  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180009ca7  movups  xmmword ptr [rbp+57h+var_B8], xmm1
0x180009cab  movups  xmmword ptr [rbp+57h+var_D0], xmm0
0x180009caf  movups  xmmword ptr [rbp+57h+var_78], xmm1
0x180009cb3  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x180009cb7  mov     rax, [rcx]
0x180009cba  movdqu  [rbp+57h+var_88], xmm0
0x180009cbf  mov     rax, [rax+30h]
0x180009cc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cc8  mov     ebx, eax
0x180009cca  test    eax, eax
0x180009ccc  jnz     loc_180009F56
0x180009cd2  mov     rcx, [rbp+57h+arg_18]
0x180009cd6  lea     r8, [rbp+57h+pvar]
0x180009cda  lea     rdx, PKEY_PNPX_RemoteAddress
0x180009ce1  mov     rax, [rcx]
0x180009ce4  mov     rax, [rax+28h]
0x180009ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ced  mov     ebx, eax
0x180009cef  test    eax, eax
0x180009cf1  jnz     loc_180009F56
0x180009cf7  mov     rcx, [rbp+57h+arg_18]
0x180009cfb  lea     r8, [rbp+57h+var_D0]
0x180009cff  lea     rdx, PKEY_PNPX_SecureChannel
0x180009d06  mov     rax, [rcx]
0x180009d09  mov     rax, [rax+28h]
0x180009d0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d12  mov     ebx, eax
0x180009d14  test    eax, eax
0x180009d16  jnz     loc_180009F56
0x180009d1c  mov     rcx, [rbp+57h+arg_18]
0x180009d20  lea     r8, [rbp+57h+var_78]
0x180009d24  lea     rdx, PKEY_PNPX_CompactSignature
0x180009d2b  mov     rax, [rcx]
0x180009d2e  mov     rax, [rax+28h]
0x180009d32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d37  mov     ebx, eax
0x180009d39  test    eax, eax
0x180009d3b  jnz     loc_180009F56
0x180009d41  mov     rcx, [rbp+57h+arg_18]
0x180009d45  lea     r8, [rbp+57h+var_60]
0x180009d49  lea     rdx, PKEY_PNPX_DeviceCertHash
0x180009d50  mov     rax, [rcx]
0x180009d53  mov     rax, [rax+28h]
0x180009d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d5c  mov     ebx, eax
0x180009d5e  test    eax, eax
0x180009d60  jnz     loc_180009F56
0x180009d66  mov     rcx, [rbp+57h+arg_18]
0x180009d6a  lea     r8, [rbp+57h+var_B8]
0x180009d6e  lea     rdx, PKEY_PNPX_GlobalIdentity
0x180009d75  mov     rax, [rcx]
0x180009d78  mov     rax, [rax+28h]
0x180009d7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d81  mov     ebx, eax
0x180009d83  test    eax, eax
0x180009d85  jnz     loc_180009F56
0x180009d8b  lea     r8, [rsp+110h+var_D8]; unsigned __int16 **
0x180009d90  mov     rcx, r14; this
0x180009d93  lea     rdx, [rsp+110h+pv]; unsigned __int16 **
0x180009d98  call    ?GetFiCategory@CServiceProvider@@IEAAJPEAPEAG0@Z; CServiceProvider::GetFiCategory(ushort * *,ushort * *)
0x180009d9d  mov     ebx, eax
0x180009d9f  test    eax, eax
0x180009da1  jnz     loc_180009F56
0x180009da7  mov     r9, [rsi+58h]; struct IFunctionDiscoveryNotification *
0x180009dab  test    r9, r9
0x180009dae  jz      short loc_180009DD8
0x180009db0  mov     rax, [rbp+57h+var_B8+8]
0x180009db4  lea     r12d, [rdi+1]
0x180009db8  mov     edx, r12d; int
0x180009dbb  mov     [rsp+110h+var_F0], rax; unsigned __int16 *
0x180009dc0  xor     r8d, r8d; enum tagQueryUpdateAction
0x180009dc3  mov     rcx, r14; this
0x180009dc6  call    ?SetupPnpNotification@CServiceProvider@@IEAAJHW4tagQueryUpdateAction@@PEAUIFunctionDiscoveryNotification@@PEBG@Z; CServiceProvider::SetupPnpNotification(int,tagQueryUpdateAction,IFunctionDiscoveryNotification *,ushort const *)
0x180009dcb  mov     ebx, eax
0x180009dcd  test    eax, eax
0x180009dcf  jnz     loc_180009F56
0x180009dd5  mov     edi, r12d
0x180009dd8  mov     r13d, 0Bh
0x180009dde  lea     rcx, [rbp+57h+var_D0]; struct tagPROPVARIANT *
0x180009de2  mov     edx, r13d; unsigned __int16
0x180009de5  call    ?ValidateKey@@YAJAEAUtagPROPVARIANT@@G@Z; ValidateKey(tagPROPVARIANT &,ushort)
0x180009dea  mov     ebx, eax
0x180009dec  test    eax, eax
0x180009dee  jnz     loc_180009F4F
0x180009df4  mov     edx, r13d; unsigned __int16
0x180009df7  lea     rcx, [rbp+57h+var_78]; struct tagPROPVARIANT *
0x180009dfb  call    ?ValidateKey@@YAJAEAUtagPROPVARIANT@@G@Z; ValidateKey(tagPROPVARIANT &,ushort)
0x180009e00  mov     ebx, eax
0x180009e02  test    eax, eax
0x180009e04  jnz     loc_180009F4F
0x180009e0a  lea     r12d, [r13+14h]
0x180009e0e  mov     edx, r12d; unsigned __int16
0x180009e11  lea     rcx, [rbp+57h+var_60]; struct tagPROPVARIANT *
0x180009e15  call    ?ValidateKey@@YAJAEAUtagPROPVARIANT@@G@Z; ValidateKey(tagPROPVARIANT &,ushort)
0x180009e1a  mov     ebx, eax
0x180009e1c  test    eax, eax
0x180009e1e  jnz     loc_180009F4F
0x180009e24  mov     edx, r12d; unsigned __int16
0x180009e27  lea     rcx, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x180009e2b  call    ?ValidateKey@@YAJAEAUtagPROPVARIANT@@G@Z; ValidateKey(tagPROPVARIANT &,ushort)
0x180009e30  mov     ebx, eax
0x180009e32  test    eax, eax
0x180009e34  jnz     loc_180009F4F
0x180009e3a  mov     rdx, [rsp+110h+pv]; unsigned __int16 *
0x180009e3f  lea     rcx, [rbp+57h+var_88]; this
0x180009e43  call    ?Init@CPnpxDafHelper@@QEAAJPEBG@Z; CPnpxDafHelper::Init(ushort const *)
0x180009e48  mov     ebx, eax
0x180009e4a  test    eax, eax
0x180009e4c  jnz     loc_180009F4F
0x180009e52  mov     r10, [rbp+57h+pvar+8]
0x180009e56  or      r12d, 0FFFFFFFFh
0x180009e5a  movzx   r11d, word ptr [rbp+57h+pvar]
0x180009e5f  cmp     r13w, word ptr [rbp+57h+var_D0]
0x180009e64  jnz     short loc_180009E6D
0x180009e66  cmp     r12w, word ptr [rbp+57h+var_D0+8]
0x180009e6b  jz      short loc_180009E7D
0x180009e6d  mov     eax, 1Fh
0x180009e72  cmp     ax, r11w
0x180009e76  jnz     short loc_180009ECF
0x180009e78  test    r10, r10
0x180009e7b  jz      short loc_180009ECF
0x180009e7d  xor     edx, edx
0x180009e7f  xor     eax, eax
0x180009e81  cmp     ax, word ptr [rbp+57h+var_60]
0x180009e85  cmovnz  rdx, [rbp+57h+var_60+8]
0x180009e8a  xor     ecx, ecx
0x180009e8c  cmp     ax, word ptr [rbp+57h+var_78]
0x180009e90  jz      short loc_180009E9A
0x180009e92  cmp     r12w, word ptr [rbp+57h+var_78+8]
0x180009e97  setz    cl
0x180009e9a  xor     r9d, r9d
0x180009e9d  cmp     ax, word ptr [rbp+57h+var_D0]
0x180009ea1  jz      short loc_180009EAC
0x180009ea3  cmp     r12w, word ptr [rbp+57h+var_D0+8]
0x180009ea8  setz    r9b; int
0x180009eac  xor     r8d, r8d
0x180009eaf  mov     [rsp+110h+var_E8], rdx; unsigned __int16 *
0x180009eb4  mov     rdx, [rbp+57h+var_B8+8]; unsigned __int16 *
0x180009eb8  cmp     ax, r11w
0x180009ebc  mov     dword ptr [rsp+110h+var_F0], ecx; int
0x180009ec0  lea     rcx, [rbp+57h+var_88]; this
0x180009ec4  cmovnz  r8, r10; unsigned __int16 *
0x180009ec8  call    ?DoDafWsdGenericAssociation@CPnpxDafHelper@@QEAAJPEBG0HHPEAG@Z; CPnpxDafHelper::DoDafWsdGenericAssociation(ushort const *,ushort const *,int,int,ushort *)
0x180009ecd  jmp     short loc_180009EDC
0x180009ecf  mov     rdx, [rbp+57h+var_B8+8]; unsigned __int16 *
0x180009ed3  lea     rcx, [rbp+57h+var_88]; this
0x180009ed7  call    ?DoDafJustWorksAssociation@CPnpxDafHelper@@QEAAJPEBG@Z; CPnpxDafHelper::DoDafJustWorksAssociation(ushort const *)
0x180009edc  mov     ebx, eax
0x180009ede  mov     [rbp+57h+arg_0], eax
0x180009ee1  xor     eax, eax
0x180009ee3  xor     ecx, ecx
0x180009ee5  cmp     cx, word ptr [rbp+57h+var_B8]
0x180009ee9  cmovnz  rax, [rbp+57h+var_B8+8]
0x180009eee  mov     [rbp+57h+var_48], rax
0x180009ef2  xor     eax, eax
0x180009ef4  cmp     cx, word ptr [rbp+57h+pvar]
0x180009ef8  cmovnz  rax, [rbp+57h+pvar+8]
0x180009efd  mov     [rbp+57h+var_40], rax
0x180009f01  xor     eax, eax
0x180009f03  cmp     ax, word ptr [rbp+57h+var_D0]
0x180009f07  jz      short loc_180009F11
0x180009f09  cmp     r12w, word ptr [rbp+57h+var_D0+8]
0x180009f0e  setz    al
0x180009f11  mov     [rbp+57h+arg_10], eax
0x180009f14  lea     r9, [rbp+57h+var_40]
0x180009f18  lea     rax, [rbp+57h+arg_0]
0x180009f1c  mov     [rsp+110h+var_E8], rax
0x180009f21  lea     r8, [rbp+57h+arg_10]
0x180009f25  lea     rax, [rbp+57h+var_48]
0x180009f29  lea     rdx, [rbp+57h+arg_8]
0x180009f2d  mov     [rsp+110h+var_F0], rax
0x180009f32  lea     rcx, [rsp+110h+pv]
0x180009f37  call    ??$Associate@AEAPEAGAEAPEBGHPEAGPEAGAEAJ@PnpxTelemetry@@SAXAEAPEAGAEAPEBG$$QEAH$$QEAPEAG3AEAJ@Z; PnpxTelemetry::Associate<ushort * &,ushort const * &,int,ushort *,ushort *,long &>(ushort * &,ushort const * &,int &&,ushort * &&,ushort * &&,long &)
0x180009f3c  lea     r13, WPP_GLOBAL_Control
0x180009f43  cmp     ebx, 80640010h
0x180009f49  jnz     short loc_180009F56
0x180009f4b  xor     ebx, ebx
0x180009f4d  jmp     short loc_180009F56
0x180009f4f  lea     r13, WPP_GLOBAL_Control
0x180009f56  test    ebx, ebx
0x180009f58  jz      short loc_180009F7A
0x180009f5a  test    edi, edi
0x180009f5c  jz      short loc_180009F87
0x180009f5e  mov     rax, [rbp+57h+var_B8+8]
0x180009f62  xor     r8d, r8d; enum tagQueryUpdateAction
0x180009f65  mov     r9, [rsi+58h]; struct IFunctionDiscoveryNotification *
0x180009f69  xor     edx, edx; int
0x180009f6b  mov     rcx, r14; this
0x180009f6e  mov     [rsp+110h+var_F0], rax; unsigned __int16 *
0x180009f73  call    ?SetupPnpNotification@CServiceProvider@@IEAAJHW4tagQueryUpdateAction@@PEAUIFunctionDiscoveryNotification@@PEBG@Z; CServiceProvider::SetupPnpNotification(int,tagQueryUpdateAction,IFunctionDiscoveryNotification *,ushort const *)
0x180009f78  jmp     short loc_180009F87
0x180009f7a  cmp     qword ptr [rsi+58h], 0
0x180009f7f  mov     eax, 8000000Ah
0x180009f84  cmovnz  ebx, eax
0x180009f87  lea     rcx, [rbp+57h+pvar]; pvar
0x180009f8b  call    cs:__imp_PropVariantClear
0x180009f91  lea     rcx, [rbp+57h+var_B8]; pvar
0x180009f95  call    cs:__imp_PropVariantClear
0x180009f9b  lea     rcx, [rbp+57h+var_D0]; pvar
0x180009f9f  call    cs:__imp_PropVariantClear
0x180009fa5  lea     rcx, [rbp+57h+var_78]; pvar
0x180009fa9  call    cs:__imp_PropVariantClear
0x180009faf  lea     rcx, [rbp+57h+var_60]; pvar
0x180009fb3  call    cs:__imp_PropVariantClear
0x180009fb9  mov     rcx, [rsp+110h+pv]; pv
0x180009fbe  test    rcx, rcx
0x180009fc1  jz      short loc_180009FD2
0x180009fc3  call    cs:__imp_CoTaskMemFree
0x180009fc9  mov     [rsp+110h+pv], 0
0x180009fd2  mov     rcx, [rsp+110h+var_D8]; pv
0x180009fd7  test    rcx, rcx
0x180009fda  jz      short loc_180009FEB
0x180009fdc  call    cs:__imp_CoTaskMemFree
0x180009fe2  mov     [rsp+110h+var_D8], 0
0x180009feb  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ff2  xor     eax, eax
0x180009ff4  test    ebx, ebx
0x180009ff6  jnz     short loc_180009FFE
0x180009ff8  cmp     byte ptr [rcx+19h], 4
0x180009ffc  jmp     short loc_18000A002
0x180009ffe  cmp     byte ptr [rcx+19h], 2
0x18000a002  setnb   al
0x18000a005  cmp     rcx, r13
0x18000a008  jz      short loc_18000A02C
0x18000a00a  test    eax, eax
0x18000a00c  jz      short loc_18000A02C
0x18000a00e  mov     rcx, [rcx+10h]
0x18000a012  lea     r8, WPP_8299e7f36ddb39903502156c86dec960_Traceguids
0x18000a019  mov     edx, 15h
0x18000a01e  mov     dword ptr [rsp+110h+var_E8], ebx
0x18000a022  mov     [rsp+110h+var_F0], r14
0x18000a027  call    WPP_SF_sqd
0x18000a02c  lea     rcx, [rbp+57h+var_88]; this
0x18000a030  call    ??1CPnpxDafHelper@@QEAA@XZ; CPnpxDafHelper::~CPnpxDafHelper(void)
0x18000a035  mov     rcx, [rbp+57h+arg_18]
0x18000a039  test    rcx, rcx
0x18000a03c  jz      short loc_18000A04A
0x18000a03e  mov     rdx, [rcx]
0x18000a041  mov     rax, [rdx+10h]
0x18000a045  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a04a  mov     eax, ebx
0x18000a04c  add     rsp, 0E0h
0x18000a053  pop     r14
0x18000a055  pop     r13
0x18000a057  pop     r12
0x18000a059  pop     rdi
0x18000a05a  pop     rsi
0x18000a05b  pop     rbx
0x18000a05c  pop     rbp
0x18000a05d  retn
```
