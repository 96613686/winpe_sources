# AddAggregateObject(CGenericList<CAggregateMarshaler> *,CAggregateMarshaler *,IUnknown *,int)

- ea: `0x18000b2e4`
- end: `0x18000b410`
- name: `?AddAggregateObject@@YAJPEAV?$CGenericList@VCAggregateMarshaler@@@@PEAVCAggregateMarshaler@@PEAUIUnknown@@H@Z`
- size: `300`
- prototype: `__int64 __fastcall(CBaseList *this, char *, LPUNKNOWN pUnkOuter, int)`
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180008690`
- `0x18000aaac`
- `0x18000dd00`
- `0x1800196f0`
- `0x180031f1c`

## callees

- `0x180003b78`
- `0x18000b2e4`
- `0x18000e400`
- `0x18001f1c4`
- `0x180045010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000b368`
- `ole32!CoCreateInstance` at `0x18000b368`

## pseudocode

```c
__int64 __fastcall AddAggregateObject(CBaseList *this, char *a2, LPUNKNOWN pUnkOuter, int a4)
{
  IUnknown *v5; // r10
  CBaseList *v7; // r14
  _QWORD *NextI; // rax
  HRESULT Instance; // edi
  __int64 v10; // rcx
  struct __POSITION *m_pFirst; // [rsp+50h] [rbp+8h] BYREF

  m_pFirst = (struct __POSITION *)this->m_pFirst;
  v5 = pUnkOuter;
  v7 = this;
  if ( m_pFirst )
  {
    while ( 1 )
    {
      NextI = CBaseList::GetNextI(this, &m_pFirst);
      this = *(CBaseList **)a2;
      if ( *(_QWORD *)a2 == *NextI )
      {
        this = (CBaseList *)*((_QWORD *)a2 + 1);
        if ( this == (CBaseList *)NextI[1] )
        {
          this = (CBaseList *)*((_QWORD *)a2 + 2);
          if ( this == (CBaseList *)NextI[2] && *((_QWORD *)a2 + 3) == NextI[3] )
            break;
        }
      }
      if ( !m_pFirst )
        goto LABEL_7;
    }
    if ( NextI )
    {
      Instance = -2147024713;
      if ( *((_DWORD *)NextI + 12) )
      {
        if ( !*((_DWORD *)NextI + 13) )
        {
          v10 = NextI[5];
          *((_DWORD *)NextI + 13) = 1;
          if ( v10 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 56LL))(v10);
        }
      }
      goto LABEL_16;
    }
  }
LABEL_7:
  Instance = CoCreateInstance(
               (const IID *const)a2 + 1,
               v5,
               0x401u,
               &GUID_00000000_0000_0000_c000_000000000046,
               (LPVOID *)a2 + 4);
  if ( Instance < 0 )
  {
LABEL_16:
    operator delete(a2, 0x38u);
    return (unsigned int)Instance;
  }
  if ( (***((int (__fastcall ****)(_QWORD, GUID *, char *))a2 + 4))(
         *((_QWORD *)a2 + 4),
         &GUID_56a868af_0ad4_11ce_b03a_0020af0ba770,
         a2 + 40) >= 0 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)a2 + 5) + 16LL))(*((_QWORD *)a2 + 5));
  *((_DWORD *)a2 + 12) = a4;
  *((_DWORD *)a2 + 13) = a4;
  CBaseList::AddTailI(v7, a2);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000b2e4  mov     [rsp+arg_8], rbx
0x18000b2e9  mov     [rsp+arg_10], rsi
0x18000b2ee  push    rdi
0x18000b2ef  push    r14
0x18000b2f1  push    r15
0x18000b2f3  sub     rsp, 30h
0x18000b2f7  mov     rax, [rcx]
0x18000b2fa  mov     esi, r9d
0x18000b2fd  mov     [rsp+48h+arg_0], rax
0x18000b302  mov     r10, r8
0x18000b305  mov     rbx, rdx
0x18000b308  mov     r14, rcx
0x18000b30b  test    rax, rax
0x18000b30e  jz      short loc_18000B34B
0x18000b310  lea     rdx, [rsp+48h+arg_0]; struct __POSITION **
0x18000b315  call    ?GetNextI@CBaseList@@IEBAPEAXAEAPEAU__POSITION@@@Z; CBaseList::GetNextI(__POSITION * &)
0x18000b31a  mov     rcx, [rbx]
0x18000b31d  mov     rdx, rax
0x18000b320  cmp     rcx, [rax]
0x18000b323  jnz     short loc_18000B343
0x18000b325  mov     rcx, [rbx+8]
0x18000b329  cmp     rcx, [rax+8]
0x18000b32d  jnz     short loc_18000B343
0x18000b32f  mov     rcx, [rbx+10h]
0x18000b333  cmp     rcx, [rax+10h]
0x18000b337  jnz     short loc_18000B343
0x18000b339  mov     rax, [rbx+18h]
0x18000b33d  cmp     rax, [rdx+18h]
0x18000b341  jz      short loc_18000B3BA
0x18000b343  cmp     [rsp+48h+arg_0], 0
0x18000b349  jnz     short loc_18000B310
0x18000b34b  lea     r15, [rbx+20h]
0x18000b34f  mov     r8d, 401h; dwClsContext
0x18000b355  lea     rcx, [rbx+10h]; rclsid
0x18000b359  mov     [rsp+48h+ppv], r15; ppv
0x18000b35e  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18000b365  mov     rdx, r10; pUnkOuter
0x18000b368  call    cs:__imp_CoCreateInstance
0x18000b36f  nop     dword ptr [rax+rax+00h]
0x18000b374  mov     edi, eax
0x18000b376  test    eax, eax
0x18000b378  js      short loc_18000B3EC
0x18000b37a  mov     rcx, [r15]
0x18000b37d  lea     r8, [rbx+28h]
0x18000b381  mov     rdx, [rcx]
0x18000b384  mov     rax, [rdx]
0x18000b387  lea     rdx, _GUID_56a868af_0ad4_11ce_b03a_0020af0ba770
0x18000b38e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b393  test    eax, eax
0x18000b395  js      short loc_18000B3A7
0x18000b397  mov     rcx, [rbx+28h]
0x18000b39b  mov     rax, [rcx]
0x18000b39e  mov     rax, [rax+10h]
0x18000b3a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3a7  mov     rdx, rbx; void *
0x18000b3aa  mov     [rbx+30h], esi
0x18000b3ad  mov     rcx, r14; this
0x18000b3b0  mov     [rbx+34h], esi
0x18000b3b3  call    ?AddTailI@CBaseList@@IEAAPEAU__POSITION@@PEAX@Z; CBaseList::AddTailI(void *)
0x18000b3b8  jmp     short loc_18000B3F9
0x18000b3ba  test    rdx, rdx
0x18000b3bd  jz      short loc_18000B34B
0x18000b3bf  cmp     dword ptr [rdx+30h], 0
0x18000b3c3  mov     edi, 800700B7h
0x18000b3c8  jz      short loc_18000B3EC
0x18000b3ca  cmp     dword ptr [rdx+34h], 0
0x18000b3ce  jnz     short loc_18000B3EC
0x18000b3d0  mov     rcx, [rdx+28h]
0x18000b3d4  mov     dword ptr [rdx+34h], 1
0x18000b3db  test    rcx, rcx
0x18000b3de  jz      short loc_18000B3EC
0x18000b3e0  mov     rax, [rcx]
0x18000b3e3  mov     rax, [rax+38h]
0x18000b3e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3ec  mov     edx, 38h ; '8'; unsigned __int64
0x18000b3f1  mov     rcx, rbx; void *
0x18000b3f4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b3f9  mov     rbx, [rsp+48h+arg_8]
0x18000b3fe  mov     eax, edi
0x18000b400  mov     rsi, [rsp+48h+arg_10]
0x18000b405  add     rsp, 30h
0x18000b409  pop     r15
0x18000b40b  pop     r14
0x18000b40d  pop     rdi
0x18000b40e  retn
```
