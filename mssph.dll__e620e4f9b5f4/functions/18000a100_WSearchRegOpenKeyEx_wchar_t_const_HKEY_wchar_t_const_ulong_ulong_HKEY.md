# WSearchRegOpenKeyEx(wchar_t const *,HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)

- ea: `0x18000a100`
- end: `0x18000a1c6`
- name: `?WSearchRegOpenKeyEx@@YAJPEB_WPEAUHKEY__@@0KKPEAPEAU1@@Z`
- size: `198`
- prototype: `int(const wchar_t *, HKEY, const wchar_t *, unsigned int, unsigned int, HKEY *)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18000c748`
- `0x18001ceb8`
- `0x18001de28`
- `0x18001fb44`

## callees

- `0x18000a100`
- `0x18000fcd0`
- `0x18001ff2c`
- `0x180020064`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a19b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a19b`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000a149`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000a149`

## pseudocode

```c
LSTATUS __fastcall WSearchRegOpenKeyEx(
        const wchar_t *a1,
        HKEY a2,
        wchar_t *a3,
        __int64 a4,
        REGSAM samDesired,
        HKEY *phkResult)
{
  const wchar_t *v8; // rcx
  bool v9; // al
  wchar_t *v10; // rdx
  struct CSearchRegistryRedirectHelper *v12; // [rsp+30h] [rbp-238h] BYREF
  wchar_t v13[264]; // [rsp+40h] [rbp-228h] BYREF

  v12 = 0;
  v9 = a2 == HKEY_LOCAL_MACHINE
    && a3
    && (unsigned __int8)RtlIsStateSeparationEnabled(a1)
    && GetSearchRegistryRedirect(v8, &v12)
    && (int)CSearchRegistryRedirectHelper::MapRegistryKeyPath((const wchar_t *)v12, a3, v13) >= 0;
  v10 = v13;
  if ( !v9 )
    v10 = a3;
  return RegOpenKeyExW(a2, v10, 0, samDesired, phkResult);
}

```

## disassembly

```asm
0x18000a100  mov     [rsp+arg_0], rbx
0x18000a105  mov     [rsp+arg_18], rsi
0x18000a10a  push    rdi
0x18000a10b  sub     rsp, 260h
0x18000a112  mov     rax, cs:__security_cookie
0x18000a119  xor     rax, rsp
0x18000a11c  mov     [rsp+268h+var_18], rax
0x18000a124  mov     rsi, [rsp+268h+arg_28]
0x18000a12c  mov     rdi, r8
0x18000a12f  mov     [rsp+268h+var_238], 0
0x18000a138  mov     rbx, rdx
0x18000a13b  cmp     rdx, 0FFFFFFFF80000002h
0x18000a142  jnz     short loc_18000A17B
0x18000a144  test    r8, r8
0x18000a147  jz      short loc_18000A17B
0x18000a149  call    cs:__imp_RtlIsStateSeparationEnabled
0x18000a14f  test    al, al
0x18000a151  jz      short loc_18000A17B
0x18000a153  lea     rdx, [rsp+268h+var_238]; struct CSearchRegistryRedirectHelper **
0x18000a158  call    ?GetSearchRegistryRedirect@@YA_NPEB_WPEAPEAVCSearchRegistryRedirectHelper@@@Z; GetSearchRegistryRedirect(wchar_t const *,CSearchRegistryRedirectHelper * *)
0x18000a15d  test    al, al
0x18000a15f  jz      short loc_18000A17B
0x18000a161  mov     rcx, [rsp+268h+var_238]; this
0x18000a166  lea     r8, [rsp+268h+var_228]; wchar_t *
0x18000a16b  mov     rdx, rdi; wchar_t *
0x18000a16e  call    ?MapRegistryKeyPath@CSearchRegistryRedirectHelper@@QEAAJPEB_WPEA_WK@Z; CSearchRegistryRedirectHelper::MapRegistryKeyPath(wchar_t const *,wchar_t *,ulong)
0x18000a173  test    eax, eax
0x18000a175  js      short loc_18000A17B
0x18000a177  mov     al, 1
0x18000a179  jmp     short loc_18000A17D
0x18000a17b  xor     al, al
0x18000a17d  mov     r9d, [rsp+268h+samDesired]; samDesired
0x18000a185  lea     rdx, [rsp+268h+var_228]
0x18000a18a  test    al, al
0x18000a18c  mov     [rsp+268h+phkResult], rsi; phkResult
0x18000a191  mov     rcx, rbx; hKey
0x18000a194  cmovz   rdx, rdi; lpSubKey
0x18000a198  xor     r8d, r8d; ulOptions
0x18000a19b  call    cs:__imp_RegOpenKeyExW
0x18000a1a1  mov     rcx, [rsp+268h+var_18]
0x18000a1a9  xor     rcx, rsp; StackCookie
0x18000a1ac  call    __security_check_cookie
0x18000a1b1  lea     r11, [rsp+268h+var_8]
0x18000a1b9  mov     rbx, [r11+10h]
0x18000a1bd  mov     rsi, [r11+28h]
0x18000a1c1  mov     rsp, r11
0x18000a1c4  pop     rdi
0x18000a1c5  retn
```
