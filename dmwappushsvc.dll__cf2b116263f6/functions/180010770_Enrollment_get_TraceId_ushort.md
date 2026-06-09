# Enrollment::get_TraceId(ushort * *)

- ea: `0x180010770`
- end: `0x1800108f9`
- name: `?get_TraceId@Enrollment@@UEAAJPEAPEAG@Z`
- size: `393`
- prototype: `__int64 __fastcall(Enrollment *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x180001a70`
- `0x180002554`
- `0x1800040a4`
- `0x18000b4d8`
- `0x18000dd1c`
- `0x18000eecc`
- `0x1800102d4`
- `0x180010378`
- `0x180010770`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800108c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800108c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800108b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800108b0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010873`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010873`
- `OLEAUT32!__imp_SysAllocString` at `0x1800108a7`
- `OLEAUT32!__imp_SysAllocString` at `0x1800108a7`

## pseudocode

```c
__int64 __fastcall Enrollment::get_TraceId(Enrollment *this, unsigned __int16 **a2)
{
  const unsigned __int16 *v4; // rax
  unsigned __int64 v5; // rdx
  int String; // ebx
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // rcx
  __int64 v10; // rax
  int v11; // eax
  bool v12; // sf
  HANDLE ProcessHeap; // rax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  OLECHAR *psz; // [rsp+38h] [rbp-C8h]
  WCHAR SubKey[264]; // [rsp+40h] [rbp-C0h] BYREF

  memset_0(SubKey, 0, 0x208u);
  hKey = 0;
  psz = 0;
  v4 = (const unsigned __int16 *)DMGetKnownRegPath();
  String = StringCchCopyW(SubKey, 0x104u, v4);
  if ( String >= 0 )
  {
    String = StringCchCatW(SubKey, v5, L"Status");
    if ( String >= 0 )
    {
      String = StringCchCatW(SubKey, v7, L"\\");
      if ( String >= 0 )
      {
        v9 = (unsigned __int64)this + 150;
        v10 = -1;
        do
          ++v10;
        while ( *(_WORD *)(v9 + 2 * v10) );
        String = StringCchCatW(SubKey, v8, (const unsigned __int16 *)(v9 & -(__int64)(v10 != 0)));
        if ( String >= 0 )
        {
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
            &hKey,
            0);
          v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey);
          v12 = v11 < 0;
          if ( v11 > 0 )
          {
            v11 = (unsigned __int16)v11 | 0x80070000;
            v12 = v11 < 0;
          }
          if ( v12 )
          {
            String = v11;
          }
          else
          {
            String = RegistryAllocAndGetString(hKey);
            if ( String >= 0 )
            {
              *a2 = SysAllocString(psz);
              ProcessHeap = GetProcessHeap();
              HeapFree(ProcessHeap, 0, psz);
            }
          }
        }
      }
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x180010770  mov     [rsp-8+arg_10], rbx
0x180010775  mov     [rsp-8+arg_18], rsi
0x18001077a  push    rbp
0x18001077b  push    rdi
0x18001077c  push    r14
0x18001077e  lea     rbp, [rsp-160h]
0x180010786  sub     rsp, 260h
0x18001078d  mov     rax, cs:__security_cookie
0x180010794  xor     rax, rsp
0x180010797  mov     [rbp+170h+var_20], rax
0x18001079e  mov     rsi, rdx
0x1800107a1  mov     rdi, rcx
0x1800107a4  xor     edx, edx; Val
0x1800107a6  lea     rcx, [rsp+270h+SubKey]; void *
0x1800107ab  mov     r8d, 208h; Size
0x1800107b1  call    memset_0
0x1800107b6  xor     r14d, r14d
0x1800107b9  mov     [rsp+270h+hKey], r14
0x1800107be  mov     [rsp+270h+psz], r14
0x1800107c3  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x1800107c8  mov     r8, rax; unsigned __int16 *
0x1800107cb  lea     rcx, [rsp+270h+SubKey]; unsigned __int16 *
0x1800107d0  mov     edx, 104h; unsigned __int64
0x1800107d5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800107da  mov     ebx, eax
0x1800107dc  test    eax, eax
0x1800107de  js      loc_1800108C6
0x1800107e4  lea     r8, aStatus; "Status"
0x1800107eb  lea     rcx, [rsp+270h+SubKey]; unsigned __int16 *
0x1800107f0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800107f5  mov     ebx, eax
0x1800107f7  test    eax, eax
0x1800107f9  js      loc_1800108C6
0x1800107ff  lea     r8, asc_1800141F4; "\\"
0x180010806  lea     rcx, [rsp+270h+SubKey]; unsigned __int16 *
0x18001080b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180010810  mov     ebx, eax
0x180010812  test    eax, eax
0x180010814  js      loc_1800108C6
0x18001081a  lea     rcx, [rdi+96h]
0x180010821  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010825  inc     rax
0x180010828  cmp     [rcx+rax*2], r14w
0x18001082d  jnz     short loc_180010825
0x18001082f  neg     rax
0x180010832  sbb     r8, r8
0x180010835  and     r8, rcx; unsigned __int16 *
0x180010838  lea     rcx, [rsp+270h+SubKey]; unsigned __int16 *
0x18001083d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180010842  mov     ebx, eax
0x180010844  test    eax, eax
0x180010846  js      short loc_1800108C6
0x180010848  xor     edx, edx
0x18001084a  lea     rcx, [rsp+270h+hKey]
0x18001084f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180010854  lea     rax, [rsp+270h+hKey]
0x180010859  mov     r9d, 1; samDesired
0x18001085f  xor     r8d, r8d; ulOptions
0x180010862  mov     [rsp+270h+phkResult], rax; phkResult
0x180010867  lea     rdx, [rsp+270h+SubKey]; lpSubKey
0x18001086c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180010873  call    cs:__imp_RegOpenKeyExW
0x180010879  test    eax, eax
0x18001087b  jle     short loc_180010887
0x18001087d  movzx   eax, ax
0x180010880  or      eax, 80070000h
0x180010885  test    eax, eax
0x180010887  jns     short loc_18001088D
0x180010889  mov     ebx, eax
0x18001088b  jmp     short loc_1800108C6
0x18001088d  mov     rcx, [rsp+270h+hKey]; hKey
0x180010892  lea     r8, [rsp+270h+psz]
0x180010897  call    RegistryAllocAndGetString
0x18001089c  mov     ebx, eax
0x18001089e  test    eax, eax
0x1800108a0  js      short loc_1800108C6
0x1800108a2  mov     rcx, [rsp+270h+psz]; psz
0x1800108a7  call    cs:__imp_SysAllocString
0x1800108ad  mov     [rsi], rax
0x1800108b0  call    cs:__imp_GetProcessHeap
0x1800108b6  mov     r8, [rsp+270h+psz]; lpMem
0x1800108bb  xor     edx, edx; dwFlags
0x1800108bd  mov     rcx, rax; hHeap
0x1800108c0  call    cs:__imp_HeapFree
0x1800108c6  lea     rcx, [rsp+270h+hKey]
0x1800108cb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800108d0  mov     eax, ebx
0x1800108d2  mov     rcx, [rbp+170h+var_20]
0x1800108d9  xor     rcx, rsp; StackCookie
0x1800108dc  call    __security_check_cookie
0x1800108e1  lea     r11, [rsp+270h+var_10]
0x1800108e9  mov     rbx, [r11+30h]
0x1800108ed  mov     rsi, [r11+38h]
0x1800108f1  mov     rsp, r11
0x1800108f4  pop     r14
0x1800108f6  pop     rdi
0x1800108f7  pop     rbp
0x1800108f8  retn
```
