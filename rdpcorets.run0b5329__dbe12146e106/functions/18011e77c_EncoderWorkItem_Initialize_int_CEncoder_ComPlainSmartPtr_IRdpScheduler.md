# EncoderWorkItem::Initialize(int,CEncoder *,ComPlainSmartPtr<IRdpScheduler>)

- ea: `0x18011e77c`
- end: `0x18011eaa6`
- name: `?Initialize@EncoderWorkItem@@QEAAJHPEAVCEncoder@@V?$ComPlainSmartPtr@UIRdpScheduler@@@@@Z`
- size: `810`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800f314c`

## callees

- `0x1800071c0`
- `0x1800071f0`
- `0x18002e600`
- `0x1800598d0`
- `0x180072abc`
- `0x18011e77c`
- `0x18011ee0c`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18011e95e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18011e95e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18011e9b9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18011e9b9`
- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x18011e9d1`
- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x18011e9d1`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18011e7cb`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18011e815`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18011e867`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18011e8a3`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18011e908`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18011e996`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18011ea18`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18011ea59`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18011e7cb`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18011e815`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18011e867`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18011e8a3`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18011e908`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18011e996`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18011ea18`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18011ea59`

## string_xrefs

- `0x18011e8b6`: `EncoderWorkItem is already initialized`
- `0x18011e91b`: `EncoderWorkItem: CriticalSection is already initialized`
- `0x18011e9a9`: `Unable to Create Event for completion`

## pseudocode

```c
__int64 __fastcall EncoderWorkItem::Initialize(unsigned __int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  int v6; // ebp
  PVOID *v8; // rax
  int v9; // ebx
  int ActivityIdPrefix; // eax
  int v11; // eax
  int v12; // edx
  const char *v13; // rcx
  int v14; // edi
  int v15; // eax
  int v16; // eax
  _QWORD *v17; // rbx
  HANDLE EventW; // rax
  int v19; // eax
  int v20; // eax
  int v21; // ebx
  int v22; // eax
  int v23; // r8d
  __int64 v25; // [rsp+28h] [rbp-60h]

  v6 = a2;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v9 = *(_DWORD *)(a1 + 56);
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(a1);
    WPP_SF_DSd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (unsigned int)&WPP_8367e28867c53ac09f374451e226c5e8_Traceguids,
      ActivityIdPrefix,
      (__int64)L"EncoderWorkItem::Initialize",
      v9);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a3 )
  {
    if ( v8 == &WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 8) == 0 || *((_BYTE *)v8 + 25) < 2u )
      goto LABEL_11;
    v11 = RdpX_GetActivityIdPrefix(a1);
    v12 = 11;
    v13 = "pEncoder";
LABEL_10:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v12,
      (unsigned int)&WPP_8367e28867c53ac09f374451e226c5e8_Traceguids,
      v11,
      (__int64)v13);
    v8 = (PVOID *)WPP_GLOBAL_Control;
LABEL_11:
    v14 = -2147467261;
    goto LABEL_42;
  }
  if ( !*a4 )
  {
    if ( v8 == &WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 8) == 0 || *((_BYTE *)v8 + 25) < 2u )
      goto LABEL_11;
    v11 = RdpX_GetActivityIdPrefix(a1);
    v12 = 12;
    v13 = "spScheduler";
    goto LABEL_10;
  }
  if ( !*(_DWORD *)(a1 + 88) )
  {
    if ( *(_DWORD *)(a1 + 152) )
    {
      v14 = -2147467259;
      if ( v8 == &WPP_GLOBAL_Control )
        goto LABEL_46;
      if ( (*((_BYTE *)v8 + 28) & 8) == 0 || *((_BYTE *)v8 + 25) < 2u )
        goto LABEL_42;
      v16 = RdpX_GetActivityIdPrefix(a1);
      LODWORD(v25) = -2147467259;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)&WPP_8367e28867c53ac09f374451e226c5e8_Traceguids,
        v16,
        (__int64)"EncoderWorkItem: CriticalSection is already initialized",
        v25);
    }
    else
    {
      *(_DWORD *)(a1 + 88) = 3;
      v17 = (_QWORD *)(a1 + 96);
      *(_DWORD *)(a1 + 56) = v6;
      *(_QWORD *)(a1 + 72) = a3;
      if ( *a4 != *(_QWORD *)(a1 + 96) )
      {
        TCntPtr<IRdpSQMLogger>::SafeRelease(a1 + 96, a2, a3);
        *v17 = *a4;
        TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(a1 + 96);
      }
      EventW = CreateEventW(0, 0, 0, 0);
      *(_QWORD *)(a1 + 64) = EventW;
      if ( EventW )
      {
        InitializeCriticalSection((LPCRITICAL_SECTION)(a1 + 112));
        *(_DWORD *)(a1 + 152) = 1;
        InitializeConditionVariable((PCONDITION_VARIABLE)(a1 + 160));
        v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int64))(*(_QWORD *)*v17 + 40LL))(
                *v17,
                (a1 + 48) & ((unsigned __int128)-(__int128)a1 >> 64),
                a1 + 104);
        if ( v14 >= 0 )
        {
          *(_DWORD *)(a1 + 28) |= 2u;
          v14 = 0;
          *(_DWORD *)(a1 + 88) = 1;
        }
        else
        {
          v8 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
            goto LABEL_46;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_42;
          v20 = RdpX_GetActivityIdPrefix(a1);
          LODWORD(v25) = v14;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            16,
            (unsigned int)&WPP_8367e28867c53ac09f374451e226c5e8_Traceguids,
            v20,
            (__int64)"Unable to register worker with RDP8 scheduler",
            v25);
        }
      }
      else
      {
        v14 = -2147024882;
        v8 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          goto LABEL_46;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_42;
        v19 = RdpX_GetActivityIdPrefix(a1);
        LODWORD(v25) = -2147024882;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          (unsigned int)&WPP_8367e28867c53ac09f374451e226c5e8_Traceguids,
          v19,
          (__int64)"Unable to Create Event for completion",
          v25);
      }
    }
    goto LABEL_41;
  }
  v14 = -2147418113;
  if ( v8 == &WPP_GLOBAL_Control )
    goto LABEL_46;
  if ( (*((_BYTE *)v8 + 28) & 8) != 0 && *((_BYTE *)v8 + 25) >= 2u )
  {
    v15 = RdpX_GetActivityIdPrefix(a1);
    LODWORD(v25) = -2147418113;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      (unsigned int)&WPP_8367e28867c53ac09f374451e226c5e8_Traceguids,
      v15,
      (__int64)"EncoderWorkItem is already initialized",
      v25);
LABEL_41:
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_42:
  if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x100) != 0 && *((_BYTE *)v8 + 25) >= 5u )
  {
    v21 = *(_DWORD *)(a1 + 56);
    v22 = RdpX_GetActivityIdPrefix(a1);
    WPP_SF_DSdd(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, v23, v22, (__int64)L"EncoderWorkItem::Initialize", v21, v14);
  }
LABEL_46:
  TCntPtr<IRdpSQMLogger>::SafeRelease(a4, a2, a3);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18011e77c  push    rbx
0x18011e77e  push    rbp
0x18011e77f  push    rsi
0x18011e780  push    rdi
0x18011e781  push    r12
0x18011e783  push    r13
0x18011e785  push    r14
0x18011e787  push    r15
0x18011e789  sub     rsp, 48h
0x18011e78d  mov     r14, r9
0x18011e790  mov     rdi, r8
0x18011e793  mov     ebp, edx
0x18011e795  mov     rsi, rcx
0x18011e798  mov     rax, cs:WPP_GLOBAL_Control
0x18011e79f  lea     r12, WPP_GLOBAL_Control
0x18011e7a6  lea     r15, aEncoderworkite; "EncoderWorkItem::Initialize"
0x18011e7ad  lea     r13, WPP_8367e28867c53ac09f374451e226c5e8_Traceguids
0x18011e7b4  cmp     rax, r12
0x18011e7b7  jz      short loc_18011E7FC
0x18011e7b9  test    dword ptr [rax+1Ch], 100h
0x18011e7c0  jz      short loc_18011E7FC
0x18011e7c2  cmp     byte ptr [rax+19h], 5
0x18011e7c6  jb      short loc_18011E7FC
0x18011e7c8  mov     ebx, [rcx+38h]
0x18011e7cb  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18011e7d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18011e7d8  mov     edx, 0Ah
0x18011e7dd  mov     dword ptr [rsp+88h+var_60], ebx
0x18011e7e1  mov     r9d, eax
0x18011e7e4  mov     r8, r13
0x18011e7e7  mov     [rsp+88h+var_68], r15
0x18011e7ec  mov     rcx, [rcx+10h]
0x18011e7f0  call    WPP_SF_DSd
0x18011e7f5  mov     rax, cs:WPP_GLOBAL_Control
0x18011e7fc  xor     r15d, r15d
0x18011e7ff  test    rdi, rdi
0x18011e802  jnz     short loc_18011E851
0x18011e804  cmp     rax, r12
0x18011e807  jz      short loc_18011E847
0x18011e809  test    byte ptr [rax+1Ch], 8
0x18011e80d  jz      short loc_18011E847
0x18011e80f  cmp     byte ptr [rax+19h], 2
0x18011e813  jb      short loc_18011E847
0x18011e815  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18011e81b  lea     edx, [rdi+0Bh]
0x18011e81e  lea     rcx, aPencoder; "pEncoder"
0x18011e825  mov     [rsp+88h+var_68], rcx
0x18011e82a  mov     r9d, eax
0x18011e82d  mov     rcx, cs:WPP_GLOBAL_Control
0x18011e834  mov     r8, r13
0x18011e837  mov     rcx, [rcx+10h]
0x18011e83b  call    WPP_SF_Ds
0x18011e840  mov     rax, cs:WPP_GLOBAL_Control
0x18011e847  mov     edi, 80004003h
0x18011e84c  jmp     loc_18011EA42
0x18011e851  cmp     [r14], r15
0x18011e854  jnz     short loc_18011E87B
0x18011e856  cmp     rax, r12
0x18011e859  jz      short loc_18011E847
0x18011e85b  test    byte ptr [rax+1Ch], 8
0x18011e85f  jz      short loc_18011E847
0x18011e861  cmp     byte ptr [rax+19h], 2
0x18011e865  jb      short loc_18011E847
0x18011e867  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18011e86d  mov     edx, 0Ch
0x18011e872  lea     rcx, aSpscheduler; "spScheduler"
0x18011e879  jmp     short loc_18011E825
0x18011e87b  cmp     [rsi+58h], r15d
0x18011e87f  jz      short loc_18011E8DD
0x18011e881  mov     edi, 8000FFFFh
0x18011e886  cmp     rax, r12
0x18011e889  jz      loc_18011EA8B
0x18011e88f  test    byte ptr [rax+1Ch], 8
0x18011e893  jz      loc_18011EA42
0x18011e899  cmp     byte ptr [rax+19h], 2
0x18011e89d  jb      loc_18011EA42
0x18011e8a3  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18011e8a9  mov     edx, 0Dh
0x18011e8ae  mov     dword ptr [rsp+88h+var_60], 8000FFFFh
0x18011e8b6  lea     rcx, aEncoderworkite_3; "EncoderWorkItem is already initialized"
0x18011e8bd  mov     [rsp+88h+var_68], rcx
0x18011e8c2  mov     r9d, eax
0x18011e8c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18011e8cc  mov     r8, r13
0x18011e8cf  mov     rcx, [rcx+10h]
0x18011e8d3  call    WPP_SF_DsD
0x18011e8d8  jmp     loc_18011EA3B
0x18011e8dd  cmp     [rsi+98h], r15d
0x18011e8e4  jz      short loc_18011E924
0x18011e8e6  mov     edi, 80004005h
0x18011e8eb  cmp     rax, r12
0x18011e8ee  jz      loc_18011EA8B
0x18011e8f4  test    byte ptr [rax+1Ch], 8
0x18011e8f8  jz      loc_18011EA42
0x18011e8fe  cmp     byte ptr [rax+19h], 2
0x18011e902  jb      loc_18011EA42
0x18011e908  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18011e90e  mov     edx, 0Eh
0x18011e913  mov     dword ptr [rsp+88h+var_60], 80004005h
0x18011e91b  lea     rcx, aEncoderworkite_4; "EncoderWorkItem: CriticalSection is alr"...
0x18011e922  jmp     short loc_18011E8BD
0x18011e924  mov     dword ptr [rsi+58h], 3
0x18011e92b  lea     rbx, [rsi+60h]
0x18011e92f  mov     [rsi+38h], ebp
0x18011e932  mov     [rsi+48h], rdi
0x18011e936  mov     rax, [rbx]
0x18011e939  cmp     [r14], rax
0x18011e93c  jz      short loc_18011E954
0x18011e93e  mov     rcx, rbx
0x18011e941  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x18011e946  mov     rax, [r14]
0x18011e949  mov     rcx, rbx
0x18011e94c  mov     [rbx], rax
0x18011e94f  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18011e954  xor     r9d, r9d; lpName
0x18011e957  xor     r8d, r8d; bInitialState
0x18011e95a  xor     edx, edx; bManualReset
0x18011e95c  xor     ecx, ecx; lpEventAttributes
0x18011e95e  call    cs:__imp_CreateEventW
0x18011e964  mov     [rsi+40h], rax
0x18011e968  test    rax, rax
0x18011e96b  jnz     short loc_18011E9B5
0x18011e96d  mov     edi, 8007000Eh
0x18011e972  mov     rax, cs:WPP_GLOBAL_Control
0x18011e979  cmp     rax, r12
0x18011e97c  jz      loc_18011EA8B
0x18011e982  test    byte ptr [rax+1Ch], 8
0x18011e986  jz      loc_18011EA42
0x18011e98c  cmp     byte ptr [rax+19h], 2
0x18011e990  jb      loc_18011EA42
0x18011e996  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18011e99c  mov     edx, 0Fh
0x18011e9a1  mov     dword ptr [rsp+88h+var_60], 8007000Eh
0x18011e9a9  lea     rcx, aUnableToCreate; "Unable to Create Event for completion"
0x18011e9b0  jmp     loc_18011E8BD
0x18011e9b5  lea     rcx, [rsi+70h]; lpCriticalSection
0x18011e9b9  call    cs:__imp_InitializeCriticalSection
0x18011e9bf  mov     ebp, 1
0x18011e9c4  lea     rcx, [rsi+0A0h]; ConditionVariable
0x18011e9cb  mov     [rsi+98h], ebp
0x18011e9d1  call    cs:__imp_InitializeConditionVariable
0x18011e9d7  mov     rcx, [rbx]
0x18011e9da  lea     r9, [rsi+30h]
0x18011e9de  mov     rax, rsi
0x18011e9e1  lea     r8, [rsi+68h]
0x18011e9e5  neg     rax
0x18011e9e8  mov     r10, [rcx]
0x18011e9eb  sbb     rdx, rdx
0x18011e9ee  and     rdx, r9
0x18011e9f1  mov     rax, [r10+28h]
0x18011e9f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011e9fa  mov     edi, eax
0x18011e9fc  test    eax, eax
0x18011e9fe  jns     short loc_18011EA31
0x18011ea00  mov     rax, cs:WPP_GLOBAL_Control
0x18011ea07  cmp     rax, r12
0x18011ea0a  jz      short loc_18011EA8B
0x18011ea0c  test    byte ptr [rax+1Ch], 8
0x18011ea10  jz      short loc_18011EA42
0x18011ea12  cmp     byte ptr [rax+19h], 2
0x18011ea16  jb      short loc_18011EA42
0x18011ea18  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18011ea1e  lea     edx, [rbp+0Fh]
0x18011ea21  mov     dword ptr [rsp+88h+var_60], edi
0x18011ea25  lea     rcx, aUnableToRegist; "Unable to register worker with RDP8 sch"...
0x18011ea2c  jmp     loc_18011E8BD
0x18011ea31  or      dword ptr [rsi+1Ch], 2
0x18011ea35  mov     edi, r15d
0x18011ea38  mov     [rsi+58h], ebp
0x18011ea3b  mov     rax, cs:WPP_GLOBAL_Control
0x18011ea42  cmp     rax, r12
0x18011ea45  jz      short loc_18011EA8B
0x18011ea47  test    dword ptr [rax+1Ch], 100h
0x18011ea4e  jz      short loc_18011EA8B
0x18011ea50  cmp     byte ptr [rax+19h], 5
0x18011ea54  jb      short loc_18011EA8B
0x18011ea56  mov     ebx, [rsi+38h]
0x18011ea59  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18011ea5f  lea     rcx, aEncoderworkite; "EncoderWorkItem::Initialize"
0x18011ea66  mov     [rsp+88h+var_58], edi
0x18011ea6a  mov     dword ptr [rsp+88h+var_60], ebx
0x18011ea6e  mov     edx, 12h
0x18011ea73  mov     [rsp+88h+var_68], rcx
0x18011ea78  mov     r9d, eax
0x18011ea7b  mov     rcx, cs:WPP_GLOBAL_Control
0x18011ea82  mov     rcx, [rcx+10h]
0x18011ea86  call    WPP_SF_DSdd
0x18011ea8b  mov     rcx, r14
0x18011ea8e  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x18011ea93  mov     eax, edi
0x18011ea95  add     rsp, 48h
0x18011ea99  pop     r15
0x18011ea9b  pop     r14
0x18011ea9d  pop     r13
0x18011ea9f  pop     r12
0x18011eaa1  pop     rdi
0x18011eaa2  pop     rsi
0x18011eaa3  pop     rbp
0x18011eaa4  pop     rbx
0x18011eaa5  retn
```
