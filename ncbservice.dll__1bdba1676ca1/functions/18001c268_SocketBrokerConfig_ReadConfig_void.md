# SocketBrokerConfig::ReadConfig(void)

- ea: `0x18001c268`
- end: `0x18001c360`
- name: `?ReadConfig@SocketBrokerConfig@@AEAAKXZ`
- size: `248`
- prototype: `unsigned int __fastcall(SocketBrokerConfig *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c0e4`

## callees

- `0x18000a0a0`
- `0x18001c268`
- `0x18002a0dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c2ca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c2ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c34e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c34e`

## string_xrefs

- `0x18001c2e2`: `SocketBrokerConfig::ReadConfig Failed open NCB key`
- `0x18001c2f5`: `SocketBrokerSocketLimit`
- `0x18001c311`: `SocketBrokerContextSizeLimit`
- `0x18001c32d`: `SocketBrokerTriggerLimit`

## pseudocode

```c
__int64 __fastcall SocketBrokerConfig::ReadConfig(SocketBrokerConfig *this)
{
  unsigned int *v1; // rsi
  unsigned int *v2; // r14
  const WCHAR *v3; // rdx
  unsigned int v5; // eax
  __int64 v6; // rdx
  SocketBrokerConfig *v7; // rcx
  unsigned int v8; // ebx
  SocketBrokerConfig *v9; // rcx
  SocketBrokerConfig *v10; // rcx
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF

  *(_DWORD *)this = 100;
  v1 = (unsigned int *)((char *)this + 4);
  v2 = (unsigned int *)((char *)this + 8);
  *((_DWORD *)this + 1) = 10485760;
  *((_DWORD *)this + 2) = 1;
  v3 = (const WCHAR *)&lpSubKey;
  hKey = 0;
  if ( *((_QWORD *)&xmmword_18004D9D0 + 1) > 7u )
    v3 = lpSubKey;
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x20019u, &hKey);
  v8 = v5;
  if ( v5 )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v7, v6, L"SocketBrokerConfig::ReadConfig Failed open NCB key", v5);
  }
  else
  {
    SocketBrokerConfig::ReadDWORDConfig(v7, hKey, L"SocketBrokerSocketLimit", 0x64u, (unsigned int *)this);
    SocketBrokerConfig::ReadDWORDConfig(v9, hKey, L"SocketBrokerContextSizeLimit", 0xA00000u, v1);
    SocketBrokerConfig::ReadDWORDConfig(v10, hKey, L"SocketBrokerTriggerLimit", 1u, v2);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v8;
}

```

## disassembly

```asm
0x18001c268  push    rbx
0x18001c26a  push    rsi
0x18001c26b  push    rdi
0x18001c26c  push    r14
0x18001c26e  sub     rsp, 38h
0x18001c272  mov     dword ptr [rcx], 64h ; 'd'
0x18001c278  lea     rsi, [rcx+4]
0x18001c27c  lea     r14, [rcx+8]
0x18001c280  mov     dword ptr [rsi], 0A00000h
0x18001c286  mov     dword ptr [r14], 1
0x18001c28d  lea     rax, [rsp+58h+hKey]
0x18001c292  cmp     qword ptr cs:xmmword_18004D9D0+8, 7
0x18001c29a  lea     rdx, lpSubKey
0x18001c2a1  mov     rdi, rcx
0x18001c2a4  mov     [rsp+58h+hKey], 0
0x18001c2ad  cmova   rdx, qword ptr cs:lpSubKey; lpSubKey
0x18001c2b5  mov     r9d, 20019h; samDesired
0x18001c2bb  xor     r8d, r8d; ulOptions
0x18001c2be  mov     [rsp+58h+phkResult], rax; phkResult
0x18001c2c3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001c2ca  call    cs:__imp_RegOpenKeyExW
0x18001c2d0  mov     ebx, eax
0x18001c2d2  test    eax, eax
0x18001c2d4  jz      short loc_18001C2F0
0x18001c2d6  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18001c2dd  jz      short loc_18001C344
0x18001c2df  mov     r9d, eax
0x18001c2e2  lea     r8, aSocketbrokerco_1; "SocketBrokerConfig::ReadConfig Failed o"...
0x18001c2e9  call    McTemplateU0zq_EventWriteTransfer
0x18001c2ee  jmp     short loc_18001C344
0x18001c2f0  mov     rdx, [rsp+58h+hKey]; HKEY
0x18001c2f5  lea     r8, aSocketbrokerso; "SocketBrokerSocketLimit"
0x18001c2fc  mov     r9d, 64h ; 'd'; unsigned int
0x18001c302  mov     [rsp+58h+phkResult], rdi; unsigned int *
0x18001c307  call    ?ReadDWORDConfig@SocketBrokerConfig@@AEAAXPEAUHKEY__@@PEAGKPEAK@Z; SocketBrokerConfig::ReadDWORDConfig(HKEY__ *,ushort *,ulong,ulong *)
0x18001c30c  mov     rdx, [rsp+58h+hKey]; HKEY
0x18001c311  lea     r8, aSocketbrokerco; "SocketBrokerContextSizeLimit"
0x18001c318  mov     r9d, 0A00000h; unsigned int
0x18001c31e  mov     [rsp+58h+phkResult], rsi; unsigned int *
0x18001c323  call    ?ReadDWORDConfig@SocketBrokerConfig@@AEAAXPEAUHKEY__@@PEAGKPEAK@Z; SocketBrokerConfig::ReadDWORDConfig(HKEY__ *,ushort *,ulong,ulong *)
0x18001c328  mov     rdx, [rsp+58h+hKey]; HKEY
0x18001c32d  lea     r8, aSocketbrokertr; "SocketBrokerTriggerLimit"
0x18001c334  mov     r9d, 1; unsigned int
0x18001c33a  mov     [rsp+58h+phkResult], r14; unsigned int *
0x18001c33f  call    ?ReadDWORDConfig@SocketBrokerConfig@@AEAAXPEAUHKEY__@@PEAGKPEAK@Z; SocketBrokerConfig::ReadDWORDConfig(HKEY__ *,ushort *,ulong,ulong *)
0x18001c344  mov     rcx, [rsp+58h+hKey]; hKey
0x18001c349  test    rcx, rcx
0x18001c34c  jz      short loc_18001C354
0x18001c34e  call    cs:__imp_RegCloseKey
0x18001c354  mov     eax, ebx
0x18001c356  add     rsp, 38h
0x18001c35a  pop     r14
0x18001c35c  pop     rdi
0x18001c35d  pop     rsi
0x18001c35e  pop     rbx
0x18001c35f  retn
```
