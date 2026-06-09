# StringDup

- ea: `0x180006db4`
- end: `0x180006e7e`
- name: `StringDup`
- size: `202`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x1800052b0`
- `0x180006594`
- `0x180006d30`
- `0x18000dfe4`
- `0x1800118a4`

## callees

- `0x180005eac`
- `0x180005ed4`
- `0x1800060c8`
- `0x180006270`
- `0x180006318`
- `0x180006db4`

## pseudocode

```c
unsigned __int16 *__fastcall StringDup(unsigned __int16 *a1)
{
  __int64 v2; // rax
  unsigned __int64 v3; // rsi
  unsigned __int16 *v4; // rax
  unsigned __int16 *v5; // rbx
  int v6; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xAu, (const GUID *)WPP_04fb59550d79390d980a26525e0212b0_Traceguids);
  }
  if ( !a1 )
    return 0;
  v2 = -1;
  do
    ++v2;
  while ( a1[v2] );
  v3 = v2 + 1;
  v4 = (unsigned __int16 *)pMemAlloc(2 * (v2 + 1));
  v5 = v4;
  if ( !v4 )
    return 0;
  v6 = StringCchCopyW(v4, v3, a1);
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        0xBu,
        (const GUID *)WPP_04fb59550d79390d980a26525e0212b0_Traceguids,
        v6);
    }
    pMemFree(v5);
    return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x180006db4  push    rbx
0x180006db6  push    rbp
0x180006db7  push    rsi
0x180006db8  push    rdi
0x180006db9  push    r15
0x180006dbb  sub     rsp, 20h
0x180006dbf  mov     rdi, rcx
0x180006dc2  mov     rcx, cs:WPP_GLOBAL_Control
0x180006dc9  lea     r15, WPP_GLOBAL_Control
0x180006dd0  cmp     rcx, r15
0x180006dd3  jz      short loc_180006DF6
0x180006dd5  test    byte ptr [rcx+1Ch], 2
0x180006dd9  jz      short loc_180006DF6
0x180006ddb  cmp     byte ptr [rcx+19h], 5
0x180006ddf  jb      short loc_180006DF6
0x180006de1  mov     rcx, [rcx+10h]
0x180006de5  lea     r8, WPP_04fb59550d79390d980a26525e0212b0_Traceguids
0x180006dec  mov     edx, 0Ah
0x180006df1  call    WPP_SF_
0x180006df6  xor     ebp, ebp
0x180006df8  test    rdi, rdi
0x180006dfb  jz      short loc_180006E71
0x180006dfd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006e01  inc     rax
0x180006e04  cmp     [rdi+rax*2], bp
0x180006e08  jnz     short loc_180006E01
0x180006e0a  lea     rsi, [rax+1]
0x180006e0e  lea     rcx, [rsi+rsi]; dwBytes
0x180006e12  call    pMemAlloc
0x180006e17  mov     rbx, rax
0x180006e1a  test    rax, rax
0x180006e1d  jz      short loc_180006E71
0x180006e1f  mov     r8, rdi; unsigned __int16 *
0x180006e22  mov     rdx, rsi; unsigned __int64
0x180006e25  mov     rcx, rax; unsigned __int16 *
0x180006e28  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180006e2d  test    eax, eax
0x180006e2f  jns     short loc_180006E6C
0x180006e31  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e38  cmp     rcx, r15
0x180006e3b  jz      short loc_180006E61
0x180006e3d  test    byte ptr [rcx+1Ch], 2
0x180006e41  jz      short loc_180006E61
0x180006e43  cmp     byte ptr [rcx+19h], 2
0x180006e47  jb      short loc_180006E61
0x180006e49  mov     rcx, [rcx+10h]
0x180006e4d  lea     r8, WPP_04fb59550d79390d980a26525e0212b0_Traceguids
0x180006e54  mov     edx, 0Bh
0x180006e59  mov     r9d, eax
0x180006e5c  call    WPP_SF_d
0x180006e61  mov     rcx, rbx; lpMem
0x180006e64  call    pMemFree
0x180006e69  mov     rbx, rbp
0x180006e6c  mov     rax, rbx
0x180006e6f  jmp     short loc_180006E73
0x180006e71  xor     eax, eax
0x180006e73  add     rsp, 20h
0x180006e77  pop     r15
0x180006e79  pop     rdi
0x180006e7a  pop     rsi
0x180006e7b  pop     rbp
0x180006e7c  pop     rbx
0x180006e7d  retn
```
