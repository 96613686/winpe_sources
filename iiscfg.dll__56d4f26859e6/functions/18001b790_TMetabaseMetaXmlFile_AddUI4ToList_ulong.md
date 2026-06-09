# TMetabaseMetaXmlFile::AddUI4ToList(ulong)

- ea: `0x18001b790`
- end: `0x18001b7fd`
- name: `?AddUI4ToList@TMetabaseMetaXmlFile@@EEAAKK@Z`
- size: `109`
- prototype: `unsigned int __fastcall(TMetabaseMetaXmlFile *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180017e84`

## callees

- `0x180015990`
- `0x18001b790`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall TMetabaseMetaXmlFile::AddUI4ToList(TMetabaseMetaXmlFile *this, unsigned int a2)
{
  char *v3; // rbx
  unsigned int v4; // [rsp+38h] [rbp+10h] BYREF

  v4 = a2;
  if ( a2 < 0x1AD )
    return *((unsigned int *)this + a2 + 204);
  v3 = (char *)this + 248;
  if ( (unsigned int)(*((_DWORD *)this + 66) - *((_DWORD *)this + 67)) < 4 )
    (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v3 + 8LL))((char *)this + 248, 4);
  *(_DWORD *)(*((unsigned int *)v3 + 5) + *((_QWORD *)v3 + 1)) = 4;
  *((_DWORD *)v3 + 5) += 4;
  return THeap<unsigned long>::AddItemToHeap(v3, &v4, 4);
}

```

## disassembly

```asm
0x18001b790  mov     [rsp+arg_8], edx
0x18001b794  push    rbx
0x18001b795  sub     rsp, 20h
0x18001b799  cmp     edx, 1ADh
0x18001b79f  jnb     short loc_18001B7AC
0x18001b7a1  mov     eax, edx
0x18001b7a3  mov     eax, [rcx+rax*4+330h]
0x18001b7aa  jmp     short loc_18001B7F7
0x18001b7ac  lea     rbx, [rcx+0F8h]
0x18001b7b3  mov     eax, [rbx+10h]
0x18001b7b6  sub     eax, [rbx+14h]
0x18001b7b9  cmp     eax, 4
0x18001b7bc  jnb     short loc_18001B7D2
0x18001b7be  mov     rax, [rbx]
0x18001b7c1  mov     edx, 4
0x18001b7c6  mov     rcx, rbx
0x18001b7c9  mov     rax, [rax+8]
0x18001b7cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7d2  mov     edx, [rbx+14h]
0x18001b7d5  mov     r8d, 4
0x18001b7db  mov     rax, [rbx+8]
0x18001b7df  mov     rcx, rbx
0x18001b7e2  mov     dword ptr [rdx+rax], 4
0x18001b7e9  lea     rdx, [rsp+28h+arg_8]
0x18001b7ee  add     dword ptr [rbx+14h], 4
0x18001b7f2  call    ?AddItemToHeap@?$THeap@K@@QEAAKPEBEK@Z; THeap<ulong>::AddItemToHeap(uchar const *,ulong)
0x18001b7f7  add     rsp, 20h
0x18001b7fb  pop     rbx
0x18001b7fc  retn
```
