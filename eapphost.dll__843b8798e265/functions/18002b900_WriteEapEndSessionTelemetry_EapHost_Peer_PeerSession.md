# WriteEapEndSessionTelemetry(EapHost::Peer::PeerSession &)

- ea: `0x18002b900`
- end: `0x18002b9b7`
- name: `?WriteEapEndSessionTelemetry@@YAXAEAVPeerSession@Peer@EapHost@@@Z`
- size: `183`
- prototype: `void __fastcall(struct EapHost::Peer::PeerSession *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180025770`

## callees

- `0x180012da8`
- `0x180013734`
- `0x180023f10`
- `0x180025290`
- `0x18002b900`
- `0x180034f1c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002b96a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002b96a`

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
0x18002b900  test    rcx, rcx
0x18002b903  jz      locret_18002B9B5
0x18002b909  mov     rax, rsp
0x18002b90c  mov     [rax+18h], rbx
0x18002b910  mov     [rax+20h], rsi
0x18002b914  push    rdi
0x18002b915  sub     rsp, 40h
0x18002b919  mov     rdi, rcx
0x18002b91c  xor     esi, esi
0x18002b91e  cmp     [rcx+168h], sil
0x18002b925  jz      short loc_18002B964
0x18002b927  mov     [rax+8], rsi
0x18002b92b  lea     rdx, [rax+10h]
0x18002b92f  call    ?LastEapError@PeerSession@Peer@EapHost@@QEBA?AV?$unique_ptr@VEapError@EapHost@@U?$default_delete@VEapError@EapHost@@@std@@@std@@XZ; EapHost::Peer::PeerSession::LastEapError(void)
0x18002b934  nop
0x18002b935  mov     rdx, [rax]
0x18002b938  lea     rcx, [rsp+48h+arg_0]
0x18002b93d  call    ?Assign@?$crt_ptr@U_EAP_ERROR@@@@QEAAXPEBU_EAP_ERROR@@@Z; crt_ptr<_EAP_ERROR>::Assign(_EAP_ERROR const *)
0x18002b942  nop
0x18002b943  lea     rcx, [rsp+48h+arg_8]
0x18002b948  call    ??1?$unique_ptr@VEapError@EapHost@@U?$default_delete@VEapError@EapHost@@@std@@@std@@QEAA@XZ; std::unique_ptr<EapHost::EapError>::~unique_ptr<EapHost::EapError>(void)
0x18002b94d  mov     rax, [rsp+48h+arg_0]
0x18002b952  test    rax, rax
0x18002b955  jz      short loc_18002B95A
0x18002b957  mov     esi, [rax+14h]
0x18002b95a  lea     rcx, [rsp+48h+arg_0]
0x18002b95f  call    ?Clear@?$crt_ptr@U_EAP_ERROR@@@@QEAAXXZ; crt_ptr<_EAP_ERROR>::Clear(void)
0x18002b964  mov     ebx, [rdi+16Ch]
0x18002b96a  call    cs:__imp_GetTickCount
0x18002b971  nop     dword ptr [rax+rax+00h]
0x18002b976  mov     edx, eax
0x18002b978  sub     edx, ebx
0x18002b97a  xor     ecx, ecx
0x18002b97c  cmp     eax, ebx
0x18002b97e  cmovb   edx, ecx
0x18002b981  lea     rcx, [rdi+0F4h]; struct _GUID *
0x18002b988  mov     [rsp+48h+var_20], esi; unsigned int
0x18002b98c  mov     [rsp+48h+var_28], edx; unsigned int
0x18002b990  mov     r9b, [rdi+84h]; unsigned __int8
0x18002b997  mov     r8b, [rdi+10Ch]; unsigned __int8
0x18002b99e  mov     edx, [rdi+38h]; unsigned int
0x18002b9a1  call    ?EapEndSession@EapHostTelemetry@@SAXAEBU_GUID@@IEEIIH@Z; EapHostTelemetry::EapEndSession(_GUID const &,uint,uchar,uchar,uint,uint,int)
0x18002b9a6  mov     rbx, [rsp+48h+arg_10]
0x18002b9ab  mov     rsi, [rsp+48h+arg_18]
0x18002b9b0  add     rsp, 40h
0x18002b9b4  pop     rdi
0x18002b9b5  retn
```
