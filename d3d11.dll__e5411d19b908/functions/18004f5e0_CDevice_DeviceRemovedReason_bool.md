# CDevice::DeviceRemovedReason(bool)

- ea: `0x18004f5e0`
- end: `0x18004f69c`
- name: `?DeviceRemovedReason@CDevice@@QEBAJ_N@Z`
- size: `188`
- prototype: `__int64 __fastcall(CDevice *__hidden this, bool)`
- caller_count: `33`
- callee_count: `2`
- tags: ``

## callers

- `0x180014144`
- `0x180018c84`
- `0x180018f5c`
- `0x1800196a4`
- `0x18001a098`
- `0x180020e30`
- `0x180023300`
- `0x180024aac`
- `0x180026498`
- `0x180027e24`
- `0x180050910`
- `0x180060d10`
- `0x18007645c`
- `0x1800777f4`
- `0x180088090`
- `0x180091c84`
- `0x1800a3e0c`
- `0x1800bec0c`
- `0x180164ea0`
- `0x18016ad40`
- `0x180176750`
- `0x18017cff0`
- `0x18017e934`
- `0x18017eed0`
- `0x1801806d0`
- `0x180181340`
- `0x180181d50`
- `0x180183060`
- `0x180189ce0`
- `0x1801995a0`
- `0x1801a1690`
- `0x1801a8400`
- `0x1801aaa40`

## callees

- `0x18004f5e0`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SwitchToThread` at `0x18004f64a`
- `api-ms-win-core-processthreads-l1-1-0!SwitchToThread` at `0x18004f64a`

## pseudocode

```c
__int64 __fastcall CDevice::DeviceRemovedReason(CDevice *this, char a2)
{
  __int64 v2; // rdi
  int i; // ebx

  v2 = *((_QWORD *)this + 154);
  for ( i = *(_DWORD *)(v2 + 1248);
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v2 + 72) + 1080LL) + 39272LL);
        i = *(_DWORD *)(v2 + 1248) )
  {
    if ( i < 0 )
      break;
    SwitchToThread();
  }
  if ( !a2 || i < 0 || (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v2 + 192LL))(v2) == 1 )
    return (unsigned int)i;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(v2 + 16) + 264LL))(v2 + 16, 2289696773LL);
  return *(unsigned int *)(v2 + 1248);
}

```

## disassembly

```asm
0x18004f5e0  mov     [rsp+arg_0], rbx
0x18004f5e5  mov     [rsp+arg_8], rsi
0x18004f5ea  push    rdi
0x18004f5eb  sub     rsp, 20h
0x18004f5ef  mov     rdi, [rcx+4D0h]
0x18004f5f6  movzx   esi, dl
0x18004f5f9  mov     ebx, [rdi+4E0h]
0x18004f5ff  mov     rax, [rdi+48h]
0x18004f603  mov     rcx, [rax+438h]
0x18004f60a  mov     eax, [rcx+9968h]
0x18004f610  test    eax, eax
0x18004f612  jnz     short loc_18004F646
0x18004f614  test    sil, sil
0x18004f617  jz      short loc_18004F634
0x18004f619  test    ebx, ebx
0x18004f61b  js      short loc_18004F634
0x18004f61d  mov     rax, [rdi]
0x18004f620  mov     rcx, rdi
0x18004f623  mov     rax, [rax+0C0h]
0x18004f62a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f62f  cmp     eax, 1
0x18004f632  jnz     short loc_18004F66D
0x18004f634  mov     eax, ebx
0x18004f636  mov     rbx, [rsp+28h+arg_0]
0x18004f63b  mov     rsi, [rsp+28h+arg_8]
0x18004f640  add     rsp, 20h
0x18004f644  pop     rdi
0x18004f645  retn
0x18004f646  test    ebx, ebx
0x18004f648  js      short loc_18004F614
0x18004f64a  call    cs:__imp_SwitchToThread
0x18004f650  mov     ebx, [rdi+4E0h]
0x18004f656  mov     rax, [rdi+48h]
0x18004f65a  mov     rcx, [rax+438h]
0x18004f661  mov     eax, [rcx+9968h]
0x18004f667  test    eax, eax
0x18004f669  jz      short loc_18004F614
0x18004f66b  jmp     short loc_18004F646
0x18004f66d  mov     rax, [rdi+10h]
0x18004f671  lea     rcx, [rdi+10h]
0x18004f675  mov     edx, 887A0005h
0x18004f67a  mov     rax, [rax+108h]
0x18004f681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f686  mov     eax, [rdi+4E0h]
0x18004f68c  mov     rbx, [rsp+28h+arg_0]
0x18004f691  mov     rsi, [rsp+28h+arg_8]
0x18004f696  add     rsp, 20h
0x18004f69a  pop     rdi
0x18004f69b  retn
```
