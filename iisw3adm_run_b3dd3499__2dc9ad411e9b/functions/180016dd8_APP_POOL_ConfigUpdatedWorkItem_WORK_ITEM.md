# APP_POOL::ConfigUpdatedWorkItem(WORK_ITEM *)

- ea: `0x180016dd8`
- end: `0x180017038`
- name: `?ConfigUpdatedWorkItem@APP_POOL@@AEAAJPEAVWORK_ITEM@@@Z`
- size: `608`
- prototype: `__int64 __fastcall(APP_POOL *__hidden this, struct WORK_ITEM *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180017dd0`

## callees

- `0x180001274`
- `0x18000d67c`
- `0x18001685c`
- `0x180016c7c`
- `0x180016dd8`
- `0x180017f18`
- `0x180018a9c`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x180017015`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180017015`
- `iisutil!PuDbgPrint` at `0x180016e45`
- `iisutil!PuDbgPrint` at `0x180016efe`
- `iisutil!PuDbgPrint` at `0x180016fae`
- `iisutil!PuDbgPrint` at `0x180016e45`
- `iisutil!PuDbgPrint` at `0x180016efe`
- `iisutil!PuDbgPrint` at `0x180016fae`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180016f23`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180016f23`

## string_xrefs

- `0x180016e17`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\app_pool.cxx`
- `0x180016edb`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\app_pool.cxx`
- `0x180016f8b`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\app_pool.cxx`
- `0x180016e2d`: `Config update completed (ptr: %p; id: %S; NewChangeNumber: %d)\n`
- `0x180016e0c`: `APP_POOL::ConfigUpdatedWorkItem`
- `0x180016ecd`: `APP_POOL::ConfigUpdatedWorkItem`
- `0x180016f7d`: `APP_POOL::ConfigUpdatedWorkItem`
- `0x180016eed`: `Retrying generation of app pool config file (ptr: %p; id: %S)\n`

## pseudocode

```c
__int64 __fastcall APP_POOL::ConfigUpdatedWorkItem(APP_POOL *this, struct WORK_ITEM *a2)
{
  int v2; // r9d
  char *v4; // rsi
  int v6; // edi
  bool v7; // zf
  _QWORD **v8; // rbx
  _QWORD *v9; // rax
  _QWORD *v10; // rcx
  _QWORD *v11; // rdi

  v2 = g_dwDebugFlags;
  v4 = (char *)*((_QWORD *)a2 + 11);
  if ( (g_dwDebugFlags & 3) != 0 && g_dwDebugFlags < 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool.cxx",
      828,
      "APP_POOL::ConfigUpdatedWorkItem",
      "Config update completed (ptr: %p; id: %S; NewChangeNumber: %d)\n",
      this,
      *((const wchar_t **)this + 7),
      *((_DWORD *)v4 + 1));
    v2 = g_dwDebugFlags;
  }
  if ( *((_DWORD *)this + 110) )
  {
    APP_POOL::GenerateErrorConfigFile(this);
LABEL_5:
    v6 = APP_POOL::CompletePendingOperations(this);
    goto LABEL_26;
  }
  if ( *((_DWORD *)this + 5) == 3 )
  {
    if ( *(_DWORD *)v4 )
    {
      if ( *((_DWORD *)this + 89) )
      {
        *((_DWORD *)this + 89) = 0;
        if ( (v2 & 3) != 0 && v2 < 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool.cxx",
            870,
            "APP_POOL::ConfigUpdatedWorkItem",
            "Retrying generation of app pool config file (ptr: %p; id: %S)\n",
            this,
            *((const wchar_t **)this + 7));
        goto LABEL_5;
      }
      v6 = 0;
      *((_DWORD *)this + 89) = 1;
      APP_POOL::NotifyConfigChanged(this, 0, 0);
    }
    else
    {
      v7 = *((_DWORD *)this + 108) == 0;
      *((_DWORD *)this + 94) = *((_DWORD *)v4 + 1);
      if ( !v7 || (v6 = STRU::Copy((APP_POOL *)((char *)this + 384), *((const unsigned __int16 **)v4 + 5)), v6 >= 0) )
      {
        if ( !(unsigned int)APP_POOL_ISOLATION::IsConfigChangeNumberOk(
                              *((APP_POOL_ISOLATION **)g_pWebAdminService + 229),
                              *((_DWORD *)this + 94)) )
          APP_POOL::NotifyConfigChanged(this, 0, 0);
        goto LABEL_5;
      }
    }
  }
  else
  {
    if ( (v2 & 3) != 0 && v2 < 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool.cxx",
        917,
        "APP_POOL::ConfigUpdatedWorkItem",
        "App Pool disabled, purging all pending isolation operations (ptr: %p; id: %S)\n",
        this,
        *((const wchar_t **)this + 7));
    v8 = (_QWORD **)((char *)this + 360);
    while ( 1 )
    {
      v9 = *v8;
      if ( *v8 == v8 )
        break;
      if ( (_QWORD **)v9[1] != v8 || (v10 = (_QWORD *)*v9, *(_QWORD **)(*v9 + 8LL) != v9) )
        __fastfail(3u);
      *v8 = v10;
      v11 = v9 - 6;
      v10[1] = v8;
      *v9 = 0;
      v9[1] = 0;
      if ( v9 != (_QWORD *)48 )
      {
        APP_POOL_WORK_CONTEXT::~APP_POOL_WORK_CONTEXT((APP_POOL_WORK_CONTEXT *)(v9 - 6));
        operator delete(v11);
      }
    }
    v6 = 0;
  }
LABEL_26:
  if ( v4 )
  {
    STRU::~STRU((STRU *)(v4 + 8));
    operator delete(v4);
  }
  *((_QWORD *)a2 + 11) = 0;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180016dd8  push    rbx
0x180016dda  push    rbp
0x180016ddb  push    rsi
0x180016ddc  push    rdi
0x180016ddd  push    r14
0x180016ddf  sub     rsp, 40h
0x180016de3  mov     r9d, cs:g_dwDebugFlags
0x180016dea  mov     rbp, rdx
0x180016ded  mov     rsi, [rdx+58h]
0x180016df1  test    r9b, 3
0x180016df5  mov     rbx, rcx
0x180016df8  setnz   r8b
0x180016dfc  bt      r9d, 1Fh
0x180016e01  setb    al
0x180016e04  test    al, r8b
0x180016e07  jz      short loc_180016E52
0x180016e09  mov     eax, [rsi+4]
0x180016e0c  lea     r9, aAppPoolConfigu; "APP_POOL::ConfigUpdatedWorkItem"
0x180016e13  mov     [rsp+68h+var_30], eax
0x180016e17  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180016e1e  mov     rax, [rcx+38h]
0x180016e22  mov     r8d, 33Ch
0x180016e28  mov     [rsp+68h+var_38], rax
0x180016e2d  lea     rax, aConfigUpdateCo; "Config update completed (ptr: %p; id: %"...
0x180016e34  mov     [rsp+68h+var_40], rcx
0x180016e39  mov     rcx, cs:g_pDebug
0x180016e40  mov     [rsp+68h+var_48], rax
0x180016e45  call    cs:__imp_PuDbgPrint
0x180016e4b  mov     r9d, cs:g_dwDebugFlags
0x180016e52  cmp     dword ptr [rbx+1B8h], 0
0x180016e59  jz      short loc_180016E72
0x180016e5b  mov     rcx, rbx; this
0x180016e5e  call    ?GenerateErrorConfigFile@APP_POOL@@QEAAXXZ; APP_POOL::GenerateErrorConfigFile(void)
0x180016e63  mov     rcx, rbx; this
0x180016e66  call    ?CompletePendingOperations@APP_POOL@@AEAAJXZ; APP_POOL::CompletePendingOperations(void)
0x180016e6b  mov     edi, eax
0x180016e6d  jmp     loc_18001700C
0x180016e72  cmp     dword ptr [rbx+14h], 3
0x180016e76  jnz     loc_180016F66
0x180016e7c  cmp     dword ptr [rsi], 0
0x180016e7f  jz      loc_180016F09
0x180016e85  cmp     dword ptr [rbx+164h], 0
0x180016e8c  jnz     short loc_180016EAC
0x180016e8e  xor     edi, edi
0x180016e90  mov     dword ptr [rbx+164h], 1
0x180016e9a  xor     r8d, r8d; int
0x180016e9d  xor     edx, edx; unsigned int
0x180016e9f  mov     rcx, rbx; this
0x180016ea2  call    ?NotifyConfigChanged@APP_POOL@@QEAAXKH@Z; APP_POOL::NotifyConfigChanged(ulong,int)
0x180016ea7  jmp     loc_18001700C
0x180016eac  test    r9b, 3
0x180016eb0  mov     dword ptr [rbx+164h], 0
0x180016eba  setnz   cl
0x180016ebd  bt      r9d, 1Fh
0x180016ec2  setb    al
0x180016ec5  test    al, cl
0x180016ec7  jz      short loc_180016E63
0x180016ec9  mov     rax, [rbx+38h]
0x180016ecd  lea     r9, aAppPoolConfigu; "APP_POOL::ConfigUpdatedWorkItem"
0x180016ed4  mov     rcx, cs:g_pDebug
0x180016edb  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180016ee2  mov     [rsp+68h+var_38], rax
0x180016ee7  mov     r8d, 366h
0x180016eed  lea     rax, aRetryingGenera; "Retrying generation of app pool config "...
0x180016ef4  mov     [rsp+68h+var_40], rbx
0x180016ef9  mov     [rsp+68h+var_48], rax
0x180016efe  call    cs:__imp_PuDbgPrint
0x180016f04  jmp     loc_180016E63
0x180016f09  mov     eax, [rsi+4]
0x180016f0c  lea     rcx, [rbx+180h]
0x180016f13  cmp     dword ptr [rcx+30h], 0
0x180016f17  mov     [rbx+178h], eax
0x180016f1d  jnz     short loc_180016F33
0x180016f1f  mov     rdx, [rsi+28h]
0x180016f23  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180016f29  mov     edi, eax
0x180016f2b  test    eax, eax
0x180016f2d  js      loc_18001700C
0x180016f33  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x180016f3a  mov     edx, [rbx+178h]; unsigned int
0x180016f40  mov     rcx, [rcx+728h]; this
0x180016f47  call    ?IsConfigChangeNumberOk@APP_POOL_ISOLATION@@QEAAHK@Z; APP_POOL_ISOLATION::IsConfigChangeNumberOk(ulong)
0x180016f4c  test    eax, eax
0x180016f4e  jnz     loc_180016E63
0x180016f54  xor     r8d, r8d; int
0x180016f57  xor     edx, edx; unsigned int
0x180016f59  mov     rcx, rbx; this
0x180016f5c  call    ?NotifyConfigChanged@APP_POOL@@QEAAXKH@Z; APP_POOL::NotifyConfigChanged(ulong,int)
0x180016f61  jmp     loc_180016E63
0x180016f66  test    r9b, 3
0x180016f6a  setnz   cl
0x180016f6d  bt      r9d, 1Fh
0x180016f72  setb    al
0x180016f75  test    al, cl
0x180016f77  jz      short loc_180016FB4
0x180016f79  mov     rax, [rbx+38h]
0x180016f7d  lea     r9, aAppPoolConfigu; "APP_POOL::ConfigUpdatedWorkItem"
0x180016f84  mov     rcx, cs:g_pDebug
0x180016f8b  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180016f92  mov     [rsp+68h+var_38], rax
0x180016f97  mov     r8d, 395h
0x180016f9d  lea     rax, aAppPoolDisable; "App Pool disabled, purging all pending "...
0x180016fa4  mov     [rsp+68h+var_40], rbx
0x180016fa9  mov     [rsp+68h+var_48], rax
0x180016fae  call    cs:__imp_PuDbgPrint
0x180016fb4  add     rbx, 168h
0x180016fbb  mov     rax, [rbx]
0x180016fbe  cmp     rax, rbx
0x180016fc1  jz      short loc_18001700A
0x180016fc3  cmp     [rax+8], rbx
0x180016fc7  jnz     short loc_180017003
0x180016fc9  mov     rcx, [rax]
0x180016fcc  cmp     [rcx+8], rax
0x180016fd0  jnz     short loc_180017003
0x180016fd2  mov     [rbx], rcx
0x180016fd5  lea     rdi, [rax-30h]
0x180016fd9  mov     [rcx+8], rbx
0x180016fdd  mov     qword ptr [rax], 0
0x180016fe4  mov     qword ptr [rax+8], 0
0x180016fec  test    rdi, rdi
0x180016fef  jz      short loc_180016FBB
0x180016ff1  mov     rcx, rdi; this
0x180016ff4  call    ??1APP_POOL_WORK_CONTEXT@@QEAA@XZ; APP_POOL_WORK_CONTEXT::~APP_POOL_WORK_CONTEXT(void)
0x180016ff9  mov     rcx, rdi; Block
0x180016ffc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180017001  jmp     short loc_180016FBB
0x180017003  mov     ecx, 3
0x180017008  int     29h; Win8: RtlFailFast(ecx)
0x18001700a  xor     edi, edi
0x18001700c  test    rsi, rsi
0x18001700f  jz      short loc_180017023
0x180017011  lea     rcx, [rsi+8]
0x180017015  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001701b  mov     rcx, rsi; Block
0x18001701e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180017023  mov     qword ptr [rbp+58h], 0
0x18001702b  mov     eax, edi
0x18001702d  add     rsp, 40h
0x180017031  pop     r14
0x180017033  pop     rdi
0x180017034  pop     rsi
0x180017035  pop     rbp
0x180017036  pop     rbx
0x180017037  retn
```
