# CKsOutputPin::GetMediaType(int,CMediaType *)

- ea: `0x1800042b0`
- end: `0x1800043bd`
- name: `?GetMediaType@CKsOutputPin@@UEAAJHPEAVCMediaType@@@Z`
- size: `269`
- prototype: `__int64 __fastcall(CKsOutputPin *__hidden this, int, struct CMediaType *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180008690`

## callees

- `0x1800042b0`
- `0x180005850`
- `0x180044850`
- `0x180045010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18000431e`
- `ole32!CoTaskMemAlloc` at `0x18000431e`

## pseudocode

```c
__int64 __fastcall CKsOutputPin::GetMediaType(CKsOutputPin *this, int a2, struct CMediaType *a3)
{
  struct CMediaType *m_ConfigAmMediaType; // rsi
  unsigned __int8 *v7; // rax
  unsigned int *p_cbFormat; // rbx
  unsigned int m_PinFactoryId; // ebx
  char *v11; // rax

  m_ConfigAmMediaType = (struct CMediaType *)this->m_ConfigAmMediaType;
  if ( !m_ConfigAmMediaType )
  {
    m_PinFactoryId = this->m_PinFactoryId;
    v11 = (char *)((__int64 (__fastcall *)(IReferenceClock **))this->m_pFilter[1].m_pClock[3].__vftable)(&this->m_pFilter[1].m_pClock);
    return KsGetMediaType(a2, (__int64)a3, v11, m_PinFactoryId);
  }
  if ( a2 )
    return 262403;
  *a3 = *m_ConfigAmMediaType;
  if ( !m_ConfigAmMediaType->cbFormat )
  {
    p_cbFormat = &a3->cbFormat;
    goto LABEL_6;
  }
  v7 = (unsigned __int8 *)CoTaskMemAlloc(m_ConfigAmMediaType->cbFormat);
  a3->pbFormat = v7;
  p_cbFormat = &a3->cbFormat;
  if ( v7 )
  {
    memcpy_0(v7, m_ConfigAmMediaType->pbFormat, *p_cbFormat);
LABEL_6:
    a3->pUnk = 0;
    goto LABEL_7;
  }
  *p_cbFormat = 0;
LABEL_7:
  if ( this->m_ConfigAmMediaType->cbFormat )
    return *p_cbFormat == 0 ? 0x8007000E : 0;
  else
    return 0;
}

```

## disassembly

```asm
0x1800042b0  push    rbx
0x1800042b2  push    rbp
0x1800042b3  push    rsi
0x1800042b4  push    rdi
0x1800042b5  push    r14
0x1800042b7  sub     rsp, 20h
0x1800042bb  mov     rsi, [rcx+350h]
0x1800042c2  mov     rdi, r8
0x1800042c5  mov     r14d, edx
0x1800042c8  mov     rbp, rcx
0x1800042cb  test    rsi, rsi
0x1800042ce  jz      loc_18000436A
0x1800042d4  test    edx, edx
0x1800042d6  jnz     loc_1800043A4
0x1800042dc  movups  xmm0, xmmword ptr [rsi]
0x1800042df  movups  xmmword ptr [r8], xmm0
0x1800042e3  movups  xmm1, xmmword ptr [rsi+10h]
0x1800042e7  movups  xmmword ptr [r8+10h], xmm1
0x1800042ec  movups  xmm0, xmmword ptr [rsi+20h]
0x1800042f0  movups  xmmword ptr [r8+20h], xmm0
0x1800042f5  movups  xmm1, xmmword ptr [rsi+30h]
0x1800042f9  movups  xmmword ptr [r8+30h], xmm1
0x1800042fe  movups  xmm0, xmmword ptr [rsi+40h]
0x180004302  movups  xmmword ptr [r8+40h], xmm0
0x180004307  movsd   xmm1, qword ptr [rsi+50h]
0x18000430c  movsd   qword ptr [r8+50h], xmm1
0x180004312  cmp     [rsi+48h], edx
0x180004315  jz      loc_1800043AB
0x18000431b  mov     ecx, [rsi+48h]; cb
0x18000431e  call    cs:__imp_CoTaskMemAlloc
0x180004325  nop     dword ptr [rax+rax+00h]
0x18000432a  mov     [rdi+50h], rax
0x18000432e  lea     rbx, [rdi+48h]
0x180004332  test    rax, rax
0x180004335  jz      short loc_1800043B1
0x180004337  mov     r8d, [rbx]; Size
0x18000433a  mov     rcx, rax; void *
0x18000433d  mov     rdx, [rsi+50h]; Src
0x180004341  call    memcpy_0
0x180004346  mov     qword ptr [rdi+40h], 0
0x18000434e  mov     rax, [rbp+350h]
0x180004355  cmp     dword ptr [rax+48h], 0
0x180004359  jz      short loc_1800043B9
0x18000435b  mov     eax, [rbx]
0x18000435d  neg     eax
0x18000435f  sbb     eax, eax
0x180004361  not     eax
0x180004363  and     eax, 8007000Eh
0x180004368  jmp     short loc_180004398
0x18000436a  mov     ebx, [rcx+248h]
0x180004370  mov     rcx, [rcx+50h]
0x180004374  add     rcx, 0A8h
0x18000437b  mov     rax, [rcx]
0x18000437e  mov     rax, [rax+18h]
0x180004382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004387  mov     r9d, ebx
0x18000438a  mov     r8, rax
0x18000438d  mov     rdx, rdi
0x180004390  mov     ecx, r14d
0x180004393  call    KsGetMediaType
0x180004398  add     rsp, 20h
0x18000439c  pop     r14
0x18000439e  pop     rdi
0x18000439f  pop     rsi
0x1800043a0  pop     rbp
0x1800043a1  pop     rbx
0x1800043a2  retn
0x1800043a4  mov     eax, 40103h
0x1800043a9  jmp     short loc_180004398
0x1800043ab  lea     rbx, [r8+48h]
0x1800043af  jmp     short loc_180004346
0x1800043b1  mov     dword ptr [rbx], 0
0x1800043b7  jmp     short loc_18000434E
0x1800043b9  xor     eax, eax
0x1800043bb  jmp     short loc_180004398
```
