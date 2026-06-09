# LuiApiServer::LuiApiServerInit(void)

- ea: `0x1800eaf40`
- end: `0x1800eb018`
- name: `?LuiApiServerInit@LuiApiServer@@YAJXZ`
- size: `216`
- prototype: `__int64 __fastcall(LuiApiServer *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180072ad4`

## callees

- `0x18000e4e0`
- `0x1800eaeb4`
- `0x1800eaf40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800eafb2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800eafb2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800eafd3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800eafd3`

## pseudocode

```c
__int64 __fastcall LuiApiServer::LuiApiServerInit(LuiApiServer *this)
{
  _DWORD *v1; // rax
  LuiApiServer *v2; // rcx
  struct _RTL_CRITICAL_SECTION *v3; // rax
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  unsigned int v5; // ebx
  HANDLE EventW; // rax

  v1 = operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v1 )
  {
    LuiApiServer::g_pLuiApiServerGlobalData = 0;
    goto LABEL_7;
  }
  *(_QWORD *)v1 = 0;
  v1[2] = 0;
  *((_QWORD *)v1 + 2) = 0;
  *((_QWORD *)v1 + 3) = 0;
  *((_QWORD *)v1 + 4) = 0;
  LuiApiServer::g_pLuiApiServerGlobalData = (LuiApiServer *)v1;
  v3 = (struct _RTL_CRITICAL_SECTION *)operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
  v4 = v3;
  if ( !v3 )
  {
    *(_QWORD *)LuiApiServer::g_pLuiApiServerGlobalData = 0;
LABEL_7:
    v5 = -2147024882;
    LuiApiServer::LuiApiServerDeInit(v2);
    return v5;
  }
  InitializeCriticalSection(v3);
  *(_QWORD *)LuiApiServer::g_pLuiApiServerGlobalData = v4;
  v5 = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  v2 = LuiApiServer::g_pLuiApiServerGlobalData;
  *((_QWORD *)LuiApiServer::g_pLuiApiServerGlobalData + 2) = EventW;
  if ( !EventW )
    goto LABEL_7;
  return v5;
}

```

## disassembly

```asm
0x1800eaf40  push    rbx
0x1800eaf42  sub     rsp, 20h
0x1800eaf46  mov     ebx, 28h ; '('
0x1800eaf4b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800eaf52  mov     ecx, ebx; unsigned __int64
0x1800eaf54  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800eaf59  mov     [rsp+28h+arg_0], rax
0x1800eaf5e  test    rax, rax
0x1800eaf61  jz      loc_1800EAFFB
0x1800eaf67  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800eaf6e  mov     qword ptr [rax], 0
0x1800eaf75  mov     ecx, ebx; unsigned __int64
0x1800eaf77  mov     dword ptr [rax+8], 0
0x1800eaf7e  mov     qword ptr [rax+10h], 0
0x1800eaf86  mov     qword ptr [rax+18h], 0
0x1800eaf8e  mov     qword ptr [rax+20h], 0
0x1800eaf96  mov     cs:?g_pLuiApiServerGlobalData@LuiApiServer@@3PEAU_LuiApiServerGlobalData@1@EA, rax; LuiApiServer::_LuiApiServerGlobalData * LuiApiServer::g_pLuiApiServerGlobalData
0x1800eaf9d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800eafa2  mov     [rsp+28h+arg_0], rax
0x1800eafa7  mov     rbx, rax
0x1800eafaa  test    rax, rax
0x1800eafad  jz      short loc_1800EAFEB
0x1800eafaf  mov     rcx, rax; lpCriticalSection
0x1800eafb2  call    cs:__imp_InitializeCriticalSection
0x1800eafb8  mov     rcx, cs:?g_pLuiApiServerGlobalData@LuiApiServer@@3PEAU_LuiApiServerGlobalData@1@EA; LuiApiServer::_LuiApiServerGlobalData * LuiApiServer::g_pLuiApiServerGlobalData
0x1800eafbf  mov     [rcx], rbx
0x1800eafc2  test    rbx, rbx
0x1800eafc5  jz      short loc_1800EB006
0x1800eafc7  xor     r9d, r9d; lpName
0x1800eafca  xor     r8d, r8d; bInitialState
0x1800eafcd  xor     edx, edx; bManualReset
0x1800eafcf  xor     ecx, ecx; lpEventAttributes
0x1800eafd1  xor     ebx, ebx
0x1800eafd3  call    cs:__imp_CreateEventW
0x1800eafd9  mov     rcx, cs:?g_pLuiApiServerGlobalData@LuiApiServer@@3PEAU_LuiApiServerGlobalData@1@EA; LuiApiServer::_LuiApiServerGlobalData * LuiApiServer::g_pLuiApiServerGlobalData
0x1800eafe0  mov     [rcx+10h], rax
0x1800eafe4  test    rax, rax
0x1800eafe7  jnz     short loc_1800EB010
0x1800eafe9  jmp     short loc_1800EB006
0x1800eafeb  mov     rax, cs:?g_pLuiApiServerGlobalData@LuiApiServer@@3PEAU_LuiApiServerGlobalData@1@EA; LuiApiServer::_LuiApiServerGlobalData * LuiApiServer::g_pLuiApiServerGlobalData
0x1800eaff2  mov     qword ptr [rax], 0
0x1800eaff9  jmp     short loc_1800EB006
0x1800eaffb  mov     cs:?g_pLuiApiServerGlobalData@LuiApiServer@@3PEAU_LuiApiServerGlobalData@1@EA, 0; LuiApiServer::_LuiApiServerGlobalData * LuiApiServer::g_pLuiApiServerGlobalData
0x1800eb006  mov     ebx, 8007000Eh
0x1800eb00b  call    ?LuiApiServerDeInit@LuiApiServer@@YAXXZ; LuiApiServer::LuiApiServerDeInit(void)
0x1800eb010  mov     eax, ebx
0x1800eb012  add     rsp, 20h
0x1800eb016  pop     rbx
0x1800eb017  retn
```
