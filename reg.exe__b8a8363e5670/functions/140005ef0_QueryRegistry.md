# QueryRegistry

- ea: `0x140005ef0`
- end: `0x1400061dd`
- name: `QueryRegistry`
- size: `749`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config`

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
- `0x140004e84`
- `0x140005910`
- `0x140005c78`
- `0x140005ef0`
- `0x1400061e4`
- `0x14000d164`
- `0x14000d694`
- `0x14000e75c`
- `0x14000e798`
- `0x14000e864`
- `0x14000ec2c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140005fdb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140005fdb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000617f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000617f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006195`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006195`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000606f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000606f`

## pseudocode

```c
__int64 __fastcall QueryRegistry(unsigned int a1, __int64 a2)
{
  FILE *v4; // rax
  unsigned int v5; // esi
  __int64 v6; // rcx
  unsigned int v7; // eax
  FILE *v8; // rax
  FILE *v10; // rax
  BOOL v11; // ebx
  __int64 v12; // rcx
  int EnumKeys; // edi
  FILE *v14; // rax
  BOOL v15; // r14d
  int v16; // edi
  __int64 ResString2FromModule; // rbx
  FILE *v18; // rax
  FILE *v19; // rax
  FILE *v20; // rax
  PHKEY phkResult; // [rsp+20h] [rbp-99h]
  int v22; // [rsp+30h] [rbp-89h] BYREF
  HKEY hkey; // [rsp+38h] [rbp-81h] BYREF
  _BYTE v24[4]; // [rsp+40h] [rbp-79h] BYREF
  int v25; // [rsp+44h] [rbp-75h]
  HKEY hKey; // [rsp+48h] [rbp-71h]
  int v27; // [rsp+60h] [rbp-59h]
  LPCWSTR lpSubKey; // [rsp+90h] [rbp-29h]
  __int64 v29; // [rsp+98h] [rbp-21h]
  LPCWSTR lpString; // [rsp+A0h] [rbp-19h]
  __int64 v31; // [rsp+B8h] [rbp-1h]
  __int64 v32; // [rsp+C0h] [rbp+7h]
  int v33; // [rsp+CCh] [rbp+13h]
  _DWORD v34[6]; // [rsp+E0h] [rbp+27h] BYREF

  hkey = 0;
  v22 = 0;
  v25 = 0;
  memset_0(v24, 0, 0x94u);
  if ( a1 && a2 )
  {
    InitGlobalData(0, v24);
    if ( !(unsigned int)ParseQueryCmdLine(a1, a2, v24, &v22) )
    {
      v4 = o___acrt_iob_func_0(2u);
      ShowLastErrorEx(v4);
      v5 = 1;
LABEL_12:
      FreeGlobalData(v24);
      return v5;
    }
    v5 = 1;
    if ( v22 == 1 )
    {
      Usage(0);
      v5 = 0;
      goto LABEL_12;
    }
    if ( !RegConnectMachine((__int64)v24) )
    {
      v6 = 0xFFFFFFFFLL;
LABEL_11:
      SaveErrorMessage(v6);
      v8 = o___acrt_iob_func_0(2u);
      ShowLastErrorEx(v8);
      goto LABEL_12;
    }
    v7 = RegOpenKeyExW(hKey, lpSubKey, 0, v33 | 0x20019, &hkey);
    if ( v7 )
    {
      v6 = v7;
      goto LABEL_11;
    }
    v10 = o___acrt_iob_func_0(1u);
    ShowMessage(v10, L"\n");
    *(_OWORD *)&v34[1] = 0;
    if ( v31 || !lpString || v32 || v27 )
    {
      v34[0] = 1;
      EnumKeys = QueryEnumKeys(hkey, v29, v24, v34);
      v11 = v31 || lpString || v32;
    }
    else
    {
      v34[0] = 1;
      if ( !lstrlenW(lpString) || (unsigned int)FindOneOf2(lpString) == -1 )
      {
        EnumKeys = QueryValue(hkey, v29, lpString, (__int64)v24, v34);
        v11 = 0;
        v14 = o___acrt_iob_func_0(1u);
        ShowMessage(v14, L"\n");
      }
      else
      {
        v11 = 1;
        EnumKeys = QueryEnumValues(hkey, v29, (__int64)v24, v34);
      }
    }
    if ( EnumKeys )
    {
      v15 = 1;
      v19 = o___acrt_iob_func_0(2u);
      ShowLastErrorEx(v19);
    }
    else
    {
      v15 = 0;
      if ( v11 )
      {
        v16 = v34[4];
        v15 = v34[4] == 0;
        ResString2FromModule = GetResString2FromModule(v12, 521, 0);
        v18 = o___acrt_iob_func_0(1u);
        LODWORD(phkResult) = v16;
        ShowMessageEx(v18, 1, 1, ResString2FromModule, phkResult);
      }
    }
    if ( hkey )
      RegCloseKey(hkey);
    return v15;
  }
  else
  {
    SetLastError(0x57u);
    v20 = o___acrt_iob_func_0(2u);
    ShowLastError(v20);
    return 1;
  }
}

```

## disassembly

```asm
0x140005ef0  mov     [rsp-8+arg_10], rbx
0x140005ef5  mov     [rsp-8+arg_18], rsi
0x140005efa  push    rbp
0x140005efb  push    rdi
0x140005efc  push    r14
0x140005efe  lea     rbp, [rsp-47h]
0x140005f03  sub     rsp, 100h
0x140005f0a  mov     rax, cs:__security_cookie
0x140005f11  xor     rax, rsp
0x140005f14  mov     [rbp+57h+var_18], rax
0x140005f18  mov     rbx, rdx
0x140005f1b  mov     [rsp+110h+hkey], 0
0x140005f24  mov     edi, ecx
0x140005f26  mov     [rsp+110h+var_E0], 0
0x140005f2e  xor     eax, eax
0x140005f30  lea     rcx, [rbp+57h+var_D0]; void *
0x140005f34  xor     edx, edx; Val
0x140005f36  mov     [rbp+57h+var_CC], eax
0x140005f39  mov     r8d, 94h; Size
0x140005f3f  call    memset_0
0x140005f44  test    edi, edi
0x140005f46  jz      loc_140006190
0x140005f4c  test    rbx, rbx
0x140005f4f  jz      loc_140006190
0x140005f55  lea     rdx, [rbp+57h+var_D0]
0x140005f59  xor     ecx, ecx
0x140005f5b  call    InitGlobalData
0x140005f60  lea     r9, [rsp+110h+var_E0]
0x140005f65  mov     rdx, rbx
0x140005f68  lea     r8, [rbp+57h+var_D0]
0x140005f6c  mov     ecx, edi
0x140005f6e  call    ParseQueryCmdLine
0x140005f73  test    eax, eax
0x140005f75  jnz     short loc_140005F93
0x140005f77  lea     ecx, [rax+2]; Ix
0x140005f7a  call    _o___acrt_iob_func_0
0x140005f7f  mov     rcx, rax
0x140005f82  mov     edx, 20000h
0x140005f87  call    ShowLastErrorEx
0x140005f8c  mov     esi, 1
0x140005f91  jmp     short loc_140006009
0x140005f93  mov     esi, 1
0x140005f98  cmp     [rsp+110h+var_E0], esi
0x140005f9c  jnz     short loc_140005FA9
0x140005f9e  xor     ecx, ecx
0x140005fa0  call    Usage
0x140005fa5  xor     esi, esi
0x140005fa7  jmp     short loc_140006009
0x140005fa9  lea     rcx, [rbp+57h+var_D0]
0x140005fad  call    RegConnectMachine
0x140005fb2  test    eax, eax
0x140005fb4  jnz     short loc_140005FBB
0x140005fb6  or      ecx, 0FFFFFFFFh
0x140005fb9  jmp     short loc_140005FED
0x140005fbb  mov     r9d, [rbp+57h+var_44]
0x140005fbf  lea     rax, [rsp+110h+hkey]
0x140005fc4  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x140005fc8  or      r9d, 20019h; samDesired
0x140005fcf  mov     rcx, [rbp+57h+hKey]; hKey
0x140005fd3  xor     r8d, r8d; ulOptions
0x140005fd6  mov     [rsp+110h+phkResult], rax; phkResult
0x140005fdb  call    cs:__imp_RegOpenKeyExW
0x140005fe2  nop     dword ptr [rax+rax+00h]
0x140005fe7  test    eax, eax
0x140005fe9  jz      short loc_140006019
0x140005feb  mov     ecx, eax
0x140005fed  call    SaveErrorMessage
0x140005ff2  mov     ecx, 2; Ix
0x140005ff7  call    _o___acrt_iob_func_0
0x140005ffc  mov     edx, 20001h
0x140006001  mov     rcx, rax
0x140006004  call    ShowLastErrorEx
0x140006009  lea     rcx, [rbp+57h+var_D0]
0x14000600d  call    FreeGlobalData
0x140006012  mov     eax, esi
0x140006014  jmp     loc_1400061B8
0x140006019  mov     ecx, esi; Ix
0x14000601b  call    _o___acrt_iob_func_0
0x140006020  mov     rcx, rax; Stream
0x140006023  lea     rdx, asc_140011950; "\n"
0x14000602a  call    ShowMessage
0x14000602f  cmp     [rbp+57h+var_58], 0
0x140006034  xorps   xmm0, xmm0
0x140006037  movdqu  xmmword ptr [rbp+57h+var_30+4], xmm0
0x14000603c  jnz     loc_1400060E4
0x140006042  mov     r8, [rbp+57h+lpString]
0x140006046  test    r8, r8
0x140006049  jz      loc_1400060E4
0x14000604f  cmp     [rbp+57h+var_50], 0
0x140006054  jnz     loc_1400060E4
0x14000605a  cmp     [rbp+57h+var_B0], 0
0x14000605e  jnz     loc_1400060E4
0x140006064  mov     [rbp+57h+var_30], esi
0x140006067  test    r8, r8
0x14000606a  jz      short loc_1400060AD
0x14000606c  mov     rcx, r8; lpString
0x14000606f  call    cs:__imp_lstrlenW
0x140006076  nop     dword ptr [rax+rax+00h]
0x14000607b  test    eax, eax
0x14000607d  jz      short loc_1400060A9
0x14000607f  mov     rcx, [rbp+57h+lpString]; lpString
0x140006083  call    FindOneOf2
0x140006088  cmp     eax, 0FFFFFFFFh
0x14000608b  jz      short loc_1400060A9
0x14000608d  mov     rdx, [rbp+57h+var_78]
0x140006091  lea     r9, [rbp+57h+var_30]
0x140006095  mov     rcx, [rsp+110h+hkey]; hKey
0x14000609a  lea     r8, [rbp+57h+var_D0]
0x14000609e  mov     ebx, esi
0x1400060a0  call    QueryEnumValues
0x1400060a5  mov     edi, eax
0x1400060a7  jmp     short loc_14000611A
0x1400060a9  mov     r8, [rbp+57h+lpString]
0x1400060ad  mov     rdx, [rbp+57h+var_78]
0x1400060b1  lea     rax, [rbp+57h+var_30]
0x1400060b5  mov     rcx, [rsp+110h+hkey]; hkey
0x1400060ba  lea     r9, [rbp+57h+var_D0]
0x1400060be  mov     [rsp+110h+phkResult], rax; __int64
0x1400060c3  call    QueryValue
0x1400060c8  mov     ecx, esi; Ix
0x1400060ca  mov     edi, eax
0x1400060cc  xor     ebx, ebx
0x1400060ce  call    _o___acrt_iob_func_0
0x1400060d3  mov     rcx, rax; Stream
0x1400060d6  lea     rdx, asc_140011950; "\n"
0x1400060dd  call    ShowMessage
0x1400060e2  jmp     short loc_14000611A
0x1400060e4  mov     rdx, [rbp+57h+var_78]
0x1400060e8  lea     r9, [rbp+57h+var_30]
0x1400060ec  mov     rcx, [rsp+110h+hkey]
0x1400060f1  lea     r8, [rbp+57h+var_D0]
0x1400060f5  mov     [rbp+57h+var_30], esi
0x1400060f8  call    QueryEnumKeys
0x1400060fd  cmp     [rbp+57h+var_58], 0
0x140006102  mov     edi, eax
0x140006104  jnz     short loc_140006118
0x140006106  cmp     [rbp+57h+lpString], 0
0x14000610b  jnz     short loc_140006118
0x14000610d  cmp     [rbp+57h+var_50], 0
0x140006112  jnz     short loc_140006118
0x140006114  xor     ebx, ebx
0x140006116  jmp     short loc_14000611A
0x140006118  mov     ebx, esi
0x14000611a  test    edi, edi
0x14000611c  jnz     short loc_14000615B
0x14000611e  xor     r14d, r14d
0x140006121  test    ebx, ebx
0x140006123  jz      short loc_140006175
0x140006125  mov     edi, [rbp+57h+var_30+10h]
0x140006128  mov     edx, 209h
0x14000612d  test    edi, edi
0x14000612f  cmovz   r14d, esi
0x140006133  xor     r8d, r8d
0x140006136  call    GetResString2FromModule
0x14000613b  mov     ecx, esi; Ix
0x14000613d  mov     rbx, rax
0x140006140  call    _o___acrt_iob_func_0
0x140006145  mov     rcx, rax
0x140006148  mov     dword ptr [rsp+110h+phkResult], edi
0x14000614c  mov     r9, rbx
0x14000614f  mov     r8d, esi
0x140006152  mov     edx, esi
0x140006154  call    ShowMessageEx
0x140006159  jmp     short loc_140006175
0x14000615b  mov     ecx, 2; Ix
0x140006160  mov     r14d, esi
0x140006163  call    _o___acrt_iob_func_0
0x140006168  mov     rcx, rax
0x14000616b  mov     edx, 20001h
0x140006170  call    ShowLastErrorEx
0x140006175  mov     rcx, [rsp+110h+hkey]; hKey
0x14000617a  test    rcx, rcx
0x14000617d  jz      short loc_14000618B
0x14000617f  call    cs:__imp_RegCloseKey
0x140006186  nop     dword ptr [rax+rax+00h]
0x14000618b  mov     eax, r14d
0x14000618e  jmp     short loc_1400061B8
0x140006190  mov     ecx, 57h ; 'W'; dwErrCode
0x140006195  call    cs:__imp_SetLastError
0x14000619c  nop     dword ptr [rax+rax+00h]
0x1400061a1  mov     ecx, 2; Ix
0x1400061a6  call    _o___acrt_iob_func_0
0x1400061ab  mov     rcx, rax
0x1400061ae  call    ShowLastError
0x1400061b3  mov     eax, 1
0x1400061b8  mov     rcx, [rbp+57h+var_18]
0x1400061bc  xor     rcx, rsp; StackCookie
0x1400061bf  call    __security_check_cookie
0x1400061c4  lea     r11, [rsp+110h+var_10]
0x1400061cc  mov     rbx, [r11+30h]
0x1400061d0  mov     rsi, [r11+38h]
0x1400061d4  mov     rsp, r11
0x1400061d7  pop     r14
0x1400061d9  pop     rdi
0x1400061da  pop     rbp
0x1400061db  retn
```
