# NfsGetServerConfiguration(_MI_Context *,_MSFT_NfsServerConfig_Self *)

- ea: `0x180010f28`
- end: `0x180011393`
- name: `?NfsGetServerConfiguration@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_MSFT_NfsServerConfig_Self@@@Z`
- size: `1131`
- prototype: `enum _MI_Result __fastcall(MI_Instance *self, struct _MSFT_NfsServerConfig_Self *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180008f30`

## callees

- `0x18000be78`
- `0x18000bff0`
- `0x18000f544`
- `0x180010184`
- `0x180010f28`
- `0x180013a40`
- `0x180014168`
- `0x18002143c`
- `0x180021598`
- `0x180021744`
- `0x180023384`
- `0x180023484`
- `0x1800234d0`
- `0x180035b02`
- `0x180035b40`
- `0x180037010`

## string_xrefs

- `0x180011275`: `Delete`
- `0x180011249`: `Write`
- `0x18001108f`: `SYSTEM\CurrentControlSet\Services\NfsServer\Parameters`
- `0x1800110f9`: `SYSTEM\CurrentControlSet\Services\NfsServer\Parameters`
- `0x180011175`: `SYSTEM\CurrentControlSet\Services\NfsServer\Parameters`
- `0x1800111dd`: `SYSTEM\CurrentControlSet\Services\NfsServer\Parameters`
- `0x180011085`: `Protocols`
- `0x18001116b`: `DirectoryCachePages`
- `0x180010fa7`: `NfsService`
- `0x18001120a`: `Mount`
- `0x18001121d`: `Unmount`
- `0x18001125f`: `Create`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NfsGetServerConfiguration(MI_Instance *self, struct _MSFT_NfsServerConfig_Self *a2)
{
  char v4; // si
  unsigned int Value; // eax
  enum _MI_Result CimProperty; // ebx
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  char v10; // dl
  __int64 v11; // rcx
  unsigned int v13; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v14; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v15; // [rsp+48h] [rbp-B8h] BYREF
  const wchar_t *v16; // [rsp+50h] [rbp-B0h] BYREF
  int v17; // [rsp+58h] [rbp-A8h]
  int v18; // [rsp+5Ch] [rbp-A4h]
  struct _MSFT_NfsServerConfig_Self *v19; // [rsp+60h] [rbp-A0h] BYREF
  int v20; // [rsp+68h] [rbp-98h]
  _BYTE v21[48]; // [rsp+70h] [rbp-90h] BYREF
  MI_Instance selfa; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v23; // [rsp+F0h] [rbp-10h]
  char v24; // [rsp+F4h] [rbp-Ch]
  unsigned int v25; // [rsp+120h] [rbp+20h]
  char v26; // [rsp+124h] [rbp+24h]
  bool v27; // [rsp+128h] [rbp+28h]
  char v28; // [rsp+129h] [rbp+29h]
  __int64 v29; // [rsp+12Ch] [rbp+2Ch]
  WCHAR ServiceName[528]; // [rsp+240h] [rbp+140h] BYREF
  _QWORD v31[8]; // [rsp+660h] [rbp+560h] BYREF

  v15 = 0;
  v14 = 0;
  v13 = 0;
  memset_0(v31, 0, sizeof(v31));
  memset_0(&selfa, 0, 0x1A0u);
  CNfsRegHive::CNfsRegHive((CNfsRegHive *)v21, 1);
  NfsService::NfsService(ServiceName, L"NfsService", L"NfsServer");
  v19 = a2;
  v20 = 0;
  CLock::AcquireLock((CLock *)&v19);
  if ( self
    && self->ft
    && !((unsigned int (__fastcall *)(MI_Instance *, void *, MI_Instance *))self->ft->IsA)(
          self,
          &MSFT_NfsServerConfig_rtti,
          &selfa) )
  {
    v16 = L"nfssvr";
    v4 = 1;
    if ( !((unsigned int (__fastcall *)(MI_Instance *, _QWORD, const wchar_t **, __int64, _DWORD))selfa.ft->SetElementAt)(
            &selfa,
            0,
            &v16,
            13,
            0)
      && !NfsService::GetServiceState((NfsService *)ServiceName, &v13) )
    {
      v23 = v13;
      v24 = 1;
      if ( !v13 )
      {
LABEL_35:
        CimProperty = MI_Instance_Destruct(self);
        goto LABEL_36;
      }
    }
  }
  else
  {
    v4 = 0;
  }
  v14 = 4;
  Value = CNfsRegHive::GetValue(
            (CNfsRegHive *)v21,
            L"SYSTEM\\CurrentControlSet\\Services\\NfsServer\\Parameters",
            L"Protocols",
            L"Protocols",
            0x10u,
            0,
            &v15,
            &v14);
  CimProperty = MapWinErrorToMIResult(Value);
  if ( CimProperty == MI_RESULT_OK )
  {
    SetServerCimProtocolProperties(v15, &selfa);
    v13 = 600;
    v14 = 4;
    v7 = CNfsRegHive::GetValue(
           (CNfsRegHive *)v21,
           L"SYSTEM\\CurrentControlSet\\Services\\NfsServer\\Parameters",
           L"LogonTimeOut",
           L"LogonTimeOut",
           0x10u,
           0,
           &v13,
           &v14);
    CimProperty = MapWinErrorToMIResult(v7);
    if ( CimProperty == MI_RESULT_OK )
    {
      v27 = v13 != -1;
      v28 = 1;
      if ( v13 == -1 )
      {
        v29 = 0;
      }
      else
      {
        LODWORD(v29) = v13;
        BYTE4(v29) = 1;
      }
      v13 = 0;
      v14 = 4;
      v8 = CNfsRegHive::GetValue(
             (CNfsRegHive *)v21,
             L"SYSTEM\\CurrentControlSet\\Services\\NfsServer\\Parameters",
             L"DirectoryCachePages",
             L"DirectoryCachePages",
             0x10u,
             0,
             &v13,
             &v14);
      CimProperty = MapWinErrorToMIResult(v8);
      if ( CimProperty == MI_RESULT_OK )
      {
        v25 = 4 * v13;
        v26 = 1;
        v13 = 0;
        v14 = 4;
        v9 = CNfsRegHive::GetValue(
               (CNfsRegHive *)v21,
               L"SYSTEM\\CurrentControlSet\\Services\\NfsServer\\Parameters",
               L"AuditBits",
               L"AuditBits",
               0x10u,
               0,
               &v13,
               &v14);
        CimProperty = MapWinErrorToMIResult(v9);
        if ( CimProperty == MI_RESULT_OK )
        {
          v10 = v13;
          v11 = v13 & 1;
          if ( (v13 & 1) != 0 )
            v31[0] = L"Mount";
          if ( (v13 & 2) != 0 )
          {
            v31[v11] = L"Unmount";
            v11 = (unsigned int)(v11 + 1);
          }
          if ( (v10 & 4) != 0 )
          {
            v31[v11] = L"Read";
            v11 = (unsigned int)(v11 + 1);
          }
          if ( (v10 & 8) != 0 )
          {
            v31[v11] = L"Write";
            v11 = (unsigned int)(v11 + 1);
          }
          if ( (v10 & 0x10) != 0 )
          {
            v31[v11] = L"Create";
            v11 = (unsigned int)(v11 + 1);
          }
          if ( (v10 & 0x20) != 0 )
          {
            v31[v11] = L"Delete";
            v11 = (unsigned int)(v11 + 1);
          }
          if ( (v10 & 0x40) != 0 )
          {
            v31[v11] = L"Lock";
            v11 = (unsigned int)(v11 + 1);
          }
          if ( v10 < 0 )
          {
            v31[v11] = L"Unlock";
            LODWORD(v11) = v11 + 1;
          }
          if ( !(_DWORD)v11
            || (v18 = 0,
                v16 = (const wchar_t *)v31,
                v17 = v11,
                (CimProperty = ((unsigned int (__fastcall *)(MI_Instance *, __int64, const wchar_t **))selfa.ft->SetElementAt)(
                                 &selfa,
                                 2,
                                 &v16)) == MI_RESULT_OK) )
          {
            CimProperty = NfsGetCimProperty(&selfa, (struct _NFS_CIMPROPERTY_REGKEY_PAIR *)off_180054C20, 0xEu);
            if ( CimProperty == MI_RESULT_OK )
              goto LABEL_35;
          }
        }
      }
    }
  }
LABEL_36:
  if ( v4 )
    MI_Instance_Destruct(&selfa);
  if ( self && self->ft )
    ((void (__fastcall *)(MI_Instance *, _QWORD))self->ft->Clone)(self, (unsigned int)CimProperty);
  CLock::ReleaseLock((CLock *)&v19);
  NfsService::~NfsService((NfsService *)ServiceName);
  CNfsRegHive::~CNfsRegHive((CNfsRegHive *)v21);
  return (unsigned int)CimProperty;
}

```

## disassembly

```asm
0x180010f28  mov     [rsp-8+arg_8], rbx
0x180010f2d  mov     [rsp-8+arg_10], rsi
0x180010f32  push    rbp
0x180010f33  push    rdi
0x180010f34  push    r14
0x180010f36  lea     rbp, [rsp-5B0h]
0x180010f3e  sub     rsp, 6B0h
0x180010f45  mov     rax, cs:__security_cookie
0x180010f4c  xor     rax, rsp
0x180010f4f  mov     [rbp+5C0h+var_20], rax
0x180010f56  mov     rbx, rdx
0x180010f59  mov     rdi, rcx
0x180010f5c  xor     r14d, r14d
0x180010f5f  mov     [rsp+6C0h+var_678], r14d
0x180010f64  mov     [rsp+6C0h+var_67C], r14d
0x180010f69  mov     [rsp+6C0h+var_680], r14d
0x180010f6e  xor     edx, edx; Val
0x180010f70  lea     r8d, [r14+40h]; Size
0x180010f74  lea     rcx, [rbp+5C0h+var_60]; void *
0x180010f7b  call    memset_0
0x180010f80  xor     edx, edx; Val
0x180010f82  mov     r8d, 1A0h; Size
0x180010f88  lea     rcx, [rbp+5C0h+self]; void *
0x180010f8c  call    memset_0
0x180010f91  lea     edx, [r14+1]; int
0x180010f95  lea     rcx, [rsp+6C0h+var_650]; this
0x180010f9a  call    ??0CNfsRegHive@@QEAA@H@Z; CNfsRegHive::CNfsRegHive(int)
0x180010f9f  nop
0x180010fa0  lea     r8, aNfsserver; "NfsServer"
0x180010fa7  lea     rdx, aNfsservice; "NfsService"
0x180010fae  lea     rcx, [rbp+5C0h+ServiceName]; lpServiceName
0x180010fb5  call    ??0NfsService@@QEAA@PEBG0@Z; NfsService::NfsService(ushort const *,ushort const *)
0x180010fba  nop
0x180010fbb  mov     [rsp+6C0h+var_660], rbx
0x180010fc0  mov     [rsp+6C0h+var_658], r14d
0x180010fc5  lea     rcx, [rsp+6C0h+var_660]; this
0x180010fca  call    ?AcquireLock@CLock@@QEAAXXZ; CLock::AcquireLock(void)
0x180010fcf  test    rdi, rdi
0x180010fd2  jz      loc_180011059
0x180010fd8  mov     rax, [rdi]
0x180010fdb  test    rax, rax
0x180010fde  jz      short loc_180011059
0x180010fe0  lea     r8, [rbp+5C0h+self]
0x180010fe4  lea     rdx, MSFT_NfsServerConfig_rtti
0x180010feb  mov     rcx, rdi
0x180010fee  mov     rax, [rax+18h]
0x180010ff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ff7  test    eax, eax
0x180010ff9  jnz     short loc_180011059
0x180010ffb  lea     rax, aNfssvr_0; "nfssvr"
0x180011002  mov     [rsp+6C0h+var_670], rax
0x180011007  mov     rax, [rbp+5C0h+self.ft]
0x18001100b  mov     [rsp+6C0h+var_6A0], r14d
0x180011010  lea     r9d, [r14+0Dh]
0x180011014  lea     r8, [rsp+6C0h+var_670]
0x180011019  xor     edx, edx
0x18001101b  lea     rcx, [rbp+5C0h+self]
0x18001101f  mov     rax, [rax+50h]
0x180011023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011028  mov     sil, 1
0x18001102b  test    eax, eax
0x18001102d  jnz     short loc_18001105C
0x18001102f  lea     rdx, [rsp+6C0h+var_680]; unsigned int *
0x180011034  lea     rcx, [rbp+5C0h+ServiceName]; this
0x18001103b  call    ?GetServiceState@NfsService@@QEAAKPEAK@Z; NfsService::GetServiceState(ulong *)
0x180011040  test    eax, eax
0x180011042  jnz     short loc_18001105C
0x180011044  mov     eax, [rsp+6C0h+var_680]
0x180011048  mov     [rbp+5C0h+var_5D0], eax
0x18001104b  mov     [rbp+5C0h+var_5CC], sil
0x18001104f  test    eax, eax
0x180011051  jz      loc_180011311
0x180011057  jmp     short loc_18001105C
0x180011059  mov     sil, r14b
0x18001105c  mov     [rsp+6C0h+var_67C], 4
0x180011064  lea     rax, [rsp+6C0h+var_67C]
0x180011069  mov     [rsp+6C0h+var_688], rax; unsigned int *
0x18001106e  lea     rax, [rsp+6C0h+var_678]
0x180011073  mov     [rsp+6C0h+var_690], rax; void *
0x180011078  mov     [rsp+6C0h+var_698], r14; unsigned int *
0x18001107d  mov     [rsp+6C0h+var_6A0], 10h; unsigned int
0x180011085  lea     r8, ValueName; "Protocols"
0x18001108c  mov     r9, r8; unsigned __int16 *
0x18001108f  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Nf"...
0x180011096  lea     rcx, [rsp+6C0h+var_650]; this
0x18001109b  call    ?GetValue@CNfsRegHive@@QEAAJPEBG00KPEAKPEAX1@Z; CNfsRegHive::GetValue(ushort const *,ushort const *,ushort const *,ulong,ulong *,void *,ulong *)
0x1800110a0  mov     ecx, eax; unsigned int
0x1800110a2  call    ?MapWinErrorToMIResult@@YA?AW4_MI_Result@@K@Z; MapWinErrorToMIResult(ulong)
0x1800110a7  mov     ebx, eax
0x1800110a9  test    eax, eax
0x1800110ab  jnz     loc_18001131F
0x1800110b1  lea     rdx, [rbp+5C0h+self]; self
0x1800110b5  mov     ecx, [rsp+6C0h+var_678]; unsigned int
0x1800110b9  call    ?SetServerCimProtocolProperties@@YAXKPEAU_MSFT_NfsServerConfig@@@Z; SetServerCimProtocolProperties(ulong,_MSFT_NfsServerConfig *)
0x1800110be  mov     [rsp+6C0h+var_680], 258h
0x1800110c6  mov     [rsp+6C0h+var_67C], 4
0x1800110ce  lea     rax, [rsp+6C0h+var_67C]
0x1800110d3  mov     [rsp+6C0h+var_688], rax; unsigned int *
0x1800110d8  lea     rax, [rsp+6C0h+var_680]
0x1800110dd  mov     [rsp+6C0h+var_690], rax; void *
0x1800110e2  mov     [rsp+6C0h+var_698], r14; unsigned int *
0x1800110e7  mov     [rsp+6C0h+var_6A0], 10h; unsigned int
0x1800110ef  lea     r8, aLogontimeout; "LogonTimeOut"
0x1800110f6  mov     r9, r8; unsigned __int16 *
0x1800110f9  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Nf"...
0x180011100  lea     rcx, [rsp+6C0h+var_650]; this
0x180011105  call    ?GetValue@CNfsRegHive@@QEAAJPEBG00KPEAKPEAX1@Z; CNfsRegHive::GetValue(ushort const *,ushort const *,ushort const *,ulong,ulong *,void *,ulong *)
0x18001110a  mov     ecx, eax; unsigned int
0x18001110c  call    ?MapWinErrorToMIResult@@YA?AW4_MI_Result@@K@Z; MapWinErrorToMIResult(ulong)
0x180011111  mov     ebx, eax
0x180011113  test    eax, eax
0x180011115  jnz     loc_18001131F
0x18001111b  mov     eax, [rsp+6C0h+var_680]
0x18001111f  or      ecx, 0FFFFFFFFh
0x180011122  cmp     eax, ecx
0x180011124  setnz   [rbp+5C0h+var_598]
0x180011128  mov     [rbp+5C0h+var_597], 1
0x18001112c  jz      short loc_180011137
0x18001112e  mov     dword ptr [rbp+5C0h+var_594], eax
0x180011131  mov     byte ptr [rbp+5C0h+var_594+4], 1
0x180011135  jmp     short loc_18001113D
0x180011137  xor     eax, eax
0x180011139  mov     [rbp+5C0h+var_594], rax
0x18001113d  mov     [rsp+6C0h+var_680], r14d
0x180011142  mov     [rsp+6C0h+var_67C], 4
0x18001114a  lea     rax, [rsp+6C0h+var_67C]
0x18001114f  mov     [rsp+6C0h+var_688], rax; unsigned int *
0x180011154  lea     rax, [rsp+6C0h+var_680]
0x180011159  mov     [rsp+6C0h+var_690], rax; void *
0x18001115e  mov     [rsp+6C0h+var_698], r14; unsigned int *
0x180011163  mov     [rsp+6C0h+var_6A0], 10h; unsigned int
0x18001116b  lea     r8, aDirectorycache_0; "DirectoryCachePages"
0x180011172  mov     r9, r8; unsigned __int16 *
0x180011175  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Nf"...
0x18001117c  lea     rcx, [rsp+6C0h+var_650]; this
0x180011181  call    ?GetValue@CNfsRegHive@@QEAAJPEBG00KPEAKPEAX1@Z; CNfsRegHive::GetValue(ushort const *,ushort const *,ushort const *,ulong,ulong *,void *,ulong *)
0x180011186  mov     ecx, eax; unsigned int
0x180011188  call    ?MapWinErrorToMIResult@@YA?AW4_MI_Result@@K@Z; MapWinErrorToMIResult(ulong)
0x18001118d  mov     ebx, eax
0x18001118f  test    eax, eax
0x180011191  jnz     loc_18001131F
0x180011197  mov     eax, [rsp+6C0h+var_680]
0x18001119b  shl     eax, 2
0x18001119e  mov     [rbp+5C0h+var_5A0], eax
0x1800111a1  mov     [rbp+5C0h+var_59C], 1
0x1800111a5  mov     [rsp+6C0h+var_680], r14d
0x1800111aa  mov     [rsp+6C0h+var_67C], 4
0x1800111b2  lea     rax, [rsp+6C0h+var_67C]
0x1800111b7  mov     [rsp+6C0h+var_688], rax; unsigned int *
0x1800111bc  lea     rax, [rsp+6C0h+var_680]
0x1800111c1  mov     [rsp+6C0h+var_690], rax; void *
0x1800111c6  mov     [rsp+6C0h+var_698], r14; unsigned int *
0x1800111cb  mov     [rsp+6C0h+var_6A0], 10h; unsigned int
0x1800111d3  lea     r8, aAuditbits; "AuditBits"
0x1800111da  mov     r9, r8; unsigned __int16 *
0x1800111dd  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Nf"...
0x1800111e4  lea     rcx, [rsp+6C0h+var_650]; this
0x1800111e9  call    ?GetValue@CNfsRegHive@@QEAAJPEBG00KPEAKPEAX1@Z; CNfsRegHive::GetValue(ushort const *,ushort const *,ushort const *,ulong,ulong *,void *,ulong *)
0x1800111ee  mov     ecx, eax; unsigned int
0x1800111f0  call    ?MapWinErrorToMIResult@@YA?AW4_MI_Result@@K@Z; MapWinErrorToMIResult(ulong)
0x1800111f5  mov     ebx, eax
0x1800111f7  test    eax, eax
0x1800111f9  jnz     loc_18001131F
0x1800111ff  mov     edx, [rsp+6C0h+var_680]
0x180011203  mov     ecx, edx
0x180011205  and     ecx, 1
0x180011208  jz      short loc_180011218
0x18001120a  lea     rax, aMount_0; "Mount"
0x180011211  mov     [rbp+5C0h+var_60], rax
0x180011218  test    dl, 2
0x18001121b  jz      short loc_18001122E
0x18001121d  lea     r8, aUnmount; "Unmount"
0x180011224  mov     [rbp+rcx*8+5C0h+var_60], r8
0x18001122c  inc     ecx
0x18001122e  test    dl, 4
0x180011231  jz      short loc_180011244
0x180011233  lea     r8, aRead; "Read"
0x18001123a  mov     [rbp+rcx*8+5C0h+var_60], r8
0x180011242  inc     ecx
0x180011244  test    dl, 8
0x180011247  jz      short loc_18001125A
0x180011249  lea     r8, aWrite; "Write"
0x180011250  mov     [rbp+rcx*8+5C0h+var_60], r8
0x180011258  inc     ecx
0x18001125a  test    dl, 10h
0x18001125d  jz      short loc_180011270
0x18001125f  lea     r8, aCreate; "Create"
0x180011266  mov     [rbp+rcx*8+5C0h+var_60], r8
0x18001126e  inc     ecx
0x180011270  test    dl, 20h
0x180011273  jz      short loc_180011286
0x180011275  lea     r8, aDelete; "Delete"
0x18001127c  mov     [rbp+rcx*8+5C0h+var_60], r8
0x180011284  inc     ecx
0x180011286  test    dl, 40h
0x180011289  jz      short loc_18001129C
0x18001128b  lea     r8, aLock; "Lock"
0x180011292  mov     [rbp+rcx*8+5C0h+var_60], r8
0x18001129a  inc     ecx
0x18001129c  test    dl, dl
0x18001129e  jns     short loc_1800112B1
0x1800112a0  lea     rdx, aUnlock; "Unlock"
0x1800112a7  mov     [rbp+rcx*8+5C0h+var_60], rdx
0x1800112af  inc     ecx
0x1800112b1  test    ecx, ecx
0x1800112b3  jz      short loc_1800112F5
0x1800112b5  mov     [rsp+6C0h+var_664], r14d
0x1800112ba  lea     rax, [rbp+5C0h+var_60]
0x1800112c1  mov     [rsp+6C0h+var_670], rax
0x1800112c6  mov     [rsp+6C0h+var_668], ecx
0x1800112ca  mov     rax, [rbp+5C0h+self.ft]
0x1800112ce  mov     [rsp+6C0h+var_6A0], r14d
0x1800112d3  mov     r9d, 1Dh
0x1800112d9  lea     r8, [rsp+6C0h+var_670]
0x1800112de  lea     edx, [r9-1Bh]
0x1800112e2  lea     rcx, [rbp+5C0h+self]
0x1800112e6  mov     rax, [rax+50h]
0x1800112ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112ef  mov     ebx, eax
0x1800112f1  test    eax, eax
0x1800112f3  jnz     short loc_18001131F
0x1800112f5  mov     r8d, 0Eh; unsigned int
0x1800112fb  lea     rdx, off_180054C20; struct _NFS_CIMPROPERTY_REGKEY_PAIR *
0x180011302  lea     rcx, [rbp+5C0h+self]; self
0x180011306  call    ?NfsGetCimProperty@@YA?AW4_MI_Result@@PEAU_MI_Instance@@PEAU_NFS_CIMPROPERTY_REGKEY_PAIR@@K@Z; NfsGetCimProperty(_MI_Instance *,_NFS_CIMPROPERTY_REGKEY_PAIR *,ulong)
0x18001130b  mov     ebx, eax
0x18001130d  test    eax, eax
0x18001130f  jnz     short loc_18001131F
0x180011311  lea     rdx, [rbp+5C0h+self]
0x180011315  mov     rcx, rdi; self
0x180011318  call    MI_Instance_Destruct
0x18001131d  mov     ebx, eax
0x18001131f  test    sil, sil
0x180011322  jz      short loc_18001132D
0x180011324  lea     rcx, [rbp+5C0h+self]; self
0x180011328  call    MI_Instance_Destruct
0x18001132d  test    rdi, rdi
0x180011330  jz      short loc_180011348
0x180011332  mov     rax, [rdi]
0x180011335  test    rax, rax
0x180011338  jz      short loc_180011348
0x18001133a  mov     edx, ebx
0x18001133c  mov     rcx, rdi
0x18001133f  mov     rax, [rax]
0x180011342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011347  nop
0x180011348  lea     rcx, [rsp+6C0h+var_660]; this
0x18001134d  call    ?ReleaseLock@CLock@@QEAAXXZ; CLock::ReleaseLock(void)
0x180011352  nop
0x180011353  lea     rcx, [rbp+5C0h+ServiceName]; this
0x18001135a  call    ??1NfsService@@QEAA@XZ; NfsService::~NfsService(void)
0x18001135f  nop
0x180011360  lea     rcx, [rsp+6C0h+var_650]; this
0x180011365  call    ??1CNfsRegHive@@QEAA@XZ; CNfsRegHive::~CNfsRegHive(void)
0x18001136a  mov     eax, ebx
0x18001136c  mov     rcx, [rbp+5C0h+var_20]
0x180011373  xor     rcx, rsp; StackCookie
0x180011376  call    __security_check_cookie
0x18001137b  lea     r11, [rsp+6C0h+var_10]
0x180011383  mov     rbx, [r11+28h]
0x180011387  mov     rsi, [r11+30h]
0x18001138b  mov     rsp, r11
0x18001138e  pop     r14
0x180011390  pop     rdi
0x180011391  pop     rbp
0x180011392  retn
```
