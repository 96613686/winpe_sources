# FindStandardVersionByKey(HKEY__ *,ushort const *,ushort * *)

- ea: `0x18003107c`
- end: `0x18003129c`
- name: `?FindStandardVersionByKey@@YAJPEAUHKEY__@@PEBGPEAPEAG@Z`
- size: `544`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800312a4`

## callees

- `0x180003740`
- `0x18000d264`
- `0x18003107c`
- `0x180041ac0`
- `0x180041b20`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1800310c8`
- `ADVAPI32!RegOpenKeyExW` at `0x1800310c8`
- `ADVAPI32!RegCloseKey` at `0x180031276`
- `ADVAPI32!RegCloseKey` at `0x180031276`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18003111f`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18003111f`
- `ADVAPI32!RegEnumValueW` at `0x1800311cc`
- `ADVAPI32!RegEnumValueW` at `0x1800311cc`

## pseudocode

```c
__int64 __fastcall FindStandardVersionByKey(HKEY a1, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  unsigned int v3; // r14d
  DWORD v4; // edx
  unsigned __int64 v5; // rcx
  __int64 v6; // rax
  void *v7; // rsp
  __int64 v8; // rax
  unsigned __int64 v9; // rax
  void *v10; // rsp
  DWORD v11; // ecx
  void *v12; // rsp
  __int64 v13; // rsi
  unsigned int v14; // r12d
  int v15; // edi
  unsigned __int128 v16; // rax
  wchar_t *v17; // rax
  unsigned __int16 *v18; // rdi
  DWORD cbMaxValueNameLen; // [rsp+60h] [rbp+0h] BYREF
  BYTE Data[4]; // [rsp+64h] [rbp+4h] BYREF
  DWORD cValues; // [rsp+68h] [rbp+8h] BYREF
  DWORD Type; // [rsp+6Ch] [rbp+Ch] BYREF
  DWORD cchValueName; // [rsp+70h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+18h] BYREF
  DWORD cbMaxValueLen; // [rsp+80h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+84h] [rbp+24h] BYREF
  unsigned __int16 **v28; // [rsp+88h] [rbp+28h]

  v28 = a3;
  Type = 0;
  hKey = 0;
  v3 = -2147467259;
  if ( !RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey) )
  {
    cValues = 0;
    cbMaxValueNameLen = 0;
    cbMaxValueLen = 0;
    if ( !RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0) )
    {
      v4 = cbMaxValueNameLen;
      v5 = 2LL * (cbMaxValueNameLen + 1);
      v6 = v5 + 15;
      if ( v5 + 15 < v5 )
        v6 = 0xFFFFFFFFFFFFFF0LL;
      v7 = alloca(v6 & 0xFFFFFFFFFFFFFFF0uLL);
      v8 = v5 + 15;
      if ( v5 + 15 < v5 )
        v8 = 0xFFFFFFFFFFFFFF0LL;
      v9 = v8 & 0xFFFFFFFFFFFFFFF0uLL;
      v10 = alloca(v9);
      v11 = cValues;
      v12 = alloca(v9);
      *(_DWORD *)Data = 0;
      LODWORD(v13) = 0;
      v14 = 0;
      v15 = 0;
      if ( cValues )
      {
        while ( 1 )
        {
          cbData = 4;
          cchValueName = v4 + 1;
          if ( !RegEnumValueW(hKey, v11 - v15 - 1, (LPWSTR)&cbMaxValueNameLen, &cchValueName, 0, &Type, Data, &cbData)
            && Type == 4
            && *(_DWORD *)Data > v14
            && cchValueName )
          {
            v14 = *(_DWORD *)Data;
            v13 = cchValueName;
            wcsncpy_s(
              (wchar_t *)&cbMaxValueNameLen,
              cbMaxValueNameLen + 1,
              (const wchar_t *)&cbMaxValueNameLen,
              cchValueName);
            *(_WORD *)&Data[2 * v13 - 4] = 0;
          }
          v11 = cValues;
          if ( ++v15 >= cValues )
            break;
          v4 = cbMaxValueNameLen;
        }
        if ( (_DWORD)v13 )
        {
          v16 = (unsigned int)(v13 + 1) * (unsigned __int128)2uLL;
          if ( !is_mul_ok((unsigned int)(v13 + 1), 2u) )
            *(_QWORD *)&v16 = -1;
          v17 = (wchar_t *)operator new(v16, *((const struct NoThrow **)&v16 + 1));
          v18 = v17;
          if ( v17 )
          {
            wcsncpy_s(v17, (unsigned int)(v13 + 1), (const wchar_t *)&cbMaxValueNameLen, (unsigned int)v13);
            v18[(unsigned int)v13] = 0;
            v3 = 0;
            *v28 = v18;
          }
          else
          {
            v3 = -2147024882;
          }
        }
      }
    }
    RegCloseKey(hKey);
  }
  return v3;
}

```

## disassembly

```asm
0x18003107c  push    rbp
0x18003107e  push    rbx
0x18003107f  push    rsi
0x180031080  push    rdi
0x180031081  push    r12
0x180031083  push    r13
0x180031085  push    r14
0x180031087  push    r15
0x180031089  sub     rsp, 0A8h
0x180031090  lea     rbp, [rsp+60h]
0x180031095  mov     rax, cs:__security_cookie
0x18003109c  xor     rax, rbp
0x18003109f  mov     [rbp+80h+var_50], rax
0x1800310a3  mov     [rbp+80h+var_58], r8
0x1800310a7  lea     rax, [rbp+80h+hKey]
0x1800310ab  xor     ebx, ebx
0x1800310ad  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1800310b2  xor     r8d, r8d; ulOptions
0x1800310b5  mov     [rbp+80h+Type], ebx
0x1800310b8  mov     r9d, 20019h; samDesired
0x1800310be  mov     [rbp+80h+hKey], rbx
0x1800310c2  mov     r14d, 80004005h
0x1800310c8  call    cs:__imp_RegOpenKeyExW
0x1800310ce  test    eax, eax
0x1800310d0  jnz     loc_18003127C
0x1800310d6  mov     rcx, [rbp+80h+hKey]; hKey
0x1800310da  lea     rax, [rbp+80h+cbMaxValueLen]
0x1800310de  mov     [rsp+0E0h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x1800310e3  xor     r9d, r9d; lpReserved
0x1800310e6  mov     [rsp+0E0h+lpcbSecurityDescriptor], rbx; lpcbSecurityDescriptor
0x1800310eb  xor     r8d, r8d; lpcchClass
0x1800310ee  mov     [rsp+0E0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1800310f3  xor     edx, edx; lpClass
0x1800310f5  lea     rax, [rbp+80h+cbMaxValueNameLen]
0x1800310f9  mov     [rbp+80h+cValues], ebx
0x1800310fc  mov     [rsp+0E0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180031101  lea     rax, [rbp+80h+cValues]
0x180031105  mov     [rsp+0E0h+lpcValues], rax; lpcValues
0x18003110a  mov     [rsp+0E0h+lpcbMaxClassLen], rbx; lpcbMaxClassLen
0x18003110f  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rbx; lpcbMaxSubKeyLen
0x180031114  mov     [rsp+0E0h+phkResult], rbx; lpcSubKeys
0x180031119  mov     [rbp+80h+cbMaxValueNameLen], ebx
0x18003111c  mov     [rbp+80h+cbMaxValueLen], ebx
0x18003111f  call    cs:__imp_RegQueryInfoKeyW
0x180031125  test    eax, eax
0x180031127  jnz     loc_180031272
0x18003112d  mov     edx, [rbp+80h+cbMaxValueNameLen]
0x180031130  mov     r8, 0FFFFFFFFFFFFFF0h
0x18003113a  lea     ecx, [rdx+1]
0x18003113d  add     rcx, rcx
0x180031140  lea     rax, [rcx+0Fh]
0x180031144  cmp     rax, rcx
0x180031147  ja      short loc_18003114C
0x180031149  mov     rax, r8
0x18003114c  and     rax, 0FFFFFFFFFFFFFFF0h
0x180031150  call    _alloca_probe
0x180031155  sub     rsp, rax
0x180031158  lea     rax, [rcx+0Fh]
0x18003115c  lea     r13, [rsp+0E0h+cbMaxValueNameLen]
0x180031161  cmp     rax, rcx
0x180031164  ja      short loc_180031169
0x180031166  mov     rax, r8
0x180031169  and     rax, 0FFFFFFFFFFFFFFF0h
0x18003116d  call    _alloca_probe
0x180031172  mov     ecx, [rbp+80h+cValues]
0x180031175  sub     rsp, rax
0x180031178  mov     dword ptr [rbp+80h+Data], ebx
0x18003117b  mov     esi, ebx
0x18003117d  mov     r12d, ebx
0x180031180  mov     edi, ebx
0x180031182  lea     r15, [rsp+0E0h+cbMaxValueNameLen]
0x180031187  test    ecx, ecx
0x180031189  jz      loc_180031272
0x18003118f  lea     eax, [rdx+1]
0x180031192  mov     [rbp+80h+cbData], 4
0x180031199  mov     [rbp+80h+cchValueName], eax
0x18003119c  lea     r9, [rbp+80h+cchValueName]; lpcchValueName
0x1800311a0  sub     ecx, edi
0x1800311a2  lea     rax, [rbp+80h+cbData]
0x1800311a6  mov     [rsp+0E0h+lpcValues], rax; lpcbData
0x1800311ab  mov     r8, r13; lpValueName
0x1800311ae  lea     rax, [rbp+80h+Data]
0x1800311b2  mov     [rsp+0E0h+lpcbMaxClassLen], rax; lpData
0x1800311b7  lea     rax, [rbp+80h+Type]
0x1800311bb  lea     edx, [rcx-1]; dwIndex
0x1800311be  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax; lpType
0x1800311c3  mov     rcx, [rbp+80h+hKey]; hKey
0x1800311c7  mov     [rsp+0E0h+phkResult], rbx; lpReserved
0x1800311cc  call    cs:__imp_RegEnumValueW
0x1800311d2  test    eax, eax
0x1800311d4  jnz     short loc_18003120B
0x1800311d6  cmp     [rbp+80h+Type], 4
0x1800311da  jnz     short loc_18003120B
0x1800311dc  cmp     dword ptr [rbp+80h+Data], r12d
0x1800311e0  jbe     short loc_18003120B
0x1800311e2  mov     eax, [rbp+80h+cchValueName]
0x1800311e5  test    eax, eax
0x1800311e7  jz      short loc_18003120B
0x1800311e9  mov     edx, [rbp+80h+cbMaxValueNameLen]
0x1800311ec  mov     r9d, eax; MaxCount
0x1800311ef  mov     r12d, dword ptr [rbp+80h+Data]
0x1800311f3  inc     edx; SizeInWords
0x1800311f5  mov     r8, r13; Source
0x1800311f8  mov     rcx, r15; Destination
0x1800311fb  mov     esi, eax
0x1800311fd  call    wcsncpy_s
0x180031202  xor     eax, eax
0x180031204  mov     [r15+rsi*2], ax
0x180031209  xor     ebx, ebx
0x18003120b  mov     ecx, [rbp+80h+cValues]
0x18003120e  inc     edi
0x180031210  cmp     edi, ecx
0x180031212  jnb     short loc_18003121C
0x180031214  mov     edx, [rbp+80h+cbMaxValueNameLen]
0x180031217  jmp     loc_18003118F
0x18003121c  test    esi, esi
0x18003121e  jz      short loc_180031272
0x180031220  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180031227  lea     r14d, [rsi+1]
0x18003122b  mov     eax, 2
0x180031230  mul     r14
0x180031233  cmovb   rax, rcx
0x180031237  mov     rcx, rax; unsigned __int64
0x18003123a  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x18003123f  mov     rdi, rax
0x180031242  test    rax, rax
0x180031245  jnz     short loc_18003124F
0x180031247  mov     r14d, 8007000Eh
0x18003124d  jmp     short loc_180031272
0x18003124f  mov     r9d, esi; MaxCount
0x180031252  mov     r8, r15; Source
0x180031255  mov     rdx, r14; SizeInWords
0x180031258  mov     ebx, esi
0x18003125a  mov     rcx, rdi; Destination
0x18003125d  call    wcsncpy_s
0x180031262  xor     eax, eax
0x180031264  mov     [rdi+rbx*2], ax
0x180031268  xor     r14d, r14d
0x18003126b  mov     rax, [rbp+80h+var_58]
0x18003126f  mov     [rax], rdi
0x180031272  mov     rcx, [rbp+80h+hKey]; hKey
0x180031276  call    cs:__imp_RegCloseKey
0x18003127c  mov     eax, r14d
0x18003127f  mov     rcx, [rbp+80h+var_50]
0x180031283  xor     rcx, rbp; StackCookie
0x180031286  call    __security_check_cookie
0x18003128b  lea     rsp, [rbp+48h]
0x18003128f  pop     r15
0x180031291  pop     r14
0x180031293  pop     r13
0x180031295  pop     r12
0x180031297  pop     rdi
0x180031298  pop     rsi
0x180031299  pop     rbx
0x18003129a  pop     rbp
0x18003129b  retn
```
