# CRecordGroup::SetBookmarkProperties(unsigned __int64,uchar *,int,__int64)

- ea: `0x180052080`
- end: `0x18005210a`
- name: `?SetBookmarkProperties@CRecordGroup@@QEAAX_KPEAEH_J@Z`
- size: `138`
- prototype: `void __fastcall(CRecordGroup *__hidden this, unsigned __int64, unsigned __int8 *, int, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180028d48`
- `0x18004a31c`

## callees

- `0x180052080`

## import_xrefs

- `MSDART!MpHeapFree` at `0x1800520d8`
- `MSDART!MpHeapFree` at `0x1800520d8`
- `ole32!CoTaskMemFree` at `0x1800520fc`
- `ole32!CoTaskMemFree` at `0x1800520fc`

## pseudocode

```c
void __fastcall CRecordGroup::SetBookmarkProperties(
        CRecordGroup *this,
        __int64 a2,
        unsigned __int8 *a3,
        int a4,
        __int64 a5)
{
  void *v7; // rcx
  __int64 v10; // rdx

  v7 = (void *)*((_QWORD *)this + 9);
  if ( v7 && *((_DWORD *)this + 15) )
    CoTaskMemFree(v7);
  v10 = *((_QWORD *)this + 10);
  *((_BYTE *)this + 97) = 0;
  *((_QWORD *)this + 8) = a2;
  *((_QWORD *)this + 9) = a3;
  *((_DWORD *)this + 15) = a4;
  *((_QWORD *)this + 4) = a5;
  if ( v10 )
  {
    MpHeapFree(g_hHeapHandle, v10);
    *((_QWORD *)this + 10) = 0;
    *((_QWORD *)this + 11) = 0;
  }
  *((_QWORD *)this + 11) = 0;
}

```

## disassembly

```asm
0x180052080  push    rbx
0x180052082  push    rbp
0x180052083  push    rsi
0x180052084  push    rdi
0x180052085  sub     rsp, 28h
0x180052089  mov     rbx, rcx
0x18005208c  mov     edi, r9d
0x18005208f  mov     rcx, [rcx+48h]; pv
0x180052093  mov     rsi, r8
0x180052096  mov     rbp, rdx
0x180052099  test    rcx, rcx
0x18005209c  jnz     short loc_1800520F6
0x18005209e  mov     rdx, [rbx+50h]
0x1800520a2  mov     rax, [rsp+48h+arg_20]
0x1800520a7  mov     byte ptr [rbx+61h], 0
0x1800520ab  mov     [rbx+40h], rbp
0x1800520af  mov     [rbx+48h], rsi
0x1800520b3  mov     [rbx+3Ch], edi
0x1800520b6  mov     [rbx+20h], rax
0x1800520ba  test    rdx, rdx
0x1800520bd  jnz     short loc_1800520D1
0x1800520bf  mov     qword ptr [rbx+58h], 0
0x1800520c7  add     rsp, 28h
0x1800520cb  pop     rdi
0x1800520cc  pop     rsi
0x1800520cd  pop     rbp
0x1800520ce  pop     rbx
0x1800520cf  retn
0x1800520d1  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800520d8  call    cs:__imp_MpHeapFree
0x1800520df  nop     dword ptr [rax+rax+00h]
0x1800520e4  mov     qword ptr [rbx+50h], 0
0x1800520ec  mov     qword ptr [rbx+58h], 0
0x1800520f4  jmp     short loc_1800520BF
0x1800520f6  cmp     dword ptr [rbx+3Ch], 0
0x1800520fa  jz      short loc_18005209E
0x1800520fc  call    cs:__imp_CoTaskMemFree
0x180052103  nop     dword ptr [rax+rax+00h]
0x180052108  jmp     short loc_18005209E
```
