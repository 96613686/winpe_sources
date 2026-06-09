# LanSvcContextDeinit(void)

- ea: `0x18000b680`
- end: `0x18000b716`
- name: `?LanSvcContextDeinit@@YAKXZ`
- size: `150`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b9fc`

## callees

- `0x18000a9c0`
- `0x18000b680`
- `0x18000c230`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b6d1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b6d1`

## pseudocode

```c
__int64 LanSvcContextDeinit(void)
{
  struct _LIST_ENTRY *v0; // rcx

  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 84, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids);
    v0 = WPP_GLOBAL_Control;
  }
  if ( g_LanInternalCtxt )
  {
    DeleteCriticalSection(&CriticalSection);
    v0 = WPP_GLOBAL_Control;
    g_LanInternalCtxt = 0;
  }
  if ( v0 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v0[1].Blink) >= 4u && (BYTE4(v0[1].Blink) & 1) != 0 )
    WPP_SF_d(v0[1].Flink, 85, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x18000b680  push    rbx
0x18000b682  sub     rsp, 20h
0x18000b686  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b68d  lea     rbx, WPP_GLOBAL_Control
0x18000b694  cmp     rcx, rbx
0x18000b697  jz      short loc_18000B6C1
0x18000b699  cmp     byte ptr [rcx+19h], 4
0x18000b69d  jb      short loc_18000B6C1
0x18000b69f  test    byte ptr [rcx+1Ch], 1
0x18000b6a3  jz      short loc_18000B6C1
0x18000b6a5  mov     rcx, [rcx+10h]
0x18000b6a9  lea     r8, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids
0x18000b6b0  mov     edx, 54h ; 'T'
0x18000b6b5  call    WPP_SF_
0x18000b6ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b6c1  cmp     cs:?g_LanInternalCtxt@@3U_LAN_INTERNAL_CONTEXT@@A, 0; _LAN_INTERNAL_CONTEXT g_LanInternalCtxt
0x18000b6c8  jz      short loc_18000B6E5
0x18000b6ca  lea     rcx, CriticalSection; lpCriticalSection
0x18000b6d1  call    cs:__imp_DeleteCriticalSection
0x18000b6d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b6de  mov     cs:?g_LanInternalCtxt@@3U_LAN_INTERNAL_CONTEXT@@A, 0; _LAN_INTERNAL_CONTEXT g_LanInternalCtxt
0x18000b6e5  cmp     rcx, rbx
0x18000b6e8  jz      short loc_18000B70E
0x18000b6ea  cmp     byte ptr [rcx+19h], 4
0x18000b6ee  jb      short loc_18000B70E
0x18000b6f0  test    byte ptr [rcx+1Ch], 1
0x18000b6f4  jz      short loc_18000B70E
0x18000b6f6  mov     rcx, [rcx+10h]
0x18000b6fa  lea     r8, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids
0x18000b701  mov     edx, 55h ; 'U'
0x18000b706  xor     r9d, r9d
0x18000b709  call    WPP_SF_d
0x18000b70e  xor     eax, eax
0x18000b710  add     rsp, 20h
0x18000b714  pop     rbx
0x18000b715  retn
```
