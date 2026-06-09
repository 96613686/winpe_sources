# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Microsoft::WRL::FtmBase>::`vector deleting destructor'(uint)

- ea: `0x1800142a0`
- end: `0x1800142f8`
- name: `??_E?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1800142a0`
- `0x180038010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800142dd`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800142dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Microsoft::WRL::FtmBase>::`vector deleting destructor'(
        __int64 a1,
        char a2)
{
  __int64 v4; // rcx

  *(_DWORD *)(a1 + 44) = -1073741823;
  v4 = *(_QWORD *)(a1 + 32);
  if ( v4 )
  {
    *(_QWORD *)(a1 + 32) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  if ( (a2 & 1) != 0 )
    operator delete((void *)a1);
  return a1;
}

```

## disassembly

```asm
0x1800142a0  mov     [rsp+arg_0], rbx
0x1800142a5  push    rdi
0x1800142a6  sub     rsp, 20h
0x1800142aa  mov     edi, edx
0x1800142ac  mov     rbx, rcx
0x1800142af  mov     dword ptr [rcx+2Ch], 0C0000001h
0x1800142b6  mov     rcx, [rcx+20h]
0x1800142ba  test    rcx, rcx
0x1800142bd  jz      short loc_1800142D4
0x1800142bf  mov     qword ptr [rbx+20h], 0
0x1800142c7  mov     rax, [rcx]
0x1800142ca  mov     rax, [rax+10h]
0x1800142ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142d3  nop
0x1800142d4  test    dil, 1
0x1800142d8  jz      short loc_1800142E9
0x1800142da  mov     rcx, rbx
0x1800142dd  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800142e4  nop     dword ptr [rax+rax+00h]
0x1800142e9  mov     rax, rbx
0x1800142ec  mov     rbx, [rsp+28h+arg_0]
0x1800142f1  add     rsp, 20h
0x1800142f5  pop     rdi
0x1800142f6  retn
```
