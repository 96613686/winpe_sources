# APP_POOL_DATA_OBJECT_CS::SetPeriodicRestart(INativeConfigurationElement *)

- ea: `0x180046788`
- end: `0x180046c73`
- name: `?SetPeriodicRestart@APP_POOL_DATA_OBJECT_CS@@AEAAJPEAVINativeConfigurationElement@@@Z`
- size: `1259`
- prototype: `__int64 __fastcall(APP_POOL_DATA_OBJECT_CS *__hidden this, struct INativeConfigurationElement *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180048718`

## callees

- `0x180046788`
- `0x180048ab4`
- `0x180052f8c`
- `0x18005304c`
- `0x180053908`
- `0x180062010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180046901`
- `iisutil!PuDbgPrint` at `0x1800469ed`
- `iisutil!PuDbgPrint` at `0x180046acf`
- `iisutil!PuDbgPrint` at `0x180046bed`
- `iisutil!PuDbgPrint` at `0x180046901`
- `iisutil!PuDbgPrint` at `0x1800469ed`
- `iisutil!PuDbgPrint` at `0x180046acf`
- `iisutil!PuDbgPrint` at `0x180046bed`
- `iisutil!PuDbgPrintError` at `0x18004680b`
- `iisutil!PuDbgPrintError` at `0x18004680b`

## string_xrefs

- `0x180046a2d`: ` Failed reading property \n`
- `0x180046b0c`: ` Failed reading property \n`
- `0x1800467f4`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\apppoolstore_cs.cxx`
- `0x1800468be`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\apppoolstore_cs.cxx`
- `0x180046850`: ` Failed reading restart virtual memory property \n`
- `0x180046941`: ` Failed reading restart private memory property \n`

## pseudocode

```c
__int64 __fastcall APP_POOL_DATA_OBJECT_CS::SetPeriodicRestart(
        APP_POOL_DATA_OBJECT_CS *this,
        struct INativeConfigurationElement *a2)
{
  __int64 v2; // rax
  __int64 (__fastcall *v4)(struct INativeConfigurationElement *, const wchar_t *, struct INativeConfigurationElement **); // rax
  int restarted; // ebx
  const char *v6; // rax
  __int64 v7; // r8
  unsigned int *v8; // r15
  struct CONFIG_ERROR *v9; // rdx
  unsigned int *v10; // r15
  struct CONFIG_ERROR *v11; // rdx
  unsigned int *v12; // r15
  struct CONFIG_ERROR *v13; // rdx
  __int64 v14; // r8
  struct INativePropertyException *v15; // r9
  struct CONFIG_ERROR *v16; // rdx
  __int64 v18; // [rsp+40h] [rbp-10h] BYREF
  struct INativePropertyException *v19; // [rsp+98h] [rbp+48h] BYREF
  struct CONFIG_ERROR *v20; // [rsp+A0h] [rbp+50h] BYREF
  struct INativeConfigurationElement *v21; // [rsp+A8h] [rbp+58h] BYREF

  v2 = *(_QWORD *)a2;
  v21 = 0;
  v18 = 0;
  v4 = *(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, struct INativeConfigurationElement **))(v2 + 32);
  v19 = 0;
  v20 = 0;
  restarted = v4(a2, L"periodicRestart", &v21);
  if ( restarted < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_45;
    v6 = " Failed getting Periodic Restart Element \n";
    v7 = 2377;
    goto LABEL_4;
  }
  v8 = (unsigned int *)((char *)this + 112);
  restarted = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)v21 + 48LL))(
                v21,
                L"memory",
                (char *)this + 112,
                &v19,
                0);
  if ( restarted >= 0 )
  {
    if ( v19 )
    {
      CONFIG_ERROR::CreateAndInitWithLong(&v20, L"memory", *v8, v19);
      v9 = v20;
      if ( v20 )
      {
        *((_DWORD *)v20 + 2) = 3;
        CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v9);
      }
      v20 = 0;
      (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v19 + 16LL))(v19);
      v19 = 0;
    }
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
        2411,
        "APP_POOL_DATA_OBJECT_CS::SetPeriodicRestart",
        " Periodic Restart Virtual Memory (bytes) = %u (0x%X) (%d) \n ",
        *v8,
        *v8,
        *v8);
    v10 = (unsigned int *)((char *)this + 116);
    restarted = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)v21 + 48LL))(
                  v21,
                  L"privateMemory",
                  (char *)this + 116,
                  &v19,
                  0);
    if ( restarted >= 0 )
    {
      if ( v19 )
      {
        CONFIG_ERROR::CreateAndInitWithLong(&v20, L"privateMemory", *v10, v19);
        v11 = v20;
        if ( v20 )
        {
          *((_DWORD *)v20 + 2) = 4;
          CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v11);
        }
        v20 = 0;
        (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v19 + 16LL))(v19);
        v19 = 0;
      }
      if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
          2444,
          "APP_POOL_DATA_OBJECT_CS::SetPeriodicRestart",
          " Periodic Restart Private Memory (bytes) = %u (0x%X) (%d) \n ",
          *v10,
          *v10,
          *v10);
      v12 = (unsigned int *)((char *)this + 108);
      restarted = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)v21 + 48LL))(
                    v21,
                    L"requests",
                    (char *)this + 108,
                    &v19,
                    0);
      if ( restarted >= 0 )
      {
        if ( v19 )
        {
          CONFIG_ERROR::CreateAndInitWithLong(&v20, L"requests", *v12, v19);
          v13 = v20;
          if ( v20 )
          {
            *((_DWORD *)v20 + 2) = 2;
            CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v13);
          }
          v20 = 0;
          (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v19 + 16LL))(v19);
          v19 = 0;
        }
        if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
            2476,
            "APP_POOL_DATA_OBJECT_CS::SetPeriodicRestart",
            " Restart Requests = %u (0x%X) \n",
            *v12,
            *v12);
        restarted = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, __int64 *, struct INativePropertyException **, _QWORD))(*(_QWORD *)v21 + 80LL))(
                      v21,
                      L"time",
                      &v18,
                      &v19,
                      0);
        if ( restarted >= 0 )
        {
          v14 = v18;
          v15 = v19;
          *((_DWORD *)this + 26) = v18 / 10000000 / 60;
          if ( v15 )
          {
            CONFIG_ERROR::CreateAndInitWithRawTimeSpan(&v20, L"time", v14, v15);
            v16 = v20;
            if ( v20 )
            {
              *((_DWORD *)v20 + 2) = 1;
              CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v16);
            }
            (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v19 + 16LL))(v19);
            v19 = 0;
          }
          if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
              2510,
              "APP_POOL_DATA_OBJECT_CS::SetPeriodicRestart",
              " Periodic Restart Time conversion = %u (0x%X) \n",
              *((_DWORD *)this + 26),
              *((_DWORD *)this + 26));
          restarted = APP_POOL_DATA_OBJECT_CS::SetRestartSchedule(this, v21);
          if ( restarted >= 0 )
          {
            (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v21 + 16LL))(v21);
            v21 = 0;
          }
          else if ( (g_dwDebugFlags & 0xF) != 0 )
          {
            v6 = " Failed setting up Restart Schedule\n";
            v7 = 2518;
            goto LABEL_4;
          }
        }
        else if ( (g_dwDebugFlags & 0xF) != 0 )
        {
          v6 = " Failed reading property \n";
          v7 = 2487;
          goto LABEL_4;
        }
      }
      else if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        v6 = " Failed reading property \n";
        v7 = 2454;
        goto LABEL_4;
      }
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      v6 = " Failed reading restart private memory property \n";
      v7 = 2421;
      goto LABEL_4;
    }
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    v6 = " Failed reading restart virtual memory property \n";
    v7 = 2388;
LABEL_4:
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
      v7,
      "APP_POOL_DATA_OBJECT_CS::SetPeriodicRestart",
      restarted,
      v6);
  }
LABEL_45:
  if ( v19 )
  {
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  if ( v21 )
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v21 + 16LL))(v21);
  return (unsigned int)restarted;
}

```

## disassembly

```asm
0x180046788  push    rbp
0x18004678a  push    rbx
0x18004678b  push    rsi
0x18004678c  push    rdi
0x18004678d  push    r12
0x18004678f  push    r14
0x180046791  push    r15
0x180046793  mov     rbp, rsp
0x180046796  sub     rsp, 50h
0x18004679a  mov     rax, [rdx]
0x18004679d  lea     r8, [rbp+arg_18]
0x1800467a1  xor     r12d, r12d
0x1800467a4  mov     r9, rdx
0x1800467a7  mov     r14, rcx
0x1800467aa  mov     [rbp+arg_18], r12
0x1800467ae  lea     rdx, aPeriodicrestar; "periodicRestart"
0x1800467b5  mov     [rbp+var_10], r12
0x1800467b9  mov     rax, [rax+20h]
0x1800467bd  mov     rcx, r9
0x1800467c0  mov     [rbp+arg_8], r12
0x1800467c4  mov     [rbp+arg_10], r12
0x1800467c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800467cd  mov     ebx, eax
0x1800467cf  test    eax, eax
0x1800467d1  jns     short loc_180046816
0x1800467d3  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800467da  jz      loc_180046C34
0x1800467e0  lea     rax, aFailedGettingP; " Failed getting Periodic Restart Elemen"...
0x1800467e7  mov     r8d, 949h
0x1800467ed  lea     r9, aAppPoolDataObj_9; "APP_POOL_DATA_OBJECT_CS::SetPeriodicRes"...
0x1800467f4  lea     rdx, aServercommonIn_62; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800467fb  mov     rcx, cs:g_pDebug
0x180046802  mov     [rsp+50h+var_28], rax
0x180046807  mov     dword ptr [rsp+50h+var_30], ebx
0x18004680b  call    cs:__imp_PuDbgPrintError
0x180046811  jmp     loc_180046C34
0x180046816  mov     rcx, [rbp+arg_18]
0x18004681a  lea     r15, [r14+70h]
0x18004681e  lea     r9, [rbp+arg_8]
0x180046822  mov     [rsp+50h+var_30], r12
0x180046827  mov     r8, r15
0x18004682a  lea     rdx, aMemory; "memory"
0x180046831  mov     rax, [rcx]
0x180046834  mov     rax, [rax+30h]
0x180046838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004683d  mov     ebx, eax
0x18004683f  test    eax, eax
0x180046841  jns     short loc_18004685F
0x180046843  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004684a  jz      loc_180046C34
0x180046850  lea     rax, aFailedReadingR_0; " Failed reading restart virtual memory "...
0x180046857  mov     r8d, 954h
0x18004685d  jmp     short loc_1800467ED
0x18004685f  mov     r9, [rbp+arg_8]; struct INativePropertyException *
0x180046863  test    r9, r9
0x180046866  jz      short loc_1800468AF
0x180046868  mov     r8d, [r15]; int
0x18004686b  lea     rdx, aMemory; "memory"
0x180046872  lea     rcx, [rbp+arg_10]; struct CONFIG_ERROR **
0x180046876  call    ?CreateAndInitWithLong@CONFIG_ERROR@@SAXPEAPEAV1@PEBGJPEAVINativePropertyException@@@Z; CONFIG_ERROR::CreateAndInitWithLong(CONFIG_ERROR * *,ushort const *,long,INativePropertyException *)
0x18004687b  mov     rdx, [rbp+arg_10]; struct CONFIG_ERROR *
0x18004687f  test    rdx, rdx
0x180046882  jz      short loc_180046897
0x180046884  lea     rcx, [r14+3E8h]; this
0x18004688b  mov     dword ptr [rdx+8], 3
0x180046892  call    ?Add@CONFIG_ERROR_LIST@@QEAAXPEAVCONFIG_ERROR@@@Z; CONFIG_ERROR_LIST::Add(CONFIG_ERROR *)
0x180046897  mov     rcx, [rbp+arg_8]
0x18004689b  mov     [rbp+arg_10], r12
0x18004689f  mov     rax, [rcx]
0x1800468a2  mov     rax, [rax+10h]
0x1800468a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800468ab  mov     [rbp+arg_8], r12
0x1800468af  mov     eax, cs:g_dwDebugFlags
0x1800468b5  lea     rdi, aAppPoolDataObj_9; "APP_POOL_DATA_OBJECT_CS::SetPeriodicRes"...
0x1800468bc  test    al, 3
0x1800468be  lea     rsi, aServercommonIn_62; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800468c5  setnz   cl
0x1800468c8  bt      eax, 1Eh
0x1800468cc  setb    al
0x1800468cf  test    al, cl
0x1800468d1  jz      short loc_180046907
0x1800468d3  mov     eax, [r15]
0x1800468d6  mov     r9, rdi
0x1800468d9  mov     rcx, cs:g_pDebug
0x1800468e0  mov     r8d, 96Bh
0x1800468e6  mov     [rsp+50h+var_18], eax
0x1800468ea  mov     rdx, rsi
0x1800468ed  mov     [rsp+50h+var_20], eax
0x1800468f1  mov     dword ptr [rsp+50h+var_28], eax
0x1800468f5  lea     rax, aPeriodicRestar_1; " Periodic Restart Virtual Memory (bytes"...
0x1800468fc  mov     [rsp+50h+var_30], rax
0x180046901  call    cs:__imp_PuDbgPrint
0x180046907  mov     rcx, [rbp+arg_18]
0x18004690b  lea     r15, [r14+74h]
0x18004690f  lea     r9, [rbp+arg_8]
0x180046913  mov     [rsp+50h+var_30], r12
0x180046918  mov     r8, r15
0x18004691b  lea     rdx, aPrivatememory; "privateMemory"
0x180046922  mov     rax, [rcx]
0x180046925  mov     rax, [rax+30h]
0x180046929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004692e  mov     ebx, eax
0x180046930  test    eax, eax
0x180046932  jns     short loc_180046959
0x180046934  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004693b  jz      loc_180046C34
0x180046941  lea     rax, aFailedReadingR; " Failed reading restart private memory "...
0x180046948  mov     r8d, 975h
0x18004694e  mov     r9, rdi
0x180046951  mov     rdx, rsi
0x180046954  jmp     loc_1800467FB
0x180046959  mov     r9, [rbp+arg_8]; struct INativePropertyException *
0x18004695d  test    r9, r9
0x180046960  jz      short loc_1800469A9
0x180046962  mov     r8d, [r15]; int
0x180046965  lea     rdx, aPrivatememory; "privateMemory"
0x18004696c  lea     rcx, [rbp+arg_10]; struct CONFIG_ERROR **
0x180046970  call    ?CreateAndInitWithLong@CONFIG_ERROR@@SAXPEAPEAV1@PEBGJPEAVINativePropertyException@@@Z; CONFIG_ERROR::CreateAndInitWithLong(CONFIG_ERROR * *,ushort const *,long,INativePropertyException *)
0x180046975  mov     rdx, [rbp+arg_10]; struct CONFIG_ERROR *
0x180046979  test    rdx, rdx
0x18004697c  jz      short loc_180046991
0x18004697e  lea     rcx, [r14+3E8h]; this
0x180046985  mov     dword ptr [rdx+8], 4
0x18004698c  call    ?Add@CONFIG_ERROR_LIST@@QEAAXPEAVCONFIG_ERROR@@@Z; CONFIG_ERROR_LIST::Add(CONFIG_ERROR *)
0x180046991  mov     rcx, [rbp+arg_8]
0x180046995  mov     [rbp+arg_10], r12
0x180046999  mov     rax, [rcx]
0x18004699c  mov     rax, [rax+10h]
0x1800469a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800469a5  mov     [rbp+arg_8], r12
0x1800469a9  mov     eax, cs:g_dwDebugFlags
0x1800469af  test    al, 3
0x1800469b1  setnz   cl
0x1800469b4  bt      eax, 1Eh
0x1800469b8  setb    al
0x1800469bb  test    al, cl
0x1800469bd  jz      short loc_1800469F3
0x1800469bf  mov     eax, [r15]
0x1800469c2  mov     r9, rdi
0x1800469c5  mov     rcx, cs:g_pDebug
0x1800469cc  mov     r8d, 98Ch
0x1800469d2  mov     [rsp+50h+var_18], eax
0x1800469d6  mov     rdx, rsi
0x1800469d9  mov     [rsp+50h+var_20], eax
0x1800469dd  mov     dword ptr [rsp+50h+var_28], eax
0x1800469e1  lea     rax, aPeriodicRestar; " Periodic Restart Private Memory (bytes"...
0x1800469e8  mov     [rsp+50h+var_30], rax
0x1800469ed  call    cs:__imp_PuDbgPrint
0x1800469f3  mov     rcx, [rbp+arg_18]
0x1800469f7  lea     r15, [r14+6Ch]
0x1800469fb  lea     r9, [rbp+arg_8]
0x1800469ff  mov     [rsp+50h+var_30], r12
0x180046a04  mov     r8, r15
0x180046a07  lea     rdx, aRequests; "requests"
0x180046a0e  mov     rax, [rcx]
0x180046a11  mov     rax, [rax+30h]
0x180046a15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046a1a  mov     ebx, eax
0x180046a1c  test    eax, eax
0x180046a1e  jns     short loc_180046A3F
0x180046a20  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180046a27  jz      loc_180046C34
0x180046a2d  lea     rax, aFailedReadingP_1; " Failed reading property \n"
0x180046a34  mov     r8d, 996h
0x180046a3a  jmp     loc_18004694E
0x180046a3f  mov     r9, [rbp+arg_8]; struct INativePropertyException *
0x180046a43  test    r9, r9
0x180046a46  jz      short loc_180046A8F
0x180046a48  mov     r8d, [r15]; int
0x180046a4b  lea     rdx, aRequests; "requests"
0x180046a52  lea     rcx, [rbp+arg_10]; struct CONFIG_ERROR **
0x180046a56  call    ?CreateAndInitWithLong@CONFIG_ERROR@@SAXPEAPEAV1@PEBGJPEAVINativePropertyException@@@Z; CONFIG_ERROR::CreateAndInitWithLong(CONFIG_ERROR * *,ushort const *,long,INativePropertyException *)
0x180046a5b  mov     rdx, [rbp+arg_10]; struct CONFIG_ERROR *
0x180046a5f  test    rdx, rdx
0x180046a62  jz      short loc_180046A77
0x180046a64  lea     rcx, [r14+3E8h]; this
0x180046a6b  mov     dword ptr [rdx+8], 2
0x180046a72  call    ?Add@CONFIG_ERROR_LIST@@QEAAXPEAVCONFIG_ERROR@@@Z; CONFIG_ERROR_LIST::Add(CONFIG_ERROR *)
0x180046a77  mov     rcx, [rbp+arg_8]
0x180046a7b  mov     [rbp+arg_10], r12
0x180046a7f  mov     rax, [rcx]
0x180046a82  mov     rax, [rax+10h]
0x180046a86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046a8b  mov     [rbp+arg_8], r12
0x180046a8f  mov     eax, cs:g_dwDebugFlags
0x180046a95  test    al, 3
0x180046a97  setnz   cl
0x180046a9a  bt      eax, 1Eh
0x180046a9e  setb    al
0x180046aa1  test    al, cl
0x180046aa3  jz      short loc_180046AD5
0x180046aa5  mov     eax, [r15]
0x180046aa8  mov     r9, rdi
0x180046aab  mov     rcx, cs:g_pDebug
0x180046ab2  mov     r8d, 9ACh
0x180046ab8  mov     [rsp+50h+var_20], eax
0x180046abc  mov     rdx, rsi
0x180046abf  mov     dword ptr [rsp+50h+var_28], eax
0x180046ac3  lea     rax, aRestartRequest; " Restart Requests = %u (0x%X) \n"
0x180046aca  mov     [rsp+50h+var_30], rax
0x180046acf  call    cs:__imp_PuDbgPrint
0x180046ad5  mov     rcx, [rbp+arg_18]
0x180046ad9  lea     r9, [rbp+arg_8]
0x180046add  lea     r8, [rbp+var_10]
0x180046ae1  mov     [rsp+50h+var_30], r12
0x180046ae6  lea     rdx, aTime; "time"
0x180046aed  mov     rax, [rcx]
0x180046af0  mov     rax, [rax+50h]
0x180046af4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046af9  mov     ebx, eax
0x180046afb  test    eax, eax
0x180046afd  jns     short loc_180046B1E
0x180046aff  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180046b06  jz      loc_180046C34
0x180046b0c  lea     rax, aFailedReadingP_1; " Failed reading property \n"
0x180046b13  mov     r8d, 9B7h
0x180046b19  jmp     loc_18004694E
0x180046b1e  mov     r8, [rbp+var_10]; __int64
0x180046b22  mov     rax, 0D6BF94D5E57A42BDh
0x180046b2c  mov     r9, [rbp+arg_8]; struct INativePropertyException *
0x180046b30  imul    r8
0x180046b33  lea     rcx, [r8+rdx]
0x180046b37  sar     rcx, 17h
0x180046b3b  mov     rax, rcx
0x180046b3e  shr     rax, 3Fh
0x180046b42  add     rcx, rax
0x180046b45  mov     rax, 8888888888888889h
0x180046b4f  imul    rcx
0x180046b52  add     rdx, rcx
0x180046b55  sar     rdx, 5
0x180046b59  mov     rax, rdx
0x180046b5c  shr     rax, 3Fh
0x180046b60  add     rdx, rax
0x180046b63  mov     [r14+68h], edx
0x180046b67  test    r9, r9
0x180046b6a  jz      short loc_180046BAC
0x180046b6c  lea     rdx, aTime; "time"
0x180046b73  lea     rcx, [rbp+arg_10]; struct CONFIG_ERROR **
0x180046b77  call    ?CreateAndInitWithRawTimeSpan@CONFIG_ERROR@@SAXPEAPEAV1@PEBG_JPEAVINativePropertyException@@@Z; CONFIG_ERROR::CreateAndInitWithRawTimeSpan(CONFIG_ERROR * *,ushort const *,__int64,INativePropertyException *)
0x180046b7c  mov     rdx, [rbp+arg_10]; struct CONFIG_ERROR *
0x180046b80  test    rdx, rdx
0x180046b83  jz      short loc_180046B98
0x180046b85  lea     rcx, [r14+3E8h]; this
0x180046b8c  mov     dword ptr [rdx+8], 1
0x180046b93  call    ?Add@CONFIG_ERROR_LIST@@QEAAXPEAVCONFIG_ERROR@@@Z; CONFIG_ERROR_LIST::Add(CONFIG_ERROR *)
0x180046b98  mov     rcx, [rbp+arg_8]
0x180046b9c  mov     rax, [rcx]
0x180046b9f  mov     rax, [rax+10h]
0x180046ba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046ba8  mov     [rbp+arg_8], r12
0x180046bac  mov     eax, cs:g_dwDebugFlags
0x180046bb2  test    al, 3
0x180046bb4  setnz   cl
0x180046bb7  bt      eax, 1Eh
0x180046bbb  setb    al
0x180046bbe  test    al, cl
0x180046bc0  jz      short loc_180046BF3
0x180046bc2  mov     eax, [r14+68h]
0x180046bc6  mov     r9, rdi
0x180046bc9  mov     rcx, cs:g_pDebug
0x180046bd0  mov     r8d, 9CEh
0x180046bd6  mov     [rsp+50h+var_20], eax
0x180046bda  mov     rdx, rsi
0x180046bdd  mov     dword ptr [rsp+50h+var_28], eax
0x180046be1  lea     rax, aPeriodicRestar_0; " Periodic Restart Time conversion = %u "...
0x180046be8  mov     [rsp+50h+var_30], rax
0x180046bed  call    cs:__imp_PuDbgPrint
0x180046bf3  mov     rdx, [rbp+arg_18]; struct INativeConfigurationElement *
0x180046bf7  mov     rcx, r14; this
0x180046bfa  call    ?SetRestartSchedule@APP_POOL_DATA_OBJECT_CS@@AEAAJPEAVINativeConfigurationElement@@@Z; APP_POOL_DATA_OBJECT_CS::SetRestartSchedule(INativeConfigurationElement *)
0x180046bff  mov     ebx, eax
0x180046c01  test    eax, eax
0x180046c03  jns     short loc_180046C20
0x180046c05  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180046c0c  jz      short loc_180046C34
0x180046c0e  lea     rax, aFailedSettingU_1; " Failed setting up Restart Schedule\n"
0x180046c15  mov     r8d, 9D6h
0x180046c1b  jmp     loc_18004694E
0x180046c20  mov     rcx, [rbp+arg_18]
0x180046c24  mov     rax, [rcx]
0x180046c27  mov     rax, [rax+10h]
0x180046c2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046c30  mov     [rbp+arg_18], r12
0x180046c34  mov     rcx, [rbp+arg_8]
0x180046c38  test    rcx, rcx
0x180046c3b  jz      short loc_180046C4D
0x180046c3d  mov     rax, [rcx]
0x180046c40  mov     rax, [rax+10h]
0x180046c44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046c49  mov     [rbp+arg_8], r12
0x180046c4d  mov     rcx, [rbp+arg_18]
0x180046c51  test    rcx, rcx
0x180046c54  jz      short loc_180046C62
0x180046c56  mov     rax, [rcx]
0x180046c59  mov     rax, [rax+10h]
0x180046c5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046c62  mov     eax, ebx
0x180046c64  add     rsp, 50h
0x180046c68  pop     r15
0x180046c6a  pop     r14
  ... truncated ...
```
