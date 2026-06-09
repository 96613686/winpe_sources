# CThreadInputMgr::OnActiveProfileChange(void)

- ea: `0x180019180`
- end: `0x180019b8f`
- name: `?OnActiveProfileChange@CThreadInputMgr@@UEAAXXZ`
- size: `2575`
- prototype: `void __fastcall(CThreadInputMgr *__hidden this)`
- caller_count: `0`
- callee_count: `24`
- tags: `file_ops, installer_update`

## callees

- `0x18000e120`
- `0x18000f170`
- `0x18000fcf0`
- `0x1800128f8`
- `0x180018354`
- `0x1800190c8`
- `0x180019150`
- `0x180019180`
- `0x180019cfc`
- `0x18002acb0`
- `0x18002da10`
- `0x18002db70`
- `0x180033e50`
- `0x180039dd4`
- `0x18003a930`
- `0x18006cab4`
- `0x180085884`
- `0x1800884b0`
- `0x180089830`
- `0x180089de0`
- `0x180094864`
- `0x18009ead2`
- `0x1800a18d4`
- `0x18010a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800194e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800194e4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019334`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800194a4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019751`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800199a8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019334`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800194a4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019751`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800199a8`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18001928a`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18001982f`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18001928a`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18001982f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019541`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019551`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019541`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019551`
- `USER32!NotifyWinEvent` at `0x180019aaf`
- `USER32!NotifyWinEvent` at `0x180019aaf`

## pseudocode

```c
void __fastcall CThreadInputMgr::OnActiveProfileChange(CThreadInputMgr *this)
{
  int *v2; // r14
  int v3; // eax
  int v4; // eax
  __int64 v5; // rcx
  int i; // edx
  CVoidStructArray *v7; // r12
  int m; // edi
  __int64 v9; // rbx
  unsigned __int64 v10; // rcx
  HLOCAL v11; // rax
  unsigned int v12; // edi
  int n; // ebx
  struct TF_INPUTPROCESSORPROFILE *v14; // r15
  DWORD dwFlags; // eax
  unsigned int v16; // eax
  unsigned int v17; // r13d
  int ii; // ebx
  unsigned int v19; // r15d
  unsigned int v20; // edi
  _WORD *v21; // rax
  struct MsgBase *v22; // rbx
  int v23; // edi
  CCtfClientPort *Instance; // rax
  CCtfClientPort *v25; // r15
  HWND v26; // rdx
  int jj; // edx
  __int64 v28; // rcx
  int v29; // edx
  int v30; // eax
  int v31; // eax
  __int64 v32; // r15
  __int64 v33; // r12
  int v34; // eax
  __int64 v35; // rax
  __int64 v36; // r15
  char *v37; // r13
  int v38; // ebx
  int v39; // r9d
  __int64 v40; // rax
  unsigned __int64 v41; // rdx
  void *v42; // rcx
  HLOCAL v43; // rax
  int v44; // edx
  int v45; // eax
  __int64 v46; // rcx
  int j; // r13d
  __int64 v48; // r15
  int v49; // eax
  int k; // r8d
  _OWORD *v51; // rax
  int v52; // edx
  __int64 v53; // rdx
  int v54; // r8d
  unsigned int v55; // edi
  bool IsTsf3TIP; // bl
  HLOCAL v57; // rax
  int v58; // r15d
  HLOCAL v59; // [rsp+40h] [rbp-178h] BYREF
  _BYTE v60[8]; // [rsp+48h] [rbp-170h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-168h]
  signed int v62; // [rsp+58h] [rbp-160h]
  int v63; // [rsp+5Ch] [rbp-15Ch]
  int v64; // [rsp+60h] [rbp-158h]
  int v65; // [rsp+68h] [rbp-150h]
  int v66; // [rsp+6Ch] [rbp-14Ch]
  int v67; // [rsp+70h] [rbp-148h]
  int v68; // [rsp+74h] [rbp-144h]
  unsigned int v69; // [rsp+78h] [rbp-140h]
  int v70; // [rsp+7Ch] [rbp-13Ch]
  int v71; // [rsp+80h] [rbp-138h]
  __int64 v72; // [rsp+88h] [rbp-130h]
  __int64 v73; // [rsp+90h] [rbp-128h]
  CVoidStructArray *v74; // [rsp+98h] [rbp-120h]
  _QWORD v75[4]; // [rsp+A0h] [rbp-118h] BYREF
  int v76; // [rsp+C0h] [rbp-F8h] BYREF
  _QWORD *v77; // [rsp+C8h] [rbp-F0h]
  __int64 v78; // [rsp+D0h] [rbp-E8h]
  int v79; // [rsp+D8h] [rbp-E0h]
  const struct TF_INPUTPROCESSORPROFILE **v80; // [rsp+E0h] [rbp-D8h]
  const struct TF_INPUTPROCESSORPROFILE **v81; // [rsp+E8h] [rbp-D0h]
  int v82; // [rsp+F0h] [rbp-C8h]
  int v83; // [rsp+F8h] [rbp-C0h]
  HLOCAL *v84; // [rsp+100h] [rbp-B8h]
  __int64 v85; // [rsp+108h] [rbp-B0h]
  int v86; // [rsp+110h] [rbp-A8h]
  unsigned int *v87; // [rsp+118h] [rbp-A0h]
  unsigned int *v88; // [rsp+120h] [rbp-98h]
  int v89; // [rsp+128h] [rbp-90h]
  _BYTE v90[40]; // [rsp+130h] [rbp-88h] BYREF
  int v91; // [rsp+158h] [rbp-60h]
  unsigned int v92; // [rsp+1C0h] [rbp+8h] BYREF
  const struct TF_INPUTPROCESSORPROFILE *v93; // [rsp+1C8h] [rbp+10h] BYREF
  unsigned int v94; // [rsp+1D0h] [rbp+18h] BYREF
  unsigned int v95; // [rsp+1D8h] [rbp+20h]

  v72 = (__int64)this - 88;
  if ( (*((_BYTE *)this + 3680) & 1) != 0 )
    return;
  v2 = (int *)((char *)this + 3580);
  v75[2] = (char *)this + 3580;
  v3 = *((_DWORD *)this + 895);
  if ( (v3 & 0x1588) != 0 )
  {
    *v2 = v3 | 0x2000;
    CThreadInputMgr::SetTimer((CThreadInputMgr *)((char *)this - 88), (unsigned __int64 *)this + 450, 0xC8u);
    return;
  }
  v75[1] = (char *)this - 88;
  v94 = 0;
  CStructArray<TF_INPUTPROCESSORPROFILE>::CStructArray<TF_INPUTPROCESSORPROFILE>(v60, 10);
  v4 = *v2 | 0x1000;
  *v2 = v4;
  *v2 = v4 & 0xFFFFDFFF;
  v5 = *((_QWORD *)this + 379);
  if ( v5 )
  {
    CInputProfileManager::GetActiveProfiles(v5, v60);
    for ( i = 0; ; ++i )
    {
      v65 = i;
      if ( i >= v62 )
        break;
      *(_DWORD *)((char *)hMem + i * v63 + 80) &= ~1u;
    }
  }
  v7 = 0;
  v74 = 0;
  if ( *((_DWORD *)this + 710) )
  {
    for ( j = 0; j < *((_DWORD *)this + 710); ++j )
    {
      v48 = *((_QWORD *)this + 354) + *((_DWORD *)this + 711) * j;
      v73 = v48;
      v49 = *(_DWORD *)(v48 + 80);
      LOBYTE(v92) = v49 & 1;
      *(_DWORD *)(v48 + 80) = v49 & 0xFFFFFFFE;
      for ( k = 0; ; k = v54 + 1 )
      {
        v66 = k;
        if ( k >= v62 )
          break;
        v93 = (const struct TF_INPUTPROCESSORPROFILE *)((char *)hMem + k * v63);
        if ( (unsigned int)IsEqualProfile((const struct TF_INPUTPROCESSORPROFILE *)v48, v93) )
        {
          v55 = *(_DWORD *)(v53 + 64);
          IsTsf3TIP = CThreadInputMgr::IsTsf3TIP((CThreadInputMgr *)((char *)this - 88), *(_DWORD *)(v48 + 64));
          if ( IsTsf3TIP == CThreadInputMgr::IsTsf3TIP((CThreadInputMgr *)((char *)this - 88), v55) )
          {
            if ( (_BYTE)v92 )
            {
              *(_DWORD *)(v48 + 80) |= 1u;
            }
            else
            {
              v48 = 0;
              v73 = 0;
            }
            v93->dwFlags |= 1u;
          }
          break;
        }
      }
      if ( v48 && (*(_BYTE *)(v48 + 80) & 1) == 0 )
      {
        if ( !v7 )
        {
          v57 = LocalAlloc(0x40u, 0x20u);
          v7 = v57
             ? (CVoidStructArray *)CStructArray<TF_INPUTPROCESSORPROFILE>::CStructArray<TF_INPUTPROCESSORPROFILE>(
                                     v57,
                                     (unsigned int)(j + 1))
             : 0LL;
          v74 = v7;
          if ( !v7 )
            goto LABEL_121;
        }
        v51 = CVoidStructArray::Append(v7, 1);
        if ( !v51 )
        {
          (**(void (__fastcall ***)(CVoidStructArray *, __int64))v7)(v7, 1);
          goto LABEL_121;
        }
        *v51 = *(_OWORD *)v48;
        v51[1] = *(_OWORD *)(v48 + 16);
        v51[2] = *(_OWORD *)(v48 + 32);
        v51[3] = *(_OWORD *)(v48 + 48);
        v51[4] = *(_OWORD *)(v48 + 64);
        *((_QWORD *)v51 + 10) = *(_QWORD *)(v48 + 80);
        v52 = j--;
        CVoidStructArray::Remove((CThreadInputMgr *)((char *)this + 2824), v52, 1);
      }
    }
  }
  for ( m = 0; ; ++m )
  {
    v67 = m;
    if ( m >= v62 )
      break;
    v36 = m * v63;
    v37 = (char *)hMem;
    if ( (*((_BYTE *)hMem + v36 + 80) & 1) != 0 )
      continue;
    v38 = *((_DWORD *)this + 710);
    if ( v38 < 0 || (v39 = v38 + 1, LODWORD(v93) = v38 + 1, __OFSUB__(v38, v38 + 1)) )
    {
      v45 = 0;
    }
    else
    {
      if ( *((_DWORD *)this + 712) < v39 )
      {
        v40 = (unsigned int)(v38 + v38 / 2);
        if ( v39 > (int)v40 )
          v40 = (unsigned int)v39;
        v92 = v40;
        v41 = v40 * *((unsigned int *)this + 711);
        if ( v41 > 0xFFFFFFFF )
          goto LABEL_84;
        v42 = (void *)*((_QWORD *)this + 354);
        v43 = v42 ? LocalReAlloc(v42, (unsigned int)v41, 0x42u) : LocalAlloc(0, (unsigned int)v41);
        if ( !v43 )
          goto LABEL_84;
        *((_QWORD *)this + 354) = v43;
        *((_DWORD *)this + 712) = v92;
        v39 = (int)v93;
      }
      v44 = *((_DWORD *)this + 710);
      if ( v38 < v44 )
        memmove_0(
          (void *)(*((_QWORD *)this + 354) + v39 * *((_DWORD *)this + 711)),
          (const void *)(*((_QWORD *)this + 354) + *((_DWORD *)this + 711) * v38),
          *((_DWORD *)this + 711) * (v44 - v38));
      v38 = ++*((_DWORD *)this + 710);
      v45 = 1;
    }
    if ( v45 )
    {
      v46 = *((_QWORD *)this + 354) + *((_DWORD *)this + 711) * (v38 - 1);
      goto LABEL_80;
    }
LABEL_84:
    v46 = 0;
LABEL_80:
    if ( v46 )
    {
      *(_OWORD *)v46 = *(_OWORD *)&v37[v36];
      *(_OWORD *)(v46 + 16) = *(_OWORD *)&v37[v36 + 16];
      *(_OWORD *)(v46 + 32) = *(_OWORD *)&v37[v36 + 32];
      *(_OWORD *)(v46 + 48) = *(_OWORD *)&v37[v36 + 48];
      *(_OWORD *)(v46 + 64) = *(_OWORD *)&v37[v36 + 64];
      *(_QWORD *)(v46 + 80) = *(_QWORD *)&v37[v36 + 80];
    }
  }
  v9 = (unsigned int)v62;
  v62 = 0;
  if ( v64 > (int)v9 && (int)v9 > 0 && v63 > 0 )
  {
    v10 = v9 * (unsigned int)v63;
    if ( v10 <= 0xFFFFFFFF )
    {
      v11 = LocalReAlloc(hMem, (unsigned int)v10, 0x42u);
      if ( v11 )
      {
        hMem = v11;
        v64 = v9;
      }
    }
  }
  if ( !v7 )
    goto LABEL_16;
  CThreadInputMgr::_CleanupContexts((CThreadInputMgr *)((char *)this - 88));
  v30 = *v2;
  if ( (*v2 & 0x10) != 0 )
  {
    *v2 = v30 | 0x2000;
  }
  else if ( (v30 & 0x2000) == 0 )
  {
LABEL_16:
    v12 = 0;
    v68 = 0;
    for ( n = 0; n < *((_DWORD *)this + 710); ++n )
    {
      v14 = (struct TF_INPUTPROCESSORPROFILE *)(*((_QWORD *)this + 354) + *((_DWORD *)this + 711) * n);
      dwFlags = v14->dwFlags;
      if ( (dwFlags & 1) != 0
        || (v14->dwFlags = dwFlags | 1,
            (int)CThreadInputMgr::ActivateInputProfile((CThreadInputMgr *)((char *)this - 88), v14, 1) >= 0) )
      {
        if ( v14->dwProfileType == 1 )
          v68 = ++v12;
      }
      else
      {
        v29 = n--;
        CVoidStructArray::Remove((CThreadInputMgr *)((char *)this + 2824), v29, 1);
      }
    }
    if ( v12 )
    {
      if ( *((_QWORD *)this + 459) )
      {
        v16 = 4 * v12;
        if ( !is_mul_ok(v12, 4u) )
          v16 = -1;
        v59 = LocalAlloc(0x40u, v16);
        if ( v59 )
        {
          v17 = 0;
          v69 = 0;
          v92 = 0;
          for ( ii = 0; ; ++ii )
          {
            v70 = ii;
            if ( ii >= *((_DWORD *)this + 710) || v92 >= v12 )
              break;
            v31 = *((_DWORD *)this + 711) * ii;
            v32 = v31;
            v33 = *((_QWORD *)this + 354);
            if ( *(_DWORD *)(v31 + v33) == 1 )
            {
              v34 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64))(**((_QWORD **)this + 379) + 16LL))(
                      *((_QWORD *)this + 379),
                      *(unsigned __int16 *)(v31 + v33 + 4),
                      v31 + v33 + 8,
                      v31 + v33 + 24);
              *((_DWORD *)v59 + v92++) = v34;
              v35 = *(_QWORD *)(v32 + v33 + 40) - *(_QWORD *)&GUID_TFCAT_TIP_KEYBOARD.Data1;
              if ( !v35 )
                v35 = *(_QWORD *)(v32 + v33 + 48) - *(_QWORD *)GUID_TFCAT_TIP_KEYBOARD.Data4;
              if ( !v35
                && CThreadInputMgr::IsTsf2TIP((CThreadInputMgr *)((char *)this - 88), *(_DWORD *)(v32 + v33 + 64)) )
              {
                v17 = *((_DWORD *)v59 + v92 - 1);
                v69 = v17;
              }
            }
          }
          v75[0] = &v92;
          LODWORD(v93) = 1;
          v76 = 5;
          v77 = v75;
          v78 = 0;
          v79 = 4;
          v80 = &v93;
          v81 = &v93;
          v82 = 0;
          v83 = 5;
          v84 = &v59;
          v85 = 0;
          v86 = 4;
          v87 = &v92;
          v88 = &v92;
          v89 = 0;
          v95 = 0;
          v94 = 0;
          if ( (int)MsgBase::CalcParamMarshalingSize(1, 2u, (struct tagCPROXY_PARAM *)&v76, &v94) >= 0
            && (v95 = 72, v19 = v94, v20 = v94 + 72, v94 + 72 >= 0x48)
            && (v95 = v94 + 72, v21 = LocalAlloc(0x40u, v20), (v22 = (struct MsgBase *)v21) != 0) )
          {
            if ( v20 > 0x200 )
            {
              LOWORD(v20) = 72;
              v21[1] = 72;
              *((_DWORD *)v21 + 10) |= 0x4000000u;
            }
            else
            {
              v21[1] = v20;
            }
            *v21 = v20 - 40;
            *((_DWORD *)v21 + 14) = 2;
            *((_DWORD *)v21 + 15) = v19;
            *((_QWORD *)v21 + 8) = v21 + 36;
            *((_DWORD *)v21 + 10) |= 0x91000029;
            *((_DWORD *)v21 + 11) = GetCurrentThreadId();
            *((_DWORD *)v22 + 12) = 0;
            v23 = MsgBase::Marshal(v22, 2u, (struct tagCPROXY_PARAM *)&v76);
            if ( v23 >= 0 )
            {
              Instance = CCtfClientPort::CreateInstance();
              v25 = Instance;
              if ( Instance )
              {
                v23 = CCtfClientPort::Send(Instance, v22, 0);
                CCtfClientPort::Release(v25);
              }
              else
              {
                v23 = -2147467259;
              }
            }
            LocalFree(v22);
          }
          else
          {
            v23 = -2147024882;
          }
          if ( v59 )
            LocalFree(v59);
          if ( v23 >= 0 )
          {
            v26 = *(HWND *)(*((_QWORD *)this + 15) + 136LL);
            if ( v26 )
              NotifyWinEvent(0x7FFFFF30u, v26, 61440, 1);
          }
          *v2 |= 0x4000u;
          for ( jj = 0; ; ++jj )
          {
            v71 = jj;
            if ( jj >= *((_DWORD *)this + 704) )
              break;
            v28 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 351) + 8LL * jj) + 56LL);
            if ( v28 )
            {
              (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v28 + 40LL))(v28, v17);
              break;
            }
          }
        }
      }
    }
    else if ( (*v2 & 0x4000) != 0 )
    {
      if ( *((_QWORD *)this + 459) )
      {
        MsgBase::MsgBase((MsgBase *)v90);
        v91 = 1090519081;
        v58 = MsgBase::Send((MsgBase *)v90);
      }
      else
      {
        v58 = v94;
      }
      if ( v58 >= 0 )
        tagSYSTHREAD::NotifyCiceroEvent(*((tagSYSTHREAD **)this + 15), 0x7FFFFF30u, 0xF000u, 0);
      *v2 &= ~0x4000u;
    }
  }
LABEL_121:
  *v2 &= ~0x1000u;
  CThreadInputMgr::UpdateIMMStatus(v72, 2, 0);
  CStructArray<TF_INPUTPROCESSORPROFILE>::~CStructArray<TF_INPUTPROCESSORPROFILE>(v60);
}

```

## disassembly

```asm
0x180019180  mov     r11, rsp
0x180019183  push    rbx
0x180019184  push    rsi
0x180019185  push    rdi
0x180019186  push    r12
0x180019188  push    r13
0x18001918a  push    r14
0x18001918c  push    r15
0x18001918e  sub     rsp, 180h
0x180019195  mov     rsi, rcx
0x180019198  lea     r13, [rcx-58h]
0x18001919c  mov     [rsp+1B8h+var_130], r13
0x1800191a4  test    byte ptr [r13+0EB8h], 1
0x1800191ac  jnz     loc_180019B5E
0x1800191b2  lea     r14, [rcx+0DFCh]
0x1800191b9  mov     [rsp+1B8h+var_108], r14
0x1800191c1  mov     eax, [r14]
0x1800191c4  test    eax, 1588h
0x1800191c9  jnz     loc_180019B71
0x1800191cf  mov     [rsp+1B8h+var_110], r13
0x1800191d7  xor     r15d, r15d
0x1800191da  mov     [r11+18h], r15d
0x1800191de  lea     edx, [r15+0Ah]
0x1800191e2  lea     rcx, [rsp+1B8h+var_170]
0x1800191e7  call    ??0?$CStructArray@UTF_INPUTPROCESSORPROFILE@@@@QEAA@H@Z; CStructArray<TF_INPUTPROCESSORPROFILE>::CStructArray<TF_INPUTPROCESSORPROFILE>(int)
0x1800191ec  mov     eax, [r14]
0x1800191ef  bts     eax, 0Ch
0x1800191f3  mov     [r14], eax
0x1800191f6  btr     eax, 0Dh
0x1800191fa  mov     [r14], eax
0x1800191fd  mov     rcx, [rsi+0BD8h]
0x180019204  test    rcx, rcx
0x180019207  jz      short loc_180019223
0x180019209  lea     rdx, [rsp+1B8h+var_170]
0x18001920e  call    ?GetActiveProfiles@CInputProfileManager@@QEAAJPEAV?$CStructArray@UTF_INPUTPROCESSORPROFILE@@@@@Z; CInputProfileManager::GetActiveProfiles(CStructArray<TF_INPUTPROCESSORPROFILE> *)
0x180019213  xor     edx, edx
0x180019215  mov     [rsp+1B8h+var_150], edx
0x180019219  cmp     edx, [rsp+1B8h+var_160]
0x18001921d  jl      loc_18001980A
0x180019223  xor     r12d, r12d
0x180019226  mov     [rsp+1B8h+var_120], r12
0x18001922e  cmp     [rsi+0B18h], r12d
0x180019235  jnz     loc_18001983A
0x18001923b  xor     edi, edi
0x18001923d  lea     ecx, [rdi+2]
0x180019240  mov     r8d, 0FFFFFFFFh
0x180019246  mov     [rsp+1B8h+var_148], edi
0x18001924a  cmp     edi, [rsp+1B8h+var_160]
0x18001924e  jl      loc_1800196D0
0x180019254  mov     ebx, [rsp+1B8h+var_160]
0x180019258  mov     [rsp+1B8h+var_160], 0
0x180019260  cmp     [rsp+1B8h+var_158], ebx
0x180019264  jle     short loc_18001929E
0x180019266  test    ebx, ebx
0x180019268  jle     short loc_18001929E
0x18001926a  mov     eax, [rsp+1B8h+var_15C]
0x18001926e  test    eax, eax
0x180019270  jle     short loc_18001929E
0x180019272  mov     ecx, eax
0x180019274  imul    rcx, rbx
0x180019278  cmp     rcx, r8
0x18001927b  ja      short loc_18001929E
0x18001927d  mov     edx, ecx; uBytes
0x18001927f  mov     r8d, 42h ; 'B'; uFlags
0x180019285  mov     rcx, [rsp+1B8h+hMem]; hMem
0x18001928a  call    cs:__imp_LocalReAlloc
0x180019290  test    rax, rax
0x180019293  jz      short loc_18001929E
0x180019295  mov     [rsp+1B8h+hMem], rax
0x18001929a  mov     [rsp+1B8h+var_158], ebx
0x18001929e  lea     r13, [rsi-58h]
0x1800192a2  test    r12, r12
0x1800192a5  jnz     loc_1800195F7
0x1800192ab  xor     edi, edi
0x1800192ad  mov     [rsp+1B8h+var_144], edi
0x1800192b1  xor     ebx, ebx
0x1800192b3  mov     [rsp+1B8h+var_184], ebx
0x1800192b7  cmp     ebx, [rsi+0B18h]
0x1800192bd  jl      short loc_1800192DB
0x1800192bf  test    edi, edi
0x1800192c1  jnz     short loc_18001930A
0x1800192c3  test    dword ptr [r14], 4000h
0x1800192ca  jnz     loc_180019ABA
0x1800192d0  mov     r12d, 2
0x1800192d6  jmp     loc_180019B1C
0x1800192db  mov     eax, ebx
0x1800192dd  imul    eax, [rsi+0B1Ch]
0x1800192e4  movsxd  r15, eax
0x1800192e7  add     r15, [rsi+0B10h]
0x1800192ee  mov     eax, [r15+50h]
0x1800192f2  test    al, 1
0x1800192f4  jz      loc_1800195A4
0x1800192fa  cmp     dword ptr [r15], 1
0x1800192fe  jnz     short loc_180019306
0x180019300  inc     edi
0x180019302  mov     [rsp+1B8h+var_144], edi
0x180019306  inc     ebx
0x180019308  jmp     short loc_1800192B3
0x18001930a  cmp     qword ptr [rsi+0E58h], 0
0x180019312  jz      loc_180019A4B
0x180019318  mov     ecx, edi
0x18001931a  mov     eax, 4
0x18001931f  mul     rcx
0x180019322  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180019329  cmovb   rax, rcx
0x18001932d  mov     edx, eax; uBytes
0x18001932f  mov     ecx, 40h ; '@'; uFlags
0x180019334  call    cs:__imp_LocalAlloc
0x18001933a  mov     [rsp+1B8h+var_178], rax
0x18001933f  test    rax, rax
0x180019342  jz      loc_180019A56
0x180019348  xor     r13d, r13d
0x18001934b  mov     [rsp+1B8h+var_140], r13d
0x180019350  mov     [rsp+1B8h+arg_0], r13d
0x180019358  xor     ebx, ebx
0x18001935a  mov     [rsp+1B8h+var_13C], ebx
0x18001935e  cmp     ebx, [rsi+0B18h]
0x180019364  jl      loc_18001962E
0x18001936a  lea     rax, [rsp+1B8h+arg_0]
0x180019372  mov     [rsp+1B8h+var_118], rax
0x18001937a  mov     dword ptr [rsp+1B8h+arg_8], 1
0x180019385  mov     ecx, 5
0x18001938a  mov     [rsp+1B8h+var_F8], ecx
0x180019391  lea     rax, [rsp+1B8h+var_118]
0x180019399  mov     [rsp+1B8h+var_F0], rax
0x1800193a1  mov     [rsp+1B8h+var_E8], 0
0x1800193ad  mov     [rsp+1B8h+var_E0], 4
0x1800193b8  lea     rax, [rsp+1B8h+arg_8]
0x1800193c0  mov     [rsp+1B8h+var_D8], rax
0x1800193c8  lea     rax, [rsp+1B8h+arg_8]
0x1800193d0  mov     [rsp+1B8h+var_D0], rax
0x1800193d8  mov     [rsp+1B8h+var_C8], 0
0x1800193e3  mov     [rsp+1B8h+var_C0], ecx
0x1800193ea  lea     rax, [rsp+1B8h+var_178]
0x1800193ef  mov     [rsp+1B8h+var_B8], rax
0x1800193f7  mov     [rsp+1B8h+var_B0], 0
0x180019403  mov     [rsp+1B8h+var_A8], 4
0x18001940e  lea     rax, [rsp+1B8h+arg_0]
0x180019416  mov     [rsp+1B8h+var_A0], rax
0x18001941e  lea     rax, [rsp+1B8h+arg_0]
0x180019426  mov     [rsp+1B8h+var_98], rax
0x18001942e  mov     [rsp+1B8h+var_90], 0
0x180019439  mov     [rsp+1B8h+arg_18], 0
0x180019444  mov     [rsp+1B8h+arg_10], 0
0x18001944f  lea     r9, [rsp+1B8h+arg_10]; unsigned int *
0x180019457  lea     r8, [rsp+1B8h+var_F8]; struct tagCPROXY_PARAM *
0x18001945f  lea     r12d, [rcx-3]
0x180019463  mov     edx, r12d; unsigned int
0x180019466  lea     ecx, [r12-1]; unsigned int
0x18001946b  call    ?CalcParamMarshalingSize@MsgBase@@SAJKKPEAUtagCPROXY_PARAM@@AEAK@Z; MsgBase::CalcParamMarshalingSize(ulong,ulong,tagCPROXY_PARAM *,ulong &)
0x180019470  test    eax, eax
0x180019472  js      loc_180019624
0x180019478  lea     eax, [r12+46h]
0x18001947d  mov     [rsp+1B8h+arg_18], eax
0x180019484  mov     r15d, [rsp+1B8h+arg_10]
0x18001948c  lea     edi, [r15+48h]
0x180019490  cmp     edi, eax
0x180019492  jb      loc_180019624
0x180019498  mov     [rsp+1B8h+arg_18], edi
0x18001949f  mov     edx, edi; uBytes
0x1800194a1  lea     ecx, [rax-8]; uFlags
0x1800194a4  call    cs:__imp_LocalAlloc
0x1800194aa  mov     rbx, rax
0x1800194ad  test    rax, rax
0x1800194b0  jz      loc_180019624
0x1800194b6  cmp     edi, 200h
0x1800194bc  ja      loc_180019A7D
0x1800194c2  mov     [rax+2], di
0x1800194c6  sub     di, 28h ; '('
0x1800194ca  mov     [rax], di
0x1800194cd  mov     [rax+38h], r12d
0x1800194d1  mov     [rax+3Ch], r15d
0x1800194d5  add     rax, 48h ; 'H'
0x1800194d9  mov     [rbx+40h], rax
0x1800194dd  or      dword ptr [rbx+28h], 91000029h
0x1800194e4  call    cs:__imp_GetCurrentThreadId
0x1800194ea  mov     [rbx+2Ch], eax
0x1800194ed  mov     dword ptr [rbx+30h], 0
0x1800194f4  lea     r8, [rsp+1B8h+var_F8]; struct tagCPROXY_PARAM *
0x1800194fc  mov     edx, r12d; unsigned int
0x1800194ff  mov     rcx, rbx; struct MsgBase *
0x180019502  call    ?Marshal@MsgBase@@SAJPEAU1@KPEAUtagCPROXY_PARAM@@@Z; MsgBase::Marshal(MsgBase *,ulong,tagCPROXY_PARAM *)
0x180019507  mov     edi, eax
0x180019509  mov     [rsp+1B8h+var_180], eax
0x18001950d  test    eax, eax
0x18001950f  js      short loc_18001953E
0x180019511  call    ?CreateInstance@CCtfClientPort@@SAPEAV1@XZ; CCtfClientPort::CreateInstance(void)
0x180019516  mov     r15, rax
0x180019519  test    rax, rax
0x18001951c  jz      loc_180019A90
0x180019522  xor     r8d, r8d; unsigned int
0x180019525  mov     rdx, rbx; struct MsgBase *
0x180019528  mov     rcx, rax; this
0x18001952b  call    ?Send@CCtfClientPort@@QEAAJPEAUMsgBase@@K@Z; CCtfClientPort::Send(MsgBase *,ulong)
0x180019530  mov     edi, eax
0x180019532  mov     [rsp+1B8h+var_180], eax
0x180019536  mov     rcx, r15; this
0x180019539  call    ?Release@CCtfClientPort@@QEAAKXZ; CCtfClientPort::Release(void)
0x18001953e  mov     rcx, rbx; hMem
0x180019541  call    cs:__imp_LocalFree
0x180019547  mov     rcx, [rsp+1B8h+var_178]; hMem
0x18001954c  test    rcx, rcx
0x18001954f  jz      short loc_180019557
0x180019551  call    cs:__imp_LocalFree
0x180019557  test    edi, edi
0x180019559  js      short loc_18001956F
0x18001955b  mov     rax, [rsi+78h]
0x18001955f  mov     rdx, [rax+88h]; hwnd
0x180019566  test    rdx, rdx
0x180019569  jnz     loc_180019A9E
0x18001956f  bts     dword ptr [r14], 0Eh
0x180019574  xor     edx, edx
0x180019576  mov     [rsp+1B8h+var_138], edx
0x18001957d  cmp     edx, [rsi+0B00h]
0x180019583  jge     loc_180019B1C
0x180019589  movsxd  rcx, edx
0x18001958c  mov     rax, [rsi+0AF8h]
0x180019593  mov     rcx, [rax+rcx*8]
0x180019597  mov     rcx, [rcx+38h]
0x18001959b  test    rcx, rcx
0x18001959e  jnz     short loc_1800195E3
0x1800195a0  inc     edx
0x1800195a2  jmp     short loc_180019576
0x1800195a4  or      eax, 1
0x1800195a7  mov     [r15+50h], eax
0x1800195ab  mov     r8d, 1; int
0x1800195b1  mov     rdx, r15; struct TF_INPUTPROCESSORPROFILE *
0x1800195b4  mov     rcx, r13; this
0x1800195b7  call    ?ActivateInputProfile@CThreadInputMgr@@AEAAJPEAUTF_INPUTPROCESSORPROFILE@@H@Z; CThreadInputMgr::ActivateInputProfile(TF_INPUTPROCESSORPROFILE *,int)
0x1800195bc  test    eax, eax
0x1800195be  jns     loc_1800192FA
0x1800195c4  mov     edx, ebx; int
0x1800195c6  dec     ebx
0x1800195c8  mov     [rsp+1B8h+var_184], ebx
0x1800195cc  mov     r8d, 1; int
0x1800195d2  lea     rcx, [rsi+0B08h]; this
0x1800195d9  call    ?Remove@CVoidStructArray@@QEAAXHH@Z; CVoidStructArray::Remove(int,int)
0x1800195de  jmp     loc_180019306
0x1800195e3  mov     rax, [rcx]
0x1800195e6  mov     edx, r13d
0x1800195e9  mov     rax, [rax+28h]
0x1800195ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195f2  jmp     loc_180019B1C
0x1800195f7  mov     r8, r12
0x1800195fa  xor     edx, edx
0x1800195fc  mov     rcx, r13; this
0x1800195ff  call    ?_CleanupContexts@CThreadInputMgr@@QEAAXHPEAV?$CStructArray@UTF_INPUTPROCESSORPROFILE@@@@@Z; CThreadInputMgr::_CleanupContexts(int,CStructArray<TF_INPUTPROCESSORPROFILE> *)
0x180019604  mov     eax, [r14]
0x180019607  test    al, 10h
0x180019609  jnz     loc_180019A39
0x18001960f  bt      eax, 0Dh
0x180019613  jnb     loc_1800192AB
0x180019619  mov     r12d, 2
0x18001961f  jmp     loc_180019B3C
0x180019624  mov     edi, 8007000Eh
0x180019629  jmp     loc_180019547
0x18001962e  cmp     [rsp+1B8h+arg_0], edi
0x180019635  jnb     loc_18001936A
0x18001963b  mov     eax, ebx
0x18001963d  imul    eax, [rsi+0B1Ch]
0x180019644  movsxd  r15, eax
0x180019647  mov     r12, [rsi+0B10h]
0x18001964e  cmp     dword ptr [r15+r12], 1
0x180019653  jnz     short loc_1800196C9
0x180019655  mov     rcx, [rsi+0BD8h]
0x18001965c  mov     rax, [rcx]
0x18001965f  lea     r9, [r12+18h]
0x180019664  add     r9, r15
0x180019667  lea     r8, [r12+8]
0x18001966c  add     r8, r15
0x18001966f  movzx   edx, word ptr [r15+r12+4]
0x180019675  mov     rax, [rax+10h]
0x180019679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001967e  mov     edx, [rsp+1B8h+arg_0]
0x180019685  mov     rcx, [rsp+1B8h+var_178]
0x18001968a  mov     [rcx+rdx*4], eax
0x18001968d  inc     [rsp+1B8h+arg_0]
0x180019694  mov     rax, [r15+r12+28h]
0x180019699  sub     rax, qword ptr cs:GUID_TFCAT_TIP_KEYBOARD.Data1
0x1800196a0  jnz     short loc_1800196AE
0x1800196a2  mov     rax, [r15+r12+30h]
0x1800196a7  sub     rax, qword ptr cs:GUID_TFCAT_TIP_KEYBOARD.Data4
0x1800196ae  test    rax, rax
0x1800196b1  jnz     short loc_1800196C9
0x1800196b3  mov     edx, [r15+r12+40h]; unsigned int
0x1800196b8  lea     rcx, [rsi-58h]; this
0x1800196bc  call    ?IsTsf2TIP@CThreadInputMgr@@QEAA_NK@Z; CThreadInputMgr::IsTsf2TIP(ulong)
0x1800196c1  test    al, al
0x1800196c3  jnz     loc_180019A61
0x1800196c9  inc     ebx
0x1800196cb  jmp     loc_18001935A
0x1800196d0  mov     eax, [rsp+1B8h+var_15C]
0x1800196d4  imul    eax, edi
0x1800196d7  movsxd  r15, eax
0x1800196da  mov     r13, [rsp+1B8h+hMem]
0x1800196df  test    byte ptr [r15+r13+50h], 1
0x1800196e5  jnz     loc_180019803
0x1800196eb  mov     ebx, [rsi+0B18h]
0x1800196f1  test    ebx, ebx
0x1800196f3  js      loc_18001991B
  ... truncated ...
```
