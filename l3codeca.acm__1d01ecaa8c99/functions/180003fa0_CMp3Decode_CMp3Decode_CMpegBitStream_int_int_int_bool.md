# CMp3Decode::CMp3Decode(CMpegBitStream &,int,int,int,bool *)

- ea: `0x180003fa0`
- end: `0x1800044cb`
- name: `??0CMp3Decode@@QEAA@AEAVCMpegBitStream@@HHHPEA_N@Z`
- size: `1323`
- prototype: `CMp3Decode *__fastcall(CMp3Decode *this, struct CMpegBitStream *, int, int, int, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180003a70`

## callees

- `0x180001cd4`
- `0x180002290`
- `0x180003fa0`
- `0x180005000`
- `0x18000e130`
- `0x18000f9c0`

## pseudocode

```c
CMp3Decode *__fastcall CMp3Decode::CMp3Decode(
        CMp3Decode *this,
        struct CMpegBitStream *a2,
        int a3,
        int a4,
        int a5,
        bool *a6)
{
  __int64 v7; // rdi
  char *v8; // rcx
  __int64 v12; // r10
  void *v13; // rax
  unsigned __int64 v14; // rax
  int v15; // ecx
  int v16; // eax
  bool v17; // zf
  void *v18; // rax
  unsigned __int64 v19; // rcx

  v7 = 0;
  *((_QWORD *)this + 1) = &CHuffmanTable::`vftable';
  *((_DWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = (char *)this + 8;
  *((_QWORD *)this + 3) = &CHuffmanBitObj::`vftable';
  v8 = (char *)this + 80;
  *((_QWORD *)this + 6) = &CHuffmanTable::`vftable';
  *((_QWORD *)this + 8) = &CHuffmanTable::`vftable';
  *((_QWORD *)this + 7) = 1;
  *(_QWORD *)this = &CMp3Huffman::`vftable';
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)v8 + 27) = (char *)this + 30312;
  *((_DWORD *)v8 + 1208) = a3;
  CMdct::Init((CMdct *)v8);
  *((_QWORD *)this + 619) = v12;
  *((_DWORD *)this + 1240) = a3;
  *((_DWORD *)this + 1241) = a4;
  *((_DWORD *)this + 1242) = a5;
  *((_QWORD *)this + 618) = 0;
  *((_QWORD *)this + 616) = 0;
  *((_QWORD *)this + 617) = 0;
  if ( !*a6 )
  {
    v13 = operator new[](0x1010u);
    *((_QWORD *)this + 618) = v13;
    if ( v13 )
    {
      v14 = ((unsigned __int64)v13 + 15) & 0xFFFFFFFFFFFFFFF0uLL;
      *((_QWORD *)this + 616) = v14;
      *((_QWORD *)this + 617) = v14 + 2048;
      do
        memset_0(*((void **)this + v7++ + 616), 0, 0x800u);
      while ( v7 != 2 );
      *((_DWORD *)this + 1230) = 32;
    }
    else
    {
      *a6 = 1;
    }
  }
  CErrorConcealment::Init((CMp3Decode *)((char *)this + 4976));
  *((_QWORD *)this + 3794) = a2;
  *((_QWORD *)this + 3795) = &CBitStream::`vftable';
  v15 = 0;
  v16 = 1;
  do
  {
    if ( v16 >= 2048 )
      break;
    ++v15;
    v16 = __ROL4__(v16, 1);
  }
  while ( v15 < 16 );
  *((_DWORD *)this + 7594) = 1 << v15;
  *((_DWORD *)this + 7595) = 8 * (1 << v15);
  *((_QWORD *)this + 3801) = operator new[](1 << v15);
  *((_QWORD *)this + 3796) = 0;
  *((_BYTE *)this + 30416) = 1;
  *((_QWORD *)this + 3798) = 0;
  *((_QWORD *)this + 3799) = 0;
  *((_BYTE *)this + 30400) = 0;
  *((_DWORD *)this + 10298) = a3;
  *((_DWORD *)this + 10299) = a4;
  *((_DWORD *)this + 10300) = a5;
  memset_0((char *)this + 30896, 0, 0x310u);
  v17 = !*a6;
  *((_QWORD *)this + 5148) = 0;
  *((_QWORD *)this + 5112) = 0;
  *((_QWORD *)this + 5113) = 0;
  *((_QWORD *)this + 5114) = 0;
  *((_QWORD *)this + 5115) = 0;
  *((_QWORD *)this + 5116) = 0;
  *((_QWORD *)this + 5117) = 0;
  *((_QWORD *)this + 5118) = 0;
  *((_QWORD *)this + 5119) = 0;
  *((_QWORD *)this + 5120) = 0;
  *((_QWORD *)this + 5121) = 0;
  *((_QWORD *)this + 5122) = 0;
  *((_QWORD *)this + 5123) = 0;
  *((_QWORD *)this + 5124) = 0;
  *((_QWORD *)this + 5125) = 0;
  *((_QWORD *)this + 5126) = 0;
  *((_QWORD *)this + 5127) = 0;
  *((_QWORD *)this + 5128) = 0;
  *((_QWORD *)this + 5129) = 0;
  *((_QWORD *)this + 5130) = 0;
  *((_QWORD *)this + 5131) = 0;
  *((_QWORD *)this + 5132) = 0;
  *((_QWORD *)this + 5133) = 0;
  *((_QWORD *)this + 5134) = 0;
  *((_QWORD *)this + 5135) = 0;
  *((_QWORD *)this + 5136) = 0;
  *((_QWORD *)this + 5137) = 0;
  *((_QWORD *)this + 5138) = 0;
  *((_QWORD *)this + 5139) = 0;
  *((_QWORD *)this + 5140) = 0;
  *((_QWORD *)this + 5141) = 0;
  *((_QWORD *)this + 5142) = 0;
  *((_QWORD *)this + 5143) = 0;
  *((_QWORD *)this + 5144) = 0;
  *((_QWORD *)this + 5145) = 0;
  *((_QWORD *)this + 5146) = 0;
  *((_QWORD *)this + 5147) = 0;
  if ( v17 )
  {
    v18 = operator new[](0x1210u);
    *((_QWORD *)this + 5148) = v18;
    if ( v18 )
    {
      v19 = ((unsigned __int64)v18 + 15) & 0xFFFFFFFFFFFFFFF0uLL;
      v17 = !*a6;
      *((_QWORD *)this + 5112) = v19;
      *((_QWORD *)this + 5113) = v19 + 128;
      *((_QWORD *)this + 5114) = v19 + 256;
      *((_QWORD *)this + 5115) = v19 + 384;
      *((_QWORD *)this + 5116) = v19 + 512;
      *((_QWORD *)this + 5117) = v19 + 640;
      *((_QWORD *)this + 5118) = v19 + 768;
      *((_QWORD *)this + 5119) = v19 + 896;
      *((_QWORD *)this + 5120) = v19 + 1024;
      *((_QWORD *)this + 5121) = v19 + 1152;
      *((_QWORD *)this + 5122) = v19 + 1280;
      *((_QWORD *)this + 5123) = v19 + 1408;
      *((_QWORD *)this + 5124) = v19 + 1536;
      *((_QWORD *)this + 5125) = v19 + 1664;
      *((_QWORD *)this + 5126) = v19 + 1792;
      *((_QWORD *)this + 5127) = v19 + 1920;
      *((_QWORD *)this + 5128) = v19 + 2048;
      *((_QWORD *)this + 5129) = v19 + 2176;
      *((_QWORD *)this + 5130) = v19 + 2304;
      *((_QWORD *)this + 5131) = v19 + 2432;
      *((_QWORD *)this + 5132) = v19 + 2560;
      *((_QWORD *)this + 5133) = v19 + 2688;
      *((_QWORD *)this + 5134) = v19 + 2816;
      *((_QWORD *)this + 5135) = v19 + 2944;
      *((_QWORD *)this + 5136) = v19 + 3072;
      *((_QWORD *)this + 5137) = v19 + 3200;
      *((_QWORD *)this + 5138) = v19 + 3328;
      *((_QWORD *)this + 5139) = v19 + 3456;
      *((_QWORD *)this + 5140) = v19 + 3584;
      *((_QWORD *)this + 5141) = v19 + 3712;
      *((_QWORD *)this + 5142) = v19 + 3840;
      *((_QWORD *)this + 5143) = v19 + 3968;
      *((_QWORD *)this + 5144) = v19 + 4096;
      *((_QWORD *)this + 5145) = v19 + 4224;
      *((_QWORD *)this + 5146) = v19 + 4352;
      *((_QWORD *)this + 5147) = v19 + 4480;
      if ( v17 )
        CMp3Decode::Init(this, 1);
    }
    else
    {
      *a6 = 1;
    }
  }
  return this;
}

```

## disassembly

```asm
0x180003fa0  push    rbx
0x180003fa2  push    rbp
0x180003fa3  push    rsi
0x180003fa4  push    rdi
0x180003fa5  push    r12
0x180003fa7  push    r13
0x180003fa9  push    r14
0x180003fab  push    r15
0x180003fad  sub     rsp, 28h
0x180003fb1  mov     rbx, rcx
0x180003fb4  lea     rax, [rcx+8]
0x180003fb8  lea     rcx, ??_7CHuffmanTable@@6B@; const CHuffmanTable::`vftable'
0x180003fbf  xor     edi, edi
0x180003fc1  mov     [rax], rcx
0x180003fc4  mov     esi, 1
0x180003fc9  mov     [rax+8], edi
0x180003fcc  lea     rcx, ??_7CHuffmanBitObj@@6B@; const CHuffmanBitObj::`vftable'
0x180003fd3  mov     [rbx+28h], rax
0x180003fd7  lea     r10, [rbx+7668h]
0x180003fde  lea     rax, ??_7CHuffmanTable@@6B@; const CHuffmanTable::`vftable'
0x180003fe5  mov     [rbx+18h], rcx
0x180003fe9  lea     rcx, [rbx+50h]; this
0x180003fed  mov     [rbx+30h], rax
0x180003ff1  mov     [rbx+40h], rax
0x180003ff5  mov     r12d, r9d
0x180003ff8  lea     rax, ??_7CMp3Huffman@@6B@; const CMp3Huffman::`vftable'
0x180003fff  mov     [rbx+38h], rsi
0x180004003  mov     [rbx], rax
0x180004006  mov     ebp, r8d
0x180004009  mov     r15, rdx
0x18000400c  mov     [rbx+48h], rdi
0x180004010  mov     [rcx+0D8h], r10
0x180004017  mov     [rcx+12E0h], r8d
0x18000401e  call    ?Init@CMdct@@QEAAXXZ; CMdct::Init(void)
0x180004023  mov     r14, [rsp+68h+arg_28]
0x18000402b  mov     r13d, [rsp+68h+arg_20]
0x180004033  mov     [rbx+1358h], r10
0x18000403a  mov     [rbx+1360h], ebp
0x180004040  mov     [rbx+1364h], r12d
0x180004047  mov     [rbx+1368h], r13d
0x18000404e  mov     [rbx+1350h], rdi
0x180004055  mov     [rbx+1340h], rdi
0x18000405c  mov     [rbx+1348h], rdi
0x180004063  cmp     [r14], dil
0x180004066  jnz     short loc_1800040CA
0x180004068  mov     ecx, 1010h; unsigned __int64
0x18000406d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180004072  mov     [rbx+1350h], rax
0x180004079  test    rax, rax
0x18000407c  jnz     short loc_180004083
0x18000407e  mov     [r14], sil
0x180004081  jmp     short loc_1800040CA
0x180004083  add     rax, 0Fh
0x180004087  and     rax, 0FFFFFFFFFFFFFFF0h
0x18000408b  mov     [rbx+1340h], rax
0x180004092  add     rax, 800h
0x180004098  mov     [rbx+1348h], rax
0x18000409f  nop
0x1800040a0  mov     rcx, [rbx+rdi*8+1340h]; void *
0x1800040a8  xor     edx, edx; Val
0x1800040aa  mov     r8d, 800h; Size
0x1800040b0  call    memset_0
0x1800040b5  inc     rdi
0x1800040b8  cmp     rdi, 2
0x1800040bc  jnz     short loc_1800040A0
0x1800040be  mov     dword ptr [rbx+1338h], 20h ; ' '
0x1800040c8  xor     edi, edi
0x1800040ca  lea     rcx, [rbx+1370h]; this
0x1800040d1  call    ?Init@CErrorConcealment@@QEAAXXZ; CErrorConcealment::Init(void)
0x1800040d6  lea     rax, ??_7CBitStream@@6B@; const CBitStream::`vftable'
0x1800040dd  mov     [rbx+7690h], r15
0x1800040e4  mov     [rbx+7698h], rax
0x1800040eb  mov     ecx, edi
0x1800040ed  mov     eax, esi
0x1800040ef  nop
0x1800040f0  cmp     eax, 800h
0x1800040f5  jge     short loc_180004100
0x1800040f7  inc     ecx
0x1800040f9  rol     eax, 1
0x1800040fb  cmp     ecx, 10h
0x1800040fe  jl      short loc_1800040F0
0x180004100  shl     esi, cl
0x180004102  movsxd  rcx, esi; unsigned __int64
0x180004105  mov     [rbx+76A8h], esi
0x18000410b  lea     eax, ds:0[rsi*8]
0x180004112  mov     [rbx+76ACh], eax
0x180004118  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000411d  mov     [rbx+76C8h], rax
0x180004124  lea     rcx, [rbx+78B0h]; void *
0x18000412b  mov     [rbx+76A0h], rdi
0x180004132  xor     edx, edx; Val
0x180004134  mov     byte ptr [rbx+76D0h], 1
0x18000413b  mov     r8d, 310h; Size
0x180004141  mov     qword ptr [rbx+76B0h], 0
0x18000414c  mov     qword ptr [rbx+76B8h], 0
0x180004157  mov     byte ptr [rbx+76C0h], 0
0x18000415e  mov     [rbx+0A0E8h], ebp
0x180004164  mov     [rbx+0A0ECh], r12d
0x18000416b  mov     [rbx+0A0F0h], r13d
0x180004172  call    memset_0
0x180004177  cmp     byte ptr [r14], 0
0x18000417b  mov     [rbx+0A0E0h], rdi
0x180004182  mov     [rbx+9FC0h], rdi
0x180004189  mov     [rbx+9FC8h], rdi
0x180004190  mov     [rbx+9FD0h], rdi
0x180004197  mov     [rbx+9FD8h], rdi
0x18000419e  mov     [rbx+9FE0h], rdi
0x1800041a5  mov     [rbx+9FE8h], rdi
0x1800041ac  mov     [rbx+9FF0h], rdi
0x1800041b3  mov     [rbx+9FF8h], rdi
0x1800041ba  mov     [rbx+0A000h], rdi
0x1800041c1  mov     [rbx+0A008h], rdi
0x1800041c8  mov     [rbx+0A010h], rdi
0x1800041cf  mov     [rbx+0A018h], rdi
0x1800041d6  mov     [rbx+0A020h], rdi
0x1800041dd  mov     [rbx+0A028h], rdi
0x1800041e4  mov     [rbx+0A030h], rdi
0x1800041eb  mov     [rbx+0A038h], rdi
0x1800041f2  mov     [rbx+0A040h], rdi
0x1800041f9  mov     [rbx+0A048h], rdi
0x180004200  mov     [rbx+0A050h], rdi
0x180004207  mov     [rbx+0A058h], rdi
0x18000420e  mov     [rbx+0A060h], rdi
0x180004215  mov     [rbx+0A068h], rdi
0x18000421c  mov     [rbx+0A070h], rdi
0x180004223  mov     [rbx+0A078h], rdi
0x18000422a  mov     [rbx+0A080h], rdi
0x180004231  mov     [rbx+0A088h], rdi
0x180004238  mov     [rbx+0A090h], rdi
0x18000423f  mov     [rbx+0A098h], rdi
0x180004246  mov     [rbx+0A0A0h], rdi
0x18000424d  mov     [rbx+0A0A8h], rdi
0x180004254  mov     [rbx+0A0B0h], rdi
0x18000425b  mov     [rbx+0A0B8h], rdi
0x180004262  mov     [rbx+0A0C0h], rdi
0x180004269  mov     [rbx+0A0C8h], rdi
0x180004270  mov     [rbx+0A0D0h], rdi
0x180004277  mov     [rbx+0A0D8h], rdi
0x18000427e  jnz     loc_1800044B7
0x180004284  mov     ecx, 1210h; unsigned __int64
0x180004289  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000428e  mov     [rbx+0A0E0h], rax
0x180004295  mov     rcx, rax
0x180004298  test    rax, rax
0x18000429b  jnz     short loc_1800042A6
0x18000429d  mov     byte ptr [r14], 1
0x1800042a1  jmp     loc_1800044B7
0x1800042a6  add     rax, 0Fh
0x1800042aa  add     rcx, 0Fh
0x1800042ae  and     rax, 0FFFFFFFFFFFFFFF0h
0x1800042b2  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800042b6  cmp     byte ptr [r14], 0
0x1800042ba  mov     [rbx+9FC0h], rax
0x1800042c1  lea     rax, [rcx+80h]
0x1800042c8  mov     [rbx+9FC8h], rax
0x1800042cf  lea     rax, [rcx+100h]
0x1800042d6  mov     [rbx+9FD0h], rax
0x1800042dd  lea     rax, [rcx+180h]
0x1800042e4  mov     [rbx+9FD8h], rax
0x1800042eb  lea     rax, [rcx+200h]
0x1800042f2  mov     [rbx+9FE0h], rax
0x1800042f9  lea     rax, [rcx+280h]
0x180004300  mov     [rbx+9FE8h], rax
0x180004307  lea     rax, [rcx+300h]
0x18000430e  mov     [rbx+9FF0h], rax
0x180004315  lea     rax, [rcx+380h]
0x18000431c  mov     [rbx+9FF8h], rax
0x180004323  lea     rax, [rcx+400h]
0x18000432a  mov     [rbx+0A000h], rax
0x180004331  lea     rax, [rcx+480h]
0x180004338  mov     [rbx+0A008h], rax
0x18000433f  lea     rax, [rcx+500h]
0x180004346  mov     [rbx+0A010h], rax
0x18000434d  lea     rax, [rcx+580h]
0x180004354  mov     [rbx+0A018h], rax
0x18000435b  lea     rax, [rcx+600h]
0x180004362  mov     [rbx+0A020h], rax
0x180004369  lea     rax, [rcx+680h]
0x180004370  mov     [rbx+0A028h], rax
0x180004377  lea     rax, [rcx+700h]
0x18000437e  mov     [rbx+0A030h], rax
0x180004385  lea     rax, [rcx+780h]
0x18000438c  mov     [rbx+0A038h], rax
0x180004393  lea     rax, [rcx+800h]
0x18000439a  mov     [rbx+0A040h], rax
0x1800043a1  lea     rax, [rcx+880h]
0x1800043a8  mov     [rbx+0A048h], rax
0x1800043af  lea     rax, [rcx+900h]
0x1800043b6  mov     [rbx+0A050h], rax
0x1800043bd  lea     rax, [rcx+980h]
0x1800043c4  mov     [rbx+0A058h], rax
0x1800043cb  lea     rax, [rcx+0A00h]
0x1800043d2  mov     [rbx+0A060h], rax
0x1800043d9  lea     rax, [rcx+0A80h]
0x1800043e0  mov     [rbx+0A068h], rax
0x1800043e7  lea     rax, [rcx+0B00h]
0x1800043ee  mov     [rbx+0A070h], rax
0x1800043f5  lea     rax, [rcx+0B80h]
0x1800043fc  mov     [rbx+0A078h], rax
0x180004403  lea     rax, [rcx+0C00h]
0x18000440a  mov     [rbx+0A080h], rax
0x180004411  lea     rax, [rcx+0C80h]
0x180004418  mov     [rbx+0A088h], rax
0x18000441f  lea     rax, [rcx+0D00h]
0x180004426  mov     [rbx+0A090h], rax
0x18000442d  lea     rax, [rcx+0D80h]
0x180004434  mov     [rbx+0A098h], rax
0x18000443b  lea     rax, [rcx+0E00h]
0x180004442  mov     [rbx+0A0A0h], rax
0x180004449  lea     rax, [rcx+0E80h]
0x180004450  mov     [rbx+0A0A8h], rax
0x180004457  lea     rax, [rcx+0F00h]
0x18000445e  mov     [rbx+0A0B0h], rax
0x180004465  lea     rax, [rcx+0F80h]
0x18000446c  mov     [rbx+0A0B8h], rax
0x180004473  lea     rax, [rcx+1000h]
0x18000447a  mov     [rbx+0A0C0h], rax
0x180004481  lea     rax, [rcx+1080h]
0x180004488  mov     [rbx+0A0C8h], rax
0x18000448f  lea     rax, [rcx+1100h]
0x180004496  mov     [rbx+0A0D0h], rax
0x18000449d  lea     rax, [rcx+1180h]
0x1800044a4  mov     [rbx+0A0D8h], rax
0x1800044ab  jnz     short loc_1800044B7
0x1800044ad  mov     dl, 1; bool
0x1800044af  mov     rcx, rbx; this
0x1800044b2  call    ?Init@CMp3Decode@@QEAAX_N@Z; CMp3Decode::Init(bool)
0x1800044b7  mov     rax, rbx
0x1800044ba  add     rsp, 28h
0x1800044be  pop     r15
0x1800044c0  pop     r14
0x1800044c2  pop     r13
0x1800044c4  pop     r12
0x1800044c6  pop     rdi
0x1800044c7  pop     rsi
0x1800044c8  pop     rbp
0x1800044c9  pop     rbx
0x1800044ca  retn
```
