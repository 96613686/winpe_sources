# CHwCommandBuffer::InsertToAllocationList(uint,uchar)

- ea: `0x14001d0a4`
- end: `0x14001d1a8`
- name: `?InsertToAllocationList@CHwCommandBuffer@@IEAAIIE@Z`
- size: `260`
- prototype: `unsigned int __fastcall(CHwCommandBuffer *__hidden this, unsigned int, unsigned __int8)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001cce4`
- `0x14001fa08`
- `0x140020e48`
- `0x14002ea64`

## callees

- `0x14001d0a4`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x14001d141`
- `ntoskrnl!DbgPrint` at `0x14001d141`
- `ntoskrnl!KdDebuggerEnabled` at `0x14001d12e`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001d168`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001d168`
- `watchdog!WdLogSingleEntry0` at `0x14001d152`
- `watchdog!WdLogSingleEntry0` at `0x14001d152`

## string_xrefs

- `0x14001d13a`: `Attempt to insert NULL allocation to the allocation list`

## pseudocode

```c
__int64 __fastcall CHwCommandBuffer::InsertToAllocationList(CHwCommandBuffer *this, int a2, char a3)
{
  __int64 i; // rdx
  _QWORD *v8; // rax

  if ( !a2 && (*(_DWORD *)(*(_QWORD *)this + 2744LL) & 0x100) != 0 && (_BYTE)KdDebuggerEnabled )
  {
    DbgPrint("Attempt to insert NULL allocation to the allocation list");
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 28;
    v8 = (_QWORD *)WdLogNewEntry5_WdError();
    v8[3] = gCddImageInfo;
    v8[4] = (unsigned int)dword_14003E570;
    v8[5] = 215857758;
    WdLogGlobalForLineNumber = 28;
    __debugbreak();
  }
  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 524); i = (unsigned int)(i + 1) )
  {
    if ( *((_DWORD *)this + 2 * i + 12) == a2 )
    {
      if ( a3 )
        *((_DWORD *)this + 2 * i + 13) |= 1u;
      return (unsigned int)i;
    }
  }
  if ( (_DWORD)i != 256 )
  {
    *((_QWORD *)this + i + 6) = 0;
    *((_DWORD *)this + 2 * i + 12) = a2;
    *((_DWORD *)this + 2 * i + 13) = a3 != 0;
    *((_DWORD *)this + 524) = i + 1;
    return (unsigned int)i;
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x14001d0a4  mov     [rsp+arg_0], rbx
0x14001d0a9  mov     [rsp+arg_8], rsi
0x14001d0ae  push    rdi
0x14001d0af  sub     rsp, 20h
0x14001d0b3  mov     sil, r8b
0x14001d0b6  mov     edi, edx
0x14001d0b8  mov     rbx, rcx
0x14001d0bb  test    edx, edx
0x14001d0bd  jz      short loc_14001D11F
0x14001d0bf  mov     ecx, [rbx+830h]
0x14001d0c5  xor     edx, edx
0x14001d0c7  cmp     edx, ecx
0x14001d0c9  jnb     short loc_14001D0F2
0x14001d0cb  cmp     [rbx+rdx*8+30h], edi
0x14001d0cf  jnz     loc_14001D1A1
0x14001d0d5  test    sil, sil
0x14001d0d8  jz      short loc_14001D0DF
0x14001d0da  or      dword ptr [rbx+rdx*8+34h], 1
0x14001d0df  mov     eax, edx
0x14001d0e1  mov     rbx, [rsp+28h+arg_0]
0x14001d0e6  mov     rsi, [rsp+28h+arg_8]
0x14001d0eb  add     rsp, 20h
0x14001d0ef  pop     rdi
0x14001d0f0  retn
0x14001d0f2  cmp     edx, 100h
0x14001d0f8  jz      short loc_14001D11A
0x14001d0fa  xor     eax, eax
0x14001d0fc  mov     [rbx+rdx*8+30h], rax
0x14001d101  test    sil, sil
0x14001d104  mov     [rbx+rdx*8+30h], edi
0x14001d108  setnz   al
0x14001d10b  mov     [rbx+rdx*8+34h], eax
0x14001d10f  lea     eax, [rdx+1]
0x14001d112  mov     [rbx+830h], eax
0x14001d118  jmp     short loc_14001D0DF
0x14001d11a  or      eax, 0FFFFFFFFh
0x14001d11d  jmp     short loc_14001D0E1
0x14001d11f  mov     rax, [rcx]
0x14001d122  test    dword ptr [rax+0AB8h], 100h
0x14001d12c  jz      short loc_14001D0BF
0x14001d12e  mov     rax, cs:KdDebuggerEnabled
0x14001d135  cmp     byte ptr [rax], 0
0x14001d138  jz      short loc_14001D0BF
0x14001d13a  lea     rcx, aAttemptToInser; "Attempt to insert NULL allocation to th"...
0x14001d141  call    cs:__imp_DbgPrint
0x14001d148  nop     dword ptr [rax+rax+00h]
0x14001d14d  mov     ecx, 2
0x14001d152  call    cs:__imp_WdLogSingleEntry0
0x14001d159  nop     dword ptr [rax+rax+00h]
0x14001d15e  mov     cs:WdLogGlobalForLineNumber, 1Ch
0x14001d168  call    cs:__imp_WdLogNewEntry5_WdError
0x14001d16f  nop     dword ptr [rax+rax+00h]
0x14001d174  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001d17b  mov     [rax+18h], rcx
0x14001d17f  mov     ecx, cs:dword_14003E570
0x14001d185  mov     [rax+20h], rcx
0x14001d189  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14001d191  mov     cs:WdLogGlobalForLineNumber, 1Ch
0x14001d19b  int     3; Trap to Debugger
0x14001d19c  jmp     loc_14001D0BF
0x14001d1a1  inc     edx
0x14001d1a3  jmp     loc_14001D0C7
```
