# CryptoKey::~CryptoKey(void)

- ea: `0x14002b540`
- end: `0x14002b5ad`
- name: `??1CryptoKey@@QEAA@XZ`
- size: `109`
- prototype: `void __fastcall(CryptoKey *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14002aa18`
- `0x14002f8df`

## callees

- `0x14002b540`

## import_xrefs

- `ncrypt!NCryptDeleteKey` at `0x14002b56e`
- `ncrypt!NCryptFreeObject` at `0x14002b558`
- `ncrypt!NCryptFreeObject` at `0x14002b558`
- `ncrypt!NCryptFreeObject` at `0x14002b598`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x14002b5a1`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x14002b5a1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CryptoKey::~CryptoKey(CryptoKey *this)
{
  NCRYPT_HANDLE v2; // rcx
  NCRYPT_KEY_HANDLE v3; // rcx
  HCRYPTPROV v4; // rcx
  int v5; // edx

  if ( *((_DWORD *)this + 8) )
  {
    v2 = *((_QWORD *)this + 2);
    if ( v2 )
      NCryptFreeObject(v2);
    v3 = *((_QWORD *)this + 3);
    if ( v3 )
      NCryptDeleteKey(v3, 0);
  }
  else
  {
    v4 = *(_QWORD *)this;
    if ( v4 && *((_DWORD *)this + 2) )
    {
      v5 = *((_DWORD *)this + 3);
      if ( (unsigned int)(v5 - 1) <= 1 )
      {
        CryptReleaseContext(v4, 0);
      }
      else if ( v5 == -1 )
      {
        NCryptFreeObject(v4);
      }
    }
  }
}

```

## disassembly

```asm
0x14002b540  push    rbx
0x14002b542  sub     rsp, 20h
0x14002b546  cmp     dword ptr [rcx+20h], 0
0x14002b54a  mov     rbx, rcx
0x14002b54d  jz      short loc_14002B575
0x14002b54f  mov     rcx, [rcx+10h]; hObject
0x14002b553  test    rcx, rcx
0x14002b556  jz      short loc_14002B55E
0x14002b558  call    cs:__imp_NCryptFreeObject
0x14002b55e  mov     rcx, [rbx+18h]
0x14002b562  test    rcx, rcx
0x14002b565  jz      short loc_14002B5A7
0x14002b567  xor     edx, edx
0x14002b569  add     rsp, 20h
0x14002b56d  pop     rbx
0x14002b56e  jmp     cs:__imp_NCryptDeleteKey
0x14002b575  mov     rcx, [rcx]; hProv
0x14002b578  test    rcx, rcx
0x14002b57b  jz      short loc_14002B5A7
0x14002b57d  cmp     dword ptr [rbx+8], 0
0x14002b581  jz      short loc_14002B5A7
0x14002b583  mov     edx, [rbx+0Ch]
0x14002b586  lea     eax, [rdx-1]
0x14002b589  cmp     eax, 1
0x14002b58c  jbe     short loc_14002B59F
0x14002b58e  cmp     edx, 0FFFFFFFFh
0x14002b591  jnz     short loc_14002B5A7
0x14002b593  add     rsp, 20h
0x14002b597  pop     rbx
0x14002b598  jmp     cs:__imp_NCryptFreeObject
0x14002b59f  xor     edx, edx; dwFlags
0x14002b5a1  call    cs:__imp_CryptReleaseContext
0x14002b5a7  add     rsp, 20h
0x14002b5ab  pop     rbx
0x14002b5ac  retn
```
