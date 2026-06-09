# _DiskQuotaUIClassFactory::CreateInstance_::_1_::catch$1

- ea: `0x18001dc2f`
- end: `0x18001dc79`
- name: `_DiskQuotaUIClassFactory::CreateInstance_::_1_::catch$1`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001dc2f`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall DiskQuotaUIClassFactory::CreateInstance_::_1_::catch_1(__int64 a1, __int64 a2)
{
  _QWORD *v3; // rbx

  v3 = *(_QWORD **)(a2 + 32);
  if ( *v3 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v3 + 16LL))(*v3);
    *v3 = 0;
  }
  *(_DWORD *)(a2 + 32) = -2147024882;
  return 0;
}

```

## disassembly

```asm
0x18001dc2f  mov     [rsp+arg_8], rdx
0x18001dc34  push    rbx
0x18001dc35  push    rbp
0x18001dc36  sub     rsp, 28h
0x18001dc3a  mov     rbp, rdx
0x18001dc3d  mov     rbx, [rbp+20h]
0x18001dc41  cmp     qword ptr [rbx], 0
0x18001dc45  jz      short loc_18001DC60
0x18001dc47  mov     rax, [rbx]
0x18001dc4a  mov     rcx, [rax]
0x18001dc4d  mov     rax, [rcx+10h]
0x18001dc51  mov     rcx, [rbx]
0x18001dc54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc59  mov     qword ptr [rbx], 0
0x18001dc60  mov     dword ptr [rbp+20h], 8007000Eh
0x18001dc67  mov     rax, 0
0x18001dc71  add     rsp, 28h
0x18001dc75  pop     rbp
0x18001dc76  pop     rbx
0x18001dc77  retn
```
