# GetCustomAllowListPathRank

- ea: `0x180025100`
- end: `0x180025223`
- name: `GetCustomAllowListPathRank`
- size: `291`
- prototype: `__int64 __fastcall(wchar_t *String1, _DWORD *, __int64, unsigned __int16 *, _DWORD *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180003620`
- `0x180003730`

## callees

- `0x18001cddc`
- `0x180022ebc`
- `0x18002323c`
- `0x180025044`
- `0x180025100`
- `0x18002c01e`
- `0x18002c050`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800251c1`
- `msvcrt!_wcsicmp` at `0x1800251c1`

## pseudocode

```c
__int64 __fastcall GetCustomAllowListPathRank(
        wchar_t *String1,
        _DWORD *a2,
        __int64 a3,
        unsigned __int16 *a4,
        _DWORD *a5)
{
  __int64 v8; // rbx
  unsigned int ConfigParamLocalWEx; // edi
  int v10; // eax
  wchar_t String2[264]; // [rsp+30h] [rbp-258h] BYREF

  memset_0(String2, 0, 0x20Au);
  *a5 = -1;
  *a2 = -1;
  *a4 = 0;
  v8 = 0;
  ConfigParamLocalWEx = GetConfigParamLocalWEx(L"AllowListFolder", (LPBYTE)String2);
  if ( ConfigParamLocalWEx )
    goto LABEL_10;
  v8 = -1;
  do
    ++v8;
  while ( String2[v8] );
  if ( v8 )
  {
    if ( String2[v8 - 1] != 92 )
    {
      v10 = StringCbCatW(String2, 0x20Au, L"\\");
      if ( v10 < 0 )
        return (unsigned __int16)v10;
    }
  }
  if ( _wcsicmp(String1, String2) )
LABEL_10:
    ConfigParamLocalWEx = GetVdcFilePathRank(String1, (__int64)a5);
  else
    *a2 = 0;
  if ( v8 )
  {
    StringCchCopyW(a4, 0x105u, String2);
    *a5 = 0;
  }
  return ConfigParamLocalWEx;
}

```

## disassembly

```asm
0x180025100  push    rbx
0x180025102  push    rbp
0x180025103  push    rsi
0x180025104  push    rdi
0x180025105  push    r12
0x180025107  push    r14
0x180025109  push    r15
0x18002510b  sub     rsp, 250h
0x180025112  mov     rax, cs:__security_cookie
0x180025119  xor     rax, rsp
0x18002511c  mov     [rsp+288h+var_48], rax
0x180025124  mov     r15, [rsp+288h+arg_20]
0x18002512c  mov     rsi, rdx
0x18002512f  mov     rbp, rcx
0x180025132  mov     edi, 20Ah
0x180025137  mov     r8d, edi; Size
0x18002513a  lea     rcx, [rsp+288h+String2]; void *
0x18002513f  xor     edx, edx; Val
0x180025141  mov     r14, r9
0x180025144  call    memset_0
0x180025149  mov     dword ptr [r15], 0FFFFFFFFh
0x180025150  lea     rdx, [rsp+288h+String2]; lpData
0x180025155  xor     r12d, r12d
0x180025158  mov     dword ptr [rsi], 0FFFFFFFFh
0x18002515e  mov     r8d, edi
0x180025161  mov     [r14], r12w
0x180025165  lea     rcx, aAllowlistfolde; "AllowListFolder"
0x18002516c  mov     ebx, r12d
0x18002516f  call    GetConfigParamLocalWEx
0x180025174  mov     edi, eax
0x180025176  test    eax, eax
0x180025178  jnz     short loc_1800251D0
0x18002517a  lea     rax, [rsp+288h+String2]
0x18002517f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180025183  inc     rbx
0x180025186  cmp     [rax+rbx*2], r12w
0x18002518b  jnz     short loc_180025183
0x18002518d  test    rbx, rbx
0x180025190  jz      short loc_1800251B9
0x180025192  cmp     [rsp+rbx*2+288h+var_25A], 5Ch ; '\'
0x180025198  jz      short loc_1800251B9
0x18002519a  lea     r8, pszSrc; "\\"
0x1800251a1  mov     edx, 20Ah; unsigned __int64
0x1800251a6  lea     rcx, [rsp+288h+String2]; unsigned __int16 *
0x1800251ab  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x1800251b0  test    eax, eax
0x1800251b2  jns     short loc_1800251B9
0x1800251b4  movzx   edi, ax
0x1800251b7  jmp     short loc_1800251FF
0x1800251b9  lea     rdx, [rsp+288h+String2]; String2
0x1800251be  mov     rcx, rbp; String1
0x1800251c1  call    cs:__imp__wcsicmp
0x1800251c7  test    eax, eax
0x1800251c9  jnz     short loc_1800251D0
0x1800251cb  mov     [rsi], r12d
0x1800251ce  jmp     short loc_1800251E5
0x1800251d0  mov     r9, r14
0x1800251d3  mov     [rsp+288h+var_268], r15; __int64
0x1800251d8  mov     rdx, rsi
0x1800251db  mov     rcx, rbp; String1
0x1800251de  call    GetVdcFilePathRank
0x1800251e3  mov     edi, eax
0x1800251e5  test    rbx, rbx
0x1800251e8  jz      short loc_1800251FF
0x1800251ea  lea     r8, [rsp+288h+String2]; unsigned __int16 *
0x1800251ef  mov     edx, 105h; unsigned __int64
0x1800251f4  mov     rcx, r14; unsigned __int16 *
0x1800251f7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800251fc  mov     [r15], r12d
0x1800251ff  mov     eax, edi
0x180025201  mov     rcx, [rsp+288h+var_48]
0x180025209  xor     rcx, rsp; StackCookie
0x18002520c  call    __security_check_cookie
0x180025211  add     rsp, 250h
0x180025218  pop     r15
0x18002521a  pop     r14
0x18002521c  pop     r12
0x18002521e  pop     rdi
0x18002521f  pop     rsi
0x180025220  pop     rbp
0x180025221  pop     rbx
0x180025222  retn
```
