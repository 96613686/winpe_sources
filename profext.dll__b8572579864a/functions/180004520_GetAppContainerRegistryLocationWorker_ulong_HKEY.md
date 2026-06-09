# GetAppContainerRegistryLocationWorker(ulong,HKEY__ * *)

- ea: `0x180004520`
- end: `0x18000458b`
- name: `?GetAppContainerRegistryLocationWorker@@YAJKPEAPEAUHKEY__@@@Z`
- size: `107`
- prototype: `__int64 __fastcall(char *, HKEY *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800040c0`
- `0x180004520`
- `0x180004594`

## import_xrefs

- `profapi!__imp_GetAppContainerRegistryHandle` at `0x18000452d`
- `profapi!__imp_GetAppContainerRegistryHandle` at `0x18000452d`

## string_xrefs

- `0x180004549`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000456e`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000453e`: `Access %x`

## pseudocode

```c
__int64 __fastcall GetAppContainerRegistryLocationWorker(char *a1, HKEY *a2)
{
  int v2; // ebx
  unsigned int AppContainerRegistryHandle; // eax
  int v5; // [rsp+20h] [rbp-18h]
  char *v6; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = (int)a1;
  if ( a2 )
  {
    AppContainerRegistryHandle = GetAppContainerRegistryHandle();
    LODWORD(v6) = v2;
    return wil::details::in1diag3::Log_IfFailedMsg(
             retaddr,
             (void *)0xBB5,
             (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
             (const char *)AppContainerRegistryHandle,
             (__int64)"Access %x",
             v6);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBB2,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)0x80070057LL,
      v5);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180004520  push    rbx
0x180004522  sub     rsp, 30h
0x180004526  mov     ebx, ecx
0x180004528  test    rdx, rdx
0x18000452b  jz      short loc_180004569
0x18000452d  call    cs:__imp_GetAppContainerRegistryHandle
0x180004534  nop     dword ptr [rax+rax+00h]
0x180004539  mov     rcx, [rsp+38h]; this
0x18000453e  lea     rdx, aAccessX; "Access %x"
0x180004545  mov     dword ptr [rsp+38h+var_10], ebx; char *
0x180004549  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180004550  mov     [rsp+38h+var_18], rdx; __int64
0x180004555  mov     r9d, eax; char *
0x180004558  mov     edx, 0BB5h; void *
0x18000455d  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180004562  add     rsp, 30h
0x180004566  pop     rbx
0x180004567  retn
0x180004569  mov     rcx, [rsp+38h]; this
0x18000456e  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180004575  mov     ebx, 80070057h
0x18000457a  mov     edx, 0BB2h; void *
0x18000457f  mov     r9d, ebx; char *
0x180004582  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004587  mov     eax, ebx
0x180004589  jmp     short loc_180004562
```
