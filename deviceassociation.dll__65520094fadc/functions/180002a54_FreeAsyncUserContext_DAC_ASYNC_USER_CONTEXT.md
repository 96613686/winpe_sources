# FreeAsyncUserContext(_DAC_ASYNC_USER_CONTEXT *)

- ea: `0x180002a54`
- end: `0x180002b02`
- name: `?FreeAsyncUserContext@@YAXPEAU_DAC_ASYNC_USER_CONTEXT@@@Z`
- size: `174`
- prototype: `void __fastcall(struct _DAC_ASYNC_USER_CONTEXT *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180001d38`
- `0x180002840`

## callees

- `0x180002a54`
- `0x180002f10`
- `0x18000a9e0`
- `0x18000bbc2`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002abc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002abc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002aca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002aca`

## pseudocode

```c
void __fastcall FreeAsyncUserContext(struct _DAC_ASYNC_USER_CONTEXT *a1)
{
  void *v2; // rcx
  HANDLE ProcessHeap; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x20u, &WPP_bf3c54b8c13833bf7cdfafd9cf29bac0_Traceguids);
  if ( *((_DWORD *)a1 + 28) <= 1u )
  {
    v2 = (void *)*((_QWORD *)a1 + 18);
    if ( v2 )
      MIDL_user_free(v2);
  }
  memset_0(a1, 0, 0xA0u);
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, a1);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x21u, &WPP_bf3c54b8c13833bf7cdfafd9cf29bac0_Traceguids);
}

```

## disassembly

```asm
0x180002a54  mov     [rsp+arg_0], rbx
0x180002a59  push    rdi
0x180002a5a  sub     rsp, 20h
0x180002a5e  mov     rbx, rcx
0x180002a61  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a68  lea     rdi, WPP_GLOBAL_Control
0x180002a6f  cmp     rcx, rdi
0x180002a72  jz      short loc_180002A8F
0x180002a74  cmp     byte ptr [rcx+19h], 4
0x180002a78  jb      short loc_180002A8F
0x180002a7a  mov     rcx, [rcx+10h]
0x180002a7e  lea     r8, WPP_bf3c54b8c13833bf7cdfafd9cf29bac0_Traceguids
0x180002a85  mov     edx, 20h ; ' '
0x180002a8a  call    WPP_SF_s
0x180002a8f  mov     ecx, [rbx+70h]
0x180002a92  test    ecx, ecx
0x180002a94  jz      short loc_180002A9B
0x180002a96  cmp     ecx, 1
0x180002a99  jnz     short loc_180002AAC
0x180002a9b  mov     rcx, [rbx+90h]; void *
0x180002aa2  test    rcx, rcx
0x180002aa5  jz      short loc_180002AAC
0x180002aa7  call    MIDL_user_free
0x180002aac  xor     edx, edx; Val
0x180002aae  mov     r8d, 0A0h; Size
0x180002ab4  mov     rcx, rbx; void *
0x180002ab7  call    memset_0
0x180002abc  call    cs:__imp_GetProcessHeap
0x180002ac2  mov     r8, rbx; lpMem
0x180002ac5  xor     edx, edx; dwFlags
0x180002ac7  mov     rcx, rax; hHeap
0x180002aca  call    cs:__imp_HeapFree
0x180002ad0  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ad7  cmp     rcx, rdi
0x180002ada  jz      short loc_180002AF7
0x180002adc  cmp     byte ptr [rcx+19h], 4
0x180002ae0  jb      short loc_180002AF7
0x180002ae2  mov     rcx, [rcx+10h]
0x180002ae6  lea     r8, WPP_bf3c54b8c13833bf7cdfafd9cf29bac0_Traceguids
0x180002aed  mov     edx, 21h ; '!'
0x180002af2  call    WPP_SF_s
0x180002af7  mov     rbx, [rsp+28h+arg_0]
0x180002afc  add     rsp, 20h
0x180002b00  pop     rdi
0x180002b01  retn
```
