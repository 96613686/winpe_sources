# DeleteProtectPasswordCache

- ea: `0x180003a88`
- end: `0x180003b4b`
- name: `DeleteProtectPasswordCache`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001300`

## callees

- `0x180003a88`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003a98`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003ab5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003b1d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003a98`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003ab5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003b1d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003ad7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003ad7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003b44`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003b33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003b33`

## pseudocode

```c
void DeleteProtectPasswordCache()
{
  _BYTE *v0; // rcx
  _QWORD *v1; // rax
  HLOCAL *v2; // rdx
  __int64 v3; // rdx
  _BYTE *v4; // rax

  if ( g_szDetailApplicationName )
  {
    LocalFree(g_szDetailApplicationName);
    g_szDetailApplicationName = 0;
  }
  if ( g_szDetailApplicationPath )
  {
    LocalFree(g_szDetailApplicationPath);
    g_szDetailApplicationPath = 0;
  }
  g_fDetailGlobalsInitialized = 0;
  EnterCriticalSection(&g_csProtectPasswordCache);
  while ( 1 )
  {
    v0 = g_ProtectPasswordCache;
    if ( g_ProtectPasswordCache == &g_ProtectPasswordCache )
      break;
    v1 = *(_QWORD **)g_ProtectPasswordCache;
    if ( *(HLOCAL *)(*(_QWORD *)g_ProtectPasswordCache + 8LL) != g_ProtectPasswordCache
      || (v2 = (HLOCAL *)*((_QWORD *)g_ProtectPasswordCache + 1), *v2 != g_ProtectPasswordCache) )
    {
      __fastfail(3u);
    }
    *v2 = v1;
    v1[1] = v2;
    v3 = 160;
    v4 = v0;
    do
    {
      *v4++ = 0;
      --v3;
    }
    while ( v3 );
    LocalFree(v0);
  }
  LeaveCriticalSection(&g_csProtectPasswordCache);
  DeleteCriticalSection(&g_csProtectPasswordCache);
}

```

## disassembly

```asm
0x180003a88  sub     rsp, 28h
0x180003a8c  mov     rcx, cs:g_szDetailApplicationName; hMem
0x180003a93  test    rcx, rcx
0x180003a96  jz      short loc_180003AA9
0x180003a98  call    cs:__imp_LocalFree
0x180003a9e  mov     cs:g_szDetailApplicationName, 0
0x180003aa9  mov     rcx, cs:g_szDetailApplicationPath; hMem
0x180003ab0  test    rcx, rcx
0x180003ab3  jz      short loc_180003AC6
0x180003ab5  call    cs:__imp_LocalFree
0x180003abb  mov     cs:g_szDetailApplicationPath, 0
0x180003ac6  lea     rcx, g_csProtectPasswordCache; lpCriticalSection
0x180003acd  mov     cs:g_fDetailGlobalsInitialized, 0
0x180003ad7  call    cs:__imp_EnterCriticalSection
0x180003add  mov     rcx, cs:g_ProtectPasswordCache; hMem
0x180003ae4  lea     rax, g_ProtectPasswordCache
0x180003aeb  cmp     rcx, rax
0x180003aee  jz      short loc_180003B2C
0x180003af0  mov     rax, [rcx]
0x180003af3  cmp     [rax+8], rcx
0x180003af7  jnz     short loc_180003B25
0x180003af9  mov     rdx, [rcx+8]
0x180003afd  cmp     [rdx], rcx
0x180003b00  jnz     short loc_180003B25
0x180003b02  mov     [rdx], rax
0x180003b05  mov     [rax+8], rdx
0x180003b09  mov     edx, 0A0h
0x180003b0e  mov     rax, rcx
0x180003b11  mov     byte ptr [rax], 0
0x180003b14  inc     rax
0x180003b17  sub     rdx, 1
0x180003b1b  jnz     short loc_180003B11
0x180003b1d  call    cs:__imp_LocalFree
0x180003b23  jmp     short loc_180003ADD
0x180003b25  mov     ecx, 3
0x180003b2a  int     29h; Win8: RtlFailFast(ecx)
0x180003b2c  lea     rcx, g_csProtectPasswordCache; lpCriticalSection
0x180003b33  call    cs:__imp_LeaveCriticalSection
0x180003b39  lea     rcx, g_csProtectPasswordCache
0x180003b40  add     rsp, 28h
0x180003b44  jmp     cs:__imp_DeleteCriticalSection
```
