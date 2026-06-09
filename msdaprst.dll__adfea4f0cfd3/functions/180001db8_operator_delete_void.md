# operator delete(void *)

- ea: `0x180001db8`
- end: `0x180001dcc`
- name: `??3@YAXPEAX@Z`
- size: `20`
- prototype: `void __fastcall(void *)`
- caller_count: `104`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180001610`
- `0x180001fc0`
- `0x1800025c0`
- `0x180002760`
- `0x1800027b0`
- `0x1800031e4`
- `0x1800045cc`
- `0x180004930`
- `0x18000510c`
- `0x180005264`
- `0x180005950`
- `0x180005ab0`
- `0x180005ae0`
- `0x180005b20`
- `0x180007838`
- `0x180008518`
- `0x180008798`
- `0x180009498`
- `0x18000a4d8`
- `0x18000a6e4`
- `0x18000a86c`
- `0x18000a918`
- `0x18000a940`
- `0x18000a968`
- `0x18000a990`
- `0x18000a9b8`
- `0x18000a9e0`
- `0x18000aa08`
- `0x18000aa30`
- `0x18000aa58`
- `0x18000aa80`
- `0x18000aaa8`
- `0x18000aad0`
- `0x18000ab10`
- `0x18000cbc8`
- `0x18000d1fc`
- `0x18000eeb0`
- `0x18000f2e0`
- `0x18000fbbc`
- `0x180010564`
- `0x180010658`
- `0x180010ee0`
- `0x180011fac`
- `0x180012300`
- `0x180014058`
- `0x180014080`
- `0x1800140a8`
- `0x1800140d0`
- `0x180014110`
- `0x180015370`

## callees

- `0x180001db8`
- `0x180001e24`

## pseudocode

```c
void __fastcall operator delete(unsigned __int8 *a1)
{
  if ( a1 )
    MMMFree(a1);
}

```

## disassembly

```asm
0x180001db8  sub     rsp, 28h
0x180001dbc  test    rcx, rcx
0x180001dbf  jz      short loc_180001DC6
0x180001dc1  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x180001dc6  add     rsp, 28h
0x180001dca  retn
```
