# SERVER_CACHE::~SERVER_CACHE(void)

- ea: `0x1800047f4`
- end: `0x180004875`
- name: `??1SERVER_CACHE@@IEAA@XZ`
- size: `129`
- prototype: `void __fastcall(SERVER_CACHE *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800050a8`

## callees

- `0x180001048`
- `0x1800047f4`
- `0x18000487c`

## pseudocode

```c
void __fastcall SERVER_CACHE::~SERVER_CACHE(SERVER_CACHE *this)
{
  int v2; // ecx
  int v3; // edx
  __int64 v4; // r8
  __int64 v5; // rax
  SERVER_CACHE_ITEM *v6; // rdi
  __int64 v7; // rax

  *((_DWORD *)this + 4) = 0;
  while ( 1 )
  {
    v2 = *((_DWORD *)this + 4);
    v3 = *((_DWORD *)this + 2);
    if ( v2 >= v3 )
      break;
    v4 = *(_QWORD *)this;
    while ( 1 )
    {
      v5 = v2++;
      v6 = *(SERVER_CACHE_ITEM **)(v4 + 8 * v5);
      *((_DWORD *)this + 4) = v2;
      if ( v6 )
        break;
      if ( v2 >= v3 )
        goto LABEL_6;
    }
    v7 = *(int *)v6;
    if ( (int)v7 >= 0 && (int)v7 < v3 )
    {
      --*((_DWORD *)this + 3);
      *(_QWORD *)(v4 + 8 * v7) = 0;
    }
    SERVER_CACHE_ITEM::~SERVER_CACHE_ITEM(v6);
    operator delete(v6);
  }
LABEL_6:
  *((_DWORD *)this + 4) = 0;
  if ( *(SERVER_CACHE **)this != (SERVER_CACHE *)((char *)this + 24) )
    operator delete(*(void **)this);
}

```

## disassembly

```asm
0x1800047f4  mov     [rsp+arg_0], rbx
0x1800047f9  push    rdi
0x1800047fa  sub     rsp, 20h
0x1800047fe  mov     rbx, rcx
0x180004801  mov     dword ptr [rcx+10h], 0
0x180004808  mov     ecx, [rbx+10h]
0x18000480b  mov     edx, [rbx+8]
0x18000480e  cmp     ecx, edx
0x180004810  jge     short loc_18000482A
0x180004812  mov     r8, [rbx]
0x180004815  movsxd  rax, ecx
0x180004818  inc     ecx
0x18000481a  mov     rdi, [r8+rax*8]
0x18000481e  mov     [rbx+10h], ecx
0x180004821  test    rdi, rdi
0x180004824  jnz     short loc_18000484D
0x180004826  cmp     ecx, edx
0x180004828  jl      short loc_180004815
0x18000482a  lea     rax, [rbx+18h]
0x18000482e  mov     dword ptr [rbx+10h], 0
0x180004835  cmp     [rbx], rax
0x180004838  jz      short loc_180004842
0x18000483a  mov     rcx, [rbx]; Block
0x18000483d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004842  mov     rbx, [rsp+28h+arg_0]
0x180004847  add     rsp, 20h
0x18000484b  pop     rdi
0x18000484c  retn
0x18000484d  movsxd  rax, dword ptr [rdi]
0x180004850  test    eax, eax
0x180004852  js      short loc_180004863
0x180004854  cmp     eax, edx
0x180004856  jge     short loc_180004863
0x180004858  dec     dword ptr [rbx+0Ch]
0x18000485b  mov     qword ptr [r8+rax*8], 0
0x180004863  mov     rcx, rdi; this
0x180004866  call    ??1SERVER_CACHE_ITEM@@QEAA@XZ; SERVER_CACHE_ITEM::~SERVER_CACHE_ITEM(void)
0x18000486b  mov     rcx, rdi; Block
0x18000486e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004873  jmp     short loc_180004808
```
