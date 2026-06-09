# CHwCommandBuffer::RecoverAllocationListState(void)

- ea: `0x140027bcc`
- end: `0x140027c42`
- name: `?RecoverAllocationListState@CHwCommandBuffer@@IEAAXXZ`
- size: `118`
- prototype: `void __fastcall(CHwCommandBuffer *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001cce4`
- `0x14001fa08`
- `0x140020e48`
- `0x14002ea64`

## callees

- `0x140027bcc`

## import_xrefs

- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140027bfc`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140027bfc`
- `watchdog!WdLogSingleEntry0` at `0x140027be6`
- `watchdog!WdLogSingleEntry0` at `0x140027be6`

## pseudocode

```c
void __fastcall CHwCommandBuffer::RecoverAllocationListState(CHwCommandBuffer *this)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  _QWORD *v4; // rax
  __int64 v5; // rcx

  if ( *((_DWORD *)this + 525) > 0x100u )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 90;
    v4 = (_QWORD *)WdLogNewEntry5_WdAssertion(v3, v2);
    v5 = (unsigned int)dword_14003E570;
    v4[3] = gCddImageInfo;
    v4[4] = v5;
    v4[5] = 215857758;
    WdLogGlobalForLineNumber = 90;
  }
  *((_DWORD *)this + 524) = *((_DWORD *)this + 525);
}

```

## disassembly

```asm
0x140027bcc  push    rbx
0x140027bce  sub     rsp, 20h
0x140027bd2  cmp     dword ptr [rcx+834h], 100h
0x140027bdc  mov     rbx, rcx
0x140027bdf  jbe     short loc_140027C2F
0x140027be1  mov     ecx, 1
0x140027be6  call    cs:__imp_WdLogSingleEntry0
0x140027bed  nop     dword ptr [rax+rax+00h]
0x140027bf2  mov     cs:WdLogGlobalForLineNumber, 5Ah ; 'Z'
0x140027bfc  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x140027c03  nop     dword ptr [rax+rax+00h]
0x140027c08  mov     rdx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140027c0f  mov     ecx, cs:dword_14003E570
0x140027c15  mov     [rax+18h], rdx
0x140027c19  mov     [rax+20h], rcx
0x140027c1d  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140027c25  mov     cs:WdLogGlobalForLineNumber, 5Ah ; 'Z'
0x140027c2f  mov     eax, [rbx+834h]
0x140027c35  mov     [rbx+830h], eax
0x140027c3b  add     rsp, 20h
0x140027c3f  pop     rbx
0x140027c40  retn
```
