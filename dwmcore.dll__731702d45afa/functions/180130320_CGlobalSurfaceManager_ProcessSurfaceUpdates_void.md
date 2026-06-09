# CGlobalSurfaceManager::ProcessSurfaceUpdates(void)

- ea: `0x180130320`
- end: `0x18013065e`
- name: `?ProcessSurfaceUpdates@CGlobalSurfaceManager@@UEAAJXZ`
- size: `830`
- prototype: `__int64 __fastcall(CGlobalSurfaceManager *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180050270`
- `0x180130320`
- `0x180131690`
- `0x180131dc0`
- `0x1802284b0`
- `0x1802b6010`

## import_xrefs

- `ntdll!RtlLookupElementGenericTable` at `0x180130485`
- `ntdll!RtlLookupElementGenericTable` at `0x180130485`
- `win32u!NtDCompositionGetFrameSurfaceUpdates` at `0x1801303bd`
- `win32u!NtDCompositionGetFrameSurfaceUpdates` at `0x1801305ae`
- `win32u!NtDCompositionGetFrameSurfaceUpdates` at `0x1801303bd`
- `win32u!NtDCompositionGetFrameSurfaceUpdates` at `0x1801305ae`

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
  MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_18032A4C8, 3u, FrameSurfaceUpdates | 0x10000000, 0x91u, 0);
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
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_18032A4C8, 3u, v20 | 0x10000000, 0x91u, 0);
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
0x180130320  push    rbp
0x180130322  push    rbx
0x180130323  push    rdi
0x180130324  push    r12
0x180130326  push    r15
0x180130328  lea     rbp, [rsp-37h]
0x18013032d  sub     rsp, 0A0h
0x180130334  mov     rax, cs:__security_cookie
0x18013033b  xor     rax, rsp
0x18013033e  mov     [rbp+57h+var_28], rax
0x180130342  xor     r12d, r12d
0x180130345  mov     [rsp+0C0h+arg_18], r14
0x18013034d  mov     [rbp+57h+var_90], r12d
0x180130351  mov     r15d, r12d
0x180130354  mov     [rbp+57h+var_80], r12d
0x180130358  mov     edi, r12d
0x18013035b  mov     [rbp+57h+var_88], r12d
0x18013035f  mov     r14, rcx
0x180130362  call    ?ProcessLegacyTokens@CGlobalSurfaceManager@@AEAAJXZ; CGlobalSurfaceManager::ProcessLegacyTokens(void)
0x180130367  test    eax, eax
0x180130369  jns     short loc_18013038A
0x18013036b  mov     [rsp+0C0h+var_98], r12; void *
0x180130370  mov     r9d, eax; int
0x180130373  xor     r8d, r8d; unsigned int
0x180130376  mov     [rsp+0C0h+var_A0], 0A1h; unsigned int
0x18013037e  xor     edx, edx; int *
0x180130380  mov     ecx, 14h; unsigned int
0x180130385  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18013038a  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits, 10h
0x180130391  jnz     loc_18013050C
0x180130397  mov     rax, cs:?g_pComposition@@3PEAVCComposition@@EA; CComposition * g_pComposition
0x18013039e  mov     rcx, r12
0x1801303a1  test    rax, rax
0x1801303a4  jz      short loc_1801303AD
0x1801303a6  mov     rcx, [rax+370h]
0x1801303ad  mov     [rbp+57h+var_78], rcx
0x1801303b1  lea     r8, [rbp+57h+var_80]
0x1801303b5  lea     rcx, [rbp+57h+var_78]
0x1801303b9  lea     rdx, [rbp+57h+var_90]
0x1801303bd  call    cs:__imp_NtDCompositionGetFrameSurfaceUpdates
0x1801303c3  mov     ebx, eax
0x1801303c5  test    eax, eax
0x1801303c7  js      loc_1801305C2
0x1801303cd  mov     ebx, r12d
0x1801303d0  mov     [rsp+0C0h+arg_8], rsi
0x1801303d8  mov     [rsp+0C0h+arg_10], r13
0x1801303e0  cmp     [rbp+57h+var_90], 0
0x1801303e4  mov     esi, r12d
0x1801303e7  ja      short loc_180130460
0x1801303e9  cmp     [rbp+57h+var_80], 0
0x1801303ed  jnz     loc_180130581
0x1801303f3  mov     rsi, [rsp+0C0h+arg_8]
0x1801303fb  mov     r13, [rsp+0C0h+arg_10]
0x180130403  mov     rax, cs:?g_pComposition@@3PEAVCComposition@@EA; CComposition * g_pComposition
0x18013040a  mov     r14, [rsp+0C0h+arg_18]
0x180130412  mov     rcx, [rax+1620h]
0x180130419  mov     rcx, [rcx+18h]
0x18013041d  test    rcx, rcx
0x180130420  jnz     loc_180130632
0x180130426  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits, 10h
0x18013042d  jnz     loc_180130533
0x180130433  add     cs:dword_1803BADFC, edi
0x180130439  mov     eax, ebx
0x18013043b  mov     rcx, [rbp+57h+var_28]
0x18013043f  xor     rcx, rsp; StackCookie
0x180130442  call    __security_check_cookie
0x180130447  add     rsp, 0A0h
0x18013044e  pop     r15
0x180130450  pop     r12
0x180130452  pop     rdi
0x180130453  pop     rbx
0x180130454  pop     rbp
0x180130455  retn
0x180130460  mov     eax, esi
0x180130462  lea     rdx, [rbp+57h+Buffer]; Buffer
0x180130466  imul    r13, rax, 178h
0x18013046d  lea     rcx, [r14+18h]; Table
0x180130471  mov     [rbp+57h+var_60], 0
0x180130479  add     r13, [r14+68h]
0x18013047d  mov     rax, [r13+4]
0x180130481  mov     [rbp+57h+Buffer], rax
0x180130485  call    cs:__imp_RtlLookupElementGenericTable
0x18013048b  test    rax, rax
0x18013048e  jz      short loc_1801304F5
0x180130490  mov     r15, [rax+8]
0x180130494  test    r15, r15
0x180130497  jz      short loc_1801304F5
0x180130499  mov     rax, [r15]
0x18013049c  mov     rcx, r15
0x18013049f  mov     rax, [rax+8]
0x1801304a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801304a8  mov     rax, [r15]
0x1801304ab  mov     rdx, r13
0x1801304ae  mov     rcx, r15
0x1801304b1  mov     rax, [rax+80h]
0x1801304b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801304bd  test    eax, eax
0x1801304bf  jns     short loc_1801304E4
0x1801304c1  mov     [rsp+0C0h+var_98], 0; void *
0x1801304ca  mov     r9d, eax; int
0x1801304cd  xor     r8d, r8d; unsigned int
0x1801304d0  mov     [rsp+0C0h+var_A0], 0BCh; unsigned int
0x1801304d8  xor     edx, edx; int *
0x1801304da  mov     ecx, 14h; unsigned int
0x1801304df  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1801304e4  mov     rax, [r15]
0x1801304e7  inc     edi
0x1801304e9  mov     rcx, r15
0x1801304ec  mov     rax, [rax+10h]
0x1801304f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801304f5  inc     esi
0x1801304f7  cmp     esi, [rbp+57h+var_90]
0x1801304fa  jb      loc_180130460
0x180130500  mov     r15d, [rbp+57h+var_88]
0x180130504  xor     r12d, r12d
0x180130507  jmp     loc_1801303E9
0x18013050c  lea     rax, [rbp+57h+Buffer]
0x180130510  mov     r9d, 1
0x180130516  lea     rdx, EVTDESC_MILEVENT_MEDIA_UCE_PROCESSSURFACEUPDATES_Start
0x18013051d  mov     qword ptr [rsp+0C0h+var_A0], rax
0x180130522  lea     rcx, Microsoft_Windows_Dwm_Core_Provider_Context
0x180130529  call    McGenEventWrite_EventWriteTransfer
0x18013052e  jmp     loc_180130397
0x180130533  lea     rax, [rbp+57h+var_88]
0x180130537  mov     dword ptr [rbp+57h+var_78], r15d
0x18013053b  mov     [rbp+57h+var_48], rax
0x18013053f  lea     rdx, EVTDESC_MILEVENT_MEDIA_UCE_PROCESSSURFACEUPDATES_Stop
0x180130546  lea     rax, [rbp+57h+var_78]
0x18013054a  mov     [rbp+57h+var_88], edi
0x18013054d  mov     [rbp+57h+var_38], rax
0x180130551  lea     rcx, Microsoft_Windows_Dwm_Core_Provider_Context
0x180130558  lea     rax, [rbp+57h+var_58]
0x18013055c  mov     [rbp+57h+var_40], 4
0x180130564  mov     r9d, 3
0x18013056a  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18013056f  mov     [rbp+57h+var_30], 4
0x180130577  call    McGenEventWrite_EventWriteTransfer
0x18013057c  jmp     loc_180130433
0x180130581  mov     rax, cs:?g_pComposition@@3PEAVCComposition@@EA; CComposition * g_pComposition
0x180130588  inc     r15d
0x18013058b  mov     [rbp+57h+var_88], r15d
0x18013058f  mov     rcx, r12
0x180130592  test    rax, rax
0x180130595  jz      short loc_18013059E
0x180130597  mov     rcx, [rax+370h]
0x18013059e  mov     [rbp+57h+var_70], rcx
0x1801305a2  lea     r8, [rbp+57h+var_80]
0x1801305a6  lea     rcx, [rbp+57h+var_70]
0x1801305aa  lea     rdx, [rbp+57h+var_90]
0x1801305ae  call    cs:__imp_NtDCompositionGetFrameSurfaceUpdates
0x1801305b4  mov     ebx, eax
0x1801305b6  test    eax, eax
0x1801305b8  js      short loc_1801305FA
0x1801305ba  mov     ebx, r12d
0x1801305bd  jmp     loc_1801303E0
0x1801305c2  bts     ebx, 1Ch
0x1801305c6  mov     [rsp+0C0h+var_98], r12; void *
0x1801305cb  mov     r9d, ebx; int
0x1801305ce  mov     [rsp+0C0h+var_A0], 91h; unsigned int
0x1801305d6  mov     r8d, 3; unsigned int
0x1801305dc  lea     rdx, qword_18032A4C8; int *
0x1801305e3  mov     ecx, 14h; unsigned int
0x1801305e8  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1801305ed  test    ebx, ebx
0x1801305ef  jns     loc_1801303D0
0x1801305f5  jmp     loc_180130403
0x1801305fa  bts     ebx, 1Ch
0x1801305fe  mov     [rsp+0C0h+var_98], r12; void *
0x180130603  mov     r9d, ebx; int
0x180130606  mov     [rsp+0C0h+var_A0], 91h; unsigned int
0x18013060e  mov     r8d, 3; unsigned int
0x180130614  lea     rdx, qword_18032A4C8; int *
0x18013061b  mov     ecx, 14h; unsigned int
0x180130620  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180130625  test    ebx, ebx
0x180130627  js      loc_1801303F3
0x18013062d  jmp     loc_1801303E0
0x180130632  mov     rax, [rcx]
0x180130635  mov     rax, [rax+30h]
0x180130639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013063e  mov     rdx, rax
0x180130641  test    rax, rax
0x180130644  jz      loc_180130426
0x18013064a  mov     rcx, [rax]
0x18013064d  mov     rax, [rcx+30h]
0x180130651  mov     rcx, rdx
0x180130654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180130659  jmp     loc_180130426
```
