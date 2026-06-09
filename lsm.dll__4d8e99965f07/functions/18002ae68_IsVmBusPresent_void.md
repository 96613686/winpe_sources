# IsVmBusPresent(void)

- ea: `0x18002ae68`
- end: `0x18002b108`
- name: `?IsVmBusPresent@@YAHXZ`
- size: `672`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180054be4`

## callees

- `0x1800077a0`
- `0x18002ae68`
- `0x18004e850`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002b039`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002b059`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002b039`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002b059`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aecb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002af16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002afae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b0b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aecb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002af16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002afae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b0b4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002afdf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002afdf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002afcb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b08d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002afcb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b08d`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18002b0da`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18002b0da`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18002aeb6`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18002aeb6`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x18002af99`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x18002af99`
- `DEVOBJ!DevObjGetClassDevs` at `0x18002af06`
- `DEVOBJ!DevObjGetClassDevs` at `0x18002af06`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x18002af5f`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x18002af5f`

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
0x18002ae68  push    rbp
0x18002ae6a  push    rbx
0x18002ae6b  push    rsi
0x18002ae6c  push    rdi
0x18002ae6d  push    r12
0x18002ae6f  push    r14
0x18002ae71  push    r15
0x18002ae73  mov     rbp, rsp
0x18002ae76  sub     rsp, 80h
0x18002ae7d  mov     rax, cs:__security_cookie
0x18002ae84  xor     rax, rsp
0x18002ae87  mov     [rbp+var_8], rax
0x18002ae8b  xorps   xmm0, xmm0
0x18002ae8e  xor     r12d, r12d
0x18002ae91  movups  [rbp+var_38], xmm0
0x18002ae95  xor     r9d, r9d
0x18002ae98  mov     dword ptr [rbp+var_38], 30h ; '0'
0x18002ae9f  xor     r8d, r8d
0x18002aea2  mov     [rsp+80h+var_60], r12
0x18002aea7  xor     edx, edx
0x18002aea9  xor     ecx, ecx
0x18002aeab  mov     r15d, r12d
0x18002aeae  movups  [rbp+var_28], xmm0
0x18002aeb2  movups  [rbp+var_18], xmm0
0x18002aeb6  call    cs:__imp_DevObjCreateDeviceInfoList
0x18002aebd  nop     dword ptr [rax+rax+00h]
0x18002aec2  mov     rsi, rax
0x18002aec5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002aec9  jnz     short loc_18002AEEE
0x18002aecb  call    cs:__imp_GetLastError
0x18002aed2  nop     dword ptr [rax+rax+00h]
0x18002aed7  mov     r8d, eax
0x18002aeda  lea     rdx, aDevobjdigetcla; "DevObjDiGetClassDevs failed: 0x%x"
0x18002aee1  lea     ecx, [rsi+9]; int
0x18002aee4  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002aee9  jmp     loc_18002B0E6
0x18002aeee  mov     [rsp+80h+var_58], r12
0x18002aef3  mov     r9d, 6
0x18002aef9  xor     r8d, r8d
0x18002aefc  mov     [rsp+80h+var_60], r12
0x18002af01  xor     edx, edx
0x18002af03  mov     rcx, rsi
0x18002af06  call    cs:__imp_DevObjGetClassDevs
0x18002af0d  nop     dword ptr [rax+rax+00h]
0x18002af12  test    eax, eax
0x18002af14  jnz     short loc_18002AF3B
0x18002af16  call    cs:__imp_GetLastError
0x18002af1d  nop     dword ptr [rax+rax+00h]
0x18002af22  lea     rdx, aDevobjdigetcla; "DevObjDiGetClassDevs failed: 0x%x"
0x18002af29  mov     ecx, 8; int
0x18002af2e  mov     r8d, eax
0x18002af31  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002af36  jmp     loc_18002B0D7
0x18002af3b  mov     r14d, r12d
0x18002af3e  test    r15d, r15d
0x18002af41  jnz     loc_18002B0D7
0x18002af47  lea     r8, [rbp+var_38]
0x18002af4b  mov     dword ptr [rbp+uBytes+4], r12d
0x18002af4f  mov     edx, r14d
0x18002af52  mov     dword ptr [rbp+uBytes], r12d
0x18002af56  mov     rcx, rsi
0x18002af59  mov     rbx, r12
0x18002af5c  mov     edi, r12d
0x18002af5f  call    cs:__imp_DevObjEnumDeviceInfo
0x18002af66  nop     dword ptr [rax+rax+00h]
0x18002af6b  test    eax, eax
0x18002af6d  jz      loc_18002B0B4
0x18002af73  lea     rax, [rbp+uBytes]
0x18002af77  mov     r8d, 1
0x18002af7d  mov     [rsp+80h+var_50], rax
0x18002af82  lea     r9, [rbp+uBytes+4]
0x18002af86  mov     eax, dword ptr [rbp+uBytes]
0x18002af89  lea     rdx, [rbp+var_38]
0x18002af8d  mov     dword ptr [rsp+80h+var_58], eax
0x18002af91  mov     rcx, rsi
0x18002af94  mov     [rsp+80h+var_60], rbx
0x18002af99  call    cs:__imp_DevObjGetDeviceRegistryProperty
0x18002afa0  nop     dword ptr [rax+rax+00h]
0x18002afa5  test    eax, eax
0x18002afa7  jnz     short loc_18002AFFE
0x18002afa9  cmp     edi, 3
0x18002afac  jge     short loc_18002AFFE
0x18002afae  call    cs:__imp_GetLastError
0x18002afb5  nop     dword ptr [rax+rax+00h]
0x18002afba  cmp     eax, 7Ah ; 'z'
0x18002afbd  jnz     loc_18002B08A
0x18002afc3  test    rbx, rbx
0x18002afc6  jz      short loc_18002AFD7
0x18002afc8  mov     rcx, rbx; hMem
0x18002afcb  call    cs:__imp_LocalFree
0x18002afd2  nop     dword ptr [rax+rax+00h]
0x18002afd7  mov     edx, dword ptr [rbp+uBytes]; uBytes
0x18002afda  mov     ecx, 40h ; '@'; uFlags
0x18002afdf  call    cs:__imp_LocalAlloc
0x18002afe6  nop     dword ptr [rax+rax+00h]
0x18002afeb  mov     rbx, rax
0x18002afee  test    rax, rax
0x18002aff1  jz      loc_18002B0A1
0x18002aff7  inc     edi
0x18002aff9  jmp     loc_18002AF73
0x18002affe  test    rbx, rbx
0x18002b001  jz      loc_18002B099
0x18002b007  cmp     edi, 3
0x18002b00a  jge     short loc_18002B08A
0x18002b00c  mov     eax, dword ptr [rbp+uBytes]
0x18002b00f  cmp     eax, 5
0x18002b012  jbe     short loc_18002B08A
0x18002b014  mov     rdi, rbx
0x18002b017  and     rax, 0FFFFFFFFFFFFFFFEh
0x18002b01b  add     rax, rbx
0x18002b01e  cmp     rdi, rax
0x18002b021  jnb     short loc_18002B08A
0x18002b023  cmp     [rdi], r12w
0x18002b027  jz      short loc_18002B08A
0x18002b029  mov     r8d, 5
0x18002b02f  lea     rcx, aVmbus; "VMBUS"
0x18002b036  mov     rdx, rdi
0x18002b039  call    cs:__imp__o__wcsnicmp
0x18002b040  nop     dword ptr [rax+rax+00h]
0x18002b045  test    eax, eax
0x18002b047  jz      short loc_18002B084
0x18002b049  mov     r8d, 0Ah
0x18002b04f  lea     rcx, aAcpiVmbus; "ACPI\\VMBUS"
0x18002b056  mov     rdx, rdi
0x18002b059  call    cs:__imp__o__wcsnicmp
0x18002b060  nop     dword ptr [rax+rax+00h]
0x18002b065  test    eax, eax
0x18002b067  jz      short loc_18002B084
0x18002b069  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b06d  inc     rax
0x18002b070  cmp     [rdi+rax*2], r12w
0x18002b075  jnz     short loc_18002B06D
0x18002b077  lea     rdi, [rdi+rax*2]
0x18002b07b  mov     eax, dword ptr [rbp+uBytes]
0x18002b07e  add     rdi, 2
0x18002b082  jmp     short loc_18002B017
0x18002b084  mov     r15d, 1
0x18002b08a  mov     rcx, rbx; hMem
0x18002b08d  call    cs:__imp_LocalFree
0x18002b094  nop     dword ptr [rax+rax+00h]
0x18002b099  inc     r14d
0x18002b09c  jmp     loc_18002AF3E
0x18002b0a1  lea     rdx, aLocalAllocatio; "Local allocation failure."
0x18002b0a8  mov     ecx, 8; int
0x18002b0ad  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002b0b2  jmp     short loc_18002B0D7
0x18002b0b4  call    cs:__imp_GetLastError
0x18002b0bb  nop     dword ptr [rax+rax+00h]
0x18002b0c0  mov     r8d, r14d
0x18002b0c3  lea     rdx, aDevobjenumdevi_1; "DevObjEnumDeviceInfo failed for device "...
0x18002b0ca  mov     r9d, eax
0x18002b0cd  mov     ecx, 4; int
0x18002b0d2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002b0d7  mov     rcx, rsi
0x18002b0da  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18002b0e1  nop     dword ptr [rax+rax+00h]
0x18002b0e6  mov     eax, r15d
0x18002b0e9  mov     rcx, [rbp+var_8]
0x18002b0ed  xor     rcx, rsp; StackCookie
0x18002b0f0  call    __security_check_cookie
0x18002b0f5  add     rsp, 80h
0x18002b0fc  pop     r15
0x18002b0fe  pop     r14
0x18002b100  pop     r12
0x18002b102  pop     rdi
0x18002b103  pop     rsi
0x18002b104  pop     rbx
0x18002b105  pop     rbp
0x18002b106  retn
```
