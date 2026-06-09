# WorkItems::Close(void)

- ea: `0x18001a6d4`
- end: `0x18001a769`
- name: `?Close@WorkItems@@QEAAXXZ`
- size: `149`
- prototype: `void __fastcall(PTP_CLEANUP_GROUP *this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18001a5ac`
- `0x18001a66c`
- `0x18001a8f0`

## callees

- `0x18000c308`
- `0x18001a6d4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18001a721`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18001a721`

## pseudocode

```c
void __fastcall WorkItems::Close(PTP_CLEANUP_GROUP *this)
{
  if ( *this )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_f0d96dd7853034934bfbcbbd7dfb6684_Traceguids, this);
    }
    CloseThreadpoolCleanupGroup(*this);
    *this = 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_f0d96dd7853034934bfbcbbd7dfb6684_Traceguids, this);
  }
}

```

## disassembly

```asm
0x18001a6d4  mov     [rsp+arg_0], rbx
0x18001a6d9  push    rdi
0x18001a6da  sub     rsp, 20h
0x18001a6de  cmp     qword ptr [rcx], 0
0x18001a6e2  lea     rdi, WPP_GLOBAL_Control
0x18001a6e9  mov     rbx, rcx
0x18001a6ec  jz      short loc_18001A72E
0x18001a6ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a6f5  cmp     rcx, rdi
0x18001a6f8  jz      short loc_18001A71E
0x18001a6fa  cmp     byte ptr [rcx+19h], 3
0x18001a6fe  jb      short loc_18001A71E
0x18001a700  test    byte ptr [rcx+1Ch], 1
0x18001a704  jz      short loc_18001A71E
0x18001a706  mov     rcx, [rcx+10h]
0x18001a70a  lea     r8, WPP_f0d96dd7853034934bfbcbbd7dfb6684_Traceguids
0x18001a711  mov     edx, 0Eh
0x18001a716  mov     r9, rbx
0x18001a719  call    WPP_SF_q
0x18001a71e  mov     rcx, [rbx]; ptpcg
0x18001a721  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18001a727  mov     qword ptr [rbx], 0
0x18001a72e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a735  cmp     rcx, rdi
0x18001a738  jz      short loc_18001A75E
0x18001a73a  cmp     byte ptr [rcx+19h], 3
0x18001a73e  jb      short loc_18001A75E
0x18001a740  test    byte ptr [rcx+1Ch], 1
0x18001a744  jz      short loc_18001A75E
0x18001a746  mov     rcx, [rcx+10h]
0x18001a74a  lea     r8, WPP_f0d96dd7853034934bfbcbbd7dfb6684_Traceguids
0x18001a751  mov     edx, 0Fh
0x18001a756  mov     r9, rbx
0x18001a759  call    WPP_SF_q
0x18001a75e  mov     rbx, [rsp+28h+arg_0]
0x18001a763  add     rsp, 20h
0x18001a767  pop     rdi
0x18001a768  retn
```
