# ConvertItemToUNCPath(IShellItem *,ushort * *)

- ea: `0x180043d8c`
- end: `0x180043e5f`
- name: `?ConvertItemToUNCPath@@YAJPEAUIShellItem@@PEAPEAG@Z`
- size: `211`
- prototype: `__int64 __fastcall(struct IShellItem *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180043ef4`
- `0x1800440f4`

## callees

- `0x180006c94`
- `0x180043d8c`
- `0x180044628`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043e33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043e4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043e33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043e4f`

## pseudocode

```c
__int64 __fastcall ConvertItemToUNCPath(struct IShellItem *a1, unsigned __int16 **a2)
{
  struct IShellItemVtbl *lpVtbl; // rax
  int v5; // ebx
  const struct _GUID *v6; // rdx
  struct IShellItemVtbl *v7; // rax
  LPVOID pv; // [rsp+40h] [rbp+8h] BYREF
  unsigned __int16 *v10; // [rsp+48h] [rbp+10h] BYREF
  void *v11; // [rsp+50h] [rbp+18h] BYREF

  *a2 = 0;
  lpVtbl = a1->lpVtbl;
  v10 = 0;
  v5 = ((__int64 (__fastcall *)(struct IShellItem *, __int64, unsigned __int16 **))lpVtbl->GetDisplayName)(
         a1,
         2147844096LL,
         &v10);
  if ( v5 >= 0 )
  {
    v5 = PathConvertToUNC(v10, a2);
    if ( v5 < 0 )
    {
      v11 = 0;
      if ( SHGetTargetItem(a1, v6, &v11) >= 0 )
      {
        v7 = a1->lpVtbl;
        pv = 0;
        v5 = ((__int64 (__fastcall *)(struct IShellItem *, __int64, LPVOID *))v7->GetDisplayName)(a1, 2147844096LL, &pv);
        if ( v5 >= 0 )
        {
          v5 = PathConvertToUNC((const unsigned __int16 *)pv, a2);
          CoTaskMemFree(pv);
        }
        (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
      }
    }
    CoTaskMemFree(v10);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180043d8c  push    rbx
0x180043d8e  push    rsi
0x180043d8f  push    rdi
0x180043d90  sub     rsp, 20h
0x180043d94  mov     qword ptr [rdx], 0
0x180043d9b  lea     r8, [rsp+38h+arg_8]
0x180043da0  mov     rax, [rcx]
0x180043da3  mov     rsi, rdx
0x180043da6  mov     edx, 80058000h
0x180043dab  mov     [rsp+38h+arg_8], 0
0x180043db4  mov     rdi, rcx
0x180043db7  mov     rax, [rax+28h]
0x180043dbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043dc0  mov     ebx, eax
0x180043dc2  test    eax, eax
0x180043dc4  js      loc_180043E55
0x180043dca  mov     rcx, [rsp+38h+arg_8]; unsigned __int16 *
0x180043dcf  mov     rdx, rsi; unsigned __int16 **
0x180043dd2  call    ?PathConvertToUNC@@YAJPEBGPEAPEAG@Z; PathConvertToUNC(ushort const *,ushort * *)
0x180043dd7  mov     ebx, eax
0x180043dd9  test    eax, eax
0x180043ddb  jns     short loc_180043E4A
0x180043ddd  lea     r8, [rsp+38h+arg_10]; void **
0x180043de2  mov     [rsp+38h+arg_10], 0
0x180043deb  mov     rcx, rdi; struct IShellItem *
0x180043dee  call    ?SHGetTargetItem@@YAJPEAUIShellItem@@AEBU_GUID@@PEAPEAX@Z; SHGetTargetItem(IShellItem *,_GUID const &,void * *)
0x180043df3  test    eax, eax
0x180043df5  js      short loc_180043E4A
0x180043df7  mov     rax, [rdi]
0x180043dfa  lea     r8, [rsp+38h+pv]
0x180043dff  mov     edx, 80058000h
0x180043e04  mov     [rsp+38h+pv], 0
0x180043e0d  mov     rcx, rdi
0x180043e10  mov     rax, [rax+28h]
0x180043e14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e19  mov     ebx, eax
0x180043e1b  test    eax, eax
0x180043e1d  js      short loc_180043E39
0x180043e1f  mov     rcx, [rsp+38h+pv]; unsigned __int16 *
0x180043e24  mov     rdx, rsi; unsigned __int16 **
0x180043e27  call    ?PathConvertToUNC@@YAJPEBGPEAPEAG@Z; PathConvertToUNC(ushort const *,ushort * *)
0x180043e2c  mov     rcx, [rsp+38h+pv]; pv
0x180043e31  mov     ebx, eax
0x180043e33  call    cs:__imp_CoTaskMemFree
0x180043e39  mov     rcx, [rsp+38h+arg_10]
0x180043e3e  mov     rax, [rcx]
0x180043e41  mov     rax, [rax+10h]
0x180043e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e4a  mov     rcx, [rsp+38h+arg_8]; pv
0x180043e4f  call    cs:__imp_CoTaskMemFree
0x180043e55  mov     eax, ebx
0x180043e57  add     rsp, 20h
0x180043e5b  pop     rdi
0x180043e5c  pop     rsi
0x180043e5d  pop     rbx
0x180043e5e  retn
```
