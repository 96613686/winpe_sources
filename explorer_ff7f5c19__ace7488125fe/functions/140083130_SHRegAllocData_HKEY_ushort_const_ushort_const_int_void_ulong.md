# SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)

- ea: `0x140083130`
- end: `0x1400832c7`
- name: `?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z`
- size: `407`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, int, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400a26f8`

## callees

- `0x140083130`
- `0x14010e160`
- `0x14010ed78`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140083191`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140083191`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140083288`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140083288`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400831de`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14008324f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400831de`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14008324f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14008326c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14008326c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400831ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400831ff`

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
  if ( aSoftwareMicros_123[0] )
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
0x140083130  push    rbp
0x140083132  push    rbx
0x140083133  push    rsi
0x140083134  push    rdi
0x140083135  push    r14
0x140083137  push    r15
0x140083139  lea     rbp, [rsp-68h]
0x14008313e  sub     rsp, 168h
0x140083145  mov     rax, cs:__security_cookie
0x14008314c  xor     rax, rsp
0x14008314f  mov     [rbp+90h+var_40], rax
0x140083153  mov     rdi, [rbp+90h+arg_20]
0x14008315a  xor     r15d, r15d
0x14008315d  cmp     word ptr cs:aSoftwareMicros_123, r15w; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x140083165  mov     rcx, 0FFFFFFFF80000001h; hkey
0x14008316c  mov     r14, r8
0x14008316f  mov     [rsp+190h+hkey], rcx
0x140083174  jz      short loc_1400831A6
0x140083176  lea     rax, [rsp+190h+hkey]
0x14008317b  xor     r8d, r8d; ulOptions
0x14008317e  lea     esi, [r15+1]
0x140083182  mov     [rsp+190h+phkResult], rax; phkResult
0x140083187  mov     r9d, esi; samDesired
0x14008318a  lea     rdx, aSoftwareMicros_123; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x140083191  call    cs:__imp_RegOpenKeyExW
0x140083198  nop     dword ptr [rax+rax+00h]
0x14008319d  mov     rcx, [rsp+190h+hkey]
0x1400831a2  mov     ebx, eax
0x1400831a4  jmp     short loc_1400831AC
0x1400831a6  mov     ebx, r15d
0x1400831a9  mov     esi, r15d
0x1400831ac  test    ebx, ebx
0x1400831ae  jnz     loc_140083298
0x1400831b4  lea     rax, [rsp+190h+var_150]
0x1400831b9  mov     [rsp+190h+var_150], 100h
0x1400831c1  mov     [rsp+190h+pcbData], rax; pcbData
0x1400831c6  lea     r9d, [rbx+2]; dwFlags
0x1400831ca  lea     rax, [rsp+190h+Src]
0x1400831cf  mov     r8, r14; lpValue
0x1400831d2  mov     [rsp+190h+pvData], rax; pvData
0x1400831d7  xor     edx, edx; lpSubKey
0x1400831d9  mov     [rsp+190h+phkResult], r15; pdwType
0x1400831de  call    cs:__imp_RegGetValueW
0x1400831e5  nop     dword ptr [rax+rax+00h]
0x1400831ea  mov     ebx, eax
0x1400831ec  test    eax, eax
0x1400831ee  jz      short loc_1400831FB
0x1400831f0  cmp     eax, 0EAh
0x1400831f5  jnz     loc_14008327F
0x1400831fb  mov     ecx, [rsp+190h+var_150]; cb
0x1400831ff  call    cs:__imp_CoTaskMemAlloc
0x140083206  nop     dword ptr [rax+rax+00h]
0x14008320b  mov     [rdi], rax
0x14008320e  test    rax, rax
0x140083211  jz      short loc_14008327A
0x140083213  test    ebx, ebx
0x140083215  jnz     short loc_14008322B
0x140083217  mov     r8d, [rsp+190h+var_150]; Size
0x14008321c  lea     rdx, [rsp+190h+Src]; Src
0x140083221  mov     rcx, rax; void *
0x140083224  call    memcpy_0
0x140083229  jmp     short loc_14008327F
0x14008322b  lea     rcx, [rsp+190h+var_150]
0x140083230  mov     r9d, 2; dwFlags
0x140083236  mov     [rsp+190h+pcbData], rcx; pcbData
0x14008323b  mov     r8, r14; lpValue
0x14008323e  mov     rcx, [rsp+190h+hkey]; hkey
0x140083243  xor     edx, edx; lpSubKey
0x140083245  mov     [rsp+190h+pvData], rax; pvData
0x14008324a  mov     [rsp+190h+phkResult], r15; pdwType
0x14008324f  call    cs:__imp_RegGetValueW
0x140083256  nop     dword ptr [rax+rax+00h]
0x14008325b  test    eax, eax
0x14008325d  jnz     short loc_140083264
0x14008325f  mov     ebx, r15d
0x140083262  jmp     short loc_14008327F
0x140083264  mov     rcx, [rdi]; pv
0x140083267  mov     ebx, 3EBh
0x14008326c  call    cs:__imp_CoTaskMemFree
0x140083273  nop     dword ptr [rax+rax+00h]
0x140083278  jmp     short loc_14008327F
0x14008327a  mov     ebx, 0Eh
0x14008327f  test    esi, esi
0x140083281  jz      short loc_140083294
0x140083283  mov     rcx, [rsp+190h+hkey]; hKey
0x140083288  call    cs:__imp_RegCloseKey
0x14008328f  nop     dword ptr [rax+rax+00h]
0x140083294  test    ebx, ebx
0x140083296  jz      short loc_1400832A8
0x140083298  mov     [rdi], r15
0x14008329b  test    ebx, ebx
0x14008329d  jle     short loc_1400832A8
0x14008329f  movzx   ebx, bx
0x1400832a2  or      ebx, 80070000h
0x1400832a8  mov     eax, ebx
0x1400832aa  mov     rcx, [rbp+90h+var_40]
0x1400832ae  xor     rcx, rsp; StackCookie
0x1400832b1  call    __security_check_cookie
0x1400832b6  add     rsp, 168h
0x1400832bd  pop     r15
0x1400832bf  pop     r14
0x1400832c1  pop     rdi
0x1400832c2  pop     rsi
0x1400832c3  pop     rbx
0x1400832c4  pop     rbp
0x1400832c5  retn
```
