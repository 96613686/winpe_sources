# AddressPoolInit

- ea: `0x180015eec`
- end: `0x1800161e8`
- name: `AddressPoolInit`
- size: `764`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001b570`

## callees

- `0x180015eec`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180015fd1`
- `KERNEL32!GetLastError` at `0x180016045`
- `KERNEL32!GetLastError` at `0x1800160fc`
- `KERNEL32!GetLastError` at `0x180016178`
- `KERNEL32!GetLastError` at `0x180015fd1`
- `KERNEL32!GetLastError` at `0x180016045`
- `KERNEL32!GetLastError` at `0x1800160fc`
- `KERNEL32!GetLastError` at `0x180016178`
- `KERNEL32!LocalAlloc` at `0x180015fc3`
- `KERNEL32!LocalAlloc` at `0x180016037`
- `KERNEL32!LocalAlloc` at `0x1800160ee`
- `KERNEL32!LocalAlloc` at `0x18001616a`
- `KERNEL32!LocalAlloc` at `0x180015fc3`
- `KERNEL32!LocalAlloc` at `0x180016037`
- `KERNEL32!LocalAlloc` at `0x1800160ee`
- `KERNEL32!LocalAlloc` at `0x18001616a`
- `ADVAPI32!RegOpenKeyExW` at `0x180015f41`
- `ADVAPI32!RegOpenKeyExW` at `0x180015f41`
- `ADVAPI32!RegQueryValueExW` at `0x180015f9b`
- `ADVAPI32!RegQueryValueExW` at `0x180015ffb`
- `ADVAPI32!RegQueryValueExW` at `0x1800160c4`
- `ADVAPI32!RegQueryValueExW` at `0x180016128`
- `ADVAPI32!RegQueryValueExW` at `0x180015f9b`
- `ADVAPI32!RegQueryValueExW` at `0x180015ffb`
- `ADVAPI32!RegQueryValueExW` at `0x1800160c4`
- `ADVAPI32!RegQueryValueExW` at `0x180016128`
- `ADVAPI32!RegCloseKey` at `0x1800161ca`
- `ADVAPI32!RegCloseKey` at `0x1800161ca`

## string_xrefs

- `0x180015f19`: `System\CurrentControlSet\Services\PptpProtocol\Parameters`

## pseudocode

```c
__int64 AddressPoolInit()
{
  DWORD LastError; // ebx
  HKEY v1; // rdi
  BYTE *v2; // rbx
  unsigned int v3; // edi
  BYTE *i; // rcx
  __int64 v5; // rax
  _QWORD *v6; // rsi
  int v7; // ecx
  __int64 v8; // rax
  HKEY v9; // rsi
  BYTE *v10; // rdi
  unsigned int v11; // esi
  BYTE *j; // rdx
  __int64 v13; // rax
  _QWORD *v14; // r14
  int v15; // ecx
  __int64 v16; // rax
  __int64 result; // rax
  DWORD cbData; // [rsp+70h] [rbp+40h] BYREF
  DWORD Type; // [rsp+78h] [rbp+48h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+50h] BYREF

  hKey = 0;
  dword_1800C862C = 0;
  hMem = 0;
  dword_1800C8638 = 0;
  qword_1800C8640 = 0;
  LastError = RegOpenKeyExW(
                HKEY_LOCAL_MACHINE,
                L"System\\CurrentControlSet\\Services\\PptpProtocol\\Parameters",
                0,
                0x20019u,
                &hKey);
  if ( !LastError )
  {
    v1 = hKey;
    Type = 0;
    cbData = 0;
    if ( hKey )
    {
      dword_1800C862C = 0;
      hMem = 0;
      if ( !RegQueryValueExW(hKey, L"AnalogIPAddressPool", 0, &Type, 0, &cbData) && Type == 7 && cbData )
      {
        v2 = (BYTE *)LocalAlloc(0x40u, cbData);
        if ( v2 )
        {
          if ( !RegQueryValueExW(v1, L"AnalogIPAddressPool", 0, &Type, v2, &cbData) )
          {
            v3 = 0;
            for ( i = v2; *(_WORD *)i; i += 2 * v5 + 2 )
            {
              v5 = -1;
              do
                ++v5;
              while ( *(_WORD *)&i[2 * v5] );
              ++v3;
            }
            v6 = LocalAlloc(0x40u, 8LL * v3);
            if ( v6 )
            {
              v7 = 0;
              while ( *(_WORD *)v2 )
              {
                v6[v7] = v2;
                v8 = -1;
                do
                  ++v8;
                while ( *(_WORD *)&v2[2 * v8] );
                v2 += 2 * v8 + 2;
                ++v7;
              }
            }
            else
            {
              GetLastError();
            }
            dword_1800C862C = v3;
            hMem = v6;
          }
        }
        else
        {
          GetLastError();
        }
      }
    }
    v9 = hKey;
    Type = 0;
    cbData = 0;
    if ( hKey )
    {
      dword_1800C8638 = 0;
      qword_1800C8640 = 0;
      LastError = RegQueryValueExW(hKey, L"DigitalIPAddressPool", 0, &Type, 0, &cbData);
      if ( !LastError && Type == 7 && cbData )
      {
        v10 = (BYTE *)LocalAlloc(0x40u, cbData);
        if ( v10 )
        {
          LastError = RegQueryValueExW(v9, L"DigitalIPAddressPool", 0, &Type, v10, &cbData);
          if ( !LastError )
          {
            v11 = 0;
            for ( j = v10; *(_WORD *)j; j += 2 * v13 + 2 )
            {
              v13 = -1;
              do
                ++v13;
              while ( *(_WORD *)&j[2 * v13] );
              ++v11;
            }
            v14 = LocalAlloc(0x40u, 8LL * v11);
            if ( v14 )
            {
              LastError = 0;
              v15 = 0;
              while ( *(_WORD *)v10 )
              {
                v14[v15] = v10;
                v16 = -1;
                do
                  ++v16;
                while ( *(_WORD *)&v10[2 * v16] );
                v10 += 2 * v16 + 2;
                ++v15;
              }
            }
            else
            {
              LastError = GetLastError();
            }
            dword_1800C8638 = v11;
            qword_1800C8640 = v14;
          }
        }
        else
        {
          LastError = GetLastError();
        }
      }
    }
    else
    {
      LastError = 6;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  result = 0;
  if ( LastError != 2 )
    return LastError;
  return result;
}

```

## disassembly

```asm
0x180015eec  push    rbp
0x180015eee  push    rbx
0x180015eef  push    rsi
0x180015ef0  push    rdi
0x180015ef1  push    r12
0x180015ef3  push    r14
0x180015ef5  push    r15
0x180015ef7  mov     rbp, rsp
0x180015efa  sub     rsp, 30h
0x180015efe  xor     r15d, r15d
0x180015f01  lea     rax, [rbp+hKey]
0x180015f05  mov     r9d, 20019h; samDesired
0x180015f0b  mov     [rbp+hKey], r15
0x180015f0f  xor     r8d, r8d; ulOptions
0x180015f12  mov     cs:dword_1800C862C, r15d
0x180015f19  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Pp"...
0x180015f20  mov     cs:hMem, r15
0x180015f27  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180015f2e  mov     cs:dword_1800C8638, r15d
0x180015f35  mov     cs:qword_1800C8640, r15
0x180015f3c  mov     [rsp+30h+phkResult], rax; phkResult
0x180015f41  call    cs:__imp_RegOpenKeyExW
0x180015f47  mov     ebx, eax
0x180015f49  test    eax, eax
0x180015f4b  jnz     loc_1800161C1
0x180015f51  mov     rdi, [rbp+hKey]
0x180015f55  lea     r14d, [r15+40h]
0x180015f59  or      r12, 0FFFFFFFFFFFFFFFFh
0x180015f5d  mov     [rbp+Type], r15d
0x180015f61  mov     [rbp+cbData], r15d
0x180015f65  test    rdi, rdi
0x180015f68  jz      loc_180016082
0x180015f6e  lea     rax, [rbp+cbData]
0x180015f72  mov     cs:dword_1800C862C, r15d
0x180015f79  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180015f7e  lea     r9, [rbp+Type]; lpType
0x180015f82  xor     r8d, r8d; lpReserved
0x180015f85  mov     [rsp+30h+phkResult], r15; lpData
0x180015f8a  lea     rdx, aAnalogipaddres; "AnalogIPAddressPool"
0x180015f91  mov     cs:hMem, r15
0x180015f98  mov     rcx, rdi; hKey
0x180015f9b  call    cs:__imp_RegQueryValueExW
0x180015fa1  test    eax, eax
0x180015fa3  jnz     loc_180016082
0x180015fa9  cmp     [rbp+Type], 7
0x180015fad  jnz     loc_180016082
0x180015fb3  mov     eax, [rbp+cbData]
0x180015fb6  test    eax, eax
0x180015fb8  jz      loc_180016082
0x180015fbe  mov     edx, eax; uBytes
0x180015fc0  mov     ecx, r14d; uFlags
0x180015fc3  call    cs:__imp_LocalAlloc
0x180015fc9  mov     rbx, rax
0x180015fcc  test    rax, rax
0x180015fcf  jnz     short loc_180015FDC
0x180015fd1  call    cs:__imp_GetLastError
0x180015fd7  jmp     loc_180016082
0x180015fdc  lea     rax, [rbp+cbData]
0x180015fe0  xor     r8d, r8d; lpReserved
0x180015fe3  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180015fe8  lea     r9, [rbp+Type]; lpType
0x180015fec  lea     rdx, aAnalogipaddres; "AnalogIPAddressPool"
0x180015ff3  mov     [rsp+30h+phkResult], rbx; lpData
0x180015ff8  mov     rcx, rdi; hKey
0x180015ffb  call    cs:__imp_RegQueryValueExW
0x180016001  test    eax, eax
0x180016003  jnz     short loc_180016082
0x180016005  mov     edi, r15d
0x180016008  mov     rcx, rbx
0x18001600b  cmp     r15w, [rbx]
0x18001600f  jz      short loc_18001602E
0x180016011  mov     rax, r12
0x180016014  inc     rax
0x180016017  cmp     [rcx+rax*2], r15w
0x18001601c  jnz     short loc_180016014
0x18001601e  lea     rcx, [rcx+rax*2]
0x180016022  inc     edi
0x180016024  add     rcx, 2
0x180016028  cmp     r15w, [rcx]
0x18001602c  jnz     short loc_180016011
0x18001602e  mov     edx, edi
0x180016030  mov     ecx, r14d; uFlags
0x180016033  shl     rdx, 3; uBytes
0x180016037  call    cs:__imp_LocalAlloc
0x18001603d  mov     rsi, rax
0x180016040  test    rax, rax
0x180016043  jnz     short loc_18001604D
0x180016045  call    cs:__imp_GetLastError
0x18001604b  jmp     short loc_180016075
0x18001604d  mov     ecx, r15d
0x180016050  jmp     short loc_18001606F
0x180016052  mov     eax, ecx
0x180016054  mov     [rsi+rax*8], rbx
0x180016058  mov     rax, r12
0x18001605b  inc     rax
0x18001605e  cmp     [rbx+rax*2], r15w
0x180016063  jnz     short loc_18001605B
0x180016065  lea     rbx, [rbx+rax*2]
0x180016069  add     rbx, 2
0x18001606d  inc     ecx
0x18001606f  cmp     r15w, [rbx]
0x180016073  jnz     short loc_180016052
0x180016075  mov     cs:dword_1800C862C, edi
0x18001607b  mov     cs:hMem, rsi
0x180016082  mov     rsi, [rbp+hKey]
0x180016086  mov     [rbp+Type], r15d
0x18001608a  mov     [rbp+cbData], r15d
0x18001608e  test    rsi, rsi
0x180016091  jz      loc_1800161BC
0x180016097  lea     rax, [rbp+cbData]
0x18001609b  mov     cs:dword_1800C8638, r15d
0x1800160a2  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800160a7  lea     r9, [rbp+Type]; lpType
0x1800160ab  xor     r8d, r8d; lpReserved
0x1800160ae  mov     [rsp+30h+phkResult], r15; lpData
0x1800160b3  lea     rdx, aDigitalipaddre; "DigitalIPAddressPool"
0x1800160ba  mov     cs:qword_1800C8640, r15
0x1800160c1  mov     rcx, rsi; hKey
0x1800160c4  call    cs:__imp_RegQueryValueExW
0x1800160ca  mov     ebx, eax
0x1800160cc  test    eax, eax
0x1800160ce  jnz     loc_1800161C1
0x1800160d4  cmp     [rbp+Type], 7
0x1800160d8  jnz     loc_1800161C1
0x1800160de  mov     eax, [rbp+cbData]
0x1800160e1  test    eax, eax
0x1800160e3  jz      loc_1800161C1
0x1800160e9  mov     edx, eax; uBytes
0x1800160eb  mov     ecx, r14d; uFlags
0x1800160ee  call    cs:__imp_LocalAlloc
0x1800160f4  mov     rdi, rax
0x1800160f7  test    rax, rax
0x1800160fa  jnz     short loc_180016109
0x1800160fc  call    cs:__imp_GetLastError
0x180016102  mov     ebx, eax
0x180016104  jmp     loc_1800161C1
0x180016109  lea     rax, [rbp+cbData]
0x18001610d  xor     r8d, r8d; lpReserved
0x180016110  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180016115  lea     r9, [rbp+Type]; lpType
0x180016119  lea     rdx, aDigitalipaddre; "DigitalIPAddressPool"
0x180016120  mov     [rsp+30h+phkResult], rdi; lpData
0x180016125  mov     rcx, rsi; hKey
0x180016128  call    cs:__imp_RegQueryValueExW
0x18001612e  mov     ebx, eax
0x180016130  test    eax, eax
0x180016132  jnz     loc_1800161C1
0x180016138  mov     esi, r15d
0x18001613b  mov     rdx, rdi
0x18001613e  cmp     r15w, [rdi]
0x180016142  jz      short loc_180016161
0x180016144  mov     rax, r12
0x180016147  inc     rax
0x18001614a  cmp     [rdx+rax*2], r15w
0x18001614f  jnz     short loc_180016147
0x180016151  lea     rdx, [rdx+rax*2]
0x180016155  inc     esi
0x180016157  add     rdx, 2
0x18001615b  cmp     r15w, [rdx]
0x18001615f  jnz     short loc_180016144
0x180016161  mov     edx, esi
0x180016163  mov     ecx, r14d; uFlags
0x180016166  shl     rdx, 3; uBytes
0x18001616a  call    cs:__imp_LocalAlloc
0x180016170  mov     r14, rax
0x180016173  test    rax, rax
0x180016176  jnz     short loc_180016182
0x180016178  call    cs:__imp_GetLastError
0x18001617e  mov     ebx, eax
0x180016180  jmp     short loc_1800161AD
0x180016182  mov     ebx, r15d
0x180016185  mov     ecx, r15d
0x180016188  jmp     short loc_1800161A7
0x18001618a  mov     eax, ecx
0x18001618c  mov     [r14+rax*8], rdi
0x180016190  mov     rax, r12
0x180016193  inc     rax
0x180016196  cmp     [rdi+rax*2], r15w
0x18001619b  jnz     short loc_180016193
0x18001619d  lea     rdi, [rdi+rax*2]
0x1800161a1  add     rdi, 2
0x1800161a5  inc     ecx
0x1800161a7  cmp     r15w, [rdi]
0x1800161ab  jnz     short loc_18001618A
0x1800161ad  mov     cs:dword_1800C8638, esi
0x1800161b3  mov     cs:qword_1800C8640, r14
0x1800161ba  jmp     short loc_1800161C1
0x1800161bc  mov     ebx, 6
0x1800161c1  mov     rcx, [rbp+hKey]; hKey
0x1800161c5  test    rcx, rcx
0x1800161c8  jz      short loc_1800161D0
0x1800161ca  call    cs:__imp_RegCloseKey
0x1800161d0  cmp     ebx, 2
0x1800161d3  mov     eax, r15d
0x1800161d6  cmovnz  eax, ebx
0x1800161d9  add     rsp, 30h
0x1800161dd  pop     r15
0x1800161df  pop     r14
0x1800161e1  pop     r12
0x1800161e3  pop     rdi
0x1800161e4  pop     rsi
0x1800161e5  pop     rbx
0x1800161e6  pop     rbp
0x1800161e7  retn
```
