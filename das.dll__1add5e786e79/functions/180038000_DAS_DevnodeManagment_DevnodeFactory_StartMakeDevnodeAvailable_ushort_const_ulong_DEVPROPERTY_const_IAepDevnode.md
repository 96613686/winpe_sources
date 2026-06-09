# DAS::DevnodeManagment::DevnodeFactory::StartMakeDevnodeAvailable(ushort const *,ulong,_DEVPROPERTY * const,IAepDevnodeCreationCallback *)

- ea: `0x180038000`
- end: `0x1800382e9`
- name: `?StartMakeDevnodeAvailable@DevnodeFactory@DevnodeManagment@DAS@@UEAAJPEBGKQEAU_DEVPROPERTY@@PEAUIAepDevnodeCreationCallback@@@Z`
- size: `745`
- prototype: `int(DAS::DevnodeManagment::DevnodeFactory *__hidden this, const unsigned __int16 *, unsigned int, struct _DEVPROPERTY *const, struct IAepDevnodeCreationCallback *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800089e0`
- `0x180013be0`
- `0x18001dfe0`
- `0x18002a948`
- `0x180038000`
- `0x1800382f0`
- `0x18003bc80`
- `0x18005c798`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800380b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180038229`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180038244`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800382af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800380b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180038229`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180038244`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800382af`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003814c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003814c`

## string_xrefs

- `0x18003808f`: `onecore\base\devices\association\service\lib\devnodefactory.cpp`

## pseudocode

```c
__int64 __fastcall DAS::DevnodeManagment::DevnodeFactory::StartMakeDevnodeAvailable(
        DAS::DevnodeManagment::DevnodeFactory *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        struct _DEVPROPERTY *const a4,
        struct IAepDevnodeCreationCallback *a5)
{
  int v5; // r14d
  struct _SW_DEVICE_CREATE_INFO *v9; // rdi
  int Property; // ebx
  const unsigned __int16 *v11; // rsi
  bool v12; // cc
  const unsigned __int16 *v13; // rdx
  const WCHAR *i; // rbx
  __int64 v15; // rax
  const unsigned __int16 *Buffer; // rdx
  __int64 v17; // rax
  int DevnodeCreationInfo; // eax
  RTL_SRWLOCK *v19; // rcx
  __int128 v20; // xmm1
  __int64 (__fastcall *v21)(DAS::DevnodeManagment::DevnodeFactory *, _OWORD *, _QWORD, struct _DEVPROPERTY *, struct IAepDevnodeCreationCallback *); // rax
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  DAS::DevnodeManagment::DevnodeFactory *v24; // rcx
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-D0h] BYREF
  struct _SW_DEVICE_CREATE_INFO *v28; // [rsp+38h] [rbp-C8h] BYREF
  struct IAepDevnodeCreationCallback *v29; // [rsp+40h] [rbp-C0h]
  struct _DEVPROPERTY *v30; // [rsp+48h] [rbp-B8h]
  struct _DEVPROPERTY v31; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v32[4]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v33; // [rsp+C0h] [rbp-40h]
  struct _DEVPROPCOMPKEY v34; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v5 = 0;
  v29 = a5;
  v30 = a4;
  memset(&v34, 0, sizeof(v34));
  memset(&v31, 0, sizeof(v31));
  v28 = 0;
  v9 = 0;
  wil::AcquireSRWLockShared(&SRWLock, (RTL_SRWLOCK *)this + 28);
  if ( *((_BYTE *)this + 232) )
  {
    v11 = (const unsigned __int16 *)((char *)this + 32);
    v34.Key.fmtid.Data1 = 992796678;
    v12 = *((_QWORD *)this + 7) <= 7u;
    *(_OWORD *)&v34.Key.fmtid.Data2 = *(__int128 *)((char *)&DEVPKEY_Aep_ProviderInstanceIds + 4);
    v34.Store = DEVPROP_STORE_SYSTEM;
    v34.LocaleName = 0;
    if ( v12 )
      v13 = (const unsigned __int16 *)((char *)this + 32);
    else
      v13 = *(const unsigned __int16 **)v11;
    Property = Windows::Devices::Pnp::Internal::PnpObjectStore::GetProperty(
                 *((Windows::Devices::Pnp::Internal::PnpObjectStore **)this + 14),
                 v13,
                 &v34,
                 0,
                 &v31);
    if ( Property >= 0 )
    {
      if ( v31.Type == 8210 )
      {
        for ( i = (const WCHAR *)v31.Buffer; ; i += v15 + 1 )
        {
          if ( !*i )
          {
LABEL_34:
            Property = -2147023728;
            goto LABEL_35;
          }
          if ( CompareStringOrdinal(i, -1, a2, -1, 1) == 2 )
            break;
          ++v5;
          v15 = -1;
          do
            ++v15;
          while ( i[v15] );
        }
        DafDevPropertyFree(&v31);
        v34.Key.fmtid.Data1 = 992796678;
        v12 = *((_QWORD *)this + 7) <= 7u;
        *(_OWORD *)&v34.Key.fmtid.Data2 = *(__int128 *)((char *)&DEVPKEY_Aep_InstanceIds + 4);
        v34.Store = DEVPROP_STORE_SYSTEM;
        v34.LocaleName = 0;
        if ( !v12 )
          v11 = *(const unsigned __int16 **)v11;
        Property = Windows::Devices::Pnp::Internal::PnpObjectStore::GetProperty(
                     *((Windows::Devices::Pnp::Internal::PnpObjectStore **)this + 14),
                     v11,
                     &v34,
                     0,
                     &v31);
        if ( Property >= 0 )
        {
          if ( v31.Type != 8210 )
            goto LABEL_9;
          Buffer = (const unsigned __int16 *)v31.Buffer;
          while ( *Buffer )
          {
            if ( !v5 )
              goto LABEL_27;
            v17 = -1;
            do
              ++v17;
            while ( Buffer[v17] );
            Buffer += v17 + 1;
            --v5;
          }
          if ( v5 )
            goto LABEL_34;
LABEL_27:
          DevnodeCreationInfo = DAS::DevnodeManagment::DevnodeFactory::GetDevnodeCreationInfo(this, Buffer, &v28);
          v19 = SRWLock;
          Property = DevnodeCreationInfo;
          if ( DevnodeCreationInfo >= 0 )
          {
            v9 = v28;
            *((_QWORD *)v28 + 1) = a2;
            if ( v19 )
              ReleaseSRWLockShared(v19);
            v20 = *((_OWORD *)v9 + 1);
            v21 = *(__int64 (__fastcall **)(DAS::DevnodeManagment::DevnodeFactory *, _OWORD *, _QWORD, struct _DEVPROPERTY *, struct IAepDevnodeCreationCallback *))(*(_QWORD *)this + 24LL);
            v32[0] = *(_OWORD *)v9;
            v22 = *((_OWORD *)v9 + 2);
            v32[1] = v20;
            v23 = *((_OWORD *)v9 + 3);
            v32[2] = v22;
            v33 = *((_QWORD *)v9 + 8);
            v32[3] = v23;
            Property = v21(this, v32, a3, v30, v29);
            *((_QWORD *)v9 + 1) = 0;
          }
          else
          {
            if ( SRWLock )
              ReleaseSRWLockShared(SRWLock);
            v9 = v28;
          }
          goto LABEL_37;
        }
      }
      else
      {
LABEL_9:
        Property = -2147418113;
      }
    }
LABEL_35:
    if ( SRWLock )
      ReleaseSRWLockShared(SRWLock);
LABEL_37:
    DafDevPropertyFree(&v31);
    DAS::DevnodeManagment::DevnodeFactory::FreeDeviceCreationInfo(v24, v9);
    return (unsigned int)Property;
  }
  Property = -2140930029;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x515,
    (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodefactory.cpp",
    (const char *)0x80640013LL,
    bIgnoreCase);
  if ( SRWLock )
    ReleaseSRWLockShared(SRWLock);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x180038000  push    rbp
0x180038002  push    rbx
0x180038003  push    rsi
0x180038004  push    rdi
0x180038005  push    r12
0x180038007  push    r13
0x180038009  push    r14
0x18003800b  push    r15
0x18003800d  lea     rbp, [rsp-8]
0x180038012  sub     rsp, 108h
0x180038019  mov     rax, cs:__security_cookie
0x180038020  xor     rax, rsp
0x180038023  mov     [rbp+40h+var_50], rax
0x180038027  mov     rax, [rbp+40h+arg_20]
0x18003802b  xorps   xmm1, xmm1
0x18003802e  xor     r14d, r14d
0x180038031  mov     [rsp+140h+var_100], rax
0x180038036  xorps   xmm0, xmm0
0x180038039  mov     [rsp+140h+var_F8], r9
0x18003803e  mov     r12, rdx
0x180038041  mov     [rbp+40h+var_70.Key.fmtid.Data1], r14d
0x180038045  mov     r15, rcx
0x180038048  mov     [rsp+140h+var_F0.CompKey.Key.fmtid.Data1], r14d
0x18003804d  lea     rdx, [rcx+0E0h]
0x180038054  mov     [rsp+140h+var_108], r14
0x180038059  movups  xmmword ptr [rbp+40h+var_70.Key.fmtid.Data2], xmm0
0x18003805d  xor     eax, eax
0x18003805f  lea     rcx, [rsp+140h+SRWLock]
0x180038064  movups  xmmword ptr [rsp+140h+var_F0.CompKey.Store], xmm1
0x180038069  mov     r13d, r8d
0x18003806c  mov     edi, r14d
0x18003806f  movups  xmmword ptr [rbp+40h+var_70.Key.pid], xmm0
0x180038073  movups  xmmword ptr [rsp+140h+var_F0.CompKey.Key.fmtid.Data2], xmm1
0x180038078  movups  xmmword ptr [rsp+140h+var_F0.Type], xmm1
0x18003807d  call    ?AcquireSRWLockShared@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockShared(_RTL_SRWLOCK *)
0x180038082  cmp     [r15+0E8h], r14b
0x180038089  jnz     short loc_1800380C1
0x18003808b  mov     rcx, [rbp+48h]; this
0x18003808f  lea     r8, aOnecoreBaseDev_18; "onecore\\base\\devices\\association\\se"...
0x180038096  mov     ebx, 80640013h
0x18003809b  mov     edx, 515h; void *
0x1800380a0  mov     r9d, ebx; char *
0x1800380a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800380a8  mov     rcx, [rsp+140h+SRWLock]; SRWLock
0x1800380ad  test    rcx, rcx
0x1800380b0  jz      loc_1800382C7
0x1800380b6  call    cs:__imp_ReleaseSRWLockShared
0x1800380bc  jmp     loc_1800382C7
0x1800380c1  movups  xmm0, cs:DEVPKEY_Aep_ProviderInstanceIds+4
0x1800380c8  lea     rsi, [r15+20h]
0x1800380cc  mov     [rbp+40h+var_70.Key.fmtid.Data1], 3B2CE006h
0x1800380d3  cmp     qword ptr [rsi+18h], 7
0x1800380d8  movdqu  xmmword ptr [rbp+40h+var_70.Key.fmtid.Data2], xmm0
0x1800380dd  mov     [rbp+40h+var_70.Store], r14d
0x1800380e1  mov     [rbp+40h+var_70.LocaleName], r14
0x1800380e5  jbe     short loc_1800380EC
0x1800380e7  mov     rdx, [rsi]
0x1800380ea  jmp     short loc_1800380EF
0x1800380ec  mov     rdx, rsi; unsigned __int16 *
0x1800380ef  mov     rcx, [r15+70h]; this
0x1800380f3  lea     rax, [rsp+140h+var_F0]
0x1800380f8  xor     r9d, r9d; unsigned __int16 *
0x1800380fb  mov     qword ptr [rsp+140h+bIgnoreCase], rax; struct _DEVPROPERTY *
0x180038100  lea     r8, [rbp+40h+var_70]; struct _DEVPROPCOMPKEY *
0x180038104  call    ?GetProperty@PnpObjectStore@Internal@Pnp@Devices@Windows@@QEAAJPEBGPEBU_DEVPROPCOMPKEY@@0PEAU_DEVPROPERTY@@@Z; Windows::Devices::Pnp::Internal::PnpObjectStore::GetProperty(ushort const *,_DEVPROPCOMPKEY const *,ushort const *,_DEVPROPERTY *)
0x180038109  mov     ebx, eax
0x18003810b  test    eax, eax
0x18003810d  js      loc_1800382A5
0x180038113  cmp     [rsp+140h+var_F0.Type], 2012h
0x18003811b  jz      short loc_180038127
0x18003811d  mov     ebx, 8000FFFFh
0x180038122  jmp     loc_1800382A5
0x180038127  mov     rbx, [rsp+140h+var_F0.Buffer]
0x18003812c  xor     eax, eax
0x18003812e  cmp     [rbx], ax
0x180038131  jz      loc_1800382A0
0x180038137  or      r9d, 0FFFFFFFFh; cchCount2
0x18003813b  mov     [rsp+140h+bIgnoreCase], 1; bIgnoreCase
0x180038143  or      edx, r9d; cchCount1
0x180038146  mov     r8, r12; lpString2
0x180038149  mov     rcx, rbx; lpString1
0x18003814c  call    cs:__imp_CompareStringOrdinal
0x180038152  cmp     eax, 2
0x180038155  jz      short loc_180038173
0x180038157  inc     r14d
0x18003815a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003815e  xor     ecx, ecx
0x180038160  inc     rax
0x180038163  cmp     [rbx+rax*2], cx
0x180038167  jnz     short loc_180038160
0x180038169  lea     rbx, [rbx+rax*2]
0x18003816d  add     rbx, 2
0x180038171  jmp     short loc_18003812C
0x180038173  lea     rcx, [rsp+140h+var_F0]
0x180038178  call    DafDevPropertyFree
0x18003817d  movups  xmm0, cs:DEVPKEY_Aep_InstanceIds+4
0x180038184  xor     eax, eax
0x180038186  mov     [rbp+40h+var_70.Key.fmtid.Data1], 3B2CE006h
0x18003818d  cmp     qword ptr [rsi+18h], 7
0x180038192  movdqu  xmmword ptr [rbp+40h+var_70.Key.fmtid.Data2], xmm0
0x180038197  mov     [rbp+40h+var_70.Store], eax
0x18003819a  mov     [rbp+40h+var_70.LocaleName], rax
0x18003819e  jbe     short loc_1800381A3
0x1800381a0  mov     rsi, [rsi]
0x1800381a3  mov     rcx, [r15+70h]; this
0x1800381a7  lea     rax, [rsp+140h+var_F0]
0x1800381ac  xor     r9d, r9d; unsigned __int16 *
0x1800381af  mov     qword ptr [rsp+140h+bIgnoreCase], rax; struct _DEVPROPERTY *
0x1800381b4  lea     r8, [rbp+40h+var_70]; struct _DEVPROPCOMPKEY *
0x1800381b8  mov     rdx, rsi; unsigned __int16 *
0x1800381bb  call    ?GetProperty@PnpObjectStore@Internal@Pnp@Devices@Windows@@QEAAJPEBGPEBU_DEVPROPCOMPKEY@@0PEAU_DEVPROPERTY@@@Z; Windows::Devices::Pnp::Internal::PnpObjectStore::GetProperty(ushort const *,_DEVPROPCOMPKEY const *,ushort const *,_DEVPROPERTY *)
0x1800381c0  xor     esi, esi
0x1800381c2  mov     ebx, eax
0x1800381c4  test    eax, eax
0x1800381c6  js      loc_1800382A5
0x1800381cc  cmp     [rsp+140h+var_F0.Type], 2012h
0x1800381d4  jnz     loc_18003811D
0x1800381da  mov     rdx, [rsp+140h+var_F0.Buffer]
0x1800381df  jmp     short loc_1800381FE
0x1800381e1  test    r14d, r14d
0x1800381e4  jz      short loc_18003820C
0x1800381e6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800381ea  inc     rax
0x1800381ed  cmp     [rdx+rax*2], si
0x1800381f1  jnz     short loc_1800381EA
0x1800381f3  lea     rdx, [rdx+rax*2]
0x1800381f7  add     rdx, 2; unsigned __int16 *
0x1800381fb  dec     r14d
0x1800381fe  cmp     [rdx], si
0x180038201  jnz     short loc_1800381E1
0x180038203  test    r14d, r14d
0x180038206  jnz     loc_1800382A0
0x18003820c  lea     r8, [rsp+140h+var_108]; struct _SW_DEVICE_CREATE_INFO **
0x180038211  mov     rcx, r15; this
0x180038214  call    ?GetDevnodeCreationInfo@DevnodeFactory@DevnodeManagment@DAS@@AEAAJPEBGPEAPEAU_SW_DEVICE_CREATE_INFO@@@Z; DAS::DevnodeManagment::DevnodeFactory::GetDevnodeCreationInfo(ushort const *,_SW_DEVICE_CREATE_INFO * *)
0x180038219  mov     rcx, [rsp+140h+SRWLock]; SRWLock
0x18003821e  mov     ebx, eax
0x180038220  test    eax, eax
0x180038222  jns     short loc_180038236
0x180038224  test    rcx, rcx
0x180038227  jz      short loc_18003822F
0x180038229  call    cs:__imp_ReleaseSRWLockShared
0x18003822f  mov     rdi, [rsp+140h+var_108]
0x180038234  jmp     short loc_1800382B5
0x180038236  mov     rdi, [rsp+140h+var_108]
0x18003823b  mov     [rdi+8], r12
0x18003823f  test    rcx, rcx
0x180038242  jz      short loc_18003824A
0x180038244  call    cs:__imp_ReleaseSRWLockShared
0x18003824a  movups  xmm0, xmmword ptr [rdi]
0x18003824d  mov     rax, [r15]
0x180038250  mov     r8d, r13d
0x180038253  movups  xmm1, xmmword ptr [rdi+10h]
0x180038257  mov     rcx, [rsp+140h+var_100]
0x18003825c  lea     rdx, [rbp+40h+var_C0]
0x180038260  mov     r9, [rsp+140h+var_F8]
0x180038265  mov     rax, [rax+18h]
0x180038269  movaps  [rbp+40h+var_C0], xmm0
0x18003826d  movups  xmm0, xmmword ptr [rdi+20h]
0x180038271  mov     qword ptr [rsp+140h+bIgnoreCase], rcx
0x180038276  mov     rcx, r15
0x180038279  movaps  [rbp+40h+var_B0], xmm1
0x18003827d  movups  xmm1, xmmword ptr [rdi+30h]
0x180038281  movaps  [rbp+40h+var_A0], xmm0
0x180038285  movsd   xmm0, qword ptr [rdi+40h]
0x18003828a  movsd   [rbp+40h+var_80], xmm0
0x18003828f  movaps  [rbp+40h+var_90], xmm1
0x180038293  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038298  mov     ebx, eax
0x18003829a  mov     [rdi+8], rsi
0x18003829e  jmp     short loc_1800382B5
0x1800382a0  mov     ebx, 80070490h
0x1800382a5  mov     rcx, [rsp+140h+SRWLock]; SRWLock
0x1800382aa  test    rcx, rcx
0x1800382ad  jz      short loc_1800382B5
0x1800382af  call    cs:__imp_ReleaseSRWLockShared
0x1800382b5  lea     rcx, [rsp+140h+var_F0]
0x1800382ba  call    DafDevPropertyFree
0x1800382bf  mov     rdx, rdi; struct _SW_DEVICE_CREATE_INFO *
0x1800382c2  call    ?FreeDeviceCreationInfo@DevnodeFactory@DevnodeManagment@DAS@@AEAAXPEAU_SW_DEVICE_CREATE_INFO@@@Z; DAS::DevnodeManagment::DevnodeFactory::FreeDeviceCreationInfo(_SW_DEVICE_CREATE_INFO *)
0x1800382c7  mov     eax, ebx
0x1800382c9  mov     rcx, [rbp+40h+var_50]
0x1800382cd  xor     rcx, rsp; StackCookie
0x1800382d0  call    __security_check_cookie
0x1800382d5  add     rsp, 108h
0x1800382dc  pop     r15
0x1800382de  pop     r14
0x1800382e0  pop     r13
0x1800382e2  pop     r12
0x1800382e4  pop     rdi
0x1800382e5  pop     rsi
0x1800382e6  pop     rbx
0x1800382e7  pop     rbp
0x1800382e8  retn
```
