# EEDBManager::CreateEnrollmentCommon(_GUID,EnrollmentStateTag,EnrollmentEnrollType,HKEY__ * *)

- ea: `0x18003e570`
- end: `0x18003e77e`
- name: `?CreateEnrollmentCommon@EEDBManager@@AEAAJU_GUID@@W4EnrollmentStateTag@@W4EnrollmentEnrollType@@PEAPEAUHKEY__@@@Z`
- size: `526`
- prototype: `__int64 __fastcall(__int64, const GUID *, int, int, HKEY *phkResult)`
- caller_count: `6`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003dd1c`
- `0x18003df5c`
- `0x18003e03c`
- `0x18003e1d0`
- `0x18003e40c`
- `0x18003e4cc`

## callees

- `0x1800067a0`
- `0x180007040`
- `0x180007120`
- `0x18000d560`
- `0x18002e1a0`
- `0x18003e570`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003e6d8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003e6d8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003e71f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003e748`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003e71f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003e748`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003e5c7`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003e5c7`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
__int64 __fastcall EEDBManager::CreateEnrollmentCommon(__int64 a1, const GUID *a2, int a3, int a4, HKEY *phkResult)
{
  int v5; // ebx
  const unsigned __int16 *EnrollmentsRootKey; // rax
  LSTATUS Key; // eax
  bool v8; // cc
  BYTE Data[8]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v11; // [rsp+58h] [rbp-A8h] BYREF
  BYTE v12[14]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v14[40]; // [rsp+70h] [rbp-90h] BYREF
  OLECHAR sz; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v16[39]; // [rsp+C2h] [rbp-3Eh] BYREF
  WCHAR SubKey[264]; // [rsp+110h] [rbp+10h] BYREF

  *(_DWORD *)Data = a3;
  *(_DWORD *)v12 = a4;
  SubKey[0] = 0;
  v14[0] = 0;
  sz = 0;
  if ( StringFromGUID2(a2, &sz, 39) != 39 )
    return (unsigned int)-2147418113;
  v11 = 0;
  v5 = StringCchLengthW(&sz, 0x27u, &v11);
  if ( v5 < 0 )
    return (unsigned int)v5;
  if ( v11 - 2 > 0x24 )
    return (unsigned int)-2147418113;
  v5 = StringCchCopyW(v14, 0x27u, v16);
  if ( v5 < 0 )
    return (unsigned int)v5;
  v5 = StringCchLengthW(v14, 0x27u, &v11);
  if ( v5 < 0 )
    return (unsigned int)v5;
  if ( v11 - 2 > 0x24 )
    return (unsigned int)-2147418113;
  v14[v11 - 1] = 0;
  EnrollmentsRootKey = EEDBManager::GetEnrollmentsRootKey();
  v5 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", EnrollmentsRootKey, v14);
  if ( v5 >= 0 )
  {
    if ( (Key = RegCreateKeyExW(
                  (HKEY)((word_1800AFC84 != 0x2000) - 0x7FFFFFFFLL),
                  SubKey,
                  0,
                  0,
                  0,
                  0x2011Fu,
                  0,
                  phkResult,
                  0),
          v8 = Key <= 0,
          Key)
      || *(_DWORD *)Data != 63
      && (Key = RegSetValueExW(*phkResult, L"EnrollmentState", 0, 4u, Data, 4u), v8 = Key <= 0, Key)
      || (Key = RegSetValueExW(*phkResult, L"EnrollmentType", 0, 4u, v12, 4u), v8 = Key <= 0, Key) )
    {
      if ( v8 )
        return (unsigned int)Key;
      else
        return (unsigned __int16)Key | 0x80070000;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003e570  mov     [rsp-8+arg_0], rbx
0x18003e575  push    rbp
0x18003e576  push    rdi
0x18003e577  push    r14
0x18003e579  lea     rbp, [rsp-230h]
0x18003e581  sub     rsp, 330h
0x18003e588  mov     rax, cs:__security_cookie
0x18003e58f  xor     rax, rsp
0x18003e592  mov     [rbp+240h+var_20], rax
0x18003e599  mov     rdi, [rbp+240h+arg_20]
0x18003e5a0  xor     eax, eax
0x18003e5a2  mov     rcx, rdx; rguid
0x18003e5a5  mov     dword ptr [rsp+340h+Data], r8d
0x18003e5aa  lea     rdx, [rbp+240h+sz]; lpsz
0x18003e5ae  mov     dword ptr [rsp+340h+var_2E0], r9d
0x18003e5b3  mov     [rbp+240h+SubKey], ax
0x18003e5b7  lea     r14d, [rax+27h]
0x18003e5bb  mov     [rsp+340h+var_2D0], ax
0x18003e5c0  mov     r8d, r14d; cchMax
0x18003e5c3  mov     [rbp+240h+sz], ax
0x18003e5c7  call    cs:__imp_StringFromGUID2
0x18003e5cd  cmp     eax, r14d
0x18003e5d0  jnz     loc_18003E754
0x18003e5d6  lea     r8, [rsp+340h+var_2E8]; unsigned __int64 *
0x18003e5db  mov     [rsp+340h+var_2E8], 0
0x18003e5e4  mov     edx, r14d; unsigned __int64
0x18003e5e7  lea     rcx, [rbp+240h+sz]; unsigned __int16 *
0x18003e5eb  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18003e5f0  mov     ebx, eax
0x18003e5f2  test    eax, eax
0x18003e5f4  js      loc_18003E759
0x18003e5fa  mov     rax, [rsp+340h+var_2E8]
0x18003e5ff  add     rax, 0FFFFFFFFFFFFFFFEh
0x18003e603  cmp     rax, 24h ; '$'
0x18003e607  ja      loc_18003E754
0x18003e60d  lea     r8, [rbp+240h+var_27E]; unsigned __int16 *
0x18003e611  mov     edx, r14d; unsigned __int64
0x18003e614  lea     rcx, [rsp+340h+var_2D0]; unsigned __int16 *
0x18003e619  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003e61e  mov     ebx, eax
0x18003e620  test    eax, eax
0x18003e622  js      loc_18003E759
0x18003e628  lea     r8, [rsp+340h+var_2E8]; unsigned __int64 *
0x18003e62d  mov     edx, r14d; unsigned __int64
0x18003e630  lea     rcx, [rsp+340h+var_2D0]; unsigned __int16 *
0x18003e635  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18003e63a  mov     ebx, eax
0x18003e63c  test    eax, eax
0x18003e63e  js      loc_18003E759
0x18003e644  mov     rcx, [rsp+340h+var_2E8]
0x18003e649  lea     rax, [rcx-2]
0x18003e64d  cmp     rax, 24h ; '$'
0x18003e651  ja      loc_18003E754
0x18003e657  xor     eax, eax
0x18003e659  mov     [rsp+rcx*2+340h+var_2D2], ax
0x18003e65e  call    ?GetEnrollmentsRootKey@EEDBManager@@SAPEBGXZ; EEDBManager::GetEnrollmentsRootKey(void)
0x18003e663  mov     r9, rax
0x18003e666  lea     r8, aSS_0; "%s\\%s"
0x18003e66d  lea     rax, [rsp+340h+var_2D0]
0x18003e672  mov     edx, 104h; unsigned __int64
0x18003e677  lea     rcx, [rbp+240h+SubKey]; unsigned __int16 *
0x18003e67b  mov     qword ptr [rsp+340h+dwOptions], rax
0x18003e680  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003e685  mov     ebx, eax
0x18003e687  test    eax, eax
0x18003e689  js      loc_18003E759
0x18003e68f  xor     ecx, ecx
0x18003e691  mov     [rsp+340h+lpdwDisposition], 0; lpdwDisposition
0x18003e69a  mov     [rsp+340h+phkResult], rdi; phkResult
0x18003e69f  lea     rdx, [rbp+240h+SubKey]; lpSubKey
0x18003e6a3  mov     eax, 2000h
0x18003e6a8  mov     [rsp+340h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18003e6b1  cmp     cs:word_1800AFC84, ax
0x18003e6b8  mov     [rsp+340h+samDesired], 2011Fh; samDesired
0x18003e6c0  setnz   cl
0x18003e6c3  mov     [rsp+340h+dwOptions], 0; dwOptions
0x18003e6cb  add     rcx, 0FFFFFFFF80000001h; hKey
0x18003e6d2  xor     r9d, r9d; lpClass
0x18003e6d5  xor     r8d, r8d; Reserved
0x18003e6d8  call    cs:__imp_RegCreateKeyExW
0x18003e6de  test    eax, eax
0x18003e6e0  jz      short loc_18003E6F3
0x18003e6e2  jg      short loc_18003E6E8
0x18003e6e4  mov     ebx, eax
0x18003e6e6  jmp     short loc_18003E759
0x18003e6e8  movzx   ebx, ax
0x18003e6eb  or      ebx, 80070000h
0x18003e6f1  jmp     short loc_18003E759
0x18003e6f3  cmp     dword ptr [rsp+340h+Data], 3Fh ; '?'
0x18003e6f8  mov     r14d, 4
0x18003e6fe  jz      short loc_18003E729
0x18003e700  mov     rcx, [rdi]; hKey
0x18003e703  lea     rax, [rsp+340h+Data]
0x18003e708  mov     [rsp+340h+samDesired], r14d; cbData
0x18003e70d  lea     rdx, Value; "EnrollmentState"
0x18003e714  mov     r9d, r14d; dwType
0x18003e717  mov     qword ptr [rsp+340h+dwOptions], rax; lpData
0x18003e71c  xor     r8d, r8d; Reserved
0x18003e71f  call    cs:__imp_RegSetValueExW
0x18003e725  test    eax, eax
0x18003e727  jnz     short loc_18003E6E2
0x18003e729  mov     rcx, [rdi]; hKey
0x18003e72c  lea     rax, [rsp+340h+var_2E0]
0x18003e731  mov     [rsp+340h+samDesired], r14d; cbData
0x18003e736  lea     rdx, aEnrollmenttype; "EnrollmentType"
0x18003e73d  mov     r9d, r14d; dwType
0x18003e740  mov     qword ptr [rsp+340h+dwOptions], rax; lpData
0x18003e745  xor     r8d, r8d; Reserved
0x18003e748  call    cs:__imp_RegSetValueExW
0x18003e74e  test    eax, eax
0x18003e750  jz      short loc_18003E759
0x18003e752  jmp     short loc_18003E6E2
0x18003e754  mov     ebx, 8000FFFFh
0x18003e759  mov     eax, ebx
0x18003e75b  mov     rcx, [rbp+240h+var_20]
0x18003e762  xor     rcx, rsp; StackCookie
0x18003e765  call    __security_check_cookie
0x18003e76a  mov     rbx, [rsp+340h+arg_0]
0x18003e772  add     rsp, 330h
0x18003e779  pop     r14
0x18003e77b  pop     rdi
0x18003e77c  pop     rbp
0x18003e77d  retn
```
