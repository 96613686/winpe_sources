# ContainerAction::compileInclude(Processor *,Element *,InheritAttrs *,bool)

- ea: `0x1800b1d44`
- end: `0x1800b205b`
- name: `?compileInclude@ContainerAction@@AEAAXPEAVProcessor@@PEAVElement@@PEAVInheritAttrs@@_N@Z`
- size: `791`
- prototype: `void(ContainerAction *__hidden this, struct Processor *, struct Element *, struct InheritAttrs *, bool)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x1800b25cc`

## callees

- `0x180012000`
- `0x180023f84`
- `0x18004aae0`
- `0x18004abb8`
- `0x180052cb4`
- `0x180064034`
- `0x1800a6d38`
- `0x1800a9284`
- `0x1800a9a00`
- `0x1800ace24`
- `0x1800acec4`
- `0x1800b06e0`
- `0x1800b1d44`
- `0x1800b2450`
- `0x1800b3934`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x1800b1f5f`
- `msvcrt!_resetstkoflw` at `0x1800b1f5f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b1fb2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b1fb2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800b1f4d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800b1fde`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800b1f4d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800b1fde`

## pseudocode

```c
void __fastcall ContainerAction::compileInclude(
        ContainerAction *this,
        struct IUnknown **a2,
        struct Element *a3,
        struct InheritAttrs *a4,
        bool a5)
{
  struct String *v9; // r14
  bool v10; // bl
  struct Processor *v11; // rdx
  XTLFunction *v12; // rcx
  struct Element *v13; // r9
  struct Object *v14; // rbx
  struct Object *v15; // rax
  struct Document *v16; // rax
  struct Element *ChildDocument; // rsi
  struct InheritAttrs *v18; // r9
  struct IUnknown *v19; // [rsp+30h] [rbp-88h]
  struct NamespaceMgr *v20; // [rsp+38h] [rbp-80h]
  _BYTE v21[24]; // [rsp+40h] [rbp-78h] BYREF
  __int64 v22; // [rsp+58h] [rbp-60h]
  struct Object *v23; // [rsp+68h] [rbp-50h]
  struct String *v24; // [rsp+70h] [rbp-48h]
  struct IUnknown **v25; // [rsp+78h] [rbp-40h]
  bool v26; // [rsp+80h] [rbp-38h]
  struct String *v27; // [rsp+C8h] [rbp+10h]
  struct IUnknown *v28; // [rsp+D8h] [rbp+20h]

  v9 = 0;
  v10 = (*((_DWORD *)a4 + 11) & 4) != 0;
  AttributeEnum::AttributeEnum((AttributeEnum *)v21, a3);
  v25 = a2;
  v26 = v10;
  while ( CompileAttributes::nextLocalAttribute((CompileAttributes *)v21) )
  {
    if ( v23 == XTLKeywords::s_nmHRef )
    {
      v9 = v24;
    }
    else if ( (*((_DWORD *)a4 + 11) & 4) == 0 )
    {
      v14 = (struct Object *)(*(__int64 (__fastcall **)(struct Element *))(*(_QWORD *)a3 + 136LL))(a3);
      v15 = (struct Object *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 136LL))(v22);
      Processor::Error(-1072897234, v15, v14, 0);
    }
  }
  if ( !v9 )
    Processor::Error(-1072898016, XTLKeywords::s_nmHRef, 0, 0);
  XTLFunction::checkEmpty(v12, v11, a3, v13);
  if ( (*(_DWORD *)(((__int64 (__fastcall *)(struct IUnknown *))a2[181]->lpVtbl[16].Release)(a2[181]) + 200) & 0x800) != 0 )
  {
    v27 = DocumentManager::calcAbsoluteURI(a3, v9, 0);
    v16 = (struct Document *)(*(__int64 (__fastcall **)(struct Element *))(*(_QWORD *)a3 + 400LL))(a3);
    ChildDocument = ImportManager::loadChildDocument((ImportManager *)(a2 + 115), (struct Processor *)a2, v16, v27, a5);
    v28 = a2[135];
    v19 = a2[136];
    assign(a2 + 135, 0);
    assign(a2 + 136, 0);
    v20 = Processor::replaceNamespaceMgr((Processor *)a2, 0);
    ContainerAction::compileStylesheetElement(this, (struct Processor *)a2, ChildDocument, v18);
    ImportManager::doneLoading((ImportManager *)(a2 + 115), v27, a5);
    assign(a2 + 135, v28);
    assign(a2 + 136, v19);
    Processor::replaceNamespaceMgr((Processor *)a2, v20);
  }
}

```

## disassembly

```asm
0x1800b1d44  mov     [rsp+arg_0], rbx
0x1800b1d49  mov     [rsp+arg_10], rsi
0x1800b1d4e  push    rdi
0x1800b1d4f  push    r12
0x1800b1d51  push    r13
0x1800b1d53  push    r14
0x1800b1d55  push    r15
0x1800b1d57  sub     rsp, 90h
0x1800b1d5e  mov     r15, r9
0x1800b1d61  mov     rsi, r8
0x1800b1d64  mov     rdi, rdx
0x1800b1d67  mov     r12, rcx
0x1800b1d6a  xor     r14d, r14d
0x1800b1d6d  mov     ebx, [r9+2Ch]
0x1800b1d71  shr     ebx, 2
0x1800b1d74  mov     r13b, 1
0x1800b1d77  and     bl, r13b
0x1800b1d7a  mov     rdx, r8; struct Element *
0x1800b1d7d  lea     rcx, [rsp+0B8h+var_78]; this
0x1800b1d82  call    ??0AttributeEnum@@QEAA@PEAVElement@@@Z; AttributeEnum::AttributeEnum(Element *)
0x1800b1d87  mov     [rsp+0B8h+var_40], rdi
0x1800b1d8c  mov     [rsp+0B8h+var_38], bl
0x1800b1d93  lea     rcx, [rsp+0B8h+var_78]; this
0x1800b1d98  call    ?nextLocalAttribute@CompileAttributes@@QEAA_NXZ; CompileAttributes::nextLocalAttribute(void)
0x1800b1d9d  test    al, al
0x1800b1d9f  jz      short loc_1800B1DFF
0x1800b1da1  mov     rax, cs:?s_nmHRef@XTLKeywords@@2V?$_staticreference@VName@@@@A; _staticreference<Name> XTLKeywords::s_nmHRef
0x1800b1da8  cmp     [rsp+0B8h+var_50], rax
0x1800b1dad  jnz     short loc_1800B1DB6
0x1800b1daf  mov     r14, [rsp+0B8h+var_48]
0x1800b1db4  jmp     short loc_1800B1D93
0x1800b1db6  mov     eax, [r15+2Ch]
0x1800b1dba  shr     eax, 2
0x1800b1dbd  test    r13b, al
0x1800b1dc0  jnz     short loc_1800B1D93
0x1800b1dc2  mov     rax, [rsi]
0x1800b1dc5  mov     rcx, rsi
0x1800b1dc8  mov     rax, [rax+88h]
0x1800b1dcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1dd4  mov     rbx, rax
0x1800b1dd7  mov     rcx, [rsp+0B8h+var_60]
0x1800b1ddc  mov     rdx, [rcx]
0x1800b1ddf  mov     rax, [rdx+88h]
0x1800b1de6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1deb  xor     r9d, r9d; struct Object *
0x1800b1dee  mov     r8, rbx; struct Object *
0x1800b1df1  mov     rdx, rax; struct Object *
0x1800b1df4  mov     ecx, 0C00CE32Eh; int
0x1800b1df9  call    ?Error@Processor@@SAXJPEAVObject@@00@Z; Processor::Error(long,Object *,Object *,Object *)
0x1800b1dff  test    r14, r14
0x1800b1e02  jnz     short loc_1800B1E1C
0x1800b1e04  xor     r9d, r9d; struct Object *
0x1800b1e07  xor     r8d, r8d; struct Object *
0x1800b1e0a  mov     rdx, cs:?s_nmHRef@XTLKeywords@@2V?$_staticreference@VName@@@@A; struct Object *
0x1800b1e11  mov     ecx, 0C00CE020h; int
0x1800b1e16  call    ?Error@Processor@@SAXJPEAVObject@@00@Z; Processor::Error(long,Object *,Object *,Object *)
0x1800b1e1c  mov     r8, rsi; struct InheritAttrs *
0x1800b1e1f  call    ?checkEmpty@XTLFunction@@YAXPEAVProcessor@@PEAVInheritAttrs@@PEAVElement@@@Z; XTLFunction::checkEmpty(Processor *,InheritAttrs *,Element *)
0x1800b1e24  mov     rcx, [rdi+5A8h]
0x1800b1e2b  mov     rax, [rcx]
0x1800b1e2e  mov     rax, [rax+190h]
0x1800b1e35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1e3a  mov     ecx, [rax+0C8h]
0x1800b1e40  shr     ecx, 0Bh
0x1800b1e43  test    r13b, cl
0x1800b1e46  jz      loc_1800B1F2A
0x1800b1e4c  xor     r8d, r8d; bool
0x1800b1e4f  mov     rdx, r14; struct String *
0x1800b1e52  mov     rcx, rsi; struct Element *
0x1800b1e55  call    ?calcAbsoluteURI@DocumentManager@@SAPEAVString@@PEAVElement@@PEAV2@_N@Z; DocumentManager::calcAbsoluteURI(Element *,String *,bool)
0x1800b1e5a  mov     r14, rax
0x1800b1e5d  mov     [rsp+0B8h+arg_8], rax
0x1800b1e65  lea     r13, [rdi+398h]
0x1800b1e6c  mov     rcx, [rsi]
0x1800b1e6f  mov     rax, [rcx+190h]
0x1800b1e76  mov     rcx, rsi
0x1800b1e79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1e7e  mov     cl, [rsp+0B8h+arg_20]
0x1800b1e85  mov     byte ptr [rsp+0B8h+var_98], cl; bool
0x1800b1e89  mov     r9, r14; struct String *
0x1800b1e8c  mov     r8, rax; struct Document *
0x1800b1e8f  mov     rdx, rdi; struct Processor *
0x1800b1e92  mov     rcx, r13; this
0x1800b1e95  call    ?loadChildDocument@ImportManager@@QEAAPEAVElement@@PEAVProcessor@@PEAVDocument@@PEAVString@@_N@Z; ImportManager::loadChildDocument(Processor *,Document *,String *,bool)
0x1800b1e9a  mov     rsi, rax
0x1800b1e9d  lea     rbx, [rdi+438h]
0x1800b1ea4  mov     rax, [rbx]
0x1800b1ea7  mov     [rsp+0B8h+arg_18], rax
0x1800b1eaf  lea     r15, [rbx+8]
0x1800b1eb3  mov     rax, [r15]
0x1800b1eb6  mov     [rsp+0B8h+var_88], rax
0x1800b1ebb  xor     edx, edx; void *
0x1800b1ebd  mov     rcx, rbx; struct IUnknown **
0x1800b1ec0  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800b1ec5  xor     edx, edx; void *
0x1800b1ec7  mov     rcx, r15; struct IUnknown **
0x1800b1eca  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800b1ecf  xor     edx, edx; struct NamespaceMgr *
0x1800b1ed1  mov     rcx, rdi; this
0x1800b1ed4  call    ?replaceNamespaceMgr@Processor@@QEAAPEAVNamespaceMgr@@PEAV2@@Z; Processor::replaceNamespaceMgr(NamespaceMgr *)
0x1800b1ed9  mov     [rsp+0B8h+var_80], rax
0x1800b1ede  mov     r8, rsi; struct Element *
0x1800b1ee1  mov     rdx, rdi; struct Processor *
0x1800b1ee4  mov     rcx, r12; this
0x1800b1ee7  call    ?compileStylesheetElement@ContainerAction@@IEAAXPEAVProcessor@@PEAVElement@@PEAVInheritAttrs@@@Z; ContainerAction::compileStylesheetElement(Processor *,Element *,InheritAttrs *)
0x1800b1eec  nop
0x1800b1eed  mov     r8b, [rsp+0B8h+arg_20]; bool
0x1800b1ef5  mov     rdx, r14; struct String *
0x1800b1ef8  mov     rcx, r13; this
0x1800b1efb  call    ?doneLoading@ImportManager@@QEAAXPEAVString@@_N@Z; ImportManager::doneLoading(String *,bool)
0x1800b1f00  mov     rdx, [rsp+0B8h+arg_18]; void *
0x1800b1f08  mov     rcx, rbx; struct IUnknown **
0x1800b1f0b  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800b1f10  mov     rdx, [rsp+0B8h+var_88]; void *
0x1800b1f15  mov     rcx, r15; struct IUnknown **
0x1800b1f18  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800b1f1d  mov     rdx, [rsp+0B8h+var_80]; struct NamespaceMgr *
0x1800b1f22  mov     rcx, rdi; this
0x1800b1f25  call    ?replaceNamespaceMgr@Processor@@QEAAPEAVNamespaceMgr@@PEAV2@@Z; Processor::replaceNamespaceMgr(NamespaceMgr *)
0x1800b1f2a  lea     r11, [rsp+0B8h+var_28]
0x1800b1f32  mov     rbx, [r11+30h]
0x1800b1f36  mov     rsi, [r11+40h]
0x1800b1f3a  mov     rsp, r11
0x1800b1f3d  pop     r15
0x1800b1f3f  pop     r14
0x1800b1f41  pop     r13
0x1800b1f43  pop     r12
0x1800b1f45  pop     rdi
0x1800b1f46  retn
0x1800b1f47  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x1800b1f4d  call    cs:__imp_TlsGetValue
0x1800b1f53  mov     rbx, rax
0x1800b1f56  cmp     dword ptr [rax+54h], 0C00000FDh
0x1800b1f5d  jnz     short loc_1800B1FD8
0x1800b1f5f  call    cs:__imp__resetstkoflw
0x1800b1f65  test    eax, eax
0x1800b1f67  jnz     short loc_1800B1FBA
0x1800b1f69  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x1800b1f70  test    rcx, rcx
0x1800b1f73  jz      short loc_1800B1F87
0x1800b1f75  cmp     [rcx+50h], rbx
0x1800b1f79  jnz     short loc_1800B1F87
0x1800b1f7b  mov     rax, [rcx]
0x1800b1f7e  mov     rax, [rax+20h]
0x1800b1f82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1f87  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x1800b1f8e  test    rcx, rcx
0x1800b1f91  jz      short loc_1800B1FA5
0x1800b1f93  cmp     [rcx+50h], rbx
0x1800b1f97  jnz     short loc_1800B1FA5
0x1800b1f99  mov     rax, [rcx]
0x1800b1f9c  mov     rax, [rax+20h]
0x1800b1fa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1fa5  xor     r9d, r9d; lpArguments
0x1800b1fa8  xor     r8d, r8d; nNumberOfArguments
0x1800b1fab  xor     edx, edx; dwExceptionFlags
0x1800b1fad  mov     ecx, 0C00000FDh; dwExceptionCode
0x1800b1fb2  call    cs:__imp_RaiseException
0x1800b1fb8  jmp     short loc_1800B1FD8
0x1800b1fba  mov     rax, [rbx+60h]
0x1800b1fbe  mov     [rbx+68h], rax
0x1800b1fc2  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x1800b1fc9  mov     [rbx+60h], rax
0x1800b1fcd  mov     dword ptr [rbx+54h], 800703E9h
0x1800b1fd4  mov     byte ptr [rbx+78h], 0
0x1800b1fd8  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x1800b1fde  call    cs:__imp_TlsGetValue
0x1800b1fe4  mov     rbx, [rax+60h]
0x1800b1fe8  cmp     qword ptr [rbx+20h], 0
0x1800b1fed  jnz     short loc_1800B2052
0x1800b1fef  mov     rax, [rbx]
0x1800b1ff2  mov     rcx, rbx
0x1800b1ff5  mov     rax, [rax+88h]
0x1800b1ffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2001  mov     rcx, rax; this
0x1800b2004  call    ?trim@String@@QEAAPEAV1@XZ; String::trim(void)
0x1800b2009  mov     [rsp+0B8h+var_90], 0; struct String *
0x1800b2012  mov     [rsp+0B8h+var_98], 0; struct String *
0x1800b201b  mov     r9, [rsp+0B8h+arg_8]; struct String *
0x1800b2023  mov     r8, rax; struct String *
0x1800b2026  mov     edx, 0C00CE32Dh; int
0x1800b202b  mov     ecx, 80004005h; int
0x1800b2030  call    ?_buildException@Exception@@KAPEAV1@JJPEAVString@@000@Z; Exception::_buildException(long,long,String *,String *,String *,String *)
0x1800b2035  mov     rbx, rax
0x1800b2038  mov     rcx, [rax]
0x1800b203b  mov     rax, [rcx+98h]
0x1800b2042  mov     rdx, [rsp+0B8h+arg_8]
0x1800b204a  mov     rcx, rbx
0x1800b204d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2052  mov     rcx, rbx; struct Exception *
0x1800b2055  call    ?raiseException@Exception@@KAXPEAV1@@Z; Exception::raiseException(Exception *)
0x1800b205a  nop
0x180103974  push    rbp
0x180103976  sub     rsp, 30h
0x18010397a  mov     rbp, rdx
0x18010397d  xor     edx, edx; bool
0x18010397f  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@_N@Z
0x180103984  nop
0x180103985  add     rsp, 30h
0x180103989  pop     rbp
0x18010398a  retn
```
