# NdfRunDllHelpTopic(HWND__ *,HINSTANCE__ *,char const *,int)

- ea: `0x1800097b0`
- end: `0x180009854`
- name: `?NdfRunDllHelpTopic@@YAXPEAUHWND__@@PEAUHINSTANCE__@@PEBDH@Z`
- size: `164`
- prototype: `void __fastcall(HWND, HINSTANCE, const char *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callees

- `0x180002674`
- `0x1800097b0`
- `0x18000f468`
- `0x18001f652`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180009843`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009843`
- `KERNEL32!MultiByteToWideChar` at `0x1800097e2`
- `KERNEL32!MultiByteToWideChar` at `0x180009832`
- `KERNEL32!MultiByteToWideChar` at `0x1800097e2`
- `KERNEL32!MultiByteToWideChar` at `0x180009832`

## pseudocode

```c
void __fastcall NdfRunDllHelpTopic(HWND a1, HINSTANCE a2, const char *a3)
{
  int cchWideChar; // esi
  unsigned __int64 v5; // r14
  unsigned __int64 v6; // rax
  WCHAR *v7; // rax
  WCHAR *lpWideCharStr; // rdi

  if ( a3 )
  {
    cchWideChar = MultiByteToWideChar(0, 0, a3, -1, 0, 0);
    v5 = cchWideChar + 1;
    v6 = 2 * v5;
    if ( !is_mul_ok(v5, 2u) )
      v6 = -1;
    v7 = (WCHAR *)operator new[](v6, (const struct std::nothrow_t *)&std::nothrow);
    lpWideCharStr = v7;
    if ( v7 )
    {
      memset_0(v7, 0, 2 * v5);
      MultiByteToWideChar(0, 0, a3, -1, lpWideCharStr, cchWideChar);
      CNetDiagClient::ShowHelpTopic(lpWideCharStr);
      operator delete[](lpWideCharStr);
    }
  }
}

```

## disassembly

```asm
0x1800097b0  test    r8, r8
0x1800097b3  jz      locret_180009853
0x1800097b9  push    rbx
0x1800097ba  push    rbp
0x1800097bb  push    rsi
0x1800097bc  push    rdi
0x1800097bd  push    r14
0x1800097bf  sub     rsp, 30h
0x1800097c3  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800097c7  mov     [rsp+58h+cchWideChar], 0; cchWideChar
0x1800097cf  mov     r9d, ebp; cbMultiByte
0x1800097d2  mov     [rsp+58h+lpWideCharStr], 0; lpWideCharStr
0x1800097db  xor     edx, edx; dwFlags
0x1800097dd  xor     ecx, ecx; CodePage
0x1800097df  mov     rbx, r8
0x1800097e2  call    cs:__imp_MultiByteToWideChar
0x1800097e8  mov     esi, eax
0x1800097ea  lea     ecx, [rax+1]
0x1800097ed  movsxd  r14, ecx
0x1800097f0  lea     eax, [rbp+3]
0x1800097f3  mul     r14
0x1800097f6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800097fd  cmovb   rax, rbp
0x180009801  mov     rcx, rax; unsigned __int64
0x180009804  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180009809  mov     rdi, rax
0x18000980c  test    rax, rax
0x18000980f  jz      short loc_180009849
0x180009811  lea     r8, [r14+r14]; Size
0x180009815  xor     edx, edx; Val
0x180009817  mov     rcx, rax; void *
0x18000981a  call    memset_0
0x18000981f  mov     r9d, ebp; cbMultiByte
0x180009822  mov     [rsp+58h+cchWideChar], esi; cchWideChar
0x180009826  mov     r8, rbx; lpMultiByteStr
0x180009829  mov     [rsp+58h+lpWideCharStr], rdi; lpWideCharStr
0x18000982e  xor     edx, edx; dwFlags
0x180009830  xor     ecx, ecx; CodePage
0x180009832  call    cs:__imp_MultiByteToWideChar
0x180009838  mov     rcx, rdi; psz
0x18000983b  call    ?ShowHelpTopic@CNetDiagClient@@SAJPEBG@Z; CNetDiagClient::ShowHelpTopic(ushort const *)
0x180009840  mov     rcx, rdi
0x180009843  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180009849  add     rsp, 30h
0x18000984d  pop     r14
0x18000984f  pop     rdi
0x180009850  pop     rsi
0x180009851  pop     rbp
0x180009852  pop     rbx
0x180009853  retn
```
