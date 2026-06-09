# IsStreamEnabled(void)

- ea: `0x180052d28`
- end: `0x180052e1c`
- name: `?IsStreamEnabled@@YAHXZ`
- size: `244`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028940`
- `0x18002ac04`

## callees

- `0x180015f88`
- `0x180048d78`
- `0x180052d28`
- `0x180083c10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180052d42`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180052d42`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052df6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052df6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180052d4d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180052d4d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180052e01`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180052e01`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180052dab`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180052dab`

## pseudocode

```c
__int64 IsStreamEnabled(void)
{
  unsigned int v0; // ebx
  int v1; // ecx
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+30h] [rbp-48h] BYREF
  WCHAR String2; // [rsp+58h] [rbp-20h] BYREF

  InitializeCriticalSection(&CriticalSection);
  EnterCriticalSection(&CriticalSection);
  if ( dword_18029A888 )
  {
    v0 = dword_18029A88C;
  }
  else
  {
    String2 = 0;
    if ( (int)GetString((__int64 *)SettingStore::IEVALUE_Ried_InternetExplorerMkEnabled[0], &String2, 4) < 0 )
    {
      v1 = dword_18029A88C;
    }
    else
    {
      v1 = CompareStringW(0x7Fu, 0x1001u, L"yes", -1, &String2, -1) == 2;
      dword_18029A88C = v1;
    }
    if ( v1 )
    {
      v1 = CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::PRIVATE_INTERNETFEATURELIST_FEATURE_DISABLE_MK_PROTOCOL) == 1;
      dword_18029A88C = v1;
    }
    dword_18029A888 = 1;
    v0 = v1;
  }
  LeaveCriticalSection(&CriticalSection);
  DeleteCriticalSection(&CriticalSection);
  return v0;
}

```

## disassembly

```asm
0x180052d28  push    rbx
0x180052d2a  sub     rsp, 70h
0x180052d2e  mov     rax, cs:__security_cookie
0x180052d35  xor     rax, rsp
0x180052d38  mov     [rsp+78h+var_18], rax
0x180052d3d  lea     rcx, [rsp+78h+CriticalSection]; lpCriticalSection
0x180052d42  call    cs:__imp_InitializeCriticalSection
0x180052d48  lea     rcx, [rsp+78h+CriticalSection]; lpCriticalSection
0x180052d4d  call    cs:__imp_EnterCriticalSection
0x180052d53  cmp     cs:dword_18029A888, 0
0x180052d5a  jz      short loc_180052D67
0x180052d5c  mov     ebx, cs:dword_18029A88C
0x180052d62  jmp     loc_180052DF1
0x180052d67  mov     rcx, cs:?IEVALUE_Ried_InternetExplorerMkEnabled@SettingStore@@3U?$VALUEID@PEAG@1@B; SettingStore::VALUEID<ushort *> const SettingStore::IEVALUE_Ried_InternetExplorerMkEnabled
0x180052d6e  lea     rdx, [rsp+78h+String2]
0x180052d73  xor     eax, eax
0x180052d75  mov     [rsp+78h+String2], ax
0x180052d7a  lea     r8d, [rax+4]
0x180052d7e  call    GetString
0x180052d83  test    eax, eax
0x180052d85  js      short loc_180052DC1
0x180052d87  or      r9d, 0FFFFFFFFh; cchCount1
0x180052d8b  lea     rax, [rsp+78h+String2]
0x180052d90  mov     [rsp+78h+cchCount2], r9d; cchCount2
0x180052d95  lea     r8, aYes_3; "yes"
0x180052d9c  mov     edx, 1001h; dwCmpFlags
0x180052da1  mov     [rsp+78h+lpString2], rax; lpString2
0x180052da6  mov     ecx, 7Fh; Locale
0x180052dab  call    cs:__imp_CompareStringW
0x180052db1  xor     ecx, ecx
0x180052db3  add     eax, 0FFFFFFFEh
0x180052db6  setz    cl
0x180052db9  mov     cs:dword_18029A88C, ecx
0x180052dbf  jmp     short loc_180052DC7
0x180052dc1  mov     ecx, cs:dword_18029A88C
0x180052dc7  test    ecx, ecx
0x180052dc9  jz      short loc_180052DE5
0x180052dcb  lea     rcx, ?PRIVATE_INTERNETFEATURELIST_FEATURE_DISABLE_MK_PROTOCOL@FCK@@3VCFeatureControlKey@@A; this
0x180052dd2  call    ?_CoInternetIsFeatureEnabledInternal@CFeatureControlKey@@QEAAJXZ; CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(void)
0x180052dd7  xor     ecx, ecx
0x180052dd9  cmp     eax, 1
0x180052ddc  setz    cl
0x180052ddf  mov     cs:dword_18029A88C, ecx
0x180052de5  mov     cs:dword_18029A888, 1
0x180052def  mov     ebx, ecx
0x180052df1  lea     rcx, [rsp+78h+CriticalSection]; lpCriticalSection
0x180052df6  call    cs:__imp_LeaveCriticalSection
0x180052dfc  lea     rcx, [rsp+78h+CriticalSection]; lpCriticalSection
0x180052e01  call    cs:__imp_DeleteCriticalSection
0x180052e07  mov     eax, ebx
0x180052e09  mov     rcx, [rsp+78h+var_18]
0x180052e0e  xor     rcx, rsp; StackCookie
0x180052e11  call    __security_check_cookie
0x180052e16  add     rsp, 70h
0x180052e1a  pop     rbx
0x180052e1b  retn
```
