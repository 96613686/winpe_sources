# CActivityID::getCurrentCActivityID(CActivityID * const)

- ea: `0x100407300`
- end: `0x100407509`
- name: `?getCurrentCActivityID@CActivityID@@SAHQEAU1@@Z`
- size: `521`
- prototype: `__int64 __fastcall(UUID *Uuid)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x100407510`
- `0x1004622fc`

## callees

- `0x100407300`
- `0x100546aa8`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1004073da`
- `KERNEL32!GetLastError` at `0x10040748f`
- `KERNEL32!GetLastError` at `0x1004074b0`
- `KERNEL32!GetLastError` at `0x1004073da`
- `KERNEL32!GetLastError` at `0x10040748f`
- `KERNEL32!GetLastError` at `0x1004074b0`
- `KERNEL32!TlsGetValue` at `0x1004073c2`
- `KERNEL32!TlsGetValue` at `0x1004073c2`
- `KERNEL32!TlsSetValue` at `0x100407484`
- `KERNEL32!TlsSetValue` at `0x100407484`
- `RPCRT4!UuidCreate` at `0x100407455`
- `RPCRT4!UuidCreate` at `0x100407455`

## pseudocode

```c
__int64 __fastcall CActivityID::getCurrentCActivityID(UUID *Uuid)
{
  wchar_t *v2; // r9
  __int64 v3; // r8
  unsigned int Value; // eax
  __int64 (*v5)(void); // rbp
  unsigned int v6; // esi
  DWORD LastError; // eax
  wchar_t *v8; // r8
  __int64 v9; // rdx
  GUID v11; // [rsp+30h] [rbp-28h] BYREF

  if ( !g_pfnEventActivityIdControl )
  {
    if ( (bidGblFlags & 2) == 0 || !off_1005E43A8[0] || bidID == -1 )
      return 0;
    v2 = off_1005E43A8[0];
    v3 = 1932288;
    goto LABEL_11;
  }
  if ( g_dwCorrelationIndex == -1 )
  {
    if ( (bidGblFlags & 2) == 0 || !off_1005E43B0[0] || bidID == -1 )
      return 0;
    v2 = off_1005E43B0[0];
    v3 = 1938432;
LABEL_11:
    ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0)(bidID, 0, v3, v2, 0);
    return 0;
  }
  Value = (unsigned int)TlsGetValue(g_dwCorrelationIndex);
  v5 = g_pfnEventActivityIdControl;
  v6 = Value;
  if ( Value )
  {
    if ( !(unsigned int)((__int64 (__fastcall *)(__int64, UUID *))g_pfnEventActivityIdControl)(1, Uuid) )
    {
      Uuid[1].Data1 = v6;
      return 1;
    }
LABEL_26:
    LastError = GetLastError();
    if ( (bidGblFlags & 2) == 0 || !off_1005E43C0[0] )
      return 0;
    v8 = off_1005E43C0[0];
    v9 = 1986560;
LABEL_17:
    bidTraceW(0, v9, v8, LastError);
    return 0;
  }
  LastError = GetLastError();
  if ( LastError )
  {
    if ( (bidGblFlags & 2) == 0 || !off_1005E43B8[0] )
      return 0;
    v8 = off_1005E43B8[0];
    v9 = 1950720;
    goto LABEL_17;
  }
  v11 = GUID_NULL;
  ((void (__fastcall *)(__int64, GUID *))v5)(1, &v11);
  if ( *(_OWORD *)&v11 == *(_OWORD *)&GUID_NULL
    && (UuidCreate(Uuid) || ((unsigned int (__fastcall *)(__int64, UUID *))v5)(2, Uuid)) )
  {
    goto LABEL_26;
  }
  Uuid[1].Data1 = 1;
  if ( !TlsSetValue(g_dwCorrelationIndex, (LPVOID)1) )
  {
    if ( GetLastError() )
      goto LABEL_26;
  }
  return 1;
}

```

## disassembly

```asm
0x100407300  mov     [rsp+arg_8], rbp
0x100407305  mov     [rsp+arg_10], rsi
0x10040730a  push    rdi
0x10040730b  sub     rsp, 50h
0x10040730f  mov     rax, cs:__security_cookie
0x100407316  xor     rax, rsp
0x100407319  mov     [rsp+58h+var_18], rax
0x10040731e  cmp     cs:?g_pfnEventActivityIdControl@@3P6A_JXZEA, 0; __int64 (*g_pfnEventActivityIdControl)(void)
0x100407326  mov     rdi, rcx
0x100407329  jnz     short loc_100407365
0x10040732b  test    byte ptr cs:_bidGblFlags, 2
0x100407332  jz      loc_10040740F
0x100407338  mov     rax, cs:off_1005E43A8; "<CActivityID::getCurrentCActivityID|ERR"...
0x10040733f  test    rax, rax
0x100407342  jz      loc_10040740F
0x100407348  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x100407350  jz      loc_10040740F
0x100407356  mov     r9, cs:off_1005E43A8; "<CActivityID::getCurrentCActivityID|ERR"...
0x10040735d  mov     r8d, 1D7C00h
0x100407363  jmp     short loc_1004073A4
0x100407365  mov     ecx, cs:?g_dwCorrelationIndex@@3VThreadLocalKey@@A; dwTlsIndex
0x10040736b  cmp     ecx, 0FFFFFFFFh
0x10040736e  jnz     short loc_1004073C2
0x100407370  test    byte ptr cs:_bidGblFlags, 2
0x100407377  jz      loc_10040740F
0x10040737d  mov     rax, cs:off_1005E43B0; "<CActivityID::getCurrentCActivityID|ERR"...
0x100407384  test    rax, rax
0x100407387  jz      loc_10040740F
0x10040738d  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x100407395  jz      short loc_10040740F
0x100407397  mov     r9, cs:off_1005E43B0; "<CActivityID::getCurrentCActivityID|ERR"...
0x10040739e  mov     r8d, 1D9400h
0x1004073a4  and     [rsp+58h+var_38], 0
0x1004073aa  xor     edx, edx
0x1004073ac  mov     rax, cs:off_1005D39E0
0x1004073b3  mov     rcx, cs:_bidID
0x1004073ba  call    cs:__guard_dispatch_icall_fptr
0x1004073c0  jmp     short loc_10040740F
0x1004073c2  call    cs:__imp_TlsGetValue
0x1004073c8  mov     rbp, cs:?g_pfnEventActivityIdControl@@3P6A_JXZEA; __int64 (*g_pfnEventActivityIdControl)(void)
0x1004073cf  mov     rsi, rax
0x1004073d2  test    eax, eax
0x1004073d4  jnz     loc_10040749B
0x1004073da  call    cs:__imp_GetLastError
0x1004073e0  test    eax, eax
0x1004073e2  jz      short loc_100407416
0x1004073e4  test    byte ptr cs:_bidGblFlags, 2
0x1004073eb  jz      short loc_10040740F
0x1004073ed  mov     rcx, cs:off_1005E43B8; "<CActivityID::getCurrentCActivityID|ERR"...
0x1004073f4  test    rcx, rcx
0x1004073f7  jz      short loc_10040740F
0x1004073f9  mov     r8, cs:off_1005E43B8; "<CActivityID::getCurrentCActivityID|ERR"...
0x100407400  mov     edx, 1DC400h
0x100407405  mov     r9d, eax
0x100407408  xor     ecx, ecx
0x10040740a  call    _bidTraceW
0x10040740f  xor     eax, eax
0x100407411  jmp     loc_1004074EC
0x100407416  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x10040741d  lea     rdx, [rsp+58h+var_28]
0x100407422  mov     ecx, 1
0x100407427  mov     rax, rbp
0x10040742a  movdqu  [rsp+58h+var_28], xmm0
0x100407430  call    cs:__guard_dispatch_icall_fptr
0x100407436  mov     rax, qword ptr [rsp+58h+var_28]
0x10040743b  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x100407442  jnz     short loc_100407472
0x100407444  mov     rax, qword ptr [rsp+58h+var_28+8]
0x100407449  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x100407450  jnz     short loc_100407472
0x100407452  mov     rcx, rdi; Uuid
0x100407455  call    cs:__imp_UuidCreate
0x10040745b  test    eax, eax
0x10040745d  jnz     short loc_1004074B0
0x10040745f  lea     ecx, [rax+2]
0x100407462  mov     rdx, rdi
0x100407465  mov     rax, rbp
0x100407468  call    cs:__guard_dispatch_icall_fptr
0x10040746e  test    eax, eax
0x100407470  jnz     short loc_1004074B0
0x100407472  mov     dword ptr [rdi+10h], 1
0x100407479  mov     edx, 1; lpTlsValue
0x10040747e  mov     ecx, cs:?g_dwCorrelationIndex@@3VThreadLocalKey@@A; dwTlsIndex
0x100407484  call    cs:__imp_TlsSetValue
0x10040748a  cmp     eax, 1
0x10040748d  jz      short loc_1004074E7
0x10040748f  call    cs:__imp_GetLastError
0x100407495  test    eax, eax
0x100407497  jnz     short loc_1004074B0
0x100407499  jmp     short loc_1004074E7
0x10040749b  mov     rdx, rdi
0x10040749e  mov     ecx, 1
0x1004074a3  mov     rax, rbp
0x1004074a6  call    cs:__guard_dispatch_icall_fptr
0x1004074ac  test    eax, eax
0x1004074ae  jz      short loc_1004074E4
0x1004074b0  call    cs:__imp_GetLastError
0x1004074b6  test    byte ptr cs:_bidGblFlags, 2
0x1004074bd  jz      loc_10040740F
0x1004074c3  mov     rcx, cs:off_1005E43C0; "<CActivityID::getCurrentCActivityID|ERR"...
0x1004074ca  test    rcx, rcx
0x1004074cd  jz      loc_10040740F
0x1004074d3  mov     r8, cs:off_1005E43C0; "<CActivityID::getCurrentCActivityID|ERR"...
0x1004074da  mov     edx, 1E5000h
0x1004074df  jmp     loc_100407405
0x1004074e4  mov     [rdi+10h], esi
0x1004074e7  mov     eax, 1
0x1004074ec  mov     rcx, [rsp+58h+var_18]
0x1004074f1  xor     rcx, rsp; StackCookie
0x1004074f4  call    __security_check_cookie
0x1004074f9  mov     rbp, [rsp+58h+arg_8]
0x1004074fe  mov     rsi, [rsp+58h+arg_10]
0x100407503  add     rsp, 50h
0x100407507  pop     rdi
0x100407508  retn
```
