# CErrors::Clear(void)

- ea: `0x180011800`
- end: `0x1800119d8`
- name: `?Clear@CErrors@@UEAAJXZ`
- size: `472`
- prototype: `__int64 __fastcall(CErrors *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180001900`
- `0x1800674c0`

## callees

- `0x180011800`
- `0x1800119e0`
- `0x1800cdade`
- `0x1800d0010`

## import_xrefs

- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x1800118a5`
- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x1800118a5`
- `MSDART!?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18001192e`
- `MSDART!?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18001192e`
- `KERNEL32!GetCurrentThreadId` at `0x180011831`
- `KERNEL32!GetCurrentThreadId` at `0x180011831`

## pseudocode

```c
__int64 __fastcall CErrors::Clear(CErrors *this)
{
  DWORD CurrentThreadId; // r13d
  __int64 v3; // rbp
  __int64 v4; // rax
  __int64 v5; // rdi
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rbx
  unsigned int v9; // r8d
  __int64 i; // rax
  __int64 v11; // r9
  CCollectionMapEntry *v12; // rcx
  __int64 v14; // rcx

  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 2) + 40LL))((char *)this + 16);
  if ( *((_QWORD *)this + 11) )
  {
    CurrentThreadId = GetCurrentThreadId();
    LODWORD(v3) = *(_DWORD *)(*((_QWORD *)this + 11) + 16LL);
    while ( (_DWORD)v3 )
    {
      v4 = *((_QWORD *)this + 11);
      v3 = (unsigned int)(v3 - 1);
      if ( (unsigned int)v3 >= *(_DWORD *)(v4 + 16) )
      {
        v5 = 0;
      }
      else
      {
        _mm_lfence();
        v5 = *(_QWORD *)(*(_QWORD *)(v4 + 8) + 8 * v3);
      }
      v6 = v5 + 140;
      if ( !v5 )
        v6 = 156;
      if ( *(_DWORD *)v6 == CurrentThreadId )
      {
        CReaderWriterLock3AR::WriteLock((CErrors *)((char *)this + 96));
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v5 + 152LL))(v5, 0);
        v8 = *((_QWORD *)this + 11);
        v9 = *(_DWORD *)(v8 + 16);
        if ( v9 )
        {
          v7 = *(_QWORD *)(v8 + 8);
          v14 = 0;
          while ( *(_QWORD *)(v7 + 8 * v14) != v5 )
          {
            v14 = (unsigned int)(v14 + 1);
            if ( (unsigned int)v14 >= v9 )
              goto LABEL_9;
          }
          if ( (_DWORD)v14 != v9 - 1 )
            memmove_0((void *)(v7 + 8 * v14), (const void *)(v7 + 8 * v14 + 8), 8LL * (~(_DWORD)v14 + v9));
          --*(_DWORD *)(v8 + 16);
        }
LABEL_9:
        for ( i = 0; (unsigned int)i < *(_DWORD *)(v8 + 24); i = (unsigned int)(i + 1) )
        {
          v11 = *(_QWORD *)(v8 + 32) + 8 * i;
          v12 = *(CCollectionMapEntry **)v11;
          if ( *(_QWORD *)v11 )
          {
            while ( v12 )
            {
              if ( *((_QWORD *)v12 + 3) == v5 )
              {
                *(_QWORD *)v11 = *(_QWORD *)(*(_QWORD *)v11 + 40LL);
                CCollectionMapEntry::`scalar deleting destructor'(v12, v7);
                --*(_DWORD *)(v8 + 40);
                goto LABEL_16;
              }
              v11 = (__int64)v12 + 40;
              v12 = (CCollectionMapEntry *)*((_QWORD *)v12 + 5);
            }
          }
        }
LABEL_16:
        (*(void (__fastcall **)(char *, __int64))(*((_QWORD *)this + 3) + 352LL))((char *)this + 24, v5);
        CReaderWriterLock3AR::WriteUnlock((CErrors *)((char *)this + 96));
      }
    }
  }
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 2) + 48LL))((char *)this + 16);
  return 0;
}

```

## disassembly

```asm
0x180011800  push    r12
0x180011802  push    r15
0x180011804  sub     rsp, 38h
0x180011808  mov     rax, [rcx+10h]
0x18001180c  mov     r15, rcx
0x18001180f  add     rcx, 10h
0x180011813  mov     rax, [rax+28h]
0x180011817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001181c  cmp     qword ptr [r15+58h], 0
0x180011821  jz      loc_180011965
0x180011827  mov     [rsp+48h+arg_8], rbp
0x18001182c  mov     [rsp+48h+var_20], r13
0x180011831  call    cs:__imp_GetCurrentThreadId
0x180011838  nop     dword ptr [rax+rax+00h]
0x18001183d  mov     rcx, [r15+58h]
0x180011841  mov     r13d, eax
0x180011844  mov     ebp, [rcx+10h]
0x180011847  test    ebp, ebp
0x180011849  jz      loc_18001195B
0x18001184f  mov     [rsp+48h+arg_0], rbx
0x180011854  mov     edx, 9Ch
0x180011859  mov     [rsp+48h+var_18], rdi
0x18001185e  mov     [rsp+48h+arg_10], rsi
0x180011863  mov     [rsp+48h+var_28], r14
0x180011868  nop     dword ptr [rax+rax+00000000h]
0x180011870  mov     rax, [r15+58h]
0x180011874  dec     ebp
0x180011876  cmp     ebp, [rax+10h]
0x180011879  jnb     loc_18001199F
0x18001187f  lfence
0x180011882  mov     rax, [rax+8]
0x180011886  mov     rdi, [rax+rbp*8]
0x18001188a  test    rdi, rdi
0x18001188d  lea     rax, [rdi+8Ch]
0x180011894  cmovz   rax, rdx
0x180011898  cmp     [rax], r13d
0x18001189b  jnz     loc_18001193F
0x1800118a1  lea     rcx, [r15+60h]
0x1800118a5  call    cs:__imp_?WriteLock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::WriteLock(void)
0x1800118ac  nop     dword ptr [rax+rax+00h]
0x1800118b1  mov     rax, [rdi]
0x1800118b4  xor     edx, edx
0x1800118b6  mov     rcx, rdi
0x1800118b9  mov     rax, [rax+98h]
0x1800118c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118c5  mov     rbx, [r15+58h]
0x1800118c9  mov     r8d, [rbx+10h]
0x1800118cd  test    r8d, r8d
0x1800118d0  jnz     loc_180011982
0x1800118d6  xor     eax, eax
0x1800118d8  cmp     eax, [rbx+18h]
0x1800118db  jnb     short loc_180011913
0x1800118dd  mov     rcx, [rbx+20h]
0x1800118e1  lea     r9, [rcx+rax*8]
0x1800118e5  mov     rcx, [rcx+rax*8]; this
0x1800118e9  test    rcx, rcx
0x1800118ec  jnz     short loc_1800118F2
0x1800118ee  inc     eax
0x1800118f0  jmp     short loc_1800118D8
0x1800118f2  test    rcx, rcx
0x1800118f5  jz      short loc_1800118EE
0x1800118f7  cmp     [rcx+18h], rdi
0x1800118fb  jnz     loc_1800119CB
0x180011901  mov     rax, [r9]
0x180011904  mov     r8, [rax+28h]
0x180011908  mov     [r9], r8
0x18001190b  call    ??_GCCollectionMapEntry@@QEAAPEAXI@Z; CCollectionMapEntry::`scalar deleting destructor'(uint)
0x180011910  dec     dword ptr [rbx+28h]
0x180011913  mov     rax, [r15+18h]
0x180011917  lea     rcx, [r15+18h]
0x18001191b  mov     rdx, rdi
0x18001191e  mov     rax, [rax+160h]
0x180011925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001192a  lea     rcx, [r15+60h]
0x18001192e  call    cs:__imp_?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::WriteUnlock(void)
0x180011935  nop     dword ptr [rax+rax+00h]
0x18001193a  mov     edx, 9Ch
0x18001193f  test    ebp, ebp
0x180011941  jnz     loc_180011870
0x180011947  mov     r14, [rsp+48h+var_28]
0x18001194c  mov     rdi, [rsp+48h+var_18]
0x180011951  mov     rsi, [rsp+48h+arg_10]
0x180011956  mov     rbx, [rsp+48h+arg_0]
0x18001195b  mov     rbp, [rsp+48h+arg_8]
0x180011960  mov     r13, [rsp+48h+var_20]
0x180011965  mov     rax, [r15+10h]
0x180011969  lea     rcx, [r15+10h]
0x18001196d  mov     rax, [rax+30h]
0x180011971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011976  xor     eax, eax
0x180011978  add     rsp, 38h
0x18001197c  pop     r15
0x18001197e  pop     r12
0x180011980  retn
0x180011982  mov     rdx, [rbx+8]
0x180011986  xor     ecx, ecx
0x180011988  cmp     [rdx+rcx*8], rdi
0x18001198c  lea     r9, [rdx+rcx*8]
0x180011990  jz      short loc_1800119A6
0x180011992  inc     ecx
0x180011994  cmp     ecx, r8d
0x180011997  jnb     loc_1800118D6
0x18001199d  jmp     short loc_180011988
0x18001199f  xor     edi, edi
0x1800119a1  jmp     loc_18001188A
0x1800119a6  lea     eax, [r8-1]
0x1800119aa  cmp     ecx, eax
0x1800119ac  jz      short loc_1800119C3
0x1800119ae  not     ecx
0x1800119b0  lea     rdx, [r9+8]; Src
0x1800119b4  add     r8d, ecx
0x1800119b7  mov     rcx, r9; void *
0x1800119ba  shl     r8, 3; Size
0x1800119be  call    memmove_0
0x1800119c3  dec     dword ptr [rbx+10h]
0x1800119c6  jmp     loc_1800118D6
0x1800119cb  lea     r9, [rcx+28h]
0x1800119cf  mov     rcx, [rcx+28h]
0x1800119d3  jmp     loc_1800118F2
```
