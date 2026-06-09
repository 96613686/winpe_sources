# CloudAPProvider::CloudApLogonUser::Stop(_LUID,ulong,ushort const *,int,ulong,int,int,int,int,int,int,long,long)

- ea: `0x180039620`
- end: `0x180039fef`
- name: `?Stop@CloudApLogonUser@CloudAPProvider@@QEAAXU_LUID@@KPEBGHKHHHHHHJJ@Z`
- size: `2511`
- prototype: `void __fastcall(CloudAPProvider::CloudApLogonUser *__hidden this, struct _LUID, unsigned int, const unsigned __int16 *, int, unsigned int, int, int, int, int, int, int, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180011960`

## callees

- `0x1800167d0`
- `0x18002b28c`
- `0x180039620`
- `0x180042410`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800396be`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800396d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800396f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180039c8e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180039ca9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180039cc1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800396be`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800396d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800396f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180039c8e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180039ca9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180039cc1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800396a6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180039c78`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800396a6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180039c78`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039d9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039d9d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180039fab`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180039fab`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CloudAPProvider::CloudApLogonUser::Stop(
        CloudAPProvider::CloudApLogonUser *this,
        struct _LUID a2,
        unsigned int a3,
        const char *a4,
        int a5,
        unsigned int a6,
        int a7,
        int a8,
        int a9,
        int a10,
        int a11,
        int a12,
        int a13,
        int a14)
{
  DWORD LowPart; // edi
  LONG HighPart; // r15d
  __int64 v18; // rsi
  int v19; // eax
  __int64 v20; // rsi
  RTL_SRWLOCK *v21; // rbx
  RTL_SRWLOCK *v22; // rbx
  RTL_SRWLOCK *v23; // rdx
  const char *v24; // rbx
  const WCHAR *v25; // rdx
  const unsigned __int16 *v26; // r8
  const WCHAR *v27; // r9
  const unsigned __int16 *v28; // r10
  const unsigned __int16 *v29; // r11
  const WCHAR *v30; // rdi
  const unsigned __int16 *v31; // r15
  const unsigned __int16 *v32; // r12
  __int64 v33; // rsi
  __int64 v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rax
  unsigned int v37; // eax
  __int64 v38; // rax
  unsigned int v39; // eax
  __int64 v40; // rax
  unsigned int v41; // eax
  __int64 v42; // rax
  unsigned int v43; // eax
  __int64 v44; // rax
  unsigned int v45; // eax
  __int64 v46; // rax
  int v47; // eax
  __int64 v48; // rax
  unsigned int v49; // eax
  unsigned int v50; // ecx
  PSRWLOCK v51; // rcx
  RTL_SRWLOCK *v52; // rbx
  __int64 v53; // rsi
  const char *v54; // rbx
  __int64 v55; // r8
  __int64 v56; // rcx
  unsigned int v57; // [rsp+30h] [rbp-D0h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v59; // [rsp+40h] [rbp-C0h] BYREF
  int v60; // [rsp+44h] [rbp-BCh] BYREF
  DWORD CurrentThreadId; // [rsp+48h] [rbp-B8h] BYREF
  int v62; // [rsp+4Ch] [rbp-B4h] BYREF
  int v63; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v64; // [rsp+54h] [rbp-ACh] BYREF
  int v65; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v66; // [rsp+5Ch] [rbp-A4h] BYREF
  int v67; // [rsp+60h] [rbp-A0h] BYREF
  int v68; // [rsp+64h] [rbp-9Ch] BYREF
  int v69; // [rsp+68h] [rbp-98h] BYREF
  int v70; // [rsp+6Ch] [rbp-94h] BYREF
  int v71; // [rsp+70h] [rbp-90h] BYREF
  int v72; // [rsp+74h] [rbp-8Ch] BYREF
  PSRWLOCK v73; // [rsp+78h] [rbp-88h] BYREF
  PSRWLOCK v74; // [rsp+80h] [rbp-80h] BYREF
  PSRWLOCK v75; // [rsp+88h] [rbp-78h] BYREF
  int v76; // [rsp+90h] [rbp-70h] BYREF
  int v77; // [rsp+94h] [rbp-6Ch] BYREF
  int v78; // [rsp+98h] [rbp-68h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v80; // [rsp+B0h] [rbp-50h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+C0h] [rbp-40h] BYREF
  char *v82; // [rsp+D0h] [rbp-30h]
  int v83; // [rsp+D8h] [rbp-28h]
  int v84; // [rsp+DCh] [rbp-24h]
  PSRWLOCK *v85; // [rsp+E0h] [rbp-20h]
  __int64 v86; // [rsp+E8h] [rbp-18h]
  PSRWLOCK *v87; // [rsp+F0h] [rbp-10h]
  __int64 v88; // [rsp+F8h] [rbp-8h]
  PSRWLOCK *p_CurrentThreadId; // [rsp+100h] [rbp+0h]
  __int64 v90; // [rsp+108h] [rbp+8h]
  PSRWLOCK *v91; // [rsp+110h] [rbp+10h]
  __int64 v92; // [rsp+118h] [rbp+18h]
  int *v93; // [rsp+120h] [rbp+20h]
  __int64 v94; // [rsp+128h] [rbp+28h]
  int *v95; // [rsp+130h] [rbp+30h]
  __int64 v96; // [rsp+138h] [rbp+38h]
  int *v97; // [rsp+140h] [rbp+40h]
  __int64 v98; // [rsp+148h] [rbp+48h]
  void *v99; // [rsp+150h] [rbp+50h]
  int v100; // [rsp+158h] [rbp+58h]
  int v101; // [rsp+15Ch] [rbp+5Ch]
  int *v102; // [rsp+160h] [rbp+60h]
  __int64 v103; // [rsp+168h] [rbp+68h]
  unsigned int *v104; // [rsp+170h] [rbp+70h]
  __int64 v105; // [rsp+178h] [rbp+78h]
  int *v106; // [rsp+180h] [rbp+80h]
  __int64 v107; // [rsp+188h] [rbp+88h]
  int *v108; // [rsp+190h] [rbp+90h]
  __int64 v109; // [rsp+198h] [rbp+98h]
  int *v110; // [rsp+1A0h] [rbp+A0h]
  __int64 v111; // [rsp+1A8h] [rbp+A8h]
  int *v112; // [rsp+1B0h] [rbp+B0h]
  __int64 v113; // [rsp+1B8h] [rbp+B8h]
  int *v114; // [rsp+1C0h] [rbp+C0h]
  __int64 v115; // [rsp+1C8h] [rbp+C8h]
  int *v116; // [rsp+1D0h] [rbp+D0h]
  __int64 v117; // [rsp+1D8h] [rbp+D8h]
  PSRWLOCK *v118; // [rsp+1E0h] [rbp+E0h]
  __int64 v119; // [rsp+1E8h] [rbp+E8h]
  PSRWLOCK *p_SRWLock; // [rsp+1F0h] [rbp+F0h]
  __int64 v121; // [rsp+1F8h] [rbp+F8h]
  unsigned int *v122; // [rsp+200h] [rbp+100h]
  __int64 v123; // [rsp+208h] [rbp+108h]
  unsigned int *v124; // [rsp+210h] [rbp+110h]
  __int64 v125; // [rsp+218h] [rbp+118h]
  const char *v126; // [rsp+220h] [rbp+120h]
  int v127; // [rsp+228h] [rbp+128h]
  int v128; // [rsp+22Ch] [rbp+12Ch]
  int *v129; // [rsp+230h] [rbp+130h]
  __int64 v130; // [rsp+238h] [rbp+138h]
  unsigned int *v131; // [rsp+240h] [rbp+140h]
  __int64 v132; // [rsp+248h] [rbp+148h]
  int *v133; // [rsp+250h] [rbp+150h]
  __int64 v134; // [rsp+258h] [rbp+158h]
  int *v135; // [rsp+260h] [rbp+160h]
  __int64 v136; // [rsp+268h] [rbp+168h]
  DWORD *v137; // [rsp+270h] [rbp+170h]
  __int64 v138; // [rsp+278h] [rbp+178h]
  int *v139; // [rsp+280h] [rbp+180h]
  __int64 v140; // [rsp+288h] [rbp+188h]
  unsigned int *v141; // [rsp+290h] [rbp+190h]
  __int64 v142; // [rsp+298h] [rbp+198h]
  int *v143; // [rsp+2A0h] [rbp+1A0h]
  __int64 v144; // [rsp+2A8h] [rbp+1A8h]
  int *v145; // [rsp+2B0h] [rbp+1B0h]
  __int64 v146; // [rsp+2B8h] [rbp+1B8h]
  int *v147; // [rsp+2C0h] [rbp+1C0h]
  __int64 v148; // [rsp+2C8h] [rbp+1C8h]

  v57 = a3;
  LowPart = a2.LowPart;
  HighPart = a2.HighPart;
  v18 = *((_QWORD *)this + 34);
  v19 = *(_DWORD *)(v18 + 72);
  if ( v19 < 0 && (v20 = v18 + 80, v19 == *(_DWORD *)(v20 + 8)) )
  {
    v21 = (RTL_SRWLOCK *)*((_QWORD *)this + 35);
    if ( v20 )
    {
      if ( v21 )
      {
        v22 = v21 + 33;
        AcquireSRWLockExclusive(v22);
        SRWLock = 0;
        **((_DWORD **)this + 34) = 2;
        if ( v22 )
          ReleaseSRWLockExclusive(v22);
      }
      else
      {
        v73 = 0;
        **((_DWORD **)this + 34) = 2;
      }
      v23 = (RTL_SRWLOCK *)*((_QWORD *)CloudAPProvider::Instance() + 1);
      SRWLock = v23;
      if ( LODWORD(v23->Ptr) > 5
        && ((__int64)v23[2].Ptr & 0x400000000000LL) != 0
        && (PVOID)((__int64)v23[3].Ptr & 0x400000000000LL) == v23[3].Ptr )
      {
        v76 = a14;
        v77 = a13;
        v78 = a12;
        v59 = a11;
        v60 = a10;
        CurrentThreadId = a9;
        v62 = a8;
        v63 = a7;
        v64 = a6;
        v65 = a5;
        v24 = L"NULL";
        if ( a4 )
          v24 = a4;
        v66 = LowPart;
        v67 = HighPart;
        v80 = 0x1000000;
        v25 = *(const WCHAR **)(v20 + 120);
        v26 = *(const unsigned __int16 **)(v20 + 112);
        v68 = *(_DWORD *)(v20 + 104);
        v27 = *(const WCHAR **)(v20 + 96);
        v28 = *(const unsigned __int16 **)(v20 + 88);
        v69 = *(_DWORD *)(v20 + 80);
        v29 = *(const unsigned __int16 **)(v20 + 72);
        v70 = *(_DWORD *)(v20 + 32);
        v30 = *(const WCHAR **)(v20 + 24);
        v71 = *(_DWORD *)v20;
        v31 = *(const unsigned __int16 **)(v20 + 128);
        v72 = *(_DWORD *)(v20 + 64);
        v32 = *(const unsigned __int16 **)(v20 + 56);
        LODWORD(v73) = *(_DWORD *)(v20 + 8);
        v74 = (PSRWLOCK)0x1000000;
        v75 = 0;
        v33 = *((_QWORD *)this + 34);
        v147 = &v76;
        v148 = 4;
        v145 = &v77;
        v146 = 4;
        v143 = &v78;
        v144 = 4;
        v141 = &v59;
        v142 = 4;
        v139 = &v60;
        v140 = 4;
        v137 = &CurrentThreadId;
        v138 = 4;
        v135 = &v62;
        v136 = 4;
        v133 = &v63;
        v134 = 4;
        v131 = &v64;
        v132 = 4;
        v129 = &v65;
        v130 = 4;
        v34 = -1;
        v35 = -1;
        do
          ++v35;
        while ( *(_WORD *)&v24[2 * v35] );
        v126 = v24;
        v127 = 2 * v35 + 2;
        v128 = 0;
        v124 = &v57;
        v125 = 4;
        v122 = &v66;
        v123 = 4;
        p_SRWLock = (PSRWLOCK *)&v67;
        v121 = 4;
        v118 = (PSRWLOCK *)&v80;
        v119 = 8;
        if ( v25 )
        {
          v36 = -1;
          do
            ++v36;
          while ( v25[v36] );
          v37 = 2 * v36 + 2;
        }
        else
        {
          v25 = &Class;
          v37 = 2;
        }
        v116 = (int *)v25;
        v117 = v37;
        if ( v26 )
        {
          v38 = -1;
          do
            ++v38;
          while ( *((_BYTE *)v26 + v38) );
          v39 = v38 + 1;
        }
        else
        {
          v26 = &byte_1800865C9;
          v39 = 1;
        }
        v114 = (int *)v26;
        v115 = v39;
        v112 = &v68;
        v113 = 4;
        if ( v27 )
        {
          v40 = -1;
          do
            ++v40;
          while ( v27[v40] );
          v41 = 2 * v40 + 2;
        }
        else
        {
          v27 = &Class;
          v41 = 2;
        }
        v110 = (int *)v27;
        v111 = v41;
        if ( v28 )
        {
          v42 = -1;
          do
            ++v42;
          while ( *((_BYTE *)v28 + v42) );
          v43 = v42 + 1;
        }
        else
        {
          v28 = &byte_1800865C9;
          v43 = 1;
        }
        v108 = (int *)v28;
        v109 = v43;
        v106 = &v69;
        v107 = 4;
        if ( v29 )
        {
          v44 = -1;
          do
            ++v44;
          while ( *((_BYTE *)v29 + v44) );
          v45 = v44 + 1;
        }
        else
        {
          v29 = &byte_1800865C9;
          v45 = 1;
        }
        v104 = (unsigned int *)v29;
        v105 = v45;
        v102 = &v70;
        v103 = 4;
        if ( v30 )
        {
          v46 = -1;
          do
            ++v46;
          while ( v30[v46] );
          v47 = 2 * v46 + 2;
        }
        else
        {
          v30 = &Class;
          v47 = 2;
        }
        v99 = (void *)v30;
        v100 = v47;
        v101 = 0;
        v97 = &v71;
        v98 = 4;
        if ( v31 )
        {
          v48 = -1;
          do
            ++v48;
          while ( *((_BYTE *)v31 + v48) );
          v49 = v48 + 1;
        }
        else
        {
          v31 = &byte_1800865C9;
          v49 = 1;
        }
        v95 = (int *)v31;
        v96 = v49;
        v93 = &v72;
        v94 = 4;
        if ( v32 )
        {
          do
            ++v34;
          while ( *((_BYTE *)v32 + v34) );
          v50 = v34 + 1;
        }
        else
        {
          v32 = &byte_1800865C9;
          v50 = 1;
        }
        v91 = (PSRWLOCK *)v32;
        v92 = v50;
        p_CurrentThreadId = &v73;
        v90 = 4;
        v87 = &v74;
        v88 = 8;
        v85 = &v75;
        v86 = 8;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        *(_DWORD *)&EventDescriptor.Level = 517;
        EventDescriptor.Keyword = 0x400000000000LL;
        v51 = SRWLock;
        UserData.Ptr = (ULONGLONG)SRWLock[1].Ptr;
        UserData.Size = *(unsigned __int16 *)UserData.Ptr;
        UserData.Reserved = 2;
        v82 = byte_18008F8B5;
        v83 = 512;
        v84 = 1;
        LODWORD(SRWLock) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer((REGHANDLE)v51[4].Ptr, &EventDescriptor, (LPCGUID)(v33 + 8), 0, 0x21u, &UserData);
      }
      goto LABEL_68;
    }
  }
  else
  {
    v21 = (RTL_SRWLOCK *)*((_QWORD *)this + 35);
  }
  if ( v21 )
  {
    v52 = v21 + 33;
    AcquireSRWLockExclusive(v52);
    v75 = 0;
    **((_DWORD **)this + 34) = 2;
    if ( v52 )
      ReleaseSRWLockExclusive(v52);
  }
  else
  {
    v74 = 0;
    **((_DWORD **)this + 34) = 2;
  }
  v53 = *((_QWORD *)CloudAPProvider::Instance() + 1);
  if ( *(_DWORD *)v53 > 5u
    && (*(_QWORD *)(v53 + 16) & 0x400000000000LL) != 0
    && (*(_QWORD *)(v53 + 24) & 0x400000000000LL) == *(_QWORD *)(v53 + 24) )
  {
    LODWORD(SRWLock) = a14;
    LODWORD(v73) = a13;
    v72 = a12;
    v71 = a11;
    v70 = a10;
    v69 = a9;
    v68 = a8;
    v67 = a7;
    v66 = a6;
    v65 = a5;
    v54 = L"NULL";
    if ( a4 )
      v54 = a4;
    v64 = v57;
    v63 = LowPart;
    v62 = HighPart;
    v75 = (PSRWLOCK)0x1000000;
    CurrentThreadId = GetCurrentThreadId();
    v55 = *((_QWORD *)this + 34);
    v60 = *(_DWORD *)(v55 + 72);
    v74 = 0;
    p_SRWLock = &SRWLock;
    v121 = 4;
    v118 = &v73;
    v119 = 4;
    v116 = &v72;
    v117 = 4;
    v114 = &v71;
    v115 = 4;
    v112 = &v70;
    v113 = 4;
    v110 = &v69;
    v111 = 4;
    v108 = &v68;
    v109 = 4;
    v106 = &v67;
    v107 = 4;
    v104 = &v66;
    v105 = 4;
    v102 = &v65;
    v103 = 4;
    v56 = -1;
    do
      ++v56;
    while ( *(_WORD *)&v54[2 * v56] );
    v99 = (void *)v54;
    v100 = 2 * v56 + 2;
    v101 = 0;
    v97 = (int *)&v64;
    v98 = 4;
    v95 = &v63;
    v96 = 4;
    v93 = &v62;
    v94 = 4;
    v91 = &v75;
    v92 = 8;
    p_CurrentThreadId = (PSRWLOCK *)&CurrentThreadId;
    v90 = 4;
    v87 = (PSRWLOCK *)&v60;
    v88 = 4;
    v85 = &v74;
    v86 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 517;
    EventDescriptor.Keyword = 0x400000000000LL;
    UserData.Ptr = *(_QWORD *)(v53 + 8);
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    UserData.Reserved = 2;
    v82 = byte_18008FAC1;
    v83 = 297;
    v84 = 1;
    v59 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(*(_QWORD *)(v53 + 32), &EventDescriptor, (LPCGUID)(v55 + 8), 0, 0x14u, &UserData);
  }
LABEL_68:
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((CloudAPProvider::CloudApLogonUser *)((char *)this + 288));
}

```

## disassembly

```asm
0x180039620  mov     [rsp-8+arg_10], rbx
0x180039625  push    rbp
0x180039626  push    rsi
0x180039627  push    rdi
0x180039628  push    r12
0x18003962a  push    r13
0x18003962c  push    r14
0x18003962e  push    r15
0x180039630  lea     rbp, [rsp-1E0h]
0x180039638  sub     rsp, 2E0h
0x18003963f  mov     rax, cs:__security_cookie
0x180039646  xor     rax, rsp
0x180039649  mov     [rbp+210h+var_40], rax
0x180039650  mov     r12, r9
0x180039653  mov     [rsp+310h+var_2E0], r8d
0x180039658  mov     rdi, rdx
0x18003965b  mov     r14, rcx
0x18003965e  mov     r15, rdx
0x180039661  shr     r15, 20h
0x180039665  xor     r13d, r13d
0x180039668  mov     rsi, [rcx+110h]
0x18003966f  mov     eax, [rsi+48h]
0x180039672  test    eax, eax
0x180039674  jns     loc_180039C62
0x18003967a  add     rsi, 50h ; 'P'
0x18003967e  cmp     eax, [rsi+8]
0x180039681  jnz     loc_180039C62
0x180039687  mov     rbx, [rcx+118h]
0x18003968e  test    rsi, rsi
0x180039691  jz      loc_180039C69
0x180039697  test    rbx, rbx
0x18003969a  jz      short loc_1800396E1
0x18003969c  add     rbx, 108h
0x1800396a3  mov     rcx, rbx; SRWLock
0x1800396a6  call    cs:__imp_AcquireSRWLockExclusive
0x1800396ac  lea     rax, [rsp+310h+SRWLock]
0x1800396b1  mov     [rax], r13
0x1800396b4  mov     rcx, [rsp+310h+SRWLock]; SRWLock
0x1800396b9  test    rcx, rcx
0x1800396bc  jz      short loc_1800396C4
0x1800396be  call    cs:__imp_ReleaseSRWLockExclusive
0x1800396c4  mov     rax, [r14+110h]
0x1800396cb  mov     dword ptr [rax], 2
0x1800396d1  test    rbx, rbx
0x1800396d4  jz      short loc_180039706
0x1800396d6  mov     rcx, rbx; SRWLock
0x1800396d9  call    cs:__imp_ReleaseSRWLockExclusive
0x1800396df  jmp     short loc_180039706
0x1800396e1  lea     rax, [rsp+310h+var_298]
0x1800396e6  mov     [rax], r13
0x1800396e9  mov     rcx, [rsp+310h+var_298]; SRWLock
0x1800396ee  test    rcx, rcx
0x1800396f1  jz      short loc_1800396F9
0x1800396f3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800396f9  mov     rax, [r14+110h]
0x180039700  mov     dword ptr [rax], 2
0x180039706  call    ?Instance@CloudAPProvider@@KAPEAV1@XZ; CloudAPProvider::Instance(void)
0x18003970b  mov     rdx, [rax+8]
0x18003970f  mov     [rsp+310h+SRWLock], rdx
0x180039714  mov     eax, [rdx]
0x180039716  cmp     eax, 5
0x180039719  jbe     loc_180039FB2
0x18003971f  mov     rcx, [rdx+18h]
0x180039723  mov     rax, [rdx+10h]
0x180039727  mov     r13, 400000000000h
0x180039731  test    r13, rax
0x180039734  jz      loc_180039FB2
0x18003973a  mov     rax, rcx
0x18003973d  and     rax, r13
0x180039740  cmp     rax, rcx
0x180039743  jnz     loc_180039FB2
0x180039749  mov     eax, [rbp+210h+arg_68]
0x18003974f  mov     [rbp+210h+var_280], eax
0x180039752  mov     eax, [rbp+210h+arg_60]
0x180039758  mov     [rbp+210h+var_27C], eax
0x18003975b  mov     eax, [rbp+210h+arg_58]
0x180039761  mov     [rbp+210h+var_278], eax
0x180039764  mov     eax, [rbp+210h+arg_50]
0x18003976a  mov     [rsp+310h+var_2D0], eax
0x18003976e  mov     eax, [rbp+210h+arg_48]
0x180039774  mov     [rsp+310h+var_2CC], eax
0x180039778  mov     eax, [rbp+210h+arg_40]
0x18003977e  mov     [rsp+310h+var_2C8], eax
0x180039782  mov     eax, [rbp+210h+arg_38]
0x180039788  mov     [rsp+310h+var_2C4], eax
0x18003978c  mov     eax, [rbp+210h+arg_30]
0x180039792  mov     [rsp+310h+var_2C0], eax
0x180039796  mov     eax, [rbp+210h+arg_28]
0x18003979c  mov     [rsp+310h+var_2BC], eax
0x1800397a0  mov     eax, [rbp+210h+arg_20]
0x1800397a6  mov     [rsp+310h+var_2B8], eax
0x1800397aa  lea     rbx, aNull_0; "NULL"
0x1800397b1  test    r12, r12
0x1800397b4  cmovnz  rbx, r12
0x1800397b8  mov     eax, [rsp+310h+var_2E0]
0x1800397bc  mov     [rsp+310h+var_2E0], eax
0x1800397c0  mov     [rsp+310h+var_2B4], edi
0x1800397c4  mov     [rsp+310h+var_2B0], r15d
0x1800397c9  mov     [rbp+210h+var_260], 1000000h
0x1800397d1  mov     rdx, [rsi+78h]
0x1800397d5  mov     r8, [rsi+70h]
0x1800397d9  mov     eax, [rsi+68h]
0x1800397dc  mov     [rsp+310h+var_2AC], eax
0x1800397e0  mov     r9, [rsi+60h]
0x1800397e4  mov     r10, [rsi+58h]
0x1800397e8  mov     eax, [rsi+50h]
0x1800397eb  mov     [rsp+310h+var_2A8], eax
0x1800397ef  mov     r11, [rsi+48h]
0x1800397f3  mov     eax, [rsi+20h]
0x1800397f6  mov     [rsp+310h+var_2A4], eax
0x1800397fa  mov     rdi, [rsi+18h]
0x1800397fe  mov     eax, [rsi]
0x180039800  mov     [rsp+310h+var_2A0], eax
0x180039804  mov     r15, [rsi+80h]
0x18003980b  mov     eax, [rsi+40h]
0x18003980e  mov     [rsp+310h+var_29C], eax
0x180039812  mov     r12, [rsi+38h]
0x180039816  mov     eax, [rsi+8]
0x180039819  mov     dword ptr [rsp+310h+var_298], eax
0x18003981d  mov     [rbp+210h+var_290], 1000000h
0x180039825  xor     ecx, ecx
0x180039827  mov     [rbp+210h+var_288], rcx
0x18003982b  mov     rsi, [r14+110h]
0x180039832  lea     rax, [rbp+210h+var_280]
0x180039836  mov     [rbp+210h+var_50], rax
0x18003983d  mov     [rbp+210h+var_48], 4
0x180039848  lea     rax, [rbp+210h+var_27C]
0x18003984c  mov     [rbp+210h+var_60], rax
0x180039853  mov     [rbp+210h+var_58], 4
0x18003985e  lea     rax, [rbp+210h+var_278]
0x180039862  mov     [rbp+210h+var_70], rax
0x180039869  mov     [rbp+210h+var_68], 4
0x180039874  lea     rax, [rsp+310h+var_2D0]
0x180039879  mov     [rbp+210h+var_80], rax
0x180039880  mov     [rbp+210h+var_78], 4
0x18003988b  lea     rax, [rsp+310h+var_2CC]
0x180039890  mov     [rbp+210h+var_90], rax
0x180039897  mov     [rbp+210h+var_88], 4
0x1800398a2  lea     rax, [rsp+310h+var_2C8]
0x1800398a7  mov     [rbp+210h+var_A0], rax
0x1800398ae  mov     [rbp+210h+var_98], 4
0x1800398b9  lea     rax, [rsp+310h+var_2C4]
0x1800398be  mov     [rbp+210h+var_B0], rax
0x1800398c5  mov     [rbp+210h+var_A8], 4
0x1800398d0  lea     rax, [rsp+310h+var_2C0]
0x1800398d5  mov     [rbp+210h+var_C0], rax
0x1800398dc  mov     [rbp+210h+var_B8], 4
0x1800398e7  lea     rax, [rsp+310h+var_2BC]
0x1800398ec  mov     [rbp+210h+var_D0], rax
0x1800398f3  mov     [rbp+210h+var_C8], 4
0x1800398fe  lea     rax, [rsp+310h+var_2B8]
0x180039903  mov     [rbp+210h+var_E0], rax
0x18003990a  mov     [rbp+210h+var_D8], 4
0x180039915  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003991c  mov     rax, rcx
0x18003991f  nop
0x180039920  lea     rax, [rax+1]
0x180039924  cmp     word ptr [rbx+rax*2], 0
0x180039929  jnz     short loc_180039920
0x18003992b  mov     [rbp+210h+var_F0], rbx
0x180039932  lea     eax, ds:2[rax*2]
0x180039939  mov     [rbp+210h+var_E8], eax
0x18003993f  xor     ebx, ebx
0x180039941  mov     [rbp+210h+var_E4], ebx
0x180039947  lea     rax, [rsp+310h+var_2E0]
0x18003994c  mov     [rbp+210h+var_100], rax
0x180039953  mov     [rbp+210h+var_F8], 4
0x18003995e  lea     rax, [rsp+310h+var_2B4]
0x180039963  mov     [rbp+210h+var_110], rax
0x18003996a  mov     [rbp+210h+var_108], 4
0x180039975  lea     rax, [rsp+310h+var_2B0]
0x18003997a  mov     [rbp+210h+var_120], rax
0x180039981  mov     [rbp+210h+var_118], 4
0x18003998c  lea     rax, [rbp+210h+var_260]
0x180039990  mov     [rbp+210h+var_130], rax
0x180039997  mov     [rbp+210h+var_128], 8
0x1800399a2  test    rdx, rdx
0x1800399a5  jz      short loc_1800399C3
0x1800399a7  mov     rax, rcx
0x1800399aa  nop     word ptr [rax+rax+00h]
0x1800399b0  lea     rax, [rax+1]
0x1800399b4  cmp     [rdx+rax*2], bx
0x1800399b8  jnz     short loc_1800399B0
0x1800399ba  lea     eax, ds:2[rax*2]
0x1800399c1  jmp     short loc_1800399CF
0x1800399c3  lea     rdx, Class
0x1800399ca  mov     eax, 2
0x1800399cf  mov     [rbp+210h+var_140], rdx
0x1800399d6  mov     dword ptr [rbp+210h+var_138], eax
0x1800399dc  mov     dword ptr [rbp+210h+var_138+4], ebx
0x1800399e2  test    r8, r8
0x1800399e5  jz      short loc_1800399FD
0x1800399e7  mov     rax, rcx
0x1800399ea  nop     word ptr [rax+rax+00h]
0x1800399f0  inc     rax
0x1800399f3  cmp     [r8+rax], bl
0x1800399f7  jnz     short loc_1800399F0
0x1800399f9  inc     eax
0x1800399fb  jmp     short loc_180039A09
0x1800399fd  lea     r8, byte_1800865C9
0x180039a04  mov     eax, 1
0x180039a09  mov     [rbp+210h+var_150], r8
0x180039a10  mov     dword ptr [rbp+210h+var_148], eax
0x180039a16  mov     dword ptr [rbp+210h+var_148+4], ebx
0x180039a1c  lea     rax, [rsp+310h+var_2AC]
0x180039a21  mov     [rbp+210h+var_160], rax
0x180039a28  mov     [rbp+210h+var_158], 4
0x180039a33  test    r9, r9
0x180039a36  jz      short loc_180039A54
0x180039a38  mov     rax, rcx
0x180039a3b  nop     dword ptr [rax+rax+00h]
0x180039a40  lea     rax, [rax+1]
0x180039a44  cmp     [r9+rax*2], bx
0x180039a49  jnz     short loc_180039A40
0x180039a4b  lea     eax, ds:2[rax*2]
0x180039a52  jmp     short loc_180039A60
0x180039a54  lea     r9, Class
0x180039a5b  mov     eax, 2
0x180039a60  mov     [rbp+210h+var_170], r9
0x180039a67  mov     dword ptr [rbp+210h+var_168], eax
0x180039a6d  mov     dword ptr [rbp+210h+var_168+4], ebx
0x180039a73  test    r10, r10
0x180039a76  jz      short loc_180039A8D
0x180039a78  mov     rax, rcx
0x180039a7b  nop     dword ptr [rax+rax+00h]
0x180039a80  inc     rax
0x180039a83  cmp     [r10+rax], bl
0x180039a87  jnz     short loc_180039A80
0x180039a89  inc     eax
0x180039a8b  jmp     short loc_180039A99
0x180039a8d  lea     r10, byte_1800865C9
0x180039a94  mov     eax, 1
0x180039a99  mov     [rbp+210h+var_180], r10
0x180039aa0  mov     dword ptr [rbp+210h+var_178], eax
0x180039aa6  mov     dword ptr [rbp+210h+var_178+4], ebx
0x180039aac  lea     rax, [rsp+310h+var_2A8]
0x180039ab1  mov     [rbp+210h+var_190], rax
0x180039ab8  mov     [rbp+210h+var_188], 4
0x180039ac3  test    r11, r11
0x180039ac6  jz      short loc_180039ADD
0x180039ac8  mov     rax, rcx
0x180039acb  nop     dword ptr [rax+rax+00h]
0x180039ad0  inc     rax
0x180039ad3  cmp     [r11+rax], bl
0x180039ad7  jnz     short loc_180039AD0
0x180039ad9  inc     eax
0x180039adb  jmp     short loc_180039AE9
0x180039add  lea     r11, byte_1800865C9
0x180039ae4  mov     eax, 1
0x180039ae9  mov     [rbp+210h+var_1A0], r11
0x180039aed  mov     dword ptr [rbp+210h+var_198], eax
0x180039af0  mov     dword ptr [rbp+210h+var_198+4], ebx
0x180039af3  lea     rax, [rsp+310h+var_2A4]
0x180039af8  mov     [rbp+210h+var_1B0], rax
0x180039afc  mov     [rbp+210h+var_1A8], 4
0x180039b04  test    rdi, rdi
0x180039b07  jz      short loc_180039B23
0x180039b09  mov     rax, rcx
0x180039b0c  nop     dword ptr [rax+00h]
0x180039b10  lea     rax, [rax+1]
0x180039b14  cmp     [rdi+rax*2], bx
0x180039b18  jnz     short loc_180039B10
0x180039b1a  lea     eax, ds:2[rax*2]
0x180039b21  jmp     short loc_180039B2F
0x180039b23  lea     rdi, Class
0x180039b2a  mov     eax, 2
0x180039b2f  mov     [rbp+210h+var_1C0], rdi
0x180039b33  mov     [rbp+210h+var_1B8], eax
0x180039b36  mov     [rbp+210h+var_1B4], ebx
0x180039b39  lea     rax, [rsp+310h+var_2A0]
0x180039b3e  mov     [rbp+210h+var_1D0], rax
0x180039b42  mov     [rbp+210h+var_1C8], 4
0x180039b4a  test    r15, r15
0x180039b4d  jz      short loc_180039B5F
0x180039b4f  mov     rax, rcx
0x180039b52  inc     rax
0x180039b55  cmp     [r15+rax], bl
0x180039b59  jnz     short loc_180039B52
0x180039b5b  inc     eax
0x180039b5d  jmp     short loc_180039B6B
0x180039b5f  lea     r15, byte_1800865C9
0x180039b66  mov     eax, 1
0x180039b6b  mov     [rbp+210h+var_1E0], r15
0x180039b6f  mov     dword ptr [rbp+210h+var_1D8], eax
0x180039b72  mov     dword ptr [rbp+210h+var_1D8+4], ebx
0x180039b75  lea     rax, [rsp+310h+var_29C]
0x180039b7a  mov     [rbp+210h+var_1F0], rax
0x180039b7e  mov     [rbp+210h+var_1E8], 4
0x180039b86  test    r12, r12
0x180039b89  jz      short loc_180039B9D
0x180039b8b  nop     dword ptr [rax+rax+00h]
0x180039b90  inc     rcx
0x180039b93  cmp     [r12+rcx], bl
0x180039b97  jnz     short loc_180039B90
0x180039b99  inc     ecx
0x180039b9b  jmp     short loc_180039BA9
0x180039b9d  lea     r12, byte_1800865C9
0x180039ba4  mov     ecx, 1
0x180039ba9  mov     [rbp+210h+var_200], r12
0x180039bad  mov     dword ptr [rbp+210h+var_1F8], ecx
  ... truncated ...
```
