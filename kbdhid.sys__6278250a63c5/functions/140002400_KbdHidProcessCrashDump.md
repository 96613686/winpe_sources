# KbdHidProcessCrashDump

- ea: `0x140002400`
- end: `0x140002692`
- name: `KbdHidProcessCrashDump`
- size: `658`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140002240`

## callees

- `0x140002400`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x140002556`
- `ntoskrnl!KeBugCheckEx` at `0x140002556`

## pseudocode

```c
void __fastcall KbdHidProcessCrashDump(__int64 a1, unsigned __int8 a2, int a3)
{
  int v4; // eax
  int v5; // eax
  ULONG NumberOfMapRegisters; // edx
  int v7; // ecx
  int v8; // ecx

  if ( a2 <= 0x7Fu )
  {
    switch ( a2 )
    {
      case 0x1Du:
        if ( a3 )
        {
          if ( a3 == 1 )
            *(_DWORD *)(a1 + 752) |= 2u;
        }
        else
        {
          *(_DWORD *)(a1 + 752) |= 0x20u;
        }
        break;
      case 0x2Au:
        if ( !a3 )
          *(_DWORD *)(a1 + 752) |= 0x10u;
        break;
      case 0x36u:
        if ( !a3 )
          *(_DWORD *)(a1 + 752) |= 1u;
        break;
      case 0x38u:
        if ( a3 )
        {
          if ( a3 == 1 )
            *(_DWORD *)(a1 + 752) |= 4u;
        }
        else
        {
          *(_DWORD *)(a1 + 752) |= 0x40u;
        }
        break;
      default:
        if ( *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters + 4) <= 0x7Fu )
        {
          if ( !a3 && (a2 & 0x7F) == *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters + 4) )
            return;
        }
        else if ( a3 == 1 && ((a2 ^ *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters + 4)) & 0x7F) == 0 )
        {
          return;
        }
        if ( *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters + 5) > 0x7Fu )
        {
          if ( a3 == 1 && ((a2 ^ *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters + 5)) & 0x7F) == 0 )
            return;
        }
        else if ( !a3 && (a2 & 0x7F) == *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters + 5) )
        {
          return;
        }
        goto LABEL_40;
    }
  }
  else
  {
    v4 = a2 & 0x7F;
    switch ( v4 )
    {
      case 42:
        if ( !a3 )
          *(_DWORD *)(a1 + 752) &= 0xFFFFFCEF;
        return;
      case 29:
        if ( a3 )
        {
          if ( a3 == 1 )
            *(_DWORD *)(a1 + 752) &= 0xFFFFFCFD;
        }
        else
        {
          *(_DWORD *)(a1 + 752) &= 0xFFFFFCDF;
        }
        break;
      case 54:
        if ( !a3 )
          *(_DWORD *)(a1 + 752) &= 0xFFFFFCFE;
        break;
      case 56:
        if ( a3 )
        {
          if ( a3 == 1 )
            *(_DWORD *)(a1 + 752) &= 0xFFFFFCFB;
        }
        else
        {
          *(_DWORD *)(a1 + 752) &= 0xFFFFFCBF;
        }
        break;
      default:
        if ( *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters + 4) <= 0x7Fu )
        {
          if ( !a3 && (a2 & 0x7F) == *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters + 4) )
            goto LABEL_32;
        }
        else if ( a3 == 1 && ((a2 ^ *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters + 4)) & 0x7F) == 0 )
        {
          goto LABEL_32;
        }
        if ( *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters + 5) <= 0x7Fu )
        {
          if ( !a3 && (a2 & 0x7F) == *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters + 5) )
            goto LABEL_32;
        }
        else if ( a3 == 1 && ((a2 ^ *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters + 5)) & 0x7F) == 0 )
        {
LABEL_32:
          v5 = *(_DWORD *)(a1 + 752);
          NumberOfMapRegisters = WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters;
          v7 = 512;
          if ( (v5 & 0x100) == 0 )
            v7 = 256;
          v8 = v5 | v7;
          *(_DWORD *)(a1 + 752) = v8;
          if ( v8 == (NumberOfMapRegisters | 0x300) )
          {
            *(_DWORD *)(a1 + 752) = 0;
            KeBugCheckEx(0xE2u, 0, 0, 0, 0);
          }
          return;
        }
LABEL_40:
        *(_DWORD *)(a1 + 752) = 0;
        return;
    }
  }
}

```

## disassembly

```asm
0x140002400  sub     rsp, 38h
0x140002404  movzx   r9d, byte ptr cs:WPP_MAIN_CB.Queue+2Dh
0x14000240c  mov     r10, rcx
0x14000240f  movzx   ecx, byte ptr cs:WPP_MAIN_CB.Queue+2Ch
0x140002416  cmp     dl, 7Fh
0x140002419  jbe     short loc_140002434
0x14000241b  mov     eax, edx
0x14000241d  and     eax, 7Fh
0x140002420  cmp     eax, 2Ah ; '*'
0x140002423  jnz     short loc_14000246F
0x140002425  test    r8d, r8d
0x140002428  jz      loc_140002682
0x14000242e  add     rsp, 38h
0x140002432  retn
0x140002434  cmp     dl, 1Dh
0x140002437  jz      short loc_1400024A9
0x140002439  cmp     dl, 2Ah ; '*'
0x14000243c  jz      short loc_14000249A
0x14000243e  cmp     dl, 36h ; '6'
0x140002441  jz      loc_1400025D9
0x140002447  cmp     dl, 38h ; '8'
0x14000244a  jz      loc_1400025B0
0x140002450  cmp     cl, 7Fh
0x140002453  jbe     loc_140002563
0x140002459  cmp     r8d, 1
0x14000245d  jnz     loc_140002568
0x140002463  xor     cl, dl
0x140002465  test    cl, 7Fh
0x140002468  jz      short loc_14000242E
0x14000246a  jmp     loc_140002568
0x14000246f  cmp     eax, 1Dh
0x140002472  jz      short loc_1400024C0
0x140002474  cmp     eax, 36h ; '6'
0x140002477  jz      loc_14000264F
0x14000247d  cmp     eax, 38h ; '8'
0x140002480  jz      loc_140002620
0x140002486  cmp     cl, 7Fh
0x140002489  jbe     short loc_1400024DA
0x14000248b  cmp     r8d, 1
0x14000248f  jnz     short loc_1400024E8
0x140002491  xor     cl, dl
0x140002493  test    cl, 7Fh
0x140002496  jz      short loc_140002505
0x140002498  jmp     short loc_1400024E8
0x14000249a  test    r8d, r8d
0x14000249d  jnz     short loc_14000242E
0x14000249f  or      dword ptr [r10+2F0h], 10h
0x1400024a7  jmp     short loc_14000242E
0x1400024a9  test    r8d, r8d
0x1400024ac  jnz     loc_1400025EF
0x1400024b2  or      dword ptr [r10+2F0h], 20h
0x1400024ba  add     rsp, 38h
0x1400024be  retn
0x1400024c0  test    r8d, r8d
0x1400024c3  jnz     loc_140002668
0x1400024c9  and     dword ptr [r10+2F0h], 0FFFFFCDFh
0x1400024d4  add     rsp, 38h
0x1400024d8  retn
0x1400024da  test    r8d, r8d
0x1400024dd  jnz     short loc_1400024E8
0x1400024df  movzx   eax, dl
0x1400024e2  and     al, 7Fh
0x1400024e4  cmp     al, cl
0x1400024e6  jz      short loc_140002505
0x1400024e8  cmp     r9b, 7Fh
0x1400024ec  jbe     loc_140002606
0x1400024f2  cmp     r8d, 1
0x1400024f6  jnz     loc_14000257F
0x1400024fc  xor     r9b, dl
0x1400024ff  test    r9b, 7Fh
0x140002503  jnz     short loc_14000257F
0x140002505  mov     eax, [r10+2F0h]
0x14000250c  mov     r8d, 100h
0x140002512  mov     edx, dword ptr cs:WPP_MAIN_CB.Queue+28h
0x140002518  test    r8d, eax
0x14000251b  mov     ecx, 200h
0x140002520  cmovz   ecx, r8d
0x140002524  or      edx, 300h
0x14000252a  or      ecx, eax
0x14000252c  mov     [r10+2F0h], ecx
0x140002533  cmp     ecx, edx
0x140002535  jnz     loc_14000242E
0x14000253b  xor     eax, eax
0x14000253d  xor     r9d, r9d; BugCheckParameter3
0x140002540  xor     r8d, r8d; BugCheckParameter2
0x140002543  mov     [r10+2F0h], eax
0x14000254a  xor     edx, edx; BugCheckParameter1
0x14000254c  mov     [rsp+38h+BugCheckParameter4], rax; BugCheckParameter4
0x140002551  mov     ecx, 0E2h; BugCheckCode
0x140002556  call    cs:__imp_KeBugCheckEx
0x140002563  test    r8d, r8d
0x140002566  jz      short loc_14000258D
0x140002568  cmp     r9b, 7Fh
0x14000256c  ja      short loc_14000259C
0x14000256e  test    r8d, r8d
0x140002571  jnz     short loc_14000257F
0x140002573  and     dl, 7Fh
0x140002576  cmp     dl, r9b
0x140002579  jz      loc_14000242E
0x14000257f  xor     eax, eax
0x140002581  mov     [r10+2F0h], eax
0x140002588  jmp     loc_14000242E
0x14000258d  movzx   eax, dl
0x140002590  and     al, 7Fh
0x140002592  cmp     al, cl
0x140002594  jz      loc_14000242E
0x14000259a  jmp     short loc_140002568
0x14000259c  cmp     r8d, 1
0x1400025a0  jnz     short loc_14000257F
0x1400025a2  xor     r9b, dl
0x1400025a5  test    r9b, 7Fh
0x1400025a9  jnz     short loc_14000257F
0x1400025ab  jmp     loc_14000242E
0x1400025b0  test    r8d, r8d
0x1400025b3  jnz     short loc_1400025C2
0x1400025b5  or      dword ptr [r10+2F0h], 40h
0x1400025bd  jmp     loc_14000242E
0x1400025c2  cmp     r8d, 1
0x1400025c6  jnz     loc_14000242E
0x1400025cc  or      dword ptr [r10+2F0h], 4
0x1400025d4  jmp     loc_14000242E
0x1400025d9  test    r8d, r8d
0x1400025dc  jnz     loc_14000242E
0x1400025e2  or      dword ptr [r10+2F0h], 1
0x1400025ea  jmp     loc_14000242E
0x1400025ef  cmp     r8d, 1
0x1400025f3  jnz     loc_14000242E
0x1400025f9  or      dword ptr [r10+2F0h], 2
0x140002601  jmp     loc_14000242E
0x140002606  test    r8d, r8d
0x140002609  jnz     loc_14000257F
0x14000260f  and     dl, 7Fh
0x140002612  cmp     dl, r9b
0x140002615  jnz     loc_14000257F
0x14000261b  jmp     loc_140002505
0x140002620  test    r8d, r8d
0x140002623  jnz     short loc_140002635
0x140002625  and     dword ptr [r10+2F0h], 0FFFFFCBFh
0x140002630  jmp     loc_14000242E
0x140002635  cmp     r8d, 1
0x140002639  jnz     loc_14000242E
0x14000263f  and     dword ptr [r10+2F0h], 0FFFFFCFBh
0x14000264a  jmp     loc_14000242E
0x14000264f  test    r8d, r8d
0x140002652  jnz     loc_14000242E
0x140002658  and     dword ptr [r10+2F0h], 0FFFFFCFEh
0x140002663  jmp     loc_14000242E
0x140002668  cmp     r8d, 1
0x14000266c  jnz     loc_14000242E
0x140002672  and     dword ptr [r10+2F0h], 0FFFFFCFDh
0x14000267d  jmp     loc_14000242E
0x140002682  and     dword ptr [r10+2F0h], 0FFFFFCEFh
0x14000268d  jmp     loc_14000242E
```
