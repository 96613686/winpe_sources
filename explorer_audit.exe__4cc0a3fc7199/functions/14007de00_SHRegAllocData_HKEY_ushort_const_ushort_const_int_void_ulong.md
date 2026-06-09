# SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)

- ea: `0x14007de00`
- end: `0x14007df6e`
- name: `?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z`
- size: `366`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, int, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14009f398`

## callees

- `0x14007de00`
- `0x1401040e0`
- `0x140104cc8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14007df36`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14007df36`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14007de61`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14007de61`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14007dea8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14007df09`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14007dea8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14007df09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14007df20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14007df20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14007debf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14007debf`

## pseudocode

```c
__int64 __fastcall SHRegAllocData(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        void **a5)
{
  HKEY v5; // rcx
  int v7; // esi
  LSTATUS v8; // eax
  int v9; // ebx
  LSTATUS ValueW; // eax
  void *pvData; // rax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE Src[256]; // [rsp+50h] [rbp-B0h] BYREF

  v5 = HKEY_CURRENT_USER;
  hkey = HKEY_CURRENT_USER;
  if ( aSoftwareMicros_122[0] )
  {
    v7 = 1;
    v8 = RegOpenKeyExW(
           HKEY_CURRENT_USER,
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\UserLogonTracing",
           0,
           1u,
           &hkey);
    v5 = hkey;
    v9 = v8;
  }
  else
  {
    v9 = 0;
    v7 = 0;
  }
  if ( v9 )
    goto LABEL_17;
  pcbData = 256;
  ValueW = RegGetValueW(v5, 0, a3, 2u, 0, Src, &pcbData);
  v9 = ValueW;
  if ( !ValueW || ValueW == 234 )
  {
    pvData = CoTaskMemAlloc(pcbData);
    *a5 = pvData;
    if ( pvData )
    {
      if ( v9 )
      {
        if ( RegGetValueW(hkey, 0, a3, 2u, 0, pvData, &pcbData) )
        {
          v9 = 1003;
          CoTaskMemFree(*a5);
        }
        else
        {
          v9 = 0;
        }
      }
      else
      {
        memcpy_0(pvData, Src, pcbData);
      }
    }
    else
    {
      v9 = 14;
    }
  }
  if ( v7 )
    RegCloseKey(hkey);
  if ( v9 )
  {
LABEL_17:
    *a5 = 0;
    if ( v9 > 0 )
      return (unsigned __int16)v9 | 0x80070000;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14007de00  push    rbp
0x14007de02  push    rbx
0x14007de03  push    rsi
0x14007de04  push    rdi
0x14007de05  push    r14
0x14007de07  push    r15
0x14007de09  lea     rbp, [rsp-68h]
0x14007de0e  sub     rsp, 168h
0x14007de15  mov     rax, cs:__security_cookie
0x14007de1c  xor     rax, rsp
0x14007de1f  mov     [rbp+90h+var_40], rax
0x14007de23  mov     rdi, [rbp+90h+arg_20]
0x14007de2a  xor     r15d, r15d
0x14007de2d  cmp     word ptr cs:aSoftwareMicros_122, r15w; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14007de35  mov     rcx, 0FFFFFFFF80000001h; hkey
0x14007de3c  mov     r14, r8
0x14007de3f  mov     [rsp+190h+hkey], rcx
0x14007de44  jz      short loc_14007DE70
0x14007de46  lea     rax, [rsp+190h+hkey]
0x14007de4b  xor     r8d, r8d; ulOptions
0x14007de4e  lea     esi, [r15+1]
0x14007de52  mov     [rsp+190h+phkResult], rax; phkResult
0x14007de57  mov     r9d, esi; samDesired
0x14007de5a  lea     rdx, aSoftwareMicros_122; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14007de61  call    cs:__imp_RegOpenKeyExW
0x14007de67  mov     rcx, [rsp+190h+hkey]
0x14007de6c  mov     ebx, eax
0x14007de6e  jmp     short loc_14007DE76
0x14007de70  mov     ebx, r15d
0x14007de73  mov     esi, r15d
0x14007de76  test    ebx, ebx
0x14007de78  jnz     loc_14007DF40
0x14007de7e  lea     rax, [rsp+190h+var_150]
0x14007de83  mov     [rsp+190h+var_150], 100h
0x14007de8b  mov     [rsp+190h+pcbData], rax; pcbData
0x14007de90  lea     r9d, [rbx+2]; dwFlags
0x14007de94  lea     rax, [rsp+190h+Src]
0x14007de99  mov     r8, r14; lpValue
0x14007de9c  mov     [rsp+190h+pvData], rax; pvData
0x14007dea1  xor     edx, edx; lpSubKey
0x14007dea3  mov     [rsp+190h+phkResult], r15; pdwType
0x14007dea8  call    cs:__imp_RegGetValueW
0x14007deae  mov     ebx, eax
0x14007deb0  test    eax, eax
0x14007deb2  jz      short loc_14007DEBB
0x14007deb4  cmp     eax, 0EAh
0x14007deb9  jnz     short loc_14007DF2D
0x14007debb  mov     ecx, [rsp+190h+var_150]; cb
0x14007debf  call    cs:__imp_CoTaskMemAlloc
0x14007dec5  mov     [rdi], rax
0x14007dec8  test    rax, rax
0x14007decb  jz      short loc_14007DF28
0x14007decd  test    ebx, ebx
0x14007decf  jnz     short loc_14007DEE5
0x14007ded1  mov     r8d, [rsp+190h+var_150]; Size
0x14007ded6  lea     rdx, [rsp+190h+Src]; Src
0x14007dedb  mov     rcx, rax; void *
0x14007dede  call    memcpy_0
0x14007dee3  jmp     short loc_14007DF2D
0x14007dee5  lea     rcx, [rsp+190h+var_150]
0x14007deea  mov     r9d, 2; dwFlags
0x14007def0  mov     [rsp+190h+pcbData], rcx; pcbData
0x14007def5  mov     r8, r14; lpValue
0x14007def8  mov     rcx, [rsp+190h+hkey]; hkey
0x14007defd  xor     edx, edx; lpSubKey
0x14007deff  mov     [rsp+190h+pvData], rax; pvData
0x14007df04  mov     [rsp+190h+phkResult], r15; pdwType
0x14007df09  call    cs:__imp_RegGetValueW
0x14007df0f  test    eax, eax
0x14007df11  jnz     short loc_14007DF18
0x14007df13  mov     ebx, r15d
0x14007df16  jmp     short loc_14007DF2D
0x14007df18  mov     rcx, [rdi]; pv
0x14007df1b  mov     ebx, 3EBh
0x14007df20  call    cs:__imp_CoTaskMemFree
0x14007df26  jmp     short loc_14007DF2D
0x14007df28  mov     ebx, 0Eh
0x14007df2d  test    esi, esi
0x14007df2f  jz      short loc_14007DF3C
0x14007df31  mov     rcx, [rsp+190h+hkey]; hKey
0x14007df36  call    cs:__imp_RegCloseKey
0x14007df3c  test    ebx, ebx
0x14007df3e  jz      short loc_14007DF50
0x14007df40  mov     [rdi], r15
0x14007df43  test    ebx, ebx
0x14007df45  jle     short loc_14007DF50
0x14007df47  movzx   ebx, bx
0x14007df4a  or      ebx, 80070000h
0x14007df50  mov     eax, ebx
0x14007df52  mov     rcx, [rbp+90h+var_40]
0x14007df56  xor     rcx, rsp; StackCookie
0x14007df59  call    __security_check_cookie
0x14007df5e  add     rsp, 168h
0x14007df65  pop     r15
0x14007df67  pop     r14
0x14007df69  pop     rdi
0x14007df6a  pop     rsi
0x14007df6b  pop     rbx
0x14007df6c  pop     rbp
0x14007df6d  retn
```
