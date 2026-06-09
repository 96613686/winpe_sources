# GetAmTypeFromKsFormat(KSDATAFORMAT *,_AMMediaType * *)

- ea: `0x18002f814`
- end: `0x18002f8c8`
- name: `?GetAmTypeFromKsFormat@@YAJPEATKSDATAFORMAT@@PEAPEAU_AMMediaType@@@Z`
- size: `180`
- prototype: `__int64 __fastcall(union KSDATAFORMAT *, struct _AMMediaType **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180031360`

## callees

- `0x180009c4c`
- `0x18000f6c0`
- `0x18001ffb0`
- `0x18002f814`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18002f82e`
- `ole32!CoTaskMemAlloc` at `0x18002f82e`

## pseudocode

```c
__int64 __fastcall GetAmTypeFromKsFormat(union KSDATAFORMAT *a1, struct _AMMediaType **a2)
{
  char *v4; // rax
  char *v5; // rdi
  unsigned int v6; // ebx

  v4 = (char *)CoTaskMemAlloc(0x58u);
  v5 = v4;
  if ( v4
    && ((memset_0(v4, 0, 0x58u),
         *(_OWORD *)v5 = *((_OWORD *)&a1->Alignment + 1),
         *((_OWORD *)v5 + 1) = *((_OWORD *)&a1->Alignment + 2),
         *(_OWORD *)(v5 + 44) = *((_OWORD *)&a1->Alignment + 3),
         *((_DWORD *)v5 + 8) = a1->SampleSize != 0,
         *((_DWORD *)v5 + 9) = a1->Flags & 1,
         *((_DWORD *)v5 + 10) = a1->SampleSize,
         a1->FormatSize <= 0x40)
     || CMediaType::SetFormat((CMediaType *)v5, (unsigned __int8 *)&a1[1], a1->FormatSize - 64)) )
  {
    v6 = 0;
    *a2 = (struct _AMMediaType *)v5;
  }
  else
  {
    v6 = -2147467259;
    FreeMediaType((struct _AMMediaType *)v5);
  }
  return v6;
}

```

## disassembly

```asm
0x18002f814  mov     [rsp+arg_0], rbx
0x18002f819  mov     [rsp+arg_8], rsi
0x18002f81e  push    rdi
0x18002f81f  sub     rsp, 20h
0x18002f823  mov     rbx, rcx
0x18002f826  mov     rsi, rdx
0x18002f829  mov     ecx, 58h ; 'X'; cb
0x18002f82e  call    cs:__imp_CoTaskMemAlloc
0x18002f835  nop     dword ptr [rax+rax+00h]
0x18002f83a  mov     rdi, rax
0x18002f83d  test    rax, rax
0x18002f840  jz      short loc_18002F8A1
0x18002f842  xor     edx, edx; Val
0x18002f844  mov     rcx, rax; void *
0x18002f847  lea     r8d, [rdx+58h]; Size
0x18002f84b  call    memset_0
0x18002f850  movups  xmm0, xmmword ptr [rbx+10h]
0x18002f854  xor     eax, eax
0x18002f856  movdqu  xmmword ptr [rdi], xmm0
0x18002f85a  movups  xmm1, xmmword ptr [rbx+20h]
0x18002f85e  movdqu  xmmword ptr [rdi+10h], xmm1
0x18002f863  movups  xmm0, xmmword ptr [rbx+30h]
0x18002f867  movdqu  xmmword ptr [rdi+2Ch], xmm0
0x18002f86c  cmp     [rbx+8], eax
0x18002f86f  setnz   al
0x18002f872  mov     [rdi+20h], eax
0x18002f875  mov     eax, [rbx+4]
0x18002f878  and     eax, 1
0x18002f87b  mov     [rdi+24h], eax
0x18002f87e  mov     eax, [rbx+8]
0x18002f881  mov     [rdi+28h], eax
0x18002f884  mov     r8d, [rbx]
0x18002f887  cmp     r8d, 40h ; '@'
0x18002f88b  jbe     short loc_18002F8B0
0x18002f88d  add     r8d, 0FFFFFFC0h; unsigned int
0x18002f891  lea     rdx, [rbx+40h]; unsigned __int8 *
0x18002f895  mov     rcx, rdi; this
0x18002f898  call    ?SetFormat@CMediaType@@QEAAHPEAEK@Z; CMediaType::SetFormat(uchar *,ulong)
0x18002f89d  test    eax, eax
0x18002f89f  jnz     short loc_18002F8B0
0x18002f8a1  mov     rcx, rdi; struct _AMMediaType *
0x18002f8a4  mov     ebx, 80004005h
0x18002f8a9  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x18002f8ae  jmp     short loc_18002F8B5
0x18002f8b0  xor     ebx, ebx
0x18002f8b2  mov     [rsi], rdi
0x18002f8b5  mov     rsi, [rsp+28h+arg_8]
0x18002f8ba  mov     eax, ebx
0x18002f8bc  mov     rbx, [rsp+28h+arg_0]
0x18002f8c1  add     rsp, 20h
0x18002f8c5  pop     rdi
0x18002f8c6  retn
```
