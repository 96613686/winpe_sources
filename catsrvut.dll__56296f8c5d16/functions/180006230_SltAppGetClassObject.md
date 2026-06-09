# SltAppGetClassObject

- ea: `0x180006230`
- end: `0x1800062f9`
- name: `SltAppGetClassObject`
- size: `201`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180002440`

## callees

- `0x180006230`
- `0x1800073c4`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800062c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800062c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006287`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006287`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SltAppGetClassObject(_QWORD *a1, __int64 a2, _QWORD *a3)
{
  __int64 v6; // rax
  CLTApp *v7; // rax
  CLTApp *v8; // rax
  CLTApp *v9; // rsi
  int v10; // ebx

  if ( !a3 )
    return 2147942487LL;
  *a3 = 0;
  v6 = clsidSLTAPP - *a1;
  if ( clsidSLTAPP == *a1 )
    v6 = 0x291C23C9A0008682LL - a1[1];
  if ( v6 )
  {
    return (unsigned int)-2147221231;
  }
  else
  {
    v7 = (CLTApp *)CoTaskMemAlloc(0x50u);
    if ( !v7 )
      return 2147942414LL;
    v8 = CLTApp::CLTApp(v7);
    v9 = v8;
    if ( !v8 )
      return 2147942414LL;
    v10 = (**(__int64 (__fastcall ***)(CLTApp *, __int64, _QWORD *))v8)(v8, a2, a3);
    if ( v10 < 0 )
      CoTaskMemFree(v9);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180006230  mov     [rsp+arg_0], rbx
0x180006235  mov     [rsp+arg_8], rsi
0x18000623a  push    rdi
0x18000623b  sub     rsp, 20h
0x18000623f  mov     rbx, r8
0x180006242  mov     rdi, rdx
0x180006245  test    r8, r8
0x180006248  jnz     short loc_18000625F
0x18000624a  mov     eax, 80070057h
0x18000624f  mov     rbx, [rsp+28h+arg_0]
0x180006254  mov     rsi, [rsp+28h+arg_8]
0x180006259  add     rsp, 20h
0x18000625d  pop     rdi
0x18000625e  retn
0x18000625f  mov     qword ptr [r8], 0
0x180006266  mov     rax, cs:clsidSLTAPP
0x18000626d  sub     rax, [rcx]
0x180006270  jnz     short loc_18000627D
0x180006272  mov     rax, cs:qword_180061190
0x180006279  sub     rax, [rcx+8]
0x18000627d  test    rax, rax
0x180006280  jnz     short loc_1800062E2
0x180006282  mov     ecx, 50h ; 'P'; cb
0x180006287  call    cs:__imp_CoTaskMemAlloc
0x18000628d  mov     [rsp+28h+arg_10], rax
0x180006292  test    rax, rax
0x180006295  jz      short loc_1800062CD
0x180006297  mov     rcx, rax; this
0x18000629a  call    ??0CLTApp@@QEAA@XZ; CLTApp::CLTApp(void)
0x18000629f  mov     rsi, rax
0x1800062a2  test    rax, rax
0x1800062a5  jz      short loc_1800062CD
0x1800062a7  mov     rcx, [rax]
0x1800062aa  mov     rax, [rcx]
0x1800062ad  mov     r8, rbx
0x1800062b0  mov     rdx, rdi
0x1800062b3  mov     rcx, rsi
0x1800062b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062bb  mov     ebx, eax
0x1800062bd  test    eax, eax
0x1800062bf  jns     short loc_1800062E7
0x1800062c1  mov     rcx, rsi; pv
0x1800062c4  call    cs:__imp_CoTaskMemFree
0x1800062ca  nop
0x1800062cb  jmp     short loc_1800062E7
0x1800062cd  mov     eax, 8007000Eh
0x1800062d2  mov     rbx, [rsp+28h+arg_0]
0x1800062d7  mov     rsi, [rsp+28h+arg_8]
0x1800062dc  add     rsp, 20h
0x1800062e0  pop     rdi
0x1800062e1  retn
0x1800062e2  mov     ebx, 80040111h
0x1800062e7  mov     eax, ebx
0x1800062e9  mov     rbx, [rsp+28h+arg_0]
0x1800062ee  mov     rsi, [rsp+28h+arg_8]
0x1800062f3  add     rsp, 20h
0x1800062f7  pop     rdi
0x1800062f8  retn
```
