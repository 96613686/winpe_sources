# CCompRC::LookupNode(ulong,int &)

- ea: `0x140012280`
- end: `0x1400122e2`
- name: `?LookupNode@CCompRC@@AEAAPEAUHINSTANCE__@@KAEAH@Z`
- size: `98`
- prototype: `HINSTANCE __fastcall(CCompRC *this, int, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400124f8`

## callees

- `0x140012280`

## pseudocode

```c
HINSTANCE __fastcall CCompRC::LookupNode(CCompRC *this, int a2, int *a3)
{
  __int64 v3; // r10
  int v4; // r9d
  __int64 v5; // r11
  __int64 v6; // rax
  __int64 v7; // rcx

  v3 = *((_QWORD *)this + 3);
  if ( v3 )
  {
    v4 = 0;
    if ( *((int *)this + 8) > 0 )
    {
      v5 = *((int *)this + 8);
      v6 = *((_QWORD *)this + 3);
      v7 = 0;
      while ( 1 )
      {
        if ( *(_QWORD *)(v6 + 8) && a2 != -1 && a2 == *(_DWORD *)v6 )
          return *(HINSTANCE *)(v3 + 24LL * v4 + 8);
        if ( *(_DWORD *)(v6 + 16) && a2 != -1 && a2 == *(_DWORD *)v6 )
          break;
        ++v4;
        ++v7;
        v6 += 24;
        if ( v7 >= v5 )
          return 0;
      }
      *a3 = 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140012280  mov     r10, [rcx+18h]
0x140012284  test    r10, r10
0x140012287  jz      short loc_1400122DF
0x140012289  xor     r9d, r9d
0x14001228c  cmp     [rcx+20h], r9d
0x140012290  jle     short loc_1400122DF
0x140012292  movsxd  r11, dword ptr [rcx+20h]
0x140012296  mov     rax, r10
0x140012299  xor     ecx, ecx
0x14001229b  cmp     qword ptr [rax+8], 0
0x1400122a0  jz      short loc_1400122AB
0x1400122a2  cmp     edx, 0FFFFFFFFh
0x1400122a5  jz      short loc_1400122AB
0x1400122a7  cmp     edx, [rax]
0x1400122a9  jz      short loc_1400122CB
0x1400122ab  cmp     dword ptr [rax+10h], 0
0x1400122af  jz      short loc_1400122BA
0x1400122b1  cmp     edx, 0FFFFFFFFh
0x1400122b4  jz      short loc_1400122BA
0x1400122b6  cmp     edx, [rax]
0x1400122b8  jz      short loc_1400122D8
0x1400122ba  inc     r9d
0x1400122bd  inc     rcx
0x1400122c0  add     rax, 18h
0x1400122c4  cmp     rcx, r11
0x1400122c7  jge     short loc_1400122DF
0x1400122c9  jmp     short loc_14001229B
0x1400122cb  movsxd  rcx, r9d
0x1400122ce  lea     rax, [rcx+rcx*2]
0x1400122d2  mov     rax, [r10+rax*8+8]
0x1400122d7  retn
0x1400122d8  mov     dword ptr [r8], 1
0x1400122df  xor     eax, eax
0x1400122e1  retn
```
