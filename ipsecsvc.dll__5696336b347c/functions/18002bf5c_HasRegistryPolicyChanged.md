# HasRegistryPolicyChanged

- ea: `0x18002bf5c`
- end: `0x18002c0ac`
- name: `HasRegistryPolicyChanged`
- size: `336`
- prototype: `__int64 __fastcall(wchar_t *String2, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002d2ec`

## callees

- `0x180001030`
- `0x180006f60`
- `0x18000e510`
- `0x18002bf5c`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002c04e`
- `msvcrt!_wcsicmp` at `0x18002c04e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002bfa4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002bfa4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c084`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c084`

## pseudocode

```c
__int64 __fastcall HasRegistryPolicyChanged(wchar_t *String2, int *a2)
{
  unsigned int v4; // eax
  unsigned int v5; // esi
  _QWORD *v6; // rcx
  int v7; // ecx
  __int64 v9; // [rsp+70h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  hKey = 0;
  LODWORD(v9) = 0;
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Policies\\Microsoft\\Windows\\IPSEC\\Policy\\Local",
         0,
         0x20019u,
         &hKey);
  v5 = v4;
  if ( v4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 128, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, v4);
        v6 = WPP_GLOBAL_Control;
      }
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x10) != 0 )
        WPP_SF_d(v6[2], 129, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, v5);
    }
    v7 = 0;
  }
  else
  {
    RegstoreQueryValueSpd(hKey, L"ActivePolicy", (__int64)&v9);
    if ( !String2 || (v7 = 1, !*String2) )
      v7 = 0;
    v5 = 0;
  }
  *a2 = v7;
  if ( hKey )
    RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x18002bf5c  mov     rax, rsp
0x18002bf5f  mov     [rax+8], rbx
0x18002bf63  mov     [rax+10h], rbp
0x18002bf67  push    rsi
0x18002bf68  push    rdi
0x18002bf69  push    r14
0x18002bf6b  sub     rsp, 40h
0x18002bf6f  xor     ebp, ebp
0x18002bf71  mov     r14, rdx
0x18002bf74  mov     [rax+20h], rbp
0x18002bf78  mov     rbx, rcx
0x18002bf7b  mov     [rax-28h], rbp
0x18002bf7f  mov     r9d, 20019h; samDesired
0x18002bf85  mov     [rax+18h], ebp
0x18002bf88  lea     rax, [rax+20h]
0x18002bf8c  xor     r8d, r8d; ulOptions
0x18002bf8f  mov     [rsp+58h+phkResult], rax; phkResult
0x18002bf94  lea     rdx, SubKey; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18002bf9b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002bfa2  mov     edi, ebp
0x18002bfa4  call    cs:__imp_RegOpenKeyExW
0x18002bfaa  mov     esi, eax
0x18002bfac  test    eax, eax
0x18002bfae  jz      short loc_18002C00F
0x18002bfb0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bfb7  lea     rbx, WPP_GLOBAL_Control
0x18002bfbe  cmp     rcx, rbx
0x18002bfc1  jz      short loc_18002C00B
0x18002bfc3  test    byte ptr [rcx+1Ch], 10h
0x18002bfc7  jz      short loc_18002BFE8
0x18002bfc9  mov     rcx, [rcx+10h]
0x18002bfcd  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002bfd4  mov     edx, 80h
0x18002bfd9  mov     r9d, eax
0x18002bfdc  call    WPP_SF_d
0x18002bfe1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bfe8  cmp     rcx, rbx
0x18002bfeb  jz      short loc_18002C00B
0x18002bfed  test    byte ptr [rcx+1Ch], 10h
0x18002bff1  jz      short loc_18002C00B
0x18002bff3  mov     rcx, [rcx+10h]
0x18002bff7  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002bffe  mov     edx, 81h
0x18002c003  mov     r9d, esi
0x18002c006  call    WPP_SF_d
0x18002c00b  mov     ecx, ebp
0x18002c00d  jmp     short loc_18002C077
0x18002c00f  mov     rcx, [rsp+58h+hKey]; hKey
0x18002c014  lea     rax, [rsp+58h+arg_10]
0x18002c019  lea     r9, [rsp+58h+String1]
0x18002c01e  mov     [rsp+58h+phkResult], rax; __int64
0x18002c023  lea     rdx, aActivepolicy; "ActivePolicy"
0x18002c02a  call    RegstoreQueryValueSpd
0x18002c02f  mov     rdi, [rsp+58h+String1]
0x18002c034  test    rdi, rdi
0x18002c037  jz      short loc_18002C064
0x18002c039  cmp     [rdi], bp
0x18002c03c  jz      short loc_18002C064
0x18002c03e  test    rbx, rbx
0x18002c041  jz      short loc_18002C05D
0x18002c043  cmp     [rbx], bp
0x18002c046  jz      short loc_18002C05D
0x18002c048  mov     rdx, rbx; String2
0x18002c04b  mov     rcx, rdi; String1
0x18002c04e  call    cs:__imp__wcsicmp
0x18002c054  test    eax, eax
0x18002c056  mov     ecx, ebp
0x18002c058  setnz   cl
0x18002c05b  jmp     short loc_18002C075
0x18002c05d  mov     ecx, 1
0x18002c062  jmp     short loc_18002C075
0x18002c064  test    rbx, rbx
0x18002c067  jz      short loc_18002C073
0x18002c069  mov     ecx, 1
0x18002c06e  cmp     [rbx], bp
0x18002c071  jnz     short loc_18002C075
0x18002c073  mov     ecx, ebp
0x18002c075  mov     esi, ebp
0x18002c077  mov     [r14], ecx
0x18002c07a  mov     rcx, [rsp+58h+hKey]; hKey
0x18002c07f  test    rcx, rcx
0x18002c082  jz      short loc_18002C08A
0x18002c084  call    cs:__imp_RegCloseKey
0x18002c08a  test    rdi, rdi
0x18002c08d  jz      short loc_18002C097
0x18002c08f  mov     rcx, rdi; lpMem
0x18002c092  call    IpsecFreeMem
0x18002c097  mov     rbx, [rsp+58h+arg_0]
0x18002c09c  mov     eax, esi
0x18002c09e  mov     rbp, [rsp+58h+arg_8]
0x18002c0a3  add     rsp, 40h
0x18002c0a7  pop     r14
0x18002c0a9  pop     rdi
0x18002c0aa  pop     rsi
0x18002c0ab  retn
```
