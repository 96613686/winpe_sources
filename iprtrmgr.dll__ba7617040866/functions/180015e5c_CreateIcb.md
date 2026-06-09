# CreateIcb

- ea: `0x180015e5c`
- end: `0x1800163d5`
- name: `CreateIcb`
- size: `1401`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, int, NET_IFINDEX InterfaceIndex)`
- caller_count: `3`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18000eb50`
- `0x18000ec98`
- `0x180022f60`

## callees

- `0x18000ac60`
- `0x18000d280`
- `0x180011790`
- `0x1800154c0`
- `0x180015bac`
- `0x180015e5c`
- `0x18001b294`
- `0x180051be4`
- `0x180057b34`
- `0x180057c8c`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`
- `0x180059010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001638e`
- `KERNEL32!DeleteCriticalSection` at `0x18001638e`
- `KERNEL32!InitializeCriticalSection` at `0x180015f4b`
- `KERNEL32!InitializeCriticalSection` at `0x180015f4b`
- `KERNEL32!HeapFree` at `0x1800163a0`
- `KERNEL32!HeapFree` at `0x1800163a0`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x1800160ab`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x1800160ab`

## string_xrefs

- `0x180015f98`: `CreateIcb: Error %d in getting routing domain Id for %ws\n`
- `0x180016152`: `GetLoopbackIdentifiersFromCompartmentId failed with error %X`
- `0x1800160c8`: `CreateIcb: ROUTER_IF_TYPE_DIALOUT: Unable to get the luid for %x: %X`
- `0x1800162c6`: `CreateIcb: Error %d in getting index for %ws\n`
- `0x18001632c`: `CreateIcb: Error %d in creating binding for %ws\n`

## pseudocode

```c
char *__fastcall CreateIcb(void *Src, __int64 a2, int a3, int a4, int a5, NET_IFINDEX InterfaceIndex)
{
  char *v11; // rbx
  _DWORD *v12; // r12
  __int64 v13; // rdx
  __int64 v14; // r8
  int v15; // eax
  unsigned int v16; // eax
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  unsigned int v23; // eax
  unsigned int LoopbackIdentifiersFromCompartmentId; // eax
  unsigned int IndexAndLuidForInterface; // eax
  unsigned int v26; // eax
  unsigned int BindingForNewIcb; // eax
  LPVOID lpMem[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v29; // [rsp+40h] [rbp-C0h]
  int v30; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v31; // [rsp+54h] [rbp-ACh]
  __int128 v32; // [rsp+64h] [rbp-9Ch]
  int v33; // [rsp+74h] [rbp-8Ch]
  int v34; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v35[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  lpMem[0] = 0;
  v34 = 0;
  memset_0(v35, 0, sizeof(v35));
  v30 = 0;
  v31 = 0;
  v33 = 0;
  v32 = 0;
  v29 = 0;
  if ( (unsigned int)AllocateIcb(Src) )
    return 0;
  v11 = (char *)lpMem[0];
  v12 = (char *)lpMem[0] + 16;
  *((_DWORD *)lpMem[0] + 4) = -1;
  *((_QWORD *)v11 + 23) = a2;
  *((_DWORD *)v11 + 36) = a3;
  *((_DWORD *)v11 + 81) = 1;
  *((_DWORD *)v11 + 129) = a5;
  *((_DWORD *)v11 + 128) = 0;
  *((_DWORD *)v11 + 176) = 1;
  *((GUID *)v11 + 43) = GUID_NULL;
  InitializeCriticalSection((LPCRITICAL_SECTION)v11 + 18);
  if ( (unsigned int)IsMultiTenancyEnabled() )
  {
    v15 = *((_DWORD *)v11 + 36);
    if ( !v15 || (unsigned int)(v15 - 2) <= 3 )
    {
      v16 = ((__int64 (__fastcall *)(__int64, char *))GetRoutingDomainIdForInterface)(a2, v11 + 688);
      if ( v16 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          LOWORD(v34) = 0;
          FormatRRASErrorString(
            &v34,
            L"CreateIcb: Error %d in getting routing domain Id for %ws\n",
            v16,
            *((_QWORD *)v11 + 9));
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v34);
        }
        goto LABEL_41;
      }
      *((_DWORD *)v11 + 176) = GetCompartmentIdForRoutingDomain(v11 + 688);
    }
  }
  *((_DWORD *)v11 + 22) = g_dwNextICBSeqNumberCounter;
  *((_QWORD *)v11 + 12) = -1;
  *((_QWORD *)v11 + 13) = -1;
  *((_QWORD *)v11 + 26) = v11 + 200;
  *((_QWORD *)v11 + 25) = v11 + 200;
  *((_QWORD *)v11 + 8) = v11 + 56;
  *((_QWORD *)v11 + 7) = v11 + 56;
  v17 = *((_DWORD *)v11 + 36);
  if ( !v17 )
  {
    *((_DWORD *)v11 + 43) = 1;
    *((_DWORD *)v11 + 42) = 3;
    *((_DWORD *)v11 + 37) = 3;
    *((_DWORD *)v11 + 45) |= 1u;
    *((_DWORD *)v11 + 131) = 1;
    *((_DWORD *)v11 + 132) = 1500;
    goto LABEL_36;
  }
  v18 = v17 - 1;
  if ( !v18 || (v19 = v18 - 1) == 0 )
  {
    *((_DWORD *)v11 + 43) = a4;
    *((_DWORD *)v11 + 42) = 2;
    *((_DWORD *)v11 + 37) = 1;
    *((_DWORD *)v11 + 131) = 1;
    *((_DWORD *)v11 + 132) = 1500;
    v26 = AddInterfaceToWanArp((struct _ICB *)v11);
    v14 = v26;
    if ( !v26 )
      goto LABEL_36;
    _InterlockedAdd(&g_dwNextICBSeqNumberCounter, 1u);
LABEL_33:
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v34) = 0;
      LOWORD(v30) = 0;
      FormatRRASErrorString(&v34, L"CreateIcb: Error %d in getting index for %ws\n", v14, *((_QWORD *)v11 + 9));
      goto LABEL_39;
    }
LABEL_41:
    DeleteCriticalSection((LPCRITICAL_SECTION)v11 + 18);
    HeapFree(IPRouterHeap, 0, v11);
    return 0;
  }
  v20 = v19 - 1;
  if ( !v20 )
  {
    *((_DWORD *)v11 + 43) = a4;
    *((_DWORD *)v11 + 42) = 0;
    *((_DWORD *)v11 + 37) = 0;
    IndexAndLuidForInterface = RtrGetIndexAndLuidForInterface(*((LPCWCH *)v11 + 9), (PNET_LUID)v11 + 20, a5);
LABEL_29:
    v14 = IndexAndLuidForInterface;
    if ( !IndexAndLuidForInterface )
      goto LABEL_36;
    goto LABEL_33;
  }
  v21 = v20 - 1;
  if ( !v21 )
  {
    *((_DWORD *)v11 + 43) = 1;
    *((_DWORD *)v11 + 42) = 2;
    *((_DWORD *)v11 + 37) = 2;
    *((_DWORD *)v11 + 131) = 1;
    *((_DWORD *)v11 + 132) = 1500;
    IndexAndLuidForInterface = AddInterfaceToWanArp((struct _ICB *)v11);
    goto LABEL_29;
  }
  v22 = v21 - 1;
  if ( v22 )
  {
    if ( v22 == 2 )
    {
      *((_DWORD *)v11 + 43) = 1;
      *((_DWORD *)v11 + 42) = 4;
      *((_DWORD *)v11 + 37) = 3;
      *v12 = InterfaceIndex;
      *((_DWORD *)v11 + 131) = 1;
      *((_DWORD *)v11 + 132) = 1500;
      v23 = ConvertInterfaceIndexToLuid(InterfaceIndex, (PNET_LUID)v11 + 20);
      if ( v23 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          LOWORD(v34) = 0;
          LOWORD(v30) = 0;
          FormatRRASErrorString(
            &v34,
            L"CreateIcb: ROUTER_IF_TYPE_DIALOUT: Unable to get the luid for %x: %X",
            InterfaceIndex,
            v23);
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasRtrmgrParamTraceInfo,
              (unsigned int)&v34,
              (_DWORD)v11 + 688,
              *((_QWORD *)v11 + 9),
              (__int64)&v30);
        }
      }
    }
  }
  else
  {
    *(_OWORD *)lpMem = 0;
    LoopbackIdentifiersFromCompartmentId = GetLoopbackIdentifiersFromCompartmentId(*((unsigned int *)v11 + 176), lpMem);
    if ( LoopbackIdentifiersFromCompartmentId )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v34) = 0;
        LOWORD(v30) = 0;
        FormatRRASErrorString(
          &v34,
          L"GetLoopbackIdentifiersFromCompartmentId failed with error %X",
          LoopbackIdentifiersFromCompartmentId);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrMgrParamTraceError,
            (unsigned int)&v34,
            (_DWORD)v11 + 688,
            *((_QWORD *)v11 + 9),
            (__int64)&v30);
      }
    }
    *((_DWORD *)v11 + 43) = 1;
    *((_DWORD *)v11 + 42) = 5;
    *((_DWORD *)v11 + 37) = 0;
    *v12 = lpMem[1];
    *((LPVOID *)v11 + 20) = lpMem[0];
  }
LABEL_36:
  BindingForNewIcb = CreateBindingForNewIcb(v11, v13, v14);
  if ( BindingForNewIcb )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v34) = 0;
      LOWORD(v30) = 0;
      FormatRRASErrorString(
        &v34,
        L"CreateIcb: Error %d in creating binding for %ws\n",
        BindingForNewIcb,
        *((_QWORD *)v11 + 9));
LABEL_39:
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v34,
          (_DWORD)v11 + 688,
          *((_QWORD *)v11 + 9),
          (__int64)&v30);
      goto LABEL_41;
    }
    goto LABEL_41;
  }
  return v11;
}

```

## disassembly

```asm
0x180015e5c  mov     [rsp-8+arg_10], rbx
0x180015e61  push    rbp
0x180015e62  push    rsi
0x180015e63  push    rdi
0x180015e64  push    r12
0x180015e66  push    r13
0x180015e68  push    r14
0x180015e6a  push    r15
0x180015e6c  lea     rbp, [rsp-790h]
0x180015e74  sub     rsp, 890h
0x180015e7b  mov     rax, cs:__security_cookie
0x180015e82  xor     rax, rsp
0x180015e85  mov     [rbp+7C0h+var_40], rax
0x180015e8c  mov     esi, r8d
0x180015e8f  mov     [rsp+8C0h+lpMem], 0
0x180015e98  mov     rdi, rdx
0x180015e9b  mov     rbx, rcx
0x180015e9e  xor     eax, eax
0x180015ea0  lea     rcx, [rbp+7C0h+var_83C]; void *
0x180015ea4  xor     edx, edx; Val
0x180015ea6  mov     [rbp+7C0h+var_840], eax
0x180015ea9  mov     r8d, 7FCh; Size
0x180015eaf  mov     r13d, r9d
0x180015eb2  call    memset_0
0x180015eb7  xorps   xmm0, xmm0
0x180015eba  lea     rdx, [rsp+8C0h+lpMem]
0x180015ebf  xor     eax, eax
0x180015ec1  mov     rcx, rbx; Src
0x180015ec4  mov     [rsp+8C0h+var_870], eax
0x180015ec8  movups  [rsp+8C0h+var_86C], xmm0
0x180015ecd  mov     [rsp+8C0h+var_84C], eax
0x180015ed1  movups  [rsp+8C0h+var_85C], xmm0
0x180015ed6  movups  [rsp+8C0h+var_880], xmm0
0x180015edb  call    AllocateIcb
0x180015ee0  test    eax, eax
0x180015ee2  jz      short loc_180015EEB
0x180015ee4  xor     eax, eax
0x180015ee6  jmp     loc_1800163AB
0x180015eeb  mov     rbx, [rsp+8C0h+lpMem]
0x180015ef0  mov     eax, 1
0x180015ef5  mov     r15d, [rbp+7C0h+arg_20]
0x180015efc  lea     r12, [rbx+10h]
0x180015f00  mov     dword ptr [r12], 0FFFFFFFFh
0x180015f08  lea     rcx, [rbx+2D0h]; lpCriticalSection
0x180015f0f  mov     [rbx+0B8h], rdi
0x180015f16  mov     [rbx+90h], esi
0x180015f1c  lea     rsi, [rbx+2B0h]
0x180015f23  mov     [rbx+144h], eax
0x180015f29  mov     [rbx+204h], r15d
0x180015f30  mov     dword ptr [rbx+200h], 0
0x180015f3a  mov     [rbx+2C0h], eax
0x180015f40  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180015f47  movdqu  xmmword ptr [rsi], xmm0
0x180015f4b  call    cs:__imp_InitializeCriticalSection
0x180015f51  call    IsMultiTenancyEnabled
0x180015f56  test    eax, eax
0x180015f58  jz      loc_180015FEA
0x180015f5e  mov     eax, [rbx+90h]
0x180015f64  test    eax, eax
0x180015f66  jz      short loc_180015F70
0x180015f68  add     eax, 0FFFFFFFEh
0x180015f6b  cmp     eax, 3
0x180015f6e  ja      short loc_180015FEA
0x180015f70  mov     rax, cs:GetRoutingDomainIdForInterface
0x180015f77  mov     rdx, rsi
0x180015f7a  mov     rcx, rdi
0x180015f7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f82  test    eax, eax
0x180015f84  jz      short loc_180015FDC
0x180015f86  mov     dil, 40h ; '@'
0x180015f89  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180015f90  jz      loc_180016387
0x180015f96  xor     ecx, ecx
0x180015f98  lea     rdx, aCreateicbError_1; "CreateIcb: Error %d in getting routing "...
0x180015f9f  mov     word ptr [rbp+7C0h+var_840], cx
0x180015fa3  mov     r8d, eax
0x180015fa6  mov     r9, [rbx+48h]
0x180015faa  lea     rcx, [rbp+7C0h+var_840]
0x180015fae  call    FormatRRASErrorString
0x180015fb3  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180015fba  jz      loc_180016387
0x180015fc0  lea     r8, [rbp+7C0h+var_840]
0x180015fc4  lea     rdx, RasRtrMgrTraceError
0x180015fcb  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180015fd2  call    McTemplateU0z_EventWriteTransfer
0x180015fd7  jmp     loc_180016387
0x180015fdc  mov     rcx, rsi
0x180015fdf  call    GetCompartmentIdForRoutingDomain
0x180015fe4  mov     [rbx+2C0h], eax
0x180015fea  mov     eax, cs:g_dwNextICBSeqNumberCounter
0x180015ff0  lea     r14, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180015ff7  mov     [rbx+58h], eax
0x180015ffa  mov     dil, 40h ; '@'
0x180015ffd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016001  mov     [rbx+60h], rax
0x180016005  mov     [rbx+68h], rax
0x180016009  lea     rax, [rbx+0C8h]
0x180016010  mov     [rax+8], rax
0x180016014  mov     [rax], rax
0x180016017  lea     rax, [rbx+38h]
0x18001601b  mov     [rax+8], rax
0x18001601f  mov     [rax], rax
0x180016022  mov     ecx, [rbx+90h]
0x180016028  test    ecx, ecx
0x18001602a  jz      loc_1800162D8
0x180016030  sub     ecx, 1
0x180016033  jz      loc_18001626E
0x180016039  sub     ecx, 1
0x18001603c  jz      loc_18001626E
0x180016042  sub     ecx, 1
0x180016045  jz      loc_18001621F
0x18001604b  sub     ecx, 1
0x18001604e  jz      loc_1800161E0
0x180016054  sub     ecx, 1
0x180016057  jz      loc_18001612B
0x18001605d  cmp     ecx, 2
0x180016060  jnz     loc_180016311
0x180016066  mov     r15d, [rbp+7C0h+InterfaceIndex]
0x18001606d  lea     r13d, [rcx-1]
0x180016071  mov     [rbx+0ACh], r13d
0x180016078  lea     rdx, [rbx+0A0h]; InterfaceLuid
0x18001607f  mov     dword ptr [rbx+0A8h], 4
0x180016089  mov     ecx, r15d; InterfaceIndex
0x18001608c  mov     dword ptr [rbx+94h], 3
0x180016096  mov     [r12], r15d
0x18001609a  mov     [rbx+20Ch], r13d
0x1800160a1  mov     dword ptr [rbx+210h], 5DCh
0x1800160ab  call    cs:__imp_ConvertInterfaceIndexToLuid
0x1800160b1  test    eax, eax
0x1800160b3  jz      loc_180016311
0x1800160b9  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800160c0  jge     loc_180016311
0x1800160c6  xor     ecx, ecx
0x1800160c8  lea     rdx, aCreateicbRoute; "CreateIcb: ROUTER_IF_TYPE_DIALOUT: Unab"...
0x1800160cf  mov     word ptr [rbp+7C0h+var_840], cx
0x1800160d3  mov     r9d, eax
0x1800160d6  mov     word ptr [rsp+8C0h+var_870], cx
0x1800160db  mov     r8d, r15d
0x1800160de  lea     rcx, [rbp+7C0h+var_840]
0x1800160e2  call    FormatRRASErrorString
0x1800160e7  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800160ee  jge     loc_180016311
0x1800160f4  lea     rax, [rsp+8C0h+var_870]
0x1800160f9  test    rsi, rsi
0x1800160fc  mov     qword ptr [rsp+8C0h+var_898], rax
0x180016101  lea     r9, [rsp+8C0h+var_880]
0x180016106  mov     rax, [rbx+48h]
0x18001610a  lea     r8, [rbp+7C0h+var_840]
0x18001610e  cmovnz  r9, rsi
0x180016112  mov     [rsp+8C0h+InterfaceLuid], rax
0x180016117  lea     rdx, RasRtrmgrParamTraceInfo
0x18001611e  mov     rcx, r14
0x180016121  call    McTemplateU0zjzz_EventWriteTransfer
0x180016126  jmp     loc_180016311
0x18001612b  xorps   xmm0, xmm0
0x18001612e  lea     rdx, [rsp+8C0h+lpMem]
0x180016133  movups  xmmword ptr [rsp+8C0h+lpMem], xmm0
0x180016138  mov     ecx, [rbx+2C0h]
0x18001613e  call    GetLoopbackIdentifiersFromCompartmentId
0x180016143  test    eax, eax
0x180016145  jz      short loc_1800161A9
0x180016147  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x18001614e  jz      short loc_1800161A9
0x180016150  xor     ecx, ecx
0x180016152  lea     rdx, aGetloopbackide; "GetLoopbackIdentifiersFromCompartmentId"...
0x180016159  mov     word ptr [rbp+7C0h+var_840], cx
0x18001615d  mov     r8d, eax
0x180016160  mov     word ptr [rsp+8C0h+var_870], cx
0x180016165  lea     rcx, [rbp+7C0h+var_840]
0x180016169  call    FormatRRASErrorString
0x18001616e  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180016175  jz      short loc_1800161A9
0x180016177  lea     rax, [rsp+8C0h+var_870]
0x18001617c  test    rsi, rsi
0x18001617f  mov     qword ptr [rsp+8C0h+var_898], rax
0x180016184  lea     r9, [rsp+8C0h+var_880]
0x180016189  mov     rax, [rbx+48h]
0x18001618d  lea     r8, [rbp+7C0h+var_840]
0x180016191  cmovnz  r9, rsi
0x180016195  mov     [rsp+8C0h+InterfaceLuid], rax
0x18001619a  lea     rdx, RasRtrMgrParamTraceError
0x1800161a1  mov     rcx, r14
0x1800161a4  call    McTemplateU0zjzz_EventWriteTransfer
0x1800161a9  mov     dword ptr [rbx+0ACh], 1
0x1800161b3  mov     dword ptr [rbx+0A8h], 5
0x1800161bd  mov     dword ptr [rbx+94h], 0
0x1800161c7  mov     eax, dword ptr [rsp+8C0h+lpMem+8]
0x1800161cb  mov     [r12], eax
0x1800161cf  mov     rax, [rsp+8C0h+lpMem]
0x1800161d4  mov     [rbx+0A0h], rax
0x1800161db  jmp     loc_180016311
0x1800161e0  mov     r13d, 1
0x1800161e6  mov     edx, r15d
0x1800161e9  mov     [rbx+0ACh], r13d
0x1800161f0  mov     rcx, rbx; struct _ICB *
0x1800161f3  mov     dword ptr [rbx+0A8h], 2
0x1800161fd  mov     dword ptr [rbx+94h], 2
0x180016207  mov     [rbx+20Ch], r13d
0x18001620e  mov     dword ptr [rbx+210h], 5DCh
0x180016218  call    AddInterfaceToWanArp
0x18001621d  jmp     short loc_180016261
0x18001621f  mov     [rbx+0ACh], r13d
0x180016226  lea     rax, [rbx+0A0h]
0x18001622d  mov     dword ptr [rbx+0A8h], 0
0x180016237  mov     r9, r12
0x18001623a  mov     dword ptr [rbx+94h], 0
0x180016244  mov     rdx, rsi
0x180016247  mov     r8, [rbx+0B8h]
0x18001624e  mov     rcx, [rbx+48h]; lpWideCharStr
0x180016252  mov     [rsp+8C0h+var_898], r15d; int
0x180016257  mov     [rsp+8C0h+InterfaceLuid], rax; InterfaceLuid
0x18001625c  call    RtrGetIndexAndLuidForInterface
0x180016261  mov     r8d, eax
0x180016264  test    eax, eax
0x180016266  jz      loc_180016311
0x18001626c  jmp     short loc_1800162B7
0x18001626e  mov     [rbx+0ACh], r13d
0x180016275  mov     edx, r15d
0x180016278  mov     dword ptr [rbx+0A8h], 2
0x180016282  mov     r13d, 1
0x180016288  mov     [rbx+94h], r13d
0x18001628f  mov     rcx, rbx; struct _ICB *
0x180016292  mov     [rbx+20Ch], r13d
0x180016299  mov     dword ptr [rbx+210h], 5DCh
0x1800162a3  call    AddInterfaceToWanArp
0x1800162a8  mov     r8d, eax
0x1800162ab  test    eax, eax
0x1800162ad  jz      short loc_180016311
0x1800162af  lock add cs:g_dwNextICBSeqNumberCounter, r13d
0x1800162b7  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x1800162be  jz      loc_180016387
0x1800162c4  xor     eax, eax
0x1800162c6  lea     rdx, aCreateicbError; "CreateIcb: Error %d in getting index fo"...
0x1800162cd  mov     word ptr [rbp+7C0h+var_840], ax
0x1800162d1  mov     word ptr [rsp+8C0h+var_870], ax
0x1800162d6  jmp     short loc_18001633F
0x1800162d8  mov     r13d, 1
0x1800162de  mov     [rbx+0ACh], r13d
0x1800162e5  mov     dword ptr [rbx+0A8h], 3
0x1800162ef  mov     dword ptr [rbx+94h], 3
0x1800162f9  or      [rbx+0B4h], r13d
0x180016300  mov     [rbx+20Ch], r13d
0x180016307  mov     dword ptr [rbx+210h], 5DCh
0x180016311  mov     rcx, rbx
0x180016314  call    CreateBindingForNewIcb
0x180016319  test    eax, eax
0x18001631b  jz      loc_1800163A8
0x180016321  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180016328  jz      short loc_180016387
0x18001632a  xor     ecx, ecx
0x18001632c  lea     rdx, aCreateicbError_0; "CreateIcb: Error %d in creating binding"...
0x180016333  mov     word ptr [rbp+7C0h+var_840], cx
0x180016337  mov     r8d, eax
0x18001633a  mov     word ptr [rsp+8C0h+var_870], cx
0x18001633f  mov     r9, [rbx+48h]
0x180016343  lea     rcx, [rbp+7C0h+var_840]
0x180016347  call    FormatRRASErrorString
0x18001634c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180016353  jz      short loc_180016387
0x180016355  lea     rax, [rsp+8C0h+var_870]
0x18001635a  test    rsi, rsi
0x18001635d  mov     qword ptr [rsp+8C0h+var_898], rax
0x180016362  lea     r9, [rsp+8C0h+var_880]
0x180016367  mov     rax, [rbx+48h]
0x18001636b  lea     r8, [rbp+7C0h+var_840]
0x18001636f  cmovnz  r9, rsi
0x180016373  mov     [rsp+8C0h+InterfaceLuid], rax
0x180016378  lea     rdx, RasRtrMgrParamTraceError
0x18001637f  mov     rcx, r14
0x180016382  call    McTemplateU0zjzz_EventWriteTransfer
0x180016387  lea     rcx, [rbx+2D0h]; lpCriticalSection
0x18001638e  call    cs:__imp_DeleteCriticalSection
0x180016394  mov     rcx, cs:IPRouterHeap; hHeap
0x18001639b  mov     r8, rbx; lpMem
0x18001639e  xor     edx, edx; dwFlags
0x1800163a0  call    cs:__imp_HeapFree
0x1800163a6  xor     ebx, ebx
0x1800163a8  mov     rax, rbx
0x1800163ab  mov     rcx, [rbp+7C0h+var_40]
0x1800163b2  xor     rcx, rsp; StackCookie
0x1800163b5  call    __security_check_cookie
0x1800163ba  mov     rbx, [rsp+8C0h+arg_10]
0x1800163c2  add     rsp, 890h
0x1800163c9  pop     r15
0x1800163cb  pop     r14
0x1800163cd  pop     r13
0x1800163cf  pop     r12
0x1800163d1  pop     rdi
0x1800163d2  pop     rsi
0x1800163d3  pop     rbp
0x1800163d4  retn
```
