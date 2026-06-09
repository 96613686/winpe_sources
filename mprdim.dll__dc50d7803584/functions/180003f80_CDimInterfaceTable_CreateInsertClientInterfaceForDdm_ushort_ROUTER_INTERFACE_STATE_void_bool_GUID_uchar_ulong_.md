# CDimInterfaceTable::CreateInsertClientInterfaceForDdm(ushort *,ROUTER_INTERFACE_STATE,void *,bool,_GUID,uchar *,ulong *,IDimInterface * *)

- ea: `0x180003f80`
- end: `0x1800042a2`
- name: `?CreateInsertClientInterfaceForDdm@CDimInterfaceTable@@UEAAKPEAGW4ROUTER_INTERFACE_STATE@@PEAX_NU_GUID@@PEAEPEAKPEAPEAUIDimInterface@@@Z`
- size: `802`
- prototype: `__int64 __fastcall(CDimInterfaceTable *, __int64, int, __int64, char, struct _GUID *, unsigned __int8 *, unsigned int *, CDimInterface **)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003f80`
- `0x180005358`
- `0x180005670`
- `0x1800056c4`
- `0x180005d14`
- `0x1800067e0`
- `0x1800076ac`
- `0x180007bf0`
- `0x18000def0`
- `0x18001b024`
- `0x180035d10`
- `0x180045d40`
- `0x180045d7c`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000408c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000408c`

## string_xrefs

- `0x1800040aa`: `CDimInterfaceTable::CreateInsertClientInterfaceForDdm  CreateInterface returned %d`
- `0x18000414b`: `CDimInterfaceTable::CreateInsertClientInterfaceForDdm  GetRoutingDomainConfiguration returned %d`
- `0x1800041bd`: `CDimInterfaceTable::CreateInsertClientInterfaceForDdm  pDimInteface->AddAllTransportsForDdm returned %d`
- `0x18000422c`: `CDimInterfaceTable::CreateInsertClientInterfaceForDdm returned %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDimInterfaceTable::CreateInsertClientInterfaceForDdm(
        CDimInterfaceTable *a1,
        __int64 a2,
        int a3,
        __int64 a4,
        char a5,
        struct _GUID *a6,
        unsigned __int8 *a7,
        unsigned int *a8,
        CDimInterface **a9)
{
  __int64 Interface; // rax
  DWORD LastError; // eax
  unsigned int v15; // ebx
  unsigned int RoutingDomainConfiguration; // eax
  void *v17; // rax
  CDimInterface *v19; // [rsp+60h] [rbp-A0h] BYREF
  std::tr1::_Ref_count_base *v20; // [rsp+68h] [rbp-98h]
  int v21; // [rsp+70h] [rbp-90h]
  int v22; // [rsp+74h] [rbp-8Ch]
  unsigned int *v23; // [rsp+78h] [rbp-88h]
  unsigned __int8 *v24; // [rsp+80h] [rbp-80h]
  char v25; // [rsp+88h] [rbp-78h] BYREF
  std::tr1::_Ref_count_base *v26; // [rsp+90h] [rbp-70h]
  GUID ActivityId; // [rsp+98h] [rbp-68h] BYREF
  int v28; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v29[2044]; // [rsp+B4h] [rbp-4Ch] BYREF

  v24 = a7;
  v23 = a8;
  ActivityId = 0;
  v28 = 0;
  memset_0(v29, 0, sizeof(v29));
  v22 = SetRasServerActivityId(&ActivityId);
  CDimInterfaceTable::GetInterfaceByName(a1, &v19, a2, 0);
  if ( v19 )
  {
    v15 = 0;
    *a9 = v19;
  }
  else
  {
    Interface = CDimInterfaceTable::CreateInterface((_DWORD)a1, (unsigned int)&v25, a2, a3, 0, a4, a5, 0, 0, 0, 0);
    std::tr1::shared_ptr<CDimInterface>::operator=(&v19, Interface);
    if ( v26 )
      std::tr1::_Ref_count_base::_Decref(v26);
    if ( v19 )
    {
      if ( *((_BYTE *)a1 + 116)
        && (v21 = 28,
            *((struct _GUID *)v19 + 194) = *a6,
            *((struct _GUID *)v19 + 59) = *a6,
            (RoutingDomainConfiguration = GetRoutingDomainConfiguration(a6, (__int64)v19 + 960)) != 0) )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
        {
          LOWORD(v28) = 0;
          FormatRRASErrorString(
            &v28,
            L"CDimInterfaceTable::CreateInsertClientInterfaceForDdm  GetRoutingDomainConfiguration returned %d",
            RoutingDomainConfiguration);
          if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceError, &v28);
        }
        v15 = 807;
      }
      else
      {
        CDimInterfaceTable::InsertInterface(a1, &v19);
        v15 = CDimInterface::AddAllTransportsForDdm(v19, v24, v23);
        if ( v15 )
        {
          if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
          {
            LOWORD(v28) = 0;
            FormatRRASErrorString(
              &v28,
              L"CDimInterfaceTable::CreateInsertClientInterfaceForDdm  pDimInteface->AddAllTransportsForDdm returned %d",
              v15);
            if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceError, &v28);
          }
          v17 = (void *)(*(__int64 (__fastcall **)(CDimInterface *))(*(_QWORD *)v19 + 16LL))(v19);
          CDimInterfaceTable::RemoveInterface(a1, v17);
        }
        else
        {
          *a9 = v19;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v15 = LastError;
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      {
        LOWORD(v28) = 0;
        FormatRRASErrorString(
          &v28,
          L"CDimInterfaceTable::CreateInsertClientInterfaceForDdm  CreateInterface returned %d",
          LastError);
        if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceError, &v28);
      }
    }
  }
  if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
  {
    LOWORD(v28) = 0;
    FormatRRASErrorString(&v28, L"CDimInterfaceTable::CreateInsertClientInterfaceForDdm returned %d", v15);
    if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceInfo, &v28);
  }
  if ( v22 )
    ReSetActivityId(&ActivityId);
  if ( v20 )
    std::tr1::_Ref_count_base::_Decref(v20);
  return v15;
}

```

## disassembly

```asm
0x180003f80  push    rbp
0x180003f82  push    rbx
0x180003f83  push    rsi
0x180003f84  push    rdi
0x180003f85  push    r12
0x180003f87  push    r13
0x180003f89  push    r14
0x180003f8b  push    r15
0x180003f8d  lea     rbp, [rsp-7C8h]
0x180003f95  sub     rsp, 8C8h
0x180003f9c  mov     rax, cs:__security_cookie
0x180003fa3  xor     rax, rsp
0x180003fa6  mov     [rbp+800h+var_50], rax
0x180003fad  mov     r12, r9
0x180003fb0  mov     r15d, r8d
0x180003fb3  mov     r14, rdx
0x180003fb6  mov     rdi, rcx
0x180003fb9  mov     r13b, [rbp+800h+arg_20]
0x180003fc0  mov     rbx, [rbp+800h+arg_28]
0x180003fc7  mov     rax, [rbp+800h+arg_30]
0x180003fce  mov     [rbp+800h+var_880], rax
0x180003fd2  mov     rax, [rbp+800h+arg_38]
0x180003fd9  mov     [rsp+900h+var_888], rax
0x180003fde  mov     rsi, [rbp+800h+arg_40]
0x180003fe5  xorps   xmm0, xmm0
0x180003fe8  movups  xmmword ptr [rbp+800h+ActivityId.Data1], xmm0
0x180003fec  xor     eax, eax
0x180003fee  mov     [rbp+800h+var_850], eax
0x180003ff1  xor     edx, edx; Val
0x180003ff3  mov     r8d, 7FCh; Size
0x180003ff9  lea     rcx, [rbp+800h+var_84C]; void *
0x180003ffd  call    memset_0
0x180004002  lea     rcx, [rbp+800h+ActivityId]; ActivityId
0x180004006  call    SetRasServerActivityId
0x18000400b  mov     [rsp+900h+var_88C], eax
0x18000400f  xor     r9d, r9d
0x180004012  mov     r8, r14
0x180004015  lea     rdx, [rsp+900h+var_8A0]
0x18000401a  mov     rcx, rdi
0x18000401d  call    ?GetInterfaceByName@CDimInterfaceTable@@QEAA?AV?$shared_ptr@VCDimInterface@@@tr1@std@@PEAG_N@Z; CDimInterfaceTable::GetInterfaceByName(ushort *,bool)
0x180004022  nop
0x180004023  mov     rcx, [rsp+900h+var_8A0]
0x180004028  xor     eax, eax
0x18000402a  test    rcx, rcx
0x18000402d  jnz     loc_180004215
0x180004033  mov     [rsp+900h+var_8B0], rax
0x180004038  mov     [rsp+900h+var_8B8], rax
0x18000403d  mov     [rsp+900h+var_8C0], eax
0x180004041  mov     [rsp+900h+var_8C8], eax
0x180004045  mov     [rsp+900h+var_8D0], r13b
0x18000404a  mov     [rsp+900h+var_8D8], r12
0x18000404f  mov     dword ptr [rsp+900h+var_8E0], eax
0x180004053  mov     r9d, r15d
0x180004056  mov     r8, r14
0x180004059  lea     rdx, [rbp+800h+var_878]
0x18000405d  mov     rcx, rdi
0x180004060  call    ?CreateInterface@CDimInterfaceTable@@QEAA?AV?$shared_ptr@VCDimInterface@@@tr1@std@@PEAGW4ROUTER_INTERFACE_STATE@@W4_ROUTER_INTERFACE_TYPE@@PEAX_NKK0PEAU_DIM_INTERFACE_OBJECT_EXTRA_INFO@@@Z; CDimInterfaceTable::CreateInterface(ushort *,ROUTER_INTERFACE_STATE,_ROUTER_INTERFACE_TYPE,void *,bool,ulong,ulong,ushort *,_DIM_INTERFACE_OBJECT_EXTRA_INFO *)
0x180004065  mov     rdx, rax
0x180004068  lea     rcx, [rsp+900h+var_8A0]
0x18000406d  call    ??4?$shared_ptr@VCDimInterface@@@tr1@std@@QEAAAEAV012@$$QEAV012@@Z; std::tr1::shared_ptr<CDimInterface>::operator=(std::tr1::shared_ptr<CDimInterface> &&)
0x180004072  nop
0x180004073  mov     rcx, [rbp+800h+var_870]; this
0x180004077  test    rcx, rcx
0x18000407a  jz      short loc_180004082
0x18000407c  call    ?_Decref@_Ref_count_base@tr1@std@@QEAAXXZ; std::tr1::_Ref_count_base::_Decref(void)
0x180004081  nop
0x180004082  mov     rax, [rsp+900h+var_8A0]
0x180004087  test    rax, rax
0x18000408a  jnz     short loc_1800040E3
0x18000408c  call    cs:__imp_GetLastError
0x180004092  mov     ebx, eax
0x180004094  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18000409b  jz      loc_18000421A
0x1800040a1  xor     ecx, ecx
0x1800040a3  mov     word ptr [rbp+800h+var_850], cx
0x1800040a7  mov     r8d, eax
0x1800040aa  lea     rdx, aCdiminterfacet_46; "CDimInterfaceTable::CreateInsertClientI"...
0x1800040b1  lea     rcx, [rbp+800h+var_850]
0x1800040b5  call    FormatRRASErrorString
0x1800040ba  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x1800040c1  jz      loc_18000421A
0x1800040c7  lea     r8, [rbp+800h+var_850]
0x1800040cb  lea     rdx, RasDimTraceError
0x1800040d2  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800040d9  call    McTemplateU0z_EventWriteTransfer
0x1800040de  jmp     loc_18000421A
0x1800040e3  cmp     byte ptr [rdi+74h], 0
0x1800040e7  jz      loc_180004185
0x1800040ed  mov     [rsp+900h+var_890], 1Ch
0x1800040f5  movups  xmm0, xmmword ptr [rbx]
0x1800040f8  movdqu  xmmword ptr [rax+0C20h], xmm0
0x180004100  movups  xmm1, xmmword ptr [rbx]
0x180004103  mov     rax, [rsp+900h+var_8A0]
0x180004108  movdqu  xmmword ptr [rax+3B0h], xmm1
0x180004110  mov     rax, [rsp+900h+var_8A0]
0x180004115  add     rax, 3C0h
0x18000411b  mov     [rsp+900h+var_8E0], rax; __int64
0x180004120  lea     r9, [rsp+900h+var_890]
0x180004125  xor     r8d, r8d
0x180004128  mov     edx, 2000h
0x18000412d  mov     rcx, rbx; struct _GUID *
0x180004130  call    GetRoutingDomainConfiguration
0x180004135  test    eax, eax
0x180004137  jz      short loc_180004185
0x180004139  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180004140  jz      short loc_18000417B
0x180004142  xor     ecx, ecx
0x180004144  mov     word ptr [rbp+800h+var_850], cx
0x180004148  mov     r8d, eax
0x18000414b  lea     rdx, aCdiminterfacet_31; "CDimInterfaceTable::CreateInsertClientI"...
0x180004152  lea     rcx, [rbp+800h+var_850]
0x180004156  call    FormatRRASErrorString
0x18000415b  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180004162  jz      short loc_18000417B
0x180004164  lea     r8, [rbp+800h+var_850]
0x180004168  lea     rdx, RasDimTraceError
0x18000416f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004176  call    McTemplateU0z_EventWriteTransfer
0x18000417b  mov     ebx, 327h
0x180004180  jmp     loc_18000421A
0x180004185  lea     rdx, [rsp+900h+var_8A0]
0x18000418a  mov     rcx, rdi
0x18000418d  call    ?InsertInterface@CDimInterfaceTable@@QEAAXAEBV?$shared_ptr@VCDimInterface@@@tr1@std@@@Z; CDimInterfaceTable::InsertInterface(std::tr1::shared_ptr<CDimInterface> const &)
0x180004192  mov     r8, [rsp+900h+var_888]; unsigned int *
0x180004197  mov     rdx, [rbp+800h+var_880]; unsigned __int8 *
0x18000419b  mov     rcx, [rsp+900h+var_8A0]; this
0x1800041a0  call    ?AddAllTransportsForDdm@CDimInterface@@QEAAKPEAEPEAK@Z; CDimInterface::AddAllTransportsForDdm(uchar *,ulong *)
0x1800041a5  mov     ebx, eax
0x1800041a7  test    eax, eax
0x1800041a9  jz      short loc_18000420B
0x1800041ab  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x1800041b2  jz      short loc_1800041ED
0x1800041b4  xor     eax, eax
0x1800041b6  mov     word ptr [rbp+800h+var_850], ax
0x1800041ba  mov     r8d, ebx
0x1800041bd  lea     rdx, aCdiminterfacet_41; "CDimInterfaceTable::CreateInsertClientI"...
0x1800041c4  lea     rcx, [rbp+800h+var_850]
0x1800041c8  call    FormatRRASErrorString
0x1800041cd  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x1800041d4  jz      short loc_1800041ED
0x1800041d6  lea     r8, [rbp+800h+var_850]
0x1800041da  lea     rdx, RasDimTraceError
0x1800041e1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800041e8  call    McTemplateU0z_EventWriteTransfer
0x1800041ed  mov     rcx, [rsp+900h+var_8A0]
0x1800041f2  mov     rax, [rcx]
0x1800041f5  mov     rax, [rax+10h]
0x1800041f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041fe  mov     rdx, rax; void *
0x180004201  mov     rcx, rdi; this
0x180004204  call    ?RemoveInterface@CDimInterfaceTable@@EEAAXQEAX@Z; CDimInterfaceTable::RemoveInterface(void * const)
0x180004209  jmp     short loc_18000421A
0x18000420b  mov     rax, [rsp+900h+var_8A0]
0x180004210  mov     [rsi], rax
0x180004213  jmp     short loc_18000421A
0x180004215  xor     ebx, ebx
0x180004217  mov     [rsi], rcx
0x18000421a  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x180004221  jz      short loc_18000425C
0x180004223  xor     eax, eax
0x180004225  mov     word ptr [rbp+800h+var_850], ax
0x180004229  mov     r8d, ebx
0x18000422c  lea     rdx, aCdiminterfacet_37; "CDimInterfaceTable::CreateInsertClientI"...
0x180004233  lea     rcx, [rbp+800h+var_850]
0x180004237  call    FormatRRASErrorString
0x18000423c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x180004243  jz      short loc_18000425C
0x180004245  lea     r8, [rbp+800h+var_850]
0x180004249  lea     rdx, RasDimTraceInfo
0x180004250  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004257  call    McTemplateU0z_EventWriteTransfer
0x18000425c  cmp     [rsp+900h+var_88C], 0
0x180004261  jz      short loc_18000426D
0x180004263  lea     rcx, [rbp+800h+ActivityId]; ActivityId
0x180004267  call    ReSetActivityId
0x18000426c  nop
0x18000426d  mov     rcx, [rsp+900h+var_898]; this
0x180004272  test    rcx, rcx
0x180004275  jz      short loc_18000427D
0x180004277  call    ?_Decref@_Ref_count_base@tr1@std@@QEAAXXZ; std::tr1::_Ref_count_base::_Decref(void)
0x18000427c  nop
0x18000427d  mov     eax, ebx
0x18000427f  mov     rcx, [rbp+800h+var_50]
0x180004286  xor     rcx, rsp; StackCookie
0x180004289  call    __security_check_cookie
0x18000428e  add     rsp, 8C8h
0x180004295  pop     r15
0x180004297  pop     r14
0x180004299  pop     r13
0x18000429b  pop     r12
0x18000429d  pop     rdi
0x18000429e  pop     rsi
0x18000429f  pop     rbx
0x1800042a0  pop     rbp
0x1800042a1  retn
```
