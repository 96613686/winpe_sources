# NatStartServiceSync(ushort const *,ulong,ulong)

- ea: `0x18003c63c`
- end: `0x18003c8cc`
- name: `?NatStartServiceSync@@YAJPEBGKK@Z`
- size: `656`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180073a7c`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x18003c63c`
- `0x18003c8d4`
- `0x18003ca48`
- `0x180051f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c71d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c82d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c71d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c82d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003c7d3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003c7d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003c6af`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003c7b0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003c6af`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003c7b0`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18003c70d`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18003c70d`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18003c78e`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18003c78e`

## pseudocode

```c
__int64 __fastcall NatStartServiceSync(LPCWSTR lpServiceName)
{
  DWORD TickCount; // esi
  unsigned int v3; // edx
  int v4; // eax
  signed int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  int v9; // edi
  signed int LastError; // eax
  unsigned int v11; // eax
  DWORD v12; // ecx
  signed int v13; // eax
  SC_HANDLE hService; // [rsp+20h] [rbp-68h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+28h] [rbp-60h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 184, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids);
  }
  hService = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  TickCount = GetTickCount();
  v4 = NatOpenService(lpServiceName, v3, &hService);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v9 = 0;
    if ( StartServiceW(hService, 0, 0) )
      goto LABEL_21;
    LastError = GetLastError();
    if ( LastError != 1056 )
    {
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      else
        v5 = LastError;
      if ( v5 >= 0 )
        goto LABEL_46;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_46;
      }
      v7 = 186;
LABEL_44:
      v8 = (unsigned int)v5;
      goto LABEL_45;
    }
LABEL_20:
    v9 = 1;
LABEL_21:
    while ( !v9 )
    {
      if ( !QueryServiceStatus(hService, &ServiceStatus) )
      {
        v13 = GetLastError();
        v5 = v13;
        if ( v13 > 0 )
          v5 = (unsigned __int16)v13 | 0x80070000;
        if ( v5 < 0 )
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v7 = 187;
            goto LABEL_44;
          }
        }
        break;
      }
      if ( ServiceStatus.dwCurrentState == 4 )
        goto LABEL_20;
      if ( ServiceStatus.dwCurrentState != 2 )
      {
        v5 = -2147023834;
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v7 = 189;
          goto LABEL_44;
        }
        break;
      }
      v11 = GetTickCount() - TickCount;
      if ( v11 >= 0x3A98 )
      {
        v5 = -2147024638;
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v7 = 188;
          goto LABEL_44;
        }
        break;
      }
      v12 = 50;
      if ( 15000 - v11 < 0x32 )
        v12 = 15000 - v11;
      Sleep(v12);
    }
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = 185;
      v8 = (unsigned int)v4;
LABEL_45:
      WPP_SF_d(v6[2], v7, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, v8);
    }
  }
LABEL_46:
  NatCloseServiceHandle(hService);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      190,
      &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids,
      (unsigned int)v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003c63c  push    rbx
0x18003c63e  push    rsi
0x18003c63f  push    rdi
0x18003c640  push    r12
0x18003c642  push    r14
0x18003c644  push    r15
0x18003c646  sub     rsp, 58h
0x18003c64a  mov     rax, cs:__security_cookie
0x18003c651  xor     rax, rsp
0x18003c654  mov     [rsp+88h+var_40], rax
0x18003c659  mov     rbx, rcx
0x18003c65c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c663  lea     r15, WPP_GLOBAL_Control
0x18003c66a  lea     r12, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18003c671  mov     r14d, 200h
0x18003c677  cmp     rcx, r15
0x18003c67a  jz      short loc_18003C699
0x18003c67c  test    [rcx+1Ch], r14d
0x18003c680  jz      short loc_18003C699
0x18003c682  cmp     byte ptr [rcx+19h], 6
0x18003c686  jb      short loc_18003C699
0x18003c688  mov     rcx, [rcx+10h]
0x18003c68c  mov     edx, 0B8h
0x18003c691  mov     r8, r12
0x18003c694  call    WPP_SF_
0x18003c699  xorps   xmm0, xmm0
0x18003c69c  mov     [rsp+88h+hService], 0
0x18003c6a5  movups  xmmword ptr [rsp+88h+ServiceStatus.dwServiceType], xmm0
0x18003c6aa  movups  xmmword ptr [rsp+88h+ServiceStatus.dwWin32ExitCode], xmm0
0x18003c6af  call    cs:__imp_GetTickCount
0x18003c6b6  nop     dword ptr [rax+rax+00h]
0x18003c6bb  lea     r8, [rsp+88h+hService]; struct SC_HANDLE__ **
0x18003c6c0  mov     rcx, rbx; lpServiceName
0x18003c6c3  mov     esi, eax
0x18003c6c5  call    ?NatOpenService@@YAJPEBGKPEAPEAUSC_HANDLE__@@@Z; NatOpenService(ushort const *,ulong,SC_HANDLE__ * *)
0x18003c6ca  mov     ebx, eax
0x18003c6cc  test    eax, eax
0x18003c6ce  jns     short loc_18003C701
0x18003c6d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c6d7  cmp     rcx, r15
0x18003c6da  jz      loc_18003C878
0x18003c6e0  test    [rcx+1Ch], r14d
0x18003c6e4  jz      loc_18003C878
0x18003c6ea  cmp     byte ptr [rcx+19h], 2
0x18003c6ee  jb      loc_18003C878
0x18003c6f4  mov     edx, 0B9h
0x18003c6f9  mov     r9d, eax
0x18003c6fc  jmp     loc_18003C86C
0x18003c701  mov     rcx, [rsp+88h+hService]; hService
0x18003c706  xor     r8d, r8d; lpServiceArgVectors
0x18003c709  xor     edx, edx; dwNumServiceArgs
0x18003c70b  xor     edi, edi
0x18003c70d  call    cs:__imp_StartServiceW
0x18003c714  nop     dword ptr [rax+rax+00h]
0x18003c719  test    eax, eax
0x18003c71b  jnz     short loc_18003C77C
0x18003c71d  call    cs:__imp_GetLastError
0x18003c724  nop     dword ptr [rax+rax+00h]
0x18003c729  cmp     eax, 420h
0x18003c72e  jz      short loc_18003C777
0x18003c730  test    eax, eax
0x18003c732  jg      short loc_18003C738
0x18003c734  mov     ebx, eax
0x18003c736  jmp     short loc_18003C741
0x18003c738  movzx   ebx, ax
0x18003c73b  or      ebx, 80070000h
0x18003c741  test    ebx, ebx
0x18003c743  jns     loc_18003C878
0x18003c749  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c750  cmp     rcx, r15
0x18003c753  jz      loc_18003C878
0x18003c759  test    [rcx+1Ch], r14d
0x18003c75d  jz      loc_18003C878
0x18003c763  cmp     byte ptr [rcx+19h], 2
0x18003c767  jb      loc_18003C878
0x18003c76d  mov     edx, 0BAh
0x18003c772  jmp     loc_18003C869
0x18003c777  mov     edi, 1
0x18003c77c  test    edi, edi
0x18003c77e  jnz     loc_18003C878
0x18003c784  mov     rcx, [rsp+88h+hService]; hService
0x18003c789  lea     rdx, [rsp+88h+ServiceStatus]; lpServiceStatus
0x18003c78e  call    cs:__imp_QueryServiceStatus
0x18003c795  nop     dword ptr [rax+rax+00h]
0x18003c79a  test    eax, eax
0x18003c79c  jz      loc_18003C82D
0x18003c7a2  cmp     [rsp+88h+ServiceStatus.dwCurrentState], 4
0x18003c7a7  jz      short loc_18003C777
0x18003c7a9  cmp     [rsp+88h+ServiceStatus.dwCurrentState], 2
0x18003c7ae  jnz     short loc_18003C809
0x18003c7b0  call    cs:__imp_GetTickCount
0x18003c7b7  nop     dword ptr [rax+rax+00h]
0x18003c7bc  sub     eax, esi
0x18003c7be  mov     ecx, 3A98h
0x18003c7c3  cmp     eax, ecx
0x18003c7c5  jnb     short loc_18003C7E1
0x18003c7c7  mov     edx, ecx
0x18003c7c9  lea     ecx, [rdi+32h]
0x18003c7cc  sub     edx, eax
0x18003c7ce  cmp     edx, ecx
0x18003c7d0  cmovb   ecx, edx; dwMilliseconds
0x18003c7d3  call    cs:__imp_Sleep
0x18003c7da  nop     dword ptr [rax+rax+00h]
0x18003c7df  jmp     short loc_18003C77C
0x18003c7e1  mov     ebx, 80070102h
0x18003c7e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c7ed  cmp     rcx, r15
0x18003c7f0  jz      loc_18003C878
0x18003c7f6  test    [rcx+1Ch], r14d
0x18003c7fa  jz      short loc_18003C878
0x18003c7fc  cmp     byte ptr [rcx+19h], 2
0x18003c800  jb      short loc_18003C878
0x18003c802  mov     edx, 0BCh
0x18003c807  jmp     short loc_18003C869
0x18003c809  mov     ebx, 80070426h
0x18003c80e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c815  cmp     rcx, r15
0x18003c818  jz      short loc_18003C878
0x18003c81a  test    [rcx+1Ch], r14d
0x18003c81e  jz      short loc_18003C878
0x18003c820  cmp     byte ptr [rcx+19h], 2
0x18003c824  jb      short loc_18003C878
0x18003c826  mov     edx, 0BDh
0x18003c82b  jmp     short loc_18003C869
0x18003c82d  call    cs:__imp_GetLastError
0x18003c834  nop     dword ptr [rax+rax+00h]
0x18003c839  mov     ebx, eax
0x18003c83b  test    eax, eax
0x18003c83d  jle     short loc_18003C848
0x18003c83f  movzx   ebx, ax
0x18003c842  or      ebx, 80070000h
0x18003c848  test    ebx, ebx
0x18003c84a  jns     short loc_18003C878
0x18003c84c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c853  cmp     rcx, r15
0x18003c856  jz      short loc_18003C878
0x18003c858  test    [rcx+1Ch], r14d
0x18003c85c  jz      short loc_18003C878
0x18003c85e  cmp     byte ptr [rcx+19h], 2
0x18003c862  jb      short loc_18003C878
0x18003c864  mov     edx, 0BBh
0x18003c869  mov     r9d, ebx
0x18003c86c  mov     rcx, [rcx+10h]
0x18003c870  mov     r8, r12
0x18003c873  call    WPP_SF_d
0x18003c878  mov     rcx, [rsp+88h+hService]; hSCObject
0x18003c87d  call    ?NatCloseServiceHandle@@YAXPEAUSC_HANDLE__@@@Z; NatCloseServiceHandle(SC_HANDLE__ *)
0x18003c882  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c889  cmp     rcx, r15
0x18003c88c  jz      short loc_18003C8AE
0x18003c88e  test    [rcx+1Ch], r14d
0x18003c892  jz      short loc_18003C8AE
0x18003c894  cmp     byte ptr [rcx+19h], 6
0x18003c898  jb      short loc_18003C8AE
0x18003c89a  mov     rcx, [rcx+10h]
0x18003c89e  mov     edx, 0BEh
0x18003c8a3  mov     r9d, ebx
0x18003c8a6  mov     r8, r12
0x18003c8a9  call    WPP_SF_d
0x18003c8ae  mov     eax, ebx
0x18003c8b0  mov     rcx, [rsp+88h+var_40]
0x18003c8b5  xor     rcx, rsp; StackCookie
0x18003c8b8  call    __security_check_cookie
0x18003c8bd  add     rsp, 58h
0x18003c8c1  pop     r15
0x18003c8c3  pop     r14
0x18003c8c5  pop     r12
0x18003c8c7  pop     rdi
0x18003c8c8  pop     rsi
0x18003c8c9  pop     rbx
0x18003c8ca  retn
```
