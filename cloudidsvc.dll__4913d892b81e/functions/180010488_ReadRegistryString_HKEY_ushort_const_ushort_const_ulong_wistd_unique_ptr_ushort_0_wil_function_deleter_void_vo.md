# ReadRegistryString(HKEY__ *,ushort const *,ushort const *,ulong,wistd::unique_ptr<ushort [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>> &)

- ea: `0x180010488`
- end: `0x180010595`
- name: `?ReadRegistryString@@YAJPEAUHKEY__@@PEBG1KAEAV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@Z`
- size: `269`
- prototype: `int __fastcall(HKEY hkey, __int64, const WCHAR *, DWORD, void **)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000afe4`
- `0x18000eaf4`
- `0x180010268`

## callees

- `0x18000dc08`
- `0x180010488`
- `0x1800105f4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800104c4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010519`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800104c4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010519`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010547`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001056d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010584`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010547`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001056d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010584`

## pseudocode

```c
int __fastcall ReadRegistryString(HKEY hkey, __int64 a2, const WCHAR *a3, DWORD a4, void **a5)
{
  unsigned int ValueW; // eax
  unsigned int v9; // r8d
  unsigned int v11; // eax
  unsigned int v12; // r8d
  int v13; // eax
  PVOID v14; // rcx
  int v15; // ebx
  PVOID v16; // rcx
  PVOID v17; // rdx
  void *v18; // r8
  unsigned int pdwType; // [rsp+20h] [rbp-38h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-38h]
  PVOID hMem[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+20h]
  DWORD pcbData; // [rsp+88h] [rbp+30h] BYREF
  int v24; // [rsp+8Ch] [rbp+34h]

  v24 = HIDWORD(a2);
  pcbData = 0;
  ValueW = RegGetValueW(hkey, 0, a3, a4, 0, 0, &pcbData);
  if ( ValueW )
    return wil::details::in1diag3::Return_Win32(retaddr, (void *)0x1A, v9, (const char *)ValueW, pdwType);
  wil::make_unique_hlocal<unsigned short [0]>(hMem);
  v11 = RegGetValueW(hkey, 0, a3, a4, 0, hMem[0], &pcbData);
  if ( v11 )
  {
    v13 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0x24, v12, (const char *)v11, pdwTypea);
    v14 = hMem[0];
    v15 = v13;
    hMem[0] = 0;
    if ( v14 )
      LocalFree(v14);
    return v15;
  }
  else
  {
    v16 = 0;
    v17 = hMem[0];
    hMem[0] = 0;
    v18 = *a5;
    *a5 = v17;
    if ( v18 )
    {
      LocalFree(v18);
      v16 = hMem[0];
    }
    hMem[0] = 0;
    if ( v16 )
      LocalFree(v16);
    return 0;
  }
}

```

## disassembly

```asm
0x180010488  mov     r11, rsp
0x18001048b  mov     [r11+10h], rdx
0x18001048f  push    rbp
0x180010490  push    rbx
0x180010491  push    rsi
0x180010492  push    rdi
0x180010493  mov     rbp, rsp
0x180010496  sub     rsp, 58h
0x18001049a  lea     rax, [rbp+arg_8]
0x18001049e  mov     [rbp+arg_8], 0
0x1800104a5  mov     [r11-48h], rax
0x1800104a9  xor     edx, edx; lpSubKey
0x1800104ab  mov     qword ptr [r11-50h], 0
0x1800104b3  mov     ebx, r9d
0x1800104b6  mov     qword ptr [r11-58h], 0
0x1800104be  mov     rdi, r8
0x1800104c1  mov     rsi, rcx
0x1800104c4  call    cs:__imp_RegGetValueW
0x1800104ca  test    eax, eax
0x1800104cc  jz      short loc_1800104E4
0x1800104ce  mov     rcx, [rbp+20h]; this
0x1800104d2  mov     r9d, eax; char *
0x1800104d5  mov     edx, 1Ah; void *
0x1800104da  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800104df  jmp     loc_18001058C
0x1800104e4  mov     edx, [rbp+arg_8]
0x1800104e7  lea     rcx, [rbp+hMem]
0x1800104eb  shr     rdx, 1
0x1800104ee  call    ??$make_unique_hlocal@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<ushort [0]>(unsigned __int64)
0x1800104f3  lea     rax, [rbp+arg_8]
0x1800104f7  mov     r9d, ebx; dwFlags
0x1800104fa  mov     [rsp+58h+pcbData], rax; pcbData
0x1800104ff  mov     r8, rdi; lpValue
0x180010502  mov     rax, [rbp+hMem]
0x180010506  xor     edx, edx; lpSubKey
0x180010508  mov     [rsp+58h+pvData], rax; pvData
0x18001050d  mov     rcx, rsi; hkey
0x180010510  mov     [rsp+58h+pdwType], 0; unsigned int
0x180010519  call    cs:__imp_RegGetValueW
0x18001051f  test    eax, eax
0x180010521  jz      short loc_180010551
0x180010523  mov     rcx, [rbp+20h]; this
0x180010527  mov     r9d, eax; char *
0x18001052a  mov     edx, 24h ; '$'; void *
0x18001052f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180010534  mov     rcx, [rbp+hMem]; hMem
0x180010538  mov     ebx, eax
0x18001053a  mov     [rbp+hMem], 0
0x180010542  test    rcx, rcx
0x180010545  jz      short loc_18001054D
0x180010547  call    cs:__imp_LocalFree
0x18001054d  mov     eax, ebx
0x18001054f  jmp     short loc_18001058C
0x180010551  mov     rax, [rbp+arg_20]
0x180010555  xor     ecx, ecx
0x180010557  mov     rdx, [rbp+hMem]
0x18001055b  mov     [rbp+hMem], rcx
0x18001055f  mov     r8, [rax]
0x180010562  mov     [rax], rdx
0x180010565  test    r8, r8
0x180010568  jz      short loc_180010577
0x18001056a  mov     rcx, r8; hMem
0x18001056d  call    cs:__imp_LocalFree
0x180010573  mov     rcx, [rbp+hMem]; hMem
0x180010577  mov     [rbp+hMem], 0
0x18001057f  test    rcx, rcx
0x180010582  jz      short loc_18001058A
0x180010584  call    cs:__imp_LocalFree
0x18001058a  xor     eax, eax
0x18001058c  add     rsp, 58h
0x180010590  pop     rdi
0x180010591  pop     rsi
0x180010592  pop     rbx
0x180010593  pop     rbp
0x180010594  retn
```
