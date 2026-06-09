# APP_POOL::InitializeAppPoolCounters(ulong)

- ea: `0x180018620`
- end: `0x180018845`
- name: `?InitializeAppPoolCounters@APP_POOL@@QEAAJK@Z`
- size: `549`
- prototype: `int(APP_POOL *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800184ac`

## callees

- `0x180018620`

## import_xrefs

- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x1800187a2`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x1800187a2`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x180018649`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x180018649`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x1800186bc`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x1800186e3`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x18001870a`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x180018731`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x180018758`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x18001877c`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x1800187c9`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x1800187ec`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x18001880f`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x180018832`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x1800186bc`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x1800186e3`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x18001870a`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x180018731`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x180018758`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x18001877c`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x1800187c9`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x1800187ec`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x18001880f`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x180018832`
- `iisutil!PuDbgPrintError` at `0x1800186a0`
- `iisutil!PuDbgPrintError` at `0x1800186a0`

## string_xrefs

- `0x18001867a`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\app_pool.cxx`
- `0x18001868c`: `Failed to create counterset Instance for '%S' app pool.\n`

## pseudocode

```c
__int64 __fastcall APP_POOL::InitializeAppPoolCounters(APP_POOL *this, ULONG a2)
{
  WEB_ADMIN_SERVICE *v2; // rdi
  struct _PERF_COUNTERSET_INSTANCE *Instance; // rax

  v2 = g_pWebAdminService;
  Instance = PerfCreateInstance(
               *((HANDLE *)g_pWebAdminService + 76),
               *((LPCGUID *)g_pWebAdminService + 77),
               *((PCWSTR *)this + 7),
               a2);
  *((_QWORD *)this + 56) = Instance;
  if ( Instance )
  {
    if ( !PerfSetCounterRefValue(*((HANDLE *)v2 + 76), Instance, 0, (char *)this + 120)
      && !PerfSetCounterRefValue(
            *((HANDLE *)v2 + 76),
            *((PPERF_COUNTERSET_INSTANCE *)this + 56),
            1u,
            (char *)this + 456)
      && !PerfSetCounterRefValue(
            *((HANDLE *)v2 + 76),
            *((PPERF_COUNTERSET_INSTANCE *)this + 56),
            2u,
            (char *)this + 460)
      && !PerfSetCounterRefValue(
            *((HANDLE *)v2 + 76),
            *((PPERF_COUNTERSET_INSTANCE *)this + 56),
            5u,
            (char *)this + 188)
      && !PerfSetCounterRefValue(
            *((HANDLE *)v2 + 76),
            *((PPERF_COUNTERSET_INSTANCE *)this + 56),
            6u,
            (char *)this + 184)
      && !PerfSetCounterRefValue(*((HANDLE *)v2 + 76), *((PPERF_COUNTERSET_INSTANCE *)this + 56), 7u, (char *)this + 20)
      && !PerfSetULongLongCounterValue(*((HANDLE *)v2 + 76), *((PPERF_COUNTERSET_INSTANCE *)this + 56), 9u, 0x989680u)
      && !PerfSetCounterRefValue(
            *((HANDLE *)v2 + 76),
            *((PPERF_COUNTERSET_INSTANCE *)this + 56),
            0xBu,
            (char *)this + 488)
      && !PerfSetCounterRefValue(
            *((HANDLE *)v2 + 76),
            *((PPERF_COUNTERSET_INSTANCE *)this + 56),
            0xCu,
            (char *)this + 492)
      && !PerfSetCounterRefValue(
            *((HANDLE *)v2 + 76),
            *((PPERF_COUNTERSET_INSTANCE *)this + 56),
            0xDu,
            (char *)this + 496) )
    {
      PerfSetCounterRefValue(*((HANDLE *)v2 + 76), *((PPERF_COUNTERSET_INSTANCE *)this + 56), 0x10u, (char *)this + 500);
    }
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool.cxx",
      545,
      "APP_POOL::InitializeAppPoolCounters",
      0,
      "Failed to create counterset Instance for '%S' app pool.\n",
      *((const wchar_t **)this + 7));
  }
  return 0;
}

```

## disassembly

```asm
0x180018620  mov     [rsp+arg_0], rbx
0x180018625  push    rdi
0x180018626  sub     rsp, 40h
0x18001862a  mov     rdi, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x180018631  mov     rbx, rcx
0x180018634  mov     r8, [rcx+38h]; Name
0x180018638  mov     r9d, edx; Id
0x18001863b  mov     rdx, [rdi+268h]; CounterSetGuid
0x180018642  mov     rcx, [rdi+260h]; ProviderHandle
0x180018649  call    cs:__imp_PerfCreateInstance
0x18001864f  mov     [rbx+1C0h], rax
0x180018656  test    rax, rax
0x180018659  jnz     short loc_1800186AB
0x18001865b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180018662  jz      loc_180018838
0x180018668  mov     rax, [rbx+38h]
0x18001866c  lea     r9, aAppPoolInitial_0; "APP_POOL::InitializeAppPoolCounters"
0x180018673  mov     rcx, cs:g_pDebug
0x18001867a  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180018681  mov     [rsp+48h+var_18], rax
0x180018686  mov     r8d, 221h
0x18001868c  lea     rax, aFailedToCreate; "Failed to create counterset Instance fo"...
0x180018693  mov     [rsp+48h+var_20], rax
0x180018698  mov     [rsp+48h+var_28], 0
0x1800186a0  call    cs:__imp_PuDbgPrintError
0x1800186a6  jmp     loc_180018838
0x1800186ab  mov     rcx, [rdi+260h]; Provider
0x1800186b2  lea     r9, [rbx+78h]; Address
0x1800186b6  xor     r8d, r8d; CounterId
0x1800186b9  mov     rdx, rax; Instance
0x1800186bc  call    cs:__imp_PerfSetCounterRefValue
0x1800186c2  test    eax, eax
0x1800186c4  jnz     loc_180018838
0x1800186ca  mov     rdx, [rbx+1C0h]; Instance
0x1800186d1  lea     r9, [rbx+1C8h]; Address
0x1800186d8  mov     rcx, [rdi+260h]; Provider
0x1800186df  lea     r8d, [rax+1]; CounterId
0x1800186e3  call    cs:__imp_PerfSetCounterRefValue
0x1800186e9  test    eax, eax
0x1800186eb  jnz     loc_180018838
0x1800186f1  mov     rdx, [rbx+1C0h]; Instance
0x1800186f8  lea     r9, [rbx+1CCh]; Address
0x1800186ff  mov     rcx, [rdi+260h]; Provider
0x180018706  lea     r8d, [rax+2]; CounterId
0x18001870a  call    cs:__imp_PerfSetCounterRefValue
0x180018710  test    eax, eax
0x180018712  jnz     loc_180018838
0x180018718  mov     rdx, [rbx+1C0h]; Instance
0x18001871f  lea     r9, [rbx+0BCh]; Address
0x180018726  mov     rcx, [rdi+260h]; Provider
0x18001872d  lea     r8d, [rax+5]; CounterId
0x180018731  call    cs:__imp_PerfSetCounterRefValue
0x180018737  test    eax, eax
0x180018739  jnz     loc_180018838
0x18001873f  mov     rdx, [rbx+1C0h]; Instance
0x180018746  lea     r9, [rbx+0B8h]; Address
0x18001874d  mov     rcx, [rdi+260h]; Provider
0x180018754  lea     r8d, [rax+6]; CounterId
0x180018758  call    cs:__imp_PerfSetCounterRefValue
0x18001875e  test    eax, eax
0x180018760  jnz     loc_180018838
0x180018766  mov     rdx, [rbx+1C0h]; Instance
0x18001876d  lea     r9, [rbx+14h]; Address
0x180018771  mov     rcx, [rdi+260h]; Provider
0x180018778  lea     r8d, [rax+7]; CounterId
0x18001877c  call    cs:__imp_PerfSetCounterRefValue
0x180018782  test    eax, eax
0x180018784  jnz     loc_180018838
0x18001878a  mov     rdx, [rbx+1C0h]; Instance
0x180018791  lea     r8d, [rax+9]; CounterId
0x180018795  mov     rcx, [rdi+260h]; Provider
0x18001879c  mov     r9d, 989680h; Value
0x1800187a2  call    cs:__imp_PerfSetULongLongCounterValue
0x1800187a8  test    eax, eax
0x1800187aa  jnz     loc_180018838
0x1800187b0  mov     rdx, [rbx+1C0h]; Instance
0x1800187b7  lea     r9, [rbx+1E8h]; Address
0x1800187be  mov     rcx, [rdi+260h]; Provider
0x1800187c5  lea     r8d, [rax+0Bh]; CounterId
0x1800187c9  call    cs:__imp_PerfSetCounterRefValue
0x1800187cf  test    eax, eax
0x1800187d1  jnz     short loc_180018838
0x1800187d3  mov     rdx, [rbx+1C0h]; Instance
0x1800187da  lea     r9, [rbx+1ECh]; Address
0x1800187e1  mov     rcx, [rdi+260h]; Provider
0x1800187e8  lea     r8d, [rax+0Ch]; CounterId
0x1800187ec  call    cs:__imp_PerfSetCounterRefValue
0x1800187f2  test    eax, eax
0x1800187f4  jnz     short loc_180018838
0x1800187f6  mov     rdx, [rbx+1C0h]; Instance
0x1800187fd  lea     r9, [rbx+1F0h]; Address
0x180018804  mov     rcx, [rdi+260h]; Provider
0x18001880b  lea     r8d, [rax+0Dh]; CounterId
0x18001880f  call    cs:__imp_PerfSetCounterRefValue
0x180018815  test    eax, eax
0x180018817  jnz     short loc_180018838
0x180018819  mov     rdx, [rbx+1C0h]; Instance
0x180018820  lea     r9, [rbx+1F4h]; Address
0x180018827  mov     rcx, [rdi+260h]; Provider
0x18001882e  lea     r8d, [rax+10h]; CounterId
0x180018832  call    cs:__imp_PerfSetCounterRefValue
0x180018838  mov     rbx, [rsp+48h+arg_0]
0x18001883d  xor     eax, eax
0x18001883f  add     rsp, 40h
0x180018843  pop     rdi
0x180018844  retn
```
