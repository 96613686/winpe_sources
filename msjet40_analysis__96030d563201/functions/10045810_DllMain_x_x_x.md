# DllMain(x,x,x)

- ea: `0x10045810`
- end: `0x100459ac`
- name: `_DllMain@12`
- size: `412`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x10122de8`

## callees

- `0x10012790`
- `0x100457c0`
- `0x10045810`
- `0x10122f60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1004598d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1004598d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x10045834`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x10045834`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1004589c`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1004589c`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x100458bf`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x100458bf`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x10045975`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x10045975`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1004584e`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1004584e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10045986`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10045986`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x10045847`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x10045847`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  struct _RTL_CRITICAL_SECTION *v3; // eax
  LPCRITICAL_SECTION v4; // esi
  int v6; // [esp-8h] [ebp-5Ch]
  REGHANDLE v7; // [esp-8h] [ebp-5Ch]
  int v8; // [esp-4h] [ebp-58h]
  GUID ProviderId; // [esp+8h] [ebp-4Ch] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [esp+18h] [ebp-3Ch] BYREF
  unsigned __int8 *Data4; // [esp+38h] [ebp-1Ch]
  int v12; // [esp+3Ch] [ebp-18h]
  int v13; // [esp+40h] [ebp-14h]
  int v14; // [esp+44h] [ebp-10h]

  if ( fdwReason == 1 )
  {
    v3 = (struct _RTL_CRITICAL_SECTION *)_malloc(0x18u);
    critJet = v3;
    if ( v3 )
      InitializeCriticalSection(v3);
    DisableThreadLibraryCalls(hinstDLL);
    ProviderId = (GUID)*((_OWORD *)off_1012B474 - 1);
    if ( RegHandle )
      __fastfail(5u);
    dword_1012B490 = 0;
    dword_1012B494 = 0;
    if ( !EventRegister(&ProviderId, _tlgEnableCallback, &dword_1012B470, &RegHandle) )
      EventSetInformation(RegHandle, HIDWORD(RegHandle), 2, off_1012B474, (unsigned __int16)*off_1012B474);
    if ( (unsigned int)dword_1012B470 > 5 )
    {
      *(_DWORD *)ProviderId.Data4 = dword_1012B478;
      if ( (dword_1012B47C & 0x4000) != 0 && !dword_1012B480 && (dword_1012B484 & 0x4000) == dword_1012B484 )
      {
        *(_DWORD *)&ProviderId.Data4[4] = 0;
        Data4 = ProviderId.Data4;
        *(_DWORD *)ProviderId.Data4 = 0x2000000;
        v12 = 0;
        v13 = 8;
        v14 = 0;
        _tlgWriteTransfer_EventWriteTransfer((int)&dword_1012B470, (int)byte_10012315, 0, 0, 3u, &UserData);
      }
    }
    McGenEventRegister_EventRegister(v6, v8);
  }
  else if ( !fdwReason )
  {
    v7 = RegHandle;
    dword_1012B470 = 0;
    RegHandle = 0;
    EventUnregister(v7);
    v4 = critJet;
    if ( critJet )
    {
      DeleteCriticalSection(critJet);
      _free(v4);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x10045810  mov     edi, edi
0x10045812  push    ebp
0x10045813  mov     ebp, esp
0x10045815  sub     esp, 50h
0x10045818  mov     eax, ___security_cookie
0x1004581d  xor     eax, ebp
0x1004581f  mov     [ebp+var_8], eax
0x10045822  mov     eax, [ebp+fdwReason]
0x10045825  push    esi
0x10045826  mov     esi, [ebp+hinstDLL]
0x10045829  cmp     eax, 1
0x1004582c  jnz     loc_1004594F
0x10045832  push    18h; Size
0x10045834  call    ds:__imp__malloc
0x1004583a  add     esp, 4
0x1004583d  mov     _critJet, eax
0x10045842  test    eax, eax
0x10045844  jz      short loc_1004584D
0x10045846  push    eax; lpCriticalSection
0x10045847  call    ds:__imp__InitializeCriticalSection@4; InitializeCriticalSection(x)
0x1004584d  push    esi; hLibModule
0x1004584e  call    ds:__imp__DisableThreadLibraryCalls@4; DisableThreadLibraryCalls(x)
0x10045854  mov     eax, off_1012B474
0x10045859  movups  xmm0, xmmword ptr [eax-10h]
0x1004585d  mov     eax, dword ptr RegHandle
0x10045862  or      eax, dword ptr RegHandle+4
0x10045868  movups  xmmword ptr [ebp+ProviderId.Data1], xmm0
0x1004586c  jz      short loc_10045875
0x1004586e  mov     ecx, 5
0x10045873  int     29h; Win8: RtlFailFast(ecx)
0x10045875  push    offset RegHandle; RegHandle
0x1004587a  push    offset dword_1012B470; CallbackContext
0x1004587f  push    offset __tlgEnableCallback@36; EnableCallback
0x10045884  lea     eax, [ebp+ProviderId]
0x10045887  mov     dword_1012B490, 0
0x10045891  push    eax; ProviderId
0x10045892  mov     dword_1012B494, 0
0x1004589c  call    ds:__imp__EventRegister@16; EventRegister(x,x,x,x)
0x100458a2  test    eax, eax
0x100458a4  jnz     short loc_100458C5
0x100458a6  mov     ecx, off_1012B474
0x100458ac  movzx   eax, word ptr [ecx]
0x100458af  push    eax
0x100458b0  push    ecx
0x100458b1  push    2
0x100458b3  push    dword ptr RegHandle+4
0x100458b9  push    dword ptr RegHandle
0x100458bf  call    ds:__imp__EventSetInformation@20; EventSetInformation(x,x,x,x,x)
0x100458c5  mov     eax, dword_1012B470
0x100458ca  cmp     eax, 5
0x100458cd  jbe     short loc_10045945
0x100458cf  mov     esi, dword_1012B480
0x100458d5  mov     edx, dword_1012B484
0x100458db  mov     eax, dword_1012B478
0x100458e0  mov     ecx, dword_1012B47C
0x100458e6  mov     dword ptr [ebp+ProviderId.Data4], eax
0x100458e9  and     ecx, 4000h
0x100458ef  xor     eax, eax
0x100458f1  or      eax, ecx
0x100458f3  jz      short loc_10045945
0x100458f5  mov     ecx, edx
0x100458f7  xor     eax, eax
0x100458f9  and     ecx, 4000h
0x100458ff  cmp     eax, esi
0x10045901  jnz     short loc_10045945
0x10045903  cmp     ecx, edx
0x10045905  jnz     short loc_10045945
0x10045907  mov     dword ptr [ebp+ProviderId.Data4+4], eax
0x1004590a  lea     eax, [ebp+ProviderId.Data4]
0x1004590d  mov     [ebp+var_1C], eax
0x10045910  lea     eax, [ebp+UserData]
0x10045913  push    eax; UserData
0x10045914  push    3; UserDataCount
0x10045916  push    0; RelatedActivityId
0x10045918  push    0; ActivityId
0x1004591a  push    offset byte_10012315; int
0x1004591f  push    offset dword_1012B470; int
0x10045924  mov     dword ptr [ebp+ProviderId.Data4], 2000000h
0x1004592b  mov     [ebp+var_18], 0
0x10045932  mov     [ebp+var_14], 8
0x10045939  mov     [ebp+var_10], 0
0x10045940  call    __tlgWriteTransfer_EventWriteTransfer@24; _tlgWriteTransfer_EventWriteTransfer(x,x,x,x,x,x)
0x10045945  sub     esp, 8
0x10045948  call    _McGenEventRegister_EventRegister@16; McGenEventRegister_EventRegister(x,x,x,x)
0x1004594d  jmp     short loc_10045996
0x1004594f  test    eax, eax
0x10045951  jnz     short loc_10045996
0x10045953  mov     eax, dword ptr RegHandle+4
0x10045958  xorps   xmm0, xmm0
0x1004595b  mov     ecx, dword ptr RegHandle
0x10045961  push    eax
0x10045962  push    ecx; RegHandle
0x10045963  mov     dword_1012B470, 0
0x1004596d  movlpd  RegHandle, xmm0
0x10045975  call    ds:__imp__EventUnregister@8; EventUnregister(x,x)
0x1004597b  mov     esi, _critJet
0x10045981  test    esi, esi
0x10045983  jz      short loc_10045996
0x10045985  push    esi; lpCriticalSection
0x10045986  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x1004598c  push    esi; Block
0x1004598d  call    ds:__imp__free
0x10045993  add     esp, 4
0x10045996  mov     ecx, [ebp+var_8]
0x10045999  mov     eax, 1
0x1004599e  xor     ecx, ebp; StackCookie
0x100459a0  pop     esi
0x100459a1  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100459a6  mov     esp, ebp
0x100459a8  pop     ebp
0x100459a9  retn    0Ch
```
