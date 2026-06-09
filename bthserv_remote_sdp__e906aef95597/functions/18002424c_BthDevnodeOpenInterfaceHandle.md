# BthDevnodeOpenInterfaceHandle

- ea: `0x18002424c`
- end: `0x18002450f`
- name: `BthDevnodeOpenInterfaceHandle`
- size: `707`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180022a74`
- `0x180025648`
- `0x180025ecc`
- `0x18002cc80`

## callees

- `0x1800017a0`
- `0x1800026d0`
- `0x1800026dc`
- `0x18000270c`
- `0x18002424c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800242a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800242f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002435d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800243bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024445`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002449f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800242a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800242f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002435d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800243bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024445`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002449f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002448a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002448a`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1800243a7`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180024435`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1800243a7`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180024435`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18002428b`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18002428b`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800242e5`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800242e5`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800244da`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800244da`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18002434d`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18002434d`

## pseudocode

```c
__int64 __fastcall BthDevnodeOpenInterfaceHandle(__int64 a1, DWORD a2, _QWORD *a3)
{
  __int64 DeviceInfoList; // rbp
  signed int LastError; // eax
  signed int v7; // ebx
  signed int v8; // eax
  signed int v9; // eax
  signed int v10; // eax
  unsigned int v11; // esi
  WCHAR *v12; // rdi
  signed int v13; // eax
  HANDLE FileW; // rsi
  signed int v15; // eax
  size_t Size; // [rsp+40h] [rbp-58h] BYREF
  _OWORD v18[2]; // [rsp+48h] [rbp-50h] BYREF

  *a3 = -1;
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  if ( DeviceInfoList != -1 )
    goto LABEL_41;
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  if ( v7 >= 0 )
  {
LABEL_41:
    if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_BTHPORT_DEVICE_INTERFACE, 0, 18, 0, 0) )
    {
      v8 = GetLastError();
      v7 = v8;
      if ( v8 > 0 )
        v7 = (unsigned __int16)v8 | 0x80070000;
      if ( v7 >= 0 )
        v7 = -2147467259;
      goto LABEL_36;
    }
    memset(v18, 0, sizeof(v18));
    LODWORD(v18[0]) = 32;
    if ( !(unsigned int)DevObjEnumDeviceInterfaces(DeviceInfoList, 0, &GUID_BTHPORT_DEVICE_INTERFACE, 0, v18) )
    {
      v9 = GetLastError();
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
      if ( v9 >= 0 )
        v9 = -2147467259;
      v7 = v9;
      goto LABEL_36;
    }
    LODWORD(Size) = 0;
    if ( (unsigned int)DevObjGetDeviceInterfaceDetail(DeviceInfoList, v18, 0, 0, &Size, 0) )
      goto LABEL_35;
    v10 = GetLastError();
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    if ( v10 != -2147024774 || (v11 = Size) == 0 )
    {
LABEL_35:
      v7 = -2147418113;
LABEL_36:
      if ( DeviceInfoList != -1 )
        DevObjDestroyDeviceInfoList(DeviceInfoList);
      return (unsigned int)v7;
    }
    v12 = (WCHAR *)o_malloc_0((unsigned int)Size);
    v7 = v12 == 0 ? 0x8007000E : 0;
    if ( !v12 )
      goto LABEL_36;
    memset_0(v12, 0, v11);
    *(_DWORD *)v12 = 8;
    if ( (unsigned int)DevObjGetDeviceInterfaceDetail(DeviceInfoList, v18, v12, v11, 0, 0) )
    {
      FileW = CreateFileW(v12 + 2, 0xC0000000, 3u, 0, 3u, a2, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        v15 = GetLastError();
        v7 = v15;
        if ( v15 > 0 )
          v7 = (unsigned __int16)v15 | 0x80070000;
        if ( v7 < 0 )
          goto LABEL_34;
      }
      else
      {
        v7 = 0;
      }
      *a3 = FileW;
    }
    else
    {
      v13 = GetLastError();
      v7 = v13;
      if ( v13 > 0 )
        v7 = (unsigned __int16)v13 | 0x80070000;
      if ( v7 >= 0 )
        v7 = -2147467259;
    }
LABEL_34:
    free(v12);
    goto LABEL_36;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002424c  mov     [rsp+arg_0], rbx
0x180024251  mov     [rsp+arg_18], rbp
0x180024256  push    rsi
0x180024257  push    rdi
0x180024258  push    r13
0x18002425a  push    r14
0x18002425c  push    r15
0x18002425e  sub     rsp, 70h
0x180024262  mov     rax, cs:__security_cookie
0x180024269  xor     rax, rsp
0x18002426c  mov     [rsp+98h+var_30], rax
0x180024271  or      qword ptr [r8], 0FFFFFFFFFFFFFFFFh
0x180024275  mov     r14, r8
0x180024278  and     qword ptr [rsp+98h+dwCreationDisposition], 0
0x18002427e  mov     r15d, edx
0x180024281  xor     r8d, r8d
0x180024284  xor     edx, edx
0x180024286  xor     r9d, r9d
0x180024289  xor     ecx, ecx
0x18002428b  call    cs:__imp_DevObjCreateDeviceInfoList
0x180024292  nop     dword ptr [rax+rax+00h]
0x180024297  mov     rbp, rax
0x18002429a  mov     r13d, 80070000h
0x1800242a0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800242a4  jnz     short loc_1800242C6
0x1800242a6  call    cs:__imp_GetLastError
0x1800242ad  nop     dword ptr [rax+rax+00h]
0x1800242b2  mov     ebx, eax
0x1800242b4  test    eax, eax
0x1800242b6  jle     short loc_1800242BE
0x1800242b8  movzx   ebx, ax
0x1800242bb  or      ebx, r13d
0x1800242be  test    ebx, ebx
0x1800242c0  js      loc_1800244E6
0x1800242c6  and     qword ptr [rsp+98h+dwFlagsAndAttributes], 0
0x1800242cc  lea     rdx, GUID_BTHPORT_DEVICE_INTERFACE
0x1800242d3  and     qword ptr [rsp+98h+dwCreationDisposition], 0
0x1800242d9  mov     r9d, 12h
0x1800242df  xor     r8d, r8d
0x1800242e2  mov     rcx, rbp
0x1800242e5  call    cs:__imp_DevObjGetClassDevs
0x1800242ec  nop     dword ptr [rax+rax+00h]
0x1800242f1  test    eax, eax
0x1800242f3  jnz     short loc_18002431F
0x1800242f5  call    cs:__imp_GetLastError
0x1800242fc  nop     dword ptr [rax+rax+00h]
0x180024301  mov     ebx, eax
0x180024303  test    eax, eax
0x180024305  jle     short loc_18002430D
0x180024307  movzx   ebx, ax
0x18002430a  or      ebx, r13d
0x18002430d  test    ebx, ebx
0x18002430f  js      loc_1800244D1
0x180024315  mov     ebx, 80004005h
0x18002431a  jmp     loc_1800244D1
0x18002431f  xorps   xmm0, xmm0
0x180024322  lea     rax, [rsp+98h+var_50]
0x180024327  movups  [rsp+98h+var_50], xmm0
0x18002432c  xor     r9d, r9d
0x18002432f  mov     dword ptr [rsp+98h+var_50], 20h ; ' '
0x180024337  lea     r8, GUID_BTHPORT_DEVICE_INTERFACE
0x18002433e  mov     qword ptr [rsp+98h+dwCreationDisposition], rax
0x180024343  xor     edx, edx
0x180024345  mov     rcx, rbp
0x180024348  movups  [rsp+98h+var_40], xmm0
0x18002434d  call    cs:__imp_DevObjEnumDeviceInterfaces
0x180024354  nop     dword ptr [rax+rax+00h]
0x180024359  test    eax, eax
0x18002435b  jnz     short loc_180024384
0x18002435d  call    cs:__imp_GetLastError
0x180024364  nop     dword ptr [rax+rax+00h]
0x180024369  test    eax, eax
0x18002436b  jle     short loc_180024373
0x18002436d  movzx   eax, ax
0x180024370  or      eax, r13d
0x180024373  mov     ebx, 80004005h
0x180024378  test    eax, eax
0x18002437a  cmovns  eax, ebx
0x18002437d  mov     ebx, eax
0x18002437f  jmp     loc_1800244D1
0x180024384  and     qword ptr [rsp+98h+dwFlagsAndAttributes], 0
0x18002438a  lea     rax, [rsp+98h+Size]
0x18002438f  and     dword ptr [rsp+98h+Size], 0
0x180024394  lea     rdx, [rsp+98h+var_50]
0x180024399  xor     r9d, r9d
0x18002439c  mov     qword ptr [rsp+98h+dwCreationDisposition], rax
0x1800243a1  xor     r8d, r8d
0x1800243a4  mov     rcx, rbp
0x1800243a7  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x1800243ae  nop     dword ptr [rax+rax+00h]
0x1800243b3  test    eax, eax
0x1800243b5  jnz     loc_1800244CC
0x1800243bb  call    cs:__imp_GetLastError
0x1800243c2  nop     dword ptr [rax+rax+00h]
0x1800243c7  test    eax, eax
0x1800243c9  jle     short loc_1800243D1
0x1800243cb  movzx   eax, ax
0x1800243ce  or      eax, r13d
0x1800243d1  cmp     eax, 8007007Ah
0x1800243d6  jnz     loc_1800244CC
0x1800243dc  mov     esi, dword ptr [rsp+98h+Size]
0x1800243e0  test    esi, esi
0x1800243e2  jz      loc_1800244CC
0x1800243e8  mov     ecx, esi; Size
0x1800243ea  call    _o_malloc_0
0x1800243ef  mov     rdi, rax
0x1800243f2  neg     rax
0x1800243f5  sbb     ebx, ebx
0x1800243f7  not     ebx
0x1800243f9  and     ebx, 8007000Eh
0x1800243ff  test    rdi, rdi
0x180024402  jz      loc_1800244D1
0x180024408  mov     r8d, esi; Size
0x18002440b  xor     edx, edx; Val
0x18002440d  mov     rcx, rdi; void *
0x180024410  call    memset_0
0x180024415  and     qword ptr [rsp+98h+dwFlagsAndAttributes], 0
0x18002441b  lea     rdx, [rsp+98h+var_50]
0x180024420  and     qword ptr [rsp+98h+dwCreationDisposition], 0
0x180024426  mov     r9d, esi
0x180024429  mov     r8, rdi
0x18002442c  mov     dword ptr [rdi], 8
0x180024432  mov     rcx, rbp
0x180024435  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x18002443c  nop     dword ptr [rax+rax+00h]
0x180024441  test    eax, eax
0x180024443  jnz     short loc_180024468
0x180024445  call    cs:__imp_GetLastError
0x18002444c  nop     dword ptr [rax+rax+00h]
0x180024451  mov     ebx, eax
0x180024453  test    eax, eax
0x180024455  jle     short loc_18002445D
0x180024457  movzx   ebx, ax
0x18002445a  or      ebx, r13d
0x18002445d  test    ebx, ebx
0x18002445f  js      short loc_1800244C2
0x180024461  mov     ebx, 80004005h
0x180024466  jmp     short loc_1800244C2
0x180024468  and     [rsp+98h+var_68], 0
0x18002446e  lea     rcx, [rdi+4]; lpFileName
0x180024472  mov     r8d, 3; dwShareMode
0x180024478  mov     [rsp+98h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x18002447d  xor     r9d, r9d; lpSecurityAttributes
0x180024480  mov     [rsp+98h+dwCreationDisposition], r8d; dwCreationDisposition
0x180024485  mov     edx, 0C0000000h; dwDesiredAccess
0x18002448a  call    cs:__imp_CreateFileW
0x180024491  nop     dword ptr [rax+rax+00h]
0x180024496  mov     rsi, rax
0x180024499  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002449d  jnz     short loc_1800244BD
0x18002449f  call    cs:__imp_GetLastError
0x1800244a6  nop     dword ptr [rax+rax+00h]
0x1800244ab  mov     ebx, eax
0x1800244ad  test    eax, eax
0x1800244af  jle     short loc_1800244B7
0x1800244b1  movzx   ebx, ax
0x1800244b4  or      ebx, r13d
0x1800244b7  test    ebx, ebx
0x1800244b9  jns     short loc_1800244BF
0x1800244bb  jmp     short loc_1800244C2
0x1800244bd  xor     ebx, ebx
0x1800244bf  mov     [r14], rsi
0x1800244c2  mov     rcx, rdi; Block
0x1800244c5  call    free
0x1800244ca  jmp     short loc_1800244D1
0x1800244cc  mov     ebx, 8000FFFFh
0x1800244d1  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x1800244d5  jz      short loc_1800244E6
0x1800244d7  mov     rcx, rbp
0x1800244da  call    cs:__imp_DevObjDestroyDeviceInfoList
0x1800244e1  nop     dword ptr [rax+rax+00h]
0x1800244e6  mov     eax, ebx
0x1800244e8  mov     rcx, [rsp+98h+var_30]
0x1800244ed  xor     rcx, rsp; StackCookie
0x1800244f0  call    __security_check_cookie
0x1800244f5  lea     r11, [rsp+98h+var_28]
0x1800244fa  mov     rbx, [r11+30h]
0x1800244fe  mov     rbp, [r11+48h]
0x180024502  mov     rsp, r11
0x180024505  pop     r15
0x180024507  pop     r14
0x180024509  pop     r13
0x18002450b  pop     rdi
0x18002450c  pop     rsi
0x18002450d  retn
```
