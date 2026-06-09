# XMLScrServProv::Release(void)

- ea: `0x1400118f0`
- end: `0x140011929`
- name: `?Release@XMLScrServProv@@UEAAKXZ`
- size: `57`
- prototype: `unsigned int __fastcall(XMLScrServProv *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callees

- `0x140009cb0`
- `0x1400111a0`
- `0x1400118f0`

## pseudocode

```c
__int64 __fastcall XMLScrServProv::Release(XMLScrServProv *this)
{
  unsigned __int32 v2; // edi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 4);
  if ( !v2 && this )
  {
    XMLScrServProv::~XMLScrServProv(this);
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x1400118f0  mov     [rsp+arg_0], rbx
0x1400118f5  push    rdi
0x1400118f6  sub     rsp, 20h
0x1400118fa  mov     rbx, rcx
0x1400118fd  or      edi, 0FFFFFFFFh
0x140011900  lock xadd [rcx+10h], edi
0x140011905  sub     edi, 1
0x140011908  jnz     short loc_14001191C
0x14001190a  test    rcx, rcx
0x14001190d  jz      short loc_14001191C
0x14001190f  call    ??1XMLScrServProv@@AEAA@XZ; XMLScrServProv::~XMLScrServProv(void)
0x140011914  mov     rcx, rbx; Block
0x140011917  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14001191c  mov     rbx, [rsp+28h+arg_0]
0x140011921  mov     eax, edi
0x140011923  add     rsp, 20h
0x140011927  pop     rdi
0x140011928  retn
```
