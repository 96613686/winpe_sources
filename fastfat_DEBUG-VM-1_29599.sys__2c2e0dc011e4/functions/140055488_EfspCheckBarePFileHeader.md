# EfspCheckBarePFileHeader

- ea: `0x140055488`
- end: `0x14005556c`
- name: `EfspCheckBarePFileHeader`
- size: `228`
- prototype: `__int64 __fastcall(void *Source1)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140055b6c`

## callees

- `0x140055488`
- `0x14005693c`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400554d6`
- `ntoskrnl!RtlCompareMemory` at `0x1400554fd`
- `ntoskrnl!RtlCompareMemory` at `0x1400554d6`
- `ntoskrnl!RtlCompareMemory` at `0x1400554fd`

## pseudocode

```c
__int64 __fastcall EfspCheckBarePFileHeader(__int64 Source1, unsigned int a2, _DWORD *a3)
{
  __int64 v5; // rbx
  __int64 v6; // r8
  unsigned int v7; // ebx
  int v8; // eax

  *a3 = 0;
  v5 = Source1;
  if ( a2 > 0x12 )
  {
    if ( RtlCompareMemory((const void *)Source1, ".pfile", 6u) == 6 )
    {
      Source1 = 2;
    }
    else
    {
      if ( RtlCompareMemory((const void *)v5, ".appx_", 6u) != 6 )
      {
        v7 = 0;
        LODWORD(Source1) = 0;
        goto LABEL_17;
      }
      Source1 = 3;
    }
    if ( *(_DWORD *)(v5 + 6) != 2 || *(_DWORD *)(v5 + 10) != 1 )
    {
      v6 = 4599;
      goto LABEL_3;
    }
    v8 = *(_DWORD *)(v5 + 14) + 18;
    if ( *(_DWORD *)(v5 + 14) >= 0xFFFFFFEE || *(_DWORD *)(v5 + 14) + 58 < (unsigned int)(*(_DWORD *)(v5 + 14) + 18) )
      return (unsigned int)-1073741675;
    v7 = 0;
    if ( a2 < v8 + 40 )
    {
      v6 = 4622;
      goto LABEL_3;
    }
LABEL_17:
    *a3 = Source1;
    return v7;
  }
  v6 = 4557;
LABEL_3:
  v7 = -1073739509;
  EfspTraceLogAssert(Source1, 6, v6, 3221227787LL);
  return v7;
}

```

## disassembly

```asm
0x140055488  mov     [rsp+arg_0], rbx
0x14005548d  mov     [rsp+arg_8], rbp
0x140055492  push    rsi
0x140055493  sub     rsp, 20h
0x140055497  mov     dword ptr [r8], 0
0x14005549e  mov     rsi, r8
0x1400554a1  mov     ebp, edx
0x1400554a3  mov     rbx, rcx
0x1400554a6  cmp     edx, 12h
0x1400554a9  ja      short loc_1400554C9
0x1400554ab  mov     r8d, 11CDh
0x1400554b1  mov     r9d, 0C000090Bh
0x1400554b7  mov     edx, 6
0x1400554bc  mov     ebx, r9d
0x1400554bf  call    EfspTraceLogAssert
0x1400554c4  jmp     loc_140055559
0x1400554c9  mov     r8d, 6; Length
0x1400554cf  lea     rdx, aPfile; ".pfile"
0x1400554d6  call    cs:__imp_RtlCompareMemory
0x1400554dd  nop     dword ptr [rax+rax+00h]
0x1400554e2  cmp     rax, 6
0x1400554e6  jnz     short loc_1400554ED
0x1400554e8  lea     ecx, [rax-4]
0x1400554eb  jmp     short loc_140055512
0x1400554ed  mov     r8d, 6; Length
0x1400554f3  lea     rdx, aAppx; ".appx_"
0x1400554fa  mov     rcx, rbx; Source1
0x1400554fd  call    cs:__imp_RtlCompareMemory
0x140055504  nop     dword ptr [rax+rax+00h]
0x140055509  cmp     rax, 6
0x14005550d  jnz     short loc_140055553
0x14005550f  lea     ecx, [rax-3]
0x140055512  cmp     dword ptr [rbx+6], 2
0x140055516  jnz     short loc_140055548
0x140055518  cmp     dword ptr [rbx+0Ah], 1
0x14005551c  jnz     short loc_140055548
0x14005551e  mov     eax, [rbx+0Eh]
0x140055521  add     eax, 12h
0x140055524  cmp     eax, 12h
0x140055527  jb      short loc_140055541
0x140055529  lea     edx, [rax+28h]
0x14005552c  cmp     edx, eax
0x14005552e  jb      short loc_140055541
0x140055530  xor     ebx, ebx
0x140055532  cmp     ebp, edx
0x140055534  jnb     short loc_140055557
0x140055536  mov     r8d, 120Eh
0x14005553c  jmp     loc_1400554B1
0x140055541  mov     ebx, 0C0000095h
0x140055546  jmp     short loc_140055559
0x140055548  mov     r8d, 11F7h
0x14005554e  jmp     loc_1400554B1
0x140055553  xor     ebx, ebx
0x140055555  xor     ecx, ecx
0x140055557  mov     [rsi], ecx
0x140055559  mov     rbp, [rsp+28h+arg_8]
0x14005555e  mov     eax, ebx
0x140055560  mov     rbx, [rsp+28h+arg_0]
0x140055565  add     rsp, 20h
0x140055569  pop     rsi
0x14005556a  retn
```
