# Smb2Negotiate_SendComplete

- ea: `0x140021f20`
- end: `0x140021f8b`
- name: `Smb2Negotiate_SendComplete`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140021f20`

## import_xrefs

- `mrxsmb!SmbCeSetExchangeExpiryTimeEx` at `0x14003c4ff`
- `mrxsmb!SmbCeSetExchangeExpiryTimeEx` at `0x14003c4ff`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140021f2e`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140021f5e`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14003c4dc`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140021f2e`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140021f5e`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14003c4dc`

## pseudocode

```c
__int64 __fastcall Smb2Negotiate_SendComplete(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  __int64 v5; // rcx
  __int64 ConfigurationBlock; // rcx
  __int64 v8; // r9
  __int64 v9; // rdx

  if ( a4 >= 0 && *(_DWORD *)(MRxSmbGetConfigurationBlock(a1) + 12) > 0xAu )
  {
    v5 = *(unsigned __int8 *)(*(_QWORD *)(a1 + 72) + 737LL);
    LOBYTE(v5) = (v5 & 3) - 1;
    if ( (v5 & 0xFD) == 0 )
    {
      ConfigurationBlock = MRxSmbGetConfigurationBlock(v5);
      if ( *(_DWORD *)(ConfigurationBlock + 12) / 6u >= 0xA )
        v9 = *(_DWORD *)(MRxSmbGetConfigurationBlock(ConfigurationBlock) + 12) / 6u;
      else
        v9 = 10;
      LOBYTE(v8) = 1;
      SmbCeSetExchangeExpiryTimeEx(a1, v9, 0, v8);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140021f20  push    rbx
0x140021f22  sub     rsp, 20h
0x140021f26  mov     rbx, rcx
0x140021f29  test    r9d, r9d
0x140021f2c  js      short loc_140021F55
0x140021f2e  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140021f35  nop     dword ptr [rax+rax+00h]
0x140021f3a  cmp     dword ptr [rax+0Ch], 0Ah
0x140021f3e  jbe     short loc_140021F55
0x140021f40  mov     rax, [rbx+48h]
0x140021f44  movzx   ecx, byte ptr [rax+2E1h]
0x140021f4b  and     cl, 3
0x140021f4e  dec     cl
0x140021f50  test    cl, 0FDh
0x140021f53  jz      short loc_140021F5E
0x140021f55  xor     eax, eax
0x140021f57  add     rsp, 20h
0x140021f5b  pop     rbx
0x140021f5c  retn
0x140021f5e  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140021f65  nop     dword ptr [rax+rax+00h]
0x140021f6a  mov     rcx, rax
0x140021f6d  mov     eax, 0AAAAAAABh
0x140021f72  mul     dword ptr [rcx+0Ch]
0x140021f75  shr     edx, 2
0x140021f78  cmp     edx, 0Ah
0x140021f7b  jnb     loc_14003C4DC
0x140021f81  mov     edx, 0Ah
0x140021f86  jmp     loc_14003C4F6
0x14003c4dc  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14003c4e3  nop     dword ptr [rax+rax+00h]
0x14003c4e8  mov     rcx, rax
0x14003c4eb  mov     eax, 0AAAAAAABh
0x14003c4f0  mul     dword ptr [rcx+0Ch]
0x14003c4f3  shr     edx, 2
0x14003c4f6  mov     r9b, 1
0x14003c4f9  xor     r8d, r8d
0x14003c4fc  mov     rcx, rbx
0x14003c4ff  call    cs:__imp_SmbCeSetExchangeExpiryTimeEx
0x14003c506  nop     dword ptr [rax+rax+00h]
0x14003c50b  nop
0x14003c50c  jmp     loc_140021F55
```
