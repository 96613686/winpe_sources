# XmlReader::FirstChildElement(void)

- ea: `0x18001cb90`
- end: `0x18001cbce`
- name: `?FirstChildElement@XmlReader@@QEAA_NXZ`
- size: `62`
- prototype: `bool __fastcall(XmlReader *__hidden this)`
- caller_count: `24`
- callee_count: `3`
- tags: `registry_config`

## callers

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

- `0x18001cb90`
- `0x18001cbd4`
- `0x180038cc4`

## pseudocode

```c
char __fastcall XmlReader::FirstChildElement(XmlReader *this)
{
  char result; // al
  enum XmlNodeType v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = XmlNodeType_None;
  result = XmlReader::FirstChild(this, &v3);
  if ( result )
  {
    result = 1;
    if ( v3 != XmlNodeType_Element )
      return XmlReader::NextChildElement((xp::XmlReader **)this);
  }
  return result;
}

```

## disassembly

```asm
0x18001cb90  push    rbx
0x18001cb92  sub     rsp, 20h
0x18001cb96  lea     rdx, [rsp+28h+arg_8]; enum XmlNodeType *
0x18001cb9b  mov     [rsp+28h+arg_8], 0
0x18001cba3  mov     rbx, rcx
0x18001cba6  call    ?FirstChild@XmlReader@@QEAA_NPEAW4XmlNodeType@@@Z; XmlReader::FirstChild(XmlNodeType *)
0x18001cbab  test    al, al
0x18001cbad  jnz     short loc_18001CBB5
0x18001cbaf  add     rsp, 20h
0x18001cbb3  pop     rbx
0x18001cbb4  retn
0x18001cbb5  mov     eax, 1
0x18001cbba  cmp     [rsp+28h+arg_8], eax
0x18001cbbe  jz      short loc_18001CBC8
0x18001cbc0  mov     rcx, rbx; this
0x18001cbc3  call    ?NextChildElement@XmlReader@@QEAA_NXZ; XmlReader::NextChildElement(void)
0x18001cbc8  add     rsp, 20h
0x18001cbcc  pop     rbx
0x18001cbcd  retn
```
