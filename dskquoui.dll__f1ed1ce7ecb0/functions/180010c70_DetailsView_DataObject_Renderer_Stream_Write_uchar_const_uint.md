# DetailsView::DataObject::Renderer::Stream::Write(uchar const *,uint)

- ea: `0x180010c70`
- end: `0x180010ce2`
- name: `?Write@Stream@Renderer@DataObject@DetailsView@@QEAAXPEBEI@Z`
- size: `114`
- prototype: `void __fastcall(DetailsView::DataObject::Renderer::Stream *__hidden this, const unsigned __int8 *, unsigned int)`
- caller_count: `14`
- callee_count: `4`
- tags: ``

## callers

- `0x180008060`
- `0x180008150`
- `0x1800083d0`
- `0x180008410`
- `0x180008460`
- `0x180008490`
- `0x180008720`
- `0x180008890`
- `0x180008970`
- `0x180008bc0`
- `0x180008c30`
- `0x18000a960`
- `0x18000a9b0`
- `0x180010c38`

## callees

- `0x180006f64`
- `0x180010c70`
- `0x18001ce34`
- `0x18001f010`

## pseudocode

```c
void __fastcall DetailsView::DataObject::Renderer::Stream::Write(
        DetailsView::DataObject::Renderer::Stream *this,
        const unsigned __int8 *a2,
        __int64 a3)
{
  __int64 v3; // rcx
  int v4; // eax
  __int64 v5; // rdx
  _BYTE pExceptionObject[24]; // [rsp+30h] [rbp-18h] BYREF
  int v7; // [rsp+50h] [rbp+8h] BYREF

  v3 = *(_QWORD *)this;
  v7 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, const unsigned __int8 *, __int64, int *))(*(_QWORD *)v3 + 32LL))(
         v3,
         a2,
         a3,
         &v7);
  if ( v4 )
  {
    if ( v4 == -2147287035 )
    {
      v5 = 4;
    }
    else if ( v4 == -2147287011 )
    {
      v5 = 5;
    }
    else
    {
      v5 = 2;
      if ( v4 == -2147286928 )
        v5 = 3;
    }
    CFileException::CFileException(pExceptionObject, v5);
    throw (CFileException *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x180010c70  sub     rsp, 48h
0x180010c74  mov     rcx, [rcx]
0x180010c77  lea     r9, [rsp+48h+arg_0]
0x180010c7c  mov     [rsp+48h+arg_0], 0
0x180010c84  mov     rax, [rcx]
0x180010c87  mov     rax, [rax+20h]
0x180010c8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c90  test    eax, eax
0x180010c92  jnz     short loc_180010C99
0x180010c94  add     rsp, 48h
0x180010c98  retn
0x180010c99  cmp     eax, 80030005h
0x180010c9e  jz      short loc_180010CC1
0x180010ca0  cmp     eax, 8003001Dh
0x180010ca5  jz      short loc_180010CBA
0x180010ca7  mov     edx, 2
0x180010cac  cmp     eax, 80030070h
0x180010cb1  jnz     short loc_180010CC6
0x180010cb3  mov     edx, 3
0x180010cb8  jmp     short loc_180010CC6
0x180010cba  mov     edx, 5
0x180010cbf  jmp     short loc_180010CC6
0x180010cc1  mov     edx, 4
0x180010cc6  lea     rcx, [rsp+48h+pExceptionObject]
0x180010ccb  call    ??0CFileException@@QEAA@W4reason@0@PEBGK@Z; CFileException::CFileException(CFileException::reason,ushort const *,ulong)
0x180010cd0  lea     rdx, _TI2?AVCFileException@@; pThrowInfo
0x180010cd7  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180010cdc  call    _CxxThrowException_0
```
