# SmbCeCompleteAdminExchange

- ea: `0x14003df64`
- end: `0x14003e063`
- name: `SmbCeCompleteAdminExchange`
- size: `255`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140011280`
- `0x1400113f4`
- `0x14003e6b4`

## callees

- `0x14001221c`
- `0x1400166c0`
- `0x14003df64`
- `0x14003e06c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14003dff1`
- `ntoskrnl!ExAllocatePool2` at `0x14003dff1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003dfbd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003dfbd`

## pseudocode

```c
__int64 __fastcall SmbCeCompleteAdminExchange(unsigned __int16 *Entry)
{
  unsigned int v2; // edi
  __int64 v3; // rbx
  unsigned int v4; // eax
  unsigned int *v5; // rsi
  void *Pool2; // rax
  unsigned int v7; // ecx
  unsigned int v8; // eax

  v2 = 0;
  if ( *((_BYTE *)Entry + 304) == 114 )
  {
    v3 = *((_QWORD *)Entry + 10);
    v4 = *((_DWORD *)Entry + 12);
    v5 = (unsigned int *)(v3 + 328);
    if ( v4 )
      *v5 = v4;
    v2 = *v5;
    if ( !*v5 )
    {
      if ( (*(_DWORD *)(v3 + 420) & 0x1000000) == 0 )
      {
        Pool2 = *(void **)(v3 + 104);
        if ( Pool2 )
        {
          ExFreePoolWithTag(*(PVOID *)(v3 + 104), 0);
          Pool2 = 0;
          *(_QWORD *)(v3 + 104) = 0;
        }
        v7 = Entry[200];
        *(_WORD *)(v3 + 96) = v7;
        *(_WORD *)(v3 + 98) = v7;
        if ( (_WORD)v7 )
        {
          Pool2 = (void *)ExAllocatePool2(66, v7, 1918070099);
          *(_QWORD *)(v3 + 104) = Pool2;
        }
        if ( Pool2 )
        {
          memmove(Pool2, *((const void **)Entry + 51), *(unsigned __int16 *)(v3 + 96));
        }
        else if ( *(_WORD *)(v3 + 96) )
        {
          *(_DWORD *)(v3 + 96) = 0;
          *v5 = -1073741670;
        }
      }
      v2 = *v5;
      if ( !*v5 )
      {
        v8 = SmbCeUpdateSrvCall(v3);
        *v5 = v8;
        v2 = v8;
        if ( !v8 )
          *(_DWORD *)(v3 + 460) = 1;
      }
    }
  }
  SmbCeDiscardAdminExchange(Entry);
  return v2;
}

```

## disassembly

```asm
0x14003df64  push    rbx
0x14003df66  push    rbp
0x14003df67  push    rsi
0x14003df68  push    rdi
0x14003df69  push    r14
0x14003df6b  sub     rsp, 20h
0x14003df6f  xor     r14d, r14d
0x14003df72  mov     rbp, rcx
0x14003df75  cmp     byte ptr [rcx+130h], 72h ; 'r'
0x14003df7c  mov     edi, r14d
0x14003df7f  jnz     loc_14003E04D
0x14003df85  mov     rbx, [rcx+50h]
0x14003df89  mov     eax, [rcx+30h]
0x14003df8c  lea     rsi, [rbx+148h]
0x14003df93  test    eax, eax
0x14003df95  jz      short loc_14003DF99
0x14003df97  mov     [rsi], eax
0x14003df99  mov     edi, [rsi]
0x14003df9b  test    edi, edi
0x14003df9d  jnz     loc_14003E04D
0x14003dfa3  test    dword ptr [rbx+1A4h], 1000000h
0x14003dfad  jnz     short loc_14003E02D
0x14003dfaf  mov     rax, [rbx+68h]
0x14003dfb3  test    rax, rax
0x14003dfb6  jz      short loc_14003DFD0
0x14003dfb8  xor     edx, edx; Tag
0x14003dfba  mov     rcx, rax; P
0x14003dfbd  call    cs:__imp_ExFreePoolWithTag
0x14003dfc4  nop     dword ptr [rax+rax+00h]
0x14003dfc9  mov     rax, r14
0x14003dfcc  mov     [rbx+68h], r14
0x14003dfd0  movzx   ecx, word ptr [rbp+190h]
0x14003dfd7  mov     [rbx+60h], cx
0x14003dfdb  mov     [rbx+62h], cx
0x14003dfdf  test    cx, cx
0x14003dfe2  jz      short loc_14003E001
0x14003dfe4  mov     edx, ecx
0x14003dfe6  mov     r8d, 72536D53h
0x14003dfec  mov     ecx, 42h ; 'B'
0x14003dff1  call    cs:__imp_ExAllocatePool2
0x14003dff8  nop     dword ptr [rax+rax+00h]
0x14003dffd  mov     [rbx+68h], rax
0x14003e001  movzx   ecx, word ptr [rbx+60h]
0x14003e005  test    rax, rax
0x14003e008  jz      short loc_14003E01E
0x14003e00a  mov     rdx, [rbp+198h]; Src
0x14003e011  mov     r8d, ecx; Size
0x14003e014  mov     rcx, rax; void *
0x14003e017  call    memmove
0x14003e01c  jmp     short loc_14003E02D
0x14003e01e  test    cx, cx
0x14003e021  jz      short loc_14003E02D
0x14003e023  mov     [rbx+60h], r14d
0x14003e027  mov     dword ptr [rsi], 0C000009Ah
0x14003e02d  mov     edi, [rsi]
0x14003e02f  test    edi, edi
0x14003e031  jnz     short loc_14003E04D
0x14003e033  mov     rcx, rbx
0x14003e036  call    SmbCeUpdateSrvCall
0x14003e03b  mov     [rsi], eax
0x14003e03d  mov     edi, eax
0x14003e03f  test    eax, eax
0x14003e041  jnz     short loc_14003E04D
0x14003e043  mov     dword ptr [rbx+1CCh], 1
0x14003e04d  mov     rcx, rbp; Entry
0x14003e050  call    SmbCeDiscardAdminExchange
0x14003e055  mov     eax, edi
0x14003e057  add     rsp, 20h
0x14003e05b  pop     r14
0x14003e05d  pop     rdi
0x14003e05e  pop     rsi
0x14003e05f  pop     rbp
0x14003e060  pop     rbx
0x14003e061  retn
```
