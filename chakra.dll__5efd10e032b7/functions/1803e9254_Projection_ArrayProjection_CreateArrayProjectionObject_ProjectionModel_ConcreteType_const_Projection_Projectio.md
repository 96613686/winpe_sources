# Projection::ArrayProjection::CreateArrayProjectionObject(ProjectionModel::ConcreteType const *,Projection::ProjectionContext *,uchar *,uint,uint,bool,void * *,bool)

- ea: `0x1803e9254`
- end: `0x1803e970b`
- name: `?CreateArrayProjectionObject@ArrayProjection@Projection@@SAJPEBUConcreteType@ProjectionModel@@PEAVProjectionContext@2@PEAEII_NPEAPEAX3@Z`
- size: `1207`
- prototype: `__int64 __fastcall(const struct ProjectionModel::ConcreteType *, struct Projection::ProjectionContext *, unsigned __int8 *, unsigned int, unsigned int, bool, void **, bool)`
- caller_count: `2`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004054`
- `0x1803e6c5c`

## callees

- `0x18008f4d4`
- `0x180149c24`
- `0x180159c48`
- `0x1801dc434`
- `0x18036da20`
- `0x1803cf46c`
- `0x1803d63c8`
- `0x1803e9254`
- `0x180470e24`
- `0x18047c00c`
- `0x18047c65c`
- `0x18047d29c`
- `0x1804fc03c`
- `0x1805a9c5a`
- `0x1805cd010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1803e9415`
- `msvcrt!memcpy_s` at `0x1803e9555`
- `msvcrt!memcpy_s` at `0x1803e9415`
- `msvcrt!memcpy_s` at `0x1803e9555`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1803e9501`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1803e9501`

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
  void **v8; // r12
  __int64 result; // rax
  void **v10; // r15
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  void *(*v16)(struct Js::ArrayBufferBase *, unsigned int, unsigned int, struct Js::JavascriptLibrary *); // rbx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  __int64 v21; // r14
  unsigned int v22; // esi
  struct Js::ArrayBuffer *ProjectionArraybuffer; // r13
  char *v24; // rax
  char *v25; // r15
  size_t v26; // r8
  __int64 v27; // rcx
  unsigned __int8 *v28; // r14
  __int64 v29; // r15
  unsigned int v30; // edi
  unsigned __int8 *v31; // rax
  unsigned __int8 *v32; // rsi
  size_t v33; // r8
  unsigned __int8 *v34; // rcx
  unsigned int i; // r12d
  struct Js::ScriptContext *v36; // rdx
  int v37; // r8d
  struct Projection::ArrayObjectInstance *v38; // rbx
  const unsigned __int16 *v39; // rax
  void *v40; // rax
  void **v41; // rax
  void *v42; // rdx
  struct Js::RecyclableObject *v43; // rax
  int v44; // [rsp+30h] [rbp-78h]
  struct Projection::ArrayObjectInstance *v45; // [rsp+40h] [rbp-68h] BYREF
  struct Projection::ArrayProjection *v46; // [rsp+48h] [rbp-60h] BYREF
  void *v47; // [rsp+50h] [rbp-58h] BYREF
  Projection *v48; // [rsp+58h] [rbp-50h]
  __int64 v49; // [rsp+60h] [rbp-48h]
  const Js::JavascriptException *v50; // [rsp+68h] [rbp-40h] BYREF

  v49 = -2;
  v8 = a7;
  if ( !a7 )
    return 2147942487LL;
  *a7 = 0;
  v46 = 0;
  v10 = (void **)*((_QWORD *)a2 + 14);
  v48 = (Projection *)v10;
  if ( *(_DWORD *)a1 != 15 )
    goto LABEL_41;
  v47 = v10[1];
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
              goto LABEL_41;
            v16 = Js::TypedArray<double,0,0>::Create;
          }
          else
          {
            v16 = Js::TypedArray<float,0,0>::Create;
          }
        }
        else
        {
          v16 = Js::TypedArray<unsigned __int64,0,0>::Create;
        }
      }
      else
      {
        v16 = Js::TypedArray<__int64,0,0>::Create;
      }
    }
    else
    {
      v16 = Js::TypedArray<unsigned int,0,0>::Create;
    }
LABEL_27:
    v21 = *((_QWORD *)a1 + 3);
    if ( v21 * (unsigned __int64)a4 <= 0xFFFFFFFF )
    {
      LODWORD(v45) = 0;
      v22 = a4 * v21;
      if ( a6 )
      {
        if ( a4 <= a5 )
        {
          v28 = a3;
        }
        else
        {
          v26 = v21 * (a4 - a5);
          v27 = v21 * a5;
          v28 = a3;
          memset_0(&a3[v27], 0, v26);
        }
        ProjectionArraybuffer = Js::JavascriptLibrary::CreateProjectionArraybuffer(
                                  (Js::JavascriptLibrary *)v10[1],
                                  v28,
                                  v22);
LABEL_76:
        try
        {
          *v8 = (void *)((__int64 (__fastcall *)(struct Js::ArrayBuffer *, _QWORD, _QWORD, void *))v16)(
                          ProjectionArraybuffer,
                          0,
                          a4,
                          v47);
        }
        catch ( Js::OutOfMemoryException )
        {
          LODWORD(v45) = -2147024882;
          return (unsigned int)v45;
        }
        catch ( Js::StackOverflowException )
        {
          LODWORD(v45) = -2146828260;
          return (unsigned int)v45;
        }
        catch ( Js::NotImplementedException )
        {
          LODWORD(v45) = -2147467263;
          return (unsigned int)v45;
        }
        catch ( Js::ScriptAbortException )
        {
          LODWORD(v45) = -2147467260;
          return (unsigned int)v45;
        }
        catch ( Js::AsmJsParseException )
        {
          LODWORD(v45) = -2146823140;
          return (unsigned int)v45;
        }
        catch ( const Js::JavascriptException *v50 )
        {
          v41 = (void **)Js::JavascriptException::GetAndClear(v50);
          if ( *v41 )
          {
            if ( Js::JavascriptError::Is(*v41) || Js::JavascriptError::IsRemoteError(v42) )
            {
              v43 = Js::RecyclableObject::FromVar(v42);
              LODWORD(v45) = Js::JavascriptError::GetRuntimeError(v43, 0);
            }
            else
            {
              LODWORD(v45) = -2146823266;
            }
          }
          else
          {
            LODWORD(v45) = -2147024882;
          }
          return (unsigned int)v45;
        }
        catch ( ... )
        {
          Js::Throw::FatalInternalError(-2147467259);
          JUMPOUT(0x1805B901FLL);
        }
        return (unsigned int)v45;
      }
      ProjectionArraybuffer = Js::JavascriptLibrary::CreateProjectionArraybuffer((Js::JavascriptLibrary *)v10[1], v22);
      v24 = (char *)(*(__int64 (__fastcall **)(struct Js::ArrayBuffer *))(*(_QWORD *)ProjectionArraybuffer + 840LL))(ProjectionArraybuffer);
      v25 = v24;
      if ( !v22 || v24 )
      {
        if ( a8 )
        {
          memcpy_s(v24, v22, a3, v21 * a5);
          if ( a4 > a5 )
            memset_0(&v25[v21 * a5], 0, v21 * (a4 - a5));
          v8 = a7;
        }
        else
        {
          memset_0(v24, 0, v22);
        }
        goto LABEL_76;
      }
    }
    return 2147942414LL;
  }
  if ( v11 == 8 )
  {
    v16 = Js::TypedArray<int,0,0>::Create;
    goto LABEL_27;
  }
  v12 = v11 - 2;
  if ( !v12 )
  {
    v16 = Js::TypedArray<bool,0,0>::Create;
    goto LABEL_27;
  }
  v13 = v12 - 1;
  if ( !v13 )
  {
    v16 = (void *(*)(struct Js::ArrayBufferBase *, unsigned int, unsigned int, struct Js::JavascriptLibrary *))Js::CharArray::Create;
    goto LABEL_27;
  }
  v14 = v13 - 2;
  if ( !v14 )
  {
    v16 = Js::TypedArray<unsigned char,0,0>::Create;
    goto LABEL_27;
  }
  v15 = v14 - 1;
  if ( !v15 )
  {
    v16 = Js::TypedArray<short,0,0>::Create;
    goto LABEL_27;
  }
  if ( v15 == 1 )
  {
    v16 = Js::TypedArray<unsigned short,0,0>::Create;
    goto LABEL_27;
  }
LABEL_41:
  result = Projection::ArrayProjection::EnsureProjection(a1, a2, &v46);
  if ( (int)result < 0 )
    return result;
  v29 = *((_QWORD *)a1 + 3);
  if ( a6 )
  {
    v30 = a4;
    v32 = a3;
    if ( a4 > a5 )
      memset_0(&a3[v29 * a5], 0, v29 * (a4 - a5));
    goto LABEL_57;
  }
  v30 = a4;
  v31 = (unsigned __int8 *)CoTaskMemAlloc(v29 * a4);
  v32 = v31;
  if ( !v31 )
    return 2147942414LL;
  if ( a8 )
  {
    if ( ProjectionModel::ConcreteType::IsBlittable(a1) )
    {
      memcpy_s(v32, v29 * a4, a3, v29 * a5);
      v33 = v29 * (a4 - a5);
      v34 = &v32[v29 * a5];
    }
    else
    {
      for ( i = 0; i < a5; ++i )
      {
        v47 = 0;
        Projection::ArrayObjectInstance::GetItemAt(a3, a4, a2, a1, i, *((_DWORD *)v46 + 10), &v47, (int *)&v45);
        Projection::ArrayObjectInstance::SetItemAt(v32, a4, a2, a1, i, v47, 0, (int *)&v45);
      }
      if ( a4 <= a5 )
        goto LABEL_54;
      v33 = v29 * (a4 - a5);
      v34 = &v32[v29 * a5];
    }
  }
  else
  {
    v33 = v29 * a4;
    v34 = v31;
  }
  memset_0(v34, 0, v33);
LABEL_54:
  v8 = a7;
LABEL_57:
  v45 = 0;
  result = Projection::ArrayObjectInstance::Create(*((void **)v46 + 4), *((_DWORD *)v46 + 10), a1, v32, v30, a2, &v45);
  if ( (int)result >= 0 )
  {
    v38 = v45;
    if ( (Microsoft_JScriptEnableBits & 0x4000) != 0 )
    {
      v39 = Projection::StringOfId(v48, (struct Js::ScriptContext *)*(unsigned int *)(*((_QWORD *)v45 + 1) + 56LL), v37);
      McTemplateU0pz_EventWriteTransfer(
        &PROVIDER_JSCRIPT9_Context,
        JSCRIPT_RECYCLER_ALLOCATE_WINRT_TYPEDARRAY_OBJECT,
        v38,
        v39);
    }
    v40 = Js::JavascriptNumber::ToVar(v30, v36);
    LOBYTE(v44) = 0;
    Js::CustomExternalObject::SetPropertyWithAttributes(v38, 193, v40, 0, 0, 0, v44);
    *v8 = v38;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1803e9254  mov     rax, rsp
0x1803e9257  mov     [rax+20h], r9d
0x1803e925b  mov     [rax+18h], r8
0x1803e925f  mov     [rax+10h], rdx
0x1803e9263  mov     [rax+8], rcx
0x1803e9267  push    rbx
0x1803e9268  push    rsi
0x1803e9269  push    rdi
0x1803e926a  push    r12
0x1803e926c  push    r13
0x1803e926e  push    r14
0x1803e9270  push    r15
0x1803e9272  sub     rsp, 70h
0x1803e9276  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x1803e927e  mov     r12, [rsp+0A8h+arg_30]
0x1803e9286  test    r12, r12
0x1803e9289  jnz     short loc_1803E9295
0x1803e928b  mov     eax, 80070057h
0x1803e9290  jmp     loc_1803E96FA
0x1803e9295  mov     qword ptr [r12], 0
0x1803e929d  mov     [rsp+0A8h+var_60], 0
0x1803e92a6  mov     r13, [rsp+0A8h+arg_8]
0x1803e92ae  mov     r15, [r13+70h]
0x1803e92b2  mov     [rsp+0A8h+var_50], r15
0x1803e92b7  mov     r14, [rsp+0A8h+arg_0]
0x1803e92bf  cmp     dword ptr [r14], 0Fh
0x1803e92c3  jnz     loc_1803E94C6
0x1803e92c9  mov     rax, [r15+8]
0x1803e92cd  mov     [rsp+0A8h+var_58], rax
0x1803e92d2  mov     rcx, r14; struct ProjectionModel::Type *
0x1803e92d5  call    ?From@BasicType@ProjectionModel@@SAPEBUImpl@12@PEBUType@2@@Z; ProjectionModel::BasicType::From(ProjectionModel::Type const *)
0x1803e92da  mov     ecx, [rax+28h]
0x1803e92dd  cmp     ecx, 8
0x1803e92e0  jg      short loc_1803E9337
0x1803e92e2  jz      short loc_1803E932E
0x1803e92e4  sub     ecx, 2
0x1803e92e7  jz      short loc_1803E9325
0x1803e92e9  sub     ecx, 1
0x1803e92ec  jz      short loc_1803E931C
0x1803e92ee  sub     ecx, 2
0x1803e92f1  jz      short loc_1803E9313
0x1803e92f3  sub     ecx, 1
0x1803e92f6  jz      short loc_1803E930A
0x1803e92f8  cmp     ecx, 1
0x1803e92fb  jnz     loc_1803E94C6
0x1803e9301  lea     rbx, ?Create@?$TypedArray@G$0A@$0A@@Js@@SAPEAXPEAVArrayBufferBase@2@IIPEAVJavascriptLibrary@2@@Z; Js::TypedArray<ushort,0,0>::Create(Js::ArrayBufferBase *,uint,uint,Js::JavascriptLibrary *)
0x1803e9308  jmp     short loc_1803E937F
0x1803e930a  lea     rbx, ?Create@?$TypedArray@F$0A@$0A@@Js@@SAPEAXPEAVArrayBufferBase@2@IIPEAVJavascriptLibrary@2@@Z; Js::TypedArray<short,0,0>::Create(Js::ArrayBufferBase *,uint,uint,Js::JavascriptLibrary *)
0x1803e9311  jmp     short loc_1803E937F
0x1803e9313  lea     rbx, ?Create@?$TypedArray@E$0A@$0A@@Js@@SAPEAXPEAVArrayBufferBase@2@IIPEAVJavascriptLibrary@2@@Z; Js::TypedArray<uchar,0,0>::Create(Js::ArrayBufferBase *,uint,uint,Js::JavascriptLibrary *)
0x1803e931a  jmp     short loc_1803E937F
0x1803e931c  lea     rbx, ?Create@CharArray@Js@@SAPEAXPEAVArrayBufferBase@2@IIPEAVJavascriptLibrary@2@@Z; Js::CharArray::Create(Js::ArrayBufferBase *,uint,uint,Js::JavascriptLibrary *)
0x1803e9323  jmp     short loc_1803E937F
0x1803e9325  lea     rbx, ?Create@?$TypedArray@_N$0A@$0A@@Js@@SAPEAXPEAVArrayBufferBase@2@IIPEAVJavascriptLibrary@2@@Z; Js::TypedArray<bool,0,0>::Create(Js::ArrayBufferBase *,uint,uint,Js::JavascriptLibrary *)
0x1803e932c  jmp     short loc_1803E937F
0x1803e932e  lea     rbx, ?Create@?$TypedArray@H$0A@$0A@@Js@@SAPEAXPEAVArrayBufferBase@2@IIPEAVJavascriptLibrary@2@@Z; Js::TypedArray<int,0,0>::Create(Js::ArrayBufferBase *,uint,uint,Js::JavascriptLibrary *)
0x1803e9335  jmp     short loc_1803E937F
0x1803e9337  sub     ecx, 9
0x1803e933a  jz      short loc_1803E9378
0x1803e933c  sub     ecx, 1
0x1803e933f  jz      short loc_1803E936F
0x1803e9341  sub     ecx, 1
0x1803e9344  jz      short loc_1803E9366
0x1803e9346  sub     ecx, 1
0x1803e9349  jz      short loc_1803E935D
0x1803e934b  cmp     ecx, 1
0x1803e934e  jnz     loc_1803E94C6
0x1803e9354  lea     rbx, ?Create@?$TypedArray@N$0A@$0A@@Js@@SAPEAXPEAVArrayBufferBase@2@IIPEAVJavascriptLibrary@2@@Z; Js::TypedArray<double,0,0>::Create(Js::ArrayBufferBase *,uint,uint,Js::JavascriptLibrary *)
0x1803e935b  jmp     short loc_1803E937F
0x1803e935d  lea     rbx, ?Create@?$TypedArray@M$0A@$0A@@Js@@SAPEAXPEAVArrayBufferBase@2@IIPEAVJavascriptLibrary@2@@Z; Js::TypedArray<float,0,0>::Create(Js::ArrayBufferBase *,uint,uint,Js::JavascriptLibrary *)
0x1803e9364  jmp     short loc_1803E937F
0x1803e9366  lea     rbx, ?Create@?$TypedArray@_K$0A@$0A@@Js@@SAPEAXPEAVArrayBufferBase@2@IIPEAVJavascriptLibrary@2@@Z; Js::TypedArray<unsigned __int64,0,0>::Create(Js::ArrayBufferBase *,uint,uint,Js::JavascriptLibrary *)
0x1803e936d  jmp     short loc_1803E937F
0x1803e936f  lea     rbx, ?Create@?$TypedArray@_J$0A@$0A@@Js@@SAPEAXPEAVArrayBufferBase@2@IIPEAVJavascriptLibrary@2@@Z; Js::TypedArray<__int64,0,0>::Create(Js::ArrayBufferBase *,uint,uint,Js::JavascriptLibrary *)
0x1803e9376  jmp     short loc_1803E937F
0x1803e9378  lea     rbx, ?Create@?$TypedArray@I$0A@$0A@@Js@@SAPEAXPEAVArrayBufferBase@2@IIPEAVJavascriptLibrary@2@@Z; Js::TypedArray<uint,0,0>::Create(Js::ArrayBufferBase *,uint,uint,Js::JavascriptLibrary *)
0x1803e937f  mov     r14, [r14+18h]
0x1803e9383  mov     edi, [rsp+0A8h+arg_18]
0x1803e938a  mov     eax, edi
0x1803e938c  imul    rax, r14
0x1803e9390  mov     ecx, 0FFFFFFFFh
0x1803e9395  cmp     rax, rcx
0x1803e9398  ja      loc_1803E9515
0x1803e939e  mov     dword ptr [rsp+0A8h+var_68], 0
0x1803e93a6  mov     esi, r14d
0x1803e93a9  imul    esi, edi
0x1803e93ac  cmp     [rsp+0A8h+arg_28], 0
0x1803e93b4  jnz     loc_1803E946A
0x1803e93ba  mov     edx, esi; unsigned int
0x1803e93bc  mov     rcx, [r15+8]; this
0x1803e93c0  call    ?CreateProjectionArraybuffer@JavascriptLibrary@Js@@QEAAPEAVArrayBuffer@2@I@Z; Js::JavascriptLibrary::CreateProjectionArraybuffer(uint)
0x1803e93c5  mov     r13, rax
0x1803e93c8  mov     rcx, [rax]
0x1803e93cb  mov     rax, [rcx+348h]
0x1803e93d2  mov     rcx, r13
0x1803e93d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803e93da  mov     r15, rax
0x1803e93dd  test    esi, esi
0x1803e93df  jz      short loc_1803E93EA
0x1803e93e1  test    rax, rax
0x1803e93e4  jz      loc_1803E9515
0x1803e93ea  mov     eax, esi
0x1803e93ec  mov     rcx, r15; void *
0x1803e93ef  cmp     [rsp+0A8h+arg_38], 0
0x1803e93f7  jz      short loc_1803E945E
0x1803e93f9  mov     r12d, [rsp+0A8h+arg_20]
0x1803e9401  mov     esi, r12d
0x1803e9404  imul    rsi, r14
0x1803e9408  mov     r9, rsi; SourceSize
0x1803e940b  mov     r8, [rsp+0A8h+Source]; Source
0x1803e9413  mov     edx, eax; DestinationSize
0x1803e9415  call    cs:__imp_memcpy_s
0x1803e941c  nop     dword ptr [rax+rax+00h]
0x1803e9421  cmp     edi, r12d
0x1803e9424  jbe     short loc_1803E943B
0x1803e9426  mov     r8d, edi
0x1803e9429  sub     r8d, r12d
0x1803e942c  imul    r8, r14; Size
0x1803e9430  lea     rcx, [rsi+r15]; void *
0x1803e9434  xor     edx, edx; Val
0x1803e9436  call    memset_0
0x1803e943b  mov     r12, [rsp+0A8h+arg_30]
0x1803e9443  mov     r9, [rsp+0A8h+var_58]
0x1803e9448  mov     r8d, edi
0x1803e944b  xor     edx, edx
0x1803e944d  mov     rcx, r13
0x1803e9450  mov     rax, rbx
0x1803e9453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803e9458  mov     [r12], rax
0x1803e945c  jmp     short loc_1803E94BD
0x1803e945e  mov     r8, rax; Size
0x1803e9461  xor     edx, edx; Val
0x1803e9463  call    memset_0
0x1803e9468  jmp     short loc_1803E9443
0x1803e946a  mov     ecx, [rsp+0A8h+arg_20]
0x1803e9471  cmp     edi, ecx
0x1803e9473  jbe     short loc_1803E9497
0x1803e9475  mov     r8d, edi
0x1803e9478  sub     r8d, ecx
0x1803e947b  imul    r8, r14; Size
0x1803e947f  imul    rcx, r14
0x1803e9483  mov     r14, [rsp+0A8h+Source]
0x1803e948b  add     rcx, r14; void *
0x1803e948e  xor     edx, edx; Val
0x1803e9490  call    memset_0
0x1803e9495  jmp     short loc_1803E949F
0x1803e9497  mov     r14, [rsp+0A8h+Source]
0x1803e949f  mov     r8d, esi; unsigned int
0x1803e94a2  mov     rdx, r14; unsigned __int8 *
0x1803e94a5  mov     rcx, [r15+8]; this
0x1803e94a9  call    ?CreateProjectionArraybuffer@JavascriptLibrary@Js@@QEAAPEAVArrayBuffer@2@PEAEI@Z; Js::JavascriptLibrary::CreateProjectionArraybuffer(uchar *,uint)
0x1803e94ae  mov     r13, rax
0x1803e94b1  jmp     short loc_1803E9443
0x1803e94b3  jmp     short loc_1803E94BD
0x1803e94b5  jmp     short loc_1803E94BD
0x1803e94b7  jmp     short loc_1803E94BD
0x1803e94b9  jmp     short loc_1803E94BD
0x1803e94bb  jmp     short $+2
0x1803e94bd  mov     eax, dword ptr [rsp+0A8h+var_68]
0x1803e94c1  jmp     loc_1803E96FA
0x1803e94c6  lea     r8, [rsp+0A8h+var_60]; struct Projection::ArrayProjection **
0x1803e94cb  mov     rdx, r13; struct Projection::ProjectionContext *
0x1803e94ce  mov     rcx, r14; struct ProjectionModel::ConcreteType *
0x1803e94d1  call    ?EnsureProjection@ArrayProjection@Projection@@SAJPEBUConcreteType@ProjectionModel@@PEAVProjectionContext@2@PEAPEAV12@@Z; Projection::ArrayProjection::EnsureProjection(ProjectionModel::ConcreteType const *,Projection::ProjectionContext *,Projection::ArrayProjection * *)
0x1803e94d6  test    eax, eax
0x1803e94d8  js      loc_1803E96FA
0x1803e94de  mov     r15, [r14+18h]
0x1803e94e2  cmp     [rsp+0A8h+arg_28], 0
0x1803e94ea  jnz     loc_1803E962A
0x1803e94f0  mov     edi, [rsp+0A8h+arg_18]
0x1803e94f7  mov     r12d, edi
0x1803e94fa  imul    r12, r15
0x1803e94fe  mov     rcx, r12; cb
0x1803e9501  call    cs:__imp_CoTaskMemAlloc
0x1803e9508  nop     dword ptr [rax+rax+00h]
0x1803e950d  mov     rsi, rax
0x1803e9510  test    rax, rax
0x1803e9513  jnz     short loc_1803E951F
0x1803e9515  mov     eax, 8007000Eh
0x1803e951a  jmp     loc_1803E96FA
0x1803e951f  cmp     [rsp+0A8h+arg_38], 0
0x1803e9527  jz      loc_1803E9613
0x1803e952d  mov     rcx, r14; struct ProjectionModel::Type *
0x1803e9530  call    ?IsBlittable@ConcreteType@ProjectionModel@@SA_NPEBUType@2@@Z; ProjectionModel::ConcreteType::IsBlittable(ProjectionModel::Type const *)
0x1803e9535  mov     ebx, [rsp+0A8h+arg_20]
0x1803e953c  test    al, al
0x1803e953e  jz      short loc_1803E9579
0x1803e9540  imul    rbx, r15
0x1803e9544  mov     r9, rbx; SourceSize
0x1803e9547  mov     r8, [rsp+0A8h+Source]; Source
0x1803e954f  mov     rdx, r12; DestinationSize
0x1803e9552  mov     rcx, rsi; Destination
0x1803e9555  call    cs:__imp_memcpy_s
0x1803e955c  nop     dword ptr [rax+rax+00h]
0x1803e9561  mov     r8d, edi
0x1803e9564  sub     r8d, [rsp+0A8h+arg_20]
0x1803e956c  imul    r8, r15
0x1803e9570  lea     rcx, [rbx+rsi]
0x1803e9574  jmp     loc_1803E9619
0x1803e9579  xor     r12d, r12d
0x1803e957c  test    ebx, ebx
0x1803e957e  jz      short loc_1803E95F9
0x1803e9580  mov     [rsp+0A8h+var_58], 0
0x1803e9589  lea     rax, [rsp+0A8h+var_68]
0x1803e958e  mov     [rsp+0A8h+var_70], rax; int *
0x1803e9593  lea     rax, [rsp+0A8h+var_58]
0x1803e9598  mov     [rsp+0A8h+var_78], rax; void **
0x1803e959d  mov     rax, [rsp+0A8h+var_60]
0x1803e95a2  mov     ecx, [rax+28h]
0x1803e95a5  mov     dword ptr [rsp+0A8h+var_80], ecx; int
0x1803e95a9  mov     [rsp+0A8h+var_88], r12d; unsigned int
0x1803e95ae  mov     r9, r14; struct ProjectionModel::ConcreteType *
0x1803e95b1  mov     r8, r13; struct Projection::ProjectionContext *
0x1803e95b4  mov     edx, edi; unsigned int
0x1803e95b6  mov     rcx, [rsp+0A8h+Source]; unsigned __int8 *
0x1803e95be  call    ?GetItemAt@ArrayObjectInstance@Projection@@SAJPEAEIPEAVProjectionContext@2@PEBUConcreteType@ProjectionModel@@IHPEAPEAXPEAH@Z; Projection::ArrayObjectInstance::GetItemAt(uchar *,uint,Projection::ProjectionContext *,ProjectionModel::ConcreteType const *,uint,int,void * *,int *)
0x1803e95c3  lea     rax, [rsp+0A8h+var_68]
0x1803e95c8  mov     [rsp+0A8h+var_70], rax; int *
0x1803e95cd  mov     byte ptr [rsp+0A8h+var_78], 0; bool
0x1803e95d2  mov     rax, [rsp+0A8h+var_58]
0x1803e95d7  mov     [rsp+0A8h+var_80], rax; void *
0x1803e95dc  mov     [rsp+0A8h+var_88], r12d; unsigned int
0x1803e95e1  mov     r9, r14; struct ProjectionModel::ConcreteType *
0x1803e95e4  mov     r8, r13; struct Projection::ProjectionContext *
0x1803e95e7  mov     edx, edi; unsigned int
0x1803e95e9  mov     rcx, rsi; unsigned __int8 *
0x1803e95ec  call    ?SetItemAt@ArrayObjectInstance@Projection@@SAJPEAEIPEAVProjectionContext@2@PEBUConcreteType@ProjectionModel@@IPEAX_NPEAH@Z; Projection::ArrayObjectInstance::SetItemAt(uchar *,uint,Projection::ProjectionContext *,ProjectionModel::ConcreteType const *,uint,void *,bool,int *)
0x1803e95f1  inc     r12d
0x1803e95f4  cmp     r12d, ebx
0x1803e95f7  jb      short loc_1803E9580
0x1803e95f9  cmp     edi, ebx
0x1803e95fb  jbe     short loc_1803E9620
0x1803e95fd  mov     r8d, edi
0x1803e9600  sub     r8d, ebx
0x1803e9603  imul    r8, r15
0x1803e9607  mov     rcx, rbx
0x1803e960a  imul    rcx, r15
0x1803e960e  add     rcx, rsi
0x1803e9611  jmp     short loc_1803E9619
0x1803e9613  mov     r8, r12; Size
0x1803e9616  mov     rcx, rsi; void *
0x1803e9619  xor     edx, edx; Val
0x1803e961b  call    memset_0
0x1803e9620  mov     r12, [rsp+0A8h+arg_30]
0x1803e9628  jmp     short loc_1803E965C
0x1803e962a  mov     edi, [rsp+0A8h+arg_18]
0x1803e9631  mov     ecx, [rsp+0A8h+arg_20]
0x1803e9638  mov     rsi, [rsp+0A8h+Source]
0x1803e9640  cmp     edi, ecx
0x1803e9642  jbe     short loc_1803E965C
0x1803e9644  mov     r8d, edi
0x1803e9647  sub     r8d, ecx
0x1803e964a  imul    r8, r15; Size
0x1803e964e  imul    rcx, r15
0x1803e9652  add     rcx, rsi; void *
0x1803e9655  xor     edx, edx; Val
0x1803e9657  call    memset_0
0x1803e965c  mov     [rsp+0A8h+var_68], 0
0x1803e9665  lea     rax, [rsp+0A8h+var_68]
0x1803e966a  mov     [rsp+0A8h+var_78], rax; struct Projection::ArrayObjectInstance **
0x1803e966f  mov     [rsp+0A8h+var_80], r13; struct Projection::ProjectionContext *
0x1803e9674  mov     [rsp+0A8h+var_88], edi; unsigned int
0x1803e9678  mov     r9, rsi; unsigned __int8 *
0x1803e967b  mov     r8, r14; struct ProjectionModel::ConcreteType *
0x1803e967e  mov     rcx, [rsp+0A8h+var_60]
0x1803e9683  mov     edx, [rcx+28h]; int
0x1803e9686  mov     rcx, [rcx+20h]; void *
0x1803e968a  call    ?Create@ArrayObjectInstance@Projection@@SAJPEAXHPEBUConcreteType@ProjectionModel@@PEAEIPEAVProjectionContext@2@PEAPEAV12@@Z; Projection::ArrayObjectInstance::Create(void *,int,ProjectionModel::ConcreteType const *,uchar *,uint,Projection::ProjectionContext *,Projection::ArrayObjectInstance * *)
0x1803e968f  test    eax, eax
0x1803e9691  js      short loc_1803E96FA
0x1803e9693  mov     rbx, [rsp+0A8h+var_68]
0x1803e9698  test    byte ptr cs:Microsoft_JScriptEnableBits+1, 40h
0x1803e969f  jz      short loc_1803E96CB
0x1803e96a1  mov     rdx, [rbx+8]
0x1803e96a5  mov     edx, [rdx+38h]; struct Js::ScriptContext *
0x1803e96a8  mov     rcx, [rsp+0A8h+var_50]; this
0x1803e96ad  call    ?StringOfId@Projection@@YAPEBGPEAVScriptContext@Js@@H@Z; Projection::StringOfId(Js::ScriptContext *,int)
0x1803e96b2  mov     r9, rax
0x1803e96b5  mov     r8, rbx
0x1803e96b8  lea     rdx, JSCRIPT_RECYCLER_ALLOCATE_WINRT_TYPEDARRAY_OBJECT
0x1803e96bf  lea     rcx, PROVIDER_JSCRIPT9_Context
0x1803e96c6  call    McTemplateU0pz_EventWriteTransfer
0x1803e96cb  mov     ecx, edi; unsigned int
0x1803e96cd  call    ?ToVar@JavascriptNumber@Js@@SAPEAXIPEAVScriptContext@2@@Z; Js::JavascriptNumber::ToVar(uint,Js::ScriptContext *)
0x1803e96d2  mov     r8, rax
0x1803e96d5  xor     eax, eax
0x1803e96d7  mov     byte ptr [rsp+0A8h+var_78], al
0x1803e96db  mov     dword ptr [rsp+0A8h+var_80], eax
0x1803e96df  mov     qword ptr [rsp+0A8h+var_88], rax
0x1803e96e4  xor     r9d, r9d
0x1803e96e7  mov     edx, 0C1h
0x1803e96ec  mov     rcx, rbx
0x1803e96ef  call    ?SetPropertyWithAttributes@CustomExternalObject@Js@@UEAAHHPEAXEPEAVPropertyValueInfo@2@W4PropertyOperationFlags@2@W4SideEffects@2@@Z; Js::CustomExternalObject::SetPropertyWithAttributes(int,void *,uchar,Js::PropertyValueInfo *,Js::PropertyOperationFlags,Js::SideEffects)
0x1803e96f4  mov     [r12], rbx
0x1803e96f8  xor     eax, eax
0x1803e96fa  add     rsp, 70h
0x1803e96fe  pop     r15
0x1803e9700  pop     r14
0x1803e9702  pop     r13
0x1803e9704  pop     r12
  ... truncated ...
```
