# PCW_QUERY::InsertQueryItem(utl::unique_ptr<PCW_QUERY_ITEM,utl::default_delete<PCW_QUERY_ITEM>>,ulong *)

- ea: `0x140009750`
- end: `0x14000981f`
- name: `?InsertQueryItem@PCW_QUERY@@AEAAXV?$unique_ptr@VPCW_QUERY_ITEM@@U?$default_delete@VPCW_QUERY_ITEM@@@utl@@@utl@@PEAK@Z`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000961c`

## callees

- `0x14000930c`
- `0x140009750`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140009763`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140009763`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400097e7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400097e7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140009778`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140009778`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400097db`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400097db`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009808`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009808`

## pseudocode

```c
void __fastcall PCW_QUERY::InsertQueryItem(__int64 a1, PCW_QUERY_ITEM **a2, int *a3)
{
  __int64 v6; // rsi
  PCW_QUERY_ITEM **v7; // rbx
  int v8; // r9d
  PCW_QUERY_ITEM *v9; // rcx
  PCW_QUERY_ITEM **v10; // rdx
  PCW_QUERY_ITEM *v11; // rax
  PCW_QUERY_ITEM *v12; // rbx

  KeEnterCriticalRegion();
  v6 = a1 + 8;
  ExAcquirePushLockExclusiveEx(a1 + 8, 0);
  v7 = (PCW_QUERY_ITEM **)(a1 + 16);
  v8 = 1;
  v9 = *v7;
  while ( v9 != (PCW_QUERY_ITEM *)v7 && v8 == *((_DWORD *)v9 + 14) )
  {
    v9 = *(PCW_QUERY_ITEM **)v9;
    ++v8;
  }
  *a3 = v8;
  *((_DWORD *)*a2 + 14) = v8;
  v10 = (PCW_QUERY_ITEM **)*((_QWORD *)v9 + 1);
  if ( *v10 != v9 )
    __fastfail(3u);
  v11 = *a2;
  *(_QWORD *)v11 = v9;
  *((_QWORD *)v11 + 1) = v10;
  *v10 = v11;
  *((_QWORD *)v9 + 1) = v11;
  *a2 = 0;
  ExReleasePushLockExclusiveEx(v6, 0);
  KeLeaveCriticalRegion();
  v12 = *a2;
  if ( *a2 )
  {
    PCW_QUERY_ITEM::~PCW_QUERY_ITEM(*a2);
    ExFreePoolWithTag(v12, 0);
  }
}

```

## disassembly

```asm
0x140009750  push    rbx
0x140009752  push    rsi
0x140009753  push    rdi
0x140009754  push    r14
0x140009756  sub     rsp, 28h
0x14000975a  mov     r14, r8
0x14000975d  mov     rdi, rdx
0x140009760  mov     rbx, rcx
0x140009763  call    cs:__imp_KeEnterCriticalRegion
0x14000976a  nop     dword ptr [rax+rax+00h]
0x14000976f  lea     rsi, [rbx+8]
0x140009773  xor     edx, edx
0x140009775  mov     rcx, rsi
0x140009778  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000977f  nop     dword ptr [rax+rax+00h]
0x140009784  add     rbx, 10h
0x140009788  mov     r9d, 1
0x14000978e  mov     rcx, [rbx]
0x140009791  jmp     short loc_14000979F
0x140009793  cmp     r9d, [rcx+38h]
0x140009797  jnz     short loc_1400097A4
0x140009799  mov     rcx, [rcx]
0x14000979c  inc     r9d
0x14000979f  cmp     rcx, rbx
0x1400097a2  jnz     short loc_140009793
0x1400097a4  mov     [r14], r9d
0x1400097a7  mov     rax, [rdi]
0x1400097aa  mov     [rax+38h], r9d
0x1400097ae  mov     rdx, [rcx+8]
0x1400097b2  cmp     [rdx], rcx
0x1400097b5  jz      short loc_1400097BE
0x1400097b7  mov     ecx, 3
0x1400097bc  int     29h; Win8: RtlFailFast(ecx)
0x1400097be  mov     rax, [rdi]
0x1400097c1  mov     [rax], rcx
0x1400097c4  mov     [rax+8], rdx
0x1400097c8  mov     [rdx], rax
0x1400097cb  xor     edx, edx
0x1400097cd  mov     [rcx+8], rax
0x1400097d1  mov     rcx, rsi
0x1400097d4  mov     qword ptr [rdi], 0
0x1400097db  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400097e2  nop     dword ptr [rax+rax+00h]
0x1400097e7  call    cs:__imp_KeLeaveCriticalRegion
0x1400097ee  nop     dword ptr [rax+rax+00h]
0x1400097f3  mov     rbx, [rdi]
0x1400097f6  test    rbx, rbx
0x1400097f9  jz      short loc_140009814
0x1400097fb  mov     rcx, rbx; this
0x1400097fe  call    ??1PCW_QUERY_ITEM@@QEAA@XZ; PCW_QUERY_ITEM::~PCW_QUERY_ITEM(void)
0x140009803  xor     edx, edx; Tag
0x140009805  mov     rcx, rbx; P
0x140009808  call    cs:__imp_ExFreePoolWithTag
0x14000980f  nop     dword ptr [rax+rax+00h]
0x140009814  add     rsp, 28h
0x140009818  pop     r14
0x14000981a  pop     rdi
0x14000981b  pop     rsi
0x14000981c  pop     rbx
0x14000981d  retn
```
