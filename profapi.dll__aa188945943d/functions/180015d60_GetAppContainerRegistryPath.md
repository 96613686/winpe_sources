# GetAppContainerRegistryPath

- ea: `0x180015d60`
- end: `0x180015e04`
- name: `GetAppContainerRegistryPath`
- size: `164`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003914`
- `0x180005b60`
- `0x180005b90`
- `0x18000a540`
- `0x180015d60`

## string_xrefs

- `0x180015dd5`: `minio\profapi\registry.cpp`

## pseudocode

```c
__int64 __fastcall GetAppContainerRegistryPath(unsigned __int16 *a1, unsigned __int64 a2)
{
  int AppContainerRegistryPathAlloc; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  unsigned __int16 *v8; // [rsp+20h] [rbp-28h] BYREF
  __int64 v9; // [rsp+28h] [rbp-20h]
  __int64 v10; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a1 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v8);
  v9 = -1;
  v10 = -1;
  AppContainerRegistryPathAlloc = GetAppContainerRegistryPathAlloc(&v8);
  v5 = AppContainerRegistryPathAlloc;
  if ( AppContainerRegistryPathAlloc >= 0 )
  {
    AppContainerRegistryPathAlloc = StringCchCopyW(a1, a2, v8);
    v5 = AppContainerRegistryPathAlloc;
    if ( AppContainerRegistryPathAlloc >= 0 )
    {
      v5 = 0;
      goto LABEL_7;
    }
    v6 = 126;
  }
  else
  {
    v6 = 123;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"minio\\profapi\\registry.cpp",
    (const char *)(unsigned int)AppContainerRegistryPathAlloc,
    (int)v8);
LABEL_7:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v8);
  return v5;
}

```

## disassembly

```asm
0x180015d60  mov     r11, rsp
0x180015d63  mov     [r11+8], rbx
0x180015d67  mov     [r11+10h], rsi
0x180015d6b  push    rdi
0x180015d6c  sub     rsp, 40h
0x180015d70  xor     eax, eax
0x180015d72  mov     rdi, rcx
0x180015d75  mov     [rcx], ax
0x180015d78  mov     rsi, rdx
0x180015d7b  lea     rcx, [r11-28h]
0x180015d7f  mov     [r11-28h], rax
0x180015d83  mov     [r11-20h], rax
0x180015d87  mov     [r11-18h], rax
0x180015d8b  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180015d90  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015d94  lea     rcx, [rsp+48h+var_28]; unsigned __int16 **
0x180015d99  mov     [rsp+48h+var_20], rax
0x180015d9e  mov     [rsp+48h+var_18], rax
0x180015da3  call    ?GetAppContainerRegistryPathAlloc@@YAJPEAPEAG@Z; GetAppContainerRegistryPathAlloc(ushort * *)
0x180015da8  mov     ebx, eax
0x180015daa  test    eax, eax
0x180015dac  jns     short loc_180015DB5
0x180015dae  mov     edx, 7Bh ; '{'
0x180015db3  jmp     short loc_180015DD0
0x180015db5  mov     r8, [rsp+48h+var_28]; unsigned __int16 *
0x180015dba  mov     rdx, rsi; unsigned __int64
0x180015dbd  mov     rcx, rdi; unsigned __int16 *
0x180015dc0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180015dc5  mov     ebx, eax
0x180015dc7  test    eax, eax
0x180015dc9  jns     short loc_180015DE6
0x180015dcb  mov     edx, 7Eh ; '~'; void *
0x180015dd0  mov     rcx, [rsp+48h]; this
0x180015dd5  lea     r8, aMinioProfapiRe; "minio\\profapi\\registry.cpp"
0x180015ddc  mov     r9d, eax; char *
0x180015ddf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015de4  jmp     short loc_180015DE8
0x180015de6  xor     ebx, ebx
0x180015de8  lea     rcx, [rsp+48h+var_28]
0x180015ded  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180015df2  mov     rsi, [rsp+48h+arg_8]
0x180015df7  mov     eax, ebx
0x180015df9  mov     rbx, [rsp+48h+arg_0]
0x180015dfe  add     rsp, 40h
0x180015e02  pop     rdi
0x180015e03  retn
```
