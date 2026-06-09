# GetTypeInfoFromProgID

- ea: `0x18009150c`
- end: `0x180091679`
- name: `GetTypeInfoFromProgID`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180090f38`

## callees

- `0x180055478`
- `0x1800568c8`
- `0x18009150c`
- `0x180091680`
- `0x1800966e0`
- `0x180098010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800915ff`
- `ADVAPI32!RegCloseKey` at `0x180091649`
- `ADVAPI32!RegCloseKey` at `0x180097599`
- `ADVAPI32!RegCloseKey` at `0x1800915ff`
- `ADVAPI32!RegCloseKey` at `0x180091649`
- `ADVAPI32!RegCloseKey` at `0x180097599`
- `ole32!CLSIDFromProgID` at `0x18009154d`
- `ole32!CLSIDFromProgID` at `0x18009154d`

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
0x18009150c  mov     r11, rsp
0x18009150f  mov     [r11+18h], rbx
0x180091513  push    rsi
0x180091514  push    rdi
0x180091515  push    r14
0x180091517  sub     rsp, 80h
0x18009151e  mov     rax, cs:__security_cookie
0x180091525  xor     rax, rsp
0x180091528  mov     [rsp+98h+var_28], rax
0x18009152d  mov     r14, rdx
0x180091530  mov     qword ptr [rdx], 0
0x180091537  xorps   xmm0, xmm0
0x18009153a  movups  [rsp+98h+var_38], xmm0
0x18009153f  xor     ebx, ebx
0x180091541  mov     [r11-68h], rbx
0x180091545  mov     [r11-70h], rbx
0x180091549  lea     rdx, [r11-38h]; lpclsid
0x18009154d  call    cs:__imp_CLSIDFromProgID
0x180091554  nop     dword ptr [rax+rax+00h]
0x180091559  mov     edi, eax
0x18009155b  test    eax, eax
0x18009155d  js      loc_18009162B
0x180091563  movaps  xmm0, [rsp+98h+var_38]
0x180091568  movdqa  xmmword ptr [rsp+98h+rclsid.Data1], xmm0
0x18009156e  lea     rdx, [rsp+98h+hKey]
0x180091573  lea     rcx, [rsp+98h+rclsid]; rclsid
0x180091578  call    GetKeyFromClsid
0x18009157d  mov     edi, eax
0x18009157f  test    eax, eax
0x180091581  js      loc_180091626
0x180091587  mov     [rsp+98h+var_78], 80004005h
0x18009158f  movaps  xmm0, [rsp+98h+var_38]
0x180091594  movdqa  xmmword ptr [rsp+98h+rclsid.Data1], xmm0
0x18009159a  lea     r8, [rsp+98h+var_70]
0x18009159f  lea     rdx, [rsp+98h+rclsid]
0x1800915a4  mov     rbx, [rsp+98h+hKey]
0x1800915a9  mov     rcx, rbx
0x1800915ac  call    GetTypeInfoFromTypeLibKey
0x1800915b1  mov     edi, eax
0x1800915b3  mov     [rsp+98h+var_78], eax
0x1800915b7  test    eax, eax
0x1800915b9  jns     short loc_1800915F7
0x1800915bb  mov     esi, 1
0x1800915c0  mov     [rsp+98h+var_60], esi
0x1800915c4  cmp     esi, 6
0x1800915c7  jge     short loc_1800915F7
0x1800915c9  movaps  xmm0, [rsp+98h+var_38]
0x1800915ce  movdqa  [rsp+98h+var_48], xmm0
0x1800915d4  lea     r9, [rsp+98h+var_70]
0x1800915d9  mov     r8d, esi
0x1800915dc  lea     rdx, [rsp+98h+var_48]
0x1800915e1  mov     rcx, rbx
0x1800915e4  call    GetTypeInfoFromInprocServer
0x1800915e9  mov     edi, eax
0x1800915eb  mov     [rsp+98h+var_78], eax
0x1800915ef  test    eax, eax
0x1800915f1  jns     short loc_1800915F7
0x1800915f3  inc     esi
0x1800915f5  jmp     short loc_1800915C0
0x1800915f7  test    rbx, rbx
0x1800915fa  jz      short loc_18009160D
0x1800915fc  mov     rcx, rbx; hKey
0x1800915ff  call    cs:__imp_RegCloseKey
0x180091606  nop     dword ptr [rax+rax+00h]
0x18009160b  xor     ebx, ebx
0x18009160d  test    edi, edi
0x18009160f  js      short loc_18009162B
0x180091611  mov     rax, [rsp+98h+var_70]
0x180091616  mov     [r14], rax
0x180091619  mov     [rsp+98h+var_70], 0
0x180091622  xor     edi, edi
0x180091624  jmp     short loc_18009162B
0x180091626  mov     rbx, [rsp+98h+hKey]
0x18009162b  mov     rcx, [rsp+98h+var_70]
0x180091630  test    rcx, rcx
0x180091633  jz      short loc_180091641
0x180091635  mov     rax, [rcx]
0x180091638  mov     rax, [rax+10h]
0x18009163c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091641  test    rbx, rbx
0x180091644  jz      short loc_180091655
0x180091646  mov     rcx, rbx; hKey
0x180091649  call    cs:__imp_RegCloseKey
0x180091650  nop     dword ptr [rax+rax+00h]
0x180091655  mov     eax, edi
0x180091657  mov     rcx, [rsp+98h+var_28]
0x18009165c  xor     rcx, rsp; StackCookie
0x18009165f  call    __security_check_cookie
0x180091664  mov     rbx, [rsp+98h+arg_10]
0x18009166c  add     rsp, 80h
0x180091673  pop     r14
0x180091675  pop     rdi
0x180091676  pop     rsi
0x180091677  retn
0x180097587  push    rbp
0x180097589  sub     rsp, 20h
0x18009758d  mov     rbp, rdx
0x180097590  mov     rcx, [rbp+30h]; hKey
0x180097594  test    rcx, rcx
0x180097597  jz      short loc_1800975A6
0x180097599  call    cs:__imp_RegCloseKey
0x1800975a0  nop     dword ptr [rax+rax+00h]
0x1800975a5  nop
0x1800975a6  add     rsp, 20h
0x1800975aa  pop     rbp
0x1800975ab  retn
```
