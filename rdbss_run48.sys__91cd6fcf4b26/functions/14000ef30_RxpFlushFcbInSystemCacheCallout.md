# RxpFlushFcbInSystemCacheCallout

- ea: `0x14000ef30`
- end: `0x14000efab`
- name: `RxpFlushFcbInSystemCacheCallout`
- size: `123`
- prototype: `EXPAND_STACK_CALLOUT`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000ef30`
- `0x140017220`

## import_xrefs

- `ntoskrnl!CcFlushCache` at `0x14000ef64`
- `ntoskrnl!CcFlushCache` at `0x14000ef64`

## pseudocode

```c
void __fastcall RxpFlushFcbInSystemCacheCallout(char *Parameter)
{
  __int64 v2; // rdi
  LARGE_INTEGER *v3; // rsi
  ULONG v4; // ebp
  __int64 v5; // rcx

  v2 = *(_QWORD *)Parameter;
  v3 = (LARGE_INTEGER *)*((_QWORD *)Parameter + 1);
  v4 = *((_DWORD *)Parameter + 4);
  if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
    McTemplateK0p_EtwWriteTransfer(Parameter, &CcFlushRequest, 0, v2);
  CcFlushCache((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v2 + 304) + 8LL), v3, v4, (PIO_STATUS_BLOCK)(Parameter + 24));
  if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
    McTemplateK0p_EtwWriteTransfer(v5, &CcFlushCompletion, 0, v2);
}

```

## disassembly

```asm
0x14000ef30  push    rbx
0x14000ef32  push    rbp
0x14000ef33  push    rsi
0x14000ef34  push    rdi
0x14000ef35  sub     rsp, 28h
0x14000ef39  test    byte ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next+4, 8
0x14000ef40  mov     rbx, rcx
0x14000ef43  mov     rdi, [rcx]
0x14000ef46  mov     rsi, [rcx+8]
0x14000ef4a  mov     ebp, [rcx+10h]
0x14000ef4d  jnz     short loc_14000EF83
0x14000ef4f  mov     rcx, [rdi+130h]
0x14000ef56  lea     r9, [rbx+18h]; IoStatus
0x14000ef5a  add     rcx, 8; SectionObjectPointer
0x14000ef5e  mov     r8d, ebp; Length
0x14000ef61  mov     rdx, rsi; FileOffset
0x14000ef64  call    cs:__imp_CcFlushCache
0x14000ef6b  nop     dword ptr [rax+rax+00h]
0x14000ef70  test    byte ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next+4, 8
0x14000ef77  jnz     short loc_14000EF97
0x14000ef79  add     rsp, 28h
0x14000ef7d  pop     rdi
0x14000ef7e  pop     rsi
0x14000ef7f  pop     rbp
0x14000ef80  pop     rbx
0x14000ef81  retn
0x14000ef83  mov     r9, rdi
0x14000ef86  lea     rdx, CcFlushRequest
0x14000ef8d  xor     r8d, r8d
0x14000ef90  call    McTemplateK0p_EtwWriteTransfer
0x14000ef95  jmp     short loc_14000EF4F
0x14000ef97  mov     r9, rdi
0x14000ef9a  lea     rdx, CcFlushCompletion
0x14000efa1  xor     r8d, r8d
0x14000efa4  call    McTemplateK0p_EtwWriteTransfer
0x14000efa9  jmp     short loc_14000EF79
```
