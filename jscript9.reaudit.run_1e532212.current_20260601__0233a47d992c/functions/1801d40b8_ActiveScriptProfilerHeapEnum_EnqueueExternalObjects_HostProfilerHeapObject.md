# ActiveScriptProfilerHeapEnum::EnqueueExternalObjects(HostProfilerHeapObject *)

- ea: `0x1801d40b8`
- end: `0x1801d41e9`
- name: `?EnqueueExternalObjects@ActiveScriptProfilerHeapEnum@@AEAAXPEAUHostProfilerHeapObject@@@Z`
- size: `305`
- prototype: `void __fastcall(ActiveScriptProfilerHeapEnum *__hidden this, struct HostProfilerHeapObject *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1801d6264`

## callees

- `0x180109220`
- `0x1801aa070`
- `0x1801d40b8`

## import_xrefs

- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x1801d4107`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x1801d4107`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801d41c3`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801d41c3`

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
0x1801d40b8  mov     rax, rsp
0x1801d40bb  mov     [rax+18h], rbx
0x1801d40bf  mov     [rax+20h], rbp
0x1801d40c3  mov     [rax+10h], rdx
0x1801d40c7  mov     [rax+8], rcx
0x1801d40cb  push    rsi
0x1801d40cc  push    rdi
0x1801d40cd  push    r12
0x1801d40cf  push    r14
0x1801d40d1  push    r15
0x1801d40d3  sub     rsp, 30h
0x1801d40d7  xor     r12d, r12d
0x1801d40da  mov     rdi, rdx
0x1801d40dd  cmp     [rdx+1Ah], r12w
0x1801d40e2  jz      loc_1801D41D2
0x1801d40e8  mov     r15, [rdx+20h]
0x1801d40ec  mov     ebp, r12d
0x1801d40ef  mov     ebx, [rsp+58h+var_2C]
0x1801d40f3  mov     r14, rcx
0x1801d40f6  movzx   eax, word ptr [rdi+1Ah]
0x1801d40fa  cmp     ebp, eax
0x1801d40fc  jnb     loc_1801D41BA
0x1801d4102  mov     ecx, 30h ; '0'; cb
0x1801d4107  call    cs:__imp_CoTaskMemAlloc
0x1801d410d  mov     rsi, rax
0x1801d4110  test    rax, rax
0x1801d4113  jz      loc_1801D41B4
0x1801d4119  xorps   xmm0, xmm0
0x1801d411c  mov     r8d, ebp
0x1801d411f  movups  xmmword ptr [rax], xmm0
0x1801d4122  mov     [rsp+58h+var_30], r12d
0x1801d4127  movups  xmmword ptr [rax+10h], xmm0
0x1801d412b  mov     [rsp+58h+var_2C], ebx
0x1801d412f  movups  xmmword ptr [rax+20h], xmm0
0x1801d4133  mov     rdx, [r15+r8*8]
0x1801d4137  mov     ecx, [rdx]
0x1801d4139  mov     [rax+8], ecx
0x1801d413c  mov     rcx, [rdx+8]
0x1801d4140  mov     [rax+10h], rcx
0x1801d4144  mov     ecx, 28h ; '('
0x1801d4149  mov     eax, [rdx+10h]
0x1801d414c  mov     [rsi+18h], eax
0x1801d414f  mov     eax, [rdx+14h]
0x1801d4152  mov     [rsi+1Ch], eax
0x1801d4155  movzx   eax, word ptr [rdx+28h]
0x1801d4159  mov     [rsi+22h], ax
0x1801d415d  mov     rax, [r15+r8*8]
0x1801d4161  lea     r8, [rsp+58h+var_38]
0x1801d4166  mov     [rsi], rax
0x1801d4169  lea     rax, ?Alloc@ArenaAllocator@@QEAAPEAD_K@Z; ArenaAllocator::Alloc(unsigned __int64)
0x1801d4170  mov     rdx, [r14+158h]
0x1801d4177  mov     [rsp+58h+var_38], rax
0x1801d417c  call    ??$?2VArenaAllocator@@@@YAPEAX_KPEAVArenaAllocator@@P80@EAAPEAD0@Z@Z; operator new<ArenaAllocator>(unsigned __int64,ArenaAllocator *,char * (ArenaAllocator::*)(unsigned __int64))
0x1801d4181  test    rax, rax
0x1801d4184  jz      short loc_1801D41B4
0x1801d4186  mov     [rax+10h], r12
0x1801d418a  inc     ebp
0x1801d418c  mov     [rax+18h], r12
0x1801d4190  mov     [rax+20h], rsi
0x1801d4194  mov     rdx, [r14+150h]
0x1801d419b  mov     [rax+8], rdx
0x1801d419f  mov     rcx, [rdx]
0x1801d41a2  mov     [rax], rcx
0x1801d41a5  mov     rcx, [rdx]
0x1801d41a8  mov     [rcx+8], rax
0x1801d41ac  mov     [rdx], rax
0x1801d41af  jmp     loc_1801D40F6
0x1801d41b4  call    ?OutOfMemory@Throw@Js@@SAXXZ; Js::Throw::OutOfMemory(void)
0x1801d41ba  test    ax, ax
0x1801d41bd  jz      short loc_1801D41D2
0x1801d41bf  mov     rcx, [rdi+20h]; pv
0x1801d41c3  call    cs:__imp_CoTaskMemFree
0x1801d41c9  mov     [rdi+20h], r12
0x1801d41cd  mov     [rdi+1Ah], r12w
0x1801d41d2  mov     rbx, [rsp+58h+arg_10]
0x1801d41d7  mov     rbp, [rsp+58h+arg_18]
0x1801d41dc  add     rsp, 30h
0x1801d41e0  pop     r15
0x1801d41e2  pop     r14
0x1801d41e4  pop     r12
0x1801d41e6  pop     rdi
0x1801d41e7  pop     rsi
0x1801d41e8  retn
```
