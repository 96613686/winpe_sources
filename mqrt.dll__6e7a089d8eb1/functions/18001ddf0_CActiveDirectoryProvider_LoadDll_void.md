# CActiveDirectoryProvider::LoadDll(void)

- ea: `0x18001ddf0`
- end: `0x18001e34e`
- name: `?LoadDll@CActiveDirectoryProvider@@AEAAJXZ`
- size: `1374`
- prototype: `__int64 __fastcall(CActiveDirectoryProvider *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001ddb0`

## callees

- `0x180013c74`
- `0x18001ddf0`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x18001de00`
- `KERNEL32!LoadLibraryW` at `0x18001de00`
- `KERNEL32!GetProcAddress` at `0x18001de2a`
- `KERNEL32!GetProcAddress` at `0x18001de50`
- `KERNEL32!GetProcAddress` at `0x18001de76`
- `KERNEL32!GetProcAddress` at `0x18001de97`
- `KERNEL32!GetProcAddress` at `0x18001deb8`
- `KERNEL32!GetProcAddress` at `0x18001dee0`
- `KERNEL32!GetProcAddress` at `0x18001df08`
- `KERNEL32!GetProcAddress` at `0x18001df30`
- `KERNEL32!GetProcAddress` at `0x18001df58`
- `KERNEL32!GetProcAddress` at `0x18001df80`
- `KERNEL32!GetProcAddress` at `0x18001dfa8`
- `KERNEL32!GetProcAddress` at `0x18001dfd0`
- `KERNEL32!GetProcAddress` at `0x18001dff8`
- `KERNEL32!GetProcAddress` at `0x18001e020`
- `KERNEL32!GetProcAddress` at `0x18001e048`
- `KERNEL32!GetProcAddress` at `0x18001e070`
- `KERNEL32!GetProcAddress` at `0x18001e09b`
- `KERNEL32!GetProcAddress` at `0x18001e0c6`
- `KERNEL32!GetProcAddress` at `0x18001e0f1`
- `KERNEL32!GetProcAddress` at `0x18001e11c`
- `KERNEL32!GetProcAddress` at `0x18001e147`
- `KERNEL32!GetProcAddress` at `0x18001e172`
- `KERNEL32!GetProcAddress` at `0x18001e19d`
- `KERNEL32!GetProcAddress` at `0x18001e1c8`
- `KERNEL32!GetProcAddress` at `0x18001e1f3`
- `KERNEL32!GetProcAddress` at `0x18001e21e`
- `KERNEL32!GetProcAddress` at `0x18001e249`
- `KERNEL32!GetProcAddress` at `0x18001e274`
- `KERNEL32!GetProcAddress` at `0x18001e29f`
- `KERNEL32!GetProcAddress` at `0x18001e2c7`
- `KERNEL32!GetProcAddress` at `0x18001e2ef`
- `KERNEL32!GetProcAddress` at `0x18001e30f`
- `KERNEL32!GetProcAddress` at `0x18001de2a`
- `KERNEL32!GetProcAddress` at `0x18001de50`
- `KERNEL32!GetProcAddress` at `0x18001de76`
- `KERNEL32!GetProcAddress` at `0x18001de97`
- `KERNEL32!GetProcAddress` at `0x18001deb8`
- `KERNEL32!GetProcAddress` at `0x18001dee0`
- `KERNEL32!GetProcAddress` at `0x18001df08`
- `KERNEL32!GetProcAddress` at `0x18001df30`
- `KERNEL32!GetProcAddress` at `0x18001df58`
- `KERNEL32!GetProcAddress` at `0x18001df80`
- `KERNEL32!GetProcAddress` at `0x18001dfa8`
- `KERNEL32!GetProcAddress` at `0x18001dfd0`
- `KERNEL32!GetProcAddress` at `0x18001dff8`
- `KERNEL32!GetProcAddress` at `0x18001e020`
- `KERNEL32!GetProcAddress` at `0x18001e048`
- `KERNEL32!GetProcAddress` at `0x18001e070`
- `KERNEL32!GetProcAddress` at `0x18001e09b`
- `KERNEL32!GetProcAddress` at `0x18001e0c6`
- `KERNEL32!GetProcAddress` at `0x18001e0f1`
- `KERNEL32!GetProcAddress` at `0x18001e11c`
- `KERNEL32!GetProcAddress` at `0x18001e147`
- `KERNEL32!GetProcAddress` at `0x18001e172`
- `KERNEL32!GetProcAddress` at `0x18001e19d`
- `KERNEL32!GetProcAddress` at `0x18001e1c8`
- `KERNEL32!GetProcAddress` at `0x18001e1f3`
- `KERNEL32!GetProcAddress` at `0x18001e21e`
- `KERNEL32!GetProcAddress` at `0x18001e249`
- `KERNEL32!GetProcAddress` at `0x18001e274`
- `KERNEL32!GetProcAddress` at `0x18001e29f`
- `KERNEL32!GetProcAddress` at `0x18001e2c7`
- `KERNEL32!GetProcAddress` at `0x18001e2ef`
- `KERNEL32!GetProcAddress` at `0x18001e30f`

## string_xrefs

- `0x18001ddf9`: `mqad.dll`
- `0x18001de20`: `MQADCreateObject`
- `0x18001de49`: `MQADDeleteObject`
- `0x18001de6f`: `MQADDeleteObjectGuid`
- `0x18001de90`: `MQADDeleteObjectGuidSid`
- `0x18001df29`: `MQADQMGetObjectSecurity`
- `0x18001dfc9`: `MQADGetComputerSites`
- `0x18001dff1`: `MQADBeginDeleteNotification`
- `0x18001e019`: `MQADNotifyDelete`
- `0x18001e041`: `MQADEndDeleteNotification`
- `0x18001e140`: `MQADQueryLinks`
- `0x18001e16b`: `MQADQueryAllLinks`
- `0x18001e242`: `MQADGetObjectSecurity`
- `0x18001e26d`: `MQADGetObjectSecurityGuid`
- `0x18001e298`: `MQADSetObjectSecurity`
- `0x18001e2c0`: `MQADSetObjectSecurityGuid`
- `0x18001e2e8`: `MQADGetADsPathInfo`

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
0x18001ddf0  push    rbx
0x18001ddf2  sub     rsp, 20h
0x18001ddf6  mov     rbx, rcx
0x18001ddf9  lea     rcx, LibFileName; "mqad.dll"
0x18001de00  call    cs:__imp_LoadLibraryW
0x18001de06  mov     [rbx+108h], rax
0x18001de0d  test    rax, rax
0x18001de10  jnz     short loc_18001DE20
0x18001de12  lea     r8d, [rax+0Ah]
0x18001de16  mov     ebx, 0C00E0085h
0x18001de1b  jmp     loc_18001E338
0x18001de20  lea     rdx, aMqadcreateobje; "MQADCreateObject"
0x18001de27  mov     rcx, rax; hModule
0x18001de2a  call    cs:__imp_GetProcAddress
0x18001de30  mov     [rbx+8], rax
0x18001de34  test    rax, rax
0x18001de37  jnz     short loc_18001DE42
0x18001de39  lea     r8d, [rax+64h]
0x18001de3d  jmp     loc_18001E333
0x18001de42  mov     rcx, [rbx+108h]; hModule
0x18001de49  lea     rdx, aMqaddeleteobje; "MQADDeleteObject"
0x18001de50  call    cs:__imp_GetProcAddress
0x18001de56  mov     [rbx+10h], rax
0x18001de5a  test    rax, rax
0x18001de5d  jnz     short loc_18001DE68
0x18001de5f  lea     r8d, [rax+6Eh]
0x18001de63  jmp     loc_18001E333
0x18001de68  mov     rcx, [rbx+108h]; hModule
0x18001de6f  lea     rdx, aMqaddeleteobje_1; "MQADDeleteObjectGuid"
0x18001de76  call    cs:__imp_GetProcAddress
0x18001de7c  mov     [rbx+18h], rax
0x18001de80  test    rax, rax
0x18001de83  jz      loc_18001E32D
0x18001de89  mov     rcx, [rbx+108h]; hModule
0x18001de90  lea     rdx, aMqaddeleteobje_0; "MQADDeleteObjectGuidSid"
0x18001de97  call    cs:__imp_GetProcAddress
0x18001de9d  mov     [rbx+20h], rax
0x18001dea1  test    rax, rax
0x18001dea4  jz      loc_18001E32D
0x18001deaa  mov     rcx, [rbx+108h]; hModule
0x18001deb1  lea     rdx, aMqadgetobjectp_0; "MQADGetObjectProperties"
0x18001deb8  call    cs:__imp_GetProcAddress
0x18001debe  mov     [rbx+28h], rax
0x18001dec2  test    rax, rax
0x18001dec5  jnz     short loc_18001DED2
0x18001dec7  mov     r8d, 82h
0x18001decd  jmp     loc_18001E333
0x18001ded2  mov     rcx, [rbx+108h]; hModule
0x18001ded9  lea     rdx, aMqadgetgenobje; "MQADGetGenObjectProperties"
0x18001dee0  call    cs:__imp_GetProcAddress
0x18001dee6  mov     [rbx+30h], rax
0x18001deea  test    rax, rax
0x18001deed  jnz     short loc_18001DEFA
0x18001deef  mov     r8d, 87h
0x18001def5  jmp     loc_18001E333
0x18001defa  mov     rcx, [rbx+108h]; hModule
0x18001df01  lea     rdx, aMqadgetobjectp; "MQADGetObjectPropertiesGuid"
0x18001df08  call    cs:__imp_GetProcAddress
0x18001df0e  mov     [rbx+38h], rax
0x18001df12  test    rax, rax
0x18001df15  jnz     short loc_18001DF22
0x18001df17  mov     r8d, 8Ch
0x18001df1d  jmp     loc_18001E333
0x18001df22  mov     rcx, [rbx+108h]; hModule
0x18001df29  lea     rdx, aMqadqmgetobjec; "MQADQMGetObjectSecurity"
0x18001df30  call    cs:__imp_GetProcAddress
0x18001df36  mov     [rbx+40h], rax
0x18001df3a  test    rax, rax
0x18001df3d  jnz     short loc_18001DF4A
0x18001df3f  mov     r8d, 96h
0x18001df45  jmp     loc_18001E333
0x18001df4a  mov     rcx, [rbx+108h]; hModule
0x18001df51  lea     rdx, aMqadsetobjectp; "MQADSetObjectProperties"
0x18001df58  call    cs:__imp_GetProcAddress
0x18001df5e  mov     [rbx+48h], rax
0x18001df62  test    rax, rax
0x18001df65  jnz     short loc_18001DF72
0x18001df67  mov     r8d, 0A0h
0x18001df6d  jmp     loc_18001E333
0x18001df72  mov     rcx, [rbx+108h]; hModule
0x18001df79  lea     rdx, aMqadsetobjectp_0; "MQADSetObjectPropertiesGuid"
0x18001df80  call    cs:__imp_GetProcAddress
0x18001df86  mov     [rbx+50h], rax
0x18001df8a  test    rax, rax
0x18001df8d  jnz     short loc_18001DF9A
0x18001df8f  mov     r8d, 0AAh
0x18001df95  jmp     loc_18001E333
0x18001df9a  mov     rcx, [rbx+108h]; hModule
0x18001dfa1  lea     rdx, aMqadinit; "MQADInit"
0x18001dfa8  call    cs:__imp_GetProcAddress
0x18001dfae  mov     [rbx+58h], rax
0x18001dfb2  test    rax, rax
0x18001dfb5  jnz     short loc_18001DFC2
0x18001dfb7  mov     r8d, 0BEh
0x18001dfbd  jmp     loc_18001E333
0x18001dfc2  mov     rcx, [rbx+108h]; hModule
0x18001dfc9  lea     rdx, aMqadgetcompute; "MQADGetComputerSites"
0x18001dfd0  call    cs:__imp_GetProcAddress
0x18001dfd6  mov     [rbx+60h], rax
0x18001dfda  test    rax, rax
0x18001dfdd  jnz     short loc_18001DFEA
0x18001dfdf  mov     r8d, 0D2h
0x18001dfe5  jmp     loc_18001E333
0x18001dfea  mov     rcx, [rbx+108h]; hModule
0x18001dff1  lea     rdx, aMqadbegindelet; "MQADBeginDeleteNotification"
0x18001dff8  call    cs:__imp_GetProcAddress
0x18001dffe  mov     [rbx+68h], rax
0x18001e002  test    rax, rax
0x18001e005  jnz     short loc_18001E012
0x18001e007  mov     r8d, 0DCh
0x18001e00d  jmp     loc_18001E333
0x18001e012  mov     rcx, [rbx+108h]; hModule
0x18001e019  lea     rdx, aMqadnotifydele; "MQADNotifyDelete"
0x18001e020  call    cs:__imp_GetProcAddress
0x18001e026  mov     [rbx+70h], rax
0x18001e02a  test    rax, rax
0x18001e02d  jnz     short loc_18001E03A
0x18001e02f  mov     r8d, 0E6h
0x18001e035  jmp     loc_18001E333
0x18001e03a  mov     rcx, [rbx+108h]; hModule
0x18001e041  lea     rdx, aMqadenddeleten; "MQADEndDeleteNotification"
0x18001e048  call    cs:__imp_GetProcAddress
0x18001e04e  mov     [rbx+78h], rax
0x18001e052  test    rax, rax
0x18001e055  jnz     short loc_18001E062
0x18001e057  mov     r8d, 0F0h
0x18001e05d  jmp     loc_18001E333
0x18001e062  mov     rcx, [rbx+108h]; hModule
0x18001e069  lea     rdx, aMqadquerymachi; "MQADQueryMachineQueues"
0x18001e070  call    cs:__imp_GetProcAddress
0x18001e076  mov     [rbx+80h], rax
0x18001e07d  test    rax, rax
0x18001e080  jnz     short loc_18001E08D
0x18001e082  mov     r8d, 0FAh
0x18001e088  jmp     loc_18001E333
0x18001e08d  mov     rcx, [rbx+108h]; hModule
0x18001e094  lea     rdx, aMqadquerysites; "MQADQuerySiteServers"
0x18001e09b  call    cs:__imp_GetProcAddress
0x18001e0a1  mov     [rbx+88h], rax
0x18001e0a8  test    rax, rax
0x18001e0ab  jnz     short loc_18001E0B8
0x18001e0ad  mov     r8d, 104h
0x18001e0b3  jmp     loc_18001E333
0x18001e0b8  mov     rcx, [rbx+108h]; hModule
0x18001e0bf  lea     rdx, aMqadqueryuserc; "MQADQueryUserCert"
0x18001e0c6  call    cs:__imp_GetProcAddress
0x18001e0cc  mov     [rbx+90h], rax
0x18001e0d3  test    rax, rax
0x18001e0d6  jnz     short loc_18001E0E3
0x18001e0d8  mov     r8d, 10Eh
0x18001e0de  jmp     loc_18001E333
0x18001e0e3  mov     rcx, [rbx+108h]; hModule
0x18001e0ea  lea     rdx, aMqadqueryconne; "MQADQueryConnectors"
0x18001e0f1  call    cs:__imp_GetProcAddress
0x18001e0f7  mov     [rbx+98h], rax
0x18001e0fe  test    rax, rax
0x18001e101  jnz     short loc_18001E10E
0x18001e103  mov     r8d, 118h
0x18001e109  jmp     loc_18001E333
0x18001e10e  mov     rcx, [rbx+108h]; hModule
0x18001e115  lea     rdx, aMqadqueryforei; "MQADQueryForeignSites"
0x18001e11c  call    cs:__imp_GetProcAddress
0x18001e122  mov     [rbx+0A0h], rax
0x18001e129  test    rax, rax
0x18001e12c  jnz     short loc_18001E139
0x18001e12e  mov     r8d, 122h
0x18001e134  jmp     loc_18001E333
0x18001e139  mov     rcx, [rbx+108h]; hModule
0x18001e140  lea     rdx, aMqadquerylinks; "MQADQueryLinks"
0x18001e147  call    cs:__imp_GetProcAddress
0x18001e14d  mov     [rbx+0A8h], rax
0x18001e154  test    rax, rax
0x18001e157  jnz     short loc_18001E164
0x18001e159  mov     r8d, 12Ch
0x18001e15f  jmp     loc_18001E333
0x18001e164  mov     rcx, [rbx+108h]; hModule
0x18001e16b  lea     rdx, aMqadqueryallli; "MQADQueryAllLinks"
0x18001e172  call    cs:__imp_GetProcAddress
0x18001e178  mov     [rbx+0B0h], rax
0x18001e17f  test    rax, rax
0x18001e182  jnz     short loc_18001E18F
0x18001e184  mov     r8d, 136h
0x18001e18a  jmp     loc_18001E333
0x18001e18f  mov     rcx, [rbx+108h]; hModule
0x18001e196  lea     rdx, aMqadqueryallsi; "MQADQueryAllSites"
0x18001e19d  call    cs:__imp_GetProcAddress
0x18001e1a3  mov     [rbx+0B8h], rax
0x18001e1aa  test    rax, rax
0x18001e1ad  jnz     short loc_18001E1BA
0x18001e1af  mov     r8d, 140h
0x18001e1b5  jmp     loc_18001E333
0x18001e1ba  mov     rcx, [rbx+108h]; hModule
0x18001e1c1  lea     rdx, aMqadqueryqueue; "MQADQueryQueues"
0x18001e1c8  call    cs:__imp_GetProcAddress
0x18001e1ce  mov     [rbx+0C0h], rax
0x18001e1d5  test    rax, rax
0x18001e1d8  jnz     short loc_18001E1E5
0x18001e1da  mov     r8d, 14Ah
0x18001e1e0  jmp     loc_18001E333
0x18001e1e5  mov     rcx, [rbx+108h]; hModule
0x18001e1ec  lea     rdx, aMqadqueryresul; "MQADQueryResults"
0x18001e1f3  call    cs:__imp_GetProcAddress
0x18001e1f9  mov     [rbx+0C8h], rax
0x18001e200  test    rax, rax
0x18001e203  jnz     short loc_18001E210
0x18001e205  mov     r8d, 154h
0x18001e20b  jmp     loc_18001E333
0x18001e210  mov     rcx, [rbx+108h]; hModule
0x18001e217  lea     rdx, aMqadendquery; "MQADEndQuery"
0x18001e21e  call    cs:__imp_GetProcAddress
0x18001e224  mov     [rbx+0D0h], rax
0x18001e22b  test    rax, rax
0x18001e22e  jnz     short loc_18001E23B
0x18001e230  mov     r8d, 15Eh
0x18001e236  jmp     loc_18001E333
0x18001e23b  mov     rcx, [rbx+108h]; hModule
0x18001e242  lea     rdx, aMqadgetobjects; "MQADGetObjectSecurity"
0x18001e249  call    cs:__imp_GetProcAddress
0x18001e24f  mov     [rbx+0D8h], rax
0x18001e256  test    rax, rax
0x18001e259  jnz     short loc_18001E266
0x18001e25b  mov     r8d, 168h
0x18001e261  jmp     loc_18001E333
0x18001e266  mov     rcx, [rbx+108h]; hModule
0x18001e26d  lea     rdx, aMqadgetobjects_0; "MQADGetObjectSecurityGuid"
0x18001e274  call    cs:__imp_GetProcAddress
0x18001e27a  mov     [rbx+0E0h], rax
0x18001e281  test    rax, rax
0x18001e284  jnz     short loc_18001E291
0x18001e286  mov     r8d, 172h
0x18001e28c  jmp     loc_18001E333
0x18001e291  mov     rcx, [rbx+108h]; hModule
0x18001e298  lea     rdx, aMqadsetobjects; "MQADSetObjectSecurity"
0x18001e29f  call    cs:__imp_GetProcAddress
0x18001e2a5  mov     [rbx+0E8h], rax
0x18001e2ac  test    rax, rax
0x18001e2af  jnz     short loc_18001E2B9
0x18001e2b1  mov     r8d, 17Ch
0x18001e2b7  jmp     short loc_18001E333
0x18001e2b9  mov     rcx, [rbx+108h]; hModule
0x18001e2c0  lea     rdx, aMqadsetobjects_0; "MQADSetObjectSecurityGuid"
0x18001e2c7  call    cs:__imp_GetProcAddress
0x18001e2cd  mov     [rbx+0F0h], rax
0x18001e2d4  test    rax, rax
0x18001e2d7  jnz     short loc_18001E2E1
0x18001e2d9  mov     r8d, 181h
0x18001e2df  jmp     short loc_18001E333
0x18001e2e1  mov     rcx, [rbx+108h]; hModule
0x18001e2e8  lea     rdx, aMqadgetadspath; "MQADGetADsPathInfo"
0x18001e2ef  call    cs:__imp_GetProcAddress
0x18001e2f5  mov     [rbx+0F8h], rax
0x18001e2fc  test    rax, rax
0x18001e2ff  jz      short loc_18001E325
0x18001e301  mov     rcx, [rbx+108h]; hModule
0x18001e308  lea     rdx, aMqadfreememory; "MQADFreeMemory"
0x18001e30f  call    cs:__imp_GetProcAddress
0x18001e315  mov     [rbx+100h], rax
0x18001e31c  test    rax, rax
0x18001e31f  jz      short loc_18001E325
0x18001e321  xor     eax, eax
0x18001e323  jmp     short loc_18001E348
0x18001e325  mov     r8d, 182h
0x18001e32b  jmp     short loc_18001E333
0x18001e32d  mov     r8d, 78h ; 'x'; unsigned __int16
0x18001e333  mov     ebx, 0C00E0043h
0x18001e338  lea     rdx, aAdAdprov; "ad/adprov"
0x18001e33f  mov     ecx, ebx; int
0x18001e341  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18001e346  mov     eax, ebx
0x18001e348  add     rsp, 20h
0x18001e34c  pop     rbx
0x18001e34d  retn
```
