# LuafvGetMirrorRenameInformation

- ea: `0x1400043c4`
- end: `0x1400044d2`
- name: `LuafvGetMirrorRenameInformation`
- size: `270`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x140003060`
- `0x1400164f0`

## callees

- `0x140004390`
- `0x1400043c4`
- `0x140004e6c`
- `0x140006080`
- `0x14001b6a0`
- `0x14001dd90`

## pseudocode

```c
__int64 __fastcall LuafvGetMirrorRenameInformation(__int64 a1, __int64 a2, char **a3, _DWORD *a4)
{
  USHORT v4; // ax
  int v5; // edi
  int MirrorFileName; // ebx
  int v11; // eax
  int v12; // r9d
  UNICODE_STRING *v13; // r8
  int v14; // esi
  char *Pool; // rax
  size_t v16; // r8
  const void *v17; // rdx
  void *Src[2]; // [rsp+30h] [rbp-30h] BYREF
  UNICODE_STRING v20; // [rsp+40h] [rbp-20h] BYREF
  struct _UNICODE_STRING v21; // [rsp+50h] [rbp-10h] BYREF

  v4 = *(_WORD *)(a2 + 16);
  v5 = 0;
  *(_DWORD *)(&v20.MaximumLength + 1) = 0;
  v20.Length = v4;
  v20.MaximumLength = v4;
  v20.Buffer = (PWSTR)(a2 + 20);
  v21 = 0;
  *(_OWORD *)Src = 0;
  if ( a2 == -20 )
  {
    MirrorFileName = -1073741811;
  }
  else
  {
    v11 = ConvertDosPathToNtPath(&v20, &v21, (__int64)a3);
    v13 = &v21;
    if ( v11 < 0 )
      v13 = &v20;
    MirrorFileName = LuafvGetMirrorFileName(*(_QWORD *)(a1 + 8), *(_QWORD *)(a1 + 16), (_DWORD)v13, v12, (__int64)Src);
    if ( MirrorFileName >= 0 )
    {
      v14 = LOWORD(Src[0]);
      *a3 = 0;
      v5 = v14 + 20;
      Pool = LuafvAllocatePool(1, v14 + 20, 1);
      *a3 = Pool;
      if ( Pool )
      {
        v16 = LOWORD(Src[0]);
        v17 = Src[1];
        *Pool = *(_BYTE *)a2;
        *((_QWORD *)Pool + 1) = 0;
        *((_DWORD *)Pool + 4) = v14;
        memmove(Pool + 20, v17, v16);
      }
      else
      {
        MirrorFileName = -1073741670;
      }
    }
  }
  if ( v21.Buffer )
    LuafvFreePool((__int64)v21.Buffer);
  if ( Src[1] )
    LuafvFreePool((__int64)Src[1]);
  *a4 = v5;
  return (unsigned int)MirrorFileName;
}

```

## disassembly

```asm
0x1400043c4  push    rbp
0x1400043c6  push    rbx
0x1400043c7  push    rsi
0x1400043c8  push    rdi
0x1400043c9  push    r12
0x1400043cb  push    r14
0x1400043cd  push    r15
0x1400043cf  mov     rbp, rsp
0x1400043d2  sub     rsp, 60h
0x1400043d6  movzx   eax, word ptr [rdx+10h]
0x1400043da  xorps   xmm0, xmm0
0x1400043dd  xorps   xmm1, xmm1
0x1400043e0  xor     edi, edi
0x1400043e2  movups  [rbp+var_20], xmm1
0x1400043e6  mov     word ptr [rbp+var_20], ax
0x1400043ea  mov     r15, r9
0x1400043ed  mov     word ptr [rbp+var_20+2], ax
0x1400043f1  mov     r12, r8
0x1400043f4  lea     rax, [rdx+14h]
0x1400043f8  mov     r14, rdx
0x1400043fb  mov     qword ptr [rbp+var_20+8], rax
0x1400043ff  mov     rbx, rcx
0x140004402  movups  [rbp+var_10], xmm0
0x140004406  movups  xmmword ptr [rbp+Src], xmm0
0x14000440a  test    rax, rax
0x14000440d  jnz     short loc_140004419
0x14000440f  mov     ebx, 0C000000Dh
0x140004414  jmp     loc_1400044A1
0x140004419  lea     rdx, [rbp+var_10]
0x14000441d  lea     rcx, [rbp+var_20]
0x140004421  call    ConvertDosPathToNtPath
0x140004426  mov     rdx, [rbx+10h]
0x14000442a  lea     r8, [rbp+var_10]
0x14000442e  mov     rcx, [rbx+8]
0x140004432  test    eax, eax
0x140004434  lea     rax, [rbp+Src]
0x140004438  mov     [rsp+60h+var_40], rax
0x14000443d  jns     short loc_140004443
0x14000443f  lea     r8, [rbp+var_20]
0x140004443  call    LuafvGetMirrorFileName
0x140004448  mov     ebx, eax
0x14000444a  test    eax, eax
0x14000444c  js      short loc_1400044A1
0x14000444e  movzx   esi, word ptr [rbp+Src]
0x140004452  mov     r8b, 1
0x140004455  mov     ecx, 1
0x14000445a  mov     qword ptr [r12], 0
0x140004462  lea     edi, [rsi+14h]
0x140004465  mov     edx, edi
0x140004467  call    LuafvAllocatePool
0x14000446c  mov     [r12], rax
0x140004470  mov     rcx, rax
0x140004473  test    rax, rax
0x140004476  jnz     short loc_14000447F
0x140004478  mov     ebx, 0C000009Ah
0x14000447d  jmp     short loc_1400044A1
0x14000447f  mov     al, [r14]
0x140004482  movzx   r8d, word ptr [rbp+Src]; Size
0x140004487  mov     rdx, [rbp+Src+8]; Src
0x14000448b  mov     [rcx], al
0x14000448d  mov     qword ptr [rcx+8], 0
0x140004495  mov     [rcx+10h], esi
0x140004498  add     rcx, 14h; void *
0x14000449c  call    memmove
0x1400044a1  mov     rcx, qword ptr [rbp+var_10+8]
0x1400044a5  test    rcx, rcx
0x1400044a8  jz      short loc_1400044AF
0x1400044aa  call    LuafvFreePool
0x1400044af  mov     rcx, [rbp+Src+8]
0x1400044b3  test    rcx, rcx
0x1400044b6  jz      short loc_1400044BD
0x1400044b8  call    LuafvFreePool
0x1400044bd  mov     [r15], edi
0x1400044c0  mov     eax, ebx
0x1400044c2  add     rsp, 60h
0x1400044c6  pop     r15
0x1400044c8  pop     r14
0x1400044ca  pop     r12
0x1400044cc  pop     rdi
0x1400044cd  pop     rsi
0x1400044ce  pop     rbx
0x1400044cf  pop     rbp
0x1400044d0  retn
```
