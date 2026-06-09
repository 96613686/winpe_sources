# CHtmlIFilter::GetCurFile(wchar_t * *)

- ea: `0x18001db50`
- end: `0x18001dbb4`
- name: `?GetCurFile@CHtmlIFilter@@UEAAJPEAPEA_W@Z`
- size: `100`
- prototype: `__int64 __fastcall(CHtmlIFilter *__hidden this, wchar_t **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800112e0`
- `0x18001db50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001db87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001db87`

## pseudocode

```c
int __fastcall CHtmlIFilter::GetCurFile(CHtmlIFilter *this, wchar_t **a2)
{
  __int64 v2; // r8
  __int64 v6; // rax
  unsigned __int64 v7; // rdi
  wchar_t *v8; // rax

  v2 = *((_QWORD *)this + 8);
  if ( !v2 )
    return -2147467259;
  v6 = -1;
  do
    ++v6;
  while ( *(_WORD *)(v2 + 2 * v6) );
  v7 = v6 + 1;
  v8 = (wchar_t *)CoTaskMemAlloc(2 * (v6 + 1));
  *a2 = v8;
  if ( v8 )
    return StringCchCopyW(v8, v7, *((const wchar_t **)this + 8));
  else
    return -2147024882;
}

```

## disassembly

```asm
0x18001db50  push    rbx
0x18001db52  push    rbp
0x18001db53  push    rsi
0x18001db54  push    rdi
0x18001db55  sub     rsp, 28h
0x18001db59  mov     r8, [rcx+40h]
0x18001db5d  xor     ebp, ebp
0x18001db5f  mov     rsi, rdx
0x18001db62  mov     rbx, rcx
0x18001db65  test    r8, r8
0x18001db68  jnz     short loc_18001DB71
0x18001db6a  mov     eax, 80004005h
0x18001db6f  jmp     short loc_18001DBAB
0x18001db71  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001db75  inc     rax
0x18001db78  cmp     [r8+rax*2], bp
0x18001db7d  jnz     short loc_18001DB75
0x18001db7f  lea     rdi, [rax+1]
0x18001db83  lea     rcx, [rdi+rdi]; cb
0x18001db87  call    cs:__imp_CoTaskMemAlloc
0x18001db8d  mov     [rsi], rax
0x18001db90  test    rax, rax
0x18001db93  jz      short loc_18001DBA6
0x18001db95  mov     r8, [rbx+40h]; wchar_t *
0x18001db99  mov     rdx, rdi; unsigned __int64
0x18001db9c  mov     rcx, rax; wchar_t *
0x18001db9f  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18001dba4  jmp     short loc_18001DBAB
0x18001dba6  mov     eax, 8007000Eh
0x18001dbab  add     rsp, 28h
0x18001dbaf  pop     rdi
0x18001dbb0  pop     rsi
0x18001dbb1  pop     rbp
0x18001dbb2  pop     rbx
0x18001dbb3  retn
```
