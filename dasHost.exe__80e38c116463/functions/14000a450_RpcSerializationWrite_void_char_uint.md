# RpcSerializationWrite(void *,char *,uint)

- ea: `0x14000a450`
- end: `0x14000a4ec`
- name: `?RpcSerializationWrite@@YAXPEAXPEADI@Z`
- size: `156`
- prototype: `void __fastcall(_DWORD *state, char *buffer, int size)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140008eec`
- `0x14000a450`
- `0x14001a83c`

## pseudocode

```c
void __fastcall RpcSerializationWrite(_DWORD *state, char *buffer, int size)
{
  size_t v3; // rdi

  v3 = (unsigned int)size;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      (int)buffer,
      size,
      18,
      &WPP_92038ab37ee4317b05ca4ff2fd992641_Traceguids);
  if ( state[2] - state[3] < (unsigned int)v3 )
  {
    state[7] = 1;
  }
  else
  {
    memcpy_0((void *)(*(_QWORD *)state + (unsigned int)state[3]), buffer, v3);
    state[3] += v3;
  }
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      (int)buffer,
      size,
      19,
      &WPP_92038ab37ee4317b05ca4ff2fd992641_Traceguids);
}

```

## disassembly

```asm
0x14000a450  push    rbx
0x14000a452  push    rbp
0x14000a453  push    rsi
0x14000a454  push    rdi
0x14000a455  push    r14
0x14000a457  sub     rsp, 30h
0x14000a45b  mov     edi, r8d
0x14000a45e  mov     rsi, rdx
0x14000a461  mov     rbx, rcx
0x14000a464  lea     rbp, WPP_RECORDER_INITIALIZED
0x14000a46b  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000a472  lea     r14, WPP_92038ab37ee4317b05ca4ff2fd992641_Traceguids
0x14000a479  jz      short loc_14000A496
0x14000a47b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a482  mov     r9d, 12h; int
0x14000a488  mov     [rsp+58h+MessageGuid], r14; MessageGuid
0x14000a48d  mov     rcx, [rcx+28h]; int
0x14000a491  call    WPP_RECORDER_SF_s
0x14000a496  mov     eax, [rbx+8]
0x14000a499  sub     eax, [rbx+0Ch]
0x14000a49c  cmp     eax, edi
0x14000a49e  jb      short loc_14000A4B6
0x14000a4a0  mov     ecx, [rbx+0Ch]
0x14000a4a3  mov     r8, rdi; Size
0x14000a4a6  add     rcx, [rbx]; void *
0x14000a4a9  mov     rdx, rsi; Src
0x14000a4ac  call    memcpy_0
0x14000a4b1  add     [rbx+0Ch], edi
0x14000a4b4  jmp     short loc_14000A4BD
0x14000a4b6  mov     dword ptr [rbx+1Ch], 1
0x14000a4bd  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000a4c4  jz      short loc_14000A4E1
0x14000a4c6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a4cd  mov     r9d, 13h; int
0x14000a4d3  mov     [rsp+58h+MessageGuid], r14; MessageGuid
0x14000a4d8  mov     rcx, [rcx+28h]; int
0x14000a4dc  call    WPP_RECORDER_SF_s
0x14000a4e1  add     rsp, 30h
0x14000a4e5  pop     r14
0x14000a4e7  pop     rdi
0x14000a4e8  pop     rsi
0x14000a4e9  pop     rbp
0x14000a4ea  pop     rbx
0x14000a4eb  retn
```
