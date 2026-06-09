# ActiveScriptProfilerHeapEnum::FreeHostObjectExternalObjectList(HostProfilerHeapObject &)

- ea: `0x1801d77c4`
- end: `0x1801d7850`
- name: `?FreeHostObjectExternalObjectList@ActiveScriptProfilerHeapEnum@@AEAAXAEAUHostProfilerHeapObject@@@Z`
- size: `140`
- prototype: `void __fastcall(ActiveScriptProfilerHeapEnum *this, BSTR *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1801d7858`

## callees

- `0x1801d774c`
- `0x1801d77c4`

## import_xrefs

- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801d780f`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801d7828`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801d780f`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801d7828`

## pseudocode

```c
void __fastcall ActiveScriptProfilerHeapEnum::FreeHostObjectExternalObjectList(
        ActiveScriptProfilerHeapEnum *this,
        BSTR *a2)
{
  ActiveScriptProfilerHeapEnum *v3; // rcx
  unsigned int v4; // ebp
  LPVOID *v5; // rdi

  ActiveScriptProfilerHeapEnum::FreeBSTR(this, a2);
  if ( *((_WORD *)a2 + 13) )
  {
    v4 = 0;
    v5 = (LPVOID *)(a2 + 4);
    do
    {
      ActiveScriptProfilerHeapEnum::FreeBSTR(v3, *((BSTR **)*v5 + v4));
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
0x1801d77c4  mov     rax, rsp
0x1801d77c7  mov     [rax+18h], rbx
0x1801d77cb  mov     [rax+20h], rbp
0x1801d77cf  mov     [rax+10h], rdx
0x1801d77d3  mov     [rax+8], rcx
0x1801d77d7  push    rsi
0x1801d77d8  push    rdi
0x1801d77d9  push    r14
0x1801d77db  sub     rsp, 20h
0x1801d77df  mov     rsi, rdx
0x1801d77e2  call    ?FreeBSTR@ActiveScriptProfilerHeapEnum@@AEAAXPEAUHostProfilerHeapObject@@@Z; ActiveScriptProfilerHeapEnum::FreeBSTR(HostProfilerHeapObject *)
0x1801d77e7  xor     r14d, r14d
0x1801d77ea  cmp     [rsi+1Ah], r14w
0x1801d77ef  jz      short loc_1801D783C
0x1801d77f1  mov     ebp, r14d
0x1801d77f4  lea     rdi, [rsi+20h]
0x1801d77f8  jbe     short loc_1801D7825
0x1801d77fa  mov     rdx, [rdi]
0x1801d77fd  mov     ebx, ebp
0x1801d77ff  mov     rdx, [rdx+rbx*8]; struct HostProfilerHeapObject *
0x1801d7803  call    ?FreeBSTR@ActiveScriptProfilerHeapEnum@@AEAAXPEAUHostProfilerHeapObject@@@Z; ActiveScriptProfilerHeapEnum::FreeBSTR(HostProfilerHeapObject *)
0x1801d7808  mov     rcx, [rdi]
0x1801d780b  mov     rcx, [rcx+rbx*8]; pv
0x1801d780f  call    cs:__imp_CoTaskMemFree
0x1801d7816  nop     dword ptr [rax+rax+00h]
0x1801d781b  movzx   eax, word ptr [rsi+1Ah]
0x1801d781f  inc     ebp
0x1801d7821  cmp     ebp, eax
0x1801d7823  jb      short loc_1801D77FA
0x1801d7825  mov     rcx, [rdi]; pv
0x1801d7828  call    cs:__imp_CoTaskMemFree
0x1801d782f  nop     dword ptr [rax+rax+00h]
0x1801d7834  mov     [rdi], r14
0x1801d7837  mov     [rsi+1Ah], r14w
0x1801d783c  mov     rbx, [rsp+38h+arg_10]
0x1801d7841  mov     rbp, [rsp+38h+arg_18]
0x1801d7846  add     rsp, 20h
0x1801d784a  pop     r14
0x1801d784c  pop     rdi
0x1801d784d  pop     rsi
0x1801d784e  retn
```
