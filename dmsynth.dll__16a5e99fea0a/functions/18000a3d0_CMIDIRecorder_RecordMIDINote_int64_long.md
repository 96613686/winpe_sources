# CMIDIRecorder::RecordMIDINote(__int64,long)

- ea: `0x18000a3d0`
- end: `0x18000a494`
- name: `?RecordMIDINote@CMIDIRecorder@@QEAAH_JJ@Z`
- size: `196`
- prototype: `__int64 __fastcall(CMIDIRecorder *__hidden this, __int64, int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004fc0`
- `0x180005630`

## callees

- `0x18000a3d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000a407`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000a407`

## pseudocode

```c
__int64 __fastcall CMIDIRecorder::RecordMIDINote(__int64 **this, __int64 a2, int a3)
{
  __int64 v3; // r9
  __int64 result; // rax
  __int64 *v8; // rcx
  __int64 *v9; // rax

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
  if ( v8 && v8[1] <= a2 )
  {
    while ( 1 )
    {
      v9 = (__int64 *)*v8;
      if ( !*v8 )
        break;
      if ( v9[1] > a2 )
      {
        *(_QWORD *)v3 = v9;
        break;
      }
      v8 = (__int64 *)*v8;
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
0x18000a3d0  mov     [rsp+arg_0], rbx
0x18000a3d5  mov     [rsp+arg_8], rsi
0x18000a3da  push    rdi
0x18000a3db  sub     rsp, 20h
0x18000a3df  mov     r9, cs:?m_sFreeList@CMIDIRecorder@@2VCMIDIDataList@@A; CMIDIDataList CMIDIRecorder::m_sFreeList
0x18000a3e6  mov     esi, r8d
0x18000a3e9  mov     rdi, rdx
0x18000a3ec  mov     rbx, rcx
0x18000a3ef  test    r9, r9
0x18000a3f2  jz      short loc_18000A402
0x18000a3f4  mov     rax, [r9]
0x18000a3f7  mov     cs:?m_sFreeList@CMIDIRecorder@@2VCMIDIDataList@@A, rax; CMIDIDataList CMIDIRecorder::m_sFreeList
0x18000a3fe  xor     eax, eax
0x18000a400  jmp     short loc_18000A41F
0x18000a402  mov     ecx, 18h; Size
0x18000a407  call    cs:__imp_malloc
0x18000a40d  mov     r9, rax
0x18000a410  test    rax, rax
0x18000a413  jz      short loc_18000A484
0x18000a415  xor     eax, eax
0x18000a417  mov     [r9+8], rax
0x18000a41b  mov     [r9+10h], eax
0x18000a41f  mov     [r9], rax
0x18000a422  mov     rcx, [rbx]
0x18000a425  mov     [r9+8], rdi
0x18000a429  mov     [r9+10h], esi
0x18000a42d  test    rcx, rcx
0x18000a430  jz      short loc_18000A438
0x18000a432  cmp     [rcx+8], rdi
0x18000a436  jle     short loc_18000A456
0x18000a438  mov     rax, [rbx]
0x18000a43b  mov     [r9], rax
0x18000a43e  mov     eax, 1
0x18000a443  mov     [rbx], r9
0x18000a446  mov     rbx, [rsp+28h+arg_0]
0x18000a44b  mov     rsi, [rsp+28h+arg_8]
0x18000a450  add     rsp, 20h
0x18000a454  pop     rdi
0x18000a455  retn
0x18000a456  mov     rax, [rcx]
0x18000a459  test    rax, rax
0x18000a45c  jz      short loc_18000A46C
0x18000a45e  cmp     [rax+8], rdi
0x18000a462  jg      short loc_18000A469
0x18000a464  mov     rcx, rax
0x18000a467  jmp     short loc_18000A456
0x18000a469  mov     [r9], rax
0x18000a46c  mov     [rcx], r9
0x18000a46f  mov     eax, 1
0x18000a474  mov     rbx, [rsp+28h+arg_0]
0x18000a479  mov     rsi, [rsp+28h+arg_8]
0x18000a47e  add     rsp, 20h
0x18000a482  pop     rdi
0x18000a483  retn
0x18000a484  mov     rbx, [rsp+28h+arg_0]
0x18000a489  mov     rsi, [rsp+28h+arg_8]
0x18000a48e  add     rsp, 20h
0x18000a492  pop     rdi
0x18000a493  retn
```
