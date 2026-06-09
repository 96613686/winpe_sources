# diaCopyFileToCache(ushort *,void *,ushort *,ushort *,ushort *,ulong)

- ea: `0x180011e98`
- end: `0x180011fb1`
- name: `?diaCopyFileToCache@@YAHPEAGPEAX000K@Z`
- size: `281`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, HANDLE hProcess@<rdx>, unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18001a5fc`
- `0x18001b03c`

## callees

- `0x180011e98`
- `0x180011fb8`
- `0x180012e6c`
- `0x1801a16d0`
- `0x1801a82d0`
- `0x1801d6350`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180011f2e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180011f2e`

## string_xrefs

- `0x180011f22`: `cache*`

## pseudocode

```c
__int64 __fastcall diaCopyFileToCache(
        unsigned __int16 *a1,
        HANDLE hProcess,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned int a6)
{
  unsigned __int16 *v9; // rbx
  unsigned int v10; // edi
  const unsigned __int16 *v12; // r8
  int v13; // eax
  unsigned __int16 *v14; // r9
  unsigned __int16 v15[6]; // [rsp+30h] [rbp-468h] BYREF
  __int16 v16; // [rsp+3Ch] [rbp-45Ch] BYREF
  unsigned __int16 v17[264]; // [rsp+240h] [rbp-258h] BYREF

  v9 = a1;
  v10 = 0;
  while ( v9 )
  {
    if ( v9 == a3 )
      break;
    v9 = TokenFromSymbolPath(v9, v15, (int)a3);
    if ( v15[0] && !(unsigned int)_o__wcsnicmp(v15, L"cache*", 6) )
    {
      if ( !v16 || v16 == 42 )
      {
        if ( !word_1802B0BBA )
          SymSetHomeDirectoryW(0, 0);
        v12 = &word_1802B0BBA;
      }
      else
      {
        v12 = (const unsigned __int16 *)&v16;
      }
      wcscpy_s_ex(v17, 0x105u, v12);
      v13 = 0;
      v14 = 0;
      if ( !v10 )
      {
        v13 = a6;
        v14 = a5;
      }
      v10 = CopyToCache(hProcess, a4, v17, v14, v13);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x180011e98  push    rbx
0x180011e9a  push    rbp
0x180011e9b  push    rsi
0x180011e9c  push    rdi
0x180011e9d  push    r12
0x180011e9f  push    r14
0x180011ea1  push    r15
0x180011ea3  sub     rsp, 460h
0x180011eaa  mov     rax, cs:__security_cookie
0x180011eb1  xor     rax, rsp
0x180011eb4  mov     [rsp+498h+var_48], rax
0x180011ebc  mov     r15, [rsp+498h+arg_20]
0x180011ec4  xor     r12d, r12d
0x180011ec7  mov     r14, r9
0x180011eca  mov     rsi, r8
0x180011ecd  mov     rbp, rdx
0x180011ed0  mov     rbx, rcx
0x180011ed3  mov     edi, r12d
0x180011ed6  test    rcx, rcx
0x180011ed9  jnz     short loc_180011EFF
0x180011edb  mov     eax, edi
0x180011edd  mov     rcx, [rsp+498h+var_48]
0x180011ee5  xor     rcx, rsp; StackCookie
0x180011ee8  call    __security_check_cookie
0x180011eed  add     rsp, 460h
0x180011ef4  pop     r15
0x180011ef6  pop     r14
0x180011ef8  pop     r12
0x180011efa  pop     rdi
0x180011efb  pop     rsi
0x180011efc  pop     rbp
0x180011efd  pop     rbx
0x180011efe  retn
0x180011eff  cmp     rbx, rsi
0x180011f02  jz      short loc_180011EDB
0x180011f04  lea     rdx, [rsp+498h+var_468]; unsigned __int16 *
0x180011f09  mov     rcx, rbx; unsigned __int16 *
0x180011f0c  call    ?TokenFromSymbolPath@@YAPEAGPEBGPEAGH@Z; TokenFromSymbolPath(ushort const *,ushort *,int)
0x180011f11  mov     rbx, rax
0x180011f14  cmp     [rsp+498h+var_468], r12w
0x180011f1a  jz      short loc_180011F38
0x180011f1c  mov     r8d, 6
0x180011f22  lea     rdx, aCache_0; "cache*"
0x180011f29  lea     rcx, [rsp+498h+var_468]
0x180011f2e  call    cs:__imp__o__wcsnicmp
0x180011f34  test    eax, eax
0x180011f36  jz      short loc_180011F3F
0x180011f38  test    rbx, rbx
0x180011f3b  jnz     short loc_180011EFF
0x180011f3d  jmp     short loc_180011EDB
0x180011f3f  movzx   eax, [rsp+498h+var_45C]
0x180011f44  test    ax, ax
0x180011f47  jz      short loc_180011F56
0x180011f49  cmp     ax, 2Ah ; '*'
0x180011f4d  jz      short loc_180011F56
0x180011f4f  lea     r8, [rsp+498h+var_45C]
0x180011f54  jmp     short loc_180011F70
0x180011f56  cmp     cs:word_1802B0BBA, r12w
0x180011f5e  jnz     short loc_180011F69
0x180011f60  xor     edx, edx; dir
0x180011f62  xor     ecx, ecx; hProcess
0x180011f64  call    SymSetHomeDirectoryW
0x180011f69  lea     r8, word_1802B0BBA; unsigned __int16 *
0x180011f70  mov     edx, 105h; unsigned __int64
0x180011f75  lea     rcx, [rsp+498h+var_258]; unsigned __int16 *
0x180011f7d  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x180011f82  test    edi, edi
0x180011f84  lea     r8, [rsp+498h+var_258]; unsigned __int16 *
0x180011f8c  mov     eax, r12d
0x180011f8f  mov     r9, r12
0x180011f92  cmovz   eax, [rsp+498h+arg_28]
0x180011f9a  cmovz   r9, r15; unsigned __int16 *
0x180011f9e  mov     rdx, r14; unsigned __int16 *
0x180011fa1  mov     [rsp+498h+var_478], eax; int
0x180011fa5  mov     rcx, rbp; hProcess
0x180011fa8  call    ?CopyToCache@@YAHPEAXPEBG1PEAGH@Z; CopyToCache(void *,ushort const *,ushort const *,ushort *,int)
0x180011fad  mov     edi, eax
0x180011faf  jmp     short loc_180011F38
```
