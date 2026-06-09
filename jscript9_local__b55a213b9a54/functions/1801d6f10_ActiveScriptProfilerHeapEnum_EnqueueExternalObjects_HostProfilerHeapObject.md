# ActiveScriptProfilerHeapEnum::EnqueueExternalObjects(HostProfilerHeapObject *)

- ea: `0x1801d6f10`
- end: `0x1801d704e`
- name: `?EnqueueExternalObjects@ActiveScriptProfilerHeapEnum@@AEAAXPEAUHostProfilerHeapObject@@@Z`
- size: `318`
- prototype: `void __fastcall(ActiveScriptProfilerHeapEnum *__hidden this, struct HostProfilerHeapObject *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1801d913c`

## callees

- `0x1801312b0`
- `0x1801acd90`
- `0x1801d6f10`

## import_xrefs

- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x1801d6f5f`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x1801d6f5f`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801d7021`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801d7021`

## pseudocode

```c
void __fastcall ActiveScriptProfilerHeapEnum::EnqueueExternalObjects(
        ActiveScriptProfilerHeapEnum *this,
        struct HostProfilerHeapObject *a2)
{
  __int64 v3; // r15
  unsigned int v4; // ebp
  int v5; // ebx
  unsigned int v7; // eax
  _OWORD *v8; // rax
  _OWORD *v9; // rsi
  __int64 v10; // rdx
  __int64 v11; // rdx
  _QWORD *v12; // rax
  __int64 v13; // rdx
  char *(__fastcall *v14)(ArenaAllocator *__hidden, unsigned __int64); // [rsp+20h] [rbp-38h] BYREF
  int v15; // [rsp+28h] [rbp-30h]
  int v16; // [rsp+2Ch] [rbp-2Ch]

  if ( *((_WORD *)a2 + 13) )
  {
    v3 = *((_QWORD *)a2 + 4);
    v4 = 0;
    v5 = v16;
    while ( 1 )
    {
      v7 = *((unsigned __int16 *)a2 + 13);
      if ( v4 >= v7 )
        break;
      v8 = CoTaskMemAlloc(0x30u);
      v9 = v8;
      if ( !v8 )
        goto LABEL_7;
      *v8 = 0;
      v15 = 0;
      v8[1] = 0;
      v16 = v5;
      v8[2] = 0;
      v10 = *(_QWORD *)(v3 + 8LL * v4);
      *((_DWORD *)v8 + 2) = *(_DWORD *)v10;
      *((_QWORD *)v8 + 2) = *(_QWORD *)(v10 + 8);
      *((_DWORD *)v8 + 6) = *(_DWORD *)(v10 + 16);
      *((_DWORD *)v8 + 7) = *(_DWORD *)(v10 + 20);
      *((_WORD *)v8 + 17) = *(_WORD *)(v10 + 40);
      *(_QWORD *)v8 = *(_QWORD *)(v3 + 8LL * v4);
      v11 = *((_QWORD *)this + 43);
      v14 = ArenaAllocator::Alloc;
      v12 = (_QWORD *)operator new<ArenaAllocator>(40, v11, &v14);
      if ( !v12 )
LABEL_7:
        Js::Throw::OutOfMemory();
      v12[2] = 0;
      ++v4;
      v12[3] = 0;
      v12[4] = v9;
      v13 = *((_QWORD *)this + 42);
      v12[1] = v13;
      *v12 = *(_QWORD *)v13;
      *(_QWORD *)(*(_QWORD *)v13 + 8LL) = v12;
      *(_QWORD *)v13 = v12;
    }
    if ( (_WORD)v7 )
    {
      CoTaskMemFree(*((LPVOID *)a2 + 4));
      *((_QWORD *)a2 + 4) = 0;
      *((_WORD *)a2 + 13) = 0;
    }
  }
}

```

## disassembly

```asm
0x1801d6f10  mov     rax, rsp
0x1801d6f13  mov     [rax+18h], rbx
0x1801d6f17  mov     [rax+20h], rbp
0x1801d6f1b  mov     [rax+10h], rdx
0x1801d6f1f  mov     [rax+8], rcx
0x1801d6f23  push    rsi
0x1801d6f24  push    rdi
0x1801d6f25  push    r12
0x1801d6f27  push    r14
0x1801d6f29  push    r15
0x1801d6f2b  sub     rsp, 30h
0x1801d6f2f  xor     r12d, r12d
0x1801d6f32  mov     rdi, rdx
0x1801d6f35  cmp     [rdx+1Ah], r12w
0x1801d6f3a  jz      loc_1801D7036
0x1801d6f40  mov     r15, [rdx+20h]
0x1801d6f44  mov     ebp, r12d
0x1801d6f47  mov     ebx, [rsp+58h+var_2C]
0x1801d6f4b  mov     r14, rcx
0x1801d6f4e  movzx   eax, word ptr [rdi+1Ah]
0x1801d6f52  cmp     ebp, eax
0x1801d6f54  jnb     loc_1801D7018
0x1801d6f5a  mov     ecx, 30h ; '0'; cb
0x1801d6f5f  call    cs:__imp_CoTaskMemAlloc
0x1801d6f66  nop     dword ptr [rax+rax+00h]
0x1801d6f6b  mov     rsi, rax
0x1801d6f6e  test    rax, rax
0x1801d6f71  jz      loc_1801D7012
0x1801d6f77  xorps   xmm0, xmm0
0x1801d6f7a  mov     r8d, ebp
0x1801d6f7d  movups  xmmword ptr [rax], xmm0
0x1801d6f80  mov     [rsp+58h+var_30], r12d
0x1801d6f85  movups  xmmword ptr [rax+10h], xmm0
0x1801d6f89  mov     [rsp+58h+var_2C], ebx
0x1801d6f8d  movups  xmmword ptr [rax+20h], xmm0
0x1801d6f91  mov     rdx, [r15+r8*8]
0x1801d6f95  mov     ecx, [rdx]
0x1801d6f97  mov     [rax+8], ecx
0x1801d6f9a  mov     rcx, [rdx+8]
0x1801d6f9e  mov     [rax+10h], rcx
0x1801d6fa2  mov     ecx, 28h ; '('
0x1801d6fa7  mov     eax, [rdx+10h]
0x1801d6faa  mov     [rsi+18h], eax
0x1801d6fad  mov     eax, [rdx+14h]
0x1801d6fb0  mov     [rsi+1Ch], eax
0x1801d6fb3  movzx   eax, word ptr [rdx+28h]
0x1801d6fb7  mov     [rsi+22h], ax
0x1801d6fbb  mov     rax, [r15+r8*8]
0x1801d6fbf  lea     r8, [rsp+58h+var_38]
0x1801d6fc4  mov     [rsi], rax
0x1801d6fc7  lea     rax, ?Alloc@ArenaAllocator@@QEAAPEAD_K@Z; ArenaAllocator::Alloc(unsigned __int64)
0x1801d6fce  mov     rdx, [r14+158h]
0x1801d6fd5  mov     [rsp+58h+var_38], rax
0x1801d6fda  call    ??$?2VArenaAllocator@@@@YAPEAX_KPEAVArenaAllocator@@P80@EAAPEAD0@Z@Z; operator new<ArenaAllocator>(unsigned __int64,ArenaAllocator *,char * (ArenaAllocator::*)(unsigned __int64))
0x1801d6fdf  test    rax, rax
0x1801d6fe2  jz      short loc_1801D7012
0x1801d6fe4  mov     [rax+10h], r12
0x1801d6fe8  inc     ebp
0x1801d6fea  mov     [rax+18h], r12
0x1801d6fee  mov     [rax+20h], rsi
0x1801d6ff2  mov     rdx, [r14+150h]
0x1801d6ff9  mov     [rax+8], rdx
0x1801d6ffd  mov     rcx, [rdx]
0x1801d7000  mov     [rax], rcx
0x1801d7003  mov     rcx, [rdx]
0x1801d7006  mov     [rcx+8], rax
0x1801d700a  mov     [rdx], rax
0x1801d700d  jmp     loc_1801D6F4E
0x1801d7012  call    ?OutOfMemory@Throw@Js@@SAXXZ; Js::Throw::OutOfMemory(void)
0x1801d7018  test    ax, ax
0x1801d701b  jz      short loc_1801D7036
0x1801d701d  mov     rcx, [rdi+20h]; pv
0x1801d7021  call    cs:__imp_CoTaskMemFree
0x1801d7028  nop     dword ptr [rax+rax+00h]
0x1801d702d  mov     [rdi+20h], r12
0x1801d7031  mov     [rdi+1Ah], r12w
0x1801d7036  mov     rbx, [rsp+58h+arg_10]
0x1801d703b  mov     rbp, [rsp+58h+arg_18]
0x1801d7040  add     rsp, 30h
0x1801d7044  pop     r15
0x1801d7046  pop     r14
0x1801d7048  pop     r12
0x1801d704a  pop     rdi
0x1801d704b  pop     rsi
0x1801d704c  retn
```
