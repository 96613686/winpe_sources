# NgcUtils::GetRegistryValue(HKEY__ *,ushort const *,ushort const *,ulong,uchar * *,ulong *)

- ea: `0x18001cc04`
- end: `0x18001cd56`
- name: `?GetRegistryValue@NgcUtils@@YAJPEAUHKEY__@@PEBG1KPEAPEAEPEAK@Z`
- size: `338`
- prototype: `__int64 __fastcall(NgcUtils *this, const WCHAR *, unsigned __int16 *, const unsigned __int16 *, _QWORD *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014490`

## callees

- `0x18000cc34`
- `0x18000cc58`
- `0x180017440`
- `0x18001cc04`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001cc4f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ccfe`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001cc4f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ccfe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cd2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cd2b`

## string_xrefs

- `0x18001cc7d`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`
- `0x18001ccbb`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`
- `0x18001cd10`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall NgcUtils::GetRegistryValue(
        NgcUtils *this,
        const WCHAR *a2,
        unsigned __int16 *a3,
        const unsigned __int16 *a4,
        _QWORD *a5,
        unsigned __int8 **a6)
{
  LSTATUS ValueW; // eax
  unsigned int v8; // ebx
  __int64 result; // rax
  PVOID v10; // rbx
  unsigned int v11; // eax
  unsigned int v12; // edi
  int pdwType; // [rsp+20h] [rbp-28h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  PVOID hMem; // [rsp+60h] [rbp+18h] BYREF
  DWORD pcbData; // [rsp+68h] [rbp+20h] BYREF

  hMem = a3;
  pcbData = 0;
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, a2, L"SRKModulusHash", 8u, 0, 0, &pcbData);
  v8 = ValueW;
  if ( ValueW > 0 )
    v8 = (unsigned __int16)ValueW | 0x80070000;
  if ( (v8 & 0x80000000) != 0 )
  {
    result = 2147942402LL;
    if ( v8 == -2147024894 )
      return result;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
      (const char *)v8,
      pdwType);
    return v8;
  }
  wil::make_unique_hlocal_nothrow<unsigned char [0]>(&hMem, pcbData);
  v10 = hMem;
  if ( !hMem )
  {
    v8 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
      (const char *)0x8007000ELL,
      pdwType);
    return v8;
  }
  v11 = RegGetValueW(HKEY_LOCAL_MACHINE, a2, L"SRKModulusHash", 8u, 0, hMem, &pcbData);
  if ( v11 )
  {
    v12 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x33,
            (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
            (const char *)v11,
            pdwTypea);
    if ( v10 )
      LocalFree(v10);
    return v12;
  }
  else
  {
    *a5 = v10;
    *(_DWORD *)a6 = pcbData;
    return 0;
  }
}

```

## disassembly

```asm
0x18001cc04  mov     r11, rsp
0x18001cc07  mov     [r11+8], rbx
0x18001cc0b  mov     [r11+20h], r9d
0x18001cc0f  mov     [r11+18h], r8
0x18001cc13  push    rdi
0x18001cc14  sub     rsp, 40h
0x18001cc18  mov     rdi, rdx
0x18001cc1b  mov     [rsp+48h+arg_18], 0
0x18001cc23  lea     rax, [r11+20h]
0x18001cc27  mov     [r11-18h], rax
0x18001cc2b  mov     qword ptr [r11-20h], 0
0x18001cc33  mov     qword ptr [r11-28h], 0
0x18001cc3b  mov     r9d, 8; dwFlags
0x18001cc41  lea     r8, aSrkmodulushash; "SRKModulusHash"
0x18001cc48  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001cc4f  call    cs:__imp_RegGetValueW
0x18001cc55  mov     ebx, eax
0x18001cc57  test    eax, eax
0x18001cc59  jle     short loc_18001CC64
0x18001cc5b  movzx   ebx, ax
0x18001cc5e  or      ebx, 80070000h
0x18001cc64  test    ebx, ebx
0x18001cc66  jns     short loc_18001CC95
0x18001cc68  mov     eax, 80070002h
0x18001cc6d  cmp     ebx, eax
0x18001cc6f  jz      loc_18001CD4B
0x18001cc75  mov     rcx, [rsp+48h]; this
0x18001cc7a  mov     r9d, ebx; char *
0x18001cc7d  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001cc84  mov     edx, 26h ; '&'; void *
0x18001cc89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cc8e  mov     eax, ebx
0x18001cc90  jmp     loc_18001CD4B
0x18001cc95  mov     edx, [rsp+48h+arg_18]
0x18001cc99  lea     rcx, [rsp+48h+hMem]
0x18001cc9e  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x18001cca3  nop
0x18001cca4  mov     rbx, [rsp+48h+hMem]
0x18001cca9  test    rbx, rbx
0x18001ccac  jnz     short loc_18001CCCF
0x18001ccae  mov     rcx, [rsp+48h]; this
0x18001ccb3  mov     ebx, 8007000Eh
0x18001ccb8  mov     r9d, ebx; char *
0x18001ccbb  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001ccc2  mov     edx, 2Ah ; '*'; void *
0x18001ccc7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cccc  nop
0x18001cccd  jmp     short loc_18001CC8E
0x18001cccf  lea     rax, [rsp+48h+arg_18]
0x18001ccd4  mov     [rsp+48h+pcbData], rax; pcbData
0x18001ccd9  mov     [rsp+48h+pvData], rbx; pvData
0x18001ccde  mov     [rsp+48h+pdwType], 0; unsigned int
0x18001cce7  mov     r9d, 8; dwFlags
0x18001cced  lea     r8, aSrkmodulushash; "SRKModulusHash"
0x18001ccf4  mov     rdx, rdi; lpSubKey
0x18001ccf7  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001ccfe  call    cs:__imp_RegGetValueW
0x18001cd04  test    eax, eax
0x18001cd06  jz      short loc_18001CD36
0x18001cd08  mov     rcx, [rsp+48h]; this
0x18001cd0d  mov     r9d, eax; char *
0x18001cd10  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001cd17  mov     edx, 33h ; '3'; void *
0x18001cd1c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001cd21  mov     edi, eax
0x18001cd23  test    rbx, rbx
0x18001cd26  jz      short loc_18001CD32
0x18001cd28  mov     rcx, rbx; hMem
0x18001cd2b  call    cs:__imp_LocalFree
0x18001cd31  nop
0x18001cd32  mov     eax, edi
0x18001cd34  jmp     short loc_18001CD4B
0x18001cd36  mov     rax, [rsp+48h+arg_20]
0x18001cd3b  mov     [rax], rbx
0x18001cd3e  mov     rcx, [rsp+48h+arg_28]
0x18001cd43  mov     eax, [rsp+48h+arg_18]
0x18001cd47  mov     [rcx], eax
0x18001cd49  xor     eax, eax
0x18001cd4b  mov     rbx, [rsp+48h+arg_0]
0x18001cd50  add     rsp, 40h
0x18001cd54  pop     rdi
0x18001cd55  retn
```
