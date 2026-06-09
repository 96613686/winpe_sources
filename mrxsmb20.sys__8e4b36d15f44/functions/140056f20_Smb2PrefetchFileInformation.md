# Smb2PrefetchFileInformation

- ea: `0x140056f20`
- end: `0x140057026`
- name: `Smb2PrefetchFileInformation`
- size: `262`
- prototype: `__int64 __fastcall(__int64, __int64, const void *, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14001cc00`

## callees

- `0x1400372c0`
- `0x140056f20`

## import_xrefs

- `mrxsmb!SmbCeAssociateExchangeWithCompoundingKeyEx` at `0x140056faa`
- `mrxsmb!SmbCeAssociateExchangeWithCompoundingKeyEx` at `0x140056faa`
- `mrxsmb!SmbCeInitiateExchange` at `0x140057002`
- `mrxsmb!SmbCeInitiateExchange` at `0x140057002`
- `mrxsmb!SmbCeInitializeExchange` at `0x140056f87`
- `mrxsmb!SmbCeInitializeExchange` at `0x140056f87`

## pseudocode

```c
__int64 __fastcall Smb2PrefetchFileInformation(__int64 a1, __int64 a2, const void *a3, unsigned int a4, __int64 a5)
{
  __int64 v5; // rbx
  __int64 result; // rax
  _QWORD v9[3]; // [rsp+40h] [rbp-18h] BYREF

  v5 = a4;
  v9[0] = 0;
  if ( a4 - 1 > 3 )
    return 3221225485LL;
  result = SmbCeInitializeExchange(
             v9,
             a1,
             0,
             0,
             0,
             *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 72) + 40LL) + 40LL),
             1384 * a4 + 2456,
             &PrefetchDispatch);
  if ( (int)result >= 0 )
  {
    if ( a2 )
      SmbCeAssociateExchangeWithCompoundingKeyEx(v9[0], a2, 0xFFFF);
    *(_DWORD *)(v9[0] + 1032LL) = v5;
    memmove((void *)(v9[0] + 1036LL), a3, 8 * v5);
    *(_QWORD *)(v9[0] + 1024LL) = a5;
    _InterlockedOr((volatile signed __int32 *)(v9[0] + 68LL), 0x400u);
    return SmbCeInitiateExchange(v9[0]);
  }
  return result;
}

```

## disassembly

```asm
0x140056f20  mov     r11, rsp
0x140056f23  mov     [r11+8], rbx
0x140056f27  mov     [r11+10h], rsi
0x140056f2b  push    rdi
0x140056f2c  sub     rsp, 50h
0x140056f30  mov     ebx, r9d
0x140056f33  mov     rsi, r8
0x140056f36  xor     r8d, r8d
0x140056f39  mov     rdi, rdx
0x140056f3c  mov     [r11-18h], r8
0x140056f40  lea     eax, [rbx-1]
0x140056f43  cmp     eax, 3
0x140056f46  ja      loc_14005701F
0x140056f4c  mov     rax, [rcx+48h]
0x140056f50  lea     rdx, PrefetchDispatch
0x140056f57  mov     [r11-20h], rdx
0x140056f5b  mov     rdx, rcx
0x140056f5e  imul    r9d, ebx, 568h
0x140056f65  lea     rcx, [r11-18h]
0x140056f69  mov     rax, [rax+28h]
0x140056f6d  add     r9d, 998h
0x140056f74  mov     rax, [rax+28h]
0x140056f78  mov     [r11-28h], r9d
0x140056f7c  xor     r9d, r9d
0x140056f7f  mov     [r11-30h], rax
0x140056f83  mov     [r11-38h], r8
0x140056f87  call    cs:__imp_SmbCeInitializeExchange
0x140056f8e  nop     dword ptr [rax+rax+00h]
0x140056f93  test    eax, eax
0x140056f95  js      short loc_14005700E
0x140056f97  test    rdi, rdi
0x140056f9a  jz      short loc_140056FB6
0x140056f9c  mov     rcx, [rsp+58h+var_18]
0x140056fa1  mov     r8d, 0FFFFh
0x140056fa7  mov     rdx, rdi
0x140056faa  call    cs:__imp_SmbCeAssociateExchangeWithCompoundingKeyEx
0x140056fb1  nop     dword ptr [rax+rax+00h]
0x140056fb6  mov     rax, [rsp+58h+var_18]
0x140056fbb  mov     r8, rbx
0x140056fbe  shl     r8, 3; Size
0x140056fc2  mov     rdx, rsi; Src
0x140056fc5  mov     [rax+408h], ebx
0x140056fcb  mov     rcx, [rsp+58h+var_18]
0x140056fd0  add     rcx, 40Ch; void *
0x140056fd7  call    memmove
0x140056fdc  mov     rax, [rsp+58h+var_18]
0x140056fe1  mov     rcx, [rsp+58h+arg_20]
0x140056fe9  mov     [rax+400h], rcx
0x140056ff0  mov     rax, [rsp+58h+var_18]
0x140056ff5  lock or dword ptr [rax+44h], 400h
0x140056ffd  mov     rcx, [rsp+58h+var_18]
0x140057002  call    cs:__imp_SmbCeInitiateExchange
0x140057009  nop     dword ptr [rax+rax+00h]
0x14005700e  mov     rbx, [rsp+58h+arg_0]
0x140057013  mov     rsi, [rsp+58h+arg_8]
0x140057018  add     rsp, 50h
0x14005701c  pop     rdi
0x14005701d  retn
0x14005701f  mov     eax, 0C000000Dh
0x140057024  jmp     short loc_14005700E
```
