# searchRhizome

- ea: `0x14001c2e0`
- end: `0x14001c456`
- name: `searchRhizome`
- size: `374`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140017168`
- `0x1400179cc`
- `0x140019550`
- `0x1400196d4`

## callees

- `0x14000218c`
- `0x14001c2e0`

## pseudocode

```c
int *__fastcall searchRhizome(__int64 a1, __int64 a2)
{
  int *v4; // rbx
  PDEVICE_OBJECT v5; // rcx
  unsigned __int16 v6; // dx
  int v7; // eax
  int v8; // edx
  __int64 v9; // r9
  int v10; // r8d

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_((__int64)WPP_GLOBAL_Control->AttachedDevice, 0xEu, (__int64)WPP_98f60eb7cbd035eae084edec7fd78373_Traceguids);
  }
  v4 = *(int **)(a1 + 8);
  if ( !v4 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0xFu,
          (__int64)WPP_98f60eb7cbd035eae084edec7fd78373_Traceguids);
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      {
        v6 = 16;
        goto LABEL_24;
      }
    }
    return 0;
  }
  v7 = *v4;
  if ( *v4 < *(_DWORD *)a1 )
  {
    v8 = *v4;
    do
    {
      v4 = *(int **)&v4[2 * (((__int64)*(char *)(((__int64)v8 >> 3) + a2) >> (7 - (v7 & 7u))) & 1) + 2];
      v7 = *v4;
      v8 = *v4;
    }
    while ( *v4 < *(_DWORD *)a1 );
  }
  v9 = *(int *)(a1 + 4);
  v10 = 0;
  if ( (int)v9 <= 0 )
  {
LABEL_28:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      WPP_SF_(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x12u,
        (__int64)WPP_98f60eb7cbd035eae084edec7fd78373_Traceguids);
    }
    return v4;
  }
  while ( 1 )
  {
    if ( (*(_BYTE *)(v10 + a2) & *((_BYTE *)v4 + v10 + v9 + 24)) == *((_BYTE *)v4 + v10 + 24) )
    {
      ++v10;
      goto LABEL_27;
    }
    v4 = (int *)*((_QWORD *)v4 + 2);
    if ( !v4 )
      break;
LABEL_27:
    if ( v10 >= (int)v9 )
      goto LABEL_28;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    v6 = 17;
LABEL_24:
    WPP_SF_((__int64)v5->AttachedDevice, v6, (__int64)WPP_98f60eb7cbd035eae084edec7fd78373_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x14001c2e0  push    rbx
0x14001c2e2  push    rbp
0x14001c2e3  push    rsi
0x14001c2e4  push    rdi
0x14001c2e5  push    r14
0x14001c2e7  sub     rsp, 20h
0x14001c2eb  mov     rsi, rdx
0x14001c2ee  mov     rdi, rcx
0x14001c2f1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c2f8  lea     rbp, WPP_GLOBAL_Control
0x14001c2ff  lea     r14, WPP_98f60eb7cbd035eae084edec7fd78373_Traceguids
0x14001c306  cmp     rcx, rbp
0x14001c309  jz      short loc_14001C329
0x14001c30b  mov     eax, [rcx+2Ch]
0x14001c30e  test    al, 1
0x14001c310  jz      short loc_14001C329
0x14001c312  cmp     byte ptr [rcx+29h], 6
0x14001c316  jb      short loc_14001C329
0x14001c318  mov     rcx, [rcx+18h]
0x14001c31c  mov     edx, 0Eh
0x14001c321  mov     r8, r14
0x14001c324  call    WPP_SF_
0x14001c329  mov     rbx, [rdi+8]
0x14001c32d  test    rbx, rbx
0x14001c330  jnz     short loc_14001C38A
0x14001c332  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c339  cmp     rcx, rbp
0x14001c33c  jz      loc_14001C410
0x14001c342  mov     eax, [rcx+2Ch]
0x14001c345  test    al, 1
0x14001c347  jz      short loc_14001C35E
0x14001c349  cmp     byte ptr [rcx+29h], 5
0x14001c34d  jb      short loc_14001C35E
0x14001c34f  mov     rcx, [rcx+18h]
0x14001c353  lea     edx, [rbx+0Fh]
0x14001c356  mov     r8, r14
0x14001c359  call    WPP_SF_
0x14001c35e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c365  cmp     rcx, rbp
0x14001c368  jz      loc_14001C410
0x14001c36e  mov     eax, [rcx+2Ch]
0x14001c371  test    al, 1
0x14001c373  jz      loc_14001C410
0x14001c379  cmp     byte ptr [rcx+29h], 6
0x14001c37d  jb      loc_14001C410
0x14001c383  mov     edx, 10h
0x14001c388  jmp     short loc_14001C404
0x14001c38a  mov     r8d, [rdi]
0x14001c38d  mov     eax, [rbx]
0x14001c38f  cmp     eax, r8d
0x14001c392  jge     short loc_14001C3BF
0x14001c394  mov     edx, eax
0x14001c396  and     al, 7
0x14001c398  mov     ecx, 7
0x14001c39d  sub     cl, al
0x14001c39f  movsxd  rax, edx
0x14001c3a2  sar     rax, 3
0x14001c3a6  movsx   rdx, byte ptr [rax+rsi]
0x14001c3ab  sar     rdx, cl
0x14001c3ae  and     edx, 1
0x14001c3b1  mov     rbx, [rbx+rdx*8+8]
0x14001c3b6  mov     eax, [rbx]
0x14001c3b8  mov     edx, eax
0x14001c3ba  cmp     eax, r8d
0x14001c3bd  jl      short loc_14001C396
0x14001c3bf  movsxd  r9, dword ptr [rdi+4]
0x14001c3c3  xor     r8d, r8d
0x14001c3c6  test    r9d, r9d
0x14001c3c9  jle     short loc_14001C41C
0x14001c3cb  movsxd  rdx, r8d
0x14001c3ce  lea     rax, [rdx+r9]
0x14001c3d2  mov     cl, [rax+rbx+18h]
0x14001c3d6  and     cl, [rdx+rsi]
0x14001c3d9  cmp     cl, [rdx+rbx+18h]
0x14001c3dd  jz      short loc_14001C414
0x14001c3df  mov     rbx, [rbx+10h]
0x14001c3e3  test    rbx, rbx
0x14001c3e6  jnz     short loc_14001C417
0x14001c3e8  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c3ef  cmp     rcx, rbp
0x14001c3f2  jz      short loc_14001C410
0x14001c3f4  mov     eax, [rcx+2Ch]
0x14001c3f7  test    al, 1
0x14001c3f9  jz      short loc_14001C410
0x14001c3fb  cmp     byte ptr [rcx+29h], 6
0x14001c3ff  jb      short loc_14001C410
0x14001c401  lea     edx, [rbx+11h]
0x14001c404  mov     rcx, [rcx+18h]
0x14001c408  mov     r8, r14
0x14001c40b  call    WPP_SF_
0x14001c410  xor     eax, eax
0x14001c412  jmp     short loc_14001C44A
0x14001c414  inc     r8d
0x14001c417  cmp     r8d, r9d
0x14001c41a  jl      short loc_14001C3CB
0x14001c41c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c423  cmp     rcx, rbp
0x14001c426  jz      short loc_14001C447
0x14001c428  mov     edx, [rcx+2Ch]
0x14001c42b  test    dl, 1
0x14001c42e  jz      short loc_14001C447
0x14001c430  cmp     byte ptr [rcx+29h], 6
0x14001c434  jb      short loc_14001C447
0x14001c436  mov     rcx, [rcx+18h]
0x14001c43a  mov     edx, 12h
0x14001c43f  mov     r8, r14
0x14001c442  call    WPP_SF_
0x14001c447  mov     rax, rbx
0x14001c44a  add     rsp, 20h
0x14001c44e  pop     r14
0x14001c450  pop     rdi
0x14001c451  pop     rsi
0x14001c452  pop     rbp
0x14001c453  pop     rbx
0x14001c454  retn
```
