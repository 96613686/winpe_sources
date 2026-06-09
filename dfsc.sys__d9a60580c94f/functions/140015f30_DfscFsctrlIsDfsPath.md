# DfscFsctrlIsDfsPath

- ea: `0x140015f30`
- end: `0x140016067`
- name: `DfscFsctrlIsDfsPath`
- size: `311`
- prototype: `__int64 __fastcall(IRP *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140014910`

## callees

- `0x140001010`
- `0x1400015c0`
- `0x140015f30`
- `0x140020d10`

## pseudocode

```c
__int64 __fastcall DfscFsctrlIsDfsPath(IRP *a1, unsigned __int16 *a2, unsigned int a3)
{
  int v5; // ecx
  __int16 *v6; // rdx
  __int16 v7; // r8
  unsigned __int16 v8; // ax
  int ContainerContextFromIrp; // ebx
  __int128 v11; // [rsp+40h] [rbp-10h] BYREF
  __int64 v12; // [rsp+78h] [rbp+28h] BYREF
  PVOID P; // [rsp+88h] [rbp+38h] BYREF

  P = 0;
  v12 = 0;
  v11 = 0;
  if ( a3 < 4 )
    return (unsigned int)-1073741811;
  if ( !a2 )
    return (unsigned int)-1073741811;
  v5 = *a2;
  if ( !(_WORD)v5 )
    return (unsigned int)-1073741811;
  if ( (v5 & 1) != 0 )
    return (unsigned int)-1073741811;
  v6 = (__int16 *)(a2 + 1);
  v7 = *v6;
  if ( !*v6 )
    return (unsigned int)-1073741811;
  if ( v5 + 2 > a3 )
    return (unsigned int)-1073741811;
  LOWORD(v11) = v5;
  v8 = v5;
  WORD1(v11) = v5;
  *((_QWORD *)&v11 + 1) = v6;
  if ( v7 != 92 )
    return (unsigned int)-1073741811;
  if ( (unsigned __int16)v5 >= 4u && v6[1] == 92 && v6 )
  {
    ++v6;
    v8 = v5 - 2;
    *((_QWORD *)&v11 + 1) = v6;
    WORD1(v11) = v5 - 2;
    LOWORD(v11) = v5 - 2;
  }
  if ( v8 < 4u || v6[1] != 92 )
  {
    ContainerContextFromIrp = DfscGetContainerContextFromIrp(a1, &v12);
    if ( ContainerContextFromIrp >= 0 )
    {
      ContainerContextFromIrp = DfscGetReferralFromPath(a1, 0, (IRP *)&v11, 1, v12, (__int64)&P, 0, 0);
      if ( ContainerContextFromIrp < 0 )
        ContainerContextFromIrp = -1073741772;
      if ( P )
        DfscReferralRelease(P);
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return (unsigned int)ContainerContextFromIrp;
}

```

## disassembly

```asm
0x140015f30  mov     [rsp-18h+arg_0], rbx
0x140015f35  push    rbp
0x140015f36  push    rsi
0x140015f37  push    rdi
0x140015f38  mov     rbp, rsp
0x140015f3b  sub     rsp, 50h
0x140015f3f  xor     esi, esi
0x140015f41  xorps   xmm0, xmm0
0x140015f44  mov     r9d, r8d
0x140015f47  mov     [rbp+P], rsi
0x140015f4b  mov     rdi, rcx
0x140015f4e  mov     [rbp+arg_8], rsi
0x140015f52  movups  [rbp+var_10], xmm0
0x140015f56  lea     r10d, [rsi+4]
0x140015f5a  cmp     r8d, r10d
0x140015f5d  jb      loc_140016052
0x140015f63  test    rdx, rdx
0x140015f66  jz      loc_140016052
0x140015f6c  movzx   ecx, word ptr [rdx]
0x140015f6f  test    cx, cx
0x140015f72  jz      loc_140016052
0x140015f78  test    cl, 1
0x140015f7b  jnz     loc_140016052
0x140015f81  add     rdx, 2
0x140015f85  movzx   r8d, word ptr [rdx]
0x140015f89  test    r8w, r8w
0x140015f8d  jz      loc_140016052
0x140015f93  lea     r11d, [rsi+2]
0x140015f97  lea     eax, [r11+rcx]
0x140015f9b  cmp     eax, r9d
0x140015f9e  ja      loc_140016052
0x140015fa4  mov     word ptr [rbp+var_10], cx
0x140015fa8  movzx   eax, cx
0x140015fab  mov     word ptr [rbp+var_10+2], cx
0x140015faf  mov     qword ptr [rbp+var_10+8], rdx
0x140015fb3  cmp     r8w, 5Ch ; '\'
0x140015fb8  jnz     loc_140016052
0x140015fbe  cmp     cx, r10w
0x140015fc2  jb      short loc_140015FE7
0x140015fc4  cmp     [rdx+2], r8w
0x140015fc9  jnz     short loc_140015FE7
0x140015fcb  test    rdx, rdx
0x140015fce  jz      short loc_140015FE7
0x140015fd0  add     rdx, r11
0x140015fd3  sub     ax, r11w
0x140015fd7  sub     cx, r11w
0x140015fdb  mov     qword ptr [rbp+var_10+8], rdx
0x140015fdf  mov     word ptr [rbp+var_10+2], cx
0x140015fe3  mov     word ptr [rbp+var_10], ax
0x140015fe7  cmp     ax, r10w
0x140015feb  jb      short loc_140015FF4
0x140015fed  cmp     word ptr [rdx+2], 5Ch ; '\'
0x140015ff2  jz      short loc_140016052
0x140015ff4  lea     rdx, [rbp+arg_8]
0x140015ff8  mov     rcx, rdi
0x140015ffb  call    DfscGetContainerContextFromIrp
0x140016000  mov     ebx, eax
0x140016002  test    eax, eax
0x140016004  js      short loc_140016057
0x140016006  mov     [rsp+50h+var_18], rsi
0x14001600b  lea     rax, [rbp+P]
0x14001600f  mov     [rsp+50h+var_20], rsi
0x140016014  lea     r8, [rbp+var_10]
0x140016018  mov     [rsp+50h+var_28], rax
0x14001601d  mov     r9d, 1
0x140016023  mov     rax, [rbp+arg_8]
0x140016027  xor     edx, edx
0x140016029  mov     rcx, rdi
0x14001602c  mov     [rsp+50h+var_30], rax
0x140016031  call    DfscGetReferralFromPath
0x140016036  mov     rcx, [rbp+P]; P
0x14001603a  mov     ebx, eax
0x14001603c  test    ebx, ebx
0x14001603e  mov     eax, 0C0000034h
0x140016043  cmovs   ebx, eax
0x140016046  test    rcx, rcx
0x140016049  jz      short loc_140016057
0x14001604b  call    DfscReferralRelease
0x140016050  jmp     short loc_140016057
0x140016052  mov     ebx, 0C000000Dh
0x140016057  mov     eax, ebx
0x140016059  mov     rbx, [rsp+50h+arg_0]
0x14001605e  add     rsp, 50h
0x140016062  pop     rdi
0x140016063  pop     rsi
0x140016064  pop     rbp
0x140016065  retn
```
