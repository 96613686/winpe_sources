# MQSetCaConfig(ulong,MQ_CA_CONFIG *)

- ea: `0x180007f20`
- end: `0x180008011`
- name: `?MQSetCaConfig@@YAJKPEAVMQ_CA_CONFIG@@@Z`
- size: `241`
- prototype: `__int64 __fastcall(unsigned int, struct MQ_CA_CONFIG *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180005d48`
- `0x180007f20`
- `0x180009ee4`
- `0x18000d5c0`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180007fdb`
- `ADVAPI32!RegSetValueExW` at `0x180007fdb`
- `ADVAPI32!RegOpenKeyExW` at `0x180007fa7`
- `ADVAPI32!RegOpenKeyExW` at `0x180007fa7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MQSetCaConfig(unsigned int a1, struct MQ_CA_CONFIG *a2)
{
  __int64 i; // rbx
  HKEY phkResult; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  hKey = 0;
  if ( (unsigned int)GetFalconKey(L"CertificationAuthorities", &hKey) )
    return 3222142977LL;
  if ( *((_QWORD *)a2 + 2) )
    return SetNewCaConfig(a1, a2, hKey);
  for ( i = 0; (unsigned int)i < a1; i = (unsigned int)(i + 1) )
  {
    phkResult = 0;
    if ( RegOpenKeyExW(hKey, *((LPCWSTR *)a2 + 5 * i), 0, 2u, &phkResult)
      || RegSetValueExW(phkResult, L"Enabled", 0, 4u, (const BYTE *)a2 + 40 * i + 28, 4u) )
    {
      CRegHandle::~CRegHandle((CRegHandle *)&phkResult);
      return 3222142977LL;
    }
    CRegHandle::~CRegHandle((CRegHandle *)&phkResult);
  }
  return 0;
}

```

## disassembly

```asm
0x180007f20  mov     [rsp+arg_0], rbx
0x180007f25  push    rbp
0x180007f26  push    rsi
0x180007f27  push    rdi
0x180007f28  sub     rsp, 30h
0x180007f2c  mov     rdi, rdx
0x180007f2f  mov     esi, ecx
0x180007f31  mov     [rsp+48h+hKey], 0
0x180007f3a  lea     rdx, [rsp+48h+hKey]; HKEY *
0x180007f3f  lea     rcx, aCertificationa; "CertificationAuthorities"
0x180007f46  call    ?GetFalconKey@@YAJPEB_WPEAPEAUHKEY__@@@Z; GetFalconKey(wchar_t const *,HKEY__ * *)
0x180007f4b  test    eax, eax
0x180007f4d  jz      short loc_180007F59
0x180007f4f  mov     eax, 0C00E0001h
0x180007f54  jmp     loc_180008004
0x180007f59  cmp     qword ptr [rdi+10h], 0
0x180007f5e  jz      short loc_180007F74
0x180007f60  mov     r8, [rsp+48h+hKey]; HKEY
0x180007f65  mov     rdx, rdi; struct MQ_CA_CONFIG *
0x180007f68  mov     ecx, esi; unsigned int
0x180007f6a  call    ?SetNewCaConfig@@YAJKPEAVMQ_CA_CONFIG@@PEAUHKEY__@@@Z; SetNewCaConfig(ulong,MQ_CA_CONFIG *,HKEY__ *)
0x180007f6f  jmp     loc_180008004
0x180007f74  xor     ebx, ebx
0x180007f76  cmp     ebx, esi
0x180007f78  jnb     loc_180008002
0x180007f7e  mov     [rsp+48h+arg_10], 0
0x180007f87  lea     rbp, [rbx+rbx*4]
0x180007f8b  lea     rax, [rsp+48h+arg_10]
0x180007f90  mov     [rsp+48h+phkResult], rax; phkResult
0x180007f95  mov     r9d, 2; samDesired
0x180007f9b  xor     r8d, r8d; ulOptions
0x180007f9e  mov     rdx, [rdi+rbp*8]; lpSubKey
0x180007fa2  mov     rcx, [rsp+48h+hKey]; hKey
0x180007fa7  call    cs:__imp_RegOpenKeyExW
0x180007fad  test    eax, eax
0x180007faf  jnz     short loc_180007FF3
0x180007fb1  lea     rax, [rdi+1Ch]
0x180007fb5  lea     rax, [rax+rbp*8]
0x180007fb9  mov     [rsp+48h+cbData], 4; cbData
0x180007fc1  mov     [rsp+48h+phkResult], rax; lpData
0x180007fc6  mov     r9d, 4; dwType
0x180007fcc  xor     r8d, r8d; Reserved
0x180007fcf  lea     rdx, ValueName; "Enabled"
0x180007fd6  mov     rcx, [rsp+48h+arg_10]; hKey
0x180007fdb  call    cs:__imp_RegSetValueExW
0x180007fe1  test    eax, eax
0x180007fe3  jnz     short loc_180007FF3
0x180007fe5  lea     rcx, [rsp+48h+arg_10]; this
0x180007fea  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x180007fef  inc     ebx
0x180007ff1  jmp     short loc_180007F76
0x180007ff3  lea     rcx, [rsp+48h+arg_10]; this
0x180007ff8  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x180007ffd  jmp     loc_180007F4F
0x180008002  xor     eax, eax
0x180008004  mov     rbx, [rsp+48h+arg_0]
0x180008009  add     rsp, 30h
0x18000800d  pop     rdi
0x18000800e  pop     rsi
0x18000800f  pop     rbp
0x180008010  retn
```
