# RegistryGetAllSubKeys

- ea: `0x18006f9e0`
- end: `0x18006fc01`
- name: `RegistryGetAllSubKeys`
- size: `545`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006f7f4`

## callees

- `0x18000dd20`
- `0x18002ec8c`
- `0x18006f9e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18006fb44`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18006fb44`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18006fa63`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18006fa63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006fbcc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006fbda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006fbcc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006fbda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006faa2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006faf8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006faa2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006faf8`
- `OLEAUT32!__imp_SysAllocString` at `0x18006fb51`
- `OLEAUT32!__imp_SysAllocString` at `0x18006fb51`
- `OLEAUT32!__imp_SysFreeString` at `0x18006fbb0`
- `OLEAUT32!__imp_SysFreeString` at `0x18006fbb0`

## pseudocode

```c
__int64 __fastcall RegistryGetAllSubKeys(HKEY hKey, DWORD *a2, _QWORD *a3)
{
  DWORD v3; // r14d
  LSTATUS v7; // eax
  signed int v8; // ebx
  size_t v9; // rbx
  _QWORD *v10; // rax
  _QWORD *v11; // rsi
  WCHAR *v12; // rdi
  __int64 v13; // rcx
  LSTATUS v14; // eax
  BSTR v15; // rax
  DWORD v16; // eax
  OLECHAR *v17; // rcx
  DWORD cb[4]; // [rsp+60h] [rbp-10h] BYREF
  DWORD v20; // [rsp+B0h] [rbp+40h] BYREF
  DWORD cSubKeys; // [rsp+C8h] [rbp+58h] BYREF

  v3 = 0;
  cSubKeys = 0;
  v20 = 0;
  cb[0] = 0;
  if ( hKey && a2 && a3 )
  {
    *a2 = 0;
    *a3 = 0;
    v7 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &v20, 0, 0, 0, 0, 0, 0);
    v8 = v7;
    if ( v7 )
    {
      if ( v7 > 0 )
        return (unsigned __int16)v7 | 0x80070000;
    }
    else
    {
      v8 = ULongLongToULong(8LL * cSubKeys, cb);
      if ( v8 >= 0 )
      {
        v9 = cb[0];
        v10 = CoTaskMemAlloc(cb[0]);
        v11 = v10;
        if ( v10 )
        {
          v12 = 0;
          memset_0(v10, 0, v9);
          v13 = v20 + 1;
          if ( (unsigned int)v13 < v20 )
          {
            v20 = -1;
            v8 = -2147024362;
          }
          else
          {
            ++v20;
            cb[0] = 0;
            v8 = ULongLongToULong(2 * v13, cb);
            if ( v8 >= 0 )
            {
              v12 = (WCHAR *)CoTaskMemAlloc(cb[0]);
              if ( v12 )
              {
                while ( 1 )
                {
                  if ( v3 >= cSubKeys )
                  {
                    *a2 = cSubKeys;
                    *a3 = v11;
                    goto LABEL_29;
                  }
                  cb[0] = v20;
                  *v12 = 0;
                  v14 = RegEnumKeyExW(hKey, v3, v12, cb, 0, 0, 0, 0);
                  if ( v14 )
                    break;
                  v15 = SysAllocString(v12);
                  v11[v3] = v15;
                  if ( !v15 )
                  {
                    v8 = -2147024882;
                    v3 = 0;
                    goto LABEL_24;
                  }
                  ++v3;
                }
                v3 = 0;
                if ( v14 > 0 )
                  v8 = (unsigned __int16)v14 | 0x80070000;
                else
                  v8 = v14;
              }
              else
              {
                v8 = -2147024882;
              }
            }
          }
LABEL_24:
          v16 = cSubKeys;
          if ( cSubKeys )
          {
            do
            {
              v17 = (OLECHAR *)v11[v3];
              if ( v17 )
              {
                SysFreeString(v17);
                v11[v3] = 0;
                v16 = cSubKeys;
              }
              ++v3;
            }
            while ( v3 < v16 );
          }
          CoTaskMemFree(v11);
          if ( v12 )
LABEL_29:
            CoTaskMemFree(v12);
        }
        else
        {
          return (unsigned int)-2147024882;
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18006f9e0  mov     r11, rsp
0x18006f9e3  mov     [r11+10h], rbx
0x18006f9e7  push    rbp
0x18006f9e8  push    rsi
0x18006f9e9  push    rdi
0x18006f9ea  push    r12
0x18006f9ec  push    r13
0x18006f9ee  push    r14
0x18006f9f0  push    r15
0x18006f9f2  mov     rbp, rsp
0x18006f9f5  sub     rsp, 70h
0x18006f9f9  xor     r14d, r14d
0x18006f9fc  mov     r15, r8
0x18006f9ff  mov     [rbp+cSubKeys], r14d
0x18006fa03  mov     r12, rdx
0x18006fa06  mov     [rbp+arg_0], r14d
0x18006fa0a  mov     r13, rcx
0x18006fa0d  mov     [rbp+cb], r14d
0x18006fa11  test    rcx, rcx
0x18006fa14  jz      loc_18006FBE2
0x18006fa1a  test    rdx, rdx
0x18006fa1d  jz      loc_18006FBE2
0x18006fa23  test    r8, r8
0x18006fa26  jz      loc_18006FBE2
0x18006fa2c  mov     [r11-50h], r14
0x18006fa30  lea     rax, [rbp+arg_0]
0x18006fa34  mov     [r11-58h], r14
0x18006fa38  xor     r9d, r9d; lpReserved
0x18006fa3b  mov     [r11-60h], r14
0x18006fa3f  mov     [r11-68h], r14
0x18006fa43  mov     [r11-70h], r14
0x18006fa47  mov     [r11-78h], r14
0x18006fa4b  mov     [r11-80h], rax
0x18006fa4f  lea     rax, [rbp+cSubKeys]
0x18006fa53  mov     [rdx], r14d
0x18006fa56  xor     edx, edx; lpClass
0x18006fa58  mov     [r8], r14
0x18006fa5b  xor     r8d, r8d; lpcchClass
0x18006fa5e  mov     [rsp+70h+lpcSubKeys], rax; lpcSubKeys
0x18006fa63  call    cs:__imp_RegQueryInfoKeyW
0x18006fa69  mov     ebx, eax
0x18006fa6b  test    eax, eax
0x18006fa6d  jz      short loc_18006FA83
0x18006fa6f  jle     loc_18006FBE7
0x18006fa75  movzx   ebx, ax
0x18006fa78  or      ebx, 80070000h
0x18006fa7e  jmp     loc_18006FBE7
0x18006fa83  mov     ecx, [rbp+cSubKeys]
0x18006fa86  lea     rdx, [rbp+cb]; unsigned int *
0x18006fa8a  shl     rcx, 3; unsigned __int64
0x18006fa8e  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18006fa93  mov     ebx, eax
0x18006fa95  test    eax, eax
0x18006fa97  js      loc_18006FBE7
0x18006fa9d  mov     ebx, [rbp+cb]
0x18006faa0  mov     ecx, ebx; cb
0x18006faa2  call    cs:__imp_CoTaskMemAlloc
0x18006faa8  mov     rsi, rax
0x18006faab  test    rax, rax
0x18006faae  jnz     short loc_18006FABA
0x18006fab0  mov     ebx, 8007000Eh
0x18006fab5  jmp     loc_18006FBE7
0x18006faba  mov     r8, rbx; Size
0x18006fabd  xor     edx, edx; Val
0x18006fabf  mov     rcx, rsi; void *
0x18006fac2  mov     rdi, r14
0x18006fac5  call    memset_0
0x18006faca  mov     eax, [rbp+arg_0]
0x18006facd  lea     ecx, [rax+1]
0x18006fad0  cmp     ecx, eax
0x18006fad2  jb      loc_18006FB91
0x18006fad8  mov     [rbp+arg_0], ecx
0x18006fadb  lea     rdx, [rbp+cb]; unsigned int *
0x18006fadf  add     rcx, rcx; unsigned __int64
0x18006fae2  mov     [rbp+cb], r14d
0x18006fae6  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18006faeb  mov     ebx, eax
0x18006faed  test    eax, eax
0x18006faef  js      loc_18006FB9D
0x18006faf5  mov     ecx, [rbp+cb]; cb
0x18006faf8  call    cs:__imp_CoTaskMemAlloc
0x18006fafe  mov     rdi, rax
0x18006fb01  test    rax, rax
0x18006fb04  jnz     short loc_18006FB10
0x18006fb06  mov     ebx, 8007000Eh
0x18006fb0b  jmp     loc_18006FB9D
0x18006fb10  mov     eax, [rbp+cSubKeys]
0x18006fb13  cmp     r14d, eax
0x18006fb16  jnb     short loc_18006FB88
0x18006fb18  mov     eax, [rbp+arg_0]
0x18006fb1b  lea     r9, [rbp+cb]; lpcchName
0x18006fb1f  mov     [rbp+cb], eax
0x18006fb22  mov     r8, rdi; lpName
0x18006fb25  xor     eax, eax
0x18006fb27  mov     edx, r14d; dwIndex
0x18006fb2a  mov     [rsp+70h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18006fb2f  mov     rcx, r13; hKey
0x18006fb32  mov     [rsp+70h+lpcchClass], rax; lpcchClass
0x18006fb37  mov     [rsp+70h+lpClass], rax; lpClass
0x18006fb3c  mov     [rsp+70h+lpcSubKeys], rax; lpReserved
0x18006fb41  mov     [rdi], ax
0x18006fb44  call    cs:__imp_RegEnumKeyExW
0x18006fb4a  test    eax, eax
0x18006fb4c  jnz     short loc_18006FB72
0x18006fb4e  mov     rcx, rdi; psz
0x18006fb51  call    cs:__imp_SysAllocString
0x18006fb57  mov     ecx, r14d
0x18006fb5a  mov     [rsi+rcx*8], rax
0x18006fb5e  test    rax, rax
0x18006fb61  jz      short loc_18006FB68
0x18006fb63  inc     r14d
0x18006fb66  jmp     short loc_18006FB10
0x18006fb68  mov     ebx, 8007000Eh
0x18006fb6d  xor     r14d, r14d
0x18006fb70  jmp     short loc_18006FB9D
0x18006fb72  xor     r14d, r14d
0x18006fb75  test    eax, eax
0x18006fb77  jg      short loc_18006FB7D
0x18006fb79  mov     ebx, eax
0x18006fb7b  jmp     short loc_18006FB9D
0x18006fb7d  movzx   ebx, ax
0x18006fb80  or      ebx, 80070000h
0x18006fb86  jmp     short loc_18006FB9D
0x18006fb88  mov     [r12], eax
0x18006fb8c  mov     [r15], rsi
0x18006fb8f  jmp     short loc_18006FBD7
0x18006fb91  mov     [rbp+arg_0], 0FFFFFFFFh
0x18006fb98  mov     ebx, 80070216h
0x18006fb9d  mov     eax, [rbp+cSubKeys]
0x18006fba0  test    eax, eax
0x18006fba2  jz      short loc_18006FBC9
0x18006fba4  mov     r15d, r14d
0x18006fba7  mov     rcx, [rsi+r15*8]; bstrString
0x18006fbab  test    rcx, rcx
0x18006fbae  jz      short loc_18006FBC1
0x18006fbb0  call    cs:__imp_SysFreeString
0x18006fbb6  mov     qword ptr [rsi+r15*8], 0
0x18006fbbe  mov     eax, [rbp+cSubKeys]
0x18006fbc1  inc     r14d
0x18006fbc4  cmp     r14d, eax
0x18006fbc7  jb      short loc_18006FBA4
0x18006fbc9  mov     rcx, rsi; pv
0x18006fbcc  call    cs:__imp_CoTaskMemFree
0x18006fbd2  test    rdi, rdi
0x18006fbd5  jz      short loc_18006FBE7
0x18006fbd7  mov     rcx, rdi; pv
0x18006fbda  call    cs:__imp_CoTaskMemFree
0x18006fbe0  jmp     short loc_18006FBE7
0x18006fbe2  mov     ebx, 80070057h
0x18006fbe7  mov     eax, ebx
0x18006fbe9  mov     rbx, [rsp+70h+arg_8]
0x18006fbf1  add     rsp, 70h
0x18006fbf5  pop     r15
0x18006fbf7  pop     r14
0x18006fbf9  pop     r13
0x18006fbfb  pop     r12
0x18006fbfd  pop     rdi
0x18006fbfe  pop     rsi
0x18006fbff  pop     rbp
0x18006fc00  retn
```
