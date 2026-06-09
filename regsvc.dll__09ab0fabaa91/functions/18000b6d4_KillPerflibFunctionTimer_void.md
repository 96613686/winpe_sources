# KillPerflibFunctionTimer(void *)

- ea: `0x18000b6d4`
- end: `0x18000b7c1`
- name: `?KillPerflibFunctionTimer@@YAKPEAX@Z`
- size: `237`
- prototype: `__int64 __fastcall(_DWORD *Block)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x180011d10`
- `0x1800136b0`
- `0x18001403c`

## callees

- `0x180008050`
- `0x18000ac80`
- `0x18000b6d4`

## import_xrefs

- `ntdll!NtWaitForSingleObject` at `0x18000b70e`
- `ntdll!NtWaitForSingleObject` at `0x18000b70e`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000b79d`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000b79d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b786`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b786`

## pseudocode

```c
__int64 __fastcall KillPerflibFunctionTimer(_DWORD *Block)
{
  _QWORD *v3; // rcx
  union _LARGE_INTEGER Timeout; // [rsp+40h] [rbp+8h] BYREF

  if ( !Handle )
    return 21;
  if ( !Block )
    return 6;
  Timeout.QuadPart = -4000000;
  if ( NtWaitForSingleObject(Handle, 0, &Timeout) )
    return 1460;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_b75a7a59dad53afbcb57d559c4580c05_Traceguids, Block, Block[6]);
  v3 = ::Block;
  if ( Block == ::Block )
  {
    ::Block = *(void **)Block;
LABEL_15:
    ReleaseMutex(Handle);
    if ( !::Block )
      ResetEvent(Object[0]);
    operator delete(Block);
    return 0;
  }
  else
  {
    while ( v3 )
    {
      if ( (_DWORD *)*v3 == Block )
      {
        *v3 = *(_QWORD *)Block;
        goto LABEL_15;
      }
      v3 = (_QWORD *)*v3;
    }
    return 1168;
  }
}

```

## disassembly

```asm
0x18000b6d4  push    rbx
0x18000b6d6  sub     rsp, 30h
0x18000b6da  mov     rbx, rcx
0x18000b6dd  mov     rcx, cs:Handle; Handle
0x18000b6e4  test    rcx, rcx
0x18000b6e7  jnz     short loc_18000B6F1
0x18000b6e9  lea     eax, [rcx+15h]
0x18000b6ec  jmp     loc_18000B7BB
0x18000b6f1  test    rbx, rbx
0x18000b6f4  jnz     short loc_18000B6FE
0x18000b6f6  lea     eax, [rbx+6]
0x18000b6f9  jmp     loc_18000B7BB
0x18000b6fe  lea     r8, [rsp+38h+Timeout]; Timeout
0x18000b703  mov     qword ptr [rsp+38h+Timeout], 0FFFFFFFFFFC2F700h
0x18000b70c  xor     edx, edx; Alertable
0x18000b70e  call    cs:__imp_NtWaitForSingleObject
0x18000b714  test    eax, eax
0x18000b716  jnz     loc_18000B7B6
0x18000b71c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b723  test    dword ptr [rcx+1Ch], 800h
0x18000b72a  jz      short loc_18000B74F
0x18000b72c  cmp     byte ptr [rcx+19h], 4
0x18000b730  jb      short loc_18000B74F
0x18000b732  mov     rcx, [rcx+10h]
0x18000b736  lea     edx, [rax+17h]
0x18000b739  mov     eax, [rbx+18h]
0x18000b73c  lea     r8, WPP_b75a7a59dad53afbcb57d559c4580c05_Traceguids
0x18000b743  mov     r9, rbx
0x18000b746  mov     [rsp+38h+var_18], eax
0x18000b74a  call    WPP_SF_qd
0x18000b74f  mov     rcx, cs:Block
0x18000b756  cmp     rbx, rcx
0x18000b759  jnz     short loc_18000B767
0x18000b75b  mov     rax, [rbx]
0x18000b75e  mov     cs:Block, rax
0x18000b765  jmp     short loc_18000B77F
0x18000b767  test    rcx, rcx
0x18000b76a  jz      short loc_18000B7AF
0x18000b76c  mov     rax, [rcx]
0x18000b76f  cmp     rax, rbx
0x18000b772  jz      short loc_18000B779
0x18000b774  mov     rcx, rax
0x18000b777  jmp     short loc_18000B767
0x18000b779  mov     rax, [rbx]
0x18000b77c  mov     [rcx], rax
0x18000b77f  mov     rcx, cs:Handle; hMutex
0x18000b786  call    cs:__imp_ReleaseMutex
0x18000b78c  cmp     cs:Block, 0
0x18000b794  jnz     short loc_18000B7A3
0x18000b796  mov     rcx, cs:Object; hEvent
0x18000b79d  call    cs:__imp_ResetEvent
0x18000b7a3  mov     rcx, rbx; Block
0x18000b7a6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b7ab  xor     eax, eax
0x18000b7ad  jmp     short loc_18000B7BB
0x18000b7af  mov     eax, 490h
0x18000b7b4  jmp     short loc_18000B7BB
0x18000b7b6  mov     eax, 5B4h
0x18000b7bb  add     rsp, 30h
0x18000b7bf  pop     rbx
0x18000b7c0  retn
```
