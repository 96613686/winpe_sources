# GetEmfFromWmf(IStream *,uint,MetafileHeader &,HENHMETAFILE__ * *,WmfCompatibilityMode)

- ea: `0x18010c470`
- end: `0x18010c555`
- name: `?GetEmfFromWmf@@YA?AW4Status@@PEAUIStream@@IAEAVMetafileHeader@@PEAPEAUHENHMETAFILE__@@W4WmfCompatibilityMode@@@Z`
- size: `229`
- prototype: `enum Status __high(struct IStream *, unsigned int, struct MetafileHeader *, HENHMETAFILE *, enum WmfCompatibilityMode)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000b8c0`

## callees

- `0x18001f950`
- `0x1800a6a9c`
- `0x1800a723c`
- `0x1800d8740`
- `0x1800e5044`
- `0x18010c470`

## import_xrefs

- `GDI32!GetMetaFileBitsEx` at `0x18010c4d9`
- `GDI32!GetMetaFileBitsEx` at `0x18010c4d9`
- `GDI32!DeleteMetaFile` at `0x18010c525`
- `GDI32!DeleteMetaFile` at `0x18010c525`

## pseudocode

```c
__int64 __fastcall GetEmfFromWmf(struct IStream *a1, unsigned int a2, __int64 a3, HENHMETAFILE *a4, int a5)
{
  unsigned int MetafileHeader; // r14d
  HMETAFILE Emf; // rdi
  void *v10; // rax
  __int64 v11; // rbx
  UINT MetaFileBits; // r9d
  HENHMETAFILE EmfFromWmfData; // rax

  if ( !a1 || !a4 )
    return 2;
  *a4 = 0;
  MetafileHeader = 7;
  Emf = (HMETAFILE)GetEmf(a1, 1, a2);
  if ( Emf )
  {
    v10 = (void *)GpMallocEx(a2, 0);
    v11 = (__int64)v10;
    if ( v10 )
    {
      MetaFileBits = GetMetaFileBitsEx(Emf, a2, v10);
      if ( MetaFileBits )
      {
        EmfFromWmfData = GetEmfFromWmfData(Emf, 0, v11, MetaFileBits, a5);
        *a4 = EmfFromWmfData;
        if ( EmfFromWmfData )
          MetafileHeader = GetMetafileHeader(EmfFromWmfData, a3, 0);
      }
      GpFree(v11);
    }
    DeleteMetaFile(Emf);
  }
  return MetafileHeader;
}

```

## disassembly

```asm
0x18010c470  mov     [rsp+arg_0], rbx
0x18010c475  mov     [rsp+arg_8], rbp
0x18010c47a  mov     [rsp+arg_10], rsi
0x18010c47f  push    rdi
0x18010c480  push    r14
0x18010c482  push    r15
0x18010c484  sub     rsp, 30h
0x18010c488  mov     ebp, edx
0x18010c48a  mov     rsi, r9
0x18010c48d  mov     r15, r8
0x18010c490  test    rcx, rcx
0x18010c493  jz      loc_18010C536
0x18010c499  test    r9, r9
0x18010c49c  jz      loc_18010C536
0x18010c4a2  and     qword ptr [r9], 0
0x18010c4a6  mov     r14d, 7
0x18010c4ac  mov     r8d, ebp; unsigned int
0x18010c4af  lea     edx, [r14-6]; int
0x18010c4b3  call    ?GetEmf@@YAPEAUHENHMETAFILE__@@PEAUIStream@@HI@Z; GetEmf(IStream *,int,uint)
0x18010c4b8  mov     rdi, rax
0x18010c4bb  test    rax, rax
0x18010c4be  jz      short loc_18010C531
0x18010c4c0  mov     ecx, ebp
0x18010c4c2  xor     edx, edx
0x18010c4c4  call    GpMallocEx
0x18010c4c9  mov     rbx, rax
0x18010c4cc  test    rax, rax
0x18010c4cf  jz      short loc_18010C522
0x18010c4d1  mov     r8, rax; lpData
0x18010c4d4  mov     edx, ebp; cbBuffer
0x18010c4d6  mov     rcx, rdi; hMF
0x18010c4d9  call    cs:__imp_GetMetaFileBitsEx
0x18010c4e0  nop     dword ptr [rax+rax+00h]
0x18010c4e5  mov     r9d, eax
0x18010c4e8  test    eax, eax
0x18010c4ea  jz      short loc_18010C51A
0x18010c4ec  mov     eax, [rsp+48h+arg_20]
0x18010c4f0  mov     r8, rbx
0x18010c4f3  xor     edx, edx
0x18010c4f5  mov     [rsp+48h+var_28], eax
0x18010c4f9  mov     rcx, rdi
0x18010c4fc  call    ?GetEmfFromWmfData@@YAPEAUHENHMETAFILE__@@PEAUHMETAFILE__@@PEBUWmfPlaceableFileHeader@@PEAEIW4WmfCompatibilityMode@@@Z; GetEmfFromWmfData(HMETAFILE__ *,WmfPlaceableFileHeader const *,uchar *,uint,WmfCompatibilityMode)
0x18010c501  mov     [rsi], rax
0x18010c504  test    rax, rax
0x18010c507  jz      short loc_18010C51A
0x18010c509  xor     r8d, r8d
0x18010c50c  mov     rdx, r15
0x18010c50f  mov     rcx, rax
0x18010c512  call    ?GetMetafileHeader@@YA?AW4Status@@PEAUHENHMETAFILE__@@AEAVMetafileHeader@@PEAH@Z; GetMetafileHeader(HENHMETAFILE__ *,MetafileHeader &,int *)
0x18010c517  mov     r14d, eax
0x18010c51a  mov     rcx, rbx
0x18010c51d  call    GpFree
0x18010c522  mov     rcx, rdi; hmf
0x18010c525  call    cs:__imp_DeleteMetaFile
0x18010c52c  nop     dword ptr [rax+rax+00h]
0x18010c531  mov     eax, r14d
0x18010c534  jmp     short loc_18010C53B
0x18010c536  mov     eax, 2
0x18010c53b  mov     rbx, [rsp+48h+arg_0]
0x18010c540  mov     rbp, [rsp+48h+arg_8]
0x18010c545  mov     rsi, [rsp+48h+arg_10]
0x18010c54a  add     rsp, 30h
0x18010c54e  pop     r15
0x18010c550  pop     r14
0x18010c552  pop     rdi
0x18010c553  retn
```
