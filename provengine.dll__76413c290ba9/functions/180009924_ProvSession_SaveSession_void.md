# ProvSession::SaveSession(void)

- ea: `0x180009924`
- end: `0x180009b7d`
- name: `?SaveSession@ProvSession@@AEAAJXZ`
- size: `601`
- prototype: `__int64 __fastcall(ProvSession *__hidden this)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180007cc0`
- `0x180008050`
- `0x18000b300`

## callees

- `0x1800010c8`
- `0x18000915c`
- `0x1800098dc`
- `0x180009900`
- `0x180009924`
- `0x18000a4e4`
- `0x180033144`
- `0x180033354`
- `0x180043750`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180009b45`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009b45`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009a76`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009aec`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009a76`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009aec`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800099d1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800099d1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall ProvSession::SaveSession(ProvSession *this)
{
  HKEY *v2; // rsi
  const WCHAR *v3; // rdx
  unsigned int Key; // eax
  const unsigned __int16 *v6; // r8
  signed int v7; // ebx
  __int64 v8; // rdx
  LSTATUS v9; // eax
  __int64 v10; // rcx
  const unsigned __int16 *v11; // rax
  LSTATUS v12; // eax
  __int64 CurrentTimeString; // rax
  unsigned int dwOptions; // [rsp+20h] [rbp-68h]
  BYTE Data[8]; // [rsp+50h] [rbp-38h] BYREF
  void *v16[4]; // [rsp+58h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  if ( (unsigned int)dword_18005A000 > 4 )
    tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, word_18004E262, 0, 0, 2, v16);
  v2 = (HKEY *)((char *)this + 96);
  if ( !*((_QWORD *)this + 12) )
  {
    *v2 = 0;
    v3 = (const WCHAR *)((char *)this + 24);
    if ( *((_QWORD *)this + 6) >= 8u )
      v3 = *(const WCHAR **)v3;
    Key = RegCreateKeyExW(*((HKEY *)this + 11), v3, 0, 0, 0, 0xFu, 0, (PHKEY)this + 12, 0);
    if ( Key )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0xBE,
               (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provsession.cpp",
               (const char *)Key,
               dwOptions);
    v6 = (const unsigned __int16 *)((char *)this + 56);
    if ( *((_QWORD *)this + 10) >= 8u )
      v6 = *(const unsigned __int16 **)v6;
    v7 = RegSetSzValue(*v2, L"BeginTime", v6);
    if ( v7 < 0 )
    {
      v8 = 193;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provsession.cpp",
        (const char *)(unsigned int)v7,
        dwOptions);
      return v7;
    }
    ProvSession::UpdateRegistryLinks(this);
  }
  *(_DWORD *)Data = *((_DWORD *)this + 4);
  v9 = RegSetValueExW(*v2, L"RebootCount", 0, 4u, Data, 4u);
  v7 = v9;
  if ( v9 > 0 )
    v7 = (unsigned __int16)v9 | 0x80070000;
  if ( v7 < 0 )
  {
    v8 = 199;
    goto LABEL_12;
  }
  v11 = (const unsigned __int16 *)ProvSession::MapSessionStateToString(v10, *((unsigned int *)this + 5));
  v7 = RegSetSzValue(*v2, L"State", v11);
  if ( v7 < 0 )
  {
    v8 = 202;
    goto LABEL_12;
  }
  *(_DWORD *)Data = *((_DWORD *)this + 5);
  v12 = RegSetValueExW(*v2, L"StateValue", 0, 4u, Data, 4u);
  v7 = v12;
  if ( v12 > 0 )
    v7 = (unsigned __int16)v12 | 0x80070000;
  if ( v7 < 0 )
  {
    v8 = 203;
    goto LABEL_12;
  }
  CurrentTimeString = GetCurrentTimeString(v16);
  if ( *(_QWORD *)(CurrentTimeString + 24) >= 8u )
    CurrentTimeString = *(_QWORD *)CurrentTimeString;
  v7 = RegSetSzValue(*v2, L"LastRunTime", (const unsigned __int16 *)CurrentTimeString);
  if ( v16[3] >= (void *)8 )
    operator delete(v16[0]);
  if ( v7 < 0 )
  {
    v8 = 206;
    goto LABEL_12;
  }
  return 0;
}

```

## disassembly

```asm
0x180009924  mov     r11, rsp
0x180009927  mov     [r11+10h], rbx
0x18000992b  mov     [r11+18h], rsi
0x18000992f  push    rdi
0x180009930  sub     rsp, 80h
0x180009937  mov     rax, cs:__security_cookie
0x18000993e  xor     rax, rsp
0x180009941  mov     [rsp+88h+var_10], rax
0x180009946  mov     rdi, rcx
0x180009949  mov     eax, cs:dword_18005A000
0x18000994f  cmp     eax, 4
0x180009952  jbe     short loc_18000997D
0x180009954  lea     rax, [r11-30h]
0x180009958  mov     [r11-60h], rax
0x18000995c  mov     [rsp+88h+dwOptions], 2
0x180009964  xor     r9d, r9d
0x180009967  xor     r8d, r8d
0x18000996a  lea     rdx, word_18004E262
0x180009971  lea     rcx, dword_18005A000
0x180009978  call    _tlgWriteTransfer_EventWriteTransfer
0x18000997d  lea     rsi, [rdi+60h]
0x180009981  cmp     qword ptr [rsi], 0
0x180009985  jnz     loc_180009A4A
0x18000998b  mov     qword ptr [rsi], 0
0x180009992  lea     rdx, [rdi+18h]
0x180009996  cmp     qword ptr [rdx+18h], 8
0x18000999b  jb      short loc_1800099A0
0x18000999d  mov     rdx, [rdx]; lpSubKey
0x1800099a0  mov     [rsp+88h+lpdwDisposition], 0; lpdwDisposition
0x1800099a9  mov     [rsp+88h+phkResult], rsi; phkResult
0x1800099ae  mov     [rsp+88h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800099b7  mov     [rsp+88h+samDesired], 0Fh; samDesired
0x1800099bf  mov     [rsp+88h+dwOptions], 0; int
0x1800099c7  xor     r9d, r9d; lpClass
0x1800099ca  xor     r8d, r8d; Reserved
0x1800099cd  mov     rcx, [rdi+58h]; hKey
0x1800099d1  call    cs:__imp_RegCreateKeyExW
0x1800099d7  test    eax, eax
0x1800099d9  jz      short loc_1800099FC
0x1800099db  mov     rcx, [rsp+88h]; this
0x1800099e3  mov     r9d, eax; char *
0x1800099e6  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800099ed  mov     edx, 0BEh; void *
0x1800099f2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800099f7  jmp     loc_180009B5B
0x1800099fc  lea     r8, [rdi+38h]
0x180009a00  cmp     qword ptr [r8+18h], 8
0x180009a05  jb      short loc_180009A0A
0x180009a07  mov     r8, [r8]; unsigned __int16 *
0x180009a0a  lea     rdx, aBegintime; "BeginTime"
0x180009a11  mov     rcx, [rsi]; HKEY
0x180009a14  call    ?RegSetSzValue@@YAJPEAUHKEY__@@PEBG1@Z; RegSetSzValue(HKEY__ *,ushort const *,ushort const *)
0x180009a19  mov     ebx, eax
0x180009a1b  test    eax, eax
0x180009a1d  jns     short loc_180009A42
0x180009a1f  mov     edx, 0C1h; void *
0x180009a24  mov     rcx, [rsp+88h]; this
0x180009a2c  mov     r9d, ebx; char *
0x180009a2f  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180009a36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009a3b  mov     eax, ebx
0x180009a3d  jmp     loc_180009B5B
0x180009a42  mov     rcx, rdi; this
0x180009a45  call    ?UpdateRegistryLinks@ProvSession@@AEAAJXZ; ProvSession::UpdateRegistryLinks(void)
0x180009a4a  mov     eax, [rdi+10h]
0x180009a4d  mov     dword ptr [rsp+88h+Data], eax
0x180009a51  mov     [rsp+88h+samDesired], 4; cbData
0x180009a59  lea     rax, [rsp+88h+Data]
0x180009a5e  mov     qword ptr [rsp+88h+dwOptions], rax; lpData
0x180009a63  mov     r9d, 4; dwType
0x180009a69  xor     r8d, r8d; Reserved
0x180009a6c  lea     rdx, aRebootcount; "RebootCount"
0x180009a73  mov     rcx, [rsi]; hKey
0x180009a76  call    cs:__imp_RegSetValueExW
0x180009a7c  mov     ebx, eax
0x180009a7e  test    eax, eax
0x180009a80  jle     short loc_180009A8B
0x180009a82  movzx   ebx, ax
0x180009a85  or      ebx, 80070000h
0x180009a8b  test    ebx, ebx
0x180009a8d  jns     short loc_180009A96
0x180009a8f  mov     edx, 0C7h
0x180009a94  jmp     short loc_180009A24
0x180009a96  mov     edx, [rdi+14h]
0x180009a99  call    ?MapSessionStateToString@ProvSession@@AEAAPEBGW4__MIDL___MIDL_itf_mvengine_0000_0000_0003@@@Z; ProvSession::MapSessionStateToString(__MIDL___MIDL_itf_mvengine_0000_0000_0003)
0x180009a9e  mov     r8, rax; unsigned __int16 *
0x180009aa1  lea     rdx, aState; "State"
0x180009aa8  mov     rcx, [rsi]; HKEY
0x180009aab  call    ?RegSetSzValue@@YAJPEAUHKEY__@@PEBG1@Z; RegSetSzValue(HKEY__ *,ushort const *,ushort const *)
0x180009ab0  mov     ebx, eax
0x180009ab2  test    eax, eax
0x180009ab4  jns     short loc_180009AC0
0x180009ab6  mov     edx, 0CAh
0x180009abb  jmp     loc_180009A24
0x180009ac0  mov     eax, [rdi+14h]
0x180009ac3  mov     dword ptr [rsp+88h+Data], eax
0x180009ac7  mov     [rsp+88h+samDesired], 4; cbData
0x180009acf  lea     rax, [rsp+88h+Data]
0x180009ad4  mov     qword ptr [rsp+88h+dwOptions], rax; lpData
0x180009ad9  mov     r9d, 4; dwType
0x180009adf  xor     r8d, r8d; Reserved
0x180009ae2  lea     rdx, ValueName; "StateValue"
0x180009ae9  mov     rcx, [rsi]; hKey
0x180009aec  call    cs:__imp_RegSetValueExW
0x180009af2  mov     ebx, eax
0x180009af4  test    eax, eax
0x180009af6  jle     short loc_180009B01
0x180009af8  movzx   ebx, ax
0x180009afb  or      ebx, 80070000h
0x180009b01  test    ebx, ebx
0x180009b03  jns     short loc_180009B0F
0x180009b05  mov     edx, 0CBh
0x180009b0a  jmp     loc_180009A24
0x180009b0f  lea     rcx, [rsp+88h+var_30]; void *
0x180009b14  call    ?GetCurrentTimeString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; GetCurrentTimeString(void)
0x180009b19  nop
0x180009b1a  cmp     qword ptr [rax+18h], 8
0x180009b1f  jb      short loc_180009B24
0x180009b21  mov     rax, [rax]
0x180009b24  mov     r8, rax; unsigned __int16 *
0x180009b27  lea     rdx, aLastruntime; "LastRunTime"
0x180009b2e  mov     rcx, [rsi]; HKEY
0x180009b31  call    ?RegSetSzValue@@YAJPEAUHKEY__@@PEBG1@Z; RegSetSzValue(HKEY__ *,ushort const *,ushort const *)
0x180009b36  mov     ebx, eax
0x180009b38  cmp     [rsp+88h+var_18], 8
0x180009b3e  jb      short loc_180009B4B
0x180009b40  mov     rcx, [rsp+88h+var_30]
0x180009b45  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009b4b  test    ebx, ebx
0x180009b4d  jns     short loc_180009B59
0x180009b4f  mov     edx, 0CEh
0x180009b54  jmp     loc_180009A24
0x180009b59  xor     eax, eax
0x180009b5b  mov     rcx, [rsp+88h+var_10]
0x180009b60  xor     rcx, rsp; StackCookie
0x180009b63  call    __security_check_cookie
0x180009b68  lea     r11, [rsp+88h+var_8]
0x180009b70  mov     rbx, [r11+18h]
0x180009b74  mov     rsi, [r11+20h]
0x180009b78  mov     rsp, r11
0x180009b7b  pop     rdi
0x180009b7c  retn
```
