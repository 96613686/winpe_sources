# CleanupStack::Done(long)

- ea: `0x18002abf4`
- end: `0x18002ac90`
- name: `?Done@CleanupStack@@QEAAXJ@Z`
- size: `156`
- prototype: `void __fastcall(CleanupStack *__hidden this, int)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800279e0`
- `0x180029f04`
- `0x18002aaa0`
- `0x1800505b4`

## callees

- `0x18002abf4`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ac28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ac28`

## pseudocode

```c
void __fastcall CleanupStack::Done(CleanupStack *this, int a2)
{
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // r8

  while ( 1 )
  {
    if ( a2 < 0 )
    {
      while ( 1 )
      {
        v6 = *((_QWORD *)this + 43);
        if ( !*(_DWORD *)(v6 + 320) )
          break;
        v5 = *(_QWORD *)(v6 + 16LL * (unsigned int)--*(_DWORD *)(v6 + 320) + 8);
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v5 + 8LL))(
          v5,
          *(_QWORD *)(v6 + 16LL * *(unsigned int *)(v6 + 320)));
      }
    }
    v4 = *(_QWORD *)(*((_QWORD *)this + 43) + 328LL);
    *((_QWORD *)this + 43) = v4;
    if ( !v4 )
      break;
    CoTaskMemFree(*(LPVOID *)(v4 + 336));
    *(_QWORD *)(*((_QWORD *)this + 43) + 336LL) = 0;
  }
  *((_QWORD *)this + 43) = this;
}

```

## disassembly

```asm
0x18002abf4  mov     [rsp+arg_0], rbx
0x18002abf9  push    rdi
0x18002abfa  sub     rsp, 20h
0x18002abfe  mov     edi, edx
0x18002ac00  mov     rbx, rcx
0x18002ac03  test    edi, edi
0x18002ac05  js      short loc_18002AC7A
0x18002ac07  mov     rax, [rbx+158h]
0x18002ac0e  mov     rcx, [rax+148h]
0x18002ac15  mov     [rbx+158h], rcx
0x18002ac1c  test    rcx, rcx
0x18002ac1f  jz      short loc_18002AC42
0x18002ac21  mov     rcx, [rcx+150h]; pv
0x18002ac28  call    cs:__imp_CoTaskMemFree
0x18002ac2e  mov     rax, [rbx+158h]
0x18002ac35  mov     qword ptr [rax+150h], 0
0x18002ac40  jmp     short loc_18002AC03
0x18002ac42  mov     [rbx+158h], rbx
0x18002ac49  mov     rbx, [rsp+28h+arg_0]
0x18002ac4e  add     rsp, 20h
0x18002ac52  pop     rdi
0x18002ac53  retn
0x18002ac54  dec     dword ptr [r8+140h]
0x18002ac5b  mov     edx, [r8+140h]
0x18002ac62  add     rdx, rdx
0x18002ac65  mov     rcx, [r8+rdx*8+8]
0x18002ac6a  mov     rdx, [r8+rdx*8]
0x18002ac6e  mov     rax, [rcx]
0x18002ac71  mov     rax, [rax+8]
0x18002ac75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac7a  mov     r8, [rbx+158h]
0x18002ac81  cmp     dword ptr [r8+140h], 0
0x18002ac89  ja      short loc_18002AC54
0x18002ac8b  jmp     loc_18002AC07
```
