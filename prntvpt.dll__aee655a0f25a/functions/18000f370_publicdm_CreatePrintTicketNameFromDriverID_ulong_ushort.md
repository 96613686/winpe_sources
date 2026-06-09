# publicdm::CreatePrintTicketNameFromDriverID(ulong,ushort * *)

- ea: `0x18000f370`
- end: `0x18000f404`
- name: `?CreatePrintTicketNameFromDriverID@publicdm@@YAJKPEAPEAG@Z`
- size: `148`
- prototype: `__int64 __fastcall(publicdm *__hidden this, unsigned int, unsigned __int16 **)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b5a0`
- `0x18000c0fc`
- `0x18001e3b0`
- `0x18001e520`
- `0x18001ecf0`

## callees

- `0x180004acc`
- `0x1800056e0`
- `0x180007660`
- `0x18000f370`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000f394`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f394`

## pseudocode

```c
__int64 __fastcall publicdm::CreatePrintTicketNameFromDriverID(
        publicdm *this,
        unsigned __int16 **a2,
        unsigned __int16 **a3)
{
  unsigned int v3; // ebx
  BSTR v5; // rax
  unsigned __int16 *v6; // rdi
  int v7; // ebx
  unsigned __int16 *v9; // [rsp+40h] [rbp+18h] BYREF

  v3 = (unsigned int)this;
  v9 = 0;
  v5 = SysAllocString(L"User##########");
  NCoreLibrary::TAutoPtrBSTR::operator=(&v9, v5);
  v6 = v9;
  if ( v9 )
  {
    v7 = StringCchPrintfW(v9, 0xFu, L"User%.10d", v3);
    if ( v7 >= 0 )
    {
      v9 = 0;
      *a2 = v6;
    }
    else
    {
      v7 = -2147024809;
    }
  }
  else
  {
    v7 = -2147024882;
  }
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v9);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000f370  mov     [rsp+arg_0], rbx
0x18000f375  mov     [rsp+arg_8], rsi
0x18000f37a  push    rdi
0x18000f37b  sub     rsp, 20h
0x18000f37f  mov     ebx, ecx
0x18000f381  mov     [rsp+28h+arg_10], 0
0x18000f38a  lea     rcx, aUser; "User##########"
0x18000f391  mov     rsi, rdx
0x18000f394  call    cs:__imp_SysAllocString
0x18000f39a  mov     rdx, rax
0x18000f39d  lea     rcx, [rsp+28h+arg_10]
0x18000f3a2  call    ??4TAutoPtrBSTR@NCoreLibrary@@QEAAPEAGPEAG@Z; NCoreLibrary::TAutoPtrBSTR::operator=(ushort *)
0x18000f3a7  mov     rdi, [rsp+28h+arg_10]
0x18000f3ac  test    rdi, rdi
0x18000f3af  jz      short loc_18000F3E3
0x18000f3b1  mov     r9d, ebx
0x18000f3b4  lea     r8, aUser10d; "User%.10d"
0x18000f3bb  mov     edx, 0Fh; unsigned __int64
0x18000f3c0  mov     rcx, rdi; unsigned __int16 *
0x18000f3c3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000f3c8  mov     ebx, eax
0x18000f3ca  test    eax, eax
0x18000f3cc  jns     short loc_18000F3D5
0x18000f3ce  mov     ebx, 80070057h
0x18000f3d3  jmp     short loc_18000F3E8
0x18000f3d5  mov     [rsp+28h+arg_10], 0
0x18000f3de  mov     [rsi], rdi
0x18000f3e1  jmp     short loc_18000F3E8
0x18000f3e3  mov     ebx, 8007000Eh
0x18000f3e8  lea     rcx, [rsp+28h+arg_10]
0x18000f3ed  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18000f3f2  mov     rsi, [rsp+28h+arg_8]
0x18000f3f7  mov     eax, ebx
0x18000f3f9  mov     rbx, [rsp+28h+arg_0]
0x18000f3fe  add     rsp, 20h
0x18000f402  pop     rdi
0x18000f403  retn
```
