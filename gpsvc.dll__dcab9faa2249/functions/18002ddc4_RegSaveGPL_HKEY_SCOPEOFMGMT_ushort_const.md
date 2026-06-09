# RegSaveGPL(HKEY__ *,_SCOPEOFMGMT *,ushort const *)

- ea: `0x18002ddc4`
- end: `0x18002e082`
- name: `?RegSaveGPL@@YAKPEAUHKEY__@@PEAU_SCOPEOFMGMT@@PEBG@Z`
- size: `702`
- prototype: `unsigned int __fastcall(HKEY hKey, struct _SCOPEOFMGMT *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18009dfc8`

## callees

- `0x18001dcf0`
- `0x18002ddc4`
- `0x18002f6e0`
- `0x180075ec0`
- `0x18007d320`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow` at `0x18002de6e`
- `api-ms-win-crt-private-l1-1-0!_o__itow` at `0x18002de6e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dfdd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e040`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e057`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dfdd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e040`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e057`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ded2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002df03`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002df6c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002dfcd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ded2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002df03`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002df6c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002dfcd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002de38`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002dea1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002de38`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002dea1`

## string_xrefs

- `0x18002df4f`: `DsPath`

## pseudocode

```c
__int64 __fastcall RegSaveGPL(HKEY hKey, struct _SCOPEOFMGMT *a2, const unsigned __int16 *a3)
{
  unsigned int v6; // ebx
  int v7; // r14d
  __int64 v8; // rdi
  wchar_t *v9; // rax
  bool v10; // zf
  const WCHAR *v11; // r9
  __int64 v12; // rcx
  const BYTE *v13; // r9
  const WCHAR *v14; // r9
  __int64 v15; // rcx
  const BYTE *v16; // r9
  LSTATUS v17; // eax
  HKEY v18; // rcx
  HKEY phkResult; // [rsp+50h] [rbp-39h] BYREF
  DWORD cbData; // [rsp+58h] [rbp-31h] BYREF
  HKEY hKeya; // [rsp+60h] [rbp-29h] BYREF
  wchar_t Buffer[32]; // [rsp+70h] [rbp-19h] BYREF

  v6 = GPRegDelnode(hKey, a3);
  if ( !v6 )
  {
    hKeya = 0;
    v6 = RegCreateKeyExW(hKey, a3, 0, 0, 0, 0xF003Fu, 0, &hKeya, 0);
    if ( !v6 )
    {
      v7 = 0;
      while ( a2 )
      {
        v8 = *((_QWORD *)a2 + 3);
        while ( v8 )
        {
          phkResult = 0;
          v9 = _itow(v7, Buffer, 16);
          v6 = RegCreateKeyExW(hKeya, v9, 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
          if ( v6 )
            break;
          v6 = RegSetValueExW(phkResult, L"Enabled", 0, 4u, (const BYTE *)(v8 + 8), 4u);
          if ( v6 || (v6 = RegSetValueExW(phkResult, L"NoOverride", 0, 4u, (const BYTE *)(v8 + 12), 4u)) != 0 )
          {
LABEL_28:
            v18 = phkResult;
LABEL_29:
            RegCloseKey(v18);
            break;
          }
          v10 = *(_QWORD *)v8 == 0;
          v11 = &DomainName;
          cbData = 0;
          if ( !v10 )
            v11 = *(const WCHAR **)v8;
          v12 = -1;
          do
            ++v12;
          while ( v11[v12] );
          if ( (int)ULongLongToULong(2 * v12 + 2, &cbData) < 0 )
            goto LABEL_22;
          v6 = RegSetValueExW(phkResult, L"DsPath", 0, 1u, v13, cbData);
          if ( v6 )
            goto LABEL_28;
          v14 = &DomainName;
          if ( *(_QWORD *)a2 )
            v14 = *(const WCHAR **)a2;
          v15 = -1;
          do
            ++v15;
          while ( v14[v15] );
          if ( (int)ULongLongToULong(2 * v15 + 2, &cbData) < 0 )
          {
LABEL_22:
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(2u, L"SizeTToDWord() Failed to convert to DWORD");
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(2u, L"SizeTToDWord() Failed to convert to DWORD");
              }
            }
            break;
          }
          v17 = RegSetValueExW(phkResult, L"SOM", 0, 1u, v16, cbData);
          v18 = phkResult;
          v6 = v17;
          if ( v17 )
            goto LABEL_29;
          RegCloseKey(phkResult);
          v8 = *(_QWORD *)(v8 + 16);
          ++v7;
        }
        a2 = (struct _SCOPEOFMGMT *)*((_QWORD *)a2 + 4);
      }
      RegCloseKey(hKeya);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18002ddc4  mov     [rsp-8+arg_18], rbx
0x18002ddc9  push    rbp
0x18002ddca  push    rsi
0x18002ddcb  push    rdi
0x18002ddcc  push    r14
0x18002ddce  push    r15
0x18002ddd0  lea     rbp, [rsp-37h]
0x18002ddd5  sub     rsp, 0C0h
0x18002dddc  mov     rax, cs:__security_cookie
0x18002dde3  xor     rax, rsp
0x18002dde6  mov     [rbp+57h+var_30], rax
0x18002ddea  mov     rsi, rdx
0x18002dded  mov     r14, r8
0x18002ddf0  mov     rdx, r8; unsigned __int16 *
0x18002ddf3  mov     rdi, rcx
0x18002ddf6  call    ?GPRegDelnode@@YAKPEAUHKEY__@@PEBG@Z; GPRegDelnode(HKEY__ *,ushort const *)
0x18002ddfb  xor     r15d, r15d
0x18002ddfe  mov     ebx, eax
0x18002de00  test    eax, eax
0x18002de02  jnz     loc_18002E05D
0x18002de08  mov     [rsp+0E0h+lpdwDisposition], r15; lpdwDisposition
0x18002de0d  lea     rax, [rbp+57h+hKey]
0x18002de11  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18002de16  xor     r9d, r9d; lpClass
0x18002de19  mov     [rsp+0E0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18002de1e  xor     r8d, r8d; Reserved
0x18002de21  mov     [rsp+0E0h+samDesired], 0F003Fh; samDesired
0x18002de29  mov     rdx, r14; lpSubKey
0x18002de2c  mov     rcx, rdi; hKey
0x18002de2f  mov     [rsp+0E0h+dwOptions], r15d; dwOptions
0x18002de34  mov     [rbp+57h+hKey], r15
0x18002de38  call    cs:__imp_RegCreateKeyExW
0x18002de3e  mov     ebx, eax
0x18002de40  test    eax, eax
0x18002de42  jnz     loc_18002E05D
0x18002de48  mov     r14d, r15d
0x18002de4b  jmp     loc_18002E04A
0x18002de50  mov     rdi, [rsi+18h]
0x18002de54  test    rdi, rdi
0x18002de57  jz      loc_18002E046
0x18002de5d  mov     r8d, 10h; Radix
0x18002de63  mov     [rbp+57h+var_90], r15
0x18002de67  lea     rdx, [rbp+57h+Buffer]; Buffer
0x18002de6b  mov     ecx, r14d; Value
0x18002de6e  call    cs:__imp__itow
0x18002de74  mov     [rsp+0E0h+lpdwDisposition], r15; lpdwDisposition
0x18002de79  lea     rcx, [rbp+57h+var_90]
0x18002de7d  mov     [rsp+0E0h+phkResult], rcx; phkResult
0x18002de82  xor     r9d, r9d; lpClass
0x18002de85  mov     rcx, [rbp+57h+hKey]; hKey
0x18002de89  xor     r8d, r8d; Reserved
0x18002de8c  mov     [rsp+0E0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18002de91  mov     rdx, rax; lpSubKey
0x18002de94  mov     [rsp+0E0h+samDesired], 0F003Fh; samDesired
0x18002de9c  mov     [rsp+0E0h+dwOptions], r15d; dwOptions
0x18002dea1  call    cs:__imp_RegCreateKeyExW
0x18002dea7  mov     ebx, eax
0x18002dea9  test    eax, eax
0x18002deab  jnz     loc_18002E046
0x18002deb1  lea     ecx, [rbx+4]
0x18002deb4  xor     r8d, r8d; Reserved
0x18002deb7  mov     [rsp+0E0h+samDesired], ecx; cbData
0x18002debb  lea     rax, [rdi+8]
0x18002debf  mov     r9d, ecx; dwType
0x18002dec2  mov     qword ptr [rsp+0E0h+dwOptions], rax; lpData
0x18002dec7  mov     rcx, [rbp+57h+var_90]; hKey
0x18002decb  lea     rdx, aEnabled; "Enabled"
0x18002ded2  call    cs:__imp_RegSetValueExW
0x18002ded8  mov     ebx, eax
0x18002deda  test    eax, eax
0x18002dedc  jnz     loc_18002E03C
0x18002dee2  lea     ecx, [rbx+4]
0x18002dee5  xor     r8d, r8d; Reserved
0x18002dee8  mov     [rsp+0E0h+samDesired], ecx; cbData
0x18002deec  lea     rax, [rdi+0Ch]
0x18002def0  mov     r9d, ecx; dwType
0x18002def3  mov     qword ptr [rsp+0E0h+dwOptions], rax; lpData
0x18002def8  mov     rcx, [rbp+57h+var_90]; hKey
0x18002defc  lea     rdx, aNooverride_0; "NoOverride"
0x18002df03  call    cs:__imp_RegSetValueExW
0x18002df09  mov     ebx, eax
0x18002df0b  test    eax, eax
0x18002df0d  jnz     loc_18002E03C
0x18002df13  cmp     [rdi], r15
0x18002df16  lea     r9, DomainName
0x18002df1d  mov     [rbp+57h+cbData], r15d
0x18002df21  cmovnz  r9, [rdi]
0x18002df25  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002df29  inc     rcx
0x18002df2c  cmp     [r9+rcx*2], r15w
0x18002df31  jnz     short loc_18002DF29
0x18002df33  lea     rcx, ds:2[rcx*2]; unsigned __int64
0x18002df3b  lea     rdx, [rbp+57h+cbData]; unsigned int *
0x18002df3f  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18002df44  test    eax, eax
0x18002df46  js      loc_18002DFEF
0x18002df4c  mov     eax, [rbp+57h+cbData]
0x18002df4f  lea     rdx, aDspath_0; "DsPath"
0x18002df56  mov     rcx, [rbp+57h+var_90]; hKey
0x18002df5a  xor     r8d, r8d; Reserved
0x18002df5d  mov     [rsp+0E0h+samDesired], eax; cbData
0x18002df61  mov     qword ptr [rsp+0E0h+dwOptions], r9; lpData
0x18002df66  mov     r9d, 1; dwType
0x18002df6c  call    cs:__imp_RegSetValueExW
0x18002df72  mov     ebx, eax
0x18002df74  test    eax, eax
0x18002df76  jnz     loc_18002E03C
0x18002df7c  cmp     [rsi], r15
0x18002df7f  lea     r9, DomainName
0x18002df86  cmovnz  r9, [rsi]
0x18002df8a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002df8e  inc     rcx
0x18002df91  cmp     [r9+rcx*2], r15w
0x18002df96  jnz     short loc_18002DF8E
0x18002df98  lea     rcx, ds:2[rcx*2]; unsigned __int64
0x18002dfa0  lea     rdx, [rbp+57h+cbData]; unsigned int *
0x18002dfa4  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18002dfa9  test    eax, eax
0x18002dfab  js      short loc_18002DFEF
0x18002dfad  mov     eax, [rbp+57h+cbData]
0x18002dfb0  lea     rdx, aSom; "SOM"
0x18002dfb7  mov     rcx, [rbp+57h+var_90]; hKey
0x18002dfbb  xor     r8d, r8d; Reserved
0x18002dfbe  mov     [rsp+0E0h+samDesired], eax; cbData
0x18002dfc2  mov     qword ptr [rsp+0E0h+dwOptions], r9; lpData
0x18002dfc7  mov     r9d, 1; dwType
0x18002dfcd  call    cs:__imp_RegSetValueExW
0x18002dfd3  mov     rcx, [rbp+57h+var_90]; hKey
0x18002dfd7  mov     ebx, eax
0x18002dfd9  test    eax, eax
0x18002dfdb  jnz     short loc_18002E040
0x18002dfdd  call    cs:__imp_RegCloseKey
0x18002dfe3  mov     rdi, [rdi+10h]
0x18002dfe7  inc     r14d
0x18002dfea  jmp     loc_18002DE54
0x18002dfef  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x18002dff6  jz      short loc_18002E046
0x18002dff8  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18002dfff  test    rax, rax
0x18002e002  jz      short loc_18002E017
0x18002e004  lea     rdx, aSizettodwordFa_1; "SizeTToDWord() Failed to convert to DWO"...
0x18002e00b  mov     ecx, 2
0x18002e010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e015  jmp     short loc_18002E046
0x18002e017  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x18002e01e  jz      short loc_18002E046
0x18002e020  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18002e027  jz      short loc_18002E046
0x18002e029  lea     rdx, aSizettodwordFa_1; "SizeTToDWord() Failed to convert to DWO"...
0x18002e030  mov     ecx, 2; unsigned int
0x18002e035  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18002e03a  jmp     short loc_18002E046
0x18002e03c  mov     rcx, [rbp+57h+var_90]; hKey
0x18002e040  call    cs:__imp_RegCloseKey
0x18002e046  mov     rsi, [rsi+20h]
0x18002e04a  test    rsi, rsi
0x18002e04d  jnz     loc_18002DE50
0x18002e053  mov     rcx, [rbp+57h+hKey]; hKey
0x18002e057  call    cs:__imp_RegCloseKey
0x18002e05d  mov     eax, ebx
0x18002e05f  mov     rcx, [rbp+57h+var_30]
0x18002e063  xor     rcx, rsp; StackCookie
0x18002e066  call    __security_check_cookie
0x18002e06b  mov     rbx, [rsp+0E0h+arg_18]
0x18002e073  add     rsp, 0C0h
0x18002e07a  pop     r15
0x18002e07c  pop     r14
0x18002e07e  pop     rdi
0x18002e07f  pop     rsi
0x18002e080  pop     rbp
0x18002e081  retn
```
