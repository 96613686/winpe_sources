# CComponentData::QueryDataObject(__int64,_DATA_OBJECT_TYPES,IDataObject * *)

- ea: `0x180006930`
- end: `0x1800069b9`
- name: `?QueryDataObject@CComponentData@@UEAAJ_JW4_DATA_OBJECT_TYPES@@PEAPEAUIDataObject@@@Z`
- size: `137`
- prototype: `__int64 __fastcall(CComponentData *__hidden this, __int64, enum _DATA_OBJECT_TYPES, struct IDataObject **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002928`
- `0x180006930`
- `0x1800094d4`

## pseudocode

```c
__int64 __fastcall CComponentData::QueryDataObject(
        CComponentData *this,
        __int64 a2,
        enum _DATA_OBJECT_TYPES a3,
        struct IDataObject **a4)
{
  CDataObject *v8; // rax
  CDataObject *v9; // rax
  unsigned int v10; // edx

  v8 = (CDataObject *)operator new(0x28u);
  if ( !v8 )
  {
    *a4 = 0;
    return (unsigned int)-2147024882;
  }
  v9 = CDataObject::CDataObject(v8);
  *a4 = (struct IDataObject *)v9;
  if ( !v9 )
    return (unsigned int)-2147024882;
  v10 = 0;
  if ( (unsigned __int64)(a2 + 1) <= 1 )
  {
    *((_QWORD *)v9 + 2) = 0;
    *((_DWORD *)v9 + 7) = 0;
    *((_DWORD *)v9 + 6) = a3;
  }
  else
  {
    *((_QWORD *)v9 + 2) = a2;
    *((_DWORD *)v9 + 7) = 1;
    *((_DWORD *)v9 + 6) = 0x8000;
    _InterlockedIncrement((volatile signed __int32 *)(a2 + 4760));
  }
  *((_QWORD *)v9 + 4) = (char *)this - 8;
  return v10;
}

```

## disassembly

```asm
0x180006930  push    rbx
0x180006932  push    rbp
0x180006933  push    rsi
0x180006934  push    rdi
0x180006935  sub     rsp, 28h
0x180006939  mov     rbp, rcx
0x18000693c  mov     rdi, r9
0x18000693f  mov     ecx, 28h ; '('; Size
0x180006944  mov     esi, r8d
0x180006947  mov     rbx, rdx
0x18000694a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000694f  test    rax, rax
0x180006952  jz      short loc_1800069A2
0x180006954  mov     rcx, rax; this
0x180006957  call    ??0CDataObject@@QEAA@XZ; CDataObject::CDataObject(void)
0x18000695c  mov     [rdi], rax
0x18000695f  mov     r10, rax
0x180006962  test    rax, rax
0x180006965  jz      short loc_1800069A9
0x180006967  xor     edx, edx
0x180006969  lea     rcx, [rbx+1]
0x18000696d  cmp     rcx, 1
0x180006971  jbe     short loc_18000698E
0x180006973  mov     [rax+10h], rbx
0x180006977  mov     dword ptr [rax+1Ch], 1
0x18000697e  mov     dword ptr [rax+18h], 8000h
0x180006985  lock inc dword ptr [rbx+1298h]
0x18000698c  jmp     short loc_180006998
0x18000698e  mov     [rax+10h], rdx
0x180006992  mov     [rax+1Ch], edx
0x180006995  mov     [rax+18h], esi
0x180006998  lea     rax, [rbp-8]
0x18000699c  mov     [r10+20h], rax
0x1800069a0  jmp     short loc_1800069AE
0x1800069a2  mov     qword ptr [rdi], 0
0x1800069a9  mov     edx, 8007000Eh
0x1800069ae  mov     eax, edx
0x1800069b0  add     rsp, 28h
0x1800069b4  pop     rdi
0x1800069b5  pop     rsi
0x1800069b6  pop     rbp
0x1800069b7  pop     rbx
0x1800069b8  retn
```
