# FileStream::Init(void *,ulong,ushort const *)

- ea: `0x18006a8e0`
- end: `0x18006a986`
- name: `?Init@FileStream@@UEAAJPEAXKPEBG@Z`
- size: `166`
- prototype: `int(FileStream *__hidden this, void *, unsigned int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000cc00`
- `0x18006a8e0`
- `0x18006aafc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006a941`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006a941`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a974`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a974`

## pseudocode

```c
__int64 __fastcall FileStream::Init(FileStream *this, const unsigned __int16 *a2, int a3, GpRuntime *a4)
{
  unsigned int v4; // ebx
  void *v7; // rcx
  const unsigned __int16 *v9; // r14
  GpRuntime *v10; // rax
  unsigned __int64 v11; // r9

  v4 = 0;
  if ( !*((_DWORD *)this + 12) )
    return 2147500037LL;
  *((_QWORD *)this + 9) = a2;
  *((_DWORD *)this + 16) = a3;
  v7 = (void *)*((_QWORD *)this + 7);
  if ( v7 )
  {
    CoTaskMemFree(v7);
    *((_QWORD *)this + 7) = 0;
  }
  if ( a4 )
  {
    v9 = (const unsigned __int16 *)(GpRuntime::UnicodeStringLength(a4, a2) + 1);
    v10 = (GpRuntime *)CoTaskMemAlloc(2LL * (_QWORD)v9);
    *((_QWORD *)this + 7) = v10;
    if ( v10 )
      GpRuntime::UnicodeStringCopyCount(v10, (unsigned __int16 *)a4, v9, v11);
    else
      return (unsigned int)-2147287032;
  }
  return v4;
}

```

## disassembly

```asm
0x18006a8e0  mov     [rsp+arg_0], rbx
0x18006a8e5  mov     [rsp+arg_8], rsi
0x18006a8ea  mov     [rsp+arg_10], rdi
0x18006a8ef  push    r14
0x18006a8f1  sub     rsp, 20h
0x18006a8f5  xor     ebx, ebx
0x18006a8f7  mov     rsi, r9
0x18006a8fa  mov     rdi, rcx
0x18006a8fd  cmp     [rcx+30h], ebx
0x18006a900  jz      short loc_18006A96D
0x18006a902  mov     [rcx+48h], rdx
0x18006a906  mov     [rcx+40h], r8d
0x18006a90a  mov     rcx, [rcx+38h]; pv
0x18006a90e  test    rcx, rcx
0x18006a911  jnz     short loc_18006A974
0x18006a913  test    rsi, rsi
0x18006a916  jnz     short loc_18006A931
0x18006a918  mov     eax, ebx
0x18006a91a  mov     rbx, [rsp+28h+arg_0]
0x18006a91f  mov     rsi, [rsp+28h+arg_8]
0x18006a924  mov     rdi, [rsp+28h+arg_10]
0x18006a929  add     rsp, 20h
0x18006a92d  pop     r14
0x18006a92f  retn
0x18006a931  mov     rcx, rsi; this
0x18006a934  call    ?UnicodeStringLength@GpRuntime@@YA_KPEBG@Z; GpRuntime::UnicodeStringLength(ushort const *)
0x18006a939  lea     r14, [rax+1]
0x18006a93d  lea     rcx, [r14+r14]; cb
0x18006a941  call    cs:__imp_CoTaskMemAlloc
0x18006a948  nop     dword ptr [rax+rax+00h]
0x18006a94d  mov     [rdi+38h], rax
0x18006a951  test    rax, rax
0x18006a954  jz      short loc_18006A966
0x18006a956  mov     r8, r14; unsigned __int16 *
0x18006a959  mov     rdx, rsi; unsigned __int16 *
0x18006a95c  mov     rcx, rax; this
0x18006a95f  call    ?UnicodeStringCopyCount@GpRuntime@@YAXPEAGPEBG_K@Z; GpRuntime::UnicodeStringCopyCount(ushort *,ushort const *,unsigned __int64)
0x18006a964  jmp     short loc_18006A918
0x18006a966  mov     ebx, 80030008h
0x18006a96b  jmp     short loc_18006A918
0x18006a96d  mov     eax, 80004005h
0x18006a972  jmp     short loc_18006A91A
0x18006a974  call    cs:__imp_CoTaskMemFree
0x18006a97b  nop     dword ptr [rax+rax+00h]
0x18006a980  mov     [rdi+38h], rbx
0x18006a984  jmp     short loc_18006A913
```
