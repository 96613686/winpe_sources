# FwRegOpenKey

- ea: `0x180001720`
- end: `0x18000180e`
- name: `FwRegOpenKey`
- size: `238`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpSubKey@<rdx>, REGSAM samDesired@<r8d>, __int64)`
- caller_count: `8`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180001270`
- `0x180001400`
- `0x1800014d0`
- `0x180001b80`
- `0x180002160`
- `0x180002610`
- `0x180002910`
- `0x180029d10`

## callees

- `0x180001720`
- `0x180004750`
- `0x1800047e0`
- `0x1800130bc`
- `0x18001e1d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000178a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000178a`

## string_xrefs

- `0x1800017e7`: `RegOpenKeyExW`
- `0x1800017ee`: `FwRegOpenKey`
- `0x180001800`: `FwRegOpenKey`

## pseudocode

```c
__int64 __fastcall FwRegOpenKey(HKEY hKey, LPCWSTR lpSubKey, REGSAM samDesired, HKEY *a4, int *a5)
{
  unsigned int v9; // eax
  int v10; // ecx
  __int64 result; // rax
  HKEY phkResult; // [rsp+30h] [rbp-48h] BYREF

  phkResult = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_ca8ecc87028c3f8cbe9deeea65f7fdbd_Traceguids, lpSubKey);
  *a4 = 0;
  v9 = RegOpenKeyExW(hKey, lpSubKey, 0, samDesired, &phkResult);
  if ( v9 == 2 )
  {
    v10 = 0;
LABEL_6:
    result = 0;
    *a5 = v10;
    return result;
  }
  if ( !v9 )
  {
    v10 = 1;
    *a4 = phkResult;
    goto LABEL_6;
  }
  result = FwReportErrorAsWinError("FwRegOpenKey", "RegOpenKeyExW", v9);
  if ( (int)result < 0 )
    return FwReportReturnError("FwRegOpenKey", (unsigned int)result);
  return result;
}

```

## disassembly

```asm
0x180001720  push    rbx
0x180001722  push    rbp
0x180001723  push    rsi
0x180001724  push    rdi
0x180001725  push    r14
0x180001727  push    r15
0x180001729  sub     rsp, 48h
0x18000172d  mov     rax, cs:__security_cookie
0x180001734  xor     rax, rsp
0x180001737  mov     [rsp+78h+var_40], rax
0x18000173c  mov     rbx, [rsp+78h+arg_20]
0x180001744  xor     r15d, r15d
0x180001747  mov     [rsp+78h+var_48], r15
0x18000174c  mov     rdi, r9
0x18000174f  mov     r14d, r8d
0x180001752  mov     rsi, rdx
0x180001755  mov     rbp, rcx
0x180001758  mov     rcx, cs:WPP_GLOBAL_Control
0x18000175f  lea     rax, WPP_GLOBAL_Control
0x180001766  cmp     rcx, rax
0x180001769  jz      short loc_180001771
0x18000176b  test    byte ptr [rcx+1Ch], 8
0x18000176f  jnz     short loc_1800017CA
0x180001771  lea     rax, [rsp+78h+var_48]
0x180001776  mov     [rdi], r15
0x180001779  mov     r9d, r14d; samDesired
0x18000177c  mov     [rsp+78h+phkResult], rax; phkResult
0x180001781  xor     r8d, r8d; ulOptions
0x180001784  mov     rdx, rsi; lpSubKey
0x180001787  mov     rcx, rbp; hKey
0x18000178a  call    cs:__imp_RegOpenKeyExW
0x180001790  cmp     eax, 2
0x180001793  jnz     short loc_1800017B7
0x180001795  mov     ecx, r15d
0x180001798  mov     eax, r15d
0x18000179b  mov     [rbx], ecx
0x18000179d  mov     rcx, [rsp+78h+var_40]
0x1800017a2  xor     rcx, rsp; StackCookie
0x1800017a5  call    __security_check_cookie
0x1800017aa  add     rsp, 48h
0x1800017ae  pop     r15
0x1800017b0  pop     r14
0x1800017b2  pop     rdi
0x1800017b3  pop     rsi
0x1800017b4  pop     rbp
0x1800017b5  pop     rbx
0x1800017b6  retn
0x1800017b7  test    eax, eax
0x1800017b9  jnz     short loc_1800017E4
0x1800017bb  mov     rax, [rsp+78h+var_48]
0x1800017c0  mov     ecx, 1
0x1800017c5  mov     [rdi], rax
0x1800017c8  jmp     short loc_180001798
0x1800017ca  mov     rcx, [rcx+10h]
0x1800017ce  lea     r8, WPP_ca8ecc87028c3f8cbe9deeea65f7fdbd_Traceguids
0x1800017d5  mov     edx, 0Bh
0x1800017da  mov     r9, rsi
0x1800017dd  call    WPP_SF_S
0x1800017e2  jmp     short loc_180001771
0x1800017e4  mov     r8d, eax
0x1800017e7  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x1800017ee  lea     rcx, aFwregopenkey_0; "FwRegOpenKey"
0x1800017f5  call    FwReportErrorAsWinError
0x1800017fa  test    eax, eax
0x1800017fc  jns     short loc_18000179D
0x1800017fe  mov     edx, eax
0x180001800  lea     rcx, aFwregopenkey_0; "FwRegOpenKey"
0x180001807  call    FwReportReturnError
0x18000180c  jmp     short loc_18000179D
```
