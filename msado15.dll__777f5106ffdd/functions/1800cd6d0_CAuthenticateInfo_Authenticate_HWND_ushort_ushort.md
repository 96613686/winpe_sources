# CAuthenticateInfo::Authenticate(HWND__ * *,ushort * *,ushort * *)

- ea: `0x1800cd6d0`
- end: `0x1800cd7f0`
- name: `?Authenticate@CAuthenticateInfo@@UEAAJPEAPEAUHWND__@@PEAPEAG1@Z`
- size: `288`
- prototype: `__int64 __fastcall(CAuthenticateInfo *__hidden this, HWND *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1800747cc`
- `0x1800c8f34`
- `0x1800cd6d0`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1800cd71f`
- `ole32!CoTaskMemAlloc` at `0x1800cd755`
- `ole32!CoTaskMemAlloc` at `0x1800cd71f`
- `ole32!CoTaskMemAlloc` at `0x1800cd755`
- `ole32!CoTaskMemFree` at `0x1800cd76c`
- `ole32!CoTaskMemFree` at `0x1800cd76c`
- `OLEAUT32!__imp_SysStringLen` at `0x1800cd6f3`
- `OLEAUT32!__imp_SysStringLen` at `0x1800cd706`
- `OLEAUT32!__imp_SysStringLen` at `0x1800cd6f3`
- `OLEAUT32!__imp_SysStringLen` at `0x1800cd706`

## pseudocode

```c
__int64 __fastcall CAuthenticateInfo::Authenticate(BSTR *this, HWND *a2, unsigned __int16 **a3, unsigned __int16 **a4)
{
  unsigned __int64 v7; // rdi
  unsigned __int64 v8; // rbx
  unsigned __int64 v9; // r12
  unsigned __int16 *v10; // rax
  __int64 v11; // rdx
  unsigned __int64 v12; // r14
  unsigned __int16 *v13; // rax
  void *v14; // rcx
  __int64 result; // rax
  int v16; // [rsp+20h] [rbp-48h]

  *a2 = HWND_MESSAGE|0x2LL;
  v7 = (int)SysStringLen(this[1]);
  v8 = (int)SysStringLen(this[2]);
  v9 = (int)v7 + 1;
  v10 = (unsigned __int16 *)CoTaskMemAlloc(2 * v9);
  *a3 = v10;
  if ( !v10 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      v16 = 86;
      v11 = 88073;
LABEL_7:
      bidTraceW(
        off_18012A238[0],
        v11,
        L"<CAuthenticateInfo::Authenticate|ADO|ERR> 0x%08x{HRESULT} line %d\n",
        2147942414LL,
        v16);
      return 2147942414LL;
    }
    return 2147942414LL;
  }
  v12 = (int)v8 + 1;
  v13 = (unsigned __int16 *)CoTaskMemAlloc(2 * v12);
  *a4 = v13;
  v14 = *a3;
  if ( !v13 )
  {
    CoTaskMemFree(v14);
    if ( (bidGblFlags & 2) != 0 )
    {
      v16 = 92;
      v11 = 94217;
      goto LABEL_7;
    }
    return 2147942414LL;
  }
  StringCchCopyNW((unsigned __int16 *)v14, v9, this[1], v7);
  StringCchCopyNW(*a4, v12, this[2], v8);
  result = 0;
  (*a3)[v7] = 0;
  (*a4)[v8] = 0;
  return result;
}

```

## disassembly

```asm
0x1800cd6d0  push    rbx
0x1800cd6d2  push    rbp
0x1800cd6d3  push    rsi
0x1800cd6d4  push    rdi
0x1800cd6d5  push    r12
0x1800cd6d7  push    r14
0x1800cd6d9  push    r15
0x1800cd6db  sub     rsp, 30h
0x1800cd6df  mov     rbp, rcx
0x1800cd6e2  mov     qword ptr [rdx], 0FFFFFFFFFFFFFFFFh
0x1800cd6e9  mov     rcx, [rcx+8]; pbstr
0x1800cd6ed  mov     r15, r9
0x1800cd6f0  mov     rsi, r8
0x1800cd6f3  call    cs:__imp_SysStringLen
0x1800cd6fa  nop     dword ptr [rax+rax+00h]
0x1800cd6ff  mov     rcx, [rbp+10h]; pbstr
0x1800cd703  movsxd  rdi, eax
0x1800cd706  call    cs:__imp_SysStringLen
0x1800cd70d  nop     dword ptr [rax+rax+00h]
0x1800cd712  lea     edx, [rdi+1]
0x1800cd715  movsxd  rbx, eax
0x1800cd718  movsxd  r12, edx
0x1800cd71b  lea     rcx, [r12+r12]; cb
0x1800cd71f  call    cs:__imp_CoTaskMemAlloc
0x1800cd726  nop     dword ptr [rax+rax+00h]
0x1800cd72b  mov     [rsi], rax
0x1800cd72e  test    rax, rax
0x1800cd731  jnz     short loc_1800CD74B
0x1800cd733  test    byte ptr cs:_bidGblFlags, 2
0x1800cd73a  jz      short loc_1800CD7A7
0x1800cd73c  mov     [rsp+68h+var_48], 56h ; 'V'
0x1800cd744  mov     edx, 15809h
0x1800cd749  jmp     short loc_1800CD78E
0x1800cd74b  lea     eax, [rbx+1]
0x1800cd74e  movsxd  r14, eax
0x1800cd751  lea     rcx, [r14+r14]; cb
0x1800cd755  call    cs:__imp_CoTaskMemAlloc
0x1800cd75c  nop     dword ptr [rax+rax+00h]
0x1800cd761  mov     [r15], rax
0x1800cd764  mov     rcx, [rsi]; unsigned __int16 *
0x1800cd767  test    rax, rax
0x1800cd76a  jnz     short loc_1800CD7AE
0x1800cd76c  call    cs:__imp_CoTaskMemFree
0x1800cd773  nop     dword ptr [rax+rax+00h]
0x1800cd778  test    byte ptr cs:_bidGblFlags, 2
0x1800cd77f  jz      short loc_1800CD7A7
0x1800cd781  mov     [rsp+68h+var_48], 5Ch ; '\'
0x1800cd789  mov     edx, 17009h
0x1800cd78e  mov     rcx, cs:off_18012A238; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800cd795  lea     r8, aCauthenticatei; "<CAuthenticateInfo::Authenticate|ADO|ER"...
0x1800cd79c  mov     r9d, 8007000Eh
0x1800cd7a2  call    _bidTraceW
0x1800cd7a7  mov     eax, 8007000Eh
0x1800cd7ac  jmp     short loc_1800CD7E0
0x1800cd7ae  mov     r8, [rbp+8]; unsigned __int16 *
0x1800cd7b2  mov     r9, rdi; unsigned __int64
0x1800cd7b5  mov     rdx, r12; unsigned __int64
0x1800cd7b8  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800cd7bd  mov     r8, [rbp+10h]; unsigned __int16 *
0x1800cd7c1  mov     r9, rbx; unsigned __int64
0x1800cd7c4  mov     rcx, [r15]; unsigned __int16 *
0x1800cd7c7  mov     rdx, r14; unsigned __int64
0x1800cd7ca  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800cd7cf  mov     r11, [rsi]
0x1800cd7d2  xor     eax, eax
0x1800cd7d4  mov     [r11+rdi*2], ax
0x1800cd7d9  mov     rcx, [r15]
0x1800cd7dc  mov     [rcx+rbx*2], ax
0x1800cd7e0  add     rsp, 30h
0x1800cd7e4  pop     r15
0x1800cd7e6  pop     r14
0x1800cd7e8  pop     r12
0x1800cd7ea  pop     rdi
0x1800cd7eb  pop     rsi
0x1800cd7ec  pop     rbp
0x1800cd7ed  pop     rbx
0x1800cd7ee  retn
```
