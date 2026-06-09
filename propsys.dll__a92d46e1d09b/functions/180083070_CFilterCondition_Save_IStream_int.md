# CFilterCondition::Save(IStream *,int)

- ea: `0x180083070`
- end: `0x180083290`
- name: `?Save@CFilterCondition@@UEAAJPEAUIStream@@H@Z`
- size: `544`
- prototype: `int(CFilterCondition *__hidden this, struct IStream *, int)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x180016b30`
- `0x180048880`
- `0x1800559e0`
- `0x180058e80`
- `0x180059060`
- `0x18005c730`
- `0x18006ed20`
- `0x18007f4bc`
- `0x1800828bc`
- `0x180083070`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x18008313c`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800831b3`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x18008313c`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800831b3`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1800831d2`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1800831d2`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x180083163`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x180083214`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x180083163`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x180083214`

## pseudocode

```c
__int64 __fastcall CFilterCondition::Save(CFilterCondition *this, struct IStream *a2, int a3)
{
  HRESULT v6; // ebx
  OLECHAR *v7; // r8
  struct IStream *v8; // rax
  const struct _GUID *const *v9; // rdx
  unsigned int v10; // r8d
  IStream *v11; // rsi
  unsigned int *v12; // rax
  IStream *v13; // rax
  struct IStream *v14; // rsi
  unsigned int v15; // r14d
  struct IUnknown *Ptr; // rax
  void *ppv; // [rsp+20h] [rbp-20h] BYREF
  unsigned int pv; // [rsp+28h] [rbp-18h] BYREF

  ppv = 0;
  v6 = PSCreateMemoryPropertyStore(&GUID_55272a00_42cb_11ce_8135_00aa004bb851, &ppv);
  if ( v6 >= 0 )
  {
    v6 = PSPropertyBag_WriteBSTR((IPropertyBag *)ppv, L"Name", *((BSTR *)this + 3));
    if ( v6 < 0 )
      goto LABEL_24;
    v7 = (OLECHAR *)*((_QWORD *)this + 4);
    if ( v7 )
    {
      v6 = PSPropertyBag_WriteBSTR((IPropertyBag *)ppv, L"InFolder", v7);
      if ( v6 < 0 )
        goto LABEL_24;
    }
    v6 = PSPropertyBag_WritePropertyKey((IPropertyBag *)ppv, L"Key", (const PROPERTYKEY *const)this + 2);
    if ( v6 < 0 )
      goto LABEL_24;
    v6 = PSPropertyBag_WriteDWORD((IPropertyBag *)ppv, L"Type", *((_DWORD *)this + 15));
    if ( v6 < 0 )
      goto LABEL_24;
    v8 = SHCreateMemStream(0, 0);
    v11 = v8;
    if ( !v8 )
      goto LABEL_23;
    v6 = IUnknown_SaveKnownImplToStream(v8, v9, v10, *((struct IUnknown **)this + 8));
    if ( v6 >= 0 )
    {
      IStream_Reset(v11);
      v6 = PSPropertyBag_WriteUnknown((IPropertyBag *)ppv, L"Condition", (IUnknown *)v11);
    }
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)v11 + 16LL))(v11);
    if ( v6 < 0 )
      goto LABEL_24;
    v12 = (unsigned int *)*((_QWORD *)this + 9);
    if ( v12 )
    {
      pv = *v12;
      if ( pv )
      {
        v13 = SHCreateMemStream(0, 0);
        v14 = v13;
        if ( v13 )
        {
          v15 = 0;
          v6 = IStream_Write(v13, &pv, 4u);
          if ( pv )
          {
            while ( v6 >= 0 )
            {
              Ptr = (struct IUnknown *)g_pfn_DPA_GetPtr(*((HDPA *)this + 9), v15++);
              v6 = IUnknown_SaveToStream(v14, a3, Ptr);
              if ( v15 >= pv )
                goto LABEL_17;
            }
          }
          else
          {
LABEL_17:
            if ( v6 >= 0 )
            {
              IStream_Reset(v14);
              v6 = PSPropertyBag_WriteUnknown((IPropertyBag *)ppv, L"Filters", (IUnknown *)v14);
            }
          }
          (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v14 + 16LL))(v14);
          if ( v6 < 0 )
            goto LABEL_24;
          goto LABEL_22;
        }
LABEL_23:
        v6 = -2147024882;
        goto LABEL_24;
      }
    }
    else
    {
      pv = 0;
    }
LABEL_22:
    v6 = IUnknown_SaveToStream(a2, a3, (struct IUnknown *)ppv);
LABEL_24:
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180083070  push    rbp
0x180083072  push    rbx
0x180083073  push    rsi
0x180083074  push    rdi
0x180083075  push    r12
0x180083077  push    r14
0x180083079  push    r15
0x18008307b  mov     rbp, rsp
0x18008307e  sub     rsp, 40h
0x180083082  mov     rax, cs:__security_cookie
0x180083089  xor     rax, rsp
0x18008308c  mov     [rbp+var_10], rax
0x180083090  mov     r12, rdx
0x180083093  mov     [rbp+ppv], 0
0x18008309b  mov     rdi, rcx
0x18008309e  lea     rdx, [rbp+ppv]; ppv
0x1800830a2  lea     rcx, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x1800830a9  mov     r15d, r8d
0x1800830ac  call    PSCreateMemoryPropertyStore
0x1800830b1  mov     ebx, eax
0x1800830b3  test    eax, eax
0x1800830b5  js      loc_180083273
0x1800830bb  mov     r8, [rdi+18h]; value
0x1800830bf  lea     rdx, propName; "Name"
0x1800830c6  mov     rcx, [rbp+ppv]; propBag
0x1800830ca  call    PSPropertyBag_WriteBSTR
0x1800830cf  mov     ebx, eax
0x1800830d1  test    eax, eax
0x1800830d3  js      loc_180083263
0x1800830d9  mov     r8, [rdi+20h]; value
0x1800830dd  test    r8, r8
0x1800830e0  jz      short loc_1800830FC
0x1800830e2  mov     rcx, [rbp+ppv]; propBag
0x1800830e6  lea     rdx, aInfolder; "InFolder"
0x1800830ed  call    PSPropertyBag_WriteBSTR
0x1800830f2  mov     ebx, eax
0x1800830f4  test    eax, eax
0x1800830f6  js      loc_180083263
0x1800830fc  mov     rcx, [rbp+ppv]; propBag
0x180083100  lea     r8, [rdi+28h]; value
0x180083104  lea     rdx, aKey; "Key"
0x18008310b  call    PSPropertyBag_WritePropertyKey
0x180083110  mov     ebx, eax
0x180083112  test    eax, eax
0x180083114  js      loc_180083263
0x18008311a  mov     r8d, [rdi+3Ch]; value
0x18008311e  lea     rdx, aType_0; "Type"
0x180083125  mov     rcx, [rbp+ppv]; propBag
0x180083129  call    PSPropertyBag_WriteDWORD
0x18008312e  mov     ebx, eax
0x180083130  test    eax, eax
0x180083132  js      loc_180083263
0x180083138  xor     edx, edx; cbInit
0x18008313a  xor     ecx, ecx; pInit
0x18008313c  call    cs:__imp_SHCreateMemStream
0x180083142  mov     rsi, rax
0x180083145  test    rax, rax
0x180083148  jz      loc_18008325E
0x18008314e  mov     r9, [rdi+40h]; struct IUnknown *
0x180083152  mov     rcx, rax; pstm
0x180083155  call    ?IUnknown_SaveKnownImplToStream@@YAJPEAUIStream@@PEBQEBU_GUID@@IPEAUIUnknown@@@Z; IUnknown_SaveKnownImplToStream(IStream *,_GUID const * const *,uint,IUnknown *)
0x18008315a  mov     ebx, eax
0x18008315c  test    eax, eax
0x18008315e  js      short loc_18008317E
0x180083160  mov     rcx, rsi; pstm
0x180083163  call    cs:__imp_IStream_Reset
0x180083169  mov     rcx, [rbp+ppv]; propBag
0x18008316d  lea     rdx, aCondition; "Condition"
0x180083174  mov     r8, rsi; punk
0x180083177  call    PSPropertyBag_WriteUnknown
0x18008317c  mov     ebx, eax
0x18008317e  mov     rax, [rsi]
0x180083181  mov     rcx, rsi
0x180083184  mov     rax, [rax+10h]
0x180083188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008318d  test    ebx, ebx
0x18008318f  js      loc_180083263
0x180083195  mov     rax, [rdi+48h]
0x180083199  test    rax, rax
0x18008319c  jz      loc_180083244
0x1800831a2  mov     eax, [rax]
0x1800831a4  mov     [rbp+pv], eax
0x1800831a7  test    eax, eax
0x1800831a9  jz      loc_18008324B
0x1800831af  xor     edx, edx; cbInit
0x1800831b1  xor     ecx, ecx; pInit
0x1800831b3  call    cs:__imp_SHCreateMemStream
0x1800831b9  mov     rsi, rax
0x1800831bc  test    rax, rax
0x1800831bf  jz      loc_18008325E
0x1800831c5  mov     r8d, 4; cb
0x1800831cb  lea     rdx, [rbp+pv]; pv
0x1800831cf  mov     rcx, rax; pstm
0x1800831d2  call    cs:__imp_IStream_Write
0x1800831d8  xor     r14d, r14d
0x1800831db  mov     ebx, eax
0x1800831dd  cmp     [rbp+pv], r14d
0x1800831e1  jbe     short loc_18008320D
0x1800831e3  test    ebx, ebx
0x1800831e5  js      short loc_18008322F
0x1800831e7  mov     rcx, [rdi+48h]; hdpa
0x1800831eb  mov     edx, r14d; i
0x1800831ee  call    cs:g_pfn_DPA_GetPtr
0x1800831f4  mov     edx, r15d; int
0x1800831f7  mov     rcx, rsi; struct IStream *
0x1800831fa  mov     r8, rax; struct IUnknown *
0x1800831fd  call    ?IUnknown_SaveToStream@@YAJPEAUIStream@@HPEAUIUnknown@@@Z; IUnknown_SaveToStream(IStream *,int,IUnknown *)
0x180083202  inc     r14d
0x180083205  mov     ebx, eax
0x180083207  cmp     r14d, [rbp+pv]
0x18008320b  jb      short loc_1800831E3
0x18008320d  test    ebx, ebx
0x18008320f  js      short loc_18008322F
0x180083211  mov     rcx, rsi; pstm
0x180083214  call    cs:__imp_IStream_Reset
0x18008321a  mov     rcx, [rbp+ppv]; propBag
0x18008321e  lea     rdx, aFilters; "Filters"
0x180083225  mov     r8, rsi; punk
0x180083228  call    PSPropertyBag_WriteUnknown
0x18008322d  mov     ebx, eax
0x18008322f  mov     rax, [rsi]
0x180083232  mov     rcx, rsi
0x180083235  mov     rax, [rax+10h]
0x180083239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008323e  test    ebx, ebx
0x180083240  jns     short loc_18008324B
0x180083242  jmp     short loc_180083263
0x180083244  mov     [rbp+pv], 0
0x18008324b  mov     r8, [rbp+ppv]; struct IUnknown *
0x18008324f  mov     edx, r15d; int
0x180083252  mov     rcx, r12; struct IStream *
0x180083255  call    ?IUnknown_SaveToStream@@YAJPEAUIStream@@HPEAUIUnknown@@@Z; IUnknown_SaveToStream(IStream *,int,IUnknown *)
0x18008325a  mov     ebx, eax
0x18008325c  jmp     short loc_180083263
0x18008325e  mov     ebx, 8007000Eh
0x180083263  mov     rcx, [rbp+ppv]
0x180083267  mov     rax, [rcx]
0x18008326a  mov     rax, [rax+10h]
0x18008326e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083273  mov     eax, ebx
0x180083275  mov     rcx, [rbp+var_10]
0x180083279  xor     rcx, rsp; StackCookie
0x18008327c  call    __security_check_cookie
0x180083281  add     rsp, 40h
0x180083285  pop     r15
0x180083287  pop     r14
0x180083289  pop     r12
0x18008328b  pop     rdi
0x18008328c  pop     rsi
0x18008328d  pop     rbx
0x18008328e  pop     rbp
0x18008328f  retn
```
