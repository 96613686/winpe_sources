# BytesToVariantArray(uchar *,ulong,tagVARIANT *)

- ea: `0x180075d6c`
- end: `0x180075e2c`
- name: `?BytesToVariantArray@@YAJPEAEKPEAUtagVARIANT@@@Z`
- size: `192`
- prototype: `__int64 __fastcall(unsigned __int8 *Src, unsigned int, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180076938`

## callees

- `0x180002d26`
- `0x180075d6c`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x180075da2`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180075da2`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180075e01`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180075e01`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180075dbe`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180075dbe`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180075de5`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180075de5`

## pseudocode

```c
__int64 __fastcall BytesToVariantArray(unsigned __int8 *Src, __int64 a2, struct tagVARIANT *a3)
{
  SAFEARRAY *v5; // rax
  SAFEARRAY *v6; // rdi
  HRESULT v7; // ebx
  void *ppvData; // [rsp+20h] [rbp-18h] BYREF
  size_t Size; // [rsp+58h] [rbp+20h] BYREF

  ppvData = 0;
  Size = 60;
  v5 = SafeArrayCreate(0x11u, 1u, (SAFEARRAYBOUND *)&Size);
  v6 = v5;
  if ( v5 )
  {
    v7 = SafeArrayAccessData(v5, &ppvData);
    if ( v7 < 0 )
    {
      SafeArrayDestroy(v6);
    }
    else
    {
      memcpy_0(ppvData, Src, (unsigned int)Size);
      SafeArrayUnaccessData(v6);
      v7 = 0;
      a3->vt = 8209;
      a3->llVal = (LONGLONG)v6;
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180075d6c  mov     rax, rsp
0x180075d6f  mov     [rax+8], rbx
0x180075d73  mov     [rax+10h], rbp
0x180075d77  mov     [rax+18h], rsi
0x180075d7b  push    rdi
0x180075d7c  sub     rsp, 30h
0x180075d80  and     qword ptr [rax-18h], 0
0x180075d85  mov     rbp, rcx
0x180075d88  and     dword ptr [rax+24h], 0
0x180075d8c  mov     ecx, 11h; vt
0x180075d91  mov     rsi, r8
0x180075d94  mov     dword ptr [rax+20h], 3Ch ; '<'
0x180075d9b  lea     r8, [rax+20h]; rgsabound
0x180075d9f  lea     edx, [rcx-10h]; cDims
0x180075da2  call    cs:__imp_SafeArrayCreate
0x180075da9  nop     dword ptr [rax+rax+00h]
0x180075dae  mov     rdi, rax
0x180075db1  test    rax, rax
0x180075db4  jz      short loc_180075E0F
0x180075db6  lea     rdx, [rsp+38h+ppvData]; ppvData
0x180075dbb  mov     rcx, rax; psa
0x180075dbe  call    cs:__imp_SafeArrayAccessData
0x180075dc5  nop     dword ptr [rax+rax+00h]
0x180075dca  mov     ebx, eax
0x180075dcc  test    eax, eax
0x180075dce  js      short loc_180075DFE
0x180075dd0  mov     r8d, dword ptr [rsp+38h+Size]; Size
0x180075dd5  mov     rdx, rbp; Src
0x180075dd8  mov     rcx, [rsp+38h+ppvData]; void *
0x180075ddd  call    memcpy_0
0x180075de2  mov     rcx, rdi; psa
0x180075de5  call    cs:__imp_SafeArrayUnaccessData
0x180075dec  nop     dword ptr [rax+rax+00h]
0x180075df1  xor     ebx, ebx
0x180075df3  mov     word ptr [rsi], 2011h
0x180075df8  mov     [rsi+8], rdi
0x180075dfc  jmp     short loc_180075E14
0x180075dfe  mov     rcx, rdi; psa
0x180075e01  call    cs:__imp_SafeArrayDestroy
0x180075e08  nop     dword ptr [rax+rax+00h]
0x180075e0d  jmp     short loc_180075E14
0x180075e0f  mov     ebx, 8007000Eh
0x180075e14  mov     rbp, [rsp+38h+arg_8]
0x180075e19  mov     eax, ebx
0x180075e1b  mov     rbx, [rsp+38h+arg_0]
0x180075e20  mov     rsi, [rsp+38h+arg_10]
0x180075e25  add     rsp, 30h
0x180075e29  pop     rdi
0x180075e2a  retn
```
