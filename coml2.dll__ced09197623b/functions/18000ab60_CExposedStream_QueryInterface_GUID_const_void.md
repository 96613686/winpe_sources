# CExposedStream::QueryInterface(_GUID const &,void * *)

- ea: `0x18000ab60`
- end: `0x18000ae0e`
- name: `?QueryInterface@CExposedStream@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `686`
- prototype: `__int64 __fastcall(CExposedStream *__hidden this, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18004df70`
- `0x18004df80`
- `0x18004df90`

## callees

- `0x18000ab60`
- `0x18000b650`
- `0x18000b8d0`
- `0x180018914`
- `0x18001bf68`
- `0x18003686c`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000adaa`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000adaa`

## pseudocode

```c
__int64 __fastcall CExposedStream::QueryInterface(CExposedStream *this, const struct _GUID *a2, void **a3)
{
  int v6; // ebx
  __int64 v7; // rax
  __int64 v8; // rax
  void (*Release)(void); // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 (__fastcall ***v18)(_QWORD, GUID *, LPUNKNOWN *); // rcx
  HRESULT v19; // eax
  LPUNKNOWN v20; // rcx
  LPUNKNOWN v21; // rcx
  _BYTE v22[16]; // [rsp+20h] [rbp-10h] BYREF
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+20h] BYREF

  CSafeMultiHeap::CSafeMultiHeap((CSafeMultiHeap *)v22, *((struct CPerContext **)this + 15));
  if ( !a3 )
  {
    v6 = -2147287031;
    goto LABEL_14;
  }
  *a3 = 0;
  v6 = CExposedStream::Validate(this);
  if ( v6 >= 0 )
  {
    if ( (*(_BYTE *)(*((_QWORD *)this + 13) + 20LL) & 0x20) != 0 )
    {
      v6 = -2147286782;
      goto LABEL_14;
    }
    v6 = 0;
    v7 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IStream.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IStream.Data1 )
      v7 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IStream.Data4;
    if ( !v7 )
      goto LABEL_10;
    v8 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
      v8 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IUnknown.Data4;
    if ( !v8 )
    {
LABEL_10:
      *a3 = this;
LABEL_11:
      Release = *(void (**)(void))(*(_QWORD *)this + 8LL);
LABEL_12:
      Release();
      goto LABEL_14;
    }
    v11 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IMarshal.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IMarshal.Data1 )
      v11 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IMarshal.Data4;
    if ( !v11 )
      goto LABEL_54;
    v12 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IAgileObject.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IAgileObject.Data1 )
      v12 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IAgileObject.Data4;
    if ( v12 )
    {
      v13 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IMappedStream.Data1;
      if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IMappedStream.Data1 )
        v13 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IMappedStream.Data4;
      if ( v13 )
      {
        v14 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IConnectionPointContainer.Data1;
        if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IConnectionPointContainer.Data1 )
          v14 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IConnectionPointContainer.Data4;
        if ( !v14 && *((_QWORD *)this + 6) )
        {
          *a3 = (void *)(((unsigned __int64)this + 24) & -(__int64)(this != 0));
          CExposedStream::AddRef(this);
          goto LABEL_14;
        }
        goto LABEL_27;
      }
      v15 = (unsigned __int64)this + 16;
    }
    else
    {
LABEL_54:
      if ( IsSharedMemoryModeDisabledForCurrentProcess() )
      {
        if ( !*((_QWORD *)this + 18) )
        {
          ppunkMarshal = 0;
          v19 = CoCreateFreeThreadedMarshaler((LPUNKNOWN)this, &ppunkMarshal);
          v20 = ppunkMarshal;
          v6 = v19;
          if ( v19 < 0 )
          {
            if ( !ppunkMarshal )
              goto LABEL_14;
            ppunkMarshal = 0;
            Release = (void (*)(void))v20->lpVtbl->Release;
            goto LABEL_12;
          }
          if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 18, (signed __int64)ppunkMarshal, 0) )
            v21 = ppunkMarshal;
          else
            v21 = 0;
          if ( v21 )
          {
            ppunkMarshal = 0;
            ((void (__fastcall *)(LPUNKNOWN))v21->lpVtbl->Release)(v21);
          }
        }
        v6 = (***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))this + 18))(
               *((_QWORD *)this + 18),
               a2,
               a3);
        goto LABEL_14;
      }
      v16 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IMarshal.Data1;
      if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IMarshal.Data1 )
        v16 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IMarshal.Data4;
      if ( v16 )
        goto LABEL_27;
      v17 = *((_QWORD *)this + 15);
      ppunkMarshal = 0;
      v18 = *(__int64 (__fastcall ****)(_QWORD, GUID *, LPUNKNOWN *))(v17 + 32);
      if ( !v18 )
        v18 = *(__int64 (__fastcall ****)(_QWORD, GUID *, LPUNKNOWN *))(v17 + 16);
      v6 = (**v18)(v18, &IID_IDfReserved1, &ppunkMarshal);
      if ( v6 < 0
        || (((void (__fastcall *)(LPUNKNOWN))ppunkMarshal->lpVtbl->Release)(ppunkMarshal),
            !*(_QWORD *)(*((_QWORD *)this + 15) + 96LL)) )
      {
LABEL_27:
        v6 = -2147467262;
        goto LABEL_14;
      }
      v15 = (unsigned __int64)this + 8;
    }
    *a3 = (void *)(v15 & -(__int64)(this != 0));
    goto LABEL_11;
  }
LABEL_14:
  CSafeMultiHeap::~CSafeMultiHeap((CSafeMultiHeap *)v22);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000ab60  mov     [rsp-18h+arg_8], rbx
0x18000ab65  mov     [rsp-18h+arg_10], rsi
0x18000ab6a  push    rbp
0x18000ab6b  push    rdi
0x18000ab6c  push    r14
0x18000ab6e  mov     rbp, rsp
0x18000ab71  sub     rsp, 30h
0x18000ab75  mov     rsi, rdx
0x18000ab78  mov     rdi, rcx
0x18000ab7b  mov     rdx, [rcx+78h]; struct CPerContext *
0x18000ab7f  mov     r14, r8
0x18000ab82  lea     rcx, [rbp+var_10]; this
0x18000ab86  call    ??0CSafeMultiHeap@@QEAA@PEAVCPerContext@@@Z; CSafeMultiHeap::CSafeMultiHeap(CPerContext *)
0x18000ab8b  test    r14, r14
0x18000ab8e  jz      short loc_18000ABFE
0x18000ab90  mov     rcx, rdi; this
0x18000ab93  mov     qword ptr [r14], 0
0x18000ab9a  call    ?Validate@CExposedStream@@QEBAJXZ; CExposedStream::Validate(void)
0x18000ab9f  mov     ebx, eax
0x18000aba1  test    eax, eax
0x18000aba3  js      short loc_18000AC03
0x18000aba5  mov     rax, [rdi+68h]
0x18000aba9  test    byte ptr [rax+14h], 20h
0x18000abad  jnz     loc_18000ACBE
0x18000abb3  mov     rax, [rsi]
0x18000abb6  xor     ebx, ebx
0x18000abb8  sub     rax, qword ptr cs:IID_IStream.Data1
0x18000abbf  jnz     short loc_18000ABCC
0x18000abc1  mov     rax, [rsi+8]
0x18000abc5  sub     rax, qword ptr cs:IID_IStream.Data4
0x18000abcc  test    rax, rax
0x18000abcf  jz      short loc_18000ABED
0x18000abd1  mov     rax, [rsi]
0x18000abd4  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x18000abdb  jnz     short loc_18000ABE8
0x18000abdd  mov     rax, [rsi+8]
0x18000abe1  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x18000abe8  test    rax, rax
0x18000abeb  jnz     short loc_18000AC21
0x18000abed  mov     [r14], rdi
0x18000abf0  mov     rax, [rdi]
0x18000abf3  mov     rax, [rax+8]
0x18000abf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abfc  jmp     short loc_18000AC03
0x18000abfe  mov     ebx, 80030009h
0x18000ac03  lea     rcx, [rbp+var_10]; this
0x18000ac07  call    ??1CSafeMultiHeap@@QEAA@XZ; CSafeMultiHeap::~CSafeMultiHeap(void)
0x18000ac0c  mov     rsi, [rsp+30h+arg_10]
0x18000ac11  mov     eax, ebx
0x18000ac13  mov     rbx, [rsp+30h+arg_8]
0x18000ac18  add     rsp, 30h
0x18000ac1c  pop     r14
0x18000ac1e  pop     rdi
0x18000ac1f  pop     rbp
0x18000ac20  retn
0x18000ac21  mov     rax, [rsi]
0x18000ac24  sub     rax, qword ptr cs:IID_IMarshal.Data1
0x18000ac2b  jnz     short loc_18000AC38
0x18000ac2d  mov     rax, [rsi+8]
0x18000ac31  sub     rax, qword ptr cs:IID_IMarshal.Data4
0x18000ac38  test    rax, rax
0x18000ac3b  jz      loc_18000ACC8
0x18000ac41  mov     rax, [rsi]
0x18000ac44  sub     rax, qword ptr cs:IID_IAgileObject.Data1
0x18000ac4b  jnz     short loc_18000AC58
0x18000ac4d  mov     rax, [rsi+8]
0x18000ac51  sub     rax, qword ptr cs:IID_IAgileObject.Data4
0x18000ac58  test    rax, rax
0x18000ac5b  jz      short loc_18000ACC8
0x18000ac5d  mov     rax, [rsi]
0x18000ac60  sub     rax, qword ptr cs:IID_IMappedStream.Data1
0x18000ac67  jnz     short loc_18000AC74
0x18000ac69  mov     rax, [rsi+8]
0x18000ac6d  sub     rax, qword ptr cs:IID_IMappedStream.Data4
0x18000ac74  test    rax, rax
0x18000ac77  jz      short loc_18000ACA3
0x18000ac79  mov     rax, [rsi]
0x18000ac7c  sub     rax, qword ptr cs:IID_IConnectionPointContainer.Data1
0x18000ac83  jnz     short loc_18000AC90
0x18000ac85  mov     rax, [rsi+8]
0x18000ac89  sub     rax, qword ptr cs:IID_IConnectionPointContainer.Data4
0x18000ac90  test    rax, rax
0x18000ac93  jz      loc_18000AD75
0x18000ac99  mov     ebx, 80004002h
0x18000ac9e  jmp     loc_18000AC03
0x18000aca3  lea     rdx, [rdi+10h]
0x18000aca7  mov     rax, rdi
0x18000acaa  neg     rax
0x18000acad  sbb     rcx, rcx
0x18000acb0  and     rcx, rdx
0x18000acb3  mov     [r14], rcx
0x18000acb6  mov     rcx, rdi
0x18000acb9  jmp     loc_18000ABF0
0x18000acbe  mov     ebx, 80030102h
0x18000acc3  jmp     loc_18000AC03
0x18000acc8  call    ?IsSharedMemoryModeDisabledForCurrentProcess@@YA_NXZ; IsSharedMemoryModeDisabledForCurrentProcess(void)
0x18000accd  test    al, al
0x18000accf  jnz     short loc_18000AD4A
0x18000acd1  mov     rax, [rsi]
0x18000acd4  sub     rax, qword ptr cs:IID_IMarshal.Data1
0x18000acdb  jnz     short loc_18000ACE8
0x18000acdd  mov     rax, [rsi+8]
0x18000ace1  sub     rax, qword ptr cs:IID_IMarshal.Data4
0x18000ace8  test    rax, rax
0x18000aceb  jnz     short loc_18000AC99
0x18000aced  mov     rax, [rdi+78h]
0x18000acf1  mov     [rbp+ppunkMarshal], rbx
0x18000acf5  mov     rcx, [rax+20h]
0x18000acf9  test    rcx, rcx
0x18000acfc  jnz     short loc_18000AD02
0x18000acfe  mov     rcx, [rax+10h]
0x18000ad02  mov     rax, [rcx]
0x18000ad05  lea     r8, [rbp+ppunkMarshal]
0x18000ad09  lea     rdx, IID_IDfReserved1
0x18000ad10  mov     rax, [rax]
0x18000ad13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad18  mov     ebx, eax
0x18000ad1a  test    eax, eax
0x18000ad1c  js      loc_18000AC99
0x18000ad22  mov     rcx, [rbp+ppunkMarshal]
0x18000ad26  mov     rax, [rcx]
0x18000ad29  mov     rax, [rax+10h]
0x18000ad2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad32  mov     rax, [rdi+78h]
0x18000ad36  cmp     qword ptr [rax+60h], 0
0x18000ad3b  jz      loc_18000AC99
0x18000ad41  lea     rdx, [rdi+8]
0x18000ad45  jmp     loc_18000ACA7
0x18000ad4a  mov     rax, [rdi+90h]
0x18000ad51  test    rax, rax
0x18000ad54  jz      short loc_18000AD9F
0x18000ad56  mov     rcx, [rdi+90h]
0x18000ad5d  mov     r8, r14
0x18000ad60  mov     rdx, rsi
0x18000ad63  mov     rax, [rcx]
0x18000ad66  mov     rax, [rax]
0x18000ad69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad6e  mov     ebx, eax
0x18000ad70  jmp     loc_18000AC03
0x18000ad75  cmp     [rdi+30h], rbx
0x18000ad79  jz      loc_18000AC99
0x18000ad7f  lea     rdx, [rdi+18h]
0x18000ad83  mov     rax, rdi
0x18000ad86  neg     rax
0x18000ad89  sbb     rcx, rcx
0x18000ad8c  and     rcx, rdx
0x18000ad8f  mov     [r14], rcx
0x18000ad92  mov     rcx, rdi; this
0x18000ad95  call    ?AddRef@CExposedStream@@UEAAKXZ; CExposedStream::AddRef(void)
0x18000ad9a  jmp     loc_18000AC03
0x18000ad9f  lea     rdx, [rbp+ppunkMarshal]; ppunkMarshal
0x18000ada3  mov     [rbp+ppunkMarshal], rbx
0x18000ada7  mov     rcx, rdi; punkOuter
0x18000adaa  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18000adb0  mov     rcx, [rbp+ppunkMarshal]
0x18000adb4  mov     ebx, eax
0x18000adb6  test    eax, eax
0x18000adb8  jns     short loc_18000ADD7
0x18000adba  test    rcx, rcx
0x18000adbd  jz      loc_18000AC03
0x18000adc3  mov     [rbp+ppunkMarshal], 0
0x18000adcb  mov     rax, [rcx]
0x18000adce  mov     rax, [rax+10h]
0x18000add2  jmp     loc_18000ABF7
0x18000add7  xor     eax, eax
0x18000add9  lock cmpxchg [rdi+90h], rcx
0x18000ade2  jnz     short loc_18000ADE8
0x18000ade4  xor     ecx, ecx
0x18000ade6  jmp     short loc_18000ADEC
0x18000ade8  mov     rcx, [rbp+ppunkMarshal]
0x18000adec  test    rcx, rcx
0x18000adef  jz      loc_18000AD56
0x18000adf5  mov     [rbp+ppunkMarshal], 0
0x18000adfd  mov     rax, [rcx]
0x18000ae00  mov     rax, [rax+10h]
0x18000ae04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae09  jmp     loc_18000AD56
```
