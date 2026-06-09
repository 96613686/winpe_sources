# RestoreHive

- ea: `0x140004518`
- end: `0x140004700`
- name: `RestoreHive`
- size: `488`
- prototype: `__int64 __fastcall(unsigned int, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1400030b8`

## callees

- `0x140001340`
- `0x140001bb2`
- `0x140001cc6`
- `0x140001fec`
- `0x140002234`
- `0x140002ac8`
- `0x140002b70`
- `0x140002f30`
- `0x14000406c`
- `0x140004450`
- `0x140004518`
- `0x14000dbe8`
- `0x14000dc24`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegRestoreKeyW` at `0x140004657`
- `api-ms-win-core-registry-l1-1-0!RegRestoreKeyW` at `0x140004657`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140004631`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140004631`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004673`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004673`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400046c4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400046c4`

## pseudocode

```c
__int64 __fastcall RestoreHive(unsigned int a1, __int64 a2)
{
  FILE *v4; // rax
  unsigned int v5; // edi
  FILE *v6; // rax
  unsigned int v8; // esi
  FILE *v9; // rax
  FILE *v10; // rax
  int v11; // [rsp+30h] [rbp-79h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-71h] BYREF
  _BYTE v13[4]; // [rsp+40h] [rbp-69h] BYREF
  int v14; // [rsp+44h] [rbp-65h]
  HKEY hKey; // [rsp+48h] [rbp-61h]
  LPCWSTR lpSubKey; // [rsp+90h] [rbp-19h]
  LPCWSTR lpFile; // [rsp+A0h] [rbp-9h]
  int v18; // [rsp+CCh] [rbp+23h]

  phkResult = 0;
  v11 = 0;
  v14 = 0;
  memset_0(v13, 0, 0x94u);
  if ( a1 && a2 )
  {
    InitGlobalData(5, v13);
    if ( !(unsigned int)ParseSaveCmdLine(a1, a2, L"RESTORE", v13, &v11) )
    {
      v4 = o___acrt_iob_func_0(2u);
      ShowLastErrorEx(v4);
      v5 = 1;
LABEL_9:
      FreeGlobalData(v13);
      return v5;
    }
    v5 = 1;
    if ( v11 == 1 )
    {
      Usage(5);
      v5 = 0;
      goto LABEL_9;
    }
    if ( !(unsigned int)RegConnectMachine(v13) )
    {
      SaveErrorMessage(0xFFFFFFFFLL);
      v6 = o___acrt_iob_func_0(2u);
      ShowLastErrorEx(v6);
      goto LABEL_9;
    }
    v8 = RegOpenKeyExW(hKey, lpSubKey, 0, v18 | 0xF003F, &phkResult);
    if ( !v8 )
    {
      v8 = RegAdjustTokenPrivileges(18);
      if ( !v8 )
      {
        v8 = RegRestoreKeyW(phkResult, lpFile, 8u);
        if ( v8 == 87 )
          v8 = 206;
      }
      if ( phkResult )
      {
        RegCloseKey(phkResult);
        phkResult = 0;
      }
    }
    SaveErrorMessage(v8);
    v9 = o___acrt_iob_func_0((unsigned int)(v8 != 0) + 1);
    ShowLastErrorEx(v9);
    FreeGlobalData(v13);
    return v8 != 0;
  }
  else
  {
    SetLastError(0x57u);
    v10 = o___acrt_iob_func_0(2u);
    ShowLastError(v10);
    return 1;
  }
}

```

## disassembly

```asm
0x140004518  mov     [rsp-8+arg_10], rbx
0x14000451d  push    rbp
0x14000451e  push    rsi
0x14000451f  push    rdi
0x140004520  lea     rbp, [rsp-47h]
0x140004525  sub     rsp, 0F0h
0x14000452c  mov     rax, cs:__security_cookie
0x140004533  xor     rax, rsp
0x140004536  mov     [rbp+57h+var_20], rax
0x14000453a  mov     rbx, rdx
0x14000453d  mov     [rbp+57h+var_C8], 0
0x140004545  mov     edi, ecx
0x140004547  mov     [rbp+57h+var_D0], 0
0x14000454e  xor     eax, eax
0x140004550  lea     rcx, [rbp+57h+var_C0]; void *
0x140004554  xor     edx, edx; Val
0x140004556  mov     [rbp+57h+var_BC], eax
0x140004559  mov     r8d, 94h; Size
0x14000455f  call    memset_0
0x140004564  test    edi, edi
0x140004566  jz      loc_1400046BF
0x14000456c  test    rbx, rbx
0x14000456f  jz      loc_1400046BF
0x140004575  mov     esi, 5
0x14000457a  lea     rdx, [rbp+57h+var_C0]
0x14000457e  mov     ecx, esi
0x140004580  call    InitGlobalData
0x140004585  lea     rax, [rbp+57h+var_D0]
0x140004589  mov     rdx, rbx
0x14000458c  lea     r9, [rbp+57h+var_C0]
0x140004590  mov     [rsp+100h+phkResult], rax
0x140004595  lea     r8, aRestore; "RESTORE"
0x14000459c  mov     ecx, edi
0x14000459e  call    ParseSaveCmdLine
0x1400045a3  test    eax, eax
0x1400045a5  jnz     short loc_1400045C1
0x1400045a7  lea     ecx, [rsi-3]; Ix
0x1400045aa  call    _o___acrt_iob_func_0
0x1400045af  mov     rcx, rax
0x1400045b2  mov     edx, 20000h
0x1400045b7  call    ShowLastErrorEx
0x1400045bc  lea     edi, [rsi-4]
0x1400045bf  jmp     short loc_140004602
0x1400045c1  mov     edi, 1
0x1400045c6  cmp     [rbp+57h+var_D0], edi
0x1400045c9  jnz     short loc_1400045D6
0x1400045cb  mov     ecx, esi
0x1400045cd  call    Usage
0x1400045d2  xor     edi, edi
0x1400045d4  jmp     short loc_140004602
0x1400045d6  lea     rcx, [rbp+57h+var_C0]
0x1400045da  call    RegConnectMachine
0x1400045df  test    eax, eax
0x1400045e1  jnz     short loc_140004612
0x1400045e3  or      ecx, 0FFFFFFFFh
0x1400045e6  call    SaveErrorMessage
0x1400045eb  mov     ecx, 2; Ix
0x1400045f0  call    _o___acrt_iob_func_0
0x1400045f5  mov     rcx, rax
0x1400045f8  mov     edx, 20001h
0x1400045fd  call    ShowLastErrorEx
0x140004602  lea     rcx, [rbp+57h+var_C0]
0x140004606  call    FreeGlobalData
0x14000460b  mov     eax, edi
0x14000460d  jmp     loc_1400046E1
0x140004612  mov     r9d, [rbp+57h+var_34]
0x140004616  lea     rax, [rbp+57h+var_C8]
0x14000461a  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x14000461e  or      r9d, 0F003Fh; samDesired
0x140004625  mov     rcx, [rbp+57h+hKey]; hKey
0x140004629  xor     r8d, r8d; ulOptions
0x14000462c  mov     [rsp+100h+phkResult], rax; phkResult
0x140004631  call    cs:__imp_RegOpenKeyExW
0x140004637  mov     esi, eax
0x140004639  test    eax, eax
0x14000463b  jnz     short loc_140004681
0x14000463d  lea     ecx, [rax+12h]
0x140004640  call    RegAdjustTokenPrivileges
0x140004645  mov     esi, eax
0x140004647  test    eax, eax
0x140004649  jnz     short loc_14000466A
0x14000464b  mov     rdx, [rbp+57h+lpFile]; lpFile
0x14000464f  lea     r8d, [rax+8]; dwFlags
0x140004653  mov     rcx, [rbp+57h+var_C8]; hKey
0x140004657  call    cs:__imp_RegRestoreKeyW
0x14000465d  mov     esi, eax
0x14000465f  mov     eax, 0CEh
0x140004664  cmp     esi, 57h ; 'W'
0x140004667  cmovz   esi, eax
0x14000466a  mov     rcx, [rbp+57h+var_C8]; hKey
0x14000466e  test    rcx, rcx
0x140004671  jz      short loc_140004681
0x140004673  call    cs:__imp_RegCloseKey
0x140004679  mov     [rbp+57h+var_C8], 0
0x140004681  mov     ecx, esi
0x140004683  call    SaveErrorMessage
0x140004688  mov     eax, esi
0x14000468a  neg     eax
0x14000468c  mov     eax, esi
0x14000468e  sbb     ebx, ebx
0x140004690  neg     ebx
0x140004692  neg     eax
0x140004694  sbb     ecx, ecx
0x140004696  neg     ecx
0x140004698  add     ecx, edi; Ix
0x14000469a  call    _o___acrt_iob_func_0
0x14000469f  mov     rcx, rax
0x1400046a2  lea     edx, [rbx+20000h]
0x1400046a8  call    ShowLastErrorEx
0x1400046ad  lea     rcx, [rbp+57h+var_C0]
0x1400046b1  call    FreeGlobalData
0x1400046b6  xor     eax, eax
0x1400046b8  test    esi, esi
0x1400046ba  setnz   al
0x1400046bd  jmp     short loc_1400046E1
0x1400046bf  mov     ecx, 57h ; 'W'; dwErrCode
0x1400046c4  call    cs:__imp_SetLastError
0x1400046ca  mov     ecx, 2; Ix
0x1400046cf  call    _o___acrt_iob_func_0
0x1400046d4  mov     rcx, rax
0x1400046d7  call    ShowLastError
0x1400046dc  mov     eax, 1
0x1400046e1  mov     rcx, [rbp+57h+var_20]
0x1400046e5  xor     rcx, rsp; StackCookie
0x1400046e8  call    __security_check_cookie
0x1400046ed  mov     rbx, [rsp+100h+arg_10]
0x1400046f5  add     rsp, 0F0h
0x1400046fc  pop     rdi
0x1400046fd  pop     rsi
0x1400046fe  pop     rbp
0x1400046ff  retn
```
