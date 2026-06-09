# SC_GPT::ReadHeader(ulong,GPT_HEADER *)

- ea: `0x14000ffcc`
- end: `0x1400100a6`
- name: `?ReadHeader@SC_GPT@@AEAAJKPEAVGPT_HEADER@@@Z`
- size: `218`
- prototype: `__int64 __fastcall(SC_DISK **this, int, struct GPT_HEADER *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400100ac`
- `0x140010380`

## callees

- `0x140005950`
- `0x14000a93d`
- `0x14000ffcc`

## pseudocode

```c
__int64 __fastcall SC_GPT::ReadHeader(SC_DISK **this, int a2, struct GPT_HEADER *a3)
{
  unsigned __int64 v5; // rbx
  int Sectors; // esi
  int v7; // ebx
  ULONG v8; // eax

  if ( a2 )
    v5 = *((_QWORD *)*this + 31) - 1LL;
  else
    v5 = 1;
  Sectors = SC_DISK::ReadSectors(*this, 1u, v5, a3);
  if ( Sectors >= 0 )
  {
    Sectors = -1073741774;
    if ( *(_QWORD *)a3 == 0x5452415020494645LL
      && *((_DWORD *)a3 + 2) == 0x10000
      && *((_DWORD *)a3 + 3) == 92
      && *((_DWORD *)a3 + 21) == 128
      && (unsigned int)(*((_DWORD *)a3 + 20) - 1) <= 0x3FF
      && *((_QWORD *)a3 + 3) == v5 )
    {
      v7 = *((_DWORD *)a3 + 4);
      *((_DWORD *)a3 + 4) = 0;
      v8 = RtlComputeCrc32_0(0, (PUCHAR)a3, 0x5Cu);
      *((_DWORD *)a3 + 4) = v7;
      if ( v8 == v7 )
        return *((_QWORD *)a3 + 5) < (unsigned __int64)(((-*((_DWORD *)*this + 59)
                                                        & (unsigned int)(*((_DWORD *)*this + 59)
                                                                       + *((_DWORD *)a3 + 20) * *((_DWORD *)a3 + 21)
                                                                       - 1)) >> *((_DWORD *)*this + 60))
                                                      + 2)
             ? 0xC0000032
             : 0;
    }
  }
  return (unsigned int)Sectors;
}

```

## disassembly

```asm
0x14000ffcc  push    rbx
0x14000ffce  push    rsi
0x14000ffcf  push    rdi
0x14000ffd0  push    r14
0x14000ffd2  sub     rsp, 28h
0x14000ffd6  mov     rdi, r8
0x14000ffd9  mov     r14, rcx
0x14000ffdc  test    edx, edx
0x14000ffde  jnz     short loc_14000FFE5
0x14000ffe0  lea     ebx, [rdx+1]
0x14000ffe3  jmp     short loc_14000FFF2
0x14000ffe5  mov     rax, [rcx]
0x14000ffe8  mov     rbx, [rax+0F8h]
0x14000ffef  dec     rbx
0x14000fff2  mov     rcx, [rcx]; this
0x14000fff5  mov     r9, rdi; void *
0x14000fff8  mov     r8, rbx; unsigned __int64
0x14000fffb  mov     edx, 1; unsigned int
0x140010000  call    ?ReadSectors@SC_DISK@@QEAAJK_KPEAX@Z; SC_DISK::ReadSectors(ulong,unsigned __int64,void *)
0x140010005  mov     esi, eax
0x140010007  test    eax, eax
0x140010009  js      loc_140010099
0x14001000f  mov     rax, 5452415020494645h
0x140010019  mov     esi, 0C0000032h
0x14001001e  cmp     [rdi], rax
0x140010021  jnz     short loc_140010099
0x140010023  cmp     dword ptr [rdi+8], 10000h
0x14001002a  jnz     short loc_140010099
0x14001002c  mov     r8d, 5Ch ; '\'; Length
0x140010032  cmp     [rdi+0Ch], r8d
0x140010036  jnz     short loc_140010099
0x140010038  cmp     dword ptr [rdi+54h], 80h
0x14001003f  jnz     short loc_140010099
0x140010041  mov     eax, [rdi+50h]
0x140010044  dec     eax
0x140010046  cmp     eax, 3FFh
0x14001004b  ja      short loc_140010099
0x14001004d  cmp     [rdi+18h], rbx
0x140010051  jnz     short loc_140010099
0x140010053  mov     ebx, [rdi+10h]
0x140010056  mov     rdx, rdi; Buffer
0x140010059  xor     ecx, ecx; InitialCrc
0x14001005b  mov     dword ptr [rdi+10h], 0
0x140010062  call    RtlComputeCrc32_0
0x140010067  mov     [rdi+10h], ebx
0x14001006a  cmp     eax, ebx
0x14001006c  jnz     short loc_140010099
0x14001006e  mov     eax, [rdi+54h]
0x140010071  imul    eax, [rdi+50h]
0x140010075  mov     rcx, [r14]
0x140010078  mov     edx, [rcx+0ECh]
0x14001007e  dec     eax
0x140010080  mov     ecx, [rcx+0F0h]
0x140010086  add     eax, edx
0x140010088  neg     edx
0x14001008a  and     eax, edx
0x14001008c  shr     eax, cl
0x14001008e  add     eax, 2
0x140010091  cmp     [rdi+28h], rax
0x140010095  sbb     eax, eax
0x140010097  and     esi, eax
0x140010099  mov     eax, esi
0x14001009b  add     rsp, 28h
0x14001009f  pop     r14
0x1400100a1  pop     rdi
0x1400100a2  pop     rsi
0x1400100a3  pop     rbx
0x1400100a4  retn
```
