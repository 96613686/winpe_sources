# DsrCmdTaskSchedulerHelper::RunTask(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ushort const *,ushort const *,ushort const *)

- ea: `0x180033984`
- end: `0x18003411a`
- name: `?RunTask@DsrCmdTaskSchedulerHelper@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0PEBG11@Z`
- size: `1942`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18009b940`
- `0x1800a523c`

## callees

- `0x18000bac0`
- `0x180012c7c`
- `0x180016ae0`
- `0x1800292ac`
- `0x180029554`
- `0x18002b9b4`
- `0x180031a20`
- `0x180033984`
- `0x180034120`
- `0x1800341d0`
- `0x180034280`
- `0x180044300`
- `0x180046ae8`
- `0x180046b3c`
- `0x180098664`
- `0x18009dcf0`
- `0x1800bf010`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@@Z` at `0x180033fab`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@@Z` at `0x180033fab`
- `msvcp_win!?good@ios_base@std@@QEBA_NXZ` at `0x180033f14`
- `msvcp_win!?good@ios_base@std@@QEBA_NXZ` at `0x180033f14`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180033bb7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180033bb7`

## string_xrefs

- `0x180033c33`: `Scheduled %s failed. Exiting...\n`
- `0x180033c53`: `Scheduled %s failed. Exiting...\n`
- `0x180033daf`: `Failed to get %s last task result. Error: 0x%08x\n`
- `0x180033df7`: `Failed to get %s last task result. Error: 0x%08x\n`
- `0x180033e1c`: `Failed to get %s last task result. Error: 0x%08x\n`
- `0x1800340be`: `Another instance of the %s is already running please retry after sometime. Exiting...\n`
- `0x1800340de`: `Another instance of the %s is already running please retry after sometime. Exiting...\n`
- `0x180033f57`: `Unable to read %s output data. Exiting...\n`
- `0x180033f77`: `Unable to read %s output data. Exiting...\n`
- `0x180033caf`: `Scheduled %s did not complete in a reasonable amount of time. Check the file %s for more information. Exiting...\n`
- `0x180033cdc`: `Scheduled %s did not complete in a reasonable amount of time. Check the file %s for more information. Exiting...\n`
- `0x180033b80`: `Waiting for %s to complete. This could take a few minutes...`
- `0x180033d13`: `Could not stop scheduled task: 0x%08x\n`
- `0x180033d49`: `Could not stop scheduled task: 0x%08x\n`

## pseudocode

```c
__int64 __fastcall DsrCmdTaskSchedulerHelper::RunTask(
        _QWORD *a1,
        _QWORD *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  _QWORD *v8; // rbx
  const unsigned __int16 *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  unsigned int ScheduledTask; // edi
  _QWORD *v13; // rax
  __int64 v14; // rdx
  _QWORD *v15; // rax
  __int64 v16; // rdx
  _QWORD *v17; // rsi
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  _QWORD *v21; // rax
  __int64 v22; // rdx
  _QWORD *v23; // rax
  __int64 v24; // rdx
  _QWORD *v25; // rsi
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rcx
  _QWORD *v29; // rax
  __int64 v30; // rdx
  _QWORD *v31; // rax
  __int64 v32; // rdx
  _QWORD *v33; // rsi
  __int64 v34; // rax
  _QWORD *v35; // rdx
  int v36; // eax
  int v37; // edi
  __int64 v38; // rdx
  __int64 v39; // rcx
  _QWORD *v40; // rax
  __int64 v41; // rdx
  _QWORD *v42; // rax
  __int64 v43; // rdx
  _QWORD *v44; // rdi
  __int64 v45; // rax
  _QWORD *v46; // rax
  __int64 v47; // rdx
  _QWORD *v48; // rax
  __int64 v49; // rdx
  _QWORD *v50; // r14
  _QWORD *v51; // rdi
  __int64 v52; // rax
  __int64 v53; // rdx
  __int64 v54; // rcx
  int v55; // ebx
  __int64 v56; // rdx
  __int64 v57; // rcx
  _QWORD *v58; // rax
  __int64 v59; // rdx
  _QWORD *v60; // rax
  __int64 v61; // rdx
  __int64 v62; // rax
  __int64 v63; // rdx
  __int64 v64; // rcx
  _QWORD *v65; // rdx
  __int64 v66; // rdx
  __int64 v67; // rcx
  _QWORD *v68; // rax
  __int64 v69; // rdx
  _QWORD *v70; // rax
  __int64 v71; // rdx
  _QWORD *v72; // r14
  __int64 v73; // rax
  _QWORD *v74; // rdx
  _QWORD *v75; // rdx
  __int64 v76; // rdx
  __int64 v77; // rcx
  _QWORD *CurrentRef; // rax
  __int64 v79; // rdx
  _QWORD *v80; // rax
  __int64 v81; // rdx
  unsigned int v82; // r15d
  _QWORD *v83; // r14
  __int64 v84; // rax
  _QWORD *v85; // rdx
  __int64 v86; // rdx
  __int64 v87; // rcx
  _QWORD *v88; // rax
  __int64 v89; // rdx
  _QWORD *v90; // rax
  __int64 v91; // rdx
  _QWORD *v92; // rdi
  __int64 v93; // rax
  __int64 v94; // rcx
  __int64 v95; // rdx
  __int64 v96; // rcx
  _QWORD *v97; // rax
  __int64 v98; // rdx
  __int64 v99; // rdx
  __int64 v100; // rcx
  const wchar_t *v101; // rbx
  __int64 v102; // rax
  const wchar_t *v103; // rcx
  _QWORD *v104; // rax
  __int64 v105; // rdx
  _QWORD *v106; // rax
  __int64 v107; // rdx
  _QWORD *v108; // rsi
  __int64 v109; // rax
  _QWORD *v111; // rax
  __int64 v112; // rdx
  const std::exception *v113; // rdi
  __int64 v114; // rdx
  __int64 v115; // rcx
  __int64 v116; // r14
  _QWORD *v117; // rbx
  _QWORD *v118; // rsi
  __int64 v119; // rax
  __int64 v120; // rax
  __int64 v121; // [rsp+0h] [rbp-2B8h] BYREF
  int v122; // [rsp+20h] [rbp-298h] BYREF
  struct IRegisteredTask *v123; // [rsp+28h] [rbp-290h] BYREF
  int v124; // [rsp+30h] [rbp-288h] BYREF
  int v125; // [rsp+34h] [rbp-284h]
  int v126; // [rsp+38h] [rbp-280h] BYREF
  _QWORD *v127; // [rsp+40h] [rbp-278h]
  const std::exception *v128; // [rsp+48h] [rbp-270h] BYREF
  _QWORD v129[2]; // [rsp+50h] [rbp-268h] BYREF
  _BYTE v130[256]; // [rsp+60h] [rbp-258h] BYREF
  _BYTE v131[8]; // [rsp+160h] [rbp-158h] BYREF
  _BYTE v132[232]; // [rsp+168h] [rbp-150h] BYREF
  wchar_t *Format[3]; // [rsp+250h] [rbp-68h] BYREF
  unsigned __int64 v134; // [rsp+268h] [rbp-50h]

  v8 = a1;
  v127 = a1;
  v123 = 0;
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v123);
  ScheduledTask = ((int (__stdcall *)(const unsigned __int16 *, const unsigned __int16 *, struct IRegisteredTask **))GetScheduledTask)(
                    v9,
                    L"Automatic-Device-Join",
                    &v123);
  if ( (ScheduledTask & 0x80000000) == 0 )
  {
    v126 = 0;
    ScheduledTask = ((__int64 (__fastcall *)(struct IRegisteredTask *, int *))v123->lpVtbl->get_State)(v123, &v126);
    if ( (ScheduledTask & 0x80000000) == 0 )
    {
      if ( ((v126 - 2) & 0xFFFFFFFD) != 0 )
      {
        ScheduledTask = DsrCmdTaskSchedulerHelper::ScheduleTask(v123, a3, a4, a5);
        if ( (ScheduledTask & 0x80000000) == 0 )
        {
          if ( v8[3] <= 7u )
            v35 = v8;
          else
            v35 = (_QWORD *)*v8;
          wprintf(L"Waiting for %s to complete. This could take a few minutes...", v35);
          v36 = 4;
          v124 = 4;
          v37 = 0;
          while ( ((v36 - 2) & 0xFFFFFFFD) == 0 && v37 <= 120 )
          {
            ++v37;
            Sleep(0x3E8u);
            ((void (__fastcall *)(struct IRegisteredTask *, int *))v123->lpVtbl->get_State)(v123, &v124);
            v36 = v124;
          }
          wprintf(L"\r                                                                                             \r");
          if ( v124 == 3 )
          {
            v122 = 0;
            ScheduledTask = ((__int64 (__fastcall *)(struct IRegisteredTask *, int *))v123->lpVtbl->get_LastTaskResult)(
                              v123,
                              &v122);
            v125 = ScheduledTask;
            if ( (ScheduledTask & 0x80000000) == 0 )
            {
              if ( v122 < 0 )
              {
                if ( **(_BYTE **)CmdOptions::GetCurrentRef(v64, v63) )
                {
                  v75 = v8[3] <= 7u ? v8 : (_QWORD *)*v8;
                  wprintf(L"%s failed. Error: 0x%08x\n", v75, (unsigned int)v122);
                  CurrentRef = (_QWORD *)CmdOptions::GetCurrentRef(v77, v76);
                  if ( *(_BYTE *)(*CurrentRef + 12LL) )
                  {
                    v80 = (_QWORD *)CmdOptions::GetCurrentRef(*CurrentRef, v79);
                    if ( *(_QWORD *)(*v80 + 184LL) )
                    {
                      v82 = v122;
                      if ( v8[3] <= 7u )
                        v83 = v8;
                      else
                        v83 = (_QWORD *)*v8;
                      v84 = CmdOptions::GetCurrentRef(*v80, v81);
                      fwprintf_s(*(FILE *const *)(*(_QWORD *)v84 + 184LL), L"%s failed. Error: 0x%08x\n", v83, v82);
                    }
                  }
                }
                if ( v8[3] <= 7u )
                  v85 = v8;
                else
                  v85 = (_QWORD *)*v8;
                Logger::TraceVerbose((wchar_t *)L"%s failed. Error: 0x%08x\n", v85, (unsigned int)v122);
              }
            }
            else
            {
              if ( **(_BYTE **)CmdOptions::GetCurrentRef(v64, v63) )
              {
                v65 = v8[3] <= 7u ? v8 : (_QWORD *)*v8;
                wprintf(L"Failed to get %s last task result. Error: 0x%08x\n", v65, ScheduledTask);
                v68 = (_QWORD *)CmdOptions::GetCurrentRef(v67, v66);
                if ( *(_BYTE *)(*v68 + 12LL) )
                {
                  v70 = (_QWORD *)CmdOptions::GetCurrentRef(*v68, v69);
                  if ( *(_QWORD *)(*v70 + 184LL) )
                  {
                    if ( v8[3] <= 7u )
                      v72 = v8;
                    else
                      v72 = (_QWORD *)*v8;
                    v73 = CmdOptions::GetCurrentRef(*v70, v71);
                    fwprintf_s(
                      *(FILE *const *)(*(_QWORD *)v73 + 184LL),
                      L"Failed to get %s last task result. Error: 0x%08x\n",
                      v72,
                      ScheduledTask);
                  }
                }
              }
              if ( v8[3] <= 7u )
                v74 = v8;
              else
                v74 = (_QWORD *)*v8;
              Logger::TraceVerbose((wchar_t *)L"Failed to get %s last task result. Error: 0x%08x\n", v74, ScheduledTask);
              ScheduledTask = 0;
              v125 = 0;
            }
            std::basic_ifstream<unsigned short>::basic_ifstream<unsigned short>(v129);
            if ( __eh34_try(-1, 0) )
            {
              __eh34_scope_strut(0);
              if ( a2[3] > 7u )
                a2 = (_QWORD *)*a2;
              std::basic_ifstream<unsigned short>::open(v129, a2);
              if ( std::ios_base::good((std::ios_base *)((char *)v129 + *(int *)(v129[0] + 4LL))) )
              {
                std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>((__int64)v131);
                std::basic_ostream<unsigned short>::operator<<(v131, v130);
                v97 = (_QWORD *)CmdOptions::GetCurrentRef(v96, v95);
                if ( *(_BYTE *)(*v97 + 12LL) && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef(*v97, v98) + 184LL) )
                {
                  std::basic_stringbuf<unsigned short>::str(v132, Format);
                  v101 = (const wchar_t *)Format;
                  if ( v134 > 7 )
                    v101 = Format[0];
                  v102 = CmdOptions::GetCurrentRef(v100, v99);
                  fwprintf_s(*(FILE *const *)(*(_QWORD *)v102 + 184LL), v101);
                  std::wstring::_Tidy_deallocate((__int64)Format);
                }
                std::basic_stringbuf<unsigned short>::str(v132, Format);
                v103 = (const wchar_t *)Format;
                if ( v134 > 7 )
                  v103 = Format[0];
                wprintf(v103);
                std::wstring::_Tidy_deallocate((__int64)Format);
                std::basic_ostringstream<unsigned short>::`vbase destructor'((__int64)v131);
              }
              else
              {
                v88 = (_QWORD *)CmdOptions::GetCurrentRef(v87, v86);
                if ( *(_BYTE *)(*v88 + 12LL) )
                {
                  v90 = (_QWORD *)CmdOptions::GetCurrentRef(*v88, v89);
                  if ( *(_QWORD *)(*v90 + 184LL) )
                  {
                    if ( v8[3] <= 7u )
                      v92 = v8;
                    else
                      v92 = (_QWORD *)*v8;
                    v93 = CmdOptions::GetCurrentRef(*v90, v91);
                    fwprintf_s(
                      *(FILE *const *)(*(_QWORD *)v93 + 184LL),
                      L"Unable to read %s output data. Exiting...\n",
                      v92);
                  }
                }
                if ( v8[3] > 7u )
                  v8 = (_QWORD *)*v8;
                wprintf(L"Unable to read %s output data. Exiting...\n", v8);
                ScheduledTask = 1;
                v125 = 1;
              }
            }
            if ( __eh34_catch(0) )
            {
              if ( __eh34_catch_type(0, &std::exception `RTTI Type Descriptor', &v128) )
              {
                v111 = (_QWORD *)CmdOptions::GetCurrentRef(v94, &v121);
                if ( *(_BYTE *)(*v111 + 12LL) && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef(*v111, v112) + 184LL) )
                {
                  v113 = v128;
                  v116 = (*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v128 + 8LL))(v128);
                  v117 = v127;
                  v118 = v127;
                  if ( v127[3] > 7u )
                    v118 = (_QWORD *)*v127;
                  v119 = CmdOptions::GetCurrentRef(v115, v114);
                  fwprintf_s(
                    *(FILE *const *)(*(_QWORD *)v119 + 184LL),
                    L"Unable to read %s output data. Exception: %S. Exiting...\n",
                    v118,
                    v116);
                }
                else
                {
                  v113 = v128;
                  v117 = v127;
                }
                v120 = (*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v113 + 8LL))(v113);
                if ( v117[3] > 7u )
                  v117 = (_QWORD *)*v117;
                wprintf(L"Unable to read %s output data. Exception: %S. Exiting...\n", v117, v120);
                ScheduledTask = v125;
                __eh34_try_continuation(0, &std::exception `RTTI Type Descriptor', &loc_180034075);
              }
            }
            std::basic_ifstream<unsigned short>::`vbase destructor'(v129);
          }
          else
          {
            if ( ((v124 - 2) & 0xFFFFFFFD) != 0 )
            {
              v40 = (_QWORD *)CmdOptions::GetCurrentRef(v39, v38);
              if ( *(_BYTE *)(*v40 + 12LL) )
              {
                v42 = (_QWORD *)CmdOptions::GetCurrentRef(*v40, v41);
                if ( *(_QWORD *)(*v42 + 184LL) )
                {
                  if ( v8[3] <= 7u )
                    v44 = v8;
                  else
                    v44 = (_QWORD *)*v8;
                  v45 = CmdOptions::GetCurrentRef(*v42, v43);
                  fwprintf_s(*(FILE *const *)(*(_QWORD *)v45 + 184LL), L"Scheduled %s failed. Exiting...\n", v44);
                }
              }
              if ( v8[3] > 7u )
                v8 = (_QWORD *)*v8;
              wprintf(L"Scheduled %s failed. Exiting...\n", v8);
            }
            else
            {
              v46 = (_QWORD *)CmdOptions::GetCurrentRef(v39, v38);
              if ( *(_BYTE *)(*v46 + 12LL) )
              {
                v48 = (_QWORD *)CmdOptions::GetCurrentRef(*v46, v47);
                if ( *(_QWORD *)(*v48 + 184LL) )
                {
                  if ( a2[3] <= 7u )
                    v50 = a2;
                  else
                    v50 = (_QWORD *)*a2;
                  if ( v8[3] <= 7u )
                    v51 = v8;
                  else
                    v51 = (_QWORD *)*v8;
                  v52 = CmdOptions::GetCurrentRef(*v48, v49);
                  fwprintf_s(
                    *(FILE *const *)(*(_QWORD *)v52 + 184LL),
                    L"Scheduled %s did not complete in a reasonable amount of time. Check the file %s for more information. Exiting...\n",
                    v51,
                    v50);
                }
              }
              if ( a2[3] > 7u )
                a2 = (_QWORD *)*a2;
              if ( v8[3] > 7u )
                v8 = (_QWORD *)*v8;
              wprintf(
                L"Scheduled %s did not complete in a reasonable amount of time. Check the file %s for more information. Exiting...\n",
                v8,
                a2);
              v55 = ((__int64 (__fastcall *)(struct IRegisteredTask *, _QWORD))v123->lpVtbl->Stop)(v123, 0);
              if ( v55 < 0 )
              {
                if ( **(_BYTE **)CmdOptions::GetCurrentRef(v54, v53) )
                {
                  wprintf(L"Could not stop scheduled task: 0x%08x\n", (unsigned int)v55);
                  v58 = (_QWORD *)CmdOptions::GetCurrentRef(v57, v56);
                  if ( *(_BYTE *)(*v58 + 12LL) )
                  {
                    v60 = (_QWORD *)CmdOptions::GetCurrentRef(*v58, v59);
                    if ( *(_QWORD *)(*v60 + 184LL) )
                    {
                      v62 = CmdOptions::GetCurrentRef(*v60, v61);
                      fwprintf_s(
                        *(FILE *const *)(*(_QWORD *)v62 + 184LL),
                        L"Could not stop scheduled task: 0x%08x\n",
                        (unsigned int)v55);
                    }
                  }
                }
              }
            }
            ScheduledTask = 1;
          }
        }
        else
        {
          v29 = (_QWORD *)CmdOptions::GetCurrentRef(v28, v27);
          if ( *(_BYTE *)(*v29 + 12LL) )
          {
            v31 = (_QWORD *)CmdOptions::GetCurrentRef(*v29, v30);
            if ( *(_QWORD *)(*v31 + 184LL) )
            {
              if ( v8[3] <= 7u )
                v33 = v8;
              else
                v33 = (_QWORD *)*v8;
              v34 = CmdOptions::GetCurrentRef(*v31, v32);
              fwprintf_s(
                *(FILE *const *)(*(_QWORD *)v34 + 184LL),
                L"Failed to schedule %s. Error: 0x%08x\n",
                v33,
                ScheduledTask);
            }
          }
          if ( v8[3] > 7u )
            v8 = (_QWORD *)*v8;
          wprintf(L"Failed to schedule %s. Error: 0x%08x\n", v8, ScheduledTask);
        }
      }
      else
      {
        v104 = (_QWORD *)CmdOptions::GetCurrentRef(v20, v19);
        if ( *(_BYTE *)(*v104 + 12LL) )
        {
          v106 = (_QWORD *)CmdOptions::GetCurrentRef(*v104, v105);
          if ( *(_QWORD *)(*v106 + 184LL) )
          {
            if ( v8[3] <= 7u )
              v108 = v8;
            else
              v108 = (_QWORD *)*v8;
            v109 = CmdOptions::GetCurrentRef(*v106, v107);
            fwprintf_s(
              *(FILE *const *)(*(_QWORD *)v109 + 184LL),
              L"Another instance of the %s is already running please retry after sometime. Exiting...\n",
              v108);
          }
        }
        if ( v8[3] > 7u )
          v8 = (_QWORD *)*v8;
        wprintf(L"Another instance of the %s is already running please retry after sometime. Exiting...\n", v8);
      }
    }
    else
    {
      v21 = (_QWORD *)CmdOptions::GetCurrentRef(v20, v19);
      if ( *(_BYTE *)(*v21 + 12LL) )
      {
        v23 = (_QWORD *)CmdOptions::GetCurrentRef(*v21, v22);
        if ( *(_QWORD *)(*v23 + 184LL) )
        {
          if ( v8[3] <= 7u )
            v25 = v8;
          else
            v25 = (_QWORD *)*v8;
          v26 = CmdOptions::GetCurrentRef(*v23, v24);
          fwprintf_s(
            *(FILE *const *)(*(_QWORD *)v26 + 184LL),
            L"Failed to get %s state. Error: 0x%08x\n",
            v25,
            ScheduledTask);
        }
      }
      if ( v8[3] > 7u )
        v8 = (_QWORD *)*v8;
      wprintf(L"Failed to get %s state. Error: 0x%08x\n", v8, ScheduledTask);
    }
  }
  else
  {
    v13 = (_QWORD *)CmdOptions::GetCurrentRef(v11, v10);
    if ( *(_BYTE *)(*v13 + 12LL) )
    {
      v15 = (_QWORD *)CmdOptions::GetCurrentRef(*v13, v14);
      if ( *(_QWORD *)(*v15 + 184LL) )
      {
        if ( v8[3] <= 7u )
          v17 = v8;
        else
          v17 = (_QWORD *)*v8;
        v18 = CmdOptions::GetCurrentRef(*v15, v16);
        fwprintf_s(*(FILE *const *)(*(_QWORD *)v18 + 184LL), L"Failed to get %s. Error: 0x%08x\n", v17, ScheduledTask);
      }
    }
    if ( v8[3] > 7u )
      v8 = (_QWORD *)*v8;
    wprintf(L"Failed to get %s. Error: 0x%08x\n", v8, ScheduledTask);
  }
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v123);
  return ScheduledTask;
}

```

## disassembly

```asm
0x180033984  push    rbx
0x180033986  push    rsi
0x180033987  push    rdi
0x180033988  push    r12
0x18003398a  push    r13
0x18003398c  push    r14
0x18003398e  push    r15
0x180033990  sub     rsp, 280h
0x180033997  mov     rax, cs:__security_cookie
0x18003399e  xor     rax, rsp
0x1800339a1  mov     [rsp+2B8h+var_48], rax
0x1800339a9  mov     r15, r9
0x1800339ac  mov     r14, r8
0x1800339af  mov     rsi, rdx
0x1800339b2  mov     rbx, rcx
0x1800339b5  mov     [rsp+2B8h+var_278], rcx
0x1800339ba  mov     r12, [rsp+2B8h+arg_20]
0x1800339c2  xor     r13d, r13d
0x1800339c5  mov     [rsp+2B8h+var_290], r13
0x1800339ca  lea     rcx, [rsp+2B8h+var_290]
0x1800339cf  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800339d4  lea     r8, [rsp+2B8h+var_290]; struct IRegisteredTask **
0x1800339d9  lea     rdx, aAutomaticDevic_0; "Automatic-Device-Join"
0x1800339e0  call    ?GetScheduledTask@@YAJPEBG0PEAPEAUIRegisteredTask@@@Z; GetScheduledTask(ushort const *,ushort const *,IRegisteredTask * *)
0x1800339e5  mov     edi, eax
0x1800339e7  test    eax, eax
0x1800339e9  jns     short loc_180033A5B
0x1800339eb  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800339f0  mov     rcx, [rax]
0x1800339f3  cmp     [rcx+0Ch], r13b
0x1800339f7  jz      short loc_180033A3A
0x1800339f9  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800339fe  mov     rcx, [rax]
0x180033a01  cmp     [rcx+0B8h], r13
0x180033a08  jz      short loc_180033A3A
0x180033a0a  cmp     qword ptr [rbx+18h], 7
0x180033a0f  jbe     short loc_180033A16
0x180033a11  mov     rsi, [rbx]
0x180033a14  jmp     short loc_180033A19
0x180033a16  mov     rsi, rbx
0x180033a19  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180033a1e  mov     rcx, [rax]
0x180033a21  mov     r9d, edi
0x180033a24  mov     r8, rsi
0x180033a27  lea     rdx, aFailedToGetSEr; "Failed to get %s. Error: 0x%08x\n"
0x180033a2e  mov     rcx, [rcx+0B8h]; Stream
0x180033a35  call    fwprintf_s
0x180033a3a  cmp     qword ptr [rbx+18h], 7
0x180033a3f  jbe     short loc_180033A44
0x180033a41  mov     rbx, [rbx]
0x180033a44  lea     rcx, aFailedToGetSEr; "Failed to get %s. Error: 0x%08x\n"
0x180033a4b  mov     r8d, edi
0x180033a4e  mov     rdx, rbx
0x180033a51  call    wprintf
0x180033a56  jmp     loc_1800340EB
0x180033a5b  mov     [rsp+2B8h+var_280], r13d
0x180033a60  mov     rcx, [rsp+2B8h+var_290]
0x180033a65  mov     rax, [rcx]
0x180033a68  lea     rdx, [rsp+2B8h+var_280]
0x180033a6d  mov     rax, [rax+48h]
0x180033a71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a76  mov     edi, eax
0x180033a78  test    eax, eax
0x180033a7a  jns     short loc_180033AE1
0x180033a7c  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180033a81  mov     rcx, [rax]
0x180033a84  cmp     [rcx+0Ch], r13b
0x180033a88  jz      short loc_180033ACB
0x180033a8a  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180033a8f  mov     rcx, [rax]
0x180033a92  cmp     [rcx+0B8h], r13
0x180033a99  jz      short loc_180033ACB
0x180033a9b  cmp     qword ptr [rbx+18h], 7
0x180033aa0  jbe     short loc_180033AA7
0x180033aa2  mov     rsi, [rbx]
0x180033aa5  jmp     short loc_180033AAA
0x180033aa7  mov     rsi, rbx
0x180033aaa  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180033aaf  mov     rcx, [rax]
0x180033ab2  mov     r9d, edi
0x180033ab5  mov     r8, rsi
0x180033ab8  lea     rdx, aFailedToGetSSt; "Failed to get %s state. Error: 0x%08x\n"
0x180033abf  mov     rcx, [rcx+0B8h]; Stream
0x180033ac6  call    fwprintf_s
0x180033acb  cmp     qword ptr [rbx+18h], 7
0x180033ad0  jbe     short loc_180033AD5
0x180033ad2  mov     rbx, [rbx]
0x180033ad5  lea     rcx, aFailedToGetSSt; "Failed to get %s state. Error: 0x%08x\n"
0x180033adc  jmp     loc_180033A4B
0x180033ae1  mov     eax, [rsp+2B8h+var_280]
0x180033ae5  add     eax, 0FFFFFFFEh
0x180033ae8  test    eax, 0FFFFFFFDh
0x180033aed  jz      loc_180034085
0x180033af3  mov     r9, r12; unsigned __int16 *
0x180033af6  mov     r8, r15; unsigned __int16 *
0x180033af9  mov     rdx, r14; unsigned __int16 *
0x180033afc  mov     rcx, [rsp+2B8h+var_290]; struct IRegisteredTask *
0x180033b01  call    ?ScheduleTask@DsrCmdTaskSchedulerHelper@@CAJQEAUIRegisteredTask@@PEBG11@Z; DsrCmdTaskSchedulerHelper::ScheduleTask(IRegisteredTask * const,ushort const *,ushort const *,ushort const *)
0x180033b06  mov     edi, eax
0x180033b08  test    eax, eax
0x180033b0a  jns     short loc_180033B71
0x180033b0c  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180033b11  mov     rcx, [rax]
0x180033b14  cmp     [rcx+0Ch], r13b
0x180033b18  jz      short loc_180033B5B
0x180033b1a  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180033b1f  mov     rcx, [rax]
0x180033b22  cmp     [rcx+0B8h], r13
0x180033b29  jz      short loc_180033B5B
0x180033b2b  cmp     qword ptr [rbx+18h], 7
0x180033b30  jbe     short loc_180033B37
0x180033b32  mov     rsi, [rbx]
0x180033b35  jmp     short loc_180033B3A
0x180033b37  mov     rsi, rbx
0x180033b3a  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180033b3f  mov     rcx, [rax]
0x180033b42  mov     r9d, edi
0x180033b45  mov     r8, rsi
0x180033b48  lea     rdx, aFailedToSchedu; "Failed to schedule %s. Error: 0x%08x\n"
0x180033b4f  mov     rcx, [rcx+0B8h]; Stream
0x180033b56  call    fwprintf_s
0x180033b5b  cmp     qword ptr [rbx+18h], 7
0x180033b60  jbe     short loc_180033B65
0x180033b62  mov     rbx, [rbx]
0x180033b65  lea     rcx, aFailedToSchedu; "Failed to schedule %s. Error: 0x%08x\n"
0x180033b6c  jmp     loc_180033A4B
0x180033b71  cmp     qword ptr [rbx+18h], 7
0x180033b76  jbe     short loc_180033B7D
0x180033b78  mov     rdx, [rbx]
0x180033b7b  jmp     short loc_180033B80
0x180033b7d  mov     rdx, rbx
0x180033b80  lea     rcx, aWaitingForSToC; "Waiting for %s to complete. This could "...
0x180033b87  call    wprintf
0x180033b8c  mov     eax, 4
0x180033b91  mov     [rsp+2B8h+var_288], eax
0x180033b95  mov     edi, r13d
0x180033b98  lea     r12d, [rax-3]
0x180033b9c  mov     r14d, 0FFFFFFFDh
0x180033ba2  add     eax, 0FFFFFFFEh
0x180033ba5  test    r14d, eax
0x180033ba8  jnz     short loc_180033BD9
0x180033baa  cmp     edi, 78h ; 'x'
0x180033bad  jg      short loc_180033BD9
0x180033baf  add     edi, r12d
0x180033bb2  mov     ecx, 3E8h; dwMilliseconds
0x180033bb7  call    cs:__imp_Sleep
0x180033bbd  mov     rcx, [rsp+2B8h+var_290]
0x180033bc2  mov     rax, [rcx]
0x180033bc5  lea     rdx, [rsp+2B8h+var_288]
0x180033bca  mov     rax, [rax+48h]
0x180033bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033bd3  mov     eax, [rsp+2B8h+var_288]
0x180033bd7  jmp     short loc_180033BA2
0x180033bd9  lea     rcx, asc_1801108B0; "\r                                     "...
0x180033be0  call    wprintf
0x180033be5  mov     eax, [rsp+2B8h+var_288]
0x180033be9  cmp     eax, 3
0x180033bec  jz      loc_180033D64
0x180033bf2  add     eax, 0FFFFFFFEh
0x180033bf5  test    r14d, eax
0x180033bf8  jz      short loc_180033C64
0x180033bfa  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180033bff  mov     rcx, [rax]
0x180033c02  cmp     [rcx+0Ch], r13b
0x180033c06  jz      short loc_180033C46
0x180033c08  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180033c0d  mov     rcx, [rax]
0x180033c10  cmp     [rcx+0B8h], r13
0x180033c17  jz      short loc_180033C46
0x180033c19  cmp     qword ptr [rbx+18h], 7
0x180033c1e  jbe     short loc_180033C25
0x180033c20  mov     rdi, [rbx]
0x180033c23  jmp     short loc_180033C28
0x180033c25  mov     rdi, rbx
0x180033c28  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180033c2d  mov     rcx, [rax]
0x180033c30  mov     r8, rdi
0x180033c33  lea     rdx, aScheduledSFail; "Scheduled %s failed. Exiting...\n"
0x180033c3a  mov     rcx, [rcx+0B8h]; Stream
0x180033c41  call    fwprintf_s
0x180033c46  cmp     qword ptr [rbx+18h], 7
0x180033c4b  jbe     short loc_180033C50
0x180033c4d  mov     rbx, [rbx]
0x180033c50  mov     rdx, rbx
0x180033c53  lea     rcx, aScheduledSFail; "Scheduled %s failed. Exiting...\n"
0x180033c5a  call    wprintf
0x180033c5f  jmp     loc_180033D5C
0x180033c64  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180033c69  mov     rcx, [rax]
0x180033c6c  cmp     [rcx+0Ch], r13b
0x180033c70  jz      short loc_180033CC2
0x180033c72  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180033c77  mov     rcx, [rax]
0x180033c7a  cmp     [rcx+0B8h], r13
0x180033c81  jz      short loc_180033CC2
0x180033c83  cmp     qword ptr [rsi+18h], 7
0x180033c88  jbe     short loc_180033C8F
0x180033c8a  mov     r14, [rsi]
0x180033c8d  jmp     short loc_180033C92
0x180033c8f  mov     r14, rsi
0x180033c92  cmp     qword ptr [rbx+18h], 7
0x180033c97  jbe     short loc_180033C9E
0x180033c99  mov     rdi, [rbx]
0x180033c9c  jmp     short loc_180033CA1
0x180033c9e  mov     rdi, rbx
0x180033ca1  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180033ca6  mov     rcx, [rax]
0x180033ca9  mov     r9, r14
0x180033cac  mov     r8, rdi
0x180033caf  lea     rdx, aScheduledSDidN; "Scheduled %s did not complete in a reas"...
0x180033cb6  mov     rcx, [rcx+0B8h]; Stream
0x180033cbd  call    fwprintf_s
0x180033cc2  cmp     qword ptr [rsi+18h], 7
0x180033cc7  jbe     short loc_180033CCC
0x180033cc9  mov     rsi, [rsi]
0x180033ccc  cmp     qword ptr [rbx+18h], 7
0x180033cd1  jbe     short loc_180033CD6
0x180033cd3  mov     rbx, [rbx]
0x180033cd6  mov     r8, rsi
0x180033cd9  mov     rdx, rbx
0x180033cdc  lea     rcx, aScheduledSDidN; "Scheduled %s did not complete in a reas"...
0x180033ce3  call    wprintf
0x180033ce8  mov     rcx, [rsp+2B8h+var_290]
0x180033ced  mov     rax, [rcx]
0x180033cf0  xor     edx, edx
0x180033cf2  mov     rax, [rax+0B8h]
0x180033cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033cfe  mov     ebx, eax
0x180033d00  test    eax, eax
0x180033d02  jns     short loc_180033D5C
0x180033d04  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180033d09  mov     rcx, [rax]
0x180033d0c  cmp     [rcx], r13b
0x180033d0f  jz      short loc_180033D5C
0x180033d11  mov     edx, ebx
0x180033d13  lea     rcx, aCouldNotStopSc; "Could not stop scheduled task: 0x%08x\n"
0x180033d1a  call    wprintf
0x180033d1f  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180033d24  mov     rcx, [rax]
0x180033d27  cmp     [rcx+0Ch], r13b
0x180033d2b  jz      short loc_180033D5C
0x180033d2d  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180033d32  mov     rcx, [rax]
0x180033d35  cmp     [rcx+0B8h], r13
0x180033d3c  jz      short loc_180033D5C
0x180033d3e  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180033d43  mov     rcx, [rax]
0x180033d46  mov     r8d, ebx
0x180033d49  lea     rdx, aCouldNotStopSc; "Could not stop scheduled task: 0x%08x\n"
0x180033d50  mov     rcx, [rcx+0B8h]; Stream
0x180033d57  call    fwprintf_s
0x180033d5c  mov     edi, r12d
0x180033d5f  jmp     loc_1800340EB
0x180033d64  mov     [rsp+2B8h+var_298], r13d
0x180033d69  mov     rcx, [rsp+2B8h+var_290]
0x180033d6e  mov     rax, [rcx]
0x180033d71  lea     rdx, [rsp+2B8h+var_298]
0x180033d76  mov     rax, [rax+80h]
0x180033d7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033d82  mov     edi, eax
0x180033d84  mov     [rsp+2B8h+var_284], eax
0x180033d88  test    eax, eax
0x180033d8a  jns     loc_180033E35
0x180033d90  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180033d95  mov     rcx, [rax]
0x180033d98  cmp     [rcx], r13b
0x180033d9b  jz      short loc_180033E0A
0x180033d9d  cmp     qword ptr [rbx+18h], 7
0x180033da2  jbe     short loc_180033DA9
0x180033da4  mov     rdx, [rbx]
0x180033da7  jmp     short loc_180033DAC
0x180033da9  mov     rdx, rbx
0x180033dac  mov     r8d, edi
0x180033daf  lea     rcx, aFailedToGetSLa; "Failed to get %s last task result. Erro"...
0x180033db6  call    wprintf
0x180033dbb  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180033dc0  mov     rcx, [rax]
0x180033dc3  cmp     [rcx+0Ch], r13b
0x180033dc7  jz      short loc_180033E0A
0x180033dc9  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180033dce  mov     rcx, [rax]
0x180033dd1  cmp     [rcx+0B8h], r13
0x180033dd8  jz      short loc_180033E0A
0x180033dda  cmp     qword ptr [rbx+18h], 7
0x180033ddf  jbe     short loc_180033DE6
0x180033de1  mov     r14, [rbx]
0x180033de4  jmp     short loc_180033DE9
0x180033de6  mov     r14, rbx
0x180033de9  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180033dee  mov     rcx, [rax]
0x180033df1  mov     r9d, edi
0x180033df4  mov     r8, r14
0x180033df7  lea     rdx, aFailedToGetSLa; "Failed to get %s last task result. Erro"...
0x180033dfe  mov     rcx, [rcx+0B8h]; Stream
0x180033e05  call    fwprintf_s
0x180033e0a  cmp     qword ptr [rbx+18h], 7
0x180033e0f  jbe     short loc_180033E16
0x180033e11  mov     rdx, [rbx]
0x180033e14  jmp     short loc_180033E19
0x180033e16  mov     rdx, rbx
  ... truncated ...
```
