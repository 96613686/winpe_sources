# LoadCKSReader(IMCSFDatastore * *)

- ea: `0x180028fdc`
- end: `0x180029090`
- name: `?LoadCKSReader@@YAJPEAPEAUIMCSFDatastore@@@Z`
- size: `180`
- prototype: `__int64 __fastcall(struct IMCSFDatastore **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180029240`

## callees

- `0x180011d6c`
- `0x180011d9c`
- `0x180028fdc`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002901a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002901a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LoadCKSReader(struct IMCSFDatastore **a1)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  int ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPVOID v8; // [rsp+48h] [rbp+10h] BYREF
  __int64 v9; // [rsp+50h] [rbp+18h] BYREF

  v8 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v8);
  v2 = CoCreateInstance(
         &GUID_649b3cc6_4621_413f_a08b_5aedd333ff6b,
         0,
         1u,
         &GUID_154c66a7_4e74_4200_a189_67c6ce528a04,
         &v8);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v9 = 0;
    v2 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, struct IMCSFDatastore **))(*(_QWORD *)v8 + 48LL))(v8, &v9, a1);
    v3 = v2;
    if ( v2 >= 0 )
    {
      v3 = 0;
      goto LABEL_7;
    }
    v4 = 82;
  }
  else
  {
    v4 = 80;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"onecoreuap\\admin\\dm\\coredpus\\wapdpu\\wapdpuimpl.cpp",
    (const char *)(unsigned int)v2,
    ppv);
LABEL_7:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v8);
  return v3;
}

```

## disassembly

```asm
0x180028fdc  mov     [rsp+arg_0], rbx
0x180028fe1  push    rdi
0x180028fe2  sub     rsp, 30h
0x180028fe6  mov     rdi, rcx
0x180028fe9  mov     [rsp+38h+arg_8], 0
0x180028ff2  lea     rcx, [rsp+38h+arg_8]
0x180028ff7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028ffc  lea     rax, [rsp+38h+arg_8]
0x180029001  mov     qword ptr [rsp+38h+ppv], rax; int
0x180029006  lea     r9, _GUID_154c66a7_4e74_4200_a189_67c6ce528a04; riid
0x18002900d  xor     edx, edx; pUnkOuter
0x18002900f  lea     r8d, [rdx+1]; dwClsContext
0x180029013  lea     rcx, _GUID_649b3cc6_4621_413f_a08b_5aedd333ff6b; rclsid
0x18002901a  call    cs:__imp_CoCreateInstance
0x180029021  nop     dword ptr [rax+rax+00h]
0x180029026  mov     ebx, eax
0x180029028  test    eax, eax
0x18002902a  jns     short loc_180029033
0x18002902c  mov     edx, 50h ; 'P'
0x180029031  jmp     short loc_180029060
0x180029033  mov     [rsp+38h+arg_10], 0
0x18002903c  mov     rcx, [rsp+38h+arg_8]
0x180029041  mov     rax, [rcx]
0x180029044  mov     r8, rdi
0x180029047  lea     rdx, [rsp+38h+arg_10]
0x18002904c  mov     rax, [rax+30h]
0x180029050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029055  mov     ebx, eax
0x180029057  test    eax, eax
0x180029059  jns     short loc_180029076
0x18002905b  mov     edx, 52h ; 'R'; void *
0x180029060  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\dm\\coredpus\\wapdpu"...
0x180029067  mov     r9d, eax; char *
0x18002906a  mov     rcx, [rsp+38h]; this
0x18002906f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029074  jmp     short loc_180029078
0x180029076  xor     ebx, ebx
0x180029078  lea     rcx, [rsp+38h+arg_8]
0x18002907d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029082  mov     eax, ebx
0x180029084  mov     rbx, [rsp+38h+arg_0]
0x180029089  add     rsp, 30h
0x18002908d  pop     rdi
0x18002908e  retn
```
