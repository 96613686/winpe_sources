# MspProvisionTbal

- ea: `0x180055e00`
- end: `0x1800561eb`
- name: `MspProvisionTbal`
- size: `1003`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, _QWORD *, _DWORD *, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180011090`
- `0x180012d10`

## callees

- `0x18000c5d0`
- `0x18000df40`
- `0x18003f7cc`
- `0x18003f864`
- `0x1800558c8`
- `0x180055e00`
- `0x18006d010`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x180055f6c`
- `ntdll!NtQuerySystemInformation` at `0x180055f6c`
- `ntdll!RtlReleaseResource` at `0x1800561b7`
- `ntdll!RtlReleaseResource` at `0x1800561b7`
- `ntdll!RtlAcquireResourceShared` at `0x180055fc3`
- `ntdll!RtlAcquireResourceShared` at `0x180055fc3`
- `ntdll!RtlInitUnicodeString` at `0x1800560c6`
- `ntdll!RtlInitUnicodeString` at `0x1800560c6`
- `LSASRV!LsarSetSecret` at `0x180056142`
- `LSASRV!LsarSetSecret` at `0x180056142`
- `LSASRV!LsarCreateSecret` at `0x18005610b`
- `LSASRV!LsarCreateSecret` at `0x18005610b`
- `LSASRV!LsarClose` at `0x1800561c8`
- `LSASRV!LsarClose` at `0x1800561c8`
- `LSASRV!LsarOpenSecret` at `0x1800560e7`
- `LSASRV!LsarOpenSecret` at `0x1800560e7`

## pseudocode

```c
__int64 __fastcall MspProvisionTbal(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        _QWORD *a5,
        _DWORD *a6,
        int *a7)
{
  int v7; // ebx
  _QWORD *v8; // rcx
  int v9; // edx
  int PrimaryCredential; // eax
  struct _MSV1_0_PRIMARY_CREDENTIAL *v11; // rdi
  _QWORD *v12; // rcx
  int v13; // edx
  __int64 v14; // rdx
  _BYTE *v15; // rax
  __int64 v17; // [rsp+40h] [rbp-11h] BYREF
  struct _MSV1_0_PRIMARY_CREDENTIAL *v18; // [rsp+48h] [rbp-9h] BYREF
  unsigned __int8 *v19[2]; // [rsp+50h] [rbp-1h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp+Fh] BYREF
  __int128 v21; // [rsp+70h] [rbp+1Fh] BYREF
  __int64 v22; // [rsp+80h] [rbp+2Fh]
  __int64 v23; // [rsp+A8h] [rbp+57h] BYREF
  __int16 SystemInformation; // [rsp+B8h] [rbp+67h] BYREF

  v23 = 0;
  v18 = 0;
  v17 = 0;
  v22 = 0;
  DestinationString = 0;
  *(_OWORD *)v19 = 0;
  v21 = 0;
  if ( a4 < 0xC )
  {
    v7 = -1073741811;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 12;
LABEL_5:
      WPP_SF_sL(
        v8[2],
        v9,
        (unsigned int)WPP_a66d676dc5db3a60f54e622a6aecb7e0_Traceguids,
        (unsigned int)"MspProvisionTbal",
        13);
      goto LABEL_54;
    }
    goto LABEL_54;
  }
  v23 = *(_QWORD *)(a2 + 4);
  if ( v23 )
  {
    if ( a5 )
      *a5 = 0;
    if ( a6 )
      *a6 = 0;
    if ( !((unsigned __int8 (__fastcall *)(__int128 *))LsaFunctions->GetCallInfo)(&v21) )
    {
      v7 = -1073741670;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sL(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          (unsigned int)WPP_a66d676dc5db3a60f54e622a6aecb7e0_Traceguids,
          (unsigned int)"MspProvisionTbal",
          154);
      goto LABEL_54;
    }
    if ( (BYTE8(v21) & 0x10) == 0 )
    {
      SystemInformation = 0;
      if ( NtQuerySystemInformation(SystemKernelDebuggerInformation, &SystemInformation, 2u, 0) < 0
        || !(_BYTE)SystemInformation
        || HIBYTE(SystemInformation) == 1 )
      {
        v7 = -1073741790;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sL(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            (unsigned int)WPP_a66d676dc5db3a60f54e622a6aecb7e0_Traceguids,
            (unsigned int)"MspProvisionTbal",
            34);
        goto LABEL_54;
      }
    }
    RtlAcquireResourceShared(&NlpActiveLogonLock, 1u);
    if ( !NlpFindActiveLogon(&v23) )
    {
      v7 = -1073741811;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDDL(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          (unsigned int)WPP_a66d676dc5db3a60f54e622a6aecb7e0_Traceguids,
          (unsigned int)"MspProvisionTbal",
          SBYTE4(v23),
          v23,
          13);
LABEL_53:
      RtlReleaseResource(&NlpActiveLogonLock);
      goto LABEL_54;
    }
    PrimaryCredential = NlpGetPrimaryCredential(&v23, &v18, &SystemInformation);
    v11 = v18;
    v7 = PrimaryCredential;
    if ( PrimaryCredential >= 0 )
    {
      v7 = MspSerializeTbalCredential(v18, &v19[1], (unsigned int *)v19);
      if ( v7 >= 0 )
      {
        RtlInitUnicodeString(&DestinationString, L"M$_MSV1_0_TBAL_PRIMARY_{22BE8E5B-58B3-4A87-BA71-41B0ECF3A9EA}");
        HIDWORD(v19[0]) = v19[0];
        v7 = LsarOpenSecret(NtLmGlobalPolicyHandle, &DestinationString, 3, &v17);
        if ( v7 == -1073741772 )
          v7 = LsarCreateSecret(NtLmGlobalPolicyHandle, &DestinationString, 983043, &v17);
        if ( v7 >= 0 )
        {
          v7 = LsarSetSecret(v17, v19, 0);
          if ( v7 < 0 )
          {
            v12 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v13 = 20;
              goto LABEL_48;
            }
          }
        }
        else
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v13 = 19;
            goto LABEL_48;
          }
        }
      }
      else
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v13 = 18;
          goto LABEL_48;
        }
      }
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v13 = 17;
LABEL_48:
        WPP_SF_sL(
          v12[2],
          v13,
          (unsigned int)WPP_a66d676dc5db3a60f54e622a6aecb7e0_Traceguids,
          (unsigned int)"MspProvisionTbal",
          v7);
      }
    }
    if ( v11 )
    {
      v14 = 352;
      v15 = (char *)v11 + 32;
      do
      {
        *v15++ = 0;
        --v14;
      }
      while ( v14 );
      ((void (__fastcall *)(struct _MSV1_0_PRIMARY_CREDENTIAL *))qword_180088240)(v11);
    }
    goto LABEL_53;
  }
  v7 = -1073741811;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v9 = 13;
    goto LABEL_5;
  }
LABEL_54:
  if ( v17 )
    LsarClose(&v17);
  *a7 = v7;
  return 0;
}

```

## disassembly

```asm
0x180055e00  mov     [rsp-8+arg_0], rbx
0x180055e05  mov     [rsp-8+arg_10], rdi
0x180055e0a  push    rbp
0x180055e0b  lea     rbp, [rsp-3Fh]
0x180055e10  sub     rsp, 90h
0x180055e17  xor     eax, eax
0x180055e19  mov     [rbp+3Fh+arg_8], 0
0x180055e21  mov     [rbp+3Fh+var_48], 0
0x180055e29  xorps   xmm0, xmm0
0x180055e2c  mov     [rbp+3Fh+var_50], 0
0x180055e34  xorps   xmm1, xmm1
0x180055e37  mov     [rbp+3Fh+var_10], rax
0x180055e3b  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x180055e3f  movups  xmmword ptr [rbp+3Fh+var_40], xmm1
0x180055e43  movups  [rbp+3Fh+var_20], xmm0
0x180055e47  cmp     r9d, 0Ch
0x180055e4b  jnb     short loc_180055E9C
0x180055e4d  mov     ebx, 0C000000Dh
0x180055e52  mov     rcx, cs:WPP_GLOBAL_Control
0x180055e59  lea     rax, WPP_GLOBAL_Control
0x180055e60  cmp     rcx, rax
0x180055e63  jz      loc_1800561BD
0x180055e69  test    byte ptr [rcx+1Ch], 1
0x180055e6d  jz      loc_1800561BD
0x180055e73  mov     edx, 0Ch
0x180055e78  mov     [rsp+90h+var_70], 0C000000Dh
0x180055e80  mov     rcx, [rcx+10h]
0x180055e84  lea     r9, aMspprovisiontb; "MspProvisionTbal"
0x180055e8b  lea     r8, WPP_a66d676dc5db3a60f54e622a6aecb7e0_Traceguids
0x180055e92  call    WPP_SF_sL
0x180055e97  jmp     loc_1800561BD
0x180055e9c  mov     rax, [rdx+4]
0x180055ea0  mov     rcx, rax
0x180055ea3  mov     [rbp+3Fh+arg_8], rax
0x180055ea7  shr     rcx, 20h
0x180055eab  test    ecx, ecx
0x180055ead  jnz     short loc_180055EE0
0x180055eaf  test    eax, eax
0x180055eb1  jnz     short loc_180055EE0
0x180055eb3  mov     ebx, 0C000000Dh
0x180055eb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180055ebf  lea     rax, WPP_GLOBAL_Control
0x180055ec6  cmp     rcx, rax
0x180055ec9  jz      loc_1800561BD
0x180055ecf  test    byte ptr [rcx+1Ch], 1
0x180055ed3  jz      loc_1800561BD
0x180055ed9  mov     edx, 0Dh
0x180055ede  jmp     short loc_180055E78
0x180055ee0  mov     rax, [rbp+3Fh+arg_20]
0x180055ee4  test    rax, rax
0x180055ee7  jz      short loc_180055EF0
0x180055ee9  mov     qword ptr [rax], 0
0x180055ef0  mov     rax, [rbp+3Fh+arg_28]
0x180055ef4  test    rax, rax
0x180055ef7  jz      short loc_180055EFF
0x180055ef9  mov     dword ptr [rax], 0
0x180055eff  mov     rax, cs:LsaFunctions
0x180055f06  lea     rcx, [rbp+3Fh+var_20]
0x180055f0a  mov     rax, [rax+0C0h]
0x180055f11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055f16  test    al, al
0x180055f18  jnz     short loc_180055F52
0x180055f1a  mov     ebx, 0C000009Ah
0x180055f1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180055f26  lea     rax, WPP_GLOBAL_Control
0x180055f2d  cmp     rcx, rax
0x180055f30  jz      loc_1800561BD
0x180055f36  test    byte ptr [rcx+1Ch], 1
0x180055f3a  jz      loc_1800561BD
0x180055f40  mov     edx, 0Eh
0x180055f45  mov     [rsp+90h+var_70], 0C000009Ah
0x180055f4d  jmp     loc_180055E80
0x180055f52  test    byte ptr [rbp+3Fh+var_20+8], 10h
0x180055f56  jnz     short loc_180055FBA
0x180055f58  xor     eax, eax
0x180055f5a  lea     rdx, [rbp+3Fh+SystemInformation]; SystemInformation
0x180055f5e  xor     r9d, r9d; ReturnLength
0x180055f61  mov     [rbp+3Fh+SystemInformation], ax
0x180055f65  lea     r8d, [rax+2]; SystemInformationLength
0x180055f69  lea     ecx, [rax+23h]; SystemInformationClass
0x180055f6c  call    cs:__imp_NtQuerySystemInformation
0x180055f72  test    eax, eax
0x180055f74  js      short loc_180055F82
0x180055f76  cmp     byte ptr [rbp+3Fh+SystemInformation], 0
0x180055f7a  jz      short loc_180055F82
0x180055f7c  cmp     byte ptr [rbp+3Fh+SystemInformation+1], 1
0x180055f80  jnz     short loc_180055FBA
0x180055f82  mov     ebx, 0C0000022h
0x180055f87  mov     rcx, cs:WPP_GLOBAL_Control
0x180055f8e  lea     rax, WPP_GLOBAL_Control
0x180055f95  cmp     rcx, rax
0x180055f98  jz      loc_1800561BD
0x180055f9e  test    byte ptr [rcx+1Ch], 1
0x180055fa2  jz      loc_1800561BD
0x180055fa8  mov     edx, 0Fh
0x180055fad  mov     [rsp+90h+var_70], 0C0000022h
0x180055fb5  jmp     loc_180055E80
0x180055fba  mov     dl, 1; Wait
0x180055fbc  lea     rcx, NlpActiveLogonLock; Resource
0x180055fc3  call    cs:__imp_RtlAcquireResourceShared
0x180055fc9  lea     rcx, [rbp+3Fh+arg_8]; void *
0x180055fcd  call    NlpFindActiveLogon
0x180055fd2  test    rax, rax
0x180055fd5  jnz     short loc_180056034
0x180055fd7  mov     ebx, 0C000000Dh
0x180055fdc  mov     rcx, cs:WPP_GLOBAL_Control
0x180055fe3  lea     rax, WPP_GLOBAL_Control
0x180055fea  cmp     rcx, rax
0x180055fed  jz      loc_1800561B0
0x180055ff3  test    byte ptr [rcx+1Ch], 1
0x180055ff7  jz      loc_1800561B0
0x180055ffd  mov     eax, dword ptr [rbp+3Fh+arg_8]
0x180056000  lea     r9, aMspprovisiontb; "MspProvisionTbal"
0x180056007  mov     rcx, [rcx+10h]
0x18005600b  lea     r8, WPP_a66d676dc5db3a60f54e622a6aecb7e0_Traceguids
0x180056012  mov     [rsp+90h+var_60], 0C000000Dh
0x18005601a  mov     edx, 10h
0x18005601f  mov     [rsp+90h+var_68], eax
0x180056023  mov     eax, dword ptr [rbp+3Fh+arg_8+4]
0x180056026  mov     [rsp+90h+var_70], eax
0x18005602a  call    WPP_SF_sDDL
0x18005602f  jmp     loc_1800561B0
0x180056034  lea     r8, [rbp+3Fh+SystemInformation]
0x180056038  lea     rdx, [rbp+3Fh+var_48]
0x18005603c  lea     rcx, [rbp+3Fh+arg_8]
0x180056040  call    NlpGetPrimaryCredential
0x180056045  mov     rdi, [rbp+3Fh+var_48]
0x180056049  mov     ebx, eax
0x18005604b  test    eax, eax
0x18005604d  jns     short loc_18005607A
0x18005604f  mov     rcx, cs:WPP_GLOBAL_Control
0x180056056  lea     rax, WPP_GLOBAL_Control
0x18005605d  cmp     rcx, rax
0x180056060  jz      loc_180056187
0x180056066  test    byte ptr [rcx+1Ch], 1
0x18005606a  jz      loc_180056187
0x180056070  mov     edx, 11h
0x180056075  jmp     loc_18005616C
0x18005607a  lea     r8, [rbp+3Fh+var_40]; unsigned int *
0x18005607e  mov     rcx, rdi; struct _MSV1_0_PRIMARY_CREDENTIAL *
0x180056081  lea     rdx, [rbp+3Fh+var_40+8]; unsigned __int8 **
0x180056085  call    ?MspSerializeTbalCredential@@YAJPEAU_MSV1_0_PRIMARY_CREDENTIAL@@PEAPEAEPEAK@Z; MspSerializeTbalCredential(_MSV1_0_PRIMARY_CREDENTIAL *,uchar * *,ulong *)
0x18005608a  mov     ebx, eax
0x18005608c  test    eax, eax
0x18005608e  jns     short loc_1800560BB
0x180056090  mov     rcx, cs:WPP_GLOBAL_Control
0x180056097  lea     rax, WPP_GLOBAL_Control
0x18005609e  cmp     rcx, rax
0x1800560a1  jz      loc_180056187
0x1800560a7  test    byte ptr [rcx+1Ch], 1
0x1800560ab  jz      loc_180056187
0x1800560b1  mov     edx, 12h
0x1800560b6  jmp     loc_18005616C
0x1800560bb  lea     rdx, aMMsv10TbalPrim; "M$_MSV1_0_TBAL_PRIMARY_{22BE8E5B-58B3-4"...
0x1800560c2  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x1800560c6  call    cs:__imp_RtlInitUnicodeString
0x1800560cc  mov     eax, dword ptr [rbp+3Fh+var_40]
0x1800560cf  lea     r9, [rbp+3Fh+var_50]
0x1800560d3  mov     rcx, cs:NtLmGlobalPolicyHandle
0x1800560da  lea     rdx, [rbp+3Fh+DestinationString]
0x1800560de  mov     r8d, 3
0x1800560e4  mov     dword ptr [rbp+3Fh+var_40+4], eax
0x1800560e7  call    cs:__imp_LsarOpenSecret
0x1800560ed  mov     ebx, eax
0x1800560ef  cmp     eax, 0C0000034h
0x1800560f4  jnz     short loc_180056113
0x1800560f6  mov     rcx, cs:NtLmGlobalPolicyHandle
0x1800560fd  lea     r9, [rbp+3Fh+var_50]
0x180056101  mov     r8d, 0F0003h
0x180056107  lea     rdx, [rbp+3Fh+DestinationString]
0x18005610b  call    cs:__imp_LsarCreateSecret
0x180056111  mov     ebx, eax
0x180056113  test    ebx, ebx
0x180056115  jns     short loc_180056137
0x180056117  mov     rcx, cs:WPP_GLOBAL_Control
0x18005611e  lea     rax, WPP_GLOBAL_Control
0x180056125  cmp     rcx, rax
0x180056128  jz      short loc_180056187
0x18005612a  test    byte ptr [rcx+1Ch], 1
0x18005612e  jz      short loc_180056187
0x180056130  mov     edx, 13h
0x180056135  jmp     short loc_18005616C
0x180056137  mov     rcx, [rbp+3Fh+var_50]
0x18005613b  lea     rdx, [rbp+3Fh+var_40]
0x18005613f  xor     r8d, r8d
0x180056142  call    cs:__imp_LsarSetSecret
0x180056148  mov     ebx, eax
0x18005614a  test    eax, eax
0x18005614c  jns     short loc_180056187
0x18005614e  mov     rcx, cs:WPP_GLOBAL_Control
0x180056155  lea     rax, WPP_GLOBAL_Control
0x18005615c  cmp     rcx, rax
0x18005615f  jz      short loc_180056187
0x180056161  test    byte ptr [rcx+1Ch], 1
0x180056165  jz      short loc_180056187
0x180056167  mov     edx, 14h
0x18005616c  mov     rcx, [rcx+10h]
0x180056170  lea     r9, aMspprovisiontb; "MspProvisionTbal"
0x180056177  lea     r8, WPP_a66d676dc5db3a60f54e622a6aecb7e0_Traceguids
0x18005617e  mov     [rsp+90h+var_70], ebx
0x180056182  call    WPP_SF_sL
0x180056187  test    rdi, rdi
0x18005618a  jz      short loc_1800561B0
0x18005618c  mov     edx, 160h
0x180056191  lea     rax, [rdi+20h]
0x180056195  mov     byte ptr [rax], 0
0x180056198  inc     rax
0x18005619b  sub     rdx, 1
0x18005619f  jnz     short loc_180056195
0x1800561a1  mov     rax, cs:qword_180088240
0x1800561a8  mov     rcx, rdi
0x1800561ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800561b0  lea     rcx, NlpActiveLogonLock; Resource
0x1800561b7  call    cs:__imp_RtlReleaseResource
0x1800561bd  cmp     [rbp+3Fh+var_50], 0
0x1800561c2  jz      short loc_1800561CE
0x1800561c4  lea     rcx, [rbp+3Fh+var_50]
0x1800561c8  call    cs:__imp_LsarClose
0x1800561ce  mov     rax, [rbp+3Fh+arg_30]
0x1800561d2  lea     r11, [rsp+90h+var_s0]
0x1800561da  mov     rdi, [r11+20h]
0x1800561de  mov     [rax], ebx
0x1800561e0  xor     eax, eax
0x1800561e2  mov     rbx, [r11+10h]
0x1800561e6  mov     rsp, r11
0x1800561e9  pop     rbp
0x1800561ea  retn
```
