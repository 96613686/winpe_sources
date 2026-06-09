# DllMain(x,x,x)

- ea: `0x10006480`
- end: `0x1000668e`
- name: `_DllMain@12`
- size: `526`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x10035398`

## callees

- `0x10006480`
- `0x10035510`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1000652d`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1000652d`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x10006671`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x10006671`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x10006643`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x10006643`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1000650a`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1000650a`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x100064ba`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x100064ba`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  REGHANDLE v4; // [esp-8h] [ebp-68h]
  _DWORD v5[2]; // [esp+8h] [ebp-58h] BYREF
  GUID ProviderId; // [esp+10h] [ebp-50h] BYREF
  _EVENT_DATA_DESCRIPTOR UserData; // [esp+28h] [ebp-38h] BYREF
  int *v8; // [esp+38h] [ebp-28h]
  int v9; // [esp+3Ch] [ebp-24h]
  int v10; // [esp+40h] [ebp-20h]
  int v11; // [esp+44h] [ebp-1Ch]
  _DWORD *v12; // [esp+48h] [ebp-18h]
  int v13; // [esp+4Ch] [ebp-14h]
  int v14; // [esp+50h] [ebp-10h]
  int v15; // [esp+54h] [ebp-Ch]

  if ( fdwReason == 1 )
  {
    if ( !hModule )
    {
      hModule = hinstDLL;
      DisableThreadLibraryCalls(hinstDLL);
      ProviderId = (GUID)*((_OWORD *)off_10038804 - 1);
      if ( RegHandle )
        __fastfail(5u);
      dword_10038820 = 0;
      dword_10038824 = 0;
      if ( !EventRegister(&ProviderId, _tlgEnableCallback, &dword_10038800, &RegHandle) )
        EventSetInformation(RegHandle, HIDWORD(RegHandle), 2, off_10038804, *(unsigned __int16 *)off_10038804);
      if ( (unsigned int)dword_10038800 > 5 )
      {
        v5[0] = dword_10038808;
        if ( (dword_1003880C & 0x4000) != 0 && !dword_10038810 && (dword_10038814 & 0x4000) == dword_10038814 )
        {
          v5[1] = 0;
          v12 = v5;
          *(_DWORD *)&ProviderId.Data2 = 5;
          UserData.Ptr = (unsigned int)off_10038804;
          v5[0] = 0x2000000;
          v13 = 0;
          v14 = 8;
          v15 = 0;
          ProviderId.Data1 = 184549376;
          *(_DWORD *)ProviderId.Data4 = 0;
          *(_DWORD *)&ProviderId.Data4[4] = 0x4000;
          UserData.Size = *(unsigned __int16 *)off_10038804;
          UserData.Reserved = 2;
          v8 = dword_10005E64;
          v9 = 0;
          v10 = 35;
          v11 = 1;
          EventWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&ProviderId, 0, 0, 3u, &UserData);
        }
      }
    }
  }
  else if ( !fdwReason )
  {
    v4 = RegHandle;
    dword_10038800 = 0;
    RegHandle = 0;
    EventUnregister(v4);
  }
  return 1;
}

```

## disassembly

```asm
0x10006480  mov     edi, edi
0x10006482  push    ebp
0x10006483  mov     ebp, esp
0x10006485  and     esp, 0FFFFFFF0h
0x10006488  sub     esp, 5Ch
0x1000648b  mov     eax, ___security_cookie
0x10006490  xor     eax, esp
0x10006492  mov     [esp+5Ch+var_4], eax
0x10006496  mov     eax, [ebp+fdwReason]
0x10006499  mov     ecx, [ebp+hinstDLL]
0x1000649c  push    esi
0x1000649d  cmp     eax, 1
0x100064a0  jnz     loc_1000664B
0x100064a6  cmp     hModule, 0
0x100064ad  jnz     loc_10006677
0x100064b3  push    ecx; hLibModule
0x100064b4  mov     hModule, ecx
0x100064ba  call    ds:__imp__DisableThreadLibraryCalls@4; DisableThreadLibraryCalls(x)
0x100064c0  mov     eax, off_10038804
0x100064c5  movups  xmm0, xmmword ptr [eax-10h]
0x100064c9  mov     eax, dword ptr RegHandle
0x100064ce  or      eax, dword ptr RegHandle+4
0x100064d4  movups  xmmword ptr [esp+60h+ProviderId.Data1], xmm0
0x100064d9  jz      short loc_100064E2
0x100064db  mov     ecx, 5
0x100064e0  int     29h; Win8: RtlFailFast(ecx)
0x100064e2  push    offset RegHandle; RegHandle
0x100064e7  push    offset dword_10038800; CallbackContext
0x100064ec  push    offset __tlgEnableCallback@36; EnableCallback
0x100064f1  lea     eax, [esp+6Ch+ProviderId]
0x100064f5  mov     dword_10038820, 0
0x100064ff  push    eax; ProviderId
0x10006500  mov     dword_10038824, 0
0x1000650a  call    ds:__imp__EventRegister@16; EventRegister(x,x,x,x)
0x10006510  test    eax, eax
0x10006512  jnz     short loc_10006533
0x10006514  mov     ecx, off_10038804
0x1000651a  movzx   eax, word ptr [ecx]
0x1000651d  push    eax
0x1000651e  push    ecx
0x1000651f  push    2
0x10006521  push    dword ptr RegHandle+4
0x10006527  push    dword ptr RegHandle
0x1000652d  call    ds:__imp__EventSetInformation@20; EventSetInformation(x,x,x,x,x)
0x10006533  mov     eax, dword_10038800
0x10006538  cmp     eax, 5
0x1000653b  jbe     loc_10006677
0x10006541  mov     esi, dword_10038810
0x10006547  mov     edx, dword_10038814
0x1000654d  mov     eax, dword_10038808
0x10006552  mov     ecx, dword_1003880C
0x10006558  mov     [esp+60h+var_58], eax
0x1000655c  and     ecx, 4000h
0x10006562  xor     eax, eax
0x10006564  or      eax, ecx
0x10006566  jz      loc_10006677
0x1000656c  mov     ecx, edx
0x1000656e  xor     eax, eax
0x10006570  and     ecx, 4000h
0x10006576  cmp     eax, esi
0x10006578  jnz     loc_10006677
0x1000657e  cmp     ecx, edx
0x10006580  jnz     loc_10006677
0x10006586  mov     [esp+60h+var_54], eax
0x1000658a  lea     eax, [esp+60h+var_58]
0x1000658e  mov     [esp+60h+var_18], eax
0x10006592  movzx   eax, ds:word_10005E5A
0x10006599  mov     dword ptr [esp+60h+ProviderId.Data2], eax
0x1000659d  mov     eax, off_10038804
0x100065a2  mov     dword ptr [esp+60h+UserData.Ptr], eax
0x100065a6  mov     [esp+60h+var_58], 2000000h
0x100065ae  mov     [esp+60h+var_14], 0
0x100065b6  mov     [esp+60h+var_10], 8
0x100065be  mov     [esp+60h+var_C], 0
0x100065c6  mov     [esp+60h+ProviderId.Data1], 0B000000h
0x100065ce  mov     dword ptr [esp+60h+ProviderId.Data4], 0
0x100065d6  mov     dword ptr [esp+60h+ProviderId.Data4+4], 4000h
0x100065de  mov     dword ptr [esp+60h+UserData.Ptr+4], 0
0x100065e6  movzx   eax, word ptr [eax]
0x100065e9  mov     [esp+60h+UserData.Size], eax
0x100065ed  mov     eax, offset __TraceLoggingMetadataEnd
0x100065f2  sub     eax, offset __TraceLoggingMetadata
0x100065f7  mov     dword ptr [esp+60h+UserData.0Ch], 2
0x100065ff  mov     [esp+60h+var_28], offset dword_10005E64
0x10006607  mov     [esp+60h+var_24], 0
0x1000660f  mov     [esp+60h+var_20], 23h ; '#'
0x10006617  mov     [esp+60h+var_1C], 1
0x1000661f  mov     [esp+60h+var_5C], eax
0x10006623  mov     eax, [esp+60h+var_5C]
0x10006627  lea     eax, [esp+60h+UserData]
0x1000662b  push    eax; UserData
0x1000662c  push    3; UserDataCount
0x1000662e  push    0; RelatedActivityId
0x10006630  push    0; ActivityId
0x10006632  lea     eax, [esp+70h+ProviderId]
0x10006636  push    eax; EventDescriptor
0x10006637  push    dword ptr RegHandle+4
0x1000663d  push    dword ptr RegHandle; RegHandle
0x10006643  call    ds:__imp__EventWriteTransfer@28; EventWriteTransfer(x,x,x,x,x,x,x)
0x10006649  jmp     short loc_10006677
0x1000664b  test    eax, eax
0x1000664d  jnz     short loc_10006677
0x1000664f  mov     eax, dword ptr RegHandle+4
0x10006654  xorps   xmm0, xmm0
0x10006657  mov     ecx, dword ptr RegHandle
0x1000665d  push    eax
0x1000665e  push    ecx; RegHandle
0x1000665f  mov     dword_10038800, 0
0x10006669  movlpd  RegHandle, xmm0
0x10006671  call    ds:__imp__EventUnregister@8; EventUnregister(x,x)
0x10006677  mov     ecx, [esp+60h+var_4]
0x1000667b  mov     eax, 1
0x10006680  pop     esi
0x10006681  xor     ecx, esp; StackCookie
0x10006683  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10006688  mov     esp, ebp
0x1000668a  pop     ebp
0x1000668b  retn    0Ch
```
