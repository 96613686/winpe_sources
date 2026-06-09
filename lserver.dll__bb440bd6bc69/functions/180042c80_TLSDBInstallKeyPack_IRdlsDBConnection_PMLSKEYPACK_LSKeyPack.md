# TLSDBInstallKeyPack(IRdlsDBConnection *,__PMLSKEYPACK *,__LSKeyPack *)

- ea: `0x180042c80`
- end: `0x180042eff`
- name: `?TLSDBInstallKeyPack@@YAKPEAVIRdlsDBConnection@@PEAU__PMLSKEYPACK@@PEAU__LSKeyPack@@@Z`
- size: `639`
- prototype: `unsigned int(struct IRdlsDBConnection *, struct __PMLSKEYPACK *, struct __LSKeyPack *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18004376c`
- `0x180043990`

## callees

- `0x180002d26`
- `0x180022c28`
- `0x180042b3c`
- `0x180042c80`
- `0x180043040`
- `0x1800436c8`
- `0x1800a0fb0`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180042d60`
- `msvcrt!wcscpy_s` at `0x180042d89`
- `msvcrt!wcscpy_s` at `0x180042d60`
- `msvcrt!wcscpy_s` at `0x180042d89`
- `msvcrt!time` at `0x180042e8b`
- `msvcrt!time` at `0x180042e8b`
- `ADVAPI32!RegOpenKeyExW` at `0x180042dbc`
- `ADVAPI32!RegOpenKeyExW` at `0x180042dbc`
- `ADVAPI32!RegCloseKey` at `0x180042dd1`
- `ADVAPI32!RegCloseKey` at `0x180042dd1`
- `KERNEL32!GetLastError` at `0x180042ce3`
- `KERNEL32!GetLastError` at `0x180042ce3`

## string_xrefs

- `0x180042dae`: `SYSTEM\CurrentControlSet\Services\TermService\Parameters\WhistlerCAL`

## pseudocode

```c
__int64 __fastcall TLSDBInstallKeyPack(struct IRdlsDBConnection *a1, struct __PMLSKEYPACK *a2, struct __LSKeyPack *a3)
{
  unsigned int v6; // ebx
  unsigned int v7; // esi
  __int64 v8; // rcx
  __int64 v9; // rbx
  unsigned int v10; // eax
  const unsigned __int16 *v11; // rcx
  HKEY hKey[2]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE Src[1030]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t Destination[512]; // [rsp+446h] [rbp+346h] BYREF
  wchar_t v16[257]; // [rsp+846h] [rbp+746h] BYREF
  __int16 v17; // [rsp+A48h] [rbp+948h]
  int v18; // [rsp+A54h] [rbp+954h]
  char v19; // [rsp+C68h] [rbp+B68h]
  _BYTE v20[4]; // [rsp+C6Ch] [rbp+B6Ch] BYREF
  _DWORD v21[4]; // [rsp+C70h] [rbp+B70h] BYREF

  v6 = 0;
  memcpy_0(Src, (char *)a2 + 24, 0xC38u);
  if ( !(unsigned int)FileTimeToLicenseDate((char *)a2 + 8, v20)
    || !(unsigned int)FileTimeToLicenseDate((char *)a2 + 16, v21) )
  {
    return GetLastError();
  }
  v7 = 0;
  if ( !*((_DWORD *)a2 + 788) )
  {
LABEL_13:
    v21[1] = 0;
    v19 = 1;
    if ( (unsigned int)FileTimeToLicenseDate((char *)a2 + 8, v20)
      && (unsigned int)FileTimeToLicenseDate((char *)a2 + 16, v21) )
    {
      LODWORD(hKey[0]) = 0;
      if ( !ExpireInDays(v11, (unsigned int *)hKey) )
        v21[0] = 86400 * LODWORD(hKey[0]) + time(0);
      v6 = TLSDBLicenseKeyPackSetStatus(a1, 1966080, Src);
      if ( !v6 )
        memcpy_0(a3, Src, 0xC38u);
      return v6;
    }
    return GetLastError();
  }
  while ( !v6 )
  {
    v19 = v7 != 0 ? 9 : 1;
    v8 = *((_QWORD *)a2 + 395);
    v9 = 1028LL * v7;
    v18 = *(_DWORD *)(v8 + v9);
    wcscpy_s(Destination, 0x100u, (const wchar_t *)(v9 + v8 + 4));
    wcscpy_s(v16, 0x100u, (const wchar_t *)(v9 + *((_QWORD *)a2 + 395) + 516LL));
    hKey[0] = 0;
    if ( RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SYSTEM\\CurrentControlSet\\Services\\TermService\\Parameters\\WhistlerCAL",
           0,
           0xF003Fu,
           hKey) )
    {
      if ( v16[256] == 5 && v17 == 1 )
      {
        v17 = 2;
        Destination[263] = 50;
      }
    }
    else
    {
      RegCloseKey(hKey[0]);
    }
    v10 = TLSDBLicenseKeyPackAdd((__int64)a1, (__int64)Src);
    v6 = v10;
    if ( ++v7 >= *((_DWORD *)a2 + 788) )
    {
      if ( v10 )
        return v6;
      goto LABEL_13;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180042c80  mov     [rsp-8+arg_18], rbx
0x180042c85  push    rbp
0x180042c86  push    rsi
0x180042c87  push    rdi
0x180042c88  push    r12
0x180042c8a  push    r13
0x180042c8c  push    r14
0x180042c8e  push    r15
0x180042c90  lea     rbp, [rsp-0B90h]
0x180042c98  sub     rsp, 0C90h
0x180042c9f  mov     rax, cs:__security_cookie
0x180042ca6  xor     rax, rsp
0x180042ca9  mov     [rbp+0BC0h+var_40], rax
0x180042cb0  mov     r13, r8
0x180042cb3  mov     rdi, rdx
0x180042cb6  mov     r15, rcx
0x180042cb9  add     rdx, 18h; Src
0x180042cbd  lea     rcx, [rsp+0CC0h+Src]; void *
0x180042cc2  mov     r8d, 0C38h; Size
0x180042cc8  xor     ebx, ebx
0x180042cca  call    memcpy_0
0x180042ccf  lea     rdx, [rbp+0BC0h+var_54]
0x180042cd6  lea     rcx, [rdi+8]
0x180042cda  call    FileTimeToLicenseDate
0x180042cdf  test    eax, eax
0x180042ce1  jnz     short loc_180042CF6
0x180042ce3  call    cs:__imp_GetLastError
0x180042cea  nop     dword ptr [rax+rax+00h]
0x180042cef  mov     ebx, eax
0x180042cf1  jmp     loc_180042ED2
0x180042cf6  lea     rdx, [rbp+0BC0h+var_50]
0x180042cfd  lea     rcx, [rdi+10h]
0x180042d01  call    FileTimeToLicenseDate
0x180042d06  test    eax, eax
0x180042d08  jz      short loc_180042CE3
0x180042d0a  xor     esi, esi
0x180042d0c  lea     edx, [rsi+1]
0x180042d0f  cmp     [rdi+0C50h], ebx
0x180042d15  jbe     loc_180042E39
0x180042d1b  test    ebx, ebx
0x180042d1d  jnz     loc_180042ED2
0x180042d23  mov     eax, esi
0x180042d25  neg     eax
0x180042d27  mov     eax, esi
0x180042d29  sbb     cl, cl
0x180042d2b  and     cl, 8
0x180042d2e  add     cl, dl
0x180042d30  mov     edx, 100h; SizeInWords
0x180042d35  mov     [rbp+0BC0h+var_58], cl
0x180042d3b  mov     rcx, [rdi+0C58h]
0x180042d42  imul    rbx, rax, 404h
0x180042d49  lea     r8, [rcx+4]
0x180042d4d  add     r8, rbx; Source
0x180042d50  mov     eax, [rcx+rbx]
0x180042d53  lea     rcx, [rbp+0BC0h+Destination]; Destination
0x180042d5a  mov     [rbp+0BC0h+var_26C], eax
0x180042d60  call    cs:__imp_wcscpy_s
0x180042d67  nop     dword ptr [rax+rax+00h]
0x180042d6c  mov     r8, [rdi+0C58h]
0x180042d73  lea     rcx, [rbp+0BC0h+var_47A]; Destination
0x180042d7a  add     r8, 204h
0x180042d81  mov     edx, 100h; SizeInWords
0x180042d86  add     r8, rbx; Source
0x180042d89  call    cs:__imp_wcscpy_s
0x180042d90  nop     dword ptr [rax+rax+00h]
0x180042d95  and     [rsp+0CC0h+hKey], 0
0x180042d9b  lea     rax, [rsp+0CC0h+hKey]
0x180042da0  mov     r9d, 0F003Fh; samDesired
0x180042da6  mov     [rsp+0CC0h+phkResult], rax; phkResult
0x180042dab  xor     r8d, r8d; ulOptions
0x180042dae  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\Te"...
0x180042db5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180042dbc  call    cs:__imp_RegOpenKeyExW
0x180042dc3  nop     dword ptr [rax+rax+00h]
0x180042dc8  test    eax, eax
0x180042dca  jnz     short loc_180042DDF
0x180042dcc  mov     rcx, [rsp+0CC0h+hKey]; hKey
0x180042dd1  call    cs:__imp_RegCloseKey
0x180042dd8  nop     dword ptr [rax+rax+00h]
0x180042ddd  jmp     short loc_180042E0F
0x180042ddf  cmp     [rbp+0BC0h+var_27A], 5
0x180042de7  jnz     short loc_180042E0F
0x180042de9  mov     eax, 1
0x180042dee  cmp     [rbp+0BC0h+var_278], ax
0x180042df5  jnz     short loc_180042E0F
0x180042df7  mov     eax, 2
0x180042dfc  mov     [rbp+0BC0h+var_278], ax
0x180042e03  mov     eax, 32h ; '2'
0x180042e08  mov     [rbp+0BC0h+var_66C], ax
0x180042e0f  lea     rdx, [rsp+0CC0h+Src]
0x180042e14  mov     rcx, r15
0x180042e17  call    TLSDBLicenseKeyPackAdd
0x180042e1c  mov     edx, 1
0x180042e21  mov     ebx, eax
0x180042e23  add     esi, edx
0x180042e25  cmp     esi, [rdi+0C50h]
0x180042e2b  jb      loc_180042D1B
0x180042e31  test    eax, eax
0x180042e33  jnz     loc_180042ED2
0x180042e39  and     [rbp+0BC0h+var_4C], 0
0x180042e40  lea     rcx, [rdi+8]
0x180042e44  mov     [rbp+0BC0h+var_58], dl
0x180042e4a  lea     rdx, [rbp+0BC0h+var_54]
0x180042e51  call    FileTimeToLicenseDate
0x180042e56  test    eax, eax
0x180042e58  jz      loc_180042CE3
0x180042e5e  lea     rdx, [rbp+0BC0h+var_50]
0x180042e65  lea     rcx, [rdi+10h]
0x180042e69  call    FileTimeToLicenseDate
0x180042e6e  test    eax, eax
0x180042e70  jz      loc_180042CE3
0x180042e76  and     dword ptr [rsp+0CC0h+hKey], 0
0x180042e7b  lea     rdx, [rsp+0CC0h+hKey]; unsigned int *
0x180042e80  call    ?ExpireInDays@@YAKPEBGPEAK@Z; ExpireInDays(ushort const *,ulong *)
0x180042e85  test    eax, eax
0x180042e87  jnz     short loc_180042EA7
0x180042e89  xor     ecx, ecx; Time
0x180042e8b  call    cs:__imp_time
0x180042e92  nop     dword ptr [rax+rax+00h]
0x180042e97  imul    edx, dword ptr [rsp+0CC0h+hKey], 15180h
0x180042e9f  add     eax, edx
0x180042ea1  mov     [rbp+0BC0h+var_50], eax
0x180042ea7  lea     r8, [rsp+0CC0h+Src]
0x180042eac  mov     edx, 1E0000h
0x180042eb1  mov     rcx, r15
0x180042eb4  call    TLSDBLicenseKeyPackSetStatus
0x180042eb9  mov     ebx, eax
0x180042ebb  test    eax, eax
0x180042ebd  jnz     short loc_180042ED2
0x180042ebf  mov     rcx, r13; void *
0x180042ec2  lea     rdx, [rsp+0CC0h+Src]; Src
0x180042ec7  mov     r8d, 0C38h; Size
0x180042ecd  call    memcpy_0
0x180042ed2  mov     eax, ebx
0x180042ed4  mov     rcx, [rbp+0BC0h+var_40]
0x180042edb  xor     rcx, rsp; StackCookie
0x180042ede  call    __security_check_cookie
0x180042ee3  mov     rbx, [rsp+0CC0h+arg_18]
0x180042eeb  add     rsp, 0C90h
0x180042ef2  pop     r15
0x180042ef4  pop     r14
0x180042ef6  pop     r13
0x180042ef8  pop     r12
0x180042efa  pop     rdi
0x180042efb  pop     rsi
0x180042efc  pop     rbp
0x180042efd  retn
```
