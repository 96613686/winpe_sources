# CMakeAvailableCmdStateHandler::_GetItemPath(IShellItem *,ushort * *,ulong,ulong *)

- ea: `0x18002bae4`
- end: `0x18002bbc0`
- name: `?_GetItemPath@CMakeAvailableCmdStateHandler@@AEAAJPEAUIShellItem@@PEAPEAGKPEAK@Z`
- size: `220`
- prototype: `int(CMakeAvailableCmdStateHandler *__hidden this, struct IShellItem *, unsigned __int16 **, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002c910`

## callees

- `0x180003c20`
- `0x180011654`
- `0x18002bae4`
- `0x1800321b8`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bb58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bb58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bb71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bb71`

## pseudocode

```c
__int64 __fastcall CMakeAvailableCmdStateHandler::_GetItemPath(
        CMakeAvailableCmdStateHandler *this,
        struct IShellItem *a2,
        unsigned __int16 **a3,
        __int64 a4,
        unsigned int *a5)
{
  struct IShellItemVtbl *lpVtbl; // rax
  int StringCopy; // ebx
  void *v9; // rdx
  LPVOID pv; // [rsp+30h] [rbp+8h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp+10h] BYREF

  pv = this;
  lpVtbl = a2->lpVtbl;
  pv = 0;
  StringCopy = ((__int64 (__fastcall *)(struct IShellItem *, __int64, LPVOID *))lpVtbl->GetDisplayName)(
                 a2,
                 2147844096LL,
                 &pv);
  if ( StringCopy >= 0 )
  {
    hMem = 0;
    if ( (unsigned int)GetRemotePath((const unsigned __int16 *)pv, (unsigned __int16 **)&hMem) )
    {
      StringCopy = CscUtil_CreateStringCopy((const unsigned __int16 *)pv, a3);
    }
    else
    {
      StringCopy = CscUtil_CreateStringCopy((const unsigned __int16 *)hMem, a3);
      LocalFree(hMem);
    }
    CoTaskMemFree(pv);
    if ( StringCopy >= 0 )
    {
      if ( a5 )
      {
        StringCopy = ((__int64 (__fastcall *)(struct IShellItem *, __int64))a2->lpVtbl->GetAttributes)(a2, 1073809408);
        if ( StringCopy < 0 )
        {
          CscUtil_HeapFree(*a3, v9);
          *a3 = 0;
        }
      }
    }
  }
  return (unsigned int)StringCopy;
}

```

## disassembly

```asm
0x18002bae4  mov     r11, rsp
0x18002bae7  mov     [r11+18h], rbx
0x18002baeb  mov     [r11+20h], rsi
0x18002baef  mov     [r11+8], rcx
0x18002baf3  push    rdi
0x18002baf4  sub     rsp, 20h
0x18002baf8  mov     rax, [rdx]
0x18002bafb  mov     rsi, rdx
0x18002bafe  mov     rdi, r8
0x18002bb01  mov     qword ptr [r11+8], 0
0x18002bb09  lea     r8, [r11+8]
0x18002bb0d  mov     edx, 80058000h
0x18002bb12  mov     rcx, rsi
0x18002bb15  mov     rax, [rax+28h]
0x18002bb19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb1e  mov     ebx, eax
0x18002bb20  test    eax, eax
0x18002bb22  js      loc_18002BBAE
0x18002bb28  mov     rcx, [rsp+28h+pv]; unsigned __int16 *
0x18002bb2d  lea     rdx, [rsp+28h+hMem]; unsigned __int16 **
0x18002bb32  mov     [rsp+28h+hMem], 0
0x18002bb3b  call    ?GetRemotePath@@YAJPEBGPEAPEAG@Z; GetRemotePath(ushort const *,ushort * *)
0x18002bb40  mov     rdx, rdi; unsigned __int16 **
0x18002bb43  test    eax, eax
0x18002bb45  jnz     short loc_18002BB60
0x18002bb47  mov     rcx, [rsp+28h+hMem]; unsigned __int16 *
0x18002bb4c  call    ?CscUtil_CreateStringCopy@@YAJPEBGPEAPEAG@Z; CscUtil_CreateStringCopy(ushort const *,ushort * *)
0x18002bb51  mov     rcx, [rsp+28h+hMem]; hMem
0x18002bb56  mov     ebx, eax
0x18002bb58  call    cs:__imp_LocalFree
0x18002bb5e  jmp     short loc_18002BB6C
0x18002bb60  mov     rcx, [rsp+28h+pv]; unsigned __int16 *
0x18002bb65  call    ?CscUtil_CreateStringCopy@@YAJPEBGPEAPEAG@Z; CscUtil_CreateStringCopy(ushort const *,ushort * *)
0x18002bb6a  mov     ebx, eax
0x18002bb6c  mov     rcx, [rsp+28h+pv]; pv
0x18002bb71  call    cs:__imp_CoTaskMemFree
0x18002bb77  test    ebx, ebx
0x18002bb79  js      short loc_18002BBAE
0x18002bb7b  mov     r8, [rsp+28h+arg_20]
0x18002bb80  test    r8, r8
0x18002bb83  jz      short loc_18002BBAE
0x18002bb85  mov     rax, [rsi]
0x18002bb88  mov     edx, 40010800h
0x18002bb8d  mov     rcx, rsi
0x18002bb90  mov     rax, [rax+30h]
0x18002bb94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb99  mov     ebx, eax
0x18002bb9b  test    eax, eax
0x18002bb9d  jns     short loc_18002BBAE
0x18002bb9f  mov     rcx, [rdi]; lpMem
0x18002bba2  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x18002bba7  mov     qword ptr [rdi], 0
0x18002bbae  mov     rsi, [rsp+28h+arg_18]
0x18002bbb3  mov     eax, ebx
0x18002bbb5  mov     rbx, [rsp+28h+arg_10]
0x18002bbba  add     rsp, 20h
0x18002bbbe  pop     rdi
0x18002bbbf  retn
```
