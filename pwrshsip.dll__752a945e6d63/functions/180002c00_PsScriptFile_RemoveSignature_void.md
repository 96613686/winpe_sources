# PsScriptFile::RemoveSignature(void)

- ea: `0x180002c00`
- end: `0x180002cda`
- name: `?RemoveSignature@PsScriptFile@@UEAAKXZ`
- size: `218`
- prototype: `unsigned int __fastcall(PsScriptFile *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180002ae8`
- `0x180002c00`
- `0x180004650`
- `0x180004fd4`
- `0x1800054c6`

## pseudocode

```c
__int64 __fastcall PsScriptFile::RemoveSignature(void **this)
{
  __int64 result; // rax
  char v3; // bp
  unsigned int v4; // esi
  __int64 v5; // rcx
  size_t v6; // r8
  wchar_t *v7; // rbx
  unsigned __int16 *v8; // rbx
  unsigned int v9; // [rsp+48h] [rbp+10h] BYREF
  wchar_t *String1; // [rsp+50h] [rbp+18h] BYREF

  v9 = 0;
  String1 = 0;
  result = SipFile::InitReadContentLoop(this);
  if ( !(_DWORD)result )
  {
    v3 = 0;
    v4 = PsScriptFile::ReadContent((PsScriptFile *)this, &v9, &String1);
    if ( v4 )
    {
LABEL_6:
      v8 = String1;
    }
    else
    {
      while ( 1 )
      {
        v5 = *((unsigned int *)this + 14);
        v6 = HIDWORD(qword_180009840[10 * v5 + 7]);
        if ( v9 >= (unsigned int)v6 )
        {
          v7 = String1;
          if ( !wcsncmp_0(String1, (const wchar_t *)qword_180009840[10 * v5 + 2], v6) )
            break;
        }
        v4 = PsScriptFile::ReadContent((PsScriptFile *)this, &v9, &String1);
        if ( v4 )
          goto LABEL_6;
      }
      v3 = 1;
      v8 = v7 - 2;
    }
    result = 0;
    if ( v4 != 259 )
      result = v4;
    if ( !(_DWORD)result )
    {
      if ( v3 )
        SipFile::SetSize((SipFile *)this, v8);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002c00  mov     rax, rsp
0x180002c03  mov     [rax+8], rbx
0x180002c07  mov     [rax+20h], rbp
0x180002c0b  push    rsi
0x180002c0c  push    rdi
0x180002c0d  push    r14
0x180002c0f  sub     rsp, 20h
0x180002c13  mov     rdi, rcx
0x180002c16  mov     dword ptr [rax+10h], 0
0x180002c1d  mov     qword ptr [rax+18h], 0
0x180002c25  call    ?InitReadContentLoop@SipFile@@QEAAKXZ; SipFile::InitReadContentLoop(void)
0x180002c2a  test    eax, eax
0x180002c2c  jnz     loc_180002CBE
0x180002c32  lea     r8, [rsp+38h+String1]; unsigned __int16 **
0x180002c37  mov     rcx, rdi; this
0x180002c3a  lea     rdx, [rsp+38h+arg_8]; unsigned int *
0x180002c3f  xor     bpl, bpl
0x180002c42  call    ?ReadContent@PsScriptFile@@QEAAKPEAKPEAPEAG@Z; PsScriptFile::ReadContent(ulong *,ushort * *)
0x180002c47  mov     esi, eax
0x180002c49  test    eax, eax
0x180002c4b  jnz     short loc_180002C98
0x180002c4d  lea     r14, qword_180009840
0x180002c54  mov     ecx, [rdi+38h]
0x180002c57  lea     rdx, [rcx+rcx*4]
0x180002c5b  add     rdx, rdx
0x180002c5e  mov     r8d, [r14+rdx*8+3Ch]; MaxCount
0x180002c63  cmp     [rsp+38h+arg_8], r8d
0x180002c68  jb      short loc_180002C80
0x180002c6a  mov     rbx, [rsp+38h+String1]
0x180002c6f  mov     rdx, [r14+rdx*8+10h]; String2
0x180002c74  mov     rcx, rbx; String1
0x180002c77  call    wcsncmp_0
0x180002c7c  test    eax, eax
0x180002c7e  jz      short loc_180002CD1
0x180002c80  lea     r8, [rsp+38h+String1]; unsigned __int16 **
0x180002c85  mov     rcx, rdi; this
0x180002c88  lea     rdx, [rsp+38h+arg_8]; unsigned int *
0x180002c8d  call    ?ReadContent@PsScriptFile@@QEAAKPEAKPEAPEAG@Z; PsScriptFile::ReadContent(ulong *,ushort * *)
0x180002c92  mov     esi, eax
0x180002c94  test    eax, eax
0x180002c96  jz      short loc_180002C54
0x180002c98  mov     rbx, [rsp+38h+String1]
0x180002c9d  xor     eax, eax
0x180002c9f  cmp     esi, 103h
0x180002ca5  cmovnz  eax, esi
0x180002ca8  test    eax, eax
0x180002caa  jnz     short loc_180002CBE
0x180002cac  test    bpl, bpl
0x180002caf  jz      short loc_180002CBC
0x180002cb1  mov     rdx, rbx; unsigned __int16 *
0x180002cb4  mov     rcx, rdi; this
0x180002cb7  call    ?SetSize@SipFile@@QEAAKPEAG@Z; SipFile::SetSize(ushort *)
0x180002cbc  xor     eax, eax
0x180002cbe  mov     rbx, [rsp+38h+arg_0]
0x180002cc3  mov     rbp, [rsp+38h+arg_18]
0x180002cc8  add     rsp, 20h
0x180002ccc  pop     r14
0x180002cce  pop     rdi
0x180002ccf  pop     rsi
0x180002cd0  retn
0x180002cd1  mov     bpl, 1
0x180002cd4  sub     rbx, 4
0x180002cd8  jmp     short loc_180002C9D
```
