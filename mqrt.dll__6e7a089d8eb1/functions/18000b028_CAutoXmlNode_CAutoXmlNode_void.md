# CAutoXmlNode::~CAutoXmlNode(void)

- ea: `0x18000b028`
- end: `0x18000b04b`
- name: `??1CAutoXmlNode@@QEAA@XZ`
- size: `35`
- prototype: `void __fastcall(CAutoXmlNode *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800244f2`
- `0x180025421`

## callees

- `0x18000b028`
- `0x18001ecfc`

## pseudocode

```c
void __fastcall CAutoXmlNode::~CAutoXmlNode(struct XmlNode **this)
{
  struct XmlNode *v2; // rcx

  v2 = *this;
  if ( v2 )
  {
    XmlFreeTree(v2);
    *this = 0;
  }
}

```

## disassembly

```asm
0x18000b028  push    rbx
0x18000b02a  sub     rsp, 20h
0x18000b02e  mov     rbx, rcx
0x18000b031  mov     rcx, [rcx]; struct XmlNode *
0x18000b034  test    rcx, rcx
0x18000b037  jz      short loc_18000B045
0x18000b039  call    ?XmlFreeTree@@YAXPEAVXmlNode@@@Z; XmlFreeTree(XmlNode *)
0x18000b03e  mov     qword ptr [rbx], 0
0x18000b045  add     rsp, 20h
0x18000b049  pop     rbx
0x18000b04a  retn
```
