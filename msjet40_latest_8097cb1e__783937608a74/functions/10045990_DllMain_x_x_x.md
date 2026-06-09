# DllMain(x,x,x)

- ea: `0x10045990`
- end: `0x10045b2c`
- name: `_DllMain@12`
- size: `412`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x10122f98`

## callees

- `0x100128d0`
- `0x10045940`
- `0x10045990`
- `0x10123110`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10045b0d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10045b0d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x100459b4`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x100459b4`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x10045a1c`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x10045a1c`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x10045a3f`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x10045a3f`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x10045af5`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x10045af5`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x100459ce`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x100459ce`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10045b06`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10045b06`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x100459c7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x100459c7`

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
    ProviderId = (GUID)*((_OWORD *)off_1012B484 - 1);
    if ( RegHandle )
      __fastfail(5u);
    dword_1012B4A0 = 0;
    dword_1012B4A4 = 0;
    if ( !EventRegister(&ProviderId, _tlgEnableCallback, &dword_1012B480, &RegHandle) )
      EventSetInformation(RegHandle, HIDWORD(RegHandle), 2, off_1012B484, (unsigned __int16)*off_1012B484);
    if ( (unsigned int)dword_1012B480 > 5 )
    {
      *(_DWORD *)ProviderId.Data4 = dword_1012B488;
      if ( (dword_1012B48C & 0x4000) != 0 && !dword_1012B490 && (dword_1012B494 & 0x4000) == dword_1012B494 )
      {
        *(_DWORD *)&ProviderId.Data4[4] = 0;
        Data4 = ProviderId.Data4;
        *(_DWORD *)ProviderId.Data4 = 0x2000000;
        v12 = 0;
        v13 = 8;
        v14 = 0;
        _tlgWriteTransfer_EventWriteTransfer((int)&dword_1012B480, (int)byte_10012455, 0, 0, 3u, &UserData);
      }
    }
    McGenEventRegister_EventRegister(v6, v8);
  }
  else if ( !fdwReason )
  {
    v7 = RegHandle;
    dword_1012B480 = 0;
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
0x10045990  mov     edi, edi
0x10045992  push    ebp
0x10045993  mov     ebp, esp
0x10045995  sub     esp, 50h
0x10045998  mov     eax, ___security_cookie
0x1004599d  xor     eax, ebp
0x1004599f  mov     [ebp+var_8], eax
0x100459a2  mov     eax, [ebp+fdwReason]
0x100459a5  push    esi
0x100459a6  mov     esi, [ebp+hinstDLL]
0x100459a9  cmp     eax, 1
0x100459ac  jnz     loc_10045ACF
0x100459b2  push    18h; Size
0x100459b4  call    ds:__imp__malloc
0x100459ba  add     esp, 4
0x100459bd  mov     _critJet, eax
0x100459c2  test    eax, eax
0x100459c4  jz      short loc_100459CD
0x100459c6  push    eax; lpCriticalSection
0x100459c7  call    ds:__imp__InitializeCriticalSection@4; InitializeCriticalSection(x)
0x100459cd  push    esi; hLibModule
0x100459ce  call    ds:__imp__DisableThreadLibraryCalls@4; DisableThreadLibraryCalls(x)
0x100459d4  mov     eax, off_1012B484
0x100459d9  movups  xmm0, xmmword ptr [eax-10h]
0x100459dd  mov     eax, dword ptr RegHandle
0x100459e2  or      eax, dword ptr RegHandle+4
0x100459e8  movups  xmmword ptr [ebp+ProviderId.Data1], xmm0
0x100459ec  jz      short loc_100459F5
0x100459ee  mov     ecx, 5
0x100459f3  int     29h; Win8: RtlFailFast(ecx)
0x100459f5  push    offset RegHandle; RegHandle
0x100459fa  push    offset dword_1012B480; CallbackContext
0x100459ff  push    offset __tlgEnableCallback@36; EnableCallback
0x10045a04  lea     eax, [ebp+ProviderId]
0x10045a07  mov     dword_1012B4A0, 0
0x10045a11  push    eax; ProviderId
0x10045a12  mov     dword_1012B4A4, 0
0x10045a1c  call    ds:__imp__EventRegister@16; EventRegister(x,x,x,x)
0x10045a22  test    eax, eax
0x10045a24  jnz     short loc_10045A45
0x10045a26  mov     ecx, off_1012B484
0x10045a2c  movzx   eax, word ptr [ecx]
0x10045a2f  push    eax
0x10045a30  push    ecx
0x10045a31  push    2
0x10045a33  push    dword ptr RegHandle+4
0x10045a39  push    dword ptr RegHandle
0x10045a3f  call    ds:__imp__EventSetInformation@20; EventSetInformation(x,x,x,x,x)
0x10045a45  mov     eax, dword_1012B480
0x10045a4a  cmp     eax, 5
0x10045a4d  jbe     short loc_10045AC5
0x10045a4f  mov     esi, dword_1012B490
0x10045a55  mov     edx, dword_1012B494
0x10045a5b  mov     eax, dword_1012B488
0x10045a60  mov     ecx, dword_1012B48C
0x10045a66  mov     dword ptr [ebp+ProviderId.Data4], eax
0x10045a69  and     ecx, 4000h
0x10045a6f  xor     eax, eax
0x10045a71  or      eax, ecx
0x10045a73  jz      short loc_10045AC5
0x10045a75  mov     ecx, edx
0x10045a77  xor     eax, eax
0x10045a79  and     ecx, 4000h
0x10045a7f  cmp     eax, esi
0x10045a81  jnz     short loc_10045AC5
0x10045a83  cmp     ecx, edx
0x10045a85  jnz     short loc_10045AC5
0x10045a87  mov     dword ptr [ebp+ProviderId.Data4+4], eax
0x10045a8a  lea     eax, [ebp+ProviderId.Data4]
0x10045a8d  mov     [ebp+var_1C], eax
0x10045a90  lea     eax, [ebp+UserData]
0x10045a93  push    eax; UserData
0x10045a94  push    3; UserDataCount
0x10045a96  push    0; RelatedActivityId
0x10045a98  push    0; ActivityId
0x10045a9a  push    offset byte_10012455; int
0x10045a9f  push    offset dword_1012B480; int
0x10045aa4  mov     dword ptr [ebp+ProviderId.Data4], 2000000h
0x10045aab  mov     [ebp+var_18], 0
0x10045ab2  mov     [ebp+var_14], 8
0x10045ab9  mov     [ebp+var_10], 0
0x10045ac0  call    __tlgWriteTransfer_EventWriteTransfer@24; _tlgWriteTransfer_EventWriteTransfer(x,x,x,x,x,x)
0x10045ac5  sub     esp, 8
0x10045ac8  call    _McGenEventRegister_EventRegister@16; McGenEventRegister_EventRegister(x,x,x,x)
0x10045acd  jmp     short loc_10045B16
0x10045acf  test    eax, eax
0x10045ad1  jnz     short loc_10045B16
0x10045ad3  mov     eax, dword ptr RegHandle+4
0x10045ad8  xorps   xmm0, xmm0
0x10045adb  mov     ecx, dword ptr RegHandle
0x10045ae1  push    eax
0x10045ae2  push    ecx; RegHandle
0x10045ae3  mov     dword_1012B480, 0
0x10045aed  movlpd  RegHandle, xmm0
0x10045af5  call    ds:__imp__EventUnregister@8; EventUnregister(x,x)
0x10045afb  mov     esi, _critJet
0x10045b01  test    esi, esi
0x10045b03  jz      short loc_10045B16
0x10045b05  push    esi; lpCriticalSection
0x10045b06  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x10045b0c  push    esi; Block
0x10045b0d  call    ds:__imp__free
0x10045b13  add     esp, 4
0x10045b16  mov     ecx, [ebp+var_8]
0x10045b19  mov     eax, 1
0x10045b1e  xor     ecx, ebp; StackCookie
0x10045b20  pop     esi
0x10045b21  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10045b26  mov     esp, ebp
0x10045b28  pop     ebp
0x10045b29  retn    0Ch
```
