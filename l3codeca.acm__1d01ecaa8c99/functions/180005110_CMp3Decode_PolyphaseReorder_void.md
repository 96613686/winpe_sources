# CMp3Decode::PolyphaseReorder(void)

- ea: `0x180005110`
- end: `0x180005378`
- name: `?PolyphaseReorder@CMp3Decode@@IEAAXXZ`
- size: `616`
- prototype: `void __fastcall(CMp3Decode *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004910`
- `0x180004da0`

## callees

- `0x180005110`

## pseudocode

```c
void __fastcall CMp3Decode::PolyphaseReorder(CMp3Decode *this)
{
  int v1; // edi
  int i; // r11d
  __int64 v3; // r8
  __int64 j; // r9
  _DWORD *v5; // rdx
  __int64 v6; // rax

  if ( *((_DWORD *)this + 10300) )
  {
    v1 = 1;
  }
  else
  {
    v1 = *(_DWORD *)(*((_QWORD *)this + 3794) + 136LL);
    if ( v1 <= 0 )
      return;
  }
  for ( i = 0; i < v1; ++i )
  {
    v3 = 576LL * i;
    for ( j = 0; j != 18; ++j )
    {
      v5 = (_DWORD *)*((_QWORD *)this + 18 * i + j + 5112);
      *v5 = *((_DWORD *)this + v3 + j + 9072);
      v5[1] = *((_DWORD *)this + v3 + j + 9090);
      v5[2] = *((_DWORD *)this + v3 + j + 9108);
      v5[3] = *((_DWORD *)this + v3 + j + 9126);
      v5[4] = *((_DWORD *)this + v3 + j + 9144);
      v5[5] = *((_DWORD *)this + v3 + j + 9162);
      v5[6] = *((_DWORD *)this + v3 + j + 9180);
      v5[7] = *((_DWORD *)this + v3 + j + 9198);
      v5[8] = *((_DWORD *)this + v3 + j + 9216);
      v5[9] = *((_DWORD *)this + v3 + j + 9234);
      v5[10] = *((_DWORD *)this + j + v3 + 9252);
      v5[11] = *((_DWORD *)this + j + v3 + 9270);
      v5[12] = *((_DWORD *)this + v3 + j + 9288);
      v5[13] = *((_DWORD *)this + v3 + j + 9306);
      v5[14] = *((_DWORD *)this + v3 + j + 9324);
      v5[15] = *((_DWORD *)this + v3 + j + 9342);
      v5[16] = *((_DWORD *)this + v3 + j + 9360);
      v5[17] = *((_DWORD *)this + v3 + j + 9378);
      v5[18] = *((_DWORD *)this + v3 + j + 9396);
      v5[19] = *((_DWORD *)this + v3 + j + 9414);
      v5[20] = *((_DWORD *)this + v3 + j + 9432);
      v5[21] = *((_DWORD *)this + v3 + j + 9450);
      v5[22] = *((_DWORD *)this + v3 + j + 9468);
      v5[23] = *((_DWORD *)this + v3 + j + 9486);
      v5[24] = *((_DWORD *)this + v3 + j + 9504);
      v5[25] = *((_DWORD *)this + v3 + j + 9522);
      v5[26] = *((_DWORD *)this + v3 + j + 9540);
      v5[27] = *((_DWORD *)this + v3 + j + 9558);
      v5[28] = *((_DWORD *)this + v3 + j + 9576);
      v5[29] = *((_DWORD *)this + v3 + j + 9594);
      v6 = v3 + j;
      v5[30] = *((_DWORD *)this + v3 + j + 9612);
      v5[31] = *((_DWORD *)this + v6 + 9630);
    }
  }
}

```

## disassembly

```asm
0x180005110  push    rdi
0x180005112  cmp     dword ptr [rcx+0A0F0h], 0
0x180005119  mov     r10, rcx
0x18000511c  jz      short loc_180005125
0x18000511e  mov     edi, 1
0x180005123  jmp     short loc_18000513A
0x180005125  mov     rax, [rcx+7690h]
0x18000512c  mov     edi, [rax+88h]
0x180005132  test    edi, edi
0x180005134  jle     loc_180005376
0x18000513a  mov     [rsp+8+arg_0], rbx
0x18000513f  xor     r11d, r11d
0x180005142  mov     [rsp+8+arg_8], rsi
0x180005147  lea     rsi, [rcx+9FC0h]
0x18000514e  xchg    ax, ax
0x180005150  movsxd  rax, r11d
0x180005153  lea     rbx, [rax+rax*8]
0x180005157  shl     rbx, 4
0x18000515b  lea     r8, [rax+rax*8]
0x18000515f  add     rbx, rsi
0x180005162  shl     r8, 6
0x180005166  xor     r9d, r9d
0x180005169  nop     dword ptr [rax+00000000h]
0x180005170  mov     rdx, [rbx+r9*8]
0x180005174  lea     rax, [r8+r9]
0x180005178  mov     ecx, [r10+rax*4+8DC0h]
0x180005180  lea     rax, [r8+r9]
0x180005184  mov     [rdx], ecx
0x180005186  mov     ecx, [r10+rax*4+8E08h]
0x18000518e  lea     rax, [r8+r9]
0x180005192  mov     [rdx+4], ecx
0x180005195  mov     ecx, [r10+rax*4+8E50h]
0x18000519d  lea     rax, [r8+r9]
0x1800051a1  mov     [rdx+8], ecx
0x1800051a4  mov     ecx, [r10+rax*4+8E98h]
0x1800051ac  lea     rax, [r8+r9]
0x1800051b0  mov     [rdx+0Ch], ecx
0x1800051b3  mov     ecx, [r10+rax*4+8EE0h]
0x1800051bb  lea     rax, [r8+r9]
0x1800051bf  mov     [rdx+10h], ecx
0x1800051c2  mov     ecx, [r10+rax*4+8F28h]
0x1800051ca  lea     rax, [r8+r9]
0x1800051ce  mov     [rdx+14h], ecx
0x1800051d1  mov     ecx, [r10+rax*4+8F70h]
0x1800051d9  lea     rax, [r8+r9]
0x1800051dd  mov     [rdx+18h], ecx
0x1800051e0  mov     ecx, [r10+rax*4+8FB8h]
0x1800051e8  lea     rax, [r8+r9]
0x1800051ec  mov     [rdx+1Ch], ecx
0x1800051ef  mov     ecx, [r10+rax*4+9000h]
0x1800051f7  lea     rax, [r8+r9]
0x1800051fb  mov     [rdx+20h], ecx
0x1800051fe  mov     ecx, [r10+rax*4+9048h]
0x180005206  lea     rax, [r9+r8]
0x18000520a  mov     [rdx+24h], ecx
0x18000520d  mov     ecx, [r10+rax*4+9090h]
0x180005215  lea     rax, [r9+r8]
0x180005219  mov     [rdx+28h], ecx
0x18000521c  mov     ecx, [r10+rax*4+90D8h]
0x180005224  lea     rax, [r8+r9]
0x180005228  mov     [rdx+2Ch], ecx
0x18000522b  mov     ecx, [r10+rax*4+9120h]
0x180005233  lea     rax, [r8+r9]
0x180005237  mov     [rdx+30h], ecx
0x18000523a  mov     ecx, [r10+rax*4+9168h]
0x180005242  lea     rax, [r8+r9]
0x180005246  mov     [rdx+34h], ecx
0x180005249  mov     ecx, [r10+rax*4+91B0h]
0x180005251  lea     rax, [r8+r9]
0x180005255  mov     [rdx+38h], ecx
0x180005258  mov     ecx, [r10+rax*4+91F8h]
0x180005260  lea     rax, [r8+r9]
0x180005264  mov     [rdx+3Ch], ecx
0x180005267  mov     ecx, [r10+rax*4+9240h]
0x18000526f  lea     rax, [r8+r9]
0x180005273  mov     [rdx+40h], ecx
0x180005276  mov     ecx, [r10+rax*4+9288h]
0x18000527e  lea     rax, [r8+r9]
0x180005282  mov     [rdx+44h], ecx
0x180005285  mov     ecx, [r10+rax*4+92D0h]
0x18000528d  lea     rax, [r8+r9]
0x180005291  mov     [rdx+48h], ecx
0x180005294  mov     ecx, [r10+rax*4+9318h]
0x18000529c  lea     rax, [r8+r9]
0x1800052a0  mov     [rdx+4Ch], ecx
0x1800052a3  mov     ecx, [r10+rax*4+9360h]
0x1800052ab  lea     rax, [r8+r9]
0x1800052af  mov     [rdx+50h], ecx
0x1800052b2  mov     ecx, [r10+rax*4+93A8h]
0x1800052ba  lea     rax, [r8+r9]
0x1800052be  mov     [rdx+54h], ecx
0x1800052c1  mov     ecx, [r10+rax*4+93F0h]
0x1800052c9  lea     rax, [r8+r9]
0x1800052cd  mov     [rdx+58h], ecx
0x1800052d0  mov     ecx, [r10+rax*4+9438h]
0x1800052d8  lea     rax, [r8+r9]
0x1800052dc  mov     [rdx+5Ch], ecx
0x1800052df  mov     ecx, [r10+rax*4+9480h]
0x1800052e7  lea     rax, [r8+r9]
0x1800052eb  mov     [rdx+60h], ecx
0x1800052ee  mov     ecx, [r10+rax*4+94C8h]
0x1800052f6  lea     rax, [r8+r9]
0x1800052fa  mov     [rdx+64h], ecx
0x1800052fd  mov     ecx, [r10+rax*4+9510h]
0x180005305  mov     [rdx+68h], ecx
0x180005308  lea     rax, [r8+r9]
0x18000530c  mov     ecx, [r10+rax*4+9558h]
0x180005314  lea     rax, [r8+r9]
0x180005318  mov     [rdx+6Ch], ecx
0x18000531b  mov     ecx, [r10+rax*4+95A0h]
0x180005323  lea     rax, [r8+r9]
0x180005327  mov     [rdx+70h], ecx
0x18000532a  mov     ecx, [r10+rax*4+95E8h]
0x180005332  lea     rax, [r8+r9]
0x180005336  mov     [rdx+74h], ecx
0x180005339  mov     ecx, [r10+rax*4+9630h]
0x180005341  lea     rax, [r8+r9]
0x180005345  mov     [rdx+78h], ecx
0x180005348  inc     r9
0x18000534b  mov     ecx, [r10+rax*4+9678h]
0x180005353  mov     [rdx+7Ch], ecx
0x180005356  cmp     r9, 12h
0x18000535a  jnz     loc_180005170
0x180005360  inc     r11d
0x180005363  cmp     r11d, edi
0x180005366  jl      loc_180005150
0x18000536c  mov     rsi, [rsp+8+arg_8]
0x180005371  mov     rbx, [rsp+8+arg_0]
0x180005376  pop     rdi
0x180005377  retn
```
