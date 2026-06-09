# SnapinOwnerTable::Dump(BookKeepingXml &)

- ea: `0x18000f2fc`
- end: `0x18000f3f2`
- name: `?Dump@SnapinOwnerTable@@QEAAJAEAVBookKeepingXml@@@Z`
- size: `246`
- prototype: `int(SnapinOwnerTable *__hidden this, struct BookKeepingXml *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000d370`

## callees

- `0x180003fa0`
- `0x180008630`
- `0x18000c64c`
- `0x18000cb94`
- `0x18000f2fc`
- `0x180010290`

## pseudocode

```c
__int64 __fastcall SnapinOwnerTable::Dump(SnapinOwnerTable *this, struct BookKeepingXml *a2)
{
  int v3; // eax
  SnapinOwnerTable *v4; // rcx
  int v5; // ebx
  int i; // esi
  SnapinRecord *Snapin; // rax
  int v8; // eax
  int v9; // eax
  unsigned int v10; // esi

  v3 = BookKeepingXml::OpenTable(a2, 0);
  v5 = v3;
  if ( v3 >= 0 )
  {
    for ( i = 0; ; ++i )
    {
      Snapin = SnapinOwnerTable::GetSnapin(v4, i);
      if ( !Snapin )
        break;
      v8 = SnapinRecord::Dump(Snapin, a2);
      v5 = v8;
      if ( v8 < 0 )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
          WPP_SF_d(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            20,
            WPP_8949107765ef31f55290197bfd8c288d_Traceguids,
            (unsigned int)v8);
        break;
      }
    }
    v9 = BookKeepingXml::CloseTable(a2);
    v10 = v9;
    if ( v9 < 0 && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        21,
        WPP_8949107765ef31f55290197bfd8c288d_Traceguids,
        (unsigned int)v9);
    if ( v5 >= 0 )
      return v10;
  }
  else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      19,
      WPP_8949107765ef31f55290197bfd8c288d_Traceguids,
      (unsigned int)v3);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000f2fc  push    rbx
0x18000f2fe  push    rbp
0x18000f2ff  push    rsi
0x18000f300  push    rdi
0x18000f301  sub     rsp, 28h
0x18000f305  mov     rbp, rdx
0x18000f308  xor     edx, edx
0x18000f30a  mov     rcx, rbp
0x18000f30d  call    ?OpenTable@BookKeepingXml@@QEAAJW4_XmlNameId@1@@Z; BookKeepingXml::OpenTable(BookKeepingXml::_XmlNameId)
0x18000f312  mov     ebx, eax
0x18000f314  test    eax, eax
0x18000f316  jns     short loc_18000F356
0x18000f318  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f31f  lea     rdi, WPP_GLOBAL_Control
0x18000f326  cmp     rcx, rdi
0x18000f329  jz      loc_18000F3E7
0x18000f32f  cmp     byte ptr [rcx+19h], 2
0x18000f333  jb      loc_18000F3E7
0x18000f339  mov     rcx, [rcx+10h]
0x18000f33d  lea     r8, WPP_8949107765ef31f55290197bfd8c288d_Traceguids
0x18000f344  mov     edx, 13h
0x18000f349  mov     r9d, eax
0x18000f34c  call    WPP_SF_d
0x18000f351  jmp     loc_18000F3E7
0x18000f356  xor     esi, esi
0x18000f358  mov     edx, esi; int
0x18000f35a  call    ?GetSnapin@SnapinOwnerTable@@QEAAPEAVSnapinRecord@@H@Z; SnapinOwnerTable::GetSnapin(int)
0x18000f35f  lea     rdi, WPP_GLOBAL_Control
0x18000f366  test    rax, rax
0x18000f369  jz      short loc_18000F3AA
0x18000f36b  mov     rdx, rbp; struct BookKeepingXml *
0x18000f36e  mov     rcx, rax; this
0x18000f371  call    ?Dump@SnapinRecord@@QEBAJAEAVBookKeepingXml@@@Z; SnapinRecord::Dump(BookKeepingXml &)
0x18000f376  mov     ebx, eax
0x18000f378  test    eax, eax
0x18000f37a  js      short loc_18000F380
0x18000f37c  inc     esi
0x18000f37e  jmp     short loc_18000F358
0x18000f380  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f387  cmp     rcx, rdi
0x18000f38a  jz      short loc_18000F3AA
0x18000f38c  cmp     byte ptr [rcx+19h], 2
0x18000f390  jb      short loc_18000F3AA
0x18000f392  mov     rcx, [rcx+10h]
0x18000f396  lea     r8, WPP_8949107765ef31f55290197bfd8c288d_Traceguids
0x18000f39d  mov     edx, 14h
0x18000f3a2  mov     r9d, eax
0x18000f3a5  call    WPP_SF_d
0x18000f3aa  mov     rcx, rbp; this
0x18000f3ad  call    ?CloseTable@BookKeepingXml@@QEAAJXZ; BookKeepingXml::CloseTable(void)
0x18000f3b2  mov     esi, eax
0x18000f3b4  test    eax, eax
0x18000f3b6  jns     short loc_18000F3E2
0x18000f3b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f3bf  cmp     rcx, rdi
0x18000f3c2  jz      short loc_18000F3E2
0x18000f3c4  cmp     byte ptr [rcx+19h], 2
0x18000f3c8  jb      short loc_18000F3E2
0x18000f3ca  mov     rcx, [rcx+10h]
0x18000f3ce  lea     r8, WPP_8949107765ef31f55290197bfd8c288d_Traceguids
0x18000f3d5  mov     edx, 15h
0x18000f3da  mov     r9d, eax
0x18000f3dd  call    WPP_SF_d
0x18000f3e2  test    ebx, ebx
0x18000f3e4  cmovns  ebx, esi
0x18000f3e7  mov     eax, ebx
0x18000f3e9  add     rsp, 28h
0x18000f3ed  pop     rdi
0x18000f3ee  pop     rsi
0x18000f3ef  pop     rbp
0x18000f3f0  pop     rbx
0x18000f3f1  retn
```
