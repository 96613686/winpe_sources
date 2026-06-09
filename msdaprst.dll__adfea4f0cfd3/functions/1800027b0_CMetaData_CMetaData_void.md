# CMetaData::~CMetaData(void)

- ea: `0x1800027b0`
- end: `0x1800028b2`
- name: `??1CMetaData@@QEAA@XZ`
- size: `258`
- prototype: `void __fastcall(CMetaData *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x180005950`
- `0x18001b400`
- `0x1800207a0`
- `0x18002f783`

## callees

- `0x180001db8`
- `0x1800027b0`
- `0x180004cc8`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800027c5`
- `ole32!CoTaskMemFree` at `0x1800027d5`
- `ole32!CoTaskMemFree` at `0x1800027e5`
- `ole32!CoTaskMemFree` at `0x1800027c5`
- `ole32!CoTaskMemFree` at `0x1800027d5`
- `ole32!CoTaskMemFree` at `0x1800027e5`

## pseudocode

```c
void __fastcall CMetaData::~CMetaData(CMetaData *this)
{
  void **v1; // r14
  CMetaData *v3; // rcx
  unsigned __int16 i; // si
  __int64 v5; // rdi

  v1 = (void **)*((_QWORD *)this + 6);
  CoTaskMemFree(*((LPVOID *)this + 1));
  CoTaskMemFree(*((LPVOID *)this + 2));
  CoTaskMemFree(*((LPVOID *)this + 3));
  if ( *((_QWORD *)this + 4) )
  {
    for ( i = 0; i < *(_WORD *)this; ++i )
    {
      v5 = *((_QWORD *)this + 4) + 9648LL * i;
      if ( *((_BYTE *)this + 56) )
      {
        CMetaData::mdReleaseByRefData(v3, (struct tagCOLRSDATA *)(*((_QWORD *)this + 4) + 9648LL * i));
      }
      else
      {
        if ( !*(_DWORD *)(v5 + 9608) )
          operator delete(*(void **)(v5 + 9600));
        if ( !*(_DWORD *)(v5 + 9632) )
          operator delete(*(void **)(v5 + 9624));
      }
    }
    operator delete(*((void **)this + 4));
  }
  while ( v1 )
  {
    *((_QWORD *)this + 6) = *(_QWORD *)(*((_QWORD *)this + 6) + 48LL);
    operator delete(*v1);
    operator delete(v1[1]);
    operator delete(v1[2]);
    operator delete(v1[4]);
    operator delete(v1);
    v1 = (void **)*((_QWORD *)this + 6);
  }
  operator delete(*((void **)this + 5));
}

```

## disassembly

```asm
0x1800027b0  push    rbx
0x1800027b2  push    rsi
0x1800027b3  push    rdi
0x1800027b4  push    r14
0x1800027b6  sub     rsp, 28h
0x1800027ba  mov     r14, [rcx+30h]
0x1800027be  mov     rbx, rcx
0x1800027c1  mov     rcx, [rcx+8]; pv
0x1800027c5  call    cs:__imp_CoTaskMemFree
0x1800027cc  nop     dword ptr [rax+rax+00h]
0x1800027d1  mov     rcx, [rbx+10h]; pv
0x1800027d5  call    cs:__imp_CoTaskMemFree
0x1800027dc  nop     dword ptr [rax+rax+00h]
0x1800027e1  mov     rcx, [rbx+18h]; pv
0x1800027e5  call    cs:__imp_CoTaskMemFree
0x1800027ec  nop     dword ptr [rax+rax+00h]
0x1800027f1  cmp     qword ptr [rbx+20h], 0
0x1800027f6  jz      loc_18000289B
0x1800027fc  xor     esi, esi
0x1800027fe  xor     eax, eax
0x180002800  cmp     ax, [rbx]
0x180002803  jnb     short loc_180002855
0x180002805  movzx   eax, si
0x180002808  imul    rdi, rax, 25B0h
0x18000280f  add     rdi, [rbx+20h]
0x180002813  cmp     byte ptr [rbx+38h], 0
0x180002817  jz      short loc_180002823
0x180002819  mov     rdx, rdi; struct tagCOLRSDATA *
0x18000281c  call    ?mdReleaseByRefData@CMetaData@@AEAAXPEAUtagCOLRSDATA@@@Z; CMetaData::mdReleaseByRefData(tagCOLRSDATA *)
0x180002821  jmp     short loc_18000284D
0x180002823  cmp     dword ptr [rdi+2588h], 0
0x18000282a  jnz     short loc_180002838
0x18000282c  mov     rcx, [rdi+2580h]; void *
0x180002833  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002838  cmp     dword ptr [rdi+25A0h], 0
0x18000283f  jnz     short loc_18000284D
0x180002841  mov     rcx, [rdi+2598h]; void *
0x180002848  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000284d  inc     si
0x180002850  cmp     si, [rbx]
0x180002853  jb      short loc_180002805
0x180002855  mov     rcx, [rbx+20h]; void *
0x180002859  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000285e  jmp     short loc_18000289B
0x180002860  mov     rax, [rbx+30h]
0x180002864  mov     rdx, [rax+30h]
0x180002868  mov     [rbx+30h], rdx
0x18000286c  mov     rcx, [r14]; void *
0x18000286f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002874  mov     rcx, [r14+8]; void *
0x180002878  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000287d  mov     rcx, [r14+10h]; void *
0x180002881  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002886  mov     rcx, [r14+20h]; void *
0x18000288a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000288f  mov     rcx, r14; void *
0x180002892  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002897  mov     r14, [rbx+30h]
0x18000289b  test    r14, r14
0x18000289e  jnz     short loc_180002860
0x1800028a0  mov     rcx, [rbx+28h]; void *
0x1800028a4  add     rsp, 28h
0x1800028a8  pop     r14
0x1800028aa  pop     rdi
0x1800028ab  pop     rsi
0x1800028ac  pop     rbx
0x1800028ad  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
