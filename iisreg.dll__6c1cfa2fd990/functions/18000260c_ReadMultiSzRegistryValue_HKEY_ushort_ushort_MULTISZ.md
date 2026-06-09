# ReadMultiSzRegistryValue(HKEY__ *,ushort *,ushort *,MULTISZ *)

- ea: `0x18000260c`
- end: `0x180002833`
- name: `?ReadMultiSzRegistryValue@@YAJPEAUHKEY__@@PEAG1PEAVMULTISZ@@@Z`
- size: `551`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpValueName, struct MULTISZ *this)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180001d7c`
- `0x18000200c`

## callees

- `0x18000260c`
- `0x180002ff8`
- `0x180003024`
- `0x1800033ac`
- `0x180003474`
- `0x180003650`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800026f6`
- `KERNEL32!GetLastError` at `0x1800026f6`
- `ADVAPI32!RegQueryValueExW` at `0x180002722`
- `ADVAPI32!RegQueryValueExW` at `0x180002777`
- `ADVAPI32!RegQueryValueExW` at `0x180002722`
- `ADVAPI32!RegQueryValueExW` at `0x180002777`
- `ADVAPI32!RegOpenKeyExW` at `0x1800026bc`
- `ADVAPI32!RegOpenKeyExW` at `0x1800026bc`
- `ADVAPI32!RegCloseKey` at `0x1800027fc`
- `ADVAPI32!RegCloseKey` at `0x1800027fc`

## pseudocode

```c
__int64 __fastcall ReadMultiSzRegistryValue(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpValueName, struct MULTISZ *this)
{
  LPBYTE v5; // rdx
  __int64 v9; // rcx
  signed int LastError; // eax
  LSTATUS v11; // ebx
  bool v12; // cc
  unsigned int v13; // eax
  const unsigned __int16 *v14; // rdx
  __int64 i; // r9
  DWORD cbData; // [rsp+30h] [rbp-19h] BYREF
  DWORD Type; // [rsp+34h] [rbp-15h] BYREF
  HKEY hKeya; // [rsp+38h] [rbp-11h] BYREF
  _QWORD v20[4]; // [rsp+40h] [rbp-9h] BYREF
  LPBYTE lpData; // [rsp+60h] [rbp+17h]
  DWORD v22; // [rsp+68h] [rbp+1Fh]
  __int16 v23; // [rsp+6Ch] [rbp+23h]
  unsigned int v24[2]; // [rsp+70h] [rbp+27h] BYREF

  hKeya = 0;
  v5 = (LPBYTE)v20;
  Type = 7;
  lpData = (LPBYTE)v20;
  cbData = 0;
  v20[0] = 0;
  v22 = 32;
  v9 = 0;
  v23 = 256;
  while ( 1 )
  {
    *(_WORD *)&v5[2 * v9++] = 0;
    if ( v9 == 2 )
      break;
    v5 = lpData;
  }
  *(_QWORD *)v24 = 2;
  if ( hKey && lpValueName && this )
  {
    LastError = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, &hKeya);
    v11 = LastError;
    v12 = LastError <= 0;
    if ( LastError )
    {
LABEL_8:
      if ( v12 )
        goto LABEL_31;
      v11 = (unsigned __int16)LastError;
      goto LABEL_10;
    }
    cbData = 520;
    if ( v22 < 0x208 && !BUFFER::ReallocStorage((BUFFER *)v20, 0x208u) )
    {
LABEL_13:
      LastError = GetLastError();
      v11 = LastError;
      v12 = LastError <= 0;
      goto LABEL_8;
    }
    v11 = RegQueryValueExW(hKeya, lpValueName, 0, &Type, lpData, &cbData);
    v13 = MULTISZ::CalcLength((const unsigned __int16 *)lpData, &v24[1]);
    v24[0] = v13;
    if ( v11 == 234 )
    {
      if ( cbData > v22 && !BUFFER::ReallocStorage((BUFFER *)v20, cbData) )
        goto LABEL_13;
      v11 = RegQueryValueExW(hKeya, lpValueName, 0, &Type, lpData, &cbData);
      v13 = MULTISZ::CalcLength((const unsigned __int16 *)lpData, &v24[1]);
      v24[0] = v13;
    }
    if ( v11 )
    {
      if ( v11 > 0 )
      {
        v11 = (unsigned __int16)v11;
LABEL_10:
        v11 |= 0x80070000;
      }
    }
    else if ( Type == 7 )
    {
      v14 = (const unsigned __int16 *)lpData;
      v11 = 0;
      if ( *((_QWORD *)this + 4) )
      {
        for ( i = 0; i != 2; ++i )
          *(_WORD *)(*((_QWORD *)this + 4) + 2 * i) = 0;
        *((_QWORD *)this + 6) = 2;
      }
      if ( v14 && !(unsigned int)MULTISZ::AuxAppend(this, v14, 2 * v13, 0) )
        goto LABEL_13;
    }
    else
    {
      v11 = -2147024883;
    }
  }
  else
  {
    v11 = -2147024809;
  }
LABEL_31:
  if ( hKeya )
  {
    RegCloseKey(hKeya);
    hKeya = 0;
  }
  if ( (_BYTE)v23 )
    BUFFER::FreeMemoryInternal((BUFFER *)v20);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000260c  push    rbp
0x18000260e  push    rbx
0x18000260f  push    rsi
0x180002610  push    rdi
0x180002611  lea     rbp, [rsp-3Fh]
0x180002616  sub     rsp, 88h
0x18000261d  mov     rax, cs:__security_cookie
0x180002624  xor     rax, rsp
0x180002627  mov     [rbp+57h+var_28], rax
0x18000262b  mov     r11, rdx
0x18000262e  mov     [rbp+57h+hKey], 0
0x180002636  lea     rdx, [rbp+57h+var_60]
0x18000263a  mov     [rbp+57h+Type], 7
0x180002641  mov     r10, rcx
0x180002644  mov     [rbp+57h+lpData], rdx
0x180002648  mov     rdi, r9
0x18000264b  mov     [rbp+57h+cbData], 0
0x180002652  mov     rsi, r8
0x180002655  mov     [rbp+57h+var_60], 0
0x18000265d  mov     [rbp+57h+var_38], 20h ; ' '
0x180002664  xor     ecx, ecx
0x180002666  mov     [rbp+57h+var_34], 100h
0x18000266c  xor     eax, eax
0x18000266e  mov     [rdx+rcx*2], ax
0x180002672  inc     rcx
0x180002675  cmp     rcx, 2
0x180002679  jz      short loc_180002681
0x18000267b  mov     rdx, [rbp+57h+lpData]
0x18000267f  jmp     short loc_18000266C
0x180002681  mov     qword ptr [rbp+57h+var_30], 2
0x180002689  test    r10, r10
0x18000268c  jz      loc_1800027EE
0x180002692  test    rsi, rsi
0x180002695  jz      loc_1800027EE
0x18000269b  test    rdi, rdi
0x18000269e  jz      loc_1800027EE
0x1800026a4  lea     rax, [rbp+57h+hKey]
0x1800026a8  mov     r9d, 20019h; samDesired
0x1800026ae  xor     r8d, r8d; ulOptions
0x1800026b1  mov     [rsp+0A0h+phkResult], rax; phkResult
0x1800026b6  mov     rdx, r11; lpSubKey
0x1800026b9  mov     rcx, r10; hKey
0x1800026bc  call    cs:__imp_RegOpenKeyExW
0x1800026c2  mov     ebx, eax
0x1800026c4  test    eax, eax
0x1800026c6  jz      short loc_1800026DC
0x1800026c8  jle     loc_1800027F3
0x1800026ce  movzx   ebx, ax
0x1800026d1  or      ebx, 80070000h
0x1800026d7  jmp     loc_1800027F3
0x1800026dc  mov     edx, 208h; unsigned int
0x1800026e1  mov     [rbp+57h+cbData], edx
0x1800026e4  cmp     [rbp+57h+var_38], edx
0x1800026e7  jnb     short loc_180002702
0x1800026e9  lea     rcx, [rbp+57h+var_60]; this
0x1800026ed  call    ?ReallocStorage@BUFFER@@AEAA_NK@Z; BUFFER::ReallocStorage(ulong)
0x1800026f2  test    al, al
0x1800026f4  jnz     short loc_180002702
0x1800026f6  call    cs:__imp_GetLastError
0x1800026fc  mov     ebx, eax
0x1800026fe  test    eax, eax
0x180002700  jmp     short loc_1800026C8
0x180002702  mov     rcx, [rbp+57h+hKey]; hKey
0x180002706  lea     rax, [rbp+57h+cbData]
0x18000270a  mov     [rsp+0A0h+lpcbData], rax; lpcbData
0x18000270f  lea     r9, [rbp+57h+Type]; lpType
0x180002713  mov     rax, [rbp+57h+lpData]
0x180002717  xor     r8d, r8d; lpReserved
0x18000271a  mov     rdx, rsi; lpValueName
0x18000271d  mov     [rsp+0A0h+phkResult], rax; lpData
0x180002722  call    cs:__imp_RegQueryValueExW
0x180002728  mov     rcx, [rbp+57h+lpData]; unsigned __int16 *
0x18000272c  lea     rdx, [rbp+57h+var_30+4]; unsigned int *
0x180002730  mov     ebx, eax
0x180002732  call    ?CalcLength@MULTISZ@@SAKPEBGPEAK@Z; MULTISZ::CalcLength(ushort const *,ulong *)
0x180002737  mov     [rbp+57h+var_30], eax
0x18000273a  cmp     ebx, 0EAh
0x180002740  jnz     short loc_18000278F
0x180002742  mov     edx, [rbp+57h+cbData]; unsigned int
0x180002745  cmp     edx, [rbp+57h+var_38]
0x180002748  jbe     short loc_180002757
0x18000274a  lea     rcx, [rbp+57h+var_60]; this
0x18000274e  call    ?ReallocStorage@BUFFER@@AEAA_NK@Z; BUFFER::ReallocStorage(ulong)
0x180002753  test    al, al
0x180002755  jz      short loc_1800026F6
0x180002757  mov     rcx, [rbp+57h+hKey]; hKey
0x18000275b  lea     rax, [rbp+57h+cbData]
0x18000275f  mov     [rsp+0A0h+lpcbData], rax; lpcbData
0x180002764  lea     r9, [rbp+57h+Type]; lpType
0x180002768  mov     rax, [rbp+57h+lpData]
0x18000276c  xor     r8d, r8d; lpReserved
0x18000276f  mov     rdx, rsi; lpValueName
0x180002772  mov     [rsp+0A0h+phkResult], rax; lpData
0x180002777  call    cs:__imp_RegQueryValueExW
0x18000277d  mov     rcx, [rbp+57h+lpData]; unsigned __int16 *
0x180002781  lea     rdx, [rbp+57h+var_30+4]; unsigned int *
0x180002785  mov     ebx, eax
0x180002787  call    ?CalcLength@MULTISZ@@SAKPEBGPEAK@Z; MULTISZ::CalcLength(ushort const *,ulong *)
0x18000278c  mov     [rbp+57h+var_30], eax
0x18000278f  test    ebx, ebx
0x180002791  jz      short loc_18000279D
0x180002793  jle     short loc_1800027F3
0x180002795  movzx   ebx, bx
0x180002798  jmp     loc_1800026D1
0x18000279d  cmp     [rbp+57h+Type], 7
0x1800027a1  jz      short loc_1800027AA
0x1800027a3  mov     ebx, 8007000Dh
0x1800027a8  jmp     short loc_1800027F3
0x1800027aa  mov     rdx, [rbp+57h+lpData]; Src
0x1800027ae  lea     r8d, [rax+rax]; Size
0x1800027b2  xor     ebx, ebx
0x1800027b4  cmp     [rdi+20h], rbx
0x1800027b8  jz      short loc_1800027D5
0x1800027ba  xor     r9d, r9d
0x1800027bd  mov     rcx, [rdi+20h]
0x1800027c1  xor     eax, eax
0x1800027c3  mov     [rcx+r9*2], ax
0x1800027c8  inc     r9
0x1800027cb  cmp     r9, 2
0x1800027cf  jnz     short loc_1800027BD
0x1800027d1  mov     [rdi+30h], r9
0x1800027d5  test    rdx, rdx
0x1800027d8  jz      short loc_1800027F3
0x1800027da  xor     r9d, r9d; int
0x1800027dd  mov     rcx, rdi; this
0x1800027e0  call    ?AuxAppend@MULTISZ@@AEAAHPEBGIH@Z; MULTISZ::AuxAppend(ushort const *,uint,int)
0x1800027e5  test    eax, eax
0x1800027e7  jnz     short loc_1800027F3
0x1800027e9  jmp     loc_1800026F6
0x1800027ee  mov     ebx, 80070057h
0x1800027f3  mov     rcx, [rbp+57h+hKey]; hKey
0x1800027f7  test    rcx, rcx
0x1800027fa  jz      short loc_18000280A
0x1800027fc  call    cs:__imp_RegCloseKey
0x180002802  mov     [rbp+57h+hKey], 0
0x18000280a  cmp     byte ptr [rbp+57h+var_34], 0
0x18000280e  jz      short loc_180002819
0x180002810  lea     rcx, [rbp+57h+var_60]; this
0x180002814  call    ?FreeMemoryInternal@BUFFER@@AEAAXXZ; BUFFER::FreeMemoryInternal(void)
0x180002819  mov     eax, ebx
0x18000281b  mov     rcx, [rbp+57h+var_28]
0x18000281f  xor     rcx, rsp; StackCookie
0x180002822  call    __security_check_cookie
0x180002827  add     rsp, 88h
0x18000282e  pop     rdi
0x18000282f  pop     rsi
0x180002830  pop     rbx
0x180002831  pop     rbp
0x180002832  retn
```
