# IcsRegReadFromLocation(ushort *,_UNICODE_STRING,ulong *)

- ea: `0x18000f2d0`
- end: `0x18000f541`
- name: `?IcsRegReadFromLocation@@YAKPEAGU_UNICODE_STRING@@PEAK@Z`
- size: `625`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct _UNICODE_STRING *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18000e0b0`

## callees

- `0x18000ca20`
- `0x18000f2d0`
- `0x180052bf4`
- `0x180095b28`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f30e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f3e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f30e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f3e5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f329`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f329`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f3f9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f3f9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f43b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f43b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f3d7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f3d7`

## string_xrefs

- `0x18000f352`: `System\CurrentControlSet\Services\Tcpip6\Parameters\Interfaces\`

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
0x18000f2d0  mov     [rsp+cbData], rcx
0x18000f2d5  push    rbx
0x18000f2d6  push    rbp
0x18000f2d7  push    rsi
0x18000f2d8  push    rdi
0x18000f2d9  push    r14
0x18000f2db  sub     rsp, 30h
0x18000f2df  mov     rsi, r8
0x18000f2e2  mov     rdi, rdx
0x18000f2e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f2ec  lea     r14, WPP_GLOBAL_Control
0x18000f2f3  cmp     rcx, r14
0x18000f2f6  jnz     loc_18000F46F
0x18000f2fc  movzx   ebp, word ptr [rdi]
0x18000f2ff  xor     eax, eax
0x18000f301  mov     [rsp+58h+hKey], rax
0x18000f306  mov     [rsp+58h+Data], eax
0x18000f30a  mov     dword ptr [rsp+58h+cbData], eax
0x18000f30e  call    cs:__imp_GetProcessHeap
0x18000f315  nop     dword ptr [rax+rax+00h]
0x18000f31a  lea     r8, [rbp+80h]; dwBytes
0x18000f321  mov     edx, 8; dwFlags
0x18000f326  mov     rcx, rax; hHeap
0x18000f329  call    cs:__imp_HeapAlloc
0x18000f330  nop     dword ptr [rax+rax+00h]
0x18000f335  mov     rbx, rax
0x18000f338  test    rax, rax
0x18000f33b  jz      loc_18000F49D
0x18000f341  lea     r8, [rbp+80h]; Size
0x18000f348  xor     edx, edx; Val
0x18000f34a  mov     rcx, rax; void *
0x18000f34d  call    memset_0
0x18000f352  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\Tc"...
0x18000f359  lea     rcx, [rbx+7Eh]; void *
0x18000f35d  movzx   r8d, word ptr [rdi]; Size
0x18000f361  mov     rdx, [rdi+8]; Src
0x18000f365  movups  xmmword ptr [rbx], xmm0
0x18000f368  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_3+10h; "urrentControlSet\\Services\\Tcpip6\\Par"...
0x18000f36f  movups  xmmword ptr [rbx+10h], xmm1
0x18000f373  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_3+20h; "ntrolSet\\Services\\Tcpip6\\Parameters"...
0x18000f37a  movups  xmmword ptr [rbx+20h], xmm0
0x18000f37e  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_3+30h; "\\Services\\Tcpip6\\Parameters\\Interfa"...
0x18000f385  movups  xmmword ptr [rbx+30h], xmm1
0x18000f389  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_3+40h; "s\\Tcpip6\\Parameters\\Interfaces\\"
0x18000f390  movups  xmmword ptr [rbx+40h], xmm0
0x18000f394  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_3+50h; "\\Parameters\\Interfaces\\"
0x18000f39b  movups  xmmword ptr [rbx+50h], xmm1
0x18000f39f  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_3+60h; "ers\\Interfaces\\"
0x18000f3a6  movups  xmmword ptr [rbx+60h], xmm0
0x18000f3aa  movups  xmm1, xmmword ptr cs:aSystemCurrentc_3+6Eh; "erfaces\\"
0x18000f3b1  movups  xmmword ptr [rbx+6Eh], xmm1
0x18000f3b5  call    memcpy_0
0x18000f3ba  lea     rax, [rsp+58h+hKey]
0x18000f3bf  mov     r9d, 1; samDesired
0x18000f3c5  xor     r8d, r8d; ulOptions
0x18000f3c8  mov     [rsp+58h+phkResult], rax; phkResult
0x18000f3cd  mov     rdx, rbx; lpSubKey
0x18000f3d0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f3d7  call    cs:__imp_RegOpenKeyExW
0x18000f3de  nop     dword ptr [rax+rax+00h]
0x18000f3e3  mov     edi, eax
0x18000f3e5  call    cs:__imp_GetProcessHeap
0x18000f3ec  nop     dword ptr [rax+rax+00h]
0x18000f3f1  mov     r8, rbx; lpMem
0x18000f3f4  xor     edx, edx; dwFlags
0x18000f3f6  mov     rcx, rax; hHeap
0x18000f3f9  call    cs:__imp_HeapFree
0x18000f400  nop     dword ptr [rax+rax+00h]
0x18000f405  test    edi, edi
0x18000f407  jnz     loc_18000F4BA
0x18000f40d  mov     rcx, [rsp+58h+hKey]; hKey
0x18000f412  lea     rax, [rsp+58h+cbData]
0x18000f417  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18000f41c  lea     rdx, aDhcpv6iaid; "Dhcpv6Iaid"
0x18000f423  lea     rax, [rsp+58h+Data]
0x18000f428  mov     dword ptr [rsp+58h+cbData], 4
0x18000f430  xor     r9d, r9d; lpType
0x18000f433  mov     [rsp+58h+phkResult], rax; lpData
0x18000f438  xor     r8d, r8d; lpReserved
0x18000f43b  call    cs:__imp_RegQueryValueExW
0x18000f442  nop     dword ptr [rax+rax+00h]
0x18000f447  test    eax, eax
0x18000f449  jnz     short loc_18000F4BA
0x18000f44b  mov     eax, [rsp+58h+Data]
0x18000f44f  mov     [rsi], eax
0x18000f451  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f458  cmp     rcx, r14
0x18000f45b  jnz     loc_18000F4F0
0x18000f461  xor     eax, eax
0x18000f463  add     rsp, 30h
0x18000f467  pop     r14
0x18000f469  pop     rdi
0x18000f46a  pop     rsi
0x18000f46b  pop     rbp
0x18000f46c  pop     rbx
0x18000f46d  retn
0x18000f46f  test    byte ptr [rcx+1Ch], 80h
0x18000f473  jz      loc_18000F2FC
0x18000f479  cmp     byte ptr [rcx+19h], 6
0x18000f47d  jb      loc_18000F2FC
0x18000f483  mov     rcx, [rcx+10h]
0x18000f487  lea     r8, WPP_b002d07646b635308a4693336a4759d4_Traceguids
0x18000f48e  mov     edx, 0Ch
0x18000f493  call    WPP_SF_
0x18000f498  jmp     loc_18000F2FC
0x18000f49d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f4a4  cmp     rcx, r14
0x18000f4a7  jnz     short loc_18000F4CD
0x18000f4a9  mov     eax, 8
0x18000f4ae  add     rsp, 30h
0x18000f4b2  pop     r14
0x18000f4b4  pop     rdi
0x18000f4b5  pop     rsi
0x18000f4b6  pop     rbp
0x18000f4b7  pop     rbx
0x18000f4b8  retn
0x18000f4ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f4c1  cmp     rcx, r14
0x18000f4c4  jnz     short loc_18000F51E
0x18000f4c6  mov     eax, 0Dh
0x18000f4cb  jmp     short loc_18000F463
0x18000f4cd  test    byte ptr [rcx+1Ch], 80h
0x18000f4d1  jz      short loc_18000F4A9
0x18000f4d3  cmp     byte ptr [rcx+19h], 6
0x18000f4d7  jb      short loc_18000F4A9
0x18000f4d9  mov     rcx, [rcx+10h]
0x18000f4dd  lea     r8, WPP_b002d07646b635308a4693336a4759d4_Traceguids
0x18000f4e4  mov     edx, 0Dh
0x18000f4e9  call    WPP_SF_
0x18000f4ee  jmp     short loc_18000F4A9
0x18000f4f0  test    byte ptr [rcx+1Ch], 80h
0x18000f4f4  jz      loc_18000F461
0x18000f4fa  cmp     byte ptr [rcx+19h], 6
0x18000f4fe  jb      loc_18000F461
0x18000f504  mov     rcx, [rcx+10h]
0x18000f508  lea     r8, WPP_b002d07646b635308a4693336a4759d4_Traceguids
0x18000f50f  mov     edx, 0Eh
0x18000f514  call    WPP_SF_
0x18000f519  jmp     loc_18000F461
0x18000f51e  test    byte ptr [rcx+1Ch], 80h
0x18000f522  jz      short loc_18000F4C6
0x18000f524  cmp     byte ptr [rcx+19h], 6
0x18000f528  jb      short loc_18000F4C6
0x18000f52a  mov     rcx, [rcx+10h]
0x18000f52e  lea     r8, WPP_b002d07646b635308a4693336a4759d4_Traceguids
0x18000f535  mov     edx, 0Fh
0x18000f53a  call    WPP_SF_
0x18000f53f  jmp     short loc_18000F4C6
```
