# SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)

- ea: `0x180021988`
- end: `0x180021b1a`
- name: `?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z`
- size: `402`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, DWORD, void **, unsigned int *)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180022b9c`
- `0x1800301a0`
- `0x18004e110`
- `0x18004f2b0`
- `0x1800a15b8`

## callees

- `0x180003470`
- `0x180005d8d`
- `0x180021988`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021ad6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021ad6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800219ea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800219ea`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180021a30`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180021a9d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180021a30`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180021a9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021a4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021a4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021abf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021abf`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall SHRegAllocData(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        DWORD a4,
        void **a5,
        unsigned int *a6)
{
  int v8; // r14d
  LSTATUS v9; // eax
  int v10; // ebx
  LSTATUS ValueW; // eax
  void *pvData; // rax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE Src[256]; // [rsp+50h] [rbp-B0h] BYREF

  hkey = a1;
  if ( a2 && *a2 )
  {
    v8 = 1;
    v9 = RegOpenKeyExW(a1, a2, 0, 1u, &hkey);
    a1 = hkey;
    v10 = v9;
  }
  else
  {
    v10 = 0;
    v8 = 0;
  }
  if ( v10 )
    goto LABEL_21;
  pcbData = 256;
  ValueW = RegGetValueW(a1, 0, a3, a4, 0, Src, &pcbData);
  v10 = ValueW;
  if ( !ValueW || ValueW == 234 )
  {
    pvData = CoTaskMemAlloc(pcbData);
    *a5 = pvData;
    if ( pvData )
    {
      if ( v10 )
      {
        if ( RegGetValueW(hkey, 0, a3, a4, 0, pvData, &pcbData) )
        {
          v10 = 1003;
          CoTaskMemFree(*a5);
        }
        else
        {
          if ( a6 )
            *a6 = pcbData;
          v10 = 0;
        }
      }
      else
      {
        memcpy_0(pvData, Src, pcbData);
        if ( a6 )
          *a6 = pcbData;
      }
    }
    else
    {
      v10 = 14;
    }
  }
  if ( v8 )
    RegCloseKey(hkey);
  if ( v10 )
  {
LABEL_21:
    *a5 = 0;
    if ( a6 )
      *a6 = 0;
    if ( v10 > 0 )
      return (unsigned __int16)v10 | 0x80070000;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180021988  push    rbp
0x18002198a  push    rbx
0x18002198b  push    rsi
0x18002198c  push    rdi
0x18002198d  push    r12
0x18002198f  push    r13
0x180021991  push    r14
0x180021993  push    r15
0x180021995  lea     rbp, [rsp-68h]
0x18002199a  sub     rsp, 168h
0x1800219a1  mov     rax, cs:__security_cookie
0x1800219a8  xor     rax, rsp
0x1800219ab  mov     [rbp+0A0h+var_50], rax
0x1800219af  mov     rsi, [rbp+0A0h+arg_20]
0x1800219b6  xor     r13d, r13d
0x1800219b9  mov     rdi, [rbp+0A0h+arg_28]
0x1800219c0  mov     r12d, r9d
0x1800219c3  mov     [rsp+1A0h+hkey], rcx
0x1800219c8  mov     r15, r8
0x1800219cb  test    rdx, rdx
0x1800219ce  jz      short loc_1800219F9
0x1800219d0  cmp     [rdx], r13w
0x1800219d4  jz      short loc_1800219F9
0x1800219d6  lea     rax, [rsp+1A0h+hkey]
0x1800219db  xor     r8d, r8d; ulOptions
0x1800219de  lea     r14d, [r13+1]
0x1800219e2  mov     [rsp+1A0h+phkResult], rax; phkResult
0x1800219e7  mov     r9d, r14d; samDesired
0x1800219ea  call    cs:__imp_RegOpenKeyExW
0x1800219f0  mov     rcx, [rsp+1A0h+hkey]; hkey
0x1800219f5  mov     ebx, eax
0x1800219f7  jmp     short loc_1800219FF
0x1800219f9  mov     ebx, r13d
0x1800219fc  mov     r14d, r13d
0x1800219ff  test    ebx, ebx
0x180021a01  jnz     loc_180021AE0
0x180021a07  lea     rax, [rsp+1A0h+var_160]
0x180021a0c  mov     [rsp+1A0h+var_160], 100h
0x180021a14  mov     [rsp+1A0h+pcbData], rax; pcbData
0x180021a19  mov     r9d, r12d; dwFlags
0x180021a1c  lea     rax, [rsp+1A0h+Src]
0x180021a21  mov     r8, r15; lpValue
0x180021a24  mov     [rsp+1A0h+pvData], rax; pvData
0x180021a29  xor     edx, edx; lpSubKey
0x180021a2b  mov     [rsp+1A0h+phkResult], r13; pdwType
0x180021a30  call    cs:__imp_RegGetValueW
0x180021a36  mov     ebx, eax
0x180021a38  test    eax, eax
0x180021a3a  jz      short loc_180021A47
0x180021a3c  cmp     eax, 0EAh
0x180021a41  jnz     loc_180021ACC
0x180021a47  mov     ecx, [rsp+1A0h+var_160]; cb
0x180021a4b  call    cs:__imp_CoTaskMemAlloc
0x180021a51  mov     [rsi], rax
0x180021a54  test    rax, rax
0x180021a57  jz      short loc_180021AC7
0x180021a59  test    ebx, ebx
0x180021a5b  jnz     short loc_180021A7C
0x180021a5d  mov     r8d, [rsp+1A0h+var_160]; Size
0x180021a62  lea     rdx, [rsp+1A0h+Src]; Src
0x180021a67  mov     rcx, rax; void *
0x180021a6a  call    memcpy_0
0x180021a6f  test    rdi, rdi
0x180021a72  jz      short loc_180021ACC
0x180021a74  mov     eax, [rsp+1A0h+var_160]
0x180021a78  mov     [rdi], eax
0x180021a7a  jmp     short loc_180021ACC
0x180021a7c  lea     rcx, [rsp+1A0h+var_160]
0x180021a81  mov     r9d, r12d; dwFlags
0x180021a84  mov     [rsp+1A0h+pcbData], rcx; pcbData
0x180021a89  mov     r8, r15; lpValue
0x180021a8c  mov     rcx, [rsp+1A0h+hkey]; hkey
0x180021a91  xor     edx, edx; lpSubKey
0x180021a93  mov     [rsp+1A0h+pvData], rax; pvData
0x180021a98  mov     [rsp+1A0h+phkResult], r13; pdwType
0x180021a9d  call    cs:__imp_RegGetValueW
0x180021aa3  test    eax, eax
0x180021aa5  jnz     short loc_180021AB7
0x180021aa7  test    rdi, rdi
0x180021aaa  jz      short loc_180021AB2
0x180021aac  mov     eax, [rsp+1A0h+var_160]
0x180021ab0  mov     [rdi], eax
0x180021ab2  mov     ebx, r13d
0x180021ab5  jmp     short loc_180021ACC
0x180021ab7  mov     rcx, [rsi]; pv
0x180021aba  mov     ebx, 3EBh
0x180021abf  call    cs:__imp_CoTaskMemFree
0x180021ac5  jmp     short loc_180021ACC
0x180021ac7  mov     ebx, 0Eh
0x180021acc  test    r14d, r14d
0x180021acf  jz      short loc_180021ADC
0x180021ad1  mov     rcx, [rsp+1A0h+hkey]; hKey
0x180021ad6  call    cs:__imp_RegCloseKey
0x180021adc  test    ebx, ebx
0x180021ade  jz      short loc_180021AF8
0x180021ae0  mov     [rsi], r13
0x180021ae3  test    rdi, rdi
0x180021ae6  jz      short loc_180021AEB
0x180021ae8  mov     [rdi], r13d
0x180021aeb  test    ebx, ebx
0x180021aed  jle     short loc_180021AF8
0x180021aef  movzx   ebx, bx
0x180021af2  or      ebx, 80070000h
0x180021af8  mov     eax, ebx
0x180021afa  mov     rcx, [rbp+0A0h+var_50]
0x180021afe  xor     rcx, rsp; StackCookie
0x180021b01  call    __security_check_cookie
0x180021b06  add     rsp, 168h
0x180021b0d  pop     r15
0x180021b0f  pop     r14
0x180021b11  pop     r13
0x180021b13  pop     r12
0x180021b15  pop     rdi
0x180021b16  pop     rsi
0x180021b17  pop     rbx
0x180021b18  pop     rbp
0x180021b19  retn
```
