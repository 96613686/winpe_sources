# UpdateUserPinnedShareCount(int)

- ea: `0x18004996c`
- end: `0x180049c42`
- name: `?UpdateUserPinnedShareCount@@YAXH@Z`
- size: `726`
- prototype: `void __fastcall(int)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180064a64`
- `0x1800650cc`

## callees

- `0x180036394`
- `0x18003c460`
- `0x18003c488`
- `0x18003c4e8`
- `0x18004996c`
- `0x18004a01c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180049a31`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180049a31`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800499ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800499ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049bb2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049bf7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049bb2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049bf7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180049b76`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180049b76`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800499fc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800499fc`

## pseudocode

```c
void __fastcall UpdateUserPinnedShareCount(int a1)
{
  unsigned int v2; // eax
  LSTATUS v3; // eax
  LSTATUS v4; // eax
  int v5; // edx
  CObjectMonitor *v6; // r10
  int v7; // edx
  int v8; // edx
  LSTATUS v9; // eax
  HKEY hKey; // [rsp+50h] [rbp-10h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-8h] BYREF
  int Data; // [rsp+88h] [rbp+28h] BYREF
  DWORD Type; // [rsp+90h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+98h] [rbp+38h] BYREF

  Data = 0;
  Type = 0;
  cbData = 4;
  phkResult = 0;
  hKey = 0;
  v2 = RegOpenCurrentUser(0x20007u, &phkResult);
  if ( !v2 )
  {
    v3 = RegCreateKeyExW(
           phkResult,
           L"Software\\Microsoft\\UserData\\OfflineFiles",
           0,
           (LPWSTR)&Class,
           0,
           0x20007u,
           0,
           &hKey,
           0);
    if ( v3 )
    {
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          (unsigned int)WPP_65174b6254cf30406df57586ff17ec03_Traceguids,
          (unsigned int)L"Software\\Microsoft\\UserData\\OfflineFiles",
          v3);
      }
      goto LABEL_37;
    }
    v4 = RegQueryValueExW(hKey, L"UserPinnedShareCount", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( v4 == 2 )
    {
      v5 = 0;
      Data = 0;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control )
        goto LABEL_20;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 )
        goto LABEL_17;
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        WPP_65174b6254cf30406df57586ff17ec03_Traceguids,
        L"UserPinnedShareCount");
      goto LABEL_16;
    }
    if ( v4 )
    {
      v5 = 0;
      Data = 0;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control )
        goto LABEL_20;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 )
        goto LABEL_17;
      v7 = 21;
    }
    else
    {
      LOBYTE(v4) = Type;
      if ( Type == 4 )
      {
LABEL_16:
        v6 = WPP_GLOBAL_Control;
        v5 = Data;
        goto LABEL_17;
      }
      v5 = 0;
      Data = 0;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control )
        goto LABEL_20;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 )
      {
LABEL_17:
        if ( v6 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x20) != 0 )
        {
          WPP_SF_Sdc(*((_QWORD *)v6 + 2));
          v5 = Data;
          v6 = WPP_GLOBAL_Control;
        }
LABEL_20:
        if ( a1 )
        {
          if ( v5 != -1 )
          {
            v8 = v5 + 1;
LABEL_25:
            Data = v8;
LABEL_29:
            v9 = RegSetValueExW(hKey, L"UserPinnedShareCount", 0, 4u, (const BYTE *)&Data, cbData);
            if ( v9
              && WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
            {
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                25,
                (unsigned int)WPP_65174b6254cf30406df57586ff17ec03_Traceguids,
                (unsigned int)L"UserPinnedShareCount",
                v9);
            }
            RegCloseKey(hKey);
LABEL_37:
            RegCloseKey(phkResult);
            return;
          }
        }
        else if ( v5 )
        {
          v8 = v5 - 1;
          goto LABEL_25;
        }
        if ( v6 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x20) != 0 )
          WPP_SF_(*((_QWORD *)v6 + 2), 24, WPP_65174b6254cf30406df57586ff17ec03_Traceguids);
        goto LABEL_29;
      }
      v7 = 22;
    }
    WPP_SF_Sd(
      *((_QWORD *)v6 + 2),
      v7,
      (unsigned int)WPP_65174b6254cf30406df57586ff17ec03_Traceguids,
      (unsigned int)L"UserPinnedShareCount",
      v4);
    goto LABEL_16;
  }
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_65174b6254cf30406df57586ff17ec03_Traceguids, v2);
}

```

## disassembly

```asm
0x18004996c  mov     [rsp-18h+arg_0], rdi
0x180049971  push    rbp
0x180049972  push    r12
0x180049974  push    r14
0x180049976  mov     rbp, rsp
0x180049979  sub     rsp, 60h
0x18004997d  mov     r14d, ecx
0x180049980  mov     [rbp+Data], 0
0x180049987  mov     ecx, 20007h; samDesired
0x18004998c  mov     [rbp+Type], 0
0x180049993  lea     rdx, [rbp+phkResult]; phkResult
0x180049997  mov     [rbp+cbData], 4
0x18004999e  mov     [rbp+phkResult], 0
0x1800499a6  mov     [rbp+hKey], 0
0x1800499ae  call    cs:__imp_RegOpenCurrentUser
0x1800499b4  test    eax, eax
0x1800499b6  jnz     loc_180049BFF
0x1800499bc  mov     rcx, [rbp+phkResult]; hKey
0x1800499c0  lea     rax, [rbp+hKey]
0x1800499c4  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x1800499cd  lea     r9, Class; lpClass
0x1800499d4  mov     [rsp+60h+var_28], rax; phkResult
0x1800499d9  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\UserData\\OfflineF"...
0x1800499e0  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800499e9  xor     r8d, r8d; Reserved
0x1800499ec  mov     [rsp+60h+samDesired], 20007h; samDesired
0x1800499f4  mov     [rsp+60h+dwOptions], 0; dwOptions
0x1800499fc  call    cs:__imp_RegCreateKeyExW
0x180049a02  test    eax, eax
0x180049a04  jnz     loc_180049BBA
0x180049a0a  mov     rcx, [rbp+hKey]; hKey
0x180049a0e  lea     rax, [rbp+cbData]
0x180049a12  mov     qword ptr [rsp+60h+samDesired], rax; lpcbData
0x180049a17  lea     r12, aUserpinnedshar; "UserPinnedShareCount"
0x180049a1e  lea     rax, [rbp+Data]
0x180049a22  xor     r8d, r8d; lpReserved
0x180049a25  lea     r9, [rbp+Type]; lpType
0x180049a29  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x180049a2e  mov     rdx, r12; lpValueName
0x180049a31  call    cs:__imp_RegQueryValueExW
0x180049a37  lea     rdi, WPP_GLOBAL_Control
0x180049a3e  cmp     eax, 2
0x180049a41  jnz     short loc_180049A7B
0x180049a43  xor     edx, edx
0x180049a45  mov     [rbp+Data], edx
0x180049a48  mov     r10, cs:WPP_GLOBAL_Control
0x180049a4f  cmp     r10, rdi
0x180049a52  jz      loc_180049B1C
0x180049a58  test    byte ptr [r10+1Ch], 20h
0x180049a5d  jz      loc_180049AE8
0x180049a63  mov     rcx, [r10+10h]
0x180049a67  lea     edx, [rax+12h]
0x180049a6a  mov     r9, r12
0x180049a6d  lea     r8, WPP_65174b6254cf30406df57586ff17ec03_Traceguids
0x180049a74  call    WPP_SF_S
0x180049a79  jmp     short loc_180049ADE
0x180049a7b  test    eax, eax
0x180049a7d  jz      short loc_180049AA2
0x180049a7f  xor     edx, edx
0x180049a81  mov     [rbp+Data], edx
0x180049a84  mov     r10, cs:WPP_GLOBAL_Control
0x180049a8b  cmp     r10, rdi
0x180049a8e  jz      loc_180049B1C
0x180049a94  test    byte ptr [r10+1Ch], 20h
0x180049a99  jz      short loc_180049AE8
0x180049a9b  mov     edx, 15h
0x180049aa0  jmp     short loc_180049AC7
0x180049aa2  mov     eax, [rbp+Type]
0x180049aa5  cmp     eax, 4
0x180049aa8  jz      short loc_180049ADE
0x180049aaa  xor     edx, edx
0x180049aac  mov     [rbp+Data], edx
0x180049aaf  mov     r10, cs:WPP_GLOBAL_Control
0x180049ab6  cmp     r10, rdi
0x180049ab9  jz      short loc_180049B1C
0x180049abb  test    byte ptr [r10+1Ch], 20h
0x180049ac0  jz      short loc_180049AE8
0x180049ac2  mov     edx, 16h
0x180049ac7  mov     rcx, [r10+10h]
0x180049acb  lea     r8, WPP_65174b6254cf30406df57586ff17ec03_Traceguids
0x180049ad2  mov     r9, r12
0x180049ad5  mov     [rsp+60h+dwOptions], eax
0x180049ad9  call    WPP_SF_Sd
0x180049ade  mov     r10, cs:WPP_GLOBAL_Control
0x180049ae5  mov     edx, [rbp+Data]
0x180049ae8  cmp     r10, rdi
0x180049aeb  jz      short loc_180049B1C
0x180049aed  test    byte ptr [r10+1Ch], 20h
0x180049af2  jz      short loc_180049B1C
0x180049af4  mov     eax, r14d
0x180049af7  neg     eax
0x180049af9  sbb     cl, cl
0x180049afb  and     cl, 0Bh
0x180049afe  add     cl, 4Eh ; 'N'
0x180049b01  mov     byte ptr [rsp+60h+samDesired], cl
0x180049b05  mov     rcx, [r10+10h]
0x180049b09  mov     [rsp+60h+dwOptions], edx
0x180049b0d  call    WPP_SF_Sdc
0x180049b12  mov     edx, [rbp+Data]
0x180049b15  mov     r10, cs:WPP_GLOBAL_Control
0x180049b1c  test    r14d, r14d
0x180049b1f  jz      short loc_180049B2A
0x180049b21  cmp     edx, 0FFFFFFFFh
0x180049b24  jnb     short loc_180049B35
0x180049b26  inc     edx
0x180049b28  jmp     short loc_180049B30
0x180049b2a  test    edx, edx
0x180049b2c  jz      short loc_180049B35
0x180049b2e  dec     edx
0x180049b30  mov     [rbp+Data], edx
0x180049b33  jmp     short loc_180049B56
0x180049b35  cmp     r10, rdi
0x180049b38  jz      short loc_180049B56
0x180049b3a  test    byte ptr [r10+1Ch], 20h
0x180049b3f  jz      short loc_180049B56
0x180049b41  mov     rcx, [r10+10h]
0x180049b45  lea     r8, WPP_65174b6254cf30406df57586ff17ec03_Traceguids
0x180049b4c  mov     edx, 18h
0x180049b51  call    WPP_SF_
0x180049b56  mov     eax, [rbp+cbData]
0x180049b59  mov     r9d, 4; dwType
0x180049b5f  mov     rcx, [rbp+hKey]; hKey
0x180049b63  xor     r8d, r8d; Reserved
0x180049b66  mov     [rsp+60h+samDesired], eax; cbData
0x180049b6a  mov     rdx, r12; lpValueName
0x180049b6d  lea     rax, [rbp+Data]
0x180049b71  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x180049b76  call    cs:__imp_RegSetValueExW
0x180049b7c  test    eax, eax
0x180049b7e  jz      short loc_180049BAE
0x180049b80  mov     rcx, cs:WPP_GLOBAL_Control
0x180049b87  cmp     rcx, rdi
0x180049b8a  jz      short loc_180049BAE
0x180049b8c  test    byte ptr [rcx+1Ch], 20h
0x180049b90  jz      short loc_180049BAE
0x180049b92  mov     rcx, [rcx+10h]
0x180049b96  lea     r8, WPP_65174b6254cf30406df57586ff17ec03_Traceguids
0x180049b9d  mov     edx, 19h
0x180049ba2  mov     [rsp+60h+dwOptions], eax
0x180049ba6  mov     r9, r12
0x180049ba9  call    WPP_SF_Sd
0x180049bae  mov     rcx, [rbp+hKey]; hKey
0x180049bb2  call    cs:__imp_RegCloseKey
0x180049bb8  jmp     short loc_180049BF3
0x180049bba  mov     rcx, cs:WPP_GLOBAL_Control
0x180049bc1  lea     rdi, WPP_GLOBAL_Control
0x180049bc8  cmp     rcx, rdi
0x180049bcb  jz      short loc_180049BF3
0x180049bcd  test    byte ptr [rcx+1Ch], 20h
0x180049bd1  jz      short loc_180049BF3
0x180049bd3  mov     rcx, [rcx+10h]
0x180049bd7  lea     r9, aSoftwareMicros_1; "Software\\Microsoft\\UserData\\OfflineF"...
0x180049bde  mov     edx, 1Ah
0x180049be3  mov     [rsp+60h+dwOptions], eax
0x180049be7  lea     r8, WPP_65174b6254cf30406df57586ff17ec03_Traceguids
0x180049bee  call    WPP_SF_Sd
0x180049bf3  mov     rcx, [rbp+phkResult]; hKey
0x180049bf7  call    cs:__imp_RegCloseKey
0x180049bfd  jmp     short loc_180049C30
0x180049bff  mov     rcx, cs:WPP_GLOBAL_Control
0x180049c06  lea     rdi, WPP_GLOBAL_Control
0x180049c0d  cmp     rcx, rdi
0x180049c10  jz      short loc_180049C30
0x180049c12  test    byte ptr [rcx+1Ch], 20h
0x180049c16  jz      short loc_180049C30
0x180049c18  mov     rcx, [rcx+10h]
0x180049c1c  lea     r8, WPP_65174b6254cf30406df57586ff17ec03_Traceguids
0x180049c23  mov     edx, 1Bh
0x180049c28  mov     r9d, eax
0x180049c2b  call    WPP_SF_d
0x180049c30  mov     rdi, [rsp+60h+arg_0]
0x180049c38  add     rsp, 60h
0x180049c3c  pop     r14
0x180049c3e  pop     r12
0x180049c40  pop     rbp
0x180049c41  retn
```
