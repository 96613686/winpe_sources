# IsVmBusPresent(void)

- ea: `0x180028c30`
- end: `0x180028e78`
- name: `?IsVmBusPresent@@YAHXZ`
- size: `584`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180051464`

## callees

- `0x1800074c0`
- `0x180028c30`
- `0x18004b460`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180028dc8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180028de2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180028dc8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180028de2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028c8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028ccc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028d52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028e31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028c8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028ccc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028d52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028e31`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028d77`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028d77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028d69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028e10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028d69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028e10`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180028e51`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180028e51`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180028c7e`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180028c7e`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x180028d43`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x180028d43`
- `DEVOBJ!DevObjGetClassDevs` at `0x180028cc2`
- `DEVOBJ!DevObjGetClassDevs` at `0x180028cc2`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x180028d0f`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x180028d0f`

## pseudocode

```c
__int64 IsVmBusPresent(void)
{
  unsigned int v0; // r15d
  __int64 DeviceInfoList; // rax
  __int64 v2; // rsi
  DWORD LastError; // eax
  DWORD v4; // eax
  unsigned int v5; // r14d
  _WORD *v6; // rbx
  int v7; // edi
  __int64 v8; // rax
  _WORD *i; // rdi
  __int64 v10; // rax
  _WORD *v11; // rdi
  DWORD v12; // eax
  SIZE_T uBytes; // [rsp+40h] [rbp-40h] BYREF
  _OWORD v15[3]; // [rsp+48h] [rbp-38h] BYREF

  memset(v15, 0, sizeof(v15));
  LODWORD(v15[0]) = 48;
  v0 = 0;
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v2 = DeviceInfoList;
  if ( DeviceInfoList == -1 )
  {
    LastError = GetLastError();
    _DbgPrintMessage(8, "DevObjDiGetClassDevs failed: 0x%x", LastError);
  }
  else
  {
    if ( (unsigned int)DevObjGetClassDevs(DeviceInfoList, 0, 0, 6, 0, 0) )
    {
      v5 = 0;
LABEL_6:
      if ( !v0 )
      {
        uBytes = 0;
        v6 = 0;
        v7 = 0;
        if ( (unsigned int)DevObjEnumDeviceInfo(v2, v5, v15) )
        {
          while ( 1 )
          {
            if ( (unsigned int)DevObjGetDeviceRegistryProperty(v2, v15, 1, (char *)&uBytes + 4, v6, uBytes, &uBytes)
              || v7 >= 3 )
            {
              if ( v6 )
              {
                if ( v7 < 3 )
                {
                  v8 = (unsigned int)uBytes;
                  if ( (unsigned int)uBytes > 5 )
                  {
                    for ( i = v6; i < (_WORD *)((char *)v6 + (v8 & 0xFFFFFFFFFFFFFFFEuLL)) && *i; i = v11 + 1 )
                    {
                      if ( !(unsigned int)_o__wcsnicmp(L"VMBUS", i, 5)
                        || !(unsigned int)_o__wcsnicmp(L"ACPI\\VMBUS", i, 10) )
                      {
                        v0 = 1;
                        break;
                      }
                      v10 = -1;
                      do
                        ++v10;
                      while ( i[v10] );
                      v11 = &i[v10];
                      v8 = (unsigned int)uBytes;
                    }
                  }
                }
LABEL_27:
                LocalFree(v6);
              }
              ++v5;
              goto LABEL_6;
            }
            if ( GetLastError() != 122 )
              goto LABEL_27;
            if ( v6 )
              LocalFree(v6);
            v6 = LocalAlloc(0x40u, (unsigned int)uBytes);
            if ( !v6 )
              break;
            ++v7;
          }
          _DbgPrintMessage(8, "Local allocation failure.");
        }
        else
        {
          v12 = GetLastError();
          _DbgPrintMessage(4, "DevObjEnumDeviceInfo failed for device %d : 0x%x", v5, v12);
        }
      }
    }
    else
    {
      v4 = GetLastError();
      _DbgPrintMessage(8, "DevObjDiGetClassDevs failed: 0x%x", v4);
    }
    DevObjDestroyDeviceInfoList(v2);
  }
  return v0;
}

```

## disassembly

```asm
0x180028c30  push    rbp
0x180028c32  push    rbx
0x180028c33  push    rsi
0x180028c34  push    rdi
0x180028c35  push    r12
0x180028c37  push    r14
0x180028c39  push    r15
0x180028c3b  mov     rbp, rsp
0x180028c3e  sub     rsp, 80h
0x180028c45  mov     rax, cs:__security_cookie
0x180028c4c  xor     rax, rsp
0x180028c4f  mov     [rbp+var_8], rax
0x180028c53  xorps   xmm0, xmm0
0x180028c56  xor     r12d, r12d
0x180028c59  movups  [rbp+var_38], xmm0
0x180028c5d  xor     r9d, r9d
0x180028c60  mov     dword ptr [rbp+var_38], 30h ; '0'
0x180028c67  xor     r8d, r8d
0x180028c6a  mov     [rsp+80h+var_60], r12
0x180028c6f  xor     edx, edx
0x180028c71  xor     ecx, ecx
0x180028c73  mov     r15d, r12d
0x180028c76  movups  [rbp+var_28], xmm0
0x180028c7a  movups  [rbp+var_18], xmm0
0x180028c7e  call    cs:__imp_DevObjCreateDeviceInfoList
0x180028c84  mov     rsi, rax
0x180028c87  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180028c8b  jnz     short loc_180028CAA
0x180028c8d  call    cs:__imp_GetLastError
0x180028c93  mov     r8d, eax
0x180028c96  lea     rdx, aDevobjdigetcla; "DevObjDiGetClassDevs failed: 0x%x"
0x180028c9d  lea     ecx, [rsi+9]; int
0x180028ca0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180028ca5  jmp     loc_180028E57
0x180028caa  mov     [rsp+80h+var_58], r12
0x180028caf  mov     r9d, 6
0x180028cb5  xor     r8d, r8d
0x180028cb8  mov     [rsp+80h+var_60], r12
0x180028cbd  xor     edx, edx
0x180028cbf  mov     rcx, rsi
0x180028cc2  call    cs:__imp_DevObjGetClassDevs
0x180028cc8  test    eax, eax
0x180028cca  jnz     short loc_180028CEB
0x180028ccc  call    cs:__imp_GetLastError
0x180028cd2  lea     rdx, aDevobjdigetcla; "DevObjDiGetClassDevs failed: 0x%x"
0x180028cd9  mov     ecx, 8; int
0x180028cde  mov     r8d, eax
0x180028ce1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180028ce6  jmp     loc_180028E4E
0x180028ceb  mov     r14d, r12d
0x180028cee  test    r15d, r15d
0x180028cf1  jnz     loc_180028E4E
0x180028cf7  lea     r8, [rbp+var_38]
0x180028cfb  mov     dword ptr [rbp+uBytes+4], r12d
0x180028cff  mov     edx, r14d
0x180028d02  mov     dword ptr [rbp+uBytes], r12d
0x180028d06  mov     rcx, rsi
0x180028d09  mov     rbx, r12
0x180028d0c  mov     edi, r12d
0x180028d0f  call    cs:__imp_DevObjEnumDeviceInfo
0x180028d15  test    eax, eax
0x180028d17  jz      loc_180028E31
0x180028d1d  lea     rax, [rbp+uBytes]
0x180028d21  mov     r8d, 1
0x180028d27  mov     [rsp+80h+var_50], rax
0x180028d2c  lea     r9, [rbp+uBytes+4]
0x180028d30  mov     eax, dword ptr [rbp+uBytes]
0x180028d33  lea     rdx, [rbp+var_38]
0x180028d37  mov     dword ptr [rsp+80h+var_58], eax
0x180028d3b  mov     rcx, rsi
0x180028d3e  mov     [rsp+80h+var_60], rbx
0x180028d43  call    cs:__imp_DevObjGetDeviceRegistryProperty
0x180028d49  test    eax, eax
0x180028d4b  jnz     short loc_180028D8D
0x180028d4d  cmp     edi, 3
0x180028d50  jge     short loc_180028D8D
0x180028d52  call    cs:__imp_GetLastError
0x180028d58  cmp     eax, 7Ah ; 'z'
0x180028d5b  jnz     loc_180028E0D
0x180028d61  test    rbx, rbx
0x180028d64  jz      short loc_180028D6F
0x180028d66  mov     rcx, rbx; hMem
0x180028d69  call    cs:__imp_LocalFree
0x180028d6f  mov     edx, dword ptr [rbp+uBytes]; uBytes
0x180028d72  mov     ecx, 40h ; '@'; uFlags
0x180028d77  call    cs:__imp_LocalAlloc
0x180028d7d  mov     rbx, rax
0x180028d80  test    rax, rax
0x180028d83  jz      loc_180028E1E
0x180028d89  inc     edi
0x180028d8b  jmp     short loc_180028D1D
0x180028d8d  test    rbx, rbx
0x180028d90  jz      loc_180028E16
0x180028d96  cmp     edi, 3
0x180028d99  jge     short loc_180028E0D
0x180028d9b  mov     eax, dword ptr [rbp+uBytes]
0x180028d9e  cmp     eax, 5
0x180028da1  jbe     short loc_180028E0D
0x180028da3  mov     rdi, rbx
0x180028da6  and     rax, 0FFFFFFFFFFFFFFFEh
0x180028daa  add     rax, rbx
0x180028dad  cmp     rdi, rax
0x180028db0  jnb     short loc_180028E0D
0x180028db2  cmp     [rdi], r12w
0x180028db6  jz      short loc_180028E0D
0x180028db8  mov     r8d, 5
0x180028dbe  lea     rcx, aVmbus; "VMBUS"
0x180028dc5  mov     rdx, rdi
0x180028dc8  call    cs:__imp__o__wcsnicmp
0x180028dce  test    eax, eax
0x180028dd0  jz      short loc_180028E07
0x180028dd2  mov     r8d, 0Ah
0x180028dd8  lea     rcx, aAcpiVmbus; "ACPI\\VMBUS"
0x180028ddf  mov     rdx, rdi
0x180028de2  call    cs:__imp__o__wcsnicmp
0x180028de8  test    eax, eax
0x180028dea  jz      short loc_180028E07
0x180028dec  or      rax, 0FFFFFFFFFFFFFFFFh
0x180028df0  inc     rax
0x180028df3  cmp     [rdi+rax*2], r12w
0x180028df8  jnz     short loc_180028DF0
0x180028dfa  lea     rdi, [rdi+rax*2]
0x180028dfe  mov     eax, dword ptr [rbp+uBytes]
0x180028e01  add     rdi, 2
0x180028e05  jmp     short loc_180028DA6
0x180028e07  mov     r15d, 1
0x180028e0d  mov     rcx, rbx; hMem
0x180028e10  call    cs:__imp_LocalFree
0x180028e16  inc     r14d
0x180028e19  jmp     loc_180028CEE
0x180028e1e  lea     rdx, aLocalAllocatio; "Local allocation failure."
0x180028e25  mov     ecx, 8; int
0x180028e2a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180028e2f  jmp     short loc_180028E4E
0x180028e31  call    cs:__imp_GetLastError
0x180028e37  mov     r8d, r14d
0x180028e3a  lea     rdx, aDevobjenumdevi_1; "DevObjEnumDeviceInfo failed for device "...
0x180028e41  mov     r9d, eax
0x180028e44  mov     ecx, 4; int
0x180028e49  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180028e4e  mov     rcx, rsi
0x180028e51  call    cs:__imp_DevObjDestroyDeviceInfoList
0x180028e57  mov     eax, r15d
0x180028e5a  mov     rcx, [rbp+var_8]
0x180028e5e  xor     rcx, rsp; StackCookie
0x180028e61  call    __security_check_cookie
0x180028e66  add     rsp, 80h
0x180028e6d  pop     r15
0x180028e6f  pop     r14
0x180028e71  pop     r12
0x180028e73  pop     rdi
0x180028e74  pop     rsi
0x180028e75  pop     rbx
0x180028e76  pop     rbp
0x180028e77  retn
```
