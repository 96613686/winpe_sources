# GetTypeInfoFromProgID

- ea: `0x18008f30c`
- end: `0x18008f466`
- name: `GetTypeInfoFromProgID`
- size: `346`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008ed4c`

## callees

- `0x180054638`
- `0x180055a30`
- `0x18008f30c`
- `0x18008f46c`
- `0x1800942d0`
- `0x180096010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18008f3f9`
- `ADVAPI32!RegCloseKey` at `0x18008f43d`
- `ADVAPI32!RegCloseKey` at `0x180095163`
- `ADVAPI32!RegCloseKey` at `0x18008f3f9`
- `ADVAPI32!RegCloseKey` at `0x18008f43d`
- `ADVAPI32!RegCloseKey` at `0x180095163`
- `ole32!CLSIDFromProgID` at `0x18008f34d`
- `ole32!CLSIDFromProgID` at `0x18008f34d`

## pseudocode

```c
__int64 __fastcall GetTypeInfoFromProgID(const OLECHAR *a1, _QWORD *a2)
{
  HKEY v3; // rbx
  int KeyFromClsid; // edi
  int i; // esi
  __int64 v7; // [rsp+28h] [rbp-70h] BYREF
  HKEY hKey; // [rsp+30h] [rbp-68h] BYREF
  int v9; // [rsp+38h] [rbp-60h]
  IID rclsid; // [rsp+40h] [rbp-58h] BYREF
  CLSID v11; // [rsp+50h] [rbp-48h] BYREF
  CLSID v12; // [rsp+60h] [rbp-38h] BYREF

  *a2 = 0;
  v12 = 0;
  v3 = 0;
  hKey = 0;
  v7 = 0;
  KeyFromClsid = CLSIDFromProgID(a1, &v12);
  if ( KeyFromClsid >= 0 )
  {
    rclsid = v12;
    KeyFromClsid = GetKeyFromClsid(&rclsid, &hKey);
    if ( KeyFromClsid < 0 )
    {
      v3 = hKey;
    }
    else
    {
      rclsid = v12;
      v3 = hKey;
      KeyFromClsid = GetTypeInfoFromTypeLibKey(hKey, &rclsid, &v7);
      if ( KeyFromClsid < 0 )
      {
        for ( i = 1; ; ++i )
        {
          v9 = i;
          if ( i >= 6 )
            break;
          v11 = v12;
          KeyFromClsid = GetTypeInfoFromInprocServer(v3, (__int64)&v11, i, &v7);
          if ( KeyFromClsid >= 0 )
            break;
        }
      }
      if ( v3 )
      {
        RegCloseKey(v3);
        v3 = 0;
      }
      if ( KeyFromClsid >= 0 )
      {
        *a2 = v7;
        v7 = 0;
        KeyFromClsid = 0;
      }
    }
  }
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  if ( v3 )
    RegCloseKey(v3);
  return (unsigned int)KeyFromClsid;
}

```

## disassembly

```asm
0x18008f30c  mov     r11, rsp
0x18008f30f  mov     [r11+18h], rbx
0x18008f313  push    rsi
0x18008f314  push    rdi
0x18008f315  push    r14
0x18008f317  sub     rsp, 80h
0x18008f31e  mov     rax, cs:__security_cookie
0x18008f325  xor     rax, rsp
0x18008f328  mov     [rsp+98h+var_28], rax
0x18008f32d  mov     r14, rdx
0x18008f330  mov     qword ptr [rdx], 0
0x18008f337  xorps   xmm0, xmm0
0x18008f33a  movups  [rsp+98h+var_38], xmm0
0x18008f33f  xor     ebx, ebx
0x18008f341  mov     [r11-68h], rbx
0x18008f345  mov     [r11-70h], rbx
0x18008f349  lea     rdx, [r11-38h]; lpclsid
0x18008f34d  call    cs:__imp_CLSIDFromProgID
0x18008f353  mov     edi, eax
0x18008f355  test    eax, eax
0x18008f357  js      loc_18008F41F
0x18008f35d  movaps  xmm0, [rsp+98h+var_38]
0x18008f362  movdqa  xmmword ptr [rsp+98h+rclsid.Data1], xmm0
0x18008f368  lea     rdx, [rsp+98h+hKey]
0x18008f36d  lea     rcx, [rsp+98h+rclsid]; rclsid
0x18008f372  call    GetKeyFromClsid
0x18008f377  mov     edi, eax
0x18008f379  test    eax, eax
0x18008f37b  js      loc_18008F41A
0x18008f381  mov     [rsp+98h+var_78], 80004005h
0x18008f389  movaps  xmm0, [rsp+98h+var_38]
0x18008f38e  movdqa  xmmword ptr [rsp+98h+rclsid.Data1], xmm0
0x18008f394  lea     r8, [rsp+98h+var_70]
0x18008f399  lea     rdx, [rsp+98h+rclsid]
0x18008f39e  mov     rbx, [rsp+98h+hKey]
0x18008f3a3  mov     rcx, rbx
0x18008f3a6  call    GetTypeInfoFromTypeLibKey
0x18008f3ab  mov     edi, eax
0x18008f3ad  mov     [rsp+98h+var_78], eax
0x18008f3b1  test    eax, eax
0x18008f3b3  jns     short loc_18008F3F1
0x18008f3b5  mov     esi, 1
0x18008f3ba  mov     [rsp+98h+var_60], esi
0x18008f3be  cmp     esi, 6
0x18008f3c1  jge     short loc_18008F3F1
0x18008f3c3  movaps  xmm0, [rsp+98h+var_38]
0x18008f3c8  movdqa  [rsp+98h+var_48], xmm0
0x18008f3ce  lea     r9, [rsp+98h+var_70]
0x18008f3d3  mov     r8d, esi
0x18008f3d6  lea     rdx, [rsp+98h+var_48]
0x18008f3db  mov     rcx, rbx
0x18008f3de  call    GetTypeInfoFromInprocServer
0x18008f3e3  mov     edi, eax
0x18008f3e5  mov     [rsp+98h+var_78], eax
0x18008f3e9  test    eax, eax
0x18008f3eb  jns     short loc_18008F3F1
0x18008f3ed  inc     esi
0x18008f3ef  jmp     short loc_18008F3BA
0x18008f3f1  test    rbx, rbx
0x18008f3f4  jz      short loc_18008F401
0x18008f3f6  mov     rcx, rbx; hKey
0x18008f3f9  call    cs:__imp_RegCloseKey
0x18008f3ff  xor     ebx, ebx
0x18008f401  test    edi, edi
0x18008f403  js      short loc_18008F41F
0x18008f405  mov     rax, [rsp+98h+var_70]
0x18008f40a  mov     [r14], rax
0x18008f40d  mov     [rsp+98h+var_70], 0
0x18008f416  xor     edi, edi
0x18008f418  jmp     short loc_18008F41F
0x18008f41a  mov     rbx, [rsp+98h+hKey]
0x18008f41f  mov     rcx, [rsp+98h+var_70]
0x18008f424  test    rcx, rcx
0x18008f427  jz      short loc_18008F435
0x18008f429  mov     rax, [rcx]
0x18008f42c  mov     rax, [rax+10h]
0x18008f430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f435  test    rbx, rbx
0x18008f438  jz      short loc_18008F443
0x18008f43a  mov     rcx, rbx; hKey
0x18008f43d  call    cs:__imp_RegCloseKey
0x18008f443  mov     eax, edi
0x18008f445  mov     rcx, [rsp+98h+var_28]
0x18008f44a  xor     rcx, rsp; StackCookie
0x18008f44d  call    __security_check_cookie
0x18008f452  mov     rbx, [rsp+98h+arg_10]
0x18008f45a  add     rsp, 80h
0x18008f461  pop     r14
0x18008f463  pop     rdi
0x18008f464  pop     rsi
0x18008f465  retn
0x180095151  push    rbp
0x180095153  sub     rsp, 20h
0x180095157  mov     rbp, rdx
0x18009515a  mov     rcx, [rbp+30h]; hKey
0x18009515e  test    rcx, rcx
0x180095161  jz      short loc_18009516A
0x180095163  call    cs:__imp_RegCloseKey
0x180095169  nop
0x18009516a  add     rsp, 20h
0x18009516e  pop     rbp
0x18009516f  retn
```
