# FreeEAPConfigInputFieldArrayFields

- ea: `0x18002e830`
- end: `0x18002e8a6`
- name: `FreeEAPConfigInputFieldArrayFields`
- size: `118`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180025e5c`
- `0x18002e80c`

## callees

- `0x18001a4dc`
- `0x18002e830`

## pseudocode

```c
void __fastcall FreeEAPConfigInputFieldArrayFields(__int64 *a1)
{
  __int64 v1; // rbx
  __int64 v2; // rdi
  __int64 v3; // rax

  if ( a1 )
  {
    v1 = *a1;
    if ( *a1 )
    {
      if ( *(_QWORD *)(v1 + 8) && *(_DWORD *)(v1 + 4) )
      {
        v2 = 0;
        do
        {
          if ( *(_QWORD *)(*(_QWORD *)(v1 + 8) + 24LL + 40 * v2) )
            ((void (*)(void))FreeOneXOrEapMemory)();
          v3 = *(_QWORD *)(v1 + 8);
          if ( *(_QWORD *)(v3 + 40 * v2 + 24) )
            FreeOneXOrEapMemory(v3 + 16 + 40 * v2);
          v2 = (unsigned int)(v2 + 1);
        }
        while ( (unsigned int)v2 < *(_DWORD *)(v1 + 4) );
      }
    }
  }
}

```

## disassembly

```asm
0x18002e830  test    rcx, rcx
0x18002e833  jz      short locret_18002E8A5
0x18002e835  mov     [rsp+arg_0], rbx
0x18002e83a  mov     [rsp+arg_8], rsi
0x18002e83f  push    rdi
0x18002e840  sub     rsp, 20h
0x18002e844  mov     rbx, [rcx]
0x18002e847  test    rbx, rbx
0x18002e84a  jz      short loc_18002E896
0x18002e84c  cmp     qword ptr [rbx+8], 0
0x18002e851  jz      short loc_18002E896
0x18002e853  cmp     dword ptr [rbx+4], 0
0x18002e857  jbe     short loc_18002E896
0x18002e859  xor     edi, edi
0x18002e85b  mov     rcx, [rbx+8]
0x18002e85f  lea     rsi, [rdi+rdi*4]
0x18002e863  add     rcx, 18h
0x18002e867  lea     rcx, [rcx+rsi*8]
0x18002e86b  cmp     qword ptr [rcx], 0
0x18002e86f  jz      short loc_18002E876
0x18002e871  call    FreeOneXOrEapMemory
0x18002e876  mov     rax, [rbx+8]
0x18002e87a  cmp     qword ptr [rax+rsi*8+18h], 0
0x18002e880  jz      short loc_18002E88F
0x18002e882  lea     rcx, [rax+10h]
0x18002e886  lea     rcx, [rcx+rsi*8]
0x18002e88a  call    FreeOneXOrEapMemory
0x18002e88f  inc     edi
0x18002e891  cmp     edi, [rbx+4]
0x18002e894  jb      short loc_18002E85B
0x18002e896  mov     rbx, [rsp+28h+arg_0]
0x18002e89b  mov     rsi, [rsp+28h+arg_8]
0x18002e8a0  add     rsp, 20h
0x18002e8a4  pop     rdi
0x18002e8a5  retn
```
