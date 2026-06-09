# FveLogGenericErrorDatum

- ea: `0x1400b5408`
- end: `0x1400b59f1`
- name: `FveLogGenericErrorDatum`
- size: `1513`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14009f0f0`

## callees

- `0x140001008`
- `0x1400010ac`
- `0x140001114`
- `0x14000a540`
- `0x14000c9ec`
- `0x140022bf0`
- `0x1400b5408`
- `0x1400b6a88`

## import_xrefs

- `ntoskrnl!KeAreAllApcsDisabled` at `0x1400b5488`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x1400b5488`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x1400b54a5`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x1400b54a5`
- `ntoskrnl!EtwWrite` at `0x1400b58bb`
- `ntoskrnl!EtwWrite` at `0x1400b58bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b59bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b59bb`

## pseudocode

```c
__int64 __fastcall FveLogGenericErrorDatum(__int64 a1, unsigned int *a2)
{
  int MustBe; // edi
  __int64 *v5; // rbx
  __int64 v6; // r15
  __int64 v7; // r8
  __int64 v8; // r9
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  unsigned int v35; // eax
  unsigned int v36; // eax
  unsigned int v37; // eax
  NTSTATUS v38; // eax
  int v39; // ecx
  __int16 v41; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING DosName; // [rsp+38h] [rbp-C8h] BYREF
  int v43; // [rsp+48h] [rbp-B8h] BYREF
  int v44; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v45; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v46; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v47; // [rsp+58h] [rbp-A8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *Buffer; // [rsp+70h] [rbp-90h]
  int MaximumLength; // [rsp+78h] [rbp-88h]
  int v51; // [rsp+7Ch] [rbp-84h]
  int *v52; // [rsp+80h] [rbp-80h]
  __int64 v53; // [rsp+88h] [rbp-78h]
  unsigned int *v54; // [rsp+90h] [rbp-70h]
  __int64 v55; // [rsp+98h] [rbp-68h]
  unsigned int *v56; // [rsp+A0h] [rbp-60h]
  __int64 v57; // [rsp+A8h] [rbp-58h]
  unsigned int *v58; // [rsp+B0h] [rbp-50h]
  __int64 v59; // [rsp+B8h] [rbp-48h]
  struct _EVENT_DATA_DESCRIPTOR v60; // [rsp+C0h] [rbp-40h] BYREF
  char v61[16]; // [rsp+E0h] [rbp-20h] BYREF
  int *v62; // [rsp+F0h] [rbp-10h]
  __int64 v63; // [rsp+F8h] [rbp-8h]
  unsigned int *v64; // [rsp+100h] [rbp+0h]
  __int64 v65; // [rsp+108h] [rbp+8h]
  unsigned int *v66; // [rsp+110h] [rbp+10h]
  __int64 v67; // [rsp+118h] [rbp+18h]
  unsigned int *v68; // [rsp+120h] [rbp+20h]
  __int64 v69; // [rsp+128h] [rbp+28h]
  unsigned int *v70; // [rsp+130h] [rbp+30h]
  __int64 v71; // [rsp+138h] [rbp+38h]

  *(_QWORD *)&DosName.Length = 0x20000;
  v41 = 0;
  DosName.Buffer = (wchar_t *)&v41;
  v43 = 0;
  MustBe = 0;
  v5 = 0;
  if ( a1 )
  {
    v6 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 8LL);
    if ( v6 )
    {
      if ( *(_QWORD *)(v6 + 88) )
      {
        if ( !KeAreAllApcsDisabled() && IoVolumeDeviceToDosName(*(PVOID *)(*(_QWORD *)(a1 + 64) + 120LL), &DosName) < 0 )
        {
          *(_DWORD *)&DosName.Length = 0x20000;
          DosName.Buffer = (wchar_t *)&v41;
        }
        MustBe = FveDatumMustBe(a2, 11, v7, v8);
        if ( MustBe >= 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            WPP_SF_LLL(
              WPP_GLOBAL_Control->AttachedDevice,
              30,
              WPP_303a4b105747300cb5f16433e0e95a1e_Traceguids,
              a2[2],
              a2[12],
              a2[3]);
          }
          v9 = a2[2];
          if ( v9 > 0x40000 )
            goto LABEL_102;
          if ( v9 == 0x40000 )
          {
            v5 = FVE_KEYRING_DEBUGGER_ENABLED;
            goto LABEL_103;
          }
          if ( v9 <= 0x17 )
          {
            if ( v9 == 23 )
            {
              v5 = FVE_KEYRING_DEVICE_LOCKOUT_MISMATCH;
              goto LABEL_103;
            }
            if ( v9 <= 0xA )
            {
              if ( v9 == 10 )
              {
                v5 = FVE_KEYRING_PIN_INVALID;
                goto LABEL_103;
              }
              if ( v9 > 5 )
              {
                v13 = v9 - 6;
                if ( !v13 )
                {
                  v5 = FVE_KEYRING_INVALID_APPLICATION;
                  goto LABEL_103;
                }
                v14 = v13 - 1;
                if ( !v14 )
                {
                  v5 = FVE_KEYRING_INVALID_CONFIG;
                  goto LABEL_103;
                }
                v15 = v14 - 1;
                if ( !v15 )
                {
                  v5 = FVE_KEYRING_KEYFILE_NO_VMK;
                  goto LABEL_103;
                }
                if ( v15 == 1 )
                {
                  v5 = FVE_KEYRING_TPM_NO_VMK;
                  goto LABEL_103;
                }
              }
              else
              {
                if ( v9 == 5 )
                {
                  v5 = FVE_KEYRING_TPM_INVALID_PCR;
                  goto LABEL_103;
                }
                if ( !v9 )
                {
                  v5 = FVE_KEYRING_GOT_KEY;
                  goto LABEL_103;
                }
                v10 = v9 - 1;
                if ( !v10 )
                {
                  v5 = FVE_KEYRING_KEYFILE_CORRUPT;
                  goto LABEL_103;
                }
                v11 = v10 - 1;
                if ( !v11 )
                {
                  v5 = FVE_KEYRING_KEYFILE_NOT_FOUND;
                  goto LABEL_103;
                }
                v12 = v11 - 1;
                if ( !v12 )
                {
                  v5 = FVE_KEYRING_TPM_DISABLED;
                  goto LABEL_103;
                }
                if ( v12 == 1 )
                {
                  v5 = (__int64 *)&FVE_KEYRING_TPM_INVALID_SRK;
LABEL_103:
                  *(_QWORD *)&UserData.Size = 4;
                  UserData.Ptr = (ULONGLONG)(a2 + 3);
                  Buffer = DosName.Buffer;
                  MaximumLength = DosName.MaximumLength;
                  v52 = &v43;
                  v54 = a2 + 4;
                  v56 = a2 + 8;
                  v58 = a2 + 12;
                  v51 = 0;
                  v53 = 4;
                  v55 = 16;
                  v57 = 16;
                  v59 = 4;
                  v38 = EtwWrite(*(_QWORD *)(v6 + 88), (PCEVENT_DESCRIPTOR)v5, 0, 6u, &UserData);
                  goto LABEL_104;
                }
              }
LABEL_102:
              v5 = FVE_KEYRING_UNEXPECTED;
              goto LABEL_103;
            }
            if ( v9 > 0x12 )
            {
              v20 = v9 - 19;
              if ( !v20 )
              {
                v5 = FVE_KEYRING_RECOVERY_PASSWORD_USED;
                goto LABEL_103;
              }
              v21 = v20 - 1;
              if ( !v21 )
              {
                v5 = FVE_KEYRING_SECUREBOOT_DISABLED;
                goto LABEL_103;
              }
              v22 = v21 - 1;
              if ( !v22 )
              {
                v5 = FVE_KEYRING_SECUREBOOT_CONFIG_CHANGE;
                goto LABEL_103;
              }
              if ( v22 == 1 )
              {
                v5 = FVE_KEYRING_DEVICE_LOCKEDOUT;
                goto LABEL_103;
              }
              goto LABEL_102;
            }
            if ( v9 == 18 )
            {
              v5 = FVE_KEYRING_PASSWORD_USED;
              goto LABEL_103;
            }
            v16 = v9 - 11;
            if ( !v16 )
            {
              v5 = FVE_KEYRING_PASSWORD_INVALID;
              goto LABEL_103;
            }
            v17 = v16 - 2;
            if ( v17 )
            {
              v18 = v17 - 2;
              if ( !v18 )
              {
                v5 = FVE_KEYRING_ENH_PIN_INVALID;
                goto LABEL_103;
              }
              v19 = v18 - 1;
              if ( !v19 )
              {
                v5 = FVE_KEYRING_NKP_INVALID;
                goto LABEL_103;
              }
              if ( v19 == 1 )
              {
                v5 = FVE_KEYRING_PASSPHRASE_INVALID;
                goto LABEL_103;
              }
              goto LABEL_102;
            }
LABEL_82:
            v5 = FVE_KEYRING_MOR_FAILED;
            goto LABEL_103;
          }
          if ( v9 <= 0x2F )
          {
            if ( v9 == 47 )
            {
              v5 = FVE_KEYRING_MATCHING_PCRS_TPM_FAILURE;
              goto LABEL_103;
            }
            if ( v9 <= 0x1D )
            {
              if ( v9 == 29 )
              {
                v5 = FVE_KEYRING_NKP_SEND_REQUEST;
                goto LABEL_103;
              }
              v23 = v9 - 24;
              if ( !v23 )
              {
                v5 = FVE_KEYRING_UNSEAL_BY_TPM;
                goto LABEL_103;
              }
              v24 = v23 - 1;
              if ( !v24 )
              {
                v5 = FVE_KEYRING_NO_VMK_FROM_NBP;
                goto LABEL_103;
              }
              v25 = v24 - 1;
              if ( !v25 )
              {
                v5 = FVE_KEYRING_NKP_GET_PROTOCOL_HANDLE;
                goto LABEL_103;
              }
              v26 = v25 - 1;
              if ( !v26 )
              {
                v5 = FVE_KEYRING_NKP_REQUEST_IP_ADDRESS;
                goto LABEL_103;
              }
              if ( v26 == 1 )
              {
                v5 = FVE_KEYRING_NKP_CREATE_REQUEST;
                goto LABEL_103;
              }
              goto LABEL_102;
            }
            v27 = v9 - 30;
            if ( !v27 )
            {
              v5 = FVE_KEYRING_NKP_PARSE_RESPONSE;
              goto LABEL_103;
            }
            v28 = v27 - 3;
            if ( v28 )
            {
              v29 = v28 - 11;
              if ( !v29 )
              {
                v5 = FVE_KEYRING_GENERAL_TPM_FAILURE;
                goto LABEL_103;
              }
              if ( v29 == 1 )
              {
                v5 = FVE_KEYRING_TPMPV2_USED;
                goto LABEL_103;
              }
              goto LABEL_102;
            }
            goto LABEL_82;
          }
          v30 = v9 - 48;
          if ( !v30 )
          {
            v5 = FVE_KEYRING_TPM_NONEXISTENT;
            goto LABEL_103;
          }
          v31 = v30 - 1;
          if ( !v31 )
          {
            v5 = FVE_KEYRING_TPMPV2_USED_FAILURE;
            goto LABEL_103;
          }
          v32 = v31 - 3;
          if ( !v32 )
          {
            v5 = (__int64 *)&FVE_KEYRING_BOOT_UNLOCK_SUCCESS;
            v38 = FveLogUnlockSuccess(v6, a2, &DosName, 6);
LABEL_104:
            MustBe = v38;
            goto LABEL_105;
          }
          v33 = v32 - 1;
          if ( !v33 )
          {
            v5 = FVE_KEYRING_CLEAR_KEY_ERROR;
            goto LABEL_103;
          }
          v34 = v33 - 1;
          if ( !v34 )
          {
            v5 = FVE_NKP_NETWORK_CONNECT_ERROR;
            goto LABEL_103;
          }
          v35 = v34 - 1;
          if ( v35 )
          {
            v36 = v35 - 1;
            if ( v36 )
            {
              v37 = v36 - 1;
              if ( v37 )
              {
                if ( v37 == 1 )
                {
                  v5 = FVE_KEYRING_WIM_BCD_MISMATCH;
                  goto LABEL_103;
                }
                goto LABEL_102;
              }
            }
          }
          v5 = FVE_KEYRING_UNEXPECTED;
        }
      }
    }
  }
LABEL_105:
  if ( a2 && (unsigned int)dword_140046040 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140046040, 0x400000000000LL) )
  {
    tlgCreate1Sz_wchar_t(&v61, DosName.Buffer);
    v39 = *(unsigned __int16 *)v5;
    v62 = &v44;
    v44 = v39;
    v64 = a2 + 4;
    v45 = a2[2];
    v63 = 4;
    v66 = &v45;
    v46 = a2[12];
    v68 = &v46;
    v47 = a2[3];
    v70 = &v47;
    v65 = 16;
    v67 = 4;
    v69 = 4;
    v71 = 4;
    tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140046040, (unsigned __int8 *)word_14003D182, 0, 0, 8u, &v60);
  }
  if ( (__int16 *)DosName.Buffer != &v41 )
    ExFreePoolWithTag(DosName.Buffer, 0);
  return (unsigned int)MustBe;
}

```

## disassembly

```asm
0x1400b5408  mov     [rsp-8+arg_10], rbx
0x1400b540d  push    rbp
0x1400b540e  push    rsi
0x1400b540f  push    rdi
0x1400b5410  push    r12
0x1400b5412  push    r13
0x1400b5414  push    r14
0x1400b5416  push    r15
0x1400b5418  lea     rbp, [rsp-50h]
0x1400b541d  sub     rsp, 150h
0x1400b5424  mov     rax, cs:__security_cookie
0x1400b542b  xor     rax, rsp
0x1400b542e  mov     [rbp+80h+var_40], rax
0x1400b5432  xor     r12d, r12d
0x1400b5435  mov     qword ptr [rsp+180h+DosName.Length], 20000h
0x1400b543e  mov     [rsp+180h+var_150], r12w
0x1400b5444  lea     rax, [rsp+180h+var_150]
0x1400b5449  mov     [rsp+180h+DosName.Buffer], rax
0x1400b544e  mov     r14, rdx
0x1400b5451  mov     [rsp+180h+var_138], r12d
0x1400b5456  mov     rsi, rcx
0x1400b5459  lea     r13d, [r12+2]
0x1400b545e  mov     edi, r12d
0x1400b5461  mov     ebx, r12d
0x1400b5464  test    rcx, rcx
0x1400b5467  jz      loc_1400B58C9
0x1400b546d  mov     rax, [rcx+40h]
0x1400b5471  mov     r15, [rax+8]
0x1400b5475  test    r15, r15
0x1400b5478  jz      loc_1400B58C9
0x1400b547e  cmp     [r15+58h], r12
0x1400b5482  jz      loc_1400B58C9
0x1400b5488  call    cs:__imp_KeAreAllApcsDisabled
0x1400b548f  nop     dword ptr [rax+rax+00h]
0x1400b5494  test    al, al
0x1400b5496  jnz     short loc_1400B54C7
0x1400b5498  mov     rcx, [rsi+40h]
0x1400b549c  lea     rdx, [rsp+180h+DosName]; DosName
0x1400b54a1  mov     rcx, [rcx+78h]; VolumeDeviceObject
0x1400b54a5  call    cs:__imp_IoVolumeDeviceToDosName
0x1400b54ac  nop     dword ptr [rax+rax+00h]
0x1400b54b1  test    eax, eax
0x1400b54b3  jns     short loc_1400B54C7
0x1400b54b5  lea     rax, [rsp+180h+var_150]
0x1400b54ba  mov     dword ptr [rsp+180h+DosName.Length], 20000h
0x1400b54c2  mov     [rsp+180h+DosName.Buffer], rax
0x1400b54c7  mov     edx, 0Bh
0x1400b54cc  mov     rcx, r14
0x1400b54cf  call    FveDatumMustBe
0x1400b54d4  mov     edi, eax
0x1400b54d6  test    eax, eax
0x1400b54d8  js      loc_1400B58C9
0x1400b54de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b54e5  lea     rax, WPP_GLOBAL_Control
0x1400b54ec  cmp     rcx, rax
0x1400b54ef  jz      short loc_1400B5529
0x1400b54f1  test    dword ptr [rcx+2Ch], 8000h
0x1400b54f8  jz      short loc_1400B5529
0x1400b54fa  cmp     byte ptr [rcx+29h], 5
0x1400b54fe  jb      short loc_1400B5529
0x1400b5500  mov     eax, [r14+0Ch]
0x1400b5504  lea     r8, WPP_303a4b105747300cb5f16433e0e95a1e_Traceguids
0x1400b550b  mov     r9d, [r14+8]
0x1400b550f  mov     edx, 1Eh
0x1400b5514  mov     rcx, [rcx+18h]
0x1400b5518  mov     dword ptr [rsp+180h+var_158], eax
0x1400b551c  mov     eax, [r14+30h]
0x1400b5520  mov     dword ptr [rsp+180h+UserData], eax
0x1400b5524  call    WPP_SF_LLL
0x1400b5529  mov     eax, [r14+8]
0x1400b552d  mov     ecx, 40000h
0x1400b5532  mov     r9d, 6; UserDataCount
0x1400b5538  cmp     eax, ecx
0x1400b553a  ja      loc_1400B5835
0x1400b5540  jz      loc_1400B582C
0x1400b5546  cmp     eax, 17h
0x1400b5549  ja      loc_1400B56DB
0x1400b554f  jz      loc_1400B56CF
0x1400b5555  cmp     eax, 0Ah
0x1400b5558  ja      loc_1400B5623
0x1400b555e  jz      loc_1400B5617
0x1400b5564  cmp     eax, 5
0x1400b5567  ja      short loc_1400B55CF
0x1400b5569  jz      short loc_1400B55C3
0x1400b556b  test    eax, eax
0x1400b556d  jz      short loc_1400B55B7
0x1400b556f  sub     eax, 1
0x1400b5572  jz      short loc_1400B55AB
0x1400b5574  sub     eax, 1
0x1400b5577  jz      short loc_1400B559F
0x1400b5579  sub     eax, 1
0x1400b557c  jz      short loc_1400B5593
0x1400b557e  cmp     eax, 1
0x1400b5581  jnz     loc_1400B5835
0x1400b5587  lea     rbx, FVE_KEYRING_TPM_INVALID_SRK
0x1400b558e  jmp     loc_1400B583C
0x1400b5593  lea     rbx, FVE_KEYRING_TPM_DISABLED
0x1400b559a  jmp     loc_1400B583C
0x1400b559f  lea     rbx, FVE_KEYRING_KEYFILE_NOT_FOUND
0x1400b55a6  jmp     loc_1400B583C
0x1400b55ab  lea     rbx, FVE_KEYRING_KEYFILE_CORRUPT
0x1400b55b2  jmp     loc_1400B583C
0x1400b55b7  lea     rbx, FVE_KEYRING_GOT_KEY
0x1400b55be  jmp     loc_1400B583C
0x1400b55c3  lea     rbx, FVE_KEYRING_TPM_INVALID_PCR
0x1400b55ca  jmp     loc_1400B583C
0x1400b55cf  sub     eax, r9d
0x1400b55d2  jz      short loc_1400B560B
0x1400b55d4  sub     eax, 1
0x1400b55d7  jz      short loc_1400B55FF
0x1400b55d9  sub     eax, 1
0x1400b55dc  jz      short loc_1400B55F3
0x1400b55de  cmp     eax, 1
0x1400b55e1  jnz     loc_1400B5835
0x1400b55e7  lea     rbx, FVE_KEYRING_TPM_NO_VMK
0x1400b55ee  jmp     loc_1400B583C
0x1400b55f3  lea     rbx, FVE_KEYRING_KEYFILE_NO_VMK
0x1400b55fa  jmp     loc_1400B583C
0x1400b55ff  lea     rbx, FVE_KEYRING_INVALID_CONFIG
0x1400b5606  jmp     loc_1400B583C
0x1400b560b  lea     rbx, FVE_KEYRING_INVALID_APPLICATION
0x1400b5612  jmp     loc_1400B583C
0x1400b5617  lea     rbx, FVE_KEYRING_PIN_INVALID
0x1400b561e  jmp     loc_1400B583C
0x1400b5623  cmp     eax, 12h
0x1400b5626  ja      short loc_1400B5687
0x1400b5628  jz      short loc_1400B567B
0x1400b562a  sub     eax, 0Bh
0x1400b562d  jz      short loc_1400B566F
0x1400b562f  sub     eax, r13d
0x1400b5632  jz      loc_1400B5786
0x1400b5638  sub     eax, r13d
0x1400b563b  jz      short loc_1400B5663
0x1400b563d  sub     eax, 1
0x1400b5640  jz      short loc_1400B5657
0x1400b5642  cmp     eax, 1
0x1400b5645  jnz     loc_1400B5835
0x1400b564b  lea     rbx, FVE_KEYRING_PASSPHRASE_INVALID
0x1400b5652  jmp     loc_1400B583C
0x1400b5657  lea     rbx, FVE_KEYRING_NKP_INVALID
0x1400b565e  jmp     loc_1400B583C
0x1400b5663  lea     rbx, FVE_KEYRING_ENH_PIN_INVALID
0x1400b566a  jmp     loc_1400B583C
0x1400b566f  lea     rbx, FVE_KEYRING_PASSWORD_INVALID
0x1400b5676  jmp     loc_1400B583C
0x1400b567b  lea     rbx, FVE_KEYRING_PASSWORD_USED
0x1400b5682  jmp     loc_1400B583C
0x1400b5687  sub     eax, 13h
0x1400b568a  jz      short loc_1400B56C3
0x1400b568c  sub     eax, 1
0x1400b568f  jz      short loc_1400B56B7
0x1400b5691  sub     eax, 1
0x1400b5694  jz      short loc_1400B56AB
0x1400b5696  cmp     eax, 1
0x1400b5699  jnz     loc_1400B5835
0x1400b569f  lea     rbx, FVE_KEYRING_DEVICE_LOCKEDOUT
0x1400b56a6  jmp     loc_1400B583C
0x1400b56ab  lea     rbx, FVE_KEYRING_SECUREBOOT_CONFIG_CHANGE
0x1400b56b2  jmp     loc_1400B583C
0x1400b56b7  lea     rbx, FVE_KEYRING_SECUREBOOT_DISABLED
0x1400b56be  jmp     loc_1400B583C
0x1400b56c3  lea     rbx, FVE_KEYRING_RECOVERY_PASSWORD_USED
0x1400b56ca  jmp     loc_1400B583C
0x1400b56cf  lea     rbx, FVE_KEYRING_DEVICE_LOCKOUT_MISMATCH
0x1400b56d6  jmp     loc_1400B583C
0x1400b56db  cmp     eax, 2Fh ; '/'
0x1400b56de  ja      loc_1400B57AA
0x1400b56e4  jz      loc_1400B579E
0x1400b56ea  cmp     eax, 1Dh
0x1400b56ed  ja      short loc_1400B5756
0x1400b56ef  jz      short loc_1400B574A
0x1400b56f1  sub     eax, 18h
0x1400b56f4  jz      short loc_1400B573E
0x1400b56f6  sub     eax, 1
0x1400b56f9  jz      short loc_1400B5732
0x1400b56fb  sub     eax, 1
0x1400b56fe  jz      short loc_1400B5726
0x1400b5700  sub     eax, 1
0x1400b5703  jz      short loc_1400B571A
0x1400b5705  cmp     eax, 1
0x1400b5708  jnz     loc_1400B5835
0x1400b570e  lea     rbx, FVE_KEYRING_NKP_CREATE_REQUEST
0x1400b5715  jmp     loc_1400B583C
0x1400b571a  lea     rbx, FVE_KEYRING_NKP_REQUEST_IP_ADDRESS
0x1400b5721  jmp     loc_1400B583C
0x1400b5726  lea     rbx, FVE_KEYRING_NKP_GET_PROTOCOL_HANDLE
0x1400b572d  jmp     loc_1400B583C
0x1400b5732  lea     rbx, FVE_KEYRING_NO_VMK_FROM_NBP
0x1400b5739  jmp     loc_1400B583C
0x1400b573e  lea     rbx, FVE_KEYRING_UNSEAL_BY_TPM
0x1400b5745  jmp     loc_1400B583C
0x1400b574a  lea     rbx, FVE_KEYRING_NKP_SEND_REQUEST
0x1400b5751  jmp     loc_1400B583C
0x1400b5756  sub     eax, 1Eh
0x1400b5759  jz      short loc_1400B5792
0x1400b575b  sub     eax, 3
0x1400b575e  jz      short loc_1400B5786
0x1400b5760  sub     eax, 0Bh
0x1400b5763  jz      short loc_1400B577A
0x1400b5765  cmp     eax, 1
0x1400b5768  jnz     loc_1400B5835
0x1400b576e  lea     rbx, FVE_KEYRING_TPMPV2_USED
0x1400b5775  jmp     loc_1400B583C
0x1400b577a  lea     rbx, FVE_KEYRING_GENERAL_TPM_FAILURE
0x1400b5781  jmp     loc_1400B583C
0x1400b5786  lea     rbx, FVE_KEYRING_MOR_FAILED
0x1400b578d  jmp     loc_1400B583C
0x1400b5792  lea     rbx, FVE_KEYRING_NKP_PARSE_RESPONSE
0x1400b5799  jmp     loc_1400B583C
0x1400b579e  lea     rbx, FVE_KEYRING_MATCHING_PCRS_TPM_FAILURE
0x1400b57a5  jmp     loc_1400B583C
0x1400b57aa  sub     eax, 30h ; '0'
0x1400b57ad  jz      short loc_1400B5823
0x1400b57af  sub     eax, 1
0x1400b57b2  jz      short loc_1400B581A
0x1400b57b4  sub     eax, 3
0x1400b57b7  jz      short loc_1400B57FE
0x1400b57b9  sub     eax, 1
0x1400b57bc  jz      short loc_1400B57F5
0x1400b57be  sub     eax, 1
0x1400b57c1  jz      short loc_1400B57EC
0x1400b57c3  sub     eax, 1
0x1400b57c6  jz      short loc_1400B57E0
0x1400b57c8  sub     eax, 1
0x1400b57cb  jz      short loc_1400B57E0
0x1400b57cd  sub     eax, 1
0x1400b57d0  jz      short loc_1400B57E0
0x1400b57d2  cmp     eax, 1
0x1400b57d5  jnz     short loc_1400B5835
0x1400b57d7  lea     rbx, FVE_KEYRING_WIM_BCD_MISMATCH
0x1400b57de  jmp     short loc_1400B583C
0x1400b57e0  lea     rbx, FVE_KEYRING_UNEXPECTED
0x1400b57e7  jmp     loc_1400B58C9
0x1400b57ec  lea     rbx, FVE_NKP_NETWORK_CONNECT_ERROR
0x1400b57f3  jmp     short loc_1400B583C
0x1400b57f5  lea     rbx, FVE_KEYRING_CLEAR_KEY_ERROR
0x1400b57fc  jmp     short loc_1400B583C
0x1400b57fe  lea     r8, [rsp+180h+DosName]
0x1400b5803  mov     rdx, r14
0x1400b5806  mov     rcx, r15
0x1400b5809  lea     rbx, FVE_KEYRING_BOOT_UNLOCK_SUCCESS
0x1400b5810  call    FveLogUnlockSuccess
0x1400b5815  jmp     loc_1400B58C7
0x1400b581a  lea     rbx, FVE_KEYRING_TPMPV2_USED_FAILURE
0x1400b5821  jmp     short loc_1400B583C
0x1400b5823  lea     rbx, FVE_KEYRING_TPM_NONEXISTENT
0x1400b582a  jmp     short loc_1400B583C
0x1400b582c  lea     rbx, FVE_KEYRING_DEBUGGER_ENABLED
0x1400b5833  jmp     short loc_1400B583C
0x1400b5835  lea     rbx, FVE_KEYRING_UNEXPECTED
0x1400b583c  lea     rax, [r14+0Ch]
0x1400b5840  mov     qword ptr [rsp+180h+var_120.Size], 4
0x1400b5849  mov     [rsp+180h+var_120.Ptr], rax
0x1400b584e  xor     r8d, r8d; ActivityId
0x1400b5851  mov     rax, [rsp+180h+DosName.Buffer]
0x1400b5856  mov     rdx, rbx; EventDescriptor
0x1400b5859  mov     [rsp+180h+var_110], rax
0x1400b585e  movzx   eax, [rsp+180h+DosName.MaximumLength]
0x1400b5863  mov     [rsp+180h+var_108], eax
0x1400b5867  lea     rax, [rsp+180h+var_138]
0x1400b586c  mov     [rbp+80h+var_100], rax
0x1400b5870  lea     rax, [r14+10h]
0x1400b5874  mov     [rbp+80h+var_F0], rax
0x1400b5878  lea     rax, [r14+20h]
0x1400b587c  mov     [rbp+80h+var_E0], rax
0x1400b5880  lea     rax, [r14+30h]
0x1400b5884  mov     [rbp+80h+var_D0], rax
0x1400b5888  lea     rax, [rsp+180h+var_120]
0x1400b588d  mov     [rsp+180h+var_104], r12d
0x1400b5892  mov     [rbp+80h+var_F8], 4
0x1400b589a  mov     [rbp+80h+var_E8], 10h
0x1400b58a2  mov     [rbp+80h+var_D8], 10h
0x1400b58aa  mov     [rbp+80h+var_C8], 4
0x1400b58b2  mov     rcx, [r15+58h]; RegHandle
0x1400b58b6  mov     [rsp+180h+UserData], rax; UserData
0x1400b58bb  call    cs:__imp_EtwWrite
0x1400b58c2  nop     dword ptr [rax+rax+00h]
0x1400b58c7  mov     edi, eax
0x1400b58c9  test    r14, r14
0x1400b58cc  jz      loc_1400B59AA
0x1400b58d2  mov     eax, cs:dword_140046040
0x1400b58d8  cmp     eax, 4
0x1400b58db  jbe     loc_1400B59AA
0x1400b58e1  mov     rdx, 400000000000h
0x1400b58eb  lea     rcx, dword_140046040
0x1400b58f2  call    _tlgKeywordOn
0x1400b58f7  test    al, al
0x1400b58f9  jz      loc_1400B59AA
0x1400b58ff  mov     rdx, [rsp+180h+DosName.Buffer]
0x1400b5904  lea     rcx, [rbp+80h+var_A0]
0x1400b5908  call    _tlgCreate1Sz_wchar_t
0x1400b590d  movzx   ecx, word ptr [rbx]
0x1400b5910  lea     rax, [rsp+180h+var_134]
0x1400b5915  mov     [rbp+80h+var_90], rax
0x1400b5919  lea     rdx, word_14003D182
0x1400b5920  lea     rax, [r14+10h]
0x1400b5924  mov     [rsp+180h+var_134], ecx
0x1400b5928  mov     [rbp+80h+var_80], rax
0x1400b592c  lea     rcx, dword_140046040
0x1400b5933  mov     eax, [r14+8]
  ... truncated ...
```
