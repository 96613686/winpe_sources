# FwSecurityDescriptorDecode(ushort const *,unsigned __int64,ICF_SECURITY_DESCRIPTOR_ *)

- ea: `0x18002b7a4`
- end: `0x18002b88a`
- name: `?FwSecurityDescriptorDecode@@YAJPEBG_KPEAUICF_SECURITY_DESCRIPTOR_@@@Z`
- size: `230`
- prototype: `__int64 __fastcall(const unsigned __int16 *Src, unsigned __int64, struct ICF_SECURITY_DESCRIPTOR_ *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001262c`

## callees

- `0x180004750`
- `0x1800047e0`
- `0x180004840`
- `0x180004870`
- `0x18001e1d0`
- `0x18002b7a4`
- `0x18002f674`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b84c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b84c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002b820`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002b820`

## string_xrefs

- `0x18002b7ee`: `FwSecurityDescriptorDecode`
- `0x18002b82f`: `FwSecurityDescriptorDecode`
- `0x18002b860`: `FwSecurityDescriptorDecode`

## pseudocode

```c
__int64 __fastcall FwSecurityDescriptorDecode(
        const unsigned __int16 *Src,
        size_t a2,
        struct ICF_SECURITY_DESCRIPTOR_ *a3)
{
  size_t v3; // rbx
  WCHAR *v6; // rax
  const WCHAR *v7; // rdi
  int v8; // ebx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+20h] [rbp-28h] BYREF

  v3 = a2;
  SecurityDescriptor = 0;
  v6 = (WCHAR *)FwAlloc(2 * a2 + 2, a2);
  v7 = v6;
  if ( v6 )
  {
    memcpy_0(v6, Src, v3 * 2);
    v7[v3] = 0;
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v7, 1u, &SecurityDescriptor, 0) )
    {
      v8 = 0;
      *(_QWORD *)a3 = v7;
      *((_DWORD *)a3 + 2) = 0;
    }
    else
    {
      v8 = -2147024883;
      FwReportReturnError("FwSecurityDescriptorDecode", 2147942413LL);
    }
  }
  else
  {
    v8 = FwReportErrorAsWinError("FwSecurityDescriptorDecode", "FwAlloc", 8);
  }
  LocalFree(SecurityDescriptor);
  if ( v8 < 0 )
  {
    FwFree(v7);
    return (unsigned int)FwReportReturnError("FwSecurityDescriptorDecode", (unsigned int)v8);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002b7a4  mov     [rsp+arg_18], rbx
0x18002b7a9  push    rbp
0x18002b7aa  push    rsi
0x18002b7ab  push    rdi
0x18002b7ac  sub     rsp, 30h
0x18002b7b0  mov     rax, cs:__security_cookie
0x18002b7b7  xor     rax, rsp
0x18002b7ba  mov     [rsp+48h+var_20], rax
0x18002b7bf  lea     rbx, [rdx+rdx]
0x18002b7c3  mov     [rsp+48h+SecurityDescriptor], 0
0x18002b7cc  mov     rbp, rcx
0x18002b7cf  mov     rsi, r8
0x18002b7d2  lea     rcx, [rbx+2]
0x18002b7d6  call    FwAlloc
0x18002b7db  mov     rdi, rax
0x18002b7de  test    rax, rax
0x18002b7e1  jnz     short loc_18002B7FE
0x18002b7e3  lea     r8d, [rax+8]
0x18002b7e7  lea     rdx, aFwalloc_0; "FwAlloc"
0x18002b7ee  lea     rcx, aFwsecuritydesc; "FwSecurityDescriptorDecode"
0x18002b7f5  call    FwReportErrorAsWinError
0x18002b7fa  mov     ebx, eax
0x18002b7fc  jmp     short loc_18002B847
0x18002b7fe  mov     r8, rbx; Size
0x18002b801  mov     rdx, rbp; Src
0x18002b804  mov     rcx, rdi; void *
0x18002b807  call    memcpy_0
0x18002b80c  xor     eax, eax
0x18002b80e  lea     r8, [rsp+48h+SecurityDescriptor]; SecurityDescriptor
0x18002b813  xor     r9d, r9d; SecurityDescriptorSize
0x18002b816  mov     [rbx+rdi], ax
0x18002b81a  mov     rcx, rdi; StringSecurityDescriptor
0x18002b81d  lea     edx, [rax+1]; StringSDRevision
0x18002b820  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002b826  test    eax, eax
0x18002b828  jnz     short loc_18002B83F
0x18002b82a  mov     ebx, 8007000Dh
0x18002b82f  lea     rcx, aFwsecuritydesc; "FwSecurityDescriptorDecode"
0x18002b836  mov     edx, ebx
0x18002b838  call    FwReportReturnError
0x18002b83d  jmp     short loc_18002B847
0x18002b83f  xor     ebx, ebx
0x18002b841  mov     [rsi], rdi
0x18002b844  mov     [rsi+8], ebx
0x18002b847  mov     rcx, [rsp+48h+SecurityDescriptor]; hMem
0x18002b84c  call    cs:__imp_LocalFree
0x18002b852  test    ebx, ebx
0x18002b854  jns     short loc_18002B86E
0x18002b856  mov     rcx, rdi
0x18002b859  call    FwFree
0x18002b85e  mov     edx, ebx
0x18002b860  lea     rcx, aFwsecuritydesc; "FwSecurityDescriptorDecode"
0x18002b867  call    FwReportReturnError
0x18002b86c  mov     ebx, eax
0x18002b86e  mov     eax, ebx
0x18002b870  mov     rcx, [rsp+48h+var_20]
0x18002b875  xor     rcx, rsp; StackCookie
0x18002b878  call    __security_check_cookie
0x18002b87d  mov     rbx, [rsp+48h+arg_18]
0x18002b882  add     rsp, 30h
0x18002b886  pop     rdi
0x18002b887  pop     rsi
0x18002b888  pop     rbp
0x18002b889  retn
```
