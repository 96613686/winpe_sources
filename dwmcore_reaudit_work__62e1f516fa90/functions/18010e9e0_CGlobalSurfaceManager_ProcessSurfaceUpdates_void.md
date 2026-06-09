# CGlobalSurfaceManager::ProcessSurfaceUpdates(void)

- ea: `0x18010e9e0`
- end: `0x18010ed1e`
- name: `?ProcessSurfaceUpdates@CGlobalSurfaceManager@@UEAAJXZ`
- size: `830`
- prototype: `__int64 __fastcall(CGlobalSurfaceManager *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180042de0`
- `0x18010e9e0`
- `0x18010fd50`
- `0x180110480`
- `0x180228490`
- `0x1802b6010`

## import_xrefs

- `ntdll!RtlLookupElementGenericTable` at `0x18010eb45`
- `ntdll!RtlLookupElementGenericTable` at `0x18010eb45`
- `win32u!NtDCompositionGetFrameSurfaceUpdates` at `0x18010ea7d`
- `win32u!NtDCompositionGetFrameSurfaceUpdates` at `0x18010ec6e`
- `win32u!NtDCompositionGetFrameSurfaceUpdates` at `0x18010ea7d`
- `win32u!NtDCompositionGetFrameSurfaceUpdates` at `0x18010ec6e`

## pseudocode

```c
__int64 __fastcall CGlobalSurfaceManager::ProcessSurfaceUpdates(CGlobalSurfaceManager *this, __int64 a2, __int64 a3)
{
  int v3; // r15d
  int v4; // edi
  int v6; // eax
  __int64 v7; // r8
  __int64 v8; // rcx
  int FrameSurfaceUpdates; // eax
  __int64 v10; // r8
  int v11; // ebx
  unsigned int v12; // esi
  __int64 v13; // rcx
  __int64 v15; // r13
  _QWORD *v16; // rax
  __int64 v17; // r15
  int v18; // eax
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rax
  unsigned int v22; // [rsp+30h] [rbp-39h] BYREF
  int v23; // [rsp+38h] [rbp-31h] BYREF
  int v24; // [rsp+40h] [rbp-29h] BYREF
  __int64 v25; // [rsp+48h] [rbp-21h] BYREF
  __int64 v26; // [rsp+50h] [rbp-19h] BYREF
  _QWORD Buffer[2]; // [rsp+58h] [rbp-11h] BYREF
  _BYTE v28[16]; // [rsp+68h] [rbp-1h] BYREF
  int *v29; // [rsp+78h] [rbp+Fh]
  __int64 v30; // [rsp+80h] [rbp+17h]
  __int64 *v31; // [rsp+88h] [rbp+1Fh]
  __int64 v32; // [rsp+90h] [rbp+27h]

  v22 = 0;
  v3 = 0;
  v24 = 0;
  v4 = 0;
  v23 = 0;
  v6 = CGlobalSurfaceManager::ProcessLegacyTokens(this, a2, a3);
  if ( v6 < 0 )
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v6, 0xA1u, 0);
  if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x10) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Dwm_Core_Provider_Context,
      EVTDESC_MILEVENT_MEDIA_UCE_PROCESSSURFACEUPDATES_Start,
      v7,
      1,
      Buffer);
  v8 = 0;
  if ( g_pComposition )
    v8 = *((_QWORD *)g_pComposition + 110);
  v25 = v8;
  FrameSurfaceUpdates = NtDCompositionGetFrameSurfaceUpdates(&v25, &v22, &v24);
  if ( FrameSurfaceUpdates >= 0 )
  {
    v11 = 0;
    goto LABEL_9;
  }
  v11 = FrameSurfaceUpdates | 0x10000000;
  MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_180329D50, 3u, FrameSurfaceUpdates | 0x10000000, 0x91u, 0);
  if ( v11 >= 0 )
  {
    while ( 1 )
    {
LABEL_9:
      v12 = 0;
      if ( v22 )
      {
        do
        {
          Buffer[1] = 0;
          v15 = *((_QWORD *)this + 13) + 376LL * v12;
          Buffer[0] = *(_QWORD *)(v15 + 4);
          v16 = RtlLookupElementGenericTable((PRTL_GENERIC_TABLE)((char *)this + 24), Buffer);
          if ( v16 )
          {
            v17 = v16[1];
            if ( v17 )
            {
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v17 + 8LL))(v16[1]);
              v18 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v17 + 128LL))(v17, v15);
              if ( v18 < 0 )
                MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v18, 0xBCu, 0);
              ++v4;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
            }
          }
          ++v12;
        }
        while ( v12 < v22 );
        v3 = v23;
      }
      if ( !v24 )
        break;
      v23 = ++v3;
      v19 = 0;
      if ( g_pComposition )
        v19 = *((_QWORD *)g_pComposition + 110);
      v26 = v19;
      v20 = NtDCompositionGetFrameSurfaceUpdates(&v26, &v22, &v24);
      if ( v20 < 0 )
      {
        v11 = v20 | 0x10000000;
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_180329D50, 3u, v20 | 0x10000000, 0x91u, 0);
        if ( v11 < 0 )
          break;
      }
      else
      {
        v11 = 0;
      }
    }
  }
  v13 = *(_QWORD *)(*((_QWORD *)g_pComposition + 708) + 24LL);
  if ( v13 )
  {
    v21 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 48LL))(v13);
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 48LL))(v21);
  }
  if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x10) != 0 )
  {
    LODWORD(v25) = v3;
    v29 = &v23;
    v23 = v4;
    v31 = &v25;
    v30 = 4;
    v32 = 4;
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Dwm_Core_Provider_Context,
      EVTDESC_MILEVENT_MEDIA_UCE_PROCESSSURFACEUPDATES_Stop,
      v10,
      3,
      v28);
  }
  dword_1803BADFC += v4;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18010e9e0  push    rbp
0x18010e9e2  push    rbx
0x18010e9e3  push    rdi
0x18010e9e4  push    r12
0x18010e9e6  push    r15
0x18010e9e8  lea     rbp, [rsp-37h]
0x18010e9ed  sub     rsp, 0A0h
0x18010e9f4  mov     rax, cs:__security_cookie
0x18010e9fb  xor     rax, rsp
0x18010e9fe  mov     [rbp+57h+var_28], rax
0x18010ea02  xor     r12d, r12d
0x18010ea05  mov     [rsp+0C0h+arg_18], r14
0x18010ea0d  mov     [rbp+57h+var_90], r12d
0x18010ea11  mov     r15d, r12d
0x18010ea14  mov     [rbp+57h+var_80], r12d
0x18010ea18  mov     edi, r12d
0x18010ea1b  mov     [rbp+57h+var_88], r12d
0x18010ea1f  mov     r14, rcx
0x18010ea22  call    ?ProcessLegacyTokens@CGlobalSurfaceManager@@AEAAJXZ; CGlobalSurfaceManager::ProcessLegacyTokens(void)
0x18010ea27  test    eax, eax
0x18010ea29  jns     short loc_18010EA4A
0x18010ea2b  mov     [rsp+0C0h+var_98], r12; void *
0x18010ea30  mov     r9d, eax; int
0x18010ea33  xor     r8d, r8d; unsigned int
0x18010ea36  mov     [rsp+0C0h+var_A0], 0A1h; unsigned int
0x18010ea3e  xor     edx, edx; int *
0x18010ea40  mov     ecx, 14h; unsigned int
0x18010ea45  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18010ea4a  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits, 10h
0x18010ea51  jnz     loc_18010EBCC
0x18010ea57  mov     rax, cs:?g_pComposition@@3PEAVCComposition@@EA; CComposition * g_pComposition
0x18010ea5e  mov     rcx, r12
0x18010ea61  test    rax, rax
0x18010ea64  jz      short loc_18010EA6D
0x18010ea66  mov     rcx, [rax+370h]
0x18010ea6d  mov     [rbp+57h+var_78], rcx
0x18010ea71  lea     r8, [rbp+57h+var_80]
0x18010ea75  lea     rcx, [rbp+57h+var_78]
0x18010ea79  lea     rdx, [rbp+57h+var_90]
0x18010ea7d  call    cs:__imp_NtDCompositionGetFrameSurfaceUpdates
0x18010ea83  mov     ebx, eax
0x18010ea85  test    eax, eax
0x18010ea87  js      loc_18010EC82
0x18010ea8d  mov     ebx, r12d
0x18010ea90  mov     [rsp+0C0h+arg_8], rsi
0x18010ea98  mov     [rsp+0C0h+arg_10], r13
0x18010eaa0  cmp     [rbp+57h+var_90], 0
0x18010eaa4  mov     esi, r12d
0x18010eaa7  ja      short loc_18010EB20
0x18010eaa9  cmp     [rbp+57h+var_80], 0
0x18010eaad  jnz     loc_18010EC41
0x18010eab3  mov     rsi, [rsp+0C0h+arg_8]
0x18010eabb  mov     r13, [rsp+0C0h+arg_10]
0x18010eac3  mov     rax, cs:?g_pComposition@@3PEAVCComposition@@EA; CComposition * g_pComposition
0x18010eaca  mov     r14, [rsp+0C0h+arg_18]
0x18010ead2  mov     rcx, [rax+1620h]
0x18010ead9  mov     rcx, [rcx+18h]
0x18010eadd  test    rcx, rcx
0x18010eae0  jnz     loc_18010ECF2
0x18010eae6  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits, 10h
0x18010eaed  jnz     loc_18010EBF3
0x18010eaf3  add     cs:dword_1803BADFC, edi
0x18010eaf9  mov     eax, ebx
0x18010eafb  mov     rcx, [rbp+57h+var_28]
0x18010eaff  xor     rcx, rsp; StackCookie
0x18010eb02  call    __security_check_cookie
0x18010eb07  add     rsp, 0A0h
0x18010eb0e  pop     r15
0x18010eb10  pop     r12
0x18010eb12  pop     rdi
0x18010eb13  pop     rbx
0x18010eb14  pop     rbp
0x18010eb15  retn
0x18010eb20  mov     eax, esi
0x18010eb22  lea     rdx, [rbp+57h+Buffer]; Buffer
0x18010eb26  imul    r13, rax, 178h
0x18010eb2d  lea     rcx, [r14+18h]; Table
0x18010eb31  mov     [rbp+57h+var_60], 0
0x18010eb39  add     r13, [r14+68h]
0x18010eb3d  mov     rax, [r13+4]
0x18010eb41  mov     [rbp+57h+Buffer], rax
0x18010eb45  call    cs:__imp_RtlLookupElementGenericTable
0x18010eb4b  test    rax, rax
0x18010eb4e  jz      short loc_18010EBB5
0x18010eb50  mov     r15, [rax+8]
0x18010eb54  test    r15, r15
0x18010eb57  jz      short loc_18010EBB5
0x18010eb59  mov     rax, [r15]
0x18010eb5c  mov     rcx, r15
0x18010eb5f  mov     rax, [rax+8]
0x18010eb63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010eb68  mov     rax, [r15]
0x18010eb6b  mov     rdx, r13
0x18010eb6e  mov     rcx, r15
0x18010eb71  mov     rax, [rax+80h]
0x18010eb78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010eb7d  test    eax, eax
0x18010eb7f  jns     short loc_18010EBA4
0x18010eb81  mov     [rsp+0C0h+var_98], 0; void *
0x18010eb8a  mov     r9d, eax; int
0x18010eb8d  xor     r8d, r8d; unsigned int
0x18010eb90  mov     [rsp+0C0h+var_A0], 0BCh; unsigned int
0x18010eb98  xor     edx, edx; int *
0x18010eb9a  mov     ecx, 14h; unsigned int
0x18010eb9f  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18010eba4  mov     rax, [r15]
0x18010eba7  inc     edi
0x18010eba9  mov     rcx, r15
0x18010ebac  mov     rax, [rax+10h]
0x18010ebb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010ebb5  inc     esi
0x18010ebb7  cmp     esi, [rbp+57h+var_90]
0x18010ebba  jb      loc_18010EB20
0x18010ebc0  mov     r15d, [rbp+57h+var_88]
0x18010ebc4  xor     r12d, r12d
0x18010ebc7  jmp     loc_18010EAA9
0x18010ebcc  lea     rax, [rbp+57h+Buffer]
0x18010ebd0  mov     r9d, 1
0x18010ebd6  lea     rdx, EVTDESC_MILEVENT_MEDIA_UCE_PROCESSSURFACEUPDATES_Start
0x18010ebdd  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18010ebe2  lea     rcx, Microsoft_Windows_Dwm_Core_Provider_Context
0x18010ebe9  call    McGenEventWrite_EventWriteTransfer
0x18010ebee  jmp     loc_18010EA57
0x18010ebf3  lea     rax, [rbp+57h+var_88]
0x18010ebf7  mov     dword ptr [rbp+57h+var_78], r15d
0x18010ebfb  mov     [rbp+57h+var_48], rax
0x18010ebff  lea     rdx, EVTDESC_MILEVENT_MEDIA_UCE_PROCESSSURFACEUPDATES_Stop
0x18010ec06  lea     rax, [rbp+57h+var_78]
0x18010ec0a  mov     [rbp+57h+var_88], edi
0x18010ec0d  mov     [rbp+57h+var_38], rax
0x18010ec11  lea     rcx, Microsoft_Windows_Dwm_Core_Provider_Context
0x18010ec18  lea     rax, [rbp+57h+var_58]
0x18010ec1c  mov     [rbp+57h+var_40], 4
0x18010ec24  mov     r9d, 3
0x18010ec2a  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18010ec2f  mov     [rbp+57h+var_30], 4
0x18010ec37  call    McGenEventWrite_EventWriteTransfer
0x18010ec3c  jmp     loc_18010EAF3
0x18010ec41  mov     rax, cs:?g_pComposition@@3PEAVCComposition@@EA; CComposition * g_pComposition
0x18010ec48  inc     r15d
0x18010ec4b  mov     [rbp+57h+var_88], r15d
0x18010ec4f  mov     rcx, r12
0x18010ec52  test    rax, rax
0x18010ec55  jz      short loc_18010EC5E
0x18010ec57  mov     rcx, [rax+370h]
0x18010ec5e  mov     [rbp+57h+var_70], rcx
0x18010ec62  lea     r8, [rbp+57h+var_80]
0x18010ec66  lea     rcx, [rbp+57h+var_70]
0x18010ec6a  lea     rdx, [rbp+57h+var_90]
0x18010ec6e  call    cs:__imp_NtDCompositionGetFrameSurfaceUpdates
0x18010ec74  mov     ebx, eax
0x18010ec76  test    eax, eax
0x18010ec78  js      short loc_18010ECBA
0x18010ec7a  mov     ebx, r12d
0x18010ec7d  jmp     loc_18010EAA0
0x18010ec82  bts     ebx, 1Ch
0x18010ec86  mov     [rsp+0C0h+var_98], r12; void *
0x18010ec8b  mov     r9d, ebx; int
0x18010ec8e  mov     [rsp+0C0h+var_A0], 91h; unsigned int
0x18010ec96  mov     r8d, 3; unsigned int
0x18010ec9c  lea     rdx, qword_180329D50; int *
0x18010eca3  mov     ecx, 14h; unsigned int
0x18010eca8  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18010ecad  test    ebx, ebx
0x18010ecaf  jns     loc_18010EA90
0x18010ecb5  jmp     loc_18010EAC3
0x18010ecba  bts     ebx, 1Ch
0x18010ecbe  mov     [rsp+0C0h+var_98], r12; void *
0x18010ecc3  mov     r9d, ebx; int
0x18010ecc6  mov     [rsp+0C0h+var_A0], 91h; unsigned int
0x18010ecce  mov     r8d, 3; unsigned int
0x18010ecd4  lea     rdx, qword_180329D50; int *
0x18010ecdb  mov     ecx, 14h; unsigned int
0x18010ece0  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18010ece5  test    ebx, ebx
0x18010ece7  js      loc_18010EAB3
0x18010eced  jmp     loc_18010EAA0
0x18010ecf2  mov     rax, [rcx]
0x18010ecf5  mov     rax, [rax+30h]
0x18010ecf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010ecfe  mov     rdx, rax
0x18010ed01  test    rax, rax
0x18010ed04  jz      loc_18010EAE6
0x18010ed0a  mov     rcx, [rax]
0x18010ed0d  mov     rax, [rcx+30h]
0x18010ed11  mov     rcx, rdx
0x18010ed14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010ed19  jmp     loc_18010EAE6
```
