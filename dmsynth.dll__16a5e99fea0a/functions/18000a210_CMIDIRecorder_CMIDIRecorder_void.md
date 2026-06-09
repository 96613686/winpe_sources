# CMIDIRecorder::~CMIDIRecorder(void)

- ea: `0x18000a210`
- end: `0x18000a2ab`
- name: `??1CMIDIRecorder@@QEAA@XZ`
- size: `155`
- prototype: `void __fastcall(CMIDIRecorder *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180003200`
- `0x180005dd0`
- `0x1800061a0`

## callees

- `0x180001514`
- `0x18000a210`

## pseudocode

```c
void __fastcall CMIDIRecorder::~CMIDIRecorder(CMIDIRecorder *this)
{
  __int64 v1; // rdx
  _QWORD *v3; // rcx
  _QWORD *v4; // r8

  v1 = *(_QWORD *)this;
  v3 = (_QWORD *)CMIDIRecorder::m_sFreeList;
  if ( v1 )
  {
    v4 = (_QWORD *)v1;
    do
    {
      if ( *(__int64 *)(v1 + 8) >= 0x7FFFFFFF )
        break;
      if ( v4 )
      {
        *(_QWORD *)this = *v4;
        *v4 = 0;
      }
      v3 = (_QWORD *)v1;
      *((_QWORD *)this + 1) = *(_QWORD *)(v1 + 8);
      *((_DWORD *)this + 4) = *(_DWORD *)(v1 + 16);
      *(_QWORD *)v1 = CMIDIRecorder::m_sFreeList;
      CMIDIRecorder::m_sFreeList = v1;
      v1 = *(_QWORD *)this;
      v4 = *(_QWORD **)this;
    }
    while ( *(_QWORD *)this );
  }
  if ( !--CMIDIRecorder::m_sUsageCount )
  {
    while ( v3 )
    {
      CMIDIRecorder::m_sFreeList = *v3;
      *v3 = 0;
      operator delete(v3);
      v3 = (_QWORD *)CMIDIRecorder::m_sFreeList;
    }
  }
}

```

## disassembly

```asm
0x18000a210  push    rbx
0x18000a212  sub     rsp, 20h
0x18000a216  mov     rdx, [rcx]
0x18000a219  xor     ebx, ebx
0x18000a21b  mov     r9, rcx
0x18000a21e  mov     rcx, cs:?m_sFreeList@CMIDIRecorder@@2VCMIDIDataList@@A; CMIDIDataList CMIDIRecorder::m_sFreeList
0x18000a225  test    rdx, rdx
0x18000a228  jz      short loc_18000A276
0x18000a22a  mov     r8, rdx
0x18000a22d  nop     dword ptr [rax]
0x18000a230  cmp     qword ptr [rdx+8], 7FFFFFFFh
0x18000a238  jge     short loc_18000A276
0x18000a23a  test    r8, r8
0x18000a23d  jz      short loc_18000A248
0x18000a23f  mov     rax, [r8]
0x18000a242  mov     [r9], rax
0x18000a245  mov     [r8], rbx
0x18000a248  mov     rax, [rdx+8]
0x18000a24c  mov     rcx, rdx; void *
0x18000a24f  mov     [r9+8], rax
0x18000a253  mov     eax, [rdx+10h]
0x18000a256  mov     [r9+10h], eax
0x18000a25a  mov     rax, cs:?m_sFreeList@CMIDIRecorder@@2VCMIDIDataList@@A; CMIDIDataList CMIDIRecorder::m_sFreeList
0x18000a261  mov     [rdx], rax
0x18000a264  mov     cs:?m_sFreeList@CMIDIRecorder@@2VCMIDIDataList@@A, rdx; CMIDIDataList CMIDIRecorder::m_sFreeList
0x18000a26b  mov     rdx, [r9]
0x18000a26e  mov     r8, rdx
0x18000a271  test    rdx, rdx
0x18000a274  jnz     short loc_18000A230
0x18000a276  add     cs:?m_sUsageCount@CMIDIRecorder@@0KA, 0FFFFFFFFh; ulong CMIDIRecorder::m_sUsageCount
0x18000a27d  jnz     short loc_18000A2A5
0x18000a27f  nop
0x18000a280  test    rcx, rcx
0x18000a283  jz      short loc_18000A2A5
0x18000a285  mov     rax, [rcx]
0x18000a288  mov     edx, 18h; unsigned __int64
0x18000a28d  mov     cs:?m_sFreeList@CMIDIRecorder@@2VCMIDIDataList@@A, rax; CMIDIDataList CMIDIRecorder::m_sFreeList
0x18000a294  mov     [rcx], rbx
0x18000a297  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a29c  mov     rcx, cs:?m_sFreeList@CMIDIRecorder@@2VCMIDIDataList@@A; CMIDIDataList CMIDIRecorder::m_sFreeList
0x18000a2a3  jmp     short loc_18000A280
0x18000a2a5  add     rsp, 20h
0x18000a2a9  pop     rbx
0x18000a2aa  retn
```
