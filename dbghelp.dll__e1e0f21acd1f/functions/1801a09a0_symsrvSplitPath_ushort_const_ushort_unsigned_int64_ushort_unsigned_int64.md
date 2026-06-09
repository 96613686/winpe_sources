# symsrvSplitPath(ushort const *,ushort *,unsigned __int64,ushort *,unsigned __int64)

- ea: `0x1801a09a0`
- end: `0x1801a0b88`
- name: `?symsrvSplitPath@@YA_NPEBGPEAG_K12@Z`
- size: `488`
- prototype: `bool(const unsigned __int16 *, unsigned __int16 *, unsigned __int64, unsigned __int16 *, unsigned __int64)`
- caller_count: `6`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18019fd0c`
- `0x1801a0104`
- `0x1801a01e4`
- `0x1801a02c0`
- `0x1801a0b90`
- `0x1801a0d04`

## callees

- `0x180012e6c`
- `0x180027430`
- `0x18019e96c`
- `0x18019eba0`
- `0x1801a09a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801a0b1f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801a0b1f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1801a09c8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1801a0a58`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1801a0acd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1801a09c8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1801a0a58`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1801a0acd`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1801a0a23`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1801a0a23`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1801a09dc`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1801a09dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a0b71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a0b71`

## string_xrefs

- `0x1801a0af7`: `symsrv.dll`
- `0x1801a0b29`: `symsrv.dll`
- `0x1801a0aa7`: `https://msdl.microsoft.com/download/symbols`
- `0x1801a0a92`: `*https://msdl.microsoft.com/download/symbols`
- `0x1801a0b15`: `symaudit.dll`

## pseudocode

```c
char __fastcall symsrvSplitPath(
        const unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int64 a3,
        unsigned __int16 *a4,
        unsigned __int64 a5)
{
  wchar_t *v9; // rsi
  unsigned __int64 v10; // r9
  const unsigned __int16 *v11; // rbx
  char v12; // si
  bool v13; // al
  const wchar_t *v14; // rcx

  if ( !(unsigned int)_o__wcsnicmp(a1, L"symsrv*", 7) )
  {
    v9 = wcschr(a1 + 7, 0x2Au);
    if ( v9 )
    {
      if ( !a2 )
        goto LABEL_7;
      memset_0(a2, 0, 2 * a3);
      v10 = ((char *)v9 - (char *)a1 - 14) >> 1;
      if ( a3 - 1 < v10 )
        v10 = a3 - 1;
      _o_wcsncpy_s(a2, a3, a1 + 7, v10);
      if ( *a2 )
      {
LABEL_7:
        v11 = v9 + 1;
        v12 = 0;
        if ( a2 )
          goto LABEL_26;
        goto LABEL_29;
      }
    }
LABEL_33:
    SetLastError(0x57u);
    return 0;
  }
  if ( (unsigned int)_o__wcsnicmp(a1, L"SRV*", 4) )
  {
    if ( (unsigned int)_o__wcsnicmp(a1, L"DEBUGINFOD*", 11) )
      goto LABEL_33;
    v11 = a1 + 11;
    if ( !*v11 || *v11 == 59 )
      goto LABEL_33;
    v12 = 1;
  }
  else
  {
    v11 = a1 + 4;
    v12 = 0;
    if ( !*v11 || *v11 == 59 )
    {
      v13 = IsInternalPackage();
      v14 = L"https://msdl.microsoft.com/download/symbols";
      v11 = L"https://symweb.azurefd.net";
    }
    else
    {
      if ( *v11 != 42 || v11[1] && v11[1] != 59 )
        goto LABEL_24;
      v13 = IsInternalPackage();
      v14 = L"*https://msdl.microsoft.com/download/symbols";
      v11 = L"*https://symweb.azurefd.net";
    }
    if ( !v13 )
      v11 = v14;
  }
LABEL_24:
  if ( a2 )
  {
    wcscpy_s_ex(a2, a3, L"symsrv.dll");
LABEL_26:
    if ( (dword_1802AF9CC & 0x40000) != 0 && (unsigned int)_o__wcsicmp(a2, L"symaudit.dll") )
      wcscpy_s_ex(a2, a3, L"symsrv.dll");
  }
LABEL_29:
  if ( a4 )
  {
    wcscpy_s_ex(a4, a5, v11);
    if ( v12 )
      patchDebugInfoDPaths(a4, a5);
  }
  return 1;
}

```

## disassembly

```asm
0x1801a09a0  push    rbx
0x1801a09a2  push    rbp
0x1801a09a3  push    rsi
0x1801a09a4  push    rdi
0x1801a09a5  push    r12
0x1801a09a7  push    r14
0x1801a09a9  push    r15
0x1801a09ab  sub     rsp, 20h
0x1801a09af  mov     r14, r8
0x1801a09b2  mov     rdi, rdx
0x1801a09b5  mov     r8d, 7
0x1801a09bb  lea     rdx, aSymsrv; "symsrv*"
0x1801a09c2  mov     rbp, r9
0x1801a09c5  mov     rbx, rcx
0x1801a09c8  call    cs:__imp__o__wcsnicmp
0x1801a09ce  xor     r12d, r12d
0x1801a09d1  test    eax, eax
0x1801a09d3  jnz     short loc_1801A0A48
0x1801a09d5  lea     edx, [rax+2Ah]; Ch
0x1801a09d8  lea     rcx, [rbx+0Eh]; Str
0x1801a09dc  call    cs:__imp_wcschr
0x1801a09e2  mov     rsi, rax
0x1801a09e5  test    rax, rax
0x1801a09e8  jz      loc_1801A0B6C
0x1801a09ee  test    rdi, rdi
0x1801a09f1  jz      short loc_1801A0A33
0x1801a09f3  lea     r8, [r14+r14]; Size
0x1801a09f7  xor     edx, edx; Val
0x1801a09f9  mov     rcx, rdi; void *
0x1801a09fc  call    memset_0
0x1801a0a01  lea     rax, [r14-1]
0x1801a0a05  mov     r9, rsi
0x1801a0a08  sub     r9, rbx
0x1801a0a0b  lea     r8, [rbx+0Eh]
0x1801a0a0f  sub     r9, 0Eh
0x1801a0a13  mov     rdx, r14
0x1801a0a16  sar     r9, 1
0x1801a0a19  mov     rcx, rdi
0x1801a0a1c  cmp     rax, r9
0x1801a0a1f  cmovb   r9, rax
0x1801a0a23  call    cs:__imp__o_wcsncpy_s
0x1801a0a29  cmp     [rdi], r12w
0x1801a0a2d  jz      loc_1801A0B6C
0x1801a0a33  lea     rbx, [rsi+2]
0x1801a0a37  mov     sil, r12b
0x1801a0a3a  test    rdi, rdi
0x1801a0a3d  jz      loc_1801A0B3B
0x1801a0a43  jmp     loc_1801A0B09
0x1801a0a48  mov     r8d, 4
0x1801a0a4e  lea     rdx, aSrv_2; "SRV*"
0x1801a0a55  mov     rcx, rbx
0x1801a0a58  call    cs:__imp__o__wcsnicmp
0x1801a0a5e  test    eax, eax
0x1801a0a60  jnz     short loc_1801A0ABD
0x1801a0a62  add     rbx, 8
0x1801a0a66  mov     sil, r12b
0x1801a0a69  cmp     [rbx], r12w
0x1801a0a6d  jz      short loc_1801A0AA2
0x1801a0a6f  cmp     word ptr [rbx], 3Bh ; ';'
0x1801a0a73  jz      short loc_1801A0AA2
0x1801a0a75  mov     eax, 2Ah ; '*'
0x1801a0a7a  cmp     [rbx], ax
0x1801a0a7d  jnz     short loc_1801A0AF2
0x1801a0a7f  cmp     [rbx+2], r12w
0x1801a0a84  jz      short loc_1801A0A8D
0x1801a0a86  cmp     word ptr [rbx+2], 3Bh ; ';'
0x1801a0a8b  jnz     short loc_1801A0AF2
0x1801a0a8d  call    ?IsInternalPackage@@YA_NXZ; IsInternalPackage(void)
0x1801a0a92  lea     rcx, aHttpsMsdlMicro; "*https://msdl.microsoft.com/download/sy"...
0x1801a0a99  lea     rbx, aHttpsSymwebAzu; "*https://symweb.azurefd.net"
0x1801a0aa0  jmp     short loc_1801A0AB5
0x1801a0aa2  call    ?IsInternalPackage@@YA_NXZ; IsInternalPackage(void)
0x1801a0aa7  lea     rcx, aHttpsMsdlMicro_0; "https://msdl.microsoft.com/download/sym"...
0x1801a0aae  lea     rbx, aHttpsSymwebAzu_0; "https://symweb.azurefd.net"
0x1801a0ab5  test    al, al
0x1801a0ab7  cmovz   rbx, rcx
0x1801a0abb  jmp     short loc_1801A0AF2
0x1801a0abd  mov     r8d, 0Bh
0x1801a0ac3  lea     rdx, aDebuginfod; "DEBUGINFOD*"
0x1801a0aca  mov     rcx, rbx
0x1801a0acd  call    cs:__imp__o__wcsnicmp
0x1801a0ad3  test    eax, eax
0x1801a0ad5  jnz     loc_1801A0B6C
0x1801a0adb  add     rbx, 16h
0x1801a0adf  cmp     [rbx], r12w
0x1801a0ae3  jz      loc_1801A0B6C
0x1801a0ae9  cmp     word ptr [rbx], 3Bh ; ';'
0x1801a0aed  jz      short loc_1801A0B6C
0x1801a0aef  mov     sil, 1
0x1801a0af2  test    rdi, rdi
0x1801a0af5  jz      short loc_1801A0B3B
0x1801a0af7  lea     r8, aSymsrvDll_1; "symsrv.dll"
0x1801a0afe  mov     rdx, r14; unsigned __int64
0x1801a0b01  mov     rcx, rdi; unsigned __int16 *
0x1801a0b04  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a0b09  test    cs:dword_1802AF9CC, 40000h
0x1801a0b13  jz      short loc_1801A0B3B
0x1801a0b15  lea     rdx, aSymauditDll; "symaudit.dll"
0x1801a0b1c  mov     rcx, rdi
0x1801a0b1f  call    cs:__imp__o__wcsicmp
0x1801a0b25  test    eax, eax
0x1801a0b27  jz      short loc_1801A0B3B
0x1801a0b29  lea     r8, aSymsrvDll_1; "symsrv.dll"
0x1801a0b30  mov     rdx, r14; unsigned __int64
0x1801a0b33  mov     rcx, rdi; unsigned __int16 *
0x1801a0b36  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a0b3b  test    rbp, rbp
0x1801a0b3e  jz      short loc_1801A0B68
0x1801a0b40  mov     rdx, [rsp+58h+arg_20]; unsigned __int64
0x1801a0b48  mov     r8, rbx; unsigned __int16 *
0x1801a0b4b  mov     rcx, rbp; unsigned __int16 *
0x1801a0b4e  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a0b53  test    sil, sil
0x1801a0b56  jz      short loc_1801A0B68
0x1801a0b58  mov     rdx, [rsp+58h+arg_20]; unsigned __int64
0x1801a0b60  mov     rcx, rbp; unsigned __int16 *
0x1801a0b63  call    ?patchDebugInfoDPaths@@YA_NPEAG_K@Z; patchDebugInfoDPaths(ushort *,unsigned __int64)
0x1801a0b68  mov     al, 1
0x1801a0b6a  jmp     short loc_1801A0B79
0x1801a0b6c  mov     ecx, 57h ; 'W'; dwErrCode
0x1801a0b71  call    cs:__imp_SetLastError
0x1801a0b77  xor     al, al
0x1801a0b79  add     rsp, 20h
0x1801a0b7d  pop     r15
0x1801a0b7f  pop     r14
0x1801a0b81  pop     r12
0x1801a0b83  pop     rdi
0x1801a0b84  pop     rsi
0x1801a0b85  pop     rbp
0x1801a0b86  pop     rbx
0x1801a0b87  retn
```
