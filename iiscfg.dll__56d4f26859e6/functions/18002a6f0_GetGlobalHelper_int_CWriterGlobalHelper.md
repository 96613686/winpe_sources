# GetGlobalHelper(int,CWriterGlobalHelper * *)

- ea: `0x18002a6f0`
- end: `0x18002a80f`
- name: `?GetGlobalHelper@@YAJHPEAPEAVCWriterGlobalHelper@@@Z`
- size: `287`
- prototype: `__int64 __fastcall(int, struct CWriterGlobalHelper **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18002a818`

## callees

- `0x18002a39c`
- `0x18002a6f0`
- `0x18002a998`
- `0x18002cf48`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18002a72d`
- `ole32!CoTaskMemAlloc` at `0x18002a72d`

## string_xrefs

- `0x18002a77c`: `IIsConfigObject`

## pseudocode

```c
__int64 __fastcall GetGlobalHelper(__int64 a1, struct CWriterGlobalHelper **a2)
{
  bool v3; // zf
  struct CWriterGlobalHelper *v4; // rax
  struct CWriterGlobalHelper *v5; // rbx
  unsigned int v6; // edx
  int v7; // esi

  v3 = dword_18004266C == 0;
  *a2 = 0;
  if ( v3 )
  {
    InitializeLengths();
    dword_18004266C = 1;
  }
  if ( *a2 )
  {
    CWriterGlobalHelper::`scalar deleting destructor'(*a2, (unsigned int)a2);
    *a2 = 0;
  }
  v4 = (struct CWriterGlobalHelper *)CoTaskMemAlloc(0x158u);
  v5 = v4;
  if ( !v4 )
    return 2147942414LL;
  *((_QWORD *)v4 + 41) = 0;
  *((_QWORD *)v4 + 42) = 0;
  *(_QWORD *)v4 = 0;
  *((_QWORD *)v4 + 1) = 0;
  *((_QWORD *)v4 + 2) = 0;
  *((_QWORD *)v4 + 3) = 0;
  *((_QWORD *)v4 + 4) = 0;
  *((_QWORD *)v4 + 5) = 0;
  *((_QWORD *)v4 + 6) = 0;
  *((_QWORD *)v4 + 7) = 0;
  *((_QWORD *)v4 + 8) = 0;
  *((_DWORD *)v4 + 18) = 18;
  *((_QWORD *)v4 + 29) = L"IIsConfigObject";
  *((_QWORD *)v4 + 28) = L"MBProperty";
  *((_DWORD *)v4 + 60) = -1;
  *((_QWORD *)v4 + 31) = 0;
  *((_DWORD *)v4 + 64) = 0;
  *((_QWORD *)v4 + 33) = 0;
  *((_DWORD *)v4 + 68) = 0;
  *((_QWORD *)v4 + 35) = 0;
  *((_DWORD *)v4 + 72) = 0;
  *((_QWORD *)v4 + 37) = 0;
  *((_DWORD *)v4 + 76) = 0;
  *((_QWORD *)v4 + 39) = 0;
  *((_DWORD *)v4 + 80) = 0;
  v7 = CWriterGlobalHelper::InitializeGlobals(v4);
  if ( v7 >= 0 )
  {
    *a2 = v5;
    return 0;
  }
  else
  {
    CWriterGlobalHelper::`scalar deleting destructor'(v5, v6);
    return (unsigned int)v7;
  }
}

```

## disassembly

```asm
0x18002a6f0  push    rbx
0x18002a6f2  push    rbp
0x18002a6f3  push    rsi
0x18002a6f4  push    rdi
0x18002a6f5  sub     rsp, 28h
0x18002a6f9  xor     ebp, ebp
0x18002a6fb  mov     rdi, rdx
0x18002a6fe  cmp     cs:dword_18004266C, ebp
0x18002a704  mov     [rdx], rbp
0x18002a707  jnz     short loc_18002A718
0x18002a709  call    ?InitializeLengths@@YAJXZ; InitializeLengths(void)
0x18002a70e  mov     cs:dword_18004266C, 1
0x18002a718  mov     rcx, [rdi]; this
0x18002a71b  test    rcx, rcx
0x18002a71e  jz      short loc_18002A728
0x18002a720  call    ??_GCWriterGlobalHelper@@QEAAPEAXI@Z; CWriterGlobalHelper::`scalar deleting destructor'(uint)
0x18002a725  mov     [rdi], rbp
0x18002a728  mov     ecx, 158h; cb
0x18002a72d  call    cs:__imp_CoTaskMemAlloc
0x18002a733  mov     rbx, rax
0x18002a736  test    rax, rax
0x18002a739  jz      loc_18002A801
0x18002a73f  mov     [rax+148h], rbp
0x18002a746  xor     edx, edx; int
0x18002a748  mov     [rax+150h], rbp
0x18002a74f  mov     rcx, rbx; this
0x18002a752  mov     [rax], rbp
0x18002a755  mov     [rax+8], rbp
0x18002a759  mov     [rax+10h], rbp
0x18002a75d  mov     [rax+18h], rbp
0x18002a761  mov     [rax+20h], rbp
0x18002a765  mov     [rax+28h], rbp
0x18002a769  mov     [rax+30h], rbp
0x18002a76d  mov     [rax+38h], rbp
0x18002a771  mov     [rax+40h], rbp
0x18002a775  mov     dword ptr [rax+48h], 12h
0x18002a77c  lea     rax, aIisconfigobjec; "IIsConfigObject"
0x18002a783  mov     [rbx+0E8h], rax
0x18002a78a  lea     rax, aMbproperty; "MBProperty"
0x18002a791  mov     [rbx+0E0h], rax
0x18002a798  mov     dword ptr [rbx+0F0h], 0FFFFFFFFh
0x18002a7a2  mov     [rbx+0F8h], rbp
0x18002a7a9  mov     [rbx+100h], ebp
0x18002a7af  mov     [rbx+108h], rbp
0x18002a7b6  mov     [rbx+110h], ebp
0x18002a7bc  mov     [rbx+118h], rbp
0x18002a7c3  mov     [rbx+120h], ebp
0x18002a7c9  mov     [rbx+128h], rbp
0x18002a7d0  mov     [rbx+130h], ebp
0x18002a7d6  mov     [rbx+138h], rbp
0x18002a7dd  mov     [rbx+140h], ebp
0x18002a7e3  call    ?InitializeGlobals@CWriterGlobalHelper@@QEAAJH@Z; CWriterGlobalHelper::InitializeGlobals(int)
0x18002a7e8  mov     esi, eax
0x18002a7ea  test    eax, eax
0x18002a7ec  jns     short loc_18002A7FA
0x18002a7ee  mov     rcx, rbx; this
0x18002a7f1  call    ??_GCWriterGlobalHelper@@QEAAPEAXI@Z; CWriterGlobalHelper::`scalar deleting destructor'(uint)
0x18002a7f6  mov     eax, esi
0x18002a7f8  jmp     short loc_18002A806
0x18002a7fa  mov     [rdi], rbx
0x18002a7fd  xor     eax, eax
0x18002a7ff  jmp     short loc_18002A806
0x18002a801  mov     eax, 8007000Eh
0x18002a806  add     rsp, 28h
0x18002a80a  pop     rdi
0x18002a80b  pop     rsi
0x18002a80c  pop     rbp
0x18002a80d  pop     rbx
0x18002a80e  retn
```
