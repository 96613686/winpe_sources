# SipFile::GetContents(uchar * *,ulong *)

- ea: `0x180003c70`
- end: `0x180003d47`
- name: `?GetContents@SipFile@@QEAAKPEAPEAEPEAK@Z`
- size: `215`
- prototype: `__int64 __fastcall(void **this, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180001e40`
- `0x180004650`

## callees

- `0x180001008`
- `0x180001014`
- `0x180003c70`
- `0x180004500`
- `0x180004ec0`

## pseudocode

```c
__int64 __fastcall SipFile::GetContents(void **this, unsigned __int8 **a2, unsigned int *a3)
{
  unsigned int Size; // ebx
  __int64 v7; // rsi
  void *v8; // rax
  unsigned __int64 v9; // rdx
  _BYTE *v10; // rax
  unsigned __int64 v12; // [rsp+78h] [rbp+10h] BYREF

  v12 = 0;
  if ( !a2 || !a3 )
  {
    Size = 87;
    goto LABEL_11;
  }
  *a2 = 0;
  *a3 = 0;
  Size = SipFile::GetSize((SipFile *)this, &v12);
  if ( Size )
  {
LABEL_11:
    operator delete(this[8]);
    return Size;
  }
  v7 = (unsigned int)v12;
  v8 = operator new((unsigned int)v12 + 2LL);
  this[8] = v8;
  if ( !v8 )
  {
    Size = 8;
    goto LABEL_11;
  }
  LODWORD(v12) = 0;
  Size = SipFile::Read((SipFile *)this, v9, v7, v8, (unsigned int *)&v12);
  if ( Size )
    goto LABEL_11;
  if ( (_DWORD)v12 != (_DWORD)v7 )
  {
    Size = 13;
    goto LABEL_11;
  }
  v10 = this[8];
  *a3 = v7;
  v10[v7] = 0;
  *((_BYTE *)this[8] + (unsigned int)(v7 + 1)) = 0;
  *a2 = (unsigned __int8 *)this[8];
  return Size;
}

```

## disassembly

```asm
0x180003c70  push    rbx
0x180003c72  push    rbp
0x180003c73  push    rsi
0x180003c74  push    rdi
0x180003c75  push    r14
0x180003c77  push    r15
0x180003c79  sub     rsp, 38h
0x180003c7d  mov     [rsp+68h+arg_8], 0
0x180003c86  mov     r14, r8
0x180003c89  mov     r15, rdx
0x180003c8c  mov     rdi, rcx
0x180003c8f  test    rdx, rdx
0x180003c92  jz      loc_180003D2A
0x180003c98  test    r8, r8
0x180003c9b  jz      loc_180003D2A
0x180003ca1  mov     qword ptr [rdx], 0
0x180003ca8  lea     rdx, [rsp+68h+arg_8]; unsigned __int64 *
0x180003cad  mov     dword ptr [r8], 0
0x180003cb4  call    ?GetSize@SipFile@@QEAAKPEA_K@Z; SipFile::GetSize(unsigned __int64 *)
0x180003cb9  mov     ebx, eax
0x180003cbb  test    eax, eax
0x180003cbd  jnz     short loc_180003D2F
0x180003cbf  mov     esi, dword ptr [rsp+68h+arg_8]
0x180003cc3  lea     rcx, [rsi+2]; Size
0x180003cc7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003ccc  mov     [rdi+40h], rax
0x180003cd0  test    rax, rax
0x180003cd3  jnz     short loc_180003CDA
0x180003cd5  lea     ebx, [rax+8]
0x180003cd8  jmp     short loc_180003D2F
0x180003cda  lea     rcx, [rsp+68h+arg_8]
0x180003cdf  mov     dword ptr [rsp+68h+arg_8], 0
0x180003ce7  mov     [rsp+68h+var_48], rcx; unsigned int *
0x180003cec  mov     r9, rax; void *
0x180003cef  mov     rcx, rdi; this
0x180003cf2  mov     r8d, esi; unsigned int
0x180003cf5  call    ?Read@SipFile@@QEAAK_KKPEAXPEAK@Z; SipFile::Read(unsigned __int64,ulong,void *,ulong *)
0x180003cfa  mov     ebx, eax
0x180003cfc  test    eax, eax
0x180003cfe  jnz     short loc_180003D2F
0x180003d00  cmp     dword ptr [rsp+68h+arg_8], esi
0x180003d04  jz      short loc_180003D0B
0x180003d06  lea     ebx, [rax+0Dh]
0x180003d09  jmp     short loc_180003D2F
0x180003d0b  mov     rax, [rdi+40h]
0x180003d0f  lea     ecx, [rsi+1]
0x180003d12  mov     [r14], esi
0x180003d15  mov     byte ptr [rax+rsi], 0
0x180003d19  mov     rax, [rdi+40h]
0x180003d1d  mov     byte ptr [rcx+rax], 0
0x180003d21  mov     rax, [rdi+40h]
0x180003d25  mov     [r15], rax
0x180003d28  jmp     short loc_180003D38
0x180003d2a  mov     ebx, 57h ; 'W'
0x180003d2f  mov     rcx, [rdi+40h]; Block
0x180003d33  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003d38  mov     eax, ebx
0x180003d3a  add     rsp, 38h
0x180003d3e  pop     r15
0x180003d40  pop     r14
0x180003d42  pop     rdi
0x180003d43  pop     rsi
0x180003d44  pop     rbp
0x180003d45  pop     rbx
0x180003d46  retn
```
