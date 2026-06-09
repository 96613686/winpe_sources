# PREAMBLE_LIST::WriteCommonWhitespace(IXmlWriter *,PREAMBLE_ENTRY *)

- ea: `0x180021f78`
- end: `0x180022063`
- name: `?WriteCommonWhitespace@PREAMBLE_LIST@@QEAAJPEAUIXmlWriter@@PEAUPREAMBLE_ENTRY@@@Z`
- size: `235`
- prototype: `__int64 __fastcall(PREAMBLE_LIST *__hidden this, struct IXmlWriter *, struct PREAMBLE_ENTRY *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18002195c`

## callees

- `0x180021f78`
- `0x180059bea`
- `0x180059c30`
- `0x18005b010`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18002203e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002203e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002201c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002201c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180021fbf`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180021fbf`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180021fe1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180021fe1`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180022001`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180022001`

## pseudocode

```c
__int64 __fastcall PREAMBLE_LIST::WriteCommonWhitespace(
        PREAMBLE_LIST *this,
        struct IXmlWriter *a2,
        struct PREAMBLE_ENTRY *a3)
{
  int v5; // ebx
  unsigned __int16 i; // di
  HRESULT (__stdcall *WriteWhitespace)(IXmlWriter *, LPCWSTR); // rbx
  unsigned __int16 *Str; // rax
  _BYTE v10[64]; // [rsp+20h] [rbp-278h] BYREF
  unsigned __int16 v11[256]; // [rsp+60h] [rbp-238h] BYREF

  memset_0(v11, 0, sizeof(v11));
  STRU::STRU((STRU *)v10, v11, 0x100u);
  if ( a2 && a3 && *(_WORD *)a3 == 5 )
  {
    v5 = STRU::Copy((STRU *)v10, L"\n");
    if ( v5 >= 0 )
    {
      for ( i = 0; i < *((_WORD *)a3 + 1); ++i )
      {
        v5 = STRU::Append((STRU *)v10, L" ");
        if ( v5 < 0 )
          goto LABEL_11;
      }
      WriteWhitespace = a2->lpVtbl->WriteWhitespace;
      Str = STRU::QueryStr((STRU *)v10);
      v5 = ((__int64 (__fastcall *)(struct IXmlWriter *, unsigned __int16 *))WriteWhitespace)(a2, Str);
    }
  }
  else
  {
    v5 = -2147024809;
  }
LABEL_11:
  STRU::~STRU((STRU *)v10);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180021f78  push    rbx
0x180021f7a  push    rsi
0x180021f7b  push    rdi
0x180021f7c  push    r14
0x180021f7e  sub     rsp, 278h
0x180021f85  mov     rax, cs:__security_cookie
0x180021f8c  xor     rax, rsp
0x180021f8f  mov     [rsp+298h+var_38], rax
0x180021f97  mov     rsi, r8
0x180021f9a  lea     rcx, [rsp+298h+var_238]; void *
0x180021f9f  mov     r14, rdx
0x180021fa2  mov     r8d, 200h; Size
0x180021fa8  xor     edx, edx; Val
0x180021faa  call    memset_0
0x180021faf  mov     r8d, 100h
0x180021fb5  lea     rdx, [rsp+298h+var_238]
0x180021fba  lea     rcx, [rsp+298h+var_278]
0x180021fbf  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180021fc5  test    r14, r14
0x180021fc8  jz      short loc_180022034
0x180021fca  test    rsi, rsi
0x180021fcd  jz      short loc_180022034
0x180021fcf  cmp     word ptr [rsi], 5
0x180021fd3  jnz     short loc_180022034
0x180021fd5  lea     rdx, asc_180060844; "\n"
0x180021fdc  lea     rcx, [rsp+298h+var_278]
0x180021fe1  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180021fe7  mov     ebx, eax
0x180021fe9  test    eax, eax
0x180021feb  js      short loc_180022039
0x180021fed  xor     edi, edi
0x180021fef  lea     rcx, [rsp+298h+var_278]
0x180021ff4  cmp     di, [rsi+2]
0x180021ff8  jnb     short loc_180022012
0x180021ffa  lea     rdx, asc_180060848; " "
0x180022001  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180022007  mov     ebx, eax
0x180022009  test    eax, eax
0x18002200b  js      short loc_180022039
0x18002200d  inc     di
0x180022010  jmp     short loc_180021FEF
0x180022012  mov     rax, [r14]
0x180022015  mov     rbx, [rax+0F0h]
0x18002201c  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180022022  mov     rdx, rax
0x180022025  mov     rcx, r14
0x180022028  mov     rax, rbx
0x18002202b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022030  mov     ebx, eax
0x180022032  jmp     short loc_180022039
0x180022034  mov     ebx, 80070057h
0x180022039  lea     rcx, [rsp+298h+var_278]
0x18002203e  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180022044  mov     eax, ebx
0x180022046  mov     rcx, [rsp+298h+var_38]
0x18002204e  xor     rcx, rsp; StackCookie
0x180022051  call    __security_check_cookie
0x180022056  add     rsp, 278h
0x18002205d  pop     r14
0x18002205f  pop     rdi
0x180022060  pop     rsi
0x180022061  pop     rbx
0x180022062  retn
```
