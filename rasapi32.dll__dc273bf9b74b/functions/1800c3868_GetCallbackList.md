# GetCallbackList

- ea: `0x1800c3868`
- end: `0x1800c3a5c`
- name: `GetCallbackList`
- size: `500`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800c3e70`

## callees

- `0x1800087b0`
- `0x1800208ec`
- `0x1800300ec`
- `0x1800c08c8`
- `0x1800c33f4`
- `0x1800c3868`
- `0x1800c4f8c`
- `0x1800c5120`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800c3a07`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800c3a07`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c38f0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c3949`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c38f0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c3949`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c39bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c3a1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c39bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c3a1d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800c39b1`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800c39c7`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800c39d2`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800c39b1`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800c39c7`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800c39d2`

## pseudocode

```c
__int64 __fastcall GetCallbackList(HKEY hKey, HGLOBAL *a2)
{
  __int64 result; // rax
  __int64 v5; // rbx
  DWORD v6; // esi
  DWORD i; // edx
  __int64 CallbackNode; // rax
  LSTATUS v9; // eax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  int v11; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKeya; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  HGLOBAL hMem; // [rsp+58h] [rbp-A8h]
  HGLOBAL v15; // [rsp+60h] [rbp-A0h] BYREF
  HGLOBAL v16; // [rsp+68h] [rbp-98h] BYREF
  WCHAR SubKey[152]; // [rsp+70h] [rbp-90h] BYREF

  v15 = 0;
  v16 = 0;
  hMem = 0;
  v11 = 0;
  cchName = 0;
  hKeya = 0;
  phkResult = 0;
  result = DtlCreateList(hKey);
  v5 = result;
  if ( result )
  {
    if ( !RegOpenKeyExW(hKey, L"Callback", 0, 0x20019u, &hKeya) )
    {
      v6 = 0;
      for ( i = 0; ; i = v6 )
      {
        cchName = 148;
        v9 = RegEnumKeyExW(hKeya, i, SubKey, &cchName, 0, 0, 0, 0);
        if ( v9 == 259 )
          break;
        if ( !v9 && (unsigned int)DeviceAndPortFromPsz(SubKey, &v15, &v16) )
        {
          if ( !RegOpenKeyExW(hKeya, SubKey, 0, 0x20019u, &phkResult) )
          {
            GetRegDword(phkResult, L"DeviceType", &v11);
            if ( !(unsigned int)GetRegSz(phkResult, L"Number") )
            {
              CallbackNode = CreateCallbackNode((__int64)v16, (__int64)v15, (__int64)hMem, v11);
              if ( CallbackNode )
                DtlAddNodeLast(v5, CallbackNode);
              GlobalFree(hMem);
            }
            RegCloseKey(phkResult);
          }
          GlobalFree(v15);
          GlobalFree(v16);
        }
        ++v6;
      }
      RegCloseKey(hKeya);
    }
    result = DtlDestroyList(*a2);
    *a2 = (HGLOBAL)v5;
  }
  return result;
}

```

## disassembly

```asm
0x1800c3868  mov     [rsp-8+arg_10], rbx
0x1800c386d  mov     [rsp-8+arg_18], rsi
0x1800c3872  push    rbp
0x1800c3873  push    rdi
0x1800c3874  push    r14
0x1800c3876  lea     rbp, [rsp-0B0h]
0x1800c387e  sub     rsp, 1B0h
0x1800c3885  mov     rax, cs:__security_cookie
0x1800c388c  xor     rax, rsp
0x1800c388f  mov     [rbp+0C0h+var_20], rax
0x1800c3896  xor     r14d, r14d
0x1800c3899  mov     rdi, rdx
0x1800c389c  mov     [rsp+1C0h+var_160], r14
0x1800c38a1  mov     rsi, rcx
0x1800c38a4  mov     [rsp+1C0h+var_158], r14
0x1800c38a9  mov     [rsp+1C0h+hMem], r14
0x1800c38ae  mov     [rsp+1C0h+var_17C], r14d
0x1800c38b3  mov     [rsp+1C0h+cchName], r14d
0x1800c38b8  mov     [rsp+1C0h+hKey], r14
0x1800c38bd  mov     [rsp+1C0h+var_170], r14
0x1800c38c2  call    DtlCreateList
0x1800c38c7  mov     rbx, rax
0x1800c38ca  test    rax, rax
0x1800c38cd  jz      loc_1800C3A35
0x1800c38d3  lea     rax, [rsp+1C0h+hKey]
0x1800c38d8  mov     r9d, 20019h; samDesired
0x1800c38de  xor     r8d, r8d; ulOptions
0x1800c38e1  mov     [rsp+1C0h+phkResult], rax; phkResult
0x1800c38e6  lea     rdx, aCallback; "Callback"
0x1800c38ed  mov     rcx, rsi; hKey
0x1800c38f0  call    cs:__imp_RegOpenKeyExW
0x1800c38f6  test    eax, eax
0x1800c38f8  jnz     loc_1800C3A23
0x1800c38fe  mov     esi, r14d
0x1800c3901  xor     edx, edx
0x1800c3903  jmp     loc_1800C39DC
0x1800c3908  test    eax, eax
0x1800c390a  jnz     loc_1800C39D8
0x1800c3910  lea     r8, [rsp+1C0h+var_158]
0x1800c3915  lea     rdx, [rsp+1C0h+var_160]
0x1800c391a  lea     rcx, [rsp+1C0h+SubKey]
0x1800c391f  call    DeviceAndPortFromPsz
0x1800c3924  test    eax, eax
0x1800c3926  jz      loc_1800C39D8
0x1800c392c  mov     rcx, [rsp+1C0h+hKey]; hKey
0x1800c3931  lea     rax, [rsp+1C0h+var_170]
0x1800c3936  mov     r9d, 20019h; samDesired
0x1800c393c  mov     [rsp+1C0h+phkResult], rax; phkResult
0x1800c3941  xor     r8d, r8d; ulOptions
0x1800c3944  lea     rdx, [rsp+1C0h+SubKey]; lpSubKey
0x1800c3949  call    cs:__imp_RegOpenKeyExW
0x1800c394f  test    eax, eax
0x1800c3951  jnz     short loc_1800C39C2
0x1800c3953  mov     rcx, [rsp+1C0h+var_170]
0x1800c3958  lea     r8, [rsp+1C0h+var_17C]
0x1800c395d  lea     rdx, aDevicetype; "DeviceType"
0x1800c3964  call    GetRegDword
0x1800c3969  mov     rcx, [rsp+1C0h+var_170]; hKey
0x1800c396e  lea     r8, [rsp+1C0h+hMem]
0x1800c3973  lea     rdx, aNumber; "Number"
0x1800c397a  call    GetRegSz
0x1800c397f  test    eax, eax
0x1800c3981  jnz     short loc_1800C39B7
0x1800c3983  mov     r9d, [rsp+1C0h+var_17C]
0x1800c3988  mov     r8, [rsp+1C0h+hMem]
0x1800c398d  mov     rdx, [rsp+1C0h+var_160]
0x1800c3992  mov     rcx, [rsp+1C0h+var_158]
0x1800c3997  call    CreateCallbackNode
0x1800c399c  test    rax, rax
0x1800c399f  jz      short loc_1800C39AC
0x1800c39a1  mov     rdx, rax
0x1800c39a4  mov     rcx, rbx
0x1800c39a7  call    DtlAddNodeLast
0x1800c39ac  mov     rcx, [rsp+1C0h+hMem]; hMem
0x1800c39b1  call    cs:__imp_GlobalFree
0x1800c39b7  mov     rcx, [rsp+1C0h+var_170]; hKey
0x1800c39bc  call    cs:__imp_RegCloseKey
0x1800c39c2  mov     rcx, [rsp+1C0h+var_160]; hMem
0x1800c39c7  call    cs:__imp_GlobalFree
0x1800c39cd  mov     rcx, [rsp+1C0h+var_158]; hMem
0x1800c39d2  call    cs:__imp_GlobalFree
0x1800c39d8  inc     esi
0x1800c39da  mov     edx, esi; dwIndex
0x1800c39dc  mov     rcx, [rsp+1C0h+hKey]; hKey
0x1800c39e1  lea     r9, [rsp+1C0h+cchName]; lpcchName
0x1800c39e6  mov     [rsp+1C0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x1800c39eb  lea     r8, [rsp+1C0h+SubKey]; lpName
0x1800c39f0  mov     [rsp+1C0h+lpcchClass], r14; lpcchClass
0x1800c39f5  mov     [rsp+1C0h+lpClass], r14; lpClass
0x1800c39fa  mov     [rsp+1C0h+phkResult], r14; lpReserved
0x1800c39ff  mov     [rsp+1C0h+cchName], 94h
0x1800c3a07  call    cs:__imp_RegEnumKeyExW
0x1800c3a0d  cmp     eax, 103h
0x1800c3a12  jnz     loc_1800C3908
0x1800c3a18  mov     rcx, [rsp+1C0h+hKey]; hKey
0x1800c3a1d  call    cs:__imp_RegCloseKey
0x1800c3a23  mov     rcx, [rdi]; hMem
0x1800c3a26  lea     rdx, DestroyCallbackNode
0x1800c3a2d  call    DtlDestroyList
0x1800c3a32  mov     [rdi], rbx
0x1800c3a35  mov     rcx, [rbp+0C0h+var_20]
0x1800c3a3c  xor     rcx, rsp; StackCookie
0x1800c3a3f  call    __security_check_cookie
0x1800c3a44  lea     r11, [rsp+1C0h+var_10]
0x1800c3a4c  mov     rbx, [r11+30h]
0x1800c3a50  mov     rsi, [r11+38h]
0x1800c3a54  mov     rsp, r11
0x1800c3a57  pop     r14
0x1800c3a59  pop     rdi
0x1800c3a5a  pop     rbp
0x1800c3a5b  retn
```
