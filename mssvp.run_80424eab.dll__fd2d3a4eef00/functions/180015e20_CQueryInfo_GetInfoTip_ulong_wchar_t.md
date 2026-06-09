# CQueryInfo::GetInfoTip(ulong,wchar_t * *)

- ea: `0x180015e20`
- end: `0x180015e99`
- name: `?GetInfoTip@CQueryInfo@@UEAAJKPEAPEA_W@Z`
- size: `121`
- prototype: `__int64 __fastcall(CQueryInfo *__hidden this, unsigned int, wchar_t **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004080`
- `0x180015e20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015e4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015e4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015e81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015e81`

## pseudocode

```c
__int64 __fastcall CQueryInfo::GetInfoTip(CQueryInfo *this, __int64 a2, LPVOID *a3)
{
  __int64 v3; // rdx
  __int64 v6; // rax
  unsigned __int64 v7; // rsi
  wchar_t *v8; // rax
  int v9; // ebx

  v3 = *((_QWORD *)this + 8);
  if ( !v3 )
    return (unsigned int)-2147467259;
  v6 = -1;
  do
    ++v6;
  while ( *(_WORD *)(v3 + 2 * v6) );
  v7 = (unsigned int)(v6 + 1);
  v8 = (wchar_t *)CoTaskMemAlloc(2 * v7);
  *a3 = v8;
  if ( v8 )
  {
    v9 = StringCchCopyW(v8, v7, *((const wchar_t **)this + 8));
    if ( v9 >= 0 )
      return (unsigned int)v9;
  }
  else
  {
    v9 = -2147024882;
  }
  if ( *a3 )
    CoTaskMemFree(*a3);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180015e20  push    rbx
0x180015e22  push    rbp
0x180015e23  push    rsi
0x180015e24  push    rdi
0x180015e25  sub     rsp, 28h
0x180015e29  mov     rdx, [rcx+40h]
0x180015e2d  xor     ebp, ebp
0x180015e2f  mov     rdi, r8
0x180015e32  mov     rbx, rcx
0x180015e35  test    rdx, rdx
0x180015e38  jz      short loc_180015E89
0x180015e3a  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015e3e  inc     rax
0x180015e41  cmp     [rdx+rax*2], bp
0x180015e45  jnz     short loc_180015E3E
0x180015e47  inc     eax
0x180015e49  mov     esi, eax
0x180015e4b  lea     rcx, [rax+rax]; cb
0x180015e4f  call    cs:__imp_CoTaskMemAlloc
0x180015e55  mov     [rdi], rax
0x180015e58  test    rax, rax
0x180015e5b  jnz     short loc_180015E64
0x180015e5d  mov     ebx, 8007000Eh
0x180015e62  jmp     short loc_180015E79
0x180015e64  mov     r8, [rbx+40h]; wchar_t *
0x180015e68  mov     rdx, rsi; unsigned __int64
0x180015e6b  mov     rcx, rax; wchar_t *
0x180015e6e  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180015e73  mov     ebx, eax
0x180015e75  test    eax, eax
0x180015e77  jns     short loc_180015E8E
0x180015e79  mov     rcx, [rdi]; pv
0x180015e7c  test    rcx, rcx
0x180015e7f  jz      short loc_180015E8E
0x180015e81  call    cs:__imp_CoTaskMemFree
0x180015e87  jmp     short loc_180015E8E
0x180015e89  mov     ebx, 80004005h
0x180015e8e  mov     eax, ebx
0x180015e90  add     rsp, 28h
0x180015e94  pop     rdi
0x180015e95  pop     rsi
0x180015e96  pop     rbp
0x180015e97  pop     rbx
0x180015e98  retn
```
