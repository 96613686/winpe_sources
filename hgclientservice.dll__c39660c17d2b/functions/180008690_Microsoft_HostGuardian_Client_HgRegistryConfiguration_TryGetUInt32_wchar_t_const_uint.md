# Microsoft::HostGuardian::Client::HgRegistryConfiguration::TryGetUInt32(wchar_t const *,uint *)

- ea: `0x180008690`
- end: `0x18000872d`
- name: `?TryGetUInt32@HgRegistryConfiguration@Client@HostGuardian@Microsoft@@UEAAJPEB_WPEAI@Z`
- size: `157`
- prototype: `int __fastcall(Microsoft::HostGuardian::Client::HgRegistryConfiguration *this, const wchar_t *, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800064b4`
- `0x180008498`
- `0x180008690`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800086d2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800086d2`

## string_xrefs

- `0x180008708`: `servercommon\base\securehostingservice\common\service\lib\hgregistryconfiguration.cpp`

## pseudocode

```c
int __fastcall Microsoft::HostGuardian::Client::HgRegistryConfiguration::TryGetUInt32(
        Microsoft::HostGuardian::Client::HgRegistryConfiguration *this,
        const wchar_t *a2,
        unsigned int *a3)
{
  HKEY v3; // rcx
  unsigned int ValueW; // eax
  unsigned int v5; // r8d
  unsigned int v7; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD v9; // [rsp+50h] [rbp+8h] BYREF
  unsigned int *v10; // [rsp+60h] [rbp+18h] BYREF
  DWORD v11; // [rsp+68h] [rbp+20h] BYREF

  v10 = a3;
  v3 = (HKEY)*((_QWORD *)this + 1);
  v9 = 0;
  v11 = 4;
  ValueW = RegGetValueW(v3, 0, a2, 0x18u, &v9, &v10, &v11);
  if ( ValueW )
    return wil::details::in1diag3::Return_Win32(retaddr, (void *)0x57, v5, (const char *)ValueW, v7);
  if ( v9 - 4 <= 1 || v11 == 4 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5C,
    (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgregistryconfiguration.cpp",
    (const char *)0x8000FFFFLL,
    v7);
  return -2147418113;
}

```

## disassembly

```asm
0x180008690  mov     r11, rsp
0x180008693  mov     [r11+18h], r8
0x180008697  sub     rsp, 48h
0x18000869b  mov     rcx, [rcx+8]; hkey
0x18000869f  lea     rax, [r11+20h]
0x1800086a3  mov     [r11-18h], rax
0x1800086a7  mov     r8, rdx; lpValue
0x1800086aa  lea     rax, [r11+18h]
0x1800086ae  mov     [rsp+48h+arg_0], 0
0x1800086b6  mov     [r11-20h], rax
0x1800086ba  mov     r9d, 18h; dwFlags
0x1800086c0  lea     rax, [r11+8]
0x1800086c4  mov     [rsp+48h+arg_18], 4
0x1800086cc  xor     edx, edx; lpSubKey
0x1800086ce  mov     [r11-28h], rax
0x1800086d2  call    cs:__imp_RegGetValueW
0x1800086d8  test    eax, eax
0x1800086da  jz      short loc_1800086F0
0x1800086dc  mov     rcx, [rsp+48h]; this
0x1800086e1  mov     r9d, eax; char *
0x1800086e4  mov     edx, 57h ; 'W'; void *
0x1800086e9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800086ee  jmp     short loc_180008728
0x1800086f0  mov     eax, [rsp+48h+arg_0]
0x1800086f4  add     eax, 0FFFFFFFCh
0x1800086f7  cmp     eax, 1
0x1800086fa  jbe     short loc_180008726
0x1800086fc  cmp     [rsp+48h+arg_18], 4
0x180008701  jz      short loc_180008726
0x180008703  mov     rcx, [rsp+48h]; this
0x180008708  lea     r8, aServercommonBa_9; "servercommon\\base\\securehostingservic"...
0x18000870f  mov     r9d, 8000FFFFh; char *
0x180008715  mov     edx, 5Ch ; '\'; void *
0x18000871a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000871f  mov     eax, 8000FFFFh
0x180008724  jmp     short loc_180008728
0x180008726  xor     eax, eax
0x180008728  add     rsp, 48h
0x18000872c  retn
```
