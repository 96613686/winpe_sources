# CIncomingConnectionSavePage::~CIncomingConnectionSavePage(void)

- ea: `0x18001ef48`
- end: `0x18001eff7`
- name: `??1CIncomingConnectionSavePage@@QEAA@XZ`
- size: `175`
- prototype: `void __fastcall(CIncomingConnectionSavePage *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004444`
- `0x180004c00`

## callees

- `0x180005080`
- `0x18001ef48`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ef5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ef5d`

## string_xrefs

- `0x18001ef89`: `ICCServiceStatus`

## pseudocode

```c
void __fastcall CIncomingConnectionSavePage::~CIncomingConnectionSavePage(CIncomingConnectionSavePage *this)
{
  void *v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx

  v2 = (void *)*((_QWORD *)this + 21);
  if ( v2 )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 21) = 0;
  }
  v3 = *((_QWORD *)this + 17);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64, _QWORD, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)v3 + 56LL))(
      v3,
      0,
      L"ICCServiceStatus",
      0,
      0);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 16LL))(*((_QWORD *)this + 17));
    *((_QWORD *)this + 17) = 0;
  }
  v4 = *((_QWORD *)this + 18);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = *((_QWORD *)this + 19);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((CIncomingConnectionSavePage *)((char *)this + 16));
}

```

## disassembly

```asm
0x18001ef48  push    rbx
0x18001ef4a  sub     rsp, 30h
0x18001ef4e  mov     rbx, rcx
0x18001ef51  mov     rcx, [rcx+0A8h]; hObject
0x18001ef58  test    rcx, rcx
0x18001ef5b  jz      short loc_18001EF6E
0x18001ef5d  call    cs:__imp_CloseHandle
0x18001ef63  mov     qword ptr [rbx+0A8h], 0
0x18001ef6e  mov     rcx, [rbx+88h]
0x18001ef75  test    rcx, rcx
0x18001ef78  jz      short loc_18001EFB9
0x18001ef7a  mov     rax, [rcx]
0x18001ef7d  mov     [rsp+38h+var_18], 0
0x18001ef86  xor     r9d, r9d
0x18001ef89  lea     r8, aIccservicestat; "ICCServiceStatus"
0x18001ef90  xor     edx, edx
0x18001ef92  mov     rax, [rax+38h]
0x18001ef96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef9b  mov     rcx, [rbx+88h]
0x18001efa2  mov     rax, [rcx]
0x18001efa5  mov     rax, [rax+10h]
0x18001efa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001efae  mov     qword ptr [rbx+88h], 0
0x18001efb9  mov     rcx, [rbx+90h]
0x18001efc0  test    rcx, rcx
0x18001efc3  jz      short loc_18001EFD1
0x18001efc5  mov     rax, [rcx]
0x18001efc8  mov     rax, [rax+10h]
0x18001efcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001efd1  mov     rcx, [rbx+98h]
0x18001efd8  test    rcx, rcx
0x18001efdb  jz      short loc_18001EFE9
0x18001efdd  mov     rax, [rcx]
0x18001efe0  mov     rax, [rax+10h]
0x18001efe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001efe9  lea     rcx, [rbx+10h]; this
0x18001efed  add     rsp, 30h
0x18001eff1  pop     rbx
0x18001eff2  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
