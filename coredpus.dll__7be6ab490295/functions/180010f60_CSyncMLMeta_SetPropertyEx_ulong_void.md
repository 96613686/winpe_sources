# CSyncMLMeta::SetPropertyEx(ulong,void *)

- ea: `0x180010f60`
- end: `0x18001102b`
- name: `?SetPropertyEx@CSyncMLMeta@@AEAAJKPEAX@Z`
- size: `203`
- prototype: `int(CSyncMLMeta *__hidden this, unsigned int, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180021ae0`

## callees

- `0x180002550`
- `0x180010f60`
- `0x180011034`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010f9c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010f9c`
- `DMCmnUtils!CopyString` at `0x180010fb8`
- `DMCmnUtils!CopyString` at `0x180010ff5`
- `DMCmnUtils!CopyString` at `0x180010fb8`
- `DMCmnUtils!CopyString` at `0x180010ff5`

## pseudocode

```c
__int64 __fastcall CSyncMLMeta::SetPropertyEx(CSyncMLMeta *this, unsigned int a2, const unsigned __int16 *a3)
{
  __int64 v4; // rdi
  int v6; // edx
  const unsigned __int16 **v7; // rbx
  unsigned __int16 *v8; // rcx
  unsigned __int64 v10; // [rsp+68h] [rbp+20h] BYREF

  v4 = a2;
  if ( !(unsigned int)CSyncMLMeta::IsImplementedProp(a2) )
    return (unsigned int)-2147467263;
  v7 = (const unsigned __int16 **)((char *)this + 8 * v4);
  if ( (unsigned int)v4 > 4 )
  {
    v6 = 0;
    *v7 = a3;
LABEL_10:
    *((_DWORD *)this + 32) |= 1 << v4;
    return (unsigned int)v6;
  }
  v8 = (unsigned __int16 *)*v7;
  v10 = 0;
  LocalFree(v8);
  *v7 = 0;
  v6 = CopyString(a3, 0xFFFFFFFF, (unsigned __int16 **)this + v4);
  if ( a3 )
  {
    v6 = StringCchLengthW(a3, 0x7FFFFFFFu, &v10);
    if ( v6 >= 0 )
    {
      if ( v10 )
      {
        v6 = CopyString(a3, v10, (unsigned __int16 **)this + v4);
        if ( v6 >= 0 )
          goto LABEL_10;
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180010f60  push    rbx
0x180010f62  push    rsi
0x180010f63  push    rdi
0x180010f64  push    r14
0x180010f66  sub     rsp, 28h
0x180010f6a  mov     r14, rcx
0x180010f6d  mov     edi, edx
0x180010f6f  mov     ecx, edx; unsigned int
0x180010f71  mov     rsi, r8
0x180010f74  call    ?IsImplementedProp@CSyncMLMeta@@CAHK@Z; CSyncMLMeta::IsImplementedProp(ulong)
0x180010f79  test    eax, eax
0x180010f7b  jnz     short loc_180010F87
0x180010f7d  mov     edx, 80004001h
0x180010f82  jmp     loc_18001101E
0x180010f87  lea     rbx, [r14+rdi*8]
0x180010f8b  cmp     edi, 4
0x180010f8e  ja      short loc_180011009
0x180010f90  mov     rcx, [rbx]; hMem
0x180010f93  mov     [rsp+48h+arg_18], 0
0x180010f9c  call    cs:__imp_LocalFree
0x180010fa3  nop     dword ptr [rax+rax+00h]
0x180010fa8  mov     r8, rbx
0x180010fab  mov     qword ptr [rbx], 0
0x180010fb2  or      edx, 0FFFFFFFFh
0x180010fb5  mov     rcx, rsi
0x180010fb8  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x180010fbf  nop     dword ptr [rax+rax+00h]
0x180010fc4  mov     edx, eax
0x180010fc6  test    rsi, rsi
0x180010fc9  jz      short loc_18001101E
0x180010fcb  lea     r8, [rsp+48h+arg_18]; unsigned __int64 *
0x180010fd0  mov     edx, 7FFFFFFFh; unsigned __int64
0x180010fd5  mov     rcx, rsi; unsigned __int16 *
0x180010fd8  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180010fdd  mov     edx, eax
0x180010fdf  test    eax, eax
0x180010fe1  js      short loc_18001101E
0x180010fe3  mov     rax, [rsp+48h+arg_18]
0x180010fe8  test    rax, rax
0x180010feb  jz      short loc_18001101E
0x180010fed  mov     r8, rbx
0x180010ff0  mov     edx, eax
0x180010ff2  mov     rcx, rsi
0x180010ff5  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x180010ffc  nop     dword ptr [rax+rax+00h]
0x180011001  mov     edx, eax
0x180011003  test    eax, eax
0x180011005  jns     short loc_18001100E
0x180011007  jmp     short loc_18001101E
0x180011009  xor     edx, edx
0x18001100b  mov     [rbx], rsi
0x18001100e  mov     ecx, edi
0x180011010  mov     eax, 1
0x180011015  shl     eax, cl
0x180011017  or      [r14+80h], eax
0x18001101e  mov     eax, edx
0x180011020  add     rsp, 28h
0x180011024  pop     r14
0x180011026  pop     rdi
0x180011027  pop     rsi
0x180011028  pop     rbx
0x180011029  retn
```
