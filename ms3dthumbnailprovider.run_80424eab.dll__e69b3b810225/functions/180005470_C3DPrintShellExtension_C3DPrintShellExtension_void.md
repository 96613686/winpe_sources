# C3DPrintShellExtension::~C3DPrintShellExtension(void)

- ea: `0x180005470`
- end: `0x1800054bb`
- name: `??1C3DPrintShellExtension@@EEAA@XZ`
- size: `75`
- prototype: `void __fastcall(C3DPrintShellExtension *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005900`

## callees

- `0x180005470`
- `0x18000b010`

## pseudocode

```c
void __fastcall C3DPrintShellExtension::~C3DPrintShellExtension(C3DPrintShellExtension *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &C3DPrintShellExtension::`vftable';
  *((_QWORD *)this + 1) = &C3DPrintShellExtension::`vftable'{for `IInitializeCommand'};
  *((_QWORD *)this + 2) = &C3DPrintShellExtension::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IObjectWithSelection>'};
  v2 = *((_QWORD *)this + 4);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  *((_DWORD *)this + 7) = -1073741823;
}

```

## disassembly

```asm
0x180005470  push    rbx
0x180005472  sub     rsp, 20h
0x180005476  mov     rbx, rcx
0x180005479  lea     rax, ??_7C3DPrintShellExtension@@6B@; const C3DPrintShellExtension::`vftable'
0x180005480  mov     [rcx], rax
0x180005483  lea     rax, ??_7C3DPrintShellExtension@@6BIInitializeCommand@@@; const C3DPrintShellExtension::`vftable'{for `IInitializeCommand'}
0x18000548a  mov     [rcx+8], rax
0x18000548e  lea     rax, ??_7C3DPrintShellExtension@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIObjectWithSelection@@@Details@WRL@Microsoft@@@; const C3DPrintShellExtension::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IObjectWithSelection>'}
0x180005495  mov     [rcx+10h], rax
0x180005499  mov     rcx, [rcx+20h]
0x18000549d  test    rcx, rcx
0x1800054a0  jz      short loc_1800054AE
0x1800054a2  mov     rax, [rcx]
0x1800054a5  mov     rax, [rax+10h]
0x1800054a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054ae  mov     dword ptr [rbx+1Ch], 0C0000001h
0x1800054b5  add     rsp, 20h
0x1800054b9  pop     rbx
0x1800054ba  retn
```
