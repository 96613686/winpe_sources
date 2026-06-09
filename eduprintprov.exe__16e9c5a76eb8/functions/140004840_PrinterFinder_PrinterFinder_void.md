# PrinterFinder::PrinterFinder(void)

- ea: `0x140004840`
- end: `0x14000491d`
- name: `??0PrinterFinder@@QEAA@XZ`
- size: `221`
- prototype: `PrinterFinder *__fastcall(PrinterFinder *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000d2a4`

## callees

- `0x140004840`
- `0x14000b914`
- `0x14000c160`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000485c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000485c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
PrinterFinder *__fastcall PrinterFinder::PrinterFinder(PrinterFinder *this)
{
  unsigned int v2; // r8d
  const char *v3; // r9
  unsigned __int64 v4; // rbx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *(_QWORD *)this = CreateEventW(0, 0, 0, 0);
  *(_OWORD *)((char *)this + 136) = 0;
  v4 = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 7;
  *((_WORD *)this + 68) = 0;
  *(_OWORD *)((char *)this + 168) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 7;
  *((_WORD *)this + 84) = 0;
  *((_OWORD *)this + 13) = 0;
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = 7;
  *((_WORD *)this + 104) = 0;
  if ( !*(_QWORD *)this )
    wil::details::in1diag3::_Throw_NullAlloc(retaddr, (void *)0x38, v2, v3);
  do
  {
    memcpy_s((char *)this + 32 * v4 + 8, 128 - 32 * v4, &qword_14001D150[5 * v4], 0x20u);
    ++v4;
  }
  while ( v4 < 4 );
  return this;
}

```

## disassembly

```asm
0x140004840  mov     [rsp+arg_8], rbx
0x140004845  mov     [rsp+arg_0], rcx
0x14000484a  push    rdi
0x14000484b  sub     rsp, 20h
0x14000484f  mov     rdi, rcx
0x140004852  xor     r9d, r9d; lpName
0x140004855  xor     r8d, r8d; bInitialState
0x140004858  xor     edx, edx; bManualReset
0x14000485a  xor     ecx, ecx; lpEventAttributes
0x14000485c  call    cs:__imp_CreateEventW
0x140004862  mov     [rdi], rax
0x140004865  xorps   xmm0, xmm0
0x140004868  movups  xmmword ptr [rdi+88h], xmm0
0x14000486f  xor     ebx, ebx
0x140004871  mov     [rdi+98h], rbx
0x140004878  lea     ecx, [rbx+7]
0x14000487b  mov     [rdi+0A0h], rcx
0x140004882  mov     [rdi+88h], bx
0x140004889  movups  xmmword ptr [rdi+0A8h], xmm0
0x140004890  mov     [rdi+0B8h], rbx
0x140004897  mov     [rdi+0C0h], rcx
0x14000489e  mov     [rdi+0A8h], bx
0x1400048a5  movups  xmmword ptr [rdi+0D0h], xmm0
0x1400048ac  mov     [rdi+0E0h], rbx
0x1400048b3  mov     [rdi+0E8h], rcx
0x1400048ba  mov     [rdi+0D0h], bx
0x1400048c1  mov     rcx, [rsp+28h]; this
0x1400048c6  cmp     [rdi], rbx
0x1400048c9  jz      short loc_140004912
0x1400048cb  mov     rcx, rbx
0x1400048ce  shl     rcx, 5
0x1400048d2  lea     rax, [rbx+rbx*4]
0x1400048d6  lea     rdx, qword_14001D150
0x1400048dd  lea     r8, [rdx+rax*8]; Source
0x1400048e1  mov     edx, 80h
0x1400048e6  sub     rdx, rcx; DestinationSize
0x1400048e9  add     rcx, 8
0x1400048ed  add     rcx, rdi; Destination
0x1400048f0  mov     r9d, 20h ; ' '; SourceSize
0x1400048f6  call    memcpy_s
0x1400048fb  inc     rbx
0x1400048fe  cmp     rbx, 4
0x140004902  jb      short loc_1400048CB
0x140004904  mov     rax, rdi
0x140004907  mov     rbx, [rsp+28h+arg_8]
0x14000490c  add     rsp, 20h
0x140004910  pop     rdi
0x140004911  retn
0x140004912  mov     edx, 38h ; '8'; void *
0x140004917  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
