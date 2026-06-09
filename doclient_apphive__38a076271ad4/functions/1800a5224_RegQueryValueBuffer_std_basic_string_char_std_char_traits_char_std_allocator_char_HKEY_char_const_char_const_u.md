# _RegQueryValueBuffer<std::basic_string<char,std::char_traits<char>,std::allocator<char>>>(HKEY__ *,char const *,char const *,uint,std::basic_string<char,std::char_traits<char>,std::allocator<char>> &)

- ea: `0x1800a5224`
- end: `0x1800a53c0`
- name: `??$_RegQueryValueBuffer@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@@YAJPEAUHKEY__@@PEBD1IAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `412`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800a4a9c`

## callees

- `0x180008b1c`
- `0x18003dbd4`
- `0x1800a5224`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a529e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a5301`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a537b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a538f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a529e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a5301`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a537b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a538f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800a527c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800a527c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800a52df`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800a534c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800a52df`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800a534c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall _RegQueryValueBuffer<std::string>(HKEY a1, const CHAR *a2, const CHAR *a3, __int64 a4, _BYTE **a5)
{
  _BYTE *pvData; // rbx
  _BYTE *v7; // rax
  LSTATUS v8; // eax
  unsigned int v9; // ebx
  LSTATUS ValueA; // eax
  unsigned int v12; // ebx
  unsigned int v13; // eax
  unsigned int v14; // ebx
  unsigned int phkResult; // [rsp+20h] [rbp-48h]
  DWORD pcbData; // [rsp+40h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  pvData = a5;
  a5[2] = 0;
  v7 = a5;
  if ( (unsigned __int64)a5[3] > 0xF )
    v7 = *a5;
  *v7 = 0;
  hKey = 0;
  v8 = RegOpenKeyExA(a1, a2, 0, 0x20019u, &hKey);
  if ( v8 )
  {
    v9 = (unsigned __int16)v8 | 0x80070000;
    if ( v8 <= 0 )
      v9 = v8;
    if ( hKey )
      RegCloseKey(hKey);
    return v9;
  }
  else
  {
    pcbData = 0;
    ValueA = RegGetValueA(hKey, 0, a3, 2u, 0, 0, &pcbData);
    if ( ValueA )
    {
      v12 = (unsigned __int16)ValueA | 0x80070000;
      if ( ValueA <= 0 )
        v12 = ValueA;
      if ( hKey )
        RegCloseKey(hKey);
      return v12;
    }
    else
    {
      std::string::resize(a5, pcbData);
      if ( (unsigned __int64)a5[3] > 0xF )
        pvData = *a5;
      v13 = RegGetValueA(hKey, 0, a3, 2u, 0, pvData, &pcbData);
      if ( v13 )
      {
        v14 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x16,
                (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\RegUtil.cpp",
                (const char *)v13,
                phkResult);
        if ( hKey )
          RegCloseKey(hKey);
        return v14;
      }
      else
      {
        if ( hKey )
          RegCloseKey(hKey);
        return 0;
      }
    }
  }
}

```

## disassembly

```asm
0x1800a5224  mov     [rsp+arg_18], rbx
0x1800a5229  push    rdi
0x1800a522a  sub     rsp, 60h
0x1800a522e  mov     rax, cs:__security_cookie
0x1800a5235  xor     rax, rsp
0x1800a5238  mov     [rsp+68h+var_18], rax
0x1800a523d  mov     rdi, r8
0x1800a5240  mov     rbx, [rsp+68h+arg_20]
0x1800a5248  mov     qword ptr [rbx+10h], 0
0x1800a5250  mov     rax, rbx
0x1800a5253  cmp     qword ptr [rbx+18h], 0Fh
0x1800a5258  jbe     short loc_1800A525D
0x1800a525a  mov     rax, [rbx]
0x1800a525d  mov     byte ptr [rax], 0
0x1800a5260  mov     [rsp+68h+hKey], 0
0x1800a5269  lea     rax, [rsp+68h+hKey]
0x1800a526e  mov     [rsp+68h+phkResult], rax; phkResult
0x1800a5273  mov     r9d, 20019h; samDesired
0x1800a5279  xor     r8d, r8d; ulOptions
0x1800a527c  call    cs:__imp_RegOpenKeyExA
0x1800a5282  test    eax, eax
0x1800a5284  jz      short loc_1800A52AB
0x1800a5286  movzx   ebx, ax
0x1800a5289  or      ebx, 80070000h
0x1800a528f  test    eax, eax
0x1800a5291  cmovle  ebx, eax
0x1800a5294  mov     rcx, [rsp+68h+hKey]; hKey
0x1800a5299  test    rcx, rcx
0x1800a529c  jz      short loc_1800A52A4
0x1800a529e  call    cs:__imp_RegCloseKey
0x1800a52a4  mov     eax, ebx
0x1800a52a6  jmp     loc_1800A53A4
0x1800a52ab  mov     [rsp+68h+var_28], 0
0x1800a52b3  lea     rax, [rsp+68h+var_28]
0x1800a52b8  mov     [rsp+68h+pcbData], rax; pcbData
0x1800a52bd  mov     [rsp+68h+pvData], 0; pvData
0x1800a52c6  mov     [rsp+68h+phkResult], 0; pdwType
0x1800a52cf  mov     r9d, 2; dwFlags
0x1800a52d5  mov     r8, rdi; lpValue
0x1800a52d8  xor     edx, edx; lpSubKey
0x1800a52da  mov     rcx, [rsp+68h+hKey]; hkey
0x1800a52df  call    cs:__imp_RegGetValueA
0x1800a52e5  test    eax, eax
0x1800a52e7  jz      short loc_1800A530E
0x1800a52e9  movzx   ebx, ax
0x1800a52ec  or      ebx, 80070000h
0x1800a52f2  test    eax, eax
0x1800a52f4  cmovle  ebx, eax
0x1800a52f7  mov     rcx, [rsp+68h+hKey]; hKey
0x1800a52fc  test    rcx, rcx
0x1800a52ff  jz      short loc_1800A5307
0x1800a5301  call    cs:__imp_RegCloseKey
0x1800a5307  mov     eax, ebx
0x1800a5309  jmp     loc_1800A53A4
0x1800a530e  mov     edx, [rsp+68h+var_28]
0x1800a5312  mov     rcx, rbx
0x1800a5315  call    ?resize@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_KD@Z; std::string::resize(unsigned __int64,char)
0x1800a531a  cmp     qword ptr [rbx+18h], 0Fh
0x1800a531f  jbe     short loc_1800A5324
0x1800a5321  mov     rbx, [rbx]
0x1800a5324  lea     rax, [rsp+68h+var_28]
0x1800a5329  mov     [rsp+68h+pcbData], rax; pcbData
0x1800a532e  mov     [rsp+68h+pvData], rbx; pvData
0x1800a5333  mov     [rsp+68h+phkResult], 0; unsigned int
0x1800a533c  mov     r9d, 2; dwFlags
0x1800a5342  mov     r8, rdi; lpValue
0x1800a5345  xor     edx, edx; lpSubKey
0x1800a5347  mov     rcx, [rsp+68h+hKey]; hkey
0x1800a534c  call    cs:__imp_RegGetValueA
0x1800a5352  test    eax, eax
0x1800a5354  jz      short loc_1800A5385
0x1800a5356  mov     rcx, [rsp+68h]; this
0x1800a535b  mov     r9d, eax; char *
0x1800a535e  lea     r8, aCW1SSrcDeliver_92; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800a5365  mov     edx, 16h; void *
0x1800a536a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a536f  mov     ebx, eax
0x1800a5371  mov     rcx, [rsp+68h+hKey]; hKey
0x1800a5376  test    rcx, rcx
0x1800a5379  jz      short loc_1800A5381
0x1800a537b  call    cs:__imp_RegCloseKey
0x1800a5381  mov     eax, ebx
0x1800a5383  jmp     short loc_1800A53A4
0x1800a5385  mov     rcx, [rsp+68h+hKey]; hKey
0x1800a538a  test    rcx, rcx
0x1800a538d  jz      short loc_1800A5395
0x1800a538f  call    cs:__imp_RegCloseKey
0x1800a5395  xor     eax, eax
0x1800a5397  jmp     short loc_1800A53A4
0x1800a5399  mov     eax, 8007000Eh
0x1800a539e  jmp     short loc_1800A53A4
0x1800a53a0  mov     eax, [rsp+68h+var_28]
0x1800a53a4  mov     rcx, [rsp+68h+var_18]
0x1800a53a9  xor     rcx, rsp; StackCookie
0x1800a53ac  call    __security_check_cookie
0x1800a53b1  mov     rbx, [rsp+68h+arg_18]
0x1800a53b9  add     rsp, 60h
0x1800a53bd  pop     rdi
0x1800a53be  retn
```
