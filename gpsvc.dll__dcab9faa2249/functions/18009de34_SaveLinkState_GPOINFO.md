# SaveLinkState(_GPOINFO *)

- ea: `0x18009de34`
- end: `0x18009dfc1`
- name: `?SaveLinkState@@YAKPEAU_GPOINFO@@@Z`
- size: `397`
- prototype: `unsigned int __fastcall(struct _GPOINFO *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005ce5c`

## callees

- `0x180003770`
- `0x180075ec0`
- `0x18007d320`
- `0x18009de34`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009deae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009df94`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009deae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009df94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009de72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009de72`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009df34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009df34`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009df27`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009df27`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009def9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009def9`

## string_xrefs

- `0x18009df1b`: `SlowLink`
- `0x18009df56`: `SaveLinkState: Failed Registry operation with %d`
- `0x18009df80`: `SaveLinkState: Failed Registry operation with %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SaveLinkState(struct _GPOINFO *a1)
{
  unsigned int v2; // edi
  DWORD LastError; // ebx
  const wchar_t *v4; // r9
  int v5; // eax
  unsigned int v6; // ebx
  unsigned int v8; // edi
  BYTE Data[8]; // [rsp+50h] [rbp-248h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-240h] BYREF
  DWORD v11; // [rsp+60h] [rbp-238h]
  WCHAR SubKey[264]; // [rsp+70h] [rbp-228h] BYREF

  v2 = *(_DWORD *)a1;
  hKey = 0;
  *(_DWORD *)Data = (v2 >> 18) & 1;
  LastError = GetLastError();
  v11 = LastError;
  v4 = L"Machine";
  if ( (v2 & 1) == 0 )
    v4 = (const wchar_t *)*((_QWORD *)a1 + 9);
  v5 = StringCchPrintfW(SubKey, 0x105u, L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\State\\%ws", v4);
  if ( v5 >= 0 )
  {
    v8 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
    if ( v8 || (v8 = RegSetValueExW(hKey, L"SlowLink", 0, 4u, Data, 4u), RegCloseKey(hKey), v8) )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"SaveLinkState: Failed Registry operation with %d", v8);
        }
        else if ( g_lpDebugMsgContextInstance )
        {
          if ( g_lpDebugMsgContext )
            RedirectDebugMsg(2u, L"SaveLinkState: Failed Registry operation with %d", v8);
        }
      }
    }
    SetLastError(LastError);
    return v8;
  }
  else
  {
    v6 = (unsigned __int16)v5;
    SetLastError((unsigned __int16)v5);
    return v6;
  }
}

```

## disassembly

```asm
0x18009de34  mov     [rsp+arg_8], rbx
0x18009de39  mov     [rsp+arg_10], rsi
0x18009de3e  push    rdi
0x18009de3f  sub     rsp, 290h
0x18009de46  mov     rax, cs:__security_cookie
0x18009de4d  xor     rax, rsp
0x18009de50  mov     [rsp+298h+var_18], rax
0x18009de58  mov     rsi, rcx
0x18009de5b  mov     eax, [rcx]
0x18009de5d  mov     edi, eax
0x18009de5f  mov     [rsp+298h+hKey], 0
0x18009de68  shr     eax, 12h
0x18009de6b  and     eax, 1
0x18009de6e  mov     dword ptr [rsp+298h+Data], eax
0x18009de72  call    cs:__imp_GetLastError
0x18009de78  mov     ebx, eax
0x18009de7a  mov     [rsp+298h+var_238], eax
0x18009de7e  bt      edi, 0
0x18009de82  lea     r9, aMachine; "Machine"
0x18009de89  jb      short loc_18009DE8F
0x18009de8b  mov     r9, [rsi+48h]
0x18009de8f  lea     r8, aSoftwareMicros_13; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18009de96  mov     edx, 105h; unsigned __int64
0x18009de9b  lea     rcx, [rsp+298h+SubKey]; unsigned __int16 *
0x18009dea0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18009dea5  test    eax, eax
0x18009dea7  jns     short loc_18009DEBB
0x18009dea9  movzx   ebx, ax
0x18009deac  mov     ecx, ebx; dwErrCode
0x18009deae  call    cs:__imp_SetLastError
0x18009deb4  mov     eax, ebx
0x18009deb6  jmp     loc_18009DF9C
0x18009debb  mov     [rsp+298h+lpdwDisposition], 0; lpdwDisposition
0x18009dec4  lea     rax, [rsp+298h+hKey]
0x18009dec9  mov     [rsp+298h+phkResult], rax; phkResult
0x18009dece  mov     [rsp+298h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18009ded7  mov     [rsp+298h+samDesired], 0F003Fh; samDesired
0x18009dedf  mov     [rsp+298h+dwOptions], 0; dwOptions
0x18009dee7  xor     r9d, r9d; lpClass
0x18009deea  xor     r8d, r8d; Reserved
0x18009deed  lea     rdx, [rsp+298h+SubKey]; lpSubKey
0x18009def2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009def9  call    cs:__imp_RegCreateKeyExW
0x18009deff  mov     edi, eax
0x18009df01  test    eax, eax
0x18009df03  jnz     short loc_18009DF3E
0x18009df05  lea     r9d, [rax+4]; dwType
0x18009df09  mov     [rsp+298h+samDesired], r9d; cbData
0x18009df0e  lea     rax, [rsp+298h+Data]
0x18009df13  mov     qword ptr [rsp+298h+dwOptions], rax; lpData
0x18009df18  xor     r8d, r8d; Reserved
0x18009df1b  lea     rdx, aSlowlink_0; "SlowLink"
0x18009df22  mov     rcx, [rsp+298h+hKey]; hKey
0x18009df27  call    cs:__imp_RegSetValueExW
0x18009df2d  mov     edi, eax
0x18009df2f  mov     rcx, [rsp+298h+hKey]; hKey
0x18009df34  call    cs:__imp_RegCloseKey
0x18009df3a  test    edi, edi
0x18009df3c  jz      short loc_18009DF92
0x18009df3e  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x18009df45  jz      short loc_18009DF92
0x18009df47  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18009df4e  test    rax, rax
0x18009df51  jz      short loc_18009DF69
0x18009df53  mov     r8d, edi
0x18009df56  lea     rdx, aSavelinkstateF; "SaveLinkState: Failed Registry operatio"...
0x18009df5d  mov     ecx, 2
0x18009df62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009df67  jmp     short loc_18009DF92
0x18009df69  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x18009df71  jz      short loc_18009DF92
0x18009df73  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18009df7b  jz      short loc_18009DF92
0x18009df7d  mov     r8d, edi
0x18009df80  lea     rdx, aSavelinkstateF; "SaveLinkState: Failed Registry operatio"...
0x18009df87  mov     ecx, 2; unsigned int
0x18009df8c  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18009df91  nop
0x18009df92  mov     ecx, ebx; dwErrCode
0x18009df94  call    cs:__imp_SetLastError
0x18009df9a  mov     eax, edi
0x18009df9c  mov     rcx, [rsp+298h+var_18]
0x18009dfa4  xor     rcx, rsp; StackCookie
0x18009dfa7  call    __security_check_cookie
0x18009dfac  lea     r11, [rsp+298h+var_8]
0x18009dfb4  mov     rbx, [r11+18h]
0x18009dfb8  mov     rsi, [r11+20h]
0x18009dfbc  mov     rsp, r11
0x18009dfbf  pop     rdi
0x18009dfc0  retn
```
