# ATL::CSimpleStringT<ushort,0>::CopyChars(ushort *,unsigned __int64,ushort const *,int)

- ea: `0x140005e1c`
- end: `0x140005e99`
- name: `?CopyChars@?$CSimpleStringT@G$0A@@ATL@@SAXPEAG_KPEBGH@Z`
- size: `125`
- prototype: `void __fastcall(void *, __int64, const void *, int)`
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x140005458`
- `0x140005d70`
- `0x140006020`
- `0x1400061dc`
- `0x14000704c`
- `0x140007bf8`
- `0x14000813c`
- `0x14000f058`

## callees

- `0x14000274e`
- `0x140002814`
- `0x140005e1c`
- `0x14002c400`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140005e3b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140005e78`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140005e3b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140005e78`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall ATL::CSimpleStringT<unsigned short,0>::CopyChars(void *a1, __int64 a2, const void *a3, int a4)
{
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // rdi

  v5 = 2LL * a4;
  if ( v5 )
  {
    if ( !a1 )
      goto LABEL_3;
    v6 = 2 * a2;
    if ( a3 && v6 >= v5 )
    {
      memcpy_0(a1, a3, 2LL * a4);
      return;
    }
    memset_0(a1, 0, 2 * a2);
    if ( a3 )
    {
      if ( v6 >= v5 )
        return;
      *(_DWORD *)_o__errno() = 34;
    }
    else
    {
LABEL_3:
      *(_DWORD *)_o__errno() = 22;
    }
    invalid_parameter_noinfo();
  }
}

```

## disassembly

```asm
0x140005e1c  mov     [rsp+arg_0], rbx
0x140005e21  mov     [rsp+arg_8], rsi
0x140005e26  push    rdi
0x140005e27  sub     rsp, 20h
0x140005e2b  movsxd  rbx, r9d
0x140005e2e  mov     rsi, r8
0x140005e31  add     rbx, rbx
0x140005e34  jz      short loc_140005E89
0x140005e36  test    rcx, rcx
0x140005e39  jnz     short loc_140005E49
0x140005e3b  call    cs:__imp__o__errno
0x140005e41  mov     dword ptr [rax], 16h
0x140005e47  jmp     short loc_140005E84
0x140005e49  lea     rdi, [rdx+rdx]
0x140005e4d  test    rsi, rsi
0x140005e50  jz      short loc_140005E64
0x140005e52  cmp     rdi, rbx
0x140005e55  jb      short loc_140005E64
0x140005e57  mov     r8, rbx; Size
0x140005e5a  mov     rdx, rsi; Src
0x140005e5d  call    memcpy_0
0x140005e62  jmp     short loc_140005E89
0x140005e64  mov     r8, rdi; Size
0x140005e67  xor     edx, edx; Val
0x140005e69  call    memset_0
0x140005e6e  test    rsi, rsi
0x140005e71  jz      short loc_140005E3B
0x140005e73  cmp     rdi, rbx
0x140005e76  jnb     short loc_140005E89
0x140005e78  call    cs:__imp__o__errno
0x140005e7e  mov     dword ptr [rax], 22h ; '"'
0x140005e84  call    _invalid_parameter_noinfo
0x140005e89  mov     rbx, [rsp+28h+arg_0]
0x140005e8e  mov     rsi, [rsp+28h+arg_8]
0x140005e93  add     rsp, 20h
0x140005e97  pop     rdi
0x140005e98  retn
```
