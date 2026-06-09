# CInventoryCache::Load(ulong)

- ea: `0x180057608`
- end: `0x1800577d5`
- name: `?Load@CInventoryCache@@SAPEAV1@K@Z`
- size: `461`
- prototype: `struct CInventoryCache *__fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180044f20`

## callees

- `0x180006210`
- `0x1800066f0`
- `0x180006d02`
- `0x180007014`
- `0x180056afc`
- `0x180056ba8`
- `0x180057608`
- `0x18006041c`
- `0x180066c10`

## import_xrefs

- `WINTRUST!CryptCATAdminAcquireContext` at `0x1800576e5`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x1800576e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800576f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800576f3`

## string_xrefs

- `0x18005764c`: `Cannot create inventory cache. Out of memory`
- `0x18005765a`: `CInventoryCache::Load`
- `0x180057681`: `CInventoryCache::Load`
- `0x180057719`: `CInventoryCache::Load`
- `0x180057742`: `CInventoryCache::Load`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct CInventoryCache *__fastcall CInventoryCache::Load(int a1)
{
  struct _RTL_CRITICAL_SECTION *v2; // rax
  CInventoryCache *v3; // rbx
  FILE *v4; // rax
  FILE *v5; // rax
  FILE *v6; // rax
  signed int LastError; // eax
  signed int v8; // edi
  FILE *v9; // rax
  FILE *v10; // rax
  FILE *v11; // rax

  v2 = (struct _RTL_CRITICAL_SECTION *)operator new(0x80u, (const struct std::nothrow_t *)std::nothrow);
  if ( v2 )
    v3 = CInventoryCache::CInventoryCache(v2);
  else
    v3 = 0;
  if ( v3 )
  {
    if ( CryptCATAdminAcquireContext((HCATADMIN *)v3 + 5, 0, 0) )
    {
      *((_DWORD *)v3 + 30) = a1;
    }
    else
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      AslLogCallPrintf(2, "CInventoryCache::Load", 112, "Failed to acquire cat admin context. 0x%08x", v8);
      if ( EnableDevInvStdErrLog )
      {
        v9 = o___acrt_iob_func_0(2u);
        fprintf(v9, "Error: %s, %u: ", "CInventoryCache::Load", 112);
        v10 = o___acrt_iob_func_0(2u);
        fprintf(v10, "Failed to acquire cat admin context. 0x%08x", v8);
        v11 = o___acrt_iob_func_0(2u);
        fprintf(v11, "\n");
      }
      if ( g_DeviceMapLogFunction )
        TraceMessageCallback(0x2000000, "Failed to acquire cat admin context. 0x%08x", v8);
      if ( v8 < 0 )
      {
        CInventoryCache::~CInventoryCache((LPCRITICAL_SECTION)v3);
        operator delete(v3);
        return 0;
      }
    }
  }
  else
  {
    AslLogCallPrintf(2, "CInventoryCache::Load", 103, "Cannot create inventory cache. Out of memory");
    if ( EnableDevInvStdErrLog )
    {
      v4 = o___acrt_iob_func_0(2u);
      fprintf(v4, "Error: %s, %u: ", "CInventoryCache::Load", 103);
      v5 = o___acrt_iob_func_0(2u);
      fprintf(v5, "Cannot create inventory cache. Out of memory");
      v6 = o___acrt_iob_func_0(2u);
      fprintf(v6, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, "Cannot create inventory cache. Out of memory");
  }
  return v3;
}

```

## disassembly

```asm
0x180057608  mov     [rsp+arg_0], rbx
0x18005760d  mov     [rsp+arg_10], rsi
0x180057612  push    rdi
0x180057613  sub     rsp, 30h
0x180057617  mov     edi, ecx
0x180057619  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180057620  mov     ecx, 80h; unsigned __int64
0x180057625  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005762a  mov     [rsp+38h+arg_8], rax
0x18005762f  test    rax, rax
0x180057632  jz      short loc_180057641
0x180057634  mov     rcx, rax; lpCriticalSection
0x180057637  call    ??0CInventoryCache@@QEAA@XZ; CInventoryCache::CInventoryCache(void)
0x18005763c  mov     rbx, rax
0x18005763f  jmp     short loc_180057643
0x180057641  xor     ebx, ebx
0x180057643  test    rbx, rbx
0x180057646  jnz     loc_1800576DC
0x18005764c  lea     rdi, aCannotCreateIn_0; "Cannot create inventory cache. Out of m"...
0x180057653  mov     r9, rdi
0x180057656  lea     r8d, [rbx+67h]
0x18005765a  lea     rdx, aCinventorycach_1; "CInventoryCache::Load"
0x180057661  lea     esi, [rbx+2]
0x180057664  mov     ecx, esi
0x180057666  call    AslLogCallPrintf
0x18005766b  cmp     cs:EnableDevInvStdErrLog, ebx
0x180057671  jz      short loc_1800576BC
0x180057673  mov     ecx, esi; Ix
0x180057675  call    _o___acrt_iob_func_0
0x18005767a  mov     rcx, rax; Stream
0x18005767d  lea     r9d, [rbx+67h]
0x180057681  lea     r8, aCinventorycach_1; "CInventoryCache::Load"
0x180057688  lea     rdx, Format; "Error: %s, %u: "
0x18005768f  call    fprintf
0x180057694  mov     ecx, esi; Ix
0x180057696  call    _o___acrt_iob_func_0
0x18005769b  mov     rcx, rax; Stream
0x18005769e  mov     rdx, rdi; Format
0x1800576a1  call    fprintf
0x1800576a6  mov     ecx, esi; Ix
0x1800576a8  call    _o___acrt_iob_func_0
0x1800576ad  mov     rcx, rax; Stream
0x1800576b0  lea     rdx, asc_18011EAD8; "\n"
0x1800576b7  call    fprintf
0x1800576bc  cmp     cs:g_DeviceMapLogFunction, 0
0x1800576c4  jz      loc_1800577C2
0x1800576ca  mov     rdx, rdi
0x1800576cd  mov     ecx, 2000000h
0x1800576d2  call    TraceMessageCallback
0x1800576d7  jmp     loc_1800577C2
0x1800576dc  lea     rcx, [rbx+28h]; phCatAdmin
0x1800576e0  xor     r8d, r8d; dwFlags
0x1800576e3  xor     edx, edx; pgSubsystem
0x1800576e5  call    cs:__imp_CryptCATAdminAcquireContext
0x1800576eb  test    eax, eax
0x1800576ed  jnz     loc_1800577BF
0x1800576f3  call    cs:__imp_GetLastError
0x1800576f9  mov     edi, eax
0x1800576fb  test    eax, eax
0x1800576fd  jle     short loc_180057708
0x1800576ff  movzx   edi, ax
0x180057702  or      edi, 80070000h
0x180057708  mov     [rsp+38h+var_18], edi
0x18005770c  lea     r9, aFailedToAcquir; "Failed to acquire cat admin context. 0x"...
0x180057713  mov     r8d, 70h ; 'p'
0x180057719  lea     rdx, aCinventorycach_1; "CInventoryCache::Load"
0x180057720  lea     esi, [r8-6Eh]
0x180057724  mov     ecx, esi
0x180057726  call    AslLogCallPrintf
0x18005772b  cmp     cs:EnableDevInvStdErrLog, 0
0x180057732  jz      short loc_180057784
0x180057734  mov     ecx, esi; Ix
0x180057736  call    _o___acrt_iob_func_0
0x18005773b  mov     rcx, rax; Stream
0x18005773e  lea     r9d, [rsi+6Eh]
0x180057742  lea     r8, aCinventorycach_1; "CInventoryCache::Load"
0x180057749  lea     rdx, Format; "Error: %s, %u: "
0x180057750  call    fprintf
0x180057755  mov     ecx, esi; Ix
0x180057757  call    _o___acrt_iob_func_0
0x18005775c  mov     rcx, rax; Stream
0x18005775f  mov     r8d, edi
0x180057762  lea     rdx, aFailedToAcquir; "Failed to acquire cat admin context. 0x"...
0x180057769  call    fprintf
0x18005776e  mov     ecx, esi; Ix
0x180057770  call    _o___acrt_iob_func_0
0x180057775  mov     rcx, rax; Stream
0x180057778  lea     rdx, asc_18011EAD8; "\n"
0x18005777f  call    fprintf
0x180057784  cmp     cs:g_DeviceMapLogFunction, 0
0x18005778c  jz      short loc_1800577A2
0x18005778e  mov     r8d, edi
0x180057791  lea     rdx, aFailedToAcquir; "Failed to acquire cat admin context. 0x"...
0x180057798  mov     ecx, 2000000h
0x18005779d  call    TraceMessageCallback
0x1800577a2  test    edi, edi
0x1800577a4  jns     short loc_1800577C2
0x1800577a6  mov     rcx, rbx; lpCriticalSection
0x1800577a9  call    ??1CInventoryCache@@QEAA@XZ; CInventoryCache::~CInventoryCache(void)
0x1800577ae  mov     edx, 80h
0x1800577b3  mov     rcx, rbx; Block
0x1800577b6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800577bb  xor     ebx, ebx
0x1800577bd  jmp     short loc_1800577C2
0x1800577bf  mov     [rbx+78h], edi
0x1800577c2  mov     rax, rbx
0x1800577c5  mov     rbx, [rsp+38h+arg_0]
0x1800577ca  mov     rsi, [rsp+38h+arg_10]
0x1800577cf  add     rsp, 30h
0x1800577d3  pop     rdi
0x1800577d4  retn
```
