# ActiveScriptProfilerHeapEnum::FreeObjectAndOptionalInfo(ActiveScriptProfilerHeapEnum::ProfilerHeapObject *)

- ea: `0x1801d4958`
- end: `0x1801d49f4`
- name: `?FreeObjectAndOptionalInfo@ActiveScriptProfilerHeapEnum@@AEAAXPEAUProfilerHeapObject@1@@Z`
- size: `156`
- prototype: `void __fastcall(ActiveScriptProfilerHeapEnum *__hidden this, struct ActiveScriptProfilerHeapEnum::ProfilerHeapObject *)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1801d2648`
- `0x1801d3038`
- `0x1801d4a00`

## callees

- `0x1801d48e4`
- `0x1801d4958`

## import_xrefs

- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801d49ad`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801d49c0`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801d49d1`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801d49ad`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801d49c0`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801d49d1`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801d49ed`

## pseudocode

```c
void __fastcall ActiveScriptProfilerHeapEnum::FreeObjectAndOptionalInfo(ActiveScriptProfilerHeapEnum *this, LPVOID *a2)
{
  char *v2; // rdi
  ActiveScriptProfilerHeapEnum *v4; // rcx
  unsigned int v5; // ebp
  LPVOID *v6; // r14

  v2 = (char *)*a2;
  if ( *a2 )
  {
    ActiveScriptProfilerHeapEnum::FreeBSTR(this, (struct HostProfilerHeapObject *)v2);
    if ( *((_WORD *)v2 + 13) )
    {
      v5 = 0;
      v6 = (LPVOID *)(v2 + 32);
      do
      {
        ActiveScriptProfilerHeapEnum::FreeBSTR(v4, *((struct HostProfilerHeapObject **)*v6 + v5));
        CoTaskMemFree(*((LPVOID *)*v6 + v5++));
      }
      while ( v5 < *((unsigned __int16 *)v2 + 13) );
      CoTaskMemFree(*v6);
      *v6 = 0;
      *((_WORD *)v2 + 13) = 0;
    }
    CoTaskMemFree(*a2);
    *a2 = 0;
  }
  CoTaskMemFree(a2);
}

```

## disassembly

```asm
0x1801d4958  mov     rax, rsp
0x1801d495b  mov     [rax+18h], rbx
0x1801d495f  mov     [rax+10h], rdx
0x1801d4963  mov     [rax+8], rcx
0x1801d4967  push    rbp
0x1801d4968  push    rsi
0x1801d4969  push    rdi
0x1801d496a  push    r14
0x1801d496c  push    r15
0x1801d496e  sub     rsp, 20h
0x1801d4972  mov     rdi, [rdx]
0x1801d4975  xor     r15d, r15d
0x1801d4978  mov     rsi, rdx
0x1801d497b  test    rdi, rdi
0x1801d497e  jz      short loc_1801D49DA
0x1801d4980  mov     rdx, rdi; struct HostProfilerHeapObject *
0x1801d4983  call    ?FreeBSTR@ActiveScriptProfilerHeapEnum@@AEAAXPEAUHostProfilerHeapObject@@@Z; ActiveScriptProfilerHeapEnum::FreeBSTR(HostProfilerHeapObject *)
0x1801d4988  cmp     [rdi+1Ah], r15w
0x1801d498d  jz      short loc_1801D49CE
0x1801d498f  mov     ebp, r15d
0x1801d4992  lea     r14, [rdi+20h]
0x1801d4996  jbe     short loc_1801D49BD
0x1801d4998  mov     rdx, [r14]
0x1801d499b  mov     ebx, ebp
0x1801d499d  mov     rdx, [rdx+rbx*8]; struct HostProfilerHeapObject *
0x1801d49a1  call    ?FreeBSTR@ActiveScriptProfilerHeapEnum@@AEAAXPEAUHostProfilerHeapObject@@@Z; ActiveScriptProfilerHeapEnum::FreeBSTR(HostProfilerHeapObject *)
0x1801d49a6  mov     rcx, [r14]
0x1801d49a9  mov     rcx, [rcx+rbx*8]; pv
0x1801d49ad  call    cs:__imp_CoTaskMemFree
0x1801d49b3  movzx   eax, word ptr [rdi+1Ah]
0x1801d49b7  inc     ebp
0x1801d49b9  cmp     ebp, eax
0x1801d49bb  jb      short loc_1801D4998
0x1801d49bd  mov     rcx, [r14]; pv
0x1801d49c0  call    cs:__imp_CoTaskMemFree
0x1801d49c6  mov     [r14], r15
0x1801d49c9  mov     [rdi+1Ah], r15w
0x1801d49ce  mov     rcx, [rsi]; pv
0x1801d49d1  call    cs:__imp_CoTaskMemFree
0x1801d49d7  mov     [rsi], r15
0x1801d49da  mov     rcx, rsi
0x1801d49dd  mov     rbx, [rsp+48h+arg_10]
0x1801d49e2  add     rsp, 20h
0x1801d49e6  pop     r15
0x1801d49e8  pop     r14
0x1801d49ea  pop     rdi
0x1801d49eb  pop     rsi
0x1801d49ec  pop     rbp
0x1801d49ed  jmp     cs:__imp_CoTaskMemFree
```
