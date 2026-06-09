# ISAPI_REQUEST::GetChannelBindingToken(uchar * *,ulong *)

- ea: `0x18000b830`
- end: `0x18000b8e8`
- name: `?GetChannelBindingToken@ISAPI_REQUEST@@UEAAJPEAPEAEPEAK@Z`
- size: `184`
- prototype: `__int64 __fastcall(ISAPI_REQUEST *__hidden this, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000b830`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ISAPI_REQUEST::GetChannelBindingToken(ISAPI_REQUEST *this, unsigned __int8 **a2, unsigned int *a3)
{
  __int64 v3; // rcx
  __int64 v6; // rsi
  __int64 result; // rax
  __int64 v8; // [rsp+40h] [rbp+8h] BYREF
  __int64 v9; // [rsp+58h] [rbp+20h] BYREF

  v3 = *((_QWORD *)this + 3);
  v9 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 24LL))(v3);
  v8 = 0;
  result = (*(__int64 (__fastcall **)(struct IHttpServer *, _QWORD, __int64 *))(*(_QWORD *)g_pGlobalInfo + 200LL))(
             g_pGlobalInfo,
             0,
             &v8);
  if ( (int)result >= 0 )
  {
    result = (*(__int64 (__fastcall **)(__int64, GUID *, __int64, GUID *, __int64 *))(*(_QWORD *)v8 + 224LL))(
               v8,
               &GUID_e8698f7e_576e_4cac_a309_67435355faef,
               v6,
               &GUID_d9244ae1_51f8_4aa1_a66d_19277c33e610,
               &v9);
    if ( (int)result >= 0 )
      return (*(__int64 (__fastcall **)(__int64, unsigned __int8 **, unsigned int *))(*(_QWORD *)v9 + 192LL))(
               v9,
               a2,
               a3);
  }
  return result;
}

```

## disassembly

```asm
0x18000b830  mov     [rsp+arg_8], rbx
0x18000b835  mov     [rsp+arg_10], rsi
0x18000b83a  push    rdi
0x18000b83b  sub     rsp, 30h
0x18000b83f  mov     rcx, [rcx+18h]
0x18000b843  mov     rbx, r8
0x18000b846  mov     [rsp+38h+arg_18], 0
0x18000b84f  mov     rdi, rdx
0x18000b852  mov     rax, [rcx]
0x18000b855  mov     rax, [rax+18h]
0x18000b859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b85e  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x18000b865  lea     r8, [rsp+38h+arg_0]
0x18000b86a  mov     rsi, rax
0x18000b86d  mov     [rsp+38h+arg_0], 0
0x18000b876  mov     rdx, [rcx]
0x18000b879  mov     rax, [rdx+0C8h]
0x18000b880  xor     edx, edx
0x18000b882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b887  test    eax, eax
0x18000b889  js      short loc_18000B8D8
0x18000b88b  mov     rcx, [rsp+38h+arg_0]
0x18000b890  lea     rdx, [rsp+38h+arg_18]
0x18000b895  mov     [rsp+38h+var_18], rdx
0x18000b89a  lea     r9, _GUID_d9244ae1_51f8_4aa1_a66d_19277c33e610
0x18000b8a1  mov     r8, rsi
0x18000b8a4  lea     rdx, _GUID_e8698f7e_576e_4cac_a309_67435355faef
0x18000b8ab  mov     rax, [rcx]
0x18000b8ae  mov     rax, [rax+0E0h]
0x18000b8b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8ba  test    eax, eax
0x18000b8bc  js      short loc_18000B8D8
0x18000b8be  mov     rcx, [rsp+38h+arg_18]
0x18000b8c3  mov     r8, rbx
0x18000b8c6  mov     rdx, rdi
0x18000b8c9  mov     rax, [rcx]
0x18000b8cc  mov     rax, [rax+0C0h]
0x18000b8d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8d8  mov     rbx, [rsp+38h+arg_8]
0x18000b8dd  mov     rsi, [rsp+38h+arg_10]
0x18000b8e2  add     rsp, 30h
0x18000b8e6  pop     rdi
0x18000b8e7  retn
```
