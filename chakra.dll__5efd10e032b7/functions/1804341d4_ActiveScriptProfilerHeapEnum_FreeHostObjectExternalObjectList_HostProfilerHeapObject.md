# ActiveScriptProfilerHeapEnum::FreeHostObjectExternalObjectList(HostProfilerHeapObject &)

- ea: `0x1804341d4`
- end: `0x180434260`
- name: `?FreeHostObjectExternalObjectList@ActiveScriptProfilerHeapEnum@@AEAAXAEAUHostProfilerHeapObject@@@Z`
- size: `140`
- prototype: `void __fastcall(ActiveScriptProfilerHeapEnum *__hidden this, struct HostProfilerHeapObject *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180434268`

## callees

- `0x18043415c`
- `0x1804341d4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18043421f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180434238`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18043421f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180434238`

## pseudocode

```c
void __fastcall ActiveScriptProfilerHeapEnum::FreeHostObjectExternalObjectList(
        ActiveScriptProfilerHeapEnum *this,
        struct HostProfilerHeapObject *a2)
{
  ActiveScriptProfilerHeapEnum *v3; // rcx
  unsigned int v4; // ebp
  LPVOID *v5; // rdi

  ActiveScriptProfilerHeapEnum::FreeBSTR(this, a2);
  if ( *((_WORD *)a2 + 13) )
  {
    v4 = 0;
    v5 = (LPVOID *)((char *)a2 + 32);
    do
    {
      ActiveScriptProfilerHeapEnum::FreeBSTR(v3, *((struct HostProfilerHeapObject **)*v5 + v4));
      CoTaskMemFree(*((LPVOID *)*v5 + v4++));
    }
    while ( v4 < *((unsigned __int16 *)a2 + 13) );
    CoTaskMemFree(*v5);
    *v5 = 0;
    *((_WORD *)a2 + 13) = 0;
  }
}

```

## disassembly

```asm
0x1804341d4  mov     rax, rsp
0x1804341d7  mov     [rax+18h], rbx
0x1804341db  mov     [rax+20h], rbp
0x1804341df  mov     [rax+10h], rdx
0x1804341e3  mov     [rax+8], rcx
0x1804341e7  push    rsi
0x1804341e8  push    rdi
0x1804341e9  push    r14
0x1804341eb  sub     rsp, 20h
0x1804341ef  mov     rsi, rdx
0x1804341f2  call    ?FreeBSTR@ActiveScriptProfilerHeapEnum@@AEAAXPEAUHostProfilerHeapObject@@@Z; ActiveScriptProfilerHeapEnum::FreeBSTR(HostProfilerHeapObject *)
0x1804341f7  xor     r14d, r14d
0x1804341fa  cmp     [rsi+1Ah], r14w
0x1804341ff  jz      short loc_18043424C
0x180434201  mov     ebp, r14d
0x180434204  lea     rdi, [rsi+20h]
0x180434208  jbe     short loc_180434235
0x18043420a  mov     rdx, [rdi]
0x18043420d  mov     ebx, ebp
0x18043420f  mov     rdx, [rdx+rbx*8]; struct HostProfilerHeapObject *
0x180434213  call    ?FreeBSTR@ActiveScriptProfilerHeapEnum@@AEAAXPEAUHostProfilerHeapObject@@@Z; ActiveScriptProfilerHeapEnum::FreeBSTR(HostProfilerHeapObject *)
0x180434218  mov     rcx, [rdi]
0x18043421b  mov     rcx, [rcx+rbx*8]; pv
0x18043421f  call    cs:__imp_CoTaskMemFree
0x180434226  nop     dword ptr [rax+rax+00h]
0x18043422b  movzx   eax, word ptr [rsi+1Ah]
0x18043422f  inc     ebp
0x180434231  cmp     ebp, eax
0x180434233  jb      short loc_18043420A
0x180434235  mov     rcx, [rdi]; pv
0x180434238  call    cs:__imp_CoTaskMemFree
0x18043423f  nop     dword ptr [rax+rax+00h]
0x180434244  mov     [rdi], r14
0x180434247  mov     [rsi+1Ah], r14w
0x18043424c  mov     rbx, [rsp+38h+arg_10]
0x180434251  mov     rbp, [rsp+38h+arg_18]
0x180434256  add     rsp, 20h
0x18043425a  pop     r14
0x18043425c  pop     rdi
0x18043425d  pop     rsi
0x18043425e  retn
```
