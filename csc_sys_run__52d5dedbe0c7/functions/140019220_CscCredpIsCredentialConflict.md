# CscCredpIsCredentialConflict

- ea: `0x140019220`
- end: `0x14001927e`
- name: `CscCredpIsCredentialConflict`
- size: `94`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140048cf8`
- `0x140085b44`

## callees

- `0x140018930`
- `0x140019220`

## import_xrefs

- `rdbss!RxIsCompatibleSecurityContext` at `0x140019226`
- `rdbss!RxIsCompatibleSecurityContext` at `0x140019226`

## pseudocode

```c
__int64 CscCredpIsCredentialConflict()
{
  unsigned int IsCompatibleSecurityContext; // ebx

  IsCompatibleSecurityContext = RxIsCompatibleSecurityContext();
  if ( IsCompatibleSecurityContext == -1073741802 )
    IsCompatibleSecurityContext = -1073740768;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      16,
      WPP_d765a1722ddb33a90f589cef06fc1524_Traceguids,
      IsCompatibleSecurityContext);
  return IsCompatibleSecurityContext;
}

```

## disassembly

```asm
0x140019220  push    rbx
0x140019222  sub     rsp, 20h
0x140019226  call    cs:__imp_RxIsCompatibleSecurityContext
0x14001922d  nop     dword ptr [rax+rax+00h]
0x140019232  mov     ebx, eax
0x140019234  mov     eax, 0C0000420h
0x140019239  cmp     ebx, 0C0000016h
0x14001923f  cmovz   ebx, eax
0x140019242  mov     rcx, cs:WPP_GLOBAL_Control
0x140019249  lea     rax, WPP_GLOBAL_Control
0x140019250  cmp     rcx, rax
0x140019253  jz      short loc_140019275
0x140019255  mov     edx, [rcx+2Ch]
0x140019258  test    dl, 40h
0x14001925b  jz      short loc_140019275
0x14001925d  mov     rcx, [rcx+18h]
0x140019261  lea     r8, WPP_d765a1722ddb33a90f589cef06fc1524_Traceguids
0x140019268  mov     edx, 10h
0x14001926d  mov     r9d, ebx
0x140019270  call    WPP_SF_d
0x140019275  mov     eax, ebx
0x140019277  add     rsp, 20h
0x14001927b  pop     rbx
0x14001927c  retn
```
