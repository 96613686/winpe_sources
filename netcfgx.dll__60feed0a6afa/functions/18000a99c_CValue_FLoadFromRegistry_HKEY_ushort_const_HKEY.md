# CValue::FLoadFromRegistry(HKEY__ *,ushort const *,HKEY__ *)

- ea: `0x18000a99c`
- end: `0x18000aa72`
- name: `?FLoadFromRegistry@CValue@@QEAAHPEAUHKEY__@@PEBG0@Z`
- size: `214`
- prototype: `__int64 __fastcall(CValue *__hidden this, HKEY, LPCWSTR lpValueName, HKEY)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000af5c`

## callees

- `0x180001f90`
- `0x18000a99c`
- `0x18000ab50`
- `0x18000b648`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000aa21`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000aa21`

## pseudocode

```c
__int64 __fastcall CValue::FLoadFromRegistry(CValue *this, HKEY a2, LPCWSTR lpValueName, HKEY a4)
{
  LSTATUS v7; // eax
  bool v8; // sf
  DWORD cbData; // [rsp+30h] [rbp-248h] BYREF
  DWORD Type[3]; // [rsp+34h] [rbp-244h] BYREF
  BYTE Data[2]; // [rsp+40h] [rbp-238h] BYREF

  *((_DWORD *)this + 3) = 0;
  cbData = 0;
  if ( a4 == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    a4 = a2;
  Type[0] = 0;
  if ( Reg_QueryInt(a4, L"Base", 0xAu) == 16 )
    *((_DWORD *)this + 3) = 1;
  cbData = 512;
  v7 = RegQueryValueExW(a2, lpValueName, 0, Type, Data, &cbData);
  v8 = v7 < 0;
  if ( v7 > 0 )
    v8 = 1;
  if ( v8 || !*(_WORD *)Data )
    return 0;
  *((_DWORD *)this + 4) = 1;
  return CValue::FromString(this, (const unsigned __int16 *const)Data);
}

```

## disassembly

```asm
0x18000a99c  push    rbx
0x18000a99e  push    rbp
0x18000a99f  push    rsi
0x18000a9a0  push    rdi
0x18000a9a1  sub     rsp, 258h
0x18000a9a8  mov     rax, cs:__security_cookie
0x18000a9af  xor     rax, rsp
0x18000a9b2  mov     [rsp+278h+var_38], rax
0x18000a9ba  xor     ebp, ebp
0x18000a9bc  mov     rsi, r8
0x18000a9bf  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x18000a9c3  mov     [rcx+0Ch], ebp
0x18000a9c6  mov     rdi, rdx
0x18000a9c9  mov     [rsp+278h+cbData], ebp
0x18000a9cd  cmovz   r9, rdx
0x18000a9d1  mov     [rsp+278h+Type], ebp
0x18000a9d5  mov     rbx, rcx
0x18000a9d8  lea     r8d, [rbp+0Ah]; unsigned int
0x18000a9dc  mov     rcx, r9; HKEY
0x18000a9df  lea     rdx, aBase; "Base"
0x18000a9e6  call    ?Reg_QueryInt@@YAIPEAUHKEY__@@PEBGI@Z; Reg_QueryInt(HKEY__ *,ushort const *,uint)
0x18000a9eb  cmp     eax, 10h
0x18000a9ee  jnz     short loc_18000A9F7
0x18000a9f0  mov     dword ptr [rbx+0Ch], 1
0x18000a9f7  lea     rax, [rsp+278h+cbData]
0x18000a9fc  mov     [rsp+278h+cbData], 200h
0x18000aa04  mov     [rsp+278h+lpcbData], rax; lpcbData
0x18000aa09  lea     r9, [rsp+278h+Type]; lpType
0x18000aa0e  lea     rax, [rsp+278h+Data]
0x18000aa13  xor     r8d, r8d; lpReserved
0x18000aa16  mov     rdx, rsi; lpValueName
0x18000aa19  mov     [rsp+278h+lpData], rax; lpData
0x18000aa1e  mov     rcx, rdi; hKey
0x18000aa21  call    cs:__imp_RegQueryValueExW
0x18000aa27  test    eax, eax
0x18000aa29  jle     short loc_18000AA35
0x18000aa2b  movzx   eax, ax
0x18000aa2e  or      eax, 80070000h
0x18000aa33  test    eax, eax
0x18000aa35  js      short loc_18000AA54
0x18000aa37  cmp     word ptr [rsp+278h+Data], bp
0x18000aa3c  jz      short loc_18000AA54
0x18000aa3e  lea     rdx, [rsp+278h+Data]; unsigned __int16 *
0x18000aa43  mov     dword ptr [rbx+10h], 1
0x18000aa4a  mov     rcx, rbx; this
0x18000aa4d  call    ?FromString@CValue@@QEAAHQEBG@Z; CValue::FromString(ushort const * const)
0x18000aa52  jmp     short loc_18000AA56
0x18000aa54  xor     eax, eax
0x18000aa56  mov     rcx, [rsp+278h+var_38]
0x18000aa5e  xor     rcx, rsp; StackCookie
0x18000aa61  call    __security_check_cookie
0x18000aa66  add     rsp, 258h
0x18000aa6d  pop     rdi
0x18000aa6e  pop     rsi
0x18000aa6f  pop     rbp
0x18000aa70  pop     rbx
0x18000aa71  retn
```
