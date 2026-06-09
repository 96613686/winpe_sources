# NUMBER_SET::~NUMBER_SET(void)

- ea: `0x18005ed00`
- end: `0x18005ed59`
- name: `??1NUMBER_SET@@UEAA@XZ`
- size: `89`
- prototype: `void __fastcall(NUMBER_SET *__hidden this)`
- caller_count: `12`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001f4b4`
- `0x180022b74`
- `0x18005ed60`
- `0x180070fd4`
- `0x180071674`
- `0x180071944`
- `0x180071f64`
- `0x1800721f4`
- `0x180073994`
- `0x180074910`
- `0x180076ce0`
- `0x180083f7a`

## callees

- `0x18005ed00`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18005ed2a`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18005ed2a`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18005ed35`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18005ed35`

## pseudocode

```c
void __fastcall NUMBER_SET::~NUMBER_SET(NUMBER_SET *this)
{
  bool v1; // zf
  struct _RTL_AVL_TABLE *i; // rdi
  PVOID v4; // rax

  v1 = *((_QWORD *)this + 15) == 0;
  *(_QWORD *)this = &NUMBER_SET::`vftable';
  if ( !v1 )
  {
    for ( i = (struct _RTL_AVL_TABLE *)((char *)this + 16); ; RtlDeleteElementGenericTableAvl(i, v4) )
    {
      v4 = RtlEnumerateGenericTableAvl(i, 1u);
      if ( !v4 )
        break;
    }
    *((_QWORD *)this + 15) = 0;
  }
  *(_QWORD *)this = &MEDIA_TRACK_INFORMATION_SORTED_BY_SIZE::`vftable';
}

```

## disassembly

```asm
0x18005ed00  mov     [rsp+arg_0], rbx
0x18005ed05  push    rdi
0x18005ed06  sub     rsp, 20h
0x18005ed0a  cmp     qword ptr [rcx+78h], 0
0x18005ed0f  lea     rax, ??_7NUMBER_SET@@6B@; const NUMBER_SET::`vftable'
0x18005ed16  mov     [rcx], rax
0x18005ed19  mov     rbx, rcx
0x18005ed1c  jz      short loc_18005ED44
0x18005ed1e  lea     rdi, [rcx+10h]
0x18005ed22  jmp     short loc_18005ED30
0x18005ed24  mov     rdx, rax; Buffer
0x18005ed27  mov     rcx, rdi; Table
0x18005ed2a  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18005ed30  mov     dl, 1; Restart
0x18005ed32  mov     rcx, rdi; Table
0x18005ed35  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18005ed3b  test    rax, rax
0x18005ed3e  jnz     short loc_18005ED24
0x18005ed40  mov     [rbx+78h], rax
0x18005ed44  lea     rax, ??_7MEDIA_TRACK_INFORMATION_SORTED_BY_SIZE@@6B@; const MEDIA_TRACK_INFORMATION_SORTED_BY_SIZE::`vftable'
0x18005ed4b  mov     [rbx], rax
0x18005ed4e  mov     rbx, [rsp+28h+arg_0]
0x18005ed53  add     rsp, 20h
0x18005ed57  pop     rdi
0x18005ed58  retn
```
