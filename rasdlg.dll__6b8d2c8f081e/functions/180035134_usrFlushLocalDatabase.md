# usrFlushLocalDatabase

- ea: `0x180035134`
- end: `0x180035351`
- name: `usrFlushLocalDatabase`
- size: `541`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002eaf0`
- `0x18002f0dc`

## callees

- `0x1800336a0`
- `0x1800337d4`
- `0x180033d3c`
- `0x180033fb8`
- `0x180034ea0`
- `0x180035134`
- `0x18003d08c`
- `0x18003d248`

## import_xrefs

- `MPRAPI!MprAdminUserOpen` at `0x1800351de`
- `MPRAPI!MprAdminUserOpen` at `0x1800351de`
- `MPRAPI!MprAdminUserWriteProfFlags` at `0x180035289`
- `MPRAPI!MprAdminUserWriteProfFlags` at `0x180035289`

## string_xrefs

- `0x1800352df`: `UsersConfiguredWithMMC`
- `0x180035270`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Parameters`

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
0x180035134  push    rbx
0x180035136  push    rbp
0x180035137  push    rsi
0x180035138  push    rdi
0x180035139  push    r12
0x18003513b  push    r13
0x18003513d  push    r14
0x18003513f  push    r15
0x180035141  sub     rsp, 38h
0x180035145  xor     edi, edi
0x180035147  mov     rsi, rcx
0x18003514a  test    rcx, rcx
0x18003514d  jz      loc_18003533B
0x180035153  mov     r12d, [rcx+8]
0x180035157  mov     r14d, edi
0x18003515a  mov     r15d, edi
0x18003515d  test    r12d, r12d
0x180035160  jz      loc_180035269
0x180035166  mov     rax, [rsi+28h]
0x18003516a  mov     r13d, r15d
0x18003516d  mov     rbp, [rax+r13*8]
0x180035171  mov     al, [rbp+31Dh]
0x180035177  test    al, al
0x180035179  jz      loc_18003525D
0x18003517f  test    al, 8
0x180035181  jz      short loc_1800351E8
0x180035183  lea     rdi, [rbp+18h]
0x180035187  mov     edx, 200h; cbDataIn
0x18003518c  mov     rcx, rdi; pDataIn
0x18003518f  call    DecryptMemoryInPlace
0x180035194  mov     rcx, [rbp+8]; username
0x180035198  lea     r8, WideCharStr
0x18003519f  xor     eax, eax
0x1800351a1  lea     rdx, WideCharStr
0x1800351a8  cmp     ax, [rdi]
0x1800351ab  cmovnz  r8, rdi
0x1800351af  cmp     [rbp+10h], rax
0x1800351b3  cmovnz  rdx, [rbp+10h]
0x1800351b8  call    RasSrvAddUser
0x1800351bd  mov     edx, 200h; cbDataIn
0x1800351c2  mov     rcx, rdi; pDataIn
0x1800351c5  mov     ebx, eax
0x1800351c7  call    EncryptMemoryInPlace
0x1800351cc  mov     rdx, [rbp+8]
0x1800351d0  xor     edi, edi
0x1800351d2  mov     rcx, [rsi]
0x1800351d5  test    ebx, ebx
0x1800351d7  mov     r8, rbp
0x1800351da  cmovnz  r14d, ebx
0x1800351de  call    cs:__imp_MprAdminUserOpen
0x1800351e4  test    eax, eax
0x1800351e6  jnz     short loc_18003525D
0x1800351e8  test    byte ptr [rbp+31Dh], 1
0x1800351ef  jz      short loc_180035204
0x1800351f1  mov     rcx, [rsi+28h]
0x1800351f5  mov     rcx, [rcx+r13*8]
0x1800351f9  call    usrCommitRasProps
0x1800351fe  test    eax, eax
0x180035200  cmovnz  r14d, eax
0x180035204  test    byte ptr [rbp+31Dh], 6
0x18003520b  jz      short loc_180035256
0x18003520d  lea     rbx, [rbp+18h]
0x180035211  mov     r13d, 200h
0x180035217  mov     edx, r13d; cbDataIn
0x18003521a  mov     rcx, rbx; pDataIn
0x18003521d  call    DecryptMemoryInPlace
0x180035222  mov     cl, [rbp+31Dh]
0x180035228  mov     al, cl
0x18003522a  and     al, 4
0x18003522c  neg     al
0x18003522e  sbb     r8, r8
0x180035231  and     r8, rbx
0x180035234  test    cl, 2
0x180035237  jz      short loc_18003523F
0x180035239  mov     rdx, [rbp+10h]
0x18003523d  jmp     short loc_180035242
0x18003523f  mov     rdx, rdi
0x180035242  mov     rcx, [rbp+8]; username
0x180035246  call    RasSrvEditUser
0x18003524b  mov     edx, r13d; cbDataIn
0x18003524e  mov     rcx, rbx; pDataIn
0x180035251  call    EncryptMemoryInPlace
0x180035256  mov     [rbp+31Dh], dil
0x18003525d  inc     r15d
0x180035260  cmp     r15d, r12d
0x180035263  jb      loc_180035166
0x180035269  lea     r15, pszregServerFlags; "ServerFlags"
0x180035270  lea     rbp, pszregRasParameters; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x180035277  cmp     [rsi+1Ch], edi
0x18003527a  jz      short loc_1800352DC
0x18003527c  mov     ebx, [rsi+10h]
0x18003527f  mov     edx, edi
0x180035281  mov     rcx, [rsi]
0x180035284  test    ebx, ebx
0x180035286  setnz   dl
0x180035289  call    cs:__imp_MprAdminUserWriteProfFlags
0x18003528f  mov     r9, r15
0x180035292  mov     [rsp+78h+arg_0], edi
0x180035299  mov     r8, rbp
0x18003529c  lea     rcx, [rsp+78h+arg_0]
0x1800352a4  xor     edx, edx
0x1800352a6  call    RassrvRegGetDwEx
0x1800352ab  mov     ecx, [rsp+78h+arg_0]
0x1800352b2  test    ebx, ebx
0x1800352b4  jz      short loc_1800352C2
0x1800352b6  and     ecx, 0FFFC7FFFh
0x1800352bc  bts     ecx, 17h
0x1800352c0  jmp     short loc_1800352CE
0x1800352c2  and     ecx, 0FFFD7FFFh
0x1800352c8  or      ecx, 810000h
0x1800352ce  xor     r9d, r9d
0x1800352d1  mov     r8, r15
0x1800352d4  mov     rdx, rbp
0x1800352d7  call    RassrvRegSetDwEx
0x1800352dc  cmp     [rsi+18h], edi
0x1800352df  lea     r8, pszregPure; "UsersConfiguredWithMMC"
0x1800352e6  mov     ecx, edi
0x1800352e8  mov     rdx, rbp
0x1800352eb  setz    cl
0x1800352ee  xor     r9d, r9d
0x1800352f1  call    RassrvRegSetDwEx
0x1800352f6  mov     r9, r15
0x1800352f9  mov     [rsp+78h+arg_0], edi
0x180035300  mov     r8, rbp
0x180035303  lea     rcx, [rsp+78h+arg_0]
0x18003530b  xor     edx, edx
0x18003530d  call    RassrvRegGetDwEx
0x180035312  mov     ecx, [rsp+78h+arg_0]
0x180035319  cmp     [rsi+14h], edi
0x18003531c  jz      short loc_180035324
0x18003531e  bts     ecx, 16h
0x180035322  jmp     short loc_180035328
0x180035324  btr     ecx, 16h
0x180035328  xor     r9d, r9d
0x18003532b  mov     r8, r15
0x18003532e  mov     rdx, rbp
0x180035331  call    RassrvRegSetDwEx
0x180035336  mov     eax, r14d
0x180035339  jmp     short loc_180035340
0x18003533b  mov     eax, 57h ; 'W'
0x180035340  add     rsp, 38h
0x180035344  pop     r15
0x180035346  pop     r14
0x180035348  pop     r13
0x18003534a  pop     r12
0x18003534c  pop     rdi
0x18003534d  pop     rsi
0x18003534e  pop     rbp
0x18003534f  pop     rbx
0x180035350  retn
```
