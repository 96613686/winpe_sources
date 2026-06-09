# CdpUpdateDisplay

- ea: `0x140008fb4`
- end: `0x1400091ba`
- name: `CdpUpdateDisplay`
- size: `518`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140008cd0`

## callees

- `0x140001154`
- `0x140001500`
- `0x140001e20`
- `0x140008164`
- `0x1400081e8`
- `0x140008fb4`

## import_xrefs

- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140009006`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140009006`
- `ntoskrnl!ProbeForWrite` at `0x14000906e`
- `ntoskrnl!ProbeForWrite` at `0x14000906e`
- `ntoskrnl!ProbeForRead` at `0x140009050`
- `ntoskrnl!ProbeForRead` at `0x140009050`
- `ntoskrnl!BgkDisplayCharacter` at `0x140009158`
- `ntoskrnl!BgkDisplayCharacter` at `0x140009158`

## pseudocode

```c
__int64 __fastcall CdpUpdateDisplay(char a1, void *a2, unsigned int a3)
{
  unsigned int i; // ebx
  char *v6; // rcx
  int Buf2; // [rsp+38h] [rbp-50h] BYREF
  volatile void *v8[2]; // [rsp+40h] [rbp-48h] BYREF
  volatile void *Address; // [rsp+50h] [rbp-38h]
  unsigned int Buf1; // [rsp+A8h] [rbp+20h] BYREF

  *(_OWORD *)v8 = 0;
  LOWORD(Address) = 0;
  Buf2 = 0;
  Buf1 = 0;
  if ( a3 < 0x18 )
    return 3221225990LL;
  if ( a1 )
  {
    if ( ((unsigned __int8)a2 & 3) != 0 )
      ExRaiseDatatypeMisalignment();
    RtlCopyFromUser(v8, a2, 0x18u);
  }
  else
  {
    RtlCopyVolatileMemory(v8, a2, 0x18u);
  }
  if ( a1 )
  {
    ProbeForRead(Address, 4LL * (unsigned int)dword_1400051A8, 4u);
    ProbeForWrite(v8[1], 4LL * (unsigned int)dword_1400051A8, 4u);
  }
  if ( SLOWORD(v8[0]) < 0 || SLOWORD(v8[0]) >= (unsigned int)dword_1400051AC )
    return 3221225485LL;
  for ( i = 0; i < dword_1400051A8; ++i )
  {
    if ( a1 )
      Buf2 = RtlReadULongFromUser((char *)v8[1] + 4 * i);
    else
      RtlCopyVolatileMemory(&Buf2, (char *)v8[1] + 4 * i, 4u);
    if ( a1 )
      Buf1 = RtlReadULongFromUser((char *)Address + 4 * i);
    else
      RtlCopyVolatileMemory(&Buf1, (char *)Address + 4 * i, 4u);
    if ( memcmp(&Buf1, &Buf2, 4u) )
    {
      BgkDisplayCharacter(
        (unsigned __int16)Buf1,
        i,
        (unsigned int)SLOWORD(v8[0]),
        *((unsigned int *)CdpPalette + (BYTE2(Buf1) & 0xF)),
        *((_DWORD *)CdpPalette + (((unsigned __int64)HIWORD(Buf1) >> 4) & 0xF)));
      v6 = (char *)v8[1] + 4 * i;
      if ( a1 )
        RtlWriteULongToUser(v6, Buf1);
      else
        RtlCopyVolatileMemory(v6, &Buf1, 4u);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140008fb4  mov     r11, rsp
0x140008fb7  mov     [r11+10h], rbx
0x140008fbb  mov     [rsp+arg_0], cl
0x140008fbf  push    rsi
0x140008fc0  push    rdi
0x140008fc1  push    r12
0x140008fc3  push    r14
0x140008fc5  push    r15
0x140008fc7  sub     rsp, 60h
0x140008fcb  mov     dil, cl
0x140008fce  xor     eax, eax
0x140008fd0  xorps   xmm0, xmm0
0x140008fd3  movups  xmmword ptr [rsp+88h+var_48], xmm0
0x140008fd8  mov     word ptr [rsp+88h+Address], ax
0x140008fdd  mov     [rsp+88h+Buf2], eax
0x140008fe1  mov     [r11+20h], eax
0x140008fe5  mov     eax, 18h
0x140008fea  cmp     r8d, eax
0x140008fed  jnb     short loc_140008FF9
0x140008fef  mov     eax, 0C0000206h
0x140008ff4  jmp     loc_1400091A4
0x140008ff9  xor     r15d, r15d
0x140008ffc  test    dil, dil
0x140008fff  jz      short loc_140009027
0x140009001  test    dl, 3
0x140009004  jz      short loc_140009013
0x140009006  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14000900d  nop     dword ptr [rax+rax+00h]
0x140009012  int     3; Trap to Debugger
0x140009013  test    dil, dil
0x140009016  jz      short loc_140009027
0x140009018  mov     r8, rax; Size
0x14000901b  lea     rcx, [rsp+88h+var_48]; void *
0x140009020  call    RtlCopyFromUser
0x140009025  jmp     short loc_140009034
0x140009027  mov     r8, rax; Size
0x14000902a  lea     rcx, [rsp+88h+var_48]; void *
0x14000902f  call    RtlCopyVolatileMemory
0x140009034  mov     esi, 4
0x140009039  test    dil, dil
0x14000903c  jz      short loc_14000907B
0x14000903e  mov     edx, dword ptr cs:qword_1400051A8
0x140009044  shl     rdx, 2; Length
0x140009048  mov     r8d, esi; Alignment
0x14000904b  mov     rcx, [rsp+88h+Address]; Address
0x140009050  call    cs:__imp_ProbeForRead
0x140009057  nop     dword ptr [rax+rax+00h]
0x14000905c  mov     edx, dword ptr cs:qword_1400051A8
0x140009062  shl     rdx, 2; Length
0x140009066  mov     r8d, esi; Alignment
0x140009069  mov     rcx, [rsp+88h+var_48+8]; Address
0x14000906e  call    cs:__imp_ProbeForWrite
0x140009075  nop     dword ptr [rax+rax+00h]
0x14000907a  nop
0x14000907b  movsx   eax, word ptr [rsp+88h+var_48]
0x140009080  test    ax, ax
0x140009083  js      loc_14000919D
0x140009089  cmp     eax, dword ptr cs:qword_1400051A8+4
0x14000908f  jnb     loc_14000919D
0x140009095  mov     ebx, r15d
0x140009098  lea     r12, CdpPalette
0x14000909f  mov     [rsp+88h+var_58], ebx
0x1400090a3  cmp     ebx, dword ptr cs:qword_1400051A8
0x1400090a9  jnb     loc_140009197
0x1400090af  mov     r14d, ebx
0x1400090b2  mov     rax, [rsp+88h+var_48+8]
0x1400090b7  lea     rdx, [rax+r14*4]; Src
0x1400090bb  test    dil, dil
0x1400090be  jz      short loc_1400090CE
0x1400090c0  mov     rcx, rdx
0x1400090c3  call    RtlReadULongFromUser
0x1400090c8  mov     [rsp+88h+Buf2], eax
0x1400090cc  jmp     short loc_1400090DB
0x1400090ce  mov     r8, rsi; Size
0x1400090d1  lea     rcx, [rsp+88h+Buf2]; void *
0x1400090d6  call    RtlCopyVolatileMemory
0x1400090db  mov     rax, [rsp+88h+Address]
0x1400090e0  lea     rdx, [rax+r14*4]; Src
0x1400090e4  test    dil, dil
0x1400090e7  jz      short loc_1400090FA
0x1400090e9  mov     rcx, rdx
0x1400090ec  call    RtlReadULongFromUser
0x1400090f1  mov     [rsp+88h+Buf1], eax
0x1400090f8  jmp     short loc_14000910A
0x1400090fa  mov     r8, rsi; Size
0x1400090fd  lea     rcx, [rsp+88h+Buf1]; void *
0x140009105  call    RtlCopyVolatileMemory
0x14000910a  mov     r8, rsi; Size
0x14000910d  lea     rdx, [rsp+88h+Buf2]; Buf2
0x140009112  lea     rcx, [rsp+88h+Buf1]; Buf1
0x14000911a  call    memcmp
0x14000911f  test    eax, eax
0x140009121  jnz     short loc_140009125
0x140009123  jmp     short loc_140009190
0x140009125  movzx   r9d, word ptr [rsp+88h+Buf1+2]
0x14000912e  mov     eax, r9d
0x140009131  shr     rax, 4
0x140009135  and     eax, 0Fh
0x140009138  and     r9d, 0Fh
0x14000913c  movsx   r8d, word ptr [rsp+88h+var_48]
0x140009142  mov     eax, [r12+rax*4]
0x140009146  mov     [rsp+88h+var_68], eax
0x14000914a  mov     r9d, [r12+r9*4]
0x14000914e  mov     edx, ebx
0x140009150  movzx   ecx, word ptr [rsp+88h+Buf1]
0x140009158  call    cs:__imp_BgkDisplayCharacter
0x14000915f  nop     dword ptr [rax+rax+00h]
0x140009164  mov     rax, [rsp+88h+var_48+8]
0x140009169  lea     rcx, [rax+r14*4]; void *
0x14000916d  test    dil, dil
0x140009170  jz      short loc_140009180
0x140009172  mov     edx, [rsp+88h+Buf1]
0x140009179  call    RtlWriteULongToUser
0x14000917e  jmp     short loc_140009190
0x140009180  mov     r8, rsi; Size
0x140009183  lea     rdx, [rsp+88h+Buf1]; Src
0x14000918b  call    RtlCopyVolatileMemory
0x140009190  inc     ebx
0x140009192  jmp     loc_14000909F
0x140009197  xor     eax, eax
0x140009199  jmp     short loc_1400091A4
0x14000919b  jmp     short loc_1400091A4
0x14000919d  mov     eax, 0C000000Dh
0x1400091a2  jmp     short $+2
0x1400091a4  mov     rbx, [rsp+88h+arg_8]
0x1400091ac  add     rsp, 60h
0x1400091b0  pop     r15
0x1400091b2  pop     r14
0x1400091b4  pop     r12
0x1400091b6  pop     rdi
0x1400091b7  pop     rsi
0x1400091b8  retn
0x14000e80f  push    rbp
0x14000e811  sub     rsp, 30h
0x14000e815  mov     rbp, rdx
0x14000e818  xor     eax, eax
0x14000e81a  cmp     [rbp+90h], al
0x14000e820  setnz   al
0x14000e823  mov     [rbp+34h], eax
0x14000e826  mov     eax, [rbp+34h]
0x14000e829  add     rsp, 30h
0x14000e82d  pop     rbp
0x14000e82e  retn
```
