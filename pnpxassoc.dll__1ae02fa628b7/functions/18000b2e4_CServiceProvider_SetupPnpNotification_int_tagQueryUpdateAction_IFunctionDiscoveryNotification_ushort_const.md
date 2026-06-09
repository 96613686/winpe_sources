# CServiceProvider::SetupPnpNotification(int,tagQueryUpdateAction,IFunctionDiscoveryNotification *,ushort const *)

- ea: `0x18000b2e4`
- end: `0x18000b4f4`
- name: `?SetupPnpNotification@CServiceProvider@@IEAAJHW4tagQueryUpdateAction@@PEAUIFunctionDiscoveryNotification@@PEBG@Z`
- size: `528`
- prototype: `__int64 __usercall@<rax>(CServiceProvider *__hidden this@<rcx>, int@<edx>, enum tagQueryUpdateAction@<r8d>, struct IFunctionDiscoveryNotification *@<r9>, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `7`
- tags: `service_task, installer_update`

## callers

- `0x180009c10`
- `0x18000a070`
- `0x18000a480`
- `0x18000b5c0`

## callees

- `0x180004efc`
- `0x18000a28c`
- `0x18000a9e8`
- `0x18000b2e4`
- `0x18000bce4`
- `0x18000bd30`
- `0x180014010`

## import_xrefs

- `ole32!PropVariantClear` at `0x18000b46e`
- `ole32!PropVariantClear` at `0x18000b46e`

## pseudocode

```c
__int64 __fastcall CServiceProvider::SetupPnpNotification(
        CServiceProvider *this,
        unsigned int a2,
        enum tagQueryUpdateAction a3,
        struct IFunctionDiscoveryNotification *a4,
        unsigned __int16 *a5)
{
  unsigned int v5; // r12d
  struct CChildDeviceInfo *v6; // r13
  struct IFunctionDiscoveryNotification *v7; // rbx
  _BYTE *v11; // rcx
  unsigned int PnpQuery; // ebx
  __int64 v13; // rcx
  int v14; // eax
  bool v15; // cf
  unsigned int v17; // [rsp+40h] [rbp-38h] BYREF
  __int64 v18; // [rsp+48h] [rbp-30h] BYREF
  struct CChildDeviceInfo *v19; // [rsp+50h] [rbp-28h] BYREF
  PROPVARIANT pvar[2]; // [rsp+58h] [rbp-20h] BYREF
  __int64 v21; // [rsp+68h] [rbp-10h]

  v5 = 0;
  v6 = 0;
  v17 = 0;
  v21 = 0;
  v7 = a4;
  v18 = 0;
  v19 = 0;
  *(_OWORD *)pvar = 0;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_8299e7f36ddb39903502156c86dec960_Traceguids);
    v11 = WPP_GLOBAL_Control;
  }
  if ( !*((_WORD *)this + 54) )
  {
    PnpQuery = StringCchPrintfW((unsigned __int16 *)this + 54, 0x20u, L"%p", this);
    if ( PnpQuery )
      goto LABEL_19;
    v11 = WPP_GLOBAL_Control;
    v7 = a4;
  }
  if ( a3 == QUA_REMOVE )
  {
    PnpQuery = CServiceProvider::CreatePnpQuery(this, a2, QUA_REMOVE, v7, a5, (wchar_t *)this + 54, 0, 0);
  }
  else
  {
    if ( a3 )
    {
      PnpQuery = -2147024809;
      goto LABEL_21;
    }
    v13 = *((_QWORD *)this + 11);
    v21 = 0;
    *(_OWORD *)pvar = 0;
    PnpQuery = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v13 + 48LL))(v13, 0, &v18);
    if ( !PnpQuery )
    {
      PnpQuery = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v18 + 40LL))(
                   v18,
                   &PKEY_PNPX_GlobalIdentity,
                   pvar);
      if ( !PnpQuery )
      {
        if ( a2 )
        {
          CServiceProvider::GetInstallableChildDevices(this, &v19, &v17);
          v5 = v17;
          v6 = v19;
        }
        PnpQuery = CServiceProvider::CreatePnpQuery(
                     this,
                     a2,
                     QUA_ADD,
                     a4,
                     (unsigned __int16 *)pvar[1],
                     (wchar_t *)this + 54,
                     v5,
                     v6);
      }
    }
    PropVariantClear(pvar);
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  if ( PnpQuery )
  {
LABEL_19:
    v11 = WPP_GLOBAL_Control;
LABEL_21:
    v14 = 0;
    v15 = v11[25] < 2u;
    goto LABEL_22;
  }
  v11 = WPP_GLOBAL_Control;
  v14 = 0;
  v15 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u;
LABEL_22:
  if ( v11 != (_BYTE *)&WPP_GLOBAL_Control )
  {
    LOBYTE(v14) = !v15;
    if ( v14 )
      WPP_SF_sqd(*((_QWORD *)v11 + 2), 34, WPP_8299e7f36ddb39903502156c86dec960_Traceguids);
  }
  return PnpQuery;
}

```

## disassembly

```asm
0x18000b2e4  mov     [rsp-40h+arg_18], r9
0x18000b2e9  push    rbp
0x18000b2ea  push    rbx
0x18000b2eb  push    rsi
0x18000b2ec  push    rdi
0x18000b2ed  push    r12
0x18000b2ef  push    r13
0x18000b2f1  push    r14
0x18000b2f3  push    r15
0x18000b2f5  mov     rbp, rsp
0x18000b2f8  sub     rsp, 78h
0x18000b2fc  xor     r12d, r12d
0x18000b2ff  xor     r13d, r13d
0x18000b302  xor     eax, eax
0x18000b304  mov     [rbp+var_38], r12d
0x18000b308  xorps   xmm0, xmm0
0x18000b30b  mov     [rbp+var_10], rax
0x18000b30f  mov     rbx, r9
0x18000b312  mov     [rbp+var_30], r12
0x18000b316  mov     r14d, r8d
0x18000b319  mov     [rbp+var_28], r13
0x18000b31d  mov     r15d, edx
0x18000b320  mov     rdi, rcx
0x18000b323  movups  xmmword ptr [rbp+pvar], xmm0
0x18000b327  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b32e  lea     rax, WPP_GLOBAL_Control
0x18000b335  cmp     rcx, rax
0x18000b338  jz      short loc_18000B361
0x18000b33a  cmp     byte ptr [rcx+19h], 4
0x18000b33e  jb      short loc_18000B361
0x18000b340  mov     rcx, [rcx+10h]
0x18000b344  lea     edx, [r12+21h]
0x18000b349  lea     r8, WPP_8299e7f36ddb39903502156c86dec960_Traceguids
0x18000b350  mov     [rsp+78h+var_58], rdi
0x18000b355  call    WPP_SF_sq
0x18000b35a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b361  lea     rsi, [rdi+6Ch]
0x18000b365  xor     eax, eax
0x18000b367  cmp     ax, [rsi]
0x18000b36a  jnz     short loc_18000B396
0x18000b36c  mov     r9, rdi
0x18000b36f  lea     r8, aP; "%p"
0x18000b376  lea     edx, [rax+20h]; unsigned __int64
0x18000b379  mov     rcx, rsi; unsigned __int16 *
0x18000b37c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b381  mov     ebx, eax
0x18000b383  test    eax, eax
0x18000b385  jnz     loc_18000B49C
0x18000b38b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b392  mov     rbx, [rbp+arg_18]
0x18000b396  mov     r8d, 1; enum tagQueryUpdateAction
0x18000b39c  cmp     r14d, r8d
0x18000b39f  jnz     short loc_18000B3CE
0x18000b3a1  mov     rax, [rbp+arg_20]
0x18000b3a5  mov     r9, rbx; struct IFunctionDiscoveryNotification *
0x18000b3a8  mov     [rsp+78h+var_40], r12; struct CChildDeviceInfo *
0x18000b3ad  mov     edx, r15d; int
0x18000b3b0  mov     [rsp+78h+var_48], r12d; unsigned int
0x18000b3b5  mov     rcx, rdi; this
0x18000b3b8  mov     [rsp+78h+var_50], rsi; unsigned __int16 *
0x18000b3bd  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x18000b3c2  call    ?CreatePnpQuery@CServiceProvider@@IEAAJHW4tagQueryUpdateAction@@PEAUIFunctionDiscoveryNotification@@PEBG2KPEAVCChildDeviceInfo@@@Z; CServiceProvider::CreatePnpQuery(int,tagQueryUpdateAction,IFunctionDiscoveryNotification *,ushort const *,ushort const *,ulong,CChildDeviceInfo *)
0x18000b3c7  mov     ebx, eax
0x18000b3c9  jmp     loc_18000B489
0x18000b3ce  test    r14d, r14d
0x18000b3d1  jnz     loc_18000B4A5
0x18000b3d7  mov     rcx, [rdi+58h]
0x18000b3db  lea     r8, [rbp+var_30]
0x18000b3df  xor     eax, eax
0x18000b3e1  xorps   xmm0, xmm0
0x18000b3e4  mov     [rbp+var_10], rax
0x18000b3e8  xor     edx, edx
0x18000b3ea  movups  xmmword ptr [rbp+pvar], xmm0
0x18000b3ee  mov     rax, [rcx]
0x18000b3f1  mov     rax, [rax+30h]
0x18000b3f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3fa  mov     ebx, eax
0x18000b3fc  test    eax, eax
0x18000b3fe  jnz     short loc_18000B46A
0x18000b400  mov     rcx, [rbp+var_30]
0x18000b404  lea     r8, [rbp+pvar]
0x18000b408  lea     rdx, PKEY_PNPX_GlobalIdentity
0x18000b40f  mov     rax, [rcx]
0x18000b412  mov     rax, [rax+28h]
0x18000b416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b41b  mov     ebx, eax
0x18000b41d  test    eax, eax
0x18000b41f  jnz     short loc_18000B46A
0x18000b421  test    r15d, r15d
0x18000b424  jz      short loc_18000B43E
0x18000b426  lea     r8, [rbp+var_38]; unsigned int *
0x18000b42a  mov     rcx, rdi; this
0x18000b42d  lea     rdx, [rbp+var_28]; struct CChildDeviceInfo **
0x18000b431  call    ?GetInstallableChildDevices@CServiceProvider@@IEAAJPEAPEAVCChildDeviceInfo@@PEAK@Z; CServiceProvider::GetInstallableChildDevices(CChildDeviceInfo * *,ulong *)
0x18000b436  mov     r12d, [rbp+var_38]
0x18000b43a  mov     r13, [rbp+var_28]
0x18000b43e  mov     rax, [rbp+pvar+8]
0x18000b442  xor     r8d, r8d; enum tagQueryUpdateAction
0x18000b445  mov     r9, [rbp+arg_18]; struct IFunctionDiscoveryNotification *
0x18000b449  mov     edx, r15d; int
0x18000b44c  mov     [rsp+78h+var_40], r13; struct CChildDeviceInfo *
0x18000b451  mov     rcx, rdi; this
0x18000b454  mov     [rsp+78h+var_48], r12d; unsigned int
0x18000b459  mov     [rsp+78h+var_50], rsi; unsigned __int16 *
0x18000b45e  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x18000b463  call    ?CreatePnpQuery@CServiceProvider@@IEAAJHW4tagQueryUpdateAction@@PEAUIFunctionDiscoveryNotification@@PEBG2KPEAVCChildDeviceInfo@@@Z; CServiceProvider::CreatePnpQuery(int,tagQueryUpdateAction,IFunctionDiscoveryNotification *,ushort const *,ushort const *,ulong,CChildDeviceInfo *)
0x18000b468  mov     ebx, eax
0x18000b46a  lea     rcx, [rbp+pvar]; pvar
0x18000b46e  call    cs:__imp_PropVariantClear
0x18000b474  mov     rcx, [rbp+var_30]
0x18000b478  test    rcx, rcx
0x18000b47b  jz      short loc_18000B489
0x18000b47d  mov     rax, [rcx]
0x18000b480  mov     rax, [rax+10h]
0x18000b484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b489  test    ebx, ebx
0x18000b48b  jnz     short loc_18000B49C
0x18000b48d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b494  xor     eax, eax
0x18000b496  cmp     byte ptr [rcx+19h], 4
0x18000b49a  jmp     short loc_18000B4B0
0x18000b49c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b4a3  jmp     short loc_18000B4AA
0x18000b4a5  mov     ebx, 80070057h
0x18000b4aa  xor     eax, eax
0x18000b4ac  cmp     byte ptr [rcx+19h], 2
0x18000b4b0  setnb   al
0x18000b4b3  lea     rdx, WPP_GLOBAL_Control
0x18000b4ba  cmp     rcx, rdx
0x18000b4bd  jz      short loc_18000B4E1
0x18000b4bf  test    eax, eax
0x18000b4c1  jz      short loc_18000B4E1
0x18000b4c3  mov     rcx, [rcx+10h]
0x18000b4c7  lea     r8, WPP_8299e7f36ddb39903502156c86dec960_Traceguids
0x18000b4ce  mov     edx, 22h ; '"'
0x18000b4d3  mov     dword ptr [rsp+78h+var_50], ebx
0x18000b4d7  mov     [rsp+78h+var_58], rdi
0x18000b4dc  call    WPP_SF_sqd
0x18000b4e1  mov     eax, ebx
0x18000b4e3  add     rsp, 78h
0x18000b4e7  pop     r15
0x18000b4e9  pop     r14
0x18000b4eb  pop     r13
0x18000b4ed  pop     r12
0x18000b4ef  pop     rdi
0x18000b4f0  pop     rsi
0x18000b4f1  pop     rbx
0x18000b4f2  pop     rbp
0x18000b4f3  retn
```
