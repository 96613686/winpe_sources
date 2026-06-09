# CPropMgr::SetHmenuPropServer(HMENU__ *,ulong,_GUID const *,int,IAccPropServer *,AnnoScope)

- ea: `0x180023cf0`
- end: `0x180023db7`
- name: `?SetHmenuPropServer@CPropMgr@@UEAAJPEAUHMENU__@@KPEBU_GUID@@HPEAUIAccPropServer@@W4AnnoScope@@@Z`
- size: `199`
- prototype: `__int64 __fastcall(CPropMgr *__hidden this, HMENU, unsigned int, const struct _GUID *, int, struct IAccPropServer *, enum AnnoScope)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x180019610`
- `0x18001a2a4`
- `0x18001e4c0`
- `0x180023cf0`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023d3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023d3f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPropMgr::SetHmenuPropServer(
        CPropMgr *this,
        HMENU a2,
        int a3,
        const struct _GUID *a4,
        int a5,
        struct IAccPropServer *a6,
        enum AnnoScope a7)
{
  int v9; // edi
  unsigned int v11; // ebx
  DWORD CurrentProcessId; // eax
  _BYTE v14[24]; // [rsp+40h] [rbp-58h] BYREF
  _DWORD v15[4]; // [rsp+58h] [rbp-40h] BYREF

  v9 = (int)a2;
  OleaccApiCallTrace::OleaccApiCallTrace(v14, 1012, this);
  if ( *((_QWORD *)this + 2) )
  {
    CurrentProcessId = GetCurrentProcessId();
    v15[0] = -2147483646;
    v15[1] = CurrentProcessId;
    v15[2] = v9;
    v15[3] = a3;
    v11 = (*(__int64 (__fastcall **)(CPropMgr *, _DWORD *, __int64, const struct _GUID *, int, struct IAccPropServer *, enum AnnoScope))(*(_QWORD *)this + 32LL))(
            this,
            v15,
            16,
            a4,
            a5,
            a6,
            a7);
  }
  else
  {
    v11 = -2147467259;
  }
  OleaccApiCallTrace::~OleaccApiCallTrace((OleaccApiCallTrace *)v14);
  return v11;
}

```

## disassembly

```asm
0x180023cf0  push    rbx
0x180023cf2  push    rbp
0x180023cf3  push    rsi
0x180023cf4  push    rdi
0x180023cf5  push    r14
0x180023cf7  sub     rsp, 70h
0x180023cfb  mov     rax, cs:__security_cookie
0x180023d02  xor     rax, rsp
0x180023d05  mov     [rsp+98h+var_30], rax
0x180023d0a  mov     rbp, r9
0x180023d0d  mov     esi, r8d
0x180023d10  mov     rdi, rdx
0x180023d13  mov     rbx, rcx
0x180023d16  mov     r14, [rsp+98h+arg_28]
0x180023d1e  mov     r8, rcx
0x180023d21  mov     edx, 3F4h
0x180023d26  lea     rcx, [rsp+98h+var_58]
0x180023d2b  call    ??0OleaccApiCallTrace@@QEAA@W4OLEACC_API_ENTRYPOINT@@PEAX@Z; OleaccApiCallTrace::OleaccApiCallTrace(OLEACC_API_ENTRYPOINT,void *)
0x180023d30  nop
0x180023d31  cmp     qword ptr [rbx+10h], 0
0x180023d36  jnz     short loc_180023D3F
0x180023d38  mov     ebx, 80004005h
0x180023d3d  jmp     short loc_180023D93
0x180023d3f  call    cs:__imp_GetCurrentProcessId
0x180023d45  mov     [rsp+98h+var_40], 80000002h
0x180023d4d  mov     [rsp+98h+var_3C], eax
0x180023d51  mov     [rsp+98h+var_38], edi
0x180023d55  mov     [rsp+98h+var_34], esi
0x180023d59  mov     rax, [rbx]
0x180023d5c  mov     edx, [rsp+98h+arg_30]
0x180023d63  mov     [rsp+98h+var_68], edx
0x180023d67  mov     [rsp+98h+var_70], r14
0x180023d6c  mov     edx, [rsp+98h+arg_20]
0x180023d73  mov     [rsp+98h+var_78], edx
0x180023d77  mov     r9, rbp
0x180023d7a  mov     r8d, 10h
0x180023d80  lea     rdx, [rsp+98h+var_40]
0x180023d85  mov     rcx, rbx
0x180023d88  mov     rax, [rax+20h]
0x180023d8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d91  mov     ebx, eax
0x180023d93  lea     rcx, [rsp+98h+var_58]; this
0x180023d98  call    ??1OleaccApiCallTrace@@QEAA@XZ; OleaccApiCallTrace::~OleaccApiCallTrace(void)
0x180023d9d  mov     eax, ebx
0x180023d9f  mov     rcx, [rsp+98h+var_30]
0x180023da4  xor     rcx, rsp; StackCookie
0x180023da7  call    __security_check_cookie
0x180023dac  add     rsp, 70h
0x180023db0  pop     r14
0x180023db2  pop     rdi
0x180023db3  pop     rsi
0x180023db4  pop     rbp
0x180023db5  pop     rbx
0x180023db6  retn
```
