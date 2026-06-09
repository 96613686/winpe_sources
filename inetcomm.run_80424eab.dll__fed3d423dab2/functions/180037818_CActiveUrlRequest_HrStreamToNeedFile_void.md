# CActiveUrlRequest::_HrStreamToNeedFile(void)

- ea: `0x180037818`
- end: `0x1800378fe`
- name: `?_HrStreamToNeedFile@CActiveUrlRequest@@AEAAJXZ`
- size: `230`
- prototype: `__int64 __fastcall(CActiveUrlRequest *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800377c8`

## callees

- `0x180002098`
- `0x180037818`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!WriteStreamToFileHandle` at `0x180037854`
- `MSOERT2!WriteStreamToFileHandle` at `0x180037854`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800378a3`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800378a3`
- `SHLWAPI!__imp_IStream_Reset` at `0x180037886`
- `SHLWAPI!__imp_IStream_Reset` at `0x180037886`
- `KERNEL32!CloseHandle` at `0x180037874`
- `KERNEL32!CloseHandle` at `0x180037874`

## pseudocode

```c
__int64 __fastcall CActiveUrlRequest::_HrStreamToNeedFile(CActiveUrlRequest *this)
{
  bool v1; // zf
  unsigned int v3; // ebx
  IStream *v4; // rcx
  __int64 v5; // rcx
  int v7; // [rsp+40h] [rbp+8h] BYREF
  void *ppvOut; // [rsp+48h] [rbp+10h] BYREF

  v1 = *((_QWORD *)this + 8) == 0;
  v7 = 0;
  ppvOut = 0;
  if ( v1 )
  {
LABEL_2:
    v3 = -2147418113;
    goto LABEL_9;
  }
  v3 = WriteStreamToFileHandle(*((_QWORD *)this + 10), *((_QWORD *)this + 15), &v7);
  if ( (int)(v3 + 0x80000000) < 0 || v3 == -2147483638 )
  {
    CloseHandle(*((HANDLE *)this + 15));
    v4 = (IStream *)*((_QWORD *)this + 10);
    *((_QWORD *)this + 15) = -1;
    IStream_Reset(v4);
    if ( IUnknown_QueryService(
           *((IUnknown **)this + 8),
           &CLSID_MimeEdit,
           &GUID_00000109_0000_0000_c000_000000000046,
           &ppvOut) >= 0 )
      (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppvOut + 40LL))(ppvOut, *((_QWORD *)this + 10));
    v5 = *((_QWORD *)this + 8);
    if ( v5 )
    {
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v5 + 40LL))(
        v5,
        *((unsigned int *)this + 34),
        0,
        0);
      goto LABEL_9;
    }
    goto LABEL_2;
  }
LABEL_9:
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&ppvOut);
  return v3;
}

```

## disassembly

```asm
0x180037818  mov     [rsp+arg_10], rbx
0x18003781d  push    rdi
0x18003781e  sub     rsp, 30h
0x180037822  cmp     qword ptr [rcx+40h], 0
0x180037827  mov     rdi, rcx
0x18003782a  mov     [rsp+38h+arg_0], 0
0x180037832  mov     [rsp+38h+ppvOut], 0
0x18003783b  jnz     short loc_180037847
0x18003783d  mov     ebx, 8000FFFFh
0x180037842  jmp     loc_1800378E7
0x180037847  mov     rdx, [rcx+78h]
0x18003784b  lea     r8, [rsp+38h+arg_0]
0x180037850  mov     rcx, [rcx+50h]
0x180037854  call    cs:__imp_WriteStreamToFileHandle
0x18003785a  mov     ebx, eax
0x18003785c  mov     eax, 80000000h
0x180037861  lea     ecx, [rbx+rax]
0x180037864  test    eax, ecx
0x180037866  jnz     short loc_180037870
0x180037868  cmp     ebx, 8000000Ah
0x18003786e  jnz     short loc_1800378E7
0x180037870  mov     rcx, [rdi+78h]; hObject
0x180037874  call    cs:__imp_CloseHandle
0x18003787a  mov     rcx, [rdi+50h]; pstm
0x18003787e  mov     qword ptr [rdi+78h], 0FFFFFFFFFFFFFFFFh
0x180037886  call    cs:__imp_IStream_Reset
0x18003788c  mov     rcx, [rdi+40h]; punk
0x180037890  lea     r9, [rsp+38h+ppvOut]; ppvOut
0x180037895  lea     r8, _GUID_00000109_0000_0000_c000_000000000046; riid
0x18003789c  lea     rdx, CLSID_MimeEdit; guidService
0x1800378a3  call    cs:__imp_IUnknown_QueryService
0x1800378a9  test    eax, eax
0x1800378ab  js      short loc_1800378C2
0x1800378ad  mov     rcx, [rsp+38h+ppvOut]
0x1800378b2  mov     rdx, [rdi+50h]
0x1800378b6  mov     rax, [rcx]
0x1800378b9  mov     rax, [rax+28h]
0x1800378bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800378c2  mov     rcx, [rdi+40h]
0x1800378c6  test    rcx, rcx
0x1800378c9  jz      loc_18003783D
0x1800378cf  mov     rax, [rcx]
0x1800378d2  xor     r9d, r9d
0x1800378d5  mov     edx, [rdi+88h]
0x1800378db  xor     r8d, r8d
0x1800378de  mov     rax, [rax+28h]
0x1800378e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800378e7  lea     rcx, [rsp+38h+ppvOut]
0x1800378ec  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800378f1  mov     eax, ebx
0x1800378f3  mov     rbx, [rsp+38h+arg_10]
0x1800378f8  add     rsp, 30h
0x1800378fc  pop     rdi
0x1800378fd  retn
```
