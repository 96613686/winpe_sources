# CMsmqVssWriter::RestoreRegistryKey(wchar_t const *,void *,HKEY__ * *)

- ea: `0x180092ec4`
- end: `0x180093185`
- name: `?RestoreRegistryKey@CMsmqVssWriter@@AEAAJPEB_WPEAXPEAPEAUHKEY__@@@Z`
- size: `705`
- prototype: `int(CMsmqVssWriter *__hidden this, const wchar_t *, void *, HKEY *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180092cb8`

## callees

- `0x18000cb80`
- `0x18002c61c`
- `0x18003c644`
- `0x180092ec4`
- `0x18009bd1c`

## import_xrefs

- `msvcrt!free` at `0x1800930e7`
- `msvcrt!free` at `0x180093117`
- `msvcrt!free` at `0x18009313e`
- `msvcrt!free` at `0x1800930e7`
- `msvcrt!free` at `0x180093117`
- `msvcrt!free` at `0x18009313e`
- `ADVAPI32!RegEnumValueW` at `0x180093096`
- `ADVAPI32!RegEnumValueW` at `0x180093096`
- `ADVAPI32!RegDeleteValueW` at `0x1800930b4`
- `ADVAPI32!RegDeleteValueW` at `0x1800930b4`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180093001`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180093001`
- `ADVAPI32!RegCreateKeyExW` at `0x180092f96`
- `ADVAPI32!RegCreateKeyExW` at `0x180092f96`
- `ADVAPI32!RegCreateKeyTransactedW` at `0x180092f72`
- `ADVAPI32!RegCreateKeyTransactedW` at `0x180092f72`

## string_xrefs

- `0x180093026`: `writer/mqwriter`
- `0x1800930d5`: `writer/mqwriter`
- `0x180093105`: `writer/mqwriter`
- `0x18009315d`: `writer/mqwriter`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CMsmqVssWriter::RestoreRegistryKey(CMsmqVssWriter *this, const wchar_t *a2, void *a3, HKEY *a4)
{
  unsigned __int16 v7; // r8
  unsigned int v8; // eax
  const WCHAR *v9; // rdx
  LSTATUS KeyTransactedW; // eax
  unsigned int v11; // ebx
  bool v12; // sf
  unsigned __int16 v13; // r8
  LSTATUS v14; // eax
  WCHAR *v15; // rbx
  LSTATUS v16; // eax
  signed int v17; // edi
  LSTATUS v18; // eax
  DWORD cchValueName; // [rsp+60h] [rbp-20h] BYREF
  HKEY hKey[3]; // [rsp+68h] [rbp-18h] BYREF
  CMsmqVssWriter *cbMaxValueNameLen; // [rsp+A0h] [rbp+20h] BYREF
  DWORD cValues; // [rsp+A8h] [rbp+28h] BYREF

  cbMaxValueNameLen = this;
  if ( !a2 )
  {
    v7 = 2180;
LABEL_40:
    v11 = -1072824314;
    LogMsgHR(-1072824314, (wchar_t *)L"writer/mqwriter", v7);
    return v11;
  }
  v8 = mqwcslen(a2);
  if ( v8 < 3 || *a2 != 91 || a2[v8 - 1] != 93 )
  {
    v7 = 2200;
    goto LABEL_40;
  }
  v9 = a2 + 1;
  a2[v8 - 1] = 0;
  hKey[0] = 0;
  if ( a3 )
    KeyTransactedW = RegCreateKeyTransactedW(HKEY_LOCAL_MACHINE, v9, 0, 0, 0, 0xF003Fu, 0, hKey, 0, a3, 0);
  else
    KeyTransactedW = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v9, 0, 0, 0, 0xF003Fu, 0, hKey, 0);
  v11 = KeyTransactedW;
  v12 = KeyTransactedW < 0;
  if ( KeyTransactedW )
  {
    if ( KeyTransactedW > 0 )
    {
      v11 = (unsigned __int16)KeyTransactedW | 0x80070000;
      v12 = 1;
    }
    if ( !v12 )
      goto LABEL_35;
    v13 = 2220;
LABEL_19:
    LogMsgHR(v11, (wchar_t *)L"writer/mqwriter", v13);
LABEL_35:
    CRegHandle::~CRegHandle((CRegHandle *)hKey);
    return v11;
  }
  cValues = 0;
  LODWORD(cbMaxValueNameLen) = 0;
  v14 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, 0, 0, 0, &cValues, (LPDWORD)&cbMaxValueNameLen, 0, 0, 0);
  v11 = v14;
  if ( v14 )
  {
    if ( v14 > 0 )
      v11 = (unsigned __int16)v14 | 0x80070000;
    if ( (v11 & 0x80000000) == 0 )
      goto LABEL_35;
    v13 = 2240;
    goto LABEL_19;
  }
  LODWORD(cbMaxValueNameLen) = (_DWORD)cbMaxValueNameLen + 1;
  v15 = (WCHAR *)MmAllocate(saturated_mul((unsigned int)cbMaxValueNameLen, 2u));
  hKey[1] = (HKEY)v15;
  while ( cValues )
  {
    cchValueName = (unsigned int)cbMaxValueNameLen;
    v16 = RegEnumValueW(hKey[0], 0, v15, &cchValueName, 0, 0, 0, 0);
    v17 = v16;
    if ( v16 == 259 )
      break;
    if ( v16 )
    {
      if ( v16 > 0 )
        v17 = (unsigned __int16)v16 | 0x80070000;
      if ( v17 < 0 )
        LogMsgHR(v17, (wchar_t *)L"writer/mqwriter", 0x8D4u);
      goto LABEL_34;
    }
    v18 = RegDeleteValueW(hKey[0], v15);
    v17 = v18;
    if ( v18 )
    {
      if ( v18 > 0 )
        v17 = (unsigned __int16)v18 | 0x80070000;
      if ( v17 < 0 )
        LogMsgHR(v17, (wchar_t *)L"writer/mqwriter", 0x8E8u);
LABEL_34:
      free(v15);
      v11 = v17;
      goto LABEL_35;
    }
  }
  if ( a4 )
  {
    *a4 = hKey[0];
    hKey[0] = 0;
  }
  free(v15);
  CRegHandle::~CRegHandle((CRegHandle *)hKey);
  return 0;
}

```

## disassembly

```asm
0x180092ec4  mov     [rsp-18h+arg_10], rbx
0x180092ec9  mov     [rsp-18h+arg_18], rsi
0x180092ece  mov     [rsp-18h+cbMaxValueNameLen], rcx
0x180092ed3  push    rbp
0x180092ed4  push    rdi
0x180092ed5  push    r14
0x180092ed7  mov     rbp, rsp
0x180092eda  sub     rsp, 80h
0x180092ee1  mov     rsi, r9
0x180092ee4  mov     rdi, r8
0x180092ee7  mov     rbx, rdx
0x180092eea  xor     r14d, r14d
0x180092eed  test    rdx, rdx
0x180092ef0  jnz     short loc_180092EFD
0x180092ef2  mov     r8d, 884h
0x180092ef8  jmp     loc_180093158
0x180092efd  mov     rcx, rbx; wchar_t *
0x180092f00  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180092f05  cmp     eax, 3
0x180092f08  jb      loc_180093152
0x180092f0e  cmp     word ptr [rbx], 5Bh ; '['
0x180092f12  jnz     loc_180093152
0x180092f18  lea     ecx, [rax-1]
0x180092f1b  cmp     word ptr [rbx+rcx*2], 5Dh ; ']'
0x180092f20  jnz     loc_180093152
0x180092f26  lea     rdx, [rbx+2]; lpSubKey
0x180092f2a  add     eax, 0FFFFFFFEh
0x180092f2d  mov     [rdx+rax*2], r14w
0x180092f32  mov     [rbp+hKey], r14
0x180092f36  lea     rax, [rbp+hKey]
0x180092f3a  xor     r9d, r9d; lpClass
0x180092f3d  xor     r8d, r8d; Reserved
0x180092f40  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180092f47  test    rdi, rdi
0x180092f4a  jz      short loc_180092F7A
0x180092f4c  mov     [rsp+80h+pExtendedParemeter], r14; pExtendedParemeter
0x180092f51  mov     [rsp+80h+hTransaction], rdi; hTransaction
0x180092f56  mov     [rsp+80h+lpdwDisposition], r14; lpdwDisposition
0x180092f5b  mov     [rsp+80h+phkResult], rax; phkResult
0x180092f60  mov     [rsp+80h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180092f65  mov     [rsp+80h+samDesired], 0F003Fh; samDesired
0x180092f6d  mov     [rsp+80h+dwOptions], r14d; dwOptions
0x180092f72  call    cs:__imp_RegCreateKeyTransactedW
0x180092f78  jmp     short loc_180092F9C
0x180092f7a  mov     [rsp+80h+lpdwDisposition], r14; lpdwDisposition
0x180092f7f  mov     [rsp+80h+phkResult], rax; phkResult
0x180092f84  mov     [rsp+80h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180092f89  mov     [rsp+80h+samDesired], 0F003Fh; samDesired
0x180092f91  mov     [rsp+80h+dwOptions], r14d; dwOptions
0x180092f96  call    cs:__imp_RegCreateKeyExW
0x180092f9c  mov     ebx, eax
0x180092f9e  test    eax, eax
0x180092fa0  jz      short loc_180092FBD
0x180092fa2  jle     short loc_180092FAF
0x180092fa4  movzx   ebx, bx
0x180092fa7  or      ebx, 80070000h
0x180092fad  test    ebx, ebx
0x180092faf  jns     loc_180093120
0x180092fb5  mov     r8d, 8ACh
0x180092fbb  jmp     short loc_180093026
0x180092fbd  mov     [rbp+cValues], r14d
0x180092fc1  mov     dword ptr [rbp+cbMaxValueNameLen], r14d
0x180092fc5  mov     [rsp+80h+lpftLastWriteTime], r14; lpftLastWriteTime
0x180092fca  mov     [rsp+80h+pExtendedParemeter], r14; lpcbSecurityDescriptor
0x180092fcf  mov     [rsp+80h+hTransaction], r14; lpcbMaxValueLen
0x180092fd4  lea     rax, [rbp+cbMaxValueNameLen]
0x180092fd8  mov     [rsp+80h+lpdwDisposition], rax; lpcbMaxValueNameLen
0x180092fdd  lea     rax, [rbp+cValues]
0x180092fe1  mov     [rsp+80h+phkResult], rax; lpcValues
0x180092fe6  mov     [rsp+80h+lpSecurityAttributes], r14; lpcbMaxClassLen
0x180092feb  mov     qword ptr [rsp+80h+samDesired], r14; lpcbMaxSubKeyLen
0x180092ff0  mov     qword ptr [rsp+80h+dwOptions], r14; lpcSubKeys
0x180092ff5  xor     r9d, r9d; lpReserved
0x180092ff8  xor     r8d, r8d; lpcchClass
0x180092ffb  xor     edx, edx; lpClass
0x180092ffd  mov     rcx, [rbp+hKey]; hKey
0x180093001  call    cs:__imp_RegQueryInfoKeyW
0x180093007  mov     ebx, eax
0x180093009  test    eax, eax
0x18009300b  jz      short loc_180093039
0x18009300d  jle     short loc_180093018
0x18009300f  movzx   ebx, ax
0x180093012  or      ebx, 80070000h
0x180093018  test    ebx, ebx
0x18009301a  jns     loc_180093120
0x180093020  mov     r8d, 8C0h; unsigned __int16
0x180093026  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18009302d  mov     ecx, ebx; int
0x18009302f  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180093034  jmp     loc_180093120
0x180093039  mov     eax, dword ptr [rbp+cbMaxValueNameLen]
0x18009303c  inc     eax
0x18009303e  mov     dword ptr [rbp+cbMaxValueNameLen], eax
0x180093041  mov     ecx, eax
0x180093043  mov     eax, 2
0x180093048  mul     rcx
0x18009304b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180093052  cmovb   rax, rcx
0x180093056  mov     rcx, rax; unsigned __int64
0x180093059  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18009305e  mov     rbx, rax
0x180093061  mov     [rbp+var_10], rax
0x180093065  cmp     [rbp+cValues], r14d
0x180093069  jbe     loc_18009312B
0x18009306f  mov     eax, dword ptr [rbp+cbMaxValueNameLen]
0x180093072  mov     [rbp+cchValueName], eax
0x180093075  mov     [rsp+80h+phkResult], r14; lpcbData
0x18009307a  mov     [rsp+80h+lpSecurityAttributes], r14; lpData
0x18009307f  mov     qword ptr [rsp+80h+samDesired], r14; lpType
0x180093084  mov     qword ptr [rsp+80h+dwOptions], r14; lpReserved
0x180093089  lea     r9, [rbp+cchValueName]; lpcchValueName
0x18009308d  mov     r8, rbx; lpValueName
0x180093090  xor     edx, edx; dwIndex
0x180093092  mov     rcx, [rbp+hKey]; hKey
0x180093096  call    cs:__imp_RegEnumValueW
0x18009309c  mov     edi, eax
0x18009309e  cmp     eax, 103h
0x1800930a3  jz      loc_18009312B
0x1800930a9  test    eax, eax
0x1800930ab  jnz     short loc_1800930F0
0x1800930ad  mov     rdx, rbx; lpValueName
0x1800930b0  mov     rcx, [rbp+hKey]; hKey
0x1800930b4  call    cs:__imp_RegDeleteValueW
0x1800930ba  mov     edi, eax
0x1800930bc  test    eax, eax
0x1800930be  jz      short loc_180093065
0x1800930c0  jle     short loc_1800930CB
0x1800930c2  movzx   edi, ax
0x1800930c5  or      edi, 80070000h
0x1800930cb  test    edi, edi
0x1800930cd  jns     short loc_1800930E4
0x1800930cf  mov     r8d, 8E8h; unsigned __int16
0x1800930d5  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x1800930dc  mov     ecx, edi; int
0x1800930de  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800930e3  nop
0x1800930e4  mov     rcx, rbx; Block
0x1800930e7  call    cs:__imp_free
0x1800930ed  nop
0x1800930ee  jmp     short loc_18009311E
0x1800930f0  jle     short loc_1800930FB
0x1800930f2  movzx   edi, ax
0x1800930f5  or      edi, 80070000h
0x1800930fb  test    edi, edi
0x1800930fd  jns     short loc_180093114
0x1800930ff  mov     r8d, 8D4h; unsigned __int16
0x180093105  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18009310c  mov     ecx, edi; int
0x18009310e  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180093113  nop
0x180093114  mov     rcx, rbx; Block
0x180093117  call    cs:__imp_free
0x18009311d  nop
0x18009311e  mov     ebx, edi
0x180093120  lea     rcx, [rbp+hKey]; this
0x180093124  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x180093129  jmp     short loc_18009316B
0x18009312b  test    rsi, rsi
0x18009312e  jz      short loc_18009313B
0x180093130  mov     rax, [rbp+hKey]
0x180093134  mov     [rsi], rax
0x180093137  mov     [rbp+hKey], r14
0x18009313b  mov     rcx, rbx; Block
0x18009313e  call    cs:__imp_free
0x180093144  nop
0x180093145  lea     rcx, [rbp+hKey]; this
0x180093149  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x18009314e  xor     eax, eax
0x180093150  jmp     short loc_18009316D
0x180093152  mov     r8d, 898h; unsigned __int16
0x180093158  mov     ebx, 0C00E0006h
0x18009315d  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x180093164  mov     ecx, ebx; int
0x180093166  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18009316b  mov     eax, ebx
0x18009316d  lea     r11, [rsp+80h+var_s0]
0x180093175  mov     rbx, [r11+30h]
0x180093179  mov     rsi, [r11+38h]
0x18009317d  mov     rsp, r11
0x180093180  pop     r14
0x180093182  pop     rdi
0x180093183  pop     rbp
0x180093184  retn
```
