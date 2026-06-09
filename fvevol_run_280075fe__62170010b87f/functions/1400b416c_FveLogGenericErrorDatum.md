# FveLogGenericErrorDatum

- ea: `0x1400b416c`
- end: `0x1400b4717`
- name: `FveLogGenericErrorDatum`
- size: `1451`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14009e1b0`

## callees

- `0x140001008`
- `0x1400010ac`
- `0x14000110c`
- `0x14000a480`
- `0x14000c85c`
- `0x1400218c0`
- `0x1400b416c`
- `0x1400b578c`

## import_xrefs

- `ntoskrnl!KeAreAllApcsDisabled` at `0x1400b41ec`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x1400b41ec`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x1400b4209`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x1400b4209`
- `ntoskrnl!EtwWrite` at `0x1400b45e4`
- `ntoskrnl!EtwWrite` at `0x1400b45e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b46e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b46e1`

## pseudocode

```c
__int64 __fastcall FveLogGenericErrorDatum(__int64 a1, unsigned int *a2)
{
  int MustBe; // esi
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
  unsigned int v38; // eax
  unsigned int v39; // eax
  NTSTATUS v40; // eax
  int v41; // ecx
  __int16 v43; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING DosName; // [rsp+38h] [rbp-C8h] BYREF
  int v45; // [rsp+48h] [rbp-B8h] BYREF
  int v46; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v47; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v48; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v49; // [rsp+58h] [rbp-A8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *Buffer; // [rsp+70h] [rbp-90h]
  int MaximumLength; // [rsp+78h] [rbp-88h]
  int v53; // [rsp+7Ch] [rbp-84h]
  int *v54; // [rsp+80h] [rbp-80h]
  __int64 v55; // [rsp+88h] [rbp-78h]
  unsigned int *v56; // [rsp+90h] [rbp-70h]
  __int64 v57; // [rsp+98h] [rbp-68h]
  unsigned int *v58; // [rsp+A0h] [rbp-60h]
  __int64 v59; // [rsp+A8h] [rbp-58h]
  unsigned int *v60; // [rsp+B0h] [rbp-50h]
  __int64 v61; // [rsp+B8h] [rbp-48h]
  struct _EVENT_DATA_DESCRIPTOR v62; // [rsp+C0h] [rbp-40h] BYREF
  char v63[16]; // [rsp+E0h] [rbp-20h] BYREF
  int *v64; // [rsp+F0h] [rbp-10h]
  __int64 v65; // [rsp+F8h] [rbp-8h]
  unsigned int *v66; // [rsp+100h] [rbp+0h]
  __int64 v67; // [rsp+108h] [rbp+8h]
  unsigned int *v68; // [rsp+110h] [rbp+10h]
  __int64 v69; // [rsp+118h] [rbp+18h]
  unsigned int *v70; // [rsp+120h] [rbp+20h]
  __int64 v71; // [rsp+128h] [rbp+28h]
  unsigned int *v72; // [rsp+130h] [rbp+30h]
  __int64 v73; // [rsp+138h] [rbp+38h]

  *(_QWORD *)&DosName.Length = 0x20000;
  v43 = 0;
  DosName.Buffer = (wchar_t *)&v43;
  v45 = 0;
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
          DosName.Buffer = (wchar_t *)&v43;
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
              WPP_7dbdcd8ecbed33ea741e2ac5e04a7ff4_Traceguids,
              a2[2],
              a2[12],
              a2[3]);
          }
          v9 = a2[2];
          if ( v9 > 0x40000 )
            goto LABEL_93;
          if ( v9 == 0x40000 )
          {
            v5 = FVE_KEYRING_DEBUGGER_ENABLED;
            goto LABEL_94;
          }
          if ( v9 > 0x15 )
          {
            if ( v9 > 0x21 )
            {
              v33 = v9 - 44;
              if ( !v33 )
              {
                v5 = FVE_KEYRING_GENERAL_TPM_FAILURE;
                goto LABEL_94;
              }
              v34 = v33 - 1;
              if ( !v34 )
              {
                v5 = FVE_KEYRING_TPMPV2_USED;
                goto LABEL_94;
              }
              v35 = v34 - 2;
              if ( !v35 )
              {
                v5 = FVE_KEYRING_MATCHING_PCRS_TPM_FAILURE;
                goto LABEL_94;
              }
              v36 = v35 - 1;
              if ( !v36 )
              {
                v5 = FVE_KEYRING_TPM_NONEXISTENT;
                goto LABEL_94;
              }
              v37 = v36 - 1;
              if ( !v37 )
              {
                v5 = FVE_KEYRING_TPMPV2_USED_FAILURE;
                goto LABEL_94;
              }
              v38 = v37 - 3;
              if ( !v38 )
              {
                v5 = (__int64 *)&FVE_KEYRING_BOOT_UNLOCK_SUCCESS;
                v40 = FveLogUnlockSuccess(v6, a2, &DosName);
LABEL_95:
                MustBe = v40;
                goto LABEL_96;
              }
              v39 = v38 - 1;
              if ( !v39 )
              {
                v5 = FVE_KEYRING_CLEAR_KEY_ERROR;
                goto LABEL_94;
              }
              if ( v39 == 1 )
              {
                v5 = FVE_NKP_NETWORK_CONNECT_ERROR;
                goto LABEL_94;
              }
              goto LABEL_93;
            }
            if ( v9 != 33 )
            {
              v25 = v9 - 22;
              if ( !v25 )
              {
                v5 = FVE_KEYRING_DEVICE_LOCKEDOUT;
                goto LABEL_94;
              }
              v26 = v25 - 1;
              if ( !v26 )
              {
                v5 = FVE_KEYRING_DEVICE_LOCKOUT_MISMATCH;
                goto LABEL_94;
              }
              v27 = v26 - 1;
              if ( !v27 )
              {
                v5 = FVE_KEYRING_UNSEAL_BY_TPM;
                goto LABEL_94;
              }
              v28 = v27 - 1;
              if ( !v28 )
              {
                v5 = FVE_KEYRING_NO_VMK_FROM_NBP;
                goto LABEL_94;
              }
              v29 = v28 - 1;
              if ( !v29 )
              {
                v5 = FVE_KEYRING_NKP_GET_PROTOCOL_HANDLE;
                goto LABEL_94;
              }
              v30 = v29 - 1;
              if ( !v30 )
              {
                v5 = FVE_KEYRING_NKP_REQUEST_IP_ADDRESS;
                goto LABEL_94;
              }
              v31 = v30 - 1;
              if ( !v31 )
              {
                v5 = FVE_KEYRING_NKP_CREATE_REQUEST;
                goto LABEL_94;
              }
              v32 = v31 - 1;
              if ( !v32 )
              {
                v5 = FVE_KEYRING_NKP_SEND_REQUEST;
                goto LABEL_94;
              }
              if ( v32 == 1 )
              {
                v5 = FVE_KEYRING_NKP_PARSE_RESPONSE;
                goto LABEL_94;
              }
              goto LABEL_93;
            }
          }
          else
          {
            if ( v9 == 21 )
            {
              v5 = FVE_KEYRING_SECUREBOOT_CONFIG_CHANGE;
              goto LABEL_94;
            }
            if ( v9 <= 9 )
            {
              if ( v9 == 9 )
              {
                v5 = FVE_KEYRING_TPM_NO_VMK;
                goto LABEL_94;
              }
              if ( !v9 )
              {
                v5 = FVE_KEYRING_GOT_KEY;
                goto LABEL_94;
              }
              v10 = v9 - 1;
              if ( !v10 )
              {
                v5 = FVE_KEYRING_KEYFILE_CORRUPT;
                goto LABEL_94;
              }
              v11 = v10 - 1;
              if ( !v11 )
              {
                v5 = FVE_KEYRING_KEYFILE_NOT_FOUND;
                goto LABEL_94;
              }
              v12 = v11 - 1;
              if ( !v12 )
              {
                v5 = FVE_KEYRING_TPM_DISABLED;
                goto LABEL_94;
              }
              v13 = v12 - 1;
              if ( !v13 )
              {
                v5 = FVE_KEYRING_TPM_INVALID_SRK;
                goto LABEL_94;
              }
              v14 = v13 - 1;
              if ( !v14 )
              {
                v5 = FVE_KEYRING_TPM_INVALID_PCR;
                goto LABEL_94;
              }
              v15 = v14 - 1;
              if ( !v15 )
              {
                v5 = FVE_KEYRING_INVALID_APPLICATION;
                goto LABEL_94;
              }
              v16 = v15 - 1;
              if ( !v16 )
              {
                v5 = FVE_KEYRING_INVALID_CONFIG;
                goto LABEL_94;
              }
              if ( v16 == 1 )
              {
                v5 = (__int64 *)&FVE_KEYRING_KEYFILE_NO_VMK;
LABEL_94:
                *(_QWORD *)&UserData.Size = 4;
                UserData.Ptr = (ULONGLONG)(a2 + 3);
                Buffer = DosName.Buffer;
                MaximumLength = DosName.MaximumLength;
                v54 = &v45;
                v56 = a2 + 4;
                v58 = a2 + 8;
                v60 = a2 + 12;
                v53 = 0;
                v55 = 4;
                v57 = 16;
                v59 = 16;
                v61 = 4;
                v40 = EtwWrite(*(_QWORD *)(v6 + 88), (PCEVENT_DESCRIPTOR)v5, 0, 6u, &UserData);
                goto LABEL_95;
              }
LABEL_93:
              v5 = FVE_KEYRING_UNEXPECTED;
              goto LABEL_94;
            }
            v17 = v9 - 10;
            if ( !v17 )
            {
              v5 = FVE_KEYRING_PIN_INVALID;
              goto LABEL_94;
            }
            v18 = v17 - 1;
            if ( !v18 )
            {
              v5 = FVE_KEYRING_PASSWORD_INVALID;
              goto LABEL_94;
            }
            v19 = v18 - 2;
            if ( v19 )
            {
              v20 = v19 - 2;
              if ( !v20 )
              {
                v5 = FVE_KEYRING_ENH_PIN_INVALID;
                goto LABEL_94;
              }
              v21 = v20 - 1;
              if ( !v21 )
              {
                v5 = FVE_KEYRING_NKP_INVALID;
                goto LABEL_94;
              }
              v22 = v21 - 1;
              if ( !v22 )
              {
                v5 = FVE_KEYRING_PASSPHRASE_INVALID;
                goto LABEL_94;
              }
              v23 = v22 - 1;
              if ( !v23 )
              {
                v5 = FVE_KEYRING_PASSWORD_USED;
                goto LABEL_94;
              }
              v24 = v23 - 1;
              if ( !v24 )
              {
                v5 = FVE_KEYRING_RECOVERY_PASSWORD_USED;
                goto LABEL_94;
              }
              if ( v24 == 1 )
              {
                v5 = FVE_KEYRING_SECUREBOOT_DISABLED;
                goto LABEL_94;
              }
              goto LABEL_93;
            }
          }
          v5 = FVE_KEYRING_MOR_FAILED;
          goto LABEL_94;
        }
      }
    }
  }
LABEL_96:
  if ( a2 && (unsigned int)dword_140045040 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140045040, 0x400000000000LL) )
  {
    tlgCreate1Sz_wchar_t(&v63, DosName.Buffer);
    v41 = *(unsigned __int16 *)v5;
    v64 = &v46;
    v46 = v41;
    v66 = a2 + 4;
    v47 = a2[2];
    v65 = 4;
    v68 = &v47;
    v48 = a2[12];
    v70 = &v48;
    v49 = a2[3];
    v72 = &v49;
    v67 = 16;
    v69 = 4;
    v71 = 4;
    v73 = 4;
    tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140045040, (unsigned __int8 *)word_14003C102, 0, 0, 8u, &v62);
  }
  if ( (__int16 *)DosName.Buffer != &v43 )
    ExFreePoolWithTag(DosName.Buffer, 0);
  return (unsigned int)MustBe;
}

```

## disassembly

```asm
0x1400b416c  mov     [rsp-8+arg_10], rbx
0x1400b4171  push    rbp
0x1400b4172  push    rsi
0x1400b4173  push    rdi
0x1400b4174  push    r12
0x1400b4176  push    r13
0x1400b4178  push    r14
0x1400b417a  push    r15
0x1400b417c  lea     rbp, [rsp-50h]
0x1400b4181  sub     rsp, 150h
0x1400b4188  mov     rax, cs:__security_cookie
0x1400b418f  xor     rax, rsp
0x1400b4192  mov     [rbp+80h+var_40], rax
0x1400b4196  xor     r12d, r12d
0x1400b4199  mov     qword ptr [rsp+180h+DosName.Length], 20000h
0x1400b41a2  mov     [rsp+180h+var_150], r12w
0x1400b41a8  lea     rax, [rsp+180h+var_150]
0x1400b41ad  mov     [rsp+180h+DosName.Buffer], rax
0x1400b41b2  mov     rdi, rdx
0x1400b41b5  mov     [rsp+180h+var_138], r12d
0x1400b41ba  mov     r14, rcx
0x1400b41bd  lea     r13d, [r12+2]
0x1400b41c2  mov     esi, r12d
0x1400b41c5  mov     ebx, r12d
0x1400b41c8  test    rcx, rcx
0x1400b41cb  jz      loc_1400B45F2
0x1400b41d1  mov     rax, [rcx+40h]
0x1400b41d5  mov     r15, [rax+8]
0x1400b41d9  test    r15, r15
0x1400b41dc  jz      loc_1400B45F2
0x1400b41e2  cmp     [r15+58h], r12
0x1400b41e6  jz      loc_1400B45F2
0x1400b41ec  call    cs:__imp_KeAreAllApcsDisabled
0x1400b41f3  nop     dword ptr [rax+rax+00h]
0x1400b41f8  test    al, al
0x1400b41fa  jnz     short loc_1400B422B
0x1400b41fc  mov     rcx, [r14+40h]
0x1400b4200  lea     rdx, [rsp+180h+DosName]; DosName
0x1400b4205  mov     rcx, [rcx+78h]; VolumeDeviceObject
0x1400b4209  call    cs:__imp_IoVolumeDeviceToDosName
0x1400b4210  nop     dword ptr [rax+rax+00h]
0x1400b4215  test    eax, eax
0x1400b4217  jns     short loc_1400B422B
0x1400b4219  lea     rax, [rsp+180h+var_150]
0x1400b421e  mov     dword ptr [rsp+180h+DosName.Length], 20000h
0x1400b4226  mov     [rsp+180h+DosName.Buffer], rax
0x1400b422b  mov     edx, 0Bh
0x1400b4230  mov     rcx, rdi
0x1400b4233  call    FveDatumMustBe
0x1400b4238  mov     esi, eax
0x1400b423a  test    eax, eax
0x1400b423c  js      loc_1400B45F2
0x1400b4242  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b4249  lea     rax, WPP_GLOBAL_Control
0x1400b4250  cmp     rcx, rax
0x1400b4253  jz      short loc_1400B428B
0x1400b4255  test    dword ptr [rcx+2Ch], 8000h
0x1400b425c  jz      short loc_1400B428B
0x1400b425e  cmp     byte ptr [rcx+29h], 5
0x1400b4262  jb      short loc_1400B428B
0x1400b4264  mov     eax, [rdi+0Ch]
0x1400b4267  lea     r8, WPP_7dbdcd8ecbed33ea741e2ac5e04a7ff4_Traceguids
0x1400b426e  mov     r9d, [rdi+8]
0x1400b4272  mov     edx, 1Eh
0x1400b4277  mov     rcx, [rcx+18h]
0x1400b427b  mov     dword ptr [rsp+180h+var_158], eax
0x1400b427f  mov     eax, [rdi+30h]
0x1400b4282  mov     dword ptr [rsp+180h+UserData], eax
0x1400b4286  call    WPP_SF_LLL
0x1400b428b  mov     eax, [rdi+8]
0x1400b428e  mov     ecx, 40000h
0x1400b4293  cmp     eax, ecx
0x1400b4295  ja      loc_1400B4558
0x1400b429b  jz      loc_1400B454F
0x1400b42a1  cmp     eax, 15h
0x1400b42a4  ja      loc_1400B4410
0x1400b42aa  jz      loc_1400B4404
0x1400b42b0  cmp     eax, 9
0x1400b42b3  ja      loc_1400B436B
0x1400b42b9  jz      loc_1400B435F
0x1400b42bf  test    eax, eax
0x1400b42c1  jz      loc_1400B4353
0x1400b42c7  sub     eax, 1
0x1400b42ca  jz      short loc_1400B4347
0x1400b42cc  sub     eax, 1
0x1400b42cf  jz      short loc_1400B433B
0x1400b42d1  sub     eax, 1
0x1400b42d4  jz      short loc_1400B432F
0x1400b42d6  sub     eax, 1
0x1400b42d9  jz      short loc_1400B4323
0x1400b42db  sub     eax, 1
0x1400b42de  jz      short loc_1400B4317
0x1400b42e0  sub     eax, 1
0x1400b42e3  jz      short loc_1400B430B
0x1400b42e5  sub     eax, 1
0x1400b42e8  jz      short loc_1400B42FF
0x1400b42ea  cmp     eax, 1
0x1400b42ed  jnz     loc_1400B4558
0x1400b42f3  lea     rbx, FVE_KEYRING_KEYFILE_NO_VMK
0x1400b42fa  jmp     loc_1400B455F
0x1400b42ff  lea     rbx, FVE_KEYRING_INVALID_CONFIG
0x1400b4306  jmp     loc_1400B455F
0x1400b430b  lea     rbx, FVE_KEYRING_INVALID_APPLICATION
0x1400b4312  jmp     loc_1400B455F
0x1400b4317  lea     rbx, FVE_KEYRING_TPM_INVALID_PCR
0x1400b431e  jmp     loc_1400B455F
0x1400b4323  lea     rbx, FVE_KEYRING_TPM_INVALID_SRK
0x1400b432a  jmp     loc_1400B455F
0x1400b432f  lea     rbx, FVE_KEYRING_TPM_DISABLED
0x1400b4336  jmp     loc_1400B455F
0x1400b433b  lea     rbx, FVE_KEYRING_KEYFILE_NOT_FOUND
0x1400b4342  jmp     loc_1400B455F
0x1400b4347  lea     rbx, FVE_KEYRING_KEYFILE_CORRUPT
0x1400b434e  jmp     loc_1400B455F
0x1400b4353  lea     rbx, FVE_KEYRING_GOT_KEY
0x1400b435a  jmp     loc_1400B455F
0x1400b435f  lea     rbx, FVE_KEYRING_TPM_NO_VMK
0x1400b4366  jmp     loc_1400B455F
0x1400b436b  sub     eax, 0Ah
0x1400b436e  jz      loc_1400B43F8
0x1400b4374  sub     eax, 1
0x1400b4377  jz      short loc_1400B43EC
0x1400b4379  sub     eax, r13d
0x1400b437c  jz      loc_1400B44C0
0x1400b4382  sub     eax, r13d
0x1400b4385  jz      short loc_1400B43E0
0x1400b4387  sub     eax, 1
0x1400b438a  jz      short loc_1400B43D4
0x1400b438c  sub     eax, 1
0x1400b438f  jz      short loc_1400B43C8
0x1400b4391  sub     eax, 1
0x1400b4394  jz      short loc_1400B43BC
0x1400b4396  sub     eax, 1
0x1400b4399  jz      short loc_1400B43B0
0x1400b439b  cmp     eax, 1
0x1400b439e  jnz     loc_1400B4558
0x1400b43a4  lea     rbx, FVE_KEYRING_SECUREBOOT_DISABLED
0x1400b43ab  jmp     loc_1400B455F
0x1400b43b0  lea     rbx, FVE_KEYRING_RECOVERY_PASSWORD_USED
0x1400b43b7  jmp     loc_1400B455F
0x1400b43bc  lea     rbx, FVE_KEYRING_PASSWORD_USED
0x1400b43c3  jmp     loc_1400B455F
0x1400b43c8  lea     rbx, FVE_KEYRING_PASSPHRASE_INVALID
0x1400b43cf  jmp     loc_1400B455F
0x1400b43d4  lea     rbx, FVE_KEYRING_NKP_INVALID
0x1400b43db  jmp     loc_1400B455F
0x1400b43e0  lea     rbx, FVE_KEYRING_ENH_PIN_INVALID
0x1400b43e7  jmp     loc_1400B455F
0x1400b43ec  lea     rbx, FVE_KEYRING_PASSWORD_INVALID
0x1400b43f3  jmp     loc_1400B455F
0x1400b43f8  lea     rbx, FVE_KEYRING_PIN_INVALID
0x1400b43ff  jmp     loc_1400B455F
0x1400b4404  lea     rbx, FVE_KEYRING_SECUREBOOT_CONFIG_CHANGE
0x1400b440b  jmp     loc_1400B455F
0x1400b4410  cmp     eax, 21h ; '!'
0x1400b4413  ja      loc_1400B44CC
0x1400b4419  jz      loc_1400B44C0
0x1400b441f  sub     eax, 16h
0x1400b4422  jz      loc_1400B44B4
0x1400b4428  sub     eax, 1
0x1400b442b  jz      short loc_1400B44A8
0x1400b442d  sub     eax, 1
0x1400b4430  jz      short loc_1400B449C
0x1400b4432  sub     eax, 1
0x1400b4435  jz      short loc_1400B4490
0x1400b4437  sub     eax, 1
0x1400b443a  jz      short loc_1400B4484
0x1400b443c  sub     eax, 1
0x1400b443f  jz      short loc_1400B4478
0x1400b4441  sub     eax, 1
0x1400b4444  jz      short loc_1400B446C
0x1400b4446  sub     eax, 1
0x1400b4449  jz      short loc_1400B4460
0x1400b444b  cmp     eax, 1
0x1400b444e  jnz     loc_1400B4558
0x1400b4454  lea     rbx, FVE_KEYRING_NKP_PARSE_RESPONSE
0x1400b445b  jmp     loc_1400B455F
0x1400b4460  lea     rbx, FVE_KEYRING_NKP_SEND_REQUEST
0x1400b4467  jmp     loc_1400B455F
0x1400b446c  lea     rbx, FVE_KEYRING_NKP_CREATE_REQUEST
0x1400b4473  jmp     loc_1400B455F
0x1400b4478  lea     rbx, FVE_KEYRING_NKP_REQUEST_IP_ADDRESS
0x1400b447f  jmp     loc_1400B455F
0x1400b4484  lea     rbx, FVE_KEYRING_NKP_GET_PROTOCOL_HANDLE
0x1400b448b  jmp     loc_1400B455F
0x1400b4490  lea     rbx, FVE_KEYRING_NO_VMK_FROM_NBP
0x1400b4497  jmp     loc_1400B455F
0x1400b449c  lea     rbx, FVE_KEYRING_UNSEAL_BY_TPM
0x1400b44a3  jmp     loc_1400B455F
0x1400b44a8  lea     rbx, FVE_KEYRING_DEVICE_LOCKOUT_MISMATCH
0x1400b44af  jmp     loc_1400B455F
0x1400b44b4  lea     rbx, FVE_KEYRING_DEVICE_LOCKEDOUT
0x1400b44bb  jmp     loc_1400B455F
0x1400b44c0  lea     rbx, FVE_KEYRING_MOR_FAILED
0x1400b44c7  jmp     loc_1400B455F
0x1400b44cc  sub     eax, 2Ch ; ','
0x1400b44cf  jz      short loc_1400B4546
0x1400b44d1  sub     eax, 1
0x1400b44d4  jz      short loc_1400B453D
0x1400b44d6  sub     eax, r13d
0x1400b44d9  jz      short loc_1400B4534
0x1400b44db  sub     eax, 1
0x1400b44de  jz      short loc_1400B452B
0x1400b44e0  sub     eax, 1
0x1400b44e3  jz      short loc_1400B4522
0x1400b44e5  sub     eax, 3
0x1400b44e8  jz      short loc_1400B4506
0x1400b44ea  sub     eax, 1
0x1400b44ed  jz      short loc_1400B44FD
0x1400b44ef  cmp     eax, 1
0x1400b44f2  jnz     short loc_1400B4558
0x1400b44f4  lea     rbx, FVE_NKP_NETWORK_CONNECT_ERROR
0x1400b44fb  jmp     short loc_1400B455F
0x1400b44fd  lea     rbx, FVE_KEYRING_CLEAR_KEY_ERROR
0x1400b4504  jmp     short loc_1400B455F
0x1400b4506  lea     r8, [rsp+180h+DosName]
0x1400b450b  mov     rdx, rdi
0x1400b450e  mov     rcx, r15
0x1400b4511  lea     rbx, FVE_KEYRING_BOOT_UNLOCK_SUCCESS
0x1400b4518  call    FveLogUnlockSuccess
0x1400b451d  jmp     loc_1400B45F0
0x1400b4522  lea     rbx, FVE_KEYRING_TPMPV2_USED_FAILURE
0x1400b4529  jmp     short loc_1400B455F
0x1400b452b  lea     rbx, FVE_KEYRING_TPM_NONEXISTENT
0x1400b4532  jmp     short loc_1400B455F
0x1400b4534  lea     rbx, FVE_KEYRING_MATCHING_PCRS_TPM_FAILURE
0x1400b453b  jmp     short loc_1400B455F
0x1400b453d  lea     rbx, FVE_KEYRING_TPMPV2_USED
0x1400b4544  jmp     short loc_1400B455F
0x1400b4546  lea     rbx, FVE_KEYRING_GENERAL_TPM_FAILURE
0x1400b454d  jmp     short loc_1400B455F
0x1400b454f  lea     rbx, FVE_KEYRING_DEBUGGER_ENABLED
0x1400b4556  jmp     short loc_1400B455F
0x1400b4558  lea     rbx, FVE_KEYRING_UNEXPECTED
0x1400b455f  lea     rax, [rdi+0Ch]
0x1400b4563  mov     qword ptr [rsp+180h+var_120.Size], 4
0x1400b456c  mov     [rsp+180h+var_120.Ptr], rax
0x1400b4571  mov     r9d, 6; UserDataCount
0x1400b4577  mov     rax, [rsp+180h+DosName.Buffer]
0x1400b457c  xor     r8d, r8d; ActivityId
0x1400b457f  mov     [rsp+180h+var_110], rax
0x1400b4584  mov     rdx, rbx; EventDescriptor
0x1400b4587  movzx   eax, [rsp+180h+DosName.MaximumLength]
0x1400b458c  mov     [rsp+180h+var_108], eax
0x1400b4590  lea     rax, [rsp+180h+var_138]
0x1400b4595  mov     [rbp+80h+var_100], rax
0x1400b4599  lea     rax, [rdi+10h]
0x1400b459d  mov     [rbp+80h+var_F0], rax
0x1400b45a1  lea     rax, [rdi+20h]
0x1400b45a5  mov     [rbp+80h+var_E0], rax
0x1400b45a9  lea     rax, [rdi+30h]
0x1400b45ad  mov     [rbp+80h+var_D0], rax
0x1400b45b1  lea     rax, [rsp+180h+var_120]
0x1400b45b6  mov     [rsp+180h+var_104], r12d
0x1400b45bb  mov     [rbp+80h+var_F8], 4
0x1400b45c3  mov     [rbp+80h+var_E8], 10h
0x1400b45cb  mov     [rbp+80h+var_D8], 10h
0x1400b45d3  mov     [rbp+80h+var_C8], 4
0x1400b45db  mov     rcx, [r15+58h]; RegHandle
0x1400b45df  mov     [rsp+180h+UserData], rax; UserData
0x1400b45e4  call    cs:__imp_EtwWrite
0x1400b45eb  nop     dword ptr [rax+rax+00h]
0x1400b45f0  mov     esi, eax
0x1400b45f2  test    rdi, rdi
0x1400b45f5  jz      loc_1400B46D0
0x1400b45fb  mov     eax, cs:dword_140045040
0x1400b4601  cmp     eax, 4
0x1400b4604  jbe     loc_1400B46D0
0x1400b460a  mov     rdx, 400000000000h
0x1400b4614  lea     rcx, dword_140045040
0x1400b461b  call    _tlgKeywordOn
0x1400b4620  test    al, al
0x1400b4622  jz      loc_1400B46D0
0x1400b4628  mov     rdx, [rsp+180h+DosName.Buffer]
0x1400b462d  lea     rcx, [rbp+80h+var_A0]
0x1400b4631  call    _tlgCreate1Sz_wchar_t
0x1400b4636  movzx   ecx, word ptr [rbx]
0x1400b4639  lea     rax, [rsp+180h+var_134]
0x1400b463e  mov     [rbp+80h+var_90], rax
0x1400b4642  lea     rdx, word_14003C102
0x1400b4649  lea     rax, [rdi+10h]
0x1400b464d  mov     [rsp+180h+var_134], ecx
0x1400b4651  mov     [rbp+80h+var_80], rax
0x1400b4655  lea     rcx, dword_140045040
0x1400b465c  mov     eax, [rdi+8]
0x1400b465f  xor     r9d, r9d
0x1400b4662  mov     [rsp+180h+var_130], eax
0x1400b4666  xor     r8d, r8d
0x1400b4669  lea     rax, [rsp+180h+var_130]
0x1400b466e  mov     [rbp+80h+var_88], 4
0x1400b4676  mov     [rbp+80h+var_70], rax
0x1400b467a  mov     eax, [rdi+30h]
0x1400b467d  mov     [rsp+180h+var_12C], eax
0x1400b4681  lea     rax, [rsp+180h+var_12C]
0x1400b4686  mov     [rbp+80h+var_60], rax
0x1400b468a  mov     eax, [rdi+0Ch]
0x1400b468d  mov     [rsp+180h+var_128], eax
0x1400b4691  lea     rax, [rsp+180h+var_128]
0x1400b4696  mov     [rbp+80h+var_50], rax
0x1400b469a  lea     rax, [rbp+80h+var_C0]
  ... truncated ...
```
