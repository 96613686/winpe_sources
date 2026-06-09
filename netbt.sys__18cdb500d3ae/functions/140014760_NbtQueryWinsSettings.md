# NbtQueryWinsSettings

- ea: `0x140014760`
- end: `0x14001488d`
- name: `NbtQueryWinsSettings`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140047f20`

## callees

- `0x140014760`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400147aa`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400147aa`

## pseudocode

```c
__int64 __fastcall NbtQueryWinsSettings(__int64 a1, __int64 a2)
{
  __int64 v4; // rcx
  unsigned int v5; // ebx
  _DWORD *v6; // rdx

  v4 = *(_QWORD *)(a2 + 8);
  if ( !v4 )
    return 3221225488LL;
  v5 = *(_DWORD *)(v4 + 40);
  if ( (*(_BYTE *)(v4 + 10) & 5) != 0 )
    v6 = *(_DWORD **)(v4 + 24);
  else
    v6 = MmMapLockedPagesSpecifyCache((PMDL)v4, 0, MmCached, 0, 0, 0x40000010u);
  if ( v5 < 8 || !v6 )
    return 3221225488LL;
  if ( v5 < 0x3C )
  {
    *v6 = *(_DWORD *)(a1 + 504);
    v6[1] = *(_DWORD *)(a1 + 508);
    *(_QWORD *)(a2 + 56) = 8;
  }
  else
  {
    *(_OWORD *)v6 = *(_OWORD *)(a1 + 504);
    *((_OWORD *)v6 + 1) = *(_OWORD *)(a1 + 520);
    *((_OWORD *)v6 + 2) = *(_OWORD *)(a1 + 536);
    *((_WORD *)v6 + 24) = *(_WORD *)(a1 + 552);
    *((_WORD *)v6 + 25) = *(_WORD *)(a1 + 554);
    *((_BYTE *)v6 + 56) = *(_BYTE *)(a1 + 864);
    v6[13] = (unsigned __int16)NodeType;
    *(_QWORD *)(a2 + 56) = 60;
    if ( v5 >= 0x40 )
    {
      *((_BYTE *)v6 + 60) = *(_BYTE *)(a1 + 858);
      *(_QWORD *)(a2 + 56) = 64;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140014760  mov     [rsp+arg_8], rsi
0x140014765  push    rdi
0x140014766  sub     rsp, 30h
0x14001476a  mov     rsi, rcx
0x14001476d  mov     rdi, rdx
0x140014770  mov     rcx, [rdx+8]; MemoryDescriptorList
0x140014774  test    rcx, rcx
0x140014777  jz      loc_140014886
0x14001477d  test    byte ptr [rcx+0Ah], 5
0x140014781  mov     [rsp+38h+arg_0], rbx
0x140014786  mov     ebx, [rcx+28h]
0x140014789  jnz     loc_14001484E
0x14001478f  mov     [rsp+38h+Priority], 40000010h; Priority
0x140014797  xor     r9d, r9d; RequestedAddress
0x14001479a  xor     edx, edx; AccessMode
0x14001479c  mov     [rsp+38h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400147a4  mov     r8d, 1; CacheType
0x1400147aa  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400147b1  nop     dword ptr [rax+rax+00h]
0x1400147b6  mov     rdx, rax
0x1400147b9  cmp     ebx, 8
0x1400147bc  jb      short loc_140014838
0x1400147be  test    rdx, rdx
0x1400147c1  jz      short loc_140014838
0x1400147c3  xor     ecx, ecx
0x1400147c5  cmp     ebx, 3Ch ; '<'
0x1400147c8  jb      loc_14001486B
0x1400147ce  movups  xmm0, xmmword ptr [rsi+1F8h]
0x1400147d5  movups  xmmword ptr [rdx], xmm0
0x1400147d8  movups  xmm1, xmmword ptr [rsi+208h]
0x1400147df  movups  xmmword ptr [rdx+10h], xmm1
0x1400147e3  movups  xmm0, xmmword ptr [rsi+218h]
0x1400147ea  movups  xmmword ptr [rdx+20h], xmm0
0x1400147ee  movzx   eax, word ptr [rsi+228h]
0x1400147f5  mov     [rdx+30h], ax
0x1400147f9  movzx   eax, word ptr [rsi+22Ah]
0x140014800  mov     [rdx+32h], ax
0x140014804  movzx   eax, byte ptr [rsi+360h]
0x14001480b  mov     [rdx+38h], al
0x14001480e  movzx   eax, cs:NodeType
0x140014815  mov     [rdx+34h], eax
0x140014818  mov     qword ptr [rdi+38h], 3Ch ; '<'
0x140014820  cmp     ebx, 40h ; '@'
0x140014823  jnb     short loc_140014857
0x140014825  mov     rbx, [rsp+38h+arg_0]
0x14001482a  mov     eax, ecx
0x14001482c  mov     rsi, [rsp+38h+arg_8]
0x140014831  add     rsp, 30h
0x140014835  pop     rdi
0x140014836  retn
0x140014838  mov     rbx, [rsp+38h+arg_0]
0x14001483d  mov     eax, 0C0000010h
0x140014842  mov     rsi, [rsp+38h+arg_8]
0x140014847  add     rsp, 30h
0x14001484b  pop     rdi
0x14001484c  retn
0x14001484e  mov     rdx, [rcx+18h]
0x140014852  jmp     loc_1400147B9
0x140014857  movzx   eax, byte ptr [rsi+35Ah]
0x14001485e  mov     [rdx+3Ch], al
0x140014861  mov     qword ptr [rdi+38h], 40h ; '@'
0x140014869  jmp     short loc_140014825
0x14001486b  mov     eax, [rsi+1F8h]
0x140014871  mov     [rdx], eax
0x140014873  mov     eax, [rsi+1FCh]
0x140014879  mov     [rdx+4], eax
0x14001487c  mov     qword ptr [rdi+38h], 8
0x140014884  jmp     short loc_140014825
0x140014886  mov     eax, 0C0000010h
0x14001488b  jmp     short loc_14001482C
```
