# QuicConnProcessRouteCompletion

- ea: `0x14002b5c4`
- end: `0x14002b6ec`
- name: `QuicConnProcessRouteCompletion`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140014d80`

## callees

- `0x14000d638`
- `0x140016210`
- `0x14001c638`
- `0x14002b5c4`
- `0x14003c8e0`
- `0x14003ec10`
- `0x140048c38`
- `0x140048c78`
- `0x140048d98`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14002b647`
- `ntoskrnl!_snprintf_s` at `0x14002b647`

## string_xrefs

- `0x14002b633`: `Route resolution failed on Path[%hhu]. Switching paths...`

## pseudocode

```c
char __fastcall QuicConnProcessRouteCompletion(__int64 a1, __int64 a2, unsigned __int8 a3)
{
  int v3; // edi
  __int64 PathByID; // rax
  __int64 v6; // rcx
  char v7; // r9
  unsigned __int8 *v8; // rdi
  __int64 v9; // rcx
  unsigned __int8 v11[16]; // [rsp+30h] [rbp-A8h] BYREF
  char DstBuf[128]; // [rsp+40h] [rbp-98h] BYREF

  v3 = a3;
  LOBYTE(a2) = a3;
  v11[0] = 0;
  PathByID = QuicConnGetPathByID(a1, a2, v11);
  if ( PathByID )
  {
    if ( v7 )
    {
      v8 = (unsigned __int8 *)(v6 + 3416);
    }
    else
    {
      if ( (*(_BYTE *)(PathByID + 1) & 2) == 0 || *(_BYTE *)(v6 + 275) <= 1u )
      {
        LOBYTE(PathByID) = QuicPathRemove(v6, v11[0]);
        goto LABEL_12;
      }
      if ( byte_14005C48B < 0 )
      {
        _snprintf_s(
          DstBuf,
          0x80u,
          0xFFFFFFFFFFFFFFFFuLL,
          "Route resolution failed on Path[%hhu]. Switching paths...",
          v3);
        McTemplateU0ps_EtwWriteTransfer(v9, QuicConnLogInfo, a1, DstBuf);
      }
      QuicPathSetActive(a1, a1 + 560);
      QuicPathRemove(a1, 1u);
      v8 = (unsigned __int8 *)(a1 + 3416);
    }
    LOBYTE(PathByID) = QuicSendFlush(v8);
    if ( !(_BYTE)PathByID )
      LOBYTE(PathByID) = QuicSendQueueFlush(v8, 13);
  }
LABEL_12:
  if ( !*(_BYTE *)(a1 + 275) )
    LOBYTE(PathByID) = QuicConnCloseLocally(a1, 19, -1073741251);
  return PathByID;
}

```

## disassembly

```asm
0x14002b5c4  mov     [rsp+arg_8], rbx
0x14002b5c9  push    rdi
0x14002b5ca  sub     rsp, 0D0h
0x14002b5d1  mov     rax, cs:__security_cookie
0x14002b5d8  xor     rax, rsp
0x14002b5db  mov     [rsp+0D8h+var_18], rax
0x14002b5e3  movzx   edi, r8b
0x14002b5e7  mov     rbx, rcx
0x14002b5ea  mov     dl, dil
0x14002b5ed  mov     [rsp+0D8h+var_A8], 0
0x14002b5f2  lea     r8, [rsp+0D8h+var_A8]
0x14002b5f7  call    QuicConnGetPathByID
0x14002b5fc  test    rax, rax
0x14002b5ff  jz      loc_14002B6AB
0x14002b605  test    r9b, r9b
0x14002b608  jz      short loc_14002B613
0x14002b60a  lea     rdi, [rcx+0D58h]
0x14002b611  jmp     short loc_14002B687
0x14002b613  test    byte ptr [rax+1], 2
0x14002b617  jz      loc_14002B6A2
0x14002b61d  cmp     byte ptr [rcx+113h], 1
0x14002b624  jbe     short loc_14002B6A2
0x14002b626  mov     edx, 80h; SizeInBytes
0x14002b62b  test    cs:byte_14005C48B, dl
0x14002b631  jz      short loc_14002B667
0x14002b633  lea     r9, aRouteResolutio; "Route resolution failed on Path[%hhu]. "...
0x14002b63a  mov     [rsp+0D8h+var_B8], edi
0x14002b63e  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14002b642  lea     rcx, [rsp+0D8h+DstBuf]; DstBuf
0x14002b647  call    cs:__imp__snprintf_s
0x14002b64e  nop     dword ptr [rax+rax+00h]
0x14002b653  lea     r9, [rsp+0D8h+DstBuf]
0x14002b658  mov     r8, rbx
0x14002b65b  lea     rdx, QuicConnLogInfo
0x14002b662  call    McTemplateU0ps_EtwWriteTransfer
0x14002b667  lea     rdx, [rbx+230h]
0x14002b66e  mov     rcx, rbx
0x14002b671  call    QuicPathSetActive
0x14002b676  mov     dl, 1
0x14002b678  mov     rcx, rbx
0x14002b67b  call    QuicPathRemove
0x14002b680  lea     rdi, [rbx+0D58h]
0x14002b687  mov     rcx, rdi
0x14002b68a  call    QuicSendFlush
0x14002b68f  test    al, al
0x14002b691  jnz     short loc_14002B6AB
0x14002b693  mov     edx, 0Dh
0x14002b698  mov     rcx, rdi
0x14002b69b  call    QuicSendQueueFlush
0x14002b6a0  jmp     short loc_14002B6AB
0x14002b6a2  mov     dl, [rsp+0D8h+var_A8]
0x14002b6a6  call    QuicPathRemove
0x14002b6ab  cmp     byte ptr [rbx+113h], 0
0x14002b6b2  jnz     short loc_14002B6CA
0x14002b6b4  xor     r9d, r9d
0x14002b6b7  mov     r8, 0FFFFFFFFC000023Dh
0x14002b6be  mov     rcx, rbx
0x14002b6c1  lea     edx, [r9+13h]
0x14002b6c5  call    QuicConnCloseLocally
0x14002b6ca  mov     rcx, [rsp+0D8h+var_18]
0x14002b6d2  xor     rcx, rsp; StackCookie
0x14002b6d5  call    __security_check_cookie
0x14002b6da  mov     rbx, [rsp+0D8h+arg_8]
0x14002b6e2  add     rsp, 0D0h
0x14002b6e9  pop     rdi
0x14002b6ea  retn
```
