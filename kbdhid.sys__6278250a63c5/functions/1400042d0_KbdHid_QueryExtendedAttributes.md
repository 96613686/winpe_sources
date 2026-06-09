# KbdHid_QueryExtendedAttributes

- ea: `0x1400042d0`
- end: `0x140004c12`
- name: `KbdHid_QueryExtendedAttributes`
- size: `2370`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, loader_planting`

## callers

- `0x1400026a0`

## callees

- `0x1400042d0`
- `0x1400052a0`
- `0x140006b70`
- `0x140006c6c`
- `0x140010510`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400044ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004a71`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400044ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004a71`
- `ntoskrnl!ExAllocatePool2` at `0x14000434b`
- `ntoskrnl!ExAllocatePool2` at `0x14000448c`
- `ntoskrnl!ExAllocatePool2` at `0x14000434b`
- `ntoskrnl!ExAllocatePool2` at `0x14000448c`
- `HIDPARSE!HidP_GetUsageValue` at `0x1400045a9`
- `HIDPARSE!HidP_GetUsageValue` at `0x140004642`
- `HIDPARSE!HidP_GetUsageValue` at `0x140004724`
- `HIDPARSE!HidP_GetUsageValue` at `0x1400047e7`
- `HIDPARSE!HidP_GetUsageValue` at `0x1400048aa`
- `HIDPARSE!HidP_GetUsageValue` at `0x140004922`
- `HIDPARSE!HidP_GetUsageValue` at `0x1400045a9`
- `HIDPARSE!HidP_GetUsageValue` at `0x140004642`
- `HIDPARSE!HidP_GetUsageValue` at `0x140004724`
- `HIDPARSE!HidP_GetUsageValue` at `0x1400047e7`
- `HIDPARSE!HidP_GetUsageValue` at `0x1400048aa`
- `HIDPARSE!HidP_GetUsageValue` at `0x140004922`
- `HIDPARSE!HidP_GetValueCaps` at `0x1400043c6`
- `HIDPARSE!HidP_GetValueCaps` at `0x1400043c6`

## pseudocode

```c
__int64 __fastcall KbdHid_QueryExtendedAttributes(__int64 a1)
{
  __int64 v1; // rdi
  __int64 v3; // rcx
  struct _HIDP_VALUE_CAPS *Pool2; // rax
  int v5; // edx
  int v6; // r8d
  struct _HIDP_VALUE_CAPS *v7; // r14
  NTSTATUS ValueCaps; // esi
  ULONG v9; // r15d
  int v10; // edx
  int v11; // r8d
  unsigned int i; // edx
  struct _HIDP_VALUE_CAPS *v13; // rax
  USHORT LinkCollection; // r13
  CHAR ReportID; // si
  CHAR *v16; // rax
  int v17; // edx
  int v18; // r8d
  CHAR *Report; // r12
  int v20; // eax
  NTSTATUS v21; // eax
  int v22; // r9d
  char v23; // dl
  NTSTATUS v24; // eax
  NTSTATUS v25; // eax
  NTSTATUS v26; // eax
  NTSTATUS v27; // eax
  char v28; // dl
  char v29; // di
  char v30; // r11
  char v31; // r10
  int v32; // r9d
  int v33; // r8d
  int v34; // edx
  int UsageValue; // [rsp+28h] [rbp-59h]
  ULONG v37; // [rsp+78h] [rbp-9h] BYREF
  ULONG v38; // [rsp+7Ch] [rbp-5h] BYREF
  ULONG v39; // [rsp+80h] [rbp-1h] BYREF
  PVOID P; // [rsp+88h] [rbp+7h]
  USHORT ValueCapsLength; // [rsp+E8h] [rbp+67h] BYREF
  ULONG v42; // [rsp+F0h] [rbp+6Fh] BYREF
  ULONG v43; // [rsp+F8h] [rbp+77h] BYREF
  ULONG v44; // [rsp+100h] [rbp+7Fh] BYREF

  v1 = *(_QWORD *)(a1 + 112);
  ValueCapsLength = 0;
  v42 = 0;
  v37 = 0;
  v43 = 0;
  v44 = 0;
  v38 = 0;
  v39 = 0;
  if ( *(_WORD *)(v1 + 16) && (v3 = *(unsigned __int16 *)(v1 + 68), (_WORD)v3) )
  {
    ValueCapsLength = *(_WORD *)(v1 + 68);
    Pool2 = (struct _HIDP_VALUE_CAPS *)ExAllocatePool2(64, 72 * v3, 1214538315);
    P = Pool2;
    v7 = Pool2;
    if ( Pool2 )
    {
      v9 = 2;
      ValueCaps = HidP_GetValueCaps(HidP_Feature, Pool2, &ValueCapsLength, *(PHIDP_PREPARSED_DATA *)v1);
      if ( ValueCaps < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_qdd(WPP_GLOBAL_Control->DeviceExtension, v10, v11, 28);
        goto LABEL_21;
      }
      for ( i = 0; i < ValueCapsLength; ++i )
      {
        v13 = &v7[i];
        if ( v13->LinkUsagePage == 12
          && v13->LinkUsage == 704
          && v13->UsagePage == 12
          && v13->IsRange == 1
          && v13->Range.UsageMin <= 0x2C6u
          && v13->Range.UsageMax >= 0x2C1u )
        {
          LinkCollection = v13->LinkCollection;
          ReportID = v13->ReportID;
          v16 = (CHAR *)ExAllocatePool2(64, *(unsigned __int16 *)(v1 + 16), 1214538315);
          Report = v16;
          if ( !v16 )
          {
            ValueCaps = -1073741670;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_qdd(WPP_GLOBAL_Control->DeviceExtension, v17, v18, 30);
            goto LABEL_21;
          }
          *v16 = ReportID;
          UsageValue = (int)v16;
          v20 = KbdHid_CallHidClass(a1, 721298);
          ValueCaps = v20;
          if ( v20 < 0 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_qd(
                WPP_GLOBAL_Control->DeviceExtension,
                2,
                1,
                31,
                (__int64)WPP_98d22518711f34f074bb80910c9ade48_Traceguids,
                *(_QWORD *)a1,
                v20);
            goto LABEL_77;
          }
          v21 = HidP_GetUsageValue(
                  HidP_Feature,
                  0xCu,
                  LinkCollection,
                  0x2C3u,
                  &v42,
                  *(PHIDP_PREPARSED_DATA *)v1,
                  Report,
                  *(unsigned __int16 *)(v1 + 16));
          if ( v21 < 0 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v22 = 32;
              v23 = 3;
              goto LABEL_35;
            }
            goto LABEL_40;
          }
          if ( v42 > 6 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_qd(
                WPP_GLOBAL_Control->DeviceExtension,
                2,
                1,
                33,
                (__int64)WPP_98d22518711f34f074bb80910c9ade48_Traceguids,
                *(_QWORD *)a1,
                v42);
LABEL_39:
            v42 = 0;
            goto LABEL_40;
          }
          if ( v42 != 6 )
            goto LABEL_40;
          v21 = HidP_GetUsageValue(
                  HidP_Feature,
                  0xCu,
                  LinkCollection,
                  0x2C4u,
                  &v37,
                  *(PHIDP_PREPARSED_DATA *)v1,
                  Report,
                  *(unsigned __int16 *)(v1 + 16));
          if ( v21 >= 0 )
          {
            if ( v37 )
              goto LABEL_40;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_qd(
                WPP_GLOBAL_Control->DeviceExtension,
                2,
                1,
                35,
                (__int64)WPP_98d22518711f34f074bb80910c9ade48_Traceguids,
                *(_QWORD *)a1,
                0);
            goto LABEL_39;
          }
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v22 = 34;
            v23 = 2;
LABEL_35:
            WPP_RECORDER_SF_qd(
              WPP_GLOBAL_Control->DeviceExtension,
              v23,
              1,
              v22,
              (__int64)WPP_98d22518711f34f074bb80910c9ade48_Traceguids,
              *(_QWORD *)a1,
              v21);
          }
LABEL_40:
          v24 = HidP_GetUsageValue(
                  HidP_Feature,
                  0xCu,
                  LinkCollection,
                  0x2C1u,
                  &v43,
                  *(PHIDP_PREPARSED_DATA *)v1,
                  Report,
                  *(unsigned __int16 *)(v1 + 16));
          if ( v24 >= 0 )
          {
            if ( v43 > 2 )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                WPP_RECORDER_SF_qd(
                  WPP_GLOBAL_Control->DeviceExtension,
                  2,
                  1,
                  37,
                  (__int64)WPP_98d22518711f34f074bb80910c9ade48_Traceguids,
                  *(_QWORD *)a1,
                  v43);
              v43 = 0;
            }
          }
          else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            WPP_RECORDER_SF_qd(
              WPP_GLOBAL_Control->DeviceExtension,
              3,
              1,
              36,
              (__int64)WPP_98d22518711f34f074bb80910c9ade48_Traceguids,
              *(_QWORD *)a1,
              v24);
          }
          v25 = HidP_GetUsageValue(
                  HidP_Feature,
                  0xCu,
                  LinkCollection,
                  0x2C2u,
                  &v44,
                  *(PHIDP_PREPARSED_DATA *)v1,
                  Report,
                  *(unsigned __int16 *)(v1 + 16));
          if ( v25 >= 0 )
          {
            if ( v44 > 3 )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                WPP_RECORDER_SF_qd(
                  WPP_GLOBAL_Control->DeviceExtension,
                  2,
                  1,
                  39,
                  (__int64)WPP_98d22518711f34f074bb80910c9ade48_Traceguids,
                  *(_QWORD *)a1,
                  v44);
              v44 = 0;
            }
          }
          else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            WPP_RECORDER_SF_qd(
              WPP_GLOBAL_Control->DeviceExtension,
              3,
              1,
              38,
              (__int64)WPP_98d22518711f34f074bb80910c9ade48_Traceguids,
              *(_QWORD *)a1,
              v25);
          }
          v26 = HidP_GetUsageValue(
                  HidP_Feature,
                  0xCu,
                  LinkCollection,
                  0x2C5u,
                  &v38,
                  *(PHIDP_PREPARSED_DATA *)v1,
                  Report,
                  *(unsigned __int16 *)(v1 + 16));
          if ( v26 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_qd(
              WPP_GLOBAL_Control->DeviceExtension,
              3,
              1,
              40,
              (__int64)WPP_98d22518711f34f074bb80910c9ade48_Traceguids,
              *(_QWORD *)a1,
              v26);
          v27 = HidP_GetUsageValue(
                  HidP_Feature,
                  0xCu,
                  LinkCollection,
                  0x2C6u,
                  &v39,
                  *(PHIDP_PREPARSED_DATA *)v1,
                  Report,
                  *(unsigned __int16 *)(v1 + 16));
          if ( v27 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_qd(
              WPP_GLOBAL_Control->DeviceExtension,
              3,
              1,
              41,
              (__int64)WPP_98d22518711f34f074bb80910c9ade48_Traceguids,
              *(_QWORD *)a1,
              v27);
          v28 = *(_BYTE *)(a1 + 280);
          if ( v28 == 4 )
          {
            v9 = 1;
          }
          else if ( *(_BYTE *)(a1 + 280) == 7 )
          {
            v9 = 5;
          }
          else if ( *(_BYTE *)(a1 + 280) != 8 )
          {
            if ( v42 == 1 )
            {
              if ( v28 != 4 )
              {
                *(_WORD *)(a1 + 280) = 4;
                *(_QWORD *)(a1 + 344) = 4;
              }
            }
            else if ( v42 == 2 )
            {
              if ( v28 != 8 )
              {
                *(_WORD *)(a1 + 280) = 1544;
                *(_DWORD *)(a1 + 344) = 8;
                *(_DWORD *)(a1 + 348) = 6;
              }
            }
            else if ( v42 == 5 && v28 != 7 )
            {
              *(_WORD *)(a1 + 280) = 519;
              *(_DWORD *)(a1 + 344) = 7;
              *(_DWORD *)(a1 + 348) = 2;
            }
LABEL_76:
            ValueCaps = 0;
LABEL_77:
            ExFreePoolWithTag(Report, 0);
            goto LABEL_21;
          }
          v42 = v9;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_qd(
              WPP_GLOBAL_Control->DeviceExtension,
              3,
              1,
              42,
              (__int64)WPP_98d22518711f34f074bb80910c9ade48_Traceguids,
              *(_QWORD *)a1,
              v9);
          goto LABEL_76;
        }
      }
      ValueCaps = -1073741275;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_qd(
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          1,
          29,
          (__int64)WPP_98d22518711f34f074bb80910c9ade48_Traceguids,
          *(_QWORD *)a1,
          37);
LABEL_21:
      ExFreePoolWithTag(P, 0);
    }
    else
    {
      ValueCaps = -1073741670;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_qdd(WPP_GLOBAL_Control->DeviceExtension, v5, v6, 27);
    }
  }
  else
  {
    ValueCaps = -1073741637;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_qd(
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        1,
        26,
        (__int64)WPP_98d22518711f34f074bb80910c9ade48_Traceguids,
        *(_QWORD *)a1,
        187);
  }
  v29 = v43;
  v30 = v44;
  v31 = v42;
  v32 = (unsigned __int8)v37;
  v33 = (unsigned __int8)v38;
  v34 = (unsigned __int8)v39;
  *(_BYTE *)(a1 + 309) = v43;
  *(_BYTE *)(a1 + 310) = v30;
  *(_BYTE *)(a1 + 311) = v31;
  *(_BYTE *)(a1 + 312) = v32;
  *(_BYTE *)(a1 + 313) = v33;
  *(_BYTE *)(a1 + 314) = v34;
  *(_BYTE *)(a1 + 308) = 1;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qdddddddd(
      WPP_GLOBAL_Control->DeviceExtension,
      v34,
      v33,
      v32,
      UsageValue,
      *(_QWORD *)a1,
      v29,
      v30,
      v31,
      v32,
      v33,
      v34,
      *(_BYTE *)(a1 + 280),
      *(_BYTE *)(a1 + 281));
  if ( ValueCaps < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qd(
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      1,
      44,
      (__int64)WPP_98d22518711f34f074bb80910c9ade48_Traceguids,
      *(_QWORD *)a1,
      ValueCaps);
  return (unsigned int)ValueCaps;
}

```

## disassembly

```asm
0x1400042d0  mov     rax, rsp
0x1400042d3  push    rbp
0x1400042d4  push    rbx
0x1400042d5  push    rsi
0x1400042d6  push    r13
0x1400042d8  push    r14
0x1400042da  lea     rbp, [rax-5Fh]
0x1400042de  sub     rsp, 0B0h
0x1400042e5  mov     [rax-30h], rdi
0x1400042e9  lea     r13, WPP_98d22518711f34f074bb80910c9ade48_Traceguids
0x1400042f0  mov     rdi, [rcx+70h]
0x1400042f4  mov     rbx, rcx
0x1400042f7  mov     [rax-38h], r12
0x1400042fb  xor     r12d, r12d
0x1400042fe  mov     [rbp+57h+ValueCapsLength], r12w
0x140004303  mov     [rbp+57h+arg_8], r12d
0x140004307  mov     [rbp+57h+var_60], r12d
0x14000430b  mov     [rbp+57h+arg_10], r12d
0x14000430f  mov     [rbp+57h+arg_18], r12d
0x140004313  mov     [rbp+57h+var_5C], r12d
0x140004317  mov     [rbp+57h+var_58], r12d
0x14000431b  cmp     r12w, [rdi+10h]
0x140004320  jz      loc_140004AD1
0x140004326  movzx   ecx, word ptr [rdi+44h]
0x14000432a  cmp     r12w, cx
0x14000432e  jz      loc_140004AD1
0x140004334  lea     rdx, [rcx+rcx*8]
0x140004338  mov     [rbp+57h+ValueCapsLength], cx
0x14000433c  shl     rdx, 3
0x140004340  mov     ecx, 40h ; '@'
0x140004345  mov     r8d, 4864624Bh
0x14000434b  call    cs:__imp_ExAllocatePool2
0x140004352  nop     dword ptr [rax+rax+00h]
0x140004357  mov     [rbp+57h+P], rax
0x14000435b  mov     r14, rax
0x14000435e  test    rax, rax
0x140004361  jnz     short loc_1400043AB
0x140004363  mov     esi, 0C000009Ah
0x140004368  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000436f  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140004376  jz      loc_140004B15
0x14000437c  movzx   eax, [rbp+57h+ValueCapsLength]
0x140004380  mov     r9d, 1Bh
0x140004386  mov     rcx, cs:WPP_GLOBAL_Control
0x14000438d  mov     [rsp+0D0h+ReportLength], esi
0x140004391  mov     dword ptr [rsp+0D0h+Report], eax
0x140004395  mov     rax, [rbx]
0x140004398  mov     rcx, [rcx+40h]
0x14000439c  mov     [rsp+0D0h+PreparsedData], rax
0x1400043a1  call    WPP_RECORDER_SF_qdd
0x1400043a6  jmp     loc_140004B15
0x1400043ab  mov     r9, [rdi]; PreparsedData
0x1400043ae  lea     r8, [rbp+57h+ValueCapsLength]; ValueCapsLength
0x1400043b2  mov     [rsp+0D0h+var_38], r15
0x1400043ba  mov     rdx, r14; ValueCaps
0x1400043bd  mov     r15d, 2
0x1400043c3  mov     ecx, r15d; ReportType
0x1400043c6  call    cs:__imp_HidP_GetValueCaps
0x1400043cd  nop     dword ptr [rax+rax+00h]
0x1400043d2  mov     esi, eax
0x1400043d4  test    eax, eax
0x1400043d6  jns     short loc_14000441B
0x1400043d8  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400043df  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400043e6  jz      loc_1400044E6
0x1400043ec  movzx   ecx, [rbp+57h+ValueCapsLength]
0x1400043f0  mov     r9d, 1Ch
0x1400043f6  mov     [rsp+0D0h+ReportLength], eax
0x1400043fa  mov     dword ptr [rsp+0D0h+Report], ecx
0x1400043fe  mov     rcx, [rbx]
0x140004401  mov     [rsp+0D0h+PreparsedData], rcx
0x140004406  mov     rcx, cs:WPP_GLOBAL_Control
0x14000440d  mov     rcx, [rcx+40h]
0x140004411  call    WPP_RECORDER_SF_qdd
0x140004416  jmp     loc_1400044E6
0x14000441b  mov     edx, r12d
0x14000441e  mov     r8d, 2C0h
0x140004424  mov     r10d, 2C6h
0x14000442a  mov     r9d, 2C1h
0x140004430  movzx   eax, [rbp+57h+ValueCapsLength]
0x140004434  cmp     edx, eax
0x140004436  jnb     loc_140004A82
0x14000443c  mov     eax, edx
0x14000443e  lea     rcx, [rax+rax*8]
0x140004442  cmp     word ptr [r14+rcx*8+0Ah], 0Ch
0x140004449  lea     rax, [r14+rcx*8]
0x14000444d  jnz     short loc_140004470
0x14000444f  cmp     [rax+8], r8w
0x140004454  jnz     short loc_140004470
0x140004456  cmp     word ptr [rax], 0Ch
0x14000445a  jnz     short loc_140004470
0x14000445c  cmp     byte ptr [rax+0Ch], 1
0x140004460  jnz     short loc_140004470
0x140004462  cmp     [rax+38h], r10w
0x140004467  ja      short loc_140004470
0x140004469  cmp     [rax+3Ah], r9w
0x14000446e  jnb     short loc_140004474
0x140004470  inc     edx
0x140004472  jmp     short loc_140004430
0x140004474  movzx   edx, word ptr [rdi+10h]
0x140004478  mov     ecx, 40h ; '@'
0x14000447d  movzx   r13d, word ptr [rax+6]
0x140004482  mov     r8d, 4864624Bh
0x140004488  movzx   esi, byte ptr [rax+2]
0x14000448c  call    cs:__imp_ExAllocatePool2
0x140004493  nop     dword ptr [rax+rax+00h]
0x140004498  mov     r12, rax
0x14000449b  test    rax, rax
0x14000449e  jnz     short loc_140004505
0x1400044a0  mov     esi, 0C000009Ah
0x1400044a5  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400044ac  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400044b3  jz      short loc_1400044DF
0x1400044b5  movzx   eax, word ptr [rdi+10h]
0x1400044b9  mov     r9d, 1Eh
0x1400044bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400044c6  mov     [rsp+0D0h+ReportLength], esi
0x1400044ca  mov     dword ptr [rsp+0D0h+Report], eax
0x1400044ce  mov     rax, [rbx]
0x1400044d1  mov     rcx, [rcx+40h]
0x1400044d5  mov     [rsp+0D0h+PreparsedData], rax
0x1400044da  call    WPP_RECORDER_SF_qdd
0x1400044df  lea     r13, WPP_98d22518711f34f074bb80910c9ade48_Traceguids
0x1400044e6  mov     rcx, [rbp+57h+P]; P
0x1400044ea  xor     edx, edx; Tag
0x1400044ec  call    cs:__imp_ExFreePoolWithTag
0x1400044f3  nop     dword ptr [rax+rax+00h]
0x1400044f8  mov     r15, [rsp+0D0h+var_38]
0x140004500  jmp     loc_140004B15
0x140004505  mov     [rax], sil
0x140004508  mov     edx, 0B0192h
0x14000450d  movzx   eax, word ptr [rdi+10h]
0x140004511  mov     rcx, rbx
0x140004514  mov     dword ptr [rsp+0D0h+PreparsedData], eax
0x140004518  mov     [rsp+0D0h+UsageValue], r12
0x14000451d  call    KbdHid_CallHidClass
0x140004522  mov     esi, eax
0x140004524  test    eax, eax
0x140004526  jns     short loc_140004579
0x140004528  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000452f  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140004536  lea     r13, WPP_98d22518711f34f074bb80910c9ade48_Traceguids
0x14000453d  jz      loc_140004A6C
0x140004543  mov     rcx, cs:WPP_GLOBAL_Control
0x14000454a  mov     r9d, 1Fh
0x140004550  mov     dword ptr [rsp+0D0h+Report], eax
0x140004554  mov     r8d, 1
0x14000455a  mov     rax, [rbx]
0x14000455d  movzx   edx, r15b
0x140004561  mov     [rsp+0D0h+PreparsedData], rax
0x140004566  mov     rcx, [rcx+40h]
0x14000456a  mov     [rsp+0D0h+UsageValue], r13
0x14000456f  call    WPP_RECORDER_SF_qd
0x140004574  jmp     loc_140004A6C
0x140004579  movzx   eax, word ptr [rdi+10h]
0x14000457d  mov     edx, 0Ch; UsagePage
0x140004582  mov     [rsp+0D0h+ReportLength], eax; ReportLength
0x140004586  mov     r9d, 2C3h; Usage
0x14000458c  mov     rax, [rdi]
0x14000458f  movzx   r8d, r13w; LinkCollection
0x140004593  mov     [rsp+0D0h+Report], r12; Report
0x140004598  mov     ecx, r15d; ReportType
0x14000459b  mov     [rsp+0D0h+PreparsedData], rax; PreparsedData
0x1400045a0  lea     rax, [rbp+57h+arg_8]
0x1400045a4  mov     [rsp+0D0h+UsageValue], rax; UsageValue
0x1400045a9  call    cs:__imp_HidP_GetUsageValue
0x1400045b0  nop     dword ptr [rax+rax+00h]
0x1400045b5  lea     r14, WPP_RECORDER_INITIALIZED
0x1400045bc  test    eax, eax
0x1400045be  jns     short loc_1400045E1
0x1400045c0  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400045c7  lea     rsi, WPP_98d22518711f34f074bb80910c9ade48_Traceguids
0x1400045ce  jz      loc_1400046F4
0x1400045d4  mov     r9d, 20h ; ' '
0x1400045da  mov     dl, 3
0x1400045dc  jmp     loc_140004670
0x1400045e1  mov     eax, [rbp+57h+arg_8]
0x1400045e4  cmp     eax, 6
0x1400045e7  jbe     short loc_14000460C
0x1400045e9  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400045f0  lea     rsi, WPP_98d22518711f34f074bb80910c9ade48_Traceguids
0x1400045f7  jz      loc_1400046E4
0x1400045fd  mov     r9d, 21h ; '!'
0x140004603  mov     dword ptr [rsp+0D0h+Report], eax
0x140004607  jmp     loc_1400046BD
0x14000460c  jnz     loc_1400046ED
0x140004612  movzx   eax, word ptr [rdi+10h]
0x140004616  mov     edx, 0Ch; UsagePage
0x14000461b  mov     [rsp+0D0h+ReportLength], eax; ReportLength
0x14000461f  mov     r9d, 2C4h; Usage
0x140004625  mov     rax, [rdi]
0x140004628  movzx   r8d, r13w; LinkCollection
0x14000462c  mov     [rsp+0D0h+Report], r12; Report
0x140004631  mov     ecx, r15d; ReportType
0x140004634  mov     [rsp+0D0h+PreparsedData], rax; PreparsedData
0x140004639  lea     rax, [rbp+57h+var_60]
0x14000463d  mov     [rsp+0D0h+UsageValue], rax; UsageValue
0x140004642  call    cs:__imp_HidP_GetUsageValue
0x140004649  nop     dword ptr [rax+rax+00h]
0x14000464e  test    eax, eax
0x140004650  jns     short loc_140004699
0x140004652  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140004659  lea     rsi, WPP_98d22518711f34f074bb80910c9ade48_Traceguids
0x140004660  jz      loc_1400046F4
0x140004666  mov     r9d, 22h ; '"'
0x14000466c  movzx   edx, r15b
0x140004670  mov     rcx, cs:WPP_GLOBAL_Control
0x140004677  mov     r8d, 1
0x14000467d  mov     dword ptr [rsp+0D0h+Report], eax
0x140004681  mov     rax, [rbx]
0x140004684  mov     [rsp+0D0h+PreparsedData], rax
0x140004689  mov     rcx, [rcx+40h]
0x14000468d  mov     [rsp+0D0h+UsageValue], rsi
0x140004692  call    WPP_RECORDER_SF_qd
0x140004697  jmp     short loc_1400046F4
0x140004699  cmp     [rbp+57h+var_60], 0
0x14000469d  jnz     short loc_1400046ED
0x14000469f  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400046a6  lea     rsi, WPP_98d22518711f34f074bb80910c9ade48_Traceguids
0x1400046ad  jz      short loc_1400046E4
0x1400046af  mov     r9d, 23h ; '#'
0x1400046b5  mov     dword ptr [rsp+0D0h+Report], 0
0x1400046bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400046c4  mov     r8d, 1
0x1400046ca  mov     rax, [rbx]
0x1400046cd  movzx   edx, r15b
0x1400046d1  mov     [rsp+0D0h+PreparsedData], rax
0x1400046d6  mov     [rsp+0D0h+UsageValue], rsi
0x1400046db  mov     rcx, [rcx+40h]
0x1400046df  call    WPP_RECORDER_SF_qd
0x1400046e4  mov     [rbp+57h+arg_8], 0
0x1400046eb  jmp     short loc_1400046F4
0x1400046ed  lea     rsi, WPP_98d22518711f34f074bb80910c9ade48_Traceguids
0x1400046f4  movzx   eax, word ptr [rdi+10h]
0x1400046f8  mov     edx, 0Ch; UsagePage
0x1400046fd  mov     [rsp+0D0h+ReportLength], eax; ReportLength
0x140004701  mov     r9d, 2C1h; Usage
0x140004707  mov     rax, [rdi]
0x14000470a  movzx   r8d, r13w; LinkCollection
0x14000470e  mov     [rsp+0D0h+Report], r12; Report
0x140004713  mov     ecx, r15d; ReportType
0x140004716  mov     [rsp+0D0h+PreparsedData], rax; PreparsedData
0x14000471b  lea     rax, [rbp+57h+arg_10]
0x14000471f  mov     [rsp+0D0h+UsageValue], rax; UsageValue
0x140004724  call    cs:__imp_HidP_GetUsageValue
0x14000472b  nop     dword ptr [rax+rax+00h]
0x140004730  test    eax, eax
0x140004732  jns     short loc_14000476E
0x140004734  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14000473b  jz      short loc_1400047B7
0x14000473d  mov     rcx, cs:WPP_GLOBAL_Control
0x140004744  mov     r9d, 24h ; '$'
0x14000474a  mov     dword ptr [rsp+0D0h+Report], eax
0x14000474e  mov     r8d, 1
0x140004754  mov     rax, [rbx]
0x140004757  mov     dl, 3
0x140004759  mov     [rsp+0D0h+PreparsedData], rax
0x14000475e  mov     rcx, [rcx+40h]
0x140004762  mov     [rsp+0D0h+UsageValue], rsi
0x140004767  call    WPP_RECORDER_SF_qd
0x14000476c  jmp     short loc_1400047B7
0x14000476e  mov     eax, [rbp+57h+arg_10]
0x140004771  cmp     eax, r15d
0x140004774  jbe     short loc_1400047B7
0x140004776  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14000477d  jz      short loc_1400047B0
0x14000477f  mov     rcx, cs:WPP_GLOBAL_Control
0x140004786  mov     r9d, 25h ; '%'
0x14000478c  mov     dword ptr [rsp+0D0h+Report], eax
0x140004790  mov     r8d, 1
0x140004796  mov     rax, [rbx]
0x140004799  movzx   edx, r15b
0x14000479d  mov     [rsp+0D0h+PreparsedData], rax
0x1400047a2  mov     rcx, [rcx+40h]
0x1400047a6  mov     [rsp+0D0h+UsageValue], rsi
0x1400047ab  call    WPP_RECORDER_SF_qd
0x1400047b0  mov     [rbp+57h+arg_10], 0
0x1400047b7  movzx   eax, word ptr [rdi+10h]
0x1400047bb  mov     edx, 0Ch; UsagePage
0x1400047c0  mov     [rsp+0D0h+ReportLength], eax; ReportLength
0x1400047c4  mov     r9d, 2C2h; Usage
0x1400047ca  mov     rax, [rdi]
0x1400047cd  movzx   r8d, r13w; LinkCollection
0x1400047d1  mov     [rsp+0D0h+Report], r12; Report
0x1400047d6  mov     ecx, r15d; ReportType
0x1400047d9  mov     [rsp+0D0h+PreparsedData], rax; PreparsedData
0x1400047de  lea     rax, [rbp+57h+arg_18]
0x1400047e2  mov     [rsp+0D0h+UsageValue], rax; UsageValue
0x1400047e7  call    cs:__imp_HidP_GetUsageValue
0x1400047ee  nop     dword ptr [rax+rax+00h]
0x1400047f3  test    eax, eax
0x1400047f5  jns     short loc_140004831
0x1400047f7  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400047fe  jz      short loc_14000487A
0x140004800  mov     rcx, cs:WPP_GLOBAL_Control
0x140004807  mov     r9d, 26h ; '&'
0x14000480d  mov     dword ptr [rsp+0D0h+Report], eax
0x140004811  mov     r8d, 1
0x140004817  mov     rax, [rbx]
0x14000481a  mov     dl, 3
  ... truncated ...
```
