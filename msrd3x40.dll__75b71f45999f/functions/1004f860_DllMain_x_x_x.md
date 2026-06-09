# DllMain(x,x,x)

- ea: `0x1004f860`
- end: `0x1004fac1`
- name: `_DllMain@12`
- size: `609`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1005e238`

## callees

- `0x1004f860`
- `0x1005e3b0`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLangID` at `0x1004f8cd`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLangID` at `0x1004f8cd`
- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByte` at `0x1004f899`
- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByte` at `0x1004f899`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1004f8ed`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1004f8ed`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1004f960`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1004f960`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1004faa4`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1004faa4`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1004f93d`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1004f93d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1004fa76`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1004fa76`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  int v3; // ecx
  bool v4; // al
  int v5; // eax
  REGHANDLE v7; // [esp-8h] [ebp-68h]
  int v8; // [esp+4h] [ebp-5Ch]
  _DWORD v9[2]; // [esp+8h] [ebp-58h] BYREF
  GUID ProviderId; // [esp+10h] [ebp-50h] BYREF
  _EVENT_DATA_DESCRIPTOR UserData; // [esp+28h] [ebp-38h] BYREF
  int *v12; // [esp+38h] [ebp-28h]
  int v13; // [esp+3Ch] [ebp-24h]
  int v14; // [esp+40h] [ebp-20h]
  int v15; // [esp+44h] [ebp-1Ch]
  _DWORD *v16; // [esp+48h] [ebp-18h]
  int v17; // [esp+4Ch] [ebp-14h]
  int v18; // [esp+50h] [ebp-10h]
  int v19; // [esp+54h] [ebp-Ch]

  if ( fdwReason == 1 )
  {
    if ( !fDbcsInitd )
    {
      LOBYTE(v3) = 0;
      v8 = 0;
      do
      {
        v4 = IsDBCSLeadByte(v3);
        rgfLeads[v8] = v4;
        v3 = v8 + 1;
        v5 = fAnyLead | v4;
        fAnyLead = v5;
        v8 = v3;
      }
      while ( v3 < 256 );
      if ( v5 )
        GetSystemDefaultLangID();
      fDbcsInitd = 1;
    }
    if ( !hModule )
      hModule = hinstDLL;
    DisableThreadLibraryCalls(hinstDLL);
    ProviderId = (GUID)*((_OWORD *)off_10066124 - 1);
    if ( RegHandle )
      __fastfail(5u);
    dword_10066140 = 0;
    dword_10066144 = 0;
    if ( !EventRegister(&ProviderId, _tlgEnableCallback, &dword_10066120, &RegHandle) )
      EventSetInformation(RegHandle, HIDWORD(RegHandle), 2, off_10066124, *(unsigned __int16 *)off_10066124);
    if ( (unsigned int)dword_10066120 > 5 )
    {
      v9[0] = dword_10066128;
      if ( (dword_1006612C & 0x4000) != 0 && !dword_10066130 && (dword_10066134 & 0x4000) == dword_10066134 )
      {
        v9[1] = 0;
        v16 = v9;
        *(_DWORD *)&ProviderId.Data2 = 5;
        UserData.Ptr = (unsigned int)off_10066124;
        v9[0] = 0x2000000;
        v17 = 0;
        v18 = 8;
        v19 = 0;
        ProviderId.Data1 = 184549376;
        *(_DWORD *)ProviderId.Data4 = 0;
        *(_DWORD *)&ProviderId.Data4[4] = 0x4000;
        UserData.Size = *(unsigned __int16 *)off_10066124;
        UserData.Reserved = 2;
        v12 = dword_10007A24;
        v13 = 0;
        v14 = 34;
        v15 = 1;
        EventWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&ProviderId, 0, 0, 3u, &UserData);
      }
    }
  }
  else if ( !fdwReason )
  {
    v7 = RegHandle;
    dword_10066120 = 0;
    RegHandle = 0;
    EventUnregister(v7);
  }
  return 1;
}

```

## disassembly

```asm
0x1004f860  mov     edi, edi
0x1004f862  push    ebp
0x1004f863  mov     ebp, esp
0x1004f865  and     esp, 0FFFFFFF0h
0x1004f868  sub     esp, 5Ch
0x1004f86b  mov     eax, ___security_cookie
0x1004f870  xor     eax, esp
0x1004f872  mov     [esp+5Ch+var_4], eax
0x1004f876  mov     eax, [ebp+fdwReason]
0x1004f879  push    esi
0x1004f87a  mov     esi, [ebp+hinstDLL]
0x1004f87d  cmp     eax, 1
0x1004f880  jnz     loc_1004FA7E
0x1004f886  cmp     _fDbcsInitd, 0
0x1004f88d  jnz     short loc_1004F8DD
0x1004f88f  xor     ecx, ecx
0x1004f891  mov     [esp+60h+var_5C], ecx
0x1004f895  movzx   eax, cl
0x1004f898  push    eax; TestChar
0x1004f899  call    ds:__imp__IsDBCSLeadByte@4; IsDBCSLeadByte(x)
0x1004f89f  mov     ecx, [esp+60h+var_5C]
0x1004f8a3  test    eax, eax
0x1004f8a5  setnz   al
0x1004f8a8  mov     _rgfLeads[ecx], al
0x1004f8ae  inc     ecx
0x1004f8af  movzx   eax, al
0x1004f8b2  or      eax, _fAnyLead
0x1004f8b8  mov     _fAnyLead, eax
0x1004f8bd  mov     [esp+60h+var_5C], ecx
0x1004f8c1  cmp     ecx, 100h
0x1004f8c7  jl      short loc_1004F895
0x1004f8c9  test    eax, eax
0x1004f8cb  jz      short loc_1004F8D3
0x1004f8cd  call    ds:__imp__GetSystemDefaultLangID@0; GetSystemDefaultLangID()
0x1004f8d3  mov     _fDbcsInitd, 1
0x1004f8dd  cmp     hModule, 0
0x1004f8e4  jnz     short loc_1004F8EC
0x1004f8e6  mov     hModule, esi
0x1004f8ec  push    esi; hLibModule
0x1004f8ed  call    ds:__imp__DisableThreadLibraryCalls@4; DisableThreadLibraryCalls(x)
0x1004f8f3  mov     eax, off_10066124
0x1004f8f8  movups  xmm0, xmmword ptr [eax-10h]
0x1004f8fc  mov     eax, dword ptr RegHandle
0x1004f901  or      eax, dword ptr RegHandle+4
0x1004f907  movups  xmmword ptr [esp+60h+ProviderId.Data1], xmm0
0x1004f90c  jz      short loc_1004F915
0x1004f90e  mov     ecx, 5
0x1004f913  int     29h; Win8: RtlFailFast(ecx)
0x1004f915  push    offset RegHandle; RegHandle
0x1004f91a  push    offset dword_10066120; CallbackContext
0x1004f91f  push    offset __tlgEnableCallback@36; EnableCallback
0x1004f924  lea     eax, [esp+6Ch+ProviderId]
0x1004f928  mov     dword_10066140, 0
0x1004f932  push    eax; ProviderId
0x1004f933  mov     dword_10066144, 0
0x1004f93d  call    ds:__imp__EventRegister@16; EventRegister(x,x,x,x)
0x1004f943  test    eax, eax
0x1004f945  jnz     short loc_1004F966
0x1004f947  mov     ecx, off_10066124
0x1004f94d  movzx   eax, word ptr [ecx]
0x1004f950  push    eax
0x1004f951  push    ecx
0x1004f952  push    2
0x1004f954  push    dword ptr RegHandle+4
0x1004f95a  push    dword ptr RegHandle
0x1004f960  call    ds:__imp__EventSetInformation@20; EventSetInformation(x,x,x,x,x)
0x1004f966  mov     eax, dword_10066120
0x1004f96b  cmp     eax, 5
0x1004f96e  jbe     loc_1004FAAA
0x1004f974  mov     esi, dword_10066130
0x1004f97a  mov     edx, dword_10066134
0x1004f980  mov     eax, dword_10066128
0x1004f985  mov     ecx, dword_1006612C
0x1004f98b  mov     [esp+60h+var_58], eax
0x1004f98f  and     ecx, 4000h
0x1004f995  xor     eax, eax
0x1004f997  or      eax, ecx
0x1004f999  jz      loc_1004FAAA
0x1004f99f  mov     ecx, edx
0x1004f9a1  xor     eax, eax
0x1004f9a3  and     ecx, 4000h
0x1004f9a9  cmp     eax, esi
0x1004f9ab  jnz     loc_1004FAAA
0x1004f9b1  cmp     ecx, edx
0x1004f9b3  jnz     loc_1004FAAA
0x1004f9b9  mov     [esp+60h+var_54], eax
0x1004f9bd  lea     eax, [esp+60h+var_58]
0x1004f9c1  mov     [esp+60h+var_18], eax
0x1004f9c5  movzx   eax, ds:word_10007A1A
0x1004f9cc  mov     dword ptr [esp+60h+ProviderId.Data2], eax
0x1004f9d0  mov     eax, off_10066124
0x1004f9d5  mov     dword ptr [esp+60h+UserData.Ptr], eax
0x1004f9d9  mov     [esp+60h+var_58], 2000000h
0x1004f9e1  mov     [esp+60h+var_14], 0
0x1004f9e9  mov     [esp+60h+var_10], 8
0x1004f9f1  mov     [esp+60h+var_C], 0
0x1004f9f9  mov     [esp+60h+ProviderId.Data1], 0B000000h
0x1004fa01  mov     dword ptr [esp+60h+ProviderId.Data4], 0
0x1004fa09  mov     dword ptr [esp+60h+ProviderId.Data4+4], 4000h
0x1004fa11  mov     dword ptr [esp+60h+UserData.Ptr+4], 0
0x1004fa19  movzx   eax, word ptr [eax]
0x1004fa1c  mov     [esp+60h+UserData.Size], eax
0x1004fa20  mov     eax, offset __TraceLoggingMetadataEnd
0x1004fa25  sub     eax, offset __TraceLoggingMetadata
0x1004fa2a  mov     dword ptr [esp+60h+UserData.0Ch], 2
0x1004fa32  mov     [esp+60h+var_28], offset dword_10007A24
0x1004fa3a  mov     [esp+60h+var_24], 0
0x1004fa42  mov     [esp+60h+var_20], 22h ; '"'
0x1004fa4a  mov     [esp+60h+var_1C], 1
0x1004fa52  mov     [esp+60h+var_5C], eax
0x1004fa56  mov     eax, [esp+60h+var_5C]
0x1004fa5a  lea     eax, [esp+60h+UserData]
0x1004fa5e  push    eax; UserData
0x1004fa5f  push    3; UserDataCount
0x1004fa61  push    0; RelatedActivityId
0x1004fa63  push    0; ActivityId
0x1004fa65  lea     eax, [esp+70h+ProviderId]
0x1004fa69  push    eax; EventDescriptor
0x1004fa6a  push    dword ptr RegHandle+4
0x1004fa70  push    dword ptr RegHandle; RegHandle
0x1004fa76  call    ds:__imp__EventWriteTransfer@28; EventWriteTransfer(x,x,x,x,x,x,x)
0x1004fa7c  jmp     short loc_1004FAAA
0x1004fa7e  test    eax, eax
0x1004fa80  jnz     short loc_1004FAAA
0x1004fa82  mov     eax, dword ptr RegHandle+4
0x1004fa87  xorps   xmm0, xmm0
0x1004fa8a  mov     ecx, dword ptr RegHandle
0x1004fa90  push    eax
0x1004fa91  push    ecx; RegHandle
0x1004fa92  mov     dword_10066120, 0
0x1004fa9c  movlpd  RegHandle, xmm0
0x1004faa4  call    ds:__imp__EventUnregister@8; EventUnregister(x,x)
0x1004faaa  mov     ecx, [esp+60h+var_4]
0x1004faae  mov     eax, 1
0x1004fab3  pop     esi
0x1004fab4  xor     ecx, esp; StackCookie
0x1004fab6  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004fabb  mov     esp, ebp
0x1004fabd  pop     ebp
0x1004fabe  retn    0Ch
```
