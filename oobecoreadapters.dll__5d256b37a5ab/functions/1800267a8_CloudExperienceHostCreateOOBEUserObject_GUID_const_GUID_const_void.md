# CloudExperienceHostCreateOOBEUserObject(_GUID const &,_GUID const &,void * *)

- ea: `0x1800267a8`
- end: `0x180026850`
- name: `?CloudExperienceHostCreateOOBEUserObject@@YAJAEBU_GUID@@0PEAPEAX@Z`
- size: `168`
- prototype: `__int64 __fastcall(const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `8`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800246c4`
- `0x180024d0c`
- `0x180024f14`
- `0x18002c588`
- `0x18002f96c`
- `0x180033490`
- `0x1800343d4`
- `0x1800344c4`

## callees

- `0x18000683c`
- `0x1800076d4`
- `0x1800267a8`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800267eb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800267eb`

## string_xrefs

- `0x180026823`: `onecoreuap\internal\shell\inc\cloudexperiencehostcreatebrokeredobjecthelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CloudExperienceHostCreateOOBEUserObject(const struct _GUID *a1, const struct _GUID *a2, void **a3)
{
  HRESULT v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  int ppv; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  LPVOID v12; // [rsp+78h] [rbp+20h] BYREF

  v12 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
  v6 = CoCreateInstance(
         &GUID_e9309678_18b4_414b_ba7a_2c9a7bcf9684,
         0,
         1u,
         &GUID_ef2e1c05_9173_433a_baa2_ada0c25d0b99,
         &v12);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(LPVOID, const struct _GUID *, const struct _GUID *, void **))(*(_QWORD *)v12 + 32LL))(
           v12,
           a1,
           a2,
           a3);
    v7 = v6;
    if ( v6 >= 0 )
    {
      v7 = 0;
      goto LABEL_7;
    }
    v8 = 32;
  }
  else
  {
    v8 = 31;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\cloudexperiencehostcreatebrokeredobjecthelpers.h",
    (const char *)(unsigned int)v6,
    ppv);
LABEL_7:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
  return v7;
}

```

## disassembly

```asm
0x1800267a8  push    rbx
0x1800267aa  push    rbp
0x1800267ab  push    rsi
0x1800267ac  push    rdi
0x1800267ad  sub     rsp, 38h
0x1800267b1  mov     rdi, r8
0x1800267b4  mov     rsi, rdx
0x1800267b7  mov     rbp, rcx
0x1800267ba  mov     [rsp+58h+arg_18], 0
0x1800267c3  lea     rcx, [rsp+58h+arg_18]
0x1800267c8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800267cd  lea     rax, [rsp+58h+arg_18]
0x1800267d2  mov     qword ptr [rsp+58h+ppv], rax; int
0x1800267d7  lea     r9, _GUID_ef2e1c05_9173_433a_baa2_ada0c25d0b99; riid
0x1800267de  xor     edx, edx; pUnkOuter
0x1800267e0  lea     r8d, [rdx+1]; dwClsContext
0x1800267e4  lea     rcx, _GUID_e9309678_18b4_414b_ba7a_2c9a7bcf9684; rclsid
0x1800267eb  call    cs:__imp_CoCreateInstance
0x1800267f1  mov     ebx, eax
0x1800267f3  test    eax, eax
0x1800267f5  jns     short loc_1800267FE
0x1800267f7  mov     edx, 1Fh
0x1800267fc  jmp     short loc_180026823
0x1800267fe  mov     rcx, [rsp+58h+arg_18]
0x180026803  mov     rax, [rcx]
0x180026806  mov     r9, rdi
0x180026809  mov     r8, rsi
0x18002680c  mov     rdx, rbp
0x18002680f  mov     rax, [rax+20h]
0x180026813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026818  mov     ebx, eax
0x18002681a  test    eax, eax
0x18002681c  jns     short loc_180026839
0x18002681e  mov     edx, 20h ; ' '; void *
0x180026823  lea     r8, aOnecoreuapInte_9; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x18002682a  mov     r9d, eax; char *
0x18002682d  mov     rcx, [rsp+58h]; this
0x180026832  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026837  jmp     short loc_18002683B
0x180026839  xor     ebx, ebx
0x18002683b  lea     rcx, [rsp+58h+arg_18]
0x180026840  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026845  mov     eax, ebx
0x180026847  add     rsp, 38h
0x18002684b  pop     rdi
0x18002684c  pop     rsi
0x18002684d  pop     rbp
0x18002684e  pop     rbx
0x18002684f  retn
```
