# FveEasUtil::IsOSRecoveryPasswordBackupAllowedByPolicy(bool *)

- ea: `0x180018144`
- end: `0x180018388`
- name: `?IsOSRecoveryPasswordBackupAllowedByPolicy@FveEasUtil@@SAJPEA_N@Z`
- size: `580`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015624`

## callees

- `0x1800037a0`
- `0x18000e354`
- `0x180018144`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180018346`
- `ADVAPI32!RegCloseKey` at `0x180018346`
- `ADVAPI32!RegOpenKeyExW` at `0x1800181eb`
- `ADVAPI32!RegOpenKeyExW` at `0x1800181eb`
- `ADVAPI32!RegQueryValueExW` at `0x180018271`
- `ADVAPI32!RegQueryValueExW` at `0x180018271`

## pseudocode

```c
__int64 __fastcall FveEasUtil::IsOSRecoveryPasswordBackupAllowedByPolicy(bool *a1)
{
  PVOID *v2; // rcx
  int v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // r9
  __int64 v6; // rdx
  unsigned int Data; // [rsp+60h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+38h] BYREF
  DWORD Type; // [rsp+70h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+48h] BYREF

  Data = 0;
  cbData = 4;
  Type = 4;
  hKey = 0;
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    v3 = -2147467261;
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x40) != 0 )
    {
      v4 = 92;
LABEL_16:
      WPP_SF_d(v2[2], v4, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, (unsigned int)v3);
LABEL_29:
      v2 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_38;
    }
    goto LABEL_38;
  }
  *a1 = 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\FVE", 0, 0x20019u, &hKey);
  if ( (unsigned int)(v3 - 2) <= 1 || v3 == 1168 )
  {
    v2 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_37;
    v6 = 93;
    goto LABEL_36;
  }
  if ( !v3 )
  {
    v3 = RegQueryValueExW(hKey, L"OSRecoveryPassword", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( (unsigned int)(v3 - 2) > 1 && v3 != 1168 )
    {
      if ( v3 )
      {
        if ( v3 > 0 )
          v3 = (unsigned __int16)v3 | 0x80070000;
        v2 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v4 = 96;
          goto LABEL_16;
        }
      }
      else
      {
        v5 = Data;
        v3 = 0;
        if ( Data - 1 > 1 )
          goto LABEL_29;
        *a1 = 1;
        v2 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, v5);
          goto LABEL_29;
        }
      }
      goto LABEL_38;
    }
    v2 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
    {
LABEL_37:
      v3 = 0;
      goto LABEL_38;
    }
    v6 = 95;
LABEL_36:
    WPP_SF_(v2[2], v6, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_37;
  }
  if ( v3 > 0 )
    v3 = (unsigned __int16)v3 | 0x80070000;
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v4 = 94;
    goto LABEL_16;
  }
LABEL_38:
  if ( hKey )
  {
    RegCloseKey(hKey);
    v2 = (PVOID *)WPP_GLOBAL_Control;
    hKey = 0;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x20) != 0 )
    WPP_SF_d(v2[2], 98, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, (unsigned int)v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180018144  push    rbp
0x180018146  push    rbx
0x180018147  push    rdi
0x180018148  push    r14
0x18001814a  push    r15
0x18001814c  mov     rbp, rsp
0x18001814f  sub     rsp, 30h
0x180018153  mov     eax, 4
0x180018158  mov     [rbp+Data], 0
0x18001815f  mov     [rbp+cbData], eax
0x180018162  mov     rdi, rcx
0x180018165  mov     [rbp+Type], eax
0x180018168  mov     [rbp+hKey], 0
0x180018170  mov     rcx, cs:WPP_GLOBAL_Control
0x180018177  lea     r14, WPP_GLOBAL_Control
0x18001817e  lea     r15, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180018185  cmp     rcx, r14
0x180018188  jz      short loc_1800181A6
0x18001818a  test    byte ptr [rcx+1Ch], 20h
0x18001818e  jz      short loc_1800181A6
0x180018190  mov     rcx, [rcx+10h]
0x180018194  lea     edx, [rax+57h]
0x180018197  mov     r8, r15
0x18001819a  call    WPP_SF_
0x18001819f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800181a6  test    rdi, rdi
0x1800181a9  jnz     short loc_1800181C8
0x1800181ab  mov     ebx, 80004003h
0x1800181b0  cmp     rcx, r14
0x1800181b3  jz      loc_18001833A
0x1800181b9  test    byte ptr [rcx+1Ch], 40h
0x1800181bd  jz      loc_18001833A
0x1800181c3  lea     edx, [rdi+5Ch]
0x1800181c6  jmp     short loc_180018239
0x1800181c8  lea     rax, [rbp+hKey]
0x1800181cc  mov     byte ptr [rdi], 0
0x1800181cf  mov     r9d, 20019h; samDesired
0x1800181d5  mov     [rsp+30h+phkResult], rax; phkResult
0x1800181da  xor     r8d, r8d; ulOptions
0x1800181dd  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\FVE"
0x1800181e4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800181eb  call    cs:__imp_RegOpenKeyExW
0x1800181f1  mov     ebx, eax
0x1800181f3  add     eax, 0FFFFFFFEh
0x1800181f6  cmp     eax, 1
0x1800181f9  jbe     loc_18001830E
0x1800181ff  cmp     ebx, 490h
0x180018205  jz      loc_18001830E
0x18001820b  test    ebx, ebx
0x18001820d  jz      short loc_18001824D
0x18001820f  jle     short loc_18001821A
0x180018211  movzx   ebx, bx
0x180018214  or      ebx, 80070000h
0x18001821a  mov     rcx, cs:WPP_GLOBAL_Control
0x180018221  cmp     rcx, r14
0x180018224  jz      loc_18001833A
0x18001822a  test    byte ptr [rcx+1Ch], 2
0x18001822e  jz      loc_18001833A
0x180018234  mov     edx, 5Eh ; '^'
0x180018239  mov     rcx, [rcx+10h]
0x18001823d  mov     r9d, ebx
0x180018240  mov     r8, r15
0x180018243  call    WPP_SF_d
0x180018248  jmp     loc_1800182EC
0x18001824d  mov     rcx, [rbp+hKey]; hKey
0x180018251  lea     rax, [rbp+cbData]
0x180018255  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18001825a  lea     r9, [rbp+Type]; lpType
0x18001825e  lea     rax, [rbp+Data]
0x180018262  xor     r8d, r8d; lpReserved
0x180018265  lea     rdx, aOsrecoverypass; "OSRecoveryPassword"
0x18001826c  mov     [rsp+30h+phkResult], rax; lpData
0x180018271  call    cs:__imp_RegQueryValueExW
0x180018277  mov     ebx, eax
0x180018279  add     eax, 0FFFFFFFEh
0x18001827c  cmp     eax, 1
0x18001827f  jbe     short loc_1800182F5
0x180018281  cmp     ebx, 490h
0x180018287  jz      short loc_1800182F5
0x180018289  test    ebx, ebx
0x18001828b  jz      short loc_1800182B9
0x18001828d  jle     short loc_180018298
0x18001828f  movzx   ebx, bx
0x180018292  or      ebx, 80070000h
0x180018298  mov     rcx, cs:WPP_GLOBAL_Control
0x18001829f  cmp     rcx, r14
0x1800182a2  jz      loc_18001833A
0x1800182a8  test    byte ptr [rcx+1Ch], 8
0x1800182ac  jz      loc_18001833A
0x1800182b2  mov     edx, 60h ; '`'
0x1800182b7  jmp     short loc_180018239
0x1800182b9  mov     r9d, [rbp+Data]
0x1800182bd  xor     ebx, ebx
0x1800182bf  lea     eax, [r9-1]
0x1800182c3  cmp     eax, 1
0x1800182c6  ja      short loc_1800182EC
0x1800182c8  mov     byte ptr [rdi], 1
0x1800182cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800182d2  cmp     rcx, r14
0x1800182d5  jz      short loc_18001833A
0x1800182d7  test    byte ptr [rcx+1Ch], 8
0x1800182db  jz      short loc_18001833A
0x1800182dd  mov     rcx, [rcx+10h]
0x1800182e1  lea     edx, [rbx+61h]
0x1800182e4  mov     r8, r15
0x1800182e7  call    WPP_SF_d
0x1800182ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800182f3  jmp     short loc_18001833A
0x1800182f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800182fc  cmp     rcx, r14
0x1800182ff  jz      short loc_180018338
0x180018301  test    byte ptr [rcx+1Ch], 8
0x180018305  jz      short loc_180018338
0x180018307  mov     edx, 5Fh ; '_'
0x18001830c  jmp     short loc_180018325
0x18001830e  mov     rcx, cs:WPP_GLOBAL_Control
0x180018315  cmp     rcx, r14
0x180018318  jz      short loc_180018338
0x18001831a  test    byte ptr [rcx+1Ch], 8
0x18001831e  jz      short loc_180018338
0x180018320  mov     edx, 5Dh ; ']'
0x180018325  mov     rcx, [rcx+10h]
0x180018329  mov     r8, r15
0x18001832c  call    WPP_SF_
0x180018331  mov     rcx, cs:WPP_GLOBAL_Control
0x180018338  xor     ebx, ebx
0x18001833a  mov     rax, [rbp+hKey]
0x18001833e  test    rax, rax
0x180018341  jz      short loc_18001835B
0x180018343  mov     rcx, rax; hKey
0x180018346  call    cs:__imp_RegCloseKey
0x18001834c  mov     rcx, cs:WPP_GLOBAL_Control
0x180018353  mov     [rbp+hKey], 0
0x18001835b  cmp     rcx, r14
0x18001835e  jz      short loc_18001837A
0x180018360  test    byte ptr [rcx+1Ch], 20h
0x180018364  jz      short loc_18001837A
0x180018366  mov     rcx, [rcx+10h]
0x18001836a  mov     edx, 62h ; 'b'
0x18001836f  mov     r9d, ebx
0x180018372  mov     r8, r15
0x180018375  call    WPP_SF_d
0x18001837a  mov     eax, ebx
0x18001837c  add     rsp, 30h
0x180018380  pop     r15
0x180018382  pop     r14
0x180018384  pop     rdi
0x180018385  pop     rbx
0x180018386  pop     rbp
0x180018387  retn
```
