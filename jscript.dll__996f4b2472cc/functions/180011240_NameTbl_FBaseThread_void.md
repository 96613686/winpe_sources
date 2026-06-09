# NameTbl::FBaseThread(void)

- ea: `0x180011240`
- end: `0x180011286`
- name: `?FBaseThread@NameTbl@@IEAAHXZ`
- size: `70`
- prototype: `__int64 __fastcall(NameTbl *__hidden this)`
- caller_count: `46`
- callee_count: `1`
- tags: ``

## callers

- `0x180001b30`
- `0x180001e60`
- `0x180010390`
- `0x1800105a0`
- `0x180010d60`
- `0x180010e40`
- `0x180010e90`
- `0x180011180`
- `0x1800115f0`
- `0x1800117e0`
- `0x180011850`
- `0x180015a10`
- `0x180015ee0`
- `0x1800307e0`
- `0x18003f7a0`
- `0x1800435e0`
- `0x180043780`
- `0x180044d20`
- `0x1800450e0`
- `0x180047860`
- `0x180047a40`
- `0x180047c00`
- `0x1800495e0`
- `0x18004a040`
- `0x18004ae10`
- `0x18004bdb0`
- `0x18004c8f0`
- `0x18004ce30`
- `0x180054de0`
- `0x180055e00`
- `0x1800571c0`
- `0x18005f2ac`
- `0x1800600a4`
- `0x1800604fc`
- `0x1800609c0`
- `0x180060af0`
- `0x180061030`
- `0x1800632d0`
- `0x18006a300`
- `0x18006a460`
- `0x18006a6f0`
- `0x18006a7a0`
- `0x180077ab0`
- `0x180077c60`
- `0x180077cf4`
- `0x180077dd0`

## callees

- `0x180011240`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x18001124f`
- `KERNEL32!TlsGetValue` at `0x18001124f`

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
0x180011240  push    rbx
0x180011242  sub     rsp, 20h
0x180011246  mov     rbx, rcx
0x180011249  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x18001124f  call    cs:__imp_TlsGetValue
0x180011256  nop     dword ptr [rax+rax+00h]
0x18001125b  test    rax, rax
0x18001125e  jz      short loc_180011274
0x180011260  mov     rdx, [rax+20h]
0x180011264  xor     eax, eax
0x180011266  cmp     rdx, [rbx+48h]
0x18001126a  setz    al
0x18001126d  add     rsp, 20h
0x180011271  pop     rbx
0x180011272  retn
0x180011274  xor     eax, eax
0x180011276  xor     edx, edx
0x180011278  cmp     rdx, [rbx+48h]
0x18001127c  setz    al
0x18001127f  add     rsp, 20h
0x180011283  pop     rbx
0x180011284  retn
```
