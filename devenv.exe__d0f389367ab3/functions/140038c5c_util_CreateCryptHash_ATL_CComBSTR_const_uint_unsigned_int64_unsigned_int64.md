# util_CreateCryptHash(ATL::CComBSTR const &,uint,unsigned __int64,unsigned __int64 *)

- ea: `0x140038c5c`
- end: `0x140038d5f`
- name: `?util_CreateCryptHash@@YA?AW4CreateCryptHashResult@@AEBVCComBSTR@ATL@@I_KPEA_K@Z`
- size: `259`
- prototype: `enum CreateCryptHashResult __high(const struct ATL::CComBSTR *, unsigned int, unsigned __int64, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400404ec`

## callees

- `0x140001020`
- `0x140001040`
- `0x140002196`
- `0x140038c5c`
- `0x1400399fc`

## import_xrefs

- `ADVAPI32!CryptCreateHash` at `0x140038cad`
- `ADVAPI32!CryptCreateHash` at `0x140038cad`
- `ADVAPI32!CryptHashData` at `0x140038d18`
- `ADVAPI32!CryptHashData` at `0x140038d18`
- `KERNEL32!lstrlenA` at `0x140038d06`
- `KERNEL32!lstrlenA` at `0x140038d06`
- `api-ms-win-crt-string-l1-1-0!_strlwr_s` at `0x140038cf8`
- `api-ms-win-crt-string-l1-1-0!_strlwr_s` at `0x140038cf8`

## pseudocode

```c
__int64 __fastcall util_CreateCryptHash(_QWORD *a1, ALG_ID a2, HCRYPTPROV a3, HCRYPTHASH *phHash)
{
  unsigned int v4; // edi
  char *v8; // rcx
  __int64 v9; // rdx
  char *v10; // rbx
  DWORD v11; // eax
  BOOL v12; // eax
  char *String; // [rsp+30h] [rbp-B8h] BYREF
  char v14; // [rsp+38h] [rbp-B0h] BYREF

  v4 = 0;
  if ( !phHash || !a3 || !*a1 )
    return 1;
  if ( !CryptCreateHash(a3, a2, 0, 0, phHash) )
    return 2;
  memset_0(&String, 0, 0x88u);
  ATL::CW2AEX<128>::CW2AEX<128>(&String, *a1);
  v8 = String;
  if ( !String )
    goto LABEL_10;
  v9 = -1;
  do
    ++v9;
  while ( String[v9] );
  _strlwr_s(String, v9 + 1);
  v10 = String;
  v11 = lstrlenA(String);
  v12 = CryptHashData(*phHash, (const BYTE *)v10, v11, 0);
  v8 = String;
  if ( !v12 )
LABEL_10:
    v4 = 3;
  if ( v8 != &v14 )
    free_0(v8);
  return v4;
}

```

## disassembly

```asm
0x140038c5c  push    rbx
0x140038c5e  push    rsi
0x140038c5f  push    rdi
0x140038c60  sub     rsp, 0D0h
0x140038c67  mov     rax, cs:__security_cookie
0x140038c6e  xor     rax, rsp
0x140038c71  mov     [rsp+0E8h+var_28], rax
0x140038c79  xor     edi, edi
0x140038c7b  mov     rsi, r9
0x140038c7e  mov     rax, r8
0x140038c81  mov     rbx, rcx
0x140038c84  test    r9, r9
0x140038c87  jz      loc_140038D3F
0x140038c8d  test    rax, rax
0x140038c90  jz      loc_140038D3F
0x140038c96  cmp     [rcx], rdi
0x140038c99  jz      loc_140038D3F
0x140038c9f  mov     [rsp+0E8h+phHash], r9; phHash
0x140038ca4  xor     r8d, r8d; hKey
0x140038ca7  xor     r9d, r9d; dwFlags
0x140038caa  mov     rcx, rax; hProv
0x140038cad  call    cs:__imp_CryptCreateHash
0x140038cb3  test    eax, eax
0x140038cb5  jnz     short loc_140038CBF
0x140038cb7  lea     eax, [rdi+2]
0x140038cba  jmp     loc_140038D44
0x140038cbf  xor     edx, edx; Val
0x140038cc1  lea     rcx, [rsp+0E8h+String]; void *
0x140038cc6  mov     r8d, 88h; Size
0x140038ccc  call    memset_0
0x140038cd1  mov     rdx, [rbx]
0x140038cd4  lea     rcx, [rsp+0E8h+String]
0x140038cd9  call    ??0?$CW2AEX@$0IA@@ATL@@QEAA@PEBG@Z; ATL::CW2AEX<128>::CW2AEX<128>(ushort const *)
0x140038cde  mov     rcx, [rsp+0E8h+String]; String
0x140038ce3  test    rcx, rcx
0x140038ce6  jz      short loc_140038D27
0x140038ce8  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140038cec  inc     rdx
0x140038cef  cmp     [rcx+rdx], dil
0x140038cf3  jnz     short loc_140038CEC
0x140038cf5  inc     rdx; Size
0x140038cf8  call    cs:__imp__strlwr_s
0x140038cfe  mov     rbx, [rsp+0E8h+String]
0x140038d03  mov     rcx, rbx; lpString
0x140038d06  call    cs:__imp_lstrlenA
0x140038d0c  mov     rcx, [rsi]; hHash
0x140038d0f  xor     r9d, r9d; dwFlags
0x140038d12  mov     r8d, eax; dwDataLen
0x140038d15  mov     rdx, rbx; pbData
0x140038d18  call    cs:__imp_CryptHashData
0x140038d1e  mov     rcx, [rsp+0E8h+String]; Block
0x140038d23  test    eax, eax
0x140038d25  jnz     short loc_140038D2C
0x140038d27  mov     edi, 3
0x140038d2c  lea     rax, [rsp+0E8h+var_B0]
0x140038d31  cmp     rcx, rax
0x140038d34  jz      short loc_140038D3B
0x140038d36  call    free_0
0x140038d3b  mov     eax, edi
0x140038d3d  jmp     short loc_140038D44
0x140038d3f  mov     eax, 1
0x140038d44  mov     rcx, [rsp+0E8h+var_28]
0x140038d4c  xor     rcx, rsp; StackCookie
0x140038d4f  call    __security_check_cookie
0x140038d54  add     rsp, 0D0h
0x140038d5b  pop     rdi
0x140038d5c  pop     rsi
0x140038d5d  pop     rbx
0x140038d5e  retn
```
