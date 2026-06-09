# DesktopShellHostExtensionsTelemetry::LaunchDefaultShell::StopActivity(void)

- ea: `0x1800132a0`
- end: `0x1800138c5`
- name: `?StopActivity@LaunchDefaultShell@DesktopShellHostExtensionsTelemetry@@MEAAXXZ`
- size: `1573`
- prototype: `void __fastcall(DesktopShellHostExtensionsTelemetry::LaunchDefaultShell *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000e83c`
- `0x1800106c0`
- `0x1800132a0`
- `0x18002a3d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013316`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001371e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013316`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001371e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001332e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013349`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013363`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013736`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013751`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001376b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001332e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013349`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013363`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013736`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013751`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001376b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800137bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800137bc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800136f5`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001388c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800136f5`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001388c`

## pseudocode

```c
void __fastcall DesktopShellHostExtensionsTelemetry::LaunchDefaultShell::StopActivity(
        DesktopShellHostExtensionsTelemetry::LaunchDefaultShell *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rbx
  RTL_SRWLOCK *v6; // rbx
  __int64 v7; // r13
  __int64 v8; // rcx
  const unsigned __int16 *v9; // rdx
  const unsigned __int16 *v10; // r8
  const unsigned __int16 *v11; // r9
  const unsigned __int16 *v12; // r10
  const unsigned __int16 *v13; // r11
  const unsigned __int16 *v14; // rbx
  const unsigned __int16 *v15; // r14
  const unsigned __int16 *v16; // r15
  int v17; // eax
  __int64 v18; // rdi
  __int64 v19; // rax
  bool v20; // zf
  int v21; // eax
  __int64 v22; // rax
  int v23; // eax
  __int64 v24; // rax
  int v25; // eax
  __int64 v26; // rax
  int v27; // eax
  __int64 v28; // rax
  int v29; // eax
  __int64 v30; // rax
  int v31; // eax
  __int64 v32; // rax
  int v33; // eax
  int v34; // ecx
  RTL_SRWLOCK *v35; // rbx
  __int64 v36; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v38; // r8
  unsigned int v39; // [rsp+30h] [rbp-D0h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-C8h] BYREF
  PSRWLOCK v41; // [rsp+40h] [rbp-C0h] BYREF
  PSRWLOCK v42; // [rsp+48h] [rbp-B8h] BYREF
  int v43; // [rsp+50h] [rbp-B0h] BYREF
  int v44; // [rsp+54h] [rbp-ACh] BYREF
  int v45; // [rsp+58h] [rbp-A8h] BYREF
  int v46; // [rsp+5Ch] [rbp-A4h] BYREF
  PSRWLOCK v47; // [rsp+60h] [rbp-A0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+68h] [rbp-98h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v49; // [rsp+80h] [rbp-80h] BYREF
  char *v50; // [rsp+90h] [rbp-70h]
  int v51; // [rsp+98h] [rbp-68h]
  int v52; // [rsp+9Ch] [rbp-64h]
  PSRWLOCK *v53; // [rsp+A0h] [rbp-60h]
  __int64 v54; // [rsp+A8h] [rbp-58h]
  PSRWLOCK *v55; // [rsp+B0h] [rbp-50h]
  __int64 v56; // [rsp+B8h] [rbp-48h]
  PSRWLOCK *p_SRWLock; // [rsp+C0h] [rbp-40h]
  __int64 v58; // [rsp+C8h] [rbp-38h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+D0h] [rbp-30h] BYREF
  char *v60; // [rsp+E0h] [rbp-20h]
  int v61; // [rsp+E8h] [rbp-18h]
  int v62; // [rsp+ECh] [rbp-14h]
  PSRWLOCK *v63; // [rsp+F0h] [rbp-10h]
  __int64 v64; // [rsp+F8h] [rbp-8h]
  PSRWLOCK *v65; // [rsp+100h] [rbp+0h]
  __int64 v66; // [rsp+108h] [rbp+8h]
  PSRWLOCK *v67; // [rsp+110h] [rbp+10h]
  __int64 v68; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v69; // [rsp+120h] [rbp+20h]
  int v70; // [rsp+128h] [rbp+28h]
  int v71; // [rsp+12Ch] [rbp+2Ch]
  unsigned int *v72; // [rsp+130h] [rbp+30h]
  __int64 v73; // [rsp+138h] [rbp+38h]
  const unsigned __int16 *v74; // [rsp+140h] [rbp+40h]
  int v75; // [rsp+148h] [rbp+48h]
  int v76; // [rsp+14Ch] [rbp+4Ch]
  int *v77; // [rsp+150h] [rbp+50h]
  __int64 v78; // [rsp+158h] [rbp+58h]
  const unsigned __int16 *v79; // [rsp+160h] [rbp+60h]
  int v80; // [rsp+168h] [rbp+68h]
  int v81; // [rsp+16Ch] [rbp+6Ch]
  int *v82; // [rsp+170h] [rbp+70h]
  __int64 v83; // [rsp+178h] [rbp+78h]
  const unsigned __int16 *v84; // [rsp+180h] [rbp+80h]
  int v85; // [rsp+188h] [rbp+88h]
  int v86; // [rsp+18Ch] [rbp+8Ch]
  int *v87; // [rsp+190h] [rbp+90h]
  __int64 v88; // [rsp+198h] [rbp+98h]
  const unsigned __int16 *v89; // [rsp+1A0h] [rbp+A0h]
  int v90; // [rsp+1A8h] [rbp+A8h]
  int v91; // [rsp+1ACh] [rbp+ACh]
  const unsigned __int16 *v92; // [rsp+1B0h] [rbp+B0h]
  int v93; // [rsp+1B8h] [rbp+B8h]
  int v94; // [rsp+1BCh] [rbp+BCh]
  int *v95; // [rsp+1C0h] [rbp+C0h]
  __int64 v96; // [rsp+1C8h] [rbp+C8h]
  const unsigned __int16 *v97; // [rsp+1D0h] [rbp+D0h]
  int v98; // [rsp+1D8h] [rbp+D8h]
  int v99; // [rsp+1DCh] [rbp+DCh]
  const unsigned __int16 *v100; // [rsp+1E0h] [rbp+E0h]
  int v101; // [rsp+1E8h] [rbp+E8h]
  int v102; // [rsp+1ECh] [rbp+ECh]

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) )
  {
    v5 = (RTL_SRWLOCK *)*((_QWORD *)this + 35);
    if ( v4 )
    {
      if ( v5 )
      {
        v6 = v5 + 33;
        AcquireSRWLockExclusive(v6);
        SRWLock = 0;
        **((_DWORD **)this + 34) = 2;
        if ( v6 )
          ReleaseSRWLockExclusive(v6);
      }
      else
      {
        v41 = 0;
        **((_DWORD **)this + 34) = 2;
      }
      v7 = *((_QWORD *)DesktopShellHostExtensionsLogging::Instance() + 1);
      if ( *(_DWORD *)v7 > 5u
        && (*(_QWORD *)(v7 + 16) & 0x400000000000LL) != 0
        && (*(_QWORD *)(v7 + 24) & 0x400000000000LL) == *(_QWORD *)(v7 + 24) )
      {
        v8 = -1;
        v9 = (const unsigned __int16 *)*((_QWORD *)v4 + 15);
        v10 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
        v11 = (const unsigned __int16 *)*((_QWORD *)v4 + 12);
        v12 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
        v13 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
        v14 = (const unsigned __int16 *)*((_QWORD *)v4 + 3);
        v15 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
        v16 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
        v43 = v4[26];
        v44 = v4[20];
        v45 = v4[8];
        v46 = *v4;
        v39 = v4[16];
        v17 = v4[2];
        v18 = *((_QWORD *)this + 34);
        LODWORD(v41) = v17;
        v47 = (PSRWLOCK)0x1000000;
        v42 = 0;
        if ( v9 )
        {
          v19 = -1;
          do
            v20 = v9[++v19] == 0;
          while ( !v20 );
          v21 = 2 * v19 + 2;
        }
        else
        {
          v9 = &qword_180090A60;
          v21 = 2;
        }
        v100 = v9;
        v101 = v21;
        v102 = 0;
        if ( v10 )
        {
          v22 = -1;
          do
            ++v22;
          while ( *((_BYTE *)v10 + v22) );
          v23 = v22 + 1;
        }
        else
        {
          v10 = &word_180091822;
          v23 = 1;
        }
        v98 = v23;
        v95 = &v43;
        v97 = v10;
        v99 = 0;
        v96 = 4;
        if ( v11 )
        {
          v24 = -1;
          do
            v20 = v11[++v24] == 0;
          while ( !v20 );
          v25 = 2 * v24 + 2;
        }
        else
        {
          v11 = &qword_180090A60;
          v25 = 2;
        }
        v92 = v11;
        v93 = v25;
        v94 = 0;
        if ( v12 )
        {
          v26 = -1;
          do
            ++v26;
          while ( *((_BYTE *)v12 + v26) );
          v27 = v26 + 1;
        }
        else
        {
          v12 = &word_180091822;
          v27 = 1;
        }
        v90 = v27;
        v87 = &v44;
        v89 = v12;
        v91 = 0;
        v88 = 4;
        if ( v13 )
        {
          v28 = -1;
          do
            ++v28;
          while ( *((_BYTE *)v13 + v28) );
          v29 = v28 + 1;
        }
        else
        {
          v13 = &word_180091822;
          v29 = 1;
        }
        v85 = v29;
        v82 = &v45;
        v84 = v13;
        v86 = 0;
        v83 = 4;
        if ( v14 )
        {
          v30 = -1;
          do
            v20 = v14[++v30] == 0;
          while ( !v20 );
          v31 = 2 * v30 + 2;
        }
        else
        {
          v14 = &qword_180090A60;
          v31 = 2;
        }
        v80 = v31;
        v77 = &v46;
        v79 = v14;
        v81 = 0;
        v78 = 4;
        if ( v15 )
        {
          v32 = -1;
          do
            ++v32;
          while ( *((_BYTE *)v15 + v32) );
          v33 = v32 + 1;
        }
        else
        {
          v15 = &word_180091822;
          v33 = 1;
        }
        v75 = v33;
        v72 = &v39;
        v74 = v15;
        v76 = 0;
        v73 = 4;
        if ( v16 )
        {
          do
            ++v8;
          while ( *((_BYTE *)v16 + v8) );
          v34 = v8 + 1;
        }
        else
        {
          v16 = &word_180091822;
          v34 = 1;
        }
        v71 = 0;
        v67 = &v41;
        v70 = v34;
        v65 = &v47;
        v69 = v16;
        v63 = &v42;
        *(_DWORD *)&EventDescriptor.Level = 517;
        UserData.Ptr = *(_QWORD *)(v7 + 8);
        v68 = 4;
        v66 = 8;
        v64 = 8;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 0x400000000000LL;
        UserData.Size = *(unsigned __int16 *)UserData.Ptr;
        v60 = byte_18009A1E5;
        UserData.Reserved = 2;
        v61 = 286;
        v62 = 1;
        LODWORD(SRWLock) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(*(_QWORD *)(v7 + 32), &EventDescriptor, (LPCGUID)(v18 + 8), 0, 0x12u, &UserData);
      }
      goto LABEL_60;
    }
  }
  else
  {
    v5 = (RTL_SRWLOCK *)*((_QWORD *)this + 35);
  }
  if ( v5 )
  {
    v35 = v5 + 33;
    AcquireSRWLockExclusive(v35);
    v42 = 0;
    **((_DWORD **)this + 34) = 2;
    if ( v35 )
      ReleaseSRWLockExclusive(v35);
  }
  else
  {
    v47 = 0;
    **((_DWORD **)this + 34) = 2;
  }
  v36 = *((_QWORD *)DesktopShellHostExtensionsLogging::Instance() + 1);
  if ( *(_DWORD *)v36 > 5u
    && (*(_QWORD *)(v36 + 16) & 0x400000000000LL) != 0
    && (*(_QWORD *)(v36 + 24) & 0x400000000000LL) == *(_QWORD *)(v36 + 24) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v38 = *((_QWORD *)this + 34);
    LODWORD(SRWLock) = CurrentThreadId;
    v58 = 4;
    v56 = 4;
    LODWORD(v41) = *(_DWORD *)(v38 + 72);
    p_SRWLock = &SRWLock;
    v55 = &v41;
    v53 = &v42;
    *(_DWORD *)&EventDescriptor.Level = 517;
    v49.Ptr = *(_QWORD *)(v36 + 8);
    v42 = 0;
    v54 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0x400000000000LL;
    v49.Size = *(unsigned __int16 *)v49.Ptr;
    v50 = &byte_18009A30F;
    v49.Reserved = 2;
    v51 = 71;
    v52 = 1;
    v39 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(*(_QWORD *)(v36 + 32), &EventDescriptor, (LPCGUID)(v38 + 8), 0, 5u, &v49);
  }
LABEL_60:
  wil::ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x1800132a0  mov     [rsp-8+arg_10], rbx
0x1800132a5  mov     [rsp-8+arg_18], rsi
0x1800132aa  push    rbp
0x1800132ab  push    rdi
0x1800132ac  push    r12
0x1800132ae  push    r13
0x1800132b0  push    r14
0x1800132b2  lea     rbp, [rsp-100h]
0x1800132ba  sub     rsp, 200h
0x1800132c1  mov     rax, cs:__security_cookie
0x1800132c8  xor     rax, rsp
0x1800132cb  mov     [rbp+120h+var_30], rax
0x1800132d2  mov     rdi, [rcx+110h]
0x1800132d9  xor     r14d, r14d
0x1800132dc  mov     rsi, rcx
0x1800132df  mov     eax, [rdi+48h]
0x1800132e2  test    eax, eax
0x1800132e4  jns     loc_180013708
0x1800132ea  add     rdi, 50h ; 'P'
0x1800132ee  cmp     eax, [rdi+8]
0x1800132f1  jnz     loc_180013708
0x1800132f7  mov     rbx, [rcx+118h]
0x1800132fe  test    rdi, rdi
0x180013301  jz      loc_18001370F
0x180013307  test    rbx, rbx
0x18001330a  jz      short loc_180013351
0x18001330c  add     rbx, 108h
0x180013313  mov     rcx, rbx; SRWLock
0x180013316  call    cs:__imp_AcquireSRWLockExclusive
0x18001331c  lea     rax, [rsp+220h+SRWLock]
0x180013321  mov     [rax], r14
0x180013324  mov     rcx, [rsp+220h+SRWLock]; SRWLock
0x180013329  test    rcx, rcx
0x18001332c  jz      short loc_180013334
0x18001332e  call    cs:__imp_ReleaseSRWLockExclusive
0x180013334  mov     rax, [rsi+110h]
0x18001333b  mov     dword ptr [rax], 2
0x180013341  test    rbx, rbx
0x180013344  jz      short loc_180013376
0x180013346  mov     rcx, rbx; SRWLock
0x180013349  call    cs:__imp_ReleaseSRWLockExclusive
0x18001334f  jmp     short loc_180013376
0x180013351  lea     rax, [rsp+220h+var_1E0]
0x180013356  mov     [rax], r14
0x180013359  mov     rcx, [rsp+220h+var_1E0]; SRWLock
0x18001335e  test    rcx, rcx
0x180013361  jz      short loc_180013369
0x180013363  call    cs:__imp_ReleaseSRWLockExclusive
0x180013369  mov     rax, [rsi+110h]
0x180013370  mov     dword ptr [rax], 2
0x180013376  call    ?Instance@DesktopShellHostExtensionsLogging@@KAPEAV1@XZ; DesktopShellHostExtensionsLogging::Instance(void)
0x18001337b  mov     r13, [rax+8]
0x18001337f  mov     eax, [r13+0]
0x180013383  cmp     eax, 5
0x180013386  jbe     loc_180013892
0x18001338c  mov     rcx, [r13+18h]
0x180013390  mov     r12, 400000000000h
0x18001339a  mov     rax, [r13+10h]
0x18001339e  test    r12, rax
0x1800133a1  jz      loc_180013892
0x1800133a7  mov     rax, rcx
0x1800133aa  and     rax, r12
0x1800133ad  cmp     rax, rcx
0x1800133b0  jnz     loc_180013892
0x1800133b6  mov     [rsp+220h+arg_8], r15
0x1800133be  mov     eax, [rdi+68h]
0x1800133c1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800133c8  mov     rdx, [rdi+78h]
0x1800133cc  mov     r8, [rdi+70h]
0x1800133d0  mov     r9, [rdi+60h]
0x1800133d4  mov     r10, [rdi+58h]
0x1800133d8  mov     r11, [rdi+48h]
0x1800133dc  mov     rbx, [rdi+18h]
0x1800133e0  mov     r14, [rdi+80h]
0x1800133e7  mov     r15, [rdi+38h]
0x1800133eb  mov     [rsp+220h+var_1D0], eax
0x1800133ef  mov     eax, [rdi+50h]
0x1800133f2  mov     [rsp+220h+var_1CC], eax
0x1800133f6  mov     eax, [rdi+20h]
0x1800133f9  mov     [rsp+220h+var_1C8], eax
0x1800133fd  mov     eax, [rdi]
0x1800133ff  mov     [rsp+220h+var_1C4], eax
0x180013403  mov     eax, [rdi+40h]
0x180013406  mov     [rsp+220h+var_1F0], eax
0x18001340a  mov     eax, [rdi+8]
0x18001340d  mov     rdi, [rsi+110h]
0x180013414  mov     dword ptr [rsp+220h+var_1E0], eax
0x180013418  mov     [rsp+220h+var_1C0], 1000000h
0x180013421  mov     [rsp+220h+var_1D8], 0
0x18001342a  test    rdx, rdx
0x18001342d  jz      short loc_180013447
0x18001342f  mov     rax, rcx
0x180013432  cmp     word ptr [rdx+rax*2+2], 0
0x180013438  lea     rax, [rax+1]
0x18001343c  jnz     short loc_180013432
0x18001343e  lea     eax, ds:2[rax*2]
0x180013445  jmp     short loc_180013453
0x180013447  lea     rdx, qword_180090A60
0x18001344e  mov     eax, 2
0x180013453  mov     [rbp+120h+var_40], rdx
0x18001345a  xor     edx, edx
0x18001345c  mov     [rbp+120h+var_38], eax
0x180013462  mov     [rbp+120h+var_34], edx
0x180013468  test    r8, r8
0x18001346b  jz      short loc_18001347D
0x18001346d  mov     rax, rcx
0x180013470  inc     rax
0x180013473  cmp     [r8+rax], dl
0x180013477  jnz     short loc_180013470
0x180013479  inc     eax
0x18001347b  jmp     short loc_180013489
0x18001347d  lea     r8, word_180091822
0x180013484  mov     eax, 1
0x180013489  mov     [rbp+120h+var_48], eax
0x18001348f  lea     rax, [rsp+220h+var_1D0]
0x180013494  mov     [rbp+120h+var_60], rax
0x18001349b  mov     [rbp+120h+var_50], r8
0x1800134a2  mov     [rbp+120h+var_44], edx
0x1800134a8  mov     [rbp+120h+var_58], 4
0x1800134b3  test    r9, r9
0x1800134b6  jz      short loc_1800134D5
0x1800134b8  mov     rax, rcx
0x1800134bb  nop     dword ptr [rax+rax+00h]
0x1800134c0  cmp     [r9+rax*2+2], dx
0x1800134c6  lea     rax, [rax+1]
0x1800134ca  jnz     short loc_1800134C0
0x1800134cc  lea     eax, ds:2[rax*2]
0x1800134d3  jmp     short loc_1800134E1
0x1800134d5  lea     r9, qword_180090A60
0x1800134dc  mov     eax, 2
0x1800134e1  mov     [rbp+120h+var_70], r9
0x1800134e8  mov     [rbp+120h+var_68], eax
0x1800134ee  mov     [rbp+120h+var_64], edx
0x1800134f4  test    r10, r10
0x1800134f7  jz      short loc_18001350D
0x1800134f9  mov     rax, rcx
0x1800134fc  nop     dword ptr [rax+00h]
0x180013500  inc     rax
0x180013503  cmp     [r10+rax], dl
0x180013507  jnz     short loc_180013500
0x180013509  inc     eax
0x18001350b  jmp     short loc_180013519
0x18001350d  lea     r10, word_180091822
0x180013514  mov     eax, 1
0x180013519  mov     [rbp+120h+var_78], eax
0x18001351f  lea     rax, [rsp+220h+var_1CC]
0x180013524  mov     [rbp+120h+var_90], rax
0x18001352b  mov     [rbp+120h+var_80], r10
0x180013532  mov     [rbp+120h+var_74], edx
0x180013538  mov     [rbp+120h+var_88], 4
0x180013543  test    r11, r11
0x180013546  jz      short loc_18001355D
0x180013548  mov     rax, rcx
0x18001354b  nop     dword ptr [rax+rax+00h]
0x180013550  inc     rax
0x180013553  cmp     [r11+rax], dl
0x180013557  jnz     short loc_180013550
0x180013559  inc     eax
0x18001355b  jmp     short loc_180013569
0x18001355d  lea     r11, word_180091822
0x180013564  mov     eax, 1
0x180013569  mov     [rbp+120h+var_98], eax
0x18001356f  lea     rax, [rsp+220h+var_1C8]
0x180013574  mov     [rbp+120h+var_B0], rax
0x180013578  mov     [rbp+120h+var_A0], r11
0x18001357f  mov     [rbp+120h+var_94], edx
0x180013585  mov     [rbp+120h+var_A8], 4
0x18001358d  test    rbx, rbx
0x180013590  jz      short loc_1800135A9
0x180013592  mov     rax, rcx
0x180013595  cmp     [rbx+rax*2+2], dx
0x18001359a  lea     rax, [rax+1]
0x18001359e  jnz     short loc_180013595
0x1800135a0  lea     eax, ds:2[rax*2]
0x1800135a7  jmp     short loc_1800135B5
0x1800135a9  lea     rbx, qword_180090A60
0x1800135b0  mov     eax, 2
0x1800135b5  mov     [rbp+120h+var_B8], eax
0x1800135b8  lea     rax, [rsp+220h+var_1C4]
0x1800135bd  mov     [rbp+120h+var_D0], rax
0x1800135c1  mov     [rbp+120h+var_C0], rbx
0x1800135c5  mov     [rbp+120h+var_B4], edx
0x1800135c8  mov     [rbp+120h+var_C8], 4
0x1800135d0  test    r14, r14
0x1800135d3  jz      short loc_1800135ED
0x1800135d5  mov     rax, rcx
0x1800135d8  nop     dword ptr [rax+rax+00000000h]
0x1800135e0  inc     rax
0x1800135e3  cmp     [r14+rax], dl
0x1800135e7  jnz     short loc_1800135E0
0x1800135e9  inc     eax
0x1800135eb  jmp     short loc_1800135F9
0x1800135ed  lea     r14, word_180091822
0x1800135f4  mov     eax, 1
0x1800135f9  mov     [rbp+120h+var_D8], eax
0x1800135fc  lea     rax, [rsp+220h+var_1F0]
0x180013601  mov     [rbp+120h+var_F0], rax
0x180013605  mov     [rbp+120h+var_E0], r14
0x180013609  mov     [rbp+120h+var_D4], edx
0x18001360c  mov     [rbp+120h+var_E8], 4
0x180013614  test    r15, r15
0x180013617  jz      short loc_18001362D
0x180013619  nop     dword ptr [rax+00000000h]
0x180013620  inc     rcx
0x180013623  cmp     [r15+rcx], dl
0x180013627  jnz     short loc_180013620
0x180013629  inc     ecx
0x18001362b  jmp     short loc_180013639
0x18001362d  lea     r15, word_180091822
0x180013634  mov     ecx, 1
0x180013639  mov     [rbp+120h+var_F4], edx
0x18001363c  lea     rax, [rsp+220h+var_1E0]
0x180013641  mov     [rbp+120h+var_110], rax
0x180013645  lea     rdx, _TraceLoggingMetadata
0x18001364c  mov     [rbp+120h+var_F8], ecx
0x18001364f  lea     rax, [rsp+220h+var_1C0]
0x180013654  mov     [rbp+120h+var_120], rax
0x180013658  lea     r8, [rdi+8]; ActivityId
0x18001365c  lea     rax, [rsp+220h+var_1D8]
0x180013661  mov     [rbp+120h+var_100], r15
0x180013665  mov     [rbp+120h+var_130], rax
0x180013669  xor     r9d, r9d; RelatedActivityId
0x18001366c  movzx   eax, cs:word_18009A1DB
0x180013673  mov     dword ptr [rsp+220h+EventDescriptor.Level], eax
0x180013677  mov     rax, [r13+8]
0x18001367b  mov     [rbp+120h+var_150.Ptr], rax
0x18001367f  mov     [rbp+120h+var_108], 4
0x180013687  mov     [rbp+120h+var_118], 8
0x18001368f  mov     [rbp+120h+var_128], 8
0x180013697  mov     dword ptr [rsp+220h+EventDescriptor.Id], 0B000000h
0x18001369f  mov     [rsp+220h+EventDescriptor.Keyword], r12
0x1800136a4  movzx   eax, word ptr [rax]
0x1800136a7  mov     [rbp+120h+var_150.Size], eax
0x1800136aa  lea     rax, byte_18009A1E5
0x1800136b1  mov     [rbp+120h+var_140], rax
0x1800136b5  lea     rax, _TraceLoggingMetadataEnd
0x1800136bc  sub     eax, edx
0x1800136be  mov     dword ptr [rbp+120h+var_150.0Ch], 2
0x1800136c5  mov     [rbp+120h+var_138], 11Eh
0x1800136cc  lea     rdx, [rsp+220h+EventDescriptor]; EventDescriptor
0x1800136d1  mov     [rbp+120h+var_134], 1
0x1800136d8  mov     dword ptr [rsp+220h+SRWLock], eax
0x1800136dc  mov     eax, dword ptr [rsp+220h+SRWLock]
0x1800136e0  mov     rcx, [r13+20h]; RegHandle
0x1800136e4  lea     rax, [rbp+120h+var_150]
0x1800136e8  mov     [rsp+220h+UserData], rax; UserData
0x1800136ed  mov     [rsp+220h+UserDataCount], 12h; UserDataCount
0x1800136f5  call    cs:__imp_EventWriteTransfer
0x1800136fb  mov     r15, [rsp+220h+arg_8]
0x180013703  jmp     loc_180013892
0x180013708  mov     rbx, [rcx+118h]
0x18001370f  test    rbx, rbx
0x180013712  jz      short loc_180013759
0x180013714  add     rbx, 108h
0x18001371b  mov     rcx, rbx; SRWLock
0x18001371e  call    cs:__imp_AcquireSRWLockExclusive
0x180013724  lea     rax, [rsp+220h+var_1D8]
0x180013729  mov     [rax], r14
0x18001372c  mov     rcx, [rsp+220h+var_1D8]; SRWLock
0x180013731  test    rcx, rcx
0x180013734  jz      short loc_18001373C
0x180013736  call    cs:__imp_ReleaseSRWLockExclusive
0x18001373c  mov     rax, [rsi+110h]
0x180013743  mov     dword ptr [rax], 2
0x180013749  test    rbx, rbx
0x18001374c  jz      short loc_18001377E
0x18001374e  mov     rcx, rbx; SRWLock
0x180013751  call    cs:__imp_ReleaseSRWLockExclusive
0x180013757  jmp     short loc_18001377E
0x180013759  lea     rax, [rsp+220h+var_1C0]
0x18001375e  mov     [rax], r14
0x180013761  mov     rcx, [rsp+220h+var_1C0]; SRWLock
0x180013766  test    rcx, rcx
0x180013769  jz      short loc_180013771
0x18001376b  call    cs:__imp_ReleaseSRWLockExclusive
0x180013771  mov     rax, [rsi+110h]
0x180013778  mov     dword ptr [rax], 2
0x18001377e  call    ?Instance@DesktopShellHostExtensionsLogging@@KAPEAV1@XZ; DesktopShellHostExtensionsLogging::Instance(void)
0x180013783  mov     rbx, [rax+8]
0x180013787  mov     eax, [rbx]
0x180013789  cmp     eax, 5
0x18001378c  jbe     loc_180013892
0x180013792  mov     rcx, [rbx+18h]
0x180013796  mov     r12, 400000000000h
0x1800137a0  mov     rax, [rbx+10h]
0x1800137a4  test    r12, rax
0x1800137a7  jz      loc_180013892
0x1800137ad  mov     rax, rcx
0x1800137b0  and     rax, r12
0x1800137b3  cmp     rax, rcx
0x1800137b6  jnz     loc_180013892
0x1800137bc  call    cs:__imp_GetCurrentThreadId
0x1800137c2  mov     r8, [rsi+110h]
0x1800137c9  lea     rdx, _TraceLoggingMetadata
0x1800137d0  mov     dword ptr [rsp+220h+SRWLock], eax
0x1800137d4  xor     r9d, r9d; RelatedActivityId
0x1800137d7  mov     [rbp+120h+var_158], 4
0x1800137df  mov     [rbp+120h+var_168], 4
0x1800137e7  mov     eax, [r8+48h]
0x1800137eb  add     r8, 8; ActivityId
  ... truncated ...
```
