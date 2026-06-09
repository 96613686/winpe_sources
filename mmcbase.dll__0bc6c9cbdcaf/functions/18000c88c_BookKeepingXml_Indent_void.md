# BookKeepingXml::Indent(void)

- ea: `0x18000c88c`
- end: `0x18000c8ed`
- name: `?Indent@BookKeepingXml@@AEAAJXZ`
- size: `97`
- prototype: `__int64 __fastcall(BookKeepingXml *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000bfcc`
- `0x18000c550`

## callees

- `0x18000c3e8`
- `0x18000c88c`

## pseudocode

```c
__int64 __fastcall BookKeepingXml::Indent(BookKeepingXml *this)
{
  __int64 v1; // rax
  int v2; // r8d
  __int64 v4; // rbx
  _WORD *v5; // rdx

  v1 = *((_QWORD *)this + 1030);
  v2 = 0;
  v4 = 3 * v1;
  if ( 3 * v1 )
  {
    v2 = BookKeepingXml::CheckBufferSize((const WCHAR *)this, 3 * v1);
    if ( v2 >= 0 )
    {
      v5 = (_WORD *)*((_QWORD *)this + 3);
      *((_QWORD *)this + 4) -= v4;
      *((_QWORD *)this + 3) = &v5[v4];
      do
      {
        *v5++ = 32;
        --v4;
      }
      while ( v4 );
      *v5 = 0;
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000c88c  mov     [rsp+arg_0], rbx
0x18000c891  push    rdi
0x18000c892  sub     rsp, 20h
0x18000c896  mov     rax, [rcx+2030h]
0x18000c89d  xor     r8d, r8d
0x18000c8a0  mov     rdi, rcx
0x18000c8a3  lea     rbx, [rax+rax*2]
0x18000c8a7  test    rbx, rbx
0x18000c8aa  jz      short loc_18000C8DF
0x18000c8ac  mov     rdx, rbx; unsigned __int64
0x18000c8af  call    ?CheckBufferSize@BookKeepingXml@@AEAAJ_K@Z; BookKeepingXml::CheckBufferSize(unsigned __int64)
0x18000c8b4  mov     r8d, eax
0x18000c8b7  test    eax, eax
0x18000c8b9  js      short loc_18000C8DF
0x18000c8bb  mov     rdx, [rdi+18h]
0x18000c8bf  sub     [rdi+20h], rbx
0x18000c8c3  lea     rcx, [rdx+rbx*2]
0x18000c8c7  mov     [rdi+18h], rcx
0x18000c8cb  mov     word ptr [rdx], 20h ; ' '
0x18000c8d0  lea     rdx, [rdx+2]
0x18000c8d4  sub     rbx, 1
0x18000c8d8  jnz     short loc_18000C8CB
0x18000c8da  xor     eax, eax
0x18000c8dc  mov     [rdx], ax
0x18000c8df  mov     rbx, [rsp+28h+arg_0]
0x18000c8e4  mov     eax, r8d
0x18000c8e7  add     rsp, 20h
0x18000c8eb  pop     rdi
0x18000c8ec  retn
```
