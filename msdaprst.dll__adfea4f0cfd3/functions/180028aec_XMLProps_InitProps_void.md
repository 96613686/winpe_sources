# XMLProps::_InitProps(void)

- ea: `0x180028aec`
- end: `0x180028d57`
- name: `?_InitProps@XMLProps@@CAXXZ`
- size: `619`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18001f7c8`
- `0x180028148`

## pseudocode

```c
void XMLProps::_InitProps(void)
{
  LODWORD(XMLProps::m_rgXMLProps) = 34;
  dword_180046598 = 0;
  word_1800465B0 = 0;
  word_1800465C8 = -1;
  xmmword_18004655C[0] = (__int128)DBPROPSET_ROWSET;
  LODWORD(XMLProps::m_rgRSAttr) = 4;
  dword_180046718 = 4;
  LODWORD(XMLProps::m_rgTags) = 370480147;
  word_1800465A8 = 11;
  dword_180046720 = 14;
  dword_1800466E8 = 14;
  dword_1800466C4 = 5;
  word_1800465C0 = 11;
  dword_18004670C = 5;
  XMLProps::m_rgPropSets = (struct tagDBPROPIDSET near *)&XMLProps::m_rgXMLProps;
  dword_180046714 = 11;
  qword_180046570 = (__int64)&dword_18004670C;
  XMLProps::m_rgTagSets = &XMLProps::m_rgTags;
  qword_180046538 = (__int64)&XMLProps::m_rgTags + 3;
  dword_1800466DC = 11;
  XMLProps::m_rgRSAttrSets = &XMLProps::m_rgRSAttr;
  LOWORD(XMLProps::m_rgDefaults) = 3;
  dword_180046704 = 127;
  dword_180046708 = 134;
  dword_1800466C8 = 6;
  dword_1800466CC = 7;
  word_1800465D8 = 3;
  dword_1800465E0 = 2;
  dword_180046710 = 19;
  dword_1800466F4 = 437852183;
  dword_1800466D0 = 8;
  word_1800465F0 = 3;
  dword_1800465F8 = 1;
  dword_1800466D4 = 9;
  word_180046608 = 3;
  dword_180046610 = 1;
  dword_1800466D8 = 10;
  word_180046620 = 3;
  dword_180046628 = 15;
  dword_18004671C = 13;
  word_180046638 = 8;
  qword_180046640 = (__int64)&strIn;
  dword_1800466F8 = 505224219;
  dword_1800466E0 = 12;
  word_180046650 = 8;
  qword_180046658 = (__int64)&strIn;
  dword_180046724 = 15;
  dword_1800466E4 = 13;
  word_180046668 = 8;
  qword_180046670 = (__int64)&strIn;
  dword_180046728 = 16;
  word_180046680 = 8;
  qword_180046688 = (__int64)&strIn;
  dword_18004672C = 18;
  dword_1800466EC = 15;
  word_180046698 = 8;
  qword_1800466A0 = (__int64)&strIn;
  dword_180046558 = 3;
  dword_180046578 = 9;
  xmmword_18004657C = (__int128)DBPROPSET_ADC;
  qword_1800466B8 = (__int64)&dword_1800466CC;
  XMLProps::m_rgDefaultSets = &XMLProps::m_rgDefaults;
  qword_180046548 = (__int64)&word_1800465D8;
  XMLProps::m_fInitialized = 1;
}

```

## disassembly

```asm
0x180028aec  mov     [rsp+arg_0], rbx
0x180028af1  movups  xmm0, xmmword ptr cs:DBPROPSET_ROWSET.Data1
0x180028af8  xor     eax, eax
0x180028afa  mov     cs:?m_rgXMLProps@XMLProps@@0PAKA, 22h ; '"'; ulong near * XMLProps::m_rgXMLProps
0x180028b04  mov     cs:dword_180046598, eax
0x180028b0a  mov     r8d, 4
0x180028b10  mov     cs:word_1800465B0, ax
0x180028b17  or      eax, 0FFFFFFFFh
0x180028b1a  mov     cs:word_1800465C8, ax
0x180028b21  movdqu  cs:xmmword_18004655C, xmm0
0x180028b29  lea     ebx, [r8-1]
0x180028b2d  mov     cs:?m_rgRSAttr@XMLProps@@0PAW4ROWSETATTRIBUTES@@A, r8d; ROWSETATTRIBUTES near * XMLProps::m_rgRSAttr
0x180028b34  movups  xmm0, xmmword ptr cs:?DBPROPSET_ADC@@3U_GUID@@B.Data1; _GUID const DBPROPSET_ADC ...
0x180028b3b  lea     r9d, [r8+4]
0x180028b3f  mov     cs:dword_180046718, r8d
0x180028b46  lea     edx, [rbx+8]
0x180028b49  mov     cs:?m_rgTags@XMLProps@@0PAEA, 16151413h; uchar near * XMLProps::m_rgTags
0x180028b53  lea     eax, [rbx+0Bh]
0x180028b56  mov     cs:word_1800465A8, dx
0x180028b5d  mov     cs:dword_180046720, eax
0x180028b63  lea     ecx, [rbx+2]
0x180028b66  mov     cs:dword_1800466E8, eax
0x180028b6c  lea     r11d, [r8-3]
0x180028b70  lea     r10d, [r8+5]
0x180028b74  mov     cs:dword_1800466C4, ecx
0x180028b7a  lea     r8d, [rbx+0Ch]
0x180028b7e  mov     cs:word_1800465C0, dx
0x180028b85  lea     rax, ?m_rgXMLProps@XMLProps@@0PAKA; ulong near * XMLProps::m_rgXMLProps
0x180028b8c  mov     cs:dword_18004670C, ecx
0x180028b92  mov     cs:?m_rgPropSets@XMLProps@@0PAUtagDBPROPIDSET@@A, rax; tagDBPROPIDSET near * XMLProps::m_rgPropSets
0x180028b99  lea     ecx, [rbx+0Ah]
0x180028b9c  lea     rax, dword_18004670C
0x180028ba3  mov     cs:dword_180046714, edx
0x180028ba9  mov     cs:qword_180046570, rax
0x180028bb0  lea     rax, ?m_rgTags@XMLProps@@0PAEA; uchar near * XMLProps::m_rgTags
0x180028bb7  mov     cs:?m_rgTagSets@XMLProps@@0PAPEAEA, rax; uchar * near * XMLProps::m_rgTagSets
0x180028bbe  lea     rax, ?m_rgTags@XMLProps@@0PAEA+3; uchar near * XMLProps::m_rgTags
0x180028bc5  mov     cs:qword_180046538, rax
0x180028bcc  lea     rax, ?m_rgRSAttr@XMLProps@@0PAW4ROWSETATTRIBUTES@@A; ROWSETATTRIBUTES near * XMLProps::m_rgRSAttr
0x180028bd3  mov     cs:dword_1800466DC, edx
0x180028bd9  lea     rdx, strIn
0x180028be0  mov     cs:?m_rgRSAttrSets@XMLProps@@0PAPEAW4ROWSETATTRIBUTES@@A, rax; ROWSETATTRIBUTES * near * XMLProps::m_rgRSAttrSets
0x180028be7  lea     rax, dword_1800466CC
0x180028bee  mov     cs:?m_rgDefaults@XMLProps@@0PAUtagVARIANT@@A, bx; tagVARIANT near * XMLProps::m_rgDefaults
0x180028bf5  mov     cs:dword_180046704, 7Fh
0x180028bff  mov     cs:dword_180046708, 86h
0x180028c09  mov     cs:dword_1800466C8, 6
0x180028c13  mov     cs:dword_1800466CC, 7
0x180028c1d  mov     cs:word_1800465D8, bx
0x180028c24  mov     cs:dword_1800465E0, 2
0x180028c2e  mov     cs:dword_180046710, 13h
0x180028c38  mov     cs:dword_1800466F4, 1A191817h
0x180028c42  mov     cs:dword_1800466D0, r9d
0x180028c49  mov     cs:word_1800465F0, bx
0x180028c50  mov     cs:dword_1800465F8, r11d
0x180028c57  mov     cs:dword_1800466D4, r10d
0x180028c5e  mov     cs:word_180046608, bx
0x180028c65  mov     cs:dword_180046610, r11d
0x180028c6c  mov     cs:dword_1800466D8, 0Ah
0x180028c76  mov     cs:word_180046620, bx
0x180028c7d  mov     cs:dword_180046628, r8d
0x180028c84  mov     cs:dword_18004671C, ecx
0x180028c8a  mov     cs:word_180046638, r9w
0x180028c92  mov     cs:qword_180046640, rdx
0x180028c99  mov     cs:dword_1800466F8, 1E1D1C1Bh
0x180028ca3  mov     cs:dword_1800466E0, 0Ch
0x180028cad  mov     cs:word_180046650, r9w
0x180028cb5  mov     cs:qword_180046658, rdx
0x180028cbc  mov     cs:dword_180046724, r8d
0x180028cc3  mov     cs:dword_1800466E4, ecx
0x180028cc9  mov     cs:word_180046668, r9w
0x180028cd1  mov     cs:qword_180046670, rdx
0x180028cd8  mov     cs:dword_180046728, 10h
0x180028ce2  mov     cs:word_180046680, r9w
0x180028cea  mov     cs:qword_180046688, rdx
0x180028cf1  mov     cs:dword_18004672C, 12h
0x180028cfb  mov     cs:dword_1800466EC, r8d
0x180028d02  mov     cs:word_180046698, r9w
0x180028d0a  mov     cs:qword_1800466A0, rdx
0x180028d11  mov     cs:dword_180046558, ebx
0x180028d17  mov     cs:dword_180046578, r10d
0x180028d1e  movdqu  cs:xmmword_18004657C, xmm0
0x180028d26  mov     rbx, [rsp+arg_0]
0x180028d2b  mov     cs:qword_1800466B8, rax
0x180028d32  lea     rax, ?m_rgDefaults@XMLProps@@0PAUtagVARIANT@@A; tagVARIANT near * XMLProps::m_rgDefaults
0x180028d39  mov     cs:?m_rgDefaultSets@XMLProps@@0PAPEAUtagVARIANT@@A, rax; tagVARIANT * near * XMLProps::m_rgDefaultSets
0x180028d40  lea     rax, word_1800465D8
0x180028d47  mov     cs:qword_180046548, rax
0x180028d4e  mov     cs:?m_fInitialized@XMLProps@@0KA, r11d; ulong XMLProps::m_fInitialized
0x180028d55  retn
```
