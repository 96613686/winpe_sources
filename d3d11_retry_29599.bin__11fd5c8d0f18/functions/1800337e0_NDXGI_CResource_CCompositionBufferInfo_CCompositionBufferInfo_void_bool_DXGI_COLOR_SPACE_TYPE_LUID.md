# NDXGI::CResource::CCompositionBufferInfo::CCompositionBufferInfo(void *,bool,DXGI_COLOR_SPACE_TYPE,_LUID)

- ea: `0x1800337e0`
- end: `0x18003390e`
- name: `??0CCompositionBufferInfo@CResource@NDXGI@@QEAA@PEAX_NW4DXGI_COLOR_SPACE_TYPE@@U_LUID@@@Z`
- size: `302`
- prototype: `__int64 __fastcall(NDXGI::CResource::CCompositionBufferInfo *__hidden this, void *, bool, enum DXGI_COLOR_SPACE_TYPE, struct _LUID)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180032ff0`

## callees

- `0x180022400`
- `0x1800229a0`
- `0x1800337e0`
- `0x1800a9d20`
- `0x1800aa9a8`

## import_xrefs

- `win32u!NtBindCompositionSurface` at `0x1800338cb`
- `win32u!NtBindCompositionSurface` at `0x1800338cb`
- `ext-ms-onecore-dcomp-l1-1-0!DCompositionCreateSurfaceHandle` at `0x180033834`
- `ext-ms-onecore-dcomp-l1-1-0!DCompositionCreateSurfaceHandle` at `0x180033834`

## string_xrefs

- `0x180033845`: `DCompositionCreateSurfaceHandle`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
NDXGI::CResource::CCompositionBufferInfo *__fastcall NDXGI::CResource::CCompositionBufferInfo::CCompositionBufferInfo(
        NDXGI::CResource::CCompositionBufferInfo *this,
        void *a2,
        char a3,
        enum DXGI_COLOR_SPACE_TYPE a4,
        struct _LUID a5)
{
  signed int SurfaceHandle; // eax
  bool v10; // r9
  int v11; // edi
  int v12; // eax
  _QWORD v14[7]; // [rsp+48h] [rbp-B8h] BYREF
  enum DXGI_COLOR_SPACE_TYPE v15; // [rsp+80h] [rbp-80h]
  int v16; // [rsp+94h] [rbp-6Ch]
  int v17; // [rsp+E0h] [rbp-20h]
  int v18; // [rsp+E4h] [rbp-1Ch]
  void *v19; // [rsp+E8h] [rbp-18h]
  struct _LUID v20; // [rsp+F0h] [rbp-10h]

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  SurfaceHandle = DCompositionCreateSurfaceHandle(3, 0, this);
  v11 = SurfaceHandle;
  if ( SurfaceHandle < 0 )
    CModule::RecordJournal((CModule *)&g_Module, SurfaceHandle, "DCompositionCreateSurfaceHandle", v10, 1);
  ThrowFailure(v11);
  memset_0(v14, 0, 0x518u);
  v16 = 1;
  v15 = a4;
  v17 = (a3 != 0) + 2;
  v18 = 1;
  v19 = a2;
  v20 = a5;
  v12 = NtBindCompositionSurface(*(_QWORD *)this, 1, 0);
  ThrowFailure(v12 | 0x10000000);
  *((_QWORD *)this + 1) = v14[0];
  return this;
}

```

## disassembly

```asm
0x1800337e0  mov     [rsp-8+arg_8], rbx
0x1800337e5  push    rbp
0x1800337e6  push    rsi
0x1800337e7  push    rdi
0x1800337e8  push    r14
0x1800337ea  push    r15
0x1800337ec  lea     rbp, [rsp-470h]
0x1800337f4  sub     rsp, 570h
0x1800337fb  mov     rax, cs:__security_cookie
0x180033802  xor     rax, rsp
0x180033805  mov     [rbp+490h+var_30], rax
0x18003380c  mov     r15d, r9d
0x18003380f  mov     sil, r8b
0x180033812  mov     r14, rdx
0x180033815  mov     rbx, rcx
0x180033818  mov     [rsp+590h+var_560], rcx
0x18003381d  mov     qword ptr [rcx], 0
0x180033824  mov     qword ptr [rcx+8], 0
0x18003382c  mov     r8, rcx
0x18003382f  xor     edx, edx
0x180033831  lea     ecx, [rdx+3]
0x180033834  call    cs:__imp_DCompositionCreateSurfaceHandle
0x18003383a  mov     edi, eax
0x18003383c  test    eax, eax
0x18003383e  jns     short loc_18003385A
0x180033840  mov     [rsp+590h+var_570], 1; bool
0x180033845  lea     r8, aDcompositioncr_0; "DCompositionCreateSurfaceHandle"
0x18003384c  mov     edx, eax; unsigned int
0x18003384e  lea     rcx, ?g_Module@@3VCModule@@A; this
0x180033855  call    ?RecordJournal@CModule@@QEAAXIPEBD_N1@Z; CModule::RecordJournal(uint,char const *,bool,bool)
0x18003385a  mov     ecx, edi; int
0x18003385c  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180033861  mov     [rsp+590h+var_550], 2
0x18003386a  xor     edx, edx; Val
0x18003386c  mov     r8d, 518h; Size
0x180033872  lea     rcx, [rsp+590h+var_548]; void *
0x180033877  call    memset_0
0x18003387c  mov     [rbp+490h+var_4FC], 1
0x180033883  mov     [rbp+490h+var_510], r15d
0x180033887  neg     sil
0x18003388a  sbb     eax, eax
0x18003388c  neg     eax
0x18003388e  add     eax, 2
0x180033891  mov     [rbp+490h+var_4B0], eax
0x180033894  mov     [rbp+490h+var_4AC], 1
0x18003389b  mov     [rbp+490h+var_4A8], r14
0x18003389f  mov     rax, qword ptr [rbp+490h+arg_20.LowPart]
0x1800338a6  mov     [rbp+490h+var_4A0], rax
0x1800338aa  lea     rax, [rsp+590h+var_548]
0x1800338af  mov     [rsp+590h+var_568], rax
0x1800338b4  lea     rax, [rsp+590h+var_550]
0x1800338b9  mov     qword ptr [rsp+590h+var_570], rax
0x1800338be  xor     r9d, r9d
0x1800338c1  xor     r8d, r8d
0x1800338c4  lea     edx, [r9+1]
0x1800338c8  mov     rcx, [rbx]
0x1800338cb  call    cs:__imp_NtBindCompositionSurface
0x1800338d1  bts     eax, 1Ch
0x1800338d5  mov     ecx, eax; int
0x1800338d7  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800338dc  mov     rcx, [rsp+590h+var_548]
0x1800338e1  mov     [rbx+8], rcx
0x1800338e5  mov     rax, rbx
0x1800338e8  mov     rcx, [rbp+490h+var_30]
0x1800338ef  xor     rcx, rsp; StackCookie
0x1800338f2  call    __security_check_cookie
0x1800338f7  mov     rbx, [rsp+590h+arg_8]
0x1800338ff  add     rsp, 570h
0x180033906  pop     r15
0x180033908  pop     r14
0x18003390a  pop     rdi
0x18003390b  pop     rsi
0x18003390c  pop     rbp
0x18003390d  retn
```
