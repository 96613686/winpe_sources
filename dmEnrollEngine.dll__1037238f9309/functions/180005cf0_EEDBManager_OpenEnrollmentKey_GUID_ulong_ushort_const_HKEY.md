# EEDBManager::OpenEnrollmentKey(_GUID,ulong,ushort const *,HKEY__ * *)

- ea: `0x180005cf0`
- end: `0x18000618d`
- name: `?OpenEnrollmentKey@EEDBManager@@CAJU_GUID@@KPEBGPEAPEAUHKEY__@@@Z`
- size: `1181`
- prototype: `static int(struct _GUID *__struct_ptr, unsigned int, const unsigned __int16 *, HKEY *)`
- caller_count: `43`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800040f0`
- `0x18000fd08`
- `0x180010490`
- `0x180010600`
- `0x18001068c`
- `0x180010730`
- `0x1800107b4`
- `0x180010840`
- `0x1800108c4`
- `0x180013854`
- `0x180013e08`
- `0x1800182a0`
- `0x180019a30`
- `0x180019e8c`
- `0x18001a6a4`
- `0x18001de18`
- `0x18001e164`
- `0x18001e4c4`
- `0x18001e794`
- `0x18001e848`
- `0x18001f9f4`
- `0x1800214ec`
- `0x1800215dc`
- `0x18003ea40`
- `0x18003eb10`
- `0x18003ebe0`
- `0x18003ecb4`
- `0x18003ed84`
- `0x18003eed4`
- `0x18003efa8`
- `0x18003f2e4`
- `0x18003f380`
- `0x18003f454`
- `0x18003f530`
- `0x18003f6c0`
- `0x18003f79c`
- `0x18003f878`
- `0x18003f98c`
- `0x18003fbc4`
- `0x18003ff08`
- `0x18003ffc0`
- `0x180040078`
- `0x180040240`

## callees

- `0x180005cf0`
- `0x1800067a0`
- `0x18002e1a0`
- `0x180078040`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x18000613e`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000613e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800060f2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800060f2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005f0c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006045`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005f0c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006045`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005f7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005f7b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180005d40`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180005d40`

## pseudocode

```c
LSTATUS __fastcall EEDBManager::OpenEnrollmentKey(struct _GUID *a1, int a2, const unsigned __int16 *a3, HKEY *a4)
{
  __int64 v5; // rbx
  __int64 v7; // rcx
  OLECHAR *p_sz; // rax
  int v9; // r10d
  __int64 v10; // rdx
  __int64 v11; // rdi
  char *v12; // rdx
  __int64 v13; // rcx
  _WORD *v14; // r9
  __int64 v15; // r8
  _WORD *v16; // rcx
  int v17; // r15d
  _WORD *v18; // rax
  __int64 v19; // rax
  __int64 v20; // rbx
  _BYTE *v21; // rcx
  wchar_t *v22; // rbp
  HKEY v23; // rsi
  signed int v24; // r14d
  LSTATUS v25; // eax
  WCHAR *v26; // rcx
  WCHAR *v27; // rdx
  LSTATUS result; // eax
  WCHAR *v29; // rcx
  LSTATUS v30; // eax
  _WORD v32[38]; // [rsp+60h] [rbp-728h] BYREF
  _BYTE v33[4]; // [rsp+ACh] [rbp-6DCh] BYREF
  OLECHAR sz; // [rsp+B0h] [rbp-6D8h] BYREF
  char v35; // [rsp+B2h] [rbp-6D6h] BYREF
  WCHAR SubKey[264]; // [rsp+100h] [rbp-688h] BYREF
  WCHAR v37[264]; // [rsp+310h] [rbp-478h] BYREF
  wchar_t String1[264]; // [rsp+520h] [rbp-268h] BYREF

  v37[0] = 0;
  v5 = 39;
  v32[0] = 0;
  sz = 0;
  if ( StringFromGUID2(a1, &sz, 39) != 39 )
    return -2147418113;
  v7 = 39;
  p_sz = &sz;
  do
  {
    if ( !*p_sz )
      break;
    ++p_sz;
    --v7;
  }
  while ( v7 );
  v9 = -2147024809;
  LODWORD(v10) = -2147024809;
  if ( !v7 )
    return v10;
  if ( (unsigned __int64)(37 - v7) > 0x24 )
    return -2147418113;
  v11 = 2147483646;
  v12 = &v35;
  v13 = 2147483646;
  v14 = v32;
  v15 = 39;
  do
  {
    if ( !v13 )
      break;
    if ( !*(_WORD *)v12 )
      break;
    *v14 = *(_WORD *)v12;
    v12 += 2;
    ++v14;
    --v13;
    --v15;
  }
  while ( v15 );
  v16 = v14 - 1;
  v17 = -2147024774;
  v10 = 2147942522LL;
  if ( v15 )
  {
    v16 = v14;
    v10 = 0;
  }
  *v16 = 0;
  if ( !v15 )
    return v10;
  v18 = v32;
  do
  {
    if ( !*v18 )
      break;
    ++v18;
    --v5;
  }
  while ( v5 );
  if ( !v5 )
    return v9;
  if ( (unsigned __int64)(37 - v5) > 0x24 )
    return -2147418113;
  v19 = 2 * v5;
  v20 = 260;
  v21 = &v33[-v19];
  *(_WORD *)&v33[-v19] = 0;
  if ( a3 )
  {
    result = StringCchPrintfW(String1, 0x104u, L"%s\\%s", a3, v32);
    if ( result < 0 )
      return result;
  }
  v22 = v32;
  if ( a3 )
    v22 = String1;
  v23 = (HKEY)((word_1800AFC84 != 0x2000) - 0x7FFFFFFFLL);
  if ( !a4 )
    return -2147467261;
  *a4 = 0;
  if ( v23 == HKEY_LOCAL_MACHINE && (unsigned __int8)RtlIsStateSeparationEnabled(v21, v10) )
  {
    v24 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", L"OSData\\Software\\Microsoft\\Enrollments", v22);
    if ( v24 < 0 )
      goto LABEL_38;
    v30 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, a2 | 0x100, a4);
    v24 = v30;
    if ( v30 > 0 )
      v24 = (unsigned __int16)v30 | 0x80070000;
    if ( v24 < 0 && (!wcsncmp_0(v22, L"Status", 6u) || !wcsncmp_0(v22, L"Context", 7u))
      || (unsigned int)(v24 + 2147024894) > 1 )
    {
      goto LABEL_27;
    }
  }
  v24 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", L"Software\\Microsoft\\Enrollments", v22);
  if ( v24 >= 0 )
  {
    v25 = RegOpenKeyExW(v23, SubKey, 0, a2 | 0x100, a4);
    v24 = v25;
    if ( v25 > 0 )
      v24 = (unsigned __int16)v25 | 0x80070000;
LABEL_27:
    v26 = SubKey;
    v27 = v37;
    do
    {
      if ( !v11 )
        break;
      if ( !*v26 )
        break;
      *v27++ = *v26++;
      --v11;
      --v20;
    }
    while ( v20 );
    result = 0;
    v29 = v27 - 1;
    if ( v20 )
    {
      v29 = v27;
      v17 = 0;
    }
    *v29 = 0;
    if ( v24 >= 0 )
    {
      if ( v20 )
        return result;
      v24 = v17;
    }
    if ( *a4 )
    {
      RegCloseKey(*a4);
      *a4 = 0;
    }
  }
LABEL_38:
  if ( v24 != -2147024894 || !a3 )
    return v24;
  result = RegCreateKeyExW((HKEY)((word_1800AFC84 != 0x2000) - 0x7FFFFFFFLL), v37, 0, 0, 0, a2 | 0x100, 0, a4, 0);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180005cf0  push    rbx
0x180005cf2  push    r12
0x180005cf4  push    r13
0x180005cf6  sub     rsp, 770h
0x180005cfd  mov     rax, cs:__security_cookie
0x180005d04  xor     rax, rsp
0x180005d07  mov     [rsp+788h+var_58], rax
0x180005d0f  xor     eax, eax
0x180005d11  mov     [rsp+788h+var_738], edx
0x180005d15  mov     r13, r8
0x180005d18  mov     [rsp+788h+var_478], ax
0x180005d20  mov     ebx, 27h ; '''
0x180005d25  mov     [rsp+788h+var_728], ax
0x180005d2a  mov     r8d, ebx; cchMax
0x180005d2d  mov     [rsp+788h+sz], ax
0x180005d35  lea     rdx, [rsp+788h+sz]; lpsz
0x180005d3d  mov     r12, r9
0x180005d40  call    cs:__imp_StringFromGUID2
0x180005d46  cmp     eax, ebx
0x180005d48  jnz     loc_180006008
0x180005d4e  mov     ecx, ebx
0x180005d50  lea     rax, [rsp+788h+sz]
0x180005d58  cmp     word ptr [rax], 0
0x180005d5c  jz      short loc_180005D68
0x180005d5e  add     rax, 2
0x180005d62  sub     rcx, 1
0x180005d66  jnz     short loc_180005D58
0x180005d68  xor     eax, eax
0x180005d6a  mov     [rsp+788h+var_30], rdi
0x180005d72  mov     r10d, 80070057h
0x180005d78  mov     [rsp+788h+var_40], r15
0x180005d80  test    rcx, rcx
0x180005d83  mov     edx, r10d
0x180005d86  cmovnz  edx, eax
0x180005d89  jz      loc_180005FE5
0x180005d8f  mov     r11d, 25h ; '%'
0x180005d95  mov     eax, r11d
0x180005d98  sub     rax, rcx
0x180005d9b  cmp     rax, 24h ; '$'
0x180005d9f  ja      loc_180005FED
0x180005da5  mov     edi, 7FFFFFFEh
0x180005daa  lea     rdx, [rsp+788h+var_6D6]
0x180005db2  mov     ecx, edi
0x180005db4  lea     r9, [rsp+788h+var_728]
0x180005db9  mov     r8, rbx
0x180005dbc  nop     dword ptr [rax+00h]
0x180005dc0  test    rcx, rcx
0x180005dc3  jz      short loc_180005DE2
0x180005dc5  movzx   eax, word ptr [rdx]
0x180005dc8  test    ax, ax
0x180005dcb  jz      short loc_180005DE2
0x180005dcd  mov     [r9], ax
0x180005dd1  add     rdx, 2
0x180005dd5  add     r9, 2
0x180005dd9  dec     rcx
0x180005ddc  sub     r8, 1
0x180005de0  jnz     short loc_180005DC0
0x180005de2  xor     eax, eax
0x180005de4  lea     rcx, [r9-2]
0x180005de8  test    r8, r8
0x180005deb  mov     r15d, 8007007Ah
0x180005df1  mov     edx, r15d
0x180005df4  cmovnz  rcx, r9
0x180005df8  cmovnz  edx, eax
0x180005dfb  mov     [rcx], ax
0x180005dfe  jz      loc_180005FE5
0x180005e04  lea     rax, [rsp+788h+var_728]
0x180005e09  nop     dword ptr [rax+00000000h]
0x180005e10  cmp     word ptr [rax], 0
0x180005e14  jz      short loc_180005E20
0x180005e16  add     rax, 2
0x180005e1a  sub     rbx, 1
0x180005e1e  jnz     short loc_180005E10
0x180005e20  xor     eax, eax
0x180005e22  test    rbx, rbx
0x180005e25  cmovnz  r10d, eax
0x180005e29  jz      loc_180005FE8
0x180005e2f  sub     r11, rbx
0x180005e32  cmp     r11, 24h ; '$'
0x180005e36  ja      loc_180005FED
0x180005e3c  lea     rax, [rbx+rbx]
0x180005e40  mov     ebx, 104h
0x180005e45  lea     rcx, [rsp+788h+var_6DC]
0x180005e4d  sub     rcx, rax
0x180005e50  xor     eax, eax
0x180005e52  mov     [rcx], ax
0x180005e55  test    r13, r13
0x180005e58  jnz     loc_18000610D
0x180005e5e  mov     [rsp+788h+var_20], rbp
0x180005e66  lea     rax, [rsp+788h+String1]
0x180005e6e  test    r13, r13
0x180005e71  mov     [rsp+788h+var_28], rsi
0x180005e79  lea     rbp, [rsp+788h+var_728]
0x180005e7e  cmovnz  rbp, rax
0x180005e82  xor     esi, esi
0x180005e84  mov     eax, 2000h
0x180005e89  cmp     cs:word_1800AFC84, ax
0x180005e90  setnz   sil
0x180005e94  add     rsi, 0FFFFFFFF80000001h
0x180005e9b  test    r12, r12
0x180005e9e  jz      loc_180005FDE
0x180005ea4  mov     [rsp+788h+var_38], r14
0x180005eac  mov     qword ptr [r12], 0
0x180005eb4  cmp     rsi, 0FFFFFFFF80000002h
0x180005ebb  jz      loc_18000613E
0x180005ec1  lea     r9, SubKey; "Software\\Microsoft\\Enrollments"
0x180005ec8  mov     [rsp+788h+phkResult], rbp
0x180005ecd  lea     r8, aSS_0; "%s\\%s"
0x180005ed4  mov     rdx, rbx; unsigned __int64
0x180005ed7  lea     rcx, [rsp+788h+SubKey]; unsigned __int16 *
0x180005edf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005ee4  mov     r14d, eax
0x180005ee7  test    eax, eax
0x180005ee9  js      loc_180005F89
0x180005eef  mov     r9d, [rsp+788h+var_738]
0x180005ef4  lea     rdx, [rsp+788h+SubKey]; lpSubKey
0x180005efc  bts     r9d, 8; samDesired
0x180005f01  mov     [rsp+788h+phkResult], r12; phkResult
0x180005f06  xor     r8d, r8d; ulOptions
0x180005f09  mov     rcx, rsi; hKey
0x180005f0c  call    cs:__imp_RegOpenKeyExW
0x180005f12  mov     r14d, eax
0x180005f15  test    eax, eax
0x180005f17  jg      loc_180005FF8
0x180005f1d  lea     rcx, [rsp+788h+SubKey]
0x180005f25  lea     rdx, [rsp+788h+var_478]
0x180005f2d  nop     dword ptr [rax]
0x180005f30  test    rdi, rdi
0x180005f33  jz      short loc_180005F51
0x180005f35  movzx   eax, word ptr [rcx]
0x180005f38  test    ax, ax
0x180005f3b  jz      short loc_180005F51
0x180005f3d  mov     [rdx], ax
0x180005f40  add     rcx, 2
0x180005f44  add     rdx, 2
0x180005f48  dec     rdi
0x180005f4b  sub     rbx, 1
0x180005f4f  jnz     short loc_180005F30
0x180005f51  xor     eax, eax
0x180005f53  lea     rcx, [rdx-2]
0x180005f57  test    rbx, rbx
0x180005f5a  cmovnz  rcx, rdx
0x180005f5e  cmovnz  r15d, eax
0x180005f62  mov     [rcx], ax
0x180005f65  test    r14d, r14d
0x180005f68  js      short loc_180005F72
0x180005f6a  test    rbx, rbx
0x180005f6d  jnz     short loc_180005F99
0x180005f6f  mov     r14d, r15d
0x180005f72  mov     rcx, [r12]; hKey
0x180005f76  test    rcx, rcx
0x180005f79  jz      short loc_180005F89
0x180005f7b  call    cs:__imp_RegCloseKey
0x180005f81  mov     qword ptr [r12], 0
0x180005f89  cmp     r14d, 80070002h
0x180005f90  jz      loc_18000617F
0x180005f96  mov     eax, r14d
0x180005f99  mov     r14, [rsp+788h+var_38]
0x180005fa1  mov     rsi, [rsp+788h+var_28]
0x180005fa9  mov     rbp, [rsp+788h+var_20]
0x180005fb1  mov     rdi, [rsp+788h+var_30]
0x180005fb9  mov     r15, [rsp+788h+var_40]
0x180005fc1  mov     rcx, [rsp+788h+var_58]
0x180005fc9  xor     rcx, rsp; StackCookie
0x180005fcc  call    __security_check_cookie
0x180005fd1  add     rsp, 770h
0x180005fd8  pop     r13
0x180005fda  pop     r12
0x180005fdc  pop     rbx
0x180005fdd  retn
0x180005fde  mov     eax, 80004003h
0x180005fe3  jmp     short loc_180005FA1
0x180005fe5  mov     r10d, edx
0x180005fe8  mov     eax, r10d
0x180005feb  jmp     short loc_180005FB1
0x180005fed  mov     r10d, 8000FFFFh
0x180005ff3  mov     eax, r10d
0x180005ff6  jmp     short loc_180005FB1
0x180005ff8  movzx   r14d, ax
0x180005ffc  or      r14d, 80070000h
0x180006003  jmp     loc_180005F1D
0x180006008  mov     eax, 8000FFFFh
0x18000600d  jmp     short loc_180005FC1
0x18000600f  lea     eax, [r14+7FF8FFFEh]
0x180006016  cmp     eax, 1
0x180006019  jbe     loc_180005EC1
0x18000601f  jmp     loc_180005F1D
0x180006024  mov     r9d, [rsp+788h+var_738]
0x180006029  lea     rdx, [rsp+788h+SubKey]; lpSubKey
0x180006031  bts     r9d, 8; samDesired
0x180006036  mov     [rsp+788h+phkResult], r12; phkResult
0x18000603b  xor     r8d, r8d; ulOptions
0x18000603e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006045  call    cs:__imp_RegOpenKeyExW
0x18000604b  mov     r14d, eax
0x18000604e  test    eax, eax
0x180006050  jle     short loc_18000605D
0x180006052  movzx   r14d, ax
0x180006056  or      r14d, 80070000h
0x18000605d  test    r14d, r14d
0x180006060  jns     short loc_18000600F
0x180006062  mov     r8d, 6; MaxCount
0x180006068  lea     rdx, aStatus; "Status"
0x18000606f  mov     rcx, rbp; String1
0x180006072  call    wcsncmp_0
0x180006077  test    eax, eax
0x180006079  jz      loc_180005F1D
0x18000607f  mov     r8d, 7; MaxCount
0x180006085  lea     rdx, aContext_0; "Context"
0x18000608c  mov     rcx, rbp; String1
0x18000608f  call    wcsncmp_0
0x180006094  test    eax, eax
0x180006096  jz      loc_180005F1D
0x18000609c  jmp     loc_18000600F
0x1800060a1  xor     ecx, ecx
0x1800060a3  mov     [rsp+788h+lpdwDisposition], 0; lpdwDisposition
0x1800060ac  mov     eax, 2000h
0x1800060b1  mov     [rsp+788h+var_750], r12; phkResult
0x1800060b6  cmp     cs:word_1800AFC84, ax
0x1800060bd  lea     rdx, [rsp+788h+var_478]; lpSubKey
0x1800060c5  mov     eax, [rsp+788h+var_738]
0x1800060c9  setnz   cl
0x1800060cc  mov     [rsp+788h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800060d5  bts     eax, 8
0x1800060d9  add     rcx, 0FFFFFFFF80000001h; hKey
0x1800060e0  mov     [rsp+788h+samDesired], eax; samDesired
0x1800060e4  xor     r9d, r9d; lpClass
0x1800060e7  xor     r8d, r8d; Reserved
0x1800060ea  mov     dword ptr [rsp+788h+phkResult], 0; dwOptions
0x1800060f2  call    cs:__imp_RegCreateKeyExW
0x1800060f8  test    eax, eax
0x1800060fa  jle     loc_180005F99
0x180006100  movzx   eax, ax
0x180006103  or      eax, 80070000h
0x180006108  jmp     loc_180005F99
0x18000610d  lea     rax, [rsp+788h+var_728]
0x180006112  mov     r9, r13
0x180006115  lea     r8, aSS_0; "%s\\%s"
0x18000611c  mov     [rsp+788h+phkResult], rax
0x180006121  mov     rdx, rbx; unsigned __int64
0x180006124  lea     rcx, [rsp+788h+String1]; unsigned __int16 *
0x18000612c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006131  test    eax, eax
0x180006133  js      loc_180005FB1
0x180006139  jmp     loc_180005E5E
0x18000613e  call    cs:__imp_RtlIsStateSeparationEnabled
0x180006144  test    al, al
0x180006146  jz      loc_180005EC1
0x18000614c  lea     r9, aOsdataSoftware_8; "OSData\\Software\\Microsoft\\Enrollment"...
0x180006153  mov     [rsp+788h+phkResult], rbp
0x180006158  lea     r8, aSS_0; "%s\\%s"
0x18000615f  mov     rdx, rbx; unsigned __int64
0x180006162  lea     rcx, [rsp+788h+SubKey]; unsigned __int16 *
0x18000616a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000616f  mov     r14d, eax
0x180006172  test    eax, eax
0x180006174  js      loc_180005F89
0x18000617a  jmp     loc_180006024
0x18000617f  test    r13, r13
0x180006182  jz      loc_180005F96
0x180006188  jmp     loc_1800060A1
```
