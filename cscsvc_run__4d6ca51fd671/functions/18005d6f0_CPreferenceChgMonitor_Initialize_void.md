# CPreferenceChgMonitor::Initialize(void)

- ea: `0x18005d6f0`
- end: `0x18005d7b2`
- name: `?Initialize@CPreferenceChgMonitor@@UEAAJXZ`
- size: `194`
- prototype: `__int64 __fastcall(CPreferenceChgMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005df80`

## callees

- `0x180044554`
- `0x18005d6f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d78b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d78b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005d725`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005d725`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005d77c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005d77c`

## string_xrefs

- `0x18005d706`: `Software\Microsoft\Windows\CurrentVersion\NetCache`

## pseudocode

```c
__int64 __fastcall CPreferenceChgMonitor::Initialize(HKEY *this)
{
  LSTATUS v2; // eax
  DWORD LastError; // ebx
  HKEY EventW; // rax

  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\NetCache",
         0,
         0x20019u,
         this + 1);
  LastError = v2;
  if ( v2 )
  {
    if ( v2 == 2 )
      return 0;
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_dS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        47,
        (unsigned int)WPP_9d3e204fa1593b4c7479993b85b659fe_Traceguids,
        v2,
        (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\NetCache");
  }
  else
  {
    EventW = (HKEY)CreateEventW(0, 0, 0, 0);
    this[2] = EventW;
    if ( EventW )
      return LastError;
    LastError = GetLastError();
  }
  if ( (int)LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return LastError;
}

```

## disassembly

```asm
0x18005d6f0  mov     [rsp+arg_0], rbx
0x18005d6f5  mov     [rsp+arg_8], rsi
0x18005d6fa  push    rdi
0x18005d6fb  sub     rsp, 30h
0x18005d6ff  lea     rax, [rcx+8]
0x18005d703  mov     rdi, rcx
0x18005d706  lea     rsi, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005d70d  mov     [rsp+38h+phkResult], rax; phkResult
0x18005d712  mov     rdx, rsi; lpSubKey
0x18005d715  mov     r9d, 20019h; samDesired
0x18005d71b  xor     r8d, r8d; ulOptions
0x18005d71e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005d725  call    cs:__imp_RegOpenKeyExW
0x18005d72b  mov     ebx, eax
0x18005d72d  test    eax, eax
0x18005d72f  jz      short loc_18005D772
0x18005d731  cmp     eax, 2
0x18005d734  jnz     short loc_18005D73A
0x18005d736  xor     ebx, ebx
0x18005d738  jmp     short loc_18005D7A0
0x18005d73a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d741  lea     rax, WPP_GLOBAL_Control
0x18005d748  cmp     rcx, rax
0x18005d74b  jz      short loc_18005D793
0x18005d74d  test    byte ptr [rcx+1Ch], 2
0x18005d751  jz      short loc_18005D793
0x18005d753  mov     rcx, [rcx+10h]
0x18005d757  lea     r8, WPP_9d3e204fa1593b4c7479993b85b659fe_Traceguids
0x18005d75e  mov     edx, 2Fh ; '/'
0x18005d763  mov     [rsp+38h+phkResult], rsi
0x18005d768  mov     r9d, ebx
0x18005d76b  call    WPP_SF_dS
0x18005d770  jmp     short loc_18005D793
0x18005d772  xor     r9d, r9d; lpName
0x18005d775  xor     r8d, r8d; bInitialState
0x18005d778  xor     edx, edx; bManualReset
0x18005d77a  xor     ecx, ecx; lpEventAttributes
0x18005d77c  call    cs:__imp_CreateEventW
0x18005d782  mov     [rdi+10h], rax
0x18005d786  test    rax, rax
0x18005d789  jnz     short loc_18005D7A0
0x18005d78b  call    cs:__imp_GetLastError
0x18005d791  mov     ebx, eax
0x18005d793  test    ebx, ebx
0x18005d795  jle     short loc_18005D7A0
0x18005d797  movzx   ebx, bx
0x18005d79a  or      ebx, 80070000h
0x18005d7a0  mov     rsi, [rsp+38h+arg_8]
0x18005d7a5  mov     eax, ebx
0x18005d7a7  mov     rbx, [rsp+38h+arg_0]
0x18005d7ac  add     rsp, 30h
0x18005d7b0  pop     rdi
0x18005d7b1  retn
```
