# StSetTimelyKey(int,int)

- ea: `0x18001e140`
- end: `0x18001e267`
- name: `?StSetTimelyKey@@YAKHH@Z`
- size: `295`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d920`
- `0x180027318`

## callees

- `0x18000a9c0`
- `0x18000c230`
- `0x18001e140`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001e1bc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001e1bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e226`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e226`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001e211`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001e211`

## string_xrefs

- `0x18001e197`: `SYSTEM\CurrentControlSet\Control\Winlogon\Notifications\Components\Dot3svc`

## pseudocode

```c
__int64 __fastcall StSetTimelyKey(int a1)
{
  unsigned int v2; // ebx
  const BYTE *v3; // rcx
  __int64 v4; // rax
  HKEY hKey; // [rsp+90h] [rbp+18h] BYREF

  hKey = 0;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 47, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids);
  }
  v2 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Control\\Winlogon\\Notifications\\Components\\Dot3svc",
         0,
         0,
         0,
         0x20006u,
         0,
         &hKey,
         0);
  if ( !v2 )
  {
    v3 = (const BYTE *)L"Logon,Logoff";
    if ( !a1 )
      v3 = L"Logoff";
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)&v3[2 * v4] );
    v2 = RegSetValueExW(hKey, L"Events", 0, 1u, v3, 2 * v4 + 2);
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 49, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids, v2);
  }
  return v2;
}

```

## disassembly

```asm
0x18001e140  mov     rax, rsp
0x18001e143  push    rbx
0x18001e144  push    rbp
0x18001e145  push    rsi
0x18001e146  push    rdi
0x18001e147  sub     rsp, 58h
0x18001e14b  xor     esi, esi
0x18001e14d  mov     edi, ecx
0x18001e14f  mov     [rax+18h], rsi
0x18001e153  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e15a  lea     rbp, WPP_GLOBAL_Control
0x18001e161  cmp     rcx, rbp
0x18001e164  jz      short loc_18001E185
0x18001e166  cmp     byte ptr [rcx+19h], 4
0x18001e16a  jb      short loc_18001E185
0x18001e16c  test    byte ptr [rcx+1Ch], 1
0x18001e170  jz      short loc_18001E185
0x18001e172  mov     rcx, [rcx+10h]
0x18001e176  lea     edx, [rsi+2Fh]
0x18001e179  lea     r8, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids
0x18001e180  call    WPP_SF_
0x18001e185  mov     [rsp+78h+lpdwDisposition], rsi; lpdwDisposition
0x18001e18a  lea     rax, [rsp+78h+hKey]
0x18001e192  mov     [rsp+78h+phkResult], rax; phkResult
0x18001e197  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Win"...
0x18001e19e  mov     [rsp+78h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18001e1a3  xor     r9d, r9d; lpClass
0x18001e1a6  mov     [rsp+78h+samDesired], 20006h; samDesired
0x18001e1ae  xor     r8d, r8d; Reserved
0x18001e1b1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e1b8  mov     [rsp+78h+dwOptions], esi; dwOptions
0x18001e1bc  call    cs:__imp_RegCreateKeyExW
0x18001e1c2  mov     ebx, eax
0x18001e1c4  test    eax, eax
0x18001e1c6  jnz     short loc_18001E219
0x18001e1c8  test    edi, edi
0x18001e1ca  lea     rax, aLogoff; "Logoff"
0x18001e1d1  lea     rcx, aLogonLogoff; "Logon,Logoff"
0x18001e1d8  cmovz   rcx, rax
0x18001e1dc  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001e1e0  inc     rax
0x18001e1e3  cmp     [rcx+rax*2], si
0x18001e1e7  jnz     short loc_18001E1E0
0x18001e1e9  lea     eax, ds:2[rax*2]
0x18001e1f0  mov     r9d, 1; dwType
0x18001e1f6  mov     [rsp+78h+samDesired], eax; cbData
0x18001e1fa  lea     rdx, aEvents; "Events"
0x18001e201  mov     qword ptr [rsp+78h+dwOptions], rcx; lpData
0x18001e206  xor     r8d, r8d; Reserved
0x18001e209  mov     rcx, [rsp+78h+hKey]; hKey
0x18001e211  call    cs:__imp_RegSetValueExW
0x18001e217  mov     ebx, eax
0x18001e219  mov     rcx, [rsp+78h+hKey]; hKey
0x18001e221  test    rcx, rcx
0x18001e224  jz      short loc_18001E22C
0x18001e226  call    cs:__imp_RegCloseKey
0x18001e22c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e233  cmp     rcx, rbp
0x18001e236  jz      short loc_18001E25C
0x18001e238  cmp     byte ptr [rcx+19h], 4
0x18001e23c  jb      short loc_18001E25C
0x18001e23e  test    byte ptr [rcx+1Ch], 1
0x18001e242  jz      short loc_18001E25C
0x18001e244  mov     rcx, [rcx+10h]
0x18001e248  lea     r8, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids
0x18001e24f  mov     edx, 31h ; '1'
0x18001e254  mov     r9d, ebx
0x18001e257  call    WPP_SF_d
0x18001e25c  mov     eax, ebx
0x18001e25e  add     rsp, 58h
0x18001e262  pop     rdi
0x18001e263  pop     rsi
0x18001e264  pop     rbp
0x18001e265  pop     rbx
0x18001e266  retn
```
