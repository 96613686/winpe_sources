# CEnumNetConnectionLuaImpl::QueryInterfaceINetLua(void *,_GUID const &,void * *,unsigned __int64)

- ea: `0x18001aa80`
- end: `0x18001ab11`
- name: `?QueryInterfaceINetLua@CEnumNetConnectionLuaImpl@@SAJPEAXAEBU_GUID@@PEAPEAX_K@Z`
- size: `145`
- prototype: `static int(void *, const struct _GUID *, void **, unsigned __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18001aa80`
- `0x180065010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18001aaf9`
- `ole32!CoTaskMemFree` at `0x18001aaf9`
- `ole32!StringFromCLSID` at `0x18001aaea`
- `ole32!StringFromCLSID` at `0x18001aaea`

## pseudocode

```c
__int64 __fastcall CEnumNetConnectionLuaImpl::QueryInterfaceINetLua(
        unsigned __int64 a1,
        const struct _GUID *a2,
        void **a3)
{
  __int64 v4; // rax
  unsigned int v5; // edi
  void *v6; // rbx
  LPOLESTR lpsz; // [rsp+30h] [rbp+8h] BYREF

  v4 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_INetLua.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_INetLua.Data1 )
    v4 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_INetLua.Data4;
  if ( v4 )
  {
    lpsz = 0;
    v5 = -2147467262;
    if ( StringFromCLSID(a2, &lpsz) >= 0 )
      CoTaskMemFree(lpsz);
  }
  else
  {
    v5 = 0;
    v6 = (void *)((a1 + 8) & ((unsigned __int128)-(__int128)a1 >> 64));
    (*(void (__fastcall **)(void *, const struct _GUID *, void **, const struct _GUID *))(*(_QWORD *)v6 + 8LL))(
      v6,
      a2,
      a3,
      a2);
    *a3 = v6;
  }
  return v5;
}

```

## disassembly

```asm
0x18001aa80  mov     [rsp+arg_8], rbx
0x18001aa85  mov     [rsp+arg_10], rsi
0x18001aa8a  push    rdi
0x18001aa8b  sub     rsp, 20h
0x18001aa8f  mov     rax, [rdx]
0x18001aa92  mov     rsi, r8
0x18001aa95  sub     rax, qword ptr cs:IID_INetLua.Data1
0x18001aa9c  mov     r9, rdx
0x18001aa9f  jnz     short loc_18001AAAC
0x18001aaa1  mov     rax, [rdx+8]
0x18001aaa5  sub     rax, qword ptr cs:IID_INetLua.Data4
0x18001aaac  test    rax, rax
0x18001aaaf  jnz     short loc_18001AAD4
0x18001aab1  lea     rax, [rcx+8]
0x18001aab5  xor     edi, edi
0x18001aab7  neg     rcx
0x18001aaba  sbb     rbx, rbx
0x18001aabd  and     rbx, rax
0x18001aac0  mov     rcx, rbx
0x18001aac3  mov     rax, [rbx]
0x18001aac6  mov     rax, [rax+8]
0x18001aaca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aacf  mov     [rsi], rbx
0x18001aad2  jmp     short loc_18001AAFF
0x18001aad4  lea     rdx, [rsp+28h+lpsz]; lplpsz
0x18001aad9  mov     [rsp+28h+lpsz], 0
0x18001aae2  mov     rcx, r9; rclsid
0x18001aae5  mov     edi, 80004002h
0x18001aaea  call    cs:__imp_StringFromCLSID
0x18001aaf0  test    eax, eax
0x18001aaf2  js      short loc_18001AAFF
0x18001aaf4  mov     rcx, [rsp+28h+lpsz]; pv
0x18001aaf9  call    cs:__imp_CoTaskMemFree
0x18001aaff  mov     rbx, [rsp+28h+arg_8]
0x18001ab04  mov     eax, edi
0x18001ab06  mov     rsi, [rsp+28h+arg_10]
0x18001ab0b  add     rsp, 20h
0x18001ab0f  pop     rdi
0x18001ab10  retn
```
