# WmiClass::CreateClass(ushort const *,ushort const *,ushort const *,WmiClass * *)

- ea: `0x18000a030`
- end: `0x18000a0ca`
- name: `?CreateClass@WmiClass@@SAJPEBG00PEAPEAV1@@Z`
- size: `154`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct WmiClass **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180009e10`

## callees

- `0x180006edc`
- `0x180009de8`
- `0x18000a030`
- `0x18000a484`

## pseudocode

```c
__int64 __fastcall WmiClass::CreateClass(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct WmiClass **a4)
{
  WmiClass *v5; // rax
  const unsigned __int16 *v6; // rdx
  const unsigned __int16 *v7; // r8
  const unsigned __int16 *v8; // r9
  WmiClass *v9; // rbx
  int v10; // edi

  if ( a4 )
  {
    v5 = (WmiClass *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
    v9 = v5;
    if ( v5 )
    {
      *(_QWORD *)v5 = 0;
      *((_QWORD *)v5 + 1) = 0;
      *((_QWORD *)v5 + 2) = 0;
      *((_QWORD *)v5 + 3) = 0;
      *((_QWORD *)v5 + 4) = 0;
      *((_QWORD *)v5 + 5) = 0;
      v10 = WmiClass::Initialize(v5, v6, v7, v8);
      if ( v10 < 0 )
        WmiClass::`scalar deleting destructor'(v9);
      else
        *a4 = v9;
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000a030  mov     [rsp+arg_0], rbx
0x18000a035  mov     [rsp+arg_8], rsi
0x18000a03a  push    rdi
0x18000a03b  sub     rsp, 20h
0x18000a03f  mov     rsi, r9
0x18000a042  test    r9, r9
0x18000a045  jz      short loc_18000A0B3
0x18000a047  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a04e  mov     ecx, 30h ; '0'; unsigned __int64
0x18000a053  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a058  mov     rbx, rax
0x18000a05b  test    rax, rax
0x18000a05e  jz      short loc_18000A0AC
0x18000a060  mov     rcx, rax; this
0x18000a063  mov     qword ptr [rax], 0
0x18000a06a  mov     qword ptr [rax+8], 0
0x18000a072  mov     qword ptr [rax+10h], 0
0x18000a07a  mov     qword ptr [rax+18h], 0
0x18000a082  mov     qword ptr [rax+20h], 0
0x18000a08a  mov     qword ptr [rax+28h], 0
0x18000a092  call    ?Initialize@WmiClass@@AEAAJPEBG00@Z; WmiClass::Initialize(ushort const *,ushort const *,ushort const *)
0x18000a097  mov     edi, eax
0x18000a099  test    eax, eax
0x18000a09b  js      short loc_18000A0A2
0x18000a09d  mov     [rsi], rbx
0x18000a0a0  jmp     short loc_18000A0B8
0x18000a0a2  mov     rcx, rbx; this
0x18000a0a5  call    ??_GWmiClass@@QEAAPEAXI@Z; WmiClass::`scalar deleting destructor'(uint)
0x18000a0aa  jmp     short loc_18000A0B8
0x18000a0ac  mov     edi, 8007000Eh
0x18000a0b1  jmp     short loc_18000A0B8
0x18000a0b3  mov     edi, 80070057h
0x18000a0b8  mov     rbx, [rsp+28h+arg_0]
0x18000a0bd  mov     eax, edi
0x18000a0bf  mov     rsi, [rsp+28h+arg_8]
0x18000a0c4  add     rsp, 20h
0x18000a0c8  pop     rdi
0x18000a0c9  retn
```
