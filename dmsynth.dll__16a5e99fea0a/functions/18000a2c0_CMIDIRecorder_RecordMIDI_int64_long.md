# CMIDIRecorder::RecordMIDI(__int64,long)

- ea: `0x18000a2c0`
- end: `0x18000a3bf`
- name: `?RecordMIDI@CMIDIRecorder@@QEAAH_JJ@Z`
- size: `255`
- prototype: `__int64 __fastcall(CMIDIRecorder *__hidden this, __int64, int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004fc0`
- `0x180005630`

## callees

- `0x18000a2c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000a2f7`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000a2f7`

## pseudocode

```c
__int64 __fastcall CMIDIRecorder::RecordMIDI(__int64 **this, __int64 a2, int a3)
{
  __int64 v3; // r9
  __int64 result; // rax
  __int64 *v8; // rcx
  bool v9; // zf
  __int64 *v10; // rax

  v3 = CMIDIRecorder::m_sFreeList;
  if ( CMIDIRecorder::m_sFreeList )
  {
    CMIDIRecorder::m_sFreeList = *CMIDIRecorder::m_sFreeList;
  }
  else
  {
    result = (__int64)malloc(0x18u);
    v3 = result;
    if ( !result )
      return result;
    *(_QWORD *)(result + 8) = 0;
    *(_DWORD *)(result + 16) = 0;
  }
  *(_QWORD *)v3 = 0;
  v8 = *this;
  *(_QWORD *)(v3 + 8) = a2;
  *(_DWORD *)(v3 + 16) = a3;
  if ( v8 && (v9 = v8[1] == a2, v8[1] <= a2) )
  {
    while ( 1 )
    {
      if ( v9 && *((_DWORD *)v8 + 4) == a3 )
      {
        *(_QWORD *)v3 = CMIDIRecorder::m_sFreeList;
        result = 1;
        CMIDIRecorder::m_sFreeList = v3;
        return result;
      }
      v10 = (__int64 *)*v8;
      if ( !*v8 )
        break;
      if ( v10[1] > a2 )
      {
        *(_QWORD *)v3 = v10;
        break;
      }
      v8 = (__int64 *)*v8;
      v9 = v10[1] == a2;
    }
    *v8 = v3;
    return 1;
  }
  else
  {
    *(_QWORD *)v3 = *this;
    result = 1;
    *this = (__int64 *)v3;
  }
  return result;
}

```

## disassembly

```asm
0x18000a2c0  mov     [rsp+arg_0], rbx
0x18000a2c5  mov     [rsp+arg_8], rsi
0x18000a2ca  push    rdi
0x18000a2cb  sub     rsp, 20h
0x18000a2cf  mov     r9, cs:?m_sFreeList@CMIDIRecorder@@2VCMIDIDataList@@A; CMIDIDataList CMIDIRecorder::m_sFreeList
0x18000a2d6  mov     esi, r8d
0x18000a2d9  mov     rbx, rdx
0x18000a2dc  mov     rdi, rcx
0x18000a2df  test    r9, r9
0x18000a2e2  jz      short loc_18000A2F2
0x18000a2e4  mov     rax, [r9]
0x18000a2e7  mov     cs:?m_sFreeList@CMIDIRecorder@@2VCMIDIDataList@@A, rax; CMIDIDataList CMIDIRecorder::m_sFreeList
0x18000a2ee  xor     eax, eax
0x18000a2f0  jmp     short loc_18000A313
0x18000a2f2  mov     ecx, 18h; Size
0x18000a2f7  call    cs:__imp_malloc
0x18000a2fd  mov     r9, rax
0x18000a300  test    rax, rax
0x18000a303  jz      loc_18000A3AF
0x18000a309  xor     eax, eax
0x18000a30b  mov     [r9+8], rax
0x18000a30f  mov     [r9+10h], eax
0x18000a313  mov     [r9], rax
0x18000a316  mov     rcx, [rdi]
0x18000a319  mov     [r9+8], rbx
0x18000a31d  mov     [r9+10h], esi
0x18000a321  test    rcx, rcx
0x18000a324  jz      short loc_18000A32C
0x18000a326  cmp     [rcx+8], rbx
0x18000a32a  jle     short loc_18000A354
0x18000a32c  mov     rax, [rdi]
0x18000a32f  mov     [r9], rax
0x18000a332  mov     eax, 1
0x18000a337  mov     [rdi], r9
0x18000a33a  mov     rbx, [rsp+28h+arg_0]
0x18000a33f  mov     rsi, [rsp+28h+arg_8]
0x18000a344  add     rsp, 20h
0x18000a348  pop     rdi
0x18000a349  retn
0x18000a350  cmp     [rcx+8], rbx
0x18000a354  jnz     short loc_18000A35B
0x18000a356  cmp     [rcx+10h], esi
0x18000a359  jz      short loc_18000A36E
0x18000a35b  mov     rax, [rcx]
0x18000a35e  test    rax, rax
0x18000a361  jz      short loc_18000A397
0x18000a363  cmp     [rax+8], rbx
0x18000a367  jg      short loc_18000A394
0x18000a369  mov     rcx, rax
0x18000a36c  jmp     short loc_18000A350
0x18000a36e  mov     rax, cs:?m_sFreeList@CMIDIRecorder@@2VCMIDIDataList@@A; CMIDIDataList CMIDIRecorder::m_sFreeList
0x18000a375  mov     [r9], rax
0x18000a378  mov     eax, 1
0x18000a37d  mov     cs:?m_sFreeList@CMIDIRecorder@@2VCMIDIDataList@@A, r9; CMIDIDataList CMIDIRecorder::m_sFreeList
0x18000a384  mov     rbx, [rsp+28h+arg_0]
0x18000a389  mov     rsi, [rsp+28h+arg_8]
0x18000a38e  add     rsp, 20h
0x18000a392  pop     rdi
0x18000a393  retn
0x18000a394  mov     [r9], rax
0x18000a397  mov     [rcx], r9
0x18000a39a  mov     eax, 1
0x18000a39f  mov     rbx, [rsp+28h+arg_0]
0x18000a3a4  mov     rsi, [rsp+28h+arg_8]
0x18000a3a9  add     rsp, 20h
0x18000a3ad  pop     rdi
0x18000a3ae  retn
0x18000a3af  mov     rbx, [rsp+28h+arg_0]
0x18000a3b4  mov     rsi, [rsp+28h+arg_8]
0x18000a3b9  add     rsp, 20h
0x18000a3bd  pop     rdi
0x18000a3be  retn
```
