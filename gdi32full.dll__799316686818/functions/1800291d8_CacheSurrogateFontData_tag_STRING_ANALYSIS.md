# CacheSurrogateFontData(tag_STRING_ANALYSIS *)

- ea: `0x1800291d8`
- end: `0x1800293d9`
- name: `?CacheSurrogateFontData@@YAXPEAUtag_STRING_ANALYSIS@@@Z`
- size: `513`
- prototype: `void __fastcall(struct tag_STRING_ANALYSIS *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a580`

## callees

- `0x180009d00`
- `0x18000a090`
- `0x1800291d8`
- `0x1800293e0`
- `0x180029544`
- `0x1800295b8`
- `0x18007ac50`
- `0x18007ba24`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800292cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029363`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800293ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800292cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029363`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800293ba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029288`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800292bd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029314`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029288`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800292bd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029314`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002933a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180029386`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002933a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180029386`
- `win32u!NtGdiGetTextFaceW` at `0x18002925c`
- `win32u!NtGdiGetTextFaceW` at `0x18002925c`

## pseudocode

```c
void __fastcall CacheSurrogateFontData(struct tag_STRING_ANALYSIS *a1)
{
  __int64 v2; // rcx
  bool v3; // zf
  const WCHAR *SurrogateBaseFaceName; // rax
  char *v5; // rax
  char *v6; // rbx
  char *v7; // rax
  char *v8; // rbx
  HKEY hKey; // [rsp+30h] [rbp-29h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-21h] BYREF
  wchar_t v11[32]; // [rsp+40h] [rbp-19h] BYREF

  hKey = 0;
  phkResult = 0;
  if ( gSurrogateFontTable == (char *)-1LL )
  {
    gSurrogateFontTable = 0;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\LanguagePack\\SurrogateFallback",
            0,
            0x101u,
            &hKey) )
    {
      if ( (unsigned int)CheckInitUspMemory() )
      {
        v5 = (char *)HeapAlloc(ghHeap, 0, 0x200u);
        v6 = v5;
        if ( v5 )
        {
          if ( (unsigned int)CopySurrogatePlaneListFromRegKey(hKey, v5) )
            UspFreeMem(v6);
          else
            gSurrogateFontTable = v6;
        }
      }
      RegCloseKey(hKey);
    }
  }
  v2 = *(_QWORD *)(*((_QWORD *)a1 + 55) + 80LL);
  if ( *(_QWORD *)(v2 + 2144) == -1 )
  {
    v3 = gSurrogateFontTable == 0;
    *(_QWORD *)(v2 + 2144) = 0;
    if ( !v3 )
    {
      memset_0(v11, 0, sizeof(v11));
      NtGdiGetTextFaceW(*(_QWORD *)a1, 32, v11, 0);
      if ( v11[0] )
      {
        if ( !RegOpenKeyExW(
                HKEY_LOCAL_MACHINE,
                L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\LanguagePack\\SurrogateFallback",
                0,
                0x109u,
                &hKey) )
        {
          CreateLocalizedNameXlateTable(hKey);
          SurrogateBaseFaceName = GetSurrogateBaseFaceName(v11);
          if ( !RegOpenKeyExW(hKey, SurrogateBaseFaceName, 0, 0x101u, &phkResult) )
          {
            if ( (unsigned int)CheckInitUspMemory() )
            {
              v7 = (char *)HeapAlloc(ghHeap, 0, 0x200u);
              v8 = v7;
              if ( v7 )
              {
                if ( (unsigned int)CopySurrogatePlaneListFromRegKey(phkResult, v7) )
                  UspFreeMem(v8);
                else
                  *(_QWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 55) + 80LL) + 2144LL) = v8;
              }
            }
            RegCloseKey(phkResult);
          }
          RegCloseKey(hKey);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800291d8  push    rbp
0x1800291da  push    rbx
0x1800291db  push    rsi
0x1800291dc  push    rdi
0x1800291dd  lea     rbp, [rsp-3Fh]
0x1800291e2  sub     rsp, 98h
0x1800291e9  mov     rax, cs:__security_cookie
0x1800291f0  xor     rax, rsp
0x1800291f3  mov     [rbp+57h+var_30], rax
0x1800291f7  xor     esi, esi
0x1800291f9  mov     rdi, rcx
0x1800291fc  cmp     cs:?gSurrogateFontTable@@3PEADEA, 0FFFFFFFFFFFFFFFFh; char * gSurrogateFontTable
0x180029204  mov     [rbp+57h+hKey], rsi
0x180029208  mov     [rbp+57h+var_78], rsi
0x18002920c  jz      loc_1800292ED
0x180029212  mov     rax, [rdi+1B8h]
0x180029219  mov     rcx, [rax+50h]
0x18002921d  cmp     qword ptr [rcx+860h], 0FFFFFFFFFFFFFFFFh
0x180029225  jnz     loc_1800292D5
0x18002922b  cmp     cs:?gSurrogateFontTable@@3PEADEA, rsi; char * gSurrogateFontTable
0x180029232  mov     [rcx+860h], rsi
0x180029239  jz      loc_1800292D5
0x18002923f  xor     edx, edx; Val
0x180029241  lea     rcx, [rbp+57h+var_70]; void *
0x180029245  lea     r8d, [rdx+40h]; Size
0x180029249  call    memset_0
0x18002924e  mov     rcx, [rdi]
0x180029251  lea     r8, [rbp+57h+var_70]
0x180029255  xor     r9d, r9d
0x180029258  lea     edx, [r9+20h]
0x18002925c  call    cs:__imp_NtGdiGetTextFaceW
0x180029262  cmp     [rbp+57h+var_70], si
0x180029266  jz      short loc_1800292D5
0x180029268  lea     rax, [rbp+57h+hKey]
0x18002926c  mov     r9d, 109h; samDesired
0x180029272  xor     r8d, r8d; ulOptions
0x180029275  mov     [rsp+0B0h+phkResult], rax; phkResult
0x18002927a  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180029281  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180029288  call    cs:__imp_RegOpenKeyExW
0x18002928e  test    eax, eax
0x180029290  jnz     short loc_1800292D5
0x180029292  mov     rcx, [rbp+57h+hKey]; hKey
0x180029296  call    ?CreateLocalizedNameXlateTable@@YAXPEAUHKEY__@@@Z; CreateLocalizedNameXlateTable(HKEY__ *)
0x18002929b  lea     rcx, [rbp+57h+var_70]; wchar_t *
0x18002929f  call    ?GetSurrogateBaseFaceName@@YAPEA_WPEA_W@Z; GetSurrogateBaseFaceName(wchar_t *)
0x1800292a4  mov     rcx, [rbp+57h+hKey]; hKey
0x1800292a8  mov     rdx, rax; lpSubKey
0x1800292ab  lea     rax, [rbp+57h+var_78]
0x1800292af  mov     r9d, 101h; samDesired
0x1800292b5  xor     r8d, r8d; ulOptions
0x1800292b8  mov     [rsp+0B0h+phkResult], rax; phkResult
0x1800292bd  call    cs:__imp_RegOpenKeyExW
0x1800292c3  test    eax, eax
0x1800292c5  jz      loc_18002936E
0x1800292cb  mov     rcx, [rbp+57h+hKey]; hKey
0x1800292cf  call    cs:__imp_RegCloseKey
0x1800292d5  mov     rcx, [rbp+57h+var_30]
0x1800292d9  xor     rcx, rsp; StackCookie
0x1800292dc  call    __security_check_cookie
0x1800292e1  add     rsp, 98h
0x1800292e8  pop     rdi
0x1800292e9  pop     rsi
0x1800292ea  pop     rbx
0x1800292eb  pop     rbp
0x1800292ec  retn
0x1800292ed  lea     rax, [rbp+57h+hKey]
0x1800292f1  mov     cs:?gSurrogateFontTable@@3PEADEA, rsi; char * gSurrogateFontTable
0x1800292f8  mov     r9d, 101h; samDesired
0x1800292fe  mov     [rsp+0B0h+phkResult], rax; phkResult
0x180029303  xor     r8d, r8d; ulOptions
0x180029306  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002930d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180029314  call    cs:__imp_RegOpenKeyExW
0x18002931a  test    eax, eax
0x18002931c  jnz     loc_180029212
0x180029322  call    ?CheckInitUspMemory@@YAHXZ; CheckInitUspMemory(void)
0x180029327  test    eax, eax
0x180029329  jz      short loc_18002935F
0x18002932b  mov     rcx, cs:?ghHeap@@3PEAXEA; hHeap
0x180029332  xor     edx, edx; dwFlags
0x180029334  mov     r8d, 200h; dwBytes
0x18002933a  call    cs:__imp_HeapAlloc
0x180029340  mov     rbx, rax
0x180029343  test    rax, rax
0x180029346  jz      short loc_18002935F
0x180029348  mov     rcx, [rbp+57h+hKey]; hKey
0x18002934c  mov     rdx, rax; char *
0x18002934f  call    ?CopySurrogatePlaneListFromRegKey@@YAJPEAUHKEY__@@PEAD@Z; CopySurrogatePlaneListFromRegKey(HKEY__ *,char *)
0x180029354  test    eax, eax
0x180029356  jnz     short loc_1800293CF
0x180029358  mov     cs:?gSurrogateFontTable@@3PEADEA, rbx; char * gSurrogateFontTable
0x18002935f  mov     rcx, [rbp+57h+hKey]; hKey
0x180029363  call    cs:__imp_RegCloseKey
0x180029369  jmp     loc_180029212
0x18002936e  call    ?CheckInitUspMemory@@YAHXZ; CheckInitUspMemory(void)
0x180029373  test    eax, eax
0x180029375  jz      short loc_1800293B6
0x180029377  mov     rcx, cs:?ghHeap@@3PEAXEA; hHeap
0x18002937e  xor     edx, edx; dwFlags
0x180029380  mov     r8d, 200h; dwBytes
0x180029386  call    cs:__imp_HeapAlloc
0x18002938c  mov     rbx, rax
0x18002938f  test    rax, rax
0x180029392  jz      short loc_1800293B6
0x180029394  mov     rcx, [rbp+57h+var_78]; hKey
0x180029398  mov     rdx, rax; char *
0x18002939b  call    ?CopySurrogatePlaneListFromRegKey@@YAJPEAUHKEY__@@PEAD@Z; CopySurrogatePlaneListFromRegKey(HKEY__ *,char *)
0x1800293a0  test    eax, eax
0x1800293a2  jnz     short loc_1800293C5
0x1800293a4  mov     rcx, [rdi+1B8h]
0x1800293ab  mov     rdx, [rcx+50h]
0x1800293af  mov     [rdx+860h], rbx
0x1800293b6  mov     rcx, [rbp+57h+var_78]; hKey
0x1800293ba  call    cs:__imp_RegCloseKey
0x1800293c0  jmp     loc_1800292CB
0x1800293c5  mov     rcx, rbx; lpMem
0x1800293c8  call    UspFreeMem
0x1800293cd  jmp     short loc_1800293B6
0x1800293cf  mov     rcx, rbx; lpMem
0x1800293d2  call    UspFreeMem
0x1800293d7  jmp     short loc_18002935F
```
