# CRegistryKeyCache::OpenRegKey(ushort const *,int,ulong,HKEY__ * &)

- ea: `0x180036344`
- end: `0x18003649b`
- name: `?OpenRegKey@CRegistryKeyCache@@QEAAJPEBGHKAEAPEAUHKEY__@@@Z`
- size: `343`
- prototype: `int(CRegistryKeyCache *__hidden this, const unsigned __int16 *, int, unsigned int, HKEY *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800364a4`
- `0x180036a60`

## callees

- `0x180023834`
- `0x180036344`
- `0x180036ec0`
- `0x180036fec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800363f6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800363f6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800363c7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800363c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003645f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003645f`

## pseudocode

```c
__int64 __fastcall CRegistryKeyCache::OpenRegKey(
        CRegistryKeyCache *this,
        const unsigned __int16 *a2,
        int a3,
        REGSAM a4,
        HKEY *phkResult)
{
  char *v5; // r14
  int v10; // ebx
  HKEY *v11; // rdi
  HKEY v12; // rcx
  LSTATUS v13; // eax
  __int64 v14; // rcx
  _QWORD v16[2]; // [rsp+50h] [rbp-10h] BYREF
  DWORD dwDisposition; // [rsp+90h] [rbp+30h] BYREF
  const unsigned __int16 *v18; // [rsp+98h] [rbp+38h] BYREF

  v18 = a2;
  v5 = (char *)this + 16;
  dwDisposition = 0;
  v16[0] = 0;
  if ( (unsigned int)Map<unsigned short const *,MyDataEntry *,HashWSTR,EmptyMapBase>::find((char *)this + 16, &v18, v16) )
  {
    v10 = 0;
    *phkResult = *(HKEY *)(*(_QWORD *)v16[0] + 40LL);
LABEL_16:
    ++*((_DWORD *)this + 2);
    return (unsigned int)v10;
  }
  v11 = phkResult;
  v12 = *(HKEY *)this;
  if ( a3 )
    v13 = RegCreateKeyExW(v12, a2, 0, 0, 0, a4, 0, phkResult, &dwDisposition);
  else
    v13 = RegOpenKeyExW(v12, a2, 0, a4, phkResult);
  v10 = v13;
  if ( v13 )
  {
    if ( v13 > 0 )
      v10 = (unsigned __int16)v13 | 0x80070000;
    if ( v10 >= 0 )
      goto LABEL_16;
  }
  else
  {
    v10 = Map<unsigned short const *,HKEY__ *,HashWSTR,EmptyMapBase>::allocAssocIfNecessary((__int64)v5);
    if ( v10 >= 0 )
    {
      v16[0] = 0;
      if ( (unsigned int)Map<unsigned short const *,MyDataEntry *,HashWSTR,EmptyMapBase>::find(v5, &v18, v16) )
      {
        v14 = v16[0];
        *(_QWORD *)(*(_QWORD *)v16[0] + 32LL) = a2;
        *(_QWORD *)(*(_QWORD *)v14 + 40LL) = *v11;
        goto LABEL_16;
      }
      v10 = Map<unsigned short const *,MyDataEntry *,HashWSTR,EmptyMapBase>::newAssoc(v5, &v18, v11, v16[0]);
    }
    if ( v10 >= 0 )
      goto LABEL_16;
    RegCloseKey(*v11);
    *v11 = 0;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180036344  mov     [rsp-28h+arg_10], rbx
0x180036349  mov     [rsp-28h+arg_18], rsi
0x18003634e  mov     [rsp-28h+arg_8], rdx
0x180036353  push    rbp
0x180036354  push    rdi
0x180036355  push    r12
0x180036357  push    r14
0x180036359  push    r15
0x18003635b  mov     rbp, rsp
0x18003635e  sub     rsp, 60h
0x180036362  lea     r14, [rcx+10h]
0x180036366  mov     [rbp+dwDisposition], 0
0x18003636d  mov     ebx, r8d
0x180036370  mov     [rbp+var_10], 0
0x180036378  mov     r15, rdx
0x18003637b  lea     r8, [rbp+var_10]
0x18003637f  mov     rsi, rcx
0x180036382  lea     rdx, [rbp+arg_8]
0x180036386  mov     rcx, r14
0x180036389  mov     r12d, r9d
0x18003638c  call    ?find@?$Map@PEBGPEAUMyDataEntry@@VHashWSTR@@VEmptyMapBase@@@@AEBAHAEBQEBGPEAPEAPEAVAssoc@1@@Z; Map<ushort const *,MyDataEntry *,HashWSTR,EmptyMapBase>::find(ushort const * const &,Map<ushort const *,MyDataEntry *,HashWSTR,EmptyMapBase>::Assoc * * *)
0x180036391  test    eax, eax
0x180036393  jz      short loc_1800363AE
0x180036395  mov     rax, [rbp+var_10]
0x180036399  xor     ebx, ebx
0x18003639b  mov     rcx, [rax]
0x18003639e  mov     rax, [rbp+arg_20]
0x1800363a2  mov     rdx, [rcx+28h]
0x1800363a6  mov     [rax], rdx
0x1800363a9  jmp     loc_18003647D
0x1800363ae  mov     rdi, [rbp+arg_20]
0x1800363b2  xor     r8d, r8d; Reserved
0x1800363b5  mov     rcx, [rsi]; hKey
0x1800363b8  mov     rdx, r15; lpSubKey
0x1800363bb  test    ebx, ebx
0x1800363bd  jnz     short loc_1800363CF
0x1800363bf  mov     r9d, r12d; samDesired
0x1800363c2  mov     [rsp+60h+phkResult], rdi; phkResult
0x1800363c7  call    cs:__imp_RegOpenKeyExW
0x1800363cd  jmp     short loc_1800363FC
0x1800363cf  lea     rax, [rbp+dwDisposition]
0x1800363d3  xor     r9d, r9d; lpClass
0x1800363d6  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x1800363db  mov     [rsp+60h+var_28], rdi; phkResult
0x1800363e0  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800363e9  mov     [rsp+60h+samDesired], r12d; samDesired
0x1800363ee  mov     dword ptr [rsp+60h+phkResult], 0; dwOptions
0x1800363f6  call    cs:__imp_RegCreateKeyExW
0x1800363fc  mov     ebx, eax
0x1800363fe  test    eax, eax
0x180036400  jnz     short loc_18003646E
0x180036402  mov     rcx, r14
0x180036405  call    ?allocAssocIfNecessary@?$Map@PEBGPEAUHKEY__@@VHashWSTR@@VEmptyMapBase@@@@AEAAJXZ; Map<ushort const *,HKEY__ *,HashWSTR,EmptyMapBase>::allocAssocIfNecessary(void)
0x18003640a  mov     ebx, eax
0x18003640c  test    eax, eax
0x18003640e  js      short loc_180036458
0x180036410  lea     r8, [rbp+var_10]
0x180036414  mov     [rbp+var_10], 0
0x18003641c  lea     rdx, [rbp+arg_8]
0x180036420  mov     rcx, r14
0x180036423  call    ?find@?$Map@PEBGPEAUMyDataEntry@@VHashWSTR@@VEmptyMapBase@@@@AEBAHAEBQEBGPEAPEAPEAVAssoc@1@@Z; Map<ushort const *,MyDataEntry *,HashWSTR,EmptyMapBase>::find(ushort const * const &,Map<ushort const *,MyDataEntry *,HashWSTR,EmptyMapBase>::Assoc * * *)
0x180036428  test    eax, eax
0x18003642a  jz      short loc_180036443
0x18003642c  mov     rcx, [rbp+var_10]
0x180036430  mov     rax, [rcx]
0x180036433  mov     [rax+20h], r15
0x180036437  mov     rcx, [rcx]
0x18003643a  mov     rax, [rdi]
0x18003643d  mov     [rcx+28h], rax
0x180036441  jmp     short loc_18003647D
0x180036443  mov     r9, [rbp+var_10]
0x180036447  lea     rdx, [rbp+arg_8]
0x18003644b  mov     r8, rdi
0x18003644e  mov     rcx, r14
0x180036451  call    ?newAssoc@?$Map@PEBGPEAUMyDataEntry@@VHashWSTR@@VEmptyMapBase@@@@AEAAJAEBQEBGAEBQEAUMyDataEntry@@PEAPEAVAssoc@1@@Z; Map<ushort const *,MyDataEntry *,HashWSTR,EmptyMapBase>::newAssoc(ushort const * const &,MyDataEntry * const &,Map<ushort const *,MyDataEntry *,HashWSTR,EmptyMapBase>::Assoc * *)
0x180036456  mov     ebx, eax
0x180036458  test    ebx, ebx
0x18003645a  jns     short loc_18003647D
0x18003645c  mov     rcx, [rdi]; hKey
0x18003645f  call    cs:__imp_RegCloseKey
0x180036465  mov     qword ptr [rdi], 0
0x18003646c  jmp     short loc_180036480
0x18003646e  jle     short loc_180036479
0x180036470  movzx   ebx, bx
0x180036473  or      ebx, 80070000h
0x180036479  test    ebx, ebx
0x18003647b  js      short loc_180036480
0x18003647d  inc     dword ptr [rsi+8]
0x180036480  lea     r11, [rsp+60h+var_s0]
0x180036485  mov     eax, ebx
0x180036487  mov     rbx, [r11+40h]
0x18003648b  mov     rsi, [r11+48h]
0x18003648f  mov     rsp, r11
0x180036492  pop     r15
0x180036494  pop     r14
0x180036496  pop     r12
0x180036498  pop     rdi
0x180036499  pop     rbp
0x18003649a  retn
```
