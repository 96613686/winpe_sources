# PurgeProtectPasswordCache

- ea: `0x1800051ec`
- end: `0x1800052e9`
- name: `PurgeProtectPasswordCache`
- size: `253`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800052f0`

## callees

- `0x1800051ec`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800052bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800052bc`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000523e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000527f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000523e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000527f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005260`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005260`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800052d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800052d1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005204`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005253`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005204`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005253`

## pseudocode

```c
void PurgeProtectPasswordCache()
{
  __int64 v0; // rax
  HLOCAL *i; // rbx
  HLOCAL v2; // rdx
  HLOCAL *v3; // rax
  HLOCAL *v4; // rcx
  __int64 v5; // rdx
  HLOCAL *v6; // rax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp+8h] BYREF

  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v0 = *(_QWORD *)&SystemTimeAsFileTime - 36000000000LL;
  SystemTimeAsFileTime.dwLowDateTime -= 1640261632;
  SystemTimeAsFileTime.dwHighDateTime = HIDWORD(v0);
  if ( CompareFileTime(&SystemTimeAsFileTime, &::SystemTimeAsFileTime) >= 0 )
  {
    GetSystemTimeAsFileTime(&::SystemTimeAsFileTime);
    EnterCriticalSection(&g_csProtectPasswordCache);
    for ( i = (HLOCAL *)g_ProtectPasswordCache; i != &g_ProtectPasswordCache; i = (HLOCAL *)*i )
    {
      if ( CompareFileTime(&SystemTimeAsFileTime, (const FILETIME *)i + 3) > 0 )
      {
        v2 = *i;
        if ( *((HLOCAL **)*i + 1) != i || (v3 = (HLOCAL *)i[1], *v3 != i) )
          __fastfail(3u);
        *v3 = v2;
        v4 = i;
        *((_QWORD *)v2 + 1) = v3;
        i = v3;
        v5 = 160;
        v6 = v4;
        do
        {
          *(_BYTE *)v6 = 0;
          v6 = (HLOCAL *)((char *)v6 + 1);
          --v5;
        }
        while ( v5 );
        LocalFree(v4);
      }
    }
    LeaveCriticalSection(&g_csProtectPasswordCache);
  }
}

```

## disassembly

```asm
0x1800051ec  mov     [rsp+arg_8], rbx
0x1800051f1  push    rdi
0x1800051f2  sub     rsp, 20h
0x1800051f6  lea     rcx, [rsp+28h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800051fb  mov     qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180005204  call    cs:__imp_GetSystemTimeAsFileTime
0x18000520a  mov     eax, [rsp+28h+SystemTimeAsFileTime.dwLowDateTime]
0x18000520e  lea     rdx, SystemTimeAsFileTime; lpFileTime2
0x180005215  mov     ecx, [rsp+28h+SystemTimeAsFileTime.dwHighDateTime]
0x180005219  shl     rcx, 20h
0x18000521d  or      rcx, rax
0x180005220  mov     rax, 0FFFFFFF79E3B9800h
0x18000522a  add     rax, rcx
0x18000522d  lea     rcx, [rsp+28h+SystemTimeAsFileTime]; lpFileTime1
0x180005232  mov     [rsp+28h+SystemTimeAsFileTime.dwLowDateTime], eax
0x180005236  shr     rax, 20h
0x18000523a  mov     [rsp+28h+SystemTimeAsFileTime.dwHighDateTime], eax
0x18000523e  call    cs:__imp_CompareFileTime
0x180005244  test    eax, eax
0x180005246  js      loc_1800052D7
0x18000524c  lea     rcx, SystemTimeAsFileTime; lpSystemTimeAsFileTime
0x180005253  call    cs:__imp_GetSystemTimeAsFileTime
0x180005259  lea     rcx, g_csProtectPasswordCache; lpCriticalSection
0x180005260  call    cs:__imp_EnterCriticalSection
0x180005266  mov     rbx, cs:g_ProtectPasswordCache
0x18000526d  lea     rdi, g_ProtectPasswordCache
0x180005274  jmp     short loc_1800052C5
0x180005276  lea     rdx, [rbx+18h]; lpFileTime2
0x18000527a  lea     rcx, [rsp+28h+SystemTimeAsFileTime]; lpFileTime1
0x18000527f  call    cs:__imp_CompareFileTime
0x180005285  test    eax, eax
0x180005287  jle     short loc_1800052C2
0x180005289  mov     rdx, [rbx]
0x18000528c  cmp     [rdx+8], rbx
0x180005290  jnz     short loc_1800052E2
0x180005292  mov     rax, [rbx+8]
0x180005296  cmp     [rax], rbx
0x180005299  jnz     short loc_1800052E2
0x18000529b  mov     [rax], rdx
0x18000529e  mov     rcx, rbx; hMem
0x1800052a1  mov     [rdx+8], rax
0x1800052a5  mov     rbx, rax
0x1800052a8  mov     edx, 0A0h
0x1800052ad  mov     rax, rcx
0x1800052b0  mov     byte ptr [rax], 0
0x1800052b3  inc     rax
0x1800052b6  sub     rdx, 1
0x1800052ba  jnz     short loc_1800052B0
0x1800052bc  call    cs:__imp_LocalFree
0x1800052c2  mov     rbx, [rbx]
0x1800052c5  cmp     rbx, rdi
0x1800052c8  jnz     short loc_180005276
0x1800052ca  lea     rcx, g_csProtectPasswordCache; lpCriticalSection
0x1800052d1  call    cs:__imp_LeaveCriticalSection
0x1800052d7  mov     rbx, [rsp+28h+arg_8]
0x1800052dc  add     rsp, 20h
0x1800052e0  pop     rdi
0x1800052e1  retn
0x1800052e2  mov     ecx, 3
0x1800052e7  int     29h; Win8: RtlFailFast(ecx)
```
