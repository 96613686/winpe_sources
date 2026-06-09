# CPropMgr::SetHmenuProp(HMENU__ *,ulong,_GUID,tagVARIANT)

- ea: `0x180023c30`
- end: `0x180023ce7`
- name: `?SetHmenuProp@CPropMgr@@UEAAJPEAUHMENU__@@KU_GUID@@UtagVARIANT@@@Z`
- size: `183`
- prototype: `__int64 __fastcall(CPropMgr *__hidden this, HMENU, unsigned int, struct _GUID *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x180010d94`
- `0x180019610`
- `0x18001a2a4`
- `0x18001e4c0`
- `0x180023c30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023c7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023c7f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPropMgr::SetHmenuProp(
        CPropMgrImpl **this,
        HMENU a2,
        int a3,
        struct _GUID *a4,
        struct tagVARIANT *a5)
{
  int v7; // edi
  unsigned int v9; // ebx
  DWORD CurrentProcessId; // eax
  struct _GUID v12; // [rsp+30h] [rbp-68h] BYREF
  unsigned __int8 v13[24]; // [rsp+40h] [rbp-58h] BYREF
  unsigned __int8 v14[4]; // [rsp+58h] [rbp-40h] BYREF
  DWORD v15; // [rsp+5Ch] [rbp-3Ch]
  int v16; // [rsp+60h] [rbp-38h]
  int v17; // [rsp+64h] [rbp-34h]

  v7 = (int)a2;
  OleaccApiCallTrace::OleaccApiCallTrace(v13, 1010, this);
  if ( this[2] )
  {
    CurrentProcessId = GetCurrentProcessId();
    *(_DWORD *)v14 = -2147483646;
    v15 = CurrentProcessId;
    v16 = v7;
    v17 = a3;
    v12 = *a4;
    v9 = CPropMgrImpl::SetPropValue(this[2], v14, 16, &v12, a5);
  }
  else
  {
    v9 = -2147467259;
  }
  OleaccApiCallTrace::~OleaccApiCallTrace((OleaccApiCallTrace *)v13);
  return v9;
}

```

## disassembly

```asm
0x180023c30  push    rbx
0x180023c32  push    rbp
0x180023c33  push    rsi
0x180023c34  push    rdi
0x180023c35  push    r14
0x180023c37  sub     rsp, 70h
0x180023c3b  mov     rax, cs:__security_cookie
0x180023c42  xor     rax, rsp
0x180023c45  mov     [rsp+98h+var_30], rax
0x180023c4a  mov     rbp, r9
0x180023c4d  mov     esi, r8d
0x180023c50  mov     rdi, rdx
0x180023c53  mov     rbx, rcx
0x180023c56  mov     r14, [rsp+98h+arg_20]
0x180023c5e  mov     r8, rcx
0x180023c61  mov     edx, 3F2h
0x180023c66  lea     rcx, [rsp+98h+var_58]
0x180023c6b  call    ??0OleaccApiCallTrace@@QEAA@W4OLEACC_API_ENTRYPOINT@@PEAX@Z; OleaccApiCallTrace::OleaccApiCallTrace(OLEACC_API_ENTRYPOINT,void *)
0x180023c70  nop
0x180023c71  cmp     qword ptr [rbx+10h], 0
0x180023c76  jnz     short loc_180023C7F
0x180023c78  mov     ebx, 80004005h
0x180023c7d  jmp     short loc_180023CC3
0x180023c7f  call    cs:__imp_GetCurrentProcessId
0x180023c85  mov     dword ptr [rsp+98h+var_40], 80000002h
0x180023c8d  mov     [rsp+98h+var_3C], eax
0x180023c91  mov     [rsp+98h+var_38], edi
0x180023c95  mov     [rsp+98h+var_34], esi
0x180023c99  movups  xmm0, xmmword ptr [rbp+0]
0x180023c9d  movdqu  xmmword ptr [rsp+98h+var_68.Data1], xmm0
0x180023ca3  mov     [rsp+98h+var_78], r14; struct tagVARIANT *
0x180023ca8  lea     r9, [rsp+98h+var_68]; struct _GUID
0x180023cad  mov     r8d, 10h; unsigned int
0x180023cb3  lea     rdx, [rsp+98h+var_40]; unsigned __int8 *
0x180023cb8  mov     rcx, [rbx+10h]; this
0x180023cbc  call    ?SetPropValue@CPropMgrImpl@@QEAAJPEBEKU_GUID@@PEAUtagVARIANT@@@Z; CPropMgrImpl::SetPropValue(uchar const *,ulong,_GUID,tagVARIANT *)
0x180023cc1  mov     ebx, eax
0x180023cc3  lea     rcx, [rsp+98h+var_58]; this
0x180023cc8  call    ??1OleaccApiCallTrace@@QEAA@XZ; OleaccApiCallTrace::~OleaccApiCallTrace(void)
0x180023ccd  mov     eax, ebx
0x180023ccf  mov     rcx, [rsp+98h+var_30]
0x180023cd4  xor     rcx, rsp; StackCookie
0x180023cd7  call    __security_check_cookie
0x180023cdc  add     rsp, 70h
0x180023ce0  pop     r14
0x180023ce2  pop     rdi
0x180023ce3  pop     rsi
0x180023ce4  pop     rbp
0x180023ce5  pop     rbx
0x180023ce6  retn
```
