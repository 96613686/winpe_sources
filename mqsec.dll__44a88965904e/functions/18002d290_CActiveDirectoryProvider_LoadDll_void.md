# CActiveDirectoryProvider::LoadDll(void)

- ea: `0x18002d290`
- end: `0x18002d8b8`
- name: `?LoadDll@CActiveDirectoryProvider@@AEAAJXZ`
- size: `1576`
- prototype: `__int64 __fastcall(CActiveDirectoryProvider *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002d250`

## callees

- `0x180004074`
- `0x180017430`
- `0x18002d290`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18002d346`
- `KERNEL32!GetProcAddress` at `0x18002d36d`
- `KERNEL32!GetProcAddress` at `0x18002d394`
- `KERNEL32!GetProcAddress` at `0x18002d3bb`
- `KERNEL32!GetProcAddress` at `0x18002d3d8`
- `KERNEL32!GetProcAddress` at `0x18002d3ff`
- `KERNEL32!GetProcAddress` at `0x18002d426`
- `KERNEL32!GetProcAddress` at `0x18002d44d`
- `KERNEL32!GetProcAddress` at `0x18002d474`
- `KERNEL32!GetProcAddress` at `0x18002d49b`
- `KERNEL32!GetProcAddress` at `0x18002d4c2`
- `KERNEL32!GetProcAddress` at `0x18002d4e9`
- `KERNEL32!GetProcAddress` at `0x18002d510`
- `KERNEL32!GetProcAddress` at `0x18002d537`
- `KERNEL32!GetProcAddress` at `0x18002d55e`
- `KERNEL32!GetProcAddress` at `0x18002d585`
- `KERNEL32!GetProcAddress` at `0x18002d5af`
- `KERNEL32!GetProcAddress` at `0x18002d5d9`
- `KERNEL32!GetProcAddress` at `0x18002d603`
- `KERNEL32!GetProcAddress` at `0x18002d62d`
- `KERNEL32!GetProcAddress` at `0x18002d657`
- `KERNEL32!GetProcAddress` at `0x18002d681`
- `KERNEL32!GetProcAddress` at `0x18002d6ab`
- `KERNEL32!GetProcAddress` at `0x18002d6d5`
- `KERNEL32!GetProcAddress` at `0x18002d6ff`
- `KERNEL32!GetProcAddress` at `0x18002d729`
- `KERNEL32!GetProcAddress` at `0x18002d753`
- `KERNEL32!GetProcAddress` at `0x18002d77d`
- `KERNEL32!GetProcAddress` at `0x18002d7a7`
- `KERNEL32!GetProcAddress` at `0x18002d7ce`
- `KERNEL32!GetProcAddress` at `0x18002d7f5`
- `KERNEL32!GetProcAddress` at `0x18002d815`
- `KERNEL32!GetProcAddress` at `0x18002d346`
- `KERNEL32!GetProcAddress` at `0x18002d36d`
- `KERNEL32!GetProcAddress` at `0x18002d394`
- `KERNEL32!GetProcAddress` at `0x18002d3bb`
- `KERNEL32!GetProcAddress` at `0x18002d3d8`
- `KERNEL32!GetProcAddress` at `0x18002d3ff`
- `KERNEL32!GetProcAddress` at `0x18002d426`
- `KERNEL32!GetProcAddress` at `0x18002d44d`
- `KERNEL32!GetProcAddress` at `0x18002d474`
- `KERNEL32!GetProcAddress` at `0x18002d49b`
- `KERNEL32!GetProcAddress` at `0x18002d4c2`
- `KERNEL32!GetProcAddress` at `0x18002d4e9`
- `KERNEL32!GetProcAddress` at `0x18002d510`
- `KERNEL32!GetProcAddress` at `0x18002d537`
- `KERNEL32!GetProcAddress` at `0x18002d55e`
- `KERNEL32!GetProcAddress` at `0x18002d585`
- `KERNEL32!GetProcAddress` at `0x18002d5af`
- `KERNEL32!GetProcAddress` at `0x18002d5d9`
- `KERNEL32!GetProcAddress` at `0x18002d603`
- `KERNEL32!GetProcAddress` at `0x18002d62d`
- `KERNEL32!GetProcAddress` at `0x18002d657`
- `KERNEL32!GetProcAddress` at `0x18002d681`
- `KERNEL32!GetProcAddress` at `0x18002d6ab`
- `KERNEL32!GetProcAddress` at `0x18002d6d5`
- `KERNEL32!GetProcAddress` at `0x18002d6ff`
- `KERNEL32!GetProcAddress` at `0x18002d729`
- `KERNEL32!GetProcAddress` at `0x18002d753`
- `KERNEL32!GetProcAddress` at `0x18002d77d`
- `KERNEL32!GetProcAddress` at `0x18002d7a7`
- `KERNEL32!GetProcAddress` at `0x18002d7ce`
- `KERNEL32!GetProcAddress` at `0x18002d7f5`
- `KERNEL32!GetProcAddress` at `0x18002d815`
- `KERNEL32!LoadLibraryW` at `0x18002d2ac`
- `KERNEL32!LoadLibraryW` at `0x18002d2ac`

## string_xrefs

- `0x18002d2a5`: `mqad.dll`
- `0x18002d33c`: `MQADCreateObject`
- `0x18002d366`: `MQADDeleteObject`
- `0x18002d38d`: `MQADDeleteObjectGuid`
- `0x18002d3b4`: `MQADDeleteObjectGuidSid`
- `0x18002d446`: `MQADQMGetObjectSecurity`
- `0x18002d4e2`: `MQADGetComputerSites`
- `0x18002d509`: `MQADBeginDeleteNotification`
- `0x18002d530`: `MQADNotifyDelete`
- `0x18002d557`: `MQADEndDeleteNotification`
- `0x18002d650`: `MQADQueryLinks`
- `0x18002d67a`: `MQADQueryAllLinks`
- `0x18002d74c`: `MQADGetObjectSecurity`
- `0x18002d776`: `MQADGetObjectSecurityGuid`
- `0x18002d7a0`: `MQADSetObjectSecurity`
- `0x18002d7c7`: `MQADSetObjectSecurityGuid`
- `0x18002d7ee`: `MQADGetADsPathInfo`

## pseudocode

```c
__int64 __fastcall CActiveDirectoryProvider::LoadDll(CActiveDirectoryProvider *this)
{
  HMODULE LibraryW; // rax
  unsigned int v3; // eax
  FARPROC ProcAddress; // rax
  __int16 v6; // ax
  FARPROC v7; // rax
  FARPROC v8; // rax
  FARPROC v9; // rax
  FARPROC v10; // rax
  FARPROC v11; // rax
  FARPROC v12; // rax
  FARPROC v13; // rax
  FARPROC v14; // rax
  FARPROC v15; // rax
  FARPROC v16; // rax
  FARPROC v17; // rax
  FARPROC v18; // rax
  FARPROC v19; // rax
  FARPROC v20; // rax
  FARPROC v21; // rax
  FARPROC v22; // rax
  FARPROC v23; // rax
  FARPROC v24; // rax
  FARPROC v25; // rax
  FARPROC v26; // rax
  FARPROC v27; // rax
  FARPROC v28; // rax
  FARPROC v29; // rax
  FARPROC v30; // rax
  FARPROC v31; // rax
  FARPROC v32; // rax
  FARPROC v33; // rax
  FARPROC v34; // rax
  FARPROC v35; // rax
  FARPROC v36; // rax
  FARPROC v37; // rax
  unsigned int v38; // eax
  __int16 v39; // [rsp+70h] [rbp+10h] BYREF
  int v40; // [rsp+78h] [rbp+18h] BYREF

  LibraryW = LoadLibraryW(L"mqad.dll");
  *((_QWORD *)this + 33) = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "MQADCreateObject");
    *((_QWORD *)this + 1) = ProcAddress;
    if ( ProcAddress )
    {
      v7 = GetProcAddress(*((HMODULE *)this + 33), "MQADDeleteObject");
      *((_QWORD *)this + 2) = v7;
      if ( v7 )
      {
        v8 = GetProcAddress(*((HMODULE *)this + 33), "MQADDeleteObjectGuid");
        *((_QWORD *)this + 3) = v8;
        if ( v8
          && (v9 = GetProcAddress(*((HMODULE *)this + 33), "MQADDeleteObjectGuidSid"), (*((_QWORD *)this + 4) = v9) != 0) )
        {
          v10 = GetProcAddress(*((HMODULE *)this + 33), "MQADGetObjectProperties");
          *((_QWORD *)this + 5) = v10;
          if ( v10 )
          {
            v11 = GetProcAddress(*((HMODULE *)this + 33), "MQADGetGenObjectProperties");
            *((_QWORD *)this + 6) = v11;
            if ( v11 )
            {
              v12 = GetProcAddress(*((HMODULE *)this + 33), "MQADGetObjectPropertiesGuid");
              *((_QWORD *)this + 7) = v12;
              if ( v12 )
              {
                v13 = GetProcAddress(*((HMODULE *)this + 33), "MQADQMGetObjectSecurity");
                *((_QWORD *)this + 8) = v13;
                if ( v13 )
                {
                  v14 = GetProcAddress(*((HMODULE *)this + 33), "MQADSetObjectProperties");
                  *((_QWORD *)this + 9) = v14;
                  if ( v14 )
                  {
                    v15 = GetProcAddress(*((HMODULE *)this + 33), "MQADSetObjectPropertiesGuid");
                    *((_QWORD *)this + 10) = v15;
                    if ( v15 )
                    {
                      v16 = GetProcAddress(*((HMODULE *)this + 33), "MQADInit");
                      *((_QWORD *)this + 11) = v16;
                      if ( v16 )
                      {
                        v17 = GetProcAddress(*((HMODULE *)this + 33), "MQADGetComputerSites");
                        *((_QWORD *)this + 12) = v17;
                        if ( v17 )
                        {
                          v18 = GetProcAddress(*((HMODULE *)this + 33), "MQADBeginDeleteNotification");
                          *((_QWORD *)this + 13) = v18;
                          if ( v18 )
                          {
                            v19 = GetProcAddress(*((HMODULE *)this + 33), "MQADNotifyDelete");
                            *((_QWORD *)this + 14) = v19;
                            if ( v19 )
                            {
                              v20 = GetProcAddress(*((HMODULE *)this + 33), "MQADEndDeleteNotification");
                              *((_QWORD *)this + 15) = v20;
                              if ( v20 )
                              {
                                v21 = GetProcAddress(*((HMODULE *)this + 33), "MQADQueryMachineQueues");
                                *((_QWORD *)this + 16) = v21;
                                if ( v21 )
                                {
                                  v22 = GetProcAddress(*((HMODULE *)this + 33), "MQADQuerySiteServers");
                                  *((_QWORD *)this + 17) = v22;
                                  if ( v22 )
                                  {
                                    v23 = GetProcAddress(*((HMODULE *)this + 33), "MQADQueryUserCert");
                                    *((_QWORD *)this + 18) = v23;
                                    if ( v23 )
                                    {
                                      v24 = GetProcAddress(*((HMODULE *)this + 33), "MQADQueryConnectors");
                                      *((_QWORD *)this + 19) = v24;
                                      if ( v24 )
                                      {
                                        v25 = GetProcAddress(*((HMODULE *)this + 33), "MQADQueryForeignSites");
                                        *((_QWORD *)this + 20) = v25;
                                        if ( v25 )
                                        {
                                          v26 = GetProcAddress(*((HMODULE *)this + 33), "MQADQueryLinks");
                                          *((_QWORD *)this + 21) = v26;
                                          if ( v26 )
                                          {
                                            v27 = GetProcAddress(*((HMODULE *)this + 33), "MQADQueryAllLinks");
                                            *((_QWORD *)this + 22) = v27;
                                            if ( v27 )
                                            {
                                              v28 = GetProcAddress(*((HMODULE *)this + 33), "MQADQueryAllSites");
                                              *((_QWORD *)this + 23) = v28;
                                              if ( v28 )
                                              {
                                                v29 = GetProcAddress(*((HMODULE *)this + 33), "MQADQueryQueues");
                                                *((_QWORD *)this + 24) = v29;
                                                if ( v29 )
                                                {
                                                  v30 = GetProcAddress(*((HMODULE *)this + 33), "MQADQueryResults");
                                                  *((_QWORD *)this + 25) = v30;
                                                  if ( v30 )
                                                  {
                                                    v31 = GetProcAddress(*((HMODULE *)this + 33), "MQADEndQuery");
                                                    *((_QWORD *)this + 26) = v31;
                                                    if ( v31 )
                                                    {
                                                      v32 = GetProcAddress(
                                                              *((HMODULE *)this + 33),
                                                              "MQADGetObjectSecurity");
                                                      *((_QWORD *)this + 27) = v32;
                                                      if ( v32 )
                                                      {
                                                        v33 = GetProcAddress(
                                                                *((HMODULE *)this + 33),
                                                                "MQADGetObjectSecurityGuid");
                                                        *((_QWORD *)this + 28) = v33;
                                                        if ( v33 )
                                                        {
                                                          v34 = GetProcAddress(
                                                                  *((HMODULE *)this + 33),
                                                                  "MQADSetObjectSecurity");
                                                          *((_QWORD *)this + 29) = v34;
                                                          if ( v34 )
                                                          {
                                                            v35 = GetProcAddress(
                                                                    *((HMODULE *)this + 33),
                                                                    "MQADSetObjectSecurityGuid");
                                                            *((_QWORD *)this + 30) = v35;
                                                            if ( v35 )
                                                            {
                                                              v36 = GetProcAddress(
                                                                      *((HMODULE *)this + 33),
                                                                      "MQADGetADsPathInfo");
                                                              *((_QWORD *)this + 31) = v36;
                                                              if ( v36 )
                                                              {
                                                                v37 = GetProcAddress(
                                                                        *((HMODULE *)this + 33),
                                                                        "MQADFreeMemory");
                                                                *((_QWORD *)this + 32) = v37;
                                                                if ( v37 )
                                                                  return 0;
                                                              }
                                                              v6 = 386;
                                                            }
                                                            else
                                                            {
                                                              v6 = 385;
                                                            }
                                                          }
                                                          else
                                                          {
                                                            v6 = 380;
                                                          }
                                                        }
                                                        else
                                                        {
                                                          v6 = 370;
                                                        }
                                                      }
                                                      else
                                                      {
                                                        v6 = 360;
                                                      }
                                                    }
                                                    else
                                                    {
                                                      v6 = 350;
                                                    }
                                                  }
                                                  else
                                                  {
                                                    v6 = 340;
                                                  }
                                                }
                                                else
                                                {
                                                  v6 = 330;
                                                }
                                              }
                                              else
                                              {
                                                v6 = 320;
                                              }
                                            }
                                            else
                                            {
                                              v6 = 310;
                                            }
                                          }
                                          else
                                          {
                                            v6 = 300;
                                          }
                                        }
                                        else
                                        {
                                          v6 = 290;
                                        }
                                      }
                                      else
                                      {
                                        v6 = 280;
                                      }
                                    }
                                    else
                                    {
                                      v6 = 270;
                                    }
                                  }
                                  else
                                  {
                                    v6 = 260;
                                  }
                                }
                                else
                                {
                                  v6 = 250;
                                }
                              }
                              else
                              {
                                v6 = 240;
                              }
                            }
                            else
                            {
                              v6 = 230;
                            }
                          }
                          else
                          {
                            v6 = 220;
                          }
                        }
                        else
                        {
                          v6 = 210;
                        }
                      }
                      else
                      {
                        v6 = 190;
                      }
                    }
                    else
                    {
                      v6 = 170;
                    }
                  }
                  else
                  {
                    v6 = 160;
                  }
                }
                else
                {
                  v6 = 150;
                }
              }
              else
              {
                v6 = 140;
              }
            }
            else
            {
              v6 = 135;
            }
          }
          else
          {
            v6 = 130;
          }
        }
        else
        {
          v6 = 120;
        }
      }
      else
      {
        v6 = 110;
      }
    }
    else
    {
      v6 = 100;
    }
    v40 = -1072824253;
    v39 = v6;
    if ( g_pMSMQErrorLoggingTrace )
    {
      v38 = mqwcslen(L"ad/adprov");
      CMSMQTrace::MSMQTraceEvent(g_pMSMQErrorLoggingTrace, 1, 1, 2LL * (v38 + 1), L"ad/adprov", 2, &v39, 4, &v40, 0, 0);
    }
    return 3222143043LL;
  }
  else
  {
    v39 = 10;
    v40 = -1072824187;
    if ( g_pMSMQErrorLoggingTrace )
    {
      v3 = mqwcslen(L"ad/adprov");
      CMSMQTrace::MSMQTraceEvent(g_pMSMQErrorLoggingTrace, 1, 1, 2LL * (v3 + 1), L"ad/adprov", 2, &v39, 4, &v40, 0, 0);
    }
    return 3222143109LL;
  }
}

```

## disassembly

```asm
0x18002d290  mov     [rsp-8+arg_10], rbx
0x18002d295  mov     [rsp-8+arg_18], rdi
0x18002d29a  push    rbp
0x18002d29b  mov     rbp, rsp
0x18002d29e  sub     rsp, 60h
0x18002d2a2  mov     rbx, rcx
0x18002d2a5  lea     rcx, aMqadDll; "mqad.dll"
0x18002d2ac  call    cs:__imp_LoadLibraryW
0x18002d2b2  xor     edi, edi
0x18002d2b4  mov     [rbx+108h], rax
0x18002d2bb  test    rax, rax
0x18002d2be  jnz     short loc_18002D33C
0x18002d2c0  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, rdi; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18002d2c7  lea     eax, [rdi+0Ah]
0x18002d2ca  mov     [rbp+arg_0], ax
0x18002d2ce  mov     [rbp+arg_8], 0C00E0085h
0x18002d2d5  jz      short loc_18002D332
0x18002d2d7  lea     rbx, aAdAdprov; "ad/adprov"
0x18002d2de  mov     rcx, rbx; wchar_t *
0x18002d2e1  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18002d2e6  mov     [rsp+60h+var_10], rdi
0x18002d2eb  lea     edx, [rdi+1]
0x18002d2ee  mov     [rsp+60h+var_18], rdi
0x18002d2f3  lea     rcx, [rbp+arg_0]
0x18002d2f7  mov     r8d, edx
0x18002d2fa  lea     r9d, [rdx+rax]
0x18002d2fe  lea     rax, [rbp+arg_8]
0x18002d302  add     r9, r9
0x18002d305  mov     [rsp+60h+var_20], rax
0x18002d30a  mov     [rsp+60h+var_28], 4
0x18002d313  mov     [rsp+60h+var_30], rcx
0x18002d318  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18002d31f  mov     [rsp+60h+var_38], 2
0x18002d328  mov     [rsp+60h+var_40], rbx
0x18002d32d  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x18002d332  mov     eax, 0C00E0085h
0x18002d337  jmp     loc_18002D8A6
0x18002d33c  lea     rdx, aMqadcreateobje; "MQADCreateObject"
0x18002d343  mov     rcx, rax; hModule
0x18002d346  call    cs:__imp_GetProcAddress
0x18002d34c  mov     [rbx+8], rax
0x18002d350  test    rax, rax
0x18002d353  jnz     short loc_18002D35F
0x18002d355  mov     eax, 64h ; 'd'
0x18002d35a  jmp     loc_18002D82C
0x18002d35f  mov     rcx, [rbx+108h]; hModule
0x18002d366  lea     rdx, aMqaddeleteobje; "MQADDeleteObject"
0x18002d36d  call    cs:__imp_GetProcAddress
0x18002d373  mov     [rbx+10h], rax
0x18002d377  test    rax, rax
0x18002d37a  jnz     short loc_18002D386
0x18002d37c  mov     eax, 6Eh ; 'n'
0x18002d381  jmp     loc_18002D82C
0x18002d386  mov     rcx, [rbx+108h]; hModule
0x18002d38d  lea     rdx, aMqaddeleteobje_1; "MQADDeleteObjectGuid"
0x18002d394  call    cs:__imp_GetProcAddress
0x18002d39a  mov     [rbx+18h], rax
0x18002d39e  test    rax, rax
0x18002d3a1  jnz     short loc_18002D3AD
0x18002d3a3  mov     eax, 78h ; 'x'
0x18002d3a8  jmp     loc_18002D82C
0x18002d3ad  mov     rcx, [rbx+108h]; hModule
0x18002d3b4  lea     rdx, aMqaddeleteobje_0; "MQADDeleteObjectGuidSid"
0x18002d3bb  call    cs:__imp_GetProcAddress
0x18002d3c1  mov     [rbx+20h], rax
0x18002d3c5  test    rax, rax
0x18002d3c8  jz      short loc_18002D3A3
0x18002d3ca  mov     rcx, [rbx+108h]; hModule
0x18002d3d1  lea     rdx, aMqadgetobjectp_0; "MQADGetObjectProperties"
0x18002d3d8  call    cs:__imp_GetProcAddress
0x18002d3de  mov     [rbx+28h], rax
0x18002d3e2  test    rax, rax
0x18002d3e5  jnz     short loc_18002D3F1
0x18002d3e7  mov     eax, 82h
0x18002d3ec  jmp     loc_18002D82C
0x18002d3f1  mov     rcx, [rbx+108h]; hModule
0x18002d3f8  lea     rdx, aMqadgetgenobje; "MQADGetGenObjectProperties"
0x18002d3ff  call    cs:__imp_GetProcAddress
0x18002d405  mov     [rbx+30h], rax
0x18002d409  test    rax, rax
0x18002d40c  jnz     short loc_18002D418
0x18002d40e  mov     eax, 87h
0x18002d413  jmp     loc_18002D82C
0x18002d418  mov     rcx, [rbx+108h]; hModule
0x18002d41f  lea     rdx, aMqadgetobjectp; "MQADGetObjectPropertiesGuid"
0x18002d426  call    cs:__imp_GetProcAddress
0x18002d42c  mov     [rbx+38h], rax
0x18002d430  test    rax, rax
0x18002d433  jnz     short loc_18002D43F
0x18002d435  mov     eax, 8Ch
0x18002d43a  jmp     loc_18002D82C
0x18002d43f  mov     rcx, [rbx+108h]; hModule
0x18002d446  lea     rdx, aMqadqmgetobjec; "MQADQMGetObjectSecurity"
0x18002d44d  call    cs:__imp_GetProcAddress
0x18002d453  mov     [rbx+40h], rax
0x18002d457  test    rax, rax
0x18002d45a  jnz     short loc_18002D466
0x18002d45c  mov     eax, 96h
0x18002d461  jmp     loc_18002D82C
0x18002d466  mov     rcx, [rbx+108h]; hModule
0x18002d46d  lea     rdx, aMqadsetobjectp; "MQADSetObjectProperties"
0x18002d474  call    cs:__imp_GetProcAddress
0x18002d47a  mov     [rbx+48h], rax
0x18002d47e  test    rax, rax
0x18002d481  jnz     short loc_18002D48D
0x18002d483  mov     eax, 0A0h
0x18002d488  jmp     loc_18002D82C
0x18002d48d  mov     rcx, [rbx+108h]; hModule
0x18002d494  lea     rdx, aMqadsetobjectp_0; "MQADSetObjectPropertiesGuid"
0x18002d49b  call    cs:__imp_GetProcAddress
0x18002d4a1  mov     [rbx+50h], rax
0x18002d4a5  test    rax, rax
0x18002d4a8  jnz     short loc_18002D4B4
0x18002d4aa  mov     eax, 0AAh
0x18002d4af  jmp     loc_18002D82C
0x18002d4b4  mov     rcx, [rbx+108h]; hModule
0x18002d4bb  lea     rdx, aMqadinit; "MQADInit"
0x18002d4c2  call    cs:__imp_GetProcAddress
0x18002d4c8  mov     [rbx+58h], rax
0x18002d4cc  test    rax, rax
0x18002d4cf  jnz     short loc_18002D4DB
0x18002d4d1  mov     eax, 0BEh
0x18002d4d6  jmp     loc_18002D82C
0x18002d4db  mov     rcx, [rbx+108h]; hModule
0x18002d4e2  lea     rdx, aMqadgetcompute; "MQADGetComputerSites"
0x18002d4e9  call    cs:__imp_GetProcAddress
0x18002d4ef  mov     [rbx+60h], rax
0x18002d4f3  test    rax, rax
0x18002d4f6  jnz     short loc_18002D502
0x18002d4f8  mov     eax, 0D2h
0x18002d4fd  jmp     loc_18002D82C
0x18002d502  mov     rcx, [rbx+108h]; hModule
0x18002d509  lea     rdx, aMqadbegindelet; "MQADBeginDeleteNotification"
0x18002d510  call    cs:__imp_GetProcAddress
0x18002d516  mov     [rbx+68h], rax
0x18002d51a  test    rax, rax
0x18002d51d  jnz     short loc_18002D529
0x18002d51f  mov     eax, 0DCh
0x18002d524  jmp     loc_18002D82C
0x18002d529  mov     rcx, [rbx+108h]; hModule
0x18002d530  lea     rdx, aMqadnotifydele; "MQADNotifyDelete"
0x18002d537  call    cs:__imp_GetProcAddress
0x18002d53d  mov     [rbx+70h], rax
0x18002d541  test    rax, rax
0x18002d544  jnz     short loc_18002D550
0x18002d546  mov     eax, 0E6h
0x18002d54b  jmp     loc_18002D82C
0x18002d550  mov     rcx, [rbx+108h]; hModule
0x18002d557  lea     rdx, aMqadenddeleten; "MQADEndDeleteNotification"
0x18002d55e  call    cs:__imp_GetProcAddress
0x18002d564  mov     [rbx+78h], rax
0x18002d568  test    rax, rax
0x18002d56b  jnz     short loc_18002D577
0x18002d56d  mov     eax, 0F0h
0x18002d572  jmp     loc_18002D82C
0x18002d577  mov     rcx, [rbx+108h]; hModule
0x18002d57e  lea     rdx, aMqadquerymachi; "MQADQueryMachineQueues"
0x18002d585  call    cs:__imp_GetProcAddress
0x18002d58b  mov     [rbx+80h], rax
0x18002d592  test    rax, rax
0x18002d595  jnz     short loc_18002D5A1
0x18002d597  mov     eax, 0FAh
0x18002d59c  jmp     loc_18002D82C
0x18002d5a1  mov     rcx, [rbx+108h]; hModule
0x18002d5a8  lea     rdx, aMqadquerysites; "MQADQuerySiteServers"
0x18002d5af  call    cs:__imp_GetProcAddress
0x18002d5b5  mov     [rbx+88h], rax
0x18002d5bc  test    rax, rax
0x18002d5bf  jnz     short loc_18002D5CB
0x18002d5c1  mov     eax, 104h
0x18002d5c6  jmp     loc_18002D82C
0x18002d5cb  mov     rcx, [rbx+108h]; hModule
0x18002d5d2  lea     rdx, aMqadqueryuserc; "MQADQueryUserCert"
0x18002d5d9  call    cs:__imp_GetProcAddress
0x18002d5df  mov     [rbx+90h], rax
0x18002d5e6  test    rax, rax
0x18002d5e9  jnz     short loc_18002D5F5
0x18002d5eb  mov     eax, 10Eh
0x18002d5f0  jmp     loc_18002D82C
0x18002d5f5  mov     rcx, [rbx+108h]; hModule
0x18002d5fc  lea     rdx, aMqadqueryconne; "MQADQueryConnectors"
0x18002d603  call    cs:__imp_GetProcAddress
0x18002d609  mov     [rbx+98h], rax
0x18002d610  test    rax, rax
0x18002d613  jnz     short loc_18002D61F
0x18002d615  mov     eax, 118h
0x18002d61a  jmp     loc_18002D82C
0x18002d61f  mov     rcx, [rbx+108h]; hModule
0x18002d626  lea     rdx, aMqadqueryforei; "MQADQueryForeignSites"
0x18002d62d  call    cs:__imp_GetProcAddress
0x18002d633  mov     [rbx+0A0h], rax
0x18002d63a  test    rax, rax
0x18002d63d  jnz     short loc_18002D649
0x18002d63f  mov     eax, 122h
0x18002d644  jmp     loc_18002D82C
0x18002d649  mov     rcx, [rbx+108h]; hModule
0x18002d650  lea     rdx, aMqadquerylinks; "MQADQueryLinks"
0x18002d657  call    cs:__imp_GetProcAddress
0x18002d65d  mov     [rbx+0A8h], rax
0x18002d664  test    rax, rax
0x18002d667  jnz     short loc_18002D673
0x18002d669  mov     eax, 12Ch
0x18002d66e  jmp     loc_18002D82C
0x18002d673  mov     rcx, [rbx+108h]; hModule
0x18002d67a  lea     rdx, aMqadqueryallli; "MQADQueryAllLinks"
0x18002d681  call    cs:__imp_GetProcAddress
0x18002d687  mov     [rbx+0B0h], rax
0x18002d68e  test    rax, rax
0x18002d691  jnz     short loc_18002D69D
0x18002d693  mov     eax, 136h
0x18002d698  jmp     loc_18002D82C
0x18002d69d  mov     rcx, [rbx+108h]; hModule
0x18002d6a4  lea     rdx, aMqadqueryallsi; "MQADQueryAllSites"
0x18002d6ab  call    cs:__imp_GetProcAddress
0x18002d6b1  mov     [rbx+0B8h], rax
0x18002d6b8  test    rax, rax
0x18002d6bb  jnz     short loc_18002D6C7
0x18002d6bd  mov     eax, 140h
0x18002d6c2  jmp     loc_18002D82C
0x18002d6c7  mov     rcx, [rbx+108h]; hModule
0x18002d6ce  lea     rdx, aMqadqueryqueue; "MQADQueryQueues"
0x18002d6d5  call    cs:__imp_GetProcAddress
0x18002d6db  mov     [rbx+0C0h], rax
0x18002d6e2  test    rax, rax
0x18002d6e5  jnz     short loc_18002D6F1
0x18002d6e7  mov     eax, 14Ah
0x18002d6ec  jmp     loc_18002D82C
0x18002d6f1  mov     rcx, [rbx+108h]; hModule
0x18002d6f8  lea     rdx, aMqadqueryresul; "MQADQueryResults"
0x18002d6ff  call    cs:__imp_GetProcAddress
0x18002d705  mov     [rbx+0C8h], rax
0x18002d70c  test    rax, rax
0x18002d70f  jnz     short loc_18002D71B
0x18002d711  mov     eax, 154h
0x18002d716  jmp     loc_18002D82C
0x18002d71b  mov     rcx, [rbx+108h]; hModule
0x18002d722  lea     rdx, aMqadendquery; "MQADEndQuery"
0x18002d729  call    cs:__imp_GetProcAddress
0x18002d72f  mov     [rbx+0D0h], rax
0x18002d736  test    rax, rax
0x18002d739  jnz     short loc_18002D745
0x18002d73b  mov     eax, 15Eh
0x18002d740  jmp     loc_18002D82C
0x18002d745  mov     rcx, [rbx+108h]; hModule
0x18002d74c  lea     rdx, aMqadgetobjects; "MQADGetObjectSecurity"
0x18002d753  call    cs:__imp_GetProcAddress
0x18002d759  mov     [rbx+0D8h], rax
0x18002d760  test    rax, rax
0x18002d763  jnz     short loc_18002D76F
0x18002d765  mov     eax, 168h
0x18002d76a  jmp     loc_18002D82C
0x18002d76f  mov     rcx, [rbx+108h]; hModule
0x18002d776  lea     rdx, aMqadgetobjects_0; "MQADGetObjectSecurityGuid"
0x18002d77d  call    cs:__imp_GetProcAddress
0x18002d783  mov     [rbx+0E0h], rax
0x18002d78a  test    rax, rax
0x18002d78d  jnz     short loc_18002D799
0x18002d78f  mov     eax, 172h
0x18002d794  jmp     loc_18002D82C
0x18002d799  mov     rcx, [rbx+108h]; hModule
0x18002d7a0  lea     rdx, aMqadsetobjects; "MQADSetObjectSecurity"
0x18002d7a7  call    cs:__imp_GetProcAddress
0x18002d7ad  mov     [rbx+0E8h], rax
0x18002d7b4  test    rax, rax
0x18002d7b7  jnz     short loc_18002D7C0
0x18002d7b9  mov     eax, 17Ch
0x18002d7be  jmp     short loc_18002D82C
0x18002d7c0  mov     rcx, [rbx+108h]; hModule
0x18002d7c7  lea     rdx, aMqadsetobjects_0; "MQADSetObjectSecurityGuid"
0x18002d7ce  call    cs:__imp_GetProcAddress
0x18002d7d4  mov     [rbx+0F0h], rax
0x18002d7db  test    rax, rax
0x18002d7de  jnz     short loc_18002D7E7
0x18002d7e0  mov     eax, 181h
0x18002d7e5  jmp     short loc_18002D82C
0x18002d7e7  mov     rcx, [rbx+108h]; hModule
0x18002d7ee  lea     rdx, aMqadgetadspath; "MQADGetADsPathInfo"
0x18002d7f5  call    cs:__imp_GetProcAddress
0x18002d7fb  mov     [rbx+0F8h], rax
0x18002d802  test    rax, rax
0x18002d805  jz      short loc_18002D827
0x18002d807  mov     rcx, [rbx+108h]; hModule
0x18002d80e  lea     rdx, aMqadfreememory; "MQADFreeMemory"
0x18002d815  call    cs:__imp_GetProcAddress
0x18002d81b  mov     [rbx+100h], rax
0x18002d822  test    rax, rax
0x18002d825  jnz     short loc_18002D8A4
0x18002d827  mov     eax, 182h
0x18002d82c  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, rdi; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18002d833  mov     [rbp+arg_8], 0C00E0043h
0x18002d83a  mov     [rbp+arg_0], ax
0x18002d83e  jz      short loc_18002D89D
0x18002d840  lea     rbx, aAdAdprov; "ad/adprov"
0x18002d847  mov     rcx, rbx; wchar_t *
0x18002d84a  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18002d84f  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18002d856  mov     edx, 1
0x18002d85b  mov     [rsp+60h+var_10], rdi
0x18002d860  mov     r8d, edx
0x18002d863  mov     [rsp+60h+var_18], rdi
  ... truncated ...
```
