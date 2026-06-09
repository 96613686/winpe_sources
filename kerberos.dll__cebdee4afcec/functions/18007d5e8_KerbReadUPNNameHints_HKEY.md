# KerbReadUPNNameHints(HKEY__ *)

- ea: `0x18007d5e8`
- end: `0x18007d86d`
- name: `?KerbReadUPNNameHints@@YAXPEAUHKEY__@@@Z`
- size: `645`
- prototype: `void __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007b8ac`

## callees

- `0x1800069a0`
- `0x1800093f0`
- `0x18007d5e8`
- `0x18008b70c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007d63d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007d6aa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007d63d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007d6aa`
- `ntdll!RtlInitUnicodeString` at `0x18007d793`
- `ntdll!RtlInitUnicodeString` at `0x18007d793`

## string_xrefs

- `0x18007d665`: `KerbReadUPNNameHints: failed to allocate memory\n`
- `0x18007d76d`: `KerbReadUPNNameHints: failed to allocate memory\n`
- `0x18007d672`: `KerbReadUPNNameHints`
- `0x18007d7eb`: `KerbReadUPNNameHints`
- `0x18007d80c`: `KerbReadUPNNameHints`
- `0x18007d845`: `KerbReadUPNNameHints`
- `0x18007d7fb`: `KerbReadUPNNameHints: failed to read hints from registry: %d\n`
- `0x18007d7de`: `KerbReadUPNNameHints: improperly formed REG_MULTI_SZ\n`
- `0x18007d722`: `KerbReadUPNNameHints: improperly formed REG_MULTI_SZ - internal double NULL\n`
- `0x18007d740`: `KerbReadUPNNameHints: improperly formed REG_MULTI_SZ - does not end with double NULL\n`
- `0x18007d834`: `KerbReadUPNNameHints: failed to get size of hints from registry: %d\n`

## pseudocode

```c
void __fastcall KerbReadUPNNameHints(HKEY hKey)
{
  LSTATUS v2; // eax
  BYTE *lpData; // rdi
  struct _UNICODE_STRING *v4; // rbp
  LSTATUS v5; // eax
  unsigned int v6; // edx
  unsigned int v7; // esi
  BYTE *v8; // r9
  __int64 v9; // r8
  const WCHAR *v10; // r14
  unsigned int i; // r15d
  __int64 v12; // rax
  size_t size; // [rsp+60h] [rbp+8h] BYREF
  DWORD Type; // [rsp+68h] [rbp+10h] BYREF

  if ( hKey )
  {
    LODWORD(size) = 0;
    Type = 0;
    if ( !KerbGlobalUPNNameHints )
    {
      v2 = RegQueryValueExW(hKey, L"UPNNameHints", 0, &Type, 0, (LPDWORD)&size);
      if ( v2 != 2 )
      {
        if ( v2 )
        {
          KerbTracerT::Log(
            1,
            "KerbReadUPNNameHints",
            607,
            "KerbReadUPNNameHints: failed to get size of hints from registry: %d\n",
            v2);
          return;
        }
        lpData = (BYTE *)MIDL_user_allocate((unsigned int)size);
        if ( !lpData )
        {
          KerbTracerT::Log(1, "KerbReadUPNNameHints", 511, "KerbReadUPNNameHints: failed to allocate memory\n");
          return;
        }
        v4 = 0;
        v5 = RegQueryValueExW(hKey, L"UPNNameHints", 0, &Type, lpData, (LPDWORD)&size);
        if ( v5 || Type != 7 )
        {
          KerbTracerT::Log(
            1,
            "KerbReadUPNNameHints",
            525,
            "KerbReadUPNNameHints: failed to read hints from registry: %d\n",
            v5);
        }
        else if ( !(_DWORD)size
               || (size & 1) != 0
               || *(_WORD *)&lpData[2 * ((unsigned __int64)(unsigned int)size >> 1) - 2] )
        {
          KerbTracerT::Log(1, "KerbReadUPNNameHints", 533, "KerbReadUPNNameHints: improperly formed REG_MULTI_SZ\n");
        }
        else
        {
          v6 = (unsigned int)size >> 1;
          v7 = 0;
          v8 = lpData;
          if ( (unsigned int)size >> 1 <= 1 )
          {
            LODWORD(v9) = 0;
LABEL_20:
            if ( v6 == 1 || (_DWORD)v9 )
            {
              if ( v7 )
              {
                v4 = (struct _UNICODE_STRING *)MIDL_user_allocate(16LL * v7);
                if ( v4 )
                {
                  v10 = (const WCHAR *)lpData;
                  for ( i = 0; i < v7; ++i )
                  {
                    RtlInitUnicodeString(&v4[i], v10);
                    v12 = -1;
                    do
                      ++v12;
                    while ( v10[v12] );
                    v10 += v12 + 1;
                  }
                  if ( !_InterlockedCompareExchange64(
                          (volatile signed __int64 *)&KerbGlobalUPNNameHints,
                          (signed __int64)v4,
                          0) )
                  {
                    KerbGlobalUPNNameHintStorage = lpData;
                    v4 = 0;
                    lpData = 0;
                    KerbGlobalUPNNameHintCount = v7;
                  }
                  if ( !lpData )
                    goto LABEL_38;
                }
                else
                {
                  KerbTracerT::Log(1, "KerbReadUPNNameHints", 577, "KerbReadUPNNameHints: failed to allocate memory\n");
                }
              }
            }
            else
            {
              KerbTracerT::Log(
                1,
                "KerbReadUPNNameHints",
                563,
                "KerbReadUPNNameHints: improperly formed REG_MULTI_SZ - does not end with double NULL\n");
            }
          }
          else
          {
            while ( 1 )
            {
              v9 = -1;
              do
                ++v9;
              while ( *(_WORD *)&v8[2 * v9] );
              if ( !(_DWORD)v9 )
                break;
              ++v7;
              v8 += 2 * (unsigned int)(v9 + 1);
              v6 += -1 - v9;
              if ( v6 <= 1 )
                goto LABEL_20;
            }
            KerbTracerT::Log(
              1,
              "KerbReadUPNNameHints",
              549,
              "KerbReadUPNNameHints: improperly formed REG_MULTI_SZ - internal double NULL\n");
          }
        }
        KerbFree(lpData);
LABEL_38:
        if ( v4 )
          KerbFree(v4);
      }
    }
  }
}

```

## disassembly

```asm
0x18007d5e8  test    rcx, rcx
0x18007d5eb  jz      locret_18007D86C
0x18007d5f1  mov     r11, rsp
0x18007d5f4  mov     [r11+18h], rbx
0x18007d5f8  mov     [r11+20h], rbp
0x18007d5fc  push    rsi
0x18007d5fd  push    rdi
0x18007d5fe  push    r12
0x18007d600  push    r14
0x18007d602  push    r15
0x18007d604  sub     rsp, 30h
0x18007d608  xor     r12d, r12d
0x18007d60b  mov     rbx, rcx
0x18007d60e  cmp     cs:?KerbGlobalUPNNameHints@@3PEAU_UNICODE_STRING@@EA, r12; _UNICODE_STRING * KerbGlobalUPNNameHints
0x18007d615  mov     [r11+8], r12d
0x18007d619  mov     [r11+10h], r12d
0x18007d61d  jnz     loc_18007D856
0x18007d623  lea     rax, [r11+8]
0x18007d627  xor     r8d, r8d; lpReserved
0x18007d62a  mov     [r11-30h], rax
0x18007d62e  lea     r9, [r11+10h]; lpType
0x18007d632  lea     rdx, aUpnnamehints; "UPNNameHints"
0x18007d639  mov     [r11-38h], r12
0x18007d63d  call    cs:__imp_RegQueryValueExW
0x18007d643  cmp     eax, 2
0x18007d646  jz      loc_18007D856
0x18007d64c  test    eax, eax
0x18007d64e  jnz     loc_18007D834
0x18007d654  mov     ecx, dword ptr [rsp+58h+size]; size
0x18007d658  call    MIDL_user_allocate
0x18007d65d  mov     rdi, rax
0x18007d660  test    rax, rax
0x18007d663  jnz     short loc_18007D686
0x18007d665  lea     r9, aKerbreadupnnam_1; "KerbReadUPNNameHints: failed to allocat"...
0x18007d66c  mov     r8d, 1FFh
0x18007d672  lea     rdx, aKerbreadupnnam_3; "KerbReadUPNNameHints"
0x18007d679  lea     ecx, [rax+1]
0x18007d67c  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18007d681  jmp     loc_18007D856
0x18007d686  lea     rax, [rsp+58h+size]
0x18007d68b  xor     r8d, r8d; lpReserved
0x18007d68e  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18007d693  lea     r9, [rsp+58h+Type]; lpType
0x18007d698  lea     rdx, aUpnnamehints; "UPNNameHints"
0x18007d69f  mov     [rsp+58h+lpData], rdi; lpData
0x18007d6a4  mov     rcx, rbx; hKey
0x18007d6a7  mov     rbp, r12
0x18007d6aa  call    cs:__imp_RegQueryValueExW
0x18007d6b0  test    eax, eax
0x18007d6b2  jnz     loc_18007D7FB
0x18007d6b8  cmp     [rsp+58h+Type], 7
0x18007d6bd  jnz     loc_18007D7FB
0x18007d6c3  mov     edx, dword ptr [rsp+58h+size]
0x18007d6c7  lea     ebx, [rax+1]
0x18007d6ca  test    edx, edx
0x18007d6cc  jz      loc_18007D7DE
0x18007d6d2  test    bl, dl
0x18007d6d4  jnz     loc_18007D7DE
0x18007d6da  mov     eax, edx
0x18007d6dc  shr     rax, 1
0x18007d6df  cmp     [rdi+rax*2-2], r12w
0x18007d6e5  jnz     loc_18007D7DE
0x18007d6eb  shr     edx, 1
0x18007d6ed  mov     esi, r12d
0x18007d6f0  mov     r9, rdi
0x18007d6f3  cmp     edx, ebx
0x18007d6f5  jbe     short loc_18007D734
0x18007d6f7  or      r8, 0FFFFFFFFFFFFFFFFh
0x18007d6fb  inc     r8
0x18007d6fe  cmp     [r9+r8*2], r12w
0x18007d703  jnz     short loc_18007D6FB
0x18007d705  test    r8d, r8d
0x18007d708  jz      short loc_18007D722
0x18007d70a  lea     eax, [r8+1]
0x18007d70e  add     esi, ebx
0x18007d710  lea     r9, [r9+rax*2]
0x18007d714  or      eax, 0FFFFFFFFh
0x18007d717  sub     eax, r8d
0x18007d71a  add     edx, eax
0x18007d71c  cmp     edx, ebx
0x18007d71e  ja      short loc_18007D6F7
0x18007d720  jmp     short loc_18007D737
0x18007d722  lea     r9, aKerbreadupnnam_5; "KerbReadUPNNameHints: improperly formed"...
0x18007d729  mov     r8d, 225h
0x18007d72f  jmp     loc_18007D7EB
0x18007d734  mov     r8d, r12d
0x18007d737  cmp     edx, ebx
0x18007d739  jz      short loc_18007D752
0x18007d73b  test    r8d, r8d
0x18007d73e  jnz     short loc_18007D752
0x18007d740  lea     r9, aKerbreadupnnam_4; "KerbReadUPNNameHints: improperly formed"...
0x18007d747  mov     r8d, 233h
0x18007d74d  jmp     loc_18007D7EB
0x18007d752  test    esi, esi
0x18007d754  jz      loc_18007D81D
0x18007d75a  mov     ecx, esi
0x18007d75c  shl     rcx, 4; size
0x18007d760  call    MIDL_user_allocate
0x18007d765  mov     rbp, rax
0x18007d768  test    rax, rax
0x18007d76b  jnz     short loc_18007D77C
0x18007d76d  lea     r9, aKerbreadupnnam_1; "KerbReadUPNNameHints: failed to allocat"...
0x18007d774  mov     r8d, 241h
0x18007d77a  jmp     short loc_18007D7EB
0x18007d77c  mov     r14, rdi
0x18007d77f  mov     r15d, r12d
0x18007d782  test    esi, esi
0x18007d784  jz      short loc_18007D7B7
0x18007d786  mov     ecx, r15d
0x18007d789  mov     rdx, r14; SourceString
0x18007d78c  shl     rcx, 4
0x18007d790  add     rcx, rbp; DestinationString
0x18007d793  call    cs:__imp_RtlInitUnicodeString
0x18007d799  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007d79d  inc     rax
0x18007d7a0  cmp     [r14+rax*2], r12w
0x18007d7a5  jnz     short loc_18007D79D
0x18007d7a7  lea     r14, [r14+rax*2]
0x18007d7ab  add     r15d, ebx
0x18007d7ae  add     r14, 2
0x18007d7b2  cmp     r15d, esi
0x18007d7b5  jb      short loc_18007D786
0x18007d7b7  xor     eax, eax
0x18007d7b9  lock cmpxchg cs:?KerbGlobalUPNNameHints@@3PEAU_UNICODE_STRING@@EA, rbp; _UNICODE_STRING * KerbGlobalUPNNameHints
0x18007d7c2  jnz     short loc_18007D7D7
0x18007d7c4  mov     cs:?KerbGlobalUPNNameHintStorage@@3PEAXEA, rdi; void * KerbGlobalUPNNameHintStorage
0x18007d7cb  mov     rbp, r12
0x18007d7ce  mov     rdi, r12
0x18007d7d1  mov     cs:?KerbGlobalUPNNameHintCount@@3KA, esi; ulong KerbGlobalUPNNameHintCount
0x18007d7d7  test    rdi, rdi
0x18007d7da  jz      short loc_18007D825
0x18007d7dc  jmp     short loc_18007D81D
0x18007d7de  lea     r9, aKerbreadupnnam; "KerbReadUPNNameHints: improperly formed"...
0x18007d7e5  mov     r8d, 215h
0x18007d7eb  lea     rdx, aKerbreadupnnam_3; "KerbReadUPNNameHints"
0x18007d7f2  mov     ecx, ebx
0x18007d7f4  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18007d7f9  jmp     short loc_18007D81D
0x18007d7fb  lea     r9, aKerbreadupnnam_0; "KerbReadUPNNameHints: failed to read hi"...
0x18007d802  mov     dword ptr [rsp+58h+lpData], eax
0x18007d806  mov     r8d, 20Dh
0x18007d80c  lea     rdx, aKerbreadupnnam_3; "KerbReadUPNNameHints"
0x18007d813  mov     ecx, 1
0x18007d818  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18007d81d  mov     rcx, rdi
0x18007d820  call    KerbFree
0x18007d825  test    rbp, rbp
0x18007d828  jz      short loc_18007D856
0x18007d82a  mov     rcx, rbp
0x18007d82d  call    KerbFree
0x18007d832  jmp     short loc_18007D856
0x18007d834  lea     r9, aKerbreadupnnam_2; "KerbReadUPNNameHints: failed to get siz"...
0x18007d83b  mov     dword ptr [rsp+58h+lpData], eax
0x18007d83f  mov     r8d, 25Fh
0x18007d845  lea     rdx, aKerbreadupnnam_3; "KerbReadUPNNameHints"
0x18007d84c  mov     ecx, 1
0x18007d851  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18007d856  mov     rbx, [rsp+58h+arg_10]
0x18007d85b  mov     rbp, [rsp+58h+arg_18]
0x18007d860  add     rsp, 30h
0x18007d864  pop     r15
0x18007d866  pop     r14
0x18007d868  pop     r12
0x18007d86a  pop     rdi
0x18007d86b  pop     rsi
0x18007d86c  retn
```
