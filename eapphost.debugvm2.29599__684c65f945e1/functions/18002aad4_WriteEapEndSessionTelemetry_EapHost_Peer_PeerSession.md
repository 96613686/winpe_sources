# WriteEapEndSessionTelemetry(EapHost::Peer::PeerSession &)

- ea: `0x18002aad4`
- end: `0x18002ab84`
- name: `?WriteEapEndSessionTelemetry@@YAXAEAVPeerSession@Peer@EapHost@@@Z`
- size: `176`
- prototype: `void __fastcall(struct EapHost::Peer::PeerSession *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180024a8c`

## callees

- `0x18001261c`
- `0x180012f8c`
- `0x180023280`
- `0x1800245b4`
- `0x18002aad4`
- `0x180033b68`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002ab3e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002ab3e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall WriteEapEndSessionTelemetry(struct EapHost::Peer::PeerSession *a1)
{
  unsigned int v2; // esi
  __int64 *v3; // rax
  unsigned int v4; // edx
  unsigned int v5; // ebx
  DWORD TickCount; // eax
  unsigned int v7; // edx
  char v8; // [rsp+30h] [rbp-18h]
  __int64 v9; // [rsp+50h] [rbp+8h] BYREF
  EapHost::EapError *v10; // [rsp+58h] [rbp+10h] BYREF

  if ( a1 )
  {
    v2 = 0;
    if ( *((_BYTE *)a1 + 360) )
    {
      v9 = 0;
      v3 = (__int64 *)EapHost::Peer::PeerSession::LastEapError(a1, &v10);
      crt_ptr<_EAP_ERROR>::Assign(&v9, *v3);
      std::unique_ptr<EapHost::EapError>::~unique_ptr<EapHost::EapError>(&v10, v4);
      if ( v9 )
        v2 = *(_DWORD *)(v9 + 20);
      crt_ptr<_EAP_ERROR>::Clear(&v9);
    }
    v5 = *((_DWORD *)a1 + 91);
    TickCount = GetTickCount();
    v7 = TickCount - v5;
    if ( TickCount < v5 )
      v7 = 0;
    EapHostTelemetry::EapEndSession(
      (const struct _GUID *)((char *)a1 + 244),
      *((_DWORD *)a1 + 14),
      *((_BYTE *)a1 + 268),
      *((_BYTE *)a1 + 132),
      v7,
      v2,
      v8);
  }
}

```

## disassembly

```asm
0x18002aad4  test    rcx, rcx
0x18002aad7  jz      locret_18002AB83
0x18002aadd  mov     rax, rsp
0x18002aae0  mov     [rax+18h], rbx
0x18002aae4  mov     [rax+20h], rsi
0x18002aae8  push    rdi
0x18002aae9  sub     rsp, 40h
0x18002aaed  mov     rdi, rcx
0x18002aaf0  xor     esi, esi
0x18002aaf2  cmp     [rcx+168h], sil
0x18002aaf9  jz      short loc_18002AB38
0x18002aafb  mov     [rax+8], rsi
0x18002aaff  lea     rdx, [rax+10h]
0x18002ab03  call    ?LastEapError@PeerSession@Peer@EapHost@@QEBA?AV?$unique_ptr@VEapError@EapHost@@U?$default_delete@VEapError@EapHost@@@std@@@std@@XZ; EapHost::Peer::PeerSession::LastEapError(void)
0x18002ab08  nop
0x18002ab09  mov     rdx, [rax]
0x18002ab0c  lea     rcx, [rsp+48h+arg_0]
0x18002ab11  call    ?Assign@?$crt_ptr@U_EAP_ERROR@@@@QEAAXPEBU_EAP_ERROR@@@Z; crt_ptr<_EAP_ERROR>::Assign(_EAP_ERROR const *)
0x18002ab16  nop
0x18002ab17  lea     rcx, [rsp+48h+arg_8]
0x18002ab1c  call    ??1?$unique_ptr@VEapError@EapHost@@U?$default_delete@VEapError@EapHost@@@std@@@std@@QEAA@XZ; std::unique_ptr<EapHost::EapError>::~unique_ptr<EapHost::EapError>(void)
0x18002ab21  mov     rax, [rsp+48h+arg_0]
0x18002ab26  test    rax, rax
0x18002ab29  jz      short loc_18002AB2E
0x18002ab2b  mov     esi, [rax+14h]
0x18002ab2e  lea     rcx, [rsp+48h+arg_0]
0x18002ab33  call    ?Clear@?$crt_ptr@U_EAP_ERROR@@@@QEAAXXZ; crt_ptr<_EAP_ERROR>::Clear(void)
0x18002ab38  mov     ebx, [rdi+16Ch]
0x18002ab3e  call    cs:__imp_GetTickCount
0x18002ab44  mov     edx, eax
0x18002ab46  sub     edx, ebx
0x18002ab48  xor     ecx, ecx
0x18002ab4a  cmp     eax, ebx
0x18002ab4c  cmovb   edx, ecx
0x18002ab4f  lea     rcx, [rdi+0F4h]; struct _GUID *
0x18002ab56  mov     [rsp+48h+var_20], esi; unsigned int
0x18002ab5a  mov     [rsp+48h+var_28], edx; unsigned int
0x18002ab5e  mov     r9b, [rdi+84h]; unsigned __int8
0x18002ab65  mov     r8b, [rdi+10Ch]; unsigned __int8
0x18002ab6c  mov     edx, [rdi+38h]; unsigned int
0x18002ab6f  call    ?EapEndSession@EapHostTelemetry@@SAXAEBU_GUID@@IEEIIH@Z; EapHostTelemetry::EapEndSession(_GUID const &,uint,uchar,uchar,uint,uint,int)
0x18002ab74  mov     rbx, [rsp+48h+arg_10]
0x18002ab79  mov     rsi, [rsp+48h+arg_18]
0x18002ab7e  add     rsp, 40h
0x18002ab82  pop     rdi
0x18002ab83  retn
```
