# FH4::HandlerMap4::DecompHandler(void)

- ea: `0x1800136b8`
- end: `0x180013840`
- name: `?DecompHandler@HandlerMap4@FH4@@AEAAXXZ`
- size: `392`
- prototype: `void __fastcall(FH4::HandlerMap4 *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800125ac`
- `0x180012b94`
- `0x180013234`

## callees

- `0x1800136b8`

## pseudocode

```c
void __fastcall FH4::HandlerMap4::DecompHandler(FH4::HandlerMap4 *this)
{
  char *v2; // rax
  char v3; // r10
  _BYTE *v4; // rdx
  __int64 v5; // rcx
  int v6; // eax
  __int64 v7; // rcx
  int *v8; // r9
  char v9; // al
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx
  char *v14; // r9
  __int64 v15; // rax
  int v16; // edx
  __int64 v17; // rcx
  _BYTE *v18; // r9
  int v19; // eax
  __int64 v20; // rcx
  _BYTE *v21; // r9
  int v22; // eax

  *((_BYTE *)this + 24) = 0;
  *(_QWORD *)((char *)this + 28) = 0;
  *(_QWORD *)((char *)this + 36) = 0;
  *((_OWORD *)this + 3) = 0;
  v2 = (char *)*((_QWORD *)this + 1);
  v3 = *v2;
  v4 = v2 + 1;
  *((_BYTE *)this + 24) = *v2;
  *((_QWORD *)this + 1) = v2 + 1;
  if ( (v3 & 1) != 0 )
  {
    v5 = *v4 & 0xF;
    v4 -= byte_18004D110[v5];
    *((_DWORD *)this + 7) = *((_DWORD *)v4 - 1) >> byte_18004D110[v5 + 16];
    *((_QWORD *)this + 1) = v4;
  }
  if ( (v3 & 2) != 0 )
  {
    v6 = *(_DWORD *)v4;
    v4 += 4;
    *((_QWORD *)this + 1) = v4;
    *((_DWORD *)this + 8) = v6;
  }
  if ( (v3 & 4) != 0 )
  {
    v7 = *v4 & 0xF;
    v4 -= byte_18004D110[v7];
    *((_DWORD *)this + 9) = *((_DWORD *)v4 - 1) >> byte_18004D110[v7 + 16];
    *((_QWORD *)this + 1) = v4;
  }
  v8 = (int *)(v4 + 4);
  *((_DWORD *)this + 10) = *(_DWORD *)v4;
  v9 = v3 & 0x30;
  *((_QWORD *)this + 1) = v4 + 4;
  if ( (v3 & 8) != 0 )
  {
    if ( v9 == 16 )
    {
      v10 = *v8;
      *((_QWORD *)this + 1) = v4 + 8;
      *((_QWORD *)this + 6) = v10;
      return;
    }
    if ( v9 == 32 )
    {
      v11 = *v8;
      *((_QWORD *)this + 1) = v4 + 8;
      *((_QWORD *)this + 6) = v11;
      v12 = *((int *)v4 + 2);
      *((_QWORD *)this + 1) = v4 + 12;
LABEL_16:
      *((_QWORD *)this + 7) = v12;
    }
  }
  else
  {
    if ( v9 == 16 )
    {
      v13 = *(_BYTE *)v8 & 0xF;
      v14 = (char *)v8 - byte_18004D110[v13];
      v15 = (unsigned int)((*((_DWORD *)v14 - 1) >> byte_18004D110[v13 + 16]) + *((_DWORD *)this + 18));
      *((_QWORD *)this + 1) = v14;
      *((_QWORD *)this + 6) = v15;
      return;
    }
    if ( v9 == 32 )
    {
      v16 = *((_DWORD *)this + 18);
      v17 = *(_BYTE *)v8 & 0xF;
      v18 = (char *)v8 - byte_18004D110[v17];
      v19 = *((_DWORD *)v18 - 1) >> byte_18004D110[v17 + 16];
      *((_QWORD *)this + 1) = v18;
      *((_QWORD *)this + 6) = (unsigned int)(v16 + v19);
      v20 = *v18 & 0xF;
      v21 = &v18[-byte_18004D110[v20]];
      v22 = *((_DWORD *)v21 - 1) >> byte_18004D110[v20 + 16];
      *((_QWORD *)this + 1) = v21;
      v12 = (unsigned int)(v16 + v22);
      goto LABEL_16;
    }
  }
}

```

## disassembly

```asm
0x1800136b8  xor     eax, eax
0x1800136ba  lea     r11, __ImageBase
0x1800136c1  mov     [rcx+18h], al
0x1800136c4  xorps   xmm0, xmm0
0x1800136c7  mov     [rcx+1Ch], rax
0x1800136cb  mov     r8, rcx
0x1800136ce  mov     [rcx+24h], rax
0x1800136d2  movups  xmmword ptr [rcx+30h], xmm0
0x1800136d6  mov     rax, [rcx+8]
0x1800136da  mov     r10b, [rax]
0x1800136dd  lea     rdx, [rax+1]
0x1800136e1  mov     [rcx+18h], r10b
0x1800136e5  mov     [rcx+8], rdx
0x1800136e9  test    r10b, 1
0x1800136ed  jz      short loc_180013716
0x1800136ef  movzx   ecx, byte ptr [rdx]
0x1800136f2  and     ecx, 0Fh
0x1800136f5  movsx   rax, byte ptr [rcx+r11+4D110h]
0x1800136fe  mov     cl, [rcx+r11+4D120h]
0x180013706  sub     rdx, rax
0x180013709  mov     eax, [rdx-4]
0x18001370c  shr     eax, cl
0x18001370e  mov     [r8+1Ch], eax
0x180013712  mov     [r8+8], rdx
0x180013716  test    r10b, 2
0x18001371a  jz      short loc_18001372A
0x18001371c  mov     eax, [rdx]
0x18001371e  add     rdx, 4
0x180013722  mov     [r8+8], rdx
0x180013726  mov     [r8+20h], eax
0x18001372a  test    r10b, 4
0x18001372e  jz      short loc_180013757
0x180013730  movzx   ecx, byte ptr [rdx]
0x180013733  and     ecx, 0Fh
0x180013736  movsx   rax, byte ptr [rcx+r11+4D110h]
0x18001373f  mov     cl, [rcx+r11+4D120h]
0x180013747  sub     rdx, rax
0x18001374a  mov     eax, [rdx-4]
0x18001374d  shr     eax, cl
0x18001374f  mov     [r8+24h], eax
0x180013753  mov     [r8+8], rdx
0x180013757  mov     eax, [rdx]
0x180013759  lea     r9, [rdx+4]
0x18001375d  mov     [r8+28h], eax
0x180013761  mov     al, r10b
0x180013764  and     al, 30h
0x180013766  mov     [r8+8], r9
0x18001376a  test    r10b, 8
0x18001376e  jz      short loc_1800137AB
0x180013770  cmp     al, 10h
0x180013772  jnz     short loc_180013784
0x180013774  movsxd  rcx, dword ptr [r9]
0x180013777  lea     rax, [r9+4]
0x18001377b  mov     [r8+8], rax
0x18001377f  mov     [r8+30h], rcx
0x180013783  retn
0x180013784  cmp     al, 20h ; ' '
0x180013786  jnz     locret_18001383F
0x18001378c  movsxd  rax, dword ptr [r9]
0x18001378f  lea     rdx, [r9+4]
0x180013793  mov     [r8+8], rdx
0x180013797  mov     [r8+30h], rax
0x18001379b  lea     rax, [rdx+4]
0x18001379f  movsxd  rcx, dword ptr [rdx]
0x1800137a2  mov     [r8+8], rax
0x1800137a6  jmp     loc_18001383B
0x1800137ab  cmp     al, 10h
0x1800137ad  jnz     short loc_1800137DF
0x1800137af  movzx   ecx, byte ptr [r9]
0x1800137b3  and     ecx, 0Fh
0x1800137b6  movsx   rax, byte ptr [rcx+r11+4D110h]
0x1800137bf  mov     cl, [rcx+r11+4D120h]
0x1800137c7  sub     r9, rax
0x1800137ca  mov     eax, [r8+48h]
0x1800137ce  mov     edx, [r9-4]
0x1800137d2  shr     edx, cl
0x1800137d4  add     eax, edx
0x1800137d6  mov     [r8+8], r9
0x1800137da  mov     [r8+30h], rax
0x1800137de  retn
0x1800137df  cmp     al, 20h ; ' '
0x1800137e1  jnz     short locret_18001383F
0x1800137e3  movzx   ecx, byte ptr [r9]
0x1800137e7  mov     edx, [r8+48h]
0x1800137eb  and     ecx, 0Fh
0x1800137ee  movsx   rax, byte ptr [rcx+r11+4D110h]
0x1800137f7  mov     cl, [rcx+r11+4D120h]
0x1800137ff  sub     r9, rax
0x180013802  mov     eax, [r9-4]
0x180013806  shr     eax, cl
0x180013808  mov     [r8+8], r9
0x18001380c  lea     ecx, [rdx+rax]
0x18001380f  mov     [r8+30h], rcx
0x180013813  movzx   ecx, byte ptr [r9]
0x180013817  and     ecx, 0Fh
0x18001381a  movsx   rax, byte ptr [rcx+r11+4D110h]
0x180013823  mov     cl, [rcx+r11+4D120h]
0x18001382b  sub     r9, rax
0x18001382e  mov     eax, [r9-4]
0x180013832  shr     eax, cl
0x180013834  mov     [r8+8], r9
0x180013838  lea     ecx, [rdx+rax]
0x18001383b  mov     [r8+38h], rcx
0x18001383f  retn
```
