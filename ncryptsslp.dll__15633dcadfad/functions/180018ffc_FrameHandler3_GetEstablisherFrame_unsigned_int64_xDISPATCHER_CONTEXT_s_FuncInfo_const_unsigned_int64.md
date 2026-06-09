# __FrameHandler3::GetEstablisherFrame(unsigned __int64 *,_xDISPATCHER_CONTEXT *,_s_FuncInfo const *,unsigned __int64 *)

- ea: `0x180018ffc`
- end: `0x1800190ce`
- name: `?GetEstablisherFrame@__FrameHandler3@@SAPEA_KPEA_KPEAU_xDISPATCHER_CONTEXT@@PEBU_s_FuncInfo@@0@Z`
- size: `210`
- prototype: `static unsigned __int64 *(unsigned __int64 *, struct _xDISPATCHER_CONTEXT *, const struct _s_FuncInfo *, unsigned __int64 *)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180018f88`
- `0x180019688`
- `0x1800196d4`
- `0x180019a24`
- `0x180019b08`
- `0x18001aa9c`

## callees

- `0x180018ffc`
- `0x180019720`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x180019064`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x180019064`

## pseudocode

```c
unsigned __int64 *__fastcall __FrameHandler3::GetEstablisherFrame(
        unsigned __int64 *a1,
        struct _xDISPATCHER_CONTEXT *a2,
        const struct _s_FuncInfo *a3,
        unsigned __int64 *a4)
{
  __int64 v4; // rbx
  int v9; // ebp
  __int64 v10; // rsi
  __int64 v11; // rdi
  PRUNTIME_FUNCTION v12; // rax
  __int64 v13; // rdx
  unsigned __int64 v14; // r9
  unsigned int v15; // r8d
  unsigned __int64 ImageBase; // [rsp+70h] [rbp+8h] BYREF

  LODWORD(v4) = a3->nTryBlocks;
  ImageBase = 0;
  v9 = __FrameHandler3::StateFromControlPc(a3, a2);
  *a4 = *a1;
  while ( (_DWORD)v4 )
  {
    v4 = (unsigned int)(v4 - 1);
    v10 = a2->ImageBase;
    v11 = a3->dispTryBlockMap + 20 * v4;
    if ( v9 > *(_DWORD *)(v11 + v10 + 4) && v9 <= *(_DWORD *)(v11 + v10 + 8) )
    {
      v12 = RtlLookupFunctionEntry(a2->ControlPc, &ImageBase, 0);
      v13 = 0;
      v14 = ImageBase + *(int *)(v11 + v10 + 16);
      v15 = *(_DWORD *)(v11 + v10 + 12);
      if ( v15 )
      {
        while ( *(_DWORD *)(v14 + 20 * v13 + 12) != (unsigned __int64)v12->BeginAddress )
        {
          v13 = (unsigned int)(v13 + 1);
          if ( (unsigned int)v13 >= v15 )
            goto LABEL_7;
        }
LABEL_10:
        _mm_lfence();
        *a4 = *(_QWORD *)(*(int *)(v14 + 20 * v13 + 16) + *a1);
        return a4;
      }
LABEL_7:
      if ( (unsigned int)v13 < v15 )
        goto LABEL_10;
    }
  }
  return a4;
}

```

## disassembly

```asm
0x180018ffc  push    rbx
0x180018ffe  push    rbp
0x180018fff  push    rsi
0x180019000  push    rdi
0x180019001  push    r12
0x180019003  push    r13
0x180019005  push    r14
0x180019007  push    r15
0x180019009  sub     rsp, 28h
0x18001900d  mov     ebx, [r8+0Ch]
0x180019011  mov     r13, rcx
0x180019014  mov     rcx, r8; struct _s_FuncInfo *
0x180019017  mov     [rsp+68h+ImageBase], 0
0x180019020  mov     r14, r9
0x180019023  mov     r15, r8
0x180019026  mov     r12, rdx
0x180019029  call    ?StateFromControlPc@__FrameHandler3@@SAHPEBU_s_FuncInfo@@PEAU_xDISPATCHER_CONTEXT@@@Z; __FrameHandler3::StateFromControlPc(_s_FuncInfo const *,_xDISPATCHER_CONTEXT *)
0x18001902e  mov     r10, [r13+0]
0x180019032  mov     ebp, eax
0x180019034  mov     [r14], r10
0x180019037  jmp     short loc_18001909D
0x180019039  movsxd  rax, dword ptr [r15+10h]
0x18001903d  dec     ebx
0x18001903f  mov     rsi, [r12+8]
0x180019044  lea     rdx, [rbx+rbx*4]
0x180019048  lea     rdi, [rax+rdx*4]
0x18001904c  cmp     ebp, [rdi+rsi+4]
0x180019050  jle     short loc_18001909D
0x180019052  cmp     ebp, [rdi+rsi+8]
0x180019056  jg      short loc_18001909D
0x180019058  mov     rcx, [r12]; ControlPc
0x18001905c  lea     rdx, [rsp+68h+ImageBase]; ImageBase
0x180019061  xor     r8d, r8d; HistoryTable
0x180019064  call    cs:__imp_RtlLookupFunctionEntry
0x18001906a  movsxd  r9, dword ptr [rdi+rsi+10h]
0x18001906f  xor     edx, edx
0x180019071  add     r9, [rsp+68h+ImageBase]
0x180019076  mov     r8d, [rdi+rsi+0Ch]
0x18001907b  mov     r10d, [rax]
0x18001907e  test    r8d, r8d
0x180019081  jz      short loc_180019098
0x180019083  lea     rcx, [rdx+rdx*4]
0x180019087  movsxd  rax, dword ptr [r9+rcx*4+0Ch]
0x18001908c  cmp     rax, r10
0x18001908f  jz      short loc_1800190A3
0x180019091  inc     edx
0x180019093  cmp     edx, r8d
0x180019096  jb      short loc_180019083
0x180019098  cmp     edx, r8d
0x18001909b  jb      short loc_1800190A3
0x18001909d  test    ebx, ebx
0x18001909f  jnz     short loc_180019039
0x1800190a1  jmp     short loc_1800190BA
0x1800190a3  lfence
0x1800190a6  mov     rax, [r13+0]
0x1800190aa  lea     rcx, [rdx+rdx*4]
0x1800190ae  movsxd  rcx, dword ptr [r9+rcx*4+10h]
0x1800190b3  mov     rcx, [rcx+rax]
0x1800190b7  mov     [r14], rcx
0x1800190ba  mov     rax, r14
0x1800190bd  add     rsp, 28h
0x1800190c1  pop     r15
0x1800190c3  pop     r14
0x1800190c5  pop     r13
0x1800190c7  pop     r12
0x1800190c9  pop     rdi
0x1800190ca  pop     rsi
0x1800190cb  pop     rbp
0x1800190cc  pop     rbx
0x1800190cd  retn
```
