# SendSysEx

- ea: `0x180004cc0`
- end: `0x180004ddf`
- name: `SendSysEx`
- size: `287`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800048fc`
- `0x180005990`
- `0x180005a1c`

## callees

- `0x180004cc0`
- `0x1800058bc`

## import_xrefs

- `WINMM!midiOutLongMsg` at `0x180004d96`
- `WINMM!midiOutLongMsg` at `0x180004d96`

## pseudocode

```c
__int64 __fastcall SendSysEx(__int64 a1)
{
  int v2; // edi
  __int64 v3; // r8
  unsigned int v4; // ecx
  __int64 v5; // rdx
  __int64 v6; // rbp
  int v7; // esi
  int v8; // r15d
  __int64 v9; // r14
  char v10; // al
  HMIDIOUT v11; // rcx
  _DWORD *v12; // rax
  __int64 result; // rax

  v2 = *(_DWORD *)(*(_QWORD *)(a1 + 80) + 20LL);
  *(_BYTE *)(a1 + 2093) = 1;
  if ( v2 )
  {
    while ( 2 )
    {
      v3 = *(_QWORD *)(a1 + 80);
      if ( !*(_DWORD *)v3 )
      {
        v4 = 0;
        while ( 1 )
        {
          v5 = 368LL * v4;
          if ( (*(_BYTE *)(v5 + a1 + 1012) & 1) != 0 )
            break;
          if ( (int)++v4 >= 2 )
            goto LABEL_19;
        }
        v6 = v5 + a1 + 988;
        if ( v6 )
        {
          v7 = 0;
          if ( *(_BYTE *)(v3 + 16) == 0xF0 )
          {
            *(_BYTE *)(v6 + 112) = -16;
            v7 = 1;
            ++v2;
            *(_BYTE *)(*(_QWORD *)(a1 + 80) + 16LL) = 0;
          }
          v8 = v2;
          if ( v2 > 256 )
            v8 = 256;
          do
          {
            v9 = *(_QWORD *)(a1 + 80);
            v10 = LookByte(v9);
            if ( !*(_DWORD *)v9 )
              ++*(_QWORD *)(v9 + 24);
            *(_BYTE *)(v7 + v6 + 112) = v10;
            if ( **(_DWORD **)(a1 + 80) )
              break;
            ++v7;
          }
          while ( v7 < v8 );
          *(_DWORD *)(v6 + 8) = v7;
          v2 -= v7;
          v11 = *(HMIDIOUT *)(a1 + 168);
          if ( v11 )
            midiOutLongMsg(v11, (LPMIDIHDR)v6, 0x70u);
          if ( v2 )
            continue;
        }
LABEL_19:
        if ( !v2 )
          goto LABEL_23;
      }
      break;
    }
    v12 = *(_DWORD **)(a1 + 80);
    if ( *v12 )
      *v12 = 275;
    else
      *(_BYTE *)(a1 + 2092) = 1;
  }
  else
  {
LABEL_23:
    *(_BYTE *)(a1 + 2093) = 0;
  }
  result = *(_QWORD *)(a1 + 80);
  *(_DWORD *)(result + 20) = v2;
  return result;
}

```

## disassembly

```asm
0x180004cc0  push    rbx
0x180004cc2  push    rbp
0x180004cc3  push    rsi
0x180004cc4  push    rdi
0x180004cc5  push    r13
0x180004cc7  push    r14
0x180004cc9  push    r15
0x180004ccb  sub     rsp, 20h
0x180004ccf  mov     rax, [rcx+50h]
0x180004cd3  mov     rbx, rcx
0x180004cd6  mov     edi, [rax+14h]
0x180004cd9  mov     byte ptr [rcx+82Dh], 1
0x180004ce0  test    edi, edi
0x180004ce2  jz      loc_180004DC2
0x180004ce8  mov     r13d, 100h
0x180004cee  mov     r8, [rbx+50h]
0x180004cf2  cmp     dword ptr [r8], 0
0x180004cf6  jnz     loc_180004DA8
0x180004cfc  xor     ecx, ecx
0x180004cfe  mov     eax, ecx
0x180004d00  imul    rdx, rax, 170h
0x180004d07  test    byte ptr [rdx+rbx+3F4h], 1
0x180004d0f  jnz     short loc_180004D1D
0x180004d11  inc     ecx
0x180004d13  cmp     ecx, 2
0x180004d16  jl      short loc_180004CFE
0x180004d18  jmp     loc_180004DA4
0x180004d1d  lea     rbp, [rbx+3DCh]
0x180004d24  add     rbp, rdx
0x180004d27  jz      short loc_180004DA4
0x180004d29  xor     esi, esi
0x180004d2b  cmp     byte ptr [r8+10h], 0F0h
0x180004d30  jnz     short loc_180004D45
0x180004d32  mov     byte ptr [rbp+70h], 0F0h
0x180004d36  mov     esi, 1
0x180004d3b  mov     rax, [rbx+50h]
0x180004d3f  inc     edi
0x180004d41  mov     byte ptr [rax+10h], 0
0x180004d45  cmp     edi, r13d
0x180004d48  mov     r15d, edi
0x180004d4b  cmovg   r15d, r13d
0x180004d4f  mov     r14, [rbx+50h]
0x180004d53  mov     rcx, r14
0x180004d56  call    LookByte
0x180004d5b  cmp     dword ptr [r14], 0
0x180004d5f  jnz     short loc_180004D65
0x180004d61  inc     qword ptr [r14+18h]
0x180004d65  movsxd  rcx, esi
0x180004d68  mov     [rcx+rbp+70h], al
0x180004d6c  mov     rax, [rbx+50h]
0x180004d70  cmp     dword ptr [rax], 0
0x180004d73  jnz     short loc_180004D7C
0x180004d75  inc     esi
0x180004d77  cmp     esi, r15d
0x180004d7a  jl      short loc_180004D4F
0x180004d7c  mov     [rbp+8], esi
0x180004d7f  sub     edi, esi
0x180004d81  mov     rcx, [rbx+0A8h]; hmo
0x180004d88  test    rcx, rcx
0x180004d8b  jz      short loc_180004D9C
0x180004d8d  mov     r8d, 70h ; 'p'; cbmh
0x180004d93  mov     rdx, rbp; pmh
0x180004d96  call    cs:__imp_midiOutLongMsg
0x180004d9c  test    edi, edi
0x180004d9e  jnz     loc_180004CEE
0x180004da4  test    edi, edi
0x180004da6  jz      short loc_180004DC2
0x180004da8  mov     rax, [rbx+50h]
0x180004dac  cmp     dword ptr [rax], 0
0x180004daf  jz      short loc_180004DB9
0x180004db1  mov     dword ptr [rax], 113h
0x180004db7  jmp     short loc_180004DC9
0x180004db9  mov     byte ptr [rbx+82Ch], 1
0x180004dc0  jmp     short loc_180004DC9
0x180004dc2  mov     byte ptr [rbx+82Dh], 0
0x180004dc9  mov     rax, [rbx+50h]
0x180004dcd  mov     [rax+14h], edi
0x180004dd0  add     rsp, 20h
0x180004dd4  pop     r15
0x180004dd6  pop     r14
0x180004dd8  pop     r13
0x180004dda  pop     rdi
0x180004ddb  pop     rsi
0x180004ddc  pop     rbp
0x180004ddd  pop     rbx
0x180004dde  retn
```
