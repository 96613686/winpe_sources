# EEDBManager::SetEnrollState(_GUID,EnrollmentStateTag)

- ea: `0x18001d580`
- end: `0x18001d71b`
- name: `?SetEnrollState@EEDBManager@@SAJU_GUID@@W4EnrollmentStateTag@@@Z`
- size: `411`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d42c`
- `0x180037230`
- `0x180040b60`
- `0x180040bc0`

## callees

- `0x180006e00`
- `0x180007040`
- `0x180007120`
- `0x1800071c0`
- `0x18001d580`
- `0x18002e1a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001d6cb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001d6cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d6f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d6f3`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001d5c6`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001d5c6`

## pseudocode

```c
__int64 __fastcall EEDBManager::SetEnrollState(const GUID *a1, int a2)
{
  HKEY v2; // rbx
  int v3; // edi
  LSTATUS v4; // eax
  unsigned __int64 v6; // [rsp+30h] [rbp-89h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-81h] BYREF
  HKEY v8; // [rsp+40h] [rbp-79h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-71h] BYREF
  wchar_t String1[40]; // [rsp+50h] [rbp-69h] BYREF
  OLECHAR sz; // [rsp+A0h] [rbp-19h] BYREF
  unsigned __int16 v12[39]; // [rsp+A2h] [rbp-17h] BYREF

  v2 = 0;
  *(_DWORD *)Data = a2;
  hKey = 0;
  v8 = 0;
  String1[0] = 0;
  sz = 0;
  if ( StringFromGUID2(a1, &sz, 39) != 39 )
    return (unsigned int)-2147418113;
  v6 = 0;
  v3 = StringCchLengthW(&sz, 0x27u, &v6);
  if ( v3 >= 0 )
  {
    if ( v6 - 2 > 0x24 )
    {
LABEL_13:
      v3 = -2147418113;
      goto LABEL_14;
    }
    v3 = StringCchCopyW(String1, 0x27u, v12);
    if ( v3 >= 0 )
    {
      v3 = StringCchLengthW(String1, 0x27u, &v6);
      if ( v3 >= 0 )
      {
        if ( v6 - 2 <= 0x24 )
        {
          String1[v6 - 1] = 0;
          v3 = EEDBManager::OpenEnrollmentHKEY(
                 (HKEY)((word_1800AFC84 != 0x2000) - 0x7FFFFFFFLL),
                 String1,
                 131078,
                 &v8,
                 0,
                 0);
          if ( v3 < 0 )
            return (unsigned int)v3;
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
            &hKey,
            v8);
          v2 = hKey;
          v4 = RegSetValueExW(hKey, L"EnrollmentState", 0, 4u, Data, 4u);
          if ( v4 )
          {
            if ( v4 > 0 )
              v3 = (unsigned __int16)v4 | 0x80070000;
            else
              v3 = v4;
          }
          goto LABEL_14;
        }
        goto LABEL_13;
      }
    }
  }
LABEL_14:
  if ( v2 )
    RegCloseKey(v2);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001d580  mov     [rsp-8+arg_10], rbx
0x18001d585  push    rbp
0x18001d586  push    rdi
0x18001d587  push    r14
0x18001d589  lea     rbp, [rsp-47h]
0x18001d58e  sub     rsp, 100h
0x18001d595  mov     rax, cs:__security_cookie
0x18001d59c  xor     rax, rsp
0x18001d59f  mov     [rbp+57h+var_20], rax
0x18001d5a3  xor     ebx, ebx
0x18001d5a5  mov     dword ptr [rsp+110h+Data], edx
0x18001d5a9  xor     eax, eax
0x18001d5ab  mov     [rbp+57h+hKey], rbx
0x18001d5af  lea     rdx, [rbp+57h+sz]; lpsz
0x18001d5b3  mov     [rbp+57h+var_D0], rbx
0x18001d5b7  mov     [rbp+57h+String1], ax
0x18001d5bb  lea     r14d, [rbx+27h]
0x18001d5bf  mov     [rbp+57h+sz], ax
0x18001d5c3  mov     r8d, r14d; cchMax
0x18001d5c6  call    cs:__imp_StringFromGUID2
0x18001d5cc  cmp     eax, r14d
0x18001d5cf  jz      short loc_18001D5DB
0x18001d5d1  mov     edi, 8000FFFFh
0x18001d5d6  jmp     loc_18001D6F9
0x18001d5db  lea     r8, [rsp+110h+var_E0]; unsigned __int64 *
0x18001d5e0  mov     [rsp+110h+var_E0], rbx
0x18001d5e5  mov     rdx, r14; unsigned __int64
0x18001d5e8  lea     rcx, [rbp+57h+sz]; unsigned __int16 *
0x18001d5ec  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001d5f1  mov     edi, eax
0x18001d5f3  test    eax, eax
0x18001d5f5  js      loc_18001D6EB
0x18001d5fb  mov     rax, [rsp+110h+var_E0]
0x18001d600  add     rax, 0FFFFFFFFFFFFFFFEh
0x18001d604  cmp     rax, 24h ; '$'
0x18001d608  ja      loc_18001D6E6
0x18001d60e  lea     r8, [rbp+57h+var_6E]; unsigned __int16 *
0x18001d612  mov     rdx, r14; unsigned __int64
0x18001d615  lea     rcx, [rbp+57h+String1]; unsigned __int16 *
0x18001d619  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001d61e  mov     edi, eax
0x18001d620  test    eax, eax
0x18001d622  js      loc_18001D6EB
0x18001d628  lea     r8, [rsp+110h+var_E0]; unsigned __int64 *
0x18001d62d  mov     rdx, r14; unsigned __int64
0x18001d630  lea     rcx, [rbp+57h+String1]; unsigned __int16 *
0x18001d634  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001d639  mov     edi, eax
0x18001d63b  test    eax, eax
0x18001d63d  js      loc_18001D6EB
0x18001d643  mov     rcx, [rsp+110h+var_E0]
0x18001d648  lea     rax, [rcx-2]
0x18001d64c  cmp     rax, 24h ; '$'
0x18001d650  ja      loc_18001D6E6
0x18001d656  xor     eax, eax
0x18001d658  mov     qword ptr [rsp+110h+cbData], rbx; unsigned __int64
0x18001d65d  mov     word ptr [rbp+rcx*2+57h+hKey+6], ax
0x18001d662  lea     r9, [rbp+57h+var_D0]; HKEY *
0x18001d666  xor     ecx, ecx
0x18001d668  mov     [rsp+110h+lpData], rbx; unsigned __int16 *
0x18001d66d  mov     eax, 2000h
0x18001d672  lea     rdx, [rbp+57h+String1]; String1
0x18001d676  cmp     cs:word_1800AFC84, ax
0x18001d67d  mov     r8d, 20006h; unsigned int
0x18001d683  setnz   cl
0x18001d686  add     rcx, 0FFFFFFFF80000001h; hKey
0x18001d68d  call    ?OpenEnrollmentHKEY@EEDBManager@@SAJPEAUHKEY__@@PEBGKPEAPEAU2@PEAG_K@Z; EEDBManager::OpenEnrollmentHKEY(HKEY__ *,ushort const *,ulong,HKEY__ * *,ushort *,unsigned __int64)
0x18001d692  mov     edi, eax
0x18001d694  test    eax, eax
0x18001d696  js      short loc_18001D6F9
0x18001d698  mov     rdx, [rbp+57h+var_D0]
0x18001d69c  lea     rcx, [rbp+57h+hKey]
0x18001d6a0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001d6a5  mov     rbx, [rbp+57h+hKey]
0x18001d6a9  lea     rax, [rsp+110h+Data]
0x18001d6ae  mov     r9d, 4; dwType
0x18001d6b4  lea     rdx, Value; "EnrollmentState"
0x18001d6bb  mov     [rsp+110h+cbData], r9d; cbData
0x18001d6c0  xor     r8d, r8d; Reserved
0x18001d6c3  mov     rcx, rbx; hKey
0x18001d6c6  mov     [rsp+110h+lpData], rax; lpData
0x18001d6cb  call    cs:__imp_RegSetValueExW
0x18001d6d1  test    eax, eax
0x18001d6d3  jz      short loc_18001D6EB
0x18001d6d5  jg      short loc_18001D6DB
0x18001d6d7  mov     edi, eax
0x18001d6d9  jmp     short loc_18001D6EB
0x18001d6db  movzx   edi, ax
0x18001d6de  or      edi, 80070000h
0x18001d6e4  jmp     short loc_18001D6EB
0x18001d6e6  mov     edi, 8000FFFFh
0x18001d6eb  test    rbx, rbx
0x18001d6ee  jz      short loc_18001D6F9
0x18001d6f0  mov     rcx, rbx; hKey
0x18001d6f3  call    cs:__imp_RegCloseKey
0x18001d6f9  mov     eax, edi
0x18001d6fb  mov     rcx, [rbp+57h+var_20]
0x18001d6ff  xor     rcx, rsp; StackCookie
0x18001d702  call    __security_check_cookie
0x18001d707  mov     rbx, [rsp+110h+arg_10]
0x18001d70f  add     rsp, 100h
0x18001d716  pop     r14
0x18001d718  pop     rdi
0x18001d719  pop     rbp
0x18001d71a  retn
```
