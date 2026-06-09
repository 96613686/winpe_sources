# NCoreLibrary::TString::~TString(void)

- ea: `0x18001772c`
- end: `0x180017756`
- name: `??1TString@NCoreLibrary@@QEAA@XZ`
- size: `42`
- prototype: `void __fastcall(NCoreLibrary::TString *__hidden this)`
- caller_count: `27`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000bd60`
- `0x18000bee0`
- `0x18000d060`
- `0x18000d338`
- `0x18000d7dc`
- `0x18000de80`
- `0x18000e7ac`
- `0x18000e9d8`
- `0x18000ec28`
- `0x18000ed10`
- `0x18000f074`
- `0x18000ffe0`
- `0x180010404`
- `0x180010780`
- `0x180011a34`
- `0x180011fb4`
- `0x180012228`
- `0x180012bd0`
- `0x180012e80`
- `0x180013580`
- `0x180014870`
- `0x180014a30`
- `0x180014b78`
- `0x180015c5c`
- `0x180015cc8`
- `0x180015ecc`
- `0x180016a70`

## callees

- `0x180001334`
- `0x18001772c`

## pseudocode

```c
void __fastcall NCoreLibrary::TString::~TString(NCoreLibrary::TString *this)
{
  __int16 *v1; // rcx

  v1 = (__int16 *)*((_QWORD *)this + 1);
  if ( v1 != (__int16 *)&NCoreLibrary::TString::gszNullState && v1 != &word_180021DD6 )
    operator delete(v1);
}

```

## disassembly

```asm
0x18001772c  sub     rsp, 28h
0x180017730  mov     rcx, [rcx+8]; Block
0x180017734  lea     rax, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x18001773b  cmp     rcx, rax
0x18001773e  jz      short loc_180017751
0x180017740  lea     rax, word_180021DD6
0x180017747  cmp     rcx, rax
0x18001774a  jz      short loc_180017751
0x18001774c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180017751  add     rsp, 28h
0x180017755  retn
```
