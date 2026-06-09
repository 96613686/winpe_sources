# RdInfo::SetRdConfigParam(_RD_IP_ADDR_CONFIG_TYPE,ulong,void *)

- ea: `0x180061734`
- end: `0x180061b60`
- name: `?SetRdConfigParam@RdInfo@@QEAAKW4_RD_IP_ADDR_CONFIG_TYPE@@KPEAX@Z`
- size: `1068`
- prototype: `unsigned int __high(enum _RD_IP_ADDR_CONFIG_TYPE, unsigned int, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180059030`

## callees

- `0x180061734`
- `0x180071b1c`
- `0x180071bd8`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180061902`
- `msvcrt!memcpy_s` at `0x180061a31`
- `msvcrt!memcpy_s` at `0x180061ae1`
- `msvcrt!memcpy_s` at `0x180061902`
- `msvcrt!memcpy_s` at `0x180061a31`
- `msvcrt!memcpy_s` at `0x180061ae1`

## string_xrefs

- `0x1800617cc`: `RdInfo::SetRdConfigParam`
- `0x180061855`: `RdInfo::SetRdConfigParam`
- `0x180061925`: `SetRdConfigParam: memcpy_s for SERVER_V6_NBO_IP_ADDRESS failed with error %d`
- `0x180061afc`: `SetRdConfigParam: memcpy_s for SERVER_ADAPTER_NAME failed with error %d`
- `0x180061a54`: `SetRdConfigParam: memcpy_s for SERVER_V6_IF_ID failed with error %d`
- `0x1800619c8`: `SetRdConfigParam: Invalid configtype passed %d`

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
  __int64 v13; // r8
  const wchar_t *v14; // rdx
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // ebx
  __int64 v19; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v20; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v21; // [rsp+30h] [rbp-D0h]
  __int128 v22; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+50h] [rbp-B0h]
  __int64 v24; // [rsp+58h] [rbp-A8h]
  int v25; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v26[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  v5 = a3;
  LODWORD(v19) = 0;
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  v21 = 0;
  v20 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0xFFFFFFFFLL;
  v9 = *((_QWORD *)&xmmword_1800C9740 + 1);
  if ( *((_QWORD *)&xmmword_1800C9740 + 1) )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v20,
      L"RdInfo::SetRdConfigParam",
      (unsigned int *)&v19,
      v8);
    v9 = *((_QWORD *)&xmmword_1800C9740 + 1);
  }
  if ( !a4 )
  {
    LODWORD(v19) = 87;
    goto LABEL_72;
  }
  if ( a2 > 5 )
  {
    switch ( a2 )
    {
      case 6:
        if ( (unsigned int)v5 > 0x204 )
        {
          LODWORD(v19) = 87;
          if ( !v9 )
            goto LABEL_72;
          v10 = 516;
          goto LABEL_15;
        }
        v16 = memcpy_s(a1 + 24, 0x204u, a4, v5);
        v13 = v16;
        LODWORD(v19) = v16;
        if ( !v16 || !(_QWORD)xmmword_1800C9740 )
          goto LABEL_72;
        v14 = L"SetRdConfigParam: memcpy_s for SERVER_ADAPTER_NAME failed with error %d";
        break;
      case 7:
        if ( (_DWORD)v5 == 4 )
        {
          a1[153] = *a4;
          goto LABEL_72;
        }
        LODWORD(v19) = 87;
        if ( v9 )
        {
          v10 = 528;
          goto LABEL_15;
        }
        goto LABEL_72;
      case 8:
        if ( (_DWORD)v5 == 4 )
        {
          a1[154] = *a4;
          goto LABEL_72;
        }
        LODWORD(v19) = 87;
        if ( v9 )
        {
          v10 = 534;
          goto LABEL_15;
        }
        goto LABEL_72;
      case 9:
        if ( (_DWORD)v5 != 8 )
        {
          LODWORD(v19) = 87;
          if ( !v9 )
            goto LABEL_72;
          v10 = 540;
          goto LABEL_15;
        }
        v15 = memcpy_s(a1 + 18, 8u, a4, 8u);
        v13 = v15;
        LODWORD(v19) = v15;
        if ( !v15 || !(_QWORD)xmmword_1800C9740 )
          goto LABEL_72;
        v14 = L"SetRdConfigParam: memcpy_s for SERVER_V6_IF_ID failed with error %d";
        break;
      case 10:
        if ( (_DWORD)v5 == 4 )
        {
          a1[156] = *a4;
          goto LABEL_72;
        }
        LODWORD(v19) = 87;
        if ( v9 )
        {
          v10 = 552;
          goto LABEL_15;
        }
        goto LABEL_72;
      default:
LABEL_44:
        LODWORD(v19) = 87;
        if ( !(_QWORD)xmmword_1800C9740 )
          goto LABEL_72;
        v13 = (unsigned int)a2;
        v14 = L"SetRdConfigParam: Invalid configtype passed %d";
        break;
    }
LABEL_70:
    LOWORD(v25) = 0;
    FormatRRASErrorString(&v25, v14, v13);
    v11 = xmmword_1800C9740;
    goto LABEL_71;
  }
  switch ( a2 )
  {
    case 5:
      if ( (_DWORD)v5 == 4 )
      {
        a1[23] = *a4;
        goto LABEL_72;
      }
      LODWORD(v19) = 87;
      if ( v9 )
      {
        v10 = 510;
        goto LABEL_15;
      }
      goto LABEL_72;
    case 0:
      if ( (_DWORD)v5 == 4 )
      {
        a1[4] = *a4;
        goto LABEL_72;
      }
      LODWORD(v19) = 87;
      if ( v9 )
      {
        v10 = 474;
        goto LABEL_15;
      }
      goto LABEL_72;
    case 1:
      if ( (_DWORD)v5 != 52 )
      {
        LODWORD(v19) = 87;
        if ( !v9 )
          goto LABEL_72;
        v10 = 480;
        goto LABEL_15;
      }
      v12 = memcpy_s(a1 + 5, 0x34u, a4, 0x34u);
      v13 = v12;
      LODWORD(v19) = v12;
      if ( !v12 || !(_QWORD)xmmword_1800C9740 )
        goto LABEL_72;
      v14 = L"SetRdConfigParam: memcpy_s for SERVER_V6_NBO_IP_ADDRESS failed with error %d";
      goto LABEL_70;
    case 2:
      if ( (_DWORD)v5 == 4 )
      {
        a1[20] = *a4;
        goto LABEL_72;
      }
      LODWORD(v19) = 87;
      if ( v9 )
      {
        v10 = 492;
        goto LABEL_15;
      }
      goto LABEL_72;
  }
  if ( a2 != 3 )
  {
    if ( a2 == 4 )
    {
      if ( (_DWORD)v5 == 4 )
      {
        a1[22] = *a4;
        goto LABEL_72;
      }
      LODWORD(v19) = 87;
      if ( v9 )
      {
        v10 = 504;
LABEL_15:
        LOWORD(v25) = 0;
        FormatRRASErrorString(
          &v25,
          L"%s(Line#%d): Invalid parameter.",
          "RdInfo::SetRdConfigParam",
          v10,
          v19,
          v20,
          v21,
          v22,
          v23,
          v24);
        v11 = *((_QWORD *)&xmmword_1800C9740 + 1);
LABEL_71:
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, __int64, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          v11,
          &v25);
        goto LABEL_72;
      }
      goto LABEL_72;
    }
    goto LABEL_44;
  }
  if ( (_DWORD)v5 == 4 )
  {
    a1[21] = *a4;
    goto LABEL_72;
  }
  LODWORD(v19) = 87;
  if ( v9 )
  {
    v10 = 498;
    goto LABEL_15;
  }
LABEL_72:
  v17 = v19;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v20);
  return v17;
}

```

## disassembly

```asm
0x180061734  push    rbp
0x180061736  push    rbx
0x180061737  push    rsi
0x180061738  push    rdi
0x180061739  push    r14
0x18006173b  lea     rbp, [rsp-770h]
0x180061743  sub     rsp, 870h
0x18006174a  mov     rax, cs:__security_cookie
0x180061751  xor     rax, rsp
0x180061754  mov     [rbp+790h+var_30], rax
0x18006175b  mov     rbx, r9
0x18006175e  mov     edi, r8d
0x180061761  mov     r14d, edx
0x180061764  mov     rsi, rcx
0x180061767  mov     dword ptr [rsp+890h+var_870], 0
0x18006176f  xor     eax, eax
0x180061771  mov     [rsp+890h+var_830], eax
0x180061775  xor     edx, edx; Val
0x180061777  mov     r8d, 7FCh; Size
0x18006177d  lea     rcx, [rsp+890h+var_82C]; void *
0x180061782  call    memset_0
0x180061787  xorps   xmm0, xmm0
0x18006178a  movdqu  [rsp+890h+var_860], xmm0
0x180061790  mov     [rsp+890h+var_868], 0
0x180061799  xorps   xmm1, xmm1
0x18006179c  movdqu  [rsp+890h+var_850], xmm1
0x1800617a2  mov     [rsp+890h+var_840], 0
0x1800617ab  mov     [rsp+890h+var_838], 0FFFFFFFFh
0x1800617b3  mov     [rsp+890h+var_834], 0
0x1800617bb  mov     rcx, qword ptr cs:xmmword_1800C9740+8
0x1800617c2  test    rcx, rcx
0x1800617c5  jz      short loc_1800617E4
0x1800617c7  lea     r8, [rsp+890h+var_870]; unsigned int *
0x1800617cc  lea     rdx, aRdinfoSetrdcon; "RdInfo::SetRdConfigParam"
0x1800617d3  lea     rcx, [rsp+890h+var_868]; this
0x1800617d8  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x1800617dd  mov     rcx, qword ptr cs:xmmword_1800C9740+8
0x1800617e4  test    rbx, rbx
0x1800617e7  jnz     short loc_1800617F6
0x1800617e9  mov     dword ptr [rsp+890h+var_870], 57h ; 'W'
0x1800617f1  jmp     loc_180061B33
0x1800617f6  cmp     r14d, 5
0x1800617fa  jg      loc_180061987
0x180061800  jz      loc_18006195C
0x180061806  mov     edx, r14d
0x180061809  test    r14d, r14d
0x18006180c  jz      loc_180061931
0x180061812  sub     edx, 1
0x180061815  jz      loc_1800618D3
0x18006181b  sub     edx, 1
0x18006181e  jz      loc_1800618AB
0x180061824  sub     edx, 1
0x180061827  jz      short loc_180061883
0x180061829  cmp     edx, 1
0x18006182c  jnz     loc_1800619AF
0x180061832  cmp     edi, 4
0x180061835  jz      short loc_180061879
0x180061837  mov     dword ptr [rsp+890h+var_870], 57h ; 'W'
0x18006183f  test    rcx, rcx
0x180061842  jz      loc_180061B33
0x180061848  mov     r9d, 1F8h
0x18006184e  xor     eax, eax
0x180061850  mov     word ptr [rsp+890h+var_830], ax
0x180061855  lea     r8, aRdinfoSetrdcon_0; "RdInfo::SetRdConfigParam"
0x18006185c  lea     rdx, aSLineDInvalidP; "%s(Line#%d): Invalid parameter."
0x180061863  lea     rcx, [rsp+890h+var_830]
0x180061868  call    FormatRRASErrorString
0x18006186d  mov     rdx, qword ptr cs:xmmword_1800C9740+8
0x180061874  jmp     loc_180061B1B
0x180061879  mov     eax, [rbx]
0x18006187b  mov     [rsi+58h], eax
0x18006187e  jmp     loc_180061B33
0x180061883  cmp     edi, 4
0x180061886  jz      short loc_1800618A1
0x180061888  mov     dword ptr [rsp+890h+var_870], 57h ; 'W'
0x180061890  test    rcx, rcx
0x180061893  jz      loc_180061B33
0x180061899  mov     r9d, 1F2h
0x18006189f  jmp     short loc_18006184E
0x1800618a1  mov     eax, [rbx]
0x1800618a3  mov     [rsi+54h], eax
0x1800618a6  jmp     loc_180061B33
0x1800618ab  cmp     edi, 4
0x1800618ae  jz      short loc_1800618C9
0x1800618b0  mov     dword ptr [rsp+890h+var_870], 57h ; 'W'
0x1800618b8  test    rcx, rcx
0x1800618bb  jz      loc_180061B33
0x1800618c1  mov     r9d, 1ECh
0x1800618c7  jmp     short loc_18006184E
0x1800618c9  mov     eax, [rbx]
0x1800618cb  mov     [rsi+50h], eax
0x1800618ce  jmp     loc_180061B33
0x1800618d3  mov     edx, 34h ; '4'; DestinationSize
0x1800618d8  cmp     edi, edx
0x1800618da  jz      short loc_1800618F8
0x1800618dc  mov     dword ptr [rsp+890h+var_870], 57h ; 'W'
0x1800618e4  test    rcx, rcx
0x1800618e7  jz      loc_180061B33
0x1800618ed  mov     r9d, 1E0h
0x1800618f3  jmp     loc_18006184E
0x1800618f8  lea     rcx, [rsi+14h]; Destination
0x1800618fc  mov     r9, rdx; SourceSize
0x1800618ff  mov     r8, rbx; Source
0x180061902  call    cs:__imp_memcpy_s
0x180061908  mov     r8d, eax
0x18006190b  mov     dword ptr [rsp+890h+var_870], eax
0x18006190f  test    eax, eax
0x180061911  jz      loc_180061B33
0x180061917  cmp     qword ptr cs:xmmword_1800C9740, 0
0x18006191f  jz      loc_180061B33
0x180061925  lea     rdx, aSetrdconfigpar; "SetRdConfigParam: memcpy_s for SERVER_V"...
0x18006192c  jmp     loc_180061B03
0x180061931  cmp     edi, 4
0x180061934  jz      short loc_180061952
0x180061936  mov     dword ptr [rsp+890h+var_870], 57h ; 'W'
0x18006193e  test    rcx, rcx
0x180061941  jz      loc_180061B33
0x180061947  mov     r9d, 1DAh
0x18006194d  jmp     loc_18006184E
0x180061952  mov     eax, [rbx]
0x180061954  mov     [rsi+10h], eax
0x180061957  jmp     loc_180061B33
0x18006195c  cmp     edi, 4
0x18006195f  jz      short loc_18006197D
0x180061961  mov     dword ptr [rsp+890h+var_870], 57h ; 'W'
0x180061969  test    rcx, rcx
0x18006196c  jz      loc_180061B33
0x180061972  mov     r9d, 1FEh
0x180061978  jmp     loc_18006184E
0x18006197d  mov     eax, [rbx]
0x18006197f  mov     [rsi+5Ch], eax
0x180061982  jmp     loc_180061B33
0x180061987  mov     edx, r14d
0x18006198a  sub     edx, 6
0x18006198d  jz      loc_180061AB9
0x180061993  sub     edx, 1
0x180061996  jz      loc_180061A8E
0x18006199c  sub     edx, 1
0x18006199f  jz      loc_180061A60
0x1800619a5  sub     edx, 1
0x1800619a8  jz      short loc_180061A02
0x1800619aa  cmp     edx, 1
0x1800619ad  jz      short loc_1800619D4
0x1800619af  mov     dword ptr [rsp+890h+var_870], 57h ; 'W'
0x1800619b7  cmp     qword ptr cs:xmmword_1800C9740, 0
0x1800619bf  jz      loc_180061B33
0x1800619c5  mov     r8d, r14d
0x1800619c8  lea     rdx, aSetrdconfigpar_0; "SetRdConfigParam: Invalid configtype pa"...
0x1800619cf  jmp     loc_180061B03
0x1800619d4  cmp     edi, 4
0x1800619d7  jz      short loc_1800619F5
0x1800619d9  mov     dword ptr [rsp+890h+var_870], 57h ; 'W'
0x1800619e1  test    rcx, rcx
0x1800619e4  jz      loc_180061B33
0x1800619ea  mov     r9d, 228h
0x1800619f0  jmp     loc_18006184E
0x1800619f5  mov     eax, [rbx]
0x1800619f7  mov     [rsi+270h], eax
0x1800619fd  jmp     loc_180061B33
0x180061a02  mov     edx, 8; DestinationSize
0x180061a07  cmp     edi, edx
0x180061a09  jz      short loc_180061A27
0x180061a0b  mov     dword ptr [rsp+890h+var_870], 57h ; 'W'
0x180061a13  test    rcx, rcx
0x180061a16  jz      loc_180061B33
0x180061a1c  mov     r9d, 21Ch
0x180061a22  jmp     loc_18006184E
0x180061a27  lea     rcx, [rsi+48h]; Destination
0x180061a2b  mov     r9, rdx; SourceSize
0x180061a2e  mov     r8, rbx; Source
0x180061a31  call    cs:__imp_memcpy_s
0x180061a37  mov     r8d, eax
0x180061a3a  mov     dword ptr [rsp+890h+var_870], eax
0x180061a3e  test    eax, eax
0x180061a40  jz      loc_180061B33
0x180061a46  cmp     qword ptr cs:xmmword_1800C9740, 0
0x180061a4e  jz      loc_180061B33
0x180061a54  lea     rdx, aSetrdconfigpar_1; "SetRdConfigParam: memcpy_s for SERVER_V"...
0x180061a5b  jmp     loc_180061B03
0x180061a60  cmp     edi, 4
0x180061a63  jz      short loc_180061A81
0x180061a65  mov     dword ptr [rsp+890h+var_870], 57h ; 'W'
0x180061a6d  test    rcx, rcx
0x180061a70  jz      loc_180061B33
0x180061a76  mov     r9d, 216h
0x180061a7c  jmp     loc_18006184E
0x180061a81  mov     eax, [rbx]
0x180061a83  mov     [rsi+268h], eax
0x180061a89  jmp     loc_180061B33
0x180061a8e  cmp     edi, 4
0x180061a91  jz      short loc_180061AAF
0x180061a93  mov     dword ptr [rsp+890h+var_870], 57h ; 'W'
0x180061a9b  test    rcx, rcx
0x180061a9e  jz      loc_180061B33
0x180061aa4  mov     r9d, 210h
0x180061aaa  jmp     loc_18006184E
0x180061aaf  mov     eax, [rbx]
0x180061ab1  mov     [rsi+264h], eax
0x180061ab7  jmp     short loc_180061B33
0x180061ab9  mov     edx, 204h; DestinationSize
0x180061abe  cmp     edi, edx
0x180061ac0  jbe     short loc_180061AD7
0x180061ac2  mov     dword ptr [rsp+890h+var_870], 57h ; 'W'
0x180061aca  test    rcx, rcx
0x180061acd  jz      short loc_180061B33
0x180061acf  mov     r9d, edx
0x180061ad2  jmp     loc_18006184E
0x180061ad7  mov     r9, rdi; SourceSize
0x180061ada  lea     rcx, [rsi+60h]; Destination
0x180061ade  mov     r8, rbx; Source
0x180061ae1  call    cs:__imp_memcpy_s
0x180061ae7  mov     r8d, eax
0x180061aea  mov     dword ptr [rsp+890h+var_870], eax
0x180061aee  test    eax, eax
0x180061af0  jz      short loc_180061B33
0x180061af2  cmp     qword ptr cs:xmmword_1800C9740, 0
0x180061afa  jz      short loc_180061B33
0x180061afc  lea     rdx, aSetrdconfigpar_3; "SetRdConfigParam: memcpy_s for SERVER_A"...
0x180061b03  xor     eax, eax
0x180061b05  mov     word ptr [rsp+890h+var_830], ax
0x180061b0a  lea     rcx, [rsp+890h+var_830]
0x180061b0f  call    FormatRRASErrorString
0x180061b14  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180061b1b  lea     r8, [rsp+890h+var_830]
0x180061b20  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180061b27  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180061b2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061b33  mov     ebx, dword ptr [rsp+890h+var_870]
0x180061b37  lea     rcx, [rsp+890h+var_868]; this
0x180061b3c  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180061b41  mov     eax, ebx
0x180061b43  mov     rcx, [rbp+790h+var_30]
0x180061b4a  xor     rcx, rsp; StackCookie
0x180061b4d  call    __security_check_cookie
0x180061b52  add     rsp, 870h
0x180061b59  pop     r14
0x180061b5b  pop     rdi
0x180061b5c  pop     rsi
0x180061b5d  pop     rbx
0x180061b5e  pop     rbp
0x180061b5f  retn
```
