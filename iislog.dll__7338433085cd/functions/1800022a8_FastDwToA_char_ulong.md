# FastDwToA(char *,ulong)

- ea: `0x1800022a8`
- end: `0x1800023e8`
- name: `?FastDwToA@@YAKPEADK@Z`
- size: `320`
- prototype: `unsigned int __fastcall(char *Buffer, unsigned int Value)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180004160`
- `0x180005394`
- `0x180006870`
- `0x1800078d0`
- `0x180007ff0`
- `0x18000c170`
- `0x18000c634`
- `0x18000cb70`

## callees

- `0x1800022a8`

## import_xrefs

- `msvcrt!_ultoa` at `0x1800023cf`
- `msvcrt!_ultoa` at `0x1800023cf`

## pseudocode

```c
__int64 __fastcall FastDwToA(char *Buffer, unsigned int Value)
{
  __int64 result; // rax
  unsigned int v4; // r9d

  if ( Value >= 0xA )
  {
    if ( Value >= 0x64 )
    {
      if ( Value >= 0x3E8 )
      {
        if ( Value >= 0x2710 )
        {
          _ultoa(Value, Buffer, 10);
          result = -1;
          do
            ++result;
          while ( Buffer[result] );
        }
        else
        {
          Buffer[4] = 0;
          *Buffer = Value / 0x3E8 + 48;
          Buffer[1] = Value % 0x3E8 / 0x64 + 48;
          v4 = Value % 0x3E8 % 0x64;
          Buffer[2] = v4 / 0xA + 48;
          result = 4;
          Buffer[3] = v4 % 0xA + 48;
        }
      }
      else
      {
        Buffer[3] = 0;
        *Buffer = Value / 0x64 + 48;
        Buffer[1] = Value % 0x64 / 0xA + 48;
        result = 3;
        Buffer[2] = Value % 0x64 % 0xA + 48;
      }
    }
    else
    {
      Buffer[2] = 0;
      *Buffer = Value / 0xA + 48;
      result = 2;
      Buffer[1] = Value % 0xA + 48;
    }
  }
  else
  {
    Buffer[1] = 0;
    *Buffer = Value + 48;
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x1800022a8  push    rbx
0x1800022aa  sub     rsp, 20h
0x1800022ae  mov     r8d, 0Ah; Radix
0x1800022b4  mov     r9d, edx
0x1800022b7  mov     rbx, rcx
0x1800022ba  cmp     edx, r8d
0x1800022bd  jnb     short loc_1800022D3
0x1800022bf  add     r9b, 30h ; '0'
0x1800022c3  mov     byte ptr [rcx+1], 0
0x1800022c7  mov     [rcx], r9b
0x1800022ca  lea     eax, [r8-9]
0x1800022ce  jmp     loc_1800023E2
0x1800022d3  cmp     r9d, 64h ; 'd'
0x1800022d7  jnb     short loc_18000230C
0x1800022d9  mov     cl, 30h ; '0'
0x1800022db  mov     byte ptr [rbx+2], 0
0x1800022df  mov     eax, 0CCCCCCCDh
0x1800022e4  mul     r9d
0x1800022e7  shr     edx, 3
0x1800022ea  lea     eax, [rcx+rdx]
0x1800022ed  mov     [rbx], al
0x1800022ef  mov     al, dl
0x1800022f1  shl     dl, 2
0x1800022f4  add     al, dl
0x1800022f6  add     al, al
0x1800022f8  sub     r9b, al
0x1800022fb  mov     eax, 2
0x180002300  add     r9b, cl
0x180002303  mov     [rbx+1], r9b
0x180002307  jmp     loc_1800023E2
0x18000230c  cmp     r9d, 3E8h
0x180002313  jnb     short loc_18000235F
0x180002315  mov     cl, 30h ; '0'
0x180002317  mov     byte ptr [rbx+3], 0
0x18000231b  mov     eax, 51EB851Fh
0x180002320  mul     r9d
0x180002323  shr     edx, 5
0x180002326  lea     eax, [rcx+rdx]
0x180002329  mov     [rbx], al
0x18000232b  imul    eax, edx, 64h ; 'd'
0x18000232e  sub     r9d, eax
0x180002331  mov     eax, 0CCCCCCCDh
0x180002336  mul     r9d
0x180002339  shr     edx, 3
0x18000233c  lea     eax, [rcx+rdx]
0x18000233f  mov     [rbx+1], al
0x180002342  mov     al, dl
0x180002344  shl     dl, 2
0x180002347  add     al, dl
0x180002349  add     al, al
0x18000234b  sub     r9b, al
0x18000234e  mov     eax, 3
0x180002353  add     r9b, cl
0x180002356  mov     [rbx+2], r9b
0x18000235a  jmp     loc_1800023E2
0x18000235f  cmp     r9d, 2710h
0x180002366  jnb     short loc_1800023C9
0x180002368  mov     cl, 30h ; '0'
0x18000236a  mov     byte ptr [rbx+4], 0
0x18000236e  mov     eax, 10624DD3h
0x180002373  mul     r9d
0x180002376  shr     edx, 6
0x180002379  lea     eax, [rcx+rdx]
0x18000237c  mov     [rbx], al
0x18000237e  imul    eax, edx, 3E8h
0x180002384  sub     r9d, eax
0x180002387  mov     eax, 51EB851Fh
0x18000238c  mul     r9d
0x18000238f  shr     edx, 5
0x180002392  lea     eax, [rcx+rdx]
0x180002395  mov     [rbx+1], al
0x180002398  imul    eax, edx, 64h ; 'd'
0x18000239b  sub     r9d, eax
0x18000239e  mov     eax, 0CCCCCCCDh
0x1800023a3  mul     r9d
0x1800023a6  shr     edx, 3
0x1800023a9  lea     eax, [rcx+rdx]
0x1800023ac  mov     [rbx+2], al
0x1800023af  mov     al, dl
0x1800023b1  shl     dl, 2
0x1800023b4  add     al, dl
0x1800023b6  add     al, al
0x1800023b8  sub     r9b, al
0x1800023bb  mov     eax, 4
0x1800023c0  add     r9b, cl
0x1800023c3  mov     [rbx+3], r9b
0x1800023c7  jmp     short loc_1800023E2
0x1800023c9  mov     rdx, rbx; Buffer
0x1800023cc  mov     ecx, r9d; Value
0x1800023cf  call    cs:__imp__ultoa
0x1800023d5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800023d9  inc     rax
0x1800023dc  cmp     byte ptr [rbx+rax], 0
0x1800023e0  jnz     short loc_1800023D9
0x1800023e2  add     rsp, 20h
0x1800023e6  pop     rbx
0x1800023e7  retn
```
