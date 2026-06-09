# _GetCrlPreFetchScheduleParameters

- ea: `0x18001eee8`
- end: `0x18001f04c`
- name: `_GetCrlPreFetchScheduleParameters`
- size: `356`
- prototype: `char __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001dde0`
- `0x18001e834`

## callees

- `0x18001eee8`
- `0x18001f9f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001eff8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001eff8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ef50`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ef50`
- `CRYPTBASE!SystemFunction036` at `0x18001f021`
- `CRYPTBASE!SystemFunction036` at `0x18001f021`

## string_xrefs

- `0x18001ef2b`: `Software\Microsoft\Cryptography\OID\EncodingType 0\CertDllCreateCertificateChainEngine\Config\CrlPreFetch`
- `0x18001ef7e`: `PublishBeforeNextUpdateSeconds`
- `0x18001efc0`: `MinBeforeNextUpdateSeconds`
- `0x18001efd4`: `MinAfterNextUpdateSeconds`

## pseudocode

```c
char __fastcall GetCrlPreFetchScheduleParameters(__int64 a1)
{
  unsigned int v1; // ebx
  int v3; // r14d
  unsigned int v4; // esi
  LSTATUS v5; // eax
  int v6; // ebx
  unsigned int RandomBuffer; // [rsp+70h] [rbp+40h] BYREF
  int v9; // [rsp+78h] [rbp+48h] BYREF
  int v10; // [rsp+80h] [rbp+50h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+58h] BYREF

  v1 = 300;
  hKey = 0;
  *(_QWORD *)a1 = 300;
  v10 = 300;
  v3 = 7200;
  v4 = 3600;
  RandomBuffer = 7200;
  v9 = 3600;
  *(_QWORD *)(a1 + 16) = 0;
  *(_DWORD *)(a1 + 8) = 300;
  *(_DWORD *)(a1 + 12) = 300;
  v5 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Cryptography\\OID\\EncodingType 0\\CertDllCreateCertificateChainEngine\\Config\\CrlPreFetch",
         0,
         0x20119u,
         &hKey);
  if ( !v5 )
  {
    UpdateDWORDParaFromRegistry(hKey, L"MaxAgeSeconds", &RandomBuffer);
    v3 = RandomBuffer;
    if ( RandomBuffer < 0x12C )
      v3 = 300;
    UpdateDWORDParaFromRegistry(hKey, L"PublishBeforeNextUpdateSeconds", &v9);
    UpdateDWORDParaFromRegistry(hKey, L"PublishRandomIntervalSeconds", &v10);
    UpdateDWORDParaFromRegistry(hKey, L"TimeoutSeconds", a1);
    UpdateDWORDParaFromRegistry(hKey, L"MinBeforeNextUpdateSeconds", a1 + 8);
    UpdateDWORDParaFromRegistry(hKey, L"MinAfterNextUpdateSeconds", a1 + 12);
    UpdateDWORDParaFromRegistry(hKey, L"DisableInformationEvents", a1 + 20);
    LOBYTE(v5) = RegCloseKey(hKey);
    v4 = v9;
    v1 = v10;
  }
  *(_DWORD *)(a1 + 4) = v3;
  if ( v1 > 1 && v1 < v4 )
  {
    RandomBuffer = 0;
    LOBYTE(v5) = SystemFunction036(&RandomBuffer, 4u);
    if ( (_BYTE)v5 )
    {
      v5 = RandomBuffer / v1;
      v6 = RandomBuffer % v1;
    }
    else
    {
      v6 = v1 >> 1;
    }
    v4 -= v6;
  }
  *(_DWORD *)(a1 + 16) = v4;
  return v5;
}

```

## disassembly

```asm
0x18001eee8  push    rbp
0x18001eeea  push    rbx
0x18001eeeb  push    rsi
0x18001eeec  push    rdi
0x18001eeed  push    r12
0x18001eeef  push    r14
0x18001eef1  push    r15
0x18001eef3  mov     rbp, rsp
0x18001eef6  sub     rsp, 30h
0x18001eefa  mov     ebx, 12Ch
0x18001eeff  mov     [rbp+hKey], 0
0x18001ef07  mov     [rcx], rbx
0x18001ef0a  lea     rax, [rbp+hKey]
0x18001ef0e  mov     rdi, rcx
0x18001ef11  mov     [rbp+arg_10], ebx
0x18001ef14  mov     r14d, 1C20h
0x18001ef1a  mov     [rsp+30h+phkResult], rax; phkResult
0x18001ef1f  mov     esi, 0E10h
0x18001ef24  mov     [rbp+RandomBuffer], r14d
0x18001ef28  mov     [rbp+arg_8], esi
0x18001ef2b  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Cryptography\\OID"...
0x18001ef32  mov     qword ptr [rcx+10h], 0
0x18001ef3a  mov     r9d, 20119h; samDesired
0x18001ef40  mov     [rcx+8], ebx
0x18001ef43  xor     r8d, r8d; ulOptions
0x18001ef46  mov     [rcx+0Ch], ebx
0x18001ef49  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001ef50  call    cs:__imp_RegOpenKeyExW
0x18001ef56  test    eax, eax
0x18001ef58  jnz     loc_18001F004
0x18001ef5e  mov     rcx, [rbp+hKey]
0x18001ef62  lea     r8, [rbp+RandomBuffer]
0x18001ef66  lea     rdx, aMaxageseconds; "MaxAgeSeconds"
0x18001ef6d  call    _UpdateDWORDParaFromRegistry
0x18001ef72  mov     r14d, [rbp+RandomBuffer]
0x18001ef76  lea     r8, [rbp+arg_8]
0x18001ef7a  mov     rcx, [rbp+hKey]
0x18001ef7e  lea     rdx, aPublishbeforen; "PublishBeforeNextUpdateSeconds"
0x18001ef85  cmp     r14d, ebx
0x18001ef88  cmovb   r14d, ebx
0x18001ef8c  call    _UpdateDWORDParaFromRegistry
0x18001ef91  mov     rcx, [rbp+hKey]
0x18001ef95  lea     r8, [rbp+arg_10]
0x18001ef99  lea     rdx, aPublishrandomi; "PublishRandomIntervalSeconds"
0x18001efa0  call    _UpdateDWORDParaFromRegistry
0x18001efa5  mov     rcx, [rbp+hKey]
0x18001efa9  lea     rdx, aTimeoutseconds; "TimeoutSeconds"
0x18001efb0  mov     r8, rdi
0x18001efb3  call    _UpdateDWORDParaFromRegistry
0x18001efb8  mov     rcx, [rbp+hKey]
0x18001efbc  lea     r8, [rdi+8]
0x18001efc0  lea     rdx, aMinbeforenextu; "MinBeforeNextUpdateSeconds"
0x18001efc7  call    _UpdateDWORDParaFromRegistry
0x18001efcc  mov     rcx, [rbp+hKey]
0x18001efd0  lea     r8, [rdi+0Ch]
0x18001efd4  lea     rdx, aMinafternextup; "MinAfterNextUpdateSeconds"
0x18001efdb  call    _UpdateDWORDParaFromRegistry
0x18001efe0  mov     rcx, [rbp+hKey]
0x18001efe4  lea     r8, [rdi+14h]
0x18001efe8  lea     rdx, aDisableinforma; "DisableInformationEvents"
0x18001efef  call    _UpdateDWORDParaFromRegistry
0x18001eff4  mov     rcx, [rbp+hKey]; hKey
0x18001eff8  call    cs:__imp_RegCloseKey
0x18001effe  mov     esi, [rbp+arg_8]
0x18001f001  mov     ebx, [rbp+arg_10]
0x18001f004  mov     [rdi+4], r14d
0x18001f008  cmp     ebx, 1
0x18001f00b  jbe     short loc_18001F03A
0x18001f00d  cmp     ebx, esi
0x18001f00f  jnb     short loc_18001F03A
0x18001f011  mov     edx, 4; RandomBufferLength
0x18001f016  mov     [rbp+RandomBuffer], 0
0x18001f01d  lea     rcx, [rbp+RandomBuffer]; RandomBuffer
0x18001f021  call    cs:__imp_SystemFunction036
0x18001f027  test    al, al
0x18001f029  jz      short loc_18001F036
0x18001f02b  mov     eax, [rbp+RandomBuffer]
0x18001f02e  xor     edx, edx
0x18001f030  div     ebx
0x18001f032  mov     ebx, edx
0x18001f034  jmp     short loc_18001F038
0x18001f036  shr     ebx, 1
0x18001f038  sub     esi, ebx
0x18001f03a  mov     [rdi+10h], esi
0x18001f03d  add     rsp, 30h
0x18001f041  pop     r15
0x18001f043  pop     r14
0x18001f045  pop     r12
0x18001f047  pop     rdi
0x18001f048  pop     rsi
0x18001f049  pop     rbx
0x18001f04a  pop     rbp
0x18001f04b  retn
```
