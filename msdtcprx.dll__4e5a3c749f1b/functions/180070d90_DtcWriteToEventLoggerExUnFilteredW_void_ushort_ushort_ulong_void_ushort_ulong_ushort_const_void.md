# DtcWriteToEventLoggerExUnFilteredW(void *,ushort,ushort,ulong,void *,ushort,ulong,ushort const * *,void *)

- ea: `0x180070d90`
- end: `0x180070f1e`
- name: `?DtcWriteToEventLoggerExUnFilteredW@@YAJPEAXGGK0GKPEAPEBG0@Z`
- size: `398`
- prototype: `__int64 __fastcall(void *, unsigned __int16, unsigned __int16, unsigned int, void *pv, unsigned __int16, size_t Size, LPCWSTR *, void *Src)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180070cd4`

## callees

- `0x18001de26`
- `0x180070d90`
- `0x1800773a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070ee1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070eea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070ee1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070eea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180070e2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180070e2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070ec9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070ec9`
- `ADVAPI32!ReportEventW` at `0x180070ebf`
- `ADVAPI32!ReportEventW` at `0x180070ebf`

## pseudocode

```c
__int64 __fastcall DtcWriteToEventLoggerExUnFilteredW(
        void *a1,
        char a2,
        WORD a3,
        DWORD a4,
        _WORD *pv,
        WORD wNumStrings,
        size_t Size,
        LPCWSTR *lpStrings,
        void *Src)
{
  WORD v9; // r13
  _WORD *v10; // rdi
  void *v11; // r15
  int ServiceNameFromTmInstance; // eax
  __int64 v13; // rax
  void *lpRawData; // rsi
  unsigned int v15; // r12d
  size_t dwDataSize; // rbp
  unsigned int v17; // ebx
  char *v18; // r14
  size_t v19; // rax
  size_t v20; // rbx
  unsigned int v21; // ebx
  signed int LastError; // eax

  v9 = a2 & 0x1F;
  pv = 0;
  v10 = 0;
  v11 = 0;
  if ( g_fEventSourceMsdtcCore
    && (ServiceNameFromTmInstance = GetServiceNameFromTmInstance(&pv), v10 = pv, ServiceNameFromTmInstance >= 0)
    && pv )
  {
    v13 = -1;
    do
      ++v13;
    while ( pv[v13] );
    lpRawData = Src;
    v15 = 2 * v13;
    dwDataSize = (unsigned int)Size;
    if ( Src )
      v17 = v15 + Size + 4;
    else
      v17 = 2 * v13;
    v18 = (char *)CoTaskMemAlloc(v17);
    if ( v18 )
    {
      v19 = dwDataSize;
      LODWORD(dwDataSize) = v17;
      v11 = v18;
      if ( lpRawData )
      {
        v20 = v19;
        memcpy_0(v18, lpRawData, v19);
        *(_DWORD *)&v18[v20] = 0;
        v18 += v20 + 4;
      }
      memcpy_0(v18, v10, v15);
      lpRawData = v11;
    }
  }
  else
  {
    lpRawData = Src;
    LODWORD(dwDataSize) = Size;
  }
  v21 = 0;
  if ( !ReportEventW(a1, v9, a3, a4, 0, wNumStrings, dwDataSize, lpStrings, lpRawData) )
  {
    LastError = GetLastError();
    v21 = LastError;
    if ( LastError > 0 )
      v21 = (unsigned __int16)LastError | 0x80070000;
  }
  CoTaskMemFree(v10);
  CoTaskMemFree(v11);
  return v21;
}

```

## disassembly

```asm
0x180070d90  mov     rax, rsp
0x180070d93  mov     [rax+10h], rbx
0x180070d97  mov     [rax+20h], r9d
0x180070d9b  mov     [rax+18h], r8w
0x180070da0  mov     [rax+8], rcx
0x180070da4  push    rbp
0x180070da5  push    rsi
0x180070da6  push    rdi
0x180070da7  push    r12
0x180070da9  push    r13
0x180070dab  push    r14
0x180070dad  push    r15
0x180070daf  sub     rsp, 50h
0x180070db3  xor     r14d, r14d
0x180070db6  movzx   r13d, dx
0x180070dba  and     r13w, 1Fh
0x180070dbf  mov     [rax+28h], r14
0x180070dc3  cmp     cs:?g_fEventSourceMsdtcCore@@3HA, r14d; int g_fEventSourceMsdtcCore
0x180070dca  mov     edi, r14d
0x180070dcd  mov     r15d, r14d
0x180070dd0  jz      loc_180070F0A
0x180070dd6  lea     rcx, [rax+28h]; unsigned __int16 **
0x180070dda  call    ?GetServiceNameFromTmInstance@@YAJPEAPEAG@Z; GetServiceNameFromTmInstance(ushort * *)
0x180070ddf  mov     rdi, [rsp+88h+pv]
0x180070de7  test    eax, eax
0x180070de9  js      loc_180070F0A
0x180070def  test    rdi, rdi
0x180070df2  jz      loc_180070F0A
0x180070df8  or      rax, 0FFFFFFFFFFFFFFFFh
0x180070dfc  inc     rax
0x180070dff  cmp     [rdi+rax*2], r14w
0x180070e04  jnz     short loc_180070DFC
0x180070e06  mov     rsi, [rsp+88h+Src]
0x180070e0e  lea     r12d, [rax+rax]
0x180070e12  mov     ebp, dword ptr [rsp+88h+Size]
0x180070e19  test    rsi, rsi
0x180070e1c  jz      short loc_180070E26
0x180070e1e  lea     ebx, [rbp+4]
0x180070e21  add     ebx, r12d
0x180070e24  jmp     short loc_180070E29
0x180070e26  mov     ebx, r12d
0x180070e29  mov     ecx, ebx; cb
0x180070e2b  call    cs:__imp_CoTaskMemAlloc
0x180070e31  mov     r14, rax
0x180070e34  test    rax, rax
0x180070e37  jz      short loc_180070E74
0x180070e39  mov     rax, rbp
0x180070e3c  mov     ebp, ebx
0x180070e3e  mov     r15, r14
0x180070e41  test    rsi, rsi
0x180070e44  jz      short loc_180070E63
0x180070e46  mov     r8, rax; Size
0x180070e49  mov     rdx, rsi; Src
0x180070e4c  mov     rcx, r14; void *
0x180070e4f  mov     rbx, rax
0x180070e52  call    memcpy_0
0x180070e57  lea     rax, [rbx+r14]
0x180070e5b  xor     ecx, ecx
0x180070e5d  mov     [rax], ecx
0x180070e5f  lea     r14, [rax+4]
0x180070e63  mov     r8d, r12d; Size
0x180070e66  mov     rdx, rdi; Src
0x180070e69  mov     rcx, r14; void *
0x180070e6c  call    memcpy_0
0x180070e71  mov     rsi, r15
0x180070e74  xor     r14d, r14d
0x180070e77  mov     rax, [rsp+88h+arg_38]
0x180070e7f  movzx   edx, r13w; wType
0x180070e83  mov     r9d, [rsp+88h+dwEventID]; dwEventID
0x180070e8b  mov     ebx, r14d
0x180070e8e  movzx   r8d, [rsp+88h+arg_10]; wCategory
0x180070e97  mov     rcx, [rsp+88h+hEventLog]; hEventLog
0x180070e9f  mov     [rsp+88h+lpRawData], rsi; lpRawData
0x180070ea4  mov     [rsp+88h+lpStrings], rax; lpStrings
0x180070ea9  movzx   eax, [rsp+88h+arg_28]
0x180070eb1  mov     [rsp+88h+dwDataSize], ebp; dwDataSize
0x180070eb5  mov     [rsp+88h+wNumStrings], ax; wNumStrings
0x180070eba  mov     [rsp+88h+lpUserSid], r14; lpUserSid
0x180070ebf  call    cs:__imp_ReportEventW
0x180070ec5  test    eax, eax
0x180070ec7  jnz     short loc_180070EDE
0x180070ec9  call    cs:__imp_GetLastError
0x180070ecf  mov     ebx, eax
0x180070ed1  test    eax, eax
0x180070ed3  jle     short loc_180070EDE
0x180070ed5  movzx   ebx, ax
0x180070ed8  or      ebx, 80070000h
0x180070ede  mov     rcx, rdi; pv
0x180070ee1  call    cs:__imp_CoTaskMemFree
0x180070ee7  mov     rcx, r15; pv
0x180070eea  call    cs:__imp_CoTaskMemFree
0x180070ef0  mov     eax, ebx
0x180070ef2  mov     rbx, [rsp+88h+arg_8]
0x180070efa  add     rsp, 50h
0x180070efe  pop     r15
0x180070f00  pop     r14
0x180070f02  pop     r13
0x180070f04  pop     r12
0x180070f06  pop     rdi
0x180070f07  pop     rsi
0x180070f08  pop     rbp
0x180070f09  retn
0x180070f0a  mov     rsi, [rsp+88h+Src]
0x180070f12  mov     ebp, dword ptr [rsp+88h+Size]
0x180070f19  jmp     loc_180070E77
```
