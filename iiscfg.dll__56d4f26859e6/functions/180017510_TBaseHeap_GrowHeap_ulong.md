# TBaseHeap::GrowHeap(ulong)

- ea: `0x180017510`
- end: `0x1800175cb`
- name: `?GrowHeap@TBaseHeap@@UEAAXK@Z`
- size: `187`
- prototype: `void __fastcall(TBaseHeap *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180019088`

## callees

- `0x180017510`
- `0x180017ad8`

## import_xrefs

- `msvcrt!realloc` at `0x18001757a`
- `msvcrt!realloc` at `0x18001757a`
- `msvcrt!free` at `0x180017589`
- `msvcrt!free` at `0x180017589`

## string_xrefs

- `0x1800175a8`: `inetsrv\iis\mb\config\src\core\schemagen\THeap.h`

## pseudocode

```c
void __fastcall TBaseHeap::GrowHeap(TBaseHeap *this, int a2)
{
  unsigned int v3; // ebx
  unsigned int v4; // ebx
  void *v5; // rax

  v3 = *((_DWORD *)this + 4) + ((a2 + 3) & 0xFFFFFFFC);
  if ( v3 < 0x10000 )
  {
    if ( v3 < 0x4000 )
    {
      if ( v3 < 0x1000 )
        v4 = (v3 + 1023) & 0xFFFFFC00;
      else
        v4 = (v3 + 4095) & 0xFFFFF000;
    }
    else
    {
      v4 = (v3 + 0x3FFF) & 0xFFFFC000;
    }
  }
  else
  {
    v4 = (v3 + 0xFFFF) & 0xFFFF0000;
  }
  v5 = realloc(*((void **)this + 1), v4);
  if ( !v5 )
  {
    free(*((void **)this + 1));
    *((_QWORD *)this + 1) = 0;
    *((_DWORD *)this + 4) = 0;
    ThrowException(L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\THeap.h", L"OUT OF MEMORY", 0x46u, 0);
  }
  *((_DWORD *)this + 4) = v4;
  *((_QWORD *)this + 1) = v5;
}

```

## disassembly

```asm
0x180017510  mov     [rsp+arg_0], rbx
0x180017515  push    rdi
0x180017516  sub     rsp, 20h
0x18001751a  lea     ebx, [rdx+3]
0x18001751d  mov     rdi, rcx
0x180017520  and     ebx, 0FFFFFFFCh
0x180017523  add     ebx, [rcx+10h]
0x180017526  cmp     ebx, 10000h
0x18001752c  jb      short loc_18001753C
0x18001752e  add     ebx, 0FFFFh
0x180017534  and     ebx, 0FFFF0000h
0x18001753a  jmp     short loc_180017574
0x18001753c  cmp     ebx, 4000h
0x180017542  jb      short loc_180017552
0x180017544  add     ebx, 3FFFh
0x18001754a  and     ebx, 0FFFFC000h
0x180017550  jmp     short loc_180017574
0x180017552  cmp     ebx, 1000h
0x180017558  jb      short loc_180017568
0x18001755a  add     ebx, 0FFFh
0x180017560  and     ebx, 0FFFFF000h
0x180017566  jmp     short loc_180017574
0x180017568  add     ebx, 3FFh
0x18001756e  and     ebx, 0FFFFFC00h
0x180017574  mov     rcx, [rcx+8]; Block
0x180017578  mov     edx, ebx; Size
0x18001757a  call    cs:__imp_realloc
0x180017580  test    rax, rax
0x180017583  jnz     short loc_1800175B9
0x180017585  mov     rcx, [rdi+8]; Block
0x180017589  call    cs:__imp_free
0x18001758f  xor     r9d, r9d; unsigned int
0x180017592  mov     qword ptr [rdi+8], 0
0x18001759a  lea     rdx, aOutOfMemory; "OUT OF MEMORY"
0x1800175a1  mov     dword ptr [rdi+10h], 0
0x1800175a8  lea     rcx, aInetsrvIisMbCo_10; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x1800175af  lea     r8d, [r9+46h]; unsigned int
0x1800175b3  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x1800175b9  mov     [rdi+10h], ebx
0x1800175bc  mov     rbx, [rsp+28h+arg_0]
0x1800175c1  mov     [rdi+8], rax
0x1800175c5  add     rsp, 20h
0x1800175c9  pop     rdi
0x1800175ca  retn
```
