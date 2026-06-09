# CDimInterfaceTable::CreateInsertInterfaceEx(_MPRI_INTERFACE_INFO_EX *,unsigned __int64 *)

- ea: `0x180006fac`
- end: `0x18000756a`
- name: `?CreateInsertInterfaceEx@CDimInterfaceTable@@QEAAKPEAU_MPRI_INTERFACE_INFO_EX@@PEA_K@Z`
- size: `1470`
- prototype: `__int64 __fastcall(CDimInterfaceTable *this, struct _MPRI_INTERFACE_INFO_EX *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000e540`

## callees

- `0x180003f40`
- `0x180003f58`
- `0x180005340`
- `0x180005358`
- `0x180005670`
- `0x1800056c4`
- `0x180005d14`
- `0x180006fac`
- `0x1800076ac`
- `0x18000d854`
- `0x18000da10`
- `0x18000def0`
- `0x180012be0`
- `0x1800182a0`
- `0x18002223c`
- `0x180035d10`
- `0x180037d0c`
- `0x180045d40`
- `0x180045d7c`
- `0x180045da4`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `msvcrt!malloc` at `0x180007237`
- `msvcrt!malloc` at `0x180007237`
- `msvcrt!free` at `0x1800074c5`
- `msvcrt!free` at `0x1800074c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007469`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007469`

## string_xrefs

- `0x1800074f7`: `CDimInterfaceTable::CreateInsertInterfaceEx: returned %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CDimInterfaceTable::CreateInsertInterfaceEx(
        CDimInterfaceTable *this,
        struct _MPRI_INTERFACE_INFO_EX *a2,
        unsigned __int64 *a3)
{
  CDimInterfaceTable *v4; // r15
  DWORD RoutingDomainConfiguration; // ebx
  int v6; // r12d
  unsigned int v7; // r14d
  __int64 *v8; // rsi
  char v9; // r13
  __int64 v10; // rax
  __int64 v11; // rax
  unsigned int v12; // r12d
  void *v13; // rax
  __int64 v14; // r9
  char v15; // r12
  __int64 v16; // rax
  __int64 v17; // rsi
  __int64 v18; // rax
  int v20; // [rsp+60h] [rbp-A0h] BYREF
  int v21; // [rsp+64h] [rbp-9Ch]
  int v22; // [rsp+68h] [rbp-98h] BYREF
  int v23; // [rsp+6Ch] [rbp-94h]
  __int64 v24; // [rsp+70h] [rbp-90h] BYREF
  __int64 v25; // [rsp+78h] [rbp-88h] BYREF
  std::tr1::_Ref_count_base *v26; // [rsp+80h] [rbp-80h]
  unsigned __int64 *v27; // [rsp+88h] [rbp-78h]
  _BYTE v28[16]; // [rsp+90h] [rbp-70h] BYREF
  int v29; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v30; // [rsp+A4h] [rbp-5Ch] BYREF
  __int64 v31; // [rsp+B4h] [rbp-4Ch]
  __int128 v32; // [rsp+BCh] [rbp-44h]
  wchar_t pszDest[258]; // [rsp+D8h] [rbp-28h] BYREF
  int v34; // [rsp+2DCh] [rbp+1DCh]
  __int128 v35; // [rsp+2E0h] [rbp+1E0h]
  int v36; // [rsp+2F0h] [rbp+1F0h]
  int v37; // [rsp+2F4h] [rbp+1F4h]
  int v38; // [rsp+2F8h] [rbp+1F8h]
  int v39; // [rsp+2FCh] [rbp+1FCh]
  int v40; // [rsp+300h] [rbp+200h]
  int v41; // [rsp+304h] [rbp+204h]
  int v42; // [rsp+308h] [rbp+208h]
  int v43; // [rsp+30Ch] [rbp+20Ch]
  int v44; // [rsp+310h] [rbp+210h]
  int v45; // [rsp+314h] [rbp+214h]
  int v46; // [rsp+318h] [rbp+218h]
  int v47; // [rsp+31Ch] [rbp+21Ch]
  int v48; // [rsp+320h] [rbp+220h]
  int v49; // [rsp+324h] [rbp+224h]
  unsigned int v50; // [rsp+328h] [rbp+228h]
  void *Block; // [rsp+330h] [rbp+230h]
  int v52; // [rsp+338h] [rbp+238h]
  int v53; // [rsp+33Ch] [rbp+23Ch]
  __int128 v54; // [rsp+340h] [rbp+240h]
  __int64 v55; // [rsp+350h] [rbp+250h]
  __int64 v56; // [rsp+358h] [rbp+258h]
  int v57; // [rsp+360h] [rbp+260h]
  GUID ActivityId; // [rsp+370h] [rbp+270h] BYREF
  int v59; // [rsp+380h] [rbp+280h] BYREF
  _BYTE v60[2044]; // [rsp+384h] [rbp+284h] BYREF

  v27 = a3;
  v4 = g_pCDimInterfaceTable;
  ActivityId = 0;
  RoutingDomainConfiguration = 0;
  v59 = 0;
  memset_0(v60, 0, sizeof(v60));
  v6 = SetRasServerActivityId(&ActivityId);
  if ( !a2 )
    goto LABEL_2;
  if ( *(_BYTE *)a2 != 1 || (v29 = 0, memset_0(&v30, 0, 0x2C4u), v7 = *((_DWORD *)a2 + 135), v20 = 0, v7 == 6) )
  {
    RoutingDomainConfiguration = 50;
    goto LABEL_60;
  }
  *((_WORD *)a2 + 260) = 0;
  *((_WORD *)a2 + 558) = 0;
  v8 = (__int64 *)((char *)a2 + 556);
  v6 = SetActivityId((LPGUID)((char *)a2 + 556));
  v21 = v6;
  if ( v7 - 3 <= 2 )
  {
    if ( *((_DWORD *)a2 + 134) )
    {
      v23 = 2;
      v9 = 1;
      goto LABEL_13;
    }
  }
  else if ( v7 <= 2 )
  {
    if ( (gblDIMConfigInfo & 0x12) == gblDIMConfigInfo )
    {
      RoutingDomainConfiguration = 903;
      goto LABEL_60;
    }
    v9 = 0;
    v23 = 0;
LABEL_13:
    v10 = *v8;
    if ( v7 == 2 )
    {
      v11 = v10 - *(_QWORD *)&GUID_NULL.Data1;
      if ( !v11 )
        v11 = *(_QWORD *)((char *)a2 + 564) - *(_QWORD *)GUID_NULL.Data4;
      if ( v11 && !*((_BYTE *)v4 + 116) )
        goto LABEL_2;
      RoutingDomainConfiguration = ValidateQoSPolicies((char *)a2 + 572);
      if ( RoutingDomainConfiguration )
      {
LABEL_59:
        v6 = v21;
        goto LABEL_60;
      }
      v29 = *((_DWORD *)a2 + 143);
      v30 = *((_OWORD *)a2 + 36);
      v31 = *((_QWORD *)a2 + 74);
      v34 = *((_DWORD *)a2 + 150);
      v35 = *((_OWORD *)a2 + 70);
      v36 = *((_DWORD *)a2 + 284);
      v37 = *((_DWORD *)a2 + 290);
      v38 = *((_DWORD *)a2 + 291);
      v39 = *((_DWORD *)a2 + 292);
      v40 = *((_DWORD *)a2 + 293);
      v41 = *((_DWORD *)a2 + 294);
      v42 = *((_DWORD *)a2 + 295);
      v43 = *((_DWORD *)a2 + 296);
      v44 = *((_DWORD *)a2 + 297);
      v45 = *((_DWORD *)a2 + 298);
      v46 = *((_DWORD *)a2 + 299);
      v47 = *((_DWORD *)a2 + 300);
      v48 = *((_DWORD *)a2 + 301);
      v49 = *((_DWORD *)a2 + 302);
      v12 = *((_DWORD *)a2 + 310);
      v50 = v12;
      v57 = *((_DWORD *)a2 + 319);
      v54 = *(_OWORD *)((char *)a2 + 1256);
      if ( *((_QWORD *)a2 + 156) )
      {
        v13 = malloc(8LL * v12);
        Block = v13;
        v14 = 0;
        if ( v12 )
        {
          while ( 1 )
          {
            *((_QWORD *)v13 + v14) = *(_QWORD *)(*((_QWORD *)a2 + 156) + 8 * v14);
            v14 = (unsigned int)(v14 + 1);
            if ( (unsigned int)v14 >= v50 )
              break;
            v13 = Block;
          }
        }
      }
      v52 = *((_DWORD *)a2 + 303);
      v53 = *((_DWORD *)a2 + 304);
      v55 = *((_QWORD *)a2 + 153);
      v56 = *((_QWORD *)a2 + 154);
      v15 = 1;
    }
    else
    {
      v16 = v10 - *(_QWORD *)&GUID_NULL.Data1;
      if ( !v16 )
        v16 = *(_QWORD *)((char *)a2 + 564) - *(_QWORD *)GUID_NULL.Data4;
      if ( v16 || *((_DWORD *)a2 + 143) )
        goto LABEL_2;
      v15 = 0;
    }
    scoped_read_lock::scoped_read_lock((scoped_read_lock *)v28, (struct IDimSRWLock *)&gblRoutingDomainOpsLock);
    if ( *((_BYTE *)v4 + 116) )
    {
      RoutingDomainConfiguration = IsRoutingDomainAvailable((struct _GUID *)((char *)a2 + 556), &v20);
      if ( RoutingDomainConfiguration )
        goto LABEL_54;
      if ( !v20 )
      {
LABEL_32:
        RoutingDomainConfiguration = 4317;
        goto LABEL_54;
      }
      v20 = 4;
      LODWORD(v24) = 0;
      v22 = 0;
      if ( (unsigned int)GetRoutingDomainConfiguration((struct _GUID *)((char *)a2 + 556), (__int64)&v24) )
      {
        RoutingDomainConfiguration = 1168;
        goto LABEL_54;
      }
      RoutingDomainConfiguration = GetRoutingDomainConfiguration((struct _GUID *)((char *)a2 + 556), (__int64)&v22);
      if ( RoutingDomainConfiguration )
      {
LABEL_54:
        scoped_lock::~scoped_lock((scoped_lock *)v28);
        if ( Block )
          free(Block);
        if ( !RoutingDomainConfiguration && v9 )
          RouterIdentityObjectUpdateAttributes(0, 0);
        goto LABEL_59;
      }
      if ( (v22 & 0x24) == 0 )
        goto LABEL_32;
      v32 = *(_OWORD *)v8;
      if ( v7 == 2 )
        StringCchCopyW(pszDest, 0x101u, (STRSAFE_LPCWSTR)a2 + 302);
      v15 = 1;
    }
    if ( v7 == 2 && !*((_BYTE *)v4 + 117) )
      UpdateGlobalPhoneBookContext();
    CDimInterfaceTable::AcquireExclusive(v4);
    if ( !v7 )
      goto LABEL_48;
    v17 = *(_QWORD *)CDimInterfaceTable::GetInterfaceByName(v4, &v25, (char *)a2 + 8, 0);
    if ( v26 )
      std::tr1::_Ref_count_base::_Decref(v26);
    if ( v17 )
    {
      RoutingDomainConfiguration = 904;
    }
    else
    {
LABEL_48:
      CDimInterfaceTable::CreateInterface(
        (_DWORD)v4,
        (unsigned int)&v25,
        (_DWORD)a2 + 8,
        v23,
        v7,
        0,
        *((_DWORD *)a2 + 134) != 0,
        60,
        21600,
        0,
        (unsigned __int64)&v29 & -(__int64)(v15 != 0));
      if ( v25 )
      {
        CDimInterfaceTable::InsertInterface(v4, &v25);
        v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
        *v27 = v18;
      }
      else
      {
        RoutingDomainConfiguration = GetLastError();
      }
      if ( v26 )
        std::tr1::_Ref_count_base::_Decref(v26);
    }
    CDimInterfaceTable::ReleaseExclusive(v4);
    goto LABEL_54;
  }
LABEL_2:
  RoutingDomainConfiguration = 87;
LABEL_60:
  if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
  {
    LOWORD(v59) = 0;
    FormatRRASErrorString(&v59, L"CDimInterfaceTable::CreateInsertInterfaceEx: returned %d", RoutingDomainConfiguration);
    if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceInfo, &v59);
  }
  if ( v6 )
    ReSetActivityId(&ActivityId);
  return RoutingDomainConfiguration;
}

```

## disassembly

```asm
0x180006fac  mov     [rsp-8+arg_0], rbx
0x180006fb1  push    rbp
0x180006fb2  push    rsi
0x180006fb3  push    rdi
0x180006fb4  push    r12
0x180006fb6  push    r13
0x180006fb8  push    r14
0x180006fba  push    r15
0x180006fbc  lea     rbp, [rsp-0A90h]
0x180006fc4  sub     rsp, 0B90h
0x180006fcb  mov     rax, cs:__security_cookie
0x180006fd2  xor     rax, rsp
0x180006fd5  mov     [rbp+0AC0h+var_40], rax
0x180006fdc  mov     [rbp+0AC0h+var_B38], r8
0x180006fe0  mov     rdi, rdx
0x180006fe3  mov     r15, cs:?g_pCDimInterfaceTable@@3PEAVCDimInterfaceTable@@EA; CDimInterfaceTable * g_pCDimInterfaceTable
0x180006fea  xorps   xmm0, xmm0
0x180006fed  movups  xmmword ptr [rbp+0AC0h+ActivityId.Data1], xmm0
0x180006ff4  xor     ebx, ebx
0x180006ff6  mov     [rbp+0AC0h+var_840], ebx
0x180006ffc  xor     edx, edx; Val
0x180006ffe  mov     r8d, 7FCh; Size
0x180007004  lea     rcx, [rbp+0AC0h+var_83C]; void *
0x18000700b  call    memset_0
0x180007010  lea     rcx, [rbp+0AC0h+ActivityId]; ActivityId
0x180007017  call    SetRasServerActivityId
0x18000701c  mov     r12d, eax
0x18000701f  test    rdi, rdi
0x180007022  jnz     short loc_18000702E
0x180007024  mov     ebx, 57h ; 'W'
0x180007029  jmp     loc_1800074E2
0x18000702e  cmp     byte ptr [rdi], 1
0x180007031  jz      short loc_18000703D
0x180007033  mov     ebx, 32h ; '2'
0x180007038  jmp     loc_1800074E2
0x18000703d  mov     [rbp+0AC0h+var_B20], ebx
0x180007040  xor     edx, edx; Val
0x180007042  mov     r8d, 2C4h; Size
0x180007048  lea     rcx, [rbp+0AC0h+var_B1C]; void *
0x18000704c  call    memset_0
0x180007051  mov     r14d, [rdi+21Ch]
0x180007058  mov     [rsp+0BC0h+var_B60], ebx
0x18000705c  cmp     r14d, 6
0x180007060  jz      short loc_180007033
0x180007062  mov     [rdi+208h], bx
0x180007069  mov     [rdi+45Ch], bx
0x180007070  lea     rsi, [rdi+22Ch]
0x180007077  lea     rdx, [rbp+0AC0h+ActivityId]
0x18000707e  mov     rcx, rsi; ActivityId
0x180007081  call    SetActivityId
0x180007086  mov     r12d, eax
0x180007089  mov     [rsp+0BC0h+var_B5C], eax
0x18000708d  lea     eax, [r14-3]
0x180007091  mov     edx, 2
0x180007096  cmp     eax, edx
0x180007098  jbe     short loc_1800070C3
0x18000709a  cmp     r14d, edx
0x18000709d  ja      short loc_180007024
0x18000709f  mov     eax, cs:?gblDIMConfigInfo@@3U_DIM_CONFIG_INFO@@A; _DIM_CONFIG_INFO gblDIMConfigInfo
0x1800070a5  and     eax, 12h
0x1800070a8  cmp     eax, cs:?gblDIMConfigInfo@@3U_DIM_CONFIG_INFO@@A; _DIM_CONFIG_INFO gblDIMConfigInfo
0x1800070ae  jnz     short loc_1800070BA
0x1800070b0  mov     ebx, 387h
0x1800070b5  jmp     loc_1800074E2
0x1800070ba  mov     r13b, bl
0x1800070bd  mov     dword ptr [rsp+0BC0h+var_B58+4], ebx
0x1800070c1  jmp     short loc_1800070D6
0x1800070c3  cmp     [rdi+218h], ebx
0x1800070c9  jz      loc_180007024
0x1800070cf  mov     dword ptr [rsp+0BC0h+var_B58+4], edx
0x1800070d3  mov     r13b, 1
0x1800070d6  mov     rax, [rsi]
0x1800070d9  cmp     r14d, edx
0x1800070dc  jnz     loc_1800072A9
0x1800070e2  sub     rax, qword ptr cs:GUID_NULL.Data1
0x1800070e9  jnz     short loc_1800070F6
0x1800070eb  mov     rax, [rsi+8]
0x1800070ef  sub     rax, qword ptr cs:GUID_NULL.Data4
0x1800070f6  test    rax, rax
0x1800070f9  jz      short loc_180007105
0x1800070fb  cmp     [r15+74h], bl
0x1800070ff  jz      loc_180007024
0x180007105  lea     r12, [rdi+23Ch]
0x18000710c  mov     rcx, r12
0x18000710f  call    ValidateQoSPolicies
0x180007114  mov     ebx, eax
0x180007116  test    eax, eax
0x180007118  jnz     loc_1800074DD
0x18000711e  mov     ecx, [r12]
0x180007122  mov     [rbp+0AC0h+var_B20], ecx
0x180007125  movups  xmm0, xmmword ptr [r12+4]
0x18000712b  movups  [rbp+0AC0h+var_B1C], xmm0
0x18000712f  movsd   xmm1, qword ptr [r12+14h]
0x180007136  movsd   [rbp+0AC0h+var_B0C], xmm1
0x18000713b  mov     ecx, [rdi+258h]
0x180007141  mov     [rbp+0AC0h+var_8E4], ecx
0x180007147  movups  xmm0, xmmword ptr [rdi+460h]
0x18000714e  movaps  [rbp+0AC0h+var_8E0], xmm0
0x180007155  mov     eax, [rdi+470h]
0x18000715b  mov     [rbp+0AC0h+var_8D0], eax
0x180007161  mov     eax, [rdi+488h]
0x180007167  mov     [rbp+0AC0h+var_8CC], eax
0x18000716d  mov     eax, [rdi+48Ch]
0x180007173  mov     [rbp+0AC0h+var_8C8], eax
0x180007179  mov     eax, [rdi+490h]
0x18000717f  mov     [rbp+0AC0h+var_8C4], eax
0x180007185  mov     eax, [rdi+494h]
0x18000718b  mov     [rbp+0AC0h+var_8C0], eax
0x180007191  mov     eax, [rdi+498h]
0x180007197  mov     [rbp+0AC0h+var_8BC], eax
0x18000719d  mov     eax, [rdi+49Ch]
0x1800071a3  mov     [rbp+0AC0h+var_8B8], eax
0x1800071a9  mov     eax, [rdi+4A0h]
0x1800071af  mov     [rbp+0AC0h+var_8B4], eax
0x1800071b5  mov     eax, [rdi+4A4h]
0x1800071bb  mov     [rbp+0AC0h+var_8B0], eax
0x1800071c1  mov     eax, [rdi+4A8h]
0x1800071c7  mov     [rbp+0AC0h+var_8AC], eax
0x1800071cd  mov     eax, [rdi+4ACh]
0x1800071d3  mov     [rbp+0AC0h+var_8A8], eax
0x1800071d9  mov     eax, [rdi+4B0h]
0x1800071df  mov     [rbp+0AC0h+var_8A4], eax
0x1800071e5  mov     eax, [rdi+4B4h]
0x1800071eb  mov     [rbp+0AC0h+var_8A0], eax
0x1800071f1  mov     eax, [rdi+4B8h]
0x1800071f7  mov     [rbp+0AC0h+var_89C], eax
0x1800071fd  mov     r12d, [rdi+4D8h]
0x180007204  mov     [rbp+0AC0h+var_898], r12d
0x18000720b  mov     eax, [rdi+4FCh]
0x180007211  mov     [rbp+0AC0h+var_860], eax
0x180007217  movups  xmm0, xmmword ptr [rdi+4E8h]
0x18000721e  movdqu  [rbp+0AC0h+var_880], xmm0
0x180007226  cmp     qword ptr [rdi+4E0h], 0
0x18000722e  jz      short loc_180007270
0x180007230  mov     ecx, r12d
0x180007233  shl     rcx, 3; Size
0x180007237  call    cs:__imp_malloc
0x18000723d  mov     [rbp+0AC0h+Block], rax
0x180007244  xor     r9d, r9d
0x180007247  test    r12d, r12d
0x18000724a  jz      short loc_180007270
0x18000724c  mov     rcx, [rdi+4E0h]
0x180007253  mov     rdx, [rcx+r9*8]
0x180007257  mov     [rax+r9*8], rdx
0x18000725b  inc     r9d
0x18000725e  cmp     r9d, [rbp+0AC0h+var_898]
0x180007265  jnb     short loc_180007270
0x180007267  mov     rax, [rbp+0AC0h+Block]
0x18000726e  jmp     short loc_18000724C
0x180007270  mov     eax, [rdi+4BCh]
0x180007276  mov     [rbp+0AC0h+var_888], eax
0x18000727c  mov     eax, [rdi+4C0h]
0x180007282  mov     [rbp+0AC0h+var_884], eax
0x180007288  mov     rax, [rdi+4C8h]
0x18000728f  mov     [rbp+0AC0h+var_870], rax
0x180007296  mov     rax, [rdi+4D0h]
0x18000729d  mov     [rbp+0AC0h+var_868], rax
0x1800072a4  mov     r12b, 1
0x1800072a7  jmp     short loc_1800072D5
0x1800072a9  sub     rax, qword ptr cs:GUID_NULL.Data1
0x1800072b0  jnz     short loc_1800072BD
0x1800072b2  mov     rax, [rsi+8]
0x1800072b6  sub     rax, qword ptr cs:GUID_NULL.Data4
0x1800072bd  test    rax, rax
0x1800072c0  jnz     loc_180007024
0x1800072c6  cmp     [rdi+23Ch], ebx
0x1800072cc  jnz     loc_180007024
0x1800072d2  xor     r12b, r12b
0x1800072d5  lea     rdx, ?gblRoutingDomainOpsLock@@3Vcritical_section@@A; struct IDimSRWLock *
0x1800072dc  lea     rcx, [rbp+0AC0h+var_B30]; this
0x1800072e0  call    ??0scoped_read_lock@@QEAA@PEAUIDimSRWLock@@@Z; scoped_read_lock::scoped_read_lock(IDimSRWLock *)
0x1800072e5  nop
0x1800072e6  cmp     byte ptr [r15+74h], 0
0x1800072eb  jz      loc_1800073AB
0x1800072f1  lea     rdx, [rsp+0BC0h+var_B60]; int *
0x1800072f6  mov     rcx, rsi; struct _GUID *
0x1800072f9  call    ?IsRoutingDomainAvailable@@YAKPEAU_GUID@@PEAH@Z; IsRoutingDomainAvailable(_GUID *,int *)
0x1800072fe  mov     ebx, eax
0x180007300  xor     r12d, r12d
0x180007303  test    eax, eax
0x180007305  jnz     loc_1800074B0
0x18000730b  cmp     [rsp+0BC0h+var_B60], r12d
0x180007310  jnz     short loc_18000731C
0x180007312  mov     ebx, 10DDh
0x180007317  jmp     loc_1800074B0
0x18000731c  mov     [rsp+0BC0h+var_B60], 4
0x180007324  mov     dword ptr [rsp+0BC0h+var_B50], r12d
0x180007329  mov     dword ptr [rsp+0BC0h+var_B58], r12d
0x18000732e  lea     rax, [rsp+0BC0h+var_B50]
0x180007333  mov     [rsp+0BC0h+var_BA0], rax; __int64
0x180007338  lea     r9, [rsp+0BC0h+var_B60]
0x18000733d  xor     r8d, r8d
0x180007340  mov     edx, 200h
0x180007345  mov     rcx, rsi; struct _GUID *
0x180007348  call    GetRoutingDomainConfiguration
0x18000734d  test    eax, eax
0x18000734f  jnz     loc_1800073FF
0x180007355  lea     rax, [rsp+0BC0h+var_B58]
0x18000735a  mov     [rsp+0BC0h+var_BA0], rax; __int64
0x18000735f  lea     r9, [rsp+0BC0h+var_B60]
0x180007364  xor     r8d, r8d
0x180007367  mov     edx, 8000h
0x18000736c  mov     rcx, rsi; struct _GUID *
0x18000736f  call    GetRoutingDomainConfiguration
0x180007374  mov     ebx, eax
0x180007376  test    eax, eax
0x180007378  jnz     loc_1800074B0
0x18000737e  test    byte ptr [rsp+0BC0h+var_B58], 24h
0x180007383  jz      short loc_180007312
0x180007385  movups  xmm0, xmmword ptr [rsi]
0x180007388  movdqu  [rbp+0AC0h+var_B04], xmm0
0x18000738d  cmp     r14d, 2
0x180007391  jnz     short loc_1800073A8
0x180007393  lea     r8, [rdi+25Ch]; pszSrc
0x18000739a  mov     edx, 101h; cchDest
0x18000739f  lea     rcx, [rbp+0AC0h+pszDest]; pszDest
0x1800073a3  call    StringCchCopyW
0x1800073a8  mov     r12b, 1
0x1800073ab  cmp     r14d, 2
0x1800073af  jnz     short loc_1800073BD
0x1800073b1  cmp     byte ptr [r15+75h], 0
0x1800073b6  jnz     short loc_1800073BD
0x1800073b8  call    ?UpdateGlobalPhoneBookContext@@YAXXZ; UpdateGlobalPhoneBookContext(void)
0x1800073bd  mov     rcx, r15; this
0x1800073c0  call    ?AcquireExclusive@CDimInterfaceTable@@UEAAXXZ; CDimInterfaceTable::AcquireExclusive(void)
0x1800073c5  test    r14d, r14d
0x1800073c8  jz      short loc_180007409
0x1800073ca  xor     r9d, r9d
0x1800073cd  lea     r8, [rdi+8]
0x1800073d1  lea     rdx, [rsp+0BC0h+var_B48]
0x1800073d6  mov     rcx, r15
0x1800073d9  call    ?GetInterfaceByName@CDimInterfaceTable@@QEAA?AV?$shared_ptr@VCDimInterface@@@tr1@std@@PEAG_N@Z; CDimInterfaceTable::GetInterfaceByName(ushort *,bool)
0x1800073de  mov     rsi, [rax]
0x1800073e1  mov     rcx, [rbp+0AC0h+var_B40]; this
0x1800073e5  test    rcx, rcx
0x1800073e8  jz      short loc_1800073F0
0x1800073ea  call    ?_Decref@_Ref_count_base@tr1@std@@QEAAXXZ; std::tr1::_Ref_count_base::_Decref(void)
0x1800073ef  nop
0x1800073f0  test    rsi, rsi
0x1800073f3  jz      short loc_180007409
0x1800073f5  mov     ebx, 388h
0x1800073fa  jmp     loc_1800074A7
0x1800073ff  mov     ebx, 490h
0x180007404  jmp     loc_1800074B0
0x180007409  neg     r12b
0x18000740c  sbb     rax, rax
0x18000740f  lea     rcx, [rbp+0AC0h+var_B20]
0x180007413  and     rax, rcx
0x180007416  xor     r12d, r12d
0x180007419  cmp     [rdi+218h], r12d
0x180007420  setnz   cl
0x180007423  mov     [rsp+0BC0h+var_B70], rax
0x180007428  mov     [rsp+0BC0h+var_B78], r12
0x18000742d  mov     [rsp+0BC0h+var_B80], 5460h
0x180007435  mov     [rsp+0BC0h+var_B88], 3Ch ; '<'
0x18000743d  mov     [rsp+0BC0h+var_B90], cl
0x180007441  mov     [rsp+0BC0h+var_B98], r12
0x180007446  mov     dword ptr [rsp+0BC0h+var_BA0], r14d
0x18000744b  mov     r9d, dword ptr [rsp+0BC0h+var_B58+4]
0x180007450  lea     r8, [rdi+8]
0x180007454  lea     rdx, [rsp+0BC0h+var_B48]
0x180007459  mov     rcx, r15
0x18000745c  call    ?CreateInterface@CDimInterfaceTable@@QEAA?AV?$shared_ptr@VCDimInterface@@@tr1@std@@PEAGW4ROUTER_INTERFACE_STATE@@W4_ROUTER_INTERFACE_TYPE@@PEAX_NKK0PEAU_DIM_INTERFACE_OBJECT_EXTRA_INFO@@@Z; CDimInterfaceTable::CreateInterface(ushort *,ROUTER_INTERFACE_STATE,_ROUTER_INTERFACE_TYPE,void *,bool,ulong,ulong,ushort *,_DIM_INTERFACE_OBJECT_EXTRA_INFO *)
0x180007461  nop
0x180007462  cmp     [rsp+0BC0h+var_B48], r12
0x180007467  jnz     short loc_180007473
0x180007469  call    cs:__imp_GetLastError
0x18000746f  mov     ebx, eax
0x180007471  jmp     short loc_180007498
0x180007473  lea     rdx, [rsp+0BC0h+var_B48]
0x180007478  mov     rcx, r15
0x18000747b  call    ?InsertInterface@CDimInterfaceTable@@QEAAXAEBV?$shared_ptr@VCDimInterface@@@tr1@std@@@Z; CDimInterfaceTable::InsertInterface(std::tr1::shared_ptr<CDimInterface> const &)
0x180007480  mov     rcx, [rsp+0BC0h+var_B48]
0x180007485  mov     rax, [rcx]
0x180007488  mov     rax, [rax+10h]
0x18000748c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007491  mov     rcx, [rbp+0AC0h+var_B38]
0x180007495  mov     [rcx], rax
0x180007498  mov     rcx, [rbp+0AC0h+var_B40]; this
0x18000749c  test    rcx, rcx
0x18000749f  jz      short loc_1800074A7
0x1800074a1  call    ?_Decref@_Ref_count_base@tr1@std@@QEAAXXZ; std::tr1::_Ref_count_base::_Decref(void)
0x1800074a6  nop
0x1800074a7  mov     rcx, r15; this
0x1800074aa  call    ?ReleaseExclusive@CDimInterfaceTable@@UEAAXXZ; CDimInterfaceTable::ReleaseExclusive(void)
0x1800074af  nop
0x1800074b0  lea     rcx, [rbp+0AC0h+var_B30]; this
0x1800074b4  call    ??1scoped_lock@@QEAA@XZ; scoped_lock::~scoped_lock(void)
0x1800074b9  mov     rcx, [rbp+0AC0h+Block]; Block
0x1800074c0  test    rcx, rcx
0x1800074c3  jz      short loc_1800074CB
0x1800074c5  call    cs:__imp_free
0x1800074cb  test    ebx, ebx
0x1800074cd  jnz     short loc_1800074DD
0x1800074cf  test    r13b, r13b
0x1800074d2  jz      short loc_1800074DD
0x1800074d4  xor     edx, edx; BOOLEAN
0x1800074d6  xor     ecx, ecx; PVOID
0x1800074d8  call    ?RouterIdentityObjectUpdateAttributes@@YAXPEAXE@Z; RouterIdentityObjectUpdateAttributes(void *,uchar)
0x1800074dd  mov     r12d, [rsp+0BC0h+var_B5C]
  ... truncated ...
```
