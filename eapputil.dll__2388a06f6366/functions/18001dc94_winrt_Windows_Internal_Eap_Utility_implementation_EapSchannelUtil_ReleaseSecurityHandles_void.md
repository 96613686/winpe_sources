# winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::ReleaseSecurityHandles(void)

- ea: `0x18001dc94`
- end: `0x18001dd04`
- name: `?ReleaseSecurityHandles@EapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@AEAAXXZ`
- size: `112`
- prototype: `void __fastcall(winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800178dc`
- `0x18001ca90`

## callees

- `0x18001dc94`

## import_xrefs

- `SspiCli!DeleteSecurityContext` at `0x18001dcbf`
- `SspiCli!DeleteSecurityContext` at `0x18001dcbf`
- `SspiCli!FreeCredentialsHandle` at `0x18001dce1`
- `SspiCli!FreeCredentialsHandle` at `0x18001dce1`

## pseudocode

```c
void __fastcall winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::ReleaseSecurityHandles(
        winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil *this)
{
  struct _SecHandle *v1; // rdi

  v1 = (struct _SecHandle *)((char *)this + 120);
  if ( *((_QWORD *)this + 15) != -1 && *((_QWORD *)this + 16) != -1 )
  {
    DeleteSecurityContext(v1);
    *((_QWORD *)this + 16) = -1;
    v1->dwLower = -1;
  }
  if ( *((_QWORD *)this + 13) != -1 && *((_QWORD *)this + 14) != -1 )
  {
    FreeCredentialsHandle((PCredHandle)((char *)this + 104));
    ++*((_DWORD *)this + 48);
    *((_QWORD *)this + 14) = -1;
    *((_QWORD *)this + 13) = -1;
  }
}

```

## disassembly

```asm
0x18001dc94  mov     [rsp+arg_0], rbx
0x18001dc99  mov     [rsp+arg_8], rsi
0x18001dc9e  push    rdi
0x18001dc9f  sub     rsp, 20h
0x18001dca3  lea     rdi, [rcx+78h]
0x18001dca7  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001dcab  mov     rbx, rcx
0x18001dcae  cmp     [rdi], rsi
0x18001dcb1  jz      short loc_18001DCCF
0x18001dcb3  cmp     [rcx+80h], rsi
0x18001dcba  jz      short loc_18001DCCF
0x18001dcbc  mov     rcx, rdi; phContext
0x18001dcbf  call    cs:__imp_DeleteSecurityContext
0x18001dcc5  mov     [rbx+80h], rsi
0x18001dccc  mov     [rdi], rsi
0x18001dccf  lea     rdi, [rbx+68h]
0x18001dcd3  cmp     [rdi], rsi
0x18001dcd6  jz      short loc_18001DCF4
0x18001dcd8  cmp     [rbx+70h], rsi
0x18001dcdc  jz      short loc_18001DCF4
0x18001dcde  mov     rcx, rdi; phCredential
0x18001dce1  call    cs:__imp_FreeCredentialsHandle
0x18001dce7  inc     dword ptr [rbx+0C0h]
0x18001dced  mov     [rbx+70h], rsi
0x18001dcf1  mov     [rdi], rsi
0x18001dcf4  mov     rbx, [rsp+28h+arg_0]
0x18001dcf9  mov     rsi, [rsp+28h+arg_8]
0x18001dcfe  add     rsp, 20h
0x18001dd02  pop     rdi
0x18001dd03  retn
```
