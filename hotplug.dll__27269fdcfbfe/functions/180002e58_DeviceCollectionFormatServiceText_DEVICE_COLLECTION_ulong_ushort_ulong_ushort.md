# DeviceCollectionFormatServiceText(DEVICE_COLLECTION *,ulong,ushort *,ulong,ushort *)

- ea: `0x180002e58`
- end: `0x180002f95`
- name: `?DeviceCollectionFormatServiceText@@YAHPEAUDEVICE_COLLECTION@@KPEAGK1@Z`
- size: `317`
- prototype: `__int64 __fastcall(struct DEVICE_COLLECTION **, __int64, unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180007f1c`

## callees

- `0x180002e58`
- `0x180003048`
- `0x180008760`

## import_xrefs

- `ADVAPI32!OpenSCManagerW` at `0x180002eec`
- `ADVAPI32!OpenSCManagerW` at `0x180002eec`
- `ADVAPI32!CloseServiceHandle` at `0x180002f26`
- `ADVAPI32!CloseServiceHandle` at `0x180002f26`
- `ADVAPI32!GetServiceDisplayNameW` at `0x180002f13`
- `ADVAPI32!GetServiceDisplayNameW` at `0x180002f13`

## string_xrefs

- `0x180002ee3`: `ServicesActive`

## pseudocode

```c
__int64 __fastcall DeviceCollectionFormatServiceText(
        struct DEVICE_COLLECTION **a1,
        __int64 a2,
        unsigned __int16 *a3,
        __int64 a4,
        unsigned __int16 *a5)
{
  struct DEVICE_COLLECTION *v5; // rax
  int v6; // edx
  __int64 result; // rax
  const WCHAR *v9; // rbx
  SC_HANDLE v10; // rax
  SC_HANDLE v11; // rsi
  __int64 v12; // rdi
  __int64 v13; // rax
  WCHAR *v14; // rcx
  WCHAR *v15; // rdx
  DWORD cchBuffer[4]; // [rsp+20h] [rbp-258h] BYREF
  WCHAR DisplayName[256]; // [rsp+30h] [rbp-248h] BYREF

  v5 = *a1;
  v6 = 0;
  cchBuffer[0] = 0;
  while ( 1 )
  {
    if ( v5 == (struct DEVICE_COLLECTION *)a1 )
    {
      *a5 = 0;
      return 0;
    }
    if ( v6 == 1 )
      break;
    v5 = *(struct DEVICE_COLLECTION **)v5;
    ++v6;
  }
  v9 = (const WCHAR *)((char *)v5 + 16);
  DisplayName[0] = 0;
  if ( v5 != (struct DEVICE_COLLECTION *)-16LL )
  {
    v10 = OpenSCManagerW(0, L"ServicesActive", 0x80000000);
    v11 = v10;
    v12 = 256;
    if ( v10 )
    {
      cchBuffer[0] = 256;
      if ( !GetServiceDisplayNameW(v10, v9, DisplayName, cchBuffer) )
        DisplayName[0] = 0;
      CloseServiceHandle(v11);
    }
    if ( !DisplayName[0] )
    {
      v13 = 2147483646;
      v14 = DisplayName;
      do
      {
        if ( !v13 )
          break;
        if ( !*v9 )
          break;
        *v14++ = *v9++;
        --v13;
        --v12;
      }
      while ( v12 );
      v15 = v14 - 1;
      if ( v12 )
        v15 = v14;
      *v15 = 0;
    }
  }
  StringCchPrintfW(a5, 0x200u, a3, DisplayName, *(_QWORD *)cchBuffer);
  result = 1;
  a5[511] = 0;
  return result;
}

```

## disassembly

```asm
0x180002e58  push    rbx
0x180002e5a  push    rbp
0x180002e5b  push    rsi
0x180002e5c  push    rdi
0x180002e5d  push    r14
0x180002e5f  push    r15
0x180002e61  sub     rsp, 248h
0x180002e68  mov     rax, cs:__security_cookie
0x180002e6f  xor     rax, rsp
0x180002e72  mov     [rsp+278h+var_48], rax
0x180002e7a  mov     r14, [rsp+278h+arg_20]
0x180002e82  xor     r15d, r15d
0x180002e85  mov     rax, [rcx]
0x180002e88  mov     edx, r15d
0x180002e8b  mov     [rsp+278h+cchBuffer], r15d
0x180002e90  mov     rbp, r8
0x180002e93  jmp     short loc_180002E9F
0x180002e95  cmp     edx, 1
0x180002e98  jz      short loc_180002ECA
0x180002e9a  mov     rax, [rax]
0x180002e9d  inc     edx
0x180002e9f  cmp     rax, rcx
0x180002ea2  jnz     short loc_180002E95
0x180002ea4  mov     [r14], r15w
0x180002ea8  xor     eax, eax
0x180002eaa  mov     rcx, [rsp+278h+var_48]
0x180002eb2  xor     rcx, rsp; StackCookie
0x180002eb5  call    __security_check_cookie
0x180002eba  add     rsp, 248h
0x180002ec1  pop     r15
0x180002ec3  pop     r14
0x180002ec5  pop     rdi
0x180002ec6  pop     rsi
0x180002ec7  pop     rbp
0x180002ec8  pop     rbx
0x180002ec9  retn
0x180002eca  lea     rbx, [rax+10h]
0x180002ece  mov     [rsp+278h+DisplayName], r15w
0x180002ed4  test    rbx, rbx
0x180002ed7  jz      loc_180002F6E
0x180002edd  mov     r8d, 80000000h; dwDesiredAccess
0x180002ee3  lea     rdx, DatabaseName; "ServicesActive"
0x180002eea  xor     ecx, ecx; lpMachineName
0x180002eec  call    cs:__imp_OpenSCManagerW
0x180002ef2  mov     rsi, rax
0x180002ef5  mov     edi, 100h
0x180002efa  test    rax, rax
0x180002efd  jz      short loc_180002F2C
0x180002eff  lea     r9, [rsp+278h+cchBuffer]; lpcchBuffer
0x180002f04  mov     [rsp+278h+cchBuffer], edi
0x180002f08  lea     r8, [rsp+278h+DisplayName]; lpDisplayName
0x180002f0d  mov     rdx, rbx; lpServiceName
0x180002f10  mov     rcx, rax; hSCManager
0x180002f13  call    cs:__imp_GetServiceDisplayNameW
0x180002f19  test    eax, eax
0x180002f1b  jnz     short loc_180002F23
0x180002f1d  mov     [rsp+278h+DisplayName], r15w
0x180002f23  mov     rcx, rsi; hSCObject
0x180002f26  call    cs:__imp_CloseServiceHandle
0x180002f2c  cmp     [rsp+278h+DisplayName], r15w
0x180002f32  jnz     short loc_180002F6E
0x180002f34  mov     eax, 7FFFFFFEh
0x180002f39  lea     rcx, [rsp+278h+DisplayName]
0x180002f3e  test    rax, rax
0x180002f41  jz      short loc_180002F5F
0x180002f43  movzx   edx, word ptr [rbx]
0x180002f46  test    dx, dx
0x180002f49  jz      short loc_180002F5F
0x180002f4b  mov     [rcx], dx
0x180002f4e  add     rbx, 2
0x180002f52  add     rcx, 2
0x180002f56  dec     rax
0x180002f59  sub     rdi, 1
0x180002f5d  jnz     short loc_180002F3E
0x180002f5f  test    rdi, rdi
0x180002f62  lea     rdx, [rcx-2]
0x180002f66  cmovnz  rdx, rcx
0x180002f6a  mov     [rdx], r15w
0x180002f6e  lea     r9, [rsp+278h+DisplayName]
0x180002f73  mov     r8, rbp; unsigned __int16 *
0x180002f76  mov     edx, 200h; unsigned __int64
0x180002f7b  mov     rcx, r14; unsigned __int16 *
0x180002f7e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002f83  mov     eax, 1
0x180002f88  mov     [r14+3FEh], r15w
0x180002f90  jmp     loc_180002EAA
```
