# DnsSetQueryRetryTimeouts

- ea: `0x180096b20`
- end: `0x180096c89`
- name: `DnsSetQueryRetryTimeouts`
- size: `361`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180029d80`
- `0x18002b050`
- `0x180079794`
- `0x180083954`
- `0x18008b5f0`
- `0x18008c0a4`
- `0x180096b20`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180096c59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180096c59`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180096c32`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180096c32`

## pseudocode

```c
__int64 __fastcall DnsSetQueryRetryTimeouts(__int128 *a1, unsigned int a2, __int64 a3)
{
  __int128 v4; // xmm0
  __int64 v5; // rbp
  BYTE *lpData; // rdi
  unsigned int QueryRetryTimeoutsRegistryHandle; // ebx
  size_t v9; // rsi
  __int64 v10; // rax
  __int64 v11; // r14
  wchar_t *v12; // rbx
  int v13; // eax
  int v14; // eax
  __int128 v15; // [rsp+30h] [rbp-48h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-38h] BYREF

  v4 = *a1;
  v5 = a2;
  hKey = 0;
  v15 = v4;
  if ( g_fVelocityDisableInternalExports )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(a1);
    return 120;
  }
  else
  {
    lpData = 0;
    if ( a2 && a3 )
    {
      QueryRetryTimeoutsRegistryHandle = DnsGetQueryRetryTimeoutsRegistryHandle((__int64)&v15, 1, &hKey);
      if ( !QueryRetryTimeoutsRegistryHandle )
      {
        v9 = 11 * v5 + 1;
        v10 = Dns_Allocate((unsigned int)(2 * v9));
        lpData = (BYTE *)v10;
        if ( v10 )
        {
          v11 = 0;
          v12 = (wchar_t *)v10;
          if ( (_DWORD)v5 )
          {
            while ( 1 )
            {
              v13 = swprintf_s(v12, v9, L"%lu", *(unsigned int *)(a3 + 4 * v11));
              if ( v13 < 1 )
                break;
              v14 = v13 + 1;
              v11 = (unsigned int)(v11 + 1);
              v9 -= v14;
              v12 += v14;
              if ( (unsigned int)v11 >= (unsigned int)v5 )
                goto LABEL_11;
            }
            QueryRetryTimeoutsRegistryHandle = 13;
          }
          else
          {
LABEL_11:
            if ( v9 )
              QueryRetryTimeoutsRegistryHandle = RegSetValueExW(
                                                   hKey,
                                                   L"DNSQueryTimeoutsMB",
                                                   0,
                                                   7u,
                                                   lpData,
                                                   2 * (((char *)v12 - (char *)lpData + 2) >> 1));
            else
              QueryRetryTimeoutsRegistryHandle = 1292;
          }
        }
        else
        {
          QueryRetryTimeoutsRegistryHandle = 14;
        }
      }
    }
    else
    {
      QueryRetryTimeoutsRegistryHandle = 87;
    }
    DnsApiFree(lpData);
    if ( hKey )
      RegCloseKey(hKey);
    return QueryRetryTimeoutsRegistryHandle;
  }
}

```

## disassembly

```asm
0x180096b20  mov     [rsp+arg_18], rbx
0x180096b25  push    rbp
0x180096b26  push    rsi
0x180096b27  push    rdi
0x180096b28  push    r14
0x180096b2a  push    r15
0x180096b2c  sub     rsp, 50h
0x180096b30  mov     rax, cs:__security_cookie
0x180096b37  xor     rax, rsp
0x180096b3a  mov     [rsp+78h+var_30], rax
0x180096b3f  cmp     cs:g_fVelocityDisableInternalExports, 0
0x180096b46  mov     r15, r8
0x180096b49  movups  xmm0, xmmword ptr [rcx]
0x180096b4c  mov     ebp, edx
0x180096b4e  mov     [rsp+78h+hKey], 0
0x180096b57  movdqu  [rsp+78h+var_48], xmm0
0x180096b5d  jz      short loc_180096B6E
0x180096b5f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180096b64  mov     eax, 78h ; 'x'
0x180096b69  jmp     loc_180096C67
0x180096b6e  xor     edi, edi
0x180096b70  test    edx, edx
0x180096b72  jz      loc_180096C42
0x180096b78  test    r15, r15
0x180096b7b  jz      loc_180096C42
0x180096b81  lea     r8, [rsp+78h+hKey]
0x180096b86  lea     edx, [rdi+1]
0x180096b89  lea     rcx, [rsp+78h+var_48]
0x180096b8e  call    DnsGetQueryRetryTimeoutsRegistryHandle
0x180096b93  mov     ebx, eax
0x180096b95  test    eax, eax
0x180096b97  jnz     loc_180096C47
0x180096b9d  imul    rsi, rbp, 0Bh
0x180096ba1  inc     rsi
0x180096ba4  lea     ecx, [rsi+rsi]
0x180096ba7  call    Dns_Allocate
0x180096bac  mov     rdi, rax
0x180096baf  test    rax, rax
0x180096bb2  jnz     short loc_180096BBC
0x180096bb4  lea     ebx, [rax+0Eh]
0x180096bb7  jmp     loc_180096C47
0x180096bbc  xor     r14d, r14d
0x180096bbf  mov     rbx, rdi
0x180096bc2  test    ebp, ebp
0x180096bc4  jz      short loc_180096BF5
0x180096bc6  mov     r9d, [r15+r14*4]
0x180096bca  lea     r8, aLu; "%lu"
0x180096bd1  mov     rdx, rsi; BufferCount
0x180096bd4  mov     rcx, rbx; Buffer
0x180096bd7  call    swprintf_s
0x180096bdc  cmp     eax, 1
0x180096bdf  jl      short loc_180096C01
0x180096be1  inc     eax
0x180096be3  inc     r14d
0x180096be6  movsxd  rcx, eax
0x180096be9  sub     rsi, rcx
0x180096bec  lea     rbx, [rbx+rcx*2]
0x180096bf0  cmp     r14d, ebp
0x180096bf3  jb      short loc_180096BC6
0x180096bf5  test    rsi, rsi
0x180096bf8  jnz     short loc_180096C08
0x180096bfa  mov     ebx, 50Ch
0x180096bff  jmp     short loc_180096C47
0x180096c01  mov     ebx, 0Dh
0x180096c06  jmp     short loc_180096C47
0x180096c08  mov     rcx, [rsp+78h+hKey]; hKey
0x180096c0d  lea     rdx, Value; "DNSQueryTimeoutsMB"
0x180096c14  sub     rbx, rdi
0x180096c17  mov     r9d, 7; dwType
0x180096c1d  add     rbx, 2
0x180096c21  xor     r8d, r8d; Reserved
0x180096c24  sar     rbx, 1
0x180096c27  add     ebx, ebx
0x180096c29  mov     [rsp+78h+cbData], ebx; cbData
0x180096c2d  mov     [rsp+78h+lpData], rdi; lpData
0x180096c32  call    cs:__imp_RegSetValueExW
0x180096c39  nop     dword ptr [rax+rax+00h]
0x180096c3e  mov     ebx, eax
0x180096c40  jmp     short loc_180096C47
0x180096c42  mov     ebx, 57h ; 'W'
0x180096c47  mov     rcx, rdi; lpMem
0x180096c4a  call    DnsApiFree
0x180096c4f  mov     rcx, [rsp+78h+hKey]; hKey
0x180096c54  test    rcx, rcx
0x180096c57  jz      short loc_180096C65
0x180096c59  call    cs:__imp_RegCloseKey
0x180096c60  nop     dword ptr [rax+rax+00h]
0x180096c65  mov     eax, ebx
0x180096c67  mov     rcx, [rsp+78h+var_30]
0x180096c6c  xor     rcx, rsp; StackCookie
0x180096c6f  call    __security_check_cookie
0x180096c74  mov     rbx, [rsp+78h+arg_18]
0x180096c7c  add     rsp, 50h
0x180096c80  pop     r15
0x180096c82  pop     r14
0x180096c84  pop     rdi
0x180096c85  pop     rsi
0x180096c86  pop     rbp
0x180096c87  retn
```
