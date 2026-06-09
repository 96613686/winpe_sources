# CPopupCommand::get_Label(ushort * *)

- ea: `0x1800029a0`
- end: `0x180002a92`
- name: `?get_Label@CPopupCommand@@UEAAJPEAPEAG@Z`
- size: `242`
- prototype: `__int64 __fastcall(CPopupCommand *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800025d8`
- `0x1800029a0`
- `0x180003100`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800029dc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800029dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002a14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002a14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a4e`

## pseudocode

```c
__int64 __fastcall CPopupCommand::get_Label(CPopupCommand *this, unsigned __int16 **a2)
{
  unsigned __int64 v3; // rdi
  unsigned __int64 v4; // rsi
  unsigned __int16 *v5; // rax
  signed int v6; // ebx
  signed int LastError; // eax
  unsigned __int16 **v9; // [rsp+20h] [rbp-D8h]
  unsigned __int64 *v10; // [rsp+28h] [rbp-D0h]
  unsigned int v11; // [rsp+30h] [rbp-C8h]
  WCHAR Buffer[64]; // [rsp+50h] [rbp-A8h] BYREF

  *a2 = 0;
  if ( LoadStringW((HINSTANCE)0x180000000LL, *((_DWORD *)this + 4), Buffer, 64) <= 0 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 >= 0 )
      return (unsigned int)-2147467259;
  }
  else
  {
    v3 = -1;
    do
      ++v3;
    while ( Buffer[v3] );
    v4 = v3 + 1;
    *a2 = 0;
    if ( v3 + 1 >= v3 && is_mul_ok(v4, 2u) )
    {
      v5 = (unsigned __int16 *)CoTaskMemAlloc(2 * v4);
      *a2 = v5;
      v6 = v5 == 0 ? 0x8007000E : 0;
      if ( v5 )
        StringCchCopyNExW(v5, v3 + 1, Buffer, v3, v9, v10, v11);
    }
    else
    {
      return (unsigned int)-2147024362;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800029a0  mov     [rsp+arg_10], rbx
0x1800029a5  push    rbp
0x1800029a6  push    rsi
0x1800029a7  push    rdi
0x1800029a8  sub     rsp, 0E0h
0x1800029af  mov     rax, cs:__security_cookie
0x1800029b6  xor     rax, rsp
0x1800029b9  mov     [rsp+0F8h+var_28], rax
0x1800029c1  xor     ebp, ebp
0x1800029c3  lea     r8, [rsp+0F8h+Buffer]; lpBuffer
0x1800029c8  mov     rbx, rdx
0x1800029cb  mov     [rdx], rbp
0x1800029ce  mov     edx, [rcx+10h]; uID
0x1800029d1  lea     rcx, cs:180000000h; hInstance
0x1800029d8  lea     r9d, [rbp+40h]; cchBufferMax
0x1800029dc  call    cs:__imp_LoadStringW
0x1800029e2  test    eax, eax
0x1800029e4  jle     short loc_180002A4E
0x1800029e6  lea     rax, [rsp+0F8h+Buffer]
0x1800029eb  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800029ef  inc     rdi
0x1800029f2  cmp     [rax+rdi*2], bp
0x1800029f6  jnz     short loc_1800029EF
0x1800029f8  lea     rsi, [rdi+1]
0x1800029fc  mov     [rbx], rbp
0x1800029ff  cmp     rsi, rdi
0x180002a02  jb      short loc_180002A47
0x180002a04  mov     eax, 2
0x180002a09  mul     rsi
0x180002a0c  test    rdx, rdx
0x180002a0f  jnz     short loc_180002A47
0x180002a11  mov     rcx, rax; cb
0x180002a14  call    cs:__imp_CoTaskMemAlloc
0x180002a1a  mov     [rbx], rax
0x180002a1d  mov     rcx, rax
0x180002a20  neg     rcx
0x180002a23  sbb     ebx, ebx
0x180002a25  not     ebx
0x180002a27  and     ebx, 8007000Eh
0x180002a2d  test    rax, rax
0x180002a30  jz      short loc_180002A6D
0x180002a32  mov     r9, rdi; unsigned __int64
0x180002a35  lea     r8, [rsp+0F8h+Buffer]; unsigned __int16 *
0x180002a3a  mov     rdx, rsi; unsigned __int64
0x180002a3d  mov     rcx, rax; unsigned __int16 *
0x180002a40  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x180002a45  jmp     short loc_180002A6D
0x180002a47  mov     ebx, 80070216h
0x180002a4c  jmp     short loc_180002A6D
0x180002a4e  call    cs:__imp_GetLastError
0x180002a54  mov     ebx, eax
0x180002a56  test    eax, eax
0x180002a58  jle     short loc_180002A63
0x180002a5a  movzx   ebx, ax
0x180002a5d  or      ebx, 80070000h
0x180002a63  test    ebx, ebx
0x180002a65  mov     eax, 80004005h
0x180002a6a  cmovns  ebx, eax
0x180002a6d  mov     eax, ebx
0x180002a6f  mov     rcx, [rsp+0F8h+var_28]
0x180002a77  xor     rcx, rsp; StackCookie
0x180002a7a  call    __security_check_cookie
0x180002a7f  mov     rbx, [rsp+0F8h+arg_10]
0x180002a87  add     rsp, 0E0h
0x180002a8e  pop     rdi
0x180002a8f  pop     rsi
0x180002a90  pop     rbp
0x180002a91  retn
```
