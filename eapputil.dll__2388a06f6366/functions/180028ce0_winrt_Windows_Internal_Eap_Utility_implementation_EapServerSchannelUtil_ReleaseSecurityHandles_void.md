# winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil::ReleaseSecurityHandles(void)

- ea: `0x180028ce0`
- end: `0x180028d4a`
- name: `?ReleaseSecurityHandles@EapServerSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@AEAAXXZ`
- size: `106`
- prototype: `void __fastcall(winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002609c`
- `0x180028528`

## callees

- `0x180028ce0`

## import_xrefs

- `SspiCli!DeleteSecurityContext` at `0x180028d08`
- `SspiCli!DeleteSecurityContext` at `0x180028d08`
- `SspiCli!FreeCredentialsHandle` at `0x180028d27`
- `SspiCli!FreeCredentialsHandle` at `0x180028d27`

## pseudocode

```c
void __fastcall winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil::ReleaseSecurityHandles(
        struct _SecHandle *this)
{
  struct _SecHandle *v1; // rdi

  v1 = this + 2;
  if ( this[2].dwLower != -1 && this[2].dwUpper != -1 )
  {
    DeleteSecurityContext(v1);
    this[2].dwUpper = -1;
    v1->dwLower = -1;
  }
  if ( this[3].dwLower != -1 && this[3].dwUpper != -1 )
  {
    FreeCredentialsHandle(this + 3);
    ++LODWORD(this[10].dwLower);
    this[3].dwUpper = -1;
    this[3].dwLower = -1;
  }
}

```

## disassembly

```asm
0x180028ce0  mov     [rsp+arg_0], rbx
0x180028ce5  mov     [rsp+arg_8], rsi
0x180028cea  push    rdi
0x180028ceb  sub     rsp, 20h
0x180028cef  lea     rdi, [rcx+20h]
0x180028cf3  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180028cf7  mov     rbx, rcx
0x180028cfa  cmp     [rdi], rsi
0x180028cfd  jz      short loc_180028D15
0x180028cff  cmp     [rcx+28h], rsi
0x180028d03  jz      short loc_180028D15
0x180028d05  mov     rcx, rdi; phContext
0x180028d08  call    cs:__imp_DeleteSecurityContext
0x180028d0e  mov     [rbx+28h], rsi
0x180028d12  mov     [rdi], rsi
0x180028d15  lea     rdi, [rbx+30h]
0x180028d19  cmp     [rdi], rsi
0x180028d1c  jz      short loc_180028D3A
0x180028d1e  cmp     [rbx+38h], rsi
0x180028d22  jz      short loc_180028D3A
0x180028d24  mov     rcx, rdi; phCredential
0x180028d27  call    cs:__imp_FreeCredentialsHandle
0x180028d2d  inc     dword ptr [rbx+0A0h]
0x180028d33  mov     [rbx+38h], rsi
0x180028d37  mov     [rdi], rsi
0x180028d3a  mov     rbx, [rsp+28h+arg_0]
0x180028d3f  mov     rsi, [rsp+28h+arg_8]
0x180028d44  add     rsp, 20h
0x180028d48  pop     rdi
0x180028d49  retn
```
