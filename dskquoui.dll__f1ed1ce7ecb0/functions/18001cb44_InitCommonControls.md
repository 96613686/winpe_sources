# InitCommonControls

- ea: `0x18001cb44`
- end: `0x18001cb7e`
- name: `InitCommonControls`
- size: `58`
- prototype: `void __stdcall()`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010960`

## callees

- `0x18001cb44`
- `0x18001cc10`
- `0x18001f010`

## string_xrefs

- `0x18001cb55`: `InitCommonControls`

## pseudocode

```c
void __stdcall InitCommonControls()
{
  void (*v0)(void); // rax

  v0 = (void (*)(void))qword_1800282E0;
  if ( qword_1800282E0 == -1 )
  {
    GetProcFromComCtl32(&qword_1800282E0, "InitCommonControls");
    v0 = (void (*)(void))qword_1800282E0;
  }
  if ( v0 )
    v0();
}

```

## disassembly

```asm
0x18001cb44  sub     rsp, 28h
0x18001cb48  mov     rax, cs:qword_1800282E0
0x18001cb4f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001cb53  jnz     short loc_18001CB6F
0x18001cb55  lea     rdx, aInitcommoncont; "InitCommonControls"
0x18001cb5c  lea     rcx, qword_1800282E0
0x18001cb63  call    _GetProcFromComCtl32
0x18001cb68  mov     rax, cs:qword_1800282E0
0x18001cb6f  test    rax, rax
0x18001cb72  jz      short loc_18001CB79
0x18001cb74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb79  add     rsp, 28h
0x18001cb7d  retn
```
