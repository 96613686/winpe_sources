# SmbCeUpdateSrvCall

- ea: `0x14001221c`
- end: `0x1400122a1`
- name: `SmbCeUpdateSrvCall`
- size: `133`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1400010f0`
- `0x140013700`
- `0x14003df64`

## callees

- `0x14001221c`

## import_xrefs

- `rdbss!RxSetSrvCallDomainName` at `0x14001223c`
- `rdbss!RxSetSrvCallDomainName` at `0x14001223c`

## pseudocode

```c
__int64 __fastcall SmbCeUpdateSrvCall(__int64 a1)
{
  __int64 v1; // rdi
  unsigned int v2; // r8d
  NTSTATUS v4; // eax
  _DWORD *v5; // rdx

  v1 = *(_QWORD *)(a1 + 48);
  v2 = 0;
  if ( v1 )
  {
    v4 = RxSetSrvCallDomainName(*(PMRX_SRV_CALL *)(a1 + 48), (PUNICODE_STRING)(a1 + 96));
    v5 = (_DWORD *)(v1 + 96);
    v2 = v4;
    if ( _bittest16((const signed __int16 *)(a1 + 500), 0xCu) )
      *v5 |= 0x10u;
    if ( (*(_BYTE *)(a1 + 500) & 0x10) != 0 )
      *v5 |= 0x100u;
    if ( (*(_BYTE *)(a1 + 500) & 0x20) != 0 )
      *v5 |= 0x400u;
    if ( *(_BYTE *)(a1 + 505) )
      *v5 |= 0x80u;
    if ( (*(_BYTE *)(a1 + 500) & 0x20) != 0 )
      *v5 |= 0x400u;
  }
  return v2;
}

```

## disassembly

```asm
0x14001221c  mov     [rsp+arg_0], rbx
0x140012221  push    rdi
0x140012222  sub     rsp, 20h
0x140012226  mov     rdi, [rcx+30h]
0x14001222a  xor     r8d, r8d
0x14001222d  mov     rbx, rcx
0x140012230  test    rdi, rdi
0x140012233  jz      short loc_140012292
0x140012235  lea     rdx, [rcx+60h]; DomainName
0x140012239  mov     rcx, rdi; SrvCall
0x14001223c  call    cs:__imp_RxSetSrvCallDomainName
0x140012243  nop     dword ptr [rax+rax+00h]
0x140012248  bt      word ptr [rbx+1F4h], 0Ch
0x140012251  lea     rdx, [rdi+60h]
0x140012255  mov     r8d, eax
0x140012258  jnb     short loc_14001225D
0x14001225a  or      dword ptr [rdx], 10h
0x14001225d  test    byte ptr [rbx+1F4h], 10h
0x140012264  jz      short loc_14001226A
0x140012266  bts     dword ptr [rdx], 8
0x14001226a  test    byte ptr [rbx+1F4h], 20h
0x140012271  mov     ecx, 400h
0x140012276  jz      short loc_14001227A
0x140012278  or      [rdx], ecx
0x14001227a  cmp     byte ptr [rbx+1F9h], 0
0x140012281  jz      short loc_140012287
0x140012283  bts     dword ptr [rdx], 7
0x140012287  test    byte ptr [rbx+1F4h], 20h
0x14001228e  jz      short loc_140012292
0x140012290  or      [rdx], ecx
0x140012292  mov     rbx, [rsp+28h+arg_0]
0x140012297  mov     eax, r8d
0x14001229a  add     rsp, 20h
0x14001229e  pop     rdi
0x14001229f  retn
```
