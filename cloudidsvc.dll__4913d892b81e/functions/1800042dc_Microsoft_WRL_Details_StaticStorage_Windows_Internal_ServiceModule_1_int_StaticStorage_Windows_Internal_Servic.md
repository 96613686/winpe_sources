# Microsoft::WRL::Details::StaticStorage<Windows::Internal::ServiceModule,1,int>::~StaticStorage<Windows::Internal::ServiceModule,1,int>(void)

- ea: `0x1800042dc`
- end: `0x180004306`
- name: `??1?$StaticStorage@VServiceModule@Internal@Windows@@$00H@Details@WRL@Microsoft@@QEAA@XZ`
- size: `42`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011540`

## callees

- `0x1800042dc`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::StaticStorage<Windows::Internal::ServiceModule,1,int>::~StaticStorage<Windows::Internal::ServiceModule,1,int>(
        __int64 a1)
{
  __int64 result; // rax

  if ( *(_BYTE *)(a1 + 56) )
  {
    result = (**(__int64 (__fastcall ***)(__int64, _QWORD))(a1 + 40))(a1 + 40, 0);
    *(_BYTE *)(a1 + 56) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800042dc  push    rbx
0x1800042de  sub     rsp, 20h
0x1800042e2  cmp     byte ptr [rcx+38h], 0
0x1800042e6  mov     rbx, rcx
0x1800042e9  jz      short loc_180004300
0x1800042eb  add     rcx, 28h ; '('
0x1800042ef  xor     edx, edx
0x1800042f1  mov     rax, [rcx]
0x1800042f4  mov     rax, [rax]
0x1800042f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042fc  mov     byte ptr [rbx+38h], 0
0x180004300  add     rsp, 20h
0x180004304  pop     rbx
0x180004305  retn
```
