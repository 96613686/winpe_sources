# GetRegistryClassIdName

- ea: `0x18000582c`
- end: `0x1800058e6`
- name: `GetRegistryClassIdName`
- size: `186`
- prototype: `__int64 __fastcall(void *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x1800056d4`

## callees

- `0x180005178`
- `0x1800057f0`
- `0x18000582c`
- `0x18004d9e8`

## string_xrefs

- `0x180005856`: `System\CurrentControlSet\Services\Tcpip\Parameters\Interfaces\?\DhcpClassId`

## pseudocode

```c
__int64 __fastcall GetRegistryClassIdName(void *a1, _QWORD *a2)
{
  unsigned int v3; // ebx
  __int64 v5; // r9
  DWORD v6; // [rsp+58h] [rbp+28h] BYREF
  DWORD v7; // [rsp+60h] [rbp+30h] BYREF
  BYTE *v8; // [rsp+68h] [rbp+38h] BYREF

  *a2 = 0;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v3 = DhcpRegReadFromLocation(
         L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces\\?\\DhcpClassId",
         a1,
         &v8,
         &v6,
         &v7);
  if ( v3 )
  {
    if ( v8 )
      DhcpPunycodeFree((LPVOID *)&v8);
    return v3;
  }
  else
  {
    v5 = v6;
    if ( v6 == 1 )
    {
      *a2 = v8;
      return 0;
    }
    else
    {
      if ( v8 )
      {
        DhcpPunycodeFree((LPVOID *)&v8);
        v5 = v6;
      }
      if ( (xmmword_1800616A0 & 2) != 0 )
        WPP_SF_d(1025, 10, WPP_951d1d083d403a6b63dfdf4ae01534a1_Traceguids, v5);
      return 13;
    }
  }
}

```

## disassembly

```asm
0x18000582c  push    rbp
0x18000582e  push    rbx
0x18000582f  push    rdi
0x180005830  mov     rbp, rsp
0x180005833  sub     rsp, 30h
0x180005837  mov     rdi, rdx
0x18000583a  mov     qword ptr [rdx], 0
0x180005841  mov     rdx, rcx; void *
0x180005844  mov     [rbp+arg_8], 0
0x18000584b  lea     rax, [rbp+arg_10]
0x18000584f  mov     [rbp+arg_10], 0
0x180005856  lea     rcx, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\Tc"...
0x18000585d  mov     [rbp+arg_18], 0
0x180005865  lea     r9, [rbp+arg_8]
0x180005869  mov     [rsp+30h+var_10], rax; LPDWORD
0x18000586e  lea     r8, [rbp+arg_18]
0x180005872  call    DhcpRegReadFromLocation
0x180005877  mov     ebx, eax
0x180005879  test    eax, eax
0x18000587b  jz      short loc_180005891
0x18000587d  cmp     [rbp+arg_18], 0
0x180005882  jz      short loc_18000588D
0x180005884  lea     rcx, [rbp+arg_18]
0x180005888  call    DhcpPunycodeFree
0x18000588d  mov     eax, ebx
0x18000588f  jmp     short loc_1800058DE
0x180005891  mov     r9d, [rbp+arg_8]
0x180005895  cmp     r9d, 1
0x180005899  jz      short loc_1800058D5
0x18000589b  cmp     [rbp+arg_18], 0
0x1800058a0  jz      short loc_1800058AF
0x1800058a2  lea     rcx, [rbp+arg_18]
0x1800058a6  call    DhcpPunycodeFree
0x1800058ab  mov     r9d, [rbp+arg_8]
0x1800058af  test    byte ptr cs:xmmword_1800616A0, 2
0x1800058b6  jz      short loc_1800058CE
0x1800058b8  mov     edx, 0Ah
0x1800058bd  lea     r8, WPP_951d1d083d403a6b63dfdf4ae01534a1_Traceguids
0x1800058c4  mov     ecx, 401h
0x1800058c9  call    WPP_SF_d
0x1800058ce  mov     eax, 0Dh
0x1800058d3  jmp     short loc_1800058DE
0x1800058d5  mov     rax, [rbp+arg_18]
0x1800058d9  mov     [rdi], rax
0x1800058dc  xor     eax, eax
0x1800058de  add     rsp, 30h
0x1800058e2  pop     rdi
0x1800058e3  pop     rbx
0x1800058e4  pop     rbp
0x1800058e5  retn
```
