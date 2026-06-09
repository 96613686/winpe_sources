# CMVEngine::Initialize(ushort const *,ushort const *)

- ea: `0x1800165e0`
- end: `0x180016cc1`
- name: `?Initialize@CMVEngine@@UEAAJPEBG0@Z`
- size: `1761`
- prototype: `__int64 __fastcall(CMVEngine *this, const unsigned __int16 *, __int64, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800010c8`
- `0x180002f0c`
- `0x18000a0f8`
- `0x18000f288`
- `0x180011c68`
- `0x1800165e0`
- `0x1800172e8`
- `0x180035d8c`
- `0x180043750`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18001673f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180016859`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001673f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180016859`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180016635`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180016635`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180016a3c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180016a3c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016aea`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016aea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016af9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016af9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180016abc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180016abc`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180016929`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180016929`
- `ntdll!RtlNtStatusToDosError` at `0x180016944`
- `ntdll!RtlNtStatusToDosError` at `0x180016944`

## pseudocode

```c
__int64 __fastcall CMVEngine::Initialize(CMVEngine *this, const unsigned __int16 *a2, __int64 a3, __int64 a4)
{
  const unsigned __int16 *v4; // r12
  const unsigned __int16 *v7; // rax
  __int64 v8; // rdx
  unsigned __int64 v9; // r13
  unsigned __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  unsigned __int16 *v14; // r14
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  unsigned int v18; // ebx
  const unsigned __int16 *v19; // rax
  unsigned int v20; // ecx
  unsigned __int64 v21; // rsi
  unsigned __int64 v22; // rax
  __int64 v23; // rdx
  unsigned __int16 *v24; // rdi
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  NTSTATUS v30; // eax
  signed int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // r9
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // r9
  signed int Context; // [rsp+50h] [rbp-69h] BYREF
  BYTE Data[4]; // [rsp+54h] [rbp-65h] BYREF
  _QWORD v44[2]; // [rsp+58h] [rbp-61h] BYREF
  char v45; // [rsp+68h] [rbp-51h]
  DWORD pcbData; // [rsp+70h] [rbp-49h] BYREF
  int pvData; // [rsp+74h] [rbp-45h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-41h] BYREF
  int v49; // [rsp+80h] [rbp-39h] BYREF
  char v50; // [rsp+84h] [rbp-35h]
  GUID ActivityId; // [rsp+88h] [rbp-31h] BYREF
  _BYTE v52[32]; // [rsp+A8h] [rbp-11h] BYREF
  BYTE *v53; // [rsp+C8h] [rbp+Fh]
  __int64 v54; // [rsp+D0h] [rbp+17h]

  v4 = (const unsigned __int16 *)a3;
  Context = 0;
  v49 = 0;
  v50 = 0;
  if ( (unsigned int)dword_18005A000 <= 5 )
    ActivityId = 0;
  else
    EventActivityIdControl(3u, &ActivityId);
  v49 = 1;
  if ( (unsigned int)dword_18005A000 > 5 )
    tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, byte_18004E88D, &ActivityId, 0, 2, v52);
  v44[0] = &v49;
  v44[1] = &Context;
  v45 = 1;
  if ( !a2 )
  {
    v8 = 2147942487LL;
LABEL_85:
    Context = v8;
    if ( (unsigned int)dword_18005A000 > 2 )
    {
      *(_DWORD *)Data = Context;
      v53 = Data;
      v54 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, byte_18004F611, &ActivityId, 0, 3, v52);
    }
    v18 = Context;
    if ( v45 )
    {
      v45 = 0;
      lambda_ef616486a7395329213daa9d56ea1427_::operator()(v44, v8, a3, a4);
    }
LABEL_89:
    if ( v49 == 1 )
    {
      v49 = 2;
      goto LABEL_91;
    }
    return v18;
  }
  a3 = 0x7FFFFFFF;
  v7 = a2;
  do
  {
    if ( !*v7 )
      break;
    ++v7;
    --a3;
  }
  while ( a3 );
  v8 = a3 == 0 ? 0x80070057 : 0;
  a4 = (0x7FFFFFFF - a3) & -(__int64)(a3 != 0);
  if ( !a3 )
    goto LABEL_85;
  Context = a3 == 0 ? 0x80070057 : 0;
  v9 = a4 + 1;
  v10 = 2 * (a4 + 1);
  if ( !is_mul_ok(a4 + 1, 2u) )
    v10 = -1;
  v14 = (unsigned __int16 *)operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
  if ( v14 == *((unsigned __int16 **)this + 4) )
  {
    v14 = (unsigned __int16 *)*((_QWORD *)this + 4);
  }
  else
  {
    operator delete[](*((void **)this + 4));
    *((_QWORD *)this + 4) = v14;
  }
  if ( !v14 )
  {
    Context = -2147024882;
    if ( v45 )
    {
      v45 = 0;
      lambda_ef616486a7395329213daa9d56ea1427_::operator()(v44, v11, v12, v13);
    }
    if ( v49 != 1 )
      return 2147942414LL;
    v49 = 2;
    goto LABEL_82;
  }
  Context = StringCchCopyW(v14, v9, a2);
  if ( Context < 0 )
  {
    if ( (unsigned int)dword_18005A000 > 2 )
    {
      *(_DWORD *)Data = Context;
      v53 = Data;
      v54 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, byte_18004E59D, &ActivityId, 0, 3, v52);
    }
    v18 = Context;
    if ( v45 )
    {
      v45 = 0;
      lambda_ef616486a7395329213daa9d56ea1427_::operator()(v44, v15, v16, v17);
    }
    goto LABEL_89;
  }
  if ( !v4 )
  {
    v20 = -2147024809;
LABEL_73:
    Context = v20;
    if ( (unsigned int)dword_18005A000 > 2 )
    {
      *(_DWORD *)Data = Context;
      v53 = Data;
      v54 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, &byte_18004E6DF, &ActivityId, 0, 3, v52);
    }
    v18 = Context;
    if ( v45 )
    {
      v45 = 0;
      lambda_ef616486a7395329213daa9d56ea1427_::operator()(v44, v15, v16, v17);
    }
    goto LABEL_89;
  }
  v15 = 0x7FFFFFFF;
  v19 = v4;
  do
  {
    if ( !*v19 )
      break;
    ++v19;
    --v15;
  }
  while ( v15 );
  v20 = v15 == 0 ? 0x80070057 : 0;
  v16 = (0x7FFFFFFF - v15) & -(__int64)(v15 != 0);
  if ( !v15 )
    goto LABEL_73;
  Context = v15 == 0 ? 0x80070057 : 0;
  v21 = v16 + 1;
  v22 = 2 * (v16 + 1);
  if ( !is_mul_ok(v16 + 1, 2u) )
    v22 = -1;
  v24 = (unsigned __int16 *)operator new[](v22, (const struct std::nothrow_t *)&std::nothrow);
  if ( v24 == *((unsigned __int16 **)this + 5) )
  {
    v24 = (unsigned __int16 *)*((_QWORD *)this + 5);
  }
  else
  {
    operator delete[](*((void **)this + 5));
    *((_QWORD *)this + 5) = v24;
  }
  if ( !v24 )
  {
    Context = -2147024882;
    if ( v45 )
    {
      v45 = 0;
      lambda_ef616486a7395329213daa9d56ea1427_::operator()(v44, v23, v25, v26);
    }
    if ( v49 != 1 )
      return 2147942414LL;
    v49 = 2;
LABEL_82:
    _tlgWriteActivityAutoStop<0,5>(&dword_18005A000, &ActivityId);
    return 2147942414LL;
  }
  Context = StringCchCopyW(v24, v21, v4);
  if ( Context < 0 )
  {
    if ( (unsigned int)dword_18005A000 > 2 )
    {
      *(_DWORD *)Data = Context;
      v53 = Data;
      v54 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, word_18004F05A, &ActivityId, 0, 3, v52);
    }
    v18 = Context;
    if ( v45 )
    {
      v45 = 0;
      lambda_ef616486a7395329213daa9d56ea1427_::operator()(v44, v27, v28, v29);
    }
    goto LABEL_39;
  }
  v30 = RtlSubscribeWnfStateChangeNotification(
          (char *)this + 144,
          WNF_SYS_SHUTDOWN_IN_PROGRESS,
          0,
          CMVEngine::OnShutdownInProgress,
          this,
          0,
          0,
          0);
  if ( (int)(v30 + 0x80000000) >= 0 && v30 != -1073741772 )
  {
    v31 = RtlNtStatusToDosError(v30);
    v18 = v31;
    if ( v31 > 0 )
      v18 = (unsigned __int16)v31 | 0x80070000;
    Context = v18;
    if ( v45 )
    {
      v45 = 0;
      lambda_ef616486a7395329213daa9d56ea1427_::operator()(v44, v32, v33, v34);
    }
    goto LABEL_39;
  }
  if ( !*((_QWORD *)this + 26) )
  {
    Context = ProvStateContext::CreateContext(this);
    if ( Context < 0 )
    {
      if ( (unsigned int)dword_18005A000 > 2 )
      {
        *(_DWORD *)Data = Context;
        v53 = Data;
        v54 = 4;
        tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, byte_18004F893, &ActivityId, 0, 3, v52);
      }
      v18 = Context;
      if ( v45 )
      {
        v45 = 0;
        lambda_ef616486a7395329213daa9d56ea1427_::operator()(v44, v35, v36, v37);
      }
LABEL_39:
      if ( v49 == 1 )
      {
        v49 = 2;
LABEL_91:
        _tlgWriteActivityAutoStop<0,5>(&dword_18005A000, &ActivityId);
      }
      return v18;
    }
  }
  CMVEngine::LoadSequenceHive(this);
  pvData = 0;
  pcbData = 4;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Provisioning\\FirstBootRun",
         0,
         0x10u,
         0,
         &pvData,
         &pcbData) )
  {
    *((_DWORD *)this + 47) = 1;
    if ( (unsigned int)dword_18005A000 > 4 )
      tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, &byte_18004F8F7, 0, 0, 2, v52);
    hKey = 0;
    if ( !RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Provisioning\\FirstBootRun",
            0,
            0,
            1u,
            2u,
            0,
            &hKey,
            0) )
    {
      *(_DWORD *)Data = 1;
      RegSetValueExW(hKey, 0, 0, 4u, Data, 4u);
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  else
  {
    *((_DWORD *)this + 47) = 0;
  }
  if ( v45 )
  {
    v45 = 0;
    lambda_ef616486a7395329213daa9d56ea1427_::operator()(v44, v38, v39, v40);
  }
  if ( v49 == 1 )
  {
    v49 = 2;
    _tlgWriteActivityAutoStop<0,5>(&dword_18005A000, &ActivityId);
  }
  return 0;
}

```

## disassembly

```asm
0x1800165e0  mov     [rsp-8+arg_18], rbx
0x1800165e5  push    rbp
0x1800165e6  push    rsi
0x1800165e7  push    rdi
0x1800165e8  push    r12
0x1800165ea  push    r13
0x1800165ec  push    r14
0x1800165ee  push    r15
0x1800165f0  lea     rbp, [rsp-27h]
0x1800165f5  sub     rsp, 0E0h
0x1800165fc  mov     rax, cs:__security_cookie
0x180016603  xor     rax, rsp
0x180016606  mov     [rbp+57h+var_38], rax
0x18001660a  mov     r12, r8
0x18001660d  mov     r15, rdx
0x180016610  mov     rbx, rcx
0x180016613  xor     r14d, r14d
0x180016616  mov     [rbp+57h+var_C0], r14d
0x18001661a  mov     [rbp+57h+var_90], r14d
0x18001661e  mov     [rbp+57h+var_8C], r14b
0x180016622  mov     eax, cs:dword_18005A000
0x180016628  cmp     eax, 5
0x18001662b  jbe     short loc_18001663D
0x18001662d  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x180016631  lea     ecx, [r14+3]; ControlCode
0x180016635  call    cs:__imp_EventActivityIdControl
0x18001663b  jmp     short loc_180016644
0x18001663d  xorps   xmm0, xmm0
0x180016640  movups  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x180016644  mov     [rbp+57h+var_90], 1
0x18001664b  mov     eax, cs:dword_18005A000
0x180016651  cmp     eax, 5
0x180016654  jbe     short loc_1800166A5
0x180016656  cmp     [rbp+57h+var_8C], r14b
0x18001665a  jz      short loc_18001667A
0x18001665c  cmp     [rbp+57h+var_78], r14d
0x180016660  jnz     short loc_180016674
0x180016662  cmp     [rbp+57h+var_74], r14d
0x180016666  jnz     short loc_180016674
0x180016668  cmp     [rbp+57h+var_70], r14d
0x18001666c  jnz     short loc_180016674
0x18001666e  cmp     [rbp+57h+var_6C], r14d
0x180016672  jz      short loc_18001667A
0x180016674  lea     r9, [rbp+57h+var_78]
0x180016678  jmp     short loc_18001667D
0x18001667a  mov     r9, r14
0x18001667d  lea     rax, [rbp+57h+var_68]
0x180016681  mov     [rsp+110h+pvData], rax
0x180016686  mov     dword ptr [rsp+110h+pdwType], 2
0x18001668e  lea     r8, [rbp+57h+ActivityId]
0x180016692  lea     rdx, byte_18004E88D
0x180016699  lea     rcx, dword_18005A000
0x1800166a0  call    _tlgWriteTransfer_EventWriteTransfer
0x1800166a5  lea     rax, [rbp+57h+var_90]
0x1800166a9  mov     [rbp+57h+var_B8], rax
0x1800166ad  lea     rax, [rbp+57h+var_C0]
0x1800166b1  mov     [rbp+57h+var_B0], rax
0x1800166b5  mov     [rbp+57h+var_A8], 1
0x1800166b9  test    r15, r15
0x1800166bc  jz      loc_180016C10
0x1800166c2  mov     esi, 7FFFFFFFh
0x1800166c7  mov     r8d, esi
0x1800166ca  mov     rax, r15
0x1800166cd  cmp     [rax], r14w
0x1800166d1  jz      short loc_1800166DD
0x1800166d3  add     rax, 2
0x1800166d7  sub     r8, 1
0x1800166db  jnz     short loc_1800166CD
0x1800166dd  mov     rax, r8
0x1800166e0  neg     rax
0x1800166e3  sbb     edx, edx
0x1800166e5  not     edx
0x1800166e7  mov     edi, 80070057h
0x1800166ec  and     edx, edi
0x1800166ee  mov     rax, r8
0x1800166f1  mov     rcx, rsi
0x1800166f4  sub     rcx, r8
0x1800166f7  neg     rax
0x1800166fa  sbb     r9, r9
0x1800166fd  and     r9, rcx
0x180016700  test    r8, r8
0x180016703  jz      loc_180016C15
0x180016709  mov     [rbp+57h+var_C0], edx
0x18001670c  lea     r13, [r9+1]
0x180016710  mov     eax, 2
0x180016715  mul     r13
0x180016718  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001671f  cmovb   rax, rcx
0x180016723  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001672a  mov     rcx, rax; unsigned __int64
0x18001672d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180016732  mov     r14, rax
0x180016735  cmp     rax, [rbx+20h]
0x180016739  jz      short loc_18001674B
0x18001673b  mov     rcx, [rbx+20h]
0x18001673f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180016745  mov     [rbx+20h], r14
0x180016749  jmp     short loc_18001674F
0x18001674b  mov     r14, [rbx+20h]
0x18001674f  xor     eax, eax
0x180016751  test    r14, r14
0x180016754  jz      loc_180016BD0
0x18001675a  mov     r8, r15; unsigned __int16 *
0x18001675d  mov     rdx, r13; unsigned __int64
0x180016760  mov     rcx, r14; unsigned __int16 *
0x180016763  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016768  mov     [rbp+57h+var_C0], eax
0x18001676b  xor     r14d, r14d
0x18001676e  test    eax, eax
0x180016770  jns     short loc_1800167DA
0x180016772  mov     eax, cs:dword_18005A000
0x180016778  cmp     eax, 2
0x18001677b  jbe     short loc_1800167BE
0x18001677d  mov     eax, [rbp+57h+var_C0]
0x180016780  mov     dword ptr [rbp+57h+Data], eax
0x180016783  lea     rax, [rbp+57h+Data]
0x180016787  mov     [rbp+57h+var_48], rax
0x18001678b  mov     [rbp+57h+var_40], 4
0x180016793  lea     rax, [rbp+57h+var_68]
0x180016797  mov     [rsp+110h+pvData], rax
0x18001679c  mov     dword ptr [rsp+110h+pdwType], 3
0x1800167a4  xor     r9d, r9d
0x1800167a7  lea     r8, [rbp+57h+ActivityId]
0x1800167ab  lea     rdx, byte_18004E59D
0x1800167b2  lea     rcx, dword_18005A000
0x1800167b9  call    _tlgWriteTransfer_EventWriteTransfer
0x1800167be  mov     ebx, [rbp+57h+var_C0]
0x1800167c1  cmp     [rbp+57h+var_A8], r14b
0x1800167c5  jz      short loc_1800167D5
0x1800167c7  mov     [rbp+57h+var_A8], r14b
0x1800167cb  lea     rcx, [rbp+57h+var_B8]
0x1800167cf  call    _lambda_ef616486a7395329213daa9d56ea1427___operator__
0x1800167d4  nop
0x1800167d5  jmp     loc_180016C7B
0x1800167da  test    r12, r12
0x1800167dd  jz      loc_180016B63
0x1800167e3  mov     rdx, rsi
0x1800167e6  mov     rax, r12
0x1800167e9  mov     r15d, 2
0x1800167ef  lea     r13d, [r15-1]
0x1800167f3  cmp     [rax], r14w
0x1800167f7  jz      short loc_180016801
0x1800167f9  add     rax, r15
0x1800167fc  sub     rdx, r13
0x1800167ff  jnz     short loc_1800167F3
0x180016801  mov     rax, rdx
0x180016804  neg     rax
0x180016807  sbb     ecx, ecx
0x180016809  not     ecx
0x18001680b  and     ecx, edi
0x18001680d  mov     rax, rdx
0x180016810  sub     rsi, rdx
0x180016813  neg     rax
0x180016816  sbb     r8, r8
0x180016819  and     r8, rsi
0x18001681c  test    rdx, rdx
0x18001681f  jz      loc_180016B65
0x180016825  mov     [rbp+57h+var_C0], ecx
0x180016828  lea     rsi, [r8+1]
0x18001682c  mov     rax, r15
0x18001682f  mul     rsi
0x180016832  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180016839  cmovb   rax, rcx
0x18001683d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180016844  mov     rcx, rax; unsigned __int64
0x180016847  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001684c  mov     rdi, rax
0x18001684f  cmp     rax, [rbx+28h]
0x180016853  jz      short loc_180016865
0x180016855  mov     rcx, [rbx+28h]
0x180016859  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001685f  mov     [rbx+28h], rdi
0x180016863  jmp     short loc_180016869
0x180016865  mov     rdi, [rbx+28h]
0x180016869  test    rdi, rdi
0x18001686c  jz      loc_180016B35
0x180016872  mov     r8, r12; unsigned __int16 *
0x180016875  mov     rdx, rsi; unsigned __int64
0x180016878  mov     rcx, rdi; unsigned __int16 *
0x18001687b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016880  mov     [rbp+57h+var_C0], eax
0x180016883  test    eax, eax
0x180016885  jns     short loc_1800168FD
0x180016887  mov     eax, cs:dword_18005A000
0x18001688d  cmp     eax, r15d
0x180016890  jbe     short loc_1800168D3
0x180016892  mov     eax, [rbp+57h+var_C0]
0x180016895  mov     dword ptr [rbp+57h+Data], eax
0x180016898  lea     rax, [rbp+57h+Data]
0x18001689c  mov     [rbp+57h+var_48], rax
0x1800168a0  mov     [rbp+57h+var_40], 4
0x1800168a8  lea     rax, [rbp+57h+var_68]
0x1800168ac  mov     [rsp+110h+pvData], rax
0x1800168b1  mov     dword ptr [rsp+110h+pdwType], 3
0x1800168b9  xor     r9d, r9d
0x1800168bc  lea     r8, [rbp+57h+ActivityId]
0x1800168c0  lea     rdx, word_18004F05A
0x1800168c7  lea     rcx, dword_18005A000
0x1800168ce  call    _tlgWriteTransfer_EventWriteTransfer
0x1800168d3  mov     ebx, [rbp+57h+var_C0]
0x1800168d6  cmp     [rbp+57h+var_A8], r14b
0x1800168da  jz      short loc_1800168EA
0x1800168dc  mov     [rbp+57h+var_A8], r14b
0x1800168e0  lea     rcx, [rbp+57h+var_B8]
0x1800168e4  call    _lambda_ef616486a7395329213daa9d56ea1427___operator__
0x1800168e9  nop
0x1800168ea  cmp     [rbp+57h+var_90], r13d
0x1800168ee  jnz     loc_180016C98
0x1800168f4  mov     [rbp+57h+var_90], r15d
0x1800168f8  jmp     loc_180016C88
0x1800168fd  lea     rcx, [rbx+90h]
0x180016904  mov     dword ptr [rsp+110h+phkResult], r14d
0x180016909  mov     dword ptr [rsp+110h+pcbData], r14d
0x18001690e  mov     [rsp+110h+pvData], r14
0x180016913  mov     [rsp+110h+pdwType], rbx
0x180016918  lea     r9, ?OnShutdownInProgress@CMVEngine@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; CMVEngine::OnShutdownInProgress(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x18001691f  xor     r8d, r8d
0x180016922  mov     rdx, cs:WNF_SYS_SHUTDOWN_IN_PROGRESS
0x180016929  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x18001692f  mov     edx, 80000000h
0x180016934  lea     ecx, [rax+rdx]
0x180016937  test    edx, ecx
0x180016939  jnz     short loc_180016975
0x18001693b  cmp     eax, 0C0000034h
0x180016940  jz      short loc_180016975
0x180016942  mov     ecx, eax; Status
0x180016944  call    cs:__imp_RtlNtStatusToDosError
0x18001694a  mov     ebx, eax
0x18001694c  test    eax, eax
0x18001694e  jle     short loc_180016959
0x180016950  movzx   ebx, ax
0x180016953  or      ebx, 80070000h
0x180016959  mov     [rbp+57h+var_C0], ebx
0x18001695c  cmp     [rbp+57h+var_A8], r14b
0x180016960  jz      short loc_180016970
0x180016962  mov     [rbp+57h+var_A8], r14b
0x180016966  lea     rcx, [rbp+57h+var_B8]
0x18001696a  call    _lambda_ef616486a7395329213daa9d56ea1427___operator__
0x18001696f  nop
0x180016970  jmp     loc_1800168EA
0x180016975  lea     rdx, [rbx+0D0h]
0x18001697c  cmp     [rdx], r14
0x18001697f  jnz     short loc_1800169F8
0x180016981  mov     rcx, rbx
0x180016984  call    ?CreateContext@ProvStateContext@@SAJPEAUIMVEngine@@AEAV?$unique_ptr@VProvStateContext@@U?$default_delete@VProvStateContext@@@std@@@std@@@Z; ProvStateContext::CreateContext(IMVEngine *,std::unique_ptr<ProvStateContext> &)
0x180016989  mov     [rbp+57h+var_C0], eax
0x18001698c  test    eax, eax
0x18001698e  jns     short loc_1800169F8
0x180016990  mov     eax, cs:dword_18005A000
0x180016996  cmp     eax, r15d
0x180016999  jbe     short loc_1800169DC
0x18001699b  mov     eax, [rbp+57h+var_C0]
0x18001699e  mov     dword ptr [rbp+57h+Data], eax
0x1800169a1  lea     rax, [rbp+57h+Data]
0x1800169a5  mov     [rbp+57h+var_48], rax
0x1800169a9  mov     [rbp+57h+var_40], 4
0x1800169b1  lea     rax, [rbp+57h+var_68]
0x1800169b5  mov     [rsp+110h+pvData], rax
0x1800169ba  mov     dword ptr [rsp+110h+pdwType], 3
0x1800169c2  xor     r9d, r9d
0x1800169c5  lea     r8, [rbp+57h+ActivityId]
0x1800169c9  lea     rdx, byte_18004F893
0x1800169d0  lea     rcx, dword_18005A000
0x1800169d7  call    _tlgWriteTransfer_EventWriteTransfer
0x1800169dc  mov     ebx, [rbp+57h+var_C0]
0x1800169df  cmp     [rbp+57h+var_A8], r14b
0x1800169e3  jz      short loc_1800169F3
0x1800169e5  mov     [rbp+57h+var_A8], r14b
0x1800169e9  lea     rcx, [rbp+57h+var_B8]
0x1800169ed  call    _lambda_ef616486a7395329213daa9d56ea1427___operator__
0x1800169f2  nop
0x1800169f3  jmp     loc_1800168EA
0x1800169f8  mov     rcx, rbx; this
0x1800169fb  call    ?LoadSequenceHive@CMVEngine@@AEAAJXZ; CMVEngine::LoadSequenceHive(void)
0x180016a00  mov     [rbp+57h+var_9C], r14d
0x180016a04  mov     [rbp+57h+var_A0], 4
0x180016a0b  lea     rax, [rbp+57h+var_A0]
0x180016a0f  mov     [rsp+110h+pcbData], rax; pcbData
0x180016a14  lea     rax, [rbp+57h+var_9C]
0x180016a18  mov     [rsp+110h+pvData], rax; pvData
0x180016a1d  mov     [rsp+110h+pdwType], r14; pdwType
0x180016a22  mov     r9d, 10h; dwFlags
0x180016a28  xor     r8d, r8d; lpValue
0x180016a2b  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Provisioning\\Firs"...
0x180016a32  mov     rdi, 0FFFFFFFF80000002h
0x180016a39  mov     rcx, rdi; hkey
0x180016a3c  call    cs:__imp_RegGetValueW
0x180016a42  test    eax, eax
0x180016a44  jnz     short loc_180016A52
0x180016a46  mov     [rbx+0BCh], r14d
0x180016a4d  jmp     loc_180016B00
0x180016a52  mov     [rbx+0BCh], r13d
0x180016a59  mov     eax, cs:dword_18005A000
0x180016a5f  cmp     eax, 4
0x180016a62  jbe     short loc_180016A8B
0x180016a64  lea     rax, [rbp+57h+var_68]
0x180016a68  mov     [rsp+110h+pvData], rax
0x180016a6d  mov     dword ptr [rsp+110h+pdwType], r15d
0x180016a72  xor     r9d, r9d
0x180016a75  xor     r8d, r8d
  ... truncated ...
```
