# CreateCopyOfSid(void *,void * *)

- ea: `0x1400326b0`
- end: `0x14003274c`
- name: `?CreateCopyOfSid@@YAJPEAXPEAPEAX@Z`
- size: `156`
- prototype: `__int64 __fastcall(PSID pSourceSid, void **)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140032754`
- `0x140032880`
- `0x14003292c`

## callees

- `0x140008168`
- `0x140008188`
- `0x14002c054`
- `0x1400326b0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400326bf`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400326bf`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x140032707`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x140032707`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400326ce`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400326ce`

## string_xrefs

- `0x1400326e6`: `clientcore\termsrv\rdpplatform\common\rdpsid\rdpsid.cpp`
- `0x140032716`: `clientcore\termsrv\rdpplatform\common\rdpsid\rdpsid.cpp`

## pseudocode

```c
__int64 __fastcall CreateCopyOfSid(PSID pSourceSid, void **a2)
{
  DWORD LengthSid; // ebp
  HLOCAL v5; // rax
  void *v6; // rbx
  unsigned int LastError; // ebx
  const char *v8; // r9
  int v10; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HLOCAL v12; // [rsp+60h] [rbp+18h] BYREF

  LengthSid = GetLengthSid(pSourceSid);
  v5 = LocalAlloc(0x40u, LengthSid);
  v12 = v5;
  v6 = v5;
  if ( v5 )
  {
    if ( CopySid(LengthSid, v5, pSourceSid) )
    {
      *a2 = v6;
      LastError = 0;
      v12 = 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xB,
                    (unsigned int)"clientcore\\termsrv\\rdpplatform\\common\\rdpsid\\rdpsid.cpp",
                    v8);
    }
  }
  else
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA,
      (unsigned int)"clientcore\\termsrv\\rdpplatform\\common\\rdpsid\\rdpsid.cpp",
      (const char *)0x8007000ELL,
      v10);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v12);
  return LastError;
}

```

## disassembly

```asm
0x1400326b0  push    rbx
0x1400326b2  push    rbp
0x1400326b3  push    rsi
0x1400326b4  push    rdi
0x1400326b5  sub     rsp, 28h
0x1400326b9  mov     rdi, rdx
0x1400326bc  mov     rsi, rcx
0x1400326bf  call    cs:__imp_GetLengthSid
0x1400326c5  mov     edx, eax; uBytes
0x1400326c7  mov     ecx, 40h ; '@'; uFlags
0x1400326cc  mov     ebp, eax
0x1400326ce  call    cs:__imp_LocalAlloc
0x1400326d4  mov     [rsp+48h+arg_10], rax
0x1400326d9  mov     rbx, rax
0x1400326dc  test    rax, rax
0x1400326df  jnz     short loc_1400326FF
0x1400326e1  mov     rcx, [rsp+48h]; this
0x1400326e6  lea     r8, aClientcoreTerm_1; "clientcore\\termsrv\\rdpplatform\\commo"...
0x1400326ed  mov     ebx, 8007000Eh
0x1400326f2  lea     edx, [rax+0Ah]; void *
0x1400326f5  mov     r9d, ebx; char *
0x1400326f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400326fd  jmp     short loc_140032737
0x1400326ff  mov     r8, rsi; pSourceSid
0x140032702  mov     rdx, rbx; pDestinationSid
0x140032705  mov     ecx, ebp; nDestinationSidLength
0x140032707  call    cs:__imp_CopySid
0x14003270d  test    eax, eax
0x14003270f  jnz     short loc_140032729
0x140032711  mov     rcx, [rsp+48h]; this
0x140032716  lea     r8, aClientcoreTerm_1; "clientcore\\termsrv\\rdpplatform\\commo"...
0x14003271d  lea     edx, [rax+0Bh]; void *
0x140032720  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140032725  mov     ebx, eax
0x140032727  jmp     short loc_140032737
0x140032729  mov     [rdi], rbx
0x14003272c  xor     ebx, ebx
0x14003272e  mov     [rsp+48h+arg_10], 0
0x140032737  lea     rcx, [rsp+48h+arg_10]
0x14003273c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140032741  mov     eax, ebx
0x140032743  add     rsp, 28h
0x140032747  pop     rdi
0x140032748  pop     rsi
0x140032749  pop     rbp
0x14003274a  pop     rbx
0x14003274b  retn
```
