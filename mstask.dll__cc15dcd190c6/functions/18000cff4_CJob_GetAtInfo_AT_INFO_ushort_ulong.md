# CJob::GetAtInfo(_AT_INFO *,ushort *,ulong *)

- ea: `0x18000cff4`
- end: `0x18000d3f1`
- name: `?GetAtInfo@CJob@@QEAAJPEAU_AT_INFO@@PEAGPEAK@Z`
- size: `1021`
- prototype: `__int64 __fastcall(CJob *__hidden this, struct _AT_INFO *, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f100`

## callees

- `0x180001840`
- `0x180006f90`
- `0x1800085d8`
- `0x1800092a8`
- `0x18000cff4`
- `0x18000d3f8`
- `0x18000d41c`
- `0x180019440`
- `0x18001aac0`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000d2a2`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000d2a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d080`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d15d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d167`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d1fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d080`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d15d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d167`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d1fb`

## pseudocode

```c
int __fastcall CJob::GetAtInfo(CJob *this, struct _AT_INFO *a2, unsigned __int16 *a3, unsigned int *a4)
{
  int result; // eax
  __int64 v9; // rax
  int v10; // eax
  void *v11; // rcx
  int v12; // ebx
  int v13; // r9d
  __int64 v14; // rdx
  __int64 v15; // r14
  void *v16; // rcx
  unsigned int v17; // eax
  unsigned __int64 v18; // rdx
  struct _TASK_TRIGGER *Trigger; // rax
  __int16 v20; // r10
  struct _TASK_TRIGGER *v21; // rbx
  int v22; // edx
  int wStartMinute; // ecx
  TASK_TRIGGER_TYPE TriggerType; // ecx
  __int32 v25; // ecx
  __int16 v26; // ax
  struct _TASK_TRIGGER *v27; // rax
  int v28; // edx
  TASK_TRIGGER_TYPE v29; // ecx
  __int32 v30; // ecx
  __int16 v31; // ax
  char v32; // al
  __int64 v33; // rax
  unsigned __int16 *v34; // [rsp+30h] [rbp-69h]
  unsigned __int16 *v35; // [rsp+30h] [rbp-69h]
  unsigned __int16 v36; // [rsp+40h] [rbp-59h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-51h] BYREF
  int v38; // [rsp+50h] [rbp-49h] BYREF
  unsigned __int16 *v39; // [rsp+58h] [rbp-41h] BYREF
  struct _SYSTEMTIME v40; // [rsp+60h] [rbp-39h] BYREF
  struct _SYSTEMTIME v41; // [rsp+70h] [rbp-29h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+80h] [rbp-19h] BYREF
  struct _SYSTEMTIME v43; // [rsp+90h] [rbp-9h] BYREF

  if ( (*((_DWORD *)this + 22) & 0x200000) == 0 )
    return -2147024894;
  v9 = *(_QWORD *)this;
  pv = 0;
  v39 = 0;
  result = (*(__int64 (__fastcall **)(CJob *, LPVOID *))(v9 + 264))(this, &pv);
  if ( result < 0 )
    return result;
  v10 = (*(__int64 (__fastcall **)(CJob *, unsigned __int16 **))(*(_QWORD *)this + 280LL))(this, &v39);
  v11 = pv;
  v12 = v10;
  if ( v10 < 0 )
  {
LABEL_5:
    CoTaskMemFree(v11);
    return v12;
  }
  v13 = HasSpacesW((const unsigned __int16 *)pv);
  v14 = -1;
  v15 = -1;
  do
    ++v15;
  while ( v39[v15] );
  v16 = pv;
  do
    ++v14;
  while ( *((_WORD *)pv + v14) );
  v17 = *a4;
  v18 = (unsigned int)v15 + (v13 != 0 ? 2 : 0) + ((_DWORD)v15 != 0) + 1 + (_DWORD)v14;
  *a4 = v18;
  if ( (unsigned int)v18 > v17 )
  {
    v12 = -2147024774;
LABEL_25:
    CoTaskMemFree(v16);
    v11 = v39;
    goto LABEL_5;
  }
  if ( !v13 )
  {
    v12 = StringCchCopyW(a3, v18, (const unsigned __int16 *)v16);
    if ( v12 >= 0 )
      goto LABEL_15;
LABEL_24:
    v16 = pv;
    goto LABEL_25;
  }
  v12 = StringCchCopyW(a3, v18, L"\"");
  if ( v12 < 0 )
    goto LABEL_24;
  StringCchCatW(a3, *a4, (const unsigned __int16 *)pv);
  StringCchCatW(a3, *a4, L"\"");
LABEL_15:
  if ( (_DWORD)v15 )
  {
    StringCchCatW(a3, *a4, L" ");
    StringCchCatW(a3, *a4, v39);
  }
  CoTaskMemFree(pv);
  CoTaskMemFree(v39);
  if ( (unsigned __int16)(*((_WORD *)this + 16) - 1) > 1u )
    return -2147467259;
  Trigger = CJob::_GetTrigger(this, 0);
  v21 = Trigger;
  if ( !Trigger )
    return -2147467259;
  v22 = 60 * Trigger->wStartHour;
  wStartMinute = Trigger->wStartMinute;
  a2->DaysOfWeek = 0;
  a2->DaysOfMonth = 0;
  a2->JobTime = 60000 * (wStartMinute + v22);
  TriggerType = Trigger->TriggerType;
  if ( TriggerType )
  {
    v25 = TriggerType - 2;
    if ( v25 )
    {
      if ( v25 != 1 )
        return -2147467259;
      a2->DaysOfMonth = Trigger->Type.MonthlyDate.rgfDays;
    }
    else
    {
      v26 = Trigger->Type.Weekly.rgfDaysOfTheWeek >> 1;
      a2->DaysOfWeek = v26;
      if ( (v21->Type.Weekly.rgfDaysOfTheWeek & 1) != 0 )
        a2->DaysOfWeek = v26 | 0x40;
    }
  }
  if ( v20 == 2 )
  {
    v27 = CJob::_GetTrigger(this, 1u);
    v21 = v27;
    v29 = v27->TriggerType;
    if ( v29 == TASK_TIME_TRIGGER_ONCE )
      return -2147467259;
    v30 = v29 - 2;
    if ( v30 )
    {
      if ( v30 != v28 )
        return -2147467259;
      a2->DaysOfMonth = v27->Type.MonthlyDate.rgfDays;
    }
    else
    {
      v31 = v27->Type.Weekly.rgfDaysOfTheWeek >> 1;
      a2->DaysOfWeek = v31;
      if ( (v21->Type.Weekly.rgfDaysOfTheWeek & 1) != 0 )
        a2->DaysOfWeek = v31 | 0x40;
    }
  }
  a2->Flags = 0;
  v32 = 0;
  if ( (*((_BYTE *)this + 88) & 1) == 0 )
  {
    v32 = 16;
    a2->Flags = 16;
  }
  if ( (v21->rgFlags & 1) == 0 && v21->TriggerType )
    a2->Flags = v32 | 1;
  SystemTime = 0;
  v41 = 0;
  v43 = 0;
  GetLocalTime(&SystemTime);
  *(_QWORD *)&v41.wYear = *(_QWORD *)&SystemTime.wYear;
  *(_QWORD *)&v41.wHour = 0;
  IncrementDay(&v41);
  v36 = 0;
  result = CJob::GetRunTimesP(this, &SystemTime, &v41, &v36, 1u, 0, v34);
  if ( result >= 0 )
  {
    if ( v36 )
      a2->Flags |= 4u;
    if ( (*((_DWORD *)this + 22) & 0x180000) != 0 )
      a2->Flags |= 2u;
    if ( v21->TriggerType || (a2->Flags & 2) != 0 )
      goto LABEL_51;
    v43 = SystemTime;
    IncrementDay(&v43);
    result = CJob::GetRunTimesP(this, &SystemTime, &v43, &v36, 1u, 0, v35);
    if ( result < 0 )
      return result;
    v33 = *(_QWORD *)this;
    v38 = 0;
    (*(void (__fastcall **)(CJob *, int *))(v33 + 128))(this, &v38);
    if ( v36 )
    {
LABEL_51:
      if ( (v21->rgFlags & 1) == 0 )
        return 0;
      v40.wYear = v21->wEndYear;
      v40.wMonth = v21->wEndMonth;
      v40.wDay = v21->wEndDay;
      v40.wHour = v21->wStartHour;
      v40.wMinute = v21->wStartMinute;
      v40.wDayOfWeek = 0;
      *(_DWORD *)&v40.wSecond = 0;
      if ( !IsFirstTimeEarlier(&v40, &SystemTime) || (a2->Flags & 2) != 0 )
        return 0;
      return -2147467259;
    }
    if ( v38 == 267009 )
    {
      a2->Flags |= 4u;
      goto LABEL_51;
    }
    return -2147467259;
  }
  return result;
}

```

## disassembly

```asm
0x18000cff4  push    rbp
0x18000cff6  push    rbx
0x18000cff7  push    rsi
0x18000cff8  push    rdi
0x18000cff9  push    r12
0x18000cffb  push    r13
0x18000cffd  push    r14
0x18000cfff  push    r15
0x18000d001  lea     rbp, [rsp-1Fh]
0x18000d006  sub     rsp, 0B8h
0x18000d00d  mov     rax, cs:__security_cookie
0x18000d014  xor     rax, rsp
0x18000d017  mov     [rbp+57h+var_50], rax
0x18000d01b  test    dword ptr [rcx+58h], 200000h
0x18000d022  mov     r12, r9
0x18000d025  mov     r15, r8
0x18000d028  mov     rdi, rdx
0x18000d02b  mov     rsi, rcx
0x18000d02e  jnz     short loc_18000D03A
0x18000d030  mov     eax, 80070002h
0x18000d035  jmp     loc_18000D3D1
0x18000d03a  mov     rax, [rcx]
0x18000d03d  lea     rdx, [rbp+57h+pv]
0x18000d041  xor     r13d, r13d
0x18000d044  mov     [rbp+57h+pv], r13
0x18000d048  mov     [rbp+57h+var_98], r13
0x18000d04c  mov     rax, [rax+108h]
0x18000d053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d058  test    eax, eax
0x18000d05a  js      loc_18000D3D1
0x18000d060  mov     rax, [rsi]
0x18000d063  lea     rdx, [rbp+57h+var_98]
0x18000d067  mov     rcx, rsi
0x18000d06a  mov     rax, [rax+118h]
0x18000d071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d076  mov     rcx, [rbp+57h+pv]; unsigned __int16 *
0x18000d07a  mov     ebx, eax
0x18000d07c  test    eax, eax
0x18000d07e  jns     short loc_18000D08D
0x18000d080  call    cs:__imp_CoTaskMemFree
0x18000d086  mov     eax, ebx
0x18000d088  jmp     loc_18000D3D1
0x18000d08d  call    ?HasSpacesW@@YAHPEBG@Z; HasSpacesW(ushort const *)
0x18000d092  mov     ecx, eax
0x18000d094  mov     r9d, eax
0x18000d097  mov     rax, [rbp+57h+var_98]
0x18000d09b  neg     ecx
0x18000d09d  sbb     r8d, r8d
0x18000d0a0  and     r8d, 2
0x18000d0a4  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000d0a8  mov     r14, rdx
0x18000d0ab  inc     r14
0x18000d0ae  cmp     [rax+r14*2], r13w
0x18000d0b3  jnz     short loc_18000D0AB
0x18000d0b5  mov     rcx, [rbp+57h+pv]
0x18000d0b9  inc     rdx
0x18000d0bc  cmp     [rcx+rdx*2], r13w
0x18000d0c1  jnz     short loc_18000D0B9
0x18000d0c3  test    r14d, r14d
0x18000d0c6  mov     eax, r13d
0x18000d0c9  setnz   al
0x18000d0cc  inc     eax
0x18000d0ce  add     eax, r8d
0x18000d0d1  add     edx, eax
0x18000d0d3  mov     eax, [r12]
0x18000d0d7  add     edx, r14d; unsigned __int64
0x18000d0da  mov     [r12], edx
0x18000d0de  cmp     edx, eax
0x18000d0e0  jbe     short loc_18000D0EC
0x18000d0e2  mov     ebx, 8007007Ah
0x18000d0e7  jmp     loc_18000D1FB
0x18000d0ec  test    r9d, r9d
0x18000d0ef  jz      loc_18000D1E2
0x18000d0f5  lea     r8, asc_18001E4D8; "\""
0x18000d0fc  mov     rcx, r15; unsigned __int16 *
0x18000d0ff  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d104  mov     ebx, eax
0x18000d106  test    eax, eax
0x18000d108  js      loc_18000D1F7
0x18000d10e  mov     edx, [r12]; unsigned __int64
0x18000d112  mov     rcx, r15; unsigned __int16 *
0x18000d115  mov     r8, [rbp+57h+pv]; unsigned __int16 *
0x18000d119  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d11e  mov     edx, [r12]; unsigned __int64
0x18000d122  lea     r8, asc_18001E4D8; "\""
0x18000d129  mov     rcx, r15; unsigned __int16 *
0x18000d12c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d131  test    r14d, r14d
0x18000d134  jz      short loc_18000D159
0x18000d136  mov     edx, [r12]; unsigned __int64
0x18000d13a  lea     r8, lParam; " "
0x18000d141  mov     rcx, r15; unsigned __int16 *
0x18000d144  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d149  mov     edx, [r12]; unsigned __int64
0x18000d14d  mov     rcx, r15; unsigned __int16 *
0x18000d150  mov     r8, [rbp+57h+var_98]; unsigned __int16 *
0x18000d154  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d159  mov     rcx, [rbp+57h+pv]; pv
0x18000d15d  call    cs:__imp_CoTaskMemFree
0x18000d163  mov     rcx, [rbp+57h+var_98]; pv
0x18000d167  call    cs:__imp_CoTaskMemFree
0x18000d16d  movzx   r10d, word ptr [rsi+20h]
0x18000d172  mov     r14d, 1
0x18000d178  movzx   eax, r10w
0x18000d17c  sub     ax, r14w
0x18000d180  cmp     ax, r14w
0x18000d184  ja      loc_18000D3CC
0x18000d18a  xor     edx, edx; unsigned __int16
0x18000d18c  mov     rcx, rsi; this
0x18000d18f  call    ?_GetTrigger@CJob@@AEAAPEAU_TASK_TRIGGER@@G@Z; CJob::_GetTrigger(ushort)
0x18000d194  mov     rbx, rax
0x18000d197  test    rax, rax
0x18000d19a  jz      loc_18000D3CC
0x18000d1a0  movzx   ecx, word ptr [rax+10h]
0x18000d1a4  lea     r15d, [r14+1]
0x18000d1a8  imul    edx, ecx, 3Ch ; '<'
0x18000d1ab  movzx   ecx, word ptr [rax+12h]
0x18000d1af  mov     [rdi+0Ch], r13b
0x18000d1b3  mov     [rdi+8], r13d
0x18000d1b7  add     edx, ecx
0x18000d1b9  imul    ecx, edx, 0EA60h
0x18000d1bf  movsxd  rdx, ecx
0x18000d1c2  mov     [rdi], rdx
0x18000d1c5  mov     ecx, [rax+20h]
0x18000d1c8  test    ecx, ecx
0x18000d1ca  jz      short loc_18000D21F
0x18000d1cc  sub     ecx, r15d
0x18000d1cf  jz      short loc_18000D20A
0x18000d1d1  cmp     ecx, r14d
0x18000d1d4  jnz     loc_18000D3CC
0x18000d1da  mov     eax, [rax+24h]
0x18000d1dd  mov     [rdi+8], eax
0x18000d1e0  jmp     short loc_18000D21F
0x18000d1e2  mov     r8, rcx; unsigned __int16 *
0x18000d1e5  mov     rcx, r15; unsigned __int16 *
0x18000d1e8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d1ed  mov     ebx, eax
0x18000d1ef  test    eax, eax
0x18000d1f1  jns     loc_18000D131
0x18000d1f7  mov     rcx, [rbp+57h+pv]; pv
0x18000d1fb  call    cs:__imp_CoTaskMemFree
0x18000d201  mov     rcx, [rbp+57h+var_98]
0x18000d205  jmp     loc_18000D080
0x18000d20a  movzx   eax, word ptr [rax+26h]
0x18000d20e  shr     ax, 1
0x18000d211  mov     [rdi+0Ch], al
0x18000d214  test    [rbx+26h], r14b
0x18000d218  jz      short loc_18000D21F
0x18000d21a  or      al, 40h
0x18000d21c  mov     [rdi+0Ch], al
0x18000d21f  cmp     r10w, r15w
0x18000d223  jnz     short loc_18000D268
0x18000d225  mov     edx, r14d; unsigned __int16
0x18000d228  mov     rcx, rsi; this
0x18000d22b  call    ?_GetTrigger@CJob@@AEAAPEAU_TASK_TRIGGER@@G@Z; CJob::_GetTrigger(ushort)
0x18000d230  mov     rbx, rax
0x18000d233  mov     ecx, [rax+20h]
0x18000d236  test    ecx, ecx
0x18000d238  jz      loc_18000D3CC
0x18000d23e  sub     ecx, r15d
0x18000d241  jz      short loc_18000D253
0x18000d243  cmp     ecx, edx
0x18000d245  jnz     loc_18000D3CC
0x18000d24b  mov     eax, [rax+24h]
0x18000d24e  mov     [rdi+8], eax
0x18000d251  jmp     short loc_18000D268
0x18000d253  movzx   eax, word ptr [rax+26h]
0x18000d257  shr     ax, 1
0x18000d25a  mov     [rdi+0Ch], al
0x18000d25d  test    [rbx+26h], r14b
0x18000d261  jz      short loc_18000D268
0x18000d263  or      al, 40h
0x18000d265  mov     [rdi+0Ch], al
0x18000d268  mov     [rdi+0Dh], r13b
0x18000d26c  mov     al, r13b
0x18000d26f  test    [rsi+58h], r14b
0x18000d273  jnz     short loc_18000D27A
0x18000d275  mov     al, 10h
0x18000d277  mov     [rdi+0Dh], al
0x18000d27a  test    [rbx+1Ch], r14b
0x18000d27e  jnz     short loc_18000D28C
0x18000d280  cmp     [rbx+20h], r13d
0x18000d284  jz      short loc_18000D28C
0x18000d286  or      al, r14b
0x18000d289  mov     [rdi+0Dh], al
0x18000d28c  xorps   xmm0, xmm0
0x18000d28f  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18000d293  xorps   xmm1, xmm1
0x18000d296  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18000d29a  movups  xmmword ptr [rbp+57h+var_80.wYear], xmm1
0x18000d29e  movups  xmmword ptr [rbp+57h+var_60.wYear], xmm0
0x18000d2a2  call    cs:__imp_GetLocalTime
0x18000d2a8  movaps  xmm0, xmmword ptr [rbp+57h+SystemTime.wYear]
0x18000d2ac  lea     rcx, [rbp+57h+var_80]; struct _SYSTEMTIME *
0x18000d2b0  movdqa  xmmword ptr [rbp+57h+var_80.wYear], xmm0
0x18000d2b5  mov     qword ptr [rbp+57h+var_80.wHour], r13
0x18000d2b9  mov     [rbp+57h+var_B0], r13w
0x18000d2be  call    ?IncrementDay@@YAXPEAU_SYSTEMTIME@@@Z; IncrementDay(_SYSTEMTIME *)
0x18000d2c3  lea     r9, [rbp+57h+var_B0]; unsigned __int16 *
0x18000d2c7  mov     [rsp+0F0h+var_C8], r13; struct CTimeRunList *
0x18000d2cc  lea     r8, [rbp+57h+var_80]; struct _SYSTEMTIME *
0x18000d2d0  mov     [rbp+57h+var_B0], r13w
0x18000d2d5  lea     rdx, [rbp+57h+SystemTime]; struct _SYSTEMTIME *
0x18000d2d9  mov     [rsp+0F0h+var_D0], r14w; unsigned __int16
0x18000d2df  mov     rcx, rsi; this
0x18000d2e2  call    ?GetRunTimesP@CJob@@QEAAJPEBU_SYSTEMTIME@@0PEAGGPEAVCTimeRunList@@1@Z; CJob::GetRunTimesP(_SYSTEMTIME const *,_SYSTEMTIME const *,ushort *,ushort,CTimeRunList *,ushort *)
0x18000d2e7  test    eax, eax
0x18000d2e9  js      loc_18000D3D1
0x18000d2ef  cmp     [rbp+57h+var_B0], r13w
0x18000d2f4  jbe     short loc_18000D2FA
0x18000d2f6  or      byte ptr [rdi+0Dh], 4
0x18000d2fa  test    dword ptr [rsi+58h], 180000h
0x18000d301  jz      short loc_18000D307
0x18000d303  or      [rdi+0Dh], r15b
0x18000d307  cmp     [rbx+20h], r13d
0x18000d30b  jnz     short loc_18000D37A
0x18000d30d  test    [rdi+0Dh], r15b
0x18000d311  jnz     short loc_18000D37A
0x18000d313  movaps  xmm0, xmmword ptr [rbp+57h+SystemTime.wYear]
0x18000d317  lea     rcx, [rbp+57h+var_60]; struct _SYSTEMTIME *
0x18000d31b  movdqa  xmmword ptr [rbp+57h+var_60.wYear], xmm0
0x18000d320  call    ?IncrementDay@@YAXPEAU_SYSTEMTIME@@@Z; IncrementDay(_SYSTEMTIME *)
0x18000d325  lea     r9, [rbp+57h+var_B0]; unsigned __int16 *
0x18000d329  mov     [rsp+0F0h+var_C8], r13; struct CTimeRunList *
0x18000d32e  lea     r8, [rbp+57h+var_60]; struct _SYSTEMTIME *
0x18000d332  mov     [rsp+0F0h+var_D0], r14w; unsigned __int16
0x18000d338  lea     rdx, [rbp+57h+SystemTime]; struct _SYSTEMTIME *
0x18000d33c  mov     rcx, rsi; this
0x18000d33f  call    ?GetRunTimesP@CJob@@QEAAJPEBU_SYSTEMTIME@@0PEAGGPEAVCTimeRunList@@1@Z; CJob::GetRunTimesP(_SYSTEMTIME const *,_SYSTEMTIME const *,ushort *,ushort,CTimeRunList *,ushort *)
0x18000d344  test    eax, eax
0x18000d346  js      loc_18000D3D1
0x18000d34c  mov     rax, [rsi]
0x18000d34f  lea     rdx, [rbp+57h+var_A0]
0x18000d353  mov     rcx, rsi
0x18000d356  mov     [rbp+57h+var_A0], r13d
0x18000d35a  mov     rax, [rax+80h]
0x18000d361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d366  cmp     [rbp+57h+var_B0], r13w
0x18000d36b  jnz     short loc_18000D37A
0x18000d36d  cmp     [rbp+57h+var_A0], 41301h
0x18000d374  jnz     short loc_18000D3CC
0x18000d376  or      byte ptr [rdi+0Dh], 4
0x18000d37a  test    [rbx+1Ch], r14b
0x18000d37e  jz      short loc_18000D3C8
0x18000d380  movzx   eax, word ptr [rbx+0Ah]
0x18000d384  lea     rdx, [rbp+57h+SystemTime]; struct _SYSTEMTIME *
0x18000d388  mov     [rbp+57h+var_90.wYear], ax
0x18000d38c  lea     rcx, [rbp+57h+var_90]; struct _SYSTEMTIME *
0x18000d390  movzx   eax, word ptr [rbx+0Ch]
0x18000d394  mov     [rbp+57h+var_90.wMonth], ax
0x18000d398  movzx   eax, word ptr [rbx+0Eh]
0x18000d39c  mov     [rbp+57h+var_90.wDay], ax
0x18000d3a0  movzx   eax, word ptr [rbx+10h]
0x18000d3a4  mov     [rbp+57h+var_90.wHour], ax
0x18000d3a8  movzx   eax, word ptr [rbx+12h]
0x18000d3ac  mov     [rbp+57h+var_90.wMinute], ax
0x18000d3b0  mov     [rbp+57h+var_90.wDayOfWeek], r13w
0x18000d3b5  mov     dword ptr [rbp+57h+var_90.wSecond], r13d
0x18000d3b9  call    ?IsFirstTimeEarlier@@YAHPEBU_SYSTEMTIME@@0@Z; IsFirstTimeEarlier(_SYSTEMTIME const *,_SYSTEMTIME const *)
0x18000d3be  test    eax, eax
0x18000d3c0  jz      short loc_18000D3C8
0x18000d3c2  test    [rdi+0Dh], r15b
0x18000d3c6  jz      short loc_18000D3CC
0x18000d3c8  xor     eax, eax
0x18000d3ca  jmp     short loc_18000D3D1
0x18000d3cc  mov     eax, 80004005h
0x18000d3d1  mov     rcx, [rbp+57h+var_50]
0x18000d3d5  xor     rcx, rsp; StackCookie
0x18000d3d8  call    __security_check_cookie
0x18000d3dd  add     rsp, 0B8h
0x18000d3e4  pop     r15
0x18000d3e6  pop     r14
0x18000d3e8  pop     r13
0x18000d3ea  pop     r12
0x18000d3ec  pop     rdi
0x18000d3ed  pop     rsi
0x18000d3ee  pop     rbx
0x18000d3ef  pop     rbp
0x18000d3f0  retn
```
