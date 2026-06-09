# ATL::CComControlBase::OnDrawAdvanced(ATL_DRAWINFO &)

- ea: `0x1803b8870`
- end: `0x1803b8a21`
- name: `?OnDrawAdvanced@CComControlBase@ATL@@UEAAJAEAUATL_DRAWINFO@@@Z`
- size: `433`
- prototype: `__int64 __fastcall(ATL::CComControlBase *__hidden this, struct ATL_DRAWINFO *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1803b0e98`
- `0x1803b7000`
- `0x1803b8870`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `GDI32!RestoreDC` at `0x1803b89f8`
- `GDI32!RestoreDC` at `0x1803b89f8`
- `GDI32!SetViewportOrgEx` at `0x1803b89aa`
- `GDI32!SetViewportOrgEx` at `0x1803b89aa`
- `GDI32!SetWindowOrgEx` at `0x1803b8998`
- `GDI32!SetWindowOrgEx` at `0x1803b8998`
- `GDI32!SetMapMode` at `0x1803b8986`
- `GDI32!SetMapMode` at `0x1803b8986`
- `GDI32!SaveDC` at `0x1803b8977`
- `GDI32!SaveDC` at `0x1803b8977`
- `GDI32!GetDeviceCaps` at `0x1803b88fd`
- `GDI32!GetDeviceCaps` at `0x1803b894b`
- `GDI32!GetDeviceCaps` at `0x1803b88fd`
- `GDI32!GetDeviceCaps` at `0x1803b894b`
- `GDI32!LPtoDP` at `0x1803b896d`
- `GDI32!LPtoDP` at `0x1803b896d`
- `GDI32!DeleteDC` at `0x1803b89e7`
- `GDI32!DeleteDC` at `0x1803b89e7`
- `GDI32!CreateDCW` at `0x1803b88dd`
- `GDI32!CreateDCW` at `0x1803b8917`
- `GDI32!CreateDCW` at `0x1803b88dd`
- `GDI32!CreateDCW` at `0x1803b8917`

## pseudocode

```c
__int64 __fastcall ATL::CComControlBase::OnDrawAdvanced(ATL::CComControlBase *this, struct ATL_DRAWINFO *a2)
{
  int v4; // ebp
  unsigned __int16 *v5; // rax
  const DEVMODEW *v6; // r9
  HDC DCW; // rax
  HDC *v8; // rsi
  HDC v9; // rdi
  bool v10; // zf
  HDC v11; // rcx
  int v12; // edi
  unsigned int v13; // esi
  __int64 v15; // [rsp+20h] [rbp-48h] BYREF
  struct tagPOINT pt[2]; // [rsp+28h] [rbp-40h] BYREF

  v4 = 0;
  if ( *((_QWORD *)a2 + 3) )
    goto LABEL_12;
  v5 = (unsigned __int16 *)*((_QWORD *)a2 + 2);
  v15 = 0;
  if ( v5 )
  {
    if ( v5[5] )
      v6 = (const DEVMODEW *)((char *)v5 + v5[5]);
    else
      v6 = 0;
    DCW = CreateDCW(
            (unsigned __int16 *)((char *)v5 + v5[2]),
            (unsigned __int16 *)((char *)v5 + v5[3]),
            (unsigned __int16 *)((char *)v5 + v5[4]),
            v6);
    v8 = (HDC *)((char *)a2 + 32);
  }
  else
  {
    v8 = (HDC *)((char *)a2 + 32);
    v9 = (HDC)*((_QWORD *)a2 + 4);
    if ( v9 && GetDeviceCaps(v9, 2) != 5 )
      goto LABEL_11;
    DCW = CreateDCW(L"DISPLAY", 0, 0, 0);
  }
  v9 = DCW;
LABEL_11:
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v15);
  v10 = v9 == *v8;
  *((_QWORD *)a2 + 3) = v9;
  LOBYTE(v4) = !v10;
LABEL_12:
  v11 = (HDC)*((_QWORD *)a2 + 4);
  *(_OWORD *)&pt[0].x = *(_OWORD *)*((_QWORD *)a2 + 5);
  if ( GetDeviceCaps(v11, 2) == 5 )
  {
    v12 = 1;
  }
  else
  {
    v12 = 0;
    LPtoDP(*((HDC *)a2 + 4), pt, 2);
    SaveDC(*((HDC *)a2 + 4));
    SetMapMode(*((HDC *)a2 + 4), 1);
    SetWindowOrgEx(*((HDC *)a2 + 4), 0, 0, 0);
    SetViewportOrgEx(*((HDC *)a2 + 4), 0, 0, 0);
    *((_DWORD *)a2 + 14) = 1;
  }
  *((_QWORD *)a2 + 5) = pt;
  ATL::CComControlBase::GetZoomInfo(this, a2);
  v13 = (*(__int64 (__fastcall **)(ATL::CComControlBase *, struct ATL_DRAWINFO *))(*(_QWORD *)this + 32LL))(this, a2);
  if ( v4 )
    DeleteDC(*((HDC *)a2 + 3));
  if ( !v12 )
    RestoreDC(*((HDC *)a2 + 4), -1);
  return v13;
}

```

## disassembly

```asm
0x1803b8870  mov     [rsp+arg_10], rbx
0x1803b8875  push    rbp
0x1803b8876  push    rsi
0x1803b8877  push    rdi
0x1803b8878  push    r14
0x1803b887a  push    r15
0x1803b887c  sub     rsp, 40h
0x1803b8880  mov     rax, cs:__security_cookie
0x1803b8887  xor     rax, rsp
0x1803b888a  mov     [rsp+68h+var_30], rax
0x1803b888f  xor     r15d, r15d
0x1803b8892  mov     rbx, rdx
0x1803b8895  mov     r14, rcx
0x1803b8898  mov     ebp, r15d
0x1803b889b  cmp     [rdx+18h], r15
0x1803b889f  jnz     loc_1803B8935
0x1803b88a5  mov     rax, [rdx+10h]
0x1803b88a9  mov     [rsp+68h+var_48], r15
0x1803b88ae  test    rax, rax
0x1803b88b1  jz      short loc_1803B88E9
0x1803b88b3  cmp     [rax+0Ah], r15w
0x1803b88b8  jnz     short loc_1803B88BF
0x1803b88ba  mov     r9d, r15d
0x1803b88bd  jmp     short loc_1803B88C7
0x1803b88bf  movzx   r9d, word ptr [rax+0Ah]
0x1803b88c4  add     r9, rax; pdm
0x1803b88c7  movzx   r8d, word ptr [rax+8]
0x1803b88cc  movzx   edx, word ptr [rax+6]
0x1803b88d0  add     r8, rax; pszPort
0x1803b88d3  movzx   ecx, word ptr [rax+4]
0x1803b88d7  add     rdx, rax; pwszDevice
0x1803b88da  add     rcx, rax; pwszDriver
0x1803b88dd  call    cs:__imp_CreateDCW
0x1803b88e3  lea     rsi, [rbx+20h]
0x1803b88e7  jmp     short loc_1803B891D
0x1803b88e9  lea     rsi, [rdx+20h]
0x1803b88ed  mov     rdi, [rsi]
0x1803b88f0  test    rdi, rdi
0x1803b88f3  jz      short loc_1803B8908
0x1803b88f5  mov     edx, 2; index
0x1803b88fa  mov     rcx, rdi; hdc
0x1803b88fd  call    cs:__imp_GetDeviceCaps
0x1803b8903  cmp     eax, 5
0x1803b8906  jnz     short loc_1803B8920
0x1803b8908  xor     r9d, r9d; pdm
0x1803b890b  lea     rcx, pwszDriver; "DISPLAY"
0x1803b8912  xor     r8d, r8d; pszPort
0x1803b8915  xor     edx, edx; pwszDevice
0x1803b8917  call    cs:__imp_CreateDCW
0x1803b891d  mov     rdi, rax
0x1803b8920  lea     rcx, [rsp+68h+var_48]
0x1803b8925  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1803b892a  cmp     rdi, [rsi]
0x1803b892d  mov     [rbx+18h], rdi
0x1803b8931  setnz   bpl
0x1803b8935  mov     rax, [rbx+28h]
0x1803b8939  mov     edx, 2; index
0x1803b893e  mov     rcx, [rbx+20h]; hdc
0x1803b8942  movups  xmm0, xmmword ptr [rax]
0x1803b8945  movdqu  xmmword ptr [rsp+68h+pt.x], xmm0
0x1803b894b  call    cs:__imp_GetDeviceCaps
0x1803b8951  cmp     eax, 5
0x1803b8954  jnz     short loc_1803B895B
0x1803b8956  lea     edi, [rax-4]
0x1803b8959  jmp     short loc_1803B89B7
0x1803b895b  mov     rcx, [rbx+20h]; hdc
0x1803b895f  lea     rdx, [rsp+68h+pt]; lppt
0x1803b8964  mov     r8d, 2; c
0x1803b896a  mov     edi, r15d
0x1803b896d  call    cs:__imp_LPtoDP
0x1803b8973  mov     rcx, [rbx+20h]; hdc
0x1803b8977  call    cs:__imp_SaveDC
0x1803b897d  mov     rcx, [rbx+20h]; hdc
0x1803b8981  mov     edx, 1; iMode
0x1803b8986  call    cs:__imp_SetMapMode
0x1803b898c  mov     rcx, [rbx+20h]; hdc
0x1803b8990  xor     r9d, r9d; lppt
0x1803b8993  xor     r8d, r8d; y
0x1803b8996  xor     edx, edx; x
0x1803b8998  call    cs:__imp_SetWindowOrgEx
0x1803b899e  mov     rcx, [rbx+20h]; hdc
0x1803b89a2  xor     r9d, r9d; lppt
0x1803b89a5  xor     r8d, r8d; y
0x1803b89a8  xor     edx, edx; x
0x1803b89aa  call    cs:__imp_SetViewportOrgEx
0x1803b89b0  mov     dword ptr [rbx+38h], 1
0x1803b89b7  lea     rax, [rsp+68h+pt]
0x1803b89bc  mov     rdx, rbx; struct ATL_DRAWINFO *
0x1803b89bf  mov     rcx, r14; this
0x1803b89c2  mov     [rbx+28h], rax
0x1803b89c6  call    ?GetZoomInfo@CComControlBase@ATL@@QEAAXAEAUATL_DRAWINFO@@@Z; ATL::CComControlBase::GetZoomInfo(ATL_DRAWINFO &)
0x1803b89cb  mov     rax, [r14]
0x1803b89ce  mov     rdx, rbx
0x1803b89d1  mov     rcx, r14
0x1803b89d4  mov     rax, [rax+20h]
0x1803b89d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803b89dd  mov     esi, eax
0x1803b89df  test    ebp, ebp
0x1803b89e1  jz      short loc_1803B89ED
0x1803b89e3  mov     rcx, [rbx+18h]; hdc
0x1803b89e7  call    cs:__imp_DeleteDC
0x1803b89ed  test    edi, edi
0x1803b89ef  jnz     short loc_1803B89FE
0x1803b89f1  mov     rcx, [rbx+20h]; hdc
0x1803b89f5  or      edx, 0FFFFFFFFh; nSavedDC
0x1803b89f8  call    cs:__imp_RestoreDC
0x1803b89fe  mov     eax, esi
0x1803b8a00  mov     rcx, [rsp+68h+var_30]
0x1803b8a05  xor     rcx, rsp; StackCookie
0x1803b8a08  call    __security_check_cookie
0x1803b8a0d  mov     rbx, [rsp+68h+arg_10]
0x1803b8a15  add     rsp, 40h
0x1803b8a19  pop     r15
0x1803b8a1b  pop     r14
0x1803b8a1d  pop     rdi
0x1803b8a1e  pop     rsi
0x1803b8a1f  pop     rbp
0x1803b8a20  retn
```
