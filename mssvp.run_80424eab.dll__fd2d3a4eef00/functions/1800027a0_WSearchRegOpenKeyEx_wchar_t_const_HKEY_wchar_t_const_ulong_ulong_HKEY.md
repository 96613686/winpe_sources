# WSearchRegOpenKeyEx(wchar_t const *,HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)

- ea: `0x1800027a0`
- end: `0x180002866`
- name: `?WSearchRegOpenKeyEx@@YAJPEB_WPEAUHKEY__@@0KKPEAPEAU1@@Z`
- size: `198`
- prototype: `int(const wchar_t *, HKEY, const wchar_t *, unsigned int, unsigned int, HKEY *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180035e64`
- `0x180035f0c`

## callees

- `0x1800027a0`
- `0x180006270`
- `0x18003833c`
- `0x180038474`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000283b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000283b`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800027e9`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800027e9`

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
0x1800027a0  mov     [rsp+arg_0], rbx
0x1800027a5  mov     [rsp+arg_18], rsi
0x1800027aa  push    rdi
0x1800027ab  sub     rsp, 260h
0x1800027b2  mov     rax, cs:__security_cookie
0x1800027b9  xor     rax, rsp
0x1800027bc  mov     [rsp+268h+var_18], rax
0x1800027c4  mov     rsi, [rsp+268h+arg_28]
0x1800027cc  mov     rdi, r8
0x1800027cf  mov     [rsp+268h+var_238], 0
0x1800027d8  mov     rbx, rdx
0x1800027db  cmp     rdx, 0FFFFFFFF80000002h
0x1800027e2  jnz     short loc_18000281B
0x1800027e4  test    r8, r8
0x1800027e7  jz      short loc_18000281B
0x1800027e9  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800027ef  test    al, al
0x1800027f1  jz      short loc_18000281B
0x1800027f3  lea     rdx, [rsp+268h+var_238]; struct CSearchRegistryRedirectHelper **
0x1800027f8  call    ?GetSearchRegistryRedirect@@YA_NPEB_WPEAPEAVCSearchRegistryRedirectHelper@@@Z; GetSearchRegistryRedirect(wchar_t const *,CSearchRegistryRedirectHelper * *)
0x1800027fd  test    al, al
0x1800027ff  jz      short loc_18000281B
0x180002801  mov     rcx, [rsp+268h+var_238]; this
0x180002806  lea     r8, [rsp+268h+var_228]; wchar_t *
0x18000280b  mov     rdx, rdi; wchar_t *
0x18000280e  call    ?MapRegistryKeyPath@CSearchRegistryRedirectHelper@@QEAAJPEB_WPEA_WK@Z; CSearchRegistryRedirectHelper::MapRegistryKeyPath(wchar_t const *,wchar_t *,ulong)
0x180002813  test    eax, eax
0x180002815  js      short loc_18000281B
0x180002817  mov     al, 1
0x180002819  jmp     short loc_18000281D
0x18000281b  xor     al, al
0x18000281d  mov     r9d, [rsp+268h+samDesired]; samDesired
0x180002825  lea     rdx, [rsp+268h+var_228]
0x18000282a  test    al, al
0x18000282c  mov     [rsp+268h+phkResult], rsi; phkResult
0x180002831  mov     rcx, rbx; hKey
0x180002834  cmovz   rdx, rdi; lpSubKey
0x180002838  xor     r8d, r8d; ulOptions
0x18000283b  call    cs:__imp_RegOpenKeyExW
0x180002841  mov     rcx, [rsp+268h+var_18]
0x180002849  xor     rcx, rsp; StackCookie
0x18000284c  call    __security_check_cookie
0x180002851  lea     r11, [rsp+268h+var_8]
0x180002859  mov     rbx, [r11+10h]
0x18000285d  mov     rsi, [r11+28h]
0x180002861  mov     rsp, r11
0x180002864  pop     rdi
0x180002865  retn
```
