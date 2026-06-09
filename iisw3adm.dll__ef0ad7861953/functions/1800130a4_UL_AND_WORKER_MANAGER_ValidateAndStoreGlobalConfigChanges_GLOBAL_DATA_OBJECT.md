# UL_AND_WORKER_MANAGER::ValidateAndStoreGlobalConfigChanges(GLOBAL_DATA_OBJECT *)

- ea: `0x1800130a4`
- end: `0x1800133fe`
- name: `?ValidateAndStoreGlobalConfigChanges@UL_AND_WORKER_MANAGER@@AEAAXPEAVGLOBAL_DATA_OBJECT@@@Z`
- size: `858`
- prototype: `void __fastcall(UL_AND_WORKER_MANAGER *__hidden this, struct GLOBAL_DATA_OBJECT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001188c`

## callees

- `0x180001234`
- `0x1800130a4`
- `0x180013404`
- `0x18003da9c`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x1800131aa`
- `iisutil!PuDbgPrint` at `0x18001327a`
- `iisutil!PuDbgPrint` at `0x1800133ce`
- `iisutil!PuDbgPrint` at `0x1800131aa`
- `iisutil!PuDbgPrint` at `0x18001327a`
- `iisutil!PuDbgPrint` at `0x1800133ce`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800130eb`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800130f5`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800130eb`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800130f5`

## string_xrefs

- `0x180013192`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`
- `0x180013273`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`
- `0x1800133a9`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`
- `0x18001319e`: `Configuring control channel for logging in UTF8 %S\n`
- `0x180013184`: `UL_AND_WORKER_MANAGER::ValidateAndStoreGlobalConfigChanges`
- `0x180013261`: `UL_AND_WORKER_MANAGER::ValidateAndStoreGlobalConfigChanges`
- `0x18001339b`: `UL_AND_WORKER_MANAGER::ValidateAndStoreGlobalConfigChanges`
- `0x180013256`: `Configuring control channel MaxBandwidth to %u\n`
- `0x1800133be`: `Configuring control channel ConnectionInfo\n       ConnectionTimeout = %u\n       HeaderWaitTimeout = %u\n       MinFileBytesSec = %u\n`

## pseudocode

```c
void __fastcall UL_AND_WORKER_MANAGER::ValidateAndStoreGlobalConfigChanges(
        UL_AND_WORKER_MANAGER *this,
        struct GLOBAL_DATA_OBJECT *a2)
{
  char *v2; // r14
  _QWORD *v5; // rax
  _QWORD *v6; // rbx
  WMS_ERROR_LOGGER **v7; // rbx
  WMS_ERROR_LOGGER *v8; // rcx
  const wchar_t *v9; // rax
  _QWORD **v10; // rbx
  int v11; // esi
  _QWORD *i; // rax
  __int64 v13; // rdx
  const unsigned __int16 *v14; // r8
  unsigned int v15; // ebp
  _QWORD *j; // rax
  __int64 v17; // rdx
  const unsigned __int16 *v18; // r8
  unsigned int v19; // esi
  _QWORD *k; // rax
  __int64 v21; // rdx
  const unsigned __int16 *v22; // r8
  unsigned __int16 *v23; // [rsp+30h] [rbp-58h]
  unsigned __int16 *v24; // [rsp+30h] [rbp-58h]
  unsigned __int16 *v25; // [rsp+30h] [rbp-58h]
  int v26; // [rsp+38h] [rbp-50h]

  v2 = (char *)this + 440;
  if ( *((_QWORD *)this + 55) )
  {
    v7 = (WMS_ERROR_LOGGER **)((char *)this + 440);
  }
  else
  {
    v5 = operator new(0xB0u);
    v6 = v5;
    if ( v5 )
    {
      *v5 = 0;
      v5[1] = 0;
      v5[2] = 0;
      STRU::STRU((STRU *)(v5 + 3));
      STRU::STRU((STRU *)(v6 + 10));
      v6[17] = 0;
      v6[18] = 0;
      v6[19] = 0;
      v6[20] = 0;
      *((_DWORD *)v6 + 42) = 0;
    }
    else
    {
      v6 = 0;
    }
    *(_QWORD *)v2 = v6;
    if ( !v6 )
      return;
    v7 = (WMS_ERROR_LOGGER **)((char *)this + 440);
  }
  UL_AND_WORKER_MANAGER::ValidateAndStoreLoggingConfigChanges(this, a2);
  if ( (*((_BYTE *)a2 + 240) & 0x10) != 0 )
  {
    if ( (g_dwDebugFlags & 0x50000) != 0 && (g_dwDebugFlags & 3) != 0 )
    {
      v9 = L"TRUE";
      if ( !*((_DWORD *)a2 + 19) )
        v9 = L"FALSE";
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
        2217,
        "UL_AND_WORKER_MANAGER::ValidateAndStoreGlobalConfigChanges",
        "Configuring control channel for logging in UTF8 %S\n",
        v9);
    }
    v8 = *v7;
    *(_DWORD *)*v7 = *((_DWORD *)a2 + 19);
  }
  v10 = (_QWORD **)((char *)a2 + 224);
  if ( (*((_BYTE *)a2 + 240) & 1) != 0 )
  {
    v11 = *((_DWORD *)a2 + 10);
    for ( i = *v10; i != v10; i = (_QWORD *)*i )
    {
      v13 = *(i - 1);
      if ( *(_DWORD *)(v13 + 8) == 53 )
      {
        if ( v13 )
        {
          v14 = *(const unsigned __int16 **)(v13 + 160);
          v23 = *(unsigned __int16 **)(v13 + 104);
          if ( *(_DWORD *)(v13 + 192) == 2 )
            WMS_ERROR_LOGGER::LogRangeGlobal(
              *(WMS_ERROR_LOGGER **)(v13 + 184),
              *(const unsigned __int16 **)(v13 + 48),
              v14,
              1,
              **(_DWORD **)(v13 + 184),
              *(_DWORD *)(*(_QWORD *)(v13 + 184) + 8LL),
              v23,
              v26);
          else
            WMS_ERROR_LOGGER::LogRangeGlobal(v8, *(const unsigned __int16 **)(v13 + 48), v14, 0, 0, 0, v23, v26);
          v11 = -1;
        }
        break;
      }
    }
    LOBYTE(v8) = (g_dwDebugFlags & 0x50000) != 0;
    if ( ((unsigned __int8)v8 & ((g_dwDebugFlags & 3) != 0)) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
        2280,
        "UL_AND_WORKER_MANAGER::ValidateAndStoreGlobalConfigChanges",
        "Configuring control channel MaxBandwidth to %u\n",
        v11);
    *(_DWORD *)(*(_QWORD *)v2 + 4LL) = v11;
  }
  if ( (*((_BYTE *)a2 + 240) & 0xE) != 0 )
  {
    v15 = *((_DWORD *)a2 + 11);
    for ( j = *v10; j != v10; j = (_QWORD *)*j )
    {
      v17 = *(j - 1);
      if ( *(_DWORD *)(v17 + 8) == 54 )
        goto LABEL_34;
    }
    v17 = 0;
LABEL_34:
    if ( v15 > 0xFFFF )
      v15 = 0xFFFF;
    if ( v17 )
    {
      v18 = *(const unsigned __int16 **)(v17 + 160);
      v24 = *(unsigned __int16 **)(v17 + 104);
      if ( *(_DWORD *)(v17 + 192) == 2 )
        WMS_ERROR_LOGGER::LogRangeGlobal(
          *(WMS_ERROR_LOGGER **)(v17 + 184),
          *(const unsigned __int16 **)(v17 + 48),
          v18,
          1,
          **(_DWORD **)(v17 + 184),
          *(_DWORD *)(*(_QWORD *)(v17 + 184) + 8LL),
          v24,
          v26);
      else
        WMS_ERROR_LOGGER::LogRangeGlobal(v8, *(const unsigned __int16 **)(v17 + 48), v18, 0, 0, 0, v24, v26);
    }
    v19 = *((_DWORD *)a2 + 12);
    for ( k = *v10; k != v10; k = (_QWORD *)*k )
    {
      v21 = *(k - 1);
      if ( *(_DWORD *)(v21 + 8) == 55 )
        goto LABEL_45;
    }
    v21 = 0;
LABEL_45:
    if ( v19 > 0xFFFF )
      v19 = 0xFFFF;
    if ( v21 )
    {
      v22 = *(const unsigned __int16 **)(v21 + 160);
      v25 = *(unsigned __int16 **)(v21 + 104);
      if ( *(_DWORD *)(v21 + 192) == 2 )
        WMS_ERROR_LOGGER::LogRangeGlobal(
          *(WMS_ERROR_LOGGER **)(v21 + 184),
          *(const unsigned __int16 **)(v21 + 48),
          v22,
          1,
          **(_DWORD **)(v21 + 184),
          *(_DWORD *)(*(_QWORD *)(v21 + 184) + 8LL),
          v25,
          v26);
      else
        WMS_ERROR_LOGGER::LogRangeGlobal(v8, *(const unsigned __int16 **)(v21 + 48), v22, 0, 0, 0, v25, v26);
    }
    if ( (g_dwDebugFlags & 0x50000) != 0 && (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
        2395,
        "UL_AND_WORKER_MANAGER::ValidateAndStoreGlobalConfigChanges",
        "Configuring control channel ConnectionInfo\n"
        "       ConnectionTimeout = %u\n"
        "       HeaderWaitTimeout = %u\n"
        "       MinFileBytesSec = %u\n",
        v15,
        v19,
        *((_DWORD *)a2 + 13));
    *(_DWORD *)(*(_QWORD *)v2 + 8LL) = v15;
    *(_DWORD *)(*(_QWORD *)v2 + 12LL) = v19;
    *(_DWORD *)(*((_QWORD *)this + 55) + 16LL) = *((_DWORD *)a2 + 13);
  }
}

```

## disassembly

```asm
0x1800130a4  push    rbx
0x1800130a6  push    rbp
0x1800130a7  push    rsi
0x1800130a8  push    rdi
0x1800130a9  push    r12
0x1800130ab  push    r13
0x1800130ad  push    r14
0x1800130af  push    r15
0x1800130b1  sub     rsp, 48h
0x1800130b5  lea     r14, [rcx+1B8h]
0x1800130bc  xor     r12d, r12d
0x1800130bf  mov     rdi, rdx
0x1800130c2  mov     r15, rcx
0x1800130c5  cmp     [r14], r12
0x1800130c8  jnz     short loc_180013138
0x1800130ca  mov     ecx, 0B0h; Size
0x1800130cf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800130d4  mov     rbx, rax
0x1800130d7  test    rax, rax
0x1800130da  jz      short loc_180013120
0x1800130dc  lea     rcx, [rax+18h]
0x1800130e0  mov     [rax], r12
0x1800130e3  mov     [rax+8], r12
0x1800130e7  mov     [rax+10h], r12
0x1800130eb  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800130f1  lea     rcx, [rbx+50h]
0x1800130f5  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800130fb  mov     [rbx+88h], r12
0x180013102  mov     [rbx+90h], r12
0x180013109  mov     [rbx+98h], r12
0x180013110  mov     [rbx+0A0h], r12
0x180013117  mov     [rbx+0A8h], r12d
0x18001311e  jmp     short loc_180013123
0x180013120  mov     rbx, r12
0x180013123  mov     [r14], rbx
0x180013126  test    rbx, rbx
0x180013129  jz      loc_1800133ED
0x18001312f  lea     rbx, [r15+1B8h]
0x180013136  jmp     short loc_18001313B
0x180013138  mov     rbx, r14
0x18001313b  mov     rdx, rdi; struct GLOBAL_DATA_OBJECT *
0x18001313e  mov     rcx, r15; this
0x180013141  call    ?ValidateAndStoreLoggingConfigChanges@UL_AND_WORKER_MANAGER@@AEAAXPEAVGLOBAL_DATA_OBJECT@@@Z; UL_AND_WORKER_MANAGER::ValidateAndStoreLoggingConfigChanges(GLOBAL_DATA_OBJECT *)
0x180013146  test    byte ptr [rdi+0F0h], 10h
0x18001314d  mov     ebp, 50000h
0x180013152  jz      short loc_1800131B8
0x180013154  mov     eax, cs:g_dwDebugFlags
0x18001315a  test    ebp, eax
0x18001315c  setnz   cl
0x18001315f  test    al, 3
0x180013161  setnz   al
0x180013164  test    al, cl
0x180013166  jz      short loc_1800131B0
0x180013168  cmp     [rdi+4Ch], r12d
0x18001316c  lea     rcx, aFalse_1; "FALSE"
0x180013173  lea     rax, aTrue_1; "TRUE"
0x18001317a  mov     r8d, 8A9h
0x180013180  cmovz   rax, rcx
0x180013184  lea     r9, aUlAndWorkerMan_8; "UL_AND_WORKER_MANAGER::ValidateAndStore"...
0x18001318b  mov     rcx, cs:g_pDebug
0x180013192  lea     rdx, aServercommonIn_68; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180013199  mov     qword ptr [rsp+88h+var_60], rax
0x18001319e  lea     rax, aConfiguringCon; "Configuring control channel for logging"...
0x1800131a5  mov     qword ptr [rsp+88h+Value], rax
0x1800131aa  call    cs:__imp_PuDbgPrint
0x1800131b0  mov     rcx, [rbx]
0x1800131b3  mov     eax, [rdi+4Ch]
0x1800131b6  mov     [rcx], eax
0x1800131b8  test    byte ptr [rdi+0F0h], 1
0x1800131bf  lea     rbx, [rdi+0E0h]
0x1800131c6  jz      loc_180013286
0x1800131cc  mov     esi, [rdi+28h]
0x1800131cf  mov     rax, [rbx]
0x1800131d2  jmp     short loc_1800131E1
0x1800131d4  mov     rdx, [rax-8]
0x1800131d8  cmp     dword ptr [rdx+8], 35h ; '5'
0x1800131dc  jz      short loc_1800131E8
0x1800131de  mov     rax, [rax]
0x1800131e1  cmp     rax, rbx
0x1800131e4  jnz     short loc_1800131D4
0x1800131e6  jmp     short loc_18001323B
0x1800131e8  test    rdx, rdx
0x1800131eb  jz      short loc_18001323B
0x1800131ed  cmp     dword ptr [rdx+0C0h], 2
0x1800131f4  mov     rax, [rdx+68h]
0x1800131f8  mov     r8, [rdx+0A0h]; unsigned __int16 *
0x1800131ff  mov     [rsp+88h+var_58], rax; unsigned __int16 *
0x180013204  jnz     short loc_180013222
0x180013206  mov     rcx, [rdx+0B8h]; this
0x18001320d  mov     r9d, 1
0x180013213  mov     eax, [rcx+8]
0x180013216  mov     [rsp+88h+var_60], eax
0x18001321a  mov     eax, [rcx]
0x18001321c  mov     [rsp+88h+Value], eax
0x180013220  jmp     short loc_18001322F
0x180013222  mov     [rsp+88h+var_60], r12d; unsigned int
0x180013227  xor     r9d, r9d; int
0x18001322a  mov     [rsp+88h+Value], r12d; Value
0x18001322f  mov     rdx, [rdx+30h]; unsigned __int16 *
0x180013233  call    ?LogRangeGlobal@WMS_ERROR_LOGGER@@QEAAXPEBG0HKK0H@Z; WMS_ERROR_LOGGER::LogRangeGlobal(ushort const *,ushort const *,int,ulong,ulong,ushort const *,int)
0x180013238  or      esi, 0FFFFFFFFh
0x18001323b  mov     eax, cs:g_dwDebugFlags
0x180013241  test    ebp, eax
0x180013243  setnz   cl
0x180013246  test    al, 3
0x180013248  setnz   al
0x18001324b  test    al, cl
0x18001324d  jz      short loc_180013280
0x18001324f  mov     rcx, cs:g_pDebug
0x180013256  lea     rax, aConfiguringCon_2; "Configuring control channel MaxBandwidt"...
0x18001325d  mov     [rsp+88h+var_60], esi
0x180013261  lea     r9, aUlAndWorkerMan_8; "UL_AND_WORKER_MANAGER::ValidateAndStore"...
0x180013268  mov     r8d, 8E8h
0x18001326e  mov     qword ptr [rsp+88h+Value], rax
0x180013273  lea     rdx, aServercommonIn_68; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001327a  call    cs:__imp_PuDbgPrint
0x180013280  mov     rax, [r14]
0x180013283  mov     [rax+4], esi
0x180013286  test    byte ptr [rdi+0F0h], 0Eh
0x18001328d  jz      loc_1800133ED
0x180013293  mov     ebp, [rdi+2Ch]
0x180013296  mov     rax, [rbx]
0x180013299  jmp     short loc_1800132A8
0x18001329b  mov     rdx, [rax-8]
0x18001329f  cmp     dword ptr [rdx+8], 36h ; '6'
0x1800132a3  jz      short loc_1800132B0
0x1800132a5  mov     rax, [rax]
0x1800132a8  cmp     rax, rbx
0x1800132ab  jnz     short loc_18001329B
0x1800132ad  mov     rdx, r12
0x1800132b0  mov     r13d, 0FFFFh
0x1800132b6  cmp     ebp, r13d
0x1800132b9  cmova   ebp, r13d
0x1800132bd  test    rdx, rdx
0x1800132c0  jz      short loc_18001330D
0x1800132c2  cmp     dword ptr [rdx+0C0h], 2
0x1800132c9  mov     rax, [rdx+68h]
0x1800132cd  mov     r8, [rdx+0A0h]; unsigned __int16 *
0x1800132d4  mov     [rsp+88h+var_58], rax; unsigned __int16 *
0x1800132d9  jnz     short loc_1800132F7
0x1800132db  mov     rcx, [rdx+0B8h]; this
0x1800132e2  mov     r9d, 1
0x1800132e8  mov     eax, [rcx+8]
0x1800132eb  mov     [rsp+88h+var_60], eax
0x1800132ef  mov     eax, [rcx]
0x1800132f1  mov     [rsp+88h+Value], eax
0x1800132f5  jmp     short loc_180013304
0x1800132f7  mov     [rsp+88h+var_60], r12d; unsigned int
0x1800132fc  xor     r9d, r9d; int
0x1800132ff  mov     [rsp+88h+Value], r12d; Value
0x180013304  mov     rdx, [rdx+30h]; unsigned __int16 *
0x180013308  call    ?LogRangeGlobal@WMS_ERROR_LOGGER@@QEAAXPEBG0HKK0H@Z; WMS_ERROR_LOGGER::LogRangeGlobal(ushort const *,ushort const *,int,ulong,ulong,ushort const *,int)
0x18001330d  mov     esi, [rdi+30h]
0x180013310  mov     rax, [rbx]
0x180013313  jmp     short loc_180013322
0x180013315  mov     rdx, [rax-8]
0x180013319  cmp     dword ptr [rdx+8], 37h ; '7'
0x18001331d  jz      short loc_18001332A
0x18001331f  mov     rax, [rax]
0x180013322  cmp     rax, rbx
0x180013325  jnz     short loc_180013315
0x180013327  mov     rdx, r12
0x18001332a  cmp     esi, r13d
0x18001332d  cmova   esi, r13d
0x180013331  test    rdx, rdx
0x180013334  jz      short loc_180013381
0x180013336  cmp     dword ptr [rdx+0C0h], 2
0x18001333d  mov     rax, [rdx+68h]
0x180013341  mov     r8, [rdx+0A0h]; unsigned __int16 *
0x180013348  mov     [rsp+88h+var_58], rax; unsigned __int16 *
0x18001334d  jnz     short loc_18001336B
0x18001334f  mov     rcx, [rdx+0B8h]; this
0x180013356  mov     r9d, 1
0x18001335c  mov     eax, [rcx+8]
0x18001335f  mov     [rsp+88h+var_60], eax
0x180013363  mov     eax, [rcx]
0x180013365  mov     [rsp+88h+Value], eax
0x180013369  jmp     short loc_180013378
0x18001336b  mov     [rsp+88h+var_60], r12d; unsigned int
0x180013370  xor     r9d, r9d; int
0x180013373  mov     [rsp+88h+Value], r12d; Value
0x180013378  mov     rdx, [rdx+30h]; unsigned __int16 *
0x18001337c  call    ?LogRangeGlobal@WMS_ERROR_LOGGER@@QEAAXPEBG0HKK0H@Z; WMS_ERROR_LOGGER::LogRangeGlobal(ushort const *,ushort const *,int,ulong,ulong,ushort const *,int)
0x180013381  mov     eax, cs:g_dwDebugFlags
0x180013387  test    eax, 50000h
0x18001338c  setnz   cl
0x18001338f  test    al, 3
0x180013391  setnz   al
0x180013394  test    al, cl
0x180013396  jz      short loc_1800133D4
0x180013398  mov     eax, [rdi+34h]
0x18001339b  lea     r9, aUlAndWorkerMan_8; "UL_AND_WORKER_MANAGER::ValidateAndStore"...
0x1800133a2  mov     rcx, cs:g_pDebug
0x1800133a9  lea     rdx, aServercommonIn_68; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800133b0  mov     [rsp+88h+var_50], eax
0x1800133b4  mov     r8d, 95Bh
0x1800133ba  mov     dword ptr [rsp+88h+var_58], esi
0x1800133be  lea     rax, aConfiguringCon_0; "Configuring control channel ConnectionI"...
0x1800133c5  mov     [rsp+88h+var_60], ebp
0x1800133c9  mov     qword ptr [rsp+88h+Value], rax
0x1800133ce  call    cs:__imp_PuDbgPrint
0x1800133d4  mov     rax, [r14]
0x1800133d7  mov     [rax+8], ebp
0x1800133da  mov     rax, [r14]
0x1800133dd  mov     [rax+0Ch], esi
0x1800133e0  mov     rcx, [r15+1B8h]
0x1800133e7  mov     eax, [rdi+34h]
0x1800133ea  mov     [rcx+10h], eax
0x1800133ed  add     rsp, 48h
0x1800133f1  pop     r15
0x1800133f3  pop     r14
0x1800133f5  pop     r13
0x1800133f7  pop     r12
0x1800133f9  pop     rdi
0x1800133fa  pop     rsi
0x1800133fb  pop     rbp
0x1800133fc  pop     rbx
0x1800133fd  retn
```
