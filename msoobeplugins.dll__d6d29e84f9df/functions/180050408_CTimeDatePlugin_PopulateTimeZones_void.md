# CTimeDatePlugin::_PopulateTimeZones(void)

- ea: `0x180050408`
- end: `0x1800506a2`
- name: `?_PopulateTimeZones@CTimeDatePlugin@@AEAAJXZ`
- size: `666`
- prototype: `__int64 __fastcall(CTimeDatePlugin *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004fcd0`

## callees

- `0x180003470`
- `0x180003ffc`
- `0x1800098cc`
- `0x18000bb38`
- `0x18000bd5c`
- `0x18001a524`
- `0x180050408`
- `0x1800506a8`
- `0x180050940`
- `0x1800b8834`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180050639`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180050639`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180050485`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180050485`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800504e5`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800504e5`

## string_xrefs

- `0x18005060c`: `Failed to read in time zone information for time zone %s with hr=0x%08X`

## pseudocode

```c
__int64 __fastcall CTimeDatePlugin::_PopulateTimeZones(struct COOBEItemCollection **this)
{
  COOBEItemCollection **v2; // rsi
  signed int Instance; // ebx
  LSTATUS v4; // eax
  DWORD i; // r14d
  LSTATUS v6; // eax
  bool v7; // sf
  CTimeDatePlugin *v8; // rcx
  struct _TIME_DYNAMIC_ZONE_INFORMATION *v9; // rax
  __int128 *v10; // rcx
  __int64 v11; // rdx
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  struct CTimeZone *v22; // rdi
  struct IOOBEItem *v23; // rdx
  int v24; // eax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  struct CTimeZone *v28; // [rsp+50h] [rbp-B0h] BYREF
  struct _TIME_DYNAMIC_ZONE_INFORMATION v29; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v30[260]; // [rsp+210h] [rbp+110h] BYREF
  char v31; // [rsp+418h] [rbp+318h] BYREF
  WCHAR Name[264]; // [rsp+5D0h] [rbp+4D0h] BYREF

  SafeRelease<IOOBETimeZoneItem>(this + 7);
  v2 = this + 6;
  SafeRelease<IOOBETimeZoneItem>(this + 6);
  Instance = COOBETimeZoneItemCollection_CreateInstance(this + 6);
  if ( Instance < 0 )
    goto LABEL_23;
  hKey = 0;
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Time Zones",
         0,
         0x20019u,
         &hKey);
  Instance = v4;
  if ( v4 > 0 )
    Instance = (unsigned __int16)v4 | 0x80070000;
  if ( Instance < 0 )
    goto LABEL_23;
  for ( i = 0; ; ++i )
  {
    cchName = 260;
    v6 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
    v7 = v6 < 0;
    if ( v6 > 0 )
      v7 = 1;
    if ( v7 )
      break;
    memset_0(v30, 0, 0x3B8u);
    Instance = CTimeDatePlugin::_ReadTimeZone(v8, hKey, Name, (struct _TIME_ZONE_INFORMATION_EX *)v30);
    if ( Instance < 0 )
      goto LABEL_18;
    v28 = 0;
    v9 = &v29;
    v10 = (__int128 *)&v31;
    v11 = 3;
    do
    {
      v12 = *v10;
      v13 = v10[1];
      v10 += 8;
      *(_OWORD *)&v9->Bias = v12;
      v14 = *(v10 - 6);
      *(_OWORD *)&v9->StandardName[6] = v13;
      v15 = *(v10 - 5);
      *(_OWORD *)&v9->StandardName[14] = v14;
      v16 = *(v10 - 4);
      *(_OWORD *)&v9->StandardName[22] = v15;
      v17 = *(v10 - 3);
      *(_OWORD *)&v9->StandardName[30] = v16;
      v18 = *(v10 - 2);
      *(_OWORD *)&v9->StandardDate.wSecond = v17;
      v19 = *(v10 - 1);
      *(_OWORD *)&v9->DaylightName[4] = v18;
      *(_OWORD *)&v9->DaylightName[12] = v19;
      v9 = (struct _TIME_DYNAMIC_ZONE_INFORMATION *)((char *)v9 + 128);
      --v11;
    }
    while ( v11 );
    v20 = v10[1];
    *(_OWORD *)&v9->Bias = *v10;
    v21 = v10[2];
    *(_OWORD *)&v9->StandardName[6] = v20;
    *(_OWORD *)&v9->StandardName[14] = v21;
    Instance = CTimeZone::s_Create(v30, &v29, &v28);
    if ( Instance < 0 )
      goto LABEL_18;
    v22 = v28;
    if ( v28 )
      v23 = (struct CTimeZone *)((char *)v28 + 24);
    else
      v23 = 0;
    Instance = COOBEItemCollection::AddItem(*v2, v23);
    if ( Instance < 0 )
    {
      (*(void (__fastcall **)(struct CTimeZone *))(*(_QWORD *)v22 + 16LL))(v22);
LABEL_18:
      UnattendLogW(
        2,
        L"Failed to read in time zone information for time zone %s with hr=0x%08X",
        Name,
        (unsigned int)Instance);
    }
  }
  (*(void (__fastcall **)(COOBEItemCollection *))(*(_QWORD *)*v2 + 40LL))(*v2);
  RegCloseKey(hKey);
  if ( Instance < 0 )
  {
LABEL_23:
    UnattendLogW(1, L"Failed to populate time zone information with hr=0x%08X", (unsigned int)Instance);
    SafeRelease<IOOBETimeZoneItem>(this + 6);
    return (unsigned int)Instance;
  }
  v24 = CTimeDatePlugin::_StoreCurrentTimeZone((CTimeDatePlugin *)this);
  if ( v24 < 0 )
    UnattendLogW(
      2,
      L"Failed to store initial system timezone as current timezone in OOBE [hr=0x%08X]",
      (unsigned int)v24);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180050408  push    rbp
0x18005040a  push    rbx
0x18005040b  push    rsi
0x18005040c  push    rdi
0x18005040d  push    r14
0x18005040f  push    r15
0x180050411  lea     rbp, [rsp-6F8h]
0x180050419  sub     rsp, 7F8h
0x180050420  mov     rax, cs:__security_cookie
0x180050427  xor     rax, rsp
0x18005042a  mov     [rbp+720h+var_40], rax
0x180050431  mov     r15, rcx
0x180050434  add     rcx, 38h ; '8'
0x180050438  call    ??$SafeRelease@UIOOBETimeZoneItem@@@@YAXPEAPEAUIOOBETimeZoneItem@@@Z; SafeRelease<IOOBETimeZoneItem>(IOOBETimeZoneItem * *)
0x18005043d  lea     rsi, [r15+30h]
0x180050441  mov     rcx, rsi
0x180050444  call    ??$SafeRelease@UIOOBETimeZoneItem@@@@YAXPEAPEAUIOOBETimeZoneItem@@@Z; SafeRelease<IOOBETimeZoneItem>(IOOBETimeZoneItem * *)
0x180050449  mov     rcx, rsi; struct COOBEItemCollection **
0x18005044c  call    ?COOBETimeZoneItemCollection_CreateInstance@@YAJPEAPEAVCOOBEItemCollection@@@Z; COOBETimeZoneItemCollection_CreateInstance(COOBEItemCollection * *)
0x180050451  mov     ebx, eax
0x180050453  test    eax, eax
0x180050455  js      loc_180050665
0x18005045b  lea     rax, [rsp+820h+hKey]
0x180050460  mov     [rsp+820h+hKey], 0
0x180050469  mov     r9d, 20019h; samDesired
0x18005046f  mov     [rsp+820h+phkResult], rax; phkResult
0x180050474  xor     r8d, r8d; ulOptions
0x180050477  lea     rdx, aSoftwareMicros_27; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18005047e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180050485  call    cs:__imp_RegOpenKeyExW
0x18005048b  mov     ebx, eax
0x18005048d  test    eax, eax
0x18005048f  jle     short loc_18005049A
0x180050491  movzx   ebx, ax
0x180050494  or      ebx, 80070000h
0x18005049a  test    ebx, ebx
0x18005049c  js      loc_180050665
0x1800504a2  xor     r14d, r14d
0x1800504a5  mov     rcx, [rsp+820h+hKey]; hKey
0x1800504aa  lea     r9, [rsp+820h+cchName]; lpcchName
0x1800504af  mov     [rsp+820h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800504b8  lea     r8, [rbp+720h+Name]; lpName
0x1800504bf  mov     [rsp+820h+lpcchClass], 0; lpcchClass
0x1800504c8  mov     edx, r14d; dwIndex
0x1800504cb  mov     [rsp+820h+lpClass], 0; lpClass
0x1800504d4  mov     [rsp+820h+phkResult], 0; lpReserved
0x1800504dd  mov     [rsp+820h+cchName], 104h
0x1800504e5  call    cs:__imp_RegEnumKeyExW
0x1800504eb  test    eax, eax
0x1800504ed  jle     short loc_1800504F9
0x1800504ef  movzx   eax, ax
0x1800504f2  or      eax, 80070000h
0x1800504f7  test    eax, eax
0x1800504f9  js      loc_180050625
0x1800504ff  xor     edx, edx; Val
0x180050501  lea     rcx, [rbp+720h+var_610]; void *
0x180050508  mov     r8d, 3B8h; Size
0x18005050e  call    memset_0
0x180050513  mov     rdx, [rsp+820h+hKey]; HKEY
0x180050518  lea     r9, [rbp+720h+var_610]; struct _TIME_ZONE_INFORMATION_EX *
0x18005051f  lea     r8, [rbp+720h+Name]; unsigned __int16 *
0x180050526  call    ?_ReadTimeZone@CTimeDatePlugin@@AEAAJPEAUHKEY__@@PEBGPEAU_TIME_ZONE_INFORMATION_EX@@@Z; CTimeDatePlugin::_ReadTimeZone(HKEY__ *,ushort const *,_TIME_ZONE_INFORMATION_EX *)
0x18005052b  mov     ebx, eax
0x18005052d  test    eax, eax
0x18005052f  js      loc_180050602
0x180050535  mov     [rsp+820h+var_7D0], 0
0x18005053e  lea     rax, [rsp+820h+var_7C0]
0x180050543  lea     rcx, [rbp+720h+var_408]
0x18005054a  mov     edx, 3
0x18005054f  movups  xmm0, xmmword ptr [rcx]
0x180050552  movups  xmm1, xmmword ptr [rcx+10h]
0x180050556  lea     rcx, [rcx+80h]
0x18005055d  movups  xmmword ptr [rax], xmm0
0x180050560  movups  xmm0, xmmword ptr [rcx-60h]
0x180050564  movups  xmmword ptr [rax+10h], xmm1
0x180050568  movups  xmm1, xmmword ptr [rcx-50h]
0x18005056c  movups  xmmword ptr [rax+20h], xmm0
0x180050570  movups  xmm0, xmmword ptr [rcx-40h]
0x180050574  movups  xmmword ptr [rax+30h], xmm1
0x180050578  movups  xmm1, xmmword ptr [rcx-30h]
0x18005057c  movups  xmmword ptr [rax+40h], xmm0
0x180050580  movups  xmm0, xmmword ptr [rcx-20h]
0x180050584  movups  xmmword ptr [rax+50h], xmm1
0x180050588  movups  xmm1, xmmword ptr [rcx-10h]
0x18005058c  movups  xmmword ptr [rax+60h], xmm0
0x180050590  movups  xmmword ptr [rax+70h], xmm1
0x180050594  lea     rax, [rax+80h]
0x18005059b  sub     rdx, 1
0x18005059f  jnz     short loc_18005054F
0x1800505a1  movups  xmm0, xmmword ptr [rcx]
0x1800505a4  lea     r8, [rsp+820h+var_7D0]; struct CTimeZone **
0x1800505a9  movups  xmm1, xmmword ptr [rcx+10h]
0x1800505ad  lea     rdx, [rsp+820h+var_7C0]; struct _TIME_DYNAMIC_ZONE_INFORMATION
0x1800505b2  movups  xmmword ptr [rax], xmm0
0x1800505b5  movups  xmm0, xmmword ptr [rcx+20h]
0x1800505b9  lea     rcx, [rbp+720h+var_610]; unsigned __int16 *
0x1800505c0  movups  xmmword ptr [rax+10h], xmm1
0x1800505c4  movups  xmmword ptr [rax+20h], xmm0
0x1800505c8  call    ?s_Create@CTimeZone@@SAJPEBGU_TIME_DYNAMIC_ZONE_INFORMATION@@PEAPEAV1@@Z; CTimeZone::s_Create(ushort const *,_TIME_DYNAMIC_ZONE_INFORMATION,CTimeZone * *)
0x1800505cd  mov     ebx, eax
0x1800505cf  test    eax, eax
0x1800505d1  js      short loc_180050602
0x1800505d3  mov     rdi, [rsp+820h+var_7D0]
0x1800505d8  test    rdi, rdi
0x1800505db  jz      short loc_1800505E3
0x1800505dd  lea     rdx, [rdi+18h]
0x1800505e1  jmp     short loc_1800505E5
0x1800505e3  xor     edx, edx; struct IOOBEItem *
0x1800505e5  mov     rcx, [rsi]; this
0x1800505e8  call    ?AddItem@COOBEItemCollection@@QEAAJPEAUIOOBEItem@@@Z; COOBEItemCollection::AddItem(IOOBEItem *)
0x1800505ed  mov     ebx, eax
0x1800505ef  test    eax, eax
0x1800505f1  jns     short loc_18005061D
0x1800505f3  mov     rax, [rdi]
0x1800505f6  mov     rcx, rdi
0x1800505f9  mov     rax, [rax+10h]
0x1800505fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050602  mov     r9d, ebx
0x180050605  lea     r8, [rbp+720h+Name]
0x18005060c  lea     rdx, aFailedToReadIn; "Failed to read in time zone information"...
0x180050613  mov     ecx, 2
0x180050618  call    UnattendLogW
0x18005061d  inc     r14d
0x180050620  jmp     loc_1800504A5
0x180050625  mov     rcx, [rsi]
0x180050628  mov     rax, [rcx]
0x18005062b  mov     rax, [rax+28h]
0x18005062f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050634  mov     rcx, [rsp+820h+hKey]; hKey
0x180050639  call    cs:__imp_RegCloseKey
0x18005063f  test    ebx, ebx
0x180050641  js      short loc_180050665
0x180050643  mov     rcx, r15; this
0x180050646  call    ?_StoreCurrentTimeZone@CTimeDatePlugin@@AEAAJXZ; CTimeDatePlugin::_StoreCurrentTimeZone(void)
0x18005064b  test    eax, eax
0x18005064d  jns     short loc_180050681
0x18005064f  mov     r8d, eax
0x180050652  lea     rdx, aFailedToStoreI; "Failed to store initial system timezone"...
0x180050659  mov     ecx, 2
0x18005065e  call    UnattendLogW
0x180050663  jmp     short loc_180050681
0x180050665  mov     r8d, ebx
0x180050668  lea     rdx, aFailedToPopula; "Failed to populate time zone informatio"...
0x18005066f  mov     ecx, 1
0x180050674  call    UnattendLogW
0x180050679  mov     rcx, rsi
0x18005067c  call    ??$SafeRelease@UIOOBETimeZoneItem@@@@YAXPEAPEAUIOOBETimeZoneItem@@@Z; SafeRelease<IOOBETimeZoneItem>(IOOBETimeZoneItem * *)
0x180050681  mov     eax, ebx
0x180050683  mov     rcx, [rbp+720h+var_40]
0x18005068a  xor     rcx, rsp; StackCookie
0x18005068d  call    __security_check_cookie
0x180050692  add     rsp, 7F8h
0x180050699  pop     r15
0x18005069b  pop     r14
0x18005069d  pop     rdi
0x18005069e  pop     rsi
0x18005069f  pop     rbx
0x1800506a0  pop     rbp
0x1800506a1  retn
```
