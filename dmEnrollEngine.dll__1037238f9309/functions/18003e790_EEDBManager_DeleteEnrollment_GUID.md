# EEDBManager::DeleteEnrollment(_GUID)

- ea: `0x18003e790`
- end: `0x18003e8de`
- name: `?DeleteEnrollment@EEDBManager@@UEAAJU_GUID@@@Z`
- size: `334`
- prototype: `int(EEDBManager *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800067a0`
- `0x180007040`
- `0x180007120`
- `0x18000d560`
- `0x18002e1a0`
- `0x18003e790`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18003e8ab`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18003e8ab`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003e7d7`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003e7d7`

## pseudocode

```c
__int64 __fastcall EEDBManager::DeleteEnrollment(EEDBManager *this, struct _GUID *a2)
{
  int v2; // ebx
  const unsigned __int16 *EnrollmentsRootKey; // rax
  unsigned __int64 v5[2]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v6[40]; // [rsp+40h] [rbp-C0h] BYREF
  OLECHAR sz; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v8[39]; // [rsp+92h] [rbp-6Eh] BYREF
  WCHAR SubKey[264]; // [rsp+E0h] [rbp-20h] BYREF

  SubKey[0] = 0;
  v6[0] = 0;
  sz = 0;
  if ( StringFromGUID2(a2, &sz, 39) != 39 )
    return (unsigned int)-2147418113;
  v5[0] = 0;
  v2 = StringCchLengthW(&sz, 0x27u, v5);
  if ( v2 < 0 )
    return (unsigned int)v2;
  if ( v5[0] - 2 > 0x24 )
    return (unsigned int)-2147418113;
  v2 = StringCchCopyW(v6, 0x27u, v8);
  if ( v2 < 0 )
    return (unsigned int)v2;
  v2 = StringCchLengthW(v6, 0x27u, v5);
  if ( v2 < 0 )
    return (unsigned int)v2;
  if ( v5[0] - 2 > 0x24 )
    return (unsigned int)-2147418113;
  *((_WORD *)&v5[1] + v5[0] + 3) = 0;
  EnrollmentsRootKey = EEDBManager::GetEnrollmentsRootKey();
  v2 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", EnrollmentsRootKey, v6);
  if ( v2 >= 0 )
    RegDeleteTreeW((HKEY)((word_1800AFC84 != 0x2000) - 0x7FFFFFFFLL), SubKey);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18003e790  mov     [rsp-8+arg_0], rbx
0x18003e795  mov     [rsp-8+arg_10], rdi
0x18003e79a  push    rbp
0x18003e79b  lea     rbp, [rsp-200h]
0x18003e7a3  sub     rsp, 300h
0x18003e7aa  mov     rax, cs:__security_cookie
0x18003e7b1  xor     rax, rsp
0x18003e7b4  mov     [rbp+200h+var_10], rax
0x18003e7bb  xor     eax, eax
0x18003e7bd  mov     rcx, rdx; rguid
0x18003e7c0  lea     rdx, [rbp+200h+sz]; lpsz
0x18003e7c4  mov     [rbp+200h+SubKey], ax
0x18003e7c8  mov     [rsp+300h+var_2C0], ax
0x18003e7cd  mov     [rbp+200h+sz], ax
0x18003e7d1  lea     edi, [rax+27h]
0x18003e7d4  mov     r8d, edi; cchMax
0x18003e7d7  call    cs:__imp_StringFromGUID2
0x18003e7dd  cmp     eax, edi
0x18003e7df  jnz     loc_18003E8B3
0x18003e7e5  lea     r8, [rsp+300h+var_2D0]; unsigned __int64 *
0x18003e7ea  mov     [rsp+300h+var_2D0], 0
0x18003e7f3  mov     edx, edi; unsigned __int64
0x18003e7f5  lea     rcx, [rbp+200h+sz]; unsigned __int16 *
0x18003e7f9  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18003e7fe  mov     ebx, eax
0x18003e800  test    eax, eax
0x18003e802  js      loc_18003E8B8
0x18003e808  mov     rax, [rsp+300h+var_2D0]
0x18003e80d  add     rax, 0FFFFFFFFFFFFFFFEh
0x18003e811  cmp     rax, 24h ; '$'
0x18003e815  ja      loc_18003E8B3
0x18003e81b  lea     r8, [rbp+200h+var_26E]; unsigned __int16 *
0x18003e81f  mov     edx, edi; unsigned __int64
0x18003e821  lea     rcx, [rsp+300h+var_2C0]; unsigned __int16 *
0x18003e826  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003e82b  mov     ebx, eax
0x18003e82d  test    eax, eax
0x18003e82f  js      loc_18003E8B8
0x18003e835  lea     r8, [rsp+300h+var_2D0]; unsigned __int64 *
0x18003e83a  mov     edx, edi; unsigned __int64
0x18003e83c  lea     rcx, [rsp+300h+var_2C0]; unsigned __int16 *
0x18003e841  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18003e846  mov     ebx, eax
0x18003e848  test    eax, eax
0x18003e84a  js      short loc_18003E8B8
0x18003e84c  mov     rcx, [rsp+300h+var_2D0]
0x18003e851  lea     rax, [rcx-2]
0x18003e855  cmp     rax, 24h ; '$'
0x18003e859  ja      short loc_18003E8B3
0x18003e85b  xor     eax, eax
0x18003e85d  mov     [rsp+rcx*2+300h+var_2C2], ax
0x18003e862  call    ?GetEnrollmentsRootKey@EEDBManager@@SAPEBGXZ; EEDBManager::GetEnrollmentsRootKey(void)
0x18003e867  mov     r9, rax
0x18003e86a  lea     r8, aSS_0; "%s\\%s"
0x18003e871  lea     rax, [rsp+300h+var_2C0]
0x18003e876  mov     edx, 104h; unsigned __int64
0x18003e87b  lea     rcx, [rbp+200h+SubKey]; unsigned __int16 *
0x18003e87f  mov     [rsp+300h+var_2E0], rax
0x18003e884  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003e889  mov     ebx, eax
0x18003e88b  test    eax, eax
0x18003e88d  js      short loc_18003E8B8
0x18003e88f  xor     ecx, ecx
0x18003e891  lea     rdx, [rbp+200h+SubKey]; lpSubKey
0x18003e895  mov     eax, 2000h
0x18003e89a  cmp     cs:word_1800AFC84, ax
0x18003e8a1  setnz   cl
0x18003e8a4  add     rcx, 0FFFFFFFF80000001h; hKey
0x18003e8ab  call    cs:__imp_RegDeleteTreeW
0x18003e8b1  jmp     short loc_18003E8B8
0x18003e8b3  mov     ebx, 8000FFFFh
0x18003e8b8  mov     eax, ebx
0x18003e8ba  mov     rcx, [rbp+200h+var_10]
0x18003e8c1  xor     rcx, rsp; StackCookie
0x18003e8c4  call    __security_check_cookie
0x18003e8c9  lea     r11, [rsp+300h+var_s0]
0x18003e8d1  mov     rbx, [r11+10h]
0x18003e8d5  mov     rdi, [r11+20h]
0x18003e8d9  mov     rsp, r11
0x18003e8dc  pop     rbp
0x18003e8dd  retn
```
