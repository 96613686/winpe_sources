# CTiBus::Initialize(ushort *)

- ea: `0x1800ab494`
- end: `0x1800ab8b7`
- name: `?Initialize@CTiBus@@QEAAJPEAG@Z`
- size: `1059`
- prototype: `__int64 __fastcall(CTiBus *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800aad64`

## callees

- `0x1800091a8`
- `0x18000e420`
- `0x18001bc38`
- `0x18002e600`
- `0x180033da0`
- `0x1800aaa60`
- `0x1800aabc4`
- `0x1800ab494`
- `0x1800abc78`
- `0x1800ac424`
- `0x1800ace90`
- `0x18014d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800ab5a9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800ab5a9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ab653`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ab653`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ab674`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ab674`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ab61e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ab61e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800ab6a3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800ab6a3`

## string_xrefs

- `0x1800ab593`: `StringCchCopy failed for szEnum`
- `0x1800ab8ab`: `CPNPPropertyStore::CreateInstance failed`
- `0x1800ab857`: `CoCreateInstance for UMBusDriver failed`

## pseudocode

```c
__int64 __fastcall CTiBus::Initialize(CTiBus *this, unsigned __int16 *a2)
{
  int v3; // edx
  int v4; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v6; // edx
  const char *v7; // rcx
  unsigned __int16 v8; // r8
  __int128 v9; // xmm0
  HRESULT Instance; // eax
  unsigned __int16 v11; // r8
  PVOID *v12; // rax
  unsigned int v13; // eax
  unsigned int v14; // eax
  int v15; // r8d
  int v16; // eax
  LPDWORD lpcbData; // [rsp+28h] [rbp-51h]
  LPDWORD lpcbDataa; // [rsp+28h] [rbp-51h]
  DWORD cbData; // [rsp+60h] [rbp-19h] BYREF
  DWORD Type; // [rsp+64h] [rbp-15h] BYREF
  BYTE Data[8]; // [rsp+68h] [rbp-11h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-9h] BYREF
  struct IPropertyStore *v24; // [rsp+78h] [rbp-1h] BYREF
  __int128 v25; // [rsp+80h] [rbp+7h] BYREF

  *((_DWORD *)this + 177) |= 2u;
  v24 = 0;
  v25 = 0;
  v4 = CTiDevice::Initialize(this);
  if ( v4 >= 0 )
  {
    v4 = StringCchCopyW((unsigned __int16 *)this + 638, 0x104u, L"TERMINPUT_BUS");
    if ( v4 >= 0 )
    {
      if ( (unsigned int)_o__wcsicmp(L"TERMINPUT_BUS", L"TERMINPUT_BUS_SXS") )
        v9 = xmmword_180177550;
      else
        v9 = xmmword_180177560;
      *((_OWORD *)this + 35) = v9;
      if ( *((_DWORD *)this + 184) )
      {
        if ( IsWindowsVersionOrGreater(0xAu, 0, v8) )
        {
          hKey = 0;
          *(_DWORD *)Data = 0;
          cbData = 0;
          Type = 0;
          if ( !RegOpenKeyExW(
                  HKEY_LOCAL_MACHINE,
                  L"SYSTEM\\CurrentControlSet\\Control\\Terminal Server",
                  0,
                  0x20019u,
                  &hKey) )
          {
            cbData = 4;
            if ( !RegQueryValueExW(hKey, L"SwDeviceBus", 0, &Type, Data, &cbData) && Type == 4 && *(_DWORD *)Data )
              *((_DWORD *)this + 184) = 0;
            RegCloseKey(hKey);
          }
        }
        if ( *((_DWORD *)this + 184) )
        {
          Instance = CoCreateInstance(
                       &GUID_9197e04d_2b9f_4849_8bf7_75294eb5c043,
                       0,
                       0x17u,
                       &GUID_712f2e95_9b00_4c34_b049_bd3c9c1402cc,
                       (LPVOID *)this + 91);
          v4 = Instance;
          if ( Instance >= 0 )
          {
            v4 = CPNPPropertyStore::CreateInstance(&v24);
            if ( v4 < 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v6 = 17;
                v7 = "CPNPPropertyStore::CreateInstance failed";
                goto LABEL_6;
              }
              goto LABEL_37;
            }
          }
          else
          {
            if ( Instance != -2147221164 || !IsWindowsVersionOrGreater(0xAu, 0, v11) )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v6 = 16;
                v7 = "CoCreateInstance for UMBusDriver failed";
                goto LABEL_6;
              }
              goto LABEL_37;
            }
            *((_DWORD *)this + 184) = 0;
          }
        }
      }
      v4 = CTiBus::SetupDevice(
             this,
             this,
             L"TERMINPUT_BUS",
             v24,
             L"TS_BUS\\TS_INPT",
             L"TI_BUS_GENERIC",
             0,
             0,
             *((_DWORD *)this + 161),
             1,
             (struct tagDEVICE_PROBLEM_DETAILS *)&v25);
      if ( v4 >= 0 )
        goto LABEL_39;
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v13 = RdpWppGetCurrentThreadActivityIdPrefix();
          LODWORD(lpcbDataa) = v4;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            (unsigned int)&WPP_6d85d9d5bb873cabab3b37f14470c4c2_Traceguids,
            v13,
            (__int64)"SetupDevice failed",
            lpcbDataa);
          v12 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 2u )
        {
          v14 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DSDDDDD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            19,
            v15,
            v14,
            (__int64)L"TERMINPUT_BUS",
            v4,
            v25,
            SBYTE4(v25),
            SBYTE8(v25),
            SBYTE12(v25));
        }
      }
      goto LABEL_37;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v6 = 15;
      v7 = "StringCchCopy failed for szEnum";
      goto LABEL_6;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 14;
    v7 = "CTiDevice::Initialize failed";
LABEL_6:
    LODWORD(lpcbData) = v4;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v6,
      (unsigned int)&WPP_6d85d9d5bb873cabab3b37f14470c4c2_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v7,
      lpcbData);
  }
LABEL_37:
  CTiBus::Clean(this, v3);
  v16 = *((_DWORD *)this + 177);
  if ( (v16 & 2) != 0 )
    *((_DWORD *)this + 177) = v16 | 4;
LABEL_39:
  if ( v24 )
    ((void (__fastcall *)(struct IPropertyStore *))v24->lpVtbl->Release)(v24);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800ab494  push    rbp
0x1800ab496  push    rbx
0x1800ab497  push    rsi
0x1800ab498  push    rdi
0x1800ab499  push    r12
0x1800ab49b  push    r14
0x1800ab49d  lea     rbp, [rsp-2Fh]
0x1800ab4a2  sub     rsp, 0A8h
0x1800ab4a9  mov     rax, cs:__security_cookie
0x1800ab4b0  xor     rax, rsp
0x1800ab4b3  mov     [rbp+57h+var_40], rax
0x1800ab4b7  or      dword ptr [rcx+2C4h], 2
0x1800ab4be  xorps   xmm0, xmm0
0x1800ab4c1  xor     r14d, r14d
0x1800ab4c4  mov     rbx, rcx
0x1800ab4c7  mov     [rbp+57h+var_58], r14
0x1800ab4cb  movups  [rbp+57h+var_50], xmm0
0x1800ab4cf  call    ?Initialize@CTiDevice@@MEAAJXZ; CTiDevice::Initialize(void)
0x1800ab4d4  mov     edi, eax
0x1800ab4d6  test    eax, eax
0x1800ab4d8  jns     short loc_1800AB53D
0x1800ab4da  mov     rax, cs:WPP_GLOBAL_Control
0x1800ab4e1  lea     rsi, WPP_GLOBAL_Control
0x1800ab4e8  cmp     rax, rsi
0x1800ab4eb  jz      loc_1800AB7E0
0x1800ab4f1  test    byte ptr [rax+1Ch], 8
0x1800ab4f5  jz      loc_1800AB7E0
0x1800ab4fb  cmp     byte ptr [rax+19h], 2
0x1800ab4ff  jb      loc_1800AB7E0
0x1800ab505  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ab50a  lea     edx, [r14+0Eh]
0x1800ab50e  lea     rcx, aCtideviceIniti_0; "CTiDevice::Initialize failed"
0x1800ab515  mov     dword ptr [rsp+0D0h+lpcbData], edi
0x1800ab519  lea     r8, WPP_6d85d9d5bb873cabab3b37f14470c4c2_Traceguids
0x1800ab520  mov     [rsp+0D0h+phkResult], rcx
0x1800ab525  mov     r9d, eax
0x1800ab528  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab52f  mov     rcx, [rcx+10h]
0x1800ab533  call    WPP_SF_DsD
0x1800ab538  jmp     loc_1800AB7E0
0x1800ab53d  lea     r12, aTerminputBus; "TERMINPUT_BUS"
0x1800ab544  mov     edx, 104h; unsigned __int64
0x1800ab549  mov     r8, r12; unsigned __int16 *
0x1800ab54c  lea     rcx, [rbx+4FCh]; unsigned __int16 *
0x1800ab553  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800ab558  mov     edi, eax
0x1800ab55a  test    eax, eax
0x1800ab55c  jns     short loc_1800AB59F
0x1800ab55e  mov     rax, cs:WPP_GLOBAL_Control
0x1800ab565  lea     rsi, WPP_GLOBAL_Control
0x1800ab56c  cmp     rax, rsi
0x1800ab56f  jz      loc_1800AB7E0
0x1800ab575  test    byte ptr [rax+1Ch], 8
0x1800ab579  jz      loc_1800AB7E0
0x1800ab57f  cmp     byte ptr [rax+19h], 2
0x1800ab583  jb      loc_1800AB7E0
0x1800ab589  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ab58e  mov     edx, 0Fh
0x1800ab593  lea     rcx, aStringcchcopyF_2; "StringCchCopy failed for szEnum"
0x1800ab59a  jmp     loc_1800AB515
0x1800ab59f  lea     rdx, aTerminputBusSx; "TERMINPUT_BUS_SXS"
0x1800ab5a6  mov     rcx, r12
0x1800ab5a9  call    cs:__imp__o__wcsicmp
0x1800ab5af  test    eax, eax
0x1800ab5b1  jnz     short loc_1800AB5BC
0x1800ab5b3  movups  xmm0, cs:xmmword_180177560
0x1800ab5ba  jmp     short loc_1800AB5C3
0x1800ab5bc  movups  xmm0, cs:xmmword_180177550
0x1800ab5c3  mov     esi, 0Ah
0x1800ab5c8  movdqu  xmmword ptr [rbx+230h], xmm0
0x1800ab5d0  cmp     [rbx+2E0h], r14d
0x1800ab5d7  jz      loc_1800AB6D6
0x1800ab5dd  xor     edx, edx; unsigned __int16
0x1800ab5df  mov     ecx, esi; unsigned __int16
0x1800ab5e1  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x1800ab5e6  test    al, al
0x1800ab5e8  jz      loc_1800AB67A
0x1800ab5ee  lea     rax, [rbp+57h+hKey]
0x1800ab5f2  mov     [rbp+57h+hKey], r14
0x1800ab5f6  mov     r9d, 20019h; samDesired
0x1800ab5fc  mov     [rsp+0D0h+phkResult], rax; phkResult
0x1800ab601  xor     r8d, r8d; ulOptions
0x1800ab604  mov     dword ptr [rbp+57h+Data], r14d
0x1800ab608  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x1800ab60f  mov     [rbp+57h+cbData], r14d
0x1800ab613  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800ab61a  mov     [rbp+57h+Type], r14d
0x1800ab61e  call    cs:__imp_RegOpenKeyExW
0x1800ab624  test    eax, eax
0x1800ab626  jnz     short loc_1800AB67A
0x1800ab628  mov     rcx, [rbp+57h+hKey]; hKey
0x1800ab62c  lea     rax, [rbp+57h+cbData]
0x1800ab630  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x1800ab635  lea     r9, [rbp+57h+Type]; lpType
0x1800ab639  lea     rax, [rbp+57h+Data]
0x1800ab63d  mov     [rbp+57h+cbData], 4
0x1800ab644  xor     r8d, r8d; lpReserved
0x1800ab647  mov     [rsp+0D0h+phkResult], rax; lpData
0x1800ab64c  lea     rdx, aSwdevicebus; "SwDeviceBus"
0x1800ab653  call    cs:__imp_RegQueryValueExW
0x1800ab659  test    eax, eax
0x1800ab65b  jnz     short loc_1800AB670
0x1800ab65d  cmp     [rbp+57h+Type], 4
0x1800ab661  jnz     short loc_1800AB670
0x1800ab663  cmp     dword ptr [rbp+57h+Data], r14d
0x1800ab667  jz      short loc_1800AB670
0x1800ab669  mov     [rbx+2E0h], r14d
0x1800ab670  mov     rcx, [rbp+57h+hKey]; hKey
0x1800ab674  call    cs:__imp_RegCloseKey
0x1800ab67a  cmp     [rbx+2E0h], r14d
0x1800ab681  jz      short loc_1800AB6D6
0x1800ab683  xor     edx, edx; pUnkOuter
0x1800ab685  lea     rax, [rbx+2D8h]
0x1800ab68c  lea     r9, _GUID_712f2e95_9b00_4c34_b049_bd3c9c1402cc; riid
0x1800ab693  mov     [rsp+0D0h+phkResult], rax; ppv
0x1800ab698  lea     rcx, _GUID_9197e04d_2b9f_4849_8bf7_75294eb5c043; rclsid
0x1800ab69f  lea     r8d, [rdx+17h]; dwClsContext
0x1800ab6a3  call    cs:__imp_CoCreateInstance
0x1800ab6a9  mov     edi, eax
0x1800ab6ab  test    eax, eax
0x1800ab6ad  jns     loc_1800AB863
0x1800ab6b3  cmp     eax, 80040154h
0x1800ab6b8  jnz     loc_1800AB82E
0x1800ab6be  xor     edx, edx; unsigned __int16
0x1800ab6c0  mov     ecx, esi; unsigned __int16
0x1800ab6c2  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x1800ab6c7  test    al, al
0x1800ab6c9  jz      loc_1800AB82E
0x1800ab6cf  mov     [rbx+2E0h], r14d
0x1800ab6d6  mov     r9, [rbp+57h+var_58]; struct IPropertyStore *
0x1800ab6da  lea     rax, [rbp+57h+var_50]
0x1800ab6de  mov     [rsp+0D0h+var_80], rax; struct tagDEVICE_PROBLEM_DETAILS *
0x1800ab6e3  mov     r8, r12; unsigned __int16 *
0x1800ab6e6  mov     eax, [rbx+284h]
0x1800ab6ec  mov     rdx, rbx; struct CTiDevice *
0x1800ab6ef  mov     [rsp+0D0h+var_88], 1; int
0x1800ab6f7  mov     rcx, rbx; this
0x1800ab6fa  mov     [rsp+0D0h+var_90], eax; unsigned int
0x1800ab6fe  lea     rax, aTiBusGeneric; "TI_BUS_GENERIC"
0x1800ab705  mov     [rsp+0D0h+var_98], r14d; unsigned int
0x1800ab70a  mov     [rsp+0D0h+var_A0], r14; struct _DEVPROPERTY *
0x1800ab70f  mov     [rsp+0D0h+lpcbData], rax; unsigned __int16 *
0x1800ab714  lea     rax, aTsBusTsInpt; "TS_BUS\\TS_INPT"
0x1800ab71b  mov     [rsp+0D0h+phkResult], rax; unsigned __int16 *
0x1800ab720  call    ?SetupDevice@CTiBus@@AEAAJPEAVCTiDevice@@PEAGPEAUIPropertyStore@@PEBG3PEAU_DEVPROPERTY@@KKHPEAUtagDEVICE_PROBLEM_DETAILS@@@Z; CTiBus::SetupDevice(CTiDevice *,ushort *,IPropertyStore *,ushort const *,ushort const *,_DEVPROPERTY *,ulong,ulong,int,tagDEVICE_PROBLEM_DETAILS *)
0x1800ab725  mov     edi, eax
0x1800ab727  test    eax, eax
0x1800ab729  jns     loc_1800AB7FB
0x1800ab72f  mov     rax, cs:WPP_GLOBAL_Control
0x1800ab736  lea     rsi, WPP_GLOBAL_Control
0x1800ab73d  cmp     rax, rsi
0x1800ab740  jz      loc_1800AB7E0
0x1800ab746  test    byte ptr [rax+1Ch], 8
0x1800ab74a  jz      short loc_1800AB78D
0x1800ab74c  cmp     byte ptr [rax+19h], 2
0x1800ab750  jb      short loc_1800AB78D
0x1800ab752  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ab757  lea     rcx, aSetupdeviceFai_0; "SetupDevice failed"
0x1800ab75e  mov     dword ptr [rsp+0D0h+lpcbData], edi
0x1800ab762  mov     [rsp+0D0h+phkResult], rcx
0x1800ab767  lea     r8, WPP_6d85d9d5bb873cabab3b37f14470c4c2_Traceguids
0x1800ab76e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab775  mov     edx, 12h
0x1800ab77a  mov     r9d, eax
0x1800ab77d  mov     rcx, [rcx+10h]
0x1800ab781  call    WPP_SF_DsD
0x1800ab786  mov     rax, cs:WPP_GLOBAL_Control
0x1800ab78d  cmp     rax, rsi
0x1800ab790  jz      short loc_1800AB7E0
0x1800ab792  test    byte ptr [rax+1Ch], 1
0x1800ab796  jz      short loc_1800AB7E0
0x1800ab798  cmp     byte ptr [rax+19h], 2
0x1800ab79c  jb      short loc_1800AB7E0
0x1800ab79e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ab7a3  mov     ecx, dword ptr [rbp+57h+var_50+0Ch]
0x1800ab7a6  mov     edx, 13h
0x1800ab7ab  mov     [rsp+0D0h+var_88], ecx
0x1800ab7af  mov     r9d, eax
0x1800ab7b2  mov     ecx, dword ptr [rbp+57h+var_50+8]
0x1800ab7b5  mov     [rsp+0D0h+var_90], ecx
0x1800ab7b9  mov     ecx, dword ptr [rbp+57h+var_50+4]
0x1800ab7bc  mov     [rsp+0D0h+var_98], ecx
0x1800ab7c0  mov     ecx, dword ptr [rbp+57h+var_50]
0x1800ab7c3  mov     dword ptr [rsp+0D0h+var_A0], ecx
0x1800ab7c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab7ce  mov     dword ptr [rsp+0D0h+lpcbData], edi
0x1800ab7d2  mov     [rsp+0D0h+phkResult], r12
0x1800ab7d7  mov     rcx, [rcx+10h]
0x1800ab7db  call    WPP_SF_DSDDDDD
0x1800ab7e0  mov     rcx, rbx; this
0x1800ab7e3  call    ?Clean@CTiBus@@AEAAJH@Z; CTiBus::Clean(int)
0x1800ab7e8  mov     eax, [rbx+2C4h]
0x1800ab7ee  test    al, 2
0x1800ab7f0  jz      short loc_1800AB7FB
0x1800ab7f2  or      eax, 4
0x1800ab7f5  mov     [rbx+2C4h], eax
0x1800ab7fb  mov     rcx, [rbp+57h+var_58]
0x1800ab7ff  test    rcx, rcx
0x1800ab802  jz      short loc_1800AB810
0x1800ab804  mov     rax, [rcx]
0x1800ab807  mov     rax, [rax+10h]
0x1800ab80b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab810  mov     eax, edi
0x1800ab812  mov     rcx, [rbp+57h+var_40]
0x1800ab816  xor     rcx, rsp; StackCookie
0x1800ab819  call    __security_check_cookie
0x1800ab81e  add     rsp, 0A8h
0x1800ab825  pop     r14
0x1800ab827  pop     r12
0x1800ab829  pop     rdi
0x1800ab82a  pop     rsi
0x1800ab82b  pop     rbx
0x1800ab82c  pop     rbp
0x1800ab82d  retn
0x1800ab82e  mov     rax, cs:WPP_GLOBAL_Control
0x1800ab835  lea     rsi, WPP_GLOBAL_Control
0x1800ab83c  cmp     rax, rsi
0x1800ab83f  jz      short loc_1800AB7E0
0x1800ab841  test    byte ptr [rax+1Ch], 8
0x1800ab845  jz      short loc_1800AB7E0
0x1800ab847  cmp     byte ptr [rax+19h], 2
0x1800ab84b  jb      short loc_1800AB7E0
0x1800ab84d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ab852  mov     edx, 10h
0x1800ab857  lea     rcx, aCocreateinstan_2; "CoCreateInstance for UMBusDriver failed"
0x1800ab85e  jmp     loc_1800AB515
0x1800ab863  lea     rcx, [rbp+57h+var_58]; struct IPropertyStore **
0x1800ab867  call    ?CreateInstance@CPNPPropertyStore@@SAJPEAPEAUIPropertyStore@@@Z; CPNPPropertyStore::CreateInstance(IPropertyStore * *)
0x1800ab86c  mov     edi, eax
0x1800ab86e  test    eax, eax
0x1800ab870  jns     loc_1800AB6D6
0x1800ab876  mov     rax, cs:WPP_GLOBAL_Control
0x1800ab87d  lea     rsi, WPP_GLOBAL_Control
0x1800ab884  cmp     rax, rsi
0x1800ab887  jz      loc_1800AB7E0
0x1800ab88d  test    byte ptr [rax+1Ch], 8
0x1800ab891  jz      loc_1800AB7E0
0x1800ab897  cmp     byte ptr [rax+19h], 2
0x1800ab89b  jb      loc_1800AB7E0
0x1800ab8a1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ab8a6  mov     edx, 11h
0x1800ab8ab  lea     rcx, aCpnppropertyst; "CPNPPropertyStore::CreateInstance faile"...
0x1800ab8b2  jmp     loc_1800AB515
```
