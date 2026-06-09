# __FrameHandler4::StateFromIp(FH4::FuncInfo4 *,_xDISPATCHER_CONTEXT *,unsigned __int64)

- ea: `0x180002f8c`
- end: `0x18000305d`
- name: `?StateFromIp@__FrameHandler4@@SAHPEAUFuncInfo4@FH4@@PEAU_xDISPATCHER_CONTEXT@@_K@Z`
- size: `209`
- prototype: `__int64 __fastcall(struct FH4::FuncInfo4 *, struct _xDISPATCHER_CONTEXT *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x180002f7c`
- `0x180003e28`

## callees

- `0x180002f8c`

## pseudocode

```c
__int64 __fastcall __FrameHandler4::StateFromIp(
        struct FH4::FuncInfo4 *a1,
        struct _xDISPATCHER_CONTEXT *a2,
        unsigned __int64 a3)
{
  __int64 ImageBase; // rdi
  _BYTE *v4; // r9
  __int64 v5; // rcx
  _BYTE *v6; // r9
  unsigned int v7; // ebx
  PRUNTIME_FUNCTION FunctionEntry; // rax
  unsigned int v9; // r10d
  unsigned int v10; // esi
  unsigned int v11; // edx
  __int64 v12; // rcx
  _BYTE *v13; // r9
  __int64 v14; // rcx

  if ( !*((_DWORD *)a1 + 4) )
    return 0xFFFFFFFFLL;
  ImageBase = a2->ImageBase;
  v4 = (_BYTE *)(ImageBase + *((int *)a1 + 4));
  v5 = *v4 & 0xF;
  v6 = &v4[-*((char *)&FH4::s_negLengthTab + v5)];
  v7 = *((_DWORD *)v6 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v5);
  if ( !v7 )
    return 0xFFFFFFFFLL;
  FunctionEntry = a2->FunctionEntry;
  v9 = 0;
  v10 = 0;
  v11 = -1;
  do
  {
    v12 = *v6 & 0xF;
    v13 = &v6[-*((char *)&FH4::s_negLengthTab + v12)];
    v10 += *((_DWORD *)v13 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v12);
    if ( a3 < ImageBase + FunctionEntry->BeginAddress + (unsigned __int64)v10 )
      break;
    ++v9;
    v14 = *v13 & 0xF;
    v6 = &v13[-*((char *)&FH4::s_negLengthTab + v14)];
    v11 = (*((_DWORD *)v6 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v14)) - 1;
  }
  while ( v9 < v7 );
  if ( !v9 )
    return (unsigned int)-1;
  return v11;
}

```

## disassembly

```asm
0x180002f8c  push    rbx
0x180002f8e  push    rbp
0x180002f8f  push    rsi
0x180002f90  push    rdi
0x180002f91  push    r14
0x180002f93  cmp     dword ptr [rcx+10h], 0
0x180002f97  mov     rbp, r8
0x180002f9a  mov     r11, rdx
0x180002f9d  jz      loc_180003053
0x180002fa3  movsxd  r9, dword ptr [rcx+10h]
0x180002fa7  lea     r14, cs:180000000h
0x180002fae  mov     rdi, [rdx+8]
0x180002fb2  add     r9, rdi
0x180002fb5  movzx   ecx, byte ptr [r9]
0x180002fb9  and     ecx, 0Fh
0x180002fbc  movsx   rax, byte ptr [rcx+r14+10238h]
0x180002fc5  mov     cl, [rcx+r14+10248h]
0x180002fcd  sub     r9, rax
0x180002fd0  mov     ebx, [r9-4]
0x180002fd4  shr     ebx, cl
0x180002fd6  test    ebx, ebx
0x180002fd8  jz      short loc_180003053
0x180002fda  mov     rax, [r11+10h]
0x180002fde  or      r8d, 0FFFFFFFFh
0x180002fe2  xor     r10d, r10d
0x180002fe5  xor     esi, esi
0x180002fe7  mov     edx, r8d
0x180002fea  mov     r11d, [rax]
0x180002fed  add     r11, rdi
0x180002ff0  movzx   ecx, byte ptr [r9]
0x180002ff4  and     ecx, 0Fh
0x180002ff7  movsx   rax, byte ptr [rcx+r14+10238h]
0x180003000  mov     cl, [rcx+r14+10248h]
0x180003008  sub     r9, rax
0x18000300b  mov     eax, [r9-4]
0x18000300f  shr     eax, cl
0x180003011  add     esi, eax
0x180003013  mov     eax, esi
0x180003015  add     rax, r11
0x180003018  cmp     rbp, rax
0x18000301b  jb      short loc_180003048
0x18000301d  movzx   ecx, byte ptr [r9]
0x180003021  inc     r10d
0x180003024  and     ecx, 0Fh
0x180003027  movsx   rax, byte ptr [rcx+r14+10238h]
0x180003030  mov     cl, [rcx+r14+10248h]
0x180003038  sub     r9, rax
0x18000303b  mov     edx, [r9-4]
0x18000303f  shr     edx, cl
0x180003041  dec     edx
0x180003043  cmp     r10d, ebx
0x180003046  jb      short loc_180002FF0
0x180003048  test    r10d, r10d
0x18000304b  cmovz   edx, r8d
0x18000304f  mov     eax, edx
0x180003051  jmp     short loc_180003056
0x180003053  or      eax, 0FFFFFFFFh
0x180003056  pop     r14
0x180003058  pop     rdi
0x180003059  pop     rsi
0x18000305a  pop     rbp
0x18000305b  pop     rbx
0x18000305c  retn
```
