# FREB_XML_SERIALIZER::Initialize(void)

- ea: `0x1800097c4`
- end: `0x18000993f`
- name: `?Initialize@FREB_XML_SERIALIZER@@SAJXZ`
- size: `379`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180003130`

## callees

- `0x180001008`
- `0x180001048`
- `0x1800097c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009806`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000985f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009806`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000985f`
- `api-ms-win-core-localization-l1-2-2!GetSystemDefaultLocaleName` at `0x1800098b0`
- `api-ms-win-core-localization-l1-2-2!GetSystemDefaultLocaleName` at `0x1800098b0`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800097f8`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180009855`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800097f8`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180009855`

## pseudocode

```c
__int64 FREB_XML_SERIALIZER::Initialize(void)
{
  unsigned __int16 *v0; // rax
  signed int LastError; // eax
  unsigned int v2; // ebx
  DWORD nSize; // [rsp+30h] [rbp+8h] BYREF

  nSize = 16;
  v0 = (unsigned __int16 *)operator new(0x20u);
  FREB_XML_SERIALIZER::sm_pszComputerName = v0;
  if ( !v0 )
    goto LABEL_16;
  if ( GetComputerNameW(v0, &nSize) )
    goto LABEL_11;
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError != 111 )
    goto LABEL_7;
  operator delete(FREB_XML_SERIALIZER::sm_pszComputerName);
  v0 = (unsigned __int16 *)operator new(saturated_mul(++nSize, 2u));
  FREB_XML_SERIALIZER::sm_pszComputerName = v0;
  if ( !v0 )
  {
LABEL_16:
    v2 = -2147024882;
    goto LABEL_17;
  }
  if ( GetComputerNameW(v0, &nSize) )
  {
LABEL_11:
    nSize = 32;
    FREB_XML_SERIALIZER::sm_pszSystemLocale = (LPWSTR)operator new(0x40u);
    if ( FREB_XML_SERIALIZER::sm_pszSystemLocale )
    {
      v2 = 0;
      while ( !GetSystemDefaultLocaleName(FREB_XML_SERIALIZER::sm_pszSystemLocale, nSize) )
      {
        operator delete(FREB_XML_SERIALIZER::sm_pszSystemLocale);
        nSize *= 2;
        FREB_XML_SERIALIZER::sm_pszSystemLocale = (LPWSTR)operator new(saturated_mul(nSize, 2u));
        if ( !FREB_XML_SERIALIZER::sm_pszSystemLocale )
          goto LABEL_15;
      }
      return v2;
    }
LABEL_15:
    v0 = FREB_XML_SERIALIZER::sm_pszComputerName;
    goto LABEL_16;
  }
  LastError = GetLastError();
  v2 = LastError;
LABEL_7:
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  if ( (v2 & 0x80000000) != 0 )
  {
    v0 = FREB_XML_SERIALIZER::sm_pszComputerName;
LABEL_17:
    if ( v0 )
    {
      operator delete(v0);
      FREB_XML_SERIALIZER::sm_pszComputerName = 0;
    }
    if ( FREB_XML_SERIALIZER::sm_pszSystemLocale )
    {
      operator delete(FREB_XML_SERIALIZER::sm_pszSystemLocale);
      FREB_XML_SERIALIZER::sm_pszSystemLocale = 0;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800097c4  mov     [rsp+arg_8], rbx
0x1800097c9  push    rbp
0x1800097ca  sub     rsp, 20h
0x1800097ce  mov     ecx, 20h ; ' '; Size
0x1800097d3  mov     [rsp+28h+nSize], 10h
0x1800097db  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800097e0  mov     cs:?sm_pszComputerName@FREB_XML_SERIALIZER@@0PEAGEA, rax; ushort * FREB_XML_SERIALIZER::sm_pszComputerName
0x1800097e7  test    rax, rax
0x1800097ea  jz      loc_1800098F9
0x1800097f0  lea     rdx, [rsp+28h+nSize]; nSize
0x1800097f5  mov     rcx, rax; lpBuffer
0x1800097f8  call    cs:__imp_GetComputerNameW
0x1800097fe  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180009802  test    eax, eax
0x180009804  jnz     short loc_180009885
0x180009806  call    cs:__imp_GetLastError
0x18000980c  mov     ebx, eax
0x18000980e  cmp     eax, 6Fh ; 'o'
0x180009811  jnz     short loc_180009867
0x180009813  mov     rcx, cs:?sm_pszComputerName@FREB_XML_SERIALIZER@@0PEAGEA; Block
0x18000981a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000981f  mov     eax, [rsp+28h+nSize]
0x180009823  inc     eax
0x180009825  mov     ecx, eax
0x180009827  mov     [rsp+28h+nSize], eax
0x18000982b  lea     eax, [rbp+3]
0x18000982e  mul     rcx
0x180009831  cmovb   rax, rbp
0x180009835  mov     rcx, rax; Size
0x180009838  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000983d  mov     cs:?sm_pszComputerName@FREB_XML_SERIALIZER@@0PEAGEA, rax; ushort * FREB_XML_SERIALIZER::sm_pszComputerName
0x180009844  test    rax, rax
0x180009847  jz      loc_1800098F9
0x18000984d  lea     rdx, [rsp+28h+nSize]; nSize
0x180009852  mov     rcx, rax; lpBuffer
0x180009855  call    cs:__imp_GetComputerNameW
0x18000985b  test    eax, eax
0x18000985d  jnz     short loc_180009885
0x18000985f  call    cs:__imp_GetLastError
0x180009865  mov     ebx, eax
0x180009867  test    eax, eax
0x180009869  jle     short loc_180009874
0x18000986b  movzx   ebx, ax
0x18000986e  or      ebx, 80070000h
0x180009874  test    ebx, ebx
0x180009876  jns     loc_180009932
0x18000987c  mov     rax, cs:?sm_pszComputerName@FREB_XML_SERIALIZER@@0PEAGEA; ushort * FREB_XML_SERIALIZER::sm_pszComputerName
0x180009883  jmp     short loc_1800098FE
0x180009885  mov     ecx, 40h ; '@'; Size
0x18000988a  mov     [rsp+28h+nSize], 20h ; ' '
0x180009892  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009897  mov     cs:?sm_pszSystemLocale@FREB_XML_SERIALIZER@@0PEAGEA, rax; ushort * FREB_XML_SERIALIZER::sm_pszSystemLocale
0x18000989e  test    rax, rax
0x1800098a1  jz      short loc_1800098F2
0x1800098a3  xor     ebx, ebx
0x1800098a5  mov     edx, [rsp+28h+nSize]; cchLocaleName
0x1800098a9  mov     rcx, cs:?sm_pszSystemLocale@FREB_XML_SERIALIZER@@0PEAGEA; lpLocaleName
0x1800098b0  call    cs:__imp_GetSystemDefaultLocaleName
0x1800098b6  test    eax, eax
0x1800098b8  jnz     short loc_180009932
0x1800098ba  mov     rcx, cs:?sm_pszSystemLocale@FREB_XML_SERIALIZER@@0PEAGEA; Block
0x1800098c1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800098c6  mov     eax, [rsp+28h+nSize]
0x1800098ca  add     eax, eax
0x1800098cc  mov     ecx, eax
0x1800098ce  mov     [rsp+28h+nSize], eax
0x1800098d2  mov     eax, 2
0x1800098d7  mul     rcx
0x1800098da  cmovb   rax, rbp
0x1800098de  mov     rcx, rax; Size
0x1800098e1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800098e6  mov     cs:?sm_pszSystemLocale@FREB_XML_SERIALIZER@@0PEAGEA, rax; ushort * FREB_XML_SERIALIZER::sm_pszSystemLocale
0x1800098ed  test    rax, rax
0x1800098f0  jnz     short loc_1800098A5
0x1800098f2  mov     rax, cs:?sm_pszComputerName@FREB_XML_SERIALIZER@@0PEAGEA; ushort * FREB_XML_SERIALIZER::sm_pszComputerName
0x1800098f9  mov     ebx, 8007000Eh
0x1800098fe  test    rax, rax
0x180009901  jz      short loc_180009916
0x180009903  mov     rcx, rax; Block
0x180009906  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000990b  mov     cs:?sm_pszComputerName@FREB_XML_SERIALIZER@@0PEAGEA, 0; ushort * FREB_XML_SERIALIZER::sm_pszComputerName
0x180009916  mov     rcx, cs:?sm_pszSystemLocale@FREB_XML_SERIALIZER@@0PEAGEA; Block
0x18000991d  test    rcx, rcx
0x180009920  jz      short loc_180009932
0x180009922  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009927  mov     cs:?sm_pszSystemLocale@FREB_XML_SERIALIZER@@0PEAGEA, 0; ushort * FREB_XML_SERIALIZER::sm_pszSystemLocale
0x180009932  mov     eax, ebx
0x180009934  mov     rbx, [rsp+28h+arg_8]
0x180009939  add     rsp, 20h
0x18000993d  pop     rbp
0x18000993e  retn
```
