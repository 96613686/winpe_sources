# RxpPurgeFcbInSystemCacheCallout

- ea: `0x140010140`
- end: `0x140010204`
- name: `RxpPurgeFcbInSystemCacheCallout`
- size: `196`
- prototype: `EXPAND_STACK_CALLOUT`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140010140`
- `0x140017220`

## import_xrefs

- `ntoskrnl!MmFlushImageSection` at `0x1400101ba`
- `ntoskrnl!MmFlushImageSection` at `0x1400101ba`
- `ntoskrnl!CcPurgeCacheSection` at `0x14001017a`
- `ntoskrnl!CcPurgeCacheSection` at `0x14001017a`

## pseudocode

```c
void __fastcall RxpPurgeFcbInSystemCacheCallout(_QWORD *Parameter)
{
  __int64 v2; // rsi
  LARGE_INTEGER *v3; // rdi
  ULONG v4; // ebp
  ULONG v5; // r14d
  __int64 v6; // rcx
  BOOLEAN v7; // di

  v2 = *Parameter;
  v3 = (LARGE_INTEGER *)Parameter[1];
  v4 = *((_DWORD *)Parameter + 4);
  v5 = *((unsigned __int8 *)Parameter + 20);
  if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
    McTemplateK0p_EtwWriteTransfer(Parameter, CcPurgeRequest, 0, *Parameter);
  v7 = CcPurgeCacheSection((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v2 + 304) + 8LL), v3, v4, v5);
  if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
    McTemplateK0p_EtwWriteTransfer(v6, CcPurgeCompletion, 0, v2);
  if ( v7 )
  {
    *((_DWORD *)Parameter + 6) = 0;
  }
  else
  {
    MmFlushImageSection((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v2 + 304) + 8LL), MmFlushForWrite);
    *((_DWORD *)Parameter + 6) = -1073740747;
  }
}

```

## disassembly

```asm
0x140010140  push    rbx
0x140010142  push    rbp
0x140010143  push    rsi
0x140010144  push    rdi
0x140010145  push    r14
0x140010147  sub     rsp, 20h
0x14001014b  test    byte ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next+4, 8
0x140010152  mov     rbx, rcx
0x140010155  mov     rsi, [rcx]
0x140010158  mov     rdi, [rcx+8]
0x14001015c  mov     ebp, [rcx+10h]
0x14001015f  movzx   r14d, byte ptr [rcx+14h]
0x140010164  jnz     short loc_1400101D9
0x140010166  mov     rcx, [rsi+130h]
0x14001016d  mov     r9d, r14d; Flags
0x140010170  add     rcx, 8; SectionObjectPointer
0x140010174  mov     r8d, ebp; Length
0x140010177  mov     rdx, rdi; FileOffset
0x14001017a  call    cs:__imp_CcPurgeCacheSection
0x140010181  nop     dword ptr [rax+rax+00h]
0x140010186  test    byte ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next+4, 8
0x14001018d  movzx   edi, al
0x140010190  jnz     short loc_1400101F0
0x140010192  test    dil, dil
0x140010195  jz      short loc_1400101AA
0x140010197  mov     dword ptr [rbx+18h], 0
0x14001019e  add     rsp, 20h
0x1400101a2  pop     r14
0x1400101a4  pop     rdi
0x1400101a5  pop     rsi
0x1400101a6  pop     rbp
0x1400101a7  pop     rbx
0x1400101a8  retn
0x1400101aa  mov     rcx, [rsi+130h]
0x1400101b1  mov     edx, 1; FlushType
0x1400101b6  add     rcx, 8; SectionObjectPointer
0x1400101ba  call    cs:__imp_MmFlushImageSection
0x1400101c1  nop     dword ptr [rax+rax+00h]
0x1400101c6  mov     dword ptr [rbx+18h], 0C0000435h
0x1400101cd  add     rsp, 20h
0x1400101d1  pop     r14
0x1400101d3  pop     rdi
0x1400101d4  pop     rsi
0x1400101d5  pop     rbp
0x1400101d6  pop     rbx
0x1400101d7  retn
0x1400101d9  mov     r9, rsi
0x1400101dc  lea     rdx, CcPurgeRequest
0x1400101e3  xor     r8d, r8d
0x1400101e6  call    McTemplateK0p_EtwWriteTransfer
0x1400101eb  jmp     loc_140010166
0x1400101f0  mov     r9, rsi
0x1400101f3  lea     rdx, CcPurgeCompletion
0x1400101fa  xor     r8d, r8d
0x1400101fd  call    McTemplateK0p_EtwWriteTransfer
0x140010202  jmp     short loc_140010192
```
