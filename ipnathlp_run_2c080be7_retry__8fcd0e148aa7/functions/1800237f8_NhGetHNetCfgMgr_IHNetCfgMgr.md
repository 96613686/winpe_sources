# NhGetHNetCfgMgr(IHNetCfgMgr * *)

- ea: `0x1800237f8`
- end: `0x180023ae7`
- name: `?NhGetHNetCfgMgr@@YAJPEAPEAUIHNetCfgMgr@@@Z`
- size: `751`
- prototype: `__int64 __fastcall(struct IHNetCfgMgr **)`
- caller_count: `6`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002362c`
- `0x18004ff48`
- `0x1800561cc`
- `0x180056ff0`
- `0x180079f30`
- `0x180082424`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x1800237f8`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023867`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023867`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023a1b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023a1b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800238aa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800238de`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800238aa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800238de`

## pseudocode

```c
__int64 __fastcall NhGetHNetCfgMgr(struct IHNetCfgMgr **a1)
{
  PVOID *v2; // rcx
  LPVOID v3; // r10
  HRESULT Instance; // eax
  int v5; // ebx
  HRESULT v6; // eax
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  int v10; // eax
  PVOID *v11; // rcx
  LPVOID ppv; // [rsp+58h] [rbp+10h] BYREF

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  v3 = NhGITp;
  if ( !NhGITp )
  {
    EnterCriticalSection(&NhLock);
    if ( !NhGITp )
    {
      ppv = 0;
      Instance = CoCreateInstance(
                   &CLSID_StdGlobalInterfaceTable,
                   0,
                   1u,
                   &GUID_00000146_0000_0000_c000_000000000046,
                   &NhGITp);
      v5 = Instance;
      if ( Instance < 0 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_28;
        }
        v8 = 12;
        v9 = (unsigned int)Instance;
      }
      else
      {
        v6 = CoCreateInstance(&CLSID_HNetCfgMgr, 0, 1u, &GUID_85d18b6c_3032_11d4_9348_00c04f8eeb71, &ppv);
        v5 = v6;
        if ( v6 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              11,
              &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids,
              (unsigned int)v6);
          }
          (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)NhGITp + 32LL))(NhGITp, NhCfgMgrCookie);
          NhCfgMgrCookie = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)NhGITp + 16LL))(NhGITp);
          NhGITp = 0;
          goto LABEL_28;
        }
        v5 = (*(__int64 (__fastcall **)(LPVOID, LPVOID, GUID *, unsigned int *))(*(_QWORD *)NhGITp + 24LL))(
               NhGITp,
               ppv,
               &IID_IHNetCfgMgr,
               &NhCfgMgrCookie);
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        if ( v5 >= 0 )
          goto LABEL_28;
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_28;
        }
        v8 = 13;
        v9 = (unsigned int)v5;
      }
      WPP_SF_d(v7[2], v8, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, v9);
      goto LABEL_28;
    }
    v5 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids);
    }
LABEL_28:
    LeaveCriticalSection(&NhLock);
    if ( v5 < 0 )
      goto LABEL_40;
    goto LABEL_34;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_DWORD *)v2 + 7) & 0x200) != 0 && *((_BYTE *)v2 + 25) >= 5u )
  {
    WPP_SF_(v2[2], 15, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids);
LABEL_34:
    v3 = NhGITp;
  }
  v10 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, struct IHNetCfgMgr **))(*(_QWORD *)v3 + 40LL))(
          v3,
          NhCfgMgrCookie,
          &GUID_85d18b6c_3032_11d4_9348_00c04f8eeb71,
          a1);
  v5 = v10;
  if ( v10 >= 0 )
  {
LABEL_40:
    v11 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_41;
  }
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return (unsigned int)v5;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids,
      (unsigned int)v10);
    goto LABEL_40;
  }
LABEL_41:
  if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 7) & 0x200) != 0 && *((_BYTE *)v11 + 25) >= 6u )
    WPP_SF_d(v11[2], 17, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800237f8  mov     [rsp+arg_0], rbx
0x1800237fd  mov     [rsp+arg_10], rbp
0x180023802  push    rdi
0x180023803  push    r14
0x180023805  push    r15
0x180023807  sub     rsp, 30h
0x18002380b  mov     rdi, rcx
0x18002380e  mov     rcx, cs:WPP_GLOBAL_Control
0x180023815  lea     r14, WPP_GLOBAL_Control
0x18002381c  lea     r15, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x180023823  mov     ebp, 200h
0x180023828  cmp     rcx, r14
0x18002382b  jz      short loc_180023850
0x18002382d  test    [rcx+1Ch], ebp
0x180023830  jz      short loc_180023850
0x180023832  cmp     byte ptr [rcx+19h], 6
0x180023836  jb      short loc_180023850
0x180023838  mov     rcx, [rcx+10h]
0x18002383c  mov     edx, 0Ah
0x180023841  mov     r8, r15
0x180023844  call    WPP_SF_
0x180023849  mov     rcx, cs:WPP_GLOBAL_Control
0x180023850  mov     r10, cs:?NhGITp@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * NhGITp
0x180023857  test    r10, r10
0x18002385a  jnz     loc_180023A2D
0x180023860  lea     rcx, ?NhLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180023867  call    cs:__imp_EnterCriticalSection
0x18002386e  nop     dword ptr [rax+rax+00h]
0x180023873  cmp     cs:?NhGITp@@3PEAUIGlobalInterfaceTable@@EA, 0; IGlobalInterfaceTable * NhGITp
0x18002387b  jnz     loc_1800239EC
0x180023881  xor     edx, edx; pUnkOuter
0x180023883  mov     [rsp+48h+arg_8], 0
0x18002388c  lea     rax, ?NhGITp@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * NhGITp
0x180023893  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18002389a  mov     [rsp+48h+ppv], rax; ppv
0x18002389f  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x1800238a6  lea     r8d, [rdx+1]; dwClsContext
0x1800238aa  call    cs:__imp_CoCreateInstance
0x1800238b1  nop     dword ptr [rax+rax+00h]
0x1800238b6  mov     ebx, eax
0x1800238b8  test    eax, eax
0x1800238ba  js      loc_1800239CB
0x1800238c0  xor     edx, edx; pUnkOuter
0x1800238c2  lea     rax, [rsp+48h+arg_8]
0x1800238c7  lea     r9, _GUID_85d18b6c_3032_11d4_9348_00c04f8eeb71; riid
0x1800238ce  mov     [rsp+48h+ppv], rax; ppv
0x1800238d3  lea     rcx, CLSID_HNetCfgMgr; rclsid
0x1800238da  lea     r8d, [rdx+1]; dwClsContext
0x1800238de  call    cs:__imp_CoCreateInstance
0x1800238e5  nop     dword ptr [rax+rax+00h]
0x1800238ea  mov     ebx, eax
0x1800238ec  test    eax, eax
0x1800238ee  jns     short loc_180023961
0x1800238f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800238f7  cmp     rcx, r14
0x1800238fa  jz      short loc_18002391B
0x1800238fc  test    [rcx+1Ch], ebp
0x1800238ff  jz      short loc_18002391B
0x180023901  cmp     byte ptr [rcx+19h], 2
0x180023905  jb      short loc_18002391B
0x180023907  mov     rcx, [rcx+10h]
0x18002390b  mov     edx, 0Bh
0x180023910  mov     r9d, eax
0x180023913  mov     r8, r15
0x180023916  call    WPP_SF_d
0x18002391b  mov     rcx, cs:?NhGITp@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * NhGITp
0x180023922  mov     edx, cs:?NhCfgMgrCookie@@3KA; ulong NhCfgMgrCookie
0x180023928  mov     rax, [rcx]
0x18002392b  mov     rax, [rax+20h]
0x18002392f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023934  mov     rcx, cs:?NhGITp@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * NhGITp
0x18002393b  mov     cs:?NhCfgMgrCookie@@3KA, 0; ulong NhCfgMgrCookie
0x180023945  mov     rax, [rcx]
0x180023948  mov     rax, [rax+10h]
0x18002394c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023951  mov     cs:?NhGITp@@3PEAUIGlobalInterfaceTable@@EA, 0; IGlobalInterfaceTable * NhGITp
0x18002395c  jmp     loc_180023A14
0x180023961  mov     rcx, cs:?NhGITp@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * NhGITp
0x180023968  lea     r9, ?NhCfgMgrCookie@@3KA; ulong NhCfgMgrCookie
0x18002396f  mov     rdx, [rsp+48h+arg_8]
0x180023974  lea     r8, IID_IHNetCfgMgr
0x18002397b  mov     rax, [rcx]
0x18002397e  mov     rax, [rax+18h]
0x180023982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023987  mov     rcx, [rsp+48h+arg_8]
0x18002398c  mov     ebx, eax
0x18002398e  mov     rax, [rcx]
0x180023991  mov     rax, [rax+10h]
0x180023995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002399a  test    ebx, ebx
0x18002399c  jns     short loc_180023A14
0x18002399e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800239a5  cmp     rcx, r14
0x1800239a8  jz      short loc_180023A14
0x1800239aa  test    [rcx+1Ch], ebp
0x1800239ad  jz      short loc_180023A14
0x1800239af  cmp     byte ptr [rcx+19h], 2
0x1800239b3  jb      short loc_180023A14
0x1800239b5  mov     edx, 0Dh
0x1800239ba  mov     r9d, ebx
0x1800239bd  mov     rcx, [rcx+10h]
0x1800239c1  mov     r8, r15
0x1800239c4  call    WPP_SF_d
0x1800239c9  jmp     short loc_180023A14
0x1800239cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800239d2  cmp     rcx, r14
0x1800239d5  jz      short loc_180023A14
0x1800239d7  test    [rcx+1Ch], ebp
0x1800239da  jz      short loc_180023A14
0x1800239dc  cmp     byte ptr [rcx+19h], 2
0x1800239e0  jb      short loc_180023A14
0x1800239e2  mov     edx, 0Ch
0x1800239e7  mov     r9d, eax
0x1800239ea  jmp     short loc_1800239BD
0x1800239ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800239f3  xor     ebx, ebx
0x1800239f5  cmp     rcx, r14
0x1800239f8  jz      short loc_180023A14
0x1800239fa  test    [rcx+1Ch], ebp
0x1800239fd  jz      short loc_180023A14
0x1800239ff  cmp     byte ptr [rcx+19h], 5
0x180023a03  jb      short loc_180023A14
0x180023a05  mov     rcx, [rcx+10h]
0x180023a09  lea     edx, [rbx+0Eh]
0x180023a0c  mov     r8, r15
0x180023a0f  call    WPP_SF_
0x180023a14  lea     rcx, ?NhLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180023a1b  call    cs:__imp_LeaveCriticalSection
0x180023a22  nop     dword ptr [rax+rax+00h]
0x180023a27  test    ebx, ebx
0x180023a29  jns     short loc_180023A4E
0x180023a2b  jmp     short loc_180023AA5
0x180023a2d  cmp     rcx, r14
0x180023a30  jz      short loc_180023A55
0x180023a32  test    [rcx+1Ch], ebp
0x180023a35  jz      short loc_180023A55
0x180023a37  cmp     byte ptr [rcx+19h], 5
0x180023a3b  jb      short loc_180023A55
0x180023a3d  mov     rcx, [rcx+10h]
0x180023a41  mov     edx, 0Fh
0x180023a46  mov     r8, r15
0x180023a49  call    WPP_SF_
0x180023a4e  mov     r10, cs:?NhGITp@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * NhGITp
0x180023a55  mov     rax, [r10]
0x180023a58  lea     r8, _GUID_85d18b6c_3032_11d4_9348_00c04f8eeb71
0x180023a5f  mov     edx, cs:?NhCfgMgrCookie@@3KA; ulong NhCfgMgrCookie
0x180023a65  mov     r9, rdi
0x180023a68  mov     rcx, r10
0x180023a6b  mov     rax, [rax+28h]
0x180023a6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a74  mov     ebx, eax
0x180023a76  test    eax, eax
0x180023a78  jns     short loc_180023AA5
0x180023a7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180023a81  cmp     rcx, r14
0x180023a84  jz      short loc_180023AD0
0x180023a86  test    [rcx+1Ch], ebp
0x180023a89  jz      short loc_180023AAC
0x180023a8b  cmp     byte ptr [rcx+19h], 2
0x180023a8f  jb      short loc_180023AAC
0x180023a91  mov     rcx, [rcx+10h]
0x180023a95  mov     edx, 10h
0x180023a9a  mov     r9d, eax
0x180023a9d  mov     r8, r15
0x180023aa0  call    WPP_SF_d
0x180023aa5  mov     rcx, cs:WPP_GLOBAL_Control
0x180023aac  cmp     rcx, r14
0x180023aaf  jz      short loc_180023AD0
0x180023ab1  test    [rcx+1Ch], ebp
0x180023ab4  jz      short loc_180023AD0
0x180023ab6  cmp     byte ptr [rcx+19h], 6
0x180023aba  jb      short loc_180023AD0
0x180023abc  mov     rcx, [rcx+10h]
0x180023ac0  mov     edx, 11h
0x180023ac5  mov     r9d, ebx
0x180023ac8  mov     r8, r15
0x180023acb  call    WPP_SF_d
0x180023ad0  mov     rbp, [rsp+48h+arg_10]
0x180023ad5  mov     eax, ebx
0x180023ad7  mov     rbx, [rsp+48h+arg_0]
0x180023adc  add     rsp, 30h
0x180023ae0  pop     r15
0x180023ae2  pop     r14
0x180023ae4  pop     rdi
0x180023ae5  retn
```
