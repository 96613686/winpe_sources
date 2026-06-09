# tson::write_buffer::push_back(void const *,unsigned __int64)

- ea: `0x18000d0b0`
- end: `0x18000d158`
- name: `?push_back@write_buffer@tson@@QEAA_NPEBX_K@Z`
- size: `168`
- prototype: `bool __fastcall(tson::write_buffer *this, const void *, size_t)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x18000af44`
- `0x18000afdc`
- `0x18000b070`
- `0x18000ce60`
- `0x18000d260`
- `0x18000e224`
- `0x18000e438`

## callees

- `0x180002666`
- `0x1800026c8`
- `0x18000d0b0`
- `0x18000d160`
- `0x180011c6c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d0f2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d135`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d0f2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d135`

## pseudocode

```c
bool __fastcall tson::write_buffer::push_back(tson::write_buffer *this, const void *a2, size_t a3)
{
  bool result; // al
  void *v7; // rcx
  size_t v8; // rsi

  if ( *((_QWORD *)this + 260) - *((_QWORD *)this + 259) >= a3 || (result = tson::write_buffer::reserve(this, a3)) )
  {
    if ( a3 )
    {
      v7 = (void *)*((_QWORD *)this + 259);
      if ( !v7 )
      {
LABEL_5:
        *(_DWORD *)_o__errno() = 22;
LABEL_12:
        invalid_parameter_noinfo();
        goto LABEL_13;
      }
      v8 = *((_QWORD *)this + 260) - (_QWORD)v7;
      if ( a2 && v8 >= a3 )
      {
        memcpy_0(v7, a2, a3);
      }
      else
      {
        memset_0(v7, 0, *((_QWORD *)this + 260) - (_QWORD)v7);
        if ( !a2 )
          goto LABEL_5;
        if ( v8 < a3 )
        {
          *(_DWORD *)_o__errno() = 34;
          goto LABEL_12;
        }
      }
    }
LABEL_13:
    *((_QWORD *)this + 259) += a3;
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18000d0b0  push    rbx
0x18000d0b2  push    rbp
0x18000d0b3  push    rsi
0x18000d0b4  push    rdi
0x18000d0b5  sub     rsp, 28h
0x18000d0b9  mov     rax, [rcx+820h]
0x18000d0c0  mov     rbx, r8
0x18000d0c3  sub     rax, [rcx+818h]
0x18000d0ca  mov     rbp, rdx
0x18000d0cd  mov     rdi, rcx
0x18000d0d0  cmp     rax, r8
0x18000d0d3  jnb     short loc_18000D0E1
0x18000d0d5  mov     rdx, rbx; unsigned __int64
0x18000d0d8  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18000d0dd  test    al, al
0x18000d0df  jz      short loc_18000D14F
0x18000d0e1  test    rbx, rbx
0x18000d0e4  jz      short loc_18000D146
0x18000d0e6  mov     rcx, [rdi+818h]; void *
0x18000d0ed  test    rcx, rcx
0x18000d0f0  jnz     short loc_18000D100
0x18000d0f2  call    cs:__imp__o__errno
0x18000d0f8  mov     dword ptr [rax], 16h
0x18000d0fe  jmp     short loc_18000D141
0x18000d100  mov     rsi, [rdi+820h]
0x18000d107  sub     rsi, rcx
0x18000d10a  test    rbp, rbp
0x18000d10d  jz      short loc_18000D121
0x18000d10f  cmp     rsi, rbx
0x18000d112  jb      short loc_18000D121
0x18000d114  mov     r8, rbx; Size
0x18000d117  mov     rdx, rbp; Src
0x18000d11a  call    memcpy_0
0x18000d11f  jmp     short loc_18000D146
0x18000d121  mov     r8, rsi; Size
0x18000d124  xor     edx, edx; Val
0x18000d126  call    memset_0
0x18000d12b  test    rbp, rbp
0x18000d12e  jz      short loc_18000D0F2
0x18000d130  cmp     rsi, rbx
0x18000d133  jnb     short loc_18000D146
0x18000d135  call    cs:__imp__o__errno
0x18000d13b  mov     dword ptr [rax], 22h ; '"'
0x18000d141  call    _invalid_parameter_noinfo
0x18000d146  add     [rdi+818h], rbx
0x18000d14d  mov     al, 1
0x18000d14f  add     rsp, 28h
0x18000d153  pop     rdi
0x18000d154  pop     rsi
0x18000d155  pop     rbp
0x18000d156  pop     rbx
0x18000d157  retn
```
