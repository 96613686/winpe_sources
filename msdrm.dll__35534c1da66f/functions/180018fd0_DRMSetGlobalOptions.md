# DRMSetGlobalOptions

- ea: `0x180018fd0`
- end: `0x18001905c`
- name: `DRMSetGlobalOptions`
- size: `140`
- prototype: `HRESULT __stdcall(DRMGLOBALOPTIONS eGlobalOptions, LPVOID pvdata, DWORD dwlen)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180037890`

## callees

- `0x1800046c8`
- `0x180018fd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019040`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019040`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018fdf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018fdf`

## string_xrefs

- `0x180019015`: `[msdrm]:+DRMSetGlobalOptions eGlobalOptions = DRMGLOBALOPTIONS_USE_SERVERSECURITYPROCESSOR\n`

## pseudocode

```c
HRESULT __stdcall DRMSetGlobalOptions(DRMGLOBALOPTIONS eGlobalOptions, LPVOID pvdata, DWORD dwlen)
{
  HRESULT v4; // ebx

  EnterCriticalSection(&g_csOptions);
  if ( eGlobalOptions )
  {
    if ( eGlobalOptions != DRMGLOBALOPTIONS_USE_SERVERSECURITYPROCESSOR )
    {
      v4 = -2147024809;
      goto LABEL_10;
    }
    _RTLTRACE("[msdrm]:+DRMSetGlobalOptions eGlobalOptions = DRMGLOBALOPTIONS_USE_SERVERSECURITYPROCESSOR\n");
    if ( g_fGlobalOptionUseServerProc )
      goto LABEL_3;
    g_fGlobalOptionUseServerProc = 1;
LABEL_8:
    v4 = 0;
    goto LABEL_10;
  }
  _RTLTRACE("[msdrm]:+DRMSetGlobalOptions eGlobalOptions = DRMGLOBALOPTIONS_USE_WINHTTP\n");
  if ( !g_fGlobalOptionUseWinhttp )
  {
    g_fGlobalOptionUseWinhttp = 1;
    goto LABEL_8;
  }
LABEL_3:
  v4 = -2147168396;
LABEL_10:
  LeaveCriticalSection(&g_csOptions);
  _RTLTRACE("[msdrm]:-DRMSetGlobalOptions HR=%x\n", v4);
  return v4;
}

```

## disassembly

```asm
0x180018fd0  push    rbx
0x180018fd2  sub     rsp, 20h
0x180018fd6  mov     ebx, ecx
0x180018fd8  lea     rcx, ?g_csOptions@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180018fdf  call    cs:__imp_EnterCriticalSection
0x180018fe5  test    ebx, ebx
0x180018fe7  jnz     short loc_180019010
0x180018fe9  lea     rcx, aMsdrmDrmsetglo_0; "[msdrm]:+DRMSetGlobalOptions eGlobalOpt"...
0x180018ff0  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180018ff5  cmp     cs:?g_fGlobalOptionUseWinhttp@@3HA, ebx; int g_fGlobalOptionUseWinhttp
0x180018ffb  jz      short loc_180019004
0x180018ffd  mov     ebx, 8004CF74h
0x180019002  jmp     short loc_180019039
0x180019004  mov     cs:?g_fGlobalOptionUseWinhttp@@3HA, 1; int g_fGlobalOptionUseWinhttp
0x18001900e  jmp     short loc_180019030
0x180019010  cmp     ebx, 1
0x180019013  jnz     short loc_180019034
0x180019015  lea     rcx, aMsdrmDrmsetglo; "[msdrm]:+DRMSetGlobalOptions eGlobalOpt"...
0x18001901c  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180019021  cmp     cs:?g_fGlobalOptionUseServerProc@@3HA, 0; int g_fGlobalOptionUseServerProc
0x180019028  jnz     short loc_180018FFD
0x18001902a  mov     cs:?g_fGlobalOptionUseServerProc@@3HA, ebx; int g_fGlobalOptionUseServerProc
0x180019030  xor     ebx, ebx
0x180019032  jmp     short loc_180019039
0x180019034  mov     ebx, 80070057h
0x180019039  lea     rcx, ?g_csOptions@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180019040  call    cs:__imp_LeaveCriticalSection
0x180019046  mov     edx, ebx
0x180019048  lea     rcx, aMsdrmDrmsetglo_1; "[msdrm]:-DRMSetGlobalOptions HR=%x\n"
0x18001904f  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180019054  mov     eax, ebx
0x180019056  add     rsp, 20h
0x18001905a  pop     rbx
0x18001905b  retn
```
