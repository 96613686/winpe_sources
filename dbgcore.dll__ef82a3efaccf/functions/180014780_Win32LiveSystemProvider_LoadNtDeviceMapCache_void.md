# Win32LiveSystemProvider::LoadNtDeviceMapCache(void)

- ea: `0x180014780`
- end: `0x180014948`
- name: `?LoadNtDeviceMapCache@Win32LiveSystemProvider@@AEAAJXZ`
- size: `456`
- prototype: `__int64 __fastcall(Win32LiveSystemProvider *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180015cf0`

## callees

- `0x180001710`
- `0x18000ae3c`
- `0x180014674`
- `0x180014780`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014879`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014900`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001490a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014879`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014900`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001490a`

## pseudocode

```c
signed int __fastcall Win32LiveSystemProvider::LoadNtDeviceMapCache(Win32LiveSystemProvider *this)
{
  __int64 v2; // rcx
  __int16 *v3; // r8
  __int64 v4; // rdx
  unsigned __int16 *v5; // rax
  unsigned __int16 *v6; // rcx
  signed int result; // eax
  __int16 v8; // [rsp+20h] [rbp-238h] BYREF
  int v9; // [rsp+22h] [rbp-236h]
  unsigned __int16 v10; // [rsp+28h] [rbp-230h] BYREF
  unsigned __int16 v11[264]; // [rsp+30h] [rbp-228h] BYREF

  v9 = 58;
  v8 = 65;
  while ( 1 )
  {
    if ( (*((unsigned int (__fastcall **)(__int16 *, unsigned __int16 *, __int64))this + 40))(&v8, v11, 260) )
    {
      v2 = 2147483646;
      v3 = &v8;
      v4 = 4;
      v5 = &v10;
      do
      {
        if ( !v2 )
          break;
        if ( !*v3 )
          break;
        *v5++ = *v3++;
        --v2;
        --v4;
      }
      while ( v4 );
      v6 = v5 - 1;
      if ( v4 )
        v6 = v5;
      *v6 = 0;
      result = v4 == 0 ? 0x8007007A : 0;
      if ( !v4 )
        return result;
      result = StringCchCatW(&v10, 4u, L"\\");
      if ( result )
        return result;
      result = Win32LiveSystemProvider::InsertNtDeviceMapEntry(this, v11, &v10);
      if ( result )
        return result;
      goto LABEL_14;
    }
    if ( GetLastError() != 2 )
      break;
LABEL_14:
    if ( (unsigned __int16)++v8 > 0x5Au )
    {
      result = Win32LiveSystemProvider::InsertNtDeviceMapEntry(this, L"\\Device\\Mup", L"\\\\");
      if ( !result )
      {
        result = Win32LiveSystemProvider::InsertNtDeviceMapEntry(this, L"\\Device\\LanmanRedirector", L"\\\\");
        if ( !result )
        {
          result = Win32LiveSystemProvider::InsertNtDeviceMapEntry(this, L"\\Device\\WinDfs", L"\\\\");
          if ( !result )
            return Win32LiveSystemProvider::InsertNtDeviceMapEntry(this, L"\\Device\\RdpDr\\TSCLIENT", L"\\\\TSCLIENT");
        }
      }
      return result;
    }
  }
  if ( !GetLastError() )
    return -2147467259;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180014780  mov     [rsp+arg_8], rbx
0x180014785  mov     [rsp+arg_10], rsi
0x18001478a  push    rdi
0x18001478b  sub     rsp, 250h
0x180014792  mov     rax, cs:__security_cookie
0x180014799  xor     rax, rsp
0x18001479c  mov     [rsp+258h+var_18], rax
0x1800147a4  mov     eax, 41h ; 'A'
0x1800147a9  mov     [rsp+258h+var_236], 3Ah ; ':'
0x1800147b1  mov     rbx, rcx
0x1800147b4  mov     [rsp+258h+var_238], ax
0x1800147b9  xor     edi, edi
0x1800147bb  lea     esi, [rax-40h]
0x1800147be  mov     rax, [rbx+140h]
0x1800147c5  lea     rdx, [rsp+258h+var_228]
0x1800147ca  mov     r8d, 104h
0x1800147d0  lea     rcx, [rsp+258h+var_238]
0x1800147d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147da  test    eax, eax
0x1800147dc  jz      loc_180014879
0x1800147e2  mov     ecx, 7FFFFFFEh
0x1800147e7  lea     r8, [rsp+258h+var_238]
0x1800147ec  mov     edx, 4
0x1800147f1  lea     rax, [rsp+258h+var_230]
0x1800147f6  test    rcx, rcx
0x1800147f9  jz      short loc_180014819
0x1800147fb  movzx   r9d, word ptr [r8]
0x1800147ff  test    r9w, r9w
0x180014803  jz      short loc_180014819
0x180014805  mov     [rax], r9w
0x180014809  add     r8, 2
0x18001480d  add     rax, 2
0x180014811  sub     rcx, rsi
0x180014814  sub     rdx, rsi
0x180014817  jnz     short loc_1800147F6
0x180014819  lea     rcx, [rax-2]
0x18001481d  test    rdx, rdx
0x180014820  cmovnz  rcx, rax
0x180014824  mov     rax, rdx
0x180014827  neg     rax
0x18001482a  sbb     eax, eax
0x18001482c  not     eax
0x18001482e  mov     [rcx], di
0x180014831  and     eax, 8007007Ah
0x180014836  test    rdx, rdx
0x180014839  jz      loc_180014923
0x18001483f  lea     r8, asc_18002ED88; "\\"
0x180014846  mov     edx, 4; unsigned __int64
0x18001484b  lea     rcx, [rsp+258h+var_230]; unsigned __int16 *
0x180014850  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180014855  test    eax, eax
0x180014857  jnz     loc_180014923
0x18001485d  lea     r8, [rsp+258h+var_230]; unsigned __int16 *
0x180014862  mov     rcx, rbx; this
0x180014865  lea     rdx, [rsp+258h+var_228]; unsigned __int16 *
0x18001486a  call    ?InsertNtDeviceMapEntry@Win32LiveSystemProvider@@AEAAJPEAG0@Z; Win32LiveSystemProvider::InsertNtDeviceMapEntry(ushort *,ushort *)
0x18001486f  test    eax, eax
0x180014871  jnz     loc_180014923
0x180014877  jmp     short loc_180014884
0x180014879  call    cs:__imp_GetLastError
0x18001487f  cmp     eax, 2
0x180014882  jnz     short loc_180014900
0x180014884  movzx   eax, [rsp+258h+var_238]
0x180014889  add     ax, si
0x18001488c  mov     [rsp+258h+var_238], ax
0x180014891  cmp     ax, 5Ah ; 'Z'
0x180014895  jbe     loc_1800147BE
0x18001489b  lea     rsi, asc_1800309A4; "\\\\"
0x1800148a2  mov     rcx, rbx; this
0x1800148a5  mov     r8, rsi; unsigned __int16 *
0x1800148a8  lea     rdx, aDeviceMup; "\\Device\\Mup"
0x1800148af  call    ?InsertNtDeviceMapEntry@Win32LiveSystemProvider@@AEAAJPEAG0@Z; Win32LiveSystemProvider::InsertNtDeviceMapEntry(ushort *,ushort *)
0x1800148b4  test    eax, eax
0x1800148b6  jnz     short loc_180014923
0x1800148b8  mov     r8, rsi; unsigned __int16 *
0x1800148bb  lea     rdx, aDeviceLanmanre; "\\Device\\LanmanRedirector"
0x1800148c2  mov     rcx, rbx; this
0x1800148c5  call    ?InsertNtDeviceMapEntry@Win32LiveSystemProvider@@AEAAJPEAG0@Z; Win32LiveSystemProvider::InsertNtDeviceMapEntry(ushort *,ushort *)
0x1800148ca  test    eax, eax
0x1800148cc  jnz     short loc_180014923
0x1800148ce  mov     r8, rsi; unsigned __int16 *
0x1800148d1  lea     rdx, aDeviceWindfs; "\\Device\\WinDfs"
0x1800148d8  mov     rcx, rbx; this
0x1800148db  call    ?InsertNtDeviceMapEntry@Win32LiveSystemProvider@@AEAAJPEAG0@Z; Win32LiveSystemProvider::InsertNtDeviceMapEntry(ushort *,ushort *)
0x1800148e0  test    eax, eax
0x1800148e2  jnz     short loc_180014923
0x1800148e4  lea     r8, aTsclient; "\\\\TSCLIENT"
0x1800148eb  mov     rcx, rbx; this
0x1800148ee  lea     rdx, aDeviceRdpdrTsc; "\\Device\\RdpDr\\TSCLIENT"
0x1800148f5  call    ?InsertNtDeviceMapEntry@Win32LiveSystemProvider@@AEAAJPEAG0@Z; Win32LiveSystemProvider::InsertNtDeviceMapEntry(ushort *,ushort *)
0x1800148fa  test    eax, eax
0x1800148fc  jnz     short loc_180014923
0x1800148fe  jmp     short loc_180014923
0x180014900  call    cs:__imp_GetLastError
0x180014906  test    eax, eax
0x180014908  jz      short loc_18001491E
0x18001490a  call    cs:__imp_GetLastError
0x180014910  test    eax, eax
0x180014912  jle     short loc_180014923
0x180014914  movzx   eax, ax
0x180014917  or      eax, 80070000h
0x18001491c  jmp     short loc_180014923
0x18001491e  mov     eax, 80004005h
0x180014923  mov     rcx, [rsp+258h+var_18]
0x18001492b  xor     rcx, rsp; StackCookie
0x18001492e  call    __security_check_cookie
0x180014933  lea     r11, [rsp+258h+var_8]
0x18001493b  mov     rbx, [r11+18h]
0x18001493f  mov     rsi, [r11+20h]
0x180014943  mov     rsp, r11
0x180014946  pop     rdi
0x180014947  retn
```
