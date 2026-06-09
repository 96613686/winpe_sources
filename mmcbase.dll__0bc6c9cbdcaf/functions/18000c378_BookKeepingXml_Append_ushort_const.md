# BookKeepingXml::Append(ushort const *,...)

- ea: `0x18000c378`
- end: `0x18000c3e2`
- name: `?Append@BookKeepingXml@@AEAAJPEBGZZ`
- size: `106`
- prototype: `int(BookKeepingXml *__hidden this, const unsigned __int16 *, ...)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000bfcc`
- `0x18000c550`
- `0x18000c914`

## callees

- `0x18000c378`
- `0x18000cc60`

## pseudocode

```c
__int64 BookKeepingXml::Append(BookKeepingXml *this, const unsigned __int16 *a2, ...)
{
  int v4; // r8d
  __int64 v5; // rdx
  __int64 v6; // rcx
  va_list va; // [rsp+60h] [rbp+18h] BYREF

  va_start(va, a2);
  if ( !*((_QWORD *)this + 4) )
    return 2147942522LL;
  v4 = StringCchVPrintfW(*((unsigned __int16 **)this + 3), *((_QWORD *)this + 4), a2, va);
  if ( v4 >= 0 )
  {
    v5 = *((_QWORD *)this + 3);
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)(v5 + 2 * v6) );
    *((_QWORD *)this + 4) -= v6;
    *((_QWORD *)this + 3) = v5 + 2 * v6;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000c378  mov     [rsp+arg_8], rdx
0x18000c37d  mov     qword ptr [rsp+arg_10], r8
0x18000c382  mov     [rsp+arg_18], r9
0x18000c387  push    rbx
0x18000c388  push    rdi
0x18000c389  sub     rsp, 38h
0x18000c38d  xor     edi, edi
0x18000c38f  mov     rbx, rcx
0x18000c392  cmp     [rcx+20h], rdi
0x18000c396  jnz     short loc_18000C39F
0x18000c398  mov     eax, 8007007Ah
0x18000c39d  jmp     short loc_18000C3DB
0x18000c39f  mov     r8, rdx; unsigned __int16 *
0x18000c3a2  lea     r9, [rsp+48h+arg_10]; char *
0x18000c3a7  mov     rdx, [rcx+20h]; unsigned __int64
0x18000c3ab  mov     rcx, [rcx+18h]; unsigned __int16 *
0x18000c3af  call    ?StringCchVPrintfW@@YAJPEAG_KPEBGPEAD@Z; StringCchVPrintfW(ushort *,unsigned __int64,ushort const *,char *)
0x18000c3b4  mov     r8d, eax
0x18000c3b7  test    eax, eax
0x18000c3b9  js      short loc_18000C3D8
0x18000c3bb  mov     rdx, [rbx+18h]
0x18000c3bf  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000c3c3  inc     rcx
0x18000c3c6  cmp     [rdx+rcx*2], di
0x18000c3ca  jnz     short loc_18000C3C3
0x18000c3cc  sub     [rbx+20h], rcx
0x18000c3d0  lea     rax, [rdx+rcx*2]
0x18000c3d4  mov     [rbx+18h], rax
0x18000c3d8  mov     eax, r8d
0x18000c3db  add     rsp, 38h
0x18000c3df  pop     rdi
0x18000c3e0  pop     rbx
0x18000c3e1  retn
```
