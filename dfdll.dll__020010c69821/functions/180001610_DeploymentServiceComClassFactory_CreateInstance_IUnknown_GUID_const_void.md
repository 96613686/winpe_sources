# DeploymentServiceComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180001610`
- end: `0x1800016b5`
- name: `?CreateInstance@DeploymentServiceComClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `165`
- prototype: `__int64 __fastcall(DeploymentServiceComClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001040`
- `0x180001610`
- `0x180012bf4`
- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall DeploymentServiceComClassFactory::CreateInstance(
        DeploymentServiceComClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  DeploymentServiceCom *v7; // rax
  DeploymentServiceCom *v8; // rbx
  int v9; // edi

  if ( !a4 )
    return 2147942487LL;
  if ( a2 )
    return 2147746064LL;
  v7 = (DeploymentServiceCom *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v7 )
    v8 = DeploymentServiceCom::DeploymentServiceCom(v7);
  else
    v8 = 0;
  if ( !v8 )
    return 2147942414LL;
  v9 = (**(__int64 (__fastcall ***)(DeploymentServiceCom *, const struct _GUID *, void **))v8)(v8, a3, a4);
  if ( v9 < 0 )
    (*(void (__fastcall **)(DeploymentServiceCom *, __int64))(*(_QWORD *)v8 + 112LL))(v8, 1);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180001610  mov     [rsp+arg_0], rbx
0x180001615  mov     [rsp+arg_8], rsi
0x18000161a  push    rdi
0x18000161b  sub     rsp, 20h
0x18000161f  mov     rdi, r9
0x180001622  mov     rsi, r8
0x180001625  test    r9, r9
0x180001628  jnz     short loc_180001631
0x18000162a  mov     eax, 80070057h
0x18000162f  jmp     short loc_1800016A5
0x180001631  test    rdx, rdx
0x180001634  jz      short loc_18000163D
0x180001636  mov     eax, 80040110h
0x18000163b  jmp     short loc_1800016A5
0x18000163d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180001644  mov     ecx, 28h ; '('; unsigned __int64
0x180001649  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000164e  mov     [rsp+28h+arg_18], rax
0x180001653  test    rax, rax
0x180001656  jz      short loc_180001665
0x180001658  mov     rcx, rax; this
0x18000165b  call    ??0DeploymentServiceCom@@QEAA@XZ; DeploymentServiceCom::DeploymentServiceCom(void)
0x180001660  mov     rbx, rax
0x180001663  jmp     short loc_180001667
0x180001665  xor     ebx, ebx
0x180001667  test    rbx, rbx
0x18000166a  jnz     short loc_180001673
0x18000166c  mov     eax, 8007000Eh
0x180001671  jmp     short loc_1800016A5
0x180001673  mov     rax, [rbx]
0x180001676  mov     r8, rdi
0x180001679  mov     rdx, rsi
0x18000167c  mov     rcx, rbx
0x18000167f  mov     rax, [rax]
0x180001682  call    cs:__guard_dispatch_icall_fptr
0x180001688  mov     edi, eax
0x18000168a  test    eax, eax
0x18000168c  jns     short loc_1800016A3
0x18000168e  mov     rcx, [rbx]
0x180001691  mov     rax, [rcx+70h]
0x180001695  mov     edx, 1
0x18000169a  mov     rcx, rbx
0x18000169d  call    cs:__guard_dispatch_icall_fptr
0x1800016a3  mov     eax, edi
0x1800016a5  mov     rbx, [rsp+28h+arg_0]
0x1800016aa  mov     rsi, [rsp+28h+arg_8]
0x1800016af  add     rsp, 20h
0x1800016b3  pop     rdi
0x1800016b4  retn
```
