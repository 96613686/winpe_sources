# CKsOutputPin2::SetPluginMediaType(KSDATAFORMAT *,int)

- ea: `0x180031844`
- end: `0x180031a20`
- name: `?SetPluginMediaType@CKsOutputPin2@@QEAAJPEATKSDATAFORMAT@@H@Z`
- size: `476`
- prototype: `__int64 __fastcall(CKsOutputPin2 *this, union KSDATAFORMAT *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x180031360`
- `0x1800315e0`

## callees

- `0x180030188`
- `0x180031844`
- `0x180044844`
- `0x180044850`
- `0x180045010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180031872`
- `ole32!CoTaskMemAlloc` at `0x180031872`
- `ole32!CoTaskMemFree` at `0x18003194e`
- `ole32!CoTaskMemFree` at `0x180031971`
- `ole32!CoTaskMemFree` at `0x1800319e2`
- `ole32!CoTaskMemFree` at `0x1800319fe`
- `ole32!CoTaskMemFree` at `0x18003194e`
- `ole32!CoTaskMemFree` at `0x180031971`
- `ole32!CoTaskMemFree` at `0x1800319e2`
- `ole32!CoTaskMemFree` at `0x1800319fe`

## pseudocode

```c
__int64 __fastcall CKsOutputPin2::SetPluginMediaType(CKsOutputPin2 *this, union KSDATAFORMAT *a2, int a3)
{
  SIZE_T FormatSize; // rcx
  void *v7; // rax
  void *v8; // rbp
  int v9; // ebx
  union KSDATAFORMAT *v10; // rsi
  unsigned int v11; // ebx
  void *v12; // rax
  void *v13; // rcx
  void *v14; // rcx
  LONGLONG v15; // rax
  LPVOID pv; // [rsp+48h] [rbp+10h] BYREF
  union KSDATAFORMAT *v18; // [rsp+58h] [rbp+20h] BYREF

  pv = 0;
  FormatSize = a2->FormatSize;
  v18 = 0;
  v7 = CoTaskMemAlloc(FormatSize);
  v8 = v7;
  if ( !v7 )
  {
    v9 = -2147467259;
    goto LABEL_20;
  }
  memcpy_0(v7, a2, a2->FormatSize);
  v9 = (*(__int64 (__fastcall **)(_QWORD, void *))(**((_QWORD **)this + 141) + 56LL))(*((_QWORD *)this + 141), v8);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(**((_QWORD **)this + 141) + 72LL))(*((_QWORD *)this + 141), &pv);
    if ( v9 >= 0 )
    {
      v10 = (union KSDATAFORMAT *)pv;
      if ( !pv )
      {
        v9 = -2147467259;
LABEL_23:
        CoTaskMemFree(v8);
        return (unsigned int)v9;
      }
      if ( a3 )
      {
        v11 = *((_DWORD *)this + 146);
        v12 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 10) + 168LL) + 24LL))(*((_QWORD *)this + 10) + 168LL);
        v9 = IntersectKsFormat(v12, v11, v10, &v18);
        if ( v9 < 0 )
          goto LABEL_20;
        v10 = v18;
      }
      else
      {
        pv = 0;
      }
      v13 = (void *)*((_QWORD *)this + 152);
      if ( v13 )
      {
        CoTaskMemFree(v13);
        *((_QWORD *)this + 152) = 0;
      }
      v14 = (void *)*((_QWORD *)this + 151);
      if ( v14 )
        CoTaskMemFree(v14);
      *((_QWORD *)this + 152) = v10;
      *((_QWORD *)this + 151) = v8;
      v15 = *(&v10->Alignment + 2) - *(_QWORD *)&MEDIATYPE_Video.Data1;
      if ( !v15 )
        v15 = *(&v10->Alignment + 3) - *(_QWORD *)MEDIATYPE_Video.Data4;
      if ( v15 )
        *((_DWORD *)this + 289) = memcmp_0(&v10->Alignment + 2, &MEDIATYPE_VBI, 0x10u) == 0 ? 0x58 : 0;
      else
        *((_DWORD *)this + 289) = 72;
    }
  }
LABEL_20:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v9 < 0 )
    goto LABEL_23;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180031844  mov     rax, rsp
0x180031847  mov     [rax+8], rbx
0x18003184b  mov     [rax+18h], rbp
0x18003184f  push    rsi
0x180031850  push    rdi
0x180031851  push    r14
0x180031853  sub     rsp, 20h
0x180031857  mov     rdi, rcx
0x18003185a  mov     qword ptr [rax+10h], 0
0x180031862  mov     ecx, [rdx]; cb
0x180031864  mov     r14d, r8d
0x180031867  mov     rbx, rdx
0x18003186a  mov     qword ptr [rax+20h], 0
0x180031872  call    cs:__imp_CoTaskMemAlloc
0x180031879  nop     dword ptr [rax+rax+00h]
0x18003187e  mov     rbp, rax
0x180031881  test    rax, rax
0x180031884  jnz     short loc_180031890
0x180031886  mov     ebx, 80004005h
0x18003188b  jmp     loc_1800319D8
0x180031890  mov     r8d, [rbx]; Size
0x180031893  mov     rdx, rbx; Src
0x180031896  mov     rcx, rbp; void *
0x180031899  call    memcpy_0
0x18003189e  mov     rcx, [rdi+468h]
0x1800318a5  mov     rdx, rbp
0x1800318a8  mov     rax, [rcx]
0x1800318ab  mov     rax, [rax+38h]
0x1800318af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800318b4  mov     ebx, eax
0x1800318b6  test    eax, eax
0x1800318b8  js      loc_1800319D8
0x1800318be  mov     rcx, [rdi+468h]
0x1800318c5  lea     rdx, [rsp+38h+pv]
0x1800318ca  mov     rax, [rcx]
0x1800318cd  mov     rax, [rax+48h]
0x1800318d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800318d6  mov     ebx, eax
0x1800318d8  test    eax, eax
0x1800318da  js      loc_1800319D8
0x1800318e0  mov     rsi, [rsp+38h+pv]
0x1800318e5  test    rsi, rsi
0x1800318e8  jnz     short loc_1800318F4
0x1800318ea  mov     ebx, 80004005h
0x1800318ef  jmp     loc_1800319FB
0x1800318f4  test    r14d, r14d
0x1800318f7  jz      short loc_180031939
0x1800318f9  mov     rcx, [rdi+50h]
0x1800318fd  mov     ebx, [rdi+248h]
0x180031903  add     rcx, 0A8h
0x18003190a  mov     rax, [rcx]
0x18003190d  mov     rax, [rax+18h]
0x180031911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031916  lea     r9, [rsp+38h+arg_18]; union KSDATAFORMAT **
0x18003191b  mov     r8, rsi; union KSDATAFORMAT *
0x18003191e  mov     edx, ebx; unsigned int
0x180031920  mov     rcx, rax; hFile
0x180031923  call    ?IntersectKsFormat@@YAJPEAXKPEATKSDATAFORMAT@@PEAPEAT1@@Z; IntersectKsFormat(void *,ulong,KSDATAFORMAT *,KSDATAFORMAT * *)
0x180031928  mov     ebx, eax
0x18003192a  test    eax, eax
0x18003192c  js      loc_1800319D8
0x180031932  mov     rsi, [rsp+38h+arg_18]
0x180031937  jmp     short loc_180031942
0x180031939  mov     [rsp+38h+pv], 0
0x180031942  mov     rcx, [rdi+4C0h]; pv
0x180031949  test    rcx, rcx
0x18003194c  jz      short loc_180031965
0x18003194e  call    cs:__imp_CoTaskMemFree
0x180031955  nop     dword ptr [rax+rax+00h]
0x18003195a  mov     qword ptr [rdi+4C0h], 0
0x180031965  mov     rcx, [rdi+4B8h]; pv
0x18003196c  test    rcx, rcx
0x18003196f  jz      short loc_18003197D
0x180031971  call    cs:__imp_CoTaskMemFree
0x180031978  nop     dword ptr [rax+rax+00h]
0x18003197d  mov     [rdi+4C0h], rsi
0x180031984  lea     rcx, [rsi+10h]; Buf1
0x180031988  mov     [rdi+4B8h], rbp
0x18003198f  mov     rax, [rcx]
0x180031992  sub     rax, qword ptr cs:MEDIATYPE_Video.Data1
0x180031999  jnz     short loc_1800319A6
0x18003199b  mov     rax, [rcx+8]
0x18003199f  sub     rax, qword ptr cs:MEDIATYPE_Video.Data4
0x1800319a6  test    rax, rax
0x1800319a9  jnz     short loc_1800319B7
0x1800319ab  mov     dword ptr [rdi+484h], 48h ; 'H'
0x1800319b5  jmp     short loc_1800319D8
0x1800319b7  mov     r8d, 10h; Size
0x1800319bd  lea     rdx, MEDIATYPE_VBI; Buf2
0x1800319c4  call    memcmp_0
0x1800319c9  neg     eax
0x1800319cb  sbb     ecx, ecx
0x1800319cd  not     ecx
0x1800319cf  and     ecx, 58h
0x1800319d2  mov     [rdi+484h], ecx
0x1800319d8  mov     rcx, [rsp+38h+pv]; pv
0x1800319dd  test    rcx, rcx
0x1800319e0  jz      short loc_1800319F7
0x1800319e2  call    cs:__imp_CoTaskMemFree
0x1800319e9  nop     dword ptr [rax+rax+00h]
0x1800319ee  mov     [rsp+38h+pv], 0
0x1800319f7  test    ebx, ebx
0x1800319f9  jns     short loc_180031A0A
0x1800319fb  mov     rcx, rbp; pv
0x1800319fe  call    cs:__imp_CoTaskMemFree
0x180031a05  nop     dword ptr [rax+rax+00h]
0x180031a0a  mov     rbp, [rsp+38h+arg_10]
0x180031a0f  mov     eax, ebx
0x180031a11  mov     rbx, [rsp+38h+arg_0]
0x180031a16  add     rsp, 20h
0x180031a1a  pop     r14
0x180031a1c  pop     rdi
0x180031a1d  pop     rsi
0x180031a1e  retn
```
