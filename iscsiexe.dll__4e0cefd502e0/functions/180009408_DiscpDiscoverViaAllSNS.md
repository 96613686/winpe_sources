# DiscpDiscoverViaAllSNS

- ea: `0x180009408`
- end: `0x180009611`
- name: `DiscpDiscoverViaAllSNS`
- size: `521`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009358`

## callees

- `0x180009408`
- `0x18000c03c`
- `0x18000ccc4`
- `0x18001b4c0`
- `0x18001b5c4`
- `0x18001b834`

## import_xrefs

- `ISCSIUM!DiscpGetRegistryValue` at `0x180009585`
- `ISCSIUM!DiscpGetRegistryValue` at `0x180009585`
- `ISCSIUM!DiscpAllocMemory` at `0x180009480`
- `ISCSIUM!DiscpAllocMemory` at `0x180009480`
- `ISCSIUM!DiscpFreeMemory` at `0x18000953b`
- `ISCSIUM!DiscpFreeMemory` at `0x18000954a`
- `ISCSIUM!DiscpFreeMemory` at `0x1800095f1`
- `ISCSIUM!DiscpFreeMemory` at `0x18000953b`
- `ISCSIUM!DiscpFreeMemory` at `0x18000954a`
- `ISCSIUM!DiscpFreeMemory` at `0x1800095f1`
- `ISCSIUM!DiscpAnsiToUnicode` at `0x18000951c`
- `ISCSIUM!DiscpAnsiToUnicode` at `0x18000951c`
- `WS2_32!__imp_inet_ntoa` at `0x180009509`
- `WS2_32!__imp_inet_ntoa` at `0x180009509`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800094a6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800094a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800094d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800094d7`

## pseudocode

```c
__int64 DiscpDiscoverViaAllSNS()
{
  int v0; // r14d
  HANDLE *v1; // rbx
  int v2; // edi
  __int64 v3; // r15
  unsigned int v4; // esi
  HANDLE *i; // rcx
  int v6; // edx
  __int64 v7; // rax
  int v8; // eax
  unsigned int j; // edi
  struct in_addr v10; // ecx
  char *v11; // rax
  int RegistryValue; // eax
  unsigned int v13; // eax
  unsigned int v14; // ebx
  const wchar_t *k; // rax
  __int64 v16; // rax
  void *Block; // [rsp+40h] [rbp-10h] BYREF
  int v19; // [rsp+90h] [rbp+40h] BYREF
  int v20; // [rsp+98h] [rbp+48h] BYREF
  STRSAFE_LPCWSTR pszSrc; // [rsp+A0h] [rbp+50h] BYREF
  STRSAFE_LPCWSTR v22; // [rsp+A8h] [rbp+58h] BYREF

  v22 = 0;
  v20 = 0;
  v0 = -1073741811;
  pszSrc = 0;
  Block = 0;
  v19 = 0;
  if ( !(unsigned int)InitializeDHCPClientForiSNS(&Block, &v19) )
  {
    v1 = (HANDLE *)Block;
    if ( v19 )
    {
      if ( !(unsigned int)DiscoveriSNSServersViaDHCP((__int64 *)Block, &v19) )
      {
        v2 = v19;
        if ( v19 )
        {
          v3 = DiscpAllocMemory((unsigned int)(4 * v19));
          if ( v3 )
          {
            if ( v1 )
            {
              v4 = 0;
              WaitForSingleObject(v1[2], 0xFFFFFFFF);
              for ( i = (HANDLE *)*v1; v2 && i && i != v1; i = (HANDLE *)*i )
              {
                v6 = *((_DWORD *)i + 7);
                if ( v6 )
                {
                  v7 = v4++;
                  --v2;
                  *(_DWORD *)(v3 + 4 * v7) = v6;
                }
              }
              ReleaseMutex(v1[2]);
            }
            else
            {
              v4 = 87;
            }
            if ( !iSNSFirewallEnabled || (v8 = DiscpEnableiSNSFirewallException(), !iSNSFirewallEnabled) && !v8 )
            {
              for ( j = 0; j < v4; ++j )
              {
                v10 = *(struct in_addr *)(v3 + 4LL * j);
                pszSrc = 0;
                v11 = inet_ntoa(v10);
                v0 = DiscpAnsiToUnicode(v11, &pszSrc, 256);
                if ( !v0 )
                {
                  v0 = DiscpDiscoverViaSNS(pszSrc);
                  DiscpFreeMemory(pszSrc);
                }
              }
            }
            DiscpFreeMemory(v3);
          }
        }
      }
    }
    DeinitializeDHCPClientForiSNS(v1);
  }
  RegistryValue = DiscpGetRegistryValue(
                    0,
                    L"Software\\Microsoft\\Windows NT\\CurrentVersion\\iSCSI\\Discovery",
                    L"SNSServerList",
                    7,
                    0,
                    &v22,
                    &v20);
  if ( RegistryValue )
    return RegistryValue & (unsigned int)-(v0 != 0);
  if ( !iSNSFirewallEnabled )
  {
    v14 = 0;
    goto LABEL_32;
  }
  v13 = DiscpEnableiSNSFirewallException();
  v14 = v13;
  if ( !iSNSFirewallEnabled )
  {
    if ( v13 )
      goto LABEL_37;
LABEL_32:
    for ( k = v22; ; k = &pszSrc[v16 + 1] )
    {
      pszSrc = k;
      if ( !*k )
        break;
      v14 = DiscpDiscoverViaSNS(k);
      v16 = -1;
      do
        ++v16;
      while ( pszSrc[v16] );
    }
    goto LABEL_37;
  }
  v14 = -268500890;
LABEL_37:
  DiscpFreeMemory(v22);
  return v14;
}

```

## disassembly

```asm
0x180009408  push    rbp
0x18000940a  push    rbx
0x18000940b  push    rsi
0x18000940c  push    rdi
0x18000940d  push    r12
0x18000940f  push    r14
0x180009411  push    r15
0x180009413  mov     rbp, rsp
0x180009416  sub     rsp, 50h
0x18000941a  xor     r12d, r12d
0x18000941d  lea     rdx, [rbp+arg_0]
0x180009421  lea     rcx, [rbp+Block]
0x180009425  mov     [rbp+arg_18], r12
0x180009429  mov     [rbp+arg_8], r12d
0x18000942d  mov     r14d, 0C000000Dh
0x180009433  mov     [rbp+pszSrc], r12
0x180009437  mov     [rbp+Block], r12
0x18000943b  mov     [rbp+arg_0], r12d
0x18000943f  call    InitializeDHCPClientForiSNS
0x180009444  test    eax, eax
0x180009446  jnz     loc_180009558
0x18000944c  mov     rbx, [rbp+Block]
0x180009450  cmp     [rbp+arg_0], r12d
0x180009454  jz      loc_180009550
0x18000945a  lea     rdx, [rbp+arg_0]
0x18000945e  mov     rcx, rbx
0x180009461  call    DiscoveriSNSServersViaDHCP
0x180009466  test    eax, eax
0x180009468  jnz     loc_180009550
0x18000946e  mov     edi, [rbp+arg_0]
0x180009471  test    edi, edi
0x180009473  jz      loc_180009550
0x180009479  lea     ecx, ds:0[rdi*4]
0x180009480  call    cs:__imp_DiscpAllocMemory
0x180009486  mov     r15, rax
0x180009489  test    rax, rax
0x18000948c  jz      loc_180009550
0x180009492  test    rbx, rbx
0x180009495  jnz     short loc_18000949C
0x180009497  lea     esi, [rbx+57h]
0x18000949a  jmp     short loc_1800094DD
0x18000949c  mov     rcx, [rbx+10h]; hHandle
0x1800094a0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800094a3  mov     esi, r12d
0x1800094a6  call    cs:__imp_WaitForSingleObject
0x1800094ac  mov     rcx, [rbx]
0x1800094af  jmp     short loc_1800094CF
0x1800094b1  test    rcx, rcx
0x1800094b4  jz      short loc_1800094D3
0x1800094b6  cmp     rcx, rbx
0x1800094b9  jz      short loc_1800094D3
0x1800094bb  mov     edx, [rcx+1Ch]
0x1800094be  test    edx, edx
0x1800094c0  jz      short loc_1800094CC
0x1800094c2  mov     eax, esi
0x1800094c4  inc     esi
0x1800094c6  dec     edi
0x1800094c8  mov     [r15+rax*4], edx
0x1800094cc  mov     rcx, [rcx]
0x1800094cf  test    edi, edi
0x1800094d1  jnz     short loc_1800094B1
0x1800094d3  mov     rcx, [rbx+10h]; hMutex
0x1800094d7  call    cs:__imp_ReleaseMutex
0x1800094dd  cmp     cs:iSNSFirewallEnabled, r12d
0x1800094e4  jz      short loc_1800094F8
0x1800094e6  call    DiscpEnableiSNSFirewallException
0x1800094eb  cmp     cs:iSNSFirewallEnabled, r12d
0x1800094f2  jnz     short loc_180009547
0x1800094f4  test    eax, eax
0x1800094f6  jnz     short loc_180009547
0x1800094f8  mov     edi, r12d
0x1800094fb  test    esi, esi
0x1800094fd  jz      short loc_180009547
0x1800094ff  mov     ecx, edi
0x180009501  mov     ecx, [r15+rcx*4]; in
0x180009505  mov     [rbp+pszSrc], r12
0x180009509  call    cs:__imp_inet_ntoa
0x18000950f  mov     r8d, 100h
0x180009515  lea     rdx, [rbp+pszSrc]
0x180009519  mov     rcx, rax
0x18000951c  call    cs:__imp_DiscpAnsiToUnicode
0x180009522  mov     r14d, eax
0x180009525  test    eax, eax
0x180009527  jnz     short loc_180009541
0x180009529  mov     rcx, [rbp+pszSrc]; pszSrc
0x18000952d  mov     dl, 1
0x18000952f  call    DiscpDiscoverViaSNS
0x180009534  mov     rcx, [rbp+pszSrc]
0x180009538  mov     r14d, eax
0x18000953b  call    cs:__imp_DiscpFreeMemory
0x180009541  inc     edi
0x180009543  cmp     edi, esi
0x180009545  jb      short loc_1800094FF
0x180009547  mov     rcx, r15
0x18000954a  call    cs:__imp_DiscpFreeMemory
0x180009550  mov     rcx, rbx; Block
0x180009553  call    DeinitializeDHCPClientForiSNS
0x180009558  lea     rax, [rbp+arg_8]
0x18000955c  mov     r9d, 7
0x180009562  mov     [rsp+50h+var_20], rax
0x180009567  lea     r8, aSnsserverlist; "SNSServerList"
0x18000956e  lea     rax, [rbp+arg_18]
0x180009572  xor     ecx, ecx
0x180009574  mov     [rsp+50h+var_28], rax
0x180009579  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows NT\\Curren"...
0x180009580  mov     [rsp+50h+var_30], r12b
0x180009585  call    cs:__imp_DiscpGetRegistryValue
0x18000958b  test    eax, eax
0x18000958d  jnz     short loc_1800095F9
0x18000958f  cmp     cs:iSNSFirewallEnabled, r12d
0x180009596  jz      short loc_1800095B5
0x180009598  call    DiscpEnableiSNSFirewallException
0x18000959d  cmp     cs:iSNSFirewallEnabled, r12d
0x1800095a4  mov     ebx, eax
0x1800095a6  jz      short loc_1800095AF
0x1800095a8  mov     ebx, 0EFFF0066h
0x1800095ad  jmp     short loc_1800095ED
0x1800095af  test    eax, eax
0x1800095b1  jz      short loc_1800095B8
0x1800095b3  jmp     short loc_1800095ED
0x1800095b5  mov     ebx, r12d
0x1800095b8  mov     rax, [rbp+arg_18]
0x1800095bc  jmp     short loc_1800095E3
0x1800095be  mov     dl, 1
0x1800095c0  mov     rcx, rax; pszSrc
0x1800095c3  call    DiscpDiscoverViaSNS
0x1800095c8  mov     rcx, [rbp+pszSrc]
0x1800095cc  mov     ebx, eax
0x1800095ce  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800095d2  inc     rax
0x1800095d5  cmp     [rcx+rax*2], r12w
0x1800095da  jnz     short loc_1800095D2
0x1800095dc  inc     rax
0x1800095df  lea     rax, [rcx+rax*2]
0x1800095e3  mov     [rbp+pszSrc], rax
0x1800095e7  cmp     [rax], r12w
0x1800095eb  jnz     short loc_1800095BE
0x1800095ed  mov     rcx, [rbp+arg_18]
0x1800095f1  call    cs:__imp_DiscpFreeMemory
0x1800095f7  jmp     short loc_180009600
0x1800095f9  neg     r14d
0x1800095fc  sbb     ebx, ebx
0x1800095fe  and     ebx, eax
0x180009600  mov     eax, ebx
0x180009602  add     rsp, 50h
0x180009606  pop     r15
0x180009608  pop     r14
0x18000960a  pop     r12
0x18000960c  pop     rdi
0x18000960d  pop     rsi
0x18000960e  pop     rbx
0x18000960f  pop     rbp
0x180009610  retn
```
