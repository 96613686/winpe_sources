# CW32System::CoCreateInstance(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)

- ea: `0x18008d5ac`
- end: `0x18008d61d`
- name: `?CoCreateInstance@CW32System@@SAJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@Z`
- size: `113`
- prototype: `__int64 __fastcall(const struct _GUID *, struct IUnknown *, unsigned int, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008f7dc`

## callees

- `0x180041adc`
- `0x18008d5ac`
- `0x1800907ac`
- `0x180092010`

## string_xrefs

- `0x18008d5cb`: `CoCreateInstance`

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
             &qword_1800A44B8);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x18008d5ac  mov     [rsp+arg_0], rbx
0x18008d5b1  push    rdi
0x18008d5b2  sub     rsp, 30h
0x18008d5b6  mov     edi, r8d
0x18008d5b9  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x18008d5be  lea     rbx, [rax+148h]
0x18008d5c5  cmp     qword ptr [rbx], 0
0x18008d5c9  jnz     short loc_18008D5DF
0x18008d5cb  lea     r8, aCocreateinstan; "CoCreateInstance"
0x18008d5d2  mov     edx, 1
0x18008d5d7  mov     rcx, rbx
0x18008d5da  call    SetProcAddr
0x18008d5df  mov     rax, [rbx]
0x18008d5e2  test    rax, rax
0x18008d5e5  jz      short loc_18008D60D
0x18008d5e7  lea     rcx, qword_1800A44B8
0x18008d5ee  mov     r8d, edi
0x18008d5f1  mov     [rsp+38h+var_18], rcx
0x18008d5f6  lea     r9, IID_IActiveIMMApp
0x18008d5fd  lea     rcx, CLSID_CActiveIMM
0x18008d604  xor     edx, edx
0x18008d606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d60b  jmp     short loc_18008D612
0x18008d60d  mov     eax, 80004005h
0x18008d612  mov     rbx, [rsp+38h+arg_0]
0x18008d617  add     rsp, 30h
0x18008d61b  pop     rdi
0x18008d61c  retn
```
