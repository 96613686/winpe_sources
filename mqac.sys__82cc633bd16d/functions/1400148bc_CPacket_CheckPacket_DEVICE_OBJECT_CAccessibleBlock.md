# CPacket::CheckPacket(_DEVICE_OBJECT *,CAccessibleBlock *)

- ea: `0x1400148bc`
- end: `0x140014942`
- name: `?CheckPacket@CPacket@@SAJPEAU_DEVICE_OBJECT@@PEAVCAccessibleBlock@@@Z`
- size: `134`
- prototype: `static int(struct _DEVICE_OBJECT *, struct CAccessibleBlock *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400107b4`

## callees

- `0x1400148bc`
- `0x140014e18`
- `0x1400197c8`

## pseudocode

```c
__int64 __fastcall CPacket::CheckPacket(struct _DEVICE_OBJECT *a1, struct CAccessibleBlock *a2)
{
  unsigned __int64 v3; // rdi
  unsigned int v4; // eax
  __int64 v5; // r8

  if ( (*((_DWORD *)a2 + 4) & 0x1FFE00) != 0x157800 )
    return 3221225473LL;
  v3 = (unsigned __int64)a2 + 36;
  if ( *((_BYTE *)a2 + 37) != 124 )
    return 3221225473LL;
  v4 = CPacket::ComputeCRC(a2);
  if ( *((_DWORD *)a2 + 10) != v4 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
    {
      WPP_SF_DDq(
        WPP_GLOBAL_Control->Queue.ListEntry.Blink,
        v3 & -(__int64)(a2 != 0),
        v5,
        v4,
        *(_DWORD *)((v3 & -(__int64)(a2 != 0)) + 4),
        a2);
    }
    return 3221225473LL;
  }
  return 0;
}

```

## disassembly

```asm
0x1400148bc  mov     [rsp+arg_0], rbx
0x1400148c1  push    rdi
0x1400148c2  sub     rsp, 30h
0x1400148c6  mov     eax, [rdx+10h]
0x1400148c9  mov     rbx, rdx
0x1400148cc  and     eax, 1FFE00h
0x1400148d1  cmp     eax, 157800h
0x1400148d6  jnz     short loc_14001492D
0x1400148d8  lea     rdi, [rdx+24h]
0x1400148dc  cmp     byte ptr [rdi+1], 7Ch ; '|'
0x1400148e0  jnz     short loc_14001492D
0x1400148e2  mov     rcx, rdx; struct CPacketBuffer *
0x1400148e5  call    ?ComputeCRC@CPacket@@CAKPEAVCPacketBuffer@@@Z; CPacket::ComputeCRC(CPacketBuffer *)
0x1400148ea  mov     r9d, eax
0x1400148ed  cmp     [rbx+28h], eax
0x1400148f0  jz      short loc_14001493E
0x1400148f2  mov     rcx, rbx
0x1400148f5  neg     rcx
0x1400148f8  sbb     rdx, rdx
0x1400148fb  and     rdx, rdi
0x1400148fe  mov     rcx, cs:WPP_GLOBAL_Control
0x140014905  lea     rax, WPP_GLOBAL_Control
0x14001490c  cmp     rcx, rax
0x14001490f  jz      short loc_14001492D
0x140014911  mov     eax, [rcx+6Ch]
0x140014914  test    al, 4
0x140014916  jz      short loc_14001492D
0x140014918  mov     eax, [rdx+4]
0x14001491b  mov     rcx, [rcx+58h]
0x14001491f  mov     [rsp+38h+var_10], rbx
0x140014924  mov     [rsp+38h+var_18], eax
0x140014928  call    WPP_SF_DDq
0x14001492d  mov     eax, 0C0000001h
0x140014932  mov     rbx, [rsp+38h+arg_0]
0x140014937  add     rsp, 30h
0x14001493b  pop     rdi
0x14001493c  retn
0x14001493e  xor     eax, eax
0x140014940  jmp     short loc_140014932
```
