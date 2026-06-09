# usrFlushLocalDatabase

- ea: `0x180026f44`
- end: `0x180027161`
- name: `usrFlushLocalDatabase`
- size: `541`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180020670`
- `0x180020c48`

## callees

- `0x18002108c`
- `0x1800211c0`
- `0x180021720`
- `0x180021994`
- `0x180026cb0`
- `0x180026f44`
- `0x18002bd70`
- `0x18002bf2c`

## import_xrefs

- `MPRAPI!MprAdminUserOpen` at `0x180026fee`
- `MPRAPI!MprAdminUserOpen` at `0x180026fee`
- `MPRAPI!MprAdminUserWriteProfFlags` at `0x180027099`
- `MPRAPI!MprAdminUserWriteProfFlags` at `0x180027099`

## string_xrefs

- `0x1800270ef`: `UsersConfiguredWithMMC`
- `0x180027080`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Parameters`

## pseudocode

```c
__int64 __fastcall usrFlushLocalDatabase(__int64 a1)
{
  unsigned int v2; // r12d
  unsigned int v3; // r14d
  unsigned int i; // r15d
  __int64 v5; // rbp
  char v6; // al
  unsigned int v7; // ebx
  unsigned int v8; // eax
  int v9; // ebx
  unsigned int v10; // ecx
  int v11; // ecx
  int v13; // [rsp+80h] [rbp+8h] BYREF

  if ( !a1 )
    return 87;
  v2 = *(_DWORD *)(a1 + 8);
  v3 = 0;
  for ( i = 0; i < v2; ++i )
  {
    v5 = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 8LL * i);
    v6 = *(_BYTE *)(v5 + 797);
    if ( v6 )
    {
      if ( (v6 & 8) == 0 )
        goto LABEL_10;
      DecryptMemoryInPlace((LPVOID)(v5 + 24), 0x200u);
      v7 = RasSrvAddUser(*(LPCWSTR *)(v5 + 8));
      EncryptMemoryInPlace((LPVOID)(v5 + 24), 0x200u);
      if ( v7 )
        v3 = v7;
      if ( !(unsigned int)MprAdminUserOpen(*(_QWORD *)a1, *(_QWORD *)(v5 + 8), v5) )
      {
LABEL_10:
        if ( (*(_BYTE *)(v5 + 797) & 1) != 0 )
        {
          v8 = usrCommitRasProps(*(_QWORD *)(*(_QWORD *)(a1 + 40) + 8LL * i));
          if ( v8 )
            v3 = v8;
        }
        if ( (*(_BYTE *)(v5 + 797) & 6) != 0 )
        {
          DecryptMemoryInPlace((LPVOID)(v5 + 24), 0x200u);
          RasSrvEditUser(*(LPCWSTR *)(v5 + 8));
          EncryptMemoryInPlace((LPVOID)(v5 + 24), 0x200u);
        }
        *(_BYTE *)(v5 + 797) = 0;
      }
    }
  }
  if ( *(_DWORD *)(a1 + 28) )
  {
    v9 = *(_DWORD *)(a1 + 16);
    MprAdminUserWriteProfFlags(*(_QWORD *)a1, v9 != 0);
    v13 = 0;
    RassrvRegGetDwEx(&v13, 0, L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Parameters", L"ServerFlags");
    if ( v9 )
      v10 = v13 & 0xFF7C7FFF | 0x800000;
    else
      v10 = v13 & 0xFF7C7FFF | 0x810000;
    RassrvRegSetDwEx(v10, L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Parameters", L"ServerFlags", 0);
  }
  RassrvRegSetDwEx(
    *(_DWORD *)(a1 + 24) == 0,
    L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Parameters",
    L"UsersConfiguredWithMMC",
    0);
  v13 = 0;
  RassrvRegGetDwEx(&v13, 0, L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Parameters", L"ServerFlags");
  if ( *(_DWORD *)(a1 + 20) )
    v11 = v13 | 0x400000;
  else
    v11 = v13 & 0xFFBFFFFF;
  RassrvRegSetDwEx(v11, L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Parameters", L"ServerFlags", 0);
  return v3;
}

```

## disassembly

```asm
0x180026f44  push    rbx
0x180026f46  push    rbp
0x180026f47  push    rsi
0x180026f48  push    rdi
0x180026f49  push    r12
0x180026f4b  push    r13
0x180026f4d  push    r14
0x180026f4f  push    r15
0x180026f51  sub     rsp, 38h
0x180026f55  xor     edi, edi
0x180026f57  mov     rsi, rcx
0x180026f5a  test    rcx, rcx
0x180026f5d  jz      loc_18002714B
0x180026f63  mov     r12d, [rcx+8]
0x180026f67  mov     r14d, edi
0x180026f6a  mov     r15d, edi
0x180026f6d  test    r12d, r12d
0x180026f70  jz      loc_180027079
0x180026f76  mov     rax, [rsi+28h]
0x180026f7a  mov     r13d, r15d
0x180026f7d  mov     rbp, [rax+r13*8]
0x180026f81  mov     al, [rbp+31Dh]
0x180026f87  test    al, al
0x180026f89  jz      loc_18002706D
0x180026f8f  test    al, 8
0x180026f91  jz      short loc_180026FF8
0x180026f93  lea     rdi, [rbp+18h]
0x180026f97  mov     edx, 200h; cbDataIn
0x180026f9c  mov     rcx, rdi; pDataIn
0x180026f9f  call    DecryptMemoryInPlace
0x180026fa4  mov     rcx, [rbp+8]; username
0x180026fa8  lea     r8, cchOriginalDestLength
0x180026faf  xor     eax, eax
0x180026fb1  lea     rdx, cchOriginalDestLength
0x180026fb8  cmp     ax, [rdi]
0x180026fbb  cmovnz  r8, rdi
0x180026fbf  cmp     [rbp+10h], rax
0x180026fc3  cmovnz  rdx, [rbp+10h]
0x180026fc8  call    RasSrvAddUser
0x180026fcd  mov     edx, 200h; cbDataIn
0x180026fd2  mov     rcx, rdi; pDataIn
0x180026fd5  mov     ebx, eax
0x180026fd7  call    EncryptMemoryInPlace
0x180026fdc  mov     rdx, [rbp+8]
0x180026fe0  xor     edi, edi
0x180026fe2  mov     rcx, [rsi]
0x180026fe5  test    ebx, ebx
0x180026fe7  mov     r8, rbp
0x180026fea  cmovnz  r14d, ebx
0x180026fee  call    cs:__imp_MprAdminUserOpen
0x180026ff4  test    eax, eax
0x180026ff6  jnz     short loc_18002706D
0x180026ff8  test    byte ptr [rbp+31Dh], 1
0x180026fff  jz      short loc_180027014
0x180027001  mov     rcx, [rsi+28h]
0x180027005  mov     rcx, [rcx+r13*8]
0x180027009  call    usrCommitRasProps
0x18002700e  test    eax, eax
0x180027010  cmovnz  r14d, eax
0x180027014  test    byte ptr [rbp+31Dh], 6
0x18002701b  jz      short loc_180027066
0x18002701d  lea     rbx, [rbp+18h]
0x180027021  mov     r13d, 200h
0x180027027  mov     edx, r13d; cbDataIn
0x18002702a  mov     rcx, rbx; pDataIn
0x18002702d  call    DecryptMemoryInPlace
0x180027032  mov     cl, [rbp+31Dh]
0x180027038  mov     al, cl
0x18002703a  and     al, 4
0x18002703c  neg     al
0x18002703e  sbb     r8, r8
0x180027041  and     r8, rbx
0x180027044  test    cl, 2
0x180027047  jz      short loc_18002704F
0x180027049  mov     rdx, [rbp+10h]
0x18002704d  jmp     short loc_180027052
0x18002704f  mov     rdx, rdi
0x180027052  mov     rcx, [rbp+8]; username
0x180027056  call    RasSrvEditUser
0x18002705b  mov     edx, r13d; cbDataIn
0x18002705e  mov     rcx, rbx; pDataIn
0x180027061  call    EncryptMemoryInPlace
0x180027066  mov     [rbp+31Dh], dil
0x18002706d  inc     r15d
0x180027070  cmp     r15d, r12d
0x180027073  jb      loc_180026F76
0x180027079  lea     r15, pszregServerFlags; "ServerFlags"
0x180027080  lea     rbp, pszregRasParameters; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x180027087  cmp     [rsi+1Ch], edi
0x18002708a  jz      short loc_1800270EC
0x18002708c  mov     ebx, [rsi+10h]
0x18002708f  mov     edx, edi
0x180027091  mov     rcx, [rsi]
0x180027094  test    ebx, ebx
0x180027096  setnz   dl
0x180027099  call    cs:__imp_MprAdminUserWriteProfFlags
0x18002709f  mov     r9, r15
0x1800270a2  mov     [rsp+78h+arg_0], edi
0x1800270a9  mov     r8, rbp
0x1800270ac  lea     rcx, [rsp+78h+arg_0]
0x1800270b4  xor     edx, edx
0x1800270b6  call    RassrvRegGetDwEx
0x1800270bb  mov     ecx, [rsp+78h+arg_0]
0x1800270c2  test    ebx, ebx
0x1800270c4  jz      short loc_1800270D2
0x1800270c6  and     ecx, 0FFFC7FFFh
0x1800270cc  bts     ecx, 17h
0x1800270d0  jmp     short loc_1800270DE
0x1800270d2  and     ecx, 0FFFD7FFFh
0x1800270d8  or      ecx, 810000h
0x1800270de  xor     r9d, r9d
0x1800270e1  mov     r8, r15
0x1800270e4  mov     rdx, rbp
0x1800270e7  call    RassrvRegSetDwEx
0x1800270ec  cmp     [rsi+18h], edi
0x1800270ef  lea     r8, pszregPure; "UsersConfiguredWithMMC"
0x1800270f6  mov     ecx, edi
0x1800270f8  mov     rdx, rbp
0x1800270fb  setz    cl
0x1800270fe  xor     r9d, r9d
0x180027101  call    RassrvRegSetDwEx
0x180027106  mov     r9, r15
0x180027109  mov     [rsp+78h+arg_0], edi
0x180027110  mov     r8, rbp
0x180027113  lea     rcx, [rsp+78h+arg_0]
0x18002711b  xor     edx, edx
0x18002711d  call    RassrvRegGetDwEx
0x180027122  mov     ecx, [rsp+78h+arg_0]
0x180027129  cmp     [rsi+14h], edi
0x18002712c  jz      short loc_180027134
0x18002712e  bts     ecx, 16h
0x180027132  jmp     short loc_180027138
0x180027134  btr     ecx, 16h
0x180027138  xor     r9d, r9d
0x18002713b  mov     r8, r15
0x18002713e  mov     rdx, rbp
0x180027141  call    RassrvRegSetDwEx
0x180027146  mov     eax, r14d
0x180027149  jmp     short loc_180027150
0x18002714b  mov     eax, 57h ; 'W'
0x180027150  add     rsp, 38h
0x180027154  pop     r15
0x180027156  pop     r14
0x180027158  pop     r13
0x18002715a  pop     r12
0x18002715c  pop     rdi
0x18002715d  pop     rsi
0x18002715e  pop     rbp
0x18002715f  pop     rbx
0x180027160  retn
```
