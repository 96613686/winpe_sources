# CreateTunnelCb

- ea: `0x140010d20`
- end: `0x140010f7e`
- name: `CreateTunnelCb`
- size: `606`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140011288`

## callees

- `0x140001af0`
- `0x140001b70`
- `0x140003050`
- `0x1400031ec`
- `0x140004c00`
- `0x140010d20`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140010e8a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010e8a`
- `ntoskrnl!KeInitializeSpinLock` at `0x140010db7`
- `ntoskrnl!KeInitializeSpinLock` at `0x140010dca`
- `ntoskrnl!KeInitializeSpinLock` at `0x140010eac`
- `ntoskrnl!KeInitializeSpinLock` at `0x140010db7`
- `ntoskrnl!KeInitializeSpinLock` at `0x140010dca`
- `ntoskrnl!KeInitializeSpinLock` at `0x140010eac`
- `NDIS!NdisInitializeTimer` at `0x140010ec6`
- `NDIS!NdisInitializeTimer` at `0x140010ec6`

## pseudocode

```c
char *__fastcall CreateTunnelCb(__int64 a1)
{
  char *v2; // rax
  char *v3; // rbx
  __int16 v4; // ax
  int v5; // eax
  int v6; // eax
  __int64 v7; // rax
  _DWORD *v8; // rsi
  _QWORD *v10; // rax
  _DWORD *v11; // [rsp+58h] [rbp+10h] BYREF

  v2 = (char *)ALLOC_NONPAGED(384, 844378700);
  v3 = v2;
  if ( !v2 )
    return v3;
  memset(v2, 0, 0x180u);
  *((_QWORD *)v3 + 1) = v3;
  *(_QWORD *)v3 = v3;
  *((_QWORD *)v3 + 17) = v3 + 128;
  *((_QWORD *)v3 + 16) = v3 + 128;
  *((_QWORD *)v3 + 19) = v3 + 144;
  *((_QWORD *)v3 + 18) = v3 + 144;
  *((_QWORD *)v3 + 27) = v3 + 208;
  *((_QWORD *)v3 + 26) = v3 + 208;
  *((_QWORD *)v3 + 37) = v3 + 288;
  *((_QWORD *)v3 + 36) = v3 + 288;
  *((_QWORD *)v3 + 44) = v3 + 344;
  *((_QWORD *)v3 + 43) = v3 + 344;
  *((_QWORD *)v3 + 40) = v3 + 312;
  *((_QWORD *)v3 + 39) = v3 + 312;
  KeInitializeSpinLock((PKSPIN_LOCK)v3 + 4);
  KeInitializeSpinLock((PKSPIN_LOCK)v3 + 41);
  *((_DWORD *)v3 + 4) = 844378700;
  *((_DWORD *)v3 + 31) = 0;
  v4 = *(_WORD *)(a1 + 160);
  do
    ++v4;
  while ( !v4 );
  *(_WORD *)(a1 + 160) = v4;
  *((_WORD *)v3 + 57) = v4;
  v5 = *(_DWORD *)(a1 + 364) >> 1;
  *((_DWORD *)v3 + 57) = v5;
  if ( !v5 )
    *((_DWORD *)v3 + 57) = 1;
  v6 = *(_DWORD *)(a1 + 28);
  *((_DWORD *)v3 + 60) = v6;
  *((_DWORD *)v3 + 62) = v6;
  *((_DWORD *)v3 + 94) = 10000000;
  v7 = ALLOC_NONPAGED(192, 911487564);
  *((_QWORD *)v3 + 38) = v7;
  v8 = (_DWORD *)v7;
  if ( v7 )
  {
    v10 = (_QWORD *)(v7 + 8);
    v10[1] = v10;
    *v10 = v10;
    KeInitializeSpinLock((PKSPIN_LOCK)v8 + 6);
    NdisInitializeTimer((PNDIS_TIMER)(v8 + 16), TimerEvent, v8);
    *((_QWORD *)v8 + 3) = 0;
    *((_BYTE *)v8 + 40) = 0;
    *v8 = 911487564;
    ++*(_DWORD *)(a1 + 400);
    if ( *(_QWORD *)(a1 + 48) )
    {
      v11 = v3 + 168;
      *((_QWORD *)v3 + 21) = MEMORY[0xFFFFF78000000014];
      v11[1] = a1;
      v11[2] = (_DWORD)v3;
      v11[3] = (unsigned int)&v11;
    }
    ReferenceAdapter(a1);
    *((_QWORD *)v3 + 3) = a1;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids, v3);
    }
    return v3;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids);
  }
  *((_DWORD *)v3 + 4) = 810824268;
  ExFreePoolWithTag(v3 - 16, 0);
  return 0;
}

```

## disassembly

```asm
0x140010d20  push    rbx
0x140010d22  push    rbp
0x140010d23  push    rsi
0x140010d24  push    rdi
0x140010d25  sub     rsp, 28h
0x140010d29  mov     rdi, rcx
0x140010d2c  mov     esi, 3254324Ch
0x140010d31  mov     ebp, 180h
0x140010d36  mov     edx, esi
0x140010d38  mov     ecx, ebp
0x140010d3a  call    ALLOC_NONPAGED
0x140010d3f  mov     rbx, rax
0x140010d42  test    rax, rax
0x140010d45  jz      loc_140010F71
0x140010d4b  mov     r8d, ebp; Size
0x140010d4e  xor     edx, edx; Val
0x140010d50  mov     rcx, rax; void *
0x140010d53  call    memset
0x140010d58  mov     [rbx+8], rbx
0x140010d5c  lea     rax, [rbx+80h]
0x140010d63  mov     [rbx], rbx
0x140010d66  lea     rcx, [rbx+20h]; SpinLock
0x140010d6a  mov     [rax+8], rax
0x140010d6e  mov     [rax], rax
0x140010d71  lea     rax, [rbx+90h]
0x140010d78  mov     [rax+8], rax
0x140010d7c  mov     [rax], rax
0x140010d7f  lea     rax, [rbx+0D0h]
0x140010d86  mov     [rax+8], rax
0x140010d8a  mov     [rax], rax
0x140010d8d  lea     rax, [rbx+120h]
0x140010d94  mov     [rax+8], rax
0x140010d98  mov     [rax], rax
0x140010d9b  lea     rax, [rbx+158h]
0x140010da2  mov     [rax+8], rax
0x140010da6  mov     [rax], rax
0x140010da9  lea     rax, [rbx+138h]
0x140010db0  mov     [rax+8], rax
0x140010db4  mov     [rax], rax
0x140010db7  call    cs:__imp_KeInitializeSpinLock
0x140010dbe  nop     dword ptr [rax+rax+00h]
0x140010dc3  lea     rcx, [rbx+148h]; SpinLock
0x140010dca  call    cs:__imp_KeInitializeSpinLock
0x140010dd1  nop     dword ptr [rax+rax+00h]
0x140010dd6  mov     [rbx+10h], esi
0x140010dd9  mov     ebp, 1
0x140010dde  mov     dword ptr [rbx+7Ch], 0
0x140010de5  movzx   eax, word ptr [rdi+0A0h]
0x140010dec  add     ax, bp
0x140010def  jz      short loc_140010DEC
0x140010df1  mov     [rdi+0A0h], ax
0x140010df8  mov     [rbx+72h], ax
0x140010dfc  mov     eax, [rdi+16Ch]
0x140010e02  shr     eax, 1
0x140010e04  mov     [rbx+0E4h], eax
0x140010e0a  jnz     short loc_140010E12
0x140010e0c  mov     [rbx+0E4h], ebp
0x140010e12  mov     eax, [rdi+1Ch]
0x140010e15  mov     edx, 3654324Ch
0x140010e1a  mov     ecx, 0C0h
0x140010e1f  mov     [rbx+0F0h], eax
0x140010e25  mov     [rbx+0F8h], eax
0x140010e2b  mov     dword ptr [rbx+178h], 989680h
0x140010e35  call    ALLOC_NONPAGED
0x140010e3a  mov     [rbx+130h], rax
0x140010e41  mov     rsi, rax
0x140010e44  test    rax, rax
0x140010e47  jnz     short loc_140010E9D
0x140010e49  mov     rcx, cs:WPP_GLOBAL_Control
0x140010e50  lea     rax, WPP_GLOBAL_Control
0x140010e57  cmp     rcx, rax
0x140010e5a  jz      short loc_140010E7D
0x140010e5c  mov     eax, [rcx+2Ch]
0x140010e5f  test    bpl, al
0x140010e62  jz      short loc_140010E7D
0x140010e64  cmp     [rcx+29h], bpl
0x140010e68  jb      short loc_140010E7D
0x140010e6a  mov     rcx, [rcx+18h]
0x140010e6e  lea     edx, [rsi+22h]
0x140010e71  lea     r8, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids
0x140010e78  call    WPP_SF_
0x140010e7d  lea     rcx, [rbx-10h]; P
0x140010e81  mov     dword ptr [rbx+10h], 3054324Ch
0x140010e88  xor     edx, edx; Tag
0x140010e8a  call    cs:__imp_ExFreePoolWithTag
0x140010e91  nop     dword ptr [rax+rax+00h]
0x140010e96  xor     eax, eax
0x140010e98  jmp     loc_140010F74
0x140010e9d  add     rax, 8
0x140010ea1  lea     rcx, [rsi+30h]; SpinLock
0x140010ea5  mov     [rax+8], rax
0x140010ea9  mov     [rax], rax
0x140010eac  call    cs:__imp_KeInitializeSpinLock
0x140010eb3  nop     dword ptr [rax+rax+00h]
0x140010eb8  lea     rcx, [rsi+40h]; Timer
0x140010ebc  mov     r8, rsi; FunctionContext
0x140010ebf  lea     rdx, TimerEvent; TimerFunction
0x140010ec6  call    cs:__imp_NdisInitializeTimer
0x140010ecd  nop     dword ptr [rax+rax+00h]
0x140010ed2  mov     qword ptr [rsi+18h], 0
0x140010eda  mov     byte ptr [rsi+28h], 0
0x140010ede  mov     dword ptr [rsi], 3654324Ch
0x140010ee4  add     [rdi+190h], ebp
0x140010eea  cmp     qword ptr [rdi+30h], 0
0x140010eef  jz      short loc_140010F2C
0x140010ef1  lea     rax, [rbx+0A8h]
0x140010ef8  mov     [rsp+48h+arg_8], rax
0x140010efd  mov     rax, ds:0FFFFF78000000014h
0x140010f07  mov     rcx, [rsp+48h+arg_8]
0x140010f0c  mov     [rcx], rax
0x140010f0f  lea     rcx, [rsp+48h+arg_8]
0x140010f14  mov     rax, [rsp+48h+arg_8]
0x140010f19  mov     [rax+4], edi
0x140010f1c  mov     rax, [rsp+48h+arg_8]
0x140010f21  mov     [rax+8], ebx
0x140010f24  mov     rax, [rsp+48h+arg_8]
0x140010f29  mov     [rax+0Ch], ecx
0x140010f2c  mov     rcx, rdi
0x140010f2f  call    ReferenceAdapter
0x140010f34  mov     [rbx+18h], rdi
0x140010f38  mov     rcx, cs:WPP_GLOBAL_Control
0x140010f3f  lea     rax, WPP_GLOBAL_Control
0x140010f46  cmp     rcx, rax
0x140010f49  jz      short loc_140010F71
0x140010f4b  mov     edx, [rcx+2Ch]
0x140010f4e  test    dl, 4
0x140010f51  jz      short loc_140010F71
0x140010f53  cmp     byte ptr [rcx+29h], 3
0x140010f57  jb      short loc_140010F71
0x140010f59  mov     rcx, [rcx+18h]
0x140010f5d  lea     r8, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids
0x140010f64  mov     edx, 23h ; '#'
0x140010f69  mov     r9, rbx
0x140010f6c  call    WPP_SF_q
0x140010f71  mov     rax, rbx
0x140010f74  add     rsp, 28h
0x140010f78  pop     rdi
0x140010f79  pop     rsi
0x140010f7a  pop     rbp
0x140010f7b  pop     rbx
0x140010f7c  retn
```
