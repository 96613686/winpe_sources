# FreeEAPConfigInputFieldArrayInternal

- ea: `0x18001df04`
- end: `0x18001dfa1`
- name: `FreeEAPConfigInputFieldArrayInternal`
- size: `157`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180017400`
- `0x18001dfa8`

## callees

- `0x18001df04`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001df45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001df66`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001df84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001df45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001df66`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001df84`

## pseudocode

```c
void __fastcall FreeEAPConfigInputFieldArrayInternal(__int64 a1)
{
  __int64 v2; // rdi
  void *v3; // rcx
  void *v4; // rcx

  if ( a1 && *(_DWORD *)(a1 + 4) && *(_QWORD *)(a1 + 8) )
  {
    v2 = 0;
    do
    {
      v3 = *(void **)(*(_QWORD *)(a1 + 8) + 40 * v2 + 16);
      if ( v3 )
      {
        LocalFree(v3);
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 40 * v2 + 16) = 0;
      }
      v4 = *(void **)(*(_QWORD *)(a1 + 8) + 40 * v2 + 24);
      if ( v4 )
      {
        LocalFree(v4);
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 40 * v2 + 24) = 0;
      }
      v2 = (unsigned int)(v2 + 1);
    }
    while ( (unsigned int)v2 < *(_DWORD *)(a1 + 4) );
    LocalFree(*(HLOCAL *)(a1 + 8));
    *(_DWORD *)(a1 + 4) = 0;
  }
}

```

## disassembly

```asm
0x18001df04  test    rcx, rcx
0x18001df07  jz      locret_18001DFA0
0x18001df0d  mov     [rsp+arg_0], rbx
0x18001df12  mov     [rsp+arg_8], rsi
0x18001df17  push    rdi
0x18001df18  sub     rsp, 20h
0x18001df1c  mov     eax, [rcx+4]
0x18001df1f  mov     rbx, rcx
0x18001df22  test    eax, eax
0x18001df24  jz      short loc_18001DF91
0x18001df26  cmp     qword ptr [rcx+8], 0
0x18001df2b  jz      short loc_18001DF91
0x18001df2d  xor     edi, edi
0x18001df2f  test    eax, eax
0x18001df31  jz      short loc_18001DF80
0x18001df33  mov     rax, [rbx+8]
0x18001df37  lea     rsi, [rdi+rdi*4]
0x18001df3b  mov     rcx, [rax+rsi*8+10h]; hMem
0x18001df40  test    rcx, rcx
0x18001df43  jz      short loc_18001DF58
0x18001df45  call    cs:__imp_LocalFree
0x18001df4b  mov     rax, [rbx+8]
0x18001df4f  mov     qword ptr [rax+rsi*8+10h], 0
0x18001df58  mov     rax, [rbx+8]
0x18001df5c  mov     rcx, [rax+rsi*8+18h]; hMem
0x18001df61  test    rcx, rcx
0x18001df64  jz      short loc_18001DF79
0x18001df66  call    cs:__imp_LocalFree
0x18001df6c  mov     rax, [rbx+8]
0x18001df70  mov     qword ptr [rax+rsi*8+18h], 0
0x18001df79  inc     edi
0x18001df7b  cmp     edi, [rbx+4]
0x18001df7e  jb      short loc_18001DF33
0x18001df80  mov     rcx, [rbx+8]; hMem
0x18001df84  call    cs:__imp_LocalFree
0x18001df8a  mov     dword ptr [rbx+4], 0
0x18001df91  mov     rbx, [rsp+28h+arg_0]
0x18001df96  mov     rsi, [rsp+28h+arg_8]
0x18001df9b  add     rsp, 20h
0x18001df9f  pop     rdi
0x18001dfa0  retn
```
