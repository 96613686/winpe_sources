# basessp::BaseSSP::~BaseSSP(void)

- ea: `0x180043460`
- end: `0x1800434d4`
- name: `??1BaseSSP@basessp@@QEAA@XZ`
- size: `116`
- prototype: `void __fastcall(basessp::BaseSSP *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180022b24`

## callees

- `0x180005770`
- `0x180043460`
- `0x1800441e4`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x180043496`
- `ntdll!RtlFreeSid` at `0x1800434b3`
- `ntdll!RtlFreeSid` at `0x180043496`
- `ntdll!RtlFreeSid` at `0x1800434b3`

## pseudocode

```c
void __fastcall basessp::BaseSSP::~BaseSSP(basessp::BaseSSP *this, unsigned __int8 *a2, unsigned int a3)
{
  void *v4; // rcx
  void *v5; // rcx

  if ( *((_DWORD *)this + 53) )
  {
    basessp::WSTLowerCase(this, a2, a3);
    if ( *((_DWORD *)this + 52) == 1 )
    {
      basessp::BaseSSP::WSTUnloadCredTable(this);
    }
    else
    {
      v4 = (void *)*((_QWORD *)this + 28);
      if ( v4 )
      {
        RtlFreeSid(v4);
        *((_QWORD *)this + 28) = 0;
      }
      v5 = (void *)*((_QWORD *)this + 29);
      if ( v5 )
      {
        RtlFreeSid(v5);
        *((_QWORD *)this + 29) = 0;
      }
    }
    *((_DWORD *)this + 53) = 0;
  }
}

```

## disassembly

```asm
0x180043460  push    rbx
0x180043462  sub     rsp, 20h
0x180043466  cmp     dword ptr [rcx+0D4h], 0
0x18004346d  mov     rbx, rcx
0x180043470  jz      short loc_1800434CE
0x180043472  call    ?WSTLowerCase@basessp@@YAXPEAEK@Z; basessp::WSTLowerCase(uchar *,ulong)
0x180043477  cmp     dword ptr [rbx+0D0h], 1
0x18004347e  jnz     short loc_18004348A
0x180043480  mov     rcx, rbx; this
0x180043483  call    ?WSTUnloadCredTable@BaseSSP@basessp@@AEAAXXZ; basessp::BaseSSP::WSTUnloadCredTable(void)
0x180043488  jmp     short loc_1800434C4
0x18004348a  mov     rcx, [rbx+0E0h]; Sid
0x180043491  test    rcx, rcx
0x180043494  jz      short loc_1800434A7
0x180043496  call    cs:__imp_RtlFreeSid
0x18004349c  mov     qword ptr [rbx+0E0h], 0
0x1800434a7  mov     rcx, [rbx+0E8h]; Sid
0x1800434ae  test    rcx, rcx
0x1800434b1  jz      short loc_1800434C4
0x1800434b3  call    cs:__imp_RtlFreeSid
0x1800434b9  mov     qword ptr [rbx+0E8h], 0
0x1800434c4  mov     dword ptr [rbx+0D4h], 0
0x1800434ce  add     rsp, 20h
0x1800434d2  pop     rbx
0x1800434d3  retn
```
