# RegOpenOtherKeyExW(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *,ushort *)

- ea: `0x18002f8dc`
- end: `0x18002fa70`
- name: `?RegOpenOtherKeyExW@@YAJPEAUHKEY__@@PEBGKKPEAPEAU1@PEAG@Z`
- size: `404`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpSubKey@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, HKEY *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180012750`

## callees

- `0x18002f8dc`
- `0x18004d900`
- `0x18009a5a0`

## import_xrefs

- `ntdll!NtQuerySystemInformationEx` at `0x18002f995`
- `ntdll!NtQuerySystemInformationEx` at `0x18002f9ee`
- `ntdll!NtQuerySystemInformationEx` at `0x18002f995`
- `ntdll!NtQuerySystemInformationEx` at `0x18002f9ee`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x18002fa20`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x18002fa4c`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x18002fa20`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x18002fa4c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f939`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fa41`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f939`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fa41`

## pseudocode

```c
__int64 __fastcall RegOpenOtherKeyExW(HKEY hKey, LPCWSTR lpSubKey, __int64 a3, REGSAM a4, HKEY *phkResult)
{
  int v5; // esi
  unsigned int v9; // edi
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rcx
  void *v13; // rsp
  void *v14; // rsp
  unsigned int *v15; // rbx
  char v16; // r15
  unsigned int v17; // ecx
  unsigned __int16 v18; // bx
  unsigned int v19; // [rsp+30h] [rbp+0h] BYREF
  __int64 v20; // [rsp+38h] [rbp+8h] BYREF
  unsigned int *v21; // [rsp+40h] [rbp+10h]

  v5 = 0;
  v19 = 0;
  v20 = 0;
  if ( (a4 & 0x300) != 0x200
    || (NtCurrentTeb()->SpareUlong0 & 0x80000000) != 0
    || (unsigned int)NtQuerySystemInformationEx(230, &v20, 8) != -1073741789 )
  {
    return (unsigned int)RegOpenKeyExW(hKey, lpSubKey, 0, a4, phkResult);
  }
  v11 = v19 + 15LL;
  if ( v11 <= v19 )
    v11 = 0xFFFFFFFFFFFFFF0LL;
  v12 = v11 & 0xFFFFFFFFFFFFFFF0uLL;
  v13 = alloca(v12);
  v14 = alloca(v12);
  v15 = &v19;
  v21 = &v19;
  if ( (int)NtQuerySystemInformationEx(230, &v20, 8) < 0 )
    return (unsigned int)RegOpenKeyExW(hKey, lpSubKey, 0, a4, phkResult);
  v16 = 0;
  v9 = 0;
  while ( 1 )
  {
    v17 = v15[v5];
    if ( !(_WORD)v17 )
      break;
    if ( (v17 & 0x160000) == 0x120000 )
    {
      v16 = 1;
      v18 = Wow64SetThreadDefaultGuestMachine(LOWORD(v15[v5]));
      v9 = RegOpenKeyExW(hKey, lpSubKey, 0, a4, phkResult);
      Wow64SetThreadDefaultGuestMachine(v18);
      if ( !v9 )
        return v9;
      v15 = v21;
    }
    ++v5;
  }
  if ( !v16 )
    return (unsigned int)RegOpenKeyExW(hKey, lpSubKey, 0, a4, phkResult);
  return v9;
}

```

## disassembly

```asm
0x18002f8dc  push    rbp
0x18002f8de  push    rbx
0x18002f8df  push    rsi
0x18002f8e0  push    rdi
0x18002f8e1  push    r12
0x18002f8e3  push    r13
0x18002f8e5  push    r14
0x18002f8e7  push    r15
0x18002f8e9  sub     rsp, 58h
0x18002f8ed  lea     rbp, [rsp+30h]
0x18002f8f2  mov     rax, cs:__security_cookie
0x18002f8f9  xor     rax, rbp
0x18002f8fc  mov     [rbp+60h+var_48], rax
0x18002f900  xor     esi, esi
0x18002f902  mov     eax, r9d
0x18002f905  and     eax, 300h
0x18002f90a  mov     [rbp+60h+var_60], esi
0x18002f90d  mov     [rbp+60h+var_58], rsi
0x18002f911  mov     r14d, r9d
0x18002f914  mov     r12, rdx
0x18002f917  mov     r13, rcx
0x18002f91a  cmp     eax, 200h
0x18002f91f  jz      short loc_18002F960
0x18002f921  mov     rax, [rbp+60h+arg_20]
0x18002f928  mov     r9d, r14d; samDesired
0x18002f92b  xor     r8d, r8d; ulOptions
0x18002f92e  mov     [rsp+90h+phkResult], rax; phkResult
0x18002f933  mov     rdx, r12; lpSubKey
0x18002f936  mov     rcx, r13; hKey
0x18002f939  call    cs:__imp_RegOpenKeyExW
0x18002f93f  mov     edi, eax
0x18002f941  mov     eax, edi
0x18002f943  mov     rcx, [rbp+60h+var_48]
0x18002f947  xor     rcx, rbp; StackCookie
0x18002f94a  call    __security_check_cookie
0x18002f94f  lea     rsp, [rbp+28h]
0x18002f953  pop     r15
0x18002f955  pop     r14
0x18002f957  pop     r13
0x18002f959  pop     r12
0x18002f95b  pop     rdi
0x18002f95c  pop     rsi
0x18002f95d  pop     rbx
0x18002f95e  pop     rbp
0x18002f95f  retn
0x18002f960  mov     rax, gs:30h
0x18002f969  cmp     [rax+180Ch], esi
0x18002f96f  jl      short loc_18002F921
0x18002f971  xor     r9d, r9d
0x18002f974  lea     rax, [rbp+60h+var_60]
0x18002f978  mov     [rsp+90h+var_68], rax
0x18002f97d  lea     rdx, [rbp+60h+var_58]
0x18002f981  mov     r15d, 0E6h
0x18002f987  mov     dword ptr [rsp+90h+phkResult], esi
0x18002f98b  mov     ecx, r15d
0x18002f98e  lea     edi, [r9+8]
0x18002f992  mov     r8d, edi
0x18002f995  call    cs:__imp_NtQuerySystemInformationEx
0x18002f99b  cmp     eax, 0C0000023h
0x18002f9a0  jnz     loc_18002F921
0x18002f9a6  mov     edx, [rbp+60h+var_60]
0x18002f9a9  lea     rcx, [rdx+0Fh]
0x18002f9ad  cmp     rcx, rdx
0x18002f9b0  ja      short loc_18002F9BC
0x18002f9b2  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18002f9bc  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18002f9c0  mov     rax, rcx
0x18002f9c3  call    _alloca_probe
0x18002f9c8  sub     rsp, rcx
0x18002f9cb  lea     rax, [rbp+60h+var_60]
0x18002f9cf  mov     r8d, edi
0x18002f9d2  mov     ecx, r15d
0x18002f9d5  lea     rbx, [rsp+90h+var_60]
0x18002f9da  mov     [rsp+90h+var_68], rax
0x18002f9df  mov     dword ptr [rsp+90h+phkResult], edx
0x18002f9e3  mov     r9, rbx
0x18002f9e6  lea     rdx, [rbp+60h+var_58]
0x18002f9ea  mov     [rbp+60h+var_50], rbx
0x18002f9ee  call    cs:__imp_NtQuerySystemInformationEx
0x18002f9f4  test    eax, eax
0x18002f9f6  js      loc_18002F921
0x18002f9fc  mov     r15b, sil
0x18002f9ff  mov     edi, esi
0x18002fa01  mov     edx, esi
0x18002fa03  mov     ecx, [rbx+rdx*4]
0x18002fa06  test    cx, cx
0x18002fa09  jz      short loc_18002FA62
0x18002fa0b  and     ecx, 160000h
0x18002fa11  cmp     ecx, 120000h
0x18002fa17  jnz     short loc_18002FA5E
0x18002fa19  movzx   ecx, word ptr [rbx+rdx*4]
0x18002fa1d  mov     r15b, 1
0x18002fa20  call    cs:__imp_Wow64SetThreadDefaultGuestMachine
0x18002fa26  mov     r9d, r14d; samDesired
0x18002fa29  xor     r8d, r8d; ulOptions
0x18002fa2c  movzx   ebx, ax
0x18002fa2f  mov     rdx, r12; lpSubKey
0x18002fa32  mov     rax, [rbp+60h+arg_20]
0x18002fa39  mov     rcx, r13; hKey
0x18002fa3c  mov     [rsp+90h+phkResult], rax; phkResult
0x18002fa41  call    cs:__imp_RegOpenKeyExW
0x18002fa47  movzx   ecx, bx
0x18002fa4a  mov     edi, eax
0x18002fa4c  call    cs:__imp_Wow64SetThreadDefaultGuestMachine
0x18002fa52  test    edi, edi
0x18002fa54  jz      loc_18002F941
0x18002fa5a  mov     rbx, [rbp+60h+var_50]
0x18002fa5e  inc     esi
0x18002fa60  jmp     short loc_18002FA01
0x18002fa62  test    r15b, r15b
0x18002fa65  jnz     loc_18002F941
0x18002fa6b  jmp     loc_18002F921
```
