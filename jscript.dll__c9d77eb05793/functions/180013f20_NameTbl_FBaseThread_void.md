# NameTbl::FBaseThread(void)

- ea: `0x180013f20`
- end: `0x180013f5e`
- name: `?FBaseThread@NameTbl@@IEAAHXZ`
- size: `62`
- prototype: `__int64 __fastcall(NameTbl *__hidden this)`
- caller_count: `45`
- callee_count: `1`
- tags: ``

## callers

- `0x180001e40`
- `0x180013140`
- `0x180013350`
- `0x180013b10`
- `0x180013bf0`
- `0x180013c40`
- `0x1800142c0`
- `0x1800144a0`
- `0x180014510`
- `0x180018b40`
- `0x180018ef0`
- `0x1800385e0`
- `0x180038910`
- `0x180042110`
- `0x1800425a0`
- `0x180043a80`
- `0x1800442b0`
- `0x180046a10`
- `0x180046bf0`
- `0x180046ee0`
- `0x1800484f0`
- `0x180049340`
- `0x18004a010`
- `0x18004b080`
- `0x18004b450`
- `0x18004b6b0`
- `0x18004c2e0`
- `0x180053fe0`
- `0x180054f80`
- `0x1800562d0`
- `0x18005e0ec`
- `0x18005eea4`
- `0x18005f2fc`
- `0x18005f7c0`
- `0x18005f8e0`
- `0x18005fe10`
- `0x180062080`
- `0x180068fc0`
- `0x180069120`
- `0x1800693b0`
- `0x180069460`
- `0x180076570`
- `0x180076720`
- `0x1800767b0`
- `0x180076880`

## callees

- `0x180013f20`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x180013f2f`
- `KERNEL32!TlsGetValue` at `0x180013f2f`

## pseudocode

```c
_BOOL8 __fastcall NameTbl::FBaseThread(NameTbl *this)
{
  _QWORD *Value; // rax

  Value = TlsGetValue(g_luTls);
  if ( Value )
    return Value[4] == *((_QWORD *)this + 9);
  else
    return *((_QWORD *)this + 9) == 0;
}

```

## disassembly

```asm
0x180013f20  push    rbx
0x180013f22  sub     rsp, 20h
0x180013f26  mov     rbx, rcx
0x180013f29  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x180013f2f  call    cs:__imp_TlsGetValue
0x180013f35  test    rax, rax
0x180013f38  jz      short loc_180013F4D
0x180013f3a  mov     rdx, [rax+20h]
0x180013f3e  xor     eax, eax
0x180013f40  cmp     rdx, [rbx+48h]
0x180013f44  setz    al
0x180013f47  add     rsp, 20h
0x180013f4b  pop     rbx
0x180013f4c  retn
0x180013f4d  xor     eax, eax
0x180013f4f  xor     edx, edx
0x180013f51  cmp     rdx, [rbx+48h]
0x180013f55  setz    al
0x180013f58  add     rsp, 20h
0x180013f5c  pop     rbx
0x180013f5d  retn
```
