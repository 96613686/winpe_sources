# StoredMatchValue::~StoredMatchValue(void)

- ea: `0x18000ce00`
- end: `0x18000ce95`
- name: `??1StoredMatchValue@@QEAA@XZ`
- size: `149`
- prototype: `void __fastcall(StoredMatchValue *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000c548`
- `0x18000cb04`
- `0x18000f970`
- `0x180010d18`
- `0x1800142d2`

## callees

- `0x18000ce00`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000ce14`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000ce3f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000ce6d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000ce14`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000ce3f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000ce6d`

## pseudocode

```c
void __fastcall StoredMatchValue::~StoredMatchValue(void **this)
{
  void *v2; // rcx

  if ( (unsigned __int64)this[11] >= 8 )
    operator delete(this[8]);
  this[11] = (void *)7;
  this[10] = 0;
  *((_WORD *)this + 32) = 0;
  v2 = this[5];
  if ( v2 )
  {
    operator delete(v2);
    this[5] = 0;
    this[6] = 0;
    this[7] = 0;
  }
  if ( (unsigned __int64)this[3] >= 8 )
    operator delete(*this);
  this[3] = (void *)7;
  this[2] = 0;
  *(_WORD *)this = 0;
}

```

## disassembly

```asm
0x18000ce00  push    rbx
0x18000ce02  sub     rsp, 20h
0x18000ce06  cmp     qword ptr [rcx+58h], 8
0x18000ce0b  mov     rbx, rcx
0x18000ce0e  jb      short loc_18000CE20
0x18000ce10  mov     rcx, [rcx+40h]
0x18000ce14  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000ce1b  nop     dword ptr [rax+rax+00h]
0x18000ce20  xor     eax, eax
0x18000ce22  mov     qword ptr [rbx+58h], 7
0x18000ce2a  mov     qword ptr [rbx+50h], 0
0x18000ce32  mov     [rbx+40h], ax
0x18000ce36  mov     rcx, [rbx+28h]
0x18000ce3a  test    rcx, rcx
0x18000ce3d  jz      short loc_18000CE63
0x18000ce3f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000ce46  nop     dword ptr [rax+rax+00h]
0x18000ce4b  mov     qword ptr [rbx+28h], 0
0x18000ce53  mov     qword ptr [rbx+30h], 0
0x18000ce5b  mov     qword ptr [rbx+38h], 0
0x18000ce63  cmp     qword ptr [rbx+18h], 8
0x18000ce68  jb      short loc_18000CE79
0x18000ce6a  mov     rcx, [rbx]
0x18000ce6d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000ce74  nop     dword ptr [rax+rax+00h]
0x18000ce79  xor     eax, eax
0x18000ce7b  mov     qword ptr [rbx+18h], 7
0x18000ce83  mov     qword ptr [rbx+10h], 0
0x18000ce8b  mov     [rbx], ax
0x18000ce8e  add     rsp, 20h
0x18000ce92  pop     rbx
0x18000ce93  retn
```
