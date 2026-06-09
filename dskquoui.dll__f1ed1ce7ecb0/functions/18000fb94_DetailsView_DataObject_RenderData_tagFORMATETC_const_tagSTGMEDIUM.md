# DetailsView::DataObject::RenderData(tagFORMATETC const *,tagSTGMEDIUM *)

- ea: `0x18000fb94`
- end: `0x18000fc4c`
- name: `?RenderData@DataObject@DetailsView@@QEAAJPEBUtagFORMATETC@@PEAUtagSTGMEDIUM@@@Z`
- size: `184`
- prototype: `__int64 __fastcall(DetailsView::DataObject *__hidden this, const struct tagFORMATETC *, struct tagSTGMEDIUM *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000af40`

## callees

- `0x18000f994`
- `0x18000fb94`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000fbc3`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000fbc3`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x18000fc1b`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x18000fc1b`

## pseudocode

```c
__int64 __fastcall DetailsView::DataObject::RenderData(
        LPSTREAM *this,
        struct tagFORMATETC *a2,
        struct tagSTGMEDIUM *a3)
{
  HBITMAP *v3; // r14
  HRESULT HGlobalFromStream; // edi

  v3 = (HBITMAP *)(this + 3);
  if ( (a2->tymed & 4) == 0 && (a2->tymed & 1) == 0
    || (HGlobalFromStream = CreateStreamOnHGlobal(0, 1, this + 3), HGlobalFromStream >= 0) )
  {
    HGlobalFromStream = DetailsView::DataObject::RenderData(
                          (DetailsView::DataObject *)this,
                          (struct IStream *)a2,
                          a2->cfFormat);
    if ( HGlobalFromStream < 0 )
      goto LABEL_9;
    if ( (a2->tymed & 4) != 0 )
    {
      a3->hBitmap = *v3;
      a3->tymed = 4;
      a3->pUnkForRelease = 0;
      return (unsigned int)HGlobalFromStream;
    }
    if ( (a2->tymed & 1) != 0 )
    {
      a3->tymed = 1;
      a3->pUnkForRelease = 0;
      HGlobalFromStream = GetHGlobalFromStream((LPSTREAM)*v3, &a3->hMetaFilePict);
      if ( HGlobalFromStream < 0 )
      {
LABEL_9:
        (*(void (__fastcall **)(HBITMAP))(*(_QWORD *)*v3 + 16LL))(*v3);
        a3->hBitmap = 0;
      }
    }
  }
  return (unsigned int)HGlobalFromStream;
}

```

## disassembly

```asm
0x18000fb94  push    rbx
0x18000fb96  push    rbp
0x18000fb97  push    rdi
0x18000fb98  push    r14
0x18000fb9a  push    r15
0x18000fb9c  sub     rsp, 20h
0x18000fba0  test    byte ptr [rdx+18h], 4
0x18000fba4  lea     r14, [rcx+18h]
0x18000fba8  mov     rbx, r8
0x18000fbab  mov     r15, rdx
0x18000fbae  mov     rbp, rcx
0x18000fbb1  jnz     short loc_18000FBB9
0x18000fbb3  test    byte ptr [rdx+18h], 1
0x18000fbb7  jz      short loc_18000FBCF
0x18000fbb9  mov     r8, r14; ppstm
0x18000fbbc  mov     edx, 1; fDeleteOnRelease
0x18000fbc1  xor     ecx, ecx; hGlobal
0x18000fbc3  call    cs:__imp_CreateStreamOnHGlobal
0x18000fbc9  mov     edi, eax
0x18000fbcb  test    eax, eax
0x18000fbcd  js      short loc_18000FC3E
0x18000fbcf  movzx   r8d, word ptr [r15]; unsigned __int16
0x18000fbd3  mov     rcx, rbp; this
0x18000fbd6  call    ?RenderData@DataObject@DetailsView@@AEAAJPEAUIStream@@G@Z; DetailsView::DataObject::RenderData(IStream *,ushort)
0x18000fbdb  mov     edi, eax
0x18000fbdd  test    eax, eax
0x18000fbdf  js      short loc_18000FC27
0x18000fbe1  test    byte ptr [r15+18h], 4
0x18000fbe6  jz      short loc_18000FBFF
0x18000fbe8  mov     rcx, [r14]
0x18000fbeb  mov     [rbx+8], rcx
0x18000fbef  mov     dword ptr [rbx], 4
0x18000fbf5  mov     qword ptr [rbx+10h], 0
0x18000fbfd  jmp     short loc_18000FC3E
0x18000fbff  test    byte ptr [r15+18h], 1
0x18000fc04  jz      short loc_18000FC3E
0x18000fc06  mov     dword ptr [rbx], 1
0x18000fc0c  lea     rdx, [rbx+8]; phglobal
0x18000fc10  mov     qword ptr [rbx+10h], 0
0x18000fc18  mov     rcx, [r14]; pstm
0x18000fc1b  call    cs:__imp_GetHGlobalFromStream
0x18000fc21  mov     edi, eax
0x18000fc23  test    eax, eax
0x18000fc25  jns     short loc_18000FC3E
0x18000fc27  mov     rcx, [r14]
0x18000fc2a  mov     rax, [rcx]
0x18000fc2d  mov     rax, [rax+10h]
0x18000fc31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc36  mov     qword ptr [rbx+8], 0
0x18000fc3e  mov     eax, edi
0x18000fc40  add     rsp, 20h
0x18000fc44  pop     r15
0x18000fc46  pop     r14
0x18000fc48  pop     rdi
0x18000fc49  pop     rbp
0x18000fc4a  pop     rbx
0x18000fc4b  retn
```
