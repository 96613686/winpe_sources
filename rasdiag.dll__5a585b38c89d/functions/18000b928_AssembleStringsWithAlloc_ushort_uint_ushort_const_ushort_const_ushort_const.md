# AssembleStringsWithAlloc(ushort * *,uint,ushort const *,ushort const *,ushort const *)

- ea: `0x18000b928`
- end: `0x18000bae6`
- name: `?AssembleStringsWithAlloc@@YAJPEAPEAGIPEBG11@Z`
- size: `446`
- prototype: `__int64 __fastcall(unsigned __int16 **, __int64, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007f20`
- `0x180009630`

## callees

- `0x18000b928`
- `0x18000cb2c`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000b96c`
- `KERNEL32!SetLastError` at `0x18000b9df`
- `KERNEL32!SetLastError` at `0x18000ba47`
- `KERNEL32!SetLastError` at `0x18000b96c`
- `KERNEL32!SetLastError` at `0x18000b9df`
- `KERNEL32!SetLastError` at `0x18000ba47`
- `KERNEL32!GetLastError` at `0x18000b99e`
- `KERNEL32!GetLastError` at `0x18000ba10`
- `KERNEL32!GetLastError` at `0x18000b99e`
- `KERNEL32!GetLastError` at `0x18000ba10`
- `USER32!LoadStringW` at `0x18000b98e`
- `USER32!LoadStringW` at `0x18000ba00`
- `USER32!LoadStringW` at `0x18000b98e`
- `USER32!LoadStringW` at `0x18000ba00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b955`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b9c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ba30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b955`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b9c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ba30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b9ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ba1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ba60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ba79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000baac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bac5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b9ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ba1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ba60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ba79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000baac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bac5`

## pseudocode

```c
__int64 __fastcall AssembleStringsWithAlloc(
        unsigned __int16 **a1,
        __int64 a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  unsigned __int16 *v7; // rbx
  WCHAR *v8; // rax
  unsigned __int16 *v9; // rdi
  WCHAR *v10; // rax
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rbp

  v7 = a4;
  if ( (unsigned __int64)a3 >= 0x10000 )
  {
    v9 = a3;
  }
  else
  {
    v8 = (WCHAR *)CoTaskMemAlloc(0x800u);
    v9 = v8;
    if ( v8 )
    {
      if ( !LoadStringW(hInstance, (unsigned __int16)a3, v8, 1024) )
      {
        GetLastError();
        CoTaskMemFree(v9);
        v9 = 0;
      }
    }
    else
    {
      SetLastError(8u);
    }
  }
  if ( (unsigned __int64)a4 < 0x10000 )
  {
    v10 = (WCHAR *)CoTaskMemAlloc(0x800u);
    v7 = v10;
    if ( v10 )
    {
      if ( !LoadStringW(hInstance, (unsigned __int16)a4, v10, 1024) )
      {
        GetLastError();
        CoTaskMemFree(v7);
        v7 = 0;
      }
    }
    else
    {
      SetLastError(8u);
    }
  }
  v11 = (unsigned __int16 *)CoTaskMemAlloc(0x800u);
  v12 = v11;
  if ( v11 )
  {
    StringCchPrintfW(v11, 0x400u, v9, v7);
    if ( (unsigned __int64)a3 < 0x10000 && v9 )
      CoTaskMemFree(v9);
    if ( (unsigned __int64)a4 < 0x10000 && v7 )
      CoTaskMemFree(v7);
    *a1 = v12;
    return 0;
  }
  else
  {
    SetLastError(8u);
    if ( (unsigned __int64)a3 < 0x10000 && v9 )
      CoTaskMemFree(v9);
    if ( (unsigned __int64)a4 < 0x10000 )
    {
      if ( v7 )
        CoTaskMemFree(v7);
    }
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18000b928  push    rbx
0x18000b92a  push    rbp
0x18000b92b  push    rsi
0x18000b92c  push    rdi
0x18000b92d  push    r12
0x18000b92f  push    r14
0x18000b931  push    r15
0x18000b933  sub     rsp, 20h
0x18000b937  mov     r12d, 10000h
0x18000b93d  mov     rsi, r9
0x18000b940  mov     r14, r8
0x18000b943  mov     r15, rcx
0x18000b946  mov     rbx, r9
0x18000b949  mov     ebp, 800h
0x18000b94e  cmp     r8, r12
0x18000b951  jnb     short loc_18000B9BD
0x18000b953  mov     ecx, ebp; cb
0x18000b955  call    cs:__imp_CoTaskMemAlloc
0x18000b95c  nop     dword ptr [rax+rax+00h]
0x18000b961  mov     rdi, rax
0x18000b964  test    rax, rax
0x18000b967  jnz     short loc_18000B97A
0x18000b969  lea     ecx, [rax+8]; dwErrCode
0x18000b96c  call    cs:__imp_SetLastError
0x18000b973  nop     dword ptr [rax+rax+00h]
0x18000b978  jmp     short loc_18000B9C0
0x18000b97a  mov     rcx, cs:hInstance; hInstance
0x18000b981  mov     r9d, 400h; cchBufferMax
0x18000b987  movzx   edx, r14w; uID
0x18000b98b  mov     r8, rdi; lpBuffer
0x18000b98e  call    cs:__imp_LoadStringW
0x18000b995  nop     dword ptr [rax+rax+00h]
0x18000b99a  test    eax, eax
0x18000b99c  jnz     short loc_18000B9C0
0x18000b99e  call    cs:__imp_GetLastError
0x18000b9a5  nop     dword ptr [rax+rax+00h]
0x18000b9aa  mov     rcx, rdi; pv
0x18000b9ad  call    cs:__imp_CoTaskMemFree
0x18000b9b4  nop     dword ptr [rax+rax+00h]
0x18000b9b9  xor     edi, edi
0x18000b9bb  jmp     short loc_18000B9C0
0x18000b9bd  mov     rdi, r14
0x18000b9c0  cmp     rsi, r12
0x18000b9c3  jnb     short loc_18000BA2D
0x18000b9c5  mov     rcx, rbp; cb
0x18000b9c8  call    cs:__imp_CoTaskMemAlloc
0x18000b9cf  nop     dword ptr [rax+rax+00h]
0x18000b9d4  mov     rbx, rax
0x18000b9d7  test    rax, rax
0x18000b9da  jnz     short loc_18000B9ED
0x18000b9dc  lea     ecx, [rax+8]; dwErrCode
0x18000b9df  call    cs:__imp_SetLastError
0x18000b9e6  nop     dword ptr [rax+rax+00h]
0x18000b9eb  jmp     short loc_18000BA2D
0x18000b9ed  mov     rcx, cs:hInstance; hInstance
0x18000b9f4  mov     r9d, 400h; cchBufferMax
0x18000b9fa  movzx   edx, si; uID
0x18000b9fd  mov     r8, rbx; lpBuffer
0x18000ba00  call    cs:__imp_LoadStringW
0x18000ba07  nop     dword ptr [rax+rax+00h]
0x18000ba0c  test    eax, eax
0x18000ba0e  jnz     short loc_18000BA2D
0x18000ba10  call    cs:__imp_GetLastError
0x18000ba17  nop     dword ptr [rax+rax+00h]
0x18000ba1c  mov     rcx, rbx; pv
0x18000ba1f  call    cs:__imp_CoTaskMemFree
0x18000ba26  nop     dword ptr [rax+rax+00h]
0x18000ba2b  xor     ebx, ebx
0x18000ba2d  mov     rcx, rbp; cb
0x18000ba30  call    cs:__imp_CoTaskMemAlloc
0x18000ba37  nop     dword ptr [rax+rax+00h]
0x18000ba3c  mov     rbp, rax
0x18000ba3f  test    rax, rax
0x18000ba42  jnz     short loc_18000BA8C
0x18000ba44  lea     ecx, [rax+8]; dwErrCode
0x18000ba47  call    cs:__imp_SetLastError
0x18000ba4e  nop     dword ptr [rax+rax+00h]
0x18000ba53  cmp     r14, r12
0x18000ba56  jnb     short loc_18000BA6C
0x18000ba58  test    rdi, rdi
0x18000ba5b  jz      short loc_18000BA6C
0x18000ba5d  mov     rcx, rdi; pv
0x18000ba60  call    cs:__imp_CoTaskMemFree
0x18000ba67  nop     dword ptr [rax+rax+00h]
0x18000ba6c  cmp     rsi, r12
0x18000ba6f  jnb     short loc_18000BA85
0x18000ba71  test    rbx, rbx
0x18000ba74  jz      short loc_18000BA85
0x18000ba76  mov     rcx, rbx; pv
0x18000ba79  call    cs:__imp_CoTaskMemFree
0x18000ba80  nop     dword ptr [rax+rax+00h]
0x18000ba85  mov     eax, 8007000Eh
0x18000ba8a  jmp     short loc_18000BAD6
0x18000ba8c  mov     r9, rbx
0x18000ba8f  mov     r8, rdi; unsigned __int16 *
0x18000ba92  mov     edx, 400h; unsigned __int64
0x18000ba97  mov     rcx, rbp; unsigned __int16 *
0x18000ba9a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ba9f  cmp     r14, r12
0x18000baa2  jnb     short loc_18000BAB8
0x18000baa4  test    rdi, rdi
0x18000baa7  jz      short loc_18000BAB8
0x18000baa9  mov     rcx, rdi; pv
0x18000baac  call    cs:__imp_CoTaskMemFree
0x18000bab3  nop     dword ptr [rax+rax+00h]
0x18000bab8  cmp     rsi, r12
0x18000babb  jnb     short loc_18000BAD1
0x18000babd  test    rbx, rbx
0x18000bac0  jz      short loc_18000BAD1
0x18000bac2  mov     rcx, rbx; pv
0x18000bac5  call    cs:__imp_CoTaskMemFree
0x18000bacc  nop     dword ptr [rax+rax+00h]
0x18000bad1  mov     [r15], rbp
0x18000bad4  xor     eax, eax
0x18000bad6  add     rsp, 20h
0x18000bada  pop     r15
0x18000badc  pop     r14
0x18000bade  pop     r12
0x18000bae0  pop     rdi
0x18000bae1  pop     rsi
0x18000bae2  pop     rbp
0x18000bae3  pop     rbx
0x18000bae4  retn
```
