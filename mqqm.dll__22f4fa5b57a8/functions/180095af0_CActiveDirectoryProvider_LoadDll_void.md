# CActiveDirectoryProvider::LoadDll(void)

- ea: `0x180095af0`
- end: `0x18009604e`
- name: `?LoadDll@CActiveDirectoryProvider@@AEAAJXZ`
- size: `1374`
- prototype: `__int64 __fastcall(CActiveDirectoryProvider *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180095ab0`

## callees

- `0x18002c61c`
- `0x180095af0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180095b2a`
- `KERNEL32!GetProcAddress` at `0x180095b50`
- `KERNEL32!GetProcAddress` at `0x180095b76`
- `KERNEL32!GetProcAddress` at `0x180095b97`
- `KERNEL32!GetProcAddress` at `0x180095bb8`
- `KERNEL32!GetProcAddress` at `0x180095be0`
- `KERNEL32!GetProcAddress` at `0x180095c08`
- `KERNEL32!GetProcAddress` at `0x180095c30`
- `KERNEL32!GetProcAddress` at `0x180095c58`
- `KERNEL32!GetProcAddress` at `0x180095c80`
- `KERNEL32!GetProcAddress` at `0x180095ca8`
- `KERNEL32!GetProcAddress` at `0x180095cd0`
- `KERNEL32!GetProcAddress` at `0x180095cf8`
- `KERNEL32!GetProcAddress` at `0x180095d20`
- `KERNEL32!GetProcAddress` at `0x180095d48`
- `KERNEL32!GetProcAddress` at `0x180095d70`
- `KERNEL32!GetProcAddress` at `0x180095d9b`
- `KERNEL32!GetProcAddress` at `0x180095dc6`
- `KERNEL32!GetProcAddress` at `0x180095df1`
- `KERNEL32!GetProcAddress` at `0x180095e1c`
- `KERNEL32!GetProcAddress` at `0x180095e47`
- `KERNEL32!GetProcAddress` at `0x180095e72`
- `KERNEL32!GetProcAddress` at `0x180095e9d`
- `KERNEL32!GetProcAddress` at `0x180095ec8`
- `KERNEL32!GetProcAddress` at `0x180095ef3`
- `KERNEL32!GetProcAddress` at `0x180095f1e`
- `KERNEL32!GetProcAddress` at `0x180095f49`
- `KERNEL32!GetProcAddress` at `0x180095f74`
- `KERNEL32!GetProcAddress` at `0x180095f9f`
- `KERNEL32!GetProcAddress` at `0x180095fc7`
- `KERNEL32!GetProcAddress` at `0x180095fef`
- `KERNEL32!GetProcAddress` at `0x18009600f`
- `KERNEL32!GetProcAddress` at `0x180095b2a`
- `KERNEL32!GetProcAddress` at `0x180095b50`
- `KERNEL32!GetProcAddress` at `0x180095b76`
- `KERNEL32!GetProcAddress` at `0x180095b97`
- `KERNEL32!GetProcAddress` at `0x180095bb8`
- `KERNEL32!GetProcAddress` at `0x180095be0`
- `KERNEL32!GetProcAddress` at `0x180095c08`
- `KERNEL32!GetProcAddress` at `0x180095c30`
- `KERNEL32!GetProcAddress` at `0x180095c58`
- `KERNEL32!GetProcAddress` at `0x180095c80`
- `KERNEL32!GetProcAddress` at `0x180095ca8`
- `KERNEL32!GetProcAddress` at `0x180095cd0`
- `KERNEL32!GetProcAddress` at `0x180095cf8`
- `KERNEL32!GetProcAddress` at `0x180095d20`
- `KERNEL32!GetProcAddress` at `0x180095d48`
- `KERNEL32!GetProcAddress` at `0x180095d70`
- `KERNEL32!GetProcAddress` at `0x180095d9b`
- `KERNEL32!GetProcAddress` at `0x180095dc6`
- `KERNEL32!GetProcAddress` at `0x180095df1`
- `KERNEL32!GetProcAddress` at `0x180095e1c`
- `KERNEL32!GetProcAddress` at `0x180095e47`
- `KERNEL32!GetProcAddress` at `0x180095e72`
- `KERNEL32!GetProcAddress` at `0x180095e9d`
- `KERNEL32!GetProcAddress` at `0x180095ec8`
- `KERNEL32!GetProcAddress` at `0x180095ef3`
- `KERNEL32!GetProcAddress` at `0x180095f1e`
- `KERNEL32!GetProcAddress` at `0x180095f49`
- `KERNEL32!GetProcAddress` at `0x180095f74`
- `KERNEL32!GetProcAddress` at `0x180095f9f`
- `KERNEL32!GetProcAddress` at `0x180095fc7`
- `KERNEL32!GetProcAddress` at `0x180095fef`
- `KERNEL32!GetProcAddress` at `0x18009600f`
- `KERNEL32!LoadLibraryW` at `0x180095b00`
- `KERNEL32!LoadLibraryW` at `0x180095b00`

## string_xrefs

- `0x180095af9`: `mqad.dll`
- `0x180095b90`: `MQADDeleteObjectGuidSid`
- `0x180095b6f`: `MQADDeleteObjectGuid`
- `0x180095b49`: `MQADDeleteObject`
- `0x180095b20`: `MQADCreateObject`
- `0x180095c29`: `MQADQMGetObjectSecurity`
- `0x180095cc9`: `MQADGetComputerSites`
- `0x180095d41`: `MQADEndDeleteNotification`
- `0x180095d19`: `MQADNotifyDelete`
- `0x180095cf1`: `MQADBeginDeleteNotification`
- `0x180095e6b`: `MQADQueryAllLinks`
- `0x180095e40`: `MQADQueryLinks`
- `0x180095f6d`: `MQADGetObjectSecurityGuid`
- `0x180095f42`: `MQADGetObjectSecurity`
- `0x180095fe8`: `MQADGetADsPathInfo`
- `0x180095fc0`: `MQADSetObjectSecurityGuid`
- `0x180095f98`: `MQADSetObjectSecurity`

## pseudocode

```c
__int64 __fastcall CActiveDirectoryProvider::LoadDll(CActiveDirectoryProvider *this)
{
  HMODULE LibraryW; // rax
  unsigned __int16 v3; // r8
  unsigned int v4; // ebx
  FARPROC ProcAddress; // rax
  FARPROC v6; // rax
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

  LibraryW = LoadLibraryW(L"mqad.dll");
  *((_QWORD *)this + 33) = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "MQADCreateObject");
    *((_QWORD *)this + 1) = ProcAddress;
    if ( ProcAddress )
    {
      v6 = GetProcAddress(*((HMODULE *)this + 33), "MQADDeleteObject");
      *((_QWORD *)this + 2) = v6;
      if ( v6 )
      {
        v7 = GetProcAddress(*((HMODULE *)this + 33), "MQADDeleteObjectGuid");
        *((_QWORD *)this + 3) = v7;
        if ( v7
          && (v8 = GetProcAddress(*((HMODULE *)this + 33), "MQADDeleteObjectGuidSid"), (*((_QWORD *)this + 4) = v8) != 0) )
        {
          v9 = GetProcAddress(*((HMODULE *)this + 33), "MQADGetObjectProperties");
          *((_QWORD *)this + 5) = v9;
          if ( v9 )
          {
            v10 = GetProcAddress(*((HMODULE *)this + 33), "MQADGetGenObjectProperties");
            *((_QWORD *)this + 6) = v10;
            if ( v10 )
            {
              v11 = GetProcAddress(*((HMODULE *)this + 33), "MQADGetObjectPropertiesGuid");
              *((_QWORD *)this + 7) = v11;
              if ( v11 )
              {
                v12 = GetProcAddress(*((HMODULE *)this + 33), "MQADQMGetObjectSecurity");
                *((_QWORD *)this + 8) = v12;
                if ( v12 )
                {
                  v13 = GetProcAddress(*((HMODULE *)this + 33), "MQADSetObjectProperties");
                  *((_QWORD *)this + 9) = v13;
                  if ( v13 )
                  {
                    v14 = GetProcAddress(*((HMODULE *)this + 33), "MQADSetObjectPropertiesGuid");
                    *((_QWORD *)this + 10) = v14;
                    if ( v14 )
                    {
                      v15 = GetProcAddress(*((HMODULE *)this + 33), "MQADInit");
                      *((_QWORD *)this + 11) = v15;
                      if ( v15 )
                      {
                        v16 = GetProcAddress(*((HMODULE *)this + 33), "MQADGetComputerSites");
                        *((_QWORD *)this + 12) = v16;
                        if ( v16 )
                        {
                          v17 = GetProcAddress(*((HMODULE *)this + 33), "MQADBeginDeleteNotification");
                          *((_QWORD *)this + 13) = v17;
                          if ( v17 )
                          {
                            v18 = GetProcAddress(*((HMODULE *)this + 33), "MQADNotifyDelete");
                            *((_QWORD *)this + 14) = v18;
                            if ( v18 )
                            {
                              v19 = GetProcAddress(*((HMODULE *)this + 33), "MQADEndDeleteNotification");
                              *((_QWORD *)this + 15) = v19;
                              if ( v19 )
                              {
                                v20 = GetProcAddress(*((HMODULE *)this + 33), "MQADQueryMachineQueues");
                                *((_QWORD *)this + 16) = v20;
                                if ( v20 )
                                {
                                  v21 = GetProcAddress(*((HMODULE *)this + 33), "MQADQuerySiteServers");
                                  *((_QWORD *)this + 17) = v21;
                                  if ( v21 )
                                  {
                                    v22 = GetProcAddress(*((HMODULE *)this + 33), "MQADQueryUserCert");
                                    *((_QWORD *)this + 18) = v22;
                                    if ( v22 )
                                    {
                                      v23 = GetProcAddress(*((HMODULE *)this + 33), "MQADQueryConnectors");
                                      *((_QWORD *)this + 19) = v23;
                                      if ( v23 )
                                      {
                                        v24 = GetProcAddress(*((HMODULE *)this + 33), "MQADQueryForeignSites");
                                        *((_QWORD *)this + 20) = v24;
                                        if ( v24 )
                                        {
                                          v25 = GetProcAddress(*((HMODULE *)this + 33), "MQADQueryLinks");
                                          *((_QWORD *)this + 21) = v25;
                                          if ( v25 )
                                          {
                                            v26 = GetProcAddress(*((HMODULE *)this + 33), "MQADQueryAllLinks");
                                            *((_QWORD *)this + 22) = v26;
                                            if ( v26 )
                                            {
                                              v27 = GetProcAddress(*((HMODULE *)this + 33), "MQADQueryAllSites");
                                              *((_QWORD *)this + 23) = v27;
                                              if ( v27 )
                                              {
                                                v28 = GetProcAddress(*((HMODULE *)this + 33), "MQADQueryQueues");
                                                *((_QWORD *)this + 24) = v28;
                                                if ( v28 )
                                                {
                                                  v29 = GetProcAddress(*((HMODULE *)this + 33), "MQADQueryResults");
                                                  *((_QWORD *)this + 25) = v29;
                                                  if ( v29 )
                                                  {
                                                    v30 = GetProcAddress(*((HMODULE *)this + 33), "MQADEndQuery");
                                                    *((_QWORD *)this + 26) = v30;
                                                    if ( v30 )
                                                    {
                                                      v31 = GetProcAddress(
                                                              *((HMODULE *)this + 33),
                                                              "MQADGetObjectSecurity");
                                                      *((_QWORD *)this + 27) = v31;
                                                      if ( v31 )
                                                      {
                                                        v32 = GetProcAddress(
                                                                *((HMODULE *)this + 33),
                                                                "MQADGetObjectSecurityGuid");
                                                        *((_QWORD *)this + 28) = v32;
                                                        if ( v32 )
                                                        {
                                                          v33 = GetProcAddress(
                                                                  *((HMODULE *)this + 33),
                                                                  "MQADSetObjectSecurity");
                                                          *((_QWORD *)this + 29) = v33;
                                                          if ( v33 )
                                                          {
                                                            v34 = GetProcAddress(
                                                                    *((HMODULE *)this + 33),
                                                                    "MQADSetObjectSecurityGuid");
                                                            *((_QWORD *)this + 30) = v34;
                                                            if ( v34 )
                                                            {
                                                              v35 = GetProcAddress(
                                                                      *((HMODULE *)this + 33),
                                                                      "MQADGetADsPathInfo");
                                                              *((_QWORD *)this + 31) = v35;
                                                              if ( v35 )
                                                              {
                                                                v36 = GetProcAddress(
                                                                        *((HMODULE *)this + 33),
                                                                        "MQADFreeMemory");
                                                                *((_QWORD *)this + 32) = v36;
                                                                if ( v36 )
                                                                  return 0;
                                                              }
                                                              v3 = 386;
                                                            }
                                                            else
                                                            {
                                                              v3 = 385;
                                                            }
                                                          }
                                                          else
                                                          {
                                                            v3 = 380;
                                                          }
                                                        }
                                                        else
                                                        {
                                                          v3 = 370;
                                                        }
                                                      }
                                                      else
                                                      {
                                                        v3 = 360;
                                                      }
                                                    }
                                                    else
                                                    {
                                                      v3 = 350;
                                                    }
                                                  }
                                                  else
                                                  {
                                                    v3 = 340;
                                                  }
                                                }
                                                else
                                                {
                                                  v3 = 330;
                                                }
                                              }
                                              else
                                              {
                                                v3 = 320;
                                              }
                                            }
                                            else
                                            {
                                              v3 = 310;
                                            }
                                          }
                                          else
                                          {
                                            v3 = 300;
                                          }
                                        }
                                        else
                                        {
                                          v3 = 290;
                                        }
                                      }
                                      else
                                      {
                                        v3 = 280;
                                      }
                                    }
                                    else
                                    {
                                      v3 = 270;
                                    }
                                  }
                                  else
                                  {
                                    v3 = 260;
                                  }
                                }
                                else
                                {
                                  v3 = 250;
                                }
                              }
                              else
                              {
                                v3 = 240;
                              }
                            }
                            else
                            {
                              v3 = 230;
                            }
                          }
                          else
                          {
                            v3 = 220;
                          }
                        }
                        else
                        {
                          v3 = 210;
                        }
                      }
                      else
                      {
                        v3 = 190;
                      }
                    }
                    else
                    {
                      v3 = 170;
                    }
                  }
                  else
                  {
                    v3 = 160;
                  }
                }
                else
                {
                  v3 = 150;
                }
              }
              else
              {
                v3 = 140;
              }
            }
            else
            {
              v3 = 135;
            }
          }
          else
          {
            v3 = 130;
          }
        }
        else
        {
          v3 = 120;
        }
      }
      else
      {
        v3 = 110;
      }
    }
    else
    {
      v3 = 100;
    }
    v4 = -1072824253;
  }
  else
  {
    v3 = 10;
    v4 = -1072824187;
  }
  LogMsgHR(v4, (wchar_t *)L"ad/adprov", v3);
  return v4;
}

```

## disassembly

```asm
0x180095af0  push    rbx
0x180095af2  sub     rsp, 20h
0x180095af6  mov     rbx, rcx
0x180095af9  lea     rcx, aMqadDll; "mqad.dll"
0x180095b00  call    cs:__imp_LoadLibraryW
0x180095b06  mov     [rbx+108h], rax
0x180095b0d  test    rax, rax
0x180095b10  jnz     short loc_180095B20
0x180095b12  lea     r8d, [rax+0Ah]
0x180095b16  mov     ebx, 0C00E0085h
0x180095b1b  jmp     loc_180096038
0x180095b20  lea     rdx, aMqadcreateobje; "MQADCreateObject"
0x180095b27  mov     rcx, rax; hModule
0x180095b2a  call    cs:__imp_GetProcAddress
0x180095b30  mov     [rbx+8], rax
0x180095b34  test    rax, rax
0x180095b37  jnz     short loc_180095B42
0x180095b39  lea     r8d, [rax+64h]
0x180095b3d  jmp     loc_180096033
0x180095b42  mov     rcx, [rbx+108h]; hModule
0x180095b49  lea     rdx, aMqaddeleteobje; "MQADDeleteObject"
0x180095b50  call    cs:__imp_GetProcAddress
0x180095b56  mov     [rbx+10h], rax
0x180095b5a  test    rax, rax
0x180095b5d  jnz     short loc_180095B68
0x180095b5f  lea     r8d, [rax+6Eh]
0x180095b63  jmp     loc_180096033
0x180095b68  mov     rcx, [rbx+108h]; hModule
0x180095b6f  lea     rdx, aMqaddeleteobje_1; "MQADDeleteObjectGuid"
0x180095b76  call    cs:__imp_GetProcAddress
0x180095b7c  mov     [rbx+18h], rax
0x180095b80  test    rax, rax
0x180095b83  jz      loc_18009602D
0x180095b89  mov     rcx, [rbx+108h]; hModule
0x180095b90  lea     rdx, aMqaddeleteobje_0; "MQADDeleteObjectGuidSid"
0x180095b97  call    cs:__imp_GetProcAddress
0x180095b9d  mov     [rbx+20h], rax
0x180095ba1  test    rax, rax
0x180095ba4  jz      loc_18009602D
0x180095baa  mov     rcx, [rbx+108h]; hModule
0x180095bb1  lea     rdx, aMqadgetobjectp_0; "MQADGetObjectProperties"
0x180095bb8  call    cs:__imp_GetProcAddress
0x180095bbe  mov     [rbx+28h], rax
0x180095bc2  test    rax, rax
0x180095bc5  jnz     short loc_180095BD2
0x180095bc7  mov     r8d, 82h
0x180095bcd  jmp     loc_180096033
0x180095bd2  mov     rcx, [rbx+108h]; hModule
0x180095bd9  lea     rdx, aMqadgetgenobje; "MQADGetGenObjectProperties"
0x180095be0  call    cs:__imp_GetProcAddress
0x180095be6  mov     [rbx+30h], rax
0x180095bea  test    rax, rax
0x180095bed  jnz     short loc_180095BFA
0x180095bef  mov     r8d, 87h
0x180095bf5  jmp     loc_180096033
0x180095bfa  mov     rcx, [rbx+108h]; hModule
0x180095c01  lea     rdx, aMqadgetobjectp; "MQADGetObjectPropertiesGuid"
0x180095c08  call    cs:__imp_GetProcAddress
0x180095c0e  mov     [rbx+38h], rax
0x180095c12  test    rax, rax
0x180095c15  jnz     short loc_180095C22
0x180095c17  mov     r8d, 8Ch
0x180095c1d  jmp     loc_180096033
0x180095c22  mov     rcx, [rbx+108h]; hModule
0x180095c29  lea     rdx, aMqadqmgetobjec; "MQADQMGetObjectSecurity"
0x180095c30  call    cs:__imp_GetProcAddress
0x180095c36  mov     [rbx+40h], rax
0x180095c3a  test    rax, rax
0x180095c3d  jnz     short loc_180095C4A
0x180095c3f  mov     r8d, 96h
0x180095c45  jmp     loc_180096033
0x180095c4a  mov     rcx, [rbx+108h]; hModule
0x180095c51  lea     rdx, aMqadsetobjectp; "MQADSetObjectProperties"
0x180095c58  call    cs:__imp_GetProcAddress
0x180095c5e  mov     [rbx+48h], rax
0x180095c62  test    rax, rax
0x180095c65  jnz     short loc_180095C72
0x180095c67  mov     r8d, 0A0h
0x180095c6d  jmp     loc_180096033
0x180095c72  mov     rcx, [rbx+108h]; hModule
0x180095c79  lea     rdx, aMqadsetobjectp_0; "MQADSetObjectPropertiesGuid"
0x180095c80  call    cs:__imp_GetProcAddress
0x180095c86  mov     [rbx+50h], rax
0x180095c8a  test    rax, rax
0x180095c8d  jnz     short loc_180095C9A
0x180095c8f  mov     r8d, 0AAh
0x180095c95  jmp     loc_180096033
0x180095c9a  mov     rcx, [rbx+108h]; hModule
0x180095ca1  lea     rdx, aMqadinit; "MQADInit"
0x180095ca8  call    cs:__imp_GetProcAddress
0x180095cae  mov     [rbx+58h], rax
0x180095cb2  test    rax, rax
0x180095cb5  jnz     short loc_180095CC2
0x180095cb7  mov     r8d, 0BEh
0x180095cbd  jmp     loc_180096033
0x180095cc2  mov     rcx, [rbx+108h]; hModule
0x180095cc9  lea     rdx, aMqadgetcompute; "MQADGetComputerSites"
0x180095cd0  call    cs:__imp_GetProcAddress
0x180095cd6  mov     [rbx+60h], rax
0x180095cda  test    rax, rax
0x180095cdd  jnz     short loc_180095CEA
0x180095cdf  mov     r8d, 0D2h
0x180095ce5  jmp     loc_180096033
0x180095cea  mov     rcx, [rbx+108h]; hModule
0x180095cf1  lea     rdx, aMqadbegindelet; "MQADBeginDeleteNotification"
0x180095cf8  call    cs:__imp_GetProcAddress
0x180095cfe  mov     [rbx+68h], rax
0x180095d02  test    rax, rax
0x180095d05  jnz     short loc_180095D12
0x180095d07  mov     r8d, 0DCh
0x180095d0d  jmp     loc_180096033
0x180095d12  mov     rcx, [rbx+108h]; hModule
0x180095d19  lea     rdx, aMqadnotifydele; "MQADNotifyDelete"
0x180095d20  call    cs:__imp_GetProcAddress
0x180095d26  mov     [rbx+70h], rax
0x180095d2a  test    rax, rax
0x180095d2d  jnz     short loc_180095D3A
0x180095d2f  mov     r8d, 0E6h
0x180095d35  jmp     loc_180096033
0x180095d3a  mov     rcx, [rbx+108h]; hModule
0x180095d41  lea     rdx, aMqadenddeleten; "MQADEndDeleteNotification"
0x180095d48  call    cs:__imp_GetProcAddress
0x180095d4e  mov     [rbx+78h], rax
0x180095d52  test    rax, rax
0x180095d55  jnz     short loc_180095D62
0x180095d57  mov     r8d, 0F0h
0x180095d5d  jmp     loc_180096033
0x180095d62  mov     rcx, [rbx+108h]; hModule
0x180095d69  lea     rdx, aMqadquerymachi; "MQADQueryMachineQueues"
0x180095d70  call    cs:__imp_GetProcAddress
0x180095d76  mov     [rbx+80h], rax
0x180095d7d  test    rax, rax
0x180095d80  jnz     short loc_180095D8D
0x180095d82  mov     r8d, 0FAh
0x180095d88  jmp     loc_180096033
0x180095d8d  mov     rcx, [rbx+108h]; hModule
0x180095d94  lea     rdx, aMqadquerysites; "MQADQuerySiteServers"
0x180095d9b  call    cs:__imp_GetProcAddress
0x180095da1  mov     [rbx+88h], rax
0x180095da8  test    rax, rax
0x180095dab  jnz     short loc_180095DB8
0x180095dad  mov     r8d, 104h
0x180095db3  jmp     loc_180096033
0x180095db8  mov     rcx, [rbx+108h]; hModule
0x180095dbf  lea     rdx, aMqadqueryuserc; "MQADQueryUserCert"
0x180095dc6  call    cs:__imp_GetProcAddress
0x180095dcc  mov     [rbx+90h], rax
0x180095dd3  test    rax, rax
0x180095dd6  jnz     short loc_180095DE3
0x180095dd8  mov     r8d, 10Eh
0x180095dde  jmp     loc_180096033
0x180095de3  mov     rcx, [rbx+108h]; hModule
0x180095dea  lea     rdx, aMqadqueryconne; "MQADQueryConnectors"
0x180095df1  call    cs:__imp_GetProcAddress
0x180095df7  mov     [rbx+98h], rax
0x180095dfe  test    rax, rax
0x180095e01  jnz     short loc_180095E0E
0x180095e03  mov     r8d, 118h
0x180095e09  jmp     loc_180096033
0x180095e0e  mov     rcx, [rbx+108h]; hModule
0x180095e15  lea     rdx, aMqadqueryforei; "MQADQueryForeignSites"
0x180095e1c  call    cs:__imp_GetProcAddress
0x180095e22  mov     [rbx+0A0h], rax
0x180095e29  test    rax, rax
0x180095e2c  jnz     short loc_180095E39
0x180095e2e  mov     r8d, 122h
0x180095e34  jmp     loc_180096033
0x180095e39  mov     rcx, [rbx+108h]; hModule
0x180095e40  lea     rdx, aMqadquerylinks; "MQADQueryLinks"
0x180095e47  call    cs:__imp_GetProcAddress
0x180095e4d  mov     [rbx+0A8h], rax
0x180095e54  test    rax, rax
0x180095e57  jnz     short loc_180095E64
0x180095e59  mov     r8d, 12Ch
0x180095e5f  jmp     loc_180096033
0x180095e64  mov     rcx, [rbx+108h]; hModule
0x180095e6b  lea     rdx, aMqadqueryallli; "MQADQueryAllLinks"
0x180095e72  call    cs:__imp_GetProcAddress
0x180095e78  mov     [rbx+0B0h], rax
0x180095e7f  test    rax, rax
0x180095e82  jnz     short loc_180095E8F
0x180095e84  mov     r8d, 136h
0x180095e8a  jmp     loc_180096033
0x180095e8f  mov     rcx, [rbx+108h]; hModule
0x180095e96  lea     rdx, aMqadqueryallsi; "MQADQueryAllSites"
0x180095e9d  call    cs:__imp_GetProcAddress
0x180095ea3  mov     [rbx+0B8h], rax
0x180095eaa  test    rax, rax
0x180095ead  jnz     short loc_180095EBA
0x180095eaf  mov     r8d, 140h
0x180095eb5  jmp     loc_180096033
0x180095eba  mov     rcx, [rbx+108h]; hModule
0x180095ec1  lea     rdx, aMqadqueryqueue; "MQADQueryQueues"
0x180095ec8  call    cs:__imp_GetProcAddress
0x180095ece  mov     [rbx+0C0h], rax
0x180095ed5  test    rax, rax
0x180095ed8  jnz     short loc_180095EE5
0x180095eda  mov     r8d, 14Ah
0x180095ee0  jmp     loc_180096033
0x180095ee5  mov     rcx, [rbx+108h]; hModule
0x180095eec  lea     rdx, aMqadqueryresul; "MQADQueryResults"
0x180095ef3  call    cs:__imp_GetProcAddress
0x180095ef9  mov     [rbx+0C8h], rax
0x180095f00  test    rax, rax
0x180095f03  jnz     short loc_180095F10
0x180095f05  mov     r8d, 154h
0x180095f0b  jmp     loc_180096033
0x180095f10  mov     rcx, [rbx+108h]; hModule
0x180095f17  lea     rdx, aMqadendquery; "MQADEndQuery"
0x180095f1e  call    cs:__imp_GetProcAddress
0x180095f24  mov     [rbx+0D0h], rax
0x180095f2b  test    rax, rax
0x180095f2e  jnz     short loc_180095F3B
0x180095f30  mov     r8d, 15Eh
0x180095f36  jmp     loc_180096033
0x180095f3b  mov     rcx, [rbx+108h]; hModule
0x180095f42  lea     rdx, aMqadgetobjects; "MQADGetObjectSecurity"
0x180095f49  call    cs:__imp_GetProcAddress
0x180095f4f  mov     [rbx+0D8h], rax
0x180095f56  test    rax, rax
0x180095f59  jnz     short loc_180095F66
0x180095f5b  mov     r8d, 168h
0x180095f61  jmp     loc_180096033
0x180095f66  mov     rcx, [rbx+108h]; hModule
0x180095f6d  lea     rdx, aMqadgetobjects_0; "MQADGetObjectSecurityGuid"
0x180095f74  call    cs:__imp_GetProcAddress
0x180095f7a  mov     [rbx+0E0h], rax
0x180095f81  test    rax, rax
0x180095f84  jnz     short loc_180095F91
0x180095f86  mov     r8d, 172h
0x180095f8c  jmp     loc_180096033
0x180095f91  mov     rcx, [rbx+108h]; hModule
0x180095f98  lea     rdx, aMqadsetobjects; "MQADSetObjectSecurity"
0x180095f9f  call    cs:__imp_GetProcAddress
0x180095fa5  mov     [rbx+0E8h], rax
0x180095fac  test    rax, rax
0x180095faf  jnz     short loc_180095FB9
0x180095fb1  mov     r8d, 17Ch
0x180095fb7  jmp     short loc_180096033
0x180095fb9  mov     rcx, [rbx+108h]; hModule
0x180095fc0  lea     rdx, aMqadsetobjects_0; "MQADSetObjectSecurityGuid"
0x180095fc7  call    cs:__imp_GetProcAddress
0x180095fcd  mov     [rbx+0F0h], rax
0x180095fd4  test    rax, rax
0x180095fd7  jnz     short loc_180095FE1
0x180095fd9  mov     r8d, 181h
0x180095fdf  jmp     short loc_180096033
0x180095fe1  mov     rcx, [rbx+108h]; hModule
0x180095fe8  lea     rdx, aMqadgetadspath; "MQADGetADsPathInfo"
0x180095fef  call    cs:__imp_GetProcAddress
0x180095ff5  mov     [rbx+0F8h], rax
0x180095ffc  test    rax, rax
0x180095fff  jz      short loc_180096025
0x180096001  mov     rcx, [rbx+108h]; hModule
0x180096008  lea     rdx, aMqadfreememory; "MQADFreeMemory"
0x18009600f  call    cs:__imp_GetProcAddress
0x180096015  mov     [rbx+100h], rax
0x18009601c  test    rax, rax
0x18009601f  jz      short loc_180096025
0x180096021  xor     eax, eax
0x180096023  jmp     short loc_180096048
0x180096025  mov     r8d, 182h
0x18009602b  jmp     short loc_180096033
0x18009602d  mov     r8d, 78h ; 'x'; unsigned __int16
0x180096033  mov     ebx, 0C00E0043h
0x180096038  lea     rdx, aAdAdprov; "ad/adprov"
0x18009603f  mov     ecx, ebx; int
0x180096041  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180096046  mov     eax, ebx
0x180096048  add     rsp, 20h
0x18009604c  pop     rbx
0x18009604d  retn
```
