# CdCreateIrpContext

- ea: `0x1400188bc`
- end: `0x140018a00`
- name: `CdCreateIrpContext`
- size: `324`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140001240`

## callees

- `0x140003300`
- `0x1400188bc`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x14001891c`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001891c`
- `ntoskrnl!ExRaiseStatus` at `0x1400188f9`
- `ntoskrnl!ExRaiseStatus` at `0x1400188f9`
- `ntoskrnl!ExReleaseFastMutex` at `0x140018969`
- `ntoskrnl!ExReleaseFastMutex` at `0x140018969`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140018988`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140018988`

## pseudocode

```c
_DWORD *__fastcall CdCreateIrpContext(__int64 a1, char a2)
{
  __int64 v2; // rdi
  void *v5; // rsi
  _DWORD *PoolWithTag; // rbx
  void *v7; // rax
  __int64 v8; // rax
  struct _DEVICE_OBJECT *v9; // rax

  v2 = *(_QWORD *)(a1 + 184);
  if ( *(PDEVICE_OBJECT *)(v2 + 40) == DeviceObject
    && *(_QWORD *)(v2 + 48)
    && ((*(_BYTE *)v2 & 0xED) != 0 || *(_BYTE *)v2 == 16) )
  {
    ExRaiseStatus(-1073741808);
  }
  if ( !dword_140007300 )
    goto LABEL_10;
  ExAcquireFastMutex(&FastMutex);
  v5 = qword_140007308;
  qword_140007350 = (__int64)KeGetCurrentThread();
  PoolWithTag = qword_140007308;
  if ( qword_140007308 )
  {
    v7 = *(void **)qword_140007308;
    --dword_140007300;
    qword_140007308 = v7;
  }
  qword_140007350 = 0;
  ExReleaseFastMutex(&FastMutex);
  if ( !v5 )
LABEL_10:
    PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)528, 0x70u, 0x63696443u);
  memset(PoolWithTag, 0, 0x70u);
  *PoolWithTag = 7340808;
  *((_QWORD *)PoolWithTag + 1) = a1;
  v8 = *(_QWORD *)(v2 + 48);
  if ( v8 )
    *((_QWORD *)PoolWithTag + 5) = *(_QWORD *)(v8 + 8);
  v9 = *(struct _DEVICE_OBJECT **)(v2 + 40);
  if ( v9 != DeviceObject )
    *((_QWORD *)PoolWithTag + 2) = (char *)v9 + 368;
  *((_BYTE *)PoolWithTag + 64) = *(_BYTE *)v2;
  *((_BYTE *)PoolWithTag + 65) = *(_BYTE *)(v2 + 1);
  PoolWithTag[8] |= a2 != 0 ? 4 : 8;
  return PoolWithTag;
}

```

## disassembly

```asm
0x1400188bc  push    rbx
0x1400188be  push    rbp
0x1400188bf  push    rsi
0x1400188c0  push    rdi
0x1400188c1  push    r12
0x1400188c3  push    r14
0x1400188c5  sub     rsp, 28h
0x1400188c9  mov     rdi, [rcx+0B8h]
0x1400188d0  mov     bpl, dl
0x1400188d3  mov     rax, cs:DeviceObject
0x1400188da  mov     r14, rcx
0x1400188dd  cmp     [rdi+28h], rax
0x1400188e1  jnz     short loc_140018906
0x1400188e3  cmp     qword ptr [rdi+30h], 0
0x1400188e8  jz      short loc_140018906
0x1400188ea  mov     al, [rdi]
0x1400188ec  test    al, 0EDh
0x1400188ee  jnz     short loc_1400188F4
0x1400188f0  cmp     al, 10h
0x1400188f2  jnz     short loc_140018906
0x1400188f4  mov     ecx, 0C0000010h; Status
0x1400188f9  call    cs:__imp_ExRaiseStatus
0x140018906  cmp     cs:dword_140007300, 0
0x14001890d  mov     r12d, 70h ; 'p'
0x140018913  jz      short loc_14001897A
0x140018915  lea     rcx, FastMutex; FastMutex
0x14001891c  call    cs:__imp_ExAcquireFastMutex
0x140018923  nop     dword ptr [rax+rax+00h]
0x140018928  mov     rax, gs:188h
0x140018931  mov     rsi, cs:qword_140007308
0x140018938  mov     cs:qword_140007350, rax
0x14001893f  mov     rbx, rsi
0x140018942  test    rsi, rsi
0x140018945  jz      short loc_140018957
0x140018947  mov     rax, [rsi]
0x14001894a  dec     cs:dword_140007300
0x140018950  mov     cs:qword_140007308, rax
0x140018957  lea     rcx, FastMutex; FastMutex
0x14001895e  mov     cs:qword_140007350, 0
0x140018969  call    cs:__imp_ExReleaseFastMutex
0x140018970  nop     dword ptr [rax+rax+00h]
0x140018975  test    rsi, rsi
0x140018978  jnz     short loc_140018997
0x14001897a  mov     r8d, 63696443h; Tag
0x140018980  mov     rdx, r12; NumberOfBytes
0x140018983  mov     ecx, 210h; PoolType
0x140018988  call    cs:__imp_ExAllocatePoolWithTag
0x14001898f  nop     dword ptr [rax+rax+00h]
0x140018994  mov     rbx, rax
0x140018997  mov     r8, r12; Size
0x14001899a  xor     edx, edx; Val
0x14001899c  mov     rcx, rbx; void *
0x14001899f  call    memset
0x1400189a4  mov     dword ptr [rbx], 700308h
0x1400189aa  mov     [rbx+8], r14
0x1400189ae  mov     rax, [rdi+30h]
0x1400189b2  test    rax, rax
0x1400189b5  jz      short loc_1400189BF
0x1400189b7  mov     rax, [rax+8]
0x1400189bb  mov     [rbx+28h], rax
0x1400189bf  mov     rax, [rdi+28h]
0x1400189c3  cmp     rax, cs:DeviceObject
0x1400189ca  jz      short loc_1400189D6
0x1400189cc  add     rax, 170h
0x1400189d2  mov     [rbx+10h], rax
0x1400189d6  mov     al, [rdi]
0x1400189d8  neg     bpl
0x1400189db  mov     [rbx+40h], al
0x1400189de  mov     al, [rdi+1]
0x1400189e1  mov     [rbx+41h], al
0x1400189e4  sbb     eax, eax
0x1400189e6  and     eax, 0FFFFFFFCh
0x1400189e9  add     eax, 8
0x1400189ec  or      [rbx+20h], eax
0x1400189ef  mov     rax, rbx
0x1400189f2  add     rsp, 28h
0x1400189f6  pop     r14
0x1400189f8  pop     r12
0x1400189fa  pop     rdi
0x1400189fb  pop     rsi
0x1400189fc  pop     rbp
0x1400189fd  pop     rbx
0x1400189fe  retn
```
