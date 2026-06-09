# CHTable::CreateHandle(void *)

- ea: `0x140011268`
- end: `0x1400112f9`
- name: `?CreateHandle@CHTable@@QEAAKPEAX@Z`
- size: `145`
- prototype: `unsigned int __fastcall(CHTable *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000c914`

## callees

- `0x140011268`
- `0x140011300`

## pseudocode

```c
__int64 __fastcall CHTable::CreateHandle(CHTable *this, void *a2)
{
  unsigned int v2; // eax
  unsigned int v4; // edx
  int v6; // edx
  __int64 i; // rax
  __int64 v9; // r8
  unsigned int v10; // eax
  int v11; // ecx

  v2 = *((_DWORD *)this + 1);
  v4 = *(_DWORD *)this;
  if ( v2 >= *(_DWORD *)this )
  {
    for ( i = 0; (unsigned int)i < v4; i = (unsigned int)(i + 1) )
    {
      v9 = *((_QWORD *)this + 1);
      if ( !*(_QWORD *)(v9 + 8 * i) )
      {
        *(_QWORD *)(v9 + 8 * i) = a2;
        return (unsigned int)(4 * i + 4);
      }
    }
    CHTable::Reallocate(this, v4 + 16);
    v10 = *((_DWORD *)this + 1);
    if ( v10 >= *(_DWORD *)this )
    {
      return 0;
    }
    else
    {
      *(_QWORD *)(*((_QWORD *)this + 1) + 8LL * v10) = a2;
      v11 = *((_DWORD *)this + 1);
      *((_DWORD *)this + 1) = v11 + 1;
      return (unsigned int)(4 * v11 + 4);
    }
  }
  else
  {
    *(_QWORD *)(*((_QWORD *)this + 1) + 8LL * v2) = a2;
    v6 = *((_DWORD *)this + 1);
    *((_DWORD *)this + 1) = v6 + 1;
    return (unsigned int)(4 * v6 + 4);
  }
}

```

## disassembly

```asm
0x140011268  mov     [rsp+arg_0], rbx
0x14001126d  push    rdi
0x14001126e  sub     rsp, 20h
0x140011272  mov     eax, [rcx+4]
0x140011275  mov     rdi, rdx
0x140011278  mov     edx, [rcx]
0x14001127a  mov     rbx, rcx
0x14001127d  cmp     eax, edx
0x14001127f  jnb     short loc_14001129E
0x140011281  mov     r8d, eax
0x140011284  mov     rax, [rcx+8]
0x140011288  mov     [rax+r8*8], rdi
0x14001128c  mov     edx, [rcx+4]
0x14001128f  lea     eax, [rdx+1]
0x140011292  mov     [rcx+4], eax
0x140011295  lea     eax, ds:4[rdx*4]
0x14001129c  jmp     short loc_1400112ED
0x14001129e  xor     eax, eax
0x1400112a0  cmp     eax, edx
0x1400112a2  jnb     short loc_1400112C0
0x1400112a4  mov     r8, [rcx+8]
0x1400112a8  cmp     qword ptr [r8+rax*8], 0
0x1400112ad  jz      short loc_1400112B3
0x1400112af  inc     eax
0x1400112b1  jmp     short loc_1400112A0
0x1400112b3  mov     [r8+rax*8], rdi
0x1400112b7  lea     eax, ds:4[rax*4]
0x1400112be  jmp     short loc_1400112ED
0x1400112c0  add     edx, 10h; unsigned int
0x1400112c3  call    ?Reallocate@CHTable@@AEAAXK@Z; CHTable::Reallocate(ulong)
0x1400112c8  mov     eax, [rbx+4]
0x1400112cb  cmp     eax, [rbx]
0x1400112cd  jnb     short loc_1400112EB
0x1400112cf  mov     ecx, eax
0x1400112d1  mov     rax, [rbx+8]
0x1400112d5  mov     [rax+rcx*8], rdi
0x1400112d9  mov     ecx, [rbx+4]
0x1400112dc  lea     eax, [rcx+1]
0x1400112df  mov     [rbx+4], eax
0x1400112e2  lea     eax, ds:4[rcx*4]
0x1400112e9  jmp     short loc_1400112ED
0x1400112eb  xor     eax, eax
0x1400112ed  mov     rbx, [rsp+28h+arg_0]
0x1400112f2  add     rsp, 20h
0x1400112f6  pop     rdi
0x1400112f7  retn
```
