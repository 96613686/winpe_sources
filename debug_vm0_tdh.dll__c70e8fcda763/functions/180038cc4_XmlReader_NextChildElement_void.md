# XmlReader::NextChildElement(void)

- ea: `0x180038cc4`
- end: `0x180038d31`
- name: `?NextChildElement@XmlReader@@QEAA_NXZ`
- size: `109`
- prototype: `bool __fastcall(XmlReader *__hidden this)`
- caller_count: `26`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180011b30`
- `0x18001cb90`
- `0x18001d810`
- `0x18002c650`
- `0x18003479c`
- `0x180034cbc`
- `0x180035780`
- `0x180036020`
- `0x1800360b4`
- `0x180036d30`
- `0x1800380ec`
- `0x180038228`
- `0x180038498`
- `0x1800386fc`
- `0x18003889c`
- `0x180038a44`
- `0x180038c30`
- `0x180038d38`
- `0x180039780`
- `0x180039878`
- `0x180039cdc`
- `0x18003b29c`
- `0x18003b4dc`
- `0x18003b6f8`
- `0x18003b7e0`
- `0x18003bae4`

## callees

- `0x18001ee78`
- `0x180038cc4`
- `0x18003afd4`

## pseudocode

```c
char __fastcall XmlReader::NextChildElement(xp::XmlReader **this)
{
  xp::XmlReader *v2; // rcx
  int v3; // ebx
  XmlNodeType v5; // [rsp+30h] [rbp+8h] BYREF

  while ( 1 )
  {
    v2 = *this;
    v5 = XmlNodeType_None;
    v3 = xp::XmlReader::Skip(v2, &v5);
    if ( !v3 )
      v3 = v5 == XmlNodeType_EndElement;
    XmlReader::ThrowIfFailed((XmlReader *)this, "NextChild", v3);
    if ( v3 )
      break;
    if ( v5 == XmlNodeType_Element )
      return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180038cc4  mov     [rsp+arg_8], rbx
0x180038cc9  mov     [rsp+arg_10], rsi
0x180038cce  push    rdi
0x180038ccf  sub     rsp, 20h
0x180038cd3  mov     rdi, rcx
0x180038cd6  mov     esi, 1
0x180038cdb  mov     rcx, [rdi]; this
0x180038cde  lea     rdx, [rsp+28h+arg_0]; enum XmlNodeType *
0x180038ce3  mov     [rsp+28h+arg_0], 0
0x180038ceb  call    ?Skip@XmlReader@xp@@QEAAJPEAW4XmlNodeType@@@Z; xp::XmlReader::Skip(XmlNodeType *)
0x180038cf0  mov     ebx, eax
0x180038cf2  test    eax, eax
0x180038cf4  jnz     short loc_180038CFE
0x180038cf6  cmp     [rsp+28h+arg_0], 0Fh
0x180038cfb  cmovz   ebx, esi
0x180038cfe  mov     r8d, ebx; int
0x180038d01  lea     rdx, aNextchild; "NextChild"
0x180038d08  mov     rcx, rdi; this
0x180038d0b  call    ?ThrowIfFailed@XmlReader@@AEBAXPEBDJ@Z; XmlReader::ThrowIfFailed(char const *,long)
0x180038d10  test    ebx, ebx
0x180038d12  jnz     short loc_180038D1F
0x180038d14  cmp     [rsp+28h+arg_0], esi
0x180038d18  jnz     short loc_180038CDB
0x180038d1a  mov     al, sil
0x180038d1d  jmp     short loc_180038D21
0x180038d1f  xor     al, al
0x180038d21  mov     rbx, [rsp+28h+arg_8]
0x180038d26  mov     rsi, [rsp+28h+arg_10]
0x180038d2b  add     rsp, 20h
0x180038d2f  pop     rdi
0x180038d30  retn
```
