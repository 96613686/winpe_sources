# AdapGetComputerObjectPath(ushort * *,bool)

- ea: `0x1800e9b4c`
- end: `0x1800e9e7b`
- name: `?AdapGetComputerObjectPath@@YAJPEAPEAG_N@Z`
- size: `815`
- prototype: `__int64 __fastcall(unsigned __int16 **, unsigned __int8)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x1800ea16c`

## callees

- `0x1800090c0`
- `0x180023800`
- `0x1800600c0`
- `0x1800cdfac`
- `0x1800e9b4c`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800e9e58`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800e9e58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e9c63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e9df7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e9c63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e9df7`
- `ext-ms-win-secur32-translatename-l1-1-0!GetComputerObjectNameW` at `0x1800e9c53`
- `ext-ms-win-secur32-translatename-l1-1-0!GetComputerObjectNameW` at `0x1800e9de7`
- `ext-ms-win-secur32-translatename-l1-1-0!GetComputerObjectNameW` at `0x1800e9c53`
- `ext-ms-win-secur32-translatename-l1-1-0!GetComputerObjectNameW` at `0x1800e9de7`
- `logoncli!DsGetDcNameW` at `0x1800e9b9e`
- `logoncli!DsGetDcNameW` at `0x1800e9b9e`
- `netutils!NetApiBufferFree` at `0x1800e9e3c`
- `netutils!NetApiBufferFree` at `0x1800e9e3c`

## pseudocode

```c
__int64 __fastcall AdapGetComputerObjectPath(unsigned __int16 **a1, unsigned __int8 a2)
{
  unsigned __int16 *v3; // rdi
  signed int DcNameW; // eax
  signed int v5; // ebx
  unsigned int v6; // eax
  LPWSTR DomainControllerName; // rsi
  signed int v8; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rbx
  unsigned __int64 v14; // rax
  wchar_t *v15; // rax
  unsigned int v16; // eax
  signed int LastError; // eax
  LPWSTR lpNameBuffer; // [rsp+40h] [rbp-10h] BYREF
  ULONG nSize; // [rsp+88h] [rbp+38h] BYREF
  PDOMAIN_CONTROLLER_INFOW DomainControllerInfo; // [rsp+90h] [rbp+40h] BYREF
  unsigned __int64 v22; // [rsp+98h] [rbp+48h] BYREF

  DomainControllerInfo = 0;
  v3 = 0;
  v22 = 0;
  nSize = 0;
  lpNameBuffer = 0;
  DcNameW = DsGetDcNameW(0, 0, 0, 0, a2 + 4112, &DomainControllerInfo);
  v5 = DcNameW;
  if ( DcNameW > 0 )
    v5 = (unsigned __int16)DcNameW | 0x80070000;
  if ( !v5 )
    goto LABEL_12;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids, (unsigned int)v5);
  if ( v5 >= 0 )
  {
LABEL_12:
    v6 = StringCchLengthW(DomainControllerInfo->DomainControllerName, 0x7FFFFFFFu, &v22);
    v5 = v6;
    if ( !v6 )
      goto LABEL_13;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids, v6);
    if ( v5 >= 0 )
    {
LABEL_13:
      DomainControllerName = DomainControllerInfo->DomainControllerName;
      if ( GetComputerObjectNameW(NameFullyQualifiedDN, 0, &nSize) )
      {
        v12 = v22 + 6;
        if ( v22 + 6 >= 8 )
        {
          v13 = v12 + nSize;
          if ( v13 >= v12 )
          {
            v14 = 2 * v13;
            if ( !is_mul_ok(v13, 2u) )
              v14 = -1;
            v15 = (wchar_t *)operator new[](v14, (const struct std::nothrow_t *)&std::nothrow);
            v3 = v15;
            if ( v15 )
            {
              v16 = StringCchPrintfExW(v15, v13, &lpNameBuffer, 0, 0, L"LDAP://%s/", DomainControllerName + 2);
              v5 = v16;
              if ( !v16 )
                goto LABEL_54;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids, v16);
              if ( v5 >= 0 )
              {
LABEL_54:
                if ( GetComputerObjectNameW(NameFullyQualifiedDN, lpNameBuffer, &nSize) )
                {
                  *a1 = v3;
                  v3 = 0;
                }
                else
                {
                  LastError = GetLastError();
                  v5 = LastError;
                  if ( LastError > 0 )
                    v5 = (unsigned __int16)LastError | 0x80070000;
                  v9 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
                  {
                    v10 = 59;
                    goto LABEL_19;
                  }
                }
              }
            }
            else
            {
              v5 = -2147024882;
              v9 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
              {
                v10 = 57;
                goto LABEL_19;
              }
            }
          }
          else
          {
            v9 = WPP_GLOBAL_Control;
            v11 = 2147942934LL;
            v5 = -2147024362;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            {
              v10 = 56;
              goto LABEL_20;
            }
          }
        }
        else
        {
          v9 = WPP_GLOBAL_Control;
          v11 = 2147942934LL;
          v5 = -2147024362;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          {
            v10 = 55;
            goto LABEL_20;
          }
        }
      }
      else
      {
        v8 = GetLastError();
        v5 = v8;
        if ( v8 > 0 )
          v5 = (unsigned __int16)v8 | 0x80070000;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          v10 = 54;
LABEL_19:
          v11 = (unsigned int)v5;
LABEL_20:
          WPP_SF_d(v9[2], v10, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids, v11);
        }
      }
    }
  }
  if ( DomainControllerInfo )
  {
    NetApiBufferFree(DomainControllerInfo);
    DomainControllerInfo = 0;
  }
  if ( v3 )
    operator delete[](v3);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800e9b4c  mov     [rsp-28h+arg_0], rbx
0x1800e9b51  push    rbp
0x1800e9b52  push    rsi
0x1800e9b53  push    rdi
0x1800e9b54  push    r12
0x1800e9b56  push    r14
0x1800e9b58  mov     rbp, rsp
0x1800e9b5b  sub     rsp, 50h
0x1800e9b5f  mov     r14, rcx
0x1800e9b62  movzx   eax, dl
0x1800e9b65  lea     rcx, [rbp+arg_10]
0x1800e9b69  mov     [rbp+arg_10], 0
0x1800e9b71  mov     [rsp+50h+DomainControllerInfo], rcx; DomainControllerInfo
0x1800e9b76  add     eax, 1010h
0x1800e9b7b  xor     edi, edi
0x1800e9b7d  mov     [rbp+arg_18], 0
0x1800e9b85  xor     ecx, ecx; ComputerName
0x1800e9b87  mov     [rbp+nSize], 0
0x1800e9b8e  xor     r9d, r9d; SiteName
0x1800e9b91  mov     [rbp+lpNameBuffer], rdi
0x1800e9b95  xor     r8d, r8d; DomainGuid
0x1800e9b98  mov     [rsp+50h+Flags], eax; Flags
0x1800e9b9c  xor     edx, edx; DomainName
0x1800e9b9e  call    cs:__imp_DsGetDcNameW
0x1800e9ba5  nop     dword ptr [rax+rax+00h]
0x1800e9baa  mov     ebx, eax
0x1800e9bac  test    eax, eax
0x1800e9bae  jle     short loc_1800E9BB9
0x1800e9bb0  movzx   ebx, ax
0x1800e9bb3  or      ebx, 80070000h
0x1800e9bb9  lea     r12, WPP_GLOBAL_Control
0x1800e9bc0  test    ebx, ebx
0x1800e9bc2  jz      short loc_1800E9BF6
0x1800e9bc4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9bcb  cmp     rcx, r12
0x1800e9bce  jz      short loc_1800E9BEE
0x1800e9bd0  test    byte ptr [rcx+1Ch], 40h
0x1800e9bd4  jz      short loc_1800E9BEE
0x1800e9bd6  mov     rcx, [rcx+10h]
0x1800e9bda  lea     r8, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids
0x1800e9be1  mov     edx, 34h ; '4'
0x1800e9be6  mov     r9d, ebx
0x1800e9be9  call    WPP_SF_d
0x1800e9bee  test    ebx, ebx
0x1800e9bf0  js      loc_1800E9E33
0x1800e9bf6  mov     rcx, [rbp+arg_10]
0x1800e9bfa  lea     r8, [rbp+arg_18]; unsigned __int64 *
0x1800e9bfe  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800e9c03  mov     rcx, [rcx]; unsigned __int16 *
0x1800e9c06  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800e9c0b  mov     ebx, eax
0x1800e9c0d  test    eax, eax
0x1800e9c0f  jz      short loc_1800E9C43
0x1800e9c11  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9c18  cmp     rcx, r12
0x1800e9c1b  jz      short loc_1800E9C3B
0x1800e9c1d  test    byte ptr [rcx+1Ch], 40h
0x1800e9c21  jz      short loc_1800E9C3B
0x1800e9c23  mov     rcx, [rcx+10h]
0x1800e9c27  lea     r8, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids
0x1800e9c2e  mov     edx, 35h ; '5'
0x1800e9c33  mov     r9d, eax
0x1800e9c36  call    WPP_SF_d
0x1800e9c3b  test    ebx, ebx
0x1800e9c3d  js      loc_1800E9E33
0x1800e9c43  mov     rax, [rbp+arg_10]
0x1800e9c47  lea     r8, [rbp+nSize]; nSize
0x1800e9c4b  xor     edx, edx; lpNameBuffer
0x1800e9c4d  mov     rsi, [rax]
0x1800e9c50  lea     ecx, [rdx+1]; NameFormat
0x1800e9c53  call    cs:__imp_GetComputerObjectNameW
0x1800e9c5a  nop     dword ptr [rax+rax+00h]
0x1800e9c5f  test    al, al
0x1800e9c61  jnz     short loc_1800E9CB5
0x1800e9c63  call    cs:__imp_GetLastError
0x1800e9c6a  nop     dword ptr [rax+rax+00h]
0x1800e9c6f  mov     ebx, eax
0x1800e9c71  test    eax, eax
0x1800e9c73  jle     short loc_1800E9C7E
0x1800e9c75  movzx   ebx, ax
0x1800e9c78  or      ebx, 80070000h
0x1800e9c7e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9c85  cmp     rcx, r12
0x1800e9c88  jz      loc_1800E9E33
0x1800e9c8e  test    byte ptr [rcx+1Ch], 40h
0x1800e9c92  jz      loc_1800E9E33
0x1800e9c98  mov     edx, 36h ; '6'
0x1800e9c9d  mov     r9d, ebx
0x1800e9ca0  mov     rcx, [rcx+10h]
0x1800e9ca4  lea     r8, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids
0x1800e9cab  call    WPP_SF_d
0x1800e9cb0  jmp     loc_1800E9E33
0x1800e9cb5  mov     rcx, [rbp+arg_18]
0x1800e9cb9  add     rcx, 6
0x1800e9cbd  cmp     rcx, 8
0x1800e9cc1  jnb     short loc_1800E9CED
0x1800e9cc3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9cca  mov     r9d, 80070216h
0x1800e9cd0  mov     ebx, r9d
0x1800e9cd3  cmp     rcx, r12
0x1800e9cd6  jz      loc_1800E9E33
0x1800e9cdc  test    byte ptr [rcx+1Ch], 40h
0x1800e9ce0  jz      loc_1800E9E33
0x1800e9ce6  mov     edx, 37h ; '7'
0x1800e9ceb  jmp     short loc_1800E9CA0
0x1800e9ced  mov     ebx, [rbp+nSize]
0x1800e9cf0  add     rbx, rcx
0x1800e9cf3  cmp     rbx, rcx
0x1800e9cf6  jnb     short loc_1800E9D25
0x1800e9cf8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9cff  mov     r9d, 80070216h
0x1800e9d05  mov     ebx, r9d
0x1800e9d08  cmp     rcx, r12
0x1800e9d0b  jz      loc_1800E9E33
0x1800e9d11  test    byte ptr [rcx+1Ch], 40h
0x1800e9d15  jz      loc_1800E9E33
0x1800e9d1b  mov     edx, 38h ; '8'
0x1800e9d20  jmp     loc_1800E9CA0
0x1800e9d25  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800e9d2c  mov     eax, 2
0x1800e9d31  mul     rbx
0x1800e9d34  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800e9d3b  cmovb   rax, rcx
0x1800e9d3f  mov     rcx, rax; unsigned __int64
0x1800e9d42  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800e9d47  mov     rdi, rax
0x1800e9d4a  test    rax, rax
0x1800e9d4d  jnz     short loc_1800E9D76
0x1800e9d4f  mov     ebx, 8007000Eh
0x1800e9d54  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9d5b  cmp     rcx, r12
0x1800e9d5e  jz      loc_1800E9E33
0x1800e9d64  test    byte ptr [rcx+1Ch], 40h
0x1800e9d68  jz      loc_1800E9E33
0x1800e9d6e  lea     edx, [rax+39h]
0x1800e9d71  jmp     loc_1800E9C9D
0x1800e9d76  lea     rax, [rsi+4]
0x1800e9d7a  xor     r9d, r9d; unsigned __int64 *
0x1800e9d7d  mov     [rsp+50h+var_20], rax
0x1800e9d82  lea     r8, [rbp+lpNameBuffer]; unsigned __int16 **
0x1800e9d86  lea     rax, aLdapS; "LDAP://%s/"
0x1800e9d8d  mov     rdx, rbx; unsigned __int64
0x1800e9d90  mov     [rsp+50h+DomainControllerInfo], rax; unsigned __int16 *
0x1800e9d95  mov     rcx, rdi; Buffer
0x1800e9d98  mov     qword ptr [rsp+50h+Flags], 0; unsigned int
0x1800e9da1  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800e9da6  mov     ebx, eax
0x1800e9da8  test    eax, eax
0x1800e9daa  jz      short loc_1800E9DDA
0x1800e9dac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9db3  cmp     rcx, r12
0x1800e9db6  jz      short loc_1800E9DD6
0x1800e9db8  test    byte ptr [rcx+1Ch], 40h
0x1800e9dbc  jz      short loc_1800E9DD6
0x1800e9dbe  mov     rcx, [rcx+10h]
0x1800e9dc2  lea     r8, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids
0x1800e9dc9  mov     edx, 3Ah ; ':'
0x1800e9dce  mov     r9d, eax
0x1800e9dd1  call    WPP_SF_d
0x1800e9dd6  test    ebx, ebx
0x1800e9dd8  js      short loc_1800E9E33
0x1800e9dda  mov     rdx, [rbp+lpNameBuffer]; lpNameBuffer
0x1800e9dde  lea     r8, [rbp+nSize]; nSize
0x1800e9de2  mov     ecx, 1; NameFormat
0x1800e9de7  call    cs:__imp_GetComputerObjectNameW
0x1800e9dee  nop     dword ptr [rax+rax+00h]
0x1800e9df3  test    al, al
0x1800e9df5  jnz     short loc_1800E9E2E
0x1800e9df7  call    cs:__imp_GetLastError
0x1800e9dfe  nop     dword ptr [rax+rax+00h]
0x1800e9e03  mov     ebx, eax
0x1800e9e05  test    eax, eax
0x1800e9e07  jle     short loc_1800E9E12
0x1800e9e09  movzx   ebx, ax
0x1800e9e0c  or      ebx, 80070000h
0x1800e9e12  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9e19  cmp     rcx, r12
0x1800e9e1c  jz      short loc_1800E9E33
0x1800e9e1e  test    byte ptr [rcx+1Ch], 40h
0x1800e9e22  jz      short loc_1800E9E33
0x1800e9e24  mov     edx, 3Bh ; ';'
0x1800e9e29  jmp     loc_1800E9C9D
0x1800e9e2e  mov     [r14], rdi
0x1800e9e31  xor     edi, edi
0x1800e9e33  mov     rcx, [rbp+arg_10]; Buffer
0x1800e9e37  test    rcx, rcx
0x1800e9e3a  jz      short loc_1800E9E50
0x1800e9e3c  call    cs:__imp_NetApiBufferFree
0x1800e9e43  nop     dword ptr [rax+rax+00h]
0x1800e9e48  mov     [rbp+arg_10], 0
0x1800e9e50  test    rdi, rdi
0x1800e9e53  jz      short loc_1800E9E64
0x1800e9e55  mov     rcx, rdi
0x1800e9e58  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800e9e5f  nop     dword ptr [rax+rax+00h]
0x1800e9e64  mov     eax, ebx
0x1800e9e66  mov     rbx, [rsp+50h+arg_0]
0x1800e9e6e  add     rsp, 50h
0x1800e9e72  pop     r14
0x1800e9e74  pop     r12
0x1800e9e76  pop     rdi
0x1800e9e77  pop     rsi
0x1800e9e78  pop     rbp
0x1800e9e79  retn
```
