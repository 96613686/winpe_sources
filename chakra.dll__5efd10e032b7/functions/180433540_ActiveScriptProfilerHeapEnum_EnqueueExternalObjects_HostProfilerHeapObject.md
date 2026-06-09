# ActiveScriptProfilerHeapEnum::EnqueueExternalObjects(HostProfilerHeapObject *)

- ea: `0x180433540`
- end: `0x1804336a6`
- name: `?EnqueueExternalObjects@ActiveScriptProfilerHeapEnum@@AEAAXPEAUHostProfilerHeapObject@@@Z`
- size: `358`
- prototype: `void __fastcall(ActiveScriptProfilerHeapEnum *__hidden this, struct HostProfilerHeapObject *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18043546c`

## callees

- `0x18002e3d0`
- `0x1803c4080`
- `0x180433540`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180433677`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180433677`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18043358f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18043358f`

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
  __int64 v12; // rax
  __int64 v13; // rcx
  char *(__fastcall *v14)(Memory::ArenaAllocator *__hidden, unsigned __int64); // [rsp+20h] [rbp-68h] BYREF
  int v15; // [rsp+28h] [rbp-60h]
  int v16; // [rsp+2Ch] [rbp-5Ch]
  int v17; // [rsp+51h] [rbp-37h]
  __int16 v18; // [rsp+55h] [rbp-33h]
  char v19; // [rsp+57h] [rbp-31h]

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
      v11 = *((_QWORD *)this + 62);
      v14 = Memory::ArenaAllocator::Alloc;
      v12 = operator new<Memory::JitArenaAllocator>(64, v11, &v14);
      if ( !v12 )
LABEL_7:
        Js::Throw::OutOfMemory();
      ++v4;
      *(_DWORD *)(v12 + 49) = v17;
      *(_WORD *)(v12 + 53) = v18;
      *(_QWORD *)(v12 + 16) = 0;
      *(_QWORD *)(v12 + 24) = 0;
      *(_QWORD *)(v12 + 32) = 0;
      *(_QWORD *)(v12 + 40) = 0;
      *(_BYTE *)(v12 + 48) = 0;
      *(_BYTE *)(v12 + 55) = v19;
      *(_QWORD *)(v12 + 56) = v9;
      v13 = *((_QWORD *)this + 61);
      *(_QWORD *)(v12 + 8) = v13;
      *(_QWORD *)v12 = *(_QWORD *)v13;
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
0x180433540  mov     rax, rsp
0x180433543  mov     [rax+18h], rbx
0x180433547  mov     [rax+20h], rbp
0x18043354b  mov     [rax+10h], rdx
0x18043354f  mov     [rax+8], rcx
0x180433553  push    rsi
0x180433554  push    rdi
0x180433555  push    r12
0x180433557  push    r14
0x180433559  push    r15
0x18043355b  sub     rsp, 60h
0x18043355f  xor     r12d, r12d
0x180433562  mov     rdi, rdx
0x180433565  cmp     [rdx+1Ah], r12w
0x18043356a  jz      loc_18043368C
0x180433570  mov     r15, [rdx+20h]
0x180433574  mov     ebp, r12d
0x180433577  mov     ebx, [rsp+88h+var_5C]
0x18043357b  mov     r14, rcx
0x18043357e  movzx   eax, word ptr [rdi+1Ah]
0x180433582  cmp     ebp, eax
0x180433584  jnb     loc_18043366E
0x18043358a  mov     ecx, 30h ; '0'; cb
0x18043358f  call    cs:__imp_CoTaskMemAlloc
0x180433596  nop     dword ptr [rax+rax+00h]
0x18043359b  mov     rsi, rax
0x18043359e  test    rax, rax
0x1804335a1  jz      loc_180433668
0x1804335a7  xorps   xmm0, xmm0
0x1804335aa  mov     r8d, ebp
0x1804335ad  movups  xmmword ptr [rax], xmm0
0x1804335b0  mov     [rsp+88h+var_60], r12d
0x1804335b5  movups  xmmword ptr [rax+10h], xmm0
0x1804335b9  mov     [rsp+88h+var_5C], ebx
0x1804335bd  movups  xmmword ptr [rax+20h], xmm0
0x1804335c1  mov     rdx, [r15+r8*8]
0x1804335c5  mov     ecx, [rdx]
0x1804335c7  mov     [rax+8], ecx
0x1804335ca  mov     rcx, [rdx+8]
0x1804335ce  mov     [rax+10h], rcx
0x1804335d2  mov     ecx, 40h ; '@'
0x1804335d7  mov     eax, [rdx+10h]
0x1804335da  mov     [rsi+18h], eax
0x1804335dd  mov     eax, [rdx+14h]
0x1804335e0  mov     [rsi+1Ch], eax
0x1804335e3  movzx   eax, word ptr [rdx+28h]
0x1804335e7  mov     [rsi+22h], ax
0x1804335eb  mov     rax, [r15+r8*8]
0x1804335ef  lea     r8, [rsp+88h+var_68]
0x1804335f4  mov     [rsi], rax
0x1804335f7  lea     rax, ?Alloc@ArenaAllocator@Memory@@QEAAPEAD_K@Z; Memory::ArenaAllocator::Alloc(unsigned __int64)
0x1804335fe  mov     rdx, [r14+1F0h]
0x180433605  mov     [rsp+88h+var_68], rax
0x18043360a  call    ??$?2VJitArenaAllocator@Memory@@@@YAPEAX_KPEAVJitArenaAllocator@Memory@@P801@EAAPEAD0@Z@Z; operator new<Memory::JitArenaAllocator>(unsigned __int64,Memory::JitArenaAllocator *,char * (Memory::JitArenaAllocator::*)(unsigned __int64))
0x18043360f  mov     rdx, rax
0x180433612  test    rax, rax
0x180433615  jz      short loc_180433668
0x180433617  mov     ecx, [rsp+88h+var_37]
0x18043361b  inc     ebp
0x18043361d  mov     [rax+31h], ecx
0x180433620  movzx   ecx, [rsp+88h+var_33]
0x180433625  mov     [rax+35h], cx
0x180433629  mov     [rax+10h], r12
0x18043362d  mov     [rax+18h], r12
0x180433631  mov     [rax+20h], r12
0x180433635  mov     [rax+28h], r12
0x180433639  mov     [rax+30h], r12b
0x18043363d  mov     al, [rsp+88h+var_31]
0x180433641  mov     [rdx+37h], al
0x180433644  mov     [rdx+38h], rsi
0x180433648  mov     rcx, [r14+1E8h]
0x18043364f  mov     [rdx+8], rcx
0x180433653  mov     rax, [rcx]
0x180433656  mov     [rdx], rax
0x180433659  mov     rax, [rcx]
0x18043365c  mov     [rax+8], rdx
0x180433660  mov     [rcx], rdx
0x180433663  jmp     loc_18043357E
0x180433668  call    ?OutOfMemory@Throw@Js@@SAXXZ; Js::Throw::OutOfMemory(void)
0x18043366e  test    ax, ax
0x180433671  jz      short loc_18043368C
0x180433673  mov     rcx, [rdi+20h]; pv
0x180433677  call    cs:__imp_CoTaskMemFree
0x18043367e  nop     dword ptr [rax+rax+00h]
0x180433683  mov     [rdi+20h], r12
0x180433687  mov     [rdi+1Ah], r12w
0x18043368c  lea     r11, [rsp+88h+var_28]
0x180433691  mov     rbx, [r11+40h]
0x180433695  mov     rbp, [r11+48h]
0x180433699  mov     rsp, r11
0x18043369c  pop     r15
0x18043369e  pop     r14
0x1804336a0  pop     r12
0x1804336a2  pop     rdi
0x1804336a3  pop     rsi
0x1804336a4  retn
```
