# CMediaWrapperFilter::Init(_GUID const &,_GUID const &)

- ea: `0x180016c50`
- end: `0x180016dcb`
- name: `?Init@CMediaWrapperFilter@@UEAAJAEBU_GUID@@0@Z`
- size: `379`
- prototype: `__int64 __fastcall(CMediaWrapperFilter *this, const struct _GUID *, const struct _GUID *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180016c50`
- `0x180017fd0`
- `0x1800185ec`
- `0x18001f010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180016c6f`
- `KERNEL32!EnterCriticalSection` at `0x180016c6f`
- `KERNEL32!LeaveCriticalSection` at `0x180016db4`
- `KERNEL32!LeaveCriticalSection` at `0x180016db4`
- `ole32!CoCreateInstance` at `0x180016c9a`
- `ole32!CoCreateInstance` at `0x180016c9a`

## pseudocode

```c
__int64 __fastcall CMediaWrapperFilter::Init(CMediaWrapperFilter *this, const struct _GUID *a2, const struct _GUID *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rbp
  _QWORD *v7; // rsi
  IUnknown *v8; // rdx
  HRESULT Instance; // edi
  int v10; // eax

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 104);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  v7 = (_QWORD *)((char *)this + 48);
  v8 = (IUnknown *)*((_QWORD *)this - 14);
  ++*((_DWORD *)this - 26);
  Instance = CoCreateInstance(a2, v8, 1u, &IID_IUnknown, (LPVOID *)this + 6);
  --*((_DWORD *)this - 26);
  if ( Instance >= 0 )
  {
    Instance = (**(__int64 (__fastcall ***)(_QWORD, GUID *, char *))*v7)(*v7, &IID_IMediaObject, (char *)this + 40);
    if ( Instance >= 0 )
    {
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this - 14) + 16LL))(*((_QWORD *)this - 14));
      if ( *((_QWORD *)this - 3)
        && (v10 = CMediaWrapperFilter::SetupSecureChannel((CMediaWrapperFilter *)((char *)this - 120)), v10 < 0) )
      {
        Instance = v10;
      }
      else
      {
        if ( (**(int (__fastcall ***)(_QWORD, GUID *, char *))*v7)(*v7, &IID_IDMOQualityControl, (char *)this + 56) < 0 )
          *((_QWORD *)this + 7) = 0;
        else
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this - 14) + 16LL))(*((_QWORD *)this - 14));
        if ( (**(int (__fastcall ***)(_QWORD, GUID *, char *))*v7)(
               *v7,
               &IID_IDMOVideoOutputOptimizations,
               (char *)this + 64) < 0 )
          *((_QWORD *)this + 8) = 0;
        else
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this - 14) + 16LL))(*((_QWORD *)this - 14));
        *((struct _GUID *)this + 18) = *a2;
        *((struct _GUID *)this + 19) = *a3;
        CMediaWrapperFilter::RefreshPinList((CMediaWrapperFilter *)((char *)this - 120));
        Instance = 0;
      }
    }
    else
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 16LL))(*v7);
      *v7 = 0;
      *((_QWORD *)this + 5) = 0;
    }
  }
  LeaveCriticalSection(v3);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180016c50  push    rbx
0x180016c52  push    rbp
0x180016c53  push    rsi
0x180016c54  push    rdi
0x180016c55  push    r12
0x180016c57  push    r14
0x180016c59  push    r15
0x180016c5b  sub     rsp, 30h
0x180016c5f  lea     rbp, [rcx+68h]
0x180016c63  mov     rbx, rcx
0x180016c66  mov     rcx, rbp; lpCriticalSection
0x180016c69  mov     r12, r8
0x180016c6c  mov     r15, rdx
0x180016c6f  call    cs:__imp_EnterCriticalSection
0x180016c75  mov     eax, [rbx-68h]
0x180016c78  lea     rsi, [rbx+30h]
0x180016c7c  mov     rdx, [rbx-70h]; pUnkOuter
0x180016c80  lea     r9, IID_IUnknown; riid
0x180016c87  inc     eax
0x180016c89  mov     [rsp+68h+ppv], rsi; ppv
0x180016c8e  mov     r8d, 1; dwClsContext
0x180016c94  mov     [rbx-68h], eax
0x180016c97  mov     rcx, r15; rclsid
0x180016c9a  call    cs:__imp_CoCreateInstance
0x180016ca0  mov     edx, [rbx-68h]
0x180016ca3  mov     edi, eax
0x180016ca5  dec     edx
0x180016ca7  mov     [rbx-68h], edx
0x180016caa  test    eax, eax
0x180016cac  js      loc_180016DB1
0x180016cb2  mov     rcx, [rsi]
0x180016cb5  lea     r8, [rbx+28h]
0x180016cb9  lea     rdx, IID_IMediaObject
0x180016cc0  mov     rax, [rcx]
0x180016cc3  mov     rax, [rax]
0x180016cc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ccb  mov     edi, eax
0x180016ccd  test    eax, eax
0x180016ccf  jns     short loc_180016CF4
0x180016cd1  mov     rcx, [rsi]
0x180016cd4  mov     rdx, [rcx]
0x180016cd7  mov     rax, [rdx+10h]
0x180016cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ce0  mov     qword ptr [rsi], 0
0x180016ce7  mov     qword ptr [rbx+28h], 0
0x180016cef  jmp     loc_180016DB1
0x180016cf4  mov     rcx, [rbx-70h]
0x180016cf8  mov     rax, [rcx]
0x180016cfb  mov     rax, [rax+10h]
0x180016cff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d04  cmp     qword ptr [rbx-18h], 0
0x180016d09  jz      short loc_180016D1F
0x180016d0b  lea     rcx, [rbx-78h]; this
0x180016d0f  call    ?SetupSecureChannel@CMediaWrapperFilter@@IEAAJXZ; CMediaWrapperFilter::SetupSecureChannel(void)
0x180016d14  test    eax, eax
0x180016d16  jns     short loc_180016D1F
0x180016d18  mov     edi, eax
0x180016d1a  jmp     loc_180016DB1
0x180016d1f  mov     rcx, [rsi]
0x180016d22  lea     r8, [rbx+38h]
0x180016d26  lea     rdx, IID_IDMOQualityControl
0x180016d2d  mov     rax, [rcx]
0x180016d30  mov     rax, [rax]
0x180016d33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d38  test    eax, eax
0x180016d3a  js      short loc_180016D4E
0x180016d3c  mov     rcx, [rbx-70h]
0x180016d40  mov     rax, [rcx]
0x180016d43  mov     rax, [rax+10h]
0x180016d47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d4c  jmp     short loc_180016D56
0x180016d4e  mov     qword ptr [rbx+38h], 0
0x180016d56  mov     rcx, [rsi]
0x180016d59  lea     r8, [rbx+40h]
0x180016d5d  lea     rdx, IID_IDMOVideoOutputOptimizations
0x180016d64  mov     rax, [rcx]
0x180016d67  mov     rax, [rax]
0x180016d6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d6f  test    eax, eax
0x180016d71  js      short loc_180016D85
0x180016d73  mov     rcx, [rbx-70h]
0x180016d77  mov     rax, [rcx]
0x180016d7a  mov     rax, [rax+10h]
0x180016d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d83  jmp     short loc_180016D8D
0x180016d85  mov     qword ptr [rbx+40h], 0
0x180016d8d  movups  xmm0, xmmword ptr [r15]
0x180016d91  lea     rcx, [rbx-78h]; this
0x180016d95  movdqu  xmmword ptr [rbx+120h], xmm0
0x180016d9d  movups  xmm1, xmmword ptr [r12]
0x180016da2  movdqu  xmmword ptr [rbx+130h], xmm1
0x180016daa  call    ?RefreshPinList@CMediaWrapperFilter@@QEAAJXZ; CMediaWrapperFilter::RefreshPinList(void)
0x180016daf  xor     edi, edi
0x180016db1  mov     rcx, rbp; lpCriticalSection
0x180016db4  call    cs:__imp_LeaveCriticalSection
0x180016dba  mov     eax, edi
0x180016dbc  add     rsp, 30h
0x180016dc0  pop     r15
0x180016dc2  pop     r14
0x180016dc4  pop     r12
0x180016dc6  pop     rdi
0x180016dc7  pop     rsi
0x180016dc8  pop     rbp
0x180016dc9  pop     rbx
0x180016dca  retn
```
