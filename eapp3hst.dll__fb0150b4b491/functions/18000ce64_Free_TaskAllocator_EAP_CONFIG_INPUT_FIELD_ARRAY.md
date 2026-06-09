# Free<TaskAllocator>(_EAP_CONFIG_INPUT_FIELD_ARRAY &)

- ea: `0x18000ce64`
- end: `0x18000cef7`
- name: `??$Free@VTaskAllocator@@@@YAXAEAU_EAP_CONFIG_INPUT_FIELD_ARRAY@@@Z`
- size: `147`
- prototype: `void __fastcall(__int64)`
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000c964`
- `0x18000cf00`
- `0x18000d118`
- `0x18000e450`
- `0x18001f680`
- `0x180030d21`

## callees

- `0x18000ce64`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ce9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cebd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cedb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ce9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cebd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cedb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Free<TaskAllocator>(__int64 a1)
{
  __int64 v2; // rdi
  void *v3; // rcx
  void *v4; // rcx

  if ( *(_DWORD *)(a1 + 4) && *(_QWORD *)(a1 + 8) )
  {
    v2 = 0;
    do
    {
      v3 = *(void **)(*(_QWORD *)(a1 + 8) + 40 * v2 + 16);
      if ( v3 )
      {
        CoTaskMemFree(v3);
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 40 * v2 + 16) = 0;
      }
      v4 = *(void **)(*(_QWORD *)(a1 + 8) + 40 * v2 + 24);
      if ( v4 )
      {
        CoTaskMemFree(v4);
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 40 * v2 + 24) = 0;
      }
      v2 = (unsigned int)(v2 + 1);
    }
    while ( (unsigned int)v2 < *(_DWORD *)(a1 + 4) );
    CoTaskMemFree(*(LPVOID *)(a1 + 8));
  }
  *(_OWORD *)a1 = 0;
}

```

## disassembly

```asm
0x18000ce64  mov     [rsp+arg_0], rbx
0x18000ce69  mov     [rsp+arg_8], rsi
0x18000ce6e  push    rdi
0x18000ce6f  sub     rsp, 20h
0x18000ce73  mov     eax, [rcx+4]
0x18000ce76  mov     rbx, rcx
0x18000ce79  test    eax, eax
0x18000ce7b  jz      short loc_18000CEE1
0x18000ce7d  cmp     qword ptr [rcx+8], 0
0x18000ce82  jz      short loc_18000CEE1
0x18000ce84  xor     edi, edi
0x18000ce86  test    eax, eax
0x18000ce88  jz      short loc_18000CED7
0x18000ce8a  mov     rax, [rbx+8]
0x18000ce8e  lea     rsi, [rdi+rdi*4]
0x18000ce92  mov     rcx, [rax+rsi*8+10h]; pv
0x18000ce97  test    rcx, rcx
0x18000ce9a  jz      short loc_18000CEAF
0x18000ce9c  call    cs:__imp_CoTaskMemFree
0x18000cea2  mov     rax, [rbx+8]
0x18000cea6  mov     qword ptr [rax+rsi*8+10h], 0
0x18000ceaf  mov     rax, [rbx+8]
0x18000ceb3  mov     rcx, [rax+rsi*8+18h]; pv
0x18000ceb8  test    rcx, rcx
0x18000cebb  jz      short loc_18000CED0
0x18000cebd  call    cs:__imp_CoTaskMemFree
0x18000cec3  mov     rax, [rbx+8]
0x18000cec7  mov     qword ptr [rax+rsi*8+18h], 0
0x18000ced0  inc     edi
0x18000ced2  cmp     edi, [rbx+4]
0x18000ced5  jb      short loc_18000CE8A
0x18000ced7  mov     rcx, [rbx+8]; pv
0x18000cedb  call    cs:__imp_CoTaskMemFree
0x18000cee1  mov     rsi, [rsp+28h+arg_8]
0x18000cee6  xorps   xmm0, xmm0
0x18000cee9  movups  xmmword ptr [rbx], xmm0
0x18000ceec  mov     rbx, [rsp+28h+arg_0]
0x18000cef1  add     rsp, 20h
0x18000cef5  pop     rdi
0x18000cef6  retn
```
