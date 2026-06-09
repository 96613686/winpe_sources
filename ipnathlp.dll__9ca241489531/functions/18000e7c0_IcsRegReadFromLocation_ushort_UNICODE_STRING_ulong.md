# IcsRegReadFromLocation(ushort *,_UNICODE_STRING,ulong *)

- ea: `0x18000e7c0`
- end: `0x18000ea0b`
- name: `?IcsRegReadFromLocation@@YAKPEAGU_UNICODE_STRING@@PEAK@Z`
- size: `587`
- prototype: `unsigned int __fastcall(unsigned __int16 *, struct _UNICODE_STRING *__struct_ptr, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18000d6a0`

## callees

- `0x18000c110`
- `0x18000e7c0`
- `0x18004ed64`
- `0x18008e908`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e7fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e8c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e7fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e8c3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e813`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e813`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e8d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e8d1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e90d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e90d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e8bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e8bb`

## string_xrefs

- `0x18000e836`: `System\CurrentControlSet\Services\Tcpip6\Parameters\Interfaces\`

## pseudocode

```c
__int64 __fastcall IcsRegReadFromLocation(unsigned __int16 *a1, struct _UNICODE_STRING *a2, unsigned int *a3)
{
  __int64 Length; // rbp
  HANDLE ProcessHeap; // rax
  _OWORD *v7; // rax
  _OWORD *v8; // rbx
  size_t v9; // r8
  PWSTR Buffer; // rdx
  LSTATUS v11; // edi
  HANDLE v12; // rax
  unsigned __int16 *cbData; // [rsp+60h] [rbp+8h] BYREF
  unsigned int Data; // [rsp+68h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  cbData = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_b002d07646b635308a4693336a4759d4_Traceguids);
  }
  Length = a2->Length;
  hKey = 0;
  Data = 0;
  LODWORD(cbData) = 0;
  ProcessHeap = GetProcessHeap();
  v7 = HeapAlloc(ProcessHeap, 8u, Length + 128);
  v8 = v7;
  if ( v7 )
  {
    memset_0(v7, 0, Length + 128);
    v9 = a2->Length;
    Buffer = a2->Buffer;
    *v8 = *(_OWORD *)L"System\\CurrentControlSet\\Services\\Tcpip6\\Parameters\\Interfaces\\";
    v8[1] = *(_OWORD *)L"urrentControlSet\\Services\\Tcpip6\\Parameters\\Interfaces\\";
    v8[2] = *(_OWORD *)L"ntrolSet\\Services\\Tcpip6\\Parameters\\Interfaces\\";
    v8[3] = *(_OWORD *)L"\\Services\\Tcpip6\\Parameters\\Interfaces\\";
    v8[4] = *(_OWORD *)L"s\\Tcpip6\\Parameters\\Interfaces\\";
    v8[5] = *(_OWORD *)L"\\Parameters\\Interfaces\\";
    v8[6] = *(_OWORD *)L"ers\\Interfaces\\";
    *(_OWORD *)((char *)v8 + 110) = *(_OWORD *)L"erfaces\\";
    memcpy_0((char *)v8 + 126, Buffer, v9);
    v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)v8, 0, 1u, &hKey);
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v8);
    if ( v11 || (LODWORD(cbData) = 4, RegQueryValueExW(hKey, L"Dhcpv6Iaid", 0, 0, (LPBYTE)&Data, (LPDWORD)&cbData)) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_b002d07646b635308a4693336a4759d4_Traceguids);
      }
      return 13;
    }
    else
    {
      *a3 = Data;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_b002d07646b635308a4693336a4759d4_Traceguids);
      }
      return 0;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_b002d07646b635308a4693336a4759d4_Traceguids);
    }
    return 8;
  }
}

```

## disassembly

```asm
0x18000e7c0  mov     [rsp+cbData], rcx
0x18000e7c5  push    rbx
0x18000e7c6  push    rbp
0x18000e7c7  push    rsi
0x18000e7c8  push    rdi
0x18000e7c9  push    r14
0x18000e7cb  sub     rsp, 30h
0x18000e7cf  mov     rsi, r8
0x18000e7d2  mov     rdi, rdx
0x18000e7d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e7dc  lea     r14, WPP_GLOBAL_Control
0x18000e7e3  cmp     rcx, r14
0x18000e7e6  jnz     loc_18000E93A
0x18000e7ec  movzx   ebp, word ptr [rdi]
0x18000e7ef  xor     eax, eax
0x18000e7f1  mov     [rsp+58h+hKey], rax
0x18000e7f6  mov     [rsp+58h+Data], eax
0x18000e7fa  mov     dword ptr [rsp+58h+cbData], eax
0x18000e7fe  call    cs:__imp_GetProcessHeap
0x18000e804  lea     r8, [rbp+80h]; dwBytes
0x18000e80b  mov     edx, 8; dwFlags
0x18000e810  mov     rcx, rax; hHeap
0x18000e813  call    cs:__imp_HeapAlloc
0x18000e819  mov     rbx, rax
0x18000e81c  test    rax, rax
0x18000e81f  jz      loc_18000E968
0x18000e825  lea     r8, [rbp+80h]; Size
0x18000e82c  xor     edx, edx; Val
0x18000e82e  mov     rcx, rax; void *
0x18000e831  call    memset_0
0x18000e836  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\Tc"...
0x18000e83d  lea     rcx, [rbx+7Eh]; void *
0x18000e841  movzx   r8d, word ptr [rdi]; Size
0x18000e845  mov     rdx, [rdi+8]; Src
0x18000e849  movups  xmmword ptr [rbx], xmm0
0x18000e84c  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_3+10h; "urrentControlSet\\Services\\Tcpip6\\Par"...
0x18000e853  movups  xmmword ptr [rbx+10h], xmm1
0x18000e857  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_3+20h; "ntrolSet\\Services\\Tcpip6\\Parameters"...
0x18000e85e  movups  xmmword ptr [rbx+20h], xmm0
0x18000e862  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_3+30h; "\\Services\\Tcpip6\\Parameters\\Interfa"...
0x18000e869  movups  xmmword ptr [rbx+30h], xmm1
0x18000e86d  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_3+40h; "s\\Tcpip6\\Parameters\\Interfaces\\"
0x18000e874  movups  xmmword ptr [rbx+40h], xmm0
0x18000e878  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_3+50h; "\\Parameters\\Interfaces\\"
0x18000e87f  movups  xmmword ptr [rbx+50h], xmm1
0x18000e883  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_3+60h; "ers\\Interfaces\\"
0x18000e88a  movups  xmmword ptr [rbx+60h], xmm0
0x18000e88e  movups  xmm1, xmmword ptr cs:aSystemCurrentc_3+6Eh; "erfaces\\"
0x18000e895  movups  xmmword ptr [rbx+6Eh], xmm1
0x18000e899  call    memcpy_0
0x18000e89e  lea     rax, [rsp+58h+hKey]
0x18000e8a3  mov     r9d, 1; samDesired
0x18000e8a9  xor     r8d, r8d; ulOptions
0x18000e8ac  mov     [rsp+58h+phkResult], rax; phkResult
0x18000e8b1  mov     rdx, rbx; lpSubKey
0x18000e8b4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e8bb  call    cs:__imp_RegOpenKeyExW
0x18000e8c1  mov     edi, eax
0x18000e8c3  call    cs:__imp_GetProcessHeap
0x18000e8c9  mov     r8, rbx; lpMem
0x18000e8cc  xor     edx, edx; dwFlags
0x18000e8ce  mov     rcx, rax; hHeap
0x18000e8d1  call    cs:__imp_HeapFree
0x18000e8d7  test    edi, edi
0x18000e8d9  jnz     loc_18000E984
0x18000e8df  mov     rcx, [rsp+58h+hKey]; hKey
0x18000e8e4  lea     rax, [rsp+58h+cbData]
0x18000e8e9  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18000e8ee  lea     rdx, aDhcpv6iaid; "Dhcpv6Iaid"
0x18000e8f5  lea     rax, [rsp+58h+Data]
0x18000e8fa  mov     dword ptr [rsp+58h+cbData], 4
0x18000e902  xor     r9d, r9d; lpType
0x18000e905  mov     [rsp+58h+phkResult], rax; lpData
0x18000e90a  xor     r8d, r8d; lpReserved
0x18000e90d  call    cs:__imp_RegQueryValueExW
0x18000e913  test    eax, eax
0x18000e915  jnz     short loc_18000E984
0x18000e917  mov     eax, [rsp+58h+Data]
0x18000e91b  mov     [rsi], eax
0x18000e91d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e924  cmp     rcx, r14
0x18000e927  jnz     loc_18000E9BA
0x18000e92d  xor     eax, eax
0x18000e92f  add     rsp, 30h
0x18000e933  pop     r14
0x18000e935  pop     rdi
0x18000e936  pop     rsi
0x18000e937  pop     rbp
0x18000e938  pop     rbx
0x18000e939  retn
0x18000e93a  test    byte ptr [rcx+1Ch], 80h
0x18000e93e  jz      loc_18000E7EC
0x18000e944  cmp     byte ptr [rcx+19h], 6
0x18000e948  jb      loc_18000E7EC
0x18000e94e  mov     rcx, [rcx+10h]
0x18000e952  lea     r8, WPP_b002d07646b635308a4693336a4759d4_Traceguids
0x18000e959  mov     edx, 0Ch
0x18000e95e  call    WPP_SF_
0x18000e963  jmp     loc_18000E7EC
0x18000e968  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e96f  cmp     rcx, r14
0x18000e972  jnz     short loc_18000E997
0x18000e974  mov     eax, 8
0x18000e979  add     rsp, 30h
0x18000e97d  pop     r14
0x18000e97f  pop     rdi
0x18000e980  pop     rsi
0x18000e981  pop     rbp
0x18000e982  pop     rbx
0x18000e983  retn
0x18000e984  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e98b  cmp     rcx, r14
0x18000e98e  jnz     short loc_18000E9E8
0x18000e990  mov     eax, 0Dh
0x18000e995  jmp     short loc_18000E92F
0x18000e997  test    byte ptr [rcx+1Ch], 80h
0x18000e99b  jz      short loc_18000E974
0x18000e99d  cmp     byte ptr [rcx+19h], 6
0x18000e9a1  jb      short loc_18000E974
0x18000e9a3  mov     rcx, [rcx+10h]
0x18000e9a7  lea     r8, WPP_b002d07646b635308a4693336a4759d4_Traceguids
0x18000e9ae  mov     edx, 0Dh
0x18000e9b3  call    WPP_SF_
0x18000e9b8  jmp     short loc_18000E974
0x18000e9ba  test    byte ptr [rcx+1Ch], 80h
0x18000e9be  jz      loc_18000E92D
0x18000e9c4  cmp     byte ptr [rcx+19h], 6
0x18000e9c8  jb      loc_18000E92D
0x18000e9ce  mov     rcx, [rcx+10h]
0x18000e9d2  lea     r8, WPP_b002d07646b635308a4693336a4759d4_Traceguids
0x18000e9d9  mov     edx, 0Eh
0x18000e9de  call    WPP_SF_
0x18000e9e3  jmp     loc_18000E92D
0x18000e9e8  test    byte ptr [rcx+1Ch], 80h
0x18000e9ec  jz      short loc_18000E990
0x18000e9ee  cmp     byte ptr [rcx+19h], 6
0x18000e9f2  jb      short loc_18000E990
0x18000e9f4  mov     rcx, [rcx+10h]
0x18000e9f8  lea     r8, WPP_b002d07646b635308a4693336a4759d4_Traceguids
0x18000e9ff  mov     edx, 0Fh
0x18000ea04  call    WPP_SF_
0x18000ea09  jmp     short loc_18000E990
```
