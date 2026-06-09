# CPacket::UpdateBitmap(ulong)

- ea: `0x14001961c`
- end: `0x14001966e`
- name: `?UpdateBitmap@CPacket@@QEAAXK@Z`
- size: `82`
- prototype: `void __fastcall(CPacket *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140017b90`
- `0x140021080`

## callees

- `0x1400037c0`
- `0x14001961c`

## pseudocode

```c
void __fastcall CPacket::UpdateBitmap(CPacket *this, unsigned int a2)
{
  unsigned int v3; // edx
  __int64 v4; // r10
  __int64 v5; // r9
  int v6; // r9d

  v3 = *((_DWORD *)this + 4);
  if ( v3 != -1 )
  {
    v4 = *((_QWORD *)this + 3);
    v5 = *(_QWORD *)(v4 + 88);
    if ( (*((_DWORD *)this + 13) & 0x2000000) != 0 )
    {
      if ( !v5 )
        return;
      v6 = 0;
    }
    else
    {
      if ( !v5 )
        return;
      v6 = 1;
    }
    CBitmap::FillBits((CBitmap *)(*(_QWORD *)(v4 + 128) + 12LL), v3 >> 9, a2 >> 9, v6);
  }
}

```

## disassembly

```asm
0x14001961c  sub     rsp, 28h
0x140019620  mov     r8d, edx
0x140019623  mov     edx, [rcx+10h]
0x140019626  cmp     edx, 0FFFFFFFFh
0x140019629  jz      short loc_140019668
0x14001962b  test    dword ptr [rcx+34h], 2000000h
0x140019632  mov     r10, [rcx+18h]
0x140019636  mov     r9, [r10+58h]
0x14001963a  jz      short loc_140019646
0x14001963c  test    r9, r9
0x14001963f  jz      short loc_140019668
0x140019641  xor     r9d, r9d
0x140019644  jmp     short loc_140019651
0x140019646  test    r9, r9
0x140019649  jz      short loc_140019668
0x14001964b  mov     r9d, 1; int
0x140019651  mov     rcx, [r10+80h]
0x140019658  add     rcx, 0Ch; this
0x14001965c  shr     r8d, 9; unsigned int
0x140019660  shr     edx, 9; unsigned int
0x140019663  call    ?FillBits@CBitmap@@QEAAXKKH@Z; CBitmap::FillBits(ulong,ulong,int)
0x140019668  add     rsp, 28h
0x14001966c  retn
```
