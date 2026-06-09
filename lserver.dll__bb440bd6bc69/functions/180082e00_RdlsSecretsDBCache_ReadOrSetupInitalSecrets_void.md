# RdlsSecretsDBCache::ReadOrSetupInitalSecrets(void)

- ea: `0x180082e00`
- end: `0x180082fe8`
- name: `?ReadOrSetupInitalSecrets@RdlsSecretsDBCache@@AEAAKXZ`
- size: `488`
- prototype: `unsigned int __fastcall(RdlsSecretsDBCache *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18007e12c`

## callees

- `0x180005665`
- `0x180066200`
- `0x1800662d0`
- `0x180066684`
- `0x18008297c`
- `0x180082e00`
- `0x1800a0fb0`
- `0x1800a5010`

## import_xrefs

- `msvcrt!wcsncmp` at `0x180082f48`
- `msvcrt!wcsncmp` at `0x180082f72`
- `msvcrt!wcsncmp` at `0x180082f48`
- `msvcrt!wcsncmp` at `0x180082f72`
- `msvcrt!wcscpy_s` at `0x180082f8e`
- `msvcrt!wcscpy_s` at `0x180082f8e`
- `KERNEL32!GetComputerNameW` at `0x180082e5f`
- `KERNEL32!GetComputerNameW` at `0x180082e5f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RdlsSecretsDBCache::ReadOrSetupInitalSecrets(RdlsSecretsDBCache *this)
{
  unsigned int InsertOrUpdateRdlsSecrets; // ebx
  DWORD nSize; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD v5[3]; // [rsp+34h] [rbp-CCh] BYREF
  _BYTE v6[98]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[257]; // [rsp+A2h] [rbp-5Eh] BYREF
  int v8; // [rsp+2A4h] [rbp+1A4h]

  __RdlsSecret::__RdlsSecret((__RdlsSecret *)v6);
  nSize = 512;
  memset_0(v6, 0, 0x2D8u);
  GetComputerNameW(Buffer, &nSize);
  v5[0] = 1;
  v8 = 1;
  (*(void (__fastcall **)(_QWORD, _BYTE *, __int64, char *, _DWORD *))(**((_QWORD **)this + 102) + 240LL))(
    *((_QWORD *)this + 102),
    v6,
    4,
    (char *)this + 88,
    v5);
  InsertOrUpdateRdlsSecrets = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 102) + 488LL))(*((_QWORD *)this + 102));
  if ( InsertOrUpdateRdlsSecrets == -1601 )
  {
    __RdlsSecret::Cleanup((RdlsSecretsDBCache *)((char *)this + 88));
    v8 = 1;
    if ( RdlsSecretsDBCache::FindInsertOrUpdateRdlsSecrets(this, (struct __RdlsSecret *)v6, 4u)
      || ((*(void (__fastcall **)(_QWORD, _BYTE *, __int64, char *, _DWORD *))(**((_QWORD **)this + 102) + 240LL))(
            *((_QWORD *)this + 102),
            v6,
            2,
            (char *)this + 88,
            v5),
          (InsertOrUpdateRdlsSecrets = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 102) + 488LL))(*((_QWORD *)this + 102))) != 0)
      || wcsncmp(Buffer, (const wchar_t *)this + 93, nSize) )
    {
      InsertOrUpdateRdlsSecrets = -1072693245;
    }
  }
  else if ( wcsncmp(Buffer, (const wchar_t *)this + 93, nSize) )
  {
    wcscpy_s((wchar_t *)this + 93, 0x100u, Buffer);
    *((_DWORD *)this + 175) = 0;
    InsertOrUpdateRdlsSecrets = RdlsSecretsDBCache::FindInsertOrUpdateRdlsSecrets(
                                  this,
                                  (RdlsSecretsDBCache *)((char *)this + 88),
                                  0xFFFCu);
  }
  __RdlsSecret::~__RdlsSecret((__RdlsSecret *)v6);
  return InsertOrUpdateRdlsSecrets;
}

```

## disassembly

```asm
0x180082e00  mov     [rsp-8+arg_8], rbx
0x180082e05  mov     [rsp-8+arg_10], rsi
0x180082e0a  push    rbp
0x180082e0b  push    rdi
0x180082e0c  push    r14
0x180082e0e  lea     rbp, [rsp-230h]
0x180082e16  sub     rsp, 330h
0x180082e1d  mov     rax, cs:__security_cookie
0x180082e24  xor     rax, rsp
0x180082e27  mov     [rbp+240h+var_20], rax
0x180082e2e  mov     rdi, rcx
0x180082e31  lea     rcx, [rsp+340h+var_300]; this
0x180082e36  call    ??0__RdlsSecret@@QEAA@XZ; __RdlsSecret::__RdlsSecret(void)
0x180082e3b  nop
0x180082e3c  mov     [rsp+340h+nSize], 200h
0x180082e44  xor     edx, edx; Val
0x180082e46  mov     r8d, 2D8h; Size
0x180082e4c  lea     rcx, [rsp+340h+var_300]; void *
0x180082e51  call    memset_0
0x180082e56  lea     rdx, [rsp+340h+nSize]; nSize
0x180082e5b  lea     rcx, [rbp+240h+Buffer]; lpBuffer
0x180082e5f  call    cs:__imp_GetComputerNameW
0x180082e66  nop     dword ptr [rax+rax+00h]
0x180082e6b  mov     esi, 1
0x180082e70  mov     [rsp+340h+var_30C], esi
0x180082e74  mov     [rbp+240h+var_9C], esi
0x180082e7a  mov     rcx, [rdi+330h]
0x180082e81  mov     rax, [rcx]
0x180082e84  lea     r14, [rdi+58h]
0x180082e88  lea     rdx, [rsp+340h+var_30C]
0x180082e8d  mov     [rsp+340h+var_320], rdx
0x180082e92  mov     r9, r14
0x180082e95  lea     r8d, [rsi+3]
0x180082e99  lea     rdx, [rsp+340h+var_300]
0x180082e9e  mov     rax, [rax+0F0h]
0x180082ea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082eaa  mov     rcx, [rdi+330h]
0x180082eb1  mov     rax, [rcx]
0x180082eb4  mov     rax, [rax+1E8h]
0x180082ebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082ec0  mov     ebx, eax
0x180082ec2  cmp     eax, 0FFFFF9BFh
0x180082ec7  jnz     loc_180082F5F
0x180082ecd  mov     rcx, r14; this
0x180082ed0  call    ?Cleanup@__RdlsSecret@@QEAAXXZ; __RdlsSecret::Cleanup(void)
0x180082ed5  mov     [rbp+240h+var_9C], esi
0x180082edb  lea     r8d, [rsi+3]; unsigned int
0x180082edf  lea     rdx, [rsp+340h+var_300]; struct __RdlsSecret *
0x180082ee4  mov     rcx, rdi; this
0x180082ee7  call    ?FindInsertOrUpdateRdlsSecrets@RdlsSecretsDBCache@@AEAAKAEAU__RdlsSecret@@K@Z; RdlsSecretsDBCache::FindInsertOrUpdateRdlsSecrets(__RdlsSecret &,ulong)
0x180082eec  test    eax, eax
0x180082eee  jnz     short loc_180082F58
0x180082ef0  mov     rcx, [rdi+330h]
0x180082ef7  mov     rax, [rcx]
0x180082efa  lea     rdx, [rsp+340h+var_30C]
0x180082eff  mov     [rsp+340h+var_320], rdx
0x180082f04  mov     r9, r14
0x180082f07  lea     r8d, [rsi+1]
0x180082f0b  lea     rdx, [rsp+340h+var_300]
0x180082f10  mov     rax, [rax+0F0h]
0x180082f17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082f1c  mov     rcx, [rdi+330h]
0x180082f23  mov     rax, [rcx]
0x180082f26  mov     rax, [rax+1E8h]
0x180082f2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082f32  mov     ebx, eax
0x180082f34  test    eax, eax
0x180082f36  jnz     short loc_180082F58
0x180082f38  mov     r8d, [rsp+340h+nSize]; MaxCount
0x180082f3d  lea     rdx, [rdi+0BAh]; String2
0x180082f44  lea     rcx, [rbp+240h+Buffer]; String1
0x180082f48  call    cs:__imp_wcsncmp
0x180082f4f  nop     dword ptr [rax+rax+00h]
0x180082f54  test    eax, eax
0x180082f56  jz      short loc_180082FB4
0x180082f58  mov     ebx, 0C0100003h
0x180082f5d  jmp     short loc_180082FB4
0x180082f5f  lea     rsi, [rdi+0BAh]
0x180082f66  mov     r8d, [rsp+340h+nSize]; MaxCount
0x180082f6b  mov     rdx, rsi; String2
0x180082f6e  lea     rcx, [rbp+240h+Buffer]; String1
0x180082f72  call    cs:__imp_wcsncmp
0x180082f79  nop     dword ptr [rax+rax+00h]
0x180082f7e  test    eax, eax
0x180082f80  jz      short loc_180082FB4
0x180082f82  lea     r8, [rbp+240h+Buffer]; Source
0x180082f86  mov     edx, 100h; SizeInWords
0x180082f8b  mov     rcx, rsi; Destination
0x180082f8e  call    cs:__imp_wcscpy_s
0x180082f95  nop     dword ptr [rax+rax+00h]
0x180082f9a  and     dword ptr [rdi+2BCh], 0
0x180082fa1  mov     r8d, 0FFFCh; unsigned int
0x180082fa7  mov     rdx, r14; struct __RdlsSecret *
0x180082faa  mov     rcx, rdi; this
0x180082fad  call    ?FindInsertOrUpdateRdlsSecrets@RdlsSecretsDBCache@@AEAAKAEAU__RdlsSecret@@K@Z; RdlsSecretsDBCache::FindInsertOrUpdateRdlsSecrets(__RdlsSecret &,ulong)
0x180082fb2  mov     ebx, eax
0x180082fb4  lea     rcx, [rsp+340h+var_300]; this
0x180082fb9  call    ??1__RdlsSecret@@QEAA@XZ; __RdlsSecret::~__RdlsSecret(void)
0x180082fbe  mov     eax, ebx
0x180082fc0  mov     rcx, [rbp+240h+var_20]
0x180082fc7  xor     rcx, rsp; StackCookie
0x180082fca  call    __security_check_cookie
0x180082fcf  lea     r11, [rsp+340h+var_10]
0x180082fd7  mov     rbx, [r11+28h]
0x180082fdb  mov     rsi, [r11+30h]
0x180082fdf  mov     rsp, r11
0x180082fe2  pop     r14
0x180082fe4  pop     rdi
0x180082fe5  pop     rbp
0x180082fe6  retn
```
