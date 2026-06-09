# RestoreHive

- ea: `0x140004764`
- end: `0x140004965`
- name: `RestoreHive`
- size: `513`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1400031f4`

## callees

- `0x140001340`
- `0x140001bb2`
- `0x140001cc6`
- `0x140002004`
- `0x1400022dc`
- `0x140002c20`
- `0x140002ce4`
- `0x140003068`
- `0x14000426c`
- `0x140004678`
- `0x140004764`
- `0x14000e75c`
- `0x14000e798`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegRestoreKeyW` at `0x1400048a9`
- `api-ms-win-core-registry-l1-1-0!RegRestoreKeyW` at `0x1400048a9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000487d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000487d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400048cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400048cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004922`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004922`

## pseudocode

```c
__int64 __fastcall RestoreHive(unsigned int a1, PCNZWCH *a2)
{
  FILE *v4; // rax
  unsigned int v5; // edi
  FILE *v6; // rax
  DWORD v8; // esi
  FILE *v9; // rax
  FILE *v10; // rax
  int v11; // [rsp+30h] [rbp-79h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-71h] BYREF
  int v13[2]; // [rsp+40h] [rbp-69h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-61h]
  LPCWSTR lpSubKey; // [rsp+90h] [rbp-19h]
  LPCWSTR lpFile; // [rsp+A0h] [rbp-9h]
  int v17; // [rsp+CCh] [rbp+23h]

  phkResult = 0;
  v11 = 0;
  v13[1] = 0;
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
    if ( !RegConnectMachine((__int64)v13) )
    {
      SaveErrorMessage(0xFFFFFFFFLL);
      v6 = o___acrt_iob_func_0(2u);
      ShowLastErrorEx(v6);
      goto LABEL_9;
    }
    v8 = RegOpenKeyExW(hKey, lpSubKey, 0, v17 | 0xF003F, &phkResult);
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
0x140004764  mov     [rsp-8+arg_10], rbx
0x140004769  push    rbp
0x14000476a  push    rsi
0x14000476b  push    rdi
0x14000476c  lea     rbp, [rsp-47h]
0x140004771  sub     rsp, 0F0h
0x140004778  mov     rax, cs:__security_cookie
0x14000477f  xor     rax, rsp
0x140004782  mov     [rbp+57h+var_20], rax
0x140004786  mov     rbx, rdx
0x140004789  mov     [rbp+57h+var_C8], 0
0x140004791  mov     edi, ecx
0x140004793  mov     [rbp+57h+var_D0], 0
0x14000479a  xor     eax, eax
0x14000479c  lea     rcx, [rbp+57h+var_C0]; void *
0x1400047a0  xor     edx, edx; Val
0x1400047a2  mov     [rbp+57h+var_BC], eax
0x1400047a5  mov     r8d, 94h; Size
0x1400047ab  call    memset_0
0x1400047b0  test    edi, edi
0x1400047b2  jz      loc_14000491D
0x1400047b8  test    rbx, rbx
0x1400047bb  jz      loc_14000491D
0x1400047c1  mov     esi, 5
0x1400047c6  lea     rdx, [rbp+57h+var_C0]
0x1400047ca  mov     ecx, esi
0x1400047cc  call    InitGlobalData
0x1400047d1  lea     rax, [rbp+57h+var_D0]
0x1400047d5  mov     rdx, rbx
0x1400047d8  lea     r9, [rbp+57h+var_C0]
0x1400047dc  mov     [rsp+100h+phkResult], rax
0x1400047e1  lea     r8, aRestore; "RESTORE"
0x1400047e8  mov     ecx, edi
0x1400047ea  call    ParseSaveCmdLine
0x1400047ef  test    eax, eax
0x1400047f1  jnz     short loc_14000480D
0x1400047f3  lea     ecx, [rsi-3]; Ix
0x1400047f6  call    _o___acrt_iob_func_0
0x1400047fb  mov     rcx, rax
0x1400047fe  mov     edx, 20000h
0x140004803  call    ShowLastErrorEx
0x140004808  lea     edi, [rsi-4]
0x14000480b  jmp     short loc_14000484E
0x14000480d  mov     edi, 1
0x140004812  cmp     [rbp+57h+var_D0], edi
0x140004815  jnz     short loc_140004822
0x140004817  mov     ecx, esi
0x140004819  call    Usage
0x14000481e  xor     edi, edi
0x140004820  jmp     short loc_14000484E
0x140004822  lea     rcx, [rbp+57h+var_C0]
0x140004826  call    RegConnectMachine
0x14000482b  test    eax, eax
0x14000482d  jnz     short loc_14000485E
0x14000482f  or      ecx, 0FFFFFFFFh
0x140004832  call    SaveErrorMessage
0x140004837  mov     ecx, 2; Ix
0x14000483c  call    _o___acrt_iob_func_0
0x140004841  mov     rcx, rax
0x140004844  mov     edx, 20001h
0x140004849  call    ShowLastErrorEx
0x14000484e  lea     rcx, [rbp+57h+var_C0]
0x140004852  call    FreeGlobalData
0x140004857  mov     eax, edi
0x140004859  jmp     loc_140004945
0x14000485e  mov     r9d, [rbp+57h+var_34]
0x140004862  lea     rax, [rbp+57h+var_C8]
0x140004866  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x14000486a  or      r9d, 0F003Fh; samDesired
0x140004871  mov     rcx, [rbp+57h+hKey]; hKey
0x140004875  xor     r8d, r8d; ulOptions
0x140004878  mov     [rsp+100h+phkResult], rax; phkResult
0x14000487d  call    cs:__imp_RegOpenKeyExW
0x140004884  nop     dword ptr [rax+rax+00h]
0x140004889  mov     esi, eax
0x14000488b  test    eax, eax
0x14000488d  jnz     short loc_1400048DF
0x14000488f  lea     ecx, [rax+12h]
0x140004892  call    RegAdjustTokenPrivileges
0x140004897  mov     esi, eax
0x140004899  test    eax, eax
0x14000489b  jnz     short loc_1400048C2
0x14000489d  mov     rdx, [rbp+57h+lpFile]; lpFile
0x1400048a1  lea     r8d, [rax+8]; dwFlags
0x1400048a5  mov     rcx, [rbp+57h+var_C8]; hKey
0x1400048a9  call    cs:__imp_RegRestoreKeyW
0x1400048b0  nop     dword ptr [rax+rax+00h]
0x1400048b5  mov     esi, eax
0x1400048b7  mov     eax, 0CEh
0x1400048bc  cmp     esi, 57h ; 'W'
0x1400048bf  cmovz   esi, eax
0x1400048c2  mov     rcx, [rbp+57h+var_C8]; hKey
0x1400048c6  test    rcx, rcx
0x1400048c9  jz      short loc_1400048DF
0x1400048cb  call    cs:__imp_RegCloseKey
0x1400048d2  nop     dword ptr [rax+rax+00h]
0x1400048d7  mov     [rbp+57h+var_C8], 0
0x1400048df  mov     ecx, esi
0x1400048e1  call    SaveErrorMessage
0x1400048e6  mov     eax, esi
0x1400048e8  neg     eax
0x1400048ea  mov     eax, esi
0x1400048ec  sbb     ebx, ebx
0x1400048ee  neg     ebx
0x1400048f0  neg     eax
0x1400048f2  sbb     ecx, ecx
0x1400048f4  neg     ecx
0x1400048f6  add     ecx, edi; Ix
0x1400048f8  call    _o___acrt_iob_func_0
0x1400048fd  mov     rcx, rax
0x140004900  lea     edx, [rbx+20000h]
0x140004906  call    ShowLastErrorEx
0x14000490b  lea     rcx, [rbp+57h+var_C0]
0x14000490f  call    FreeGlobalData
0x140004914  xor     eax, eax
0x140004916  test    esi, esi
0x140004918  setnz   al
0x14000491b  jmp     short loc_140004945
0x14000491d  mov     ecx, 57h ; 'W'; dwErrCode
0x140004922  call    cs:__imp_SetLastError
0x140004929  nop     dword ptr [rax+rax+00h]
0x14000492e  mov     ecx, 2; Ix
0x140004933  call    _o___acrt_iob_func_0
0x140004938  mov     rcx, rax
0x14000493b  call    ShowLastError
0x140004940  mov     eax, 1
0x140004945  mov     rcx, [rbp+57h+var_20]
0x140004949  xor     rcx, rsp; StackCookie
0x14000494c  call    __security_check_cookie
0x140004951  mov     rbx, [rsp+100h+arg_10]
0x140004959  add     rsp, 0F0h
0x140004960  pop     rdi
0x140004961  pop     rsi
0x140004962  pop     rbp
0x140004963  retn
```
