# KerbPingWlBalloon(_LUID *,WlBalloonType)

- ea: `0x180059cec`
- end: `0x180059e12`
- name: `?KerbPingWlBalloon@@YAEPEAU_LUID@@W4WlBalloonType@@@Z`
- size: `294`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180058f14`
- `0x1800ab118`

## callees

- `0x180059cec`
- `0x180070680`
- `0x18007108c`
- `0x1800710ec`
- `0x18008b70c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180059d65`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180059d65`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180059daa`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180059daa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059d73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059db4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059d73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059db4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059de9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059de9`

## string_xrefs

- `0x180059d7d`: `Opening winlogon event %S failed %x\n`

## pseudocode

```c
char __fastcall KerbPingWlBalloon(_DWORD *a1, int a2)
{
  const wchar_t *v4; // rax
  HANDLE v5; // rax
  void *v6; // rbx
  DWORD v7; // eax
  DWORD LastError; // eax
  wchar_t Buffer[512]; // [rsp+30h] [rbp-418h] BYREF

  memset_0(Buffer, 0, sizeof(Buffer));
  v4 = L"WlballoonKerberosNotificationEventName";
  if ( a2 )
    v4 = L"WlballoonKerberosCloudPasswordExpired";
  swprintf_s(Buffer, 0x1FFu, L"Global\\%08x%08x_%s", (unsigned int)a1[1], *a1, v4);
  v5 = OpenEventW(2u, 0, Buffer);
  v6 = v5;
  if ( v5 )
  {
    if ( !SetEvent(v5) )
    {
      LastError = GetLastError();
      KerbTracerT::Log(1, "KerbPingWlBalloon", 1655, "SETTING winlogon event %S failed %x\n", Buffer, LastError);
    }
    CloseHandle(v6);
    return 1;
  }
  else
  {
    v7 = GetLastError();
    KerbTracerT::Log(3, "KerbPingWlBalloon", 1649, "Opening winlogon event %S failed %x\n", Buffer, v7);
    return 0;
  }
}

```

## disassembly

```asm
0x180059cec  mov     [rsp+arg_8], rbx
0x180059cf1  push    rdi
0x180059cf2  sub     rsp, 440h
0x180059cf9  mov     rax, cs:__security_cookie
0x180059d00  xor     rax, rsp
0x180059d03  mov     [rsp+448h+var_18], rax
0x180059d0b  mov     ebx, edx
0x180059d0d  mov     rdi, rcx
0x180059d10  xor     edx, edx; Val
0x180059d12  lea     rcx, [rsp+448h+Buffer]; void *
0x180059d17  mov     r8d, 400h; Size
0x180059d1d  call    memset_0
0x180059d22  mov     r9d, [rdi+4]
0x180059d26  lea     rcx, aWlballoonkerbe_0; "WlballoonKerberosCloudPasswordExpired"
0x180059d2d  test    ebx, ebx
0x180059d2f  lea     rax, aWlballoonkerbe; "WlballoonKerberosNotificationEventName"
0x180059d36  lea     r8, aGlobal08x08xS; "Global\\%08x%08x_%s"
0x180059d3d  mov     edx, 1FFh; BufferCount
0x180059d42  cmovnz  rax, rcx
0x180059d46  lea     rcx, [rsp+448h+Buffer]; Buffer
0x180059d4b  mov     [rsp+448h+var_420], rax
0x180059d50  mov     eax, [rdi]
0x180059d52  mov     dword ptr [rsp+448h+var_428], eax
0x180059d56  call    swprintf_s
0x180059d5b  xor     edx, edx; bInheritHandle
0x180059d5d  lea     r8, [rsp+448h+Buffer]; lpName
0x180059d62  lea     ecx, [rdx+2]; dwDesiredAccess
0x180059d65  call    cs:__imp_OpenEventW
0x180059d6b  mov     rbx, rax
0x180059d6e  test    rax, rax
0x180059d71  jnz     short loc_180059DA7
0x180059d73  call    cs:__imp_GetLastError
0x180059d79  mov     dword ptr [rsp+448h+var_420], eax
0x180059d7d  lea     r9, aOpeningWinlogo; "Opening winlogon event %S failed %x\n"
0x180059d84  lea     rax, [rsp+448h+Buffer]
0x180059d89  mov     r8d, 671h
0x180059d8f  lea     rdx, aKerbpingwlball; "KerbPingWlBalloon"
0x180059d96  mov     [rsp+448h+var_428], rax
0x180059d9b  lea     ecx, [rbx+3]
0x180059d9e  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180059da3  xor     al, al
0x180059da5  jmp     short loc_180059DF1
0x180059da7  mov     rcx, rbx; hEvent
0x180059daa  call    cs:__imp_SetEvent
0x180059db0  test    eax, eax
0x180059db2  jnz     short loc_180059DE6
0x180059db4  call    cs:__imp_GetLastError
0x180059dba  lea     rcx, [rsp+448h+Buffer]
0x180059dbf  mov     dword ptr [rsp+448h+var_420], eax
0x180059dc3  mov     [rsp+448h+var_428], rcx
0x180059dc8  mov     r8d, 677h
0x180059dce  mov     ecx, 1
0x180059dd3  lea     r9, aSettingWinlogo; "SETTING winlogon event %S failed %x\n"
0x180059dda  lea     rdx, aKerbpingwlball; "KerbPingWlBalloon"
0x180059de1  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180059de6  mov     rcx, rbx; hObject
0x180059de9  call    cs:__imp_CloseHandle
0x180059def  mov     al, 1
0x180059df1  mov     rcx, [rsp+448h+var_18]
0x180059df9  xor     rcx, rsp; StackCookie
0x180059dfc  call    __security_check_cookie
0x180059e01  mov     rbx, [rsp+448h+arg_8]
0x180059e09  add     rsp, 440h
0x180059e10  pop     rdi
0x180059e11  retn
```
