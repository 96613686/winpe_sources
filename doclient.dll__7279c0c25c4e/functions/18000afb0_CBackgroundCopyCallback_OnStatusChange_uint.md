# CBackgroundCopyCallback::OnStatusChange(uint)

- ea: `0x18000afb0`
- end: `0x18000b312`
- name: `?OnStatusChange@CBackgroundCopyCallback@@EEAAJI@Z`
- size: `866`
- prototype: `__int64 __fastcall(CBackgroundCopyCallback *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180008d14`
- `0x18000933c`
- `0x18000afb0`
- `0x18000c178`
- `0x18000c1ac`
- `0x18000c2bc`
- `0x1800f82f0`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000affa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000affa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b080`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b0ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b150`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b187`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b1ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b1ed`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b2a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b2d4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b080`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b0ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b150`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b187`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b1ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b1ed`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b2a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b2d4`

## string_xrefs

- `0x18000b050`: `C:\__w\1\s\src\DeliveryOptimization\dll\DownloadCallbacks.cpp`
- `0x18000b0bb`: `C:\__w\1\s\src\DeliveryOptimization\dll\DownloadCallbacks.cpp`
- `0x18000b11f`: `C:\__w\1\s\src\DeliveryOptimization\dll\DownloadCallbacks.cpp`
- `0x18000b230`: `C:\__w\1\s\src\DeliveryOptimization\dll\DownloadCallbacks.cpp`
- `0x18000b26f`: `C:\__w\1\s\src\DeliveryOptimization\dll\DownloadCallbacks.cpp`
- `0x18000b2bf`: `C:\__w\1\s\src\DeliveryOptimization\dll\DownloadCallbacks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CBackgroundCopyCallback::OnStatusChange(RTL_SRWLOCK *this, int a2)
{
  RTL_SRWLOCK *v4; // rdi
  __int64 *v5; // r8
  int v6; // eax
  unsigned int v7; // r14d
  __int64 v8; // rcx
  const char *v9; // r9
  __int64 result; // rax
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  int v17; // eax
  int v18; // eax
  __int64 v19; // rcx
  int v20[2]; // [rsp+20h] [rbp-58h] BYREF
  int v21; // [rsp+28h] [rbp-50h]
  int v22; // [rsp+2Ch] [rbp-4Ch]
  __int128 v23; // [rsp+30h] [rbp-48h]
  __int64 v24; // [rsp+40h] [rbp-38h] BYREF
  int v25; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v23 = 0;
  v4 = this + 3;
  *(_QWORD *)&v23 = this + 3;
  BYTE8(v23) = 1;
  AcquireSRWLockShared(this + 3);
  try
  {
    if ( !this[1].Ptr || !this[2].Ptr )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6E,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\DownloadCallbacks.cpp",
        (const char *)0x8000FFFFLL,
        v20[0]);
      ReleaseSRWLockShared(v4);
      return 2147549183LL;
    }
    v24 = 0;
    v5 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IBackgroundCopyJob>>(&v24);
    v6 = (*(__int64 (__fastcall **)(PVOID, GUID *, __int64 *))(*(_QWORD *)this[1].Ptr + 24LL))(
           this[1].Ptr,
           &GUID_37668d37_507e_4160_9316_26306d150b12,
           v5);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x73,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\DownloadCallbacks.cpp",
        (const char *)(unsigned int)v6,
        v20[0]);
      v8 = v24;
      if ( v24 )
      {
        v24 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      }
LABEL_7:
      ReleaseSRWLockShared(v4);
      return v7;
    }
    v25 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v24 + 192LL))(v24, &v25);
    v7 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x76,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\DownloadCallbacks.cpp",
        (const char *)(unsigned int)v11,
        v20[0]);
      v12 = v24;
      if ( v24 )
      {
        v24 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      }
      goto LABEL_7;
    }
    if ( a2 )
    {
      if ( a2 == 1 )
      {
        if ( (v25 & 1) == 0 )
        {
          v15 = v24;
          if ( v24 )
          {
            v24 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
          }
          goto LABEL_29;
        }
      }
      else
      {
        if ( a2 != 2 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x85,
            (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\DownloadCallbacks.cpp",
            (const char *)0x8000FFFFLL,
            v20[0]);
          v13 = v24;
          if ( v24 )
          {
            v24 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
          }
          ReleaseSRWLockShared(v4);
          return 2147549183LL;
        }
        if ( (v25 & 2) == 0 )
        {
          v14 = v24;
          if ( v24 )
          {
            v24 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
          }
LABEL_29:
          ReleaseSRWLockShared(v4);
          return 0;
        }
      }
    }
    else if ( (v25 & 8) == 0 )
    {
      v16 = v24;
      if ( v24 )
      {
        v24 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      }
      goto LABEL_29;
    }
    v22 = 0;
    *(_QWORD *)v20 = this;
    v21 = a2;
    if ( a2 )
    {
      if ( (unsigned int)(a2 - 1) > 1 )
      {
LABEL_38:
        v19 = v24;
        if ( v24 )
        {
          v24 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        }
        ReleaseSRWLockShared(v4);
        return 0;
      }
      v17 = COrderedTaskExecutor::QueueTaskAndCancelPending__CBackgroundCopyCallback::OnStatusChange_::_3_::_lambda_1____((CTaskQueue *)&this[6]);
      if ( v17 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xDC,
          (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\DownloadCallbacks.cpp",
          (const char *)(unsigned int)v17,
          v20[0]);
        goto LABEL_38;
      }
    }
    else
    {
      if ( LOBYTE(this[19].Ptr) )
        goto LABEL_38;
      LOBYTE(this[19].Ptr) = 1;
      v18 = COrderedTaskExecutor::QueueTask__CBackgroundCopyCallback::OnStatusChange_::_3_::_lambda_1____(&this[6], v20);
      if ( v18 >= 0 )
        goto LABEL_38;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xD3,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\DownloadCallbacks.cpp",
        (const char *)(unsigned int)v18,
        v20[0]);
    }
    LOBYTE(this[19].Ptr) = 0;
    goto LABEL_38;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xE4,
                           (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\DownloadCallbacks.cpp",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x18000afb0  mov     r11, rsp
0x18000afb3  mov     [r11+10h], rbx
0x18000afb7  mov     [r11+18h], rsi
0x18000afbb  mov     [r11+20h], rdi
0x18000afbf  push    r12
0x18000afc1  push    r14
0x18000afc3  push    r15
0x18000afc5  sub     rsp, 60h
0x18000afc9  mov     rax, cs:__security_cookie
0x18000afd0  xor     rax, rsp
0x18000afd3  mov     [rsp+78h+var_28], rax
0x18000afd8  mov     esi, edx
0x18000afda  mov     rbx, rcx
0x18000afdd  xorps   xmm0, xmm0
0x18000afe0  movups  [rsp+78h+var_48], xmm0
0x18000afe5  lea     rdi, [rcx+18h]
0x18000afe9  mov     [r11-48h], rdi
0x18000afed  mov     r15d, 1
0x18000aff3  mov     [r11-40h], r15b
0x18000aff7  mov     rcx, rdi; SRWLock
0x18000affa  call    cs:__imp_AcquireSRWLockShared
0x18000b000  nop
0x18000b001  xor     r12d, r12d
0x18000b004  cmp     [rbx+8], r12
0x18000b008  jz      loc_18000B2B2
0x18000b00e  cmp     [rbx+10h], r12
0x18000b012  jz      loc_18000B2B2
0x18000b018  mov     [rsp+78h+var_38], r12
0x18000b01d  lea     rcx, [rsp+78h+var_38]
0x18000b022  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIBackgroundCopyJob@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIBackgroundCopyJob@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IBackgroundCopyJob>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IBackgroundCopyJob>>)
0x18000b027  mov     r8, rax
0x18000b02a  mov     rcx, [rbx+8]
0x18000b02e  mov     rdx, [rcx]
0x18000b031  mov     rax, [rdx+18h]
0x18000b035  lea     rdx, _GUID_37668d37_507e_4160_9316_26306d150b12
0x18000b03c  call    _guard_dispatch_icall
0x18000b041  mov     r14d, eax
0x18000b044  test    eax, eax
0x18000b046  jns     short loc_18000B08E
0x18000b048  mov     rcx, [rsp+78h]; this
0x18000b04d  mov     r9d, eax; char *
0x18000b050  lea     r8, aCW1SSrcDeliver_97; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18000b057  lea     edx, [r15+72h]; void *
0x18000b05b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b060  nop
0x18000b061  mov     rcx, [rsp+78h+var_38]
0x18000b066  test    rcx, rcx
0x18000b069  jz      short loc_18000B07D
0x18000b06b  mov     [rsp+78h+var_38], r12
0x18000b070  mov     rax, [rcx]
0x18000b073  mov     rax, [rax+10h]
0x18000b077  call    _guard_dispatch_icall
0x18000b07c  nop
0x18000b07d  mov     rcx, rdi; SRWLock
0x18000b080  call    cs:__imp_ReleaseSRWLockShared
0x18000b086  mov     eax, r14d
0x18000b089  jmp     loc_18000B2E9
0x18000b08e  mov     [rsp+78h+var_30], r12d
0x18000b093  mov     rcx, [rsp+78h+var_38]
0x18000b098  mov     rax, [rcx]
0x18000b09b  lea     rdx, [rsp+78h+var_30]
0x18000b0a0  mov     rax, [rax+0C0h]
0x18000b0a7  call    _guard_dispatch_icall
0x18000b0ac  mov     r14d, eax
0x18000b0af  test    eax, eax
0x18000b0b1  jns     short loc_18000B0FA
0x18000b0b3  mov     rcx, [rsp+78h]; this
0x18000b0b8  mov     r9d, eax; char *
0x18000b0bb  lea     r8, aCW1SSrcDeliver_97; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18000b0c2  mov     edx, 76h ; 'v'; void *
0x18000b0c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b0cc  nop
0x18000b0cd  mov     rcx, [rsp+78h+var_38]
0x18000b0d2  test    rcx, rcx
0x18000b0d5  jz      short loc_18000B0E9
0x18000b0d7  mov     [rsp+78h+var_38], r12
0x18000b0dc  mov     rax, [rcx]
0x18000b0df  mov     rax, [rax+10h]
0x18000b0e3  call    _guard_dispatch_icall
0x18000b0e8  nop
0x18000b0e9  mov     rcx, rdi; SRWLock
0x18000b0ec  call    cs:__imp_ReleaseSRWLockShared
0x18000b0f2  mov     eax, r14d
0x18000b0f5  jmp     loc_18000B2E9
0x18000b0fa  mov     eax, esi
0x18000b0fc  test    esi, esi
0x18000b0fe  jz      loc_18000B1C7
0x18000b104  sub     eax, 1
0x18000b107  jz      loc_18000B194
0x18000b10d  cmp     eax, 1
0x18000b110  jz      short loc_18000B15D
0x18000b112  mov     rcx, [rsp+78h]; this
0x18000b117  mov     ebx, 8000FFFFh
0x18000b11c  mov     r9d, ebx; char *
0x18000b11f  lea     r8, aCW1SSrcDeliver_97; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18000b126  mov     edx, 85h; void *
0x18000b12b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b130  nop
0x18000b131  mov     rcx, [rsp+78h+var_38]
0x18000b136  test    rcx, rcx
0x18000b139  jz      short loc_18000B14D
0x18000b13b  mov     [rsp+78h+var_38], r12
0x18000b140  mov     rdx, [rcx]
0x18000b143  mov     rax, [rdx+10h]
0x18000b147  call    _guard_dispatch_icall
0x18000b14c  nop
0x18000b14d  mov     rcx, rdi; SRWLock
0x18000b150  call    cs:__imp_ReleaseSRWLockShared
0x18000b156  mov     eax, ebx
0x18000b158  jmp     loc_18000B2E9
0x18000b15d  test    byte ptr [rsp+78h+var_30], 2
0x18000b162  jnz     loc_18000B1FA
0x18000b168  mov     rcx, [rsp+78h+var_38]
0x18000b16d  test    rcx, rcx
0x18000b170  jz      short loc_18000B184
0x18000b172  mov     [rsp+78h+var_38], r12
0x18000b177  mov     rax, [rcx]
0x18000b17a  mov     rax, [rax+10h]
0x18000b17e  call    _guard_dispatch_icall
0x18000b183  nop
0x18000b184  mov     rcx, rdi; SRWLock
0x18000b187  call    cs:__imp_ReleaseSRWLockShared
0x18000b18d  xor     eax, eax
0x18000b18f  jmp     loc_18000B2E9
0x18000b194  test    byte ptr [rsp+78h+var_30], r15b
0x18000b199  jnz     short loc_18000B1FA
0x18000b19b  mov     rcx, [rsp+78h+var_38]
0x18000b1a0  test    rcx, rcx
0x18000b1a3  jz      short loc_18000B1B7
0x18000b1a5  mov     [rsp+78h+var_38], r12
0x18000b1aa  mov     rax, [rcx]
0x18000b1ad  mov     rax, [rax+10h]
0x18000b1b1  call    _guard_dispatch_icall
0x18000b1b6  nop
0x18000b1b7  mov     rcx, rdi; SRWLock
0x18000b1ba  call    cs:__imp_ReleaseSRWLockShared
0x18000b1c0  xor     eax, eax
0x18000b1c2  jmp     loc_18000B2E9
0x18000b1c7  test    byte ptr [rsp+78h+var_30], 8
0x18000b1cc  jnz     short loc_18000B1FA
0x18000b1ce  mov     rcx, [rsp+78h+var_38]
0x18000b1d3  test    rcx, rcx
0x18000b1d6  jz      short loc_18000B1EA
0x18000b1d8  mov     [rsp+78h+var_38], r12
0x18000b1dd  mov     rax, [rcx]
0x18000b1e0  mov     rax, [rax+10h]
0x18000b1e4  call    _guard_dispatch_icall
0x18000b1e9  nop
0x18000b1ea  mov     rcx, rdi; SRWLock
0x18000b1ed  call    cs:__imp_ReleaseSRWLockShared
0x18000b1f3  xor     eax, eax
0x18000b1f5  jmp     loc_18000B2E9
0x18000b1fa  mov     [rsp+78h+var_4C], r12d
0x18000b1ff  mov     qword ptr [rsp+78h+var_58], rbx; int
0x18000b204  mov     [rsp+78h+var_50], esi
0x18000b208  test    esi, esi
0x18000b20a  jz      short loc_18000B243
0x18000b20c  sub     esi, 1
0x18000b20f  jz      short loc_18000B216
0x18000b211  cmp     esi, 1
0x18000b214  jnz     short loc_18000B289
0x18000b216  lea     rcx, [rbx+30h]; this
0x18000b21a  lea     rdx, [rsp+78h+var_58]
0x18000b21f  call    COrderedTaskExecutor__QueueTaskAndCancelPending__CBackgroundCopyCallback__OnStatusChange____3____lambda_1____
0x18000b224  mov     rcx, [rsp+78h]; this
0x18000b229  test    eax, eax
0x18000b22b  jns     short loc_18000B280
0x18000b22d  mov     r9d, eax; char *
0x18000b230  lea     r8, aCW1SSrcDeliver_97; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18000b237  mov     edx, 0DCh; void *
0x18000b23c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000b241  jmp     short loc_18000B289
0x18000b243  mov     al, [rbx+98h]
0x18000b249  nop
0x18000b24a  test    al, al
0x18000b24c  jnz     short loc_18000B289
0x18000b24e  xchg    r15b, [rbx+98h]
0x18000b255  lea     rcx, [rbx+30h]
0x18000b259  lea     rdx, [rsp+78h+var_58]
0x18000b25e  call    COrderedTaskExecutor__QueueTask__CBackgroundCopyCallback__OnStatusChange____3____lambda_1____
0x18000b263  mov     rcx, [rsp+78h]; this
0x18000b268  test    eax, eax
0x18000b26a  jns     short loc_18000B289
0x18000b26c  mov     r9d, eax; char *
0x18000b26f  lea     r8, aCW1SSrcDeliver_97; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18000b276  mov     edx, 0D3h; void *
0x18000b27b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000b280  mov     eax, r12d
0x18000b283  xchg    al, [rbx+98h]
0x18000b289  mov     rcx, [rsp+78h+var_38]
0x18000b28e  test    rcx, rcx
0x18000b291  jz      short loc_18000B2A5
0x18000b293  mov     [rsp+78h+var_38], r12
0x18000b298  mov     rax, [rcx]
0x18000b29b  mov     rax, [rax+10h]
0x18000b29f  call    _guard_dispatch_icall
0x18000b2a4  nop
0x18000b2a5  mov     rcx, rdi; SRWLock
0x18000b2a8  call    cs:__imp_ReleaseSRWLockShared
0x18000b2ae  xor     eax, eax
0x18000b2b0  jmp     short loc_18000B2E9
0x18000b2b2  mov     rcx, [rsp+78h]; this
0x18000b2b7  mov     ebx, 8000FFFFh
0x18000b2bc  mov     r9d, ebx; char *
0x18000b2bf  lea     r8, aCW1SSrcDeliver_97; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18000b2c6  mov     edx, 6Eh ; 'n'; void *
0x18000b2cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b2d0  nop
0x18000b2d1  mov     rcx, rdi; SRWLock
0x18000b2d4  call    cs:__imp_ReleaseSRWLockShared
0x18000b2da  mov     eax, ebx
0x18000b2dc  jmp     short loc_18000B2E9
0x18000b2de  mov     eax, [rsp+78h+var_30]
0x18000b2e2  jmp     short loc_18000B2E9
0x18000b2e4  mov     eax, 8007000Eh
0x18000b2e9  mov     rcx, [rsp+78h+var_28]
0x18000b2ee  xor     rcx, rsp; StackCookie
0x18000b2f1  call    __security_check_cookie
0x18000b2f6  lea     r11, [rsp+78h+var_18]
0x18000b2fb  mov     rbx, [r11+28h]
0x18000b2ff  mov     rsi, [r11+30h]
0x18000b303  mov     rdi, [r11+38h]
0x18000b307  mov     rsp, r11
0x18000b30a  pop     r15
0x18000b30c  pop     r14
0x18000b30e  pop     r12
0x18000b310  retn
```
