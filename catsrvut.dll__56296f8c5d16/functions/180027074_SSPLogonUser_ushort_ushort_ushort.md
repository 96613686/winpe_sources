# SSPLogonUser(ushort *,ushort *,ushort *)

- ea: `0x180027074`
- end: `0x180027222`
- name: `?SSPLogonUser@@YAHPEAG00@Z`
- size: `430`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180026e10`

## callees

- `0x18000717c`
- `0x180014ec8`
- `0x180015594`
- `0x180027074`
- `0x18002aac8`
- `0x18002ac5c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027174`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002718e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800271e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027174`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002718e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800271e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027126`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027126`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800270ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800270ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027201`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027201`
- `SspiCli!LogonUserExExW` at `0x1800270c6`
- `SspiCli!LogonUserExExW` at `0x1800271d1`
- `SspiCli!LogonUserExExW` at `0x1800270c6`
- `SspiCli!LogonUserExExW` at `0x1800271d1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SSPLogonUser(unsigned __int16 *a1, unsigned __int16 *a2, unsigned __int16 *a3)
{
  unsigned int v6; // esi
  DWORD LastError; // eax
  int v8; // eax
  int v9; // r8d
  unsigned __int64 v10; // rsi
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rbx
  const unsigned __int16 *v14; // rdx
  int v15; // ebp
  const unsigned __int16 *v16; // rdx
  HANDLE hObject; // [rsp+A8h] [rbp+20h] BYREF

  hObject = 0;
  v6 = LogonUserExExW(a2, a1, a3, 3, 0, 0, &hObject, 0, 0, 0, 0);
  LastError = GetLastError();
  if ( v6 )
    goto LABEL_19;
  if ( LastError == 1385 || LastError == 1348 )
  {
    if ( a1 )
      safe_lstrlenW(a1);
    v8 = safe_lstrlenW(a2);
    v10 = (unsigned int)(v9 + v8 + 1);
    v11 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v10, 2u));
    v12 = v11;
    if ( !v11 )
      return 0;
    if ( a1 )
    {
      if ( (int)StringCchPrintfW(v11, v10, L"%s\\", a1) < 0 )
      {
LABEL_15:
        CoTaskMemFree(v12);
        return 0;
      }
    }
    else
    {
      *v11 = 0;
    }
    if ( StringCchCatW(v12, v10, a2) < 0 )
      goto LABEL_15;
    v15 = SetAccountRights(v12, v14);
    if ( v15 < 0 )
      goto LABEL_15;
    v6 = LogonUserExExW(a2, a1, a3, 4, 0, 0, &hObject, 0, 0, 0, 0);
    if ( !v15 )
      RemoveAccountRights(v12, v16);
    CoTaskMemFree(v12);
    if ( v6 )
    {
LABEL_19:
      if ( hObject )
        CloseHandle(hObject);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180027074  mov     r11, rsp
0x180027077  mov     [r11+8], rbx
0x18002707b  mov     [r11+10h], rbp
0x18002707f  push    rsi
0x180027080  push    rdi
0x180027081  push    r12
0x180027083  push    r14
0x180027085  push    r15
0x180027087  sub     rsp, 60h
0x18002708b  mov     r15, r8
0x18002708e  mov     r14, rdx
0x180027091  mov     rdi, rcx
0x180027094  xor     r12d, r12d
0x180027097  mov     [r11+20h], r12
0x18002709b  mov     [r11-38h], r12
0x18002709f  mov     [r11-40h], r12
0x1800270a3  mov     [r11-48h], r12
0x1800270a7  mov     [r11-50h], r12
0x1800270ab  lea     rax, [r11+20h]
0x1800270af  mov     [r11-58h], rax
0x1800270b3  mov     [r11-60h], r12
0x1800270b7  mov     [r11-68h], r12d
0x1800270bb  lea     r9d, [r12+3]
0x1800270c0  mov     rdx, rcx
0x1800270c3  mov     rcx, r14
0x1800270c6  call    cs:__imp_LogonUserExExW
0x1800270cc  mov     esi, eax
0x1800270ce  call    cs:__imp_GetLastError
0x1800270d4  test    esi, esi
0x1800270d6  jnz     loc_1800271F4
0x1800270dc  cmp     eax, 569h
0x1800270e1  jz      short loc_1800270EE
0x1800270e3  cmp     eax, 544h
0x1800270e8  jnz     loc_180027207
0x1800270ee  mov     r8d, r12d
0x1800270f1  test    rdi, rdi
0x1800270f4  jz      short loc_180027102
0x1800270f6  mov     rcx, rdi; unsigned __int16 *
0x1800270f9  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x1800270fe  lea     r8d, [rax+1]
0x180027102  mov     rcx, r14; unsigned __int16 *
0x180027105  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18002710a  lea     esi, [rax+1]
0x18002710d  add     esi, r8d
0x180027110  mov     eax, 2
0x180027115  mul     rsi
0x180027118  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002711f  cmovb   rax, rcx
0x180027123  mov     rcx, rax; cb
0x180027126  call    cs:__imp_CoTaskMemAlloc
0x18002712c  mov     rbx, rax
0x18002712f  test    rax, rax
0x180027132  jnz     short loc_18002713B
0x180027134  xor     eax, eax
0x180027136  jmp     loc_180027209
0x18002713b  test    rdi, rdi
0x18002713e  jz      short loc_18002715B
0x180027140  mov     r9, rdi
0x180027143  lea     r8, aS_1; "%s\\"
0x18002714a  mov     rdx, rsi; unsigned __int64
0x18002714d  mov     rcx, rbx; unsigned __int16 *
0x180027150  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180027155  test    eax, eax
0x180027157  js      short loc_180027171
0x180027159  jmp     short loc_18002715F
0x18002715b  mov     [rax], r12w
0x18002715f  mov     r8, r14; unsigned __int16 *
0x180027162  mov     rdx, rsi; unsigned __int64
0x180027165  mov     rcx, rbx; unsigned __int16 *
0x180027168  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002716d  test    eax, eax
0x18002716f  jns     short loc_18002717D
0x180027171  mov     rcx, rbx; pv
0x180027174  call    cs:__imp_CoTaskMemFree
0x18002717a  nop
0x18002717b  jmp     short loc_180027134
0x18002717d  mov     rcx, rbx; Str
0x180027180  call    ?SetAccountRights@@YAJPEBG0@Z; SetAccountRights(ushort const *,ushort const *)
0x180027185  mov     ebp, eax
0x180027187  test    eax, eax
0x180027189  jns     short loc_180027197
0x18002718b  mov     rcx, rbx; pv
0x18002718e  call    cs:__imp_CoTaskMemFree
0x180027194  nop
0x180027195  jmp     short loc_180027134
0x180027197  mov     [rsp+88h+var_38], r12
0x18002719c  mov     [rsp+88h+var_40], r12
0x1800271a1  mov     [rsp+88h+var_48], r12
0x1800271a6  mov     [rsp+88h+var_50], r12
0x1800271ab  lea     rax, [rsp+88h+hObject]
0x1800271b3  mov     [rsp+88h+var_58], rax
0x1800271b8  mov     [rsp+88h+var_60], r12
0x1800271bd  mov     [rsp+88h+var_68], r12d
0x1800271c2  mov     r9d, 4
0x1800271c8  mov     r8, r15
0x1800271cb  mov     rdx, rdi
0x1800271ce  mov     rcx, r14
0x1800271d1  call    cs:__imp_LogonUserExExW
0x1800271d7  mov     esi, eax
0x1800271d9  test    ebp, ebp
0x1800271db  jnz     short loc_1800271E6
0x1800271dd  mov     rcx, rbx; Str
0x1800271e0  call    ?RemoveAccountRights@@YAJPEBG0@Z; RemoveAccountRights(ushort const *,ushort const *)
0x1800271e5  nop
0x1800271e6  mov     rcx, rbx; pv
0x1800271e9  call    cs:__imp_CoTaskMemFree
0x1800271ef  nop
0x1800271f0  test    esi, esi
0x1800271f2  jz      short loc_180027207
0x1800271f4  mov     rcx, [rsp+88h+hObject]; hObject
0x1800271fc  test    rcx, rcx
0x1800271ff  jz      short loc_180027207
0x180027201  call    cs:__imp_CloseHandle
0x180027207  mov     eax, esi
0x180027209  lea     r11, [rsp+88h+var_28]
0x18002720e  mov     rbx, [r11+30h]
0x180027212  mov     rbp, [r11+38h]
0x180027216  mov     rsp, r11
0x180027219  pop     r15
0x18002721b  pop     r14
0x18002721d  pop     r12
0x18002721f  pop     rdi
0x180027220  pop     rsi
0x180027221  retn
```
