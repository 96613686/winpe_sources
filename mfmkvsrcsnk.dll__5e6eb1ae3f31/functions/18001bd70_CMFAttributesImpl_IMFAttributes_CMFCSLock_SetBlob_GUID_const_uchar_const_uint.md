# CMFAttributesImpl<IMFAttributes,CMFCSLock>::SetBlob(_GUID const &,uchar const *,uint)

- ea: `0x18001bd70`
- end: `0x18001be13`
- name: `?SetBlob@?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@UEAAJAEBU_GUID@@PEBEI@Z`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800036c5`
- `0x18000e798`
- `0x18001bd70`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bd8f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bd8f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bdfc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bdfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001bdb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001bdb2`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CMFCSLock>::SetBlob(
        __int64 a1,
        __int64 a2,
        const void *a3,
        unsigned int a4)
{
  SIZE_T v5; // r15
  __int64 Item; // rsi
  unsigned int v9; // ebx
  void *v10; // rax

  v5 = a4;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  Item = CMFAttributesImpl<IMFAttributes,CMFCSLock>::CreateItem(a1, a2);
  if ( Item )
  {
    v10 = CoTaskMemAlloc(v5);
    *(_QWORD *)(Item + 16) = v10;
    if ( v10 )
    {
      v9 = 0;
      memcpy_0(v10, a3, v5);
      *(_WORD *)Item = 4113;
      *(_DWORD *)(Item + 8) = v5;
      *(_DWORD *)(a1 + 64) = 1;
      goto LABEL_6;
    }
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 152LL))(a1, a2);
  }
  v9 = -2147024882;
LABEL_6:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return v9;
}

```

## disassembly

```asm
0x18001bd70  push    rbx
0x18001bd72  push    rbp
0x18001bd73  push    rsi
0x18001bd74  push    rdi
0x18001bd75  push    r12
0x18001bd77  push    r14
0x18001bd79  push    r15
0x18001bd7b  sub     rsp, 20h
0x18001bd7f  mov     rdi, rcx
0x18001bd82  mov     r15d, r9d
0x18001bd85  add     rcx, 8; lpCriticalSection
0x18001bd89  mov     r12, r8
0x18001bd8c  mov     rbx, rdx
0x18001bd8f  call    cs:__imp_EnterCriticalSection
0x18001bd95  mov     rdx, rbx
0x18001bd98  mov     rcx, rdi
0x18001bd9b  call    ?CreateItem@?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CMFCSLock>::CreateItem(_GUID const &)
0x18001bda0  mov     rsi, rax
0x18001bda3  test    rax, rax
0x18001bda6  jnz     short loc_18001BDAF
0x18001bda8  mov     ebx, 8007000Eh
0x18001bdad  jmp     short loc_18001BDF8
0x18001bdaf  mov     rcx, r15; cb
0x18001bdb2  call    cs:__imp_CoTaskMemAlloc
0x18001bdb8  mov     [rsi+10h], rax
0x18001bdbc  test    rax, rax
0x18001bdbf  jnz     short loc_18001BDD8
0x18001bdc1  mov     rax, [rdi]
0x18001bdc4  mov     rdx, rbx
0x18001bdc7  mov     rcx, rdi
0x18001bdca  mov     rax, [rax+98h]
0x18001bdd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bdd6  jmp     short loc_18001BDA8
0x18001bdd8  xor     ebx, ebx
0x18001bdda  mov     r8, r15; Size
0x18001bddd  mov     rdx, r12; Src
0x18001bde0  mov     rcx, rax; void *
0x18001bde3  call    memcpy_0
0x18001bde8  mov     word ptr [rsi], 1011h
0x18001bded  mov     [rsi+8], r15d
0x18001bdf1  mov     dword ptr [rdi+40h], 1
0x18001bdf8  lea     rcx, [rdi+8]; lpCriticalSection
0x18001bdfc  call    cs:__imp_LeaveCriticalSection
0x18001be02  mov     eax, ebx
0x18001be04  add     rsp, 20h
0x18001be08  pop     r15
0x18001be0a  pop     r14
0x18001be0c  pop     r12
0x18001be0e  pop     rdi
0x18001be0f  pop     rsi
0x18001be10  pop     rbp
0x18001be11  pop     rbx
0x18001be12  retn
```
