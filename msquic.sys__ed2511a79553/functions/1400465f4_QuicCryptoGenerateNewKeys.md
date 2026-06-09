# QuicCryptoGenerateNewKeys

- ea: `0x1400465f4`
- end: `0x140046704`
- name: `QuicCryptoGenerateNewKeys`
- size: `272`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140001d6c`
- `0x140012f10`
- `0x140017580`

## callees

- `0x140008ef0`
- `0x1400291f0`
- `0x14003fdf8`
- `0x1400465f4`
- `0x14004a1f8`

## string_xrefs

- `0x140046674`: `Failed to update read packet key.`
- `0x1400466a2`: `Failed to update write packet key`

## pseudocode

```c
__int64 __fastcall QuicCryptoGenerateNewKeys(__int64 a1)
{
  int v1; // edx
  PVOID *v2; // rsi
  int v3; // edi
  __int64 v5; // rax
  __int64 v6; // rcx
  char **v7; // rbp
  const char *v8; // rax

  v1 = *(_DWORD *)(a1 + 3636);
  v2 = (PVOID *)(a1 + 2912);
  v3 = 0;
  v5 = 0;
  v6 = (__int64)QuicSupportedVersionList;
  while ( *(_DWORD *)v6 != v1 )
  {
    v5 = (unsigned int)(v5 + 1);
    v6 += 88;
    if ( (unsigned int)v5 >= 4 )
    {
      v7 = off_14004C048;
      goto LABEL_6;
    }
  }
  v6 = 88 * v5;
  v7 = &off_14004C048[11 * v5];
LABEL_6:
  if ( !*v2 )
  {
    v3 = QuicPacketKeyUpdate(v7, *(_QWORD *)(a1 + 2896), v2);
    if ( v3 < 0 )
    {
      if ( (byte_14005C48B & 4) != 0 )
      {
        v8 = "Failed to update read packet key.";
LABEL_13:
        McTemplateU0pqs_EtwWriteTransfer(v6, (unsigned int)QuicConnErrorStatus, a1, v3, (__int64)v8);
        goto LABEL_14;
      }
      goto LABEL_14;
    }
    v3 = QuicPacketKeyUpdate(v7, *(_QWORD *)(a1 + 2944), a1 + 2960);
    if ( v3 < 0 )
    {
      if ( (byte_14005C48B & 4) != 0 )
      {
        v8 = "Failed to update write packet key";
        goto LABEL_13;
      }
LABEL_14:
      QuicPacketKeyFree(*v2);
      *v2 = 0;
      return (unsigned int)v3;
    }
  }
  if ( (byte_14005C489 & 0x40) != 0 )
    McTemplateU0p_EtwWriteTransfer(v6, QuicConnNewPacketKeys);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400465f4  mov     rax, rsp
0x1400465f7  mov     [rax+8], rbx
0x1400465fb  mov     [rax+10h], rbp
0x1400465ff  mov     [rax+18h], rsi
0x140046603  mov     [rax+20h], rdi
0x140046607  push    r14
0x140046609  sub     rsp, 30h
0x14004660d  mov     edx, [rcx+0E34h]
0x140046613  lea     rsi, [rcx+0B60h]
0x14004661a  xor     edi, edi
0x14004661c  mov     rbx, rcx
0x14004661f  xor     eax, eax
0x140046621  lea     rcx, QuicSupportedVersionList
0x140046628  cmp     [rcx], edx
0x14004662a  jz      short loc_140046640
0x14004662c  inc     eax
0x14004662e  add     rcx, 58h ; 'X'
0x140046632  cmp     eax, 4
0x140046635  jb      short loc_140046628
0x140046637  lea     rbp, off_14004C048; "quicv2 key"
0x14004663e  jmp     short loc_14004664E
0x140046640  imul    rcx, rax, 58h ; 'X'
0x140046644  lea     rbp, off_14004C048; "quicv2 key"
0x14004664b  add     rbp, rcx
0x14004664e  cmp     [rsi], rdi
0x140046651  jnz     short loc_1400466CE
0x140046653  mov     rdx, [rbx+0B50h]
0x14004665a  mov     r8, rsi
0x14004665d  mov     rcx, rbp
0x140046660  call    QuicPacketKeyUpdate
0x140046665  mov     edi, eax
0x140046667  test    eax, eax
0x140046669  jns     short loc_14004667D
0x14004666b  test    cs:byte_14005C48B, 4
0x140046672  jz      short loc_1400466C0
0x140046674  lea     rax, aFailedToUpdate_1; "Failed to update read packet key."
0x14004667b  jmp     short loc_1400466A9
0x14004667d  mov     rdx, [rbx+0B80h]
0x140046684  lea     r8, [rbx+0B90h]
0x14004668b  mov     rcx, rbp
0x14004668e  call    QuicPacketKeyUpdate
0x140046693  mov     edi, eax
0x140046695  test    eax, eax
0x140046697  jns     short loc_1400466CE
0x140046699  test    cs:byte_14005C48B, 4
0x1400466a0  jz      short loc_1400466C0
0x1400466a2  lea     rax, aFailedToUpdate; "Failed to update write packet key"
0x1400466a9  mov     r9d, edi
0x1400466ac  mov     [rsp+38h+var_18], rax
0x1400466b1  mov     r8, rbx
0x1400466b4  lea     rdx, QuicConnErrorStatus
0x1400466bb  call    McTemplateU0pqs_EtwWriteTransfer
0x1400466c0  mov     rcx, [rsi]; P
0x1400466c3  call    QuicPacketKeyFree
0x1400466c8  and     qword ptr [rsi], 0
0x1400466cc  jmp     short loc_1400466E6
0x1400466ce  test    cs:byte_14005C489, 40h
0x1400466d5  jz      short loc_1400466E6
0x1400466d7  mov     r8, rbx
0x1400466da  lea     rdx, QuicConnNewPacketKeys
0x1400466e1  call    McTemplateU0p_EtwWriteTransfer
0x1400466e6  mov     rbx, [rsp+38h+arg_0]
0x1400466eb  mov     eax, edi
0x1400466ed  mov     rdi, [rsp+38h+arg_18]
0x1400466f2  mov     rbp, [rsp+38h+arg_8]
0x1400466f7  mov     rsi, [rsp+38h+arg_10]
0x1400466fc  add     rsp, 30h
0x140046700  pop     r14
0x140046702  retn
```
