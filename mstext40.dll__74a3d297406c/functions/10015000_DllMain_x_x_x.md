# DllMain(x,x,x)

- ea: `0x10015000`
- end: `0x100150f9`
- name: `_DllMain@12`
- size: `249`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1002e384`

## callees

- `0x10008b40`
- `0x10008c60`
- `0x10015000`
- `0x1002b81a`

## import_xrefs

- `KERNEL32!DisableThreadLibraryCalls` at `0x10015021`
- `KERNEL32!DisableThreadLibraryCalls` at `0x10015021`
- `ADVAPI32!EventUnregister` at `0x100150c7`
- `ADVAPI32!EventUnregister` at `0x100150c7`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  _DWORD v4[2]; // [esp+4h] [ebp-3Ch] BYREF
  EVENT_DATA_DESCRIPTOR pData; // [esp+Ch] [ebp-34h] BYREF
  _DWORD *v6; // [esp+2Ch] [ebp-14h]
  int v7; // [esp+30h] [ebp-10h]
  int v8; // [esp+34h] [ebp-Ch]
  int v9; // [esp+38h] [ebp-8h]

  if ( fdwReason == 1 )
  {
    DisableThreadLibraryCalls(hinstDLL);
    hModule = hinstDLL;
    TraceLoggingRegisterEx((TraceLoggingHProvider)&hProvider, 0, 0);
    if ( hProvider > 5u
      && (dword_1003E0F4 & 0x4000) != 0
      && !dword_1003E0F8
      && (dword_1003E0FC & 0x4000) == dword_1003E0FC )
    {
      v4[0] = 0x2000000;
      v4[1] = 0;
      v6 = v4;
      v7 = 0;
      v8 = 8;
      v9 = 0;
      _TlgWrite((TraceLoggingHProvider)&hProvider, byte_10008AC1, 0, 0, 3u, &pData);
    }
  }
  else if ( !fdwReason )
  {
    EventUnregister(RegHandle);
    hProvider = 0;
    RegHandle = 0;
  }
  return 1;
}

```

## disassembly

```asm
0x10015000  sub     esp, 3Ch
0x10015003  mov     eax, ___security_cookie
0x10015008  xor     eax, esp
0x1001500a  mov     [esp+3Ch+var_4], eax
0x1001500e  mov     eax, [esp+3Ch+fdwReason]
0x10015012  push    esi
0x10015013  mov     esi, [esp+40h+hinstDLL]
0x10015017  cmp     eax, 1
0x1001501a  jnz     loc_100150B7
0x10015020  push    esi; hLibModule
0x10015021  call    ds:__imp__DisableThreadLibraryCalls@4; DisableThreadLibraryCalls(x)
0x10015027  push    0; pCallbackContext
0x10015029  push    0; pEnableCallback
0x1001502b  push    offset hProvider; hProvider
0x10015030  mov     hModule, esi
0x10015036  call    _TraceLoggingRegisterEx@12; TraceLoggingRegisterEx(x,x,x)
0x1001503b  cmp     hProvider, 5
0x10015042  jbe     loc_100150E2
0x10015048  mov     ecx, dword_1003E0F4
0x1001504e  xor     eax, eax
0x10015050  and     ecx, 4000h
0x10015056  or      eax, ecx
0x10015058  jz      loc_100150E2
0x1001505e  mov     ecx, dword_1003E0FC
0x10015064  xor     edx, edx
0x10015066  mov     eax, ecx
0x10015068  and     eax, 4000h
0x1001506d  cmp     edx, dword_1003E0F8
0x10015073  jnz     short loc_100150E2
0x10015075  cmp     eax, ecx
0x10015077  jnz     short loc_100150E2
0x10015079  lea     eax, [esp+40h+var_3C]
0x1001507d  mov     [esp+40h+var_3C], 2000000h
0x10015085  mov     [esp+40h+var_38], edx
0x10015089  mov     [esp+40h+var_14], eax
0x1001508d  mov     [esp+40h+var_10], edx
0x10015091  mov     [esp+40h+var_C], 8
0x10015099  mov     [esp+40h+var_8], edx
0x1001509d  lea     eax, [esp+40h+pData]
0x100150a1  push    eax; pData
0x100150a2  push    3; cData
0x100150a4  push    edx; pRelatedActivityId
0x100150a5  push    edx; pActivityId
0x100150a6  push    offset byte_10008AC1; pEventMetadata
0x100150ab  push    offset hProvider; hProvider
0x100150b0  call    __TlgWrite@24; _TlgWrite(x,x,x,x,x,x)
0x100150b5  jmp     short loc_100150E2
0x100150b7  test    eax, eax
0x100150b9  jnz     short loc_100150E2
0x100150bb  push    dword ptr RegHandle+4
0x100150c1  push    dword ptr RegHandle; RegHandle
0x100150c7  call    ds:__imp__EventUnregister@8; EventUnregister(x,x)
0x100150cd  xorps   xmm0, xmm0
0x100150d0  mov     hProvider, 0
0x100150da  movlpd  RegHandle, xmm0
0x100150e2  mov     ecx, [esp+40h+var_4]
0x100150e6  mov     eax, 1
0x100150eb  pop     esi
0x100150ec  xor     ecx, esp; StackCookie
0x100150ee  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100150f3  add     esp, 3Ch
0x100150f6  retn    0Ch
```
