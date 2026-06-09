# ReplaceStringInsert(SDescriptionStr *,_EVENTLOGRECORD *)

- ea: `0x18000f4b4`
- end: `0x18000f55d`
- name: `?ReplaceStringInsert@@YAJPEAUSDescriptionStr@@PEAU_EVENTLOGRECORD@@@Z`
- size: `169`
- prototype: `int __fastcall(unsigned __int16 **, struct _EVENTLOGRECORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000eb2c`

## callees

- `0x18000f4b4`
- `0x18000f564`

## import_xrefs

- `msvcrt!wcstoul` at `0x18000f4de`
- `msvcrt!wcstoul` at `0x18000f4de`

## pseudocode

```c
int __fastcall ReplaceStringInsert(unsigned __int16 **a1, struct _EVENTLOGRECORD *a2)
{
  unsigned __int16 **v2; // rdi
  unsigned __int16 *v4; // rcx
  unsigned int v6; // eax
  unsigned int NumStrings; // ecx
  const unsigned __int16 *v8; // rcx
  unsigned int v9; // edx
  __int64 v10; // rax
  wchar_t *EndPtr; // [rsp+60h] [rbp+8h] BYREF

  v2 = a1 + 1;
  v4 = a1[1];
  EndPtr = 0;
  v6 = wcstoul(v4 + 1, &EndPtr, 10);
  if ( v6 && (NumStrings = a2->NumStrings, v6 <= NumStrings) )
  {
    if ( (_WORD)NumStrings && (v8 = (const unsigned __int16 *)((char *)a2 + a2->StringOffset)) != 0 )
    {
      v9 = v6 - 1;
      if ( v6 != 1 )
      {
        do
        {
          v10 = -1;
          do
            ++v10;
          while ( v8[v10] );
          v8 += v10 + 1;
          --v9;
        }
        while ( v9 );
      }
    }
    else
    {
      v8 = &String;
    }
    return ReplaceSubStr(v8, a1, v2, EndPtr, (unsigned int *)a1 + 4, (unsigned int *)a1 + 5);
  }
  else
  {
    ++*v2;
    return -2147024809;
  }
}

```

## disassembly

```asm
0x18000f4b4  push    rbx
0x18000f4b6  push    rbp
0x18000f4b7  push    rsi
0x18000f4b8  push    rdi
0x18000f4b9  sub     rsp, 38h
0x18000f4bd  lea     rdi, [rcx+8]
0x18000f4c1  mov     rsi, rcx
0x18000f4c4  mov     rcx, [rdi]
0x18000f4c7  xor     ebp, ebp
0x18000f4c9  mov     rbx, rdx
0x18000f4cc  mov     [rsp+58h+EndPtr], rbp
0x18000f4d1  add     rcx, 2; String
0x18000f4d5  lea     rdx, [rsp+58h+EndPtr]; EndPtr
0x18000f4da  lea     r8d, [rbp+0Ah]; Radix
0x18000f4de  call    cs:__imp_wcstoul
0x18000f4e4  test    eax, eax
0x18000f4e6  jz      short loc_18000F54B
0x18000f4e8  movzx   ecx, word ptr [rbx+1Ah]
0x18000f4ec  cmp     eax, ecx
0x18000f4ee  ja      short loc_18000F54B
0x18000f4f0  test    cx, cx
0x18000f4f3  jz      short loc_18000F520
0x18000f4f5  mov     ecx, [rbx+24h]
0x18000f4f8  add     rcx, rbx
0x18000f4fb  jz      short loc_18000F520
0x18000f4fd  lea     edx, [rax-1]
0x18000f500  test    edx, edx
0x18000f502  jz      short loc_18000F527
0x18000f504  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f508  inc     rax
0x18000f50b  cmp     [rcx+rax*2], bp
0x18000f50f  jnz     short loc_18000F508
0x18000f511  lea     rcx, [rcx+rax*2]
0x18000f515  add     rcx, 2
0x18000f519  add     edx, 0FFFFFFFFh
0x18000f51c  jnz     short loc_18000F504
0x18000f51e  jmp     short loc_18000F527
0x18000f520  lea     rcx, String; unsigned __int16 *
0x18000f527  mov     r9, [rsp+58h+EndPtr]; unsigned __int16 *
0x18000f52c  lea     rax, [rsi+14h]
0x18000f530  lea     rdx, [rsi+10h]
0x18000f534  mov     [rsp+58h+var_30], rax; unsigned int *
0x18000f539  mov     [rsp+58h+var_38], rdx; unsigned int *
0x18000f53e  mov     r8, rdi; unsigned __int16 **
0x18000f541  mov     rdx, rsi; unsigned __int16 **
0x18000f544  call    ?ReplaceSubStr@@YAJPEBGPEAPEAG10PEAK2@Z; ReplaceSubStr(ushort const *,ushort * *,ushort * *,ushort const *,ulong *,ulong *)
0x18000f549  jmp     short loc_18000F554
0x18000f54b  add     qword ptr [rdi], 2
0x18000f54f  mov     eax, 80070057h
0x18000f554  add     rsp, 38h
0x18000f558  pop     rdi
0x18000f559  pop     rsi
0x18000f55a  pop     rbp
0x18000f55b  pop     rbx
0x18000f55c  retn
```
