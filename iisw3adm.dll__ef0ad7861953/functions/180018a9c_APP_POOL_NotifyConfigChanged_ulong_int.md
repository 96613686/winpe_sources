# APP_POOL::NotifyConfigChanged(ulong,int)

- ea: `0x180018a9c`
- end: `0x180018e04`
- name: `?NotifyConfigChanged@APP_POOL@@QEAAXKH@Z`
- size: `872`
- prototype: `void __fastcall(APP_POOL *__hidden this, unsigned int, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180011ca0`
- `0x180016dd8`

## callees

- `0x180001234`
- `0x180001274`
- `0x18000d67c`
- `0x180016c7c`
- `0x180018a9c`
- `0x180060878`
- `0x1800608f4`
- `0x180060b18`
- `0x180062010`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x180018d81`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180018d81`
- `iisutil!PuDbgPrint` at `0x180018b30`
- `iisutil!PuDbgPrint` at `0x180018bd6`
- `iisutil!PuDbgPrint` at `0x180018ce8`
- `iisutil!PuDbgPrint` at `0x180018b30`
- `iisutil!PuDbgPrint` at `0x180018bd6`
- `iisutil!PuDbgPrint` at `0x180018ce8`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180018d32`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180018d32`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180018d73`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180018d73`

## string_xrefs

- `0x180018b16`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\app_pool.cxx`
- `0x180018b86`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\app_pool.cxx`
- `0x180018cbd`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\app_pool.cxx`
- `0x180018b21`: `Config update skipped (ptr: %p; id: %S; CurChangeNumber: %d)\n`
- `0x180018afe`: `APP_POOL::NotifyConfigChanged`
- `0x180018b7c`: `APP_POOL::NotifyConfigChanged`
- `0x180018caf`: `APP_POOL::NotifyConfigChanged`
- `0x180018bc5`: `Considering config update (ptr: %p; id: %S; CurChangeNumber: %d; Pending Config: %d; WP Count: %d; IsPendingOperation: %d, ConfigChangeNumberOk: %d)\n`
- `0x180018cd7`: `Config update requested (ptr: %p; id: %S; CurChangeNumber: %d)\n`

## pseudocode

```c
void __fastcall APP_POOL::NotifyConfigChanged(APP_POOL *this, unsigned int a2, int a3)
{
  int v6; // eax
  bool v7; // zf
  int v8; // eax
  _QWORD *v9; // rdi
  _QWORD *v10; // rax
  _QWORD *v11; // rcx
  _QWORD *v12; // rax
  _QWORD *v13; // rax
  int BlankWorkItem; // eax
  struct MULTI_WORK_ITEM *v15; // rdi
  _QWORD *v16; // rax
  _QWORD *v17; // rsi
  const unsigned __int16 *v18; // rdx
  WEB_ADMIN_SERVICE *v19; // rax
  struct MULTI_WORK_ITEM *v20; // [rsp+80h] [rbp+8h] BYREF

  v20 = 0;
  *((_DWORD *)this + 110) = 0;
  if ( *((_DWORD *)this + 94) || *((_DWORD *)this + 30) || *((APP_POOL **)this + 45) != (APP_POOL *)((char *)this + 360) )
  {
    v6 = g_dwDebugFlags;
    v7 = (g_dwDebugFlags & 3) == 0;
    *((_DWORD *)this + 94) = a2;
    if ( !v7 && v6 < 0 )
    {
      v8 = APP_POOL_ISOLATION::IsConfigChangeNumberOk(*((APP_POOL_ISOLATION **)g_pWebAdminService + 229), a2);
      v9 = (_QWORD *)((char *)this + 360);
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool.cxx",
        1722,
        "APP_POOL::NotifyConfigChanged",
        "Considering config update (ptr: %p; id: %S; CurChangeNumber: %d; Pending Config: %d; WP Count: %d; IsPendingOper"
        "ation: %d, ConfigChangeNumberOk: %d)\n",
        this,
        *((const wchar_t **)this + 7),
        *((_DWORD *)this + 94),
        *((_DWORD *)this + 88),
        *((_DWORD *)this + 30),
        *v9 != (_QWORD)v9,
        v8);
    }
    else
    {
      v9 = (_QWORD *)((char *)this + 360);
    }
    if ( a3 )
    {
      v10 = operator new(0x40u);
      if ( !v10 )
        return;
      v10[1] = 0;
      v11 = v10 + 6;
      v10[2] = 0;
      v10[3] = 0;
      v10[4] = 0;
      v10[6] = 0;
      *(_DWORD *)v10 = 2;
      *((_DWORD *)v10 + 10) = 1;
      v10[7] = 0;
      v12 = (_QWORD *)v9[1];
      if ( (_QWORD *)*v12 != v9 )
        __fastfail(3u);
      v11[1] = v12;
      *v11 = v9;
      *v12 = v11;
      v13 = (_QWORD *)((char *)this + 360);
      v9[1] = v11;
    }
    else
    {
      v13 = v9;
    }
    if ( !*((_DWORD *)this + 88) )
    {
      if ( a2 )
      {
        if ( (_QWORD *)*v9 != v9 )
          APP_POOL::CompletePendingOperations((const wchar_t **)this);
      }
      else if ( (*((_DWORD *)this + 30) || (_QWORD *)*v13 != v13)
             && !(unsigned int)APP_POOL_ISOLATION::IsConfigChangeNumberOk(
                                 *((APP_POOL_ISOLATION **)g_pWebAdminService + 229),
                                 *((_DWORD *)this + 94)) )
      {
        if ( (g_dwDebugFlags & 3) != 0 && g_dwDebugFlags < 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool.cxx",
            1765,
            "APP_POOL::NotifyConfigChanged",
            "Config update requested (ptr: %p; id: %S; CurChangeNumber: %d)\n",
            this,
            *((const wchar_t **)this + 7),
            *((_DWORD *)this + 94));
        BlankWorkItem = MULTI_WORK_QUEUE::GetBlankWorkItem(
                          (MULTI_WORK_QUEUE *)(*((_QWORD *)g_pWebAdminService + 229) + 392LL),
                          &v20);
        v15 = v20;
        if ( BlankWorkItem >= 0 )
        {
          v16 = operator new(0x40u);
          v17 = v16;
          if ( v16 )
          {
            STRU::STRU((STRU *)(v16 + 1));
            MULTI_WORK_ITEM::SetWorkDispatchPointer(v15, *((struct MULTI_WORK_DISPATCH **)g_pWebAdminService + 229));
            (**(void (__fastcall ***)(APP_POOL *))this)(this);
            *v17 = this;
            v18 = *(const unsigned __int16 **)(*((_QWORD *)this + 11) + 192LL);
            if ( v18 && (int)STRU::Copy((STRU *)(v17 + 1), v18) < 0 )
            {
              STRU::~STRU((STRU *)(v17 + 1));
              operator delete(v17);
            }
            else
            {
              v19 = g_pWebAdminService;
              *((_QWORD *)v15 + 5) = v17;
              *((_QWORD *)v15 + 2) = 1;
              if ( (int)MULTI_WORK_QUEUE::QueueWorkItem((MULTI_WORK_QUEUE *)(*((_QWORD *)v19 + 229) + 392LL), v15) >= 0 )
              {
                *((_DWORD *)this + 88) = 1;
                return;
              }
            }
          }
        }
        if ( v15 )
          (**(void (__fastcall ***)(struct MULTI_WORK_ITEM *, __int64))v15)(v15, 1);
      }
    }
  }
  else if ( (g_dwDebugFlags & 3) != 0 && g_dwDebugFlags < 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool.cxx",
      1702,
      "APP_POOL::NotifyConfigChanged",
      "Config update skipped (ptr: %p; id: %S; CurChangeNumber: %d)\n",
      this,
      *((const wchar_t **)this + 7),
      a2);
  }
}

```

## disassembly

```asm
0x180018a9c  mov     r11, rsp
0x180018a9f  mov     [r11+10h], rbx
0x180018aa3  mov     [r11+18h], rbp
0x180018aa7  push    rsi
0x180018aa8  push    rdi
0x180018aa9  push    r14
0x180018aab  sub     rsp, 60h
0x180018aaf  xor     r14d, r14d
0x180018ab2  mov     ebp, r8d
0x180018ab5  mov     esi, edx
0x180018ab7  mov     rbx, rcx
0x180018aba  mov     [r11+8], r14
0x180018abe  mov     [rcx+1B8h], r14d
0x180018ac5  cmp     [rcx+178h], r14d
0x180018acc  jnz     short loc_180018B3B
0x180018ace  cmp     [rcx+78h], r14d
0x180018ad2  jnz     short loc_180018B3B
0x180018ad4  lea     rax, [rcx+168h]
0x180018adb  cmp     [rax], rax
0x180018ade  jnz     short loc_180018B3B
0x180018ae0  mov     eax, cs:g_dwDebugFlags
0x180018ae6  test    al, 3
0x180018ae8  setnz   cl
0x180018aeb  bt      eax, 1Fh
0x180018aef  setb    al
0x180018af2  test    al, cl
0x180018af4  jz      loc_180018DEF
0x180018afa  mov     rax, [rbx+38h]
0x180018afe  lea     r9, aAppPoolNotifyc; "APP_POOL::NotifyConfigChanged"
0x180018b05  mov     rcx, cs:g_pDebug
0x180018b0c  mov     r8d, 6A6h
0x180018b12  mov     [rsp+78h+var_40], edx
0x180018b16  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180018b1d  mov     [r11-48h], rax
0x180018b21  lea     rax, aConfigUpdateSk; "Config update skipped (ptr: %p; id: %S;"...
0x180018b28  mov     [r11-50h], rbx
0x180018b2c  mov     [r11-58h], rax
0x180018b30  call    cs:__imp_PuDbgPrint
0x180018b36  jmp     loc_180018DEF
0x180018b3b  mov     eax, cs:g_dwDebugFlags
0x180018b41  test    al, 3
0x180018b43  mov     [rcx+178h], esi
0x180018b49  setnz   cl
0x180018b4c  bt      eax, 1Fh
0x180018b50  setb    al
0x180018b53  test    al, cl
0x180018b55  jz      loc_180018BDE
0x180018b5b  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x180018b62  mov     rcx, [rcx+728h]; this
0x180018b69  call    ?IsConfigChangeNumberOk@APP_POOL_ISOLATION@@QEAAHK@Z; APP_POOL_ISOLATION::IsConfigChangeNumberOk(ulong)
0x180018b6e  mov     [rsp+78h+var_20], eax
0x180018b72  lea     rdi, [rbx+168h]
0x180018b79  mov     eax, [rbx+78h]
0x180018b7c  lea     r9, aAppPoolNotifyc; "APP_POOL::NotifyConfigChanged"
0x180018b83  cmp     [rdi], rdi
0x180018b86  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180018b8d  mov     ecx, r14d
0x180018b90  mov     r8d, 6BAh
0x180018b96  setnz   cl
0x180018b99  mov     [rsp+78h+var_28], ecx
0x180018b9d  mov     rcx, cs:g_pDebug
0x180018ba4  mov     [rsp+78h+var_30], eax
0x180018ba8  mov     eax, [rbx+160h]
0x180018bae  mov     [rsp+78h+var_38], eax
0x180018bb2  mov     eax, [rbx+178h]
0x180018bb8  mov     [rsp+78h+var_40], eax
0x180018bbc  mov     rax, [rbx+38h]
0x180018bc0  mov     [rsp+78h+var_48], rax
0x180018bc5  lea     rax, aConsideringCon; "Considering config update (ptr: %p; id:"...
0x180018bcc  mov     [rsp+78h+var_50], rbx
0x180018bd1  mov     [rsp+78h+var_58], rax
0x180018bd6  call    cs:__imp_PuDbgPrint
0x180018bdc  jmp     short loc_180018BE5
0x180018bde  lea     rdi, [rbx+168h]
0x180018be5  test    ebp, ebp
0x180018be7  jz      short loc_180018C4B
0x180018be9  mov     ecx, 40h ; '@'; Size
0x180018bee  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018bf3  test    rax, rax
0x180018bf6  jz      loc_180018DEF
0x180018bfc  mov     [rax+8], r14
0x180018c00  lea     rcx, [rax+30h]
0x180018c04  mov     [rax+10h], r14
0x180018c08  mov     [rax+18h], r14
0x180018c0c  mov     [rax+20h], r14
0x180018c10  mov     [rcx], r14
0x180018c13  mov     dword ptr [rax], 2
0x180018c19  mov     dword ptr [rax+28h], 1
0x180018c20  mov     [rax+38h], r14
0x180018c24  mov     rax, [rdi+8]
0x180018c28  cmp     [rax], rdi
0x180018c2b  jz      short loc_180018C34
0x180018c2d  mov     ecx, 3
0x180018c32  int     29h; Win8: RtlFailFast(ecx)
0x180018c34  mov     [rcx+8], rax
0x180018c38  mov     [rcx], rdi
0x180018c3b  mov     [rax], rcx
0x180018c3e  lea     rax, [rbx+168h]
0x180018c45  mov     [rdi+8], rcx
0x180018c49  jmp     short loc_180018C4E
0x180018c4b  mov     rax, rdi
0x180018c4e  cmp     [rbx+160h], r14d
0x180018c55  jnz     loc_180018DEF
0x180018c5b  test    esi, esi
0x180018c5d  jnz     loc_180018DE2
0x180018c63  cmp     [rbx+78h], r14d
0x180018c67  ja      short loc_180018C72
0x180018c69  cmp     [rax], rax
0x180018c6c  jz      loc_180018DEF
0x180018c72  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x180018c79  mov     edx, [rbx+178h]; unsigned int
0x180018c7f  mov     rcx, [rcx+728h]; this
0x180018c86  call    ?IsConfigChangeNumberOk@APP_POOL_ISOLATION@@QEAAHK@Z; APP_POOL_ISOLATION::IsConfigChangeNumberOk(ulong)
0x180018c8b  test    eax, eax
0x180018c8d  jnz     loc_180018DEF
0x180018c93  mov     eax, cs:g_dwDebugFlags
0x180018c99  test    al, 3
0x180018c9b  setnz   cl
0x180018c9e  bt      eax, 1Fh
0x180018ca2  setb    al
0x180018ca5  test    al, cl
0x180018ca7  jz      short loc_180018CEE
0x180018ca9  mov     eax, [rbx+178h]
0x180018caf  lea     r9, aAppPoolNotifyc; "APP_POOL::NotifyConfigChanged"
0x180018cb6  mov     rcx, cs:g_pDebug
0x180018cbd  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180018cc4  mov     [rsp+78h+var_40], eax
0x180018cc8  mov     r8d, 6E5h
0x180018cce  mov     rax, [rbx+38h]
0x180018cd2  mov     [rsp+78h+var_48], rax
0x180018cd7  lea     rax, aConfigUpdateRe; "Config update requested (ptr: %p; id: %"...
0x180018cde  mov     [rsp+78h+var_50], rbx
0x180018ce3  mov     [rsp+78h+var_58], rax
0x180018ce8  call    cs:__imp_PuDbgPrint
0x180018cee  mov     rax, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x180018cf5  lea     rdx, [rsp+78h+arg_0]; struct MULTI_WORK_ITEM **
0x180018cfd  mov     rcx, [rax+728h]
0x180018d04  add     rcx, 188h; this
0x180018d0b  call    ?GetBlankWorkItem@MULTI_WORK_QUEUE@@QEAAJPEAPEAVMULTI_WORK_ITEM@@@Z; MULTI_WORK_QUEUE::GetBlankWorkItem(MULTI_WORK_ITEM * *)
0x180018d10  mov     rdi, [rsp+78h+arg_0]
0x180018d18  test    eax, eax
0x180018d1a  js      short loc_180018D8F
0x180018d1c  mov     ecx, 40h ; '@'; Size
0x180018d21  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018d26  mov     rsi, rax
0x180018d29  test    rax, rax
0x180018d2c  jz      short loc_180018D8F
0x180018d2e  lea     rcx, [rax+8]
0x180018d32  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180018d38  mov     rdx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x180018d3f  mov     rcx, rdi; this
0x180018d42  mov     rdx, [rdx+728h]; struct MULTI_WORK_DISPATCH *
0x180018d49  call    ?SetWorkDispatchPointer@MULTI_WORK_ITEM@@QEAAXPEAVMULTI_WORK_DISPATCH@@@Z; MULTI_WORK_ITEM::SetWorkDispatchPointer(MULTI_WORK_DISPATCH *)
0x180018d4e  mov     rcx, [rbx]
0x180018d51  mov     rax, [rcx]
0x180018d54  mov     rcx, rbx
0x180018d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d5c  mov     [rsi], rbx
0x180018d5f  mov     rax, [rbx+58h]
0x180018d63  mov     rdx, [rax+0C0h]
0x180018d6a  test    rdx, rdx
0x180018d6d  jz      short loc_180018DA9
0x180018d6f  lea     rcx, [rsi+8]
0x180018d73  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180018d79  test    eax, eax
0x180018d7b  jns     short loc_180018DA9
0x180018d7d  lea     rcx, [rsi+8]
0x180018d81  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180018d87  mov     rcx, rsi; Block
0x180018d8a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018d8f  test    rdi, rdi
0x180018d92  jz      short loc_180018DEF
0x180018d94  mov     rax, [rdi]
0x180018d97  mov     edx, 1
0x180018d9c  mov     rcx, rdi
0x180018d9f  mov     rax, [rax]
0x180018da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018da7  jmp     short loc_180018DEF
0x180018da9  mov     rax, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x180018db0  mov     rdx, rdi; struct MULTI_WORK_ITEM *
0x180018db3  mov     [rdi+28h], rsi
0x180018db7  mov     qword ptr [rdi+10h], 1
0x180018dbf  mov     rcx, [rax+728h]
0x180018dc6  add     rcx, 188h; this
0x180018dcd  call    ?QueueWorkItem@MULTI_WORK_QUEUE@@QEAAJPEAVMULTI_WORK_ITEM@@@Z; MULTI_WORK_QUEUE::QueueWorkItem(MULTI_WORK_ITEM *)
0x180018dd2  test    eax, eax
0x180018dd4  js      short loc_180018D8F
0x180018dd6  mov     dword ptr [rbx+160h], 1
0x180018de0  jmp     short loc_180018DEF
0x180018de2  cmp     [rdi], rdi
0x180018de5  jz      short loc_180018DEF
0x180018de7  mov     rcx, rbx; this
0x180018dea  call    ?CompletePendingOperations@APP_POOL@@AEAAJXZ; APP_POOL::CompletePendingOperations(void)
0x180018def  lea     r11, [rsp+78h+var_18]
0x180018df4  mov     rbx, [r11+28h]
0x180018df8  mov     rbp, [r11+30h]
0x180018dfc  mov     rsp, r11
0x180018dff  pop     r14
0x180018e01  pop     rdi
0x180018e02  pop     rsi
0x180018e03  retn
```
