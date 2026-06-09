# NhGetHNetCfgMgr(IHNetCfgMgr * *)

- ea: `0x1800307ec`
- end: `0x180030ac2`
- name: `?NhGetHNetCfgMgr@@YAJPEAPEAUIHNetCfgMgr@@@Z`
- size: `726`
- prototype: `__int64 __fastcall(struct IHNetCfgMgr **)`
- caller_count: `6`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003062c`
- `0x18004c214`
- `0x1800521c0`
- `0x180052f3c`
- `0x180074350`
- `0x18007c140`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x1800307ec`
- `0x180090010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003085b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003085b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800309fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800309fd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180030898`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800308c6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180030898`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800308c6`

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
0x1800307ec  mov     [rsp+arg_0], rbx
0x1800307f1  mov     [rsp+arg_10], rbp
0x1800307f6  push    rdi
0x1800307f7  push    r14
0x1800307f9  push    r15
0x1800307fb  sub     rsp, 30h
0x1800307ff  mov     rdi, rcx
0x180030802  mov     rcx, cs:WPP_GLOBAL_Control
0x180030809  lea     r14, WPP_GLOBAL_Control
0x180030810  lea     r15, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x180030817  mov     ebp, 200h
0x18003081c  cmp     rcx, r14
0x18003081f  jz      short loc_180030844
0x180030821  test    [rcx+1Ch], ebp
0x180030824  jz      short loc_180030844
0x180030826  cmp     byte ptr [rcx+19h], 6
0x18003082a  jb      short loc_180030844
0x18003082c  mov     rcx, [rcx+10h]
0x180030830  mov     edx, 0Ah
0x180030835  mov     r8, r15
0x180030838  call    WPP_SF_
0x18003083d  mov     rcx, cs:WPP_GLOBAL_Control
0x180030844  mov     r10, cs:?NhGITp@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * NhGITp
0x18003084b  test    r10, r10
0x18003084e  jnz     loc_180030A09
0x180030854  lea     rcx, ?NhLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003085b  call    cs:__imp_EnterCriticalSection
0x180030861  cmp     cs:?NhGITp@@3PEAUIGlobalInterfaceTable@@EA, 0; IGlobalInterfaceTable * NhGITp
0x180030869  jnz     loc_1800309CE
0x18003086f  xor     edx, edx; pUnkOuter
0x180030871  mov     [rsp+48h+arg_8], 0
0x18003087a  lea     rax, ?NhGITp@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * NhGITp
0x180030881  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180030888  mov     [rsp+48h+ppv], rax; ppv
0x18003088d  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180030894  lea     r8d, [rdx+1]; dwClsContext
0x180030898  call    cs:__imp_CoCreateInstance
0x18003089e  mov     ebx, eax
0x1800308a0  test    eax, eax
0x1800308a2  js      loc_1800309AD
0x1800308a8  xor     edx, edx; pUnkOuter
0x1800308aa  lea     rax, [rsp+48h+arg_8]
0x1800308af  lea     r9, _GUID_85d18b6c_3032_11d4_9348_00c04f8eeb71; riid
0x1800308b6  mov     [rsp+48h+ppv], rax; ppv
0x1800308bb  lea     rcx, CLSID_HNetCfgMgr; rclsid
0x1800308c2  lea     r8d, [rdx+1]; dwClsContext
0x1800308c6  call    cs:__imp_CoCreateInstance
0x1800308cc  mov     ebx, eax
0x1800308ce  test    eax, eax
0x1800308d0  jns     short loc_180030943
0x1800308d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800308d9  cmp     rcx, r14
0x1800308dc  jz      short loc_1800308FD
0x1800308de  test    [rcx+1Ch], ebp
0x1800308e1  jz      short loc_1800308FD
0x1800308e3  cmp     byte ptr [rcx+19h], 2
0x1800308e7  jb      short loc_1800308FD
0x1800308e9  mov     rcx, [rcx+10h]
0x1800308ed  mov     edx, 0Bh
0x1800308f2  mov     r9d, eax
0x1800308f5  mov     r8, r15
0x1800308f8  call    WPP_SF_d
0x1800308fd  mov     rcx, cs:?NhGITp@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * NhGITp
0x180030904  mov     edx, cs:?NhCfgMgrCookie@@3KA; ulong NhCfgMgrCookie
0x18003090a  mov     rax, [rcx]
0x18003090d  mov     rax, [rax+20h]
0x180030911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030916  mov     rcx, cs:?NhGITp@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * NhGITp
0x18003091d  mov     cs:?NhCfgMgrCookie@@3KA, 0; ulong NhCfgMgrCookie
0x180030927  mov     rax, [rcx]
0x18003092a  mov     rax, [rax+10h]
0x18003092e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030933  mov     cs:?NhGITp@@3PEAUIGlobalInterfaceTable@@EA, 0; IGlobalInterfaceTable * NhGITp
0x18003093e  jmp     loc_1800309F6
0x180030943  mov     rcx, cs:?NhGITp@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * NhGITp
0x18003094a  lea     r9, ?NhCfgMgrCookie@@3KA; ulong NhCfgMgrCookie
0x180030951  mov     rdx, [rsp+48h+arg_8]
0x180030956  lea     r8, IID_IHNetCfgMgr
0x18003095d  mov     rax, [rcx]
0x180030960  mov     rax, [rax+18h]
0x180030964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030969  mov     rcx, [rsp+48h+arg_8]
0x18003096e  mov     ebx, eax
0x180030970  mov     rax, [rcx]
0x180030973  mov     rax, [rax+10h]
0x180030977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003097c  test    ebx, ebx
0x18003097e  jns     short loc_1800309F6
0x180030980  mov     rcx, cs:WPP_GLOBAL_Control
0x180030987  cmp     rcx, r14
0x18003098a  jz      short loc_1800309F6
0x18003098c  test    [rcx+1Ch], ebp
0x18003098f  jz      short loc_1800309F6
0x180030991  cmp     byte ptr [rcx+19h], 2
0x180030995  jb      short loc_1800309F6
0x180030997  mov     edx, 0Dh
0x18003099c  mov     r9d, ebx
0x18003099f  mov     rcx, [rcx+10h]
0x1800309a3  mov     r8, r15
0x1800309a6  call    WPP_SF_d
0x1800309ab  jmp     short loc_1800309F6
0x1800309ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800309b4  cmp     rcx, r14
0x1800309b7  jz      short loc_1800309F6
0x1800309b9  test    [rcx+1Ch], ebp
0x1800309bc  jz      short loc_1800309F6
0x1800309be  cmp     byte ptr [rcx+19h], 2
0x1800309c2  jb      short loc_1800309F6
0x1800309c4  mov     edx, 0Ch
0x1800309c9  mov     r9d, eax
0x1800309cc  jmp     short loc_18003099F
0x1800309ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800309d5  xor     ebx, ebx
0x1800309d7  cmp     rcx, r14
0x1800309da  jz      short loc_1800309F6
0x1800309dc  test    [rcx+1Ch], ebp
0x1800309df  jz      short loc_1800309F6
0x1800309e1  cmp     byte ptr [rcx+19h], 5
0x1800309e5  jb      short loc_1800309F6
0x1800309e7  mov     rcx, [rcx+10h]
0x1800309eb  lea     edx, [rbx+0Eh]
0x1800309ee  mov     r8, r15
0x1800309f1  call    WPP_SF_
0x1800309f6  lea     rcx, ?NhLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800309fd  call    cs:__imp_LeaveCriticalSection
0x180030a03  test    ebx, ebx
0x180030a05  jns     short loc_180030A2A
0x180030a07  jmp     short loc_180030A81
0x180030a09  cmp     rcx, r14
0x180030a0c  jz      short loc_180030A31
0x180030a0e  test    [rcx+1Ch], ebp
0x180030a11  jz      short loc_180030A31
0x180030a13  cmp     byte ptr [rcx+19h], 5
0x180030a17  jb      short loc_180030A31
0x180030a19  mov     rcx, [rcx+10h]
0x180030a1d  mov     edx, 0Fh
0x180030a22  mov     r8, r15
0x180030a25  call    WPP_SF_
0x180030a2a  mov     r10, cs:?NhGITp@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * NhGITp
0x180030a31  mov     rax, [r10]
0x180030a34  lea     r8, _GUID_85d18b6c_3032_11d4_9348_00c04f8eeb71
0x180030a3b  mov     edx, cs:?NhCfgMgrCookie@@3KA; ulong NhCfgMgrCookie
0x180030a41  mov     r9, rdi
0x180030a44  mov     rcx, r10
0x180030a47  mov     rax, [rax+28h]
0x180030a4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a50  mov     ebx, eax
0x180030a52  test    eax, eax
0x180030a54  jns     short loc_180030A81
0x180030a56  mov     rcx, cs:WPP_GLOBAL_Control
0x180030a5d  cmp     rcx, r14
0x180030a60  jz      short loc_180030AAC
0x180030a62  test    [rcx+1Ch], ebp
0x180030a65  jz      short loc_180030A88
0x180030a67  cmp     byte ptr [rcx+19h], 2
0x180030a6b  jb      short loc_180030A88
0x180030a6d  mov     rcx, [rcx+10h]
0x180030a71  mov     edx, 10h
0x180030a76  mov     r9d, eax
0x180030a79  mov     r8, r15
0x180030a7c  call    WPP_SF_d
0x180030a81  mov     rcx, cs:WPP_GLOBAL_Control
0x180030a88  cmp     rcx, r14
0x180030a8b  jz      short loc_180030AAC
0x180030a8d  test    [rcx+1Ch], ebp
0x180030a90  jz      short loc_180030AAC
0x180030a92  cmp     byte ptr [rcx+19h], 6
0x180030a96  jb      short loc_180030AAC
0x180030a98  mov     rcx, [rcx+10h]
0x180030a9c  mov     edx, 11h
0x180030aa1  mov     r9d, ebx
0x180030aa4  mov     r8, r15
0x180030aa7  call    WPP_SF_d
0x180030aac  mov     rbp, [rsp+48h+arg_10]
0x180030ab1  mov     eax, ebx
0x180030ab3  mov     rbx, [rsp+48h+arg_0]
0x180030ab8  add     rsp, 30h
0x180030abc  pop     r15
0x180030abe  pop     r14
0x180030ac0  pop     rdi
0x180030ac1  retn
```
