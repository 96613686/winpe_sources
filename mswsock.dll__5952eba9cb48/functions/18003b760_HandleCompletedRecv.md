# HandleCompletedRecv

- ea: `0x18003b760`
- end: `0x18003c7c3`
- name: `HandleCompletedRecv`
- size: `4195`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004a520`

## callees

- `0x180023a5c`
- `0x180023f14`
- `0x180024518`
- `0x180037195`
- `0x180038104`
- `0x180038944`
- `0x180038a20`
- `0x18003ae8c`
- `0x18003b054`
- `0x18003b760`
- `0x18003c7cc`
- `0x18003cdc8`
- `0x18003dae8`
- `0x18003f28c`
- `0x18003f2e0`
- `0x180041b44`
- `0x180042128`
- `0x180046088`
- `0x1800462b0`
- `0x1800485dc`
- `0x18004958c`
- `0x180049af0`
- `0x180049eac`
- `0x18004c204`
- `0x18004c4b8`
- `0x18004fb58`
- `0x18004ff80`
- `0x180051a68`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b9f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003bc9f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003be7d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003bf79`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c022`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c136`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c277`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c483`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c636`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c74f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b9f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003bc9f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003be7d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003bf79`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c022`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c136`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c277`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c483`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c636`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c74f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b84d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003be40`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003bfc5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c0be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c261`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c312`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c365`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c617`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c6d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b84d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003be40`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003bfc5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c0be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c261`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c312`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c365`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c617`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c6d6`

## pseudocode

```c
void __fastcall HandleCompletedRecv(__int64 a1, unsigned int a2, int a3)
{
  unsigned int v3; // r12d
  __int64 v4; // rdi
  __int64 v5; // rbx
  __int64 v6; // r15
  __int64 v7; // r15
  char v8; // al
  __int64 v9; // r13
  char v10; // dl
  char v11; // cl
  _DWORD *v12; // r12
  __int64 *v13; // rax
  __int64 v14; // rcx
  unsigned int v15; // r12d
  __int64 v16; // rdx
  int v17; // eax
  int v18; // ebx
  __int64 *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rcx
  int v22; // eax
  _QWORD *v23; // rbx
  unsigned int v24; // ecx
  __int64 v25; // r12
  __int64 v26; // r14
  _QWORD *v27; // rdx
  __int64 *v28; // rax
  __int64 v29; // rcx
  unsigned int v30; // r13d
  int v31; // eax
  int v32; // eax
  unsigned int v33; // edx
  unsigned int v34; // ebx
  _QWORD *v35; // rcx
  __int64 v36; // rax
  struct _RTL_CRITICAL_SECTION *v37; // r12
  __int64 v38; // rcx
  _QWORD *v39; // rax
  __int64 v40; // rdx
  _QWORD *v41; // r8
  _QWORD *v42; // rdx
  __int64 *v43; // rax
  __int64 v44; // rcx
  unsigned int v45; // r12d
  int v46; // ebx
  _QWORD *v47; // rcx
  __int64 v48; // rdx
  struct _RTL_CRITICAL_SECTION *v49; // rbx
  unsigned int v50; // eax
  __int64 v51; // rbx
  __int64 v52; // rdx
  __int64 v53; // rax
  _QWORD *v54; // rdx
  _QWORD *v55; // rax
  int v56; // r13d
  __int64 v57; // r9
  int v58; // r12d
  unsigned int v59; // ebx
  int v60; // r12d
  bool v61; // zf
  __int64 v62; // rbx
  int v63; // eax
  _QWORD *v64; // rbx
  struct _RTL_CRITICAL_SECTION *v65; // r15
  _QWORD *v66; // rdx
  int v67; // r8d
  __int64 v68; // rax
  _QWORD *v69; // rcx
  _QWORD *v70; // rcx
  __int64 *v71; // rax
  signed __int32 v72[8]; // [rsp+0h] [rbp-138h] BYREF
  unsigned int v73; // [rsp+40h] [rbp-F8h] BYREF
  unsigned int v74; // [rsp+44h] [rbp-F4h] BYREF
  size_t Size; // [rsp+48h] [rbp-F0h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+50h] [rbp-E8h]
  _DWORD *v77; // [rsp+58h] [rbp-E0h]
  __int64 v78; // [rsp+60h] [rbp-D8h]
  __int64 v79; // [rsp+68h] [rbp-D0h]
  unsigned int v80; // [rsp+70h] [rbp-C8h] BYREF
  __int64 v81; // [rsp+78h] [rbp-C0h]
  _QWORD *v82; // [rsp+80h] [rbp-B8h]
  int v83; // [rsp+88h] [rbp-B0h]
  __int64 v84; // [rsp+90h] [rbp-A8h]
  __int64 v85; // [rsp+98h] [rbp-A0h]
  unsigned int v86; // [rsp+A0h] [rbp-98h]
  int v87; // [rsp+A4h] [rbp-94h] BYREF
  __int64 v88; // [rsp+A8h] [rbp-90h]
  unsigned int v89; // [rsp+B0h] [rbp-88h]
  __int64 v90; // [rsp+B8h] [rbp-80h]
  __int64 v91; // [rsp+C0h] [rbp-78h]
  volatile __int32 *v92; // [rsp+C8h] [rbp-70h]
  volatile __int32 *v93; // [rsp+D0h] [rbp-68h]
  int v94; // [rsp+D8h] [rbp-60h] BYREF
  _OWORD v95[5]; // [rsp+E0h] [rbp-58h]
  char i; // [rsp+140h] [rbp+8h]
  unsigned int v97; // [rsp+148h] [rbp+10h]
  int v98; // [rsp+150h] [rbp+18h]
  unsigned __int8 v99; // [rsp+158h] [rbp+20h]
  __int64 v100; // [rsp+158h] [rbp+20h]
  unsigned int v101; // [rsp+158h] [rbp+20h]

  v98 = a3;
  v97 = a2;
  v3 = a2;
  v80 = 0;
  v4 = *(_QWORD *)(a1 + 56);
  v91 = v4;
  *(_DWORD *)(a1 + 88) = a2;
  *(_DWORD *)(a1 + 28) = a3;
  _InterlockedOr(v72, 0);
  *(_BYTE *)(a1 + 85) = 1;
LABEL_2:
  v93 = (volatile __int32 *)(v4 + 40);
  if ( _InterlockedIncrement((volatile signed __int32 *)(v4 + 40)) == 1 )
  {
    v92 = (volatile __int32 *)(v4 + 40);
    v5 = v4 + 304;
    v82 = (_QWORD *)(v4 + 304);
    v79 = v4 + 304;
    v90 = v4 + 304;
    v6 = *(_QWORD *)(v4 + 304);
    if ( v6 == v4 + 304 )
    {
      v7 = 0;
      v8 = 0;
    }
    else
    {
      v7 = v6 - 40;
      v8 = *(_BYTE *)(v7 + 85);
      v3 = *(_DWORD *)(v7 + 88);
      v97 = v3;
      v98 = *(_DWORD *)(v7 + 28);
    }
LABEL_6:
    while ( 2 )
    {
      for ( i = v8; ; v8 = i )
      {
        v78 = v7;
        if ( !v7 || !v8 )
        {
          if ( _InterlockedExchange(v93, 0) != 1 )
            goto LABEL_2;
          return;
        }
        v73 = 0;
        v87 = 0;
        v74 = 0;
        lpCriticalSection = (LPCRITICAL_SECTION)(v4 + 48);
        EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 48));
        v9 = *(_QWORD *)(v7 + 96);
        v85 = v9;
        v99 = *(_BYTE *)(v9 + 20) & 1;
        v10 = *(_BYTE *)(v9 + 24);
        if ( v10 != 4
          || (*(_BYTE *)(v4 + 801) & 8) == 0
          || (v11 = 1, v3 != *(_DWORD *)(*(_QWORD *)(v4 + 16) + 20LL) + 32) )
        {
          v11 = 0;
        }
        if ( v10 && !v11 && v10 != 2 )
          goto LABEL_102;
        if ( v98 )
          goto LABEL_102;
        if ( (*(_BYTE *)(v9 + 20) & 1) != 0 )
          goto LABEL_102;
        v12 = (_DWORD *)(v4 + 444);
        v77 = (_DWORD *)(v4 + 444);
        v88 = v4 + 444;
        if ( *(_DWORD *)(v9 + 8) != *(_DWORD *)(v4 + 444) || !v97 )
          goto LABEL_102;
        if ( v11 )
        {
          if ( *(_QWORD *)(v4 + 336) == v4 + 336
            && *(_QWORD *)(v4 + 352) == v4 + 352
            && (*(_BYTE *)(*(_QWORD *)v4 + 69LL) & 1) == 0
            && (*(_BYTE *)(*(_QWORD *)(v4 + 216) + 24LL) & 4) != 0 )
          {
            v13 = *(__int64 **)v5;
            if ( *(_QWORD *)(*(_QWORD *)v5 + 8LL) != v90 )
              goto LABEL_224;
            v14 = *v13;
            if ( *(__int64 **)(*v13 + 8) != v13 )
              goto LABEL_224;
            *(_QWORD *)v5 = v14;
            *(_QWORD *)(v14 + 8) = v79;
            --*(_DWORD *)(v4 + 436);
            ++*v12;
            if ( *(_DWORD *)(v4 + 120) || (v15 = 1, *(_DWORD *)(v4 + 616)) )
              v15 = 0;
            _InterlockedDecrement((volatile signed __int32 *)(v4 + 448));
            v16 = (unsigned int)(*(_DWORD *)(v9 + 12) + *(_DWORD *)(v9 + 16) - *(_DWORD *)(v4 + 440));
            v17 = *(_DWORD *)(v4 + 432);
            if ( v17 <= (int)v16 )
              v17 = *(_DWORD *)(v9 + 12) + *(_DWORD *)(v9 + 16) - *(_DWORD *)(v4 + 440);
            *(_DWORD *)(v4 + 432) = v17;
            if ( (BYTE1(xmmword_180063D60) & 0x10) != 0 )
              WPP_SF_qD(1036, 92, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, v4, *(_DWORD *)(v9 + 8));
            *(_DWORD *)(v4 + 884) = 0;
            v18 = PushLargeSendFCInfo(v4, v16, *(unsigned int *)(v9 + 28), v9 + 32);
            LeaveCriticalSection(lpCriticalSection);
            PostReceive((PVOID)v4);
            if ( v18 )
              *(_DWORD *)(v4 + 244) = *(_DWORD *)(v9 + 8);
            else
              SendControlMessage((PVOID)v4, 0, 0);
            if ( *(_QWORD *)(v4 + 400) != v4 + 400 || *(_QWORD *)(v4 + 416) != v4 + 416 )
              RestartBlockedSends((PVOID)v4);
            NotifyAfdOfReceiveComplete(v4, v15, 0);
            CheckPendingAppRecvs((PVOID)v4);
            goto LABEL_209;
          }
          goto LABEL_102;
        }
        if ( v10 != 2 )
          break;
        if ( *(_DWORD *)(v4 + 248) )
          goto LABEL_102;
        *(_DWORD *)(v4 + 464) = 1;
        v19 = *(__int64 **)v5;
        v20 = v79;
        if ( *(_QWORD *)(*(_QWORD *)v5 + 8LL) != v79 )
          goto LABEL_224;
        v21 = *v19;
        if ( *(__int64 **)(*v19 + 8) != v19 )
          goto LABEL_224;
        *(_QWORD *)v5 = v21;
        *(_QWORD *)(v21 + 8) = v20;
        --*(_DWORD *)(v4 + 436);
        ++*v12;
        if ( (BYTE1(xmmword_180063D60) & 0x10) != 0 )
          WPP_SF_dd(
            1036,
            94,
            WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids,
            (unsigned int)*(char *)(v9 + 24),
            *(_DWORD *)(v9 + 8));
        _InterlockedDecrement((volatile signed __int32 *)(v4 + 448));
        v22 = *(_DWORD *)(v4 + 432);
        if ( v22 <= *(_DWORD *)(v9 + 12) + *(_DWORD *)(v9 + 16) - *(_DWORD *)(v4 + 440) )
          v22 = *(_DWORD *)(v9 + 12) + *(_DWORD *)(v9 + 16) - *(_DWORD *)(v4 + 440);
        *(_DWORD *)(v4 + 432) = v22;
        ProcessRdmaReadCompletion(v4, *(unsigned int *)(v9 + 28), *(unsigned int *)(v9 + 32));
        *(_DWORD *)(v4 + 464) = 0;
        PostReceive((PVOID)v4);
LABEL_210:
        v64 = (_QWORD *)(v4 + 352);
        if ( (_QWORD *)*v64 != v64 )
        {
          v65 = lpCriticalSection;
          EnterCriticalSection(lpCriticalSection);
          v66 = (_QWORD *)*v64;
          v67 = 0;
          while ( v66 != v64 )
          {
            i = *((_BYTE *)v66 + 45);
            if ( *(_DWORD *)(v66[7] + 8LL) == *v12 )
            {
              v67 = 1;
              break;
            }
            v66 = (_QWORD *)*v66;
          }
          if ( v67 )
          {
            v68 = *v66;
            if ( *(_QWORD **)(*v66 + 8LL) != v66 )
              goto LABEL_224;
            v69 = (_QWORD *)v66[1];
            if ( (_QWORD *)*v69 != v66 )
              goto LABEL_224;
            *v69 = v68;
            *(_QWORD *)(v68 + 8) = v69;
            v70 = v82;
            v71 = (__int64 *)*v82;
            if ( *(_QWORD **)(*v82 + 8LL) != v82 )
              goto LABEL_224;
            *v66 = v71;
            v66[1] = v70;
            v71[1] = (__int64)v66;
            *v70 = v66;
          }
          LeaveCriticalSection(v65);
        }
        v5 = (__int64)v82;
        if ( (_QWORD *)*v82 != v82 )
        {
          v7 = *v82 - 40LL;
          v8 = *(_BYTE *)(v7 + 85);
          v98 = *(_DWORD *)(v7 + 28);
          v3 = *(_DWORD *)(v7 + 88);
          v97 = v3;
          goto LABEL_6;
        }
LABEL_111:
        v7 = 0;
        v3 = v97;
      }
      v23 = (_QWORD *)(v4 + 320);
      if ( ((_QWORD *)*v23 != v23 || *(_QWORD *)(v4 + 296))
        && *(_QWORD *)(v4 + 336) == v4 + 336
        && *(_QWORD *)(v4 + 352) == v4 + 352
        && v97 > 0x28
        && !*(_DWORD *)(v4 + 240)
        && (*(_BYTE *)(*(_QWORD *)v4 + 69LL) & 1) == 0
        && (*(_BYTE *)(*(_QWORD *)(v4 + 216) + 24LL) & 4) != 0 )
      {
        v24 = v97 - 40;
        LODWORD(Size) = v97 - 40;
        v25 = 0;
        if ( *(_QWORD *)(v4 + 296) )
          v25 = _InterlockedExchange64((volatile __int64 *)(v4 + 296), 0);
        v81 = v25;
        if ( v25 )
        {
          if ( *(_DWORD *)(v25 + 12) < v24 )
          {
            *(_DWORD *)(v25 + 20) = 997;
            _InterlockedOr(v72, 0);
            goto LABEL_102;
          }
          v26 = 0;
          v84 = 0;
LABEL_64:
          v100 = 0;
          memcpy_0(&v94, *(const void **)v25, 16LL * *(unsigned int *)(v25 + 8));
          goto LABEL_65;
        }
        if ( (_QWORD *)*v23 != v23 )
        {
          v26 = *v23 - 16LL;
          if ( *v23 == 16
            || *(int *)(v26 + 56) <= 2
            && *(_DWORD *)(v26 + 80) >= (signed int)v24
            && !*(_QWORD *)(v26 + 120)
            && !*(_QWORD *)(v26 + 136)
            && !*(_DWORD *)(v26 + 36)
            && !*(_DWORD *)(v26 + 108)
            && !*(_QWORD *)(v26 + 64)
            && (*(_BYTE *)(v26 + 60) & 3) == 0 )
          {
            v84 = *v23 - 16LL;
            if ( !v26 )
              goto LABEL_64;
            memcpy_0(&v94, *(const void **)(v26 + 48), 16LL * *(int *)(v26 + 56));
            v35 = *(_QWORD **)(v4 + 320);
            if ( (_QWORD *)v35[1] != v23 )
              goto LABEL_224;
            v36 = *v35;
            if ( *(_QWORD **)(*v35 + 8LL) != v35 )
              goto LABEL_224;
            v100 = *(_QWORD *)(v26 + 8);
            *v23 = v36;
            *(_QWORD *)(v36 + 8) = v23;
            if ( *(_QWORD *)(v4 + 504) == v26 )
              *(_QWORD *)(v4 + 504) = 0;
            ReleaseWsaBufArray(v4, *(_QWORD *)(v26 + 48));
            ReleaseApplicationBuffer(v4, v26);
LABEL_65:
            v27 = v82;
            v28 = (__int64 *)*v82;
            if ( *(_QWORD **)(*v82 + 8LL) != v82 )
              goto LABEL_224;
            v29 = *v28;
            if ( *(__int64 **)(*v28 + 8) != v28 )
              goto LABEL_224;
            v30 = 0;
            *v82 = v29;
            *(_QWORD *)(v29 + 8) = v27;
            --*(_DWORD *)(v4 + 436);
            ++*v77;
            _InterlockedDecrement((volatile signed __int32 *)(v4 + 448));
            v31 = *(_DWORD *)(v4 + 432);
            if ( v31 <= *(_DWORD *)(v85 + 12) + *(_DWORD *)(v85 + 16) - *(_DWORD *)(v4 + 440) )
              v31 = *(_DWORD *)(v85 + 12) + *(_DWORD *)(v85 + 16) - *(_DWORD *)(v4 + 440);
            *(_DWORD *)(v4 + 432) = v31;
            LeaveCriticalSection(lpCriticalSection);
            v74 = 0;
            v32 = 0;
            v83 = 0;
            v33 = Size;
            while ( v33 )
            {
              v34 = v95[v32];
              if ( v33 < v34 )
                v34 = v33;
              memcpy_0(*(void **)&v95[v32], (const void *)(*(_QWORD *)(v7 + 96) + 40LL + v30), v34);
              v33 = Size - v34;
              LODWORD(Size) = v33;
              v89 = v33;
              v30 += v34;
              v86 = v30;
              v32 = ++v83;
            }
            if ( v26 )
            {
              CompleteOverlappedIO(*(_QWORD *)(*(_QWORD *)v4 + 8LL), v100, 0, 0, v74, v30);
            }
            else
            {
              *(_DWORD *)(v25 + 16) = v30;
              _InterlockedOr(v72, 0);
              *(_DWORD *)(v25 + 20) = v74;
              _InterlockedOr(v72, 0);
            }
            if ( !v74 || (CheckPendingAppRecvs((PVOID)v4), !v74) )
            {
              _InterlockedAdd((volatile signed __int32 *)(v4 + 456), 1u);
              PostReceive((PVOID)v4);
            }
            if ( *(_QWORD *)(v4 + 400) != v4 + 400 || *(_QWORD *)(v4 + 416) != v4 + 416 )
              RestartBlockedSends((PVOID)v4);
            if ( *(_DWORD *)(v4 + 176) == 1 || *(_BYTE *)(v4 + 208) )
              CheckForSocketDuplicationProtocol((char *)v4);
LABEL_209:
            v12 = v77;
            goto LABEL_210;
          }
        }
      }
LABEL_102:
      v37 = lpCriticalSection;
      LeaveCriticalSection(lpCriticalSection);
      v38 = *(_QWORD *)(v4 + 104);
      v77 = (_DWORD *)(v4 + 444);
      if ( *(_DWORD *)(v9 + 8) == *(_DWORD *)(v4 + 444) || !v97 || *(_DWORD *)(v7 + 28) )
      {
        if ( v38 != -1 )
        {
          LODWORD(v84) = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *, _QWORD, int *, unsigned int *))(*(_QWORD *)(v4 + 16) + 152LL))(
                           v38,
                           v7 + 8,
                           &v73,
                           0,
                           &v87,
                           &v74);
          if ( (_DWORD)v84 )
            goto LABEL_117;
          goto LABEL_116;
        }
      }
      else if ( v38 != -1 )
      {
        EnterCriticalSection(v37);
        v5 = (__int64)v82;
        v39 = (_QWORD *)*v82;
        if ( *(_QWORD **)(*v82 + 8LL) != v82 )
          goto LABEL_224;
        v40 = *v39;
        if ( *(_QWORD **)(*v39 + 8LL) != v39 )
          goto LABEL_224;
        *v82 = v40;
        *(_QWORD *)(v40 + 8) = v5;
        v41 = *(_QWORD **)(v4 + 360);
        if ( *v41 != v4 + 352 )
          goto LABEL_224;
        *v39 = v4 + 352;
        v39[1] = v41;
        *v41 = v39;
        *(_QWORD *)(v4 + 360) = v39;
        LeaveCriticalSection(v37);
        if ( *(_QWORD *)v5 != v5 )
        {
          v7 = *(_QWORD *)v5 - 40LL;
          v8 = *(_BYTE *)(v7 + 85);
          v3 = v97;
          continue;
        }
        goto LABEL_111;
      }
      break;
    }
    LODWORD(v84) = 0;
    v74 = 10054;
LABEL_116:
    v73 = 0;
LABEL_117:
    EnterCriticalSection(v37);
    _InterlockedDecrement((volatile signed __int32 *)(v4 + 448));
    v42 = v82;
    v43 = (__int64 *)*v82;
    if ( *(_QWORD **)(*v82 + 8LL) != v82 )
      goto LABEL_224;
    v44 = *v43;
    if ( *(__int64 **)(*v43 + 8) != v43 )
      goto LABEL_224;
    LODWORD(v78) = 0;
    v45 = 0;
    LODWORD(v81) = 0;
    *v82 = v44;
    *(_QWORD *)(v44 + 8) = v42;
    if ( v73 )
    {
      --*(_DWORD *)(v4 + 436);
      ++*(_DWORD *)(v4 + 444);
    }
    if ( *(_DWORD *)(v4 + 168) == 3 )
    {
      v46 = 1;
      *(_DWORD *)(v4 + 168) = 0;
    }
    else
    {
      v46 = 0;
    }
    LODWORD(Size) = v46;
    LeaveCriticalSection(lpCriticalSection);
    if ( (xmmword_180063D60 & 0x80u) != 0LL )
      WPP_SF_qD(1031, 102, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, v7, v73);
    if ( v73 )
    {
      if ( (xmmword_180063D60 & 0x80u) != 0LL )
        WPP_SF_d(1031, 104, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, *(unsigned int *)(v4 + 436));
      LODWORD(v78) = *(_DWORD *)(v4 + 176);
      v45 = HandleControlMessage((char *)v4, v9);
      LODWORD(v81) = v45;
      if ( v46 )
      {
        v47 = (_QWORD *)(v4 + 224);
        v48 = *(_QWORD *)(v4 + 224);
        if ( *(_QWORD *)(v48 + 8) != v4 + 224 )
LABEL_224:
          __fastfail(3u);
        *(_QWORD *)(v7 + 40) = v48;
        *(_QWORD *)(v7 + 48) = v47;
        *(_QWORD *)(v48 + 8) = v7 + 40;
        *v47 = v7 + 40;
        _InterlockedExchange(v92, 0);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 676), 0xFFFFFFFF) == 1 )
          SockSanDeleteHalfAcceptedSocket((char *)v4);
        ContinueAcceptProcessing((PVOID)v4);
        return;
      }
    }
    if ( v73 > v45 || *(_BYTE *)(v9 + 24) == 4 && v73 )
    {
      if ( (xmmword_180063D60 & 0x80u) != 0LL )
        WPP_SF_(1031, 105, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids);
      if ( (*(_BYTE *)(*(_QWORD *)v4 + 69LL) & 1) != 0 )
      {
        v49 = lpCriticalSection;
        EnterCriticalSection(lpCriticalSection);
        *(_BYTE *)(v4 + 800) |= 4u;
        LeaveCriticalSection(v49);
        if ( (*(_BYTE *)(*(_QWORD *)v4 + 69LL) & 2) != 0 )
          SendControlMessage((PVOID)v4, 0, 0);
        v50 = AbortSanConnection(v4);
        v74 = v50;
        if ( v50 && (xmmword_180063D60 & 2) != 0 )
          WPP_SF_d(1025, 106, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, v50);
LABEL_179:
        if ( v73 <= v45 )
        {
          if ( v73 || *(_DWORD *)(v4 + 136) )
          {
            v60 = Size;
          }
          else
          {
            if ( (xmmword_180063D60 & 0x80u) != 0LL )
              WPP_SF_(1031, v73 + 108, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids);
            v60 = Size;
            if ( (_DWORD)Size )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 676), 0xFFFFFFFF) == 1 )
                SockSanDeleteHalfAcceptedSocket((char *)v4);
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 676), 0xFFFFFFFF) == 1 )
                SockSanDeleteHalfAcceptedSocket((char *)v4);
              return;
            }
            if ( (unsigned int)(*(_DWORD *)(v4 + 176) - 1) > 1 || !(_DWORD)v84 && (*(_BYTE *)(v4 + 801) & 1) == 0 )
              HandleRemoteClose((PVOID)v4);
          }
          v61 = v73 == 0;
          if ( !v73 )
          {
            if ( (_QWORD *)*v82 == v82 )
            {
              if ( (*(_BYTE *)(v4 + 800) & 1) != 0 )
                v74 = ContinueGracefulDisconnect(v4);
              if ( _InterlockedIncrement((volatile signed __int32 *)(v4 + 888)) == 3 )
              {
                EnterCriticalSection(v49);
                v62 = *(_QWORD *)(v4 + 824);
                *(_QWORD *)(v4 + 824) = 0;
                LeaveCriticalSection(lpCriticalSection);
                if ( v62 )
                  DoTPReuse(v4, v62);
              }
            }
            v61 = v73 == 0;
          }
          if ( !v61 )
          {
            v63 = *(_DWORD *)(v4 + 176);
            if ( (v63 != 1 || (*(_BYTE *)(v4 + 801) & 1) == 0) && v63 != 2 )
              v74 = PostReceive((PVOID)v4);
          }
          if ( !v60 )
            RestartBlockedSends((PVOID)v4);
        }
        goto LABEL_209;
      }
      v51 = v7;
      v88 = v7;
      if ( v73 == v45 )
      {
        v101 = *(_DWORD *)(v4 + 120) == 0;
        v80 = 0;
        EnterCriticalSection(lpCriticalSection);
        v45 = v81;
      }
      else
      {
        RestartBlockedSends((PVOID)v4);
        if ( (xmmword_180063D60 & 0x80u) != 0LL )
          WPP_SF_(1031, 107, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids);
        *(_DWORD *)(v7 + 80) = v45;
        *(_BYTE *)(v7 + 87) = v99;
        EnterCriticalSection(lpCriticalSection);
        v53 = CheckSoRcvBuf(v4, v7, v73 - v45);
        v7 = v53;
        if ( v53 )
        {
          v54 = *(_QWORD **)(v4 + 344);
          if ( *v54 != v4 + 336 )
            goto LABEL_224;
          v55 = (_QWORD *)(v53 + 40);
          *v55 = v4 + 336;
          v55[1] = v54;
          *v54 = v55;
          *(_QWORD *)(v4 + 344) = v55;
        }
        v101 = AdjustReceiveBytesBufferedOnReceiveComplete(v4, v73 - v45, v99, &v80);
      }
      v56 = 1;
      if ( *(_BYTE *)(v85 + 24) == 4 )
      {
        v57 = v85 + 32;
        if ( (*(_BYTE *)(v4 + 801) & 8) == 0 )
          v57 = 0;
        v56 = PushLargeSendFCInfo(v4, v52, *(unsigned int *)(v85 + 28), v57);
      }
      if ( v73 <= v45 || *(_DWORD *)(v4 + 436) > 2u || (v58 = 1, *(_DWORD *)(v4 + 448) <= 2u) )
        v58 = 0;
      if ( v51 != v7 || (v59 = 2, v58) )
      {
        if ( (*(_BYTE *)(v4 + 801) & 4) != 0
          || *(_QWORD *)(v4 + 400) == v4 + 400
          || *(_DWORD *)(v4 + 432) > 2u
          || !(unsigned __int8)InitializeStuckSendTracker(v4) )
        {
          v59 = 2;
        }
        else
        {
          *(_DWORD *)(*(_QWORD *)(v4 + 512) + 40LL) = 1;
          *(_DWORD *)(*(_QWORD *)(v4 + 512) + 44LL) = *(_DWORD *)(v4 + 440);
          v59 = 1;
        }
      }
      LeaveCriticalSection(lpCriticalSection);
      if ( v88 == v7 )
      {
        if ( v58 )
          UpdateSendCredit(v4, v59);
      }
      else
      {
        v74 = PostReceive((PVOID)v4);
      }
      if ( v56 )
      {
        if ( *(_BYTE *)(v85 + 24) == 4 )
          *(_DWORD *)(v4 + 244) = *(_DWORD *)(v85 + 8);
      }
      else
      {
        SendControlMessage((PVOID)v4, 0, 0);
      }
      NotifyAfdOfReceiveComplete(v4, v101, v80);
      CheckPendingAppRecvs((PVOID)v4);
      v45 = v81;
    }
    v49 = lpCriticalSection;
    goto LABEL_179;
  }
}

```

## disassembly

```asm
0x18003b760  mov     [rsp+arg_10], r8d
0x18003b765  mov     [rsp+arg_8], edx
0x18003b769  push    rbx
0x18003b76a  push    rsi
0x18003b76b  push    rdi
0x18003b76c  push    r12
0x18003b76e  push    r13
0x18003b770  push    r14
0x18003b772  push    r15
0x18003b774  sub     rsp, 100h
0x18003b77b  mov     r12d, edx
0x18003b77e  xor     esi, esi
0x18003b780  mov     [rsp+138h+var_C8], esi
0x18003b784  mov     rdi, [rcx+38h]
0x18003b788  mov     [rsp+138h+var_78], rdi
0x18003b790  mov     [rcx+58h], edx
0x18003b793  mov     [rcx+1Ch], r8d
0x18003b797  lock or [rsp+138h+var_138], esi
0x18003b79b  lea     r14d, [rsi+1]
0x18003b79f  mov     [rcx+55h], r14b
0x18003b7a3  lea     rcx, [rdi+28h]
0x18003b7a7  mov     [rsp+138h+var_68], rcx
0x18003b7af  mov     eax, r14d
0x18003b7b2  lock xadd [rcx], eax
0x18003b7b6  add     eax, r14d
0x18003b7b9  cmp     eax, r14d
0x18003b7bc  jnz     loc_18003C7AF
0x18003b7c2  mov     [rsp+138h+var_70], rcx
0x18003b7ca  lea     rbx, [rdi+130h]
0x18003b7d1  mov     [rsp+138h+var_B8], rbx
0x18003b7d9  mov     [rsp+138h+var_D0], rbx
0x18003b7de  mov     [rsp+138h+var_80], rbx
0x18003b7e6  mov     r15, [rbx]
0x18003b7e9  cmp     r15, rbx
0x18003b7ec  jz      short loc_18003B80F
0x18003b7ee  add     r15, 0FFFFFFFFFFFFFFD8h
0x18003b7f2  mov     al, [r15+55h]
0x18003b7f6  mov     r12d, [r15+58h]
0x18003b7fa  mov     [rsp+138h+arg_8], r12d
0x18003b802  mov     ecx, [r15+1Ch]
0x18003b806  mov     [rsp+138h+arg_10], ecx
0x18003b80d  jmp     short loc_18003B815
0x18003b80f  mov     r15, rsi
0x18003b812  mov     al, sil
0x18003b815  mov     [rsp+138h+arg_0], al
0x18003b81c  mov     [rsp+138h+var_D8], r15
0x18003b821  test    r15, r15
0x18003b824  jz      loc_18003C79A
0x18003b82a  test    al, al
0x18003b82c  jz      loc_18003C79A
0x18003b832  mov     [rsp+138h+var_F8], esi
0x18003b836  mov     [rsp+138h+var_94], esi
0x18003b83d  mov     [rsp+138h+var_F4], esi
0x18003b841  lea     rax, [rdi+30h]
0x18003b845  mov     [rsp+138h+lpCriticalSection], rax
0x18003b84a  mov     rcx, rax; lpCriticalSection
0x18003b84d  call    cs:__imp_EnterCriticalSection
0x18003b854  nop     dword ptr [rax+rax+00h]
0x18003b859  mov     r13, [r15+60h]
0x18003b85d  mov     [rsp+138h+var_A0], r13
0x18003b865  mov     r8b, [r13+14h]
0x18003b869  and     r8b, r14b
0x18003b86c  mov     byte ptr [rsp+138h+arg_18], r8b
0x18003b874  mov     dl, [r13+18h]
0x18003b878  mov     r9b, 4
0x18003b87b  cmp     dl, r9b
0x18003b87e  jnz     short loc_18003B89B
0x18003b880  test    byte ptr [rdi+321h], 8
0x18003b887  jz      short loc_18003B89B
0x18003b889  mov     rax, [rdi+10h]
0x18003b88d  mov     ecx, [rax+14h]
0x18003b890  add     ecx, 20h ; ' '
0x18003b893  cmp     r12d, ecx
0x18003b896  mov     cl, r14b
0x18003b899  jz      short loc_18003B89E
0x18003b89b  mov     cl, sil
0x18003b89e  test    dl, dl
0x18003b8a0  jz      short loc_18003B8AF
0x18003b8a2  test    cl, cl
0x18003b8a4  jnz     short loc_18003B8AF
0x18003b8a6  cmp     dl, 2
0x18003b8a9  jnz     loc_18003BF71
0x18003b8af  cmp     [rsp+138h+arg_10], esi
0x18003b8b6  jnz     loc_18003BF71
0x18003b8bc  test    r8b, r8b
0x18003b8bf  jnz     loc_18003BF71
0x18003b8c5  lea     r12, [rdi+1BCh]
0x18003b8cc  mov     [rsp+138h+var_E0], r12
0x18003b8d1  mov     [rsp+138h+var_90], r12
0x18003b8d9  mov     eax, [r12]
0x18003b8dd  cmp     [r13+8], eax
0x18003b8e1  jnz     loc_18003BF71
0x18003b8e7  mov     r8d, [rsp+138h+arg_8]
0x18003b8ef  test    r8d, r8d
0x18003b8f2  jz      loc_18003BF71
0x18003b8f8  test    cl, cl
0x18003b8fa  jz      loc_18003BA75
0x18003b900  lea     rax, [rdi+150h]
0x18003b907  cmp     [rax], rax
0x18003b90a  jnz     loc_18003BF71
0x18003b910  lea     rax, [rdi+160h]
0x18003b917  cmp     [rax], rax
0x18003b91a  jnz     loc_18003BF71
0x18003b920  mov     rax, [rdi]
0x18003b923  test    [rax+45h], r14b
0x18003b927  jnz     loc_18003BF71
0x18003b92d  mov     rax, [rdi+0D8h]
0x18003b934  test    [rax+18h], r9b
0x18003b938  jz      loc_18003BF71
0x18003b93e  mov     rax, [rbx]
0x18003b941  mov     rcx, [rsp+138h+var_80]
0x18003b949  cmp     [rax+8], rcx
0x18003b94d  jnz     loc_18003C793
0x18003b953  mov     rcx, [rax]
0x18003b956  cmp     [rcx+8], rax
0x18003b95a  jnz     loc_18003C793
0x18003b960  mov     [rbx], rcx
0x18003b963  mov     rax, [rsp+138h+var_D0]
0x18003b968  mov     [rcx+8], rax
0x18003b96c  dec     dword ptr [rdi+1B4h]
0x18003b972  add     [r12], r14d
0x18003b976  cmp     [rdi+78h], esi
0x18003b979  jnz     short loc_18003B986
0x18003b97b  cmp     [rdi+268h], esi
0x18003b981  mov     r12d, r14d
0x18003b984  jz      short loc_18003B989
0x18003b986  mov     r12d, esi
0x18003b989  lock dec dword ptr [rdi+1C0h]
0x18003b990  mov     edx, [r13+10h]
0x18003b994  sub     edx, [rdi+1B8h]
0x18003b99a  add     edx, [r13+0Ch]
0x18003b99e  mov     eax, [rdi+1B0h]
0x18003b9a4  cmp     eax, edx
0x18003b9a6  cmovle  eax, edx
0x18003b9a9  mov     [rdi+1B0h], eax
0x18003b9af  test    byte ptr cs:xmmword_180063D60+1, 10h
0x18003b9b6  jz      short loc_18003B9D9
0x18003b9b8  mov     edx, 5Ch ; '\'
0x18003b9bd  mov     ecx, 40Ch
0x18003b9c2  mov     eax, [r13+8]
0x18003b9c6  mov     dword ptr [rsp+138h+var_118], eax
0x18003b9ca  mov     r9, rdi
0x18003b9cd  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x18003b9d4  call    WPP_SF_qD
0x18003b9d9  mov     [rdi+374h], esi
0x18003b9df  lea     r9, [r13+20h]
0x18003b9e3  mov     r8d, [r13+1Ch]
0x18003b9e7  mov     rcx, rdi
0x18003b9ea  call    PushLargeSendFCInfo
0x18003b9ef  mov     ebx, eax
0x18003b9f1  mov     rcx, [rsp+138h+lpCriticalSection]; lpCriticalSection
0x18003b9f6  call    cs:__imp_LeaveCriticalSection
0x18003b9fd  nop     dword ptr [rax+rax+00h]
0x18003ba02  mov     r8d, r14d
0x18003ba05  mov     rdx, r15
0x18003ba08  mov     rcx, rdi; CompletionContext
0x18003ba0b  call    PostReceive
0x18003ba10  test    ebx, ebx
0x18003ba12  jnz     short loc_18003BA30
0x18003ba14  mov     [rsp+138h+var_110], rsi
0x18003ba19  mov     [rsp+138h+var_118], rsi
0x18003ba1e  xor     r9d, r9d
0x18003ba21  xor     r8d, r8d
0x18003ba24  mov     dl, 8
0x18003ba26  mov     rcx, rdi
0x18003ba29  call    SendControlMessage
0x18003ba2e  jmp     short loc_18003BA3A
0x18003ba30  mov     eax, [r13+8]
0x18003ba34  mov     [rdi+0F4h], eax
0x18003ba3a  lea     rax, [rdi+190h]
0x18003ba41  cmp     [rax], rax
0x18003ba44  jnz     short loc_18003BA52
0x18003ba46  lea     rax, [rdi+1A0h]
0x18003ba4d  cmp     [rax], rax
0x18003ba50  jz      short loc_18003BA5A
0x18003ba52  mov     rcx, rdi; CompletionContext
0x18003ba55  call    RestartBlockedSends
0x18003ba5a  xor     r8d, r8d
0x18003ba5d  mov     edx, r12d
0x18003ba60  mov     rcx, rdi
0x18003ba63  call    NotifyAfdOfReceiveComplete
0x18003ba68  mov     rcx, rdi; CompletionContext
0x18003ba6b  call    CheckPendingAppRecvs
0x18003ba70  jmp     loc_18003C6B9
0x18003ba75  cmp     dl, 2
0x18003ba78  jnz     loc_18003BB54
0x18003ba7e  cmp     [rdi+0F8h], esi
0x18003ba84  jnz     loc_18003BF71
0x18003ba8a  mov     [rdi+1D0h], r14d
0x18003ba91  mov     rax, [rbx]
0x18003ba94  mov     rdx, [rsp+138h+var_D0]
0x18003ba99  cmp     [rax+8], rdx
0x18003ba9d  jnz     loc_18003C793
0x18003baa3  mov     rcx, [rax]
0x18003baa6  cmp     [rcx+8], rax
0x18003baaa  jnz     loc_18003C793
0x18003bab0  mov     [rbx], rcx
0x18003bab3  mov     [rcx+8], rdx
0x18003bab7  dec     dword ptr [rdi+1B4h]
0x18003babd  add     [r12], r14d
0x18003bac1  test    byte ptr cs:xmmword_180063D60+1, 10h
0x18003bac8  jz      short loc_18003BAED
0x18003baca  movsx   r9d, byte ptr [r13+18h]
0x18003bacf  mov     edx, 5Eh ; '^'
0x18003bad4  mov     ecx, 40Ch
0x18003bad9  mov     eax, [r13+8]
0x18003badd  mov     dword ptr [rsp+138h+var_118], eax
0x18003bae1  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x18003bae8  call    WPP_SF_dd
0x18003baed  lock dec dword ptr [rdi+1C0h]
0x18003baf4  mov     edx, [r13+10h]
0x18003baf8  sub     edx, [rdi+1B8h]
0x18003bafe  add     edx, [r13+0Ch]
0x18003bb02  mov     eax, [rdi+1B0h]
0x18003bb08  cmp     eax, edx
0x18003bb0a  cmovle  eax, edx
0x18003bb0d  mov     [rdi+1B0h], eax
0x18003bb13  mov     r8d, [r13+20h]
0x18003bb17  mov     edx, [r13+1Ch]
0x18003bb1b  mov     rcx, rdi
0x18003bb1e  call    ProcessRdmaReadCompletion
0x18003bb23  mov     [rdi+1D0h], esi
0x18003bb29  cmp     dword ptr [rdi+1B4h], 2
0x18003bb30  ja      short loc_18003BB41
0x18003bb32  cmp     dword ptr [rdi+1C0h], 2
0x18003bb39  mov     r8d, 2
0x18003bb3f  jnb     short loc_18003BB44
0x18003bb41  mov     r8d, r14d
0x18003bb44  mov     rdx, r15
0x18003bb47  mov     rcx, rdi; CompletionContext
0x18003bb4a  call    PostReceive
0x18003bb4f  jmp     loc_18003C6BE
0x18003bb54  lea     rbx, [rdi+140h]
0x18003bb5b  cmp     [rbx], rbx
0x18003bb5e  jnz     short loc_18003BB6D
0x18003bb60  cmp     [rdi+128h], rsi
0x18003bb67  jz      loc_18003BF71
0x18003bb6d  lea     rax, [rdi+150h]
0x18003bb74  cmp     [rax], rax
0x18003bb77  jnz     loc_18003BF71
0x18003bb7d  lea     rax, [rdi+160h]
0x18003bb84  cmp     [rax], rax
0x18003bb87  jnz     loc_18003BF71
0x18003bb8d  cmp     r8d, 28h ; '('
0x18003bb91  jbe     loc_18003BF71
0x18003bb97  cmp     [rdi+0F0h], esi
0x18003bb9d  jnz     loc_18003BF71
0x18003bba3  mov     rax, [rdi]
0x18003bba6  test    [rax+45h], r14b
0x18003bbaa  jnz     loc_18003BF71
0x18003bbb0  mov     rax, [rdi+0D8h]
0x18003bbb7  test    [rax+18h], r9b
0x18003bbbb  jz      loc_18003BF71
0x18003bbc1  lea     ecx, [r8-28h]
0x18003bbc5  mov     dword ptr [rsp+138h+Size], ecx
0x18003bbc9  mov     r12, rsi
0x18003bbcc  cmp     [rdi+128h], rsi
0x18003bbd3  jz      short loc_18003BBDC
0x18003bbd5  xchg    r12, [rdi+128h]
0x18003bbdc  mov     [rsp+138h+var_C0], r12
0x18003bbe1  test    r12, r12
0x18003bbe4  jz      loc_18003BD21
0x18003bbea  cmp     [r12+0Ch], ecx
0x18003bbef  jnb     short loc_18003BC03
0x18003bbf1  mov     dword ptr [r12+14h], 3E5h
0x18003bbfa  lock or [rsp+138h+var_138], esi
0x18003bbfe  jmp     loc_18003BF71
0x18003bc03  mov     r14, rsi
0x18003bc06  mov     [rsp+138h+var_A8], rsi
0x18003bc0e  mov     [rsp+138h+arg_18], rsi
0x18003bc16  mov     r8d, [r12+8]
0x18003bc1b  shl     r8, 4; Size
0x18003bc1f  mov     rdx, [r12]; Src
0x18003bc23  lea     rcx, [rsp+138h+var_60]; void *
0x18003bc2b  call    memcpy_0
0x18003bc30  mov     rdx, [rsp+138h+var_B8]
0x18003bc38  mov     rax, [rdx]
0x18003bc3b  mov     r8, rdx
0x18003bc3e  cmp     [rax+8], rdx
0x18003bc42  jnz     loc_18003C793
0x18003bc48  mov     rcx, [rax]
0x18003bc4b  cmp     [rcx+8], rax
0x18003bc4f  jnz     loc_18003C793
0x18003bc55  mov     r13d, esi
0x18003bc58  mov     [rdx], rcx
0x18003bc5b  mov     [rcx+8], rdx
0x18003bc5f  dec     dword ptr [rdi+1B4h]
0x18003bc65  mov     rax, [rsp+138h+var_E0]
0x18003bc6a  inc     dword ptr [rax]
0x18003bc6c  lock dec dword ptr [rdi+1C0h]
0x18003bc73  mov     r8, [rsp+138h+var_A0]
0x18003bc7b  mov     edx, [r8+10h]
0x18003bc7f  sub     edx, [rdi+1B8h]
0x18003bc85  add     edx, [r8+0Ch]
0x18003bc89  mov     eax, [rdi+1B0h]
0x18003bc8f  cmp     eax, edx
0x18003bc91  cmovle  eax, edx
0x18003bc94  mov     [rdi+1B0h], eax
0x18003bc9a  mov     rcx, [rsp+138h+lpCriticalSection]; lpCriticalSection
0x18003bc9f  call    cs:__imp_LeaveCriticalSection
  ... truncated ...
```
