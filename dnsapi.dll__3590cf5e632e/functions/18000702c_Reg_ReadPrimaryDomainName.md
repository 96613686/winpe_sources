# Reg_ReadPrimaryDomainName

- ea: `0x18000702c`
- end: `0x180007236`
- name: `Reg_ReadPrimaryDomainName`
- size: `522`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005a98`
- `0x180005b10`
- `0x1800065c0`
- `0x180086a64`

## callees

- `0x18000702c`
- `0x18000723c`
- `0x180007cfc`
- `0x18002b050`
- `0x18007e1f0`
- `0x18008b5f0`
- `0x1800dbfe0`
- `0x1800de650`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800071db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800071db`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800070b0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800070b0`

## pseudocode

```c
__int64 __fastcall Reg_ReadPrimaryDomainName(HKEY *a1, __int64 a2, _QWORD *a3)
{
  unsigned int v5; // eax
  _WORD *v6; // r8
  unsigned int v7; // edi
  __int64 v8; // rax
  unsigned int ValueEx2; // eax
  LPVOID lpMem; // [rsp+40h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-28h] BYREF
  HKEY v13[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v14; // [rsp+60h] [rbp-10h]

  v14 = 0;
  lpMem = 0;
  hKey = 0;
  *(_OWORD *)v13 = 0;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_(1035, 24, WPP_e863ea8ca75532f1bb84a1ddbc806e72_Traceguids);
  if ( a1 || (a1 = v13, (v7 = Reg_OpenSession(v13)) == 0) )
  {
    if ( *a1 )
    {
      ValueEx2 = Reg_GetValueEx2(0, *a1, 0, 4, 1, 0, &lpMem);
      v6 = lpMem;
      v7 = ValueEx2;
      if ( lpMem )
        goto LABEL_9;
    }
    if ( (RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\System\\DNSClient", 0, 1u, &hKey), hKey)
      && (v7 = Reg_GetValueEx2(0, hKey, 0, 5, 1, 0, &lpMem), RegCloseKey(hKey), (v6 = lpMem) != 0)
      || (v5 = Reg_GetValueEx2(0, a1[1], 0, 1, 1, 0, &lpMem), v6 = lpMem, v7 = v5, lpMem) )
    {
LABEL_9:
      v8 = -1;
      do
        ++v8;
      while ( v6[v8] );
      if ( !v8 )
      {
        DnsApiFree(v6);
        v6 = 0;
        lpMem = 0;
      }
    }
  }
  else
  {
    v6 = lpMem;
  }
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
  {
    WPP_SF_S(1035, 25, WPP_e863ea8ca75532f1bb84a1ddbc806e72_Traceguids, v6);
    v6 = lpMem;
  }
  *a3 = v6;
  if ( a1 == v13 )
    Reg_CloseSession(a1);
  return v7;
}

```

## disassembly

```asm
0x18000702c  mov     [rsp-28h+arg_8], rbx
0x180007031  push    rbp
0x180007032  push    rsi
0x180007033  push    rdi
0x180007034  push    r14
0x180007036  push    r15
0x180007038  mov     rbp, rsp
0x18000703b  sub     rsp, 70h
0x18000703f  mov     rax, cs:__security_cookie
0x180007046  xor     rax, rsp
0x180007049  mov     [rbp+var_8], rax
0x18000704d  xor     eax, eax
0x18000704f  xorps   xmm0, xmm0
0x180007052  xor     r14d, r14d
0x180007055  mov     [rbp+var_10], rax
0x180007059  mov     [rbp+lpMem], r14
0x18000705d  mov     rsi, r8
0x180007060  mov     [rbp+hKey], r14
0x180007064  mov     rbx, rcx
0x180007067  movups  xmmword ptr [rbp+var_20], xmm0
0x18000706b  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180007072  jnz     loc_1800071F9
0x180007078  test    rbx, rbx
0x18000707b  jz      loc_18000715E
0x180007081  mov     rdx, [rbx]
0x180007084  mov     r15d, 1
0x18000708a  test    rdx, rdx
0x18000708d  jnz     loc_18000717B
0x180007093  lea     rax, [rbp+hKey]
0x180007097  mov     r9d, r15d; samDesired
0x18000709a  xor     r8d, r8d; ulOptions
0x18000709d  mov     [rsp+70h+phkResult], rax; phkResult
0x1800070a2  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\System\\"...
0x1800070a9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800070b0  call    cs:__imp_RegOpenKeyExW
0x1800070b7  nop     dword ptr [rax+rax+00h]
0x1800070bc  mov     rdx, [rbp+hKey]
0x1800070c0  test    rdx, rdx
0x1800070c3  jnz     loc_1800071B2
0x1800070c9  mov     rdx, [rbx+8]
0x1800070cd  lea     rax, [rbp+lpMem]
0x1800070d1  mov     [rsp+70h+var_40], rax
0x1800070d6  mov     r9d, r15d
0x1800070d9  mov     [rsp+70h+var_48], r14d
0x1800070de  xor     r8d, r8d
0x1800070e1  xor     ecx, ecx
0x1800070e3  mov     dword ptr [rsp+70h+phkResult], r15d
0x1800070e8  call    Reg_GetValueEx2
0x1800070ed  mov     r8, [rbp+lpMem]
0x1800070f1  mov     edi, eax
0x1800070f3  test    r8, r8
0x1800070f6  jz      short loc_18000711A
0x1800070f8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800070fc  inc     rax
0x1800070ff  cmp     [r8+rax*2], r14w
0x180007104  jnz     short loc_1800070FC
0x180007106  test    rax, rax
0x180007109  jnz     short loc_18000711A
0x18000710b  mov     rcx, r8; lpMem
0x18000710e  call    DnsApiFree
0x180007113  mov     r8, r14
0x180007116  mov     [rbp+lpMem], r14
0x18000711a  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180007121  jnz     loc_180007214
0x180007127  lea     rax, [rbp+var_20]
0x18000712b  mov     [rsi], r8
0x18000712e  cmp     rbx, rax
0x180007131  jnz     short loc_18000713B
0x180007133  mov     rcx, rbx
0x180007136  call    Reg_CloseSession
0x18000713b  mov     eax, edi
0x18000713d  mov     rcx, [rbp+var_8]
0x180007141  xor     rcx, rsp; StackCookie
0x180007144  call    __security_check_cookie
0x180007149  mov     rbx, [rsp+70h+arg_8]
0x180007151  add     rsp, 70h
0x180007155  pop     r15
0x180007157  pop     r14
0x180007159  pop     rdi
0x18000715a  pop     rsi
0x18000715b  pop     rbp
0x18000715c  retn
0x18000715e  lea     rcx, [rbp+var_20]; phkResult
0x180007162  lea     rbx, [rbp+var_20]
0x180007166  call    Reg_OpenSession
0x18000716b  mov     edi, eax
0x18000716d  test    eax, eax
0x18000716f  jz      loc_180007081
0x180007175  mov     r8, [rbp+lpMem]
0x180007179  jmp     short loc_18000711A
0x18000717b  lea     rax, [rbp+lpMem]
0x18000717f  mov     r9d, 4
0x180007185  mov     [rsp+70h+var_40], rax
0x18000718a  xor     r8d, r8d
0x18000718d  mov     [rsp+70h+var_48], r14d
0x180007192  xor     ecx, ecx
0x180007194  mov     dword ptr [rsp+70h+phkResult], r15d
0x180007199  call    Reg_GetValueEx2
0x18000719e  mov     r8, [rbp+lpMem]
0x1800071a2  mov     edi, eax
0x1800071a4  test    r8, r8
0x1800071a7  jz      loc_180007093
0x1800071ad  jmp     loc_1800070F8
0x1800071b2  lea     rax, [rbp+lpMem]
0x1800071b6  mov     r9d, 5
0x1800071bc  mov     [rsp+70h+var_40], rax
0x1800071c1  xor     r8d, r8d
0x1800071c4  mov     [rsp+70h+var_48], r14d
0x1800071c9  xor     ecx, ecx
0x1800071cb  mov     dword ptr [rsp+70h+phkResult], r15d
0x1800071d0  call    Reg_GetValueEx2
0x1800071d5  mov     rcx, [rbp+hKey]; hKey
0x1800071d9  mov     edi, eax
0x1800071db  call    cs:__imp_RegCloseKey
0x1800071e2  nop     dword ptr [rax+rax+00h]
0x1800071e7  mov     r8, [rbp+lpMem]
0x1800071eb  test    r8, r8
0x1800071ee  jnz     loc_1800070F8
0x1800071f4  jmp     loc_1800070C9
0x1800071f9  mov     edx, 18h
0x1800071fe  lea     r8, WPP_e863ea8ca75532f1bb84a1ddbc806e72_Traceguids
0x180007205  mov     ecx, 40Bh
0x18000720a  call    WPP_SF_
0x18000720f  jmp     loc_180007078
0x180007214  mov     r9, r8
0x180007217  mov     edx, 19h
0x18000721c  lea     r8, WPP_e863ea8ca75532f1bb84a1ddbc806e72_Traceguids
0x180007223  mov     ecx, 40Bh
0x180007228  call    WPP_SF_S
0x18000722d  mov     r8, [rbp+lpMem]
0x180007231  jmp     loc_180007127
```
