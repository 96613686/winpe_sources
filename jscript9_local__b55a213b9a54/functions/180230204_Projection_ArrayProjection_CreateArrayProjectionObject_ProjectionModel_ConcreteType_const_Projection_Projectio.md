# Projection::ArrayProjection::CreateArrayProjectionObject(ProjectionModel::ConcreteType const *,Projection::ProjectionContext *,uchar *,uint,uint,bool,void * *,bool)

- ea: `0x180230204`
- end: `0x18023066f`
- name: `?CreateArrayProjectionObject@ArrayProjection@Projection@@SAJPEBUConcreteType@ProjectionModel@@PEAVProjectionContext@2@PEAEII_NPEAPEAX3@Z`
- size: `1131`
- prototype: `__int64 __usercall@<rax>(const struct ProjectionModel::ConcreteType *@<rcx>, struct Projection::ProjectionContext *@<rdx>, unsigned __int8 *@<r8>, unsigned int@<r9d>, unsigned int, bool, void **, bool)`
- caller_count: `2`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801c0b04`
- `0x1802494a4`

## callees

- `0x180004ad4`
- `0x1800d5580`
- `0x1801cc26b`
- `0x1801e63b0`
- `0x1802300b4`
- `0x180230204`
- `0x180230678`
- `0x180230784`
- `0x180230858`
- `0x180230c5c`
- `0x180231924`
- `0x180231c18`
- `0x18024aa1c`
- `0x1802b8d88`
- `0x180336cf8`
- `0x180364010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18023036e`
- `msvcrt!memcpy_s` at `0x1802304c0`
- `msvcrt!memcpy_s` at `0x18023036e`
- `msvcrt!memcpy_s` at `0x1802304c0`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x18023046c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x18023046c`

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
      McTemplateU0pz_EventWriteTransfer(v41, JSCRIPT_RECYCLER_ALLOCATE_WINRT_TYPEDARRAY_OBJECT, v39, v40);
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
0x180230204  mov     rax, rsp
0x180230207  mov     [rax+20h], r9d
0x18023020b  mov     [rax+18h], r8
0x18023020f  mov     [rax+10h], rdx
0x180230213  mov     [rax+8], rcx
0x180230217  push    rbx
0x180230218  push    rsi
0x180230219  push    rdi
0x18023021a  push    r12
0x18023021c  push    r13
0x18023021e  push    r14
0x180230220  push    r15
0x180230222  sub     rsp, 70h
0x180230226  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x18023022e  mov     qword ptr [rax-60h], 0
0x180230236  mov     r13, rdx
0x180230239  mov     r12, [rdx+70h]
0x18023023d  mov     [rsp+0A8h+var_50], r12
0x180230242  mov     r14, rcx
0x180230245  cmp     dword ptr [rcx], 0Fh
0x180230248  jnz     loc_180230431
0x18023024e  mov     rax, [r12]
0x180230252  mov     [rsp+0A8h+var_58], rax
0x180230257  call    ?From@BasicType@ProjectionModel@@SAPEBUImpl@12@PEBUType@2@@Z; ProjectionModel::BasicType::From(ProjectionModel::Type const *)
0x18023025c  mov     ecx, [rax+28h]
0x18023025f  cmp     ecx, 8
0x180230262  jg      short loc_1802302B9
0x180230264  jz      short loc_1802302B0
0x180230266  sub     ecx, 2
0x180230269  jz      short loc_1802302A7
0x18023026b  sub     ecx, 1
0x18023026e  jz      short loc_18023029E
0x180230270  sub     ecx, 2
0x180230273  jz      short loc_180230295
0x180230275  sub     ecx, 1
0x180230278  jz      short loc_18023028C
0x18023027a  cmp     ecx, 1
0x18023027d  jnz     loc_180230431
0x180230283  lea     rbx, ?Create@?$TypedArray@G$0A@@Js@@SAPEAXPEAVArrayBuffer@2@IIPEAVJavascriptLibrary@2@@Z; Js::TypedArray<ushort,0>::Create(Js::ArrayBuffer *,uint,uint,Js::JavascriptLibrary *)
0x18023028a  jmp     short loc_180230301
0x18023028c  lea     rbx, ?Create@?$TypedArray@F$0A@@Js@@SAPEAXPEAVArrayBuffer@2@IIPEAVJavascriptLibrary@2@@Z; Js::TypedArray<short,0>::Create(Js::ArrayBuffer *,uint,uint,Js::JavascriptLibrary *)
0x180230293  jmp     short loc_180230301
0x180230295  lea     rbx, ?Create@?$TypedArray@E$0A@@Js@@SAPEAXPEAVArrayBuffer@2@IIPEAVJavascriptLibrary@2@@Z; Js::TypedArray<uchar,0>::Create(Js::ArrayBuffer *,uint,uint,Js::JavascriptLibrary *)
0x18023029c  jmp     short loc_180230301
0x18023029e  lea     rbx, ?Create@CharArray@Js@@SAPEAXPEAVArrayBuffer@2@IIPEAVJavascriptLibrary@2@@Z; Js::CharArray::Create(Js::ArrayBuffer *,uint,uint,Js::JavascriptLibrary *)
0x1802302a5  jmp     short loc_180230301
0x1802302a7  lea     rbx, ?Create@?$TypedArray@_N$0A@@Js@@SAPEAXPEAVArrayBuffer@2@IIPEAVJavascriptLibrary@2@@Z; Js::TypedArray<bool,0>::Create(Js::ArrayBuffer *,uint,uint,Js::JavascriptLibrary *)
0x1802302ae  jmp     short loc_180230301
0x1802302b0  lea     rbx, ?Create@?$TypedArray@H$0A@@Js@@SAPEAXPEAVArrayBuffer@2@IIPEAVJavascriptLibrary@2@@Z; Js::TypedArray<int,0>::Create(Js::ArrayBuffer *,uint,uint,Js::JavascriptLibrary *)
0x1802302b7  jmp     short loc_180230301
0x1802302b9  sub     ecx, 9
0x1802302bc  jz      short loc_1802302FA
0x1802302be  sub     ecx, 1
0x1802302c1  jz      short loc_1802302F1
0x1802302c3  sub     ecx, 1
0x1802302c6  jz      short loc_1802302E8
0x1802302c8  sub     ecx, 1
0x1802302cb  jz      short loc_1802302DF
0x1802302cd  cmp     ecx, 1
0x1802302d0  jnz     loc_180230431
0x1802302d6  lea     rbx, ?Create@?$TypedArray@N$0A@@Js@@SAPEAXPEAVArrayBuffer@2@IIPEAVJavascriptLibrary@2@@Z; Js::TypedArray<double,0>::Create(Js::ArrayBuffer *,uint,uint,Js::JavascriptLibrary *)
0x1802302dd  jmp     short loc_180230301
0x1802302df  lea     rbx, ?Create@?$TypedArray@M$0A@@Js@@SAPEAXPEAVArrayBuffer@2@IIPEAVJavascriptLibrary@2@@Z; Js::TypedArray<float,0>::Create(Js::ArrayBuffer *,uint,uint,Js::JavascriptLibrary *)
0x1802302e6  jmp     short loc_180230301
0x1802302e8  lea     rbx, ?Create@?$TypedArray@_K$0A@@Js@@SAPEAXPEAVArrayBuffer@2@IIPEAVJavascriptLibrary@2@@Z; Js::TypedArray<unsigned __int64,0>::Create(Js::ArrayBuffer *,uint,uint,Js::JavascriptLibrary *)
0x1802302ef  jmp     short loc_180230301
0x1802302f1  lea     rbx, ?Create@?$TypedArray@_J$0A@@Js@@SAPEAXPEAVArrayBuffer@2@IIPEAVJavascriptLibrary@2@@Z; Js::TypedArray<__int64,0>::Create(Js::ArrayBuffer *,uint,uint,Js::JavascriptLibrary *)
0x1802302f8  jmp     short loc_180230301
0x1802302fa  lea     rbx, ?Create@?$TypedArray@I$0A@@Js@@SAPEAXPEAVArrayBuffer@2@IIPEAVJavascriptLibrary@2@@Z; Js::TypedArray<uint,0>::Create(Js::ArrayBuffer *,uint,uint,Js::JavascriptLibrary *)
0x180230301  mov     dword ptr [rsp+0A8h+var_68], 0
0x180230309  mov     r15, [r14+18h]
0x18023030d  mov     edi, r15d
0x180230310  mov     esi, [rsp+0A8h+arg_18]
0x180230317  imul    edi, esi
0x18023031a  cmp     [rsp+0A8h+arg_28], 0
0x180230322  jnz     short loc_18023039B
0x180230324  mov     edx, edi; unsigned int
0x180230326  mov     rcx, [r12]; this
0x18023032a  call    ?CreateProjectionArraybuffer@JavascriptLibrary@Js@@QEAAPEAVArrayBuffer@2@I@Z; Js::JavascriptLibrary::CreateProjectionArraybuffer(uint)
0x18023032f  mov     r13, rax
0x180230332  mov     r14, [rax+38h]
0x180230336  test    edi, edi
0x180230338  jz      short loc_180230343
0x18023033a  test    r14, r14
0x18023033d  jz      loc_180230480
0x180230343  mov     eax, edi
0x180230345  mov     rcx, r14; void *
0x180230348  cmp     [rsp+0A8h+arg_38], 0
0x180230350  jz      short loc_18023038F
0x180230352  mov     r12d, [rsp+0A8h+arg_20]
0x18023035a  mov     edi, r12d
0x18023035d  imul    rdi, r15
0x180230361  mov     r9, rdi; SourceSize
0x180230364  mov     r8, [rsp+0A8h+Source]; Source
0x18023036c  mov     edx, eax; DestinationSize
0x18023036e  call    cs:__imp_memcpy_s
0x180230375  nop     dword ptr [rax+rax+00h]
0x18023037a  cmp     esi, r12d
0x18023037d  jbe     short loc_1802303F7
0x18023037f  mov     r8d, esi
0x180230382  sub     r8d, r12d
0x180230385  imul    r8, r15
0x180230389  lea     rcx, [rdi+r14]
0x18023038d  jmp     short loc_180230392
0x18023038f  mov     r8, rax; Size
0x180230392  xor     edx, edx; Val
0x180230394  call    memset_0
0x180230399  jmp     short loc_1802303F7
0x18023039b  mov     ecx, [rsp+0A8h+arg_20]
0x1802303a2  mov     r14, [rsp+0A8h+Source]
0x1802303aa  cmp     esi, ecx
0x1802303ac  jbe     short loc_1802303C6
0x1802303ae  mov     r8d, esi
0x1802303b1  sub     r8d, ecx
0x1802303b4  imul    r8, r15; Size
0x1802303b8  imul    rcx, r15
0x1802303bc  add     rcx, r14; void *
0x1802303bf  xor     edx, edx; Val
0x1802303c1  call    memset_0
0x1802303c6  mov     r8, [r12]
0x1802303ca  mov     r8, [r8+478h]; struct Js::DynamicType *
0x1802303d1  mov     edx, edi; unsigned int
0x1802303d3  mov     rcx, r14; unsigned __int8 *
0x1802303d6  call    ?Create@ProjectionArrayBuffer@Js@@SAPEAV12@PEAEIPEAVDynamicType@2@@Z; Js::ProjectionArrayBuffer::Create(uchar *,uint,Js::DynamicType *)
0x1802303db  mov     r13, rax
0x1802303de  test    byte ptr cs:Microsoft_JScriptEnableBits+1, 8
0x1802303e5  jz      short loc_1802303F7
0x1802303e7  mov     r8, rax
0x1802303ea  lea     rdx, JSCRIPT_RECYCLER_ALLOCATE_OBJECT; "l"
0x1802303f1  call    McTemplateU0p_EventWriteTransfer
0x1802303f6  nop
0x1802303f7  mov     r9, [rsp+0A8h+var_58]
0x1802303fc  mov     r8d, esi
0x1802303ff  xor     edx, edx
0x180230401  mov     rcx, r13
0x180230404  mov     rax, rbx
0x180230407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18023040c  mov     rcx, rax
0x18023040f  mov     rax, [rsp+0A8h+arg_30]
0x180230417  mov     [rax], rcx
0x18023041a  jmp     short loc_180230428
0x18023041c  jmp     short loc_180230428
0x18023041e  jmp     short loc_180230428
0x180230420  jmp     short loc_180230428
0x180230422  jmp     short loc_180230428
0x180230424  jmp     short loc_180230428
0x180230426  jmp     short $+2
0x180230428  mov     eax, dword ptr [rsp+0A8h+var_68]
0x18023042c  jmp     loc_18023065E
0x180230431  lea     r8, [rsp+0A8h+var_60]; struct Projection::ArrayProjection **
0x180230436  mov     rdx, r13; struct Projection::ProjectionContext *
0x180230439  mov     rcx, r14; struct ProjectionModel::ConcreteType *
0x18023043c  call    ?EnsureProjection@ArrayProjection@Projection@@SAJPEBUConcreteType@ProjectionModel@@PEAVProjectionContext@2@PEAPEAV12@@Z; Projection::ArrayProjection::EnsureProjection(ProjectionModel::ConcreteType const *,Projection::ProjectionContext *,Projection::ArrayProjection * *)
0x180230441  test    eax, eax
0x180230443  js      loc_18023065E
0x180230449  mov     r15, [r14+18h]
0x18023044d  cmp     [rsp+0A8h+arg_28], 0
0x180230455  jnz     loc_180230592
0x18023045b  mov     edi, [rsp+0A8h+arg_18]
0x180230462  mov     r12d, edi
0x180230465  imul    r12, r15
0x180230469  mov     rcx, r12; cb
0x18023046c  call    cs:__imp_CoTaskMemAlloc
0x180230473  nop     dword ptr [rax+rax+00h]
0x180230478  mov     rsi, rax
0x18023047b  test    rax, rax
0x18023047e  jnz     short loc_18023048A
0x180230480  mov     eax, 8007000Eh
0x180230485  jmp     loc_18023065E
0x18023048a  cmp     [rsp+0A8h+arg_38], 0
0x180230492  jz      loc_18023057E
0x180230498  mov     rcx, r14; struct ProjectionModel::Type *
0x18023049b  call    ?IsBlittable@ConcreteType@ProjectionModel@@SA_NPEBUType@2@@Z; ProjectionModel::ConcreteType::IsBlittable(ProjectionModel::Type const *)
0x1802304a0  mov     ebx, [rsp+0A8h+arg_20]
0x1802304a7  test    al, al
0x1802304a9  jz      short loc_1802304E4
0x1802304ab  imul    rbx, r15
0x1802304af  mov     r9, rbx; SourceSize
0x1802304b2  mov     r8, [rsp+0A8h+Source]; Source
0x1802304ba  mov     rdx, r12; DestinationSize
0x1802304bd  mov     rcx, rsi; Destination
0x1802304c0  call    cs:__imp_memcpy_s
0x1802304c7  nop     dword ptr [rax+rax+00h]
0x1802304cc  mov     r8d, edi
0x1802304cf  sub     r8d, [rsp+0A8h+arg_20]
0x1802304d7  imul    r8, r15
0x1802304db  lea     rcx, [rbx+rsi]
0x1802304df  jmp     loc_180230584
0x1802304e4  xor     r12d, r12d
0x1802304e7  test    ebx, ebx
0x1802304e9  jz      short loc_180230564
0x1802304eb  mov     [rsp+0A8h+var_58], 0
0x1802304f4  lea     rax, [rsp+0A8h+var_68]
0x1802304f9  mov     [rsp+0A8h+var_70], rax; int *
0x1802304fe  lea     rax, [rsp+0A8h+var_58]
0x180230503  mov     [rsp+0A8h+var_78], rax; void **
0x180230508  mov     rax, [rsp+0A8h+var_60]
0x18023050d  mov     ecx, [rax+28h]
0x180230510  mov     dword ptr [rsp+0A8h+var_80], ecx; int
0x180230514  mov     [rsp+0A8h+var_88], r12d; unsigned int
0x180230519  mov     r9, r14; struct ProjectionModel::ConcreteType *
0x18023051c  mov     r8, r13; struct Projection::ProjectionContext *
0x18023051f  mov     edx, edi; unsigned int
0x180230521  mov     rcx, [rsp+0A8h+Source]; unsigned __int8 *
0x180230529  call    ?GetItemAt@ArrayObjectInstance@Projection@@SAJPEAEIPEAVProjectionContext@2@PEBUConcreteType@ProjectionModel@@IHPEAPEAXPEAH@Z; Projection::ArrayObjectInstance::GetItemAt(uchar *,uint,Projection::ProjectionContext *,ProjectionModel::ConcreteType const *,uint,int,void * *,int *)
0x18023052e  lea     rax, [rsp+0A8h+var_68]
0x180230533  mov     [rsp+0A8h+var_70], rax; int *
0x180230538  mov     byte ptr [rsp+0A8h+var_78], 0; bool
0x18023053d  mov     rax, [rsp+0A8h+var_58]
0x180230542  mov     [rsp+0A8h+var_80], rax; void *
0x180230547  mov     [rsp+0A8h+var_88], r12d; unsigned int
0x18023054c  mov     r9, r14; struct ProjectionModel::ConcreteType *
0x18023054f  mov     r8, r13; struct Projection::ProjectionContext *
0x180230552  mov     edx, edi; unsigned int
0x180230554  mov     rcx, rsi; unsigned __int8 *
0x180230557  call    ?SetItemAt@ArrayObjectInstance@Projection@@SAJPEAEIPEAVProjectionContext@2@PEBUConcreteType@ProjectionModel@@IPEAX_NPEAH@Z; Projection::ArrayObjectInstance::SetItemAt(uchar *,uint,Projection::ProjectionContext *,ProjectionModel::ConcreteType const *,uint,void *,bool,int *)
0x18023055c  inc     r12d
0x18023055f  cmp     r12d, ebx
0x180230562  jb      short loc_1802304EB
0x180230564  cmp     edi, ebx
0x180230566  jbe     short loc_18023058B
0x180230568  mov     r8d, edi
0x18023056b  sub     r8d, ebx
0x18023056e  imul    r8, r15
0x180230572  mov     rcx, rbx
0x180230575  imul    rcx, r15
0x180230579  add     rcx, rsi
0x18023057c  jmp     short loc_180230584
0x18023057e  mov     r8, r12; Size
0x180230581  mov     rcx, rsi; void *
0x180230584  xor     edx, edx; Val
0x180230586  call    memset_0
0x18023058b  mov     r12, [rsp+0A8h+var_50]
0x180230590  jmp     short loc_1802305C4
0x180230592  mov     edi, [rsp+0A8h+arg_18]
0x180230599  mov     ecx, [rsp+0A8h+arg_20]
0x1802305a0  mov     rsi, [rsp+0A8h+Source]
0x1802305a8  cmp     edi, ecx
0x1802305aa  jbe     short loc_1802305C4
0x1802305ac  mov     r8d, edi
0x1802305af  sub     r8d, ecx
0x1802305b2  imul    r8, r15; Size
0x1802305b6  imul    rcx, r15
0x1802305ba  add     rcx, rsi; void *
0x1802305bd  xor     edx, edx; Val
0x1802305bf  call    memset_0
0x1802305c4  mov     [rsp+0A8h+var_68], 0
0x1802305cd  lea     rax, [rsp+0A8h+var_68]
0x1802305d2  mov     [rsp+0A8h+var_78], rax; struct Projection::ArrayObjectInstance **
0x1802305d7  mov     [rsp+0A8h+var_80], r13; struct Projection::ProjectionContext *
0x1802305dc  mov     [rsp+0A8h+var_88], edi; unsigned int
0x1802305e0  mov     r9, rsi; unsigned __int8 *
0x1802305e3  mov     r8, r14; struct ProjectionModel::ConcreteType *
0x1802305e6  mov     rcx, [rsp+0A8h+var_60]
0x1802305eb  mov     edx, [rcx+28h]; int
0x1802305ee  mov     rcx, [rcx+20h]; void *
0x1802305f2  call    ?Create@ArrayObjectInstance@Projection@@SAJPEAXHPEBUConcreteType@ProjectionModel@@PEAEIPEAVProjectionContext@2@PEAPEAV12@@Z; Projection::ArrayObjectInstance::Create(void *,int,ProjectionModel::ConcreteType const *,uchar *,uint,Projection::ProjectionContext *,Projection::ArrayObjectInstance * *)
0x1802305f7  test    eax, eax
0x1802305f9  js      short loc_18023065E
0x1802305fb  mov     rbx, [rsp+0A8h+var_68]
0x180230600  test    byte ptr cs:Microsoft_JScriptEnableBits+1, 40h
0x180230607  jz      short loc_18023062A
0x180230609  mov     rdx, [rbx+8]
0x18023060d  mov     edx, [rdx+40h]; struct Js::ScriptContext *
0x180230610  mov     rcx, r12; this
0x180230613  call    ?StringOfId@Projection@@YAPEBGPEAVScriptContext@Js@@H@Z; Projection::StringOfId(Js::ScriptContext *,int)
0x180230618  mov     r9, rax
0x18023061b  mov     r8, rbx
0x18023061e  lea     rdx, JSCRIPT_RECYCLER_ALLOCATE_WINRT_TYPEDARRAY_OBJECT
0x180230625  call    McTemplateU0pz_EventWriteTransfer
0x18023062a  mov     ecx, edi; unsigned int
0x18023062c  call    ?ToVar@JavascriptNumber@Js@@SAPEAXIPEAVScriptContext@2@@Z; Js::JavascriptNumber::ToVar(uint,Js::ScriptContext *)
0x180230631  mov     r8, rax
0x180230634  xor     eax, eax
0x180230636  mov     dword ptr [rsp+0A8h+var_78], eax
0x18023063a  mov     dword ptr [rsp+0A8h+var_80], eax
0x18023063e  mov     qword ptr [rsp+0A8h+var_88], rax
0x180230643  xor     r9d, r9d
0x180230646  lea     edx, [rax+78h]
0x180230649  mov     rcx, rbx
0x18023064c  call    ?SetPropertyWithAttributes@CustomExternalObject@Js@@UEAAHHPEAXEPEAVPropertyValueInfo@2@W4PropertyOperationFlags@2@W4SideEffects@2@@Z; Js::CustomExternalObject::SetPropertyWithAttributes(int,void *,uchar,Js::PropertyValueInfo *,Js::PropertyOperationFlags,Js::SideEffects)
0x180230651  mov     rax, [rsp+0A8h+arg_30]
0x180230659  mov     [rax], rbx
0x18023065c  xor     eax, eax
0x18023065e  add     rsp, 70h
0x180230662  pop     r15
0x180230664  pop     r14
0x180230666  pop     r13
0x180230668  pop     r12
0x18023066a  pop     rdi
0x18023066b  pop     rsi
0x18023066c  pop     rbx
0x18023066d  retn
```
