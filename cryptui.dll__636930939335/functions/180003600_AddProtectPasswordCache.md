# AddProtectPasswordCache

- ea: `0x180003600`
- end: `0x18000370a`
- name: `AddProtectPasswordCache`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180004350`

## callees

- `0x180003600`
- `0x1800037f4`
- `0x18000383c`
- `0x180003884`
- `0x180004994`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003625`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003625`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800036b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800036b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800036ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800036ef`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003644`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003644`

## pseudocode

```c
__int64 __fastcall AddProtectPasswordCache(unsigned int *a1, _OWORD *a2)
{
  __int64 result; // rax
  struct _FILETIME *v5; // rbx
  __int64 v6; // rcx
  BCRYPT_HASH_HANDLE *p_phHash; // rax
  _QWORD *v8; // rax
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp+18h] BYREF

  phHash = 0;
  result = (__int64)LocalAlloc(0, 0xA0u);
  v5 = (struct _FILETIME *)result;
  if ( result )
  {
    GetEffectiveLogonId((_QWORD *)(result + 16));
    GetSystemTimeAsFileTime(v5 + 3);
    CngRsa32Compat_SHAInit(&phHash);
    CngRsa32Compat_SHAUpdate(&phHash, *((_QWORD *)a1 + 1), *a1);
    CngRsa32Compat_SHAFinal(&phHash, &v5[4]);
    v6 = 8;
    p_phHash = &phHash;
    do
    {
      *(_BYTE *)p_phHash = 0;
      p_phHash = (BCRYPT_HASH_HANDLE *)((char *)p_phHash + 1);
      --v6;
    }
    while ( v6 );
    *(_OWORD *)&v5[12].dwLowDateTime = *a2;
    *(_OWORD *)&v5[14].dwLowDateTime = a2[1];
    *(_OWORD *)&v5[16].dwLowDateTime = a2[2];
    *(_OWORD *)&v5[18].dwLowDateTime = a2[3];
    EnterCriticalSection(&g_csProtectPasswordCache);
    v8 = g_ProtectPasswordCache;
    if ( *((HLOCAL **)g_ProtectPasswordCache + 1) != &g_ProtectPasswordCache )
      __fastfail(3u);
    v5[1] = (struct _FILETIME)&g_ProtectPasswordCache;
    *v5 = (struct _FILETIME)v8;
    v8[1] = v5;
    g_ProtectPasswordCache = v5;
    LeaveCriticalSection(&g_csProtectPasswordCache);
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180003600  mov     [rsp+arg_0], rbx
0x180003605  mov     [rsp+arg_8], rsi
0x18000360a  push    rdi
0x18000360b  sub     rsp, 20h
0x18000360f  mov     rdi, rdx
0x180003612  mov     [rsp+28h+phHash], 0
0x18000361b  mov     rsi, rcx
0x18000361e  mov     edx, 0A0h; uBytes
0x180003623  xor     ecx, ecx; uFlags
0x180003625  call    cs:__imp_LocalAlloc
0x18000362b  mov     rbx, rax
0x18000362e  test    rax, rax
0x180003631  jz      loc_1800036FA
0x180003637  lea     rcx, [rax+10h]
0x18000363b  call    GetEffectiveLogonId
0x180003640  lea     rcx, [rbx+18h]; lpSystemTimeAsFileTime
0x180003644  call    cs:__imp_GetSystemTimeAsFileTime
0x18000364a  lea     rcx, [rsp+28h+phHash]; phHash
0x18000364f  call    CngRsa32Compat_SHAInit
0x180003654  mov     r8d, [rsi]
0x180003657  lea     rcx, [rsp+28h+phHash]
0x18000365c  mov     rdx, [rsi+8]
0x180003660  call    CngRsa32Compat_SHAUpdate
0x180003665  lea     rdx, [rbx+20h]
0x180003669  lea     rcx, [rsp+28h+phHash]
0x18000366e  call    CngRsa32Compat_SHAFinal
0x180003673  mov     ecx, 8
0x180003678  lea     rax, [rsp+28h+phHash]
0x18000367d  mov     byte ptr [rax], 0
0x180003680  inc     rax
0x180003683  sub     rcx, 1
0x180003687  jnz     short loc_18000367D
0x180003689  movups  xmm0, xmmword ptr [rdi]
0x18000368c  lea     rcx, g_csProtectPasswordCache; lpCriticalSection
0x180003693  movups  xmmword ptr [rbx+60h], xmm0
0x180003697  movups  xmm1, xmmword ptr [rdi+10h]
0x18000369b  movups  xmmword ptr [rbx+70h], xmm1
0x18000369f  movups  xmm0, xmmword ptr [rdi+20h]
0x1800036a3  movups  xmmword ptr [rbx+80h], xmm0
0x1800036aa  movups  xmm1, xmmword ptr [rdi+30h]
0x1800036ae  movups  xmmword ptr [rbx+90h], xmm1
0x1800036b5  call    cs:__imp_EnterCriticalSection
0x1800036bb  mov     rax, cs:g_ProtectPasswordCache
0x1800036c2  lea     rcx, g_ProtectPasswordCache
0x1800036c9  cmp     [rax+8], rcx
0x1800036cd  jz      short loc_1800036D6
0x1800036cf  mov     ecx, 3
0x1800036d4  int     29h; Win8: RtlFailFast(ecx)
0x1800036d6  mov     [rbx+8], rcx
0x1800036da  lea     rcx, g_csProtectPasswordCache; lpCriticalSection
0x1800036e1  mov     [rbx], rax
0x1800036e4  mov     [rax+8], rbx
0x1800036e8  mov     cs:g_ProtectPasswordCache, rbx
0x1800036ef  call    cs:__imp_LeaveCriticalSection
0x1800036f5  mov     eax, 1
0x1800036fa  mov     rbx, [rsp+28h+arg_0]
0x1800036ff  mov     rsi, [rsp+28h+arg_8]
0x180003704  add     rsp, 20h
0x180003708  pop     rdi
0x180003709  retn
```
