# CPropMgr::ClearHmenuProps(HMENU__ *,ulong,_GUID const *,int)

- ea: `0x1800238a0`
- end: `0x18002394b`
- name: `?ClearHmenuProps@CPropMgr@@UEAAJPEAUHMENU__@@KPEBU_GUID@@H@Z`
- size: `171`
- prototype: `__int64 __fastcall(CPropMgr *__hidden this, HMENU, unsigned int, const struct _GUID *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x180019610`
- `0x18001a2a4`
- `0x18001e4c0`
- `0x1800238a0`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800238e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800238e5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPropMgr::ClearHmenuProps(CPropMgr *this, HMENU a2, int a3, const struct _GUID *a4, int a5)
{
  int v7; // edi
  unsigned int v9; // ebx
  DWORD CurrentProcessId; // eax
  _BYTE v12[24]; // [rsp+30h] [rbp-58h] BYREF
  _DWORD v13[4]; // [rsp+48h] [rbp-40h] BYREF

  v7 = (int)a2;
  OleaccApiCallTrace::OleaccApiCallTrace(v12, 1013, this);
  if ( *((_QWORD *)this + 2) )
  {
    CurrentProcessId = GetCurrentProcessId();
    v13[0] = -2147483646;
    v13[1] = CurrentProcessId;
    v13[2] = v7;
    v13[3] = a3;
    v9 = (*(__int64 (__fastcall **)(CPropMgr *, _DWORD *, __int64, const struct _GUID *, int))(*(_QWORD *)this + 40LL))(
           this,
           v13,
           16,
           a4,
           a5);
  }
  else
  {
    v9 = -2147467259;
  }
  OleaccApiCallTrace::~OleaccApiCallTrace((OleaccApiCallTrace *)v12);
  return v9;
}

```

## disassembly

```asm
0x1800238a0  push    rbx
0x1800238a2  push    rbp
0x1800238a3  push    rsi
0x1800238a4  push    rdi
0x1800238a5  sub     rsp, 68h
0x1800238a9  mov     rax, cs:__security_cookie
0x1800238b0  xor     rax, rsp
0x1800238b3  mov     [rsp+88h+var_30], rax
0x1800238b8  mov     rbp, r9
0x1800238bb  mov     esi, r8d
0x1800238be  mov     rdi, rdx
0x1800238c1  mov     rbx, rcx
0x1800238c4  mov     r8, rcx
0x1800238c7  mov     edx, 3F5h
0x1800238cc  lea     rcx, [rsp+88h+var_58]
0x1800238d1  call    ??0OleaccApiCallTrace@@QEAA@W4OLEACC_API_ENTRYPOINT@@PEAX@Z; OleaccApiCallTrace::OleaccApiCallTrace(OLEACC_API_ENTRYPOINT,void *)
0x1800238d6  nop
0x1800238d7  cmp     qword ptr [rbx+10h], 0
0x1800238dc  jnz     short loc_1800238E5
0x1800238de  mov     ebx, 80004005h
0x1800238e3  jmp     short loc_180023929
0x1800238e5  call    cs:__imp_GetCurrentProcessId
0x1800238eb  mov     [rsp+88h+var_40], 80000002h
0x1800238f3  mov     [rsp+88h+var_3C], eax
0x1800238f7  mov     [rsp+88h+var_38], edi
0x1800238fb  mov     [rsp+88h+var_34], esi
0x1800238ff  mov     rax, [rbx]
0x180023902  mov     edx, [rsp+88h+arg_20]
0x180023909  mov     [rsp+88h+var_68], edx
0x18002390d  mov     r9, rbp
0x180023910  mov     r8d, 10h
0x180023916  lea     rdx, [rsp+88h+var_40]
0x18002391b  mov     rcx, rbx
0x18002391e  mov     rax, [rax+28h]
0x180023922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023927  mov     ebx, eax
0x180023929  lea     rcx, [rsp+88h+var_58]; this
0x18002392e  call    ??1OleaccApiCallTrace@@QEAA@XZ; OleaccApiCallTrace::~OleaccApiCallTrace(void)
0x180023933  mov     eax, ebx
0x180023935  mov     rcx, [rsp+88h+var_30]
0x18002393a  xor     rcx, rsp; StackCookie
0x18002393d  call    __security_check_cookie
0x180023942  add     rsp, 68h
0x180023946  pop     rdi
0x180023947  pop     rsi
0x180023948  pop     rbp
0x180023949  pop     rbx
0x18002394a  retn
```
