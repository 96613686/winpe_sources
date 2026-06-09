# Dns_NSPStartup

- ea: `0x180002b4c`
- end: `0x180002cf1`
- name: `Dns_NSPStartup`
- size: `421`
- prototype: `__int64 __fastcall(void *Buf1)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000ecc0`

## callees

- `0x180002b4c`
- `0x180003804`
- `0x180037189`
- `0x180038104`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c6e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002c91`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002c91`
- `DNSAPI!DnsQueryConfigAllocEx` at `0x180002ba7`
- `DNSAPI!DnsQueryConfigAllocEx` at `0x180002c51`
- `DNSAPI!DnsQueryConfigAllocEx` at `0x180002ba7`
- `DNSAPI!DnsQueryConfigAllocEx` at `0x180002c51`

## pseudocode

```c
__int64 __fastcall Dns_NSPStartup(void *Buf1, __int64 a2)
{
  const WCHAR *v4; // rax
  const WCHAR *ConfigAlloc; // rax
  DWORD v7; // ecx

  if ( (xmmword_180063D60 & 2) != 0 )
  {
    WPP_SF_(1025, 11, WPP_a6cfffb9308e3c45e18981891f5b37e8_Traceguids);
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_(1025, 12, WPP_a6cfffb9308e3c45e18981891f5b37e8_Traceguids);
  }
  if ( *(_DWORD *)a2 < 0x58u )
  {
    v7 = 10104;
    goto LABEL_18;
  }
  if ( !(unsigned __int8)RNRPROV_SockEnterApi() )
    goto LABEL_14;
  _InterlockedIncrement(&g_NspRefCount);
  if ( g_pszHostName )
    goto LABEL_5;
  ConfigAlloc = (const WCHAR *)DnsQueryConfigAllocEx(12, 0, 0);
  if ( !ConfigAlloc )
  {
LABEL_14:
    if ( GetLastError() )
      return 0xFFFFFFFFLL;
    v7 = 10091;
LABEL_18:
    SetLastError(v7);
    return 0xFFFFFFFFLL;
  }
  g_pszHostName = ConfigAlloc;
LABEL_5:
  if ( !g_pszHostFqdn )
  {
    v4 = (const WCHAR *)DnsQueryConfigAllocEx(15, 0, 0);
    if ( v4 )
    {
      g_pszHostFqdn = v4;
      goto LABEL_8;
    }
    goto LABEL_14;
  }
LABEL_8:
  *(_OWORD *)a2 = g_NspVector;
  *(_OWORD *)(a2 + 16) = *(_OWORD *)&off_180063140;
  *(_OWORD *)(a2 + 32) = *(_OWORD *)off_180063150;
  *(_OWORD *)(a2 + 48) = *(_OWORD *)off_180063160;
  *(_OWORD *)(a2 + 64) = *(_OWORD *)off_180063170;
  *(_QWORD *)(a2 + 80) = qword_180063180;
  if ( !memcmp_0(Buf1, &NbtProviderId, 0x10u) )
  {
    MaskOfGuids |= 1u;
  }
  else if ( !memcmp_0(Buf1, DNSProviderId, 0x10u) )
  {
    MaskOfGuids |= 2u;
  }
  return 0;
}

```

## disassembly

```asm
0x180002b4c  mov     [rsp+arg_0], rbx
0x180002b51  push    rdi
0x180002b52  sub     rsp, 20h
0x180002b56  mov     rbx, rdx
0x180002b59  mov     rdi, rcx
0x180002b5c  mov     al, byte ptr cs:xmmword_180063D60
0x180002b62  test    al, 2
0x180002b64  jnz     loc_180002C9F
0x180002b6a  cmp     dword ptr [rbx], 58h ; 'X'
0x180002b6d  jb      loc_180002C8C
0x180002b73  call    RNRPROV_SockEnterApi
0x180002b78  test    al, al
0x180002b7a  jz      loc_180002C6E
0x180002b80  lock inc cs:g_NspRefCount
0x180002b87  cmp     cs:g_pszHostName, 0
0x180002b8f  jz      loc_180002C49
0x180002b95  cmp     cs:g_pszHostFqdn, 0
0x180002b9d  jnz     short loc_180002BC3
0x180002b9f  xor     edx, edx
0x180002ba1  xor     r8d, r8d
0x180002ba4  lea     ecx, [rdx+0Fh]
0x180002ba7  call    cs:__imp_DnsQueryConfigAllocEx
0x180002bae  nop     dword ptr [rax+rax+00h]
0x180002bb3  test    rax, rax
0x180002bb6  jz      loc_180002C6E
0x180002bbc  mov     cs:g_pszHostFqdn, rax
0x180002bc3  movaps  xmm0, cs:g_NspVector
0x180002bca  lea     rdx, NbtProviderId; Buf2
0x180002bd1  movups  xmmword ptr [rbx], xmm0
0x180002bd4  mov     rcx, rdi; Buf1
0x180002bd7  movaps  xmm1, xmmword ptr cs:off_180063140
0x180002bde  movups  xmmword ptr [rbx+10h], xmm1
0x180002be2  movaps  xmm0, xmmword ptr cs:off_180063150
0x180002be9  movups  xmmword ptr [rbx+20h], xmm0
0x180002bed  movaps  xmm1, xmmword ptr cs:off_180063160
0x180002bf4  movups  xmmword ptr [rbx+30h], xmm1
0x180002bf8  movaps  xmm0, xmmword ptr cs:off_180063170
0x180002bff  movups  xmmword ptr [rbx+40h], xmm0
0x180002c03  movsd   xmm1, cs:qword_180063180
0x180002c0b  movsd   qword ptr [rbx+50h], xmm1
0x180002c10  mov     ebx, 10h
0x180002c15  mov     r8d, ebx; Size
0x180002c18  call    memcmp_0
0x180002c1d  test    eax, eax
0x180002c1f  jz      short loc_180002C83
0x180002c21  mov     r8d, ebx; Size
0x180002c24  lea     rdx, DNSProviderId; Buf2
0x180002c2b  mov     rcx, rdi; Buf1
0x180002c2e  call    memcmp_0
0x180002c33  test    eax, eax
0x180002c35  jz      loc_180002CDE
0x180002c3b  xor     eax, eax
0x180002c3d  mov     rbx, [rsp+28h+arg_0]
0x180002c42  add     rsp, 20h
0x180002c46  pop     rdi
0x180002c47  retn
0x180002c49  xor     edx, edx
0x180002c4b  xor     r8d, r8d
0x180002c4e  lea     ecx, [rdx+0Ch]
0x180002c51  call    cs:__imp_DnsQueryConfigAllocEx
0x180002c58  nop     dword ptr [rax+rax+00h]
0x180002c5d  test    rax, rax
0x180002c60  jz      short loc_180002C6E
0x180002c62  mov     cs:g_pszHostName, rax
0x180002c69  jmp     loc_180002B95
0x180002c6e  call    cs:__imp_GetLastError
0x180002c75  nop     dword ptr [rax+rax+00h]
0x180002c7a  test    eax, eax
0x180002c7c  jz      short loc_180002CEA
0x180002c7e  or      eax, 0FFFFFFFFh
0x180002c81  jmp     short loc_180002C3D
0x180002c83  or      cs:MaskOfGuids, 1
0x180002c8a  jmp     short loc_180002C3B
0x180002c8c  mov     ecx, 2778h; dwErrCode
0x180002c91  call    cs:__imp_SetLastError
0x180002c98  nop     dword ptr [rax+rax+00h]
0x180002c9d  jmp     short loc_180002C7E
0x180002c9f  mov     edx, 0Bh
0x180002ca4  lea     r8, WPP_a6cfffb9308e3c45e18981891f5b37e8_Traceguids
0x180002cab  mov     ecx, 401h
0x180002cb0  call    WPP_SF_
0x180002cb5  mov     al, byte ptr cs:xmmword_180063D60
0x180002cbb  test    al, 2
0x180002cbd  jz      loc_180002B6A
0x180002cc3  mov     edx, 0Ch
0x180002cc8  lea     r8, WPP_a6cfffb9308e3c45e18981891f5b37e8_Traceguids
0x180002ccf  mov     ecx, 401h
0x180002cd4  call    WPP_SF_
0x180002cd9  jmp     loc_180002B6A
0x180002cde  or      cs:MaskOfGuids, 2
0x180002ce5  jmp     loc_180002C3B
0x180002cea  mov     ecx, 276Bh
0x180002cef  jmp     short loc_180002C91
```
