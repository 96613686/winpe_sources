# LuafvGetMirrorRenameInformation

- ea: `0x1400045f4`
- end: `0x140004702`
- name: `LuafvGetMirrorRenameInformation`
- size: `270`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *, _DWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x140003290`
- `0x1400164f0`

## callees

- `0x1400045c0`
- `0x1400045f4`
- `0x140005034`
- `0x140005d00`
- `0x14001b650`
- `0x14001dd40`

## pseudocode

```c
__int64 __fastcall LuafvGetMirrorRenameInformation(__int64 a1, __int64 a2, __int64 *a3, _DWORD *a4)
{
  __int16 v4; // ax
  int v5; // edi
  int MirrorFileName; // ebx
  int v11; // eax
  int v12; // r9d
  __int128 *v13; // r8
  __int64 v14; // r8
  int v15; // esi
  __int64 Pool; // rax
  size_t v17; // r8
  const void *v18; // rdx
  void *Src[2]; // [rsp+30h] [rbp-30h] BYREF
  _WORD v21[2]; // [rsp+40h] [rbp-20h] BYREF
  int v22; // [rsp+44h] [rbp-1Ch]
  __int64 v23; // [rsp+48h] [rbp-18h]
  __int128 v24; // [rsp+50h] [rbp-10h] BYREF

  v4 = *(_WORD *)(a2 + 16);
  v5 = 0;
  v22 = 0;
  v21[0] = v4;
  v21[1] = v4;
  v23 = a2 + 20;
  v24 = 0;
  *(_OWORD *)Src = 0;
  if ( a2 == -20 )
  {
    MirrorFileName = -1073741811;
  }
  else
  {
    v11 = ConvertDosPathToNtPath(v21, &v24);
    v13 = &v24;
    if ( v11 < 0 )
      v13 = (__int128 *)v21;
    MirrorFileName = LuafvGetMirrorFileName(*(_QWORD *)(a1 + 8), *(_QWORD *)(a1 + 16), (_DWORD)v13, v12, (__int64)Src);
    if ( MirrorFileName >= 0 )
    {
      v15 = LOWORD(Src[0]);
      LOBYTE(v14) = 1;
      *a3 = 0;
      v5 = v15 + 20;
      Pool = LuafvAllocatePool(1, (unsigned int)(v15 + 20), v14);
      *a3 = Pool;
      if ( Pool )
      {
        v17 = LOWORD(Src[0]);
        v18 = Src[1];
        *(_BYTE *)Pool = *(_BYTE *)a2;
        *(_QWORD *)(Pool + 8) = 0;
        *(_DWORD *)(Pool + 16) = v15;
        memmove((void *)(Pool + 20), v18, v17);
      }
      else
      {
        MirrorFileName = -1073741670;
      }
    }
  }
  if ( *((_QWORD *)&v24 + 1) )
    LuafvFreePool(*((_QWORD *)&v24 + 1));
  if ( Src[1] )
    LuafvFreePool(Src[1]);
  *a4 = v5;
  return (unsigned int)MirrorFileName;
}

```

## disassembly

```asm
0x1400045f4  push    rbp
0x1400045f6  push    rbx
0x1400045f7  push    rsi
0x1400045f8  push    rdi
0x1400045f9  push    r12
0x1400045fb  push    r14
0x1400045fd  push    r15
0x1400045ff  mov     rbp, rsp
0x140004602  sub     rsp, 60h
0x140004606  movzx   eax, word ptr [rdx+10h]
0x14000460a  xorps   xmm0, xmm0
0x14000460d  xorps   xmm1, xmm1
0x140004610  xor     edi, edi
0x140004612  movups  [rbp+var_20], xmm1
0x140004616  mov     word ptr [rbp+var_20], ax
0x14000461a  mov     r15, r9
0x14000461d  mov     word ptr [rbp+var_20+2], ax
0x140004621  mov     r12, r8
0x140004624  lea     rax, [rdx+14h]
0x140004628  mov     r14, rdx
0x14000462b  mov     qword ptr [rbp+var_20+8], rax
0x14000462f  mov     rbx, rcx
0x140004632  movups  [rbp+var_10], xmm0
0x140004636  movups  xmmword ptr [rbp+Src], xmm0
0x14000463a  test    rax, rax
0x14000463d  jnz     short loc_140004649
0x14000463f  mov     ebx, 0C000000Dh
0x140004644  jmp     loc_1400046D1
0x140004649  lea     rdx, [rbp+var_10]
0x14000464d  lea     rcx, [rbp+var_20]
0x140004651  call    ConvertDosPathToNtPath
0x140004656  mov     rdx, [rbx+10h]
0x14000465a  lea     r8, [rbp+var_10]
0x14000465e  mov     rcx, [rbx+8]
0x140004662  test    eax, eax
0x140004664  lea     rax, [rbp+Src]
0x140004668  mov     [rsp+60h+var_40], rax
0x14000466d  jns     short loc_140004673
0x14000466f  lea     r8, [rbp+var_20]
0x140004673  call    LuafvGetMirrorFileName
0x140004678  mov     ebx, eax
0x14000467a  test    eax, eax
0x14000467c  js      short loc_1400046D1
0x14000467e  movzx   esi, word ptr [rbp+Src]
0x140004682  mov     r8b, 1
0x140004685  mov     ecx, 1
0x14000468a  mov     qword ptr [r12], 0
0x140004692  lea     edi, [rsi+14h]
0x140004695  mov     edx, edi
0x140004697  call    LuafvAllocatePool
0x14000469c  mov     [r12], rax
0x1400046a0  mov     rcx, rax
0x1400046a3  test    rax, rax
0x1400046a6  jnz     short loc_1400046AF
0x1400046a8  mov     ebx, 0C000009Ah
0x1400046ad  jmp     short loc_1400046D1
0x1400046af  mov     al, [r14]
0x1400046b2  movzx   r8d, word ptr [rbp+Src]; Size
0x1400046b7  mov     rdx, [rbp+Src+8]; Src
0x1400046bb  mov     [rcx], al
0x1400046bd  mov     qword ptr [rcx+8], 0
0x1400046c5  mov     [rcx+10h], esi
0x1400046c8  add     rcx, 14h; void *
0x1400046cc  call    memmove
0x1400046d1  mov     rcx, qword ptr [rbp+var_10+8]
0x1400046d5  test    rcx, rcx
0x1400046d8  jz      short loc_1400046DF
0x1400046da  call    LuafvFreePool
0x1400046df  mov     rcx, [rbp+Src+8]
0x1400046e3  test    rcx, rcx
0x1400046e6  jz      short loc_1400046ED
0x1400046e8  call    LuafvFreePool
0x1400046ed  mov     [r15], edi
0x1400046f0  mov     eax, ebx
0x1400046f2  add     rsp, 60h
0x1400046f6  pop     r15
0x1400046f8  pop     r14
0x1400046fa  pop     r12
0x1400046fc  pop     rdi
0x1400046fd  pop     rsi
0x1400046fe  pop     rbx
0x1400046ff  pop     rbp
0x140004700  retn
```
