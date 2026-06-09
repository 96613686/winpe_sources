# CSyncMLDPU::ExecuteAllCommands(tagSyncMLDPUParams * const)

- ea: `0x180005370`
- end: `0x180005bc2`
- name: `?ExecuteAllCommands@CSyncMLDPU@@AEAAJQEAUtagSyncMLDPUParams@@@Z`
- size: `2130`
- prototype: `__int64 __fastcall(CSyncMLDPU *__hidden this, struct tagSyncMLDPUParams *const)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007820`

## callees

- `0x180005370`
- `0x180014330`
- `0x180015c87`
- `0x180030010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000553a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800056a6`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800057b8`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800058bf`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180005999`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180005a63`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180005b47`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000553a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800056a6`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800057b8`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800058bf`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180005999`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180005a63`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180005b47`
- `OLEAUT32!__imp_SysAllocString` at `0x1800053e6`
- `OLEAUT32!__imp_SysAllocString` at `0x18000541d`
- `OLEAUT32!__imp_SysAllocString` at `0x1800053e6`
- `OLEAUT32!__imp_SysAllocString` at `0x18000541d`
- `OLEAUT32!__imp_SysFreeString` at `0x180005472`
- `OLEAUT32!__imp_SysFreeString` at `0x180005b7f`
- `OLEAUT32!__imp_SysFreeString` at `0x180005472`
- `OLEAUT32!__imp_SysFreeString` at `0x180005b7f`
- `OLEAUT32!__imp_VariantInit` at `0x1800053b0`
- `OLEAUT32!__imp_VariantInit` at `0x1800053b0`
- `OLEAUT32!__imp_VariantClear` at `0x180005403`
- `OLEAUT32!__imp_VariantClear` at `0x180005b90`
- `OLEAUT32!__imp_VariantClear` at `0x180005403`
- `OLEAUT32!__imp_VariantClear` at `0x180005b90`

## pseudocode

```c
__int64 __fastcall CSyncMLDPU::ExecuteAllCommands(CSyncMLDPU *this, struct tagSyncMLDPUParams *const a2)
{
  _QWORD *v4; // rbx
  const OLECHAR *v5; // rcx
  OLECHAR *v6; // r15
  const OLECHAR *v7; // rcx
  __int64 *v8; // rcx
  __int64 v9; // rax
  unsigned int v10; // r12d
  __int64 *v11; // rsi
  __int64 v12; // rbx
  size_t v13; // r14
  int v14; // r14d
  int v15; // esi
  __int64 v16; // rsi
  int v17; // eax
  int v18; // r14d
  __int64 v19; // rsi
  int v20; // eax
  int v21; // eax
  int v22; // eax
  unsigned int v24; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v25; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v26; // [rsp+38h] [rbp-C8h] BYREF
  int v27; // [rsp+3Ch] [rbp-C4h] BYREF
  unsigned int v28; // [rsp+40h] [rbp-C0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-A8h] BYREF
  EVENT_DESCRIPTOR v31; // [rsp+70h] [rbp-90h] BYREF
  EVENT_DESCRIPTOR v32; // [rsp+80h] [rbp-80h] BYREF
  EVENT_DESCRIPTOR v33; // [rsp+90h] [rbp-70h] BYREF
  EVENT_DESCRIPTOR v34; // [rsp+A0h] [rbp-60h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v35; // [rsp+B0h] [rbp-50h] BYREF
  int *v36; // [rsp+C0h] [rbp-40h]
  int v37; // [rsp+C8h] [rbp-38h]
  int v38; // [rsp+CCh] [rbp-34h]
  unsigned int *v39; // [rsp+D0h] [rbp-30h]
  __int64 v40; // [rsp+D8h] [rbp-28h]
  unsigned int *v41; // [rsp+E0h] [rbp-20h]
  __int64 v42; // [rsp+E8h] [rbp-18h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+F0h] [rbp-10h] BYREF
  IRecordInfo *pRecInfo; // [rsp+100h] [rbp+0h]
  int v45; // [rsp+108h] [rbp+8h]
  int v46; // [rsp+10Ch] [rbp+Ch]

  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v4 = (_QWORD *)*((_QWORD *)this + 46);
  while ( 1 )
  {
    v4 = (_QWORD *)*v4;
    if ( v4 == *((_QWORD **)this + 46) )
      break;
    v5 = (const OLECHAR *)(v4 + 2);
    if ( v4[5] > 7u )
      v5 = *(const OLECHAR **)v5;
    v6 = SysAllocString(v5);
    if ( !v6 )
      goto LABEL_59;
    VariantClear(&pvarg);
    v7 = (const OLECHAR *)(v4 + 6);
    if ( v4[9] > 7u )
      v7 = *(const OLECHAR **)v7;
    pvarg.llVal = (LONGLONG)SysAllocString(v7);
    if ( !pvarg.llVal )
      goto LABEL_59;
    v8 = (__int64 *)*((_QWORD *)this + 7);
    pvarg.vt = 8;
    v9 = *v8;
    pRecInfo = pvarg.pRecInfo;
    UserData = *(struct _EVENT_DATA_DESCRIPTOR *)&pvarg.vt;
    if ( (*(int (__fastcall **)(__int64 *, OLECHAR *, struct _EVENT_DATA_DESCRIPTOR *))(v9 + 104))(v8, v6, &UserData) < 0 )
      goto LABEL_59;
    SysFreeString(v6);
  }
  v6 = 0;
  if ( *((_QWORD *)this + 9) != *((_QWORD *)this + 10) )
  {
    v10 = 0;
    if ( (unsigned int)dword_18003E048 > 5 )
    {
      *(_DWORD *)&EventDescriptor.Level = 5;
      UserData.Ptr = (ULONGLONG)off_18003E050;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      UserData.Size = (unsigned __int16)*off_18003E050;
      pRecInfo = (IRecordInfo *)&word_180035FCE;
      UserData.Reserved = 2;
      v45 = 23;
      v46 = 1;
      v25 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &UserData);
    }
    while ( 1 )
    {
      v11 = (__int64 *)*((_QWORD *)this + 9);
      if ( !((__int64)(*((_QWORD *)this + 10) - (_QWORD)v11) >> 3) )
        goto LABEL_59;
      v12 = *v11;
      ++v10;
      v13 = *((_QWORD *)this + 10) - (_QWORD)(v11 + 1);
      memmove_0(*((void **)this + 9), v11 + 1, v13);
      *((_QWORD *)this + 10) = (char *)v11 + v13;
      v14 = *(_DWORD *)(v12 + 92);
      if ( v14 == 25 )
      {
        if ( (*(_DWORD *)(v12 + 168) & 2) != 0 )
          ++*((_DWORD *)this + 59);
      }
      else
      {
        ++*((_DWORD *)this + 59);
        if ( v14 != 27 )
          *((_DWORD *)this + 111) |= 4u;
      }
      v15 = *(_DWORD *)(v12 + 56);
      *(_QWORD *)(v12 + 72) = a2;
      if ( v15 < 0
        || (v16 = *(_QWORD *)(v12 + 96)) != 0 && (v15 = *(_DWORD *)(v16 + 132), v15 < 0)
        || (v15 = *(_DWORD *)(v12 + 60), v15 < 0) )
      {
        if ( (unsigned int)dword_18003E048 > 2 )
        {
          v25 = v15;
          v41 = &v25;
          v26 = v10;
          v39 = &v26;
          *(_DWORD *)&EventDescriptor.Level = 2;
          v35.Ptr = (ULONGLONG)off_18003E050;
          v42 = 4;
          v40 = 4;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          EventDescriptor.Keyword = 0;
          v35.Size = (unsigned __int16)*off_18003E050;
          v36 = (int *)byte_180035E3D;
          v35.Reserved = 2;
          v37 = 42;
          v38 = 1;
          v24 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &v35);
        }
      }
      if ( *((_DWORD *)this + 110) != 1 )
        break;
      if ( v14 == 25 || v14 == 27 )
      {
LABEL_31:
        v17 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v12 + 24LL))(v12, *((_QWORD *)this + 7));
        v18 = v17;
        if ( v17 < 0 && (unsigned int)dword_18003E048 > 2 )
        {
          v24 = v17;
          v26 = v10;
          v41 = &v24;
          v42 = 4;
          v39 = &v26;
          *(_DWORD *)&v31.Level = 2;
          v35.Ptr = (ULONGLONG)off_18003E050;
          v40 = 4;
          *(_DWORD *)&v31.Id = 184549376;
          v31.Keyword = 0;
          v35.Size = (unsigned __int16)*off_18003E050;
          v36 = &dword_180035C34;
          v35.Reserved = 2;
          v37 = 43;
          v38 = 1;
          v25 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(RegHandle, &v31, 0, 0, 4u, &v35);
        }
        v19 = v12 + 96;
        if ( (*(int *)(v12 + 56) < 0 || *(_QWORD *)v19 && *(int *)(*(_QWORD *)v19 + 132LL) < 0 || *(int *)(v12 + 60) < 0)
          && (unsigned int)dword_18003E048 > 2 )
        {
          v20 = *(_DWORD *)(v12 + 56);
          if ( v20 >= 0 )
          {
            if ( !*(_QWORD *)v19 || (v20 = *(_DWORD *)(*(_QWORD *)v19 + 132LL), v20 >= 0) )
              v20 = *(_DWORD *)(v12 + 60);
          }
          v27 = v20;
          v28 = v10;
          v41 = (unsigned int *)&v27;
          v42 = 4;
          v39 = &v28;
          *(_DWORD *)&v32.Level = 2;
          v35.Ptr = (ULONGLONG)off_18003E050;
          v40 = 4;
          *(_DWORD *)&v32.Id = 184549376;
          v32.Keyword = 0;
          v35.Size = (unsigned __int16)*off_18003E050;
          v36 = &dword_180036014;
          v35.Reserved = 2;
          v37 = 43;
          v38 = 1;
          v24 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(RegHandle, &v32, 0, 0, 4u, &v35);
        }
        if ( v18 >= 0
          && *(int *)(v12 + 56) >= 0
          && (!*(_QWORD *)v19 || *(int *)(*(_QWORD *)v19 + 132LL) >= 0)
          && *(int *)(v12 + 60) >= 0
          && *((_DWORD *)this + 110) != 1 )
        {
          if ( (unsigned int)dword_18003E048 > 5 )
          {
            *(_DWORD *)&v33.Level = 5;
            v35.Ptr = (ULONGLONG)off_18003E050;
            *(_DWORD *)&v33.Id = 184549376;
            v33.Keyword = 0;
            v35.Size = (unsigned __int16)*off_18003E050;
            v36 = (int *)byte_180036109;
            v35.Reserved = 2;
            v37 = 25;
            v38 = 1;
            v24 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EventWriteTransfer(RegHandle, &v33, 0, 0, 2u, &v35);
          }
          v21 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 24LL))(*((_QWORD *)this + 7));
          if ( v21 < 0 && (unsigned int)dword_18003E048 > 2 )
          {
            v24 = v21;
            v40 = 4;
            v39 = &v24;
            *(_DWORD *)&v34.Level = 2;
            v35.Ptr = (ULONGLONG)off_18003E050;
            *(_DWORD *)&v34.Id = 184549376;
            v34.Keyword = 0;
            v35.Size = (unsigned __int16)*off_18003E050;
            v36 = (int *)byte_180035EA1;
            v35.Reserved = 2;
            v37 = 32;
            v38 = 1;
            v26 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EventWriteTransfer(RegHandle, &v34, 0, 0, 3u, &v35);
          }
        }
LABEL_55:
        v22 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v12 + 32LL))(v12, *((_QWORD *)this + 32));
        if ( v22 < 0 && (unsigned int)dword_18003E048 > 2 )
        {
          v24 = v22;
          v26 = v10;
          v41 = &v24;
          v42 = 4;
          v39 = &v26;
          v35.Ptr = (ULONGLONG)off_18003E050;
          v40 = 4;
          UserData.Ptr = 0x20B000000LL;
          *(_QWORD *)&UserData.Size = 0;
          v35.Size = (unsigned __int16)*off_18003E050;
          v36 = &dword_180035EF4;
          v35.Reserved = 2;
          v37 = 44;
          v38 = 1;
          v25 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&UserData, 0, 0, 4u, &v35);
        }
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 40LL))(v12, 1);
      }
    }
    if ( v15 < 0 )
      goto LABEL_55;
    goto LABEL_31;
  }
LABEL_59:
  SysFreeString(v6);
  VariantClear(&pvarg);
  return 0;
}

```

## disassembly

```asm
0x180005370  mov     [rsp-8+arg_18], rbx
0x180005375  push    rbp
0x180005376  push    rsi
0x180005377  push    rdi
0x180005378  push    r13
0x18000537a  push    r15
0x18000537c  lea     rbp, [rsp-20h]
0x180005381  sub     rsp, 120h
0x180005388  mov     rax, cs:__security_cookie
0x18000538f  xor     rax, rsp
0x180005392  mov     [rbp+40h+var_30], rax
0x180005396  mov     rdi, rcx
0x180005399  xorps   xmm0, xmm0
0x18000539c  xor     eax, eax
0x18000539e  lea     rcx, [rsp+140h+pvarg]; pvarg
0x1800053a3  movups  xmmword ptr [rsp+140h+pvarg], xmm0
0x1800053a8  mov     qword ptr [rsp+140h+pvarg+10h], rax
0x1800053ad  mov     r13, rdx
0x1800053b0  call    cs:__imp_VariantInit
0x1800053b7  nop     dword ptr [rax+rax+00h]
0x1800053bc  mov     rbx, [rdi+170h]
0x1800053c3  mov     esi, 8
0x1800053c8  mov     rbx, [rbx]
0x1800053cb  cmp     rbx, [rdi+170h]
0x1800053d2  jz      loc_180005483
0x1800053d8  cmp     qword ptr [rbx+28h], 7
0x1800053dd  lea     rcx, [rbx+10h]
0x1800053e1  jbe     short loc_1800053E6
0x1800053e3  mov     rcx, [rcx]; psz
0x1800053e6  call    cs:__imp_SysAllocString
0x1800053ed  nop     dword ptr [rax+rax+00h]
0x1800053f2  mov     r15, rax
0x1800053f5  test    rax, rax
0x1800053f8  jz      loc_180005B7C
0x1800053fe  lea     rcx, [rsp+140h+pvarg]; pvarg
0x180005403  call    cs:__imp_VariantClear
0x18000540a  nop     dword ptr [rax+rax+00h]
0x18000540f  cmp     qword ptr [rbx+48h], 7
0x180005414  lea     rcx, [rbx+30h]
0x180005418  jbe     short loc_18000541D
0x18000541a  mov     rcx, [rcx]; psz
0x18000541d  call    cs:__imp_SysAllocString
0x180005424  nop     dword ptr [rax+rax+00h]
0x180005429  mov     qword ptr [rsp+140h+pvarg+8], rax
0x18000542e  test    rax, rax
0x180005431  jz      loc_180005B7C
0x180005437  mov     rcx, [rdi+38h]
0x18000543b  lea     r8, [rbp+40h+var_50]
0x18000543f  movsd   xmm1, qword ptr [rsp+140h+pvarg+10h]
0x180005445  mov     rdx, r15
0x180005448  mov     word ptr [rsp+140h+pvarg], si
0x18000544d  movups  xmm0, xmmword ptr [rsp+140h+pvarg]
0x180005452  mov     rax, [rcx]
0x180005455  movsd   [rbp+40h+var_40], xmm1
0x18000545a  movaps  xmmword ptr [rbp+40h+var_50.Ptr], xmm0
0x18000545e  mov     rax, [rax+68h]
0x180005462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005467  test    eax, eax
0x180005469  js      loc_180005B7C
0x18000546f  mov     rcx, r15; bstrString
0x180005472  call    cs:__imp_SysFreeString
0x180005479  nop     dword ptr [rax+rax+00h]
0x18000547e  jmp     loc_1800053C8
0x180005483  mov     rax, [rdi+50h]
0x180005487  xor     r15d, r15d
0x18000548a  cmp     [rdi+48h], rax
0x18000548e  jz      loc_180005B7C
0x180005494  mov     eax, cs:dword_18003E048
0x18000549a  lea     rcx, _TraceLoggingMetadata
0x1800054a1  mov     [rsp+140h+arg_8], r12
0x1800054a9  mov     r12d, r15d
0x1800054ac  mov     [rsp+140h+arg_10], r14
0x1800054b4  cmp     eax, 5
0x1800054b7  jbe     loc_180005546
0x1800054bd  movzx   eax, cs:word_180035FC4
0x1800054c4  lea     rdx, [rsp+140h+EventDescriptor]; EventDescriptor
0x1800054c9  mov     dword ptr [rsp+140h+EventDescriptor.Level], eax
0x1800054cd  xor     r9d, r9d; RelatedActivityId
0x1800054d0  mov     rax, cs:off_18003E050
0x1800054d7  xor     r8d, r8d; ActivityId
0x1800054da  mov     [rbp+40h+var_50.Ptr], rax
0x1800054de  mov     dword ptr [rsp+140h+EventDescriptor.Id], 0B000000h
0x1800054e6  mov     [rsp+140h+EventDescriptor.Keyword], r15
0x1800054eb  movzx   eax, word ptr [rax]
0x1800054ee  mov     [rbp+40h+var_50.Size], eax
0x1800054f1  lea     rax, word_180035FCE
0x1800054f8  mov     [rbp+40h+var_40], rax
0x1800054fc  lea     rax, _TraceLoggingMetadataEnd
0x180005503  sub     eax, ecx
0x180005505  mov     dword ptr [rbp+40h+var_50.0Ch], 2
0x18000550c  mov     [rbp+40h+var_38], 17h
0x180005513  mov     [rbp+40h+var_34], 1
0x18000551a  mov     [rsp+140h+var_10C], eax
0x18000551e  mov     eax, [rsp+140h+var_10C]
0x180005522  mov     rcx, cs:RegHandle; RegHandle
0x180005529  lea     rax, [rbp+40h+var_50]
0x18000552d  mov     [rsp+140h+UserData], rax; UserData
0x180005532  mov     [rsp+140h+UserDataCount], 2; UserDataCount
0x18000553a  call    cs:__imp_EventWriteTransfer
0x180005541  nop     dword ptr [rax+rax+00h]
0x180005546  lea     rcx, byte_180035E3D
0x18000554d  nop     dword ptr [rax]
0x180005550  mov     r14, [rdi+50h]
0x180005554  mov     rsi, [rdi+48h]
0x180005558  mov     rax, r14
0x18000555b  sub     rax, rsi
0x18000555e  sar     rax, 3
0x180005562  test    rax, rax
0x180005565  jz      loc_180005B6C
0x18000556b  mov     rbx, [rsi]
0x18000556e  lea     rdx, [rsi+8]; Src
0x180005572  inc     r12d
0x180005575  cmp     rsi, rdx
0x180005578  jz      short loc_180005597
0x18000557a  sub     r14, rdx
0x18000557d  mov     rcx, rsi; void *
0x180005580  mov     r8, r14; Size
0x180005583  call    memmove_0
0x180005588  lea     rax, [rsi+r14]
0x18000558c  mov     [rdi+50h], rax
0x180005590  lea     rcx, byte_180035E3D
0x180005597  mov     r14d, [rbx+5Ch]
0x18000559b  cmp     r14d, 19h
0x18000559f  jnz     short loc_1800055B3
0x1800055a1  mov     eax, [rbx+0A8h]
0x1800055a7  test    al, 2
0x1800055a9  jz      short loc_1800055C6
0x1800055ab  inc     dword ptr [rdi+0ECh]
0x1800055b1  jmp     short loc_1800055C6
0x1800055b3  inc     dword ptr [rdi+0ECh]
0x1800055b9  cmp     r14d, 1Bh
0x1800055bd  jz      short loc_1800055C6
0x1800055bf  or      dword ptr [rdi+1BCh], 4
0x1800055c6  mov     esi, [rbx+38h]
0x1800055c9  mov     [rbx+48h], r13
0x1800055cd  test    esi, esi
0x1800055cf  js      short loc_1800055EF
0x1800055d1  mov     rsi, [rbx+60h]
0x1800055d5  test    rsi, rsi
0x1800055d8  jz      short loc_1800055E4
0x1800055da  mov     esi, [rsi+84h]
0x1800055e0  test    esi, esi
0x1800055e2  js      short loc_1800055EF
0x1800055e4  mov     esi, [rbx+3Ch]
0x1800055e7  test    esi, esi
0x1800055e9  jns     loc_1800056B2
0x1800055ef  mov     eax, cs:dword_18003E048
0x1800055f5  cmp     eax, 2
0x1800055f8  jbe     loc_1800056B2
0x1800055fe  mov     [rsp+140h+var_10C], esi
0x180005602  lea     rax, [rsp+140h+var_10C]
0x180005607  mov     [rbp+40h+var_60], rax
0x18000560b  lea     rdx, [rsp+140h+EventDescriptor]; EventDescriptor
0x180005610  lea     rax, [rsp+140h+var_108]
0x180005615  mov     [rsp+140h+var_108], r12d
0x18000561a  mov     [rbp+40h+var_70], rax
0x18000561e  xor     r9d, r9d; RelatedActivityId
0x180005621  movzx   eax, cs:word_180035E33
0x180005628  xor     r8d, r8d; ActivityId
0x18000562b  mov     dword ptr [rsp+140h+EventDescriptor.Level], eax
0x18000562f  mov     rax, cs:off_18003E050
0x180005636  mov     [rbp+40h+var_90.Ptr], rax
0x18000563a  mov     [rbp+40h+var_58], 4
0x180005642  mov     [rbp+40h+var_68], 4
0x18000564a  mov     dword ptr [rsp+140h+EventDescriptor.Id], 0B000000h
0x180005652  mov     [rsp+140h+EventDescriptor.Keyword], r15
0x180005657  movzx   eax, word ptr [rax]
0x18000565a  mov     [rbp+40h+var_90.Size], eax
0x18000565d  lea     rax, _TraceLoggingMetadataEnd
0x180005664  mov     [rbp+40h+var_80], rcx
0x180005668  lea     rcx, _TraceLoggingMetadata
0x18000566f  sub     eax, ecx
0x180005671  mov     dword ptr [rbp+40h+var_90.0Ch], 2
0x180005678  mov     [rbp+40h+var_78], 2Ah ; '*'
0x18000567f  mov     [rbp+40h+var_74], 1
0x180005686  mov     [rsp+140h+var_110], eax
0x18000568a  mov     eax, [rsp+140h+var_110]
0x18000568e  mov     rcx, cs:RegHandle; RegHandle
0x180005695  lea     rax, [rbp+40h+var_90]
0x180005699  mov     [rsp+140h+UserData], rax; UserData
0x18000569e  mov     [rsp+140h+UserDataCount], 4; UserDataCount
0x1800056a6  call    cs:__imp_EventWriteTransfer
0x1800056ad  nop     dword ptr [rax+rax+00h]
0x1800056b2  cmp     dword ptr [rdi+1B8h], 1
0x1800056b9  jnz     short loc_1800056D4
0x1800056bb  cmp     r14d, 19h
0x1800056bf  jz      short loc_1800056DC
0x1800056c1  lea     rcx, byte_180035E3D
0x1800056c8  cmp     r14d, 1Bh
0x1800056cc  jnz     loc_180005550
0x1800056d2  jmp     short loc_1800056DC
0x1800056d4  test    esi, esi
0x1800056d6  js      loc_180005A6F
0x1800056dc  mov     rax, [rbx]
0x1800056df  mov     rcx, rbx
0x1800056e2  mov     rdx, [rdi+38h]
0x1800056e6  mov     rax, [rax+18h]
0x1800056ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056ef  mov     r14d, eax
0x1800056f2  test    eax, eax
0x1800056f4  jns     loc_1800057C4
0x1800056fa  mov     ecx, cs:dword_18003E048
0x180005700  cmp     ecx, 2
0x180005703  jbe     loc_1800057C4
0x180005709  mov     [rsp+140h+var_110], eax
0x18000570d  lea     rcx, _TraceLoggingMetadata
0x180005714  mov     [rsp+140h+var_108], r12d
0x180005719  lea     rax, [rsp+140h+var_110]
0x18000571e  mov     [rbp+40h+var_60], rax
0x180005722  lea     rdx, [rsp+140h+var_D0]; EventDescriptor
0x180005727  lea     rax, [rsp+140h+var_108]
0x18000572c  mov     [rbp+40h+var_58], 4
0x180005734  mov     [rbp+40h+var_70], rax
0x180005738  xor     r9d, r9d; RelatedActivityId
0x18000573b  movzx   eax, cs:word_180035C2A
0x180005742  xor     r8d, r8d; ActivityId
0x180005745  mov     dword ptr [rsp+140h+var_D0.Level], eax
0x180005749  mov     rax, cs:off_18003E050
0x180005750  mov     [rbp+40h+var_90.Ptr], rax
0x180005754  mov     [rbp+40h+var_68], 4
0x18000575c  mov     dword ptr [rsp+140h+var_D0.Id], 0B000000h
0x180005764  mov     [rsp+140h+var_D0.Keyword], r15
0x180005769  movzx   eax, word ptr [rax]
0x18000576c  mov     [rbp+40h+var_90.Size], eax
0x18000576f  lea     rax, dword_180035C34
0x180005776  mov     [rbp+40h+var_80], rax
0x18000577a  lea     rax, _TraceLoggingMetadataEnd
0x180005781  sub     eax, ecx
0x180005783  mov     dword ptr [rbp+40h+var_90.0Ch], 2
0x18000578a  mov     [rbp+40h+var_78], 2Bh ; '+'
0x180005791  mov     [rbp+40h+var_74], 1
0x180005798  mov     [rsp+140h+var_10C], eax
0x18000579c  mov     eax, [rsp+140h+var_10C]
0x1800057a0  mov     rcx, cs:RegHandle; RegHandle
0x1800057a7  lea     rax, [rbp+40h+var_90]
0x1800057ab  mov     [rsp+140h+UserData], rax; UserData
0x1800057b0  mov     [rsp+140h+UserDataCount], 4; UserDataCount
0x1800057b8  call    cs:__imp_EventWriteTransfer
0x1800057bf  nop     dword ptr [rax+rax+00h]
0x1800057c4  lea     rsi, [rbx+60h]
0x1800057c8  cmp     [rbx+38h], r15d
0x1800057cc  jl      short loc_1800057E9
0x1800057ce  mov     rax, [rsi]
0x1800057d1  test    rax, rax
0x1800057d4  jz      short loc_1800057DF
0x1800057d6  cmp     [rax+84h], r15d
0x1800057dd  jl      short loc_1800057E9
0x1800057df  cmp     [rbx+3Ch], r15d
0x1800057e3  jge     loc_1800058CB
0x1800057e9  mov     eax, cs:dword_18003E048
0x1800057ef  cmp     eax, 2
0x1800057f2  jbe     loc_1800058CB
0x1800057f8  mov     eax, [rbx+38h]
0x1800057fb  test    eax, eax
0x1800057fd  js      short loc_180005814
0x1800057ff  mov     rax, [rsi]
0x180005802  test    rax, rax
0x180005805  jz      short loc_180005811
0x180005807  mov     eax, [rax+84h]
0x18000580d  test    eax, eax
0x18000580f  js      short loc_180005814
0x180005811  mov     eax, [rbx+3Ch]
0x180005814  mov     [rsp+140h+var_104], eax
0x180005818  lea     rcx, _TraceLoggingMetadata
0x18000581f  mov     [rsp+140h+var_100], r12d
0x180005824  lea     rax, [rsp+140h+var_104]
0x180005829  mov     [rbp+40h+var_60], rax
0x18000582d  lea     rdx, [rbp+40h+var_C0]; EventDescriptor
0x180005831  lea     rax, [rsp+140h+var_100]
0x180005836  mov     [rbp+40h+var_58], 4
0x18000583e  mov     [rbp+40h+var_70], rax
0x180005842  xor     r9d, r9d; RelatedActivityId
0x180005845  movzx   eax, cs:word_18003600A
0x18000584c  xor     r8d, r8d; ActivityId
0x18000584f  mov     dword ptr [rbp+40h+var_C0.Level], eax
0x180005852  mov     rax, cs:off_18003E050
0x180005859  mov     [rbp+40h+var_90.Ptr], rax
0x18000585d  mov     [rbp+40h+var_68], 4
0x180005865  mov     dword ptr [rbp+40h+var_C0.Id], 0B000000h
0x18000586c  mov     [rbp+40h+var_C0.Keyword], r15
0x180005870  movzx   eax, word ptr [rax]
0x180005873  mov     [rbp+40h+var_90.Size], eax
0x180005876  lea     rax, dword_180036014
0x18000587d  mov     [rbp+40h+var_80], rax
0x180005881  lea     rax, _TraceLoggingMetadataEnd
0x180005888  sub     eax, ecx
0x18000588a  mov     dword ptr [rbp+40h+var_90.0Ch], 2
0x180005891  mov     [rbp+40h+var_78], 2Bh ; '+'
0x180005898  mov     [rbp+40h+var_74], 1
0x18000589f  mov     [rsp+140h+var_110], eax
0x1800058a3  mov     eax, [rsp+140h+var_110]
0x1800058a7  mov     rcx, cs:RegHandle; RegHandle
0x1800058ae  lea     rax, [rbp+40h+var_90]
0x1800058b2  mov     [rsp+140h+UserData], rax; UserData
0x1800058b7  mov     [rsp+140h+UserDataCount], 4; UserDataCount
0x1800058bf  call    cs:__imp_EventWriteTransfer
0x1800058c6  nop     dword ptr [rax+rax+00h]
0x1800058cb  test    r14d, r14d
0x1800058ce  js      loc_180005A6F
0x1800058d4  cmp     [rbx+38h], r15d
  ... truncated ...
```
