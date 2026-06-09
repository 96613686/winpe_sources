# CDispTypeInfo::StrICmp(ushort *,int,ushort *,int)

- ea: `0x180040b70`
- end: `0x180040bd6`
- name: `?StrICmp@CDispTypeInfo@@QEAAHPEAGH0H@Z`
- size: `102`
- prototype: `int(CDispTypeInfo *__hidden this, unsigned __int16 *, int, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180040a20`

## callees

- `0x180007590`
- `0x18002b020`
- `0x180040b70`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180040baa`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180040baa`

## pseudocode

```c
__int64 __fastcall CDispTypeInfo::StrICmp(CDispTypeInfo *this, unsigned __int16 *a2, int a3, unsigned __int16 *a4)
{
  DWORD v8; // edx

  if ( (unsigned int)IsDBCS(*((unsigned int *)this + 3)) )
    v8 = (unsigned int)IsJapan(*((unsigned int *)this + 3)) != 0 ? 196609 : 131073;
  else
    v8 = 3;
  return (unsigned int)(CompareStringW(*((_DWORD *)this + 3), v8, a2, a3, a4, -1) - 2);
}

```

## disassembly

```asm
0x180040b70  push    rbx
0x180040b72  push    rbp
0x180040b73  push    rsi
0x180040b74  push    rdi
0x180040b75  sub     rsp, 38h
0x180040b79  mov     rbx, rcx
0x180040b7c  mov     rdi, r9
0x180040b7f  mov     ecx, [rcx+0Ch]
0x180040b82  mov     esi, r8d
0x180040b85  mov     rbp, rdx
0x180040b88  call    IsDBCS
0x180040b8d  test    eax, eax
0x180040b8f  jnz     short loc_180040BBC
0x180040b91  lea     edx, [rax+3]; dwCmpFlags
0x180040b94  mov     ecx, [rbx+0Ch]; Locale
0x180040b97  mov     r9d, esi; cchCount1
0x180040b9a  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x180040ba2  mov     r8, rbp; lpString1
0x180040ba5  mov     [rsp+58h+lpString2], rdi; lpString2
0x180040baa  call    cs:__imp_CompareStringW
0x180040bb0  sub     eax, 2
0x180040bb3  add     rsp, 38h
0x180040bb7  pop     rdi
0x180040bb8  pop     rsi
0x180040bb9  pop     rbp
0x180040bba  pop     rbx
0x180040bbb  retn
0x180040bbc  mov     ecx, [rbx+0Ch]
0x180040bbf  call    IsJapan
0x180040bc4  neg     eax
0x180040bc6  sbb     edx, edx
0x180040bc8  and     edx, 10000h
0x180040bce  add     edx, 20001h
0x180040bd4  jmp     short loc_180040B94
```
