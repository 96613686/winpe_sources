# DfscFileSystemControl

- ea: `0x140014910`
- end: `0x140014d27`
- name: `DfscFileSystemControl`
- size: `1047`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `27`
- tags: `broker_com_uri`

## callees

- `0x140001010`
- `0x140001744`
- `0x140004314`
- `0x1400044c4`
- `0x140004510`
- `0x140014910`
- `0x140014d30`
- `0x140015050`
- `0x14001520c`
- `0x140015520`
- `0x1400158f0`
- `0x140015f30`
- `0x140016070`
- `0x1400169f8`
- `0x140016b80`
- `0x14001a79c`
- `0x14001a7bc`
- `0x140021410`
- `0x140021c60`
- `0x140021e28`
- `0x140022b60`
- `0x140025f20`
- `0x1400270f0`
- `0x140028004`
- `0x1400282f4`
- `0x14002856c`
- `0x140029160`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140014d05`
- `ntoskrnl!IofCompleteRequest` at `0x140014d05`

## pseudocode

```c
__int64 __fastcall DfscFileSystemControl(__int64 a1, IRP *a2)
{
  unsigned int *p_MajorFunction; // rax
  struct _IRP *MasterIrp; // rsi
  unsigned int v5; // ecx
  size_t v6; // r8
  unsigned int v7; // r14d
  int ContainerContextFromIrp; // ebx
  int DriveLetter; // eax
  int NetUses; // eax
  __int64 v11; // r9
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  struct _UNICODE_PREFIX_TABLE *ReferralCache; // rax
  unsigned int v19; // edx
  __int64 v22; // [rsp+58h] [rbp+28h] BYREF
  __int64 v23; // [rsp+60h] [rbp+30h] BYREF

  p_MajorFunction = (unsigned int *)&a2->Tail.Overlay.CurrentStackLocation->MajorFunction;
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  v23 = 0;
  a2->IoStatus.Information = 0;
  v5 = p_MajorFunction[6];
  v6 = p_MajorFunction[2];
  v7 = p_MajorFunction[4];
  LODWORD(v22) = p_MajorFunction[2];
  if ( v5 > 0x680A4 )
  {
    if ( v5 > 0x6A00C )
    {
      if ( !(v5 - 434192) )
      {
        DriveLetter = DfscFsctrlFlushClusterSetCache(a2, MasterIrp, v7);
        goto LABEL_66;
      }
    }
    else
    {
      if ( v5 == 434188 )
      {
        DriveLetter = DfscFsctrlFlushDomainCache(a2, MasterIrp, v7);
        goto LABEL_66;
      }
      v12 = v5 - 426268;
      if ( !v12 )
      {
        DriveLetter = DfscFsctrlSetDomainNameFlat(a2, MasterIrp, v7);
        goto LABEL_66;
      }
      v13 = v12 - 4;
      if ( !v13 )
      {
        DriveLetter = DfscFsctrlSetDomainNameDns(a2, MasterIrp, v7);
        goto LABEL_66;
      }
      v14 = v13 - 8;
      if ( !v14 )
      {
        DriveLetter = DfscFsctrlSpecialSetDc(a2, MasterIrp, v7);
        goto LABEL_66;
      }
      v15 = v14 - 32;
      if ( !v15 )
      {
        DriveLetter = DfscFsctrlSetClusterSetName(a2, MasterIrp, v7);
        goto LABEL_66;
      }
      v16 = v15 - 7800;
      if ( !v16 )
      {
        DriveLetter = DfscFsctrlSetClientInfo(a2, MasterIrp, v7);
        goto LABEL_66;
      }
      v17 = v16 - 48;
      if ( !v17 )
      {
        DriveLetter = DfscFsctrlFlushRefCache(a2, MasterIrp, v7);
        goto LABEL_66;
      }
      if ( v17 == 4 )
      {
        v22 = 0;
        if ( MasterIrp && v7 >= 4 )
        {
          ContainerContextFromIrp = DfscGetContainerContextFromIrp(a2, &v22);
          if ( ContainerContextFromIrp < 0 )
            goto LABEL_67;
          ReferralCache = (struct _UNICODE_PREFIX_TABLE *)DfscGetReferralCache(v22);
          v19 = *(_DWORD *)&MasterIrp->Type;
          if ( (unsigned int)(*(_DWORD *)&MasterIrp->Type - 3) <= 1 )
          {
            DfscCacheExpire(ReferralCache);
            goto LABEL_67;
          }
          if ( v19 <= 2 || v19 == 5 )
          {
            DfscCachePurge(ReferralCache);
            goto LABEL_67;
          }
        }
        goto LABEL_14;
      }
    }
    goto LABEL_64;
  }
  if ( v5 == 426148 )
  {
    ContainerContextFromIrp = DfscGetContainerContextFromIrp(a2, &v23);
    if ( ContainerContextFromIrp < 0 )
      goto LABEL_67;
    LOBYTE(v11) = 1;
    DriveLetter = DfscFsctrlSetDcName(a2, MasterIrp, v7, v11, v23);
    v23 = 0;
    goto LABEL_66;
  }
  if ( v5 <= 0x601E0 )
  {
    if ( v5 == 393696 )
    {
      DriveLetter = DfscFsctrlCreateDriveLetter(a2, MasterIrp, v7);
      goto LABEL_66;
    }
    if ( v5 == 393408 )
    {
      DriveLetter = DfscFsctrlGetServerName((_DWORD)a2, (_DWORD)MasterIrp, v7, (_DWORD)MasterIrp, v6);
      goto LABEL_66;
    }
    if ( v5 != 393496 )
    {
      if ( v5 == 393508 )
        goto LABEL_18;
      if ( v5 != 393536 )
      {
        if ( v5 != 393540 )
        {
          switch ( v5 )
          {
            case 0x60168u:
              DriveLetter = DfscFsctrlSqmGetReg(a2, MasterIrp);
              goto LABEL_66;
            case 0x6016Cu:
              DriveLetter = DfscFsctrlSqmGetData((_DWORD)a2, (_DWORD)MasterIrp, v7, (_DWORD)MasterIrp, v6);
              goto LABEL_66;
            case 0x601A8u:
              if ( v7 < 6 )
              {
LABEL_14:
                ContainerContextFromIrp = -1073741811;
                goto LABEL_67;
              }
              DriveLetter = DfscFsctrlIsDfsPath(a2, &MasterIrp->Size, v7 - 2);
LABEL_66:
              ContainerContextFromIrp = DriveLetter;
              goto LABEL_67;
          }
LABEL_64:
          ContainerContextFromIrp = -1073741808;
          goto LABEL_67;
        }
LABEL_18:
        DriveLetter = DfscFsctrlGetDomainCache((_DWORD)a2, (_DWORD)MasterIrp, v7, (_DWORD)MasterIrp, v6, v5);
        goto LABEL_66;
      }
    }
    DriveLetter = DfscFsctrlGetRefCache(a2, MasterIrp, v6);
    goto LABEL_66;
  }
  switch ( v5 )
  {
    case 0x601E4u:
      DriveLetter = DfscFsctrlRemoveDriveLetter((_DWORD)a2, (_DWORD)MasterIrp, v7, (_DWORD)MasterIrp, (__int64)&v22);
      goto LABEL_66;
    case 0x601E8u:
      NetUses = DfscFsctrlGetNetUses((_DWORD)a2, (_DWORD)MasterIrp, v7, (_DWORD)MasterIrp, (__int64)&v22);
      break;
    case 0x601ECu:
      DriveLetter = DfscFsctrlIsValidDriveLetterConnection(a2, MasterIrp, v7);
      goto LABEL_66;
    case 0x601F0u:
      NetUses = DfscFsctrlGetDriveLetterConnectionPath(
                  (_DWORD)a2,
                  (_DWORD)MasterIrp,
                  v7,
                  (_DWORD)MasterIrp,
                  (__int64)&v22);
      break;
    case 0x601F4u:
    case 0x601F8u:
      NetUses = DfscFsctrlGetUseInfo((_DWORD)a2, (_DWORD)MasterIrp, v7, (_DWORD)MasterIrp, (__int64)&v22, v5);
      break;
    case 0x61FBCu:
      DriveLetter = DfscFsctrlGetClientInfo(a2, MasterIrp, v7, MasterIrp, v6);
      goto LABEL_66;
    default:
      goto LABEL_64;
  }
  ContainerContextFromIrp = NetUses;
  if ( !NetUses )
    a2->IoStatus.Information = (unsigned int)v22;
LABEL_67:
  a2->IoStatus.Status = ContainerContextFromIrp;
  IofCompleteRequest(a2, 0);
  return (unsigned int)ContainerContextFromIrp;
}

```

## disassembly

```asm
0x140014910  mov     [rsp-18h+arg_0], rbx
0x140014915  mov     [rsp-18h+arg_18], rsi
0x14001491a  push    rbp
0x14001491b  push    rdi
0x14001491c  push    r14
0x14001491e  mov     rbp, rsp
0x140014921  sub     rsp, 30h
0x140014925  mov     rax, [rdx+0B8h]
0x14001492c  mov     rdi, rdx
0x14001492f  mov     rsi, [rdx+18h]
0x140014933  mov     [rbp+arg_10], 0
0x14001493b  mov     qword ptr [rdx+38h], 0
0x140014943  mov     ecx, [rax+18h]
0x140014946  mov     r8d, [rax+8]; Size
0x14001494a  mov     r14d, [rax+10h]
0x14001494e  mov     eax, 680A4h
0x140014953  mov     dword ptr [rbp+arg_8], r8d
0x140014957  cmp     ecx, eax
0x140014959  ja      loc_140014B8F
0x14001495f  jz      loc_140014B52
0x140014965  mov     eax, 601E0h
0x14001496a  cmp     ecx, eax
0x14001496c  ja      loc_140014A64
0x140014972  jz      loc_140014A51
0x140014978  mov     eax, ecx
0x14001497a  sub     eax, 600C0h
0x14001497f  jz      loc_140014A36
0x140014985  sub     eax, 58h ; 'X'
0x140014988  jz      loc_140014A23
0x14001498e  sub     eax, 0Ch
0x140014991  jz      short loc_140014A04
0x140014993  sub     eax, 1Ch
0x140014996  jz      loc_140014A23
0x14001499c  sub     eax, 4
0x14001499f  jz      short loc_140014A04
0x1400149a1  sub     eax, 24h ; '$'
0x1400149a4  jz      short loc_1400149F4
0x1400149a6  sub     eax, 4
0x1400149a9  jz      short loc_1400149D9
0x1400149ab  cmp     eax, 3Ch ; '<'
0x1400149ae  jnz     loc_140014CE6
0x1400149b4  cmp     r14d, 6
0x1400149b8  jnb     short loc_1400149C4
0x1400149ba  mov     ebx, 0C000000Dh
0x1400149bf  jmp     loc_140014CFD
0x1400149c4  lea     r8d, [r14-2]
0x1400149c8  mov     rcx, rdi
0x1400149cb  lea     rdx, [rsi+2]
0x1400149cf  call    DfscFsctrlIsDfsPath
0x1400149d4  jmp     loc_140014CFB
0x1400149d9  mov     [rsp+30h+var_10], r8d
0x1400149de  mov     r9, rsi
0x1400149e1  mov     r8d, r14d
0x1400149e4  mov     rdx, rsi
0x1400149e7  mov     rcx, rdi
0x1400149ea  call    DfscFsctrlSqmGetData
0x1400149ef  jmp     loc_140014CFB
0x1400149f4  mov     rdx, rsi
0x1400149f7  mov     rcx, rdi
0x1400149fa  call    DfscFsctrlSqmGetReg
0x1400149ff  jmp     loc_140014CFB
0x140014a04  mov     [rsp+30h+var_8], ecx
0x140014a08  mov     r9, rsi
0x140014a0b  mov     [rsp+30h+var_10], r8d
0x140014a10  mov     rdx, rsi
0x140014a13  mov     r8d, r14d
0x140014a16  mov     rcx, rdi
0x140014a19  call    DfscFsctrlGetDomainCache
0x140014a1e  jmp     loc_140014CFB
0x140014a23  mov     r9d, ecx
0x140014a26  mov     rdx, rsi; void *
0x140014a29  mov     rcx, rdi; Irp
0x140014a2c  call    DfscFsctrlGetRefCache
0x140014a31  jmp     loc_140014CFB
0x140014a36  mov     [rsp+30h+var_10], r8d
0x140014a3b  mov     r9, rsi
0x140014a3e  mov     r8d, r14d
0x140014a41  mov     rdx, rsi
0x140014a44  mov     rcx, rdi
0x140014a47  call    DfscFsctrlGetServerName
0x140014a4c  jmp     loc_140014CFB
0x140014a51  mov     r8d, r14d
0x140014a54  mov     rdx, rsi
0x140014a57  mov     rcx, rdi
0x140014a5a  call    DfscFsctrlCreateDriveLetter
0x140014a5f  jmp     loc_140014CFB
0x140014a64  mov     eax, ecx
0x140014a66  sub     eax, 601E4h
0x140014a6b  jz      loc_140014B33
0x140014a71  sub     eax, 4
0x140014a74  jz      loc_140014B03
0x140014a7a  sub     eax, 4
0x140014a7d  jz      short loc_140014AF0
0x140014a7f  sub     eax, 4
0x140014a82  jz      short loc_140014AD4
0x140014a84  sub     eax, 4
0x140014a87  jz      short loc_140014AB4
0x140014a89  sub     eax, 4
0x140014a8c  jz      short loc_140014AB4
0x140014a8e  cmp     eax, 1DC4h
0x140014a93  jnz     loc_140014CE6
0x140014a99  mov     [rsp+30h+var_10], r8d; int
0x140014a9e  mov     r9, rsi; void *
0x140014aa1  mov     r8d, r14d; Size
0x140014aa4  mov     rdx, rsi; Src
0x140014aa7  mov     rcx, rdi; Irp
0x140014aaa  call    DfscFsctrlGetClientInfo
0x140014aaf  jmp     loc_140014CFB
0x140014ab4  mov     [rsp+30h+var_8], ecx
0x140014ab8  lea     rax, [rbp+arg_8]
0x140014abc  mov     rcx, rdi
0x140014abf  mov     qword ptr [rsp+30h+var_10], rax
0x140014ac4  mov     r9, rsi
0x140014ac7  mov     r8d, r14d
0x140014aca  mov     rdx, rsi
0x140014acd  call    DfscFsctrlGetUseInfo
0x140014ad2  jmp     short loc_140014B1D
0x140014ad4  lea     rax, [rbp+arg_8]
0x140014ad8  mov     r9, rsi
0x140014adb  mov     r8d, r14d
0x140014ade  mov     qword ptr [rsp+30h+var_10], rax
0x140014ae3  mov     rdx, rsi
0x140014ae6  mov     rcx, rdi
0x140014ae9  call    DfscFsctrlGetDriveLetterConnectionPath
0x140014aee  jmp     short loc_140014B1D
0x140014af0  mov     r8d, r14d
0x140014af3  mov     rdx, rsi
0x140014af6  mov     rcx, rdi
0x140014af9  call    DfscFsctrlIsValidDriveLetterConnection
0x140014afe  jmp     loc_140014CFB
0x140014b03  lea     rax, [rbp+arg_8]
0x140014b07  mov     r9, rsi
0x140014b0a  mov     r8d, r14d
0x140014b0d  mov     qword ptr [rsp+30h+var_10], rax
0x140014b12  mov     rdx, rsi
0x140014b15  mov     rcx, rdi
0x140014b18  call    DfscFsctrlGetNetUses
0x140014b1d  mov     ebx, eax
0x140014b1f  test    eax, eax
0x140014b21  jnz     loc_140014CFD
0x140014b27  mov     eax, dword ptr [rbp+arg_8]
0x140014b2a  mov     [rdi+38h], rax
0x140014b2e  jmp     loc_140014CFD
0x140014b33  lea     rax, [rbp+arg_8]
0x140014b37  mov     r9, rsi
0x140014b3a  mov     r8d, r14d
0x140014b3d  mov     qword ptr [rsp+30h+var_10], rax
0x140014b42  mov     rdx, rsi
0x140014b45  mov     rcx, rdi
0x140014b48  call    DfscFsctrlRemoveDriveLetter
0x140014b4d  jmp     loc_140014CFB
0x140014b52  lea     rdx, [rbp+arg_10]
0x140014b56  mov     rcx, rdi
0x140014b59  call    DfscGetContainerContextFromIrp
0x140014b5e  mov     ebx, eax
0x140014b60  test    eax, eax
0x140014b62  js      loc_140014CFD
0x140014b68  mov     rax, [rbp+arg_10]
0x140014b6c  mov     r9b, 1
0x140014b6f  mov     r8d, r14d
0x140014b72  mov     qword ptr [rsp+30h+var_10], rax
0x140014b77  mov     rdx, rsi
0x140014b7a  mov     rcx, rdi
0x140014b7d  call    DfscFsctrlSetDcName
0x140014b82  mov     [rbp+arg_10], 0
0x140014b8a  jmp     loc_140014CFB
0x140014b8f  mov     eax, 6A00Ch
0x140014b94  cmp     ecx, eax
0x140014b96  ja      loc_140014CC4
0x140014b9c  jz      loc_140014CB4
0x140014ba2  sub     ecx, 6811Ch
0x140014ba8  jz      loc_140014CA4
0x140014bae  sub     ecx, 4
0x140014bb1  jz      loc_140014C94
0x140014bb7  sub     ecx, 8
0x140014bba  jz      loc_140014C84
0x140014bc0  sub     ecx, 20h ; ' '
0x140014bc3  jz      loc_140014C74
0x140014bc9  sub     ecx, 1E78h
0x140014bcf  jz      loc_140014C61
0x140014bd5  sub     ecx, 30h ; '0'
0x140014bd8  jz      short loc_140014C4E
0x140014bda  cmp     ecx, 4
0x140014bdd  jnz     loc_140014CE6
0x140014be3  mov     [rbp+arg_8], 0
0x140014beb  test    rsi, rsi
0x140014bee  jz      loc_1400149BA
0x140014bf4  cmp     r14d, ecx
0x140014bf7  jb      loc_1400149BA
0x140014bfd  lea     rdx, [rbp+arg_8]
0x140014c01  mov     rcx, rdi
0x140014c04  call    DfscGetContainerContextFromIrp
0x140014c09  mov     ebx, eax
0x140014c0b  test    eax, eax
0x140014c0d  js      loc_140014CFD
0x140014c13  mov     rcx, [rbp+arg_8]
0x140014c17  call    DfscGetReferralCache
0x140014c1c  mov     edx, [rsi]
0x140014c1e  lea     ecx, [rdx-3]
0x140014c21  cmp     ecx, 1
0x140014c24  jbe     short loc_140014C41
0x140014c26  cmp     edx, 2
0x140014c29  jbe     short loc_140014C34
0x140014c2b  cmp     edx, 5
0x140014c2e  jnz     loc_1400149BA
0x140014c34  mov     rcx, rax; PrefixTable
0x140014c37  call    DfscCachePurge
0x140014c3c  jmp     loc_140014CFD
0x140014c41  mov     rcx, rax; PrefixTable
0x140014c44  call    DfscCacheExpire
0x140014c49  jmp     loc_140014CFD
0x140014c4e  mov     r8d, r14d
0x140014c51  mov     rdx, rsi
0x140014c54  mov     rcx, rdi
0x140014c57  call    DfscFsctrlFlushRefCache
0x140014c5c  jmp     loc_140014CFB
0x140014c61  mov     r8d, r14d
0x140014c64  mov     rdx, rsi
0x140014c67  mov     rcx, rdi
0x140014c6a  call    DfscFsctrlSetClientInfo
0x140014c6f  jmp     loc_140014CFB
0x140014c74  mov     r8d, r14d
0x140014c77  mov     rdx, rsi
0x140014c7a  mov     rcx, rdi
0x140014c7d  call    DfscFsctrlSetClusterSetName
0x140014c82  jmp     short loc_140014CFB
0x140014c84  mov     r8d, r14d
0x140014c87  mov     rdx, rsi
0x140014c8a  mov     rcx, rdi
0x140014c8d  call    DfscFsctrlSpecialSetDc
0x140014c92  jmp     short loc_140014CFB
0x140014c94  mov     r8d, r14d
0x140014c97  mov     rdx, rsi
0x140014c9a  mov     rcx, rdi
0x140014c9d  call    DfscFsctrlSetDomainNameDns
0x140014ca2  jmp     short loc_140014CFB
0x140014ca4  mov     r8d, r14d
0x140014ca7  mov     rdx, rsi
0x140014caa  mov     rcx, rdi
0x140014cad  call    DfscFsctrlSetDomainNameFlat
0x140014cb2  jmp     short loc_140014CFB
0x140014cb4  mov     r8d, r14d
0x140014cb7  mov     rdx, rsi
0x140014cba  mov     rcx, rdi
0x140014cbd  call    DfscFsctrlFlushDomainCache
0x140014cc2  jmp     short loc_140014CFB
0x140014cc4  sub     ecx, 6A010h
0x140014cca  jz      short loc_140014CED
0x140014ccc  sub     ecx, 25FF0h
0x140014cd2  jz      short loc_140014CE6
0x140014cd4  sub     ecx, 4
0x140014cd7  jz      short loc_140014CE6
0x140014cd9  sub     ecx, 4
0x140014cdc  jz      short loc_140014CE6
0x140014cde  sub     ecx, 4
0x140014ce1  jz      short loc_140014CE6
0x140014ce3  sub     ecx, 4
0x140014ce6  mov     ebx, 0C0000010h
0x140014ceb  jmp     short loc_140014CFD
0x140014ced  mov     r8d, r14d
0x140014cf0  mov     rdx, rsi
0x140014cf3  mov     rcx, rdi
0x140014cf6  call    DfscFsctrlFlushClusterSetCache
0x140014cfb  mov     ebx, eax
0x140014cfd  xor     edx, edx; PriorityBoost
0x140014cff  mov     [rdi+30h], ebx
0x140014d02  mov     rcx, rdi; Irp
0x140014d05  call    cs:__imp_IofCompleteRequest
0x140014d0c  nop     dword ptr [rax+rax+00h]
0x140014d11  mov     rsi, [rsp+30h+arg_18]
0x140014d16  mov     eax, ebx
0x140014d18  mov     rbx, [rsp+30h+arg_0]
0x140014d1d  add     rsp, 30h
0x140014d21  pop     r14
0x140014d23  pop     rdi
0x140014d24  pop     rbp
0x140014d25  retn
```
