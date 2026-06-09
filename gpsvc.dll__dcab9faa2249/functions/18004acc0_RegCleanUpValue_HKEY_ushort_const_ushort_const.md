# RegCleanUpValue(HKEY__ *,ushort const *,ushort const *)

- ea: `0x18004acc0`
- end: `0x18004b07b`
- name: `?RegCleanUpValue@@YAHPEAUHKEY__@@PEBG1@Z`
- size: `955`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x18004aa50`

## callees

- `0x18004acc0`
- `0x180075ec0`
- `0x18007d320`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004af0f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004af0f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ae9e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004af1c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ae9e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004af1c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18004ae91`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18004ae91`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18004aecc`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18004aecc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004ad9e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004ae44`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004ad9e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004ae44`

## string_xrefs

- `0x18004ad64`: `RegCleanUpKey:  Failed to copy value name.`
- `0x18004af6e`: `RegCleanUpKey:  Failed to copy value name.`
- `0x18004af46`: `RegCleanUpKey:  Failed to delete value <%s> with %d.`
- `0x18004afa1`: `RegCleanUpKey:  Failed to delete value <%s> with %d.`
- `0x18004afdd`: `RegCleanUpKey:  Failed to open key <%s> with %d.`
- `0x18004b010`: `RegCleanUpKey:  Failed to open key <%s> with %d.`

## pseudocode

```c
__int64 __fastcall RegCleanUpValue(HKEY hKey, WCHAR *a2, const unsigned __int16 *a3)
{
  WCHAR *v4; // r9
  __int64 v6; // rax
  __int64 v7; // r8
  bool v8; // zf
  __int64 v9; // rax
  WCHAR *v10; // rbx
  unsigned int v12; // eax
  unsigned int v13; // edi
  unsigned int v14; // ebx
  __int64 v15; // r9
  const unsigned __int16 *v16; // rdx
  HKEY hKeya; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cSubKeys; // [rsp+68h] [rbp-98h] BYREF
  DWORD cValues; // [rsp+6Ch] [rbp-94h] BYREF
  WCHAR SubKey[520]; // [rsp+70h] [rbp-90h] BYREF

  cSubKeys = 0;
  cValues = 0;
  v4 = SubKey;
  hKeya = 0;
  v6 = 2147483646;
  v7 = 520;
  while ( v6 && *a2 )
  {
    *v4++ = *a2++;
    --v6;
    if ( !--v7 )
    {
      v8 = *(_DWORD *)&g_dwDebugLevel == 0;
      *(v4 - 1) = 0;
      if ( !v8 )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"RegCleanUpKey:  Failed to copy value name.");
        }
        else if ( g_lpDebugMsgContextInstance )
        {
          if ( g_lpDebugMsgContext )
            RedirectDebugMsg(2u, L"RegCleanUpKey:  Failed to copy value name.");
        }
      }
      return 0;
    }
  }
  *v4 = 0;
  if ( !RegOpenKeyExW(hKey, SubKey, 0, 0x20006u, &hKeya) )
  {
    v14 = RegDeleteValueW(hKeya, a3);
    RegCloseKey(hKeya);
    if ( (v14 & 0xFFFFFFFD) != 0 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"RegCleanUpKey:  Failed to delete value <%s> with %d.", a3, v14);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"RegCleanUpKey:  Failed to delete value <%s> with %d.", a3, v14);
        }
      }
      return 0;
    }
  }
  v9 = -1;
  do
    v8 = SubKey[++v9] == 0;
  while ( !v8 );
  v10 = &SubKey[v9 - 1];
  while ( 1 )
  {
    if ( v10 < SubKey )
      return 1;
    for ( ; v10 > SubKey; --v10 )
    {
      if ( *v10 == 92 )
        break;
    }
    v12 = RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, &hKeya);
    if ( v12 )
      break;
    v13 = RegQueryInfoKeyW(hKeya, 0, 0, 0, &cSubKeys, 0, 0, &cValues, 0, 0, 0, 0);
    RegCloseKey(hKeya);
    if ( v13 )
    {
      if ( !*(_DWORD *)&g_dwDebugLevel )
        return 0;
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"RegCleanUpKey:  Failed to query key <%s> with %d.", SubKey, v13);
        return 0;
      }
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v15 = v13;
        v16 = L"RegCleanUpKey:  Failed to query key <%s> with %d.";
        goto LABEL_49;
      }
      return 0;
    }
    if ( cSubKeys || cValues )
      return 1;
    RegDeleteKeyExW(hKey, SubKey, 0, 0);
LABEL_22:
    if ( v10 == SubKey )
      return 1;
    if ( *v10 == 92 )
      *v10 = 0;
  }
  if ( v12 == 2 )
    goto LABEL_22;
  if ( !*(_DWORD *)&g_dwDebugLevel )
    return 0;
  if ( g_lpDebugMsg )
  {
    g_lpDebugMsg(2u, L"RegCleanUpKey:  Failed to open key <%s> with %d.", SubKey, v12);
    return 0;
  }
  if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
  {
    v15 = v12;
    v16 = L"RegCleanUpKey:  Failed to open key <%s> with %d.";
LABEL_49:
    RedirectDebugMsg(2u, v16, SubKey, v15);
  }
  return 0;
}

```

## disassembly

```asm
0x18004acc0  mov     [rsp-8+arg_18], rsi
0x18004acc5  push    rbp
0x18004acc6  push    rdi
0x18004acc7  push    r14
0x18004acc9  lea     rbp, [rsp-390h]
0x18004acd1  sub     rsp, 490h
0x18004acd8  mov     rax, cs:__security_cookie
0x18004acdf  xor     rax, rsp
0x18004ace2  mov     [rbp+3A0h+var_20], rax
0x18004ace9  xor     r14d, r14d
0x18004acec  mov     [rsp+4A0h+arg_8], rbx
0x18004acf4  mov     rdi, r8
0x18004acf7  mov     [rsp+4A0h+cSubKeys], r14d
0x18004acfc  mov     [rsp+4A0h+cValues], r14d
0x18004ad01  lea     r9, [rsp+4A0h+SubKey]
0x18004ad06  mov     [rsp+4A0h+hKey], r14
0x18004ad0b  mov     rsi, rcx
0x18004ad0e  mov     eax, 7FFFFFFEh
0x18004ad13  mov     r8d, 208h
0x18004ad19  nop     dword ptr [rax+00000000h]
0x18004ad20  test    rax, rax
0x18004ad23  jz      short loc_18004AD7F
0x18004ad25  movzx   ecx, word ptr [rdx]
0x18004ad28  test    cx, cx
0x18004ad2b  jz      short loc_18004AD7A
0x18004ad2d  mov     [r9], cx
0x18004ad31  add     rdx, 2
0x18004ad35  add     r9, 2
0x18004ad39  dec     rax
0x18004ad3c  sub     r8, 1
0x18004ad40  jnz     short loc_18004AD20
0x18004ad42  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x18004ad49  mov     [r9-2], r14w
0x18004ad4e  jz      loc_18004AF00
0x18004ad54  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18004ad5b  test    rax, rax
0x18004ad5e  jz      loc_18004AF5C
0x18004ad64  lea     rdx, aRegcleanupkeyF; "RegCleanUpKey:  Failed to copy value na"...
0x18004ad6b  mov     ecx, 2
0x18004ad70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ad75  jmp     loc_18004AF00
0x18004ad7a  test    r8, r8
0x18004ad7d  jz      short loc_18004AD42
0x18004ad7f  mov     [r9], r14w
0x18004ad83  lea     rax, [rsp+4A0h+hKey]
0x18004ad88  mov     r9d, 20006h; samDesired
0x18004ad8e  mov     [rsp+4A0h+phkResult], rax; phkResult
0x18004ad93  xor     r8d, r8d; ulOptions
0x18004ad96  lea     rdx, [rsp+4A0h+SubKey]; lpSubKey
0x18004ad9b  mov     rcx, rsi; hKey
0x18004ad9e  call    cs:__imp_RegOpenKeyExW
0x18004ada4  test    eax, eax
0x18004ada6  jz      loc_18004AF07
0x18004adac  lea     rcx, [rsp+4A0h+SubKey]
0x18004adb1  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18004adb8  nop     dword ptr [rax+rax+00000000h]
0x18004adc0  cmp     [rcx+rax*2+2], r14w
0x18004adc6  lea     rax, [rax+1]
0x18004adca  jnz     short loc_18004ADC0
0x18004adcc  lea     rbx, [rsp+rax*2+4A0h+cValues+2]
0x18004add1  lea     rax, [rsp+4A0h+SubKey]
0x18004add6  cmp     rbx, rax
0x18004add9  jnb     short loc_18004AE0B
0x18004addb  mov     eax, 1
0x18004ade0  mov     rbx, [rsp+4A0h+arg_8]
0x18004ade8  mov     rcx, [rbp+3A0h+var_20]
0x18004adef  xor     rcx, rsp; StackCookie
0x18004adf2  call    __security_check_cookie
0x18004adf7  mov     rsi, [rsp+4A0h+arg_18]
0x18004adff  add     rsp, 490h
0x18004ae06  pop     r14
0x18004ae08  pop     rdi
0x18004ae09  pop     rbp
0x18004ae0a  retn
0x18004ae0b  lea     rax, [rsp+4A0h+SubKey]
0x18004ae10  cmp     rbx, rax
0x18004ae13  jbe     short loc_18004AE29
0x18004ae15  cmp     word ptr [rbx], 5Ch ; '\'
0x18004ae19  jz      short loc_18004AE29
0x18004ae1b  sub     rbx, 2
0x18004ae1f  lea     rax, [rsp+4A0h+SubKey]
0x18004ae24  cmp     rbx, rax
0x18004ae27  ja      short loc_18004AE15
0x18004ae29  lea     rax, [rsp+4A0h+hKey]
0x18004ae2e  mov     r9d, 20019h; samDesired
0x18004ae34  xor     r8d, r8d; ulOptions
0x18004ae37  mov     [rsp+4A0h+phkResult], rax; phkResult
0x18004ae3c  lea     rdx, [rsp+4A0h+SubKey]; lpSubKey
0x18004ae41  mov     rcx, rsi; hKey
0x18004ae44  call    cs:__imp_RegOpenKeyExW
0x18004ae4a  test    eax, eax
0x18004ae4c  jnz     loc_18004AFB0
0x18004ae52  mov     rcx, [rsp+4A0h+hKey]; hKey
0x18004ae57  lea     rax, [rsp+4A0h+cValues]
0x18004ae5c  mov     [rsp+4A0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18004ae61  xor     r9d, r9d; lpReserved
0x18004ae64  mov     [rsp+4A0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18004ae69  xor     r8d, r8d; lpcchClass
0x18004ae6c  mov     [rsp+4A0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x18004ae71  xor     edx, edx; lpClass
0x18004ae73  mov     [rsp+4A0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x18004ae78  mov     [rsp+4A0h+lpcValues], rax; lpcValues
0x18004ae7d  lea     rax, [rsp+4A0h+cSubKeys]
0x18004ae82  mov     [rsp+4A0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18004ae87  mov     [rsp+4A0h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x18004ae8c  mov     [rsp+4A0h+phkResult], rax; lpcSubKeys
0x18004ae91  call    cs:__imp_RegQueryInfoKeyW
0x18004ae97  mov     rcx, [rsp+4A0h+hKey]; hKey
0x18004ae9c  mov     edi, eax
0x18004ae9e  call    cs:__imp_RegCloseKey
0x18004aea4  test    edi, edi
0x18004aea6  jnz     short loc_18004AEF3
0x18004aea8  cmp     [rsp+4A0h+cSubKeys], r14d
0x18004aead  jnz     loc_18004ADDB
0x18004aeb3  cmp     [rsp+4A0h+cValues], r14d
0x18004aeb8  jnz     loc_18004ADDB
0x18004aebe  xor     r9d, r9d; Reserved
0x18004aec1  lea     rdx, [rsp+4A0h+SubKey]; lpSubKey
0x18004aec6  xor     r8d, r8d; samDesired
0x18004aec9  mov     rcx, rsi; hKey
0x18004aecc  call    cs:__imp_RegDeleteKeyExW
0x18004aed2  lea     rax, [rsp+4A0h+SubKey]
0x18004aed7  cmp     rbx, rax
0x18004aeda  jz      loc_18004ADDB
0x18004aee0  cmp     word ptr [rbx], 5Ch ; '\'
0x18004aee4  jnz     loc_18004ADD1
0x18004aeea  mov     [rbx], r14w
0x18004aeee  jmp     loc_18004ADD1
0x18004aef3  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x18004aefa  jnz     loc_18004B019
0x18004af00  xor     eax, eax
0x18004af02  jmp     loc_18004ADE0
0x18004af07  mov     rcx, [rsp+4A0h+hKey]; hKey
0x18004af0c  mov     rdx, rdi; lpValueName
0x18004af0f  call    cs:__imp_RegDeleteValueW
0x18004af15  mov     rcx, [rsp+4A0h+hKey]; hKey
0x18004af1a  mov     ebx, eax
0x18004af1c  call    cs:__imp_RegCloseKey
0x18004af22  test    ebx, 0FFFFFFFDh
0x18004af28  jz      loc_18004ADAC
0x18004af2e  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x18004af35  jz      short loc_18004AF00
0x18004af37  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18004af3e  test    rax, rax
0x18004af41  jz      short loc_18004AF84
0x18004af43  mov     r9d, ebx
0x18004af46  lea     rdx, aRegcleanupkeyF_1; "RegCleanUpKey:  Failed to delete value "...
0x18004af4d  mov     r8, rdi
0x18004af50  mov     ecx, 2
0x18004af55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004af5a  jmp     short loc_18004AF00
0x18004af5c  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x18004af63  jz      short loc_18004AF00
0x18004af65  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18004af6c  jz      short loc_18004AF00
0x18004af6e  lea     rdx, aRegcleanupkeyF; "RegCleanUpKey:  Failed to copy value na"...
0x18004af75  mov     ecx, 2; unsigned int
0x18004af7a  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18004af7f  jmp     loc_18004AF00
0x18004af84  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x18004af8b  jz      loc_18004AF00
0x18004af91  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18004af98  jz      loc_18004AF00
0x18004af9e  mov     r9d, ebx
0x18004afa1  lea     rdx, aRegcleanupkeyF_1; "RegCleanUpKey:  Failed to delete value "...
0x18004afa8  mov     r8, rdi
0x18004afab  jmp     loc_18004B06C
0x18004afb0  cmp     eax, 2
0x18004afb3  jz      loc_18004AED2
0x18004afb9  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x18004afc0  jz      loc_18004AF00
0x18004afc6  mov     r10, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18004afcd  test    r10, r10
0x18004afd0  jz      short loc_18004AFF3
0x18004afd2  mov     r9d, eax
0x18004afd5  lea     r8, [rsp+4A0h+SubKey]
0x18004afda  mov     rax, r10
0x18004afdd  lea     rdx, aRegcleanupkeyF_0; "RegCleanUpKey:  Failed to open key <%s>"...
0x18004afe4  mov     ecx, 2
0x18004afe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004afee  jmp     loc_18004AF00
0x18004aff3  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x18004affa  jz      loc_18004AF00
0x18004b000  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18004b007  jz      loc_18004AF00
0x18004b00d  mov     r9d, eax
0x18004b010  lea     rdx, aRegcleanupkeyF_0; "RegCleanUpKey:  Failed to open key <%s>"...
0x18004b017  jmp     short loc_18004B067
0x18004b019  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18004b020  test    rax, rax
0x18004b023  jz      short loc_18004B043
0x18004b025  mov     r9d, edi
0x18004b028  lea     r8, [rsp+4A0h+SubKey]
0x18004b02d  lea     rdx, aRegcleanupkeyF_2; "RegCleanUpKey:  Failed to query key <%s"...
0x18004b034  mov     ecx, 2
0x18004b039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b03e  jmp     loc_18004AF00
0x18004b043  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x18004b04a  jz      loc_18004AF00
0x18004b050  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18004b057  jz      loc_18004AF00
0x18004b05d  mov     r9d, edi
0x18004b060  lea     rdx, aRegcleanupkeyF_2; "RegCleanUpKey:  Failed to query key <%s"...
0x18004b067  lea     r8, [rsp+4A0h+SubKey]
0x18004b06c  mov     ecx, 2; unsigned int
0x18004b071  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18004b076  jmp     loc_18004AF00
```
