# RtlNameValueArray::Clear(void)

- ea: `0x180003094`
- end: `0x180003123`
- name: `?Clear@RtlNameValueArray@@QEAAXXZ`
- size: `143`
- prototype: `void __fastcall(RtlNameValueArray *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180002a68`
- `0x180004ef4`
- `0x180006664`
- `0x180008948`
- `0x180018064`

## callees

- `0x180003094`
- `0x1800191a2`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800030d8`
- `KERNEL32!HeapFree` at `0x1800030d8`

## pseudocode

```c
void __fastcall RtlNameValueArray::Clear(RtlNameValueArray *this)
{
  unsigned __int64 v1; // rdx
  unsigned __int64 i; // rdi
  LPVOID *v4; // rax
  unsigned __int128 v5; // rax

  v1 = *((_QWORD *)this + 2);
  if ( v1 )
  {
    for ( i = 0; i < v1; ++i )
    {
      v4 = 0;
      if ( i < v1 )
      {
        if ( !is_mul_ok(*((_QWORD *)this + 1), i)
          || (v4 = (LPVOID *)(*((_QWORD *)this + 5) + *((_QWORD *)this + 1) * i),
              (unsigned __int64)v4 < *((_QWORD *)this + 5)) )
        {
          v4 = 0;
        }
      }
      if ( *v4 )
        HeapFree(*(HANDLE *)this, 0, *v4);
      v1 = *((_QWORD *)this + 2);
    }
    if ( v1 )
    {
      v5 = v1 * (unsigned __int128)*((unsigned __int64 *)this + 1);
      if ( is_mul_ok(*((_QWORD *)this + 2), *((_QWORD *)this + 1)) )
      {
        memset_0(*((void **)this + 5), SDWORD2(v5), v5);
        *((_QWORD *)this + 2) = 0;
      }
    }
  }
}

```

## disassembly

```asm
0x180003094  mov     [rsp+arg_8], rbx
0x180003099  push    rdi
0x18000309a  sub     rsp, 20h
0x18000309e  mov     rdx, [rcx+10h]
0x1800030a2  mov     rbx, rcx
0x1800030a5  test    rdx, rdx
0x1800030a8  jz      short loc_180003118
0x1800030aa  xor     edi, edi
0x1800030ac  xor     eax, eax
0x1800030ae  cmp     rdi, rdx
0x1800030b1  jnb     short loc_1800030CB
0x1800030b3  mov     rax, rdi
0x1800030b6  mul     qword ptr [rbx+8]
0x1800030ba  test    rdx, rdx
0x1800030bd  jnz     short loc_1800030C9
0x1800030bf  add     rax, [rbx+28h]
0x1800030c3  cmp     rax, [rbx+28h]
0x1800030c7  jnb     short loc_1800030CB
0x1800030c9  xor     eax, eax
0x1800030cb  mov     r8, [rax]; lpMem
0x1800030ce  test    r8, r8
0x1800030d1  jz      short loc_1800030DE
0x1800030d3  mov     rcx, [rbx]; hHeap
0x1800030d6  xor     edx, edx; dwFlags
0x1800030d8  call    cs:__imp_HeapFree
0x1800030de  mov     rdx, [rbx+10h]; Val
0x1800030e2  inc     rdi
0x1800030e5  cmp     rdi, rdx
0x1800030e8  jb      short loc_1800030AC
0x1800030ea  test    rdx, rdx
0x1800030ed  jz      short loc_180003118
0x1800030ef  mov     rax, [rbx+8]
0x1800030f3  mul     rdx
0x1800030f6  mov     [rsp+28h+arg_0], 0
0x1800030ff  test    rdx, rdx
0x180003102  jnz     short loc_180003118
0x180003104  mov     rcx, [rbx+28h]; void *
0x180003108  mov     r8, rax; Size
0x18000310b  call    memset_0
0x180003110  mov     qword ptr [rbx+10h], 0
0x180003118  mov     rbx, [rsp+28h+arg_8]
0x18000311d  add     rsp, 20h
0x180003121  pop     rdi
0x180003122  retn
```
