# NgenTask::TaskWorkAvailable(bool)

- ea: `0x180016fd4`
- end: `0x1800171a5`
- name: `?TaskWorkAvailable@NgenTask@@YAJ_N@Z`
- size: `465`
- prototype: `__int64 __fastcall(NgenTask *this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800283d0`

## callees

- `0x180003c90`
- `0x18001458c`
- `0x180015208`
- `0x180015de4`
- `0x180016648`
- `0x180016708`
- `0x180016794`
- `0x180016920`
- `0x180016eb0`
- `0x180016fd4`
- `0x1800171a8`
- `0x18003069c`
- `0x1800364c0`
- `0x1800366a8`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800170dd`
- `KERNEL32!CloseHandle` at `0x180017182`
- `KERNEL32!CloseHandle` at `0x1800170dd`
- `KERNEL32!CloseHandle` at `0x180017182`

## string_xrefs

- `0x180017022`: `ngentasknewworklock.dat`

## pseudocode

```c
__int64 __fastcall NgenTask::TaskWorkAvailable(NgenTask *this)
{
  char v1; // r14
  int v2; // esi
  char v3; // di
  int IsTaskRunning; // ebx
  bool v5; // r8
  int v6; // edx
  NgenTask *v7; // rcx
  NGENService *v8; // rcx
  bool v9; // r8
  int v10; // edi
  NgenTask *v11; // rcx
  bool v12; // dl
  NGENService *v13; // rcx
  bool v14; // dl
  NgenTask *v15; // rcx
  NgenTask *v16; // rcx
  bool v17; // dl
  bool v18; // dl
  NgenTask *v19; // rcx
  NgenTask *v21; // rcx
  void **v23; // [rsp+20h] [rbp-10h] BYREF
  HANDLE hObject; // [rsp+28h] [rbp-8h]
  bool v25; // [rsp+60h] [rbp+30h] BYREF

  v1 = (char)this;
  if ( (_BYTE)this )
    NgenTask::CreateFXUpdateFile(this);
  v2 = 0;
  while ( 1 )
  {
    v3 = 0;
    hObject = (HANDLE)-1LL;
    v23 = (void **)&VersionedMutexHolder::`vftable';
    IsTaskRunning = FileLockHolder::AcquireNoThrow((FileLockHolder *)&v23, L"ngentasknewworklock.dat", 0, 0);
    if ( IsTaskRunning < 0 )
      goto LABEL_33;
    v25 = 0;
    IsTaskRunning = NgenTask::IsTaskRunning((NgenTask *)&v25, 0, v5);
    if ( IsTaskRunning < 0 )
      goto LABEL_33;
    if ( !v25 )
    {
LABEL_17:
      v3 = 1;
      goto LABEL_18;
    }
    if ( NgenTask::IsTaskHighPriority(v7) )
      goto LABEL_14;
    if ( v2 == 2 )
      break;
LABEL_18:
    v23 = &FileLockHolder::`vftable';
    v13 = (NGENService *)hObject;
    if ( hObject != (HANDLE)-1LL )
    {
      CloseHandle(hObject);
      hObject = (HANDLE)-1LL;
    }
    if ( v3 )
    {
      if ( v1 )
      {
        if ( CLRConfig::GetConfigValue(
               (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::INTERNAL_NGenTaskDelayStart,
               v6,
               &v25) )
        {
          NgenTask::SetTaskHighPriority(v15, v14);
          LOBYTE(v16) = 1;
          IsTaskRunning = NgenTask::SetTaskBootTrigger(v16, v17);
          if ( IsTaskRunning < 0 )
            return (unsigned int)IsTaskRunning;
          LOBYTE(v19) = 1;
          IsTaskRunning = NgenTask::SetTaskDelayStartTrigger(v19, v18);
          if ( IsTaskRunning < 0 )
            return (unsigned int)IsTaskRunning;
          v15 = 0;
        }
        else
        {
          LOBYTE(v15) = 1;
        }
        return (unsigned int)NgenTask::SetCriticalTaskState(v15, v14);
      }
      else
      {
        NGENService::ControllerNotifyNewWorkAvailable(v13);
        return (unsigned int)NgenTask::StartTask(v21);
      }
    }
    ClrSleepEx(0x3E8u, v6);
    if ( (unsigned int)++v2 >= 3 )
      return (unsigned int)IsTaskRunning;
  }
  IsTaskRunning = NgenTask::StopTaskIfRunning(0, v6);
  if ( IsTaskRunning >= 0 )
  {
    v10 = 0;
    while ( 1 )
    {
      v25 = 0;
      IsTaskRunning = NgenTask::IsTaskRunning((NgenTask *)&v25, 0, v9);
      if ( IsTaskRunning < 0 )
        break;
      if ( !v25 )
        goto LABEL_17;
      ClrSleepEx(0x64u, v6);
      if ( (unsigned int)++v10 >= 0x14 )
        goto LABEL_14;
    }
  }
  if ( IsTaskRunning == -2147467259 )
  {
LABEL_14:
    NGENService::ControllerNotifyNewWorkAvailable(v8);
    LOBYTE(v11) = 1;
    IsTaskRunning = NgenTask::SetTaskBootTrigger(v11, v12);
  }
LABEL_33:
  v23 = &FileLockHolder::`vftable';
  if ( hObject != (HANDLE)-1LL )
  {
    CloseHandle(hObject);
    hObject = (HANDLE)-1LL;
  }
  return (unsigned int)IsTaskRunning;
}

```

## disassembly

```asm
0x180016fd4  mov     [rsp-28h+arg_8], rbx
0x180016fd9  mov     [rsp-28h+arg_10], rsi
0x180016fde  push    rbp
0x180016fdf  push    rdi
0x180016fe0  push    r13
0x180016fe2  push    r14
0x180016fe4  push    r15
0x180016fe6  mov     rbp, rsp
0x180016fe9  sub     rsp, 30h
0x180016fed  mov     r14b, cl
0x180016ff0  test    cl, cl
0x180016ff2  jz      short loc_180016FF9
0x180016ff4  call    ?CreateFXUpdateFile@NgenTask@@YAXXZ; NgenTask::CreateFXUpdateFile(void)
0x180016ff9  xor     esi, esi
0x180016ffb  lea     r13, ??_7FileLockHolder@@6B@; const FileLockHolder::`vftable'
0x180017002  or      r15, 0FFFFFFFFFFFFFFFFh
0x180017006  xor     dil, dil
0x180017009  mov     [rbp+var_10], r13
0x18001700d  mov     [rbp+hObject], r15
0x180017011  lea     rax, ??_7VersionedMutexHolder@@6B@; const VersionedMutexHolder::`vftable'
0x180017018  mov     [rbp+var_10], rax
0x18001701c  xor     r9d, r9d; int *
0x18001701f  xor     r8d, r8d; void *
0x180017022  lea     rdx, aNgentasknewwor; "ngentasknewworklock.dat"
0x180017029  lea     rcx, [rbp+var_10]; this
0x18001702d  call    ?AcquireNoThrow@FileLockHolder@@QEAAJPEBGPEAXPEAH@Z; FileLockHolder::AcquireNoThrow(ushort const *,void *,int *)
0x180017032  mov     ebx, eax
0x180017034  test    eax, eax
0x180017036  js      loc_180017175
0x18001703c  mov     [rbp+arg_0], dil
0x180017040  xor     edx, edx; bool *
0x180017042  lea     rcx, [rbp+arg_0]; this
0x180017046  call    ?IsTaskRunning@NgenTask@@YAJAEA_N_N@Z; NgenTask::IsTaskRunning(bool &,bool)
0x18001704b  mov     ebx, eax
0x18001704d  test    eax, eax
0x18001704f  js      loc_180017173
0x180017055  cmp     [rbp+arg_0], dil
0x180017059  jz      short loc_1800170CD
0x18001705b  call    ?IsTaskHighPriority@NgenTask@@YA_NXZ; NgenTask::IsTaskHighPriority(void)
0x180017060  test    al, al
0x180017062  jnz     loc_18001710A
0x180017068  cmp     esi, 2
0x18001706b  jnz     short loc_1800170D0
0x18001706d  xor     ecx, ecx; this
0x18001706f  call    ?StopTaskIfRunning@NgenTask@@YAJ_N@Z; NgenTask::StopTaskIfRunning(bool)
0x180017074  mov     ebx, eax
0x180017076  test    eax, eax
0x180017078  js      short loc_1800170BF
0x18001707a  xor     edi, edi
0x18001707c  mov     [rbp+arg_0], 0
0x180017080  xor     edx, edx; bool *
0x180017082  lea     rcx, [rbp+arg_0]; this
0x180017086  call    ?IsTaskRunning@NgenTask@@YAJAEA_N_N@Z; NgenTask::IsTaskRunning(bool &,bool)
0x18001708b  mov     ebx, eax
0x18001708d  test    eax, eax
0x18001708f  js      short loc_1800170BF
0x180017091  cmp     [rbp+arg_0], 0
0x180017095  jz      short loc_1800170CD
0x180017097  mov     ecx, 64h ; 'd'; unsigned int
0x18001709c  call    ?ClrSleepEx@@YAKKH@Z; ClrSleepEx(ulong,int)
0x1800170a1  inc     edi
0x1800170a3  cmp     edi, 14h
0x1800170a6  jb      short loc_18001707C
0x1800170a8  call    ?ControllerNotifyNewWorkAvailable@NGENService@@YAJXZ; NGENService::ControllerNotifyNewWorkAvailable(void)
0x1800170ad  mov     cl, 1; this
0x1800170af  call    ?SetTaskBootTrigger@NgenTask@@YAJ_N@Z; NgenTask::SetTaskBootTrigger(bool)
0x1800170b4  mov     ebx, eax
0x1800170b6  test    eax, eax
0x1800170b8  jns     short loc_180017108
0x1800170ba  jmp     loc_180017175
0x1800170bf  mov     eax, ebx
0x1800170c1  cmp     ebx, 80004005h
0x1800170c7  jz      short loc_1800170A8
0x1800170c9  test    eax, eax
0x1800170cb  js      short loc_180017106
0x1800170cd  mov     dil, 1
0x1800170d0  mov     [rbp+var_10], r13
0x1800170d4  mov     rcx, [rbp+hObject]; hObject
0x1800170d8  cmp     rcx, r15
0x1800170db  jz      short loc_1800170E7
0x1800170dd  call    cs:__imp_CloseHandle
0x1800170e3  mov     [rbp+hObject], r15
0x1800170e7  test    dil, dil
0x1800170ea  jnz     short loc_180017120
0x1800170ec  mov     ecx, 3E8h; unsigned int
0x1800170f1  call    ?ClrSleepEx@@YAKKH@Z; ClrSleepEx(ulong,int)
0x1800170f6  inc     esi
0x1800170f8  cmp     esi, 3
0x1800170fb  jnb     loc_18001718C
0x180017101  jmp     loc_180017006
0x180017106  jmp     short loc_180017175
0x180017108  jmp     short loc_180017175
0x18001710a  call    ?ControllerNotifyNewWorkAvailable@NGENService@@YAJXZ; NGENService::ControllerNotifyNewWorkAvailable(void)
0x18001710f  mov     cl, 1; this
0x180017111  call    ?SetTaskBootTrigger@NgenTask@@YAJ_N@Z; NgenTask::SetTaskBootTrigger(bool)
0x180017116  mov     ebx, eax
0x180017118  test    eax, eax
0x18001711a  jns     short loc_18001711E
0x18001711c  jmp     short loc_180017175
0x18001711e  jmp     short loc_180017175
0x180017120  test    r14b, r14b
0x180017123  jz      short loc_180017167
0x180017125  lea     r8, [rbp+arg_0]; bool *
0x180017129  lea     rcx, ?INTERNAL_NGenTaskDelayStart@CLRConfig@@2UConfigDWORDInfo@1@B; struct CLRConfig::ConfigDWORDInfo *
0x180017130  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x180017135  test    eax, eax
0x180017137  jz      short loc_18001715C
0x180017139  call    ?SetTaskHighPriority@NgenTask@@YAX_N@Z; NgenTask::SetTaskHighPriority(bool)
0x18001713e  mov     cl, 1; this
0x180017140  call    ?SetTaskBootTrigger@NgenTask@@YAJ_N@Z; NgenTask::SetTaskBootTrigger(bool)
0x180017145  mov     ebx, eax
0x180017147  test    eax, eax
0x180017149  js      short loc_18001718C
0x18001714b  mov     cl, 1; this
0x18001714d  call    ?SetTaskDelayStartTrigger@NgenTask@@YAJ_N@Z; NgenTask::SetTaskDelayStartTrigger(bool)
0x180017152  mov     ebx, eax
0x180017154  test    eax, eax
0x180017156  js      short loc_18001718C
0x180017158  xor     ecx, ecx
0x18001715a  jmp     short loc_18001715E
0x18001715c  mov     cl, 1; this
0x18001715e  call    ?SetCriticalTaskState@NgenTask@@YAJ_N@Z; NgenTask::SetCriticalTaskState(bool)
0x180017163  mov     ebx, eax
0x180017165  jmp     short loc_18001718C
0x180017167  call    ?ControllerNotifyNewWorkAvailable@NGENService@@YAJXZ; NGENService::ControllerNotifyNewWorkAvailable(void)
0x18001716c  call    ?StartTask@NgenTask@@YAJXZ; NgenTask::StartTask(void)
0x180017171  jmp     short loc_180017163
0x180017173  jmp     short $+2
0x180017175  mov     rcx, [rbp+hObject]; hObject
0x180017179  cmp     rcx, r15
0x18001717c  mov     [rbp+var_10], r13
0x180017180  jz      short loc_18001718C
0x180017182  call    cs:__imp_CloseHandle
0x180017188  mov     [rbp+hObject], r15
0x18001718c  mov     eax, ebx
0x18001718e  mov     rbx, [rsp+30h+arg_8]
0x180017193  mov     rsi, [rsp+30h+arg_10]
0x180017198  add     rsp, 30h
0x18001719c  pop     r15
0x18001719e  pop     r14
0x1800171a0  pop     r13
0x1800171a2  pop     rdi
0x1800171a3  pop     rbp
0x1800171a4  retn
```
