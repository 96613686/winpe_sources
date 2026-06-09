# Projection::ArrayProjection::CreateArrayProjectionObject(ProjectionModel::ConcreteType const *,Projection::ProjectionContext *,uchar *,uint,uint,bool,void * *,bool)

- ea: `0x18022c278`
- end: `0x18022c6d0`
- name: `?CreateArrayProjectionObject@ArrayProjection@Projection@@SAJPEBUConcreteType@ProjectionModel@@PEAVProjectionContext@2@PEAEII_NPEAPEAX3@Z`
- size: `1112`
- prototype: `__int64 __usercall@<rax>(const struct ProjectionModel::ConcreteType *@<rcx>, struct Projection::ProjectionContext *@<rdx>, unsigned __int8 *@<r8>, unsigned int@<r9d>, unsigned int, bool, void **, bool)`
- caller_count: `2`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801be2bc`
- `0x180245254`

## callees

- `0x18000463c`
- `0x1800194d0`
- `0x1801c989b`
- `0x1801e30c0`
- `0x18022c134`
- `0x18022c278`
- `0x18022c6d8`
- `0x18022c7e0`
- `0x18022c8b4`
- `0x18022cca8`
- `0x18022d950`
- `0x18022dc48`
- `0x180246790`
- `0x1802b39b0`
- `0x180330cc4`
- `0x18035e010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18022c3e2`
- `msvcrt!memcpy_s` at `0x18022c528`
- `msvcrt!memcpy_s` at `0x18022c3e2`
- `msvcrt!memcpy_s` at `0x18022c528`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x18022c4da`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x18022c4da`

## pseudocode

```c
__int64 __fastcall Projection::ArrayProjection::CreateArrayProjectionObject(
        const struct ProjectionModel::ConcreteType *a1,
        struct Projection::ProjectionContext *a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned int a5,
        bool a6,
        void **a7,
        bool a8)
{
  Projection *v9; // r12
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  __int64 (__fastcall *v16)(struct Js::ArrayBuffer *); // rbx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  __int64 v21; // r15
  unsigned int v22; // edi
  struct Js::ArrayBuffer *ProjectionArraybuffer; // r13
  char *v24; // r14
  char *v25; // rcx
  size_t v26; // r8
  struct Js::ProjectionArrayBuffer *v27; // rax
  __int64 v28; // rcx
  __int64 result; // rax
  __int64 v30; // r15
  unsigned int v31; // edi
  unsigned __int8 *v32; // rax
  unsigned __int8 *v33; // rsi
  size_t v34; // r8
  unsigned __int8 *v35; // rcx
  unsigned int i; // r12d
  struct Js::ScriptContext *v37; // rdx
  int v38; // r8d
  struct Projection::ArrayObjectInstance *v39; // rbx
  const unsigned __int16 *v40; // rax
  __int64 v41; // rcx
  void *v42; // rax
  struct Js::RecyclableObject *v43; // r8
  struct Projection::ArrayObjectInstance *v44; // [rsp+40h] [rbp-68h] BYREF
  struct Projection::ArrayProjection *v45; // [rsp+48h] [rbp-60h] BYREF
  void *v46; // [rsp+50h] [rbp-58h] BYREF
  Projection *v47; // [rsp+58h] [rbp-50h]
  __int64 v48; // [rsp+60h] [rbp-48h]
  _QWORD *v49; // [rsp+68h] [rbp-40h] BYREF

  v48 = -2;
  v45 = 0;
  v9 = (Projection *)*((_QWORD *)a2 + 14);
  v47 = v9;
  if ( *(_DWORD *)a1 != 15 )
    goto LABEL_38;
  v46 = *(void **)v9;
  v11 = *((_DWORD *)ProjectionModel::BasicType::From(a1) + 10);
  if ( v11 > 8 )
  {
    v17 = v11 - 9;
    if ( v17 )
    {
      v18 = v17 - 1;
      if ( v18 )
      {
        v19 = v18 - 1;
        if ( v19 )
        {
          v20 = v19 - 1;
          if ( v20 )
          {
            if ( v20 != 1 )
              goto LABEL_38;
            v16 = (__int64 (__fastcall *)(struct Js::ArrayBuffer *))Js::TypedArray<double,0>::Create;
          }
          else
          {
            v16 = (__int64 (__fastcall *)(struct Js::ArrayBuffer *))Js::TypedArray<float,0>::Create;
          }
        }
        else
        {
          v16 = (__int64 (__fastcall *)(struct Js::ArrayBuffer *))Js::TypedArray<unsigned __int64,0>::Create;
        }
      }
      else
      {
        v16 = (__int64 (__fastcall *)(struct Js::ArrayBuffer *))Js::TypedArray<__int64,0>::Create;
      }
    }
    else
    {
      v16 = (__int64 (__fastcall *)(struct Js::ArrayBuffer *))Js::TypedArray<unsigned int,0>::Create;
    }
LABEL_25:
    LODWORD(v44) = 0;
    v21 = *((_QWORD *)a1 + 3);
    v22 = a4 * v21;
    if ( a6 )
    {
      if ( a4 > a5 )
        memset_0(&a3[v21 * a5], 0, v21 * (a4 - a5));
      v27 = Js::ProjectionArrayBuffer::Create(a3, v22, *(struct Js::DynamicType **)(*(_QWORD *)v9 + 1144LL));
      ProjectionArraybuffer = v27;
      if ( (Microsoft_JScriptEnableBits & 0x800) != 0 )
        McTemplateU0p_EventWriteTransfer(v28, L"l", v27);
      goto LABEL_71;
    }
    ProjectionArraybuffer = Js::JavascriptLibrary::CreateProjectionArraybuffer(*(Js::JavascriptLibrary **)v9, v22);
    v24 = (char *)*((_QWORD *)ProjectionArraybuffer + 7);
    if ( !v22 || v24 )
    {
      v25 = (char *)*((_QWORD *)ProjectionArraybuffer + 7);
      if ( a8 )
      {
        memcpy_s(v24, v22, a3, v21 * a5);
        if ( a4 <= a5 )
        {
LABEL_71:
          try
          {
            *a7 = (void *)((__int64 (__fastcall *)(struct Js::ArrayBuffer *, _QWORD, _QWORD, void *))v16)(
                            ProjectionArraybuffer,
                            0,
                            a4,
                            v46);
          }
          catch ( Js::InternalErrorException )
          {
            LODWORD(v44) = -2147467259;
            return (unsigned int)v44;
          }
          catch ( Js::OutOfMemoryException )
          {
            LODWORD(v44) = -2147024882;
            return (unsigned int)v44;
          }
          catch ( Js::StackOverflowException )
          {
            LODWORD(v44) = -2146828260;
            return (unsigned int)v44;
          }
          catch ( Js::NotImplementedException )
          {
            LODWORD(v44) = -2147467263;
            return (unsigned int)v44;
          }
          catch ( Js::ScriptAbortException )
          {
            LODWORD(v44) = -2147467260;
            return (unsigned int)v44;
          }
          catch ( Js::JavascriptExceptionObject *v49 )
          {
            if ( *v49
              && ((unsigned int)Js::JavascriptOperators::GetTypeId(*v49) == 23
               || (unsigned int)Js::JavascriptOperators::GetTypeId(v43) == 11) )
            {
              LODWORD(v44) = Js::JavascriptError::GetRuntimeError(v43, 0);
            }
            else
            {
              LODWORD(v44) = -2147024882;
            }
            return (unsigned int)v44;
          }
          catch ( ... )
          {
            LODWORD(v44) = -2147467259;
          }
          return (unsigned int)v44;
        }
        v26 = v21 * (a4 - a5);
        v25 = &v24[v21 * a5];
      }
      else
      {
        v26 = v22;
      }
      memset_0(v25, 0, v26);
      goto LABEL_71;
    }
    return 2147942414LL;
  }
  if ( v11 == 8 )
  {
    v16 = (__int64 (__fastcall *)(struct Js::ArrayBuffer *))Js::TypedArray<int,0>::Create;
    goto LABEL_25;
  }
  v12 = v11 - 2;
  if ( !v12 )
  {
    v16 = (__int64 (__fastcall *)(struct Js::ArrayBuffer *))Js::TypedArray<bool,0>::Create;
    goto LABEL_25;
  }
  v13 = v12 - 1;
  if ( !v13 )
  {
    v16 = (__int64 (__fastcall *)(struct Js::ArrayBuffer *))Js::CharArray::Create;
    goto LABEL_25;
  }
  v14 = v13 - 2;
  if ( !v14 )
  {
    v16 = Js::TypedArray<unsigned char,0>::Create;
    goto LABEL_25;
  }
  v15 = v14 - 1;
  if ( !v15 )
  {
    v16 = (__int64 (__fastcall *)(struct Js::ArrayBuffer *))Js::TypedArray<short,0>::Create;
    goto LABEL_25;
  }
  if ( v15 == 1 )
  {
    v16 = (__int64 (__fastcall *)(struct Js::ArrayBuffer *))Js::TypedArray<unsigned short,0>::Create;
    goto LABEL_25;
  }
LABEL_38:
  result = Projection::ArrayProjection::EnsureProjection(a1, a2, &v45);
  if ( (int)result < 0 )
    return result;
  v30 = *((_QWORD *)a1 + 3);
  if ( a6 )
  {
    v31 = a4;
    v33 = a3;
    if ( a4 > a5 )
      memset_0(&a3[v30 * a5], 0, v30 * (a4 - a5));
    goto LABEL_54;
  }
  v31 = a4;
  v32 = (unsigned __int8 *)CoTaskMemAlloc(v30 * a4);
  v33 = v32;
  if ( !v32 )
    return 2147942414LL;
  if ( a8 )
  {
    if ( ProjectionModel::ConcreteType::IsBlittable(a1) )
    {
      memcpy_s(v33, v30 * a4, a3, v30 * a5);
      v34 = v30 * (a4 - a5);
      v35 = &v33[v30 * a5];
    }
    else
    {
      for ( i = 0; i < a5; ++i )
      {
        v46 = 0;
        Projection::ArrayObjectInstance::GetItemAt(a3, a4, a2, a1, i, *((_DWORD *)v45 + 10), &v46, (int *)&v44);
        Projection::ArrayObjectInstance::SetItemAt(v33, a4, a2, a1, i, v46, 0, (int *)&v44);
      }
      if ( a4 <= a5 )
        goto LABEL_51;
      v34 = v30 * (a4 - a5);
      v35 = &v33[v30 * a5];
    }
  }
  else
  {
    v34 = v30 * a4;
    v35 = v32;
  }
  memset_0(v35, 0, v34);
LABEL_51:
  v9 = v47;
LABEL_54:
  v44 = 0;
  result = Projection::ArrayObjectInstance::Create(*((void **)v45 + 4), *((_DWORD *)v45 + 10), a1, v33, v31, a2, &v44);
  if ( (int)result >= 0 )
  {
    v39 = v44;
    if ( (Microsoft_JScriptEnableBits & 0x4000) != 0 )
    {
      v40 = Projection::StringOfId(v9, (struct Js::ScriptContext *)*(unsigned int *)(*((_QWORD *)v44 + 1) + 64LL), v38);
      McTemplateU0pz_EventWriteTransfer(v41, &JSCRIPT_RECYCLER_ALLOCATE_WINRT_TYPEDARRAY_OBJECT, v39, v40);
    }
    v42 = Js::JavascriptNumber::ToVar(v31, v37);
    Js::CustomExternalObject::SetPropertyWithAttributes(v39, 120, v42, 0, 0, 0, 0);
    *a7 = v39;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18022c278  mov     rax, rsp
0x18022c27b  mov     [rax+20h], r9d
0x18022c27f  mov     [rax+18h], r8
0x18022c283  mov     [rax+10h], rdx
0x18022c287  mov     [rax+8], rcx
0x18022c28b  push    rbx
0x18022c28c  push    rsi
0x18022c28d  push    rdi
0x18022c28e  push    r12
0x18022c290  push    r13
0x18022c292  push    r14
0x18022c294  push    r15
0x18022c296  sub     rsp, 70h
0x18022c29a  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x18022c2a2  mov     qword ptr [rax-60h], 0
0x18022c2aa  mov     r13, rdx
0x18022c2ad  mov     r12, [rdx+70h]
0x18022c2b1  mov     [rsp+0A8h+var_50], r12
0x18022c2b6  mov     r14, rcx
0x18022c2b9  cmp     dword ptr [rcx], 0Fh
0x18022c2bc  jnz     loc_18022C49F
0x18022c2c2  mov     rax, [r12]
0x18022c2c6  mov     [rsp+0A8h+var_58], rax
0x18022c2cb  call    ?From@BasicType@ProjectionModel@@SAPEBUImpl@12@PEBUType@2@@Z; ProjectionModel::BasicType::From(ProjectionModel::Type const *)
0x18022c2d0  mov     ecx, [rax+28h]
0x18022c2d3  cmp     ecx, 8
0x18022c2d6  jg      short loc_18022C32D
0x18022c2d8  jz      short loc_18022C324
0x18022c2da  sub     ecx, 2
0x18022c2dd  jz      short loc_18022C31B
0x18022c2df  sub     ecx, 1
0x18022c2e2  jz      short loc_18022C312
0x18022c2e4  sub     ecx, 2
0x18022c2e7  jz      short loc_18022C309
0x18022c2e9  sub     ecx, 1
0x18022c2ec  jz      short loc_18022C300
0x18022c2ee  cmp     ecx, 1
0x18022c2f1  jnz     loc_18022C49F
0x18022c2f7  lea     rbx, ?Create@?$TypedArray@G$0A@@Js@@SAPEAXPEAVArrayBuffer@2@IIPEAVJavascriptLibrary@2@@Z; Js::TypedArray<ushort,0>::Create(Js::ArrayBuffer *,uint,uint,Js::JavascriptLibrary *)
0x18022c2fe  jmp     short loc_18022C375
0x18022c300  lea     rbx, ?Create@?$TypedArray@F$0A@@Js@@SAPEAXPEAVArrayBuffer@2@IIPEAVJavascriptLibrary@2@@Z; Js::TypedArray<short,0>::Create(Js::ArrayBuffer *,uint,uint,Js::JavascriptLibrary *)
0x18022c307  jmp     short loc_18022C375
0x18022c309  lea     rbx, ?Create@?$TypedArray@E$0A@@Js@@SAPEAXPEAVArrayBuffer@2@IIPEAVJavascriptLibrary@2@@Z; Js::TypedArray<uchar,0>::Create(Js::ArrayBuffer *,uint,uint,Js::JavascriptLibrary *)
0x18022c310  jmp     short loc_18022C375
0x18022c312  lea     rbx, ?Create@CharArray@Js@@SAPEAXPEAVArrayBuffer@2@IIPEAVJavascriptLibrary@2@@Z; Js::CharArray::Create(Js::ArrayBuffer *,uint,uint,Js::JavascriptLibrary *)
0x18022c319  jmp     short loc_18022C375
0x18022c31b  lea     rbx, ?Create@?$TypedArray@_N$0A@@Js@@SAPEAXPEAVArrayBuffer@2@IIPEAVJavascriptLibrary@2@@Z; Js::TypedArray<bool,0>::Create(Js::ArrayBuffer *,uint,uint,Js::JavascriptLibrary *)
0x18022c322  jmp     short loc_18022C375
0x18022c324  lea     rbx, ?Create@?$TypedArray@H$0A@@Js@@SAPEAXPEAVArrayBuffer@2@IIPEAVJavascriptLibrary@2@@Z; Js::TypedArray<int,0>::Create(Js::ArrayBuffer *,uint,uint,Js::JavascriptLibrary *)
0x18022c32b  jmp     short loc_18022C375
0x18022c32d  sub     ecx, 9
0x18022c330  jz      short loc_18022C36E
0x18022c332  sub     ecx, 1
0x18022c335  jz      short loc_18022C365
0x18022c337  sub     ecx, 1
0x18022c33a  jz      short loc_18022C35C
0x18022c33c  sub     ecx, 1
0x18022c33f  jz      short loc_18022C353
0x18022c341  cmp     ecx, 1
0x18022c344  jnz     loc_18022C49F
0x18022c34a  lea     rbx, ?Create@?$TypedArray@N$0A@@Js@@SAPEAXPEAVArrayBuffer@2@IIPEAVJavascriptLibrary@2@@Z; Js::TypedArray<double,0>::Create(Js::ArrayBuffer *,uint,uint,Js::JavascriptLibrary *)
0x18022c351  jmp     short loc_18022C375
0x18022c353  lea     rbx, ?Create@?$TypedArray@M$0A@@Js@@SAPEAXPEAVArrayBuffer@2@IIPEAVJavascriptLibrary@2@@Z; Js::TypedArray<float,0>::Create(Js::ArrayBuffer *,uint,uint,Js::JavascriptLibrary *)
0x18022c35a  jmp     short loc_18022C375
0x18022c35c  lea     rbx, ?Create@?$TypedArray@_K$0A@@Js@@SAPEAXPEAVArrayBuffer@2@IIPEAVJavascriptLibrary@2@@Z; Js::TypedArray<unsigned __int64,0>::Create(Js::ArrayBuffer *,uint,uint,Js::JavascriptLibrary *)
0x18022c363  jmp     short loc_18022C375
0x18022c365  lea     rbx, ?Create@?$TypedArray@_J$0A@@Js@@SAPEAXPEAVArrayBuffer@2@IIPEAVJavascriptLibrary@2@@Z; Js::TypedArray<__int64,0>::Create(Js::ArrayBuffer *,uint,uint,Js::JavascriptLibrary *)
0x18022c36c  jmp     short loc_18022C375
0x18022c36e  lea     rbx, ?Create@?$TypedArray@I$0A@@Js@@SAPEAXPEAVArrayBuffer@2@IIPEAVJavascriptLibrary@2@@Z; Js::TypedArray<uint,0>::Create(Js::ArrayBuffer *,uint,uint,Js::JavascriptLibrary *)
0x18022c375  mov     dword ptr [rsp+0A8h+var_68], 0
0x18022c37d  mov     r15, [r14+18h]
0x18022c381  mov     edi, r15d
0x18022c384  mov     esi, [rsp+0A8h+arg_18]
0x18022c38b  imul    edi, esi
0x18022c38e  cmp     [rsp+0A8h+arg_28], 0
0x18022c396  jnz     short loc_18022C409
0x18022c398  mov     edx, edi; unsigned int
0x18022c39a  mov     rcx, [r12]; this
0x18022c39e  call    ?CreateProjectionArraybuffer@JavascriptLibrary@Js@@QEAAPEAVArrayBuffer@2@I@Z; Js::JavascriptLibrary::CreateProjectionArraybuffer(uint)
0x18022c3a3  mov     r13, rax
0x18022c3a6  mov     r14, [rax+38h]
0x18022c3aa  test    edi, edi
0x18022c3ac  jz      short loc_18022C3B7
0x18022c3ae  test    r14, r14
0x18022c3b1  jz      loc_18022C4E8
0x18022c3b7  mov     eax, edi
0x18022c3b9  mov     rcx, r14; void *
0x18022c3bc  cmp     [rsp+0A8h+arg_38], 0
0x18022c3c4  jz      short loc_18022C3FD
0x18022c3c6  mov     r12d, [rsp+0A8h+arg_20]
0x18022c3ce  mov     edi, r12d
0x18022c3d1  imul    rdi, r15
0x18022c3d5  mov     r9, rdi; SourceSize
0x18022c3d8  mov     r8, [rsp+0A8h+Source]; Source
0x18022c3e0  mov     edx, eax; DestinationSize
0x18022c3e2  call    cs:__imp_memcpy_s
0x18022c3e8  cmp     esi, r12d
0x18022c3eb  jbe     short loc_18022C465
0x18022c3ed  mov     r8d, esi
0x18022c3f0  sub     r8d, r12d
0x18022c3f3  imul    r8, r15
0x18022c3f7  lea     rcx, [rdi+r14]
0x18022c3fb  jmp     short loc_18022C400
0x18022c3fd  mov     r8, rax; Size
0x18022c400  xor     edx, edx; Val
0x18022c402  call    memset_0
0x18022c407  jmp     short loc_18022C465
0x18022c409  mov     ecx, [rsp+0A8h+arg_20]
0x18022c410  mov     r14, [rsp+0A8h+Source]
0x18022c418  cmp     esi, ecx
0x18022c41a  jbe     short loc_18022C434
0x18022c41c  mov     r8d, esi
0x18022c41f  sub     r8d, ecx
0x18022c422  imul    r8, r15; Size
0x18022c426  imul    rcx, r15
0x18022c42a  add     rcx, r14; void *
0x18022c42d  xor     edx, edx; Val
0x18022c42f  call    memset_0
0x18022c434  mov     r8, [r12]
0x18022c438  mov     r8, [r8+478h]; struct Js::DynamicType *
0x18022c43f  mov     edx, edi; unsigned int
0x18022c441  mov     rcx, r14; unsigned __int8 *
0x18022c444  call    ?Create@ProjectionArrayBuffer@Js@@SAPEAV12@PEAEIPEAVDynamicType@2@@Z; Js::ProjectionArrayBuffer::Create(uchar *,uint,Js::DynamicType *)
0x18022c449  mov     r13, rax
0x18022c44c  test    byte ptr cs:Microsoft_JScriptEnableBits+1, 8
0x18022c453  jz      short loc_18022C465
0x18022c455  mov     r8, rax
0x18022c458  lea     rdx, JSCRIPT_RECYCLER_ALLOCATE_OBJECT; "l"
0x18022c45f  call    McTemplateU0p_EventWriteTransfer
0x18022c464  nop
0x18022c465  mov     r9, [rsp+0A8h+var_58]
0x18022c46a  mov     r8d, esi
0x18022c46d  xor     edx, edx
0x18022c46f  mov     rcx, r13
0x18022c472  mov     rax, rbx
0x18022c475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022c47a  mov     rcx, rax
0x18022c47d  mov     rax, [rsp+0A8h+arg_30]
0x18022c485  mov     [rax], rcx
0x18022c488  jmp     short loc_18022C496
0x18022c48a  jmp     short loc_18022C496
0x18022c48c  jmp     short loc_18022C496
0x18022c48e  jmp     short loc_18022C496
0x18022c490  jmp     short loc_18022C496
0x18022c492  jmp     short loc_18022C496
0x18022c494  jmp     short $+2
0x18022c496  mov     eax, dword ptr [rsp+0A8h+var_68]
0x18022c49a  jmp     loc_18022C6C0
0x18022c49f  lea     r8, [rsp+0A8h+var_60]; struct Projection::ArrayProjection **
0x18022c4a4  mov     rdx, r13; struct Projection::ProjectionContext *
0x18022c4a7  mov     rcx, r14; struct ProjectionModel::ConcreteType *
0x18022c4aa  call    ?EnsureProjection@ArrayProjection@Projection@@SAJPEBUConcreteType@ProjectionModel@@PEAVProjectionContext@2@PEAPEAV12@@Z; Projection::ArrayProjection::EnsureProjection(ProjectionModel::ConcreteType const *,Projection::ProjectionContext *,Projection::ArrayProjection * *)
0x18022c4af  test    eax, eax
0x18022c4b1  js      loc_18022C6C0
0x18022c4b7  mov     r15, [r14+18h]
0x18022c4bb  cmp     [rsp+0A8h+arg_28], 0
0x18022c4c3  jnz     loc_18022C5F4
0x18022c4c9  mov     edi, [rsp+0A8h+arg_18]
0x18022c4d0  mov     r12d, edi
0x18022c4d3  imul    r12, r15
0x18022c4d7  mov     rcx, r12; cb
0x18022c4da  call    cs:__imp_CoTaskMemAlloc
0x18022c4e0  mov     rsi, rax
0x18022c4e3  test    rax, rax
0x18022c4e6  jnz     short loc_18022C4F2
0x18022c4e8  mov     eax, 8007000Eh
0x18022c4ed  jmp     loc_18022C6C0
0x18022c4f2  cmp     [rsp+0A8h+arg_38], 0
0x18022c4fa  jz      loc_18022C5E0
0x18022c500  mov     rcx, r14; struct ProjectionModel::Type *
0x18022c503  call    ?IsBlittable@ConcreteType@ProjectionModel@@SA_NPEBUType@2@@Z; ProjectionModel::ConcreteType::IsBlittable(ProjectionModel::Type const *)
0x18022c508  mov     ebx, [rsp+0A8h+arg_20]
0x18022c50f  test    al, al
0x18022c511  jz      short loc_18022C546
0x18022c513  imul    rbx, r15
0x18022c517  mov     r9, rbx; SourceSize
0x18022c51a  mov     r8, [rsp+0A8h+Source]; Source
0x18022c522  mov     rdx, r12; DestinationSize
0x18022c525  mov     rcx, rsi; Destination
0x18022c528  call    cs:__imp_memcpy_s
0x18022c52e  mov     r8d, edi
0x18022c531  sub     r8d, [rsp+0A8h+arg_20]
0x18022c539  imul    r8, r15
0x18022c53d  lea     rcx, [rbx+rsi]
0x18022c541  jmp     loc_18022C5E6
0x18022c546  xor     r12d, r12d
0x18022c549  test    ebx, ebx
0x18022c54b  jz      short loc_18022C5C6
0x18022c54d  mov     [rsp+0A8h+var_58], 0
0x18022c556  lea     rax, [rsp+0A8h+var_68]
0x18022c55b  mov     [rsp+0A8h+var_70], rax; int *
0x18022c560  lea     rax, [rsp+0A8h+var_58]
0x18022c565  mov     [rsp+0A8h+var_78], rax; void **
0x18022c56a  mov     rax, [rsp+0A8h+var_60]
0x18022c56f  mov     ecx, [rax+28h]
0x18022c572  mov     dword ptr [rsp+0A8h+var_80], ecx; int
0x18022c576  mov     [rsp+0A8h+var_88], r12d; unsigned int
0x18022c57b  mov     r9, r14; struct ProjectionModel::ConcreteType *
0x18022c57e  mov     r8, r13; struct Projection::ProjectionContext *
0x18022c581  mov     edx, edi; unsigned int
0x18022c583  mov     rcx, [rsp+0A8h+Source]; unsigned __int8 *
0x18022c58b  call    ?GetItemAt@ArrayObjectInstance@Projection@@SAJPEAEIPEAVProjectionContext@2@PEBUConcreteType@ProjectionModel@@IHPEAPEAXPEAH@Z; Projection::ArrayObjectInstance::GetItemAt(uchar *,uint,Projection::ProjectionContext *,ProjectionModel::ConcreteType const *,uint,int,void * *,int *)
0x18022c590  lea     rax, [rsp+0A8h+var_68]
0x18022c595  mov     [rsp+0A8h+var_70], rax; int *
0x18022c59a  mov     byte ptr [rsp+0A8h+var_78], 0; bool
0x18022c59f  mov     rax, [rsp+0A8h+var_58]
0x18022c5a4  mov     [rsp+0A8h+var_80], rax; void *
0x18022c5a9  mov     [rsp+0A8h+var_88], r12d; unsigned int
0x18022c5ae  mov     r9, r14; struct ProjectionModel::ConcreteType *
0x18022c5b1  mov     r8, r13; struct Projection::ProjectionContext *
0x18022c5b4  mov     edx, edi; unsigned int
0x18022c5b6  mov     rcx, rsi; unsigned __int8 *
0x18022c5b9  call    ?SetItemAt@ArrayObjectInstance@Projection@@SAJPEAEIPEAVProjectionContext@2@PEBUConcreteType@ProjectionModel@@IPEAX_NPEAH@Z; Projection::ArrayObjectInstance::SetItemAt(uchar *,uint,Projection::ProjectionContext *,ProjectionModel::ConcreteType const *,uint,void *,bool,int *)
0x18022c5be  inc     r12d
0x18022c5c1  cmp     r12d, ebx
0x18022c5c4  jb      short loc_18022C54D
0x18022c5c6  cmp     edi, ebx
0x18022c5c8  jbe     short loc_18022C5ED
0x18022c5ca  mov     r8d, edi
0x18022c5cd  sub     r8d, ebx
0x18022c5d0  imul    r8, r15
0x18022c5d4  mov     rcx, rbx
0x18022c5d7  imul    rcx, r15
0x18022c5db  add     rcx, rsi
0x18022c5de  jmp     short loc_18022C5E6
0x18022c5e0  mov     r8, r12; Size
0x18022c5e3  mov     rcx, rsi; void *
0x18022c5e6  xor     edx, edx; Val
0x18022c5e8  call    memset_0
0x18022c5ed  mov     r12, [rsp+0A8h+var_50]
0x18022c5f2  jmp     short loc_18022C626
0x18022c5f4  mov     edi, [rsp+0A8h+arg_18]
0x18022c5fb  mov     ecx, [rsp+0A8h+arg_20]
0x18022c602  mov     rsi, [rsp+0A8h+Source]
0x18022c60a  cmp     edi, ecx
0x18022c60c  jbe     short loc_18022C626
0x18022c60e  mov     r8d, edi
0x18022c611  sub     r8d, ecx
0x18022c614  imul    r8, r15; Size
0x18022c618  imul    rcx, r15
0x18022c61c  add     rcx, rsi; void *
0x18022c61f  xor     edx, edx; Val
0x18022c621  call    memset_0
0x18022c626  mov     [rsp+0A8h+var_68], 0
0x18022c62f  lea     rax, [rsp+0A8h+var_68]
0x18022c634  mov     [rsp+0A8h+var_78], rax; struct Projection::ArrayObjectInstance **
0x18022c639  mov     [rsp+0A8h+var_80], r13; struct Projection::ProjectionContext *
0x18022c63e  mov     [rsp+0A8h+var_88], edi; unsigned int
0x18022c642  mov     r9, rsi; unsigned __int8 *
0x18022c645  mov     r8, r14; struct ProjectionModel::ConcreteType *
0x18022c648  mov     rcx, [rsp+0A8h+var_60]
0x18022c64d  mov     edx, [rcx+28h]; int
0x18022c650  mov     rcx, [rcx+20h]; void *
0x18022c654  call    ?Create@ArrayObjectInstance@Projection@@SAJPEAXHPEBUConcreteType@ProjectionModel@@PEAEIPEAVProjectionContext@2@PEAPEAV12@@Z; Projection::ArrayObjectInstance::Create(void *,int,ProjectionModel::ConcreteType const *,uchar *,uint,Projection::ProjectionContext *,Projection::ArrayObjectInstance * *)
0x18022c659  test    eax, eax
0x18022c65b  js      short loc_18022C6C0
0x18022c65d  mov     rbx, [rsp+0A8h+var_68]
0x18022c662  test    byte ptr cs:Microsoft_JScriptEnableBits+1, 40h
0x18022c669  jz      short loc_18022C68C
0x18022c66b  mov     rdx, [rbx+8]
0x18022c66f  mov     edx, [rdx+40h]; struct Js::ScriptContext *
0x18022c672  mov     rcx, r12; this
0x18022c675  call    ?StringOfId@Projection@@YAPEBGPEAVScriptContext@Js@@H@Z; Projection::StringOfId(Js::ScriptContext *,int)
0x18022c67a  mov     r9, rax
0x18022c67d  mov     r8, rbx
0x18022c680  lea     rdx, JSCRIPT_RECYCLER_ALLOCATE_WINRT_TYPEDARRAY_OBJECT
0x18022c687  call    McTemplateU0pz_EventWriteTransfer
0x18022c68c  mov     ecx, edi; unsigned int
0x18022c68e  call    ?ToVar@JavascriptNumber@Js@@SAPEAXIPEAVScriptContext@2@@Z; Js::JavascriptNumber::ToVar(uint,Js::ScriptContext *)
0x18022c693  mov     r8, rax
0x18022c696  xor     eax, eax
0x18022c698  mov     dword ptr [rsp+0A8h+var_78], eax
0x18022c69c  mov     dword ptr [rsp+0A8h+var_80], eax
0x18022c6a0  mov     qword ptr [rsp+0A8h+var_88], rax
0x18022c6a5  xor     r9d, r9d
0x18022c6a8  lea     edx, [rax+78h]
0x18022c6ab  mov     rcx, rbx
0x18022c6ae  call    ?SetPropertyWithAttributes@CustomExternalObject@Js@@UEAAHHPEAXEPEAVPropertyValueInfo@2@W4PropertyOperationFlags@2@W4SideEffects@2@@Z; Js::CustomExternalObject::SetPropertyWithAttributes(int,void *,uchar,Js::PropertyValueInfo *,Js::PropertyOperationFlags,Js::SideEffects)
0x18022c6b3  mov     rax, [rsp+0A8h+arg_30]
0x18022c6bb  mov     [rax], rbx
0x18022c6be  xor     eax, eax
0x18022c6c0  add     rsp, 70h
0x18022c6c4  pop     r15
0x18022c6c6  pop     r14
0x18022c6c8  pop     r13
0x18022c6ca  pop     r12
0x18022c6cc  pop     rdi
0x18022c6cd  pop     rsi
0x18022c6ce  pop     rbx
0x18022c6cf  retn
```
