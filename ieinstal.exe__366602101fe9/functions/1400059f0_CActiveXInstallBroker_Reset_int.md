# CActiveXInstallBroker::Reset(int)

- ea: `0x1400059f0`
- end: `0x140005b0a`
- name: `?Reset@CActiveXInstallBroker@@AEAAXH@Z`
- size: `282`
- prototype: `void __fastcall(CActiveXInstallBroker *__hidden this, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x14000447c`
- `0x140004aa0`

## callees

- `0x1400059f0`
- `0x140011010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x140005a49`
- `KERNEL32!FreeLibrary` at `0x140005a5e`
- `KERNEL32!FreeLibrary` at `0x140005a49`
- `KERNEL32!FreeLibrary` at `0x140005a5e`
- `ole32!CoTaskMemFree` at `0x140005a7b`
- `ole32!CoTaskMemFree` at `0x140005a99`
- `ole32!CoTaskMemFree` at `0x140005a7b`
- `ole32!CoTaskMemFree` at `0x140005a99`
- `OLEAUT32!__imp_SysFreeString` at `0x140005a02`
- `OLEAUT32!__imp_SysFreeString` at `0x140005a12`
- `OLEAUT32!__imp_SysFreeString` at `0x140005a22`
- `OLEAUT32!__imp_SysFreeString` at `0x140005a32`
- `OLEAUT32!__imp_SysFreeString` at `0x140005a02`
- `OLEAUT32!__imp_SysFreeString` at `0x140005a12`
- `OLEAUT32!__imp_SysFreeString` at `0x140005a22`
- `OLEAUT32!__imp_SysFreeString` at `0x140005a32`

## pseudocode

```c
void __fastcall CActiveXInstallBroker::Reset(BSTR *this, int a2)
{
  HMODULE v4; // rcx
  HMODULE v5; // rcx
  BSTR v6; // rdi
  BSTR v7; // rcx
  OLECHAR *v8; // rax
  BSTR v9; // rcx

  SysFreeString(this[7]);
  SysFreeString(this[8]);
  SysFreeString(this[9]);
  SysFreeString(this[10]);
  v4 = (HMODULE)this[13];
  if ( v4 )
    FreeLibrary(v4);
  v5 = (HMODULE)this[14];
  if ( v5 )
    FreeLibrary(v5);
  v6 = this[16];
  while ( v6 )
  {
    if ( *(_QWORD *)v6 )
      CoTaskMemFree(*(LPVOID *)v6);
    v7 = v6;
    v8 = 0;
    if ( v6 != *((BSTR *)v6 + 1) )
      v8 = (OLECHAR *)*((_QWORD *)v6 + 1);
    v6 = v8;
    CoTaskMemFree(v7);
  }
  v9 = this[19];
  if ( v9 )
  {
    (*(void (__fastcall **)(BSTR))(*(_QWORD *)v9 + 16LL))(v9);
    this[19] = 0;
  }
  if ( a2 )
  {
    this[13] = 0;
    this[14] = 0;
    this[7] = 0;
    this[8] = 0;
    this[9] = 0;
    this[10] = 0;
    *((_BYTE *)this + 160) = 0;
    *((_DWORD *)this + 30) = 0;
    this[16] = 0;
    this[19] = 0;
    *((_DWORD *)this + 12) = 0;
  }
}

```

## disassembly

```asm
0x1400059f0  push    rbx
0x1400059f2  push    rbp
0x1400059f3  push    rsi
0x1400059f4  push    rdi
0x1400059f5  sub     rsp, 28h
0x1400059f9  mov     rbx, rcx
0x1400059fc  mov     esi, edx
0x1400059fe  mov     rcx, [rcx+38h]; bstrString
0x140005a02  call    cs:__imp_SysFreeString
0x140005a09  nop     dword ptr [rax+rax+00h]
0x140005a0e  mov     rcx, [rbx+40h]; bstrString
0x140005a12  call    cs:__imp_SysFreeString
0x140005a19  nop     dword ptr [rax+rax+00h]
0x140005a1e  mov     rcx, [rbx+48h]; bstrString
0x140005a22  call    cs:__imp_SysFreeString
0x140005a29  nop     dword ptr [rax+rax+00h]
0x140005a2e  mov     rcx, [rbx+50h]; bstrString
0x140005a32  call    cs:__imp_SysFreeString
0x140005a39  nop     dword ptr [rax+rax+00h]
0x140005a3e  mov     rcx, [rbx+68h]; hLibModule
0x140005a42  xor     ebp, ebp
0x140005a44  test    rcx, rcx
0x140005a47  jz      short loc_140005A55
0x140005a49  call    cs:__imp_FreeLibrary
0x140005a50  nop     dword ptr [rax+rax+00h]
0x140005a55  mov     rcx, [rbx+70h]; hLibModule
0x140005a59  test    rcx, rcx
0x140005a5c  jz      short loc_140005A6A
0x140005a5e  call    cs:__imp_FreeLibrary
0x140005a65  nop     dword ptr [rax+rax+00h]
0x140005a6a  mov     rdi, [rbx+80h]
0x140005a71  jmp     short loc_140005AA5
0x140005a73  mov     rcx, [rdi]; pv
0x140005a76  test    rcx, rcx
0x140005a79  jz      short loc_140005A87
0x140005a7b  call    cs:__imp_CoTaskMemFree
0x140005a82  nop     dword ptr [rax+rax+00h]
0x140005a87  cmp     rdi, [rdi+8]
0x140005a8b  mov     rcx, rdi; pv
0x140005a8e  mov     rax, rbp
0x140005a91  cmovnz  rax, [rdi+8]
0x140005a96  mov     rdi, rax
0x140005a99  call    cs:__imp_CoTaskMemFree
0x140005aa0  nop     dword ptr [rax+rax+00h]
0x140005aa5  test    rdi, rdi
0x140005aa8  jnz     short loc_140005A73
0x140005aaa  mov     rcx, [rbx+98h]
0x140005ab1  test    rcx, rcx
0x140005ab4  jz      short loc_140005AC9
0x140005ab6  mov     rax, [rcx]
0x140005ab9  mov     rax, [rax+10h]
0x140005abd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005ac2  mov     [rbx+98h], rbp
0x140005ac9  test    esi, esi
0x140005acb  jz      short loc_140005B00
0x140005acd  mov     [rbx+68h], rbp
0x140005ad1  mov     [rbx+70h], rbp
0x140005ad5  mov     [rbx+38h], rbp
0x140005ad9  mov     [rbx+40h], rbp
0x140005add  mov     [rbx+48h], rbp
0x140005ae1  mov     [rbx+50h], rbp
0x140005ae5  mov     [rbx+0A0h], bpl
0x140005aec  mov     [rbx+78h], ebp
0x140005aef  mov     [rbx+80h], rbp
0x140005af6  mov     [rbx+98h], rbp
0x140005afd  mov     [rbx+30h], ebp
0x140005b00  add     rsp, 28h
0x140005b04  pop     rdi
0x140005b05  pop     rsi
0x140005b06  pop     rbp
0x140005b07  pop     rbx
0x140005b08  retn
```
