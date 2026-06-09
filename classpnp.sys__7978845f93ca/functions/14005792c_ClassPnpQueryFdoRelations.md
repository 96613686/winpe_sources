# ClassPnpQueryFdoRelations

- ea: `0x14005792c`
- end: `0x1400579ad`
- name: `ClassPnpQueryFdoRelations`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14005fe50`

## callees

- `0x14003e470`
- `0x14005792c`
- `0x140058b98`

## import_xrefs

- `ntoskrnl!IoGetDriverObjectExtension` at `0x140057950`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x140057950`

## pseudocode

```c
__int64 __fastcall ClassPnpQueryFdoRelations(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  void (__fastcall **DriverObjectExtension)(__int64); // rax
  __int64 v6; // rdx

  v2 = *(_QWORD *)(a1 + 64);
  DriverObjectExtension = (void (__fastcall **)(__int64))IoGetDriverObjectExtension(
                                                           *(PDRIVER_OBJECT *)(a1 + 8),
                                                           ClassInitialize);
  if ( _InterlockedIncrement((volatile signed __int32 *)(v2 + 836)) == 1 )
    DriverObjectExtension[46](a1);
  *(_DWORD *)(a2 + 48) = ClassRetrieveDeviceRelations(a1, v6, (_DWORD **)(a2 + 56));
  _InterlockedDecrement((volatile signed __int32 *)(v2 + 836));
  return *(unsigned int *)(a2 + 48);
}

```

## disassembly

```asm
0x14005792c  mov     [rsp+arg_0], rbx
0x140057931  mov     [rsp+arg_8], rsi
0x140057936  push    rdi
0x140057937  sub     rsp, 20h
0x14005793b  mov     rsi, [rcx+40h]
0x14005793f  mov     rdi, rdx
0x140057942  mov     rbx, rcx
0x140057945  lea     rdx, ClassInitialize; ClientIdentificationAddress
0x14005794c  mov     rcx, [rcx+8]; DriverObject
0x140057950  call    cs:__imp_IoGetDriverObjectExtension
0x140057957  nop     dword ptr [rax+rax+00h]
0x14005795c  mov     r8d, 1
0x140057962  lock xadd [rsi+344h], r8d
0x14005796b  inc     r8d
0x14005796e  cmp     r8d, 1
0x140057972  jnz     short loc_140057983
0x140057974  mov     rax, [rax+170h]
0x14005797b  mov     rcx, rbx
0x14005797e  call    _guard_dispatch_icall
0x140057983  lea     r8, [rdi+38h]
0x140057987  mov     rcx, rbx
0x14005798a  call    ClassRetrieveDeviceRelations
0x14005798f  mov     rbx, [rsp+28h+arg_0]
0x140057994  mov     [rdi+30h], eax
0x140057997  lock dec dword ptr [rsi+344h]
0x14005799e  mov     eax, [rdi+30h]
0x1400579a1  mov     rsi, [rsp+28h+arg_8]
0x1400579a6  add     rsp, 20h
0x1400579aa  pop     rdi
0x1400579ab  retn
```
