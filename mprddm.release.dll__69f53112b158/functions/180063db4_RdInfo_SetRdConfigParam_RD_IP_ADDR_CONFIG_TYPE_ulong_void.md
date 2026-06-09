# RdInfo::SetRdConfigParam(_RD_IP_ADDR_CONFIG_TYPE,ulong,void *)

- ea: `0x180063db4`
- end: `0x1800641dd`
- name: `?SetRdConfigParam@RdInfo@@QEAAKW4_RD_IP_ADDR_CONFIG_TYPE@@KPEAX@Z`
- size: `1065`
- prototype: `unsigned int __high(enum _RD_IP_ADDR_CONFIG_TYPE, unsigned int, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18005af78`

## callees

- `0x180063db4`
- `0x1800753f4`
- `0x1800754ac`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180063f74`
- `msvcrt!memcpy_s` at `0x1800640a4`
- `msvcrt!memcpy_s` at `0x180064157`
- `msvcrt!memcpy_s` at `0x180063f74`
- `msvcrt!memcpy_s` at `0x1800640a4`
- `msvcrt!memcpy_s` at `0x180064157`

## string_xrefs

- `0x180063e3f`: `RdInfo::SetRdConfigParam`
- `0x180063ec7`: `RdInfo::SetRdConfigParam`
- `0x180063f99`: `SetRdConfigParam: memcpy_s for SERVER_V6_NBO_IP_ADDRESS failed with error %d`
- `0x180064174`: `SetRdConfigParam: memcpy_s for SERVER_ADAPTER_NAME failed with error %d`
- `0x1800640c9`: `SetRdConfigParam: memcpy_s for SERVER_V6_IF_ID failed with error %d`
- `0x18006403b`: `SetRdConfigParam: Invalid configtype passed %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RdInfo::SetRdConfigParam(_DWORD *a1, int a2, unsigned int a3, _DWORD *a4)
{
  rsize_t v5; // rdi
  void (*v8)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  __int64 v9; // rcx
  __int64 v10; // r9
  __int64 v11; // rdx
  unsigned int v12; // eax
  const wchar_t *v13; // rdx
  __int64 v14; // r8
  unsigned int v15; // ebx
  __int64 v17; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v18; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v19; // [rsp+30h] [rbp-D0h]
  __int128 v20; // [rsp+40h] [rbp-C0h]
  __int64 v21; // [rsp+50h] [rbp-B0h]
  __int64 v22; // [rsp+58h] [rbp-A8h]
  int v23; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v24[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  v5 = a3;
  LODWORD(v17) = 0;
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v19 = 0;
  v18 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0xFFFFFFFFLL;
  v9 = *((_QWORD *)&xmmword_1800D0740 + 1);
  if ( *((_QWORD *)&xmmword_1800D0740 + 1) )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v18,
      L"RdInfo::SetRdConfigParam",
      (unsigned int *)&v17,
      v8);
    v9 = *((_QWORD *)&xmmword_1800D0740 + 1);
  }
  if ( !a4 )
  {
    LODWORD(v17) = 87;
    goto LABEL_73;
  }
  if ( a2 > 5 )
  {
    switch ( a2 )
    {
      case 6:
        if ( (unsigned int)v5 > 0x204 )
        {
          LODWORD(v17) = 87;
          if ( !v9 )
            goto LABEL_73;
          v10 = 517;
          goto LABEL_15;
        }
        v12 = memcpy_s(a1 + 24, 0x204u, a4, v5);
        LODWORD(v17) = v12;
        if ( !v12 || !(_QWORD)xmmword_1800D0740 )
          goto LABEL_73;
        v13 = L"SetRdConfigParam: memcpy_s for SERVER_ADAPTER_NAME failed with error %d";
        break;
      case 7:
        if ( (_DWORD)v5 == 4 )
        {
          a1[153] = *a4;
          goto LABEL_73;
        }
        LODWORD(v17) = 87;
        if ( v9 )
        {
          v10 = 529;
          goto LABEL_15;
        }
        goto LABEL_73;
      case 8:
        if ( (_DWORD)v5 == 4 )
        {
          a1[154] = *a4;
          goto LABEL_73;
        }
        LODWORD(v17) = 87;
        if ( v9 )
        {
          v10 = 535;
          goto LABEL_15;
        }
        goto LABEL_73;
      case 9:
        if ( (_DWORD)v5 != 8 )
        {
          LODWORD(v17) = 87;
          if ( !v9 )
            goto LABEL_73;
          v10 = 541;
          goto LABEL_15;
        }
        v12 = memcpy_s(a1 + 18, 8u, a4, 8u);
        LODWORD(v17) = v12;
        if ( !v12 || !(_QWORD)xmmword_1800D0740 )
          goto LABEL_73;
        v13 = L"SetRdConfigParam: memcpy_s for SERVER_V6_IF_ID failed with error %d";
        break;
      case 10:
        if ( (_DWORD)v5 == 4 )
        {
          a1[156] = *a4;
          goto LABEL_73;
        }
        LODWORD(v17) = 87;
        if ( v9 )
        {
          v10 = 553;
          goto LABEL_15;
        }
        goto LABEL_73;
      default:
LABEL_44:
        LODWORD(v17) = 87;
        if ( !(_QWORD)xmmword_1800D0740 )
          goto LABEL_73;
        v14 = (unsigned int)a2;
        v13 = L"SetRdConfigParam: Invalid configtype passed %d";
        goto LABEL_71;
    }
LABEL_70:
    v14 = v12;
LABEL_71:
    LOWORD(v23) = 0;
    FormatRRASErrorString(&v23, v13, v14);
    v11 = xmmword_1800D0740;
    goto LABEL_72;
  }
  switch ( a2 )
  {
    case 5:
      if ( (_DWORD)v5 == 4 )
      {
        a1[23] = *a4;
        goto LABEL_73;
      }
      LODWORD(v17) = 87;
      if ( v9 )
      {
        v10 = 511;
        goto LABEL_15;
      }
      goto LABEL_73;
    case 0:
      if ( (_DWORD)v5 == 4 )
      {
        a1[4] = *a4;
        goto LABEL_73;
      }
      LODWORD(v17) = 87;
      if ( v9 )
      {
        v10 = 475;
        goto LABEL_15;
      }
      goto LABEL_73;
    case 1:
      if ( (_DWORD)v5 != 52 )
      {
        LODWORD(v17) = 87;
        if ( !v9 )
          goto LABEL_73;
        v10 = 481;
        goto LABEL_15;
      }
      v12 = memcpy_s(a1 + 5, 0x34u, a4, 0x34u);
      LODWORD(v17) = v12;
      if ( !v12 || !(_QWORD)xmmword_1800D0740 )
        goto LABEL_73;
      v13 = L"SetRdConfigParam: memcpy_s for SERVER_V6_NBO_IP_ADDRESS failed with error %d";
      goto LABEL_70;
    case 2:
      if ( (_DWORD)v5 == 4 )
      {
        a1[20] = *a4;
        goto LABEL_73;
      }
      LODWORD(v17) = 87;
      if ( v9 )
      {
        v10 = 493;
        goto LABEL_15;
      }
      goto LABEL_73;
  }
  if ( a2 != 3 )
  {
    if ( a2 == 4 )
    {
      if ( (_DWORD)v5 == 4 )
      {
        a1[22] = *a4;
        goto LABEL_73;
      }
      LODWORD(v17) = 87;
      if ( v9 )
      {
        v10 = 505;
LABEL_15:
        LOWORD(v23) = 0;
        FormatRRASErrorString(
          &v23,
          L"%s(Line#%d): Invalid parameter.",
          "RdInfo::SetRdConfigParam",
          v10,
          v17,
          v18,
          v19,
          v20,
          v21,
          v22);
        v11 = *((_QWORD *)&xmmword_1800D0740 + 1);
LABEL_72:
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, __int64, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          v11,
          &v23);
        goto LABEL_73;
      }
      goto LABEL_73;
    }
    goto LABEL_44;
  }
  if ( (_DWORD)v5 == 4 )
  {
    a1[21] = *a4;
    goto LABEL_73;
  }
  LODWORD(v17) = 87;
  if ( v9 )
  {
    v10 = 499;
    goto LABEL_15;
  }
LABEL_73:
  v15 = v17;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v18);
  return v15;
}

```

## disassembly

```asm
0x180063db4  push    rbp
0x180063db6  push    rbx
0x180063db7  push    rsi
0x180063db8  push    rdi
0x180063db9  push    r14
0x180063dbb  push    r15
0x180063dbd  lea     rbp, [rsp-778h]
0x180063dc5  sub     rsp, 878h
0x180063dcc  mov     rax, cs:__security_cookie
0x180063dd3  xor     rax, rsp
0x180063dd6  mov     [rbp+7A0h+var_40], rax
0x180063ddd  mov     rbx, r9
0x180063de0  mov     edi, r8d
0x180063de3  mov     r14d, edx
0x180063de6  mov     rsi, rcx
0x180063de9  xor     r15d, r15d
0x180063dec  mov     dword ptr [rsp+8A0h+var_880], r15d
0x180063df1  mov     [rsp+8A0h+var_840], r15d
0x180063df6  xor     edx, edx; Val
0x180063df8  mov     r8d, 7FCh; Size
0x180063dfe  lea     rcx, [rsp+8A0h+var_83C]; void *
0x180063e03  call    memset_0
0x180063e08  xorps   xmm0, xmm0
0x180063e0b  movdqu  [rsp+8A0h+var_870], xmm0
0x180063e11  mov     [rsp+8A0h+var_878], r15
0x180063e16  xorps   xmm1, xmm1
0x180063e19  movdqu  [rsp+8A0h+var_860], xmm1
0x180063e1f  mov     [rsp+8A0h+var_850], r15
0x180063e24  or      [rsp+8A0h+var_848], 0FFFFFFFFh
0x180063e29  mov     [rsp+8A0h+var_844], r15d
0x180063e2e  mov     rcx, qword ptr cs:xmmword_1800D0740+8
0x180063e35  test    rcx, rcx
0x180063e38  jz      short loc_180063E57
0x180063e3a  lea     r8, [rsp+8A0h+var_880]; unsigned int *
0x180063e3f  lea     rdx, aRdinfoSetrdcon; "RdInfo::SetRdConfigParam"
0x180063e46  lea     rcx, [rsp+8A0h+var_878]; this
0x180063e4b  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180063e50  mov     rcx, qword ptr cs:xmmword_1800D0740+8
0x180063e57  test    rbx, rbx
0x180063e5a  jnz     short loc_180063E69
0x180063e5c  mov     dword ptr [rsp+8A0h+var_880], 57h ; 'W'
0x180063e64  jmp     loc_1800641AD
0x180063e69  cmp     r14d, 5
0x180063e6d  jg      loc_180063FFB
0x180063e73  jz      loc_180063FD0
0x180063e79  mov     edx, r14d
0x180063e7c  test    r14d, r14d
0x180063e7f  jz      loc_180063FA5
0x180063e85  sub     edx, 1
0x180063e88  jz      loc_180063F45
0x180063e8e  sub     edx, 1
0x180063e91  jz      loc_180063F1D
0x180063e97  sub     edx, 1
0x180063e9a  jz      short loc_180063EF5
0x180063e9c  cmp     edx, 1
0x180063e9f  jnz     loc_180064023
0x180063ea5  cmp     edi, 4
0x180063ea8  jz      short loc_180063EEB
0x180063eaa  mov     dword ptr [rsp+8A0h+var_880], 57h ; 'W'
0x180063eb2  test    rcx, rcx
0x180063eb5  jz      loc_1800641AD
0x180063ebb  mov     r9d, 1F9h
0x180063ec1  mov     word ptr [rsp+8A0h+var_840], r15w
0x180063ec7  lea     r8, aRdinfoSetrdcon_0; "RdInfo::SetRdConfigParam"
0x180063ece  lea     rdx, aSLineDInvalidP; "%s(Line#%d): Invalid parameter."
0x180063ed5  lea     rcx, [rsp+8A0h+var_840]
0x180063eda  call    FormatRRASErrorString
0x180063edf  mov     rdx, qword ptr cs:xmmword_1800D0740+8
0x180063ee6  jmp     loc_180064195
0x180063eeb  mov     eax, [rbx]
0x180063eed  mov     [rsi+58h], eax
0x180063ef0  jmp     loc_1800641AD
0x180063ef5  cmp     edi, 4
0x180063ef8  jz      short loc_180063F13
0x180063efa  mov     dword ptr [rsp+8A0h+var_880], 57h ; 'W'
0x180063f02  test    rcx, rcx
0x180063f05  jz      loc_1800641AD
0x180063f0b  mov     r9d, 1F3h
0x180063f11  jmp     short loc_180063EC1
0x180063f13  mov     eax, [rbx]
0x180063f15  mov     [rsi+54h], eax
0x180063f18  jmp     loc_1800641AD
0x180063f1d  cmp     edi, 4
0x180063f20  jz      short loc_180063F3B
0x180063f22  mov     dword ptr [rsp+8A0h+var_880], 57h ; 'W'
0x180063f2a  test    rcx, rcx
0x180063f2d  jz      loc_1800641AD
0x180063f33  mov     r9d, 1EDh
0x180063f39  jmp     short loc_180063EC1
0x180063f3b  mov     eax, [rbx]
0x180063f3d  mov     [rsi+50h], eax
0x180063f40  jmp     loc_1800641AD
0x180063f45  mov     edx, 34h ; '4'; DestinationSize
0x180063f4a  cmp     edi, edx
0x180063f4c  jz      short loc_180063F6A
0x180063f4e  mov     dword ptr [rsp+8A0h+var_880], 57h ; 'W'
0x180063f56  test    rcx, rcx
0x180063f59  jz      loc_1800641AD
0x180063f5f  mov     r9d, 1E1h
0x180063f65  jmp     loc_180063EC1
0x180063f6a  lea     rcx, [rsi+14h]; Destination
0x180063f6e  mov     r9, rdx; SourceSize
0x180063f71  mov     r8, rbx; Source
0x180063f74  call    cs:__imp_memcpy_s
0x180063f7b  nop     dword ptr [rax+rax+00h]
0x180063f80  mov     dword ptr [rsp+8A0h+var_880], eax
0x180063f84  test    eax, eax
0x180063f86  jz      loc_1800641AD
0x180063f8c  cmp     qword ptr cs:xmmword_1800D0740, r15
0x180063f93  jz      loc_1800641AD
0x180063f99  lea     rdx, aSetrdconfigpar; "SetRdConfigParam: memcpy_s for SERVER_V"...
0x180063fa0  jmp     loc_18006417B
0x180063fa5  cmp     edi, 4
0x180063fa8  jz      short loc_180063FC6
0x180063faa  mov     dword ptr [rsp+8A0h+var_880], 57h ; 'W'
0x180063fb2  test    rcx, rcx
0x180063fb5  jz      loc_1800641AD
0x180063fbb  mov     r9d, 1DBh
0x180063fc1  jmp     loc_180063EC1
0x180063fc6  mov     eax, [rbx]
0x180063fc8  mov     [rsi+10h], eax
0x180063fcb  jmp     loc_1800641AD
0x180063fd0  cmp     edi, 4
0x180063fd3  jz      short loc_180063FF1
0x180063fd5  mov     dword ptr [rsp+8A0h+var_880], 57h ; 'W'
0x180063fdd  test    rcx, rcx
0x180063fe0  jz      loc_1800641AD
0x180063fe6  mov     r9d, 1FFh
0x180063fec  jmp     loc_180063EC1
0x180063ff1  mov     eax, [rbx]
0x180063ff3  mov     [rsi+5Ch], eax
0x180063ff6  jmp     loc_1800641AD
0x180063ffb  mov     edx, r14d
0x180063ffe  sub     edx, 6
0x180064001  jz      loc_18006412E
0x180064007  sub     edx, 1
0x18006400a  jz      loc_180064103
0x180064010  sub     edx, 1
0x180064013  jz      loc_1800640D5
0x180064019  sub     edx, 1
0x18006401c  jz      short loc_180064075
0x18006401e  cmp     edx, 1
0x180064021  jz      short loc_180064047
0x180064023  mov     dword ptr [rsp+8A0h+var_880], 57h ; 'W'
0x18006402b  cmp     qword ptr cs:xmmword_1800D0740, r15
0x180064032  jz      loc_1800641AD
0x180064038  mov     r8d, r14d
0x18006403b  lea     rdx, aSetrdconfigpar_0; "SetRdConfigParam: Invalid configtype pa"...
0x180064042  jmp     loc_18006417E
0x180064047  cmp     edi, 4
0x18006404a  jz      short loc_180064068
0x18006404c  mov     dword ptr [rsp+8A0h+var_880], 57h ; 'W'
0x180064054  test    rcx, rcx
0x180064057  jz      loc_1800641AD
0x18006405d  mov     r9d, 229h
0x180064063  jmp     loc_180063EC1
0x180064068  mov     eax, [rbx]
0x18006406a  mov     [rsi+270h], eax
0x180064070  jmp     loc_1800641AD
0x180064075  mov     edx, 8; DestinationSize
0x18006407a  cmp     edi, edx
0x18006407c  jz      short loc_18006409A
0x18006407e  mov     dword ptr [rsp+8A0h+var_880], 57h ; 'W'
0x180064086  test    rcx, rcx
0x180064089  jz      loc_1800641AD
0x18006408f  mov     r9d, 21Dh
0x180064095  jmp     loc_180063EC1
0x18006409a  lea     rcx, [rsi+48h]; Destination
0x18006409e  mov     r9, rdx; SourceSize
0x1800640a1  mov     r8, rbx; Source
0x1800640a4  call    cs:__imp_memcpy_s
0x1800640ab  nop     dword ptr [rax+rax+00h]
0x1800640b0  mov     dword ptr [rsp+8A0h+var_880], eax
0x1800640b4  test    eax, eax
0x1800640b6  jz      loc_1800641AD
0x1800640bc  cmp     qword ptr cs:xmmword_1800D0740, r15
0x1800640c3  jz      loc_1800641AD
0x1800640c9  lea     rdx, aSetrdconfigpar_1; "SetRdConfigParam: memcpy_s for SERVER_V"...
0x1800640d0  jmp     loc_18006417B
0x1800640d5  cmp     edi, 4
0x1800640d8  jz      short loc_1800640F6
0x1800640da  mov     dword ptr [rsp+8A0h+var_880], 57h ; 'W'
0x1800640e2  test    rcx, rcx
0x1800640e5  jz      loc_1800641AD
0x1800640eb  mov     r9d, 217h
0x1800640f1  jmp     loc_180063EC1
0x1800640f6  mov     eax, [rbx]
0x1800640f8  mov     [rsi+268h], eax
0x1800640fe  jmp     loc_1800641AD
0x180064103  cmp     edi, 4
0x180064106  jz      short loc_180064124
0x180064108  mov     dword ptr [rsp+8A0h+var_880], 57h ; 'W'
0x180064110  test    rcx, rcx
0x180064113  jz      loc_1800641AD
0x180064119  mov     r9d, 211h
0x18006411f  jmp     loc_180063EC1
0x180064124  mov     eax, [rbx]
0x180064126  mov     [rsi+264h], eax
0x18006412c  jmp     short loc_1800641AD
0x18006412e  mov     edx, 204h; DestinationSize
0x180064133  cmp     edi, edx
0x180064135  jbe     short loc_18006414D
0x180064137  mov     dword ptr [rsp+8A0h+var_880], 57h ; 'W'
0x18006413f  test    rcx, rcx
0x180064142  jz      short loc_1800641AD
0x180064144  lea     r9d, [rdx+1]
0x180064148  jmp     loc_180063EC1
0x18006414d  mov     r9, rdi; SourceSize
0x180064150  lea     rcx, [rsi+60h]; Destination
0x180064154  mov     r8, rbx; Source
0x180064157  call    cs:__imp_memcpy_s
0x18006415e  nop     dword ptr [rax+rax+00h]
0x180064163  mov     dword ptr [rsp+8A0h+var_880], eax
0x180064167  test    eax, eax
0x180064169  jz      short loc_1800641AD
0x18006416b  cmp     qword ptr cs:xmmword_1800D0740, r15
0x180064172  jz      short loc_1800641AD
0x180064174  lea     rdx, aSetrdconfigpar_3; "SetRdConfigParam: memcpy_s for SERVER_A"...
0x18006417b  mov     r8d, eax
0x18006417e  mov     word ptr [rsp+8A0h+var_840], r15w
0x180064184  lea     rcx, [rsp+8A0h+var_840]
0x180064189  call    FormatRRASErrorString
0x18006418e  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180064195  lea     r8, [rsp+8A0h+var_840]
0x18006419a  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800641a1  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800641a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800641ad  mov     ebx, dword ptr [rsp+8A0h+var_880]
0x1800641b1  lea     rcx, [rsp+8A0h+var_878]; this
0x1800641b6  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x1800641bb  mov     eax, ebx
0x1800641bd  mov     rcx, [rbp+7A0h+var_40]
0x1800641c4  xor     rcx, rsp; StackCookie
0x1800641c7  call    __security_check_cookie
0x1800641cc  add     rsp, 878h
0x1800641d3  pop     r15
0x1800641d5  pop     r14
0x1800641d7  pop     rdi
0x1800641d8  pop     rsi
0x1800641d9  pop     rbx
0x1800641da  pop     rbp
0x1800641db  retn
```
