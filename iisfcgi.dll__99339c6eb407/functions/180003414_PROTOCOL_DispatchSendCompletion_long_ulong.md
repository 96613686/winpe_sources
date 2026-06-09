# PROTOCOL::DispatchSendCompletion(long,ulong)

- ea: `0x180003414`
- end: `0x180003479`
- name: `?DispatchSendCompletion@PROTOCOL@@AEAAXJK@Z`
- size: `101`
- prototype: `void(PROTOCOL *__hidden this, int, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180002f60`
- `0x180003bc0`

## callees

- `0x180002128`
- `0x180003414`
- `0x180009128`

## pseudocode

```c
void __fastcall PROTOCOL::DispatchSendCompletion(PROTOCOL *this, signed int a2, int a3)
{
  int v4; // edi
  FCGI_BUFFER *v5; // rcx

  v4 = 0;
  v5 = (FCGI_BUFFER *)*((_QWORD *)this + 18);
  if ( v5 )
  {
    LOBYTE(v4) = *((_DWORD *)v5 + 7) == 2;
    FCGI_BUFFER::Free(v5);
    *((_QWORD *)this + 18) = 0;
  }
  if ( !a3 || v4 )
    *((_DWORD *)this + 11) = *((_DWORD *)this + 15) != 0 ? 4 : 6;
  SEND_QUEUE::SendCompletion(*((struct _RTL_CRITICAL_SECTION **)this + 22), a2);
}

```

## disassembly

```asm
0x180003414  push    rbx
0x180003416  push    rbp
0x180003417  push    rsi
0x180003418  push    rdi
0x180003419  sub     rsp, 28h
0x18000341d  mov     rbx, rcx
0x180003420  xor     edi, edi
0x180003422  mov     rcx, [rcx+90h]; this
0x180003429  mov     esi, r8d
0x18000342c  mov     ebp, edx
0x18000342e  test    rcx, rcx
0x180003431  jz      short loc_18000344B
0x180003433  cmp     dword ptr [rcx+1Ch], 2
0x180003437  setz    dil
0x18000343b  call    ?Free@FCGI_BUFFER@@QEAAJXZ; FCGI_BUFFER::Free(void)
0x180003440  mov     qword ptr [rbx+90h], 0
0x18000344b  test    esi, esi
0x18000344d  jz      short loc_180003453
0x18000344f  test    edi, edi
0x180003451  jz      short loc_180003463
0x180003453  mov     eax, [rbx+3Ch]
0x180003456  neg     eax
0x180003458  sbb     ecx, ecx
0x18000345a  and     ecx, 0FFFFFFFEh
0x18000345d  add     ecx, 6
0x180003460  mov     [rbx+2Ch], ecx
0x180003463  mov     rcx, [rbx+0B0h]; this
0x18000346a  mov     edx, ebp; int
0x18000346c  add     rsp, 28h
0x180003470  pop     rdi
0x180003471  pop     rsi
0x180003472  pop     rbp
0x180003473  pop     rbx
0x180003474  jmp     ?SendCompletion@SEND_QUEUE@@QEAAXJ@Z; SEND_QUEUE::SendCompletion(long)
```
