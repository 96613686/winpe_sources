# CW32System::CoCreateInstance(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)

- ea: `0x18008fd88`
- end: `0x18008fdfa`
- name: `?CoCreateInstance@CW32System@@SAJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@Z`
- size: `114`
- prototype: `__int64 __fastcall(const struct _GUID *, struct IUnknown *, unsigned int, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800920f4`

## callees

- `0x1800427ac`
- `0x18008fd88`
- `0x1800931b0`
- `0x180095010`

## string_xrefs

- `0x18008fda7`: `CoCreateInstance`

## pseudocode

```c
__int64 __fastcall CW32System::CoCreateInstance(
        const struct _GUID *a1,
        struct IUnknown *a2,
        unsigned int a3,
        const struct _GUID *a4)
{
  struct COLE32_PROC *Ole32Procs; // rax
  struct COLE32_PROC *v6; // rbx

  Ole32Procs = CThreadData::GetOle32Procs();
  v6 = (struct COLE32_PROC *)((char *)Ole32Procs + 328);
  if ( !*((_QWORD *)Ole32Procs + 41) )
    SetProcAddr((FARPROC *)Ole32Procs + 41, 1, "CoCreateInstance");
  if ( *(_QWORD *)v6 )
    return (*(__int64 (__fastcall **)(GUID *, _QWORD, _QWORD, GUID *, __int64 *))v6)(
             &CLSID_CActiveIMM,
             0,
             a3,
             &IID_IActiveIMMApp,
             &qword_1800A7598);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x18008fd88  mov     [rsp+arg_0], rbx
0x18008fd8d  push    rdi
0x18008fd8e  sub     rsp, 30h
0x18008fd92  mov     edi, r8d
0x18008fd95  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x18008fd9a  lea     rbx, [rax+148h]
0x18008fda1  cmp     qword ptr [rbx], 0
0x18008fda5  jnz     short loc_18008FDBB
0x18008fda7  lea     r8, aCocreateinstan; "CoCreateInstance"
0x18008fdae  mov     edx, 1
0x18008fdb3  mov     rcx, rbx
0x18008fdb6  call    SetProcAddr
0x18008fdbb  mov     rax, [rbx]
0x18008fdbe  test    rax, rax
0x18008fdc1  jz      short loc_18008FDE9
0x18008fdc3  lea     rcx, qword_1800A7598
0x18008fdca  mov     r8d, edi
0x18008fdcd  mov     [rsp+38h+var_18], rcx
0x18008fdd2  lea     r9, IID_IActiveIMMApp
0x18008fdd9  lea     rcx, CLSID_CActiveIMM
0x18008fde0  xor     edx, edx
0x18008fde2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fde7  jmp     short loc_18008FDEE
0x18008fde9  mov     eax, 80004005h
0x18008fdee  mov     rbx, [rsp+38h+arg_0]
0x18008fdf3  add     rsp, 30h
0x18008fdf7  pop     rdi
0x18008fdf8  retn
```
