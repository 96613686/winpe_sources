# CHiveUploadTaskHandler_CreateInstance(_GUID const &,void * *)

- ea: `0x1800194d0`
- end: `0x18001956a`
- name: `?CHiveUploadTaskHandler_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `154`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180005aa0`
- `0x180006a9c`
- `0x180017fe4`
- `0x1800194d0`
- `0x180020010`

## string_xrefs

- `0x180019536`: `clientcore\ds\security\gina\profile\roaming\uploadtask.cpp`

## pseudocode

```c
__int64 __fastcall CHiveUploadTaskHandler_CreateInstance(const struct _GUID *a1, void **a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 (__fastcall ***v10)(_QWORD, const struct _GUID *, void **); // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  v10 = 0;
  Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(&v10);
  v4 = Microsoft::WRL::Details::MakeAndInitialize<CHiveUploadTaskHandler,CHiveUploadTaskHandler,>(&v10);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v4 = (**v10)(v10, a1, a2);
    v5 = v4;
    if ( v4 >= 0 )
    {
      v5 = 0;
      goto LABEL_7;
    }
    v6 = 694;
  }
  else
  {
    v6 = 693;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\uploadtask.cpp",
    (const char *)(unsigned int)v4,
    v8);
LABEL_7:
  Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(&v10);
  return v5;
}

```

## disassembly

```asm
0x1800194d0  mov     rax, rsp
0x1800194d3  mov     [rax+8], rbx
0x1800194d7  mov     [rax+18h], rsi
0x1800194db  push    rdi; int
0x1800194dc  sub     rsp, 20h
0x1800194e0  mov     rdi, rdx
0x1800194e3  mov     rsi, rcx
0x1800194e6  mov     qword ptr [rdx], 0
0x1800194ed  mov     qword ptr [rax+10h], 0
0x1800194f5  lea     rcx, [rax+10h]
0x1800194f9  call    ?InternalRelease@?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(void)
0x1800194fe  lea     rcx, [rsp+28h+arg_8]
0x180019503  call    ??$MakeAndInitialize@VCHiveUploadTaskHandler@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCHiveUploadTaskHandler@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CHiveUploadTaskHandler,CHiveUploadTaskHandler,>(CHiveUploadTaskHandler * *)
0x180019508  mov     ebx, eax
0x18001950a  test    eax, eax
0x18001950c  jns     short loc_180019515
0x18001950e  mov     edx, 2B5h
0x180019513  jmp     short loc_180019536
0x180019515  mov     rcx, [rsp+28h+arg_8]
0x18001951a  mov     rax, [rcx]
0x18001951d  mov     r8, rdi
0x180019520  mov     rdx, rsi
0x180019523  mov     rax, [rax]
0x180019526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001952b  mov     ebx, eax
0x18001952d  test    eax, eax
0x18001952f  jns     short loc_18001954C
0x180019531  mov     edx, 2B6h; void *
0x180019536  lea     r8, aClientcoreDsSe_0; "clientcore\\ds\\security\\gina\\profile"...
0x18001953d  mov     r9d, eax; char *
0x180019540  mov     rcx, [rsp+28h]; this
0x180019545  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001954a  jmp     short loc_18001954E
0x18001954c  xor     ebx, ebx
0x18001954e  lea     rcx, [rsp+28h+arg_8]
0x180019553  call    ?InternalRelease@?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(void)
0x180019558  mov     eax, ebx
0x18001955a  mov     rbx, [rsp+28h+arg_0]
0x18001955f  mov     rsi, [rsp+28h+arg_10]
0x180019564  add     rsp, 20h
0x180019568  pop     rdi
0x180019569  retn
```
