# APP_POOL::Terminate(void)

- ea: `0x18001ac94`
- end: `0x18001af44`
- name: `?Terminate@APP_POOL@@QEAAXXZ`
- size: `688`
- prototype: `void __fastcall(APP_POOL *__hidden this)`
- caller_count: `6`
- callee_count: `9`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800060b8`
- `0x18000ebe0`
- `0x18000fe6c`
- `0x180012ac4`
- `0x1800184ac`
- `0x1800193e4`

## callees

- `0x180012504`
- `0x180019358`
- `0x18001ac94`
- `0x180027d04`
- `0x1800354c4`
- `0x18003e918`
- `0x18006101a`
- `0x180061060`
- `0x180062010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18001aeac`
- `msvcrt!wcsrchr` at `0x18001aeac`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18001aecf`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18001aecf`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001ae65`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001ae65`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x18001acfd`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x18001acfd`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18001ad82`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18001ad82`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x18001adbc`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x18001adbc`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001aeda`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001aeda`
- `iisutil!PuDbgPrintError` at `0x18001ad51`
- `iisutil!PuDbgPrintError` at `0x18001ad51`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001ae8b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001ae8b`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x18001aec5`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x18001aec5`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18001ae99`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18001ae99`

## string_xrefs

- `0x18001ad2d`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\app_pool.cxx`
- `0x18001ad34`: `Failed to delete counterset instance for '%S' app pool.\n`

## pseudocode

```c
void __fastcall APP_POOL::Terminate(APP_POOL *this)
{
  struct _PERF_COUNTERSET_INSTANCE *v2; // rdx
  signed int v3; // eax
  unsigned int v4; // ecx
  __int64 v5; // rcx
  __int64 v6; // rax
  REQUEST_QUEUE_DATA *v7; // rcx
  JOB_OBJECT *v8; // rcx
  wchar_t *v9; // rax
  void (__fastcall ***v10)(_QWORD, __int64); // rcx
  _QWORD v11[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v12[3]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v13[32]; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *Str; // [rsp+88h] [rbp-78h]
  unsigned __int16 v15[264]; // [rsp+A0h] [rbp-60h] BYREF

  *((_DWORD *)this + 55) = *((_DWORD *)this + 54);
  *((_DWORD *)this + 5) = 7;
  APP_POOL::RecordState(this);
  if ( !*((_DWORD *)g_pWebAdminService + 412) )
  {
    v2 = (struct _PERF_COUNTERSET_INSTANCE *)*((_QWORD *)this + 56);
    if ( v2 )
    {
      v3 = PerfDeleteInstance(*((HANDLE *)g_pWebAdminService + 76), v2);
      v4 = v3;
      if ( v3 )
      {
        if ( v3 > 0 )
          v4 = (unsigned __int16)v3 | 0x80070000;
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool.cxx",
            701,
            "APP_POOL::TerminateAppPoolCounters",
            v4,
            "Failed to delete counterset instance for '%S' app pool.\n",
            *((const wchar_t **)this + 7));
      }
      else
      {
        *((_QWORD *)this + 56) = 0;
      }
    }
  }
  v11[1] = v11;
  v11[0] = v11;
  CLKRHashTable::Size((APP_POOL *)((char *)this + 240));
  v12[0] = 0;
  v12[1] = &REQUEST_QUEUE_DATA_TABLE::CreateListRequestQueueDataAction;
  v12[2] = v11;
  CLKRHashTable::Apply(
    (char *)this + 240,
    CTypedHashTable<HASH_POOL_HASH,POOL_HASH_ENTRY,APP_POOL_HASH const *,CLKRHashTable>::_Action,
    v12,
    2);
  while ( 1 )
  {
    v5 = v11[0];
    if ( (_QWORD *)v11[0] == v11 )
      break;
    if ( *(_QWORD **)(v11[0] + 8LL) != v11 || (v6 = *(_QWORD *)v11[0], *(_QWORD *)(*(_QWORD *)v11[0] + 8LL) != v11[0]) )
      __fastfail(3u);
    v11[0] = *(_QWORD *)v11[0];
    v7 = (REQUEST_QUEUE_DATA *)(v5 - 192);
    *(_QWORD *)(v6 + 8) = v11;
    *((_DWORD *)v7 + 46) = 1;
    REQUEST_QUEUE_DATA::CheckIfShouldTerminate(v7);
  }
  v8 = (JOB_OBJECT *)*((_QWORD *)this + 10);
  if ( v8 )
  {
    JOB_OBJECT::Terminate(v8);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 8LL))(*((_QWORD *)this + 10));
    *((_QWORD *)this + 10) = 0;
  }
  while ( *((_DWORD *)this + 30) )
    WORKER_PROCESS::Terminate((WORKER_PROCESS *)(*((_QWORD *)this + 13) - 16LL));
  if ( *((_DWORD *)this + 108) )
  {
    DeleteFileW(*((LPCWSTR *)this + 52));
    memset_0(v15, 0, 0x208u);
    STRU::STRU((STRU *)v13, v15, 0x104u);
    if ( (int)STRU::Copy((STRU *)v13, (APP_POOL *)((char *)this + 384)) >= 0 )
    {
      v9 = wcsrchr(Str, 0x5Cu);
      if ( v9 )
      {
        STRU::SetLen((STRU *)v13, v9 - Str);
        RemoveDirectoryW(Str);
      }
    }
    STRU::~STRU((STRU *)v13);
  }
  v10 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 64);
  if ( v10 )
  {
    (**v10)(v10, 1);
    *((_QWORD *)this + 64) = 0;
  }
  if ( *((_DWORD *)this + 4) )
    UL_AND_WORKER_MANAGER::RemoveAppPoolFromTable((WEB_ADMIN_SERVICE *)((char *)g_pWebAdminService + 112), this);
}

```

## disassembly

```asm
0x18001ac94  mov     [rsp-8+arg_8], rbx
0x18001ac99  mov     [rsp-8+arg_10], rdi
0x18001ac9e  push    rbp
0x18001ac9f  lea     rbp, [rsp-1C0h]
0x18001aca7  sub     rsp, 2C0h
0x18001acae  mov     rax, cs:__security_cookie
0x18001acb5  xor     rax, rsp
0x18001acb8  mov     [rbp+1C0h+var_10], rax
0x18001acbf  mov     eax, [rcx+0D8h]
0x18001acc5  mov     rdi, rcx
0x18001acc8  mov     [rcx+0DCh], eax
0x18001acce  mov     dword ptr [rcx+14h], 7
0x18001acd5  call    ?RecordState@APP_POOL@@QEAAXXZ; APP_POOL::RecordState(void)
0x18001acda  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x18001ace1  cmp     dword ptr [rcx+670h], 0
0x18001ace8  jnz     short loc_18001AD64
0x18001acea  mov     rdx, [rdi+1C0h]; InstanceBlock
0x18001acf1  test    rdx, rdx
0x18001acf4  jz      short loc_18001AD64
0x18001acf6  mov     rcx, [rcx+260h]; Provider
0x18001acfd  call    cs:__imp_PerfDeleteInstance
0x18001ad03  mov     ecx, eax
0x18001ad05  test    eax, eax
0x18001ad07  jz      short loc_18001AD59
0x18001ad09  jle     short loc_18001AD14
0x18001ad0b  movzx   ecx, ax
0x18001ad0e  or      ecx, 80070000h
0x18001ad14  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001ad1b  jz      short loc_18001AD64
0x18001ad1d  mov     rax, [rdi+38h]
0x18001ad21  lea     r9, aAppPoolTermina; "APP_POOL::TerminateAppPoolCounters"
0x18001ad28  mov     [rsp+2C0h+var_290], rax
0x18001ad2d  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001ad34  lea     rax, aFailedToDelete; "Failed to delete counterset instance fo"...
0x18001ad3b  mov     r8d, 2BDh
0x18001ad41  mov     [rsp+2C0h+var_298], rax
0x18001ad46  mov     [rsp+2C0h+var_2A0], ecx
0x18001ad4a  mov     rcx, cs:g_pDebug
0x18001ad51  call    cs:__imp_PuDbgPrintError
0x18001ad57  jmp     short loc_18001AD64
0x18001ad59  mov     qword ptr [rdi+1C0h], 0
0x18001ad64  lea     rax, [rsp+2C0h+var_280]
0x18001ad69  mov     [rsp+2C0h+var_278], rax
0x18001ad6e  lea     rbx, [rdi+0F0h]
0x18001ad75  lea     rax, [rsp+2C0h+var_280]
0x18001ad7a  mov     rcx, rbx
0x18001ad7d  mov     [rsp+2C0h+var_280], rax
0x18001ad82  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x18001ad88  lea     rax, ?CreateListRequestQueueDataAction@REQUEST_QUEUE_DATA_TABLE@@SA?AW4LK_ACTION@@PEAVREQUEST_QUEUE_DATA@@PEAX@Z; REQUEST_QUEUE_DATA_TABLE::CreateListRequestQueueDataAction(REQUEST_QUEUE_DATA *,void *)
0x18001ad8f  mov     [rsp+2C0h+var_270], 0
0x18001ad98  mov     [rsp+2C0h+var_268], rax
0x18001ad9d  lea     r8, [rsp+2C0h+var_270]
0x18001ada2  lea     rax, [rsp+2C0h+var_280]
0x18001ada7  mov     r9d, 2
0x18001adad  lea     rdx, ?_Action@?$CTypedHashTable@VHASH_POOL_HASH@@VPOOL_HASH_ENTRY@@PEBUAPP_POOL_HASH@@VCLKRHashTable@@@@CA?AW4LK_ACTION@@PEBXPEAX@Z; CTypedHashTable<HASH_POOL_HASH,POOL_HASH_ENTRY,APP_POOL_HASH const *,CLKRHashTable>::_Action(void const *,void *)
0x18001adb4  mov     [rsp+2C0h+var_260], rax
0x18001adb9  mov     rcx, rbx
0x18001adbc  call    cs:__imp_?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z; CLKRHashTable::Apply(LK_ACTION (*)(void const *,void *),void *,LK_LOCKTYPE)
0x18001adc2  mov     rcx, [rsp+2C0h+var_280]
0x18001adc7  lea     rax, [rsp+2C0h+var_280]
0x18001adcc  cmp     rcx, rax
0x18001adcf  jz      short loc_18001AE12
0x18001add1  lea     rax, [rsp+2C0h+var_280]
0x18001add6  cmp     [rcx+8], rax
0x18001adda  jnz     short loc_18001AE0B
0x18001addc  mov     rax, [rcx]
0x18001addf  cmp     [rax+8], rcx
0x18001ade3  jnz     short loc_18001AE0B
0x18001ade5  mov     [rsp+2C0h+var_280], rax
0x18001adea  lea     rdx, [rsp+2C0h+var_280]
0x18001adef  add     rcx, 0FFFFFFFFFFFFFF40h; this
0x18001adf6  mov     [rax+8], rdx
0x18001adfa  mov     dword ptr [rcx+0B8h], 1
0x18001ae04  call    ?CheckIfShouldTerminate@REQUEST_QUEUE_DATA@@QEAAXXZ; REQUEST_QUEUE_DATA::CheckIfShouldTerminate(void)
0x18001ae09  jmp     short loc_18001ADC2
0x18001ae0b  mov     ecx, 3
0x18001ae10  int     29h; Win8: RtlFailFast(ecx)
0x18001ae12  mov     rcx, [rdi+50h]; this
0x18001ae16  test    rcx, rcx
0x18001ae19  jz      short loc_18001AE47
0x18001ae1b  call    ?Terminate@JOB_OBJECT@@QEAAXXZ; JOB_OBJECT::Terminate(void)
0x18001ae20  mov     rcx, [rdi+50h]
0x18001ae24  mov     rax, [rcx]
0x18001ae27  mov     rax, [rax+8]
0x18001ae2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae30  mov     qword ptr [rdi+50h], 0
0x18001ae38  jmp     short loc_18001AE47
0x18001ae3a  mov     rcx, [rdi+68h]
0x18001ae3e  sub     rcx, 10h; this
0x18001ae42  call    ?Terminate@WORKER_PROCESS@@QEAAXXZ; WORKER_PROCESS::Terminate(void)
0x18001ae47  cmp     dword ptr [rdi+78h], 0
0x18001ae4b  ja      short loc_18001AE3A
0x18001ae4d  lea     rbx, [rdi+180h]
0x18001ae54  cmp     dword ptr [rbx+30h], 0
0x18001ae58  jz      loc_18001AEE0
0x18001ae5e  mov     rcx, [rdi+1A0h]; lpFileName
0x18001ae65  call    cs:__imp_DeleteFileW
0x18001ae6b  xor     edx, edx; Val
0x18001ae6d  lea     rcx, [rbp+1C0h+var_220]; void *
0x18001ae71  mov     r8d, 208h; Size
0x18001ae77  call    memset_0
0x18001ae7c  mov     r8d, 104h
0x18001ae82  lea     rdx, [rbp+1C0h+var_220]
0x18001ae86  lea     rcx, [rsp+2C0h+var_258]
0x18001ae8b  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001ae91  mov     rdx, rbx
0x18001ae94  lea     rcx, [rsp+2C0h+var_258]
0x18001ae99  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x18001ae9f  test    eax, eax
0x18001aea1  js      short loc_18001AED5
0x18001aea3  mov     rcx, [rbp+1C0h+Str]; Str
0x18001aea7  mov     edx, 5Ch ; '\'; Ch
0x18001aeac  call    cs:__imp_wcsrchr
0x18001aeb2  test    rax, rax
0x18001aeb5  jz      short loc_18001AED5
0x18001aeb7  sub     rax, [rbp+1C0h+Str]
0x18001aebb  lea     rcx, [rsp+2C0h+var_258]
0x18001aec0  sar     rax, 1
0x18001aec3  mov     edx, eax
0x18001aec5  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x18001aecb  mov     rcx, [rbp+1C0h+Str]; lpPathName
0x18001aecf  call    cs:__imp_RemoveDirectoryW
0x18001aed5  lea     rcx, [rsp+2C0h+var_258]
0x18001aeda  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001aee0  mov     rcx, [rdi+200h]
0x18001aee7  test    rcx, rcx
0x18001aeea  jz      short loc_18001AF07
0x18001aeec  mov     rax, [rcx]
0x18001aeef  mov     edx, 1
0x18001aef4  mov     rax, [rax]
0x18001aef7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aefc  mov     qword ptr [rdi+200h], 0
0x18001af07  cmp     dword ptr [rdi+10h], 0
0x18001af0b  jz      short loc_18001AF20
0x18001af0d  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x18001af14  mov     rdx, rdi; struct APP_POOL *
0x18001af17  add     rcx, 70h ; 'p'; this
0x18001af1b  call    ?RemoveAppPoolFromTable@UL_AND_WORKER_MANAGER@@QEAAXPEAVAPP_POOL@@@Z; UL_AND_WORKER_MANAGER::RemoveAppPoolFromTable(APP_POOL *)
0x18001af20  mov     rcx, [rbp+1C0h+var_10]
0x18001af27  xor     rcx, rsp; StackCookie
0x18001af2a  call    __security_check_cookie
0x18001af2f  lea     r11, [rsp+2C0h+var_s0]
0x18001af37  mov     rbx, [r11+18h]
0x18001af3b  mov     rdi, [r11+20h]
0x18001af3f  mov     rsp, r11
0x18001af42  pop     rbp
0x18001af43  retn
```
