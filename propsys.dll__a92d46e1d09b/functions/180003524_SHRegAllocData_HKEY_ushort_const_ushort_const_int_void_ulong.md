# SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)

- ea: `0x180003524`
- end: `0x180003691`
- name: `?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z`
- size: `365`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, int, void **, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800032fc`
- `0x180003434`

## callees

- `0x180003524`
- `0x18006ed20`
- `0x18006fb80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000357a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000357a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800035c3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180003624`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800035c3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180003624`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003651`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003651`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000363b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000363b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800035da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800035da`

## pseudocode

```c
__int64 __fastcall SHRegAllocData(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        void **a5)
{
  int v5; // esi
  LSTATUS v6; // eax
  int v7; // ebx
  LSTATUS ValueW; // eax
  void *pvData; // rax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE Src[256]; // [rsp+50h] [rbp-B0h] BYREF

  hkey = a1;
  if ( a2 && *a2 )
  {
    v5 = 1;
    v6 = RegOpenKeyExW(a1, a2, 0, 1u, &hkey);
    a1 = hkey;
    v7 = v6;
  }
  else
  {
    v7 = 0;
    v5 = 0;
  }
  if ( v7 )
    goto LABEL_18;
  pcbData = 256;
  ValueW = RegGetValueW(a1, 0, 0, 0x10000006u, 0, Src, &pcbData);
  v7 = ValueW;
  if ( !ValueW || ValueW == 234 )
  {
    pvData = CoTaskMemAlloc(pcbData);
    *a5 = pvData;
    if ( pvData )
    {
      if ( v7 )
      {
        if ( RegGetValueW(hkey, 0, 0, 0x10000006u, 0, pvData, &pcbData) )
        {
          v7 = 1003;
          CoTaskMemFree(*a5);
        }
        else
        {
          v7 = 0;
        }
      }
      else
      {
        memcpy_0(pvData, Src, pcbData);
      }
    }
    else
    {
      v7 = 14;
    }
  }
  if ( v5 )
    RegCloseKey(hkey);
  if ( v7 )
  {
LABEL_18:
    *a5 = 0;
    if ( v7 > 0 )
      return (unsigned __int16)v7 | 0x80070000;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180003524  mov     [rsp-8+arg_10], rbx
0x180003529  mov     [rsp-8+arg_18], rsi
0x18000352e  push    rbp
0x18000352f  push    rdi
0x180003530  push    r14
0x180003532  lea     rbp, [rsp-60h]
0x180003537  sub     rsp, 160h
0x18000353e  mov     rax, cs:__security_cookie
0x180003545  xor     rax, rsp
0x180003548  mov     [rbp+70h+var_20], rax
0x18000354c  mov     rdi, [rbp+70h+arg_20]
0x180003553  xor     r14d, r14d
0x180003556  mov     [rsp+170h+hkey], rcx
0x18000355b  test    rdx, rdx
0x18000355e  jz      short loc_180003589
0x180003560  cmp     [rdx], r14w
0x180003564  jz      short loc_180003589
0x180003566  lea     rax, [rsp+170h+hkey]
0x18000356b  xor     r8d, r8d; ulOptions
0x18000356e  lea     esi, [r14+1]
0x180003572  mov     [rsp+170h+phkResult], rax; phkResult
0x180003577  mov     r9d, esi; samDesired
0x18000357a  call    cs:__imp_RegOpenKeyExW
0x180003580  mov     rcx, [rsp+170h+hkey]; hkey
0x180003585  mov     ebx, eax
0x180003587  jmp     short loc_18000358F
0x180003589  mov     ebx, r14d
0x18000358c  mov     esi, r14d
0x18000358f  test    ebx, ebx
0x180003591  jnz     loc_18000365B
0x180003597  lea     rax, [rsp+170h+var_130]
0x18000359c  mov     [rsp+170h+var_130], 100h
0x1800035a4  mov     [rsp+170h+pcbData], rax; pcbData
0x1800035a9  mov     r9d, 10000006h; dwFlags
0x1800035af  lea     rax, [rsp+170h+Src]
0x1800035b4  xor     r8d, r8d; lpValue
0x1800035b7  mov     [rsp+170h+pvData], rax; pvData
0x1800035bc  xor     edx, edx; lpSubKey
0x1800035be  mov     [rsp+170h+phkResult], r14; pdwType
0x1800035c3  call    cs:__imp_RegGetValueW
0x1800035c9  mov     ebx, eax
0x1800035cb  test    eax, eax
0x1800035cd  jz      short loc_1800035D6
0x1800035cf  cmp     eax, 0EAh
0x1800035d4  jnz     short loc_180003648
0x1800035d6  mov     ecx, [rsp+170h+var_130]; cb
0x1800035da  call    cs:__imp_CoTaskMemAlloc
0x1800035e0  mov     [rdi], rax
0x1800035e3  test    rax, rax
0x1800035e6  jz      short loc_180003643
0x1800035e8  test    ebx, ebx
0x1800035ea  jnz     short loc_180003600
0x1800035ec  mov     r8d, [rsp+170h+var_130]; Size
0x1800035f1  lea     rdx, [rsp+170h+Src]; Src
0x1800035f6  mov     rcx, rax; void *
0x1800035f9  call    memcpy_0
0x1800035fe  jmp     short loc_180003648
0x180003600  lea     rcx, [rsp+170h+var_130]
0x180003605  mov     r9d, 10000006h; dwFlags
0x18000360b  mov     [rsp+170h+pcbData], rcx; pcbData
0x180003610  xor     r8d, r8d; lpValue
0x180003613  mov     rcx, [rsp+170h+hkey]; hkey
0x180003618  xor     edx, edx; lpSubKey
0x18000361a  mov     [rsp+170h+pvData], rax; pvData
0x18000361f  mov     [rsp+170h+phkResult], r14; pdwType
0x180003624  call    cs:__imp_RegGetValueW
0x18000362a  test    eax, eax
0x18000362c  jnz     short loc_180003633
0x18000362e  mov     ebx, r14d
0x180003631  jmp     short loc_180003648
0x180003633  mov     rcx, [rdi]; pv
0x180003636  mov     ebx, 3EBh
0x18000363b  call    cs:__imp_CoTaskMemFree
0x180003641  jmp     short loc_180003648
0x180003643  mov     ebx, 0Eh
0x180003648  test    esi, esi
0x18000364a  jz      short loc_180003657
0x18000364c  mov     rcx, [rsp+170h+hkey]; hKey
0x180003651  call    cs:__imp_RegCloseKey
0x180003657  test    ebx, ebx
0x180003659  jz      short loc_18000366B
0x18000365b  mov     [rdi], r14
0x18000365e  test    ebx, ebx
0x180003660  jle     short loc_18000366B
0x180003662  movzx   ebx, bx
0x180003665  or      ebx, 80070000h
0x18000366b  mov     eax, ebx
0x18000366d  mov     rcx, [rbp+70h+var_20]
0x180003671  xor     rcx, rsp; StackCookie
0x180003674  call    __security_check_cookie
0x180003679  lea     r11, [rsp+170h+var_10]
0x180003681  mov     rbx, [r11+30h]
0x180003685  mov     rsi, [r11+38h]
0x180003689  mov     rsp, r11
0x18000368c  pop     r14
0x18000368e  pop     rdi
0x18000368f  pop     rbp
0x180003690  retn
```
