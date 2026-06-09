# MRxSmbFixupFindFirst

- ea: `0x140039210`
- end: `0x140039383`
- name: `MRxSmbFixupFindFirst`
- size: `371`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x14000dfd8`
- `0x140010934`
- `0x1400166c0`
- `0x140039210`

## import_xrefs

- `ntoskrnl!RtlxUnicodeStringToOemSize` at `0x140039335`
- `ntoskrnl!RtlxUnicodeStringToOemSize` at `0x140039335`
- `ntoskrnl!RtlUpcaseUnicodeStringToOemString` at `0x1400392f8`
- `ntoskrnl!RtlUpcaseUnicodeStringToOemString` at `0x1400392f8`
- `ntoskrnl!RtlUnicodeStringToOemString` at `0x140039315`
- `ntoskrnl!RtlUnicodeStringToOemString` at `0x140039315`

## pseudocode

```c
__int64 __fastcall MRxSmbFixupFindFirst(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdi
  __int64 v5; // rdx
  __int64 v6; // rsi
  unsigned int v7; // edi
  bool v8; // zf
  NTSTATUS v9; // eax
  struct _STRING DestinationString; // [rsp+40h] [rbp-38h] BYREF

  v3 = *(_QWORD *)(a1 + 920);
  v5 = *(unsigned __int16 *)(v3 + 53);
  v6 = v5 + v3;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_qLLq(WPP_GLOBAL_Control->AttachedDevice, v5, a3, a1, *(unsigned __int16 *)(v3 + 51), v5, v5 + v3);
  *(_DWORD *)v6 = 65558;
  *(_QWORD *)(v6 + 4) = 17039367;
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 80) + 420LL) & 0x8000) != 0 )
  {
    v7 = 0;
    memmove((void *)(v6 + 12), *(const void **)(*(_QWORD *)(a1 + 864) + 8LL), **(unsigned __int16 **)(a1 + 864));
    *(_WORD *)(**(unsigned __int16 **)(a1 + 864) + v6 + 12) = 0;
  }
  else
  {
    *(_QWORD *)&DestinationString.Length = 0;
    DestinationString.Buffer = (PCHAR)(v6 + 12);
    v8 = (*(_BYTE *)(v3 + 9) & 8) == 0;
    DestinationString.MaximumLength = *(_WORD *)(a1 + 928) + ~(_WORD)v6;
    DestinationString.Length = DestinationString.MaximumLength;
    if ( v8 || (*(_BYTE *)(v3 + 10) & 1) != 0 )
      v9 = RtlUnicodeStringToOemString(&DestinationString, *(PCUNICODE_STRING *)(a1 + 864), 0);
    else
      v9 = RtlUpcaseUnicodeStringToOemString(&DestinationString, *(PCUNICODE_STRING *)(a1 + 864), 0);
    v7 = v9;
    if ( v9 < 0 )
      return 2147483653LL;
    *(_BYTE *)((unsigned __int16)RtlxUnicodeStringToOemSize(*(PCUNICODE_STRING *)(a1 + 864)) + v6 + 11) = 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 100, WPP_d95790c14120305e97e490eb33b089fe_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x140039210  push    rbx
0x140039212  push    rsi
0x140039213  push    rdi
0x140039214  push    r14
0x140039216  sub     rsp, 58h
0x14003921a  mov     rdi, [rcx+398h]
0x140039221  mov     rbx, rcx
0x140039224  movzx   edx, word ptr [rdi+35h]
0x140039228  lea     rsi, [rdx+rdi]
0x14003922c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140039233  lea     r14, WPP_GLOBAL_Control
0x14003923a  cmp     rcx, r14
0x14003923d  jz      short loc_140039265
0x14003923f  test    dword ptr [rcx+2Ch], 400h
0x140039246  jz      short loc_140039265
0x140039248  movzx   eax, word ptr [rdi+33h]
0x14003924c  mov     r9, rbx
0x14003924f  mov     rcx, [rcx+18h]
0x140039253  mov     [rsp+78h+var_48], rsi
0x140039258  mov     [rsp+78h+var_50], edx
0x14003925c  mov     [rsp+78h+var_58], eax
0x140039260  call    WPP_SF_qLLq
0x140039265  mov     dword ptr [rsi], 10016h
0x14003926b  lea     rcx, [rsi+0Ch]; void *
0x14003926f  mov     qword ptr [rsi+4], 1040007h
0x140039277  mov     r8d, 1
0x14003927d  mov     rax, [rbx+50h]
0x140039281  test    dword ptr [rax+1A4h], 8000h
0x14003928b  jz      short loc_1400392B9
0x14003928d  mov     rdx, [rbx+360h]
0x140039294  xor     edi, edi
0x140039296  movzx   r8d, word ptr [rdx]; Size
0x14003929a  mov     rdx, [rdx+8]; Src
0x14003929e  call    memmove
0x1400392a3  mov     rax, [rbx+360h]
0x1400392aa  movzx   ecx, word ptr [rax]
0x1400392ad  xor     eax, eax
0x1400392af  mov     [rcx+rsi+0Ch], ax
0x1400392b4  jmp     loc_140039349
0x1400392b9  movzx   eax, si
0x1400392bc  xorps   xmm0, xmm0
0x1400392bf  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x1400392c4  not     ax
0x1400392c7  mov     [rsp+78h+DestinationString.Buffer], rcx
0x1400392cc  add     ax, [rbx+3A0h]
0x1400392d3  test    byte ptr [rdi+9], 8
0x1400392d7  mov     [rsp+78h+DestinationString.MaximumLength], ax
0x1400392dc  mov     [rsp+78h+DestinationString.Length], ax
0x1400392e1  jz      short loc_140039306
0x1400392e3  test    [rdi+0Ah], r8b
0x1400392e7  jnz     short loc_140039306
0x1400392e9  mov     rdx, [rbx+360h]; SourceString
0x1400392f0  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x1400392f5  xor     r8d, r8d; AllocateDestinationString
0x1400392f8  call    cs:__imp_RtlUpcaseUnicodeStringToOemString
0x1400392ff  nop     dword ptr [rax+rax+00h]
0x140039304  jmp     short loc_140039321
0x140039306  mov     rdx, [rbx+360h]; SourceString
0x14003930d  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x140039312  xor     r8d, r8d; AllocateDestinationString
0x140039315  call    cs:__imp_RtlUnicodeStringToOemString
0x14003931c  nop     dword ptr [rax+rax+00h]
0x140039321  mov     edi, eax
0x140039323  test    eax, eax
0x140039325  jns     short loc_14003932E
0x140039327  mov     eax, 80000005h
0x14003932c  jmp     short loc_140039378
0x14003932e  mov     rcx, [rbx+360h]; UnicodeString
0x140039335  call    cs:__imp_RtlxUnicodeStringToOemSize
0x14003933c  nop     dword ptr [rax+rax+00h]
0x140039341  movzx   ecx, ax
0x140039344  mov     byte ptr [rcx+rsi+0Bh], 0
0x140039349  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140039350  cmp     rcx, r14
0x140039353  jz      short loc_140039376
0x140039355  test    dword ptr [rcx+2Ch], 400h
0x14003935c  jz      short loc_140039376
0x14003935e  mov     rcx, [rcx+18h]
0x140039362  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x140039369  mov     edx, 64h ; 'd'
0x14003936e  mov     r9d, edi
0x140039371  call    WPP_SF_d
0x140039376  mov     eax, edi
0x140039378  add     rsp, 58h
0x14003937c  pop     r14
0x14003937e  pop     rdi
0x14003937f  pop     rsi
0x140039380  pop     rbx
0x140039381  retn
```
